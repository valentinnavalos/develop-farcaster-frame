# develop-farcaster-frame
Farcaster Frame V2 development workflow

## REQUIEREMENTS
- ngrok installed
- warpcast account
- developer mode enabled on warpcast mobile app.

## DEVELOPMENT PROCESS

1. npm run dev

2. in another terminal: ngrok http http://localhost:3000

3. go to `warpcast mobile app > settings > developer > domains`

     you should generate a domain manifest. to achieve that we need to set ngrok http path as "Domain without protocol"
     and uncheck the "Include example frame definition" checkbox.

4. then this json generated and copied, should be set on our frontend to fill the following values (env vars):
     - NEXT_PUBLIC_FRAME_HEADER
     - NEXT_PUBLIC_FRAME_PAYLOAD
     - NEXT_PUBLIC_FRAME_SIGNATURE
  
5. for NEXT_PUBLIC_FRONTEND_URL we should place the ngrok http path.

6. after fill in the env vars, we can go back to `warpcast > settings > developer > domains` and check if everything is ok
     on Domains section, fill the "Domain without protocol" input with the ngrok http path, and instead of generate a new domain manifest, check domain status.
     if you successfully fill in the env vars, it should retrieve a Verified!

7. navigate to `warpcast mobile app > settings > developer > frames`
    and set launch frame values with the ngrok http path.
       example:
         URL: https://12345.ngrok.app
         SplashImage: https://1234.ngrok.app/favicon.ico
         SplashBgColor: #f7f7f7
   

