# SageMathCloud virtual office hours -- Feb 6, 2014

Video: <https://www.youtube.com/watch?v=X2bpKQod4Qs>

## Status

### Backend -- stuff you hopefully won't notice much!

 - **ZFS backend architecture**: moved from ext4 on individual VM's + snapshots made using bup(=Python+git) to... ZFSonlinux with two replicas per data center, distributed using "consistent hashing".
   - took most of December; some of January.
   - spent a lot of time investigating and building another(geo-)distributed file system options on glusterfs, which I threw away
   - some growing pains with ZFS, but is working pretty well
   - finally we have high availability: if up to 5 machines that host your project fail, you can continue working
   - snapshots are local, so in the long run much MORE can be done with them -- much, much faster to browse.
   - open question: save all snapshots or trim old ones: e.g., save only hourly, daily, weekly
 - More systematic backend monitoring
 - Major VPN/network improvements (tinc scalability)
 - Google Compute Engine

### Usage

 - Increasing: number of accounts doubled in 89 days: today "There are 20310 accounts and 30183 projects."
 - Yesterday was maybe heaviest ever: 350-400 simultaneous clients most of the day.
 - If things feel slow, and your net connection is good, the most likely cause is somebody using a lot of resources on the same VM as you, e.g., a fork bomb, bitcoin mining, etc.
 - Very near future: cgroups, to allocate resources more fairly.

### Marketing

 - JMM in Baltimore -- booth
 - Poster -- see poster-surf.pdf that Hao Chen made.
 - Harald has been tracking websites that point to SMC -- lots of interesting courses.

### Commercialization

 - not yet ready, due to more needing to be implemented (e.g., cgroups) for this to make sense
 - not clear what/when/how to sell
 - first product will be a "private premium plan" available only to a select group of users we'll choose (and sold by Univ of Washington).
 - I will focus much more on commercialization starting in June 2014 (when my sabbatical starts)
