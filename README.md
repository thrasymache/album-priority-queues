# Album Priority Queues

A Django App for making a record of when music is played, and using that to 
influence when that music is suggested for subsequent play.

## Background

I have a substantial collection of music and have always preferred to listen to 
music that I have not recently heard rather than have anything "on repeat". I 
have enough music that it helps for me to have a shorter list to select from. 
There was a time when this meant taking time to move CDs from large organizers 
to a smaller one, and then returning them to the larger organizers after they 
had been played. Subsequently, I set up iTunes to attempt to do this for me 
automatically: I gave each album a star rating, except albums that I had heard
less than three times being left unrated. I then created smart playlists that
selected unrated music roughly if it had not been played in the past 3 months,
5 star rated music if it had not been played in 6 months, 4 star rated music if 
it had not been played in the past year and so on. I configured my iPod to sync
music on these playlists, (which had the side-effect that as soon as the iPod 
was synced after i played an album, it was removed from the iPod). Later, in 
recognition of the fact that some albums had been mis-rated so that I had not 
selected to listen to them despite their being on the playlist for an extended 
period of time, I created a second set of playlists to identify these albums so 
that I could fix their ratings. I happily used this system for a number of 
years, since it was such a large improvement over manually selecting CDs from 
an organizer. However, it had a number of issues:

   1. Separation of albums: iTunes records all of its information at the track
      level, while I generally listen to music an album at a time, playing the
     tracks in order. Various things could cause tracks to become separated 
     from the rest of their album, such as myself or anyone else ever listening 
     to a track by itself, and if an album wasn't played from start to finish in 
     a single day, then there was a magical moment when the iPod could be 
     synced, (several months later), which would cause only the first several 
     tracks to be offered. iTunes provided no warning of this, so I had to know 
     the albums well enough to identify partial albums, and manually fix this.
   1. Only iTunes support: all of this required iTunes and iPods to be the only
     players that I used to listen to my music, which has become a problem as I 
     primarily use Linux computers and Android now.
   1. Maintenance of the ratings had to be done manually as did adjusting the 
     expected time for each rating, both as I acquired more music, and as I 
     listened more and less. This was enough maintenance that I never took the 
     effort to go further, and make it easier to select particular types of 
     music, which was likely partly caused by the fact that I was generally 
     limited to the iPod interface.
   1. Guessed ratings with large granularity: initially I just had to go through 
     the music collection and for each album guess how frequently I wanted to 
     play it, which gets stuck feeling that you are judging the overall quality 
     of the music rather than what you find yourself wanting to hear more or 
     less often, something that is encouraged by them being a count of stars. 
     When you get past the sense that you are giving an abstract quality it is 
     likely to be the strength of your feelings about the music rather than how 
     often you want to play it (for instance I really enjoy musical soundtracks,
     but because they remind me of a plot arc and action not visible, I find 
     them incredibly distracting, so there are very few tasks I can do while 
     listening to them, and so I listen to them very rarely). My setup has 
     enormous jumps between different ratings, which helps the fact that they 
     are guesses, but also emphasizes how this is a problem.
   1. Binary in and out: I had to create a completely separate set of playlists 
     to identify albums that were not being listened to in twice the expected 
     time and I never bothered to create a third set of playlists, 
   1. A lack of queryability - "About how much music did I listen to last 
     year?", is something that you can ask of iTunes, but is a huge nuisance 
     involving playlists for each of a number of bins of play counts and 
     requires you to keep separate records. It provides no help in answering 
     really valuable questions, like "what categories of music should I seek 
     more of?", other than its internal recommendation system.
   
On the other had there are a few advantages that I will not be able to recreate:

   1. The setup requires selecting a few dozen options from drop-down menus, and 
   no specific programming.
   1. Automated record-keeping: the iPod and iTunes will keep track of what you 
   played when without any additional effort.
   1. Automated iPod syncing: if all goes well, then getting the current list of 
   music on an iPod only requires clicking the sync button when connected. If it
   goes badly, then the worst that is needed is adjusting a half-dozen 
   parameters until the selected music fits on the iPod or meets some other
   criteria of not being too much.
   
## Plans

   * The ability to record the date on which an album was played
   * The ability to record one or more albums (with specific tracks) as the thing 
     currently being played.
   * The ability to import a listing of albums, preferably with ratings and 
     play counts from some sort of iTunes export.
   * Listings of music that has not been played in an amount of time that scales 
     with its expected frequency of play.
   * An attempt to adjust the expected frequency of play based upon the 
     historical frequency of play (perhaps it just divides the play count by the 
     addition date and lets you add a modifier from there).
   * The ability to filter the listings by other criteria, such as type of music, 
     and the ability to scale the listing so that rather than playing music being
     "due" at a particular time, you can request a shorter list of those tracks 
     that haven't been played in an extra long time, or a longer list that 
     includes tracks that "aren't due" yet.

While I will set the system up to support multiple users, it is not my current
intention to be providing this as an available web service to others, until 
there is a compelling reason otherwise, I'll host my own copy privately and 
provide the source code publically for others to be able to do the same.