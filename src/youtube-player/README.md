# Angular YouTube Player component

This component provides a simple angular wrapper around the embed [YouTube player API](https://developers.google.com/youtube/iframe_api_reference). File any bugs against the [angular/components repo](https://github.com/angular/components/issues).

## Installation

To install, run `npm install @angular/youtube-player`.

## Usage

Follow the following instructions for setting up the YouTube player component:

- First, follow the [instructions for installing the API script](https://developers.google.com/youtube/iframe_api_reference#Getting_Started).
- Then make sure the API is available before bootstraping the YouTube Player component.
- Provide the video id by extracting it from the video URL.

## Example

If your video is found at https://www.youtube.com/watch?v=PRQCAL_RMVo, then your video id is `PRQCAL_RMVo`.

```typescript
// example-module.ts
import {NgModule} from '@angular/core';
import {YouTubePlayerModule} from '@angular/youtube-player';

@NgModule({
  imports: [
    YouTubePlayerModule,
  ],
  declarations: [YoutubePlayerExample],
})
export class YoutubePlayerExampleModule {
}

// example-component.ts
@Component({
  moduleId: module.id,
  template: '<youtube-player videoId="PRQCAL_RMVo" />',
  selector: 'youtube-player-example',
})
class YoutubePlayerExample implements OnInit {
  ngOnInit() {
    // This code loads the IFrame Player API code asynchronously, according to the instructions at
    // https://developers.google.com/youtube/iframe_api_reference#Getting_Started
    const tag = document.createElement('script');

    tag.src = "https://www.youtube.com/iframe_api";
    document.body.appendChild(tag);
  }
}

```

## API

Check out the [source](./youtube-player.ts) to read the API.
