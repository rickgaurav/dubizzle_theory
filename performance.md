#Ways to Improve Performace:

## Backend 

1. First and foremost is to write efficient queries which hit the database. Using ORM, developers often overlook the queries that get generated. ORM constructs should be used in such a way that number of joins could be kept minimum.
2. Database schema design should be given a lot of thought and should be designed in such a way that queries could be written efficiently.
3. Whichever fields are going to be used to fetch records should be indexed properly and can make queries really fast.
4. If traffic is really high, then some caching mechanism should be used to cache requests. BUT there is always an overhead of maintaining cache.
5. Wherever heavy DB operations are required try to make them asynchronous. This avoid unnecessary waiting at front end when it is already known that the API will take time.

## Frontend

1. Minimize number of HTTP requests made to fetch resources, data etc.
2. Enable browser caching so that any subsequent visit to website after first visit may become faster. Loading the website first time will cache some resources on browser and on subsequent visits, the http calls to thise resource can be prevented, making the page load faster.
3. Minify resources(HTML, CSS and Javascript): For developers understanding we write modular code. We divide the code in chunks that is understandable to humans viz developers. But browser doesn't need such structured code. So the code should be minified to remove all the extra characters, spaces, comments etc to reduce the size of the resource being served.
4. Optimize Images: Do not just use larger images and set their width and height even though you need a smaller image. Larger image takes time to load and hence increase the page load time. Also if possible use fonts, SVGs, sprites wherver possible instead of images. Also in code do not leave src attribute to be equal to an empty string as it result in an unnecessary http call.
5. Defer parsing of Javascript: Javascript should not be loaded in head of html document as it defers loading of html document. Instead Javascript should be loaded at the end of body tag as it does not block loading ofpage just because javascript has not laoded.
6. Use Content Delivery Notwork: Traditionally a server stores a copy of the website and when a user request for it from anywhere, the server serves it. The time it takes for user to receive the response depends on how far from server is the user located. To overcome this we should use CDN which keeps multiple copies of site on different servers located across the world. So when a user request for site it is served from the server closes to the user reducing load time significantly.
7. Use Progressive loading: It does not pace up the loading time of site but the nature of loading actually gives a feel to user as if the site is loading faster since the blank screen or loading screen is there for a very minimal time and then the fields are there with some loading sign, which is replaces with actual content when it is available.
8. Bundle resources: We should bundle all our javascript files into one minimized and compressed bundle and should be served in on http call.
