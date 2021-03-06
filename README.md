# MultiType-FilePicker
This is a light Android file picker library.

Please star this library if you like it. :)

## Demo
![Demo](/pic/pick_img.gif)
![Demo](/pic/pick_img1.gif)
![Demo](/pic/pick_vid.png)
![Demo](/pic/pick_aud.png)
![Demo](/pic/pick_file.png)

## Usage
### 1.Start Activity For Result
    case R.id.btn_pick_image:
		Intent intent1 = new Intent(this, ImagePickActivity.class);
		intent1.putExtra(IS_NEED_CAMERA, true);
		intent1.putExtra(Constant.MAX_NUMBER, 9);
		startActivityForResult(intent1, Constant.REQUEST_CODE_PICK_IMAGE);
		break;
	case R.id.btn_pick_video:
		intent2 = new Intent(this, VideoPickActivity.class);
		intent2.putExtra(IS_NEED_CAMERA, true);
		intent2.putExtra(Constant.MAX_NUMBER, 9);
		startActivityForResult(intent2, Constant.REQUEST_CODE_PICK_VIDEO);
		break;
	case R.id.btn_pick_audio:
		Intent intent3 = new Intent(this, AudioPickActivity.class);
		intent3.putExtra(IS_NEED_RECORDER, true);
		intent3.putExtra(Constant.MAX_NUMBER, 9);
		startActivityForResult(intent3, Constant.REQUEST_CODE_PICK_AUDIO);
		break;
	case R.id.btn_pick_file:
		Intent intent4 = new Intent(this, NormalFilePickActivity.class);
		intent4.putExtra(Constant.MAX_NUMBER, 9);
		intent4.putExtra(NormalFilePickActivity.SUFFIX, new String[] {"xlsx", "xls", "doc", "docx", "ppt", "pptx", "pdf"});
		startActivityForResult(intent4, Constant.REQUEST_CODE_PICK_FILE);
		break;
		
### 2.Receive the Result from Activity
    case Constant.REQUEST_CODE_PICK_IMAGE:
		if (resultCode == RESULT_OK) {
            ArrayList<ImageFile> list = data.getParcelableArrayListExtra(Constant.RESULT_PICK_IMAGE);
        }
        break;
	case Constant.REQUEST_CODE_PICK_VIDEO:
		if (resultCode == RESULT_OK) {
            ArrayList<VideoFile> list = data.getParcelableArrayListExtra(Constant.RESULT_PICK_VIDEO);
        }
        break;
    case Constant.REQUEST_CODE_PICK_AUDIO:
		if (resultCode == RESULT_OK) {
            ArrayList<AudioFile> list = data.getParcelableArrayListExtra(Constant.RESULT_PICK_AUDIO);
        }
        break;
	case Constant.REQUEST_CODE_PICK_FILE:
		if (resultCode == RESULT_OK) {
            ArrayList<NormalFile> list = data.getParcelableArrayListExtra(Constant.RESULT_PICK_FILE);
        }
        break;

## Thanks
Inspired by [Android-FilePicker](https://github.com/DroidNinja/Android-FilePicker)

Image Viewer provide by [PhotoView](https://github.com/bm-x/PhotoView)

Image Loader provide by [Glide](https://github.com/bumptech/glide)

## License
```
Copyright 2016 Vincent Woo

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
