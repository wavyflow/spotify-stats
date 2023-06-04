# Spotify Stats

Spotify-stats is a program for getting statistics such as favorite music lists as well as music currently playing on Spotify which provides results in the form of vector images (SVG) to be displayed to the user.

# Setup Guide

## Part 1. Vercel

1. Click button below to quick deploy and then fill in the form given

[![Deploy to Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/vermaysha/spotify-stats)

2. After deploy successfully click **Continue to Dashboard**
  <div><img src="https://i.imgur.com/dvizZZT.png"/></div>

3. You will get your domain like [https://sadasdsadsad.vercel.app/](https://sadasdsadsad.vercel.app/). This is the domain that will be used later

## Part 2. Configure Environment Vars

1. Navigate to [Spotify Dashboard](https://developer.spotify.com/dashboard/) and create new app
  <div><img src="https://i.imgur.com/N8HXIzN.png" alt="Create new app"/></div>

2. Click edit settings and add "{YOUR_BASE_URL}/api/login" and "{YOUR_BASE_URL}/api/login-callback" to the "Redirect URIs" section then save. Replace {YOUR_BASE_URL} by domain given by vercel
  <div><img src="https://i.imgur.com/WgWmAF8.png" alt="Redirect URIs"/></div>

3. Click '**SHOW CLIENT SECRET**' under Client ID. Copy both Client ID and Client Secret.

4. After getting the Client ID and Client Secret, please add them to the Environment vars by clicking Settings on the vercel dashboard page

  <div><img src="https://i.imgur.com/7EmXVWR.png" alt="Environment Variable"/></div>

5. Redeploy your application by click Deployment -> Redeploy

<div><img src="https://i.imgur.com/3hYLBXd.png"></div>

5. Next, we need to retrieve a Refresh Token through [Authoration Code flow](https://developer.spotify.com/documentation/general/guides/authorization-guide/#authorization-code-flow) by accessing "{YOUR_BASE_URL}/api/login" Replace {YOUR_BASE_URL} by domain given by vercel.


6. Then press **Agree** button, and you will be redirected to get your SPOTIFY_REFRESH_TOKEN

<div><img src="https://i.imgur.com/bWcNLog.png"></div>

7. Copy your refresh token and add to SPOTIFY_REFRESH_TOKEN env

<div><img src="https://i.imgur.com/DRJSHAO.png"></div>

8. After add env, please redeploy your application

<div><img src="https://i.imgur.com/3hYLBXd.png"></div>

9. Now you can access by {YOUR_BASE_URL}/api/now-playing or {YOUR_BASE_URL}/api/top-played, or embed as image

````html
<a href="{YOUR_BASE_URL}/api/now-playing?open=yes">
  <img src="{YOUR_BASE_URL}/api/now-playing" alt="Now Playing"/>
</a>

<a href="{YOUR_BASE_URL}/api/now-playing">
  <img src="{YOUR_BASE_URL}/api/now-playing" alt="Top Played" />
</a>
````

# LICENSE

MIT License

Copyright (c) 2022 Ashary Vermaysha

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
