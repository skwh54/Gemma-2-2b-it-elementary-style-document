# Gemma-2-2b-it-elementary-style-document

---
license: cc-by-nc-4.0
base_model:
- google/gemma-2-2b-it
---

# Gemma-2-2b 초등학생 글 변환기

[huggingface](https://huggingface.co/skwh54/Gemma-2-2b-it-elementary-style-document)

## 💻 Model Description
- Gemma2-2b 한국 초등학생 글 변환기는 입력한 글을 초등학생이 쓴 것 같은 글로 변환해 주는 모델입니다.
- Gemma2-2b-it 모델을 base model로 사용하였고 LoRA기법을 사용하여 효율적으로 fine-tuning 하였습니다. 

(Gemma2-2b is a model that transforms input text to resemble the writing style of an elementary school student. It is based on the Gemma2-2b-it model and was fine-tuned efficiently using the LoRA technique.)

## 🚦Usage
```
import transformers
from huggingface_hub import notebook_login

notebook_login()

BASE_MODEL = "skwh54/Gemma-2-2b-it-elementary-style-document"

model = AutoModelForCausalLM.from_pretrained(BASE_MODEL, device_map={"":0})
tokenizer = AutoTokenizer.from_pretrained(BASE_MODEL)
```

## 📂 Example
|  Input  |  Output  |
|---------|----------|
| 안녕하세요. 저는 친구와 공원에서 만나서 놀았어요. 날씨가 좋아서 놀기 좋았어요. 맛있는 음식들도 많이 먹었어요. 내일도 놀고 싶다! | ㅎㅇ 난 친구랑 공원에서 만나서 놀았는데 날씨가 좋아서 더 좋았고 맛있는 음식도 많이 먹었음 내일도 놀고 싶다 |
|오늘은 회사에서 중요한 프로젝트 회의를 했다. 준비한 만큼 좋은 피드백을 받아서 뿌듯했다. 퇴근 후에는 운동을 하고 나서 집에서 책을 읽으며 하루를 마무리했다.|오늘 회사에서 중요한 프로젝트 회의함 ㅋㅋ 준비한 만큼 좋은 피드백 받아서 뿌듯함 퇴근 후에 운동하고 집에 오면 책 읽으며 하루 마무리함|


## 📃 Training data
- [korean_smile_style_dataset](https://github.com/smilegate-ai/korean_smile_style_dataset)을 사용하였습니다.
- 본 데이터는 Smilegate AI에서 공개하는 한국어 문체 스타일 변환 "SmileStyle" 데이터셋입니다.
- 여러 스타일의 문체가 존재하며 이 중에서 formal과 choding 스타일의 데이터만을 추출하여 사용하였습니다.

(The korean_smile_style_dataset was used for training. This dataset, "SmileStyle," is provided by Smilegate AI and includes various writing styles in Korean. Only the formal and elementary school styles were used in this model.)


더 많은 실험은 [Test colab link](https://colab.research.google.com/drive/1tWEx-uwiF84N0a964Q_9fm4x9lg8d5k3?usp=sharing#scrollTo=uGRtxPNmYeKK) 에서 해보세요!

## 🏃‍♂️‍➡️ Coworker
[JiwookHan](https://huggingface.co/mreraser) 
