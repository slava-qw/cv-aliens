# Code execution instruction:

Все эксперименты и их результаты представлены в основном ноутбуке. Так как некоторые ячейки слишком долго выполняются, то для повторного запуска рекомендуется их не запускать, а загружать уже полученные ранее с них данные (подробнее см. в самом ноутбуке). Также некоторые ячейки предзагружают исполняемые файлы, и поэтому для корректного выполнения нужно убедиться, что путь, куда скачиваются файлы, и путь в самой программе совпадают.

P.S. ссылка на этот же ноутбук, но в колабе: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1KqiZgU1xODBLNGQ8h7Rt7riQFciwQUgc?usp=sharing)


# Образ Инопланетян 👽👾

Согласно имеющейся (у меня) информации, инопланетяне имеют следующие черты:

* Они обладают многомерной структурой тела, состоящей из плавных изгибов и органических форм.
* Инопланетяне обладают немного отличной от человека структурой тела, но их основные черты могут быть узнаваемыми. У них также как и у людей есть четко выделенные лицевые черты, они также имеют голову, тело и конечности, однако их формы и пропорции могут быть немного иной. Например, у них могут быть дополнительные суставы или необычные изгибы, которые придают им уникальный вид. Они также обладают кожей, покрытой интересными узорами и рисунками, которые могут меняться в зависимости от настроения или обстановки.
* Они воспринимают мир через цветовой спектр, включая инфракрасные и ультрафиолетовые диапазоны, поэтому и зрительные ораганы у них устроены не так как у людей. В зависимости от принимаемого спектра они могут менять цвет.

# Предпочтения при выборе отеля 🏨🤷‍♂️🛏️
Исходя из анализа их особенностей, мы можем предположить следующие предпочтения инопланетян при выборе отеля:

* Освещение: Инопланетяне ценят яркие и разнообразные цветовые схемы, которые подчеркивают их способности видеть цвета в широком диапазоне. Это позволит им в полной мере насладиться красотой земных отелей.
* Органичность: Отель должен иметь органическую архитектуру с плавными формами, что соответствует их собственной физиологии.
* Экзотичность: Поскольку инопланетяне прилетели к нам с другой планеты, а может даже и галактики, то они заинтересованы в экзотических земных пейзажах и природных элементах. Добиться этого помогут разнообразные земные расстения, которые можно поставить в номере.
* Окружение: некоторые предметы интерьера можно заменить на больше подходящий под неземную цивилизацию, например, картины, которые напоминали бы им об их доме.

Эти предположения будут использованы для направления нашей работы по адаптации изображений отелей для инопланетян.

Ниже представлены их фотографии:

> Для их получения использовался данный туториал (<a href="https://youtu.be/vmhex7wXCsw" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/youtube.svg" height="27" width="27" /></a>) и этот ноутбук: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1PNv9JCoS_XyJVKlqPGnlnSvRcRiFkw69). В качестве генерации была взята модель `stable-diffusion-xl-base-1.0` с 🤗 [Hugging Face](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0).


<img src="data\imgs\alien children_2.png" width="235" height=235/>
<img src="data\imgs\alien children_1.png" width="235" height=235/>
<img src="data\imgs\full-length aliens_female.png" width="474" height=474/>
<img src="data\imgs\full-length aliens_male.png" width="474" height=474/>

В фото альбоме выше изображён вид пришельцев разного возраста и пола.

# Изучение датасета 📊🔍

## Тематика и её проблемы.

Useful topic-links: <a href="https://huggingface.co/docs/transformers/tasks/image_captioning" target="blank"><img align="center" src="https://huggingface.co/datasets/huggingface/brand-assets/resolve/main/hf-logo.svg" height="30" width="30" /></a>, <a href="https://paperswithcode.com/task/image-captioning" target="blank"><img align="center" src="https://paperswithcode.com/static/logo.png" height="20" width="30" /></a>, <a href="https://medium.com/swlh/image-captioning-using-attention-mechanism-f3d7fc96eb0e" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/medium.svg" height="25" width="30" /></a>, <a href="https://www.tensorflow.org/text/tutorials/image_captioning" target="blank"><img align="center" src="https://avatars.githubusercontent.com/u/15658638?s=200&v=4" height="25" width="25" /></a>

Videos: <a href="https://youtu.be/LWIZj_RJYjM" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/youtube.svg" height="30" width="40" /></a>

🤔 ***Что такое image captioning?***

Создание описания к изображениям (image captioning) - это задача компьютерного зрения (CV) и обработки естественного языка (NLP), которая заключается в автоматическом генерировании текстовых описаний изображений. 

👨‍💻 ***Почему над этим работают?***

Создание "субтитров" к изображениям имеет множество практических применений. Эта технология может быть использована для создания описаний к видео, фотографиям и изображениям в медицинской и научной областях. Это также полезно для визуальных помощников, автоматического описания веб-контента и повышения доступности контента для людей с ограниченными возможностями.

Само свойство сопоставления картинки и текста, ее описывающего, предоставляет возможность поиска по большим коллекциям изображений с помощью текстовых запросов и является чрезвычайно мощной функцией. Возможные области применения включают национальную оборону и антитеррористическую деятельность, способность обнаруживать и устранять последствия изменения климата до того, как они станут неконтролируемыми и т.д.

📝 ***Как формулируется задача?***

Задача создания подписей к изображениям состоит в обучении модели, способной генерировать описания к изображениям. Входными данными для модели является изображение, а выходными - текстовое описание. Модель должна выучить связь между визуальными особенностями изображения и соответствующими словами или фразами описания. Постановка задачи включает в себя обучение модели на размеченном наборе данных таким образом, чтобы она могла правильно сопоставлять изображения с описаниями и впоследствии генерировать описания для новых изображений.


## Обзор датасета 🔍📊👀
* *Что представлено на изображениях?*

    В тренировочном датасете представлены фоторафии отелей. На самих изображениях изображены различные комнаты квартир/отелей с различным окружающим интерьером. Важно отметить, что некоторые из фотографий перевернуты (например: [эта](https://traffickcam.com/images/2017/2/20160126_003646_R6Q5EX.jpg), [эта](https://traffickcam.com/images/2017/2/20160126_003646_6QK6W3.jpg) и [эта](https://traffickcam.com/images/2017/2/20160126_003646_30FFBF.jpg)); также есть фото не относящихся к тематике комнат (например, фотография [монетки](https://i.travelapi.com/hotels/1000000/910000/903700/903617/7d99f5db_b.jpg) или [медали](https://i.travelapi.com/hotels/2000000/1750000/1744200/1744111/19f0153f_b.jpg))

* *Сколько объектов в датасете? Сколько уникальных классов? Сбалансирован ли датасет?*

    Объектов в датасете $1124215$. Причем, каких-либо пропусков в таблице нет. Количество уникальных изображений $1055785$. Если смотреть по отелям, то датасет не сбалансирован, так как частотность распределена не равномерно. Аналогично получается и для ресурса с которого брались фотографии.

* *Какие параметры у изображений? Размер фотографий?*

    Как и у любого изображения у него есть ширина, высота, цветовая модель, формат. Для нашего датасета фотографии были в формате .png/.jpeg, модель была типа RGB, а средний размер фотографий по выборке из 776 изображений составил (414, 309).

# Обогащение датасета описаниями 🏷️➕🖼️

Из анализа датасета, стало ясно, что предобработка в себя будет включать изменеия масштаба картинки с соответсвующей нормализацией пиксилей. Это необходимо для правильного обучения (или тюнинга) модели, иначе поступающие каждый раз на вход векторы, полученные из этих изображений, будут разной размерности, что ломает всю работу (почти любой) сети. 

Немного не понятно зачем составлять именно тренировочную выборку, только разве что для тюнинга, хотя даже zero-shot предобученная модель судя по статьям дает хороший результат. Ведь у нас нет каких-либо специфичных снимков как, [например](https://huggingface.co/blog/fine-tune-clip-rsicd), снимки со спутников и т.д. У нас только лишь фото интерьера различных комнат. В связи с техническими и временными ограничениями среды разработки (Google Colab) от общего датасета из более чем миллиона картинок возмём выборку из 1000 изображений.

Будем пользоваться официальной имплементацией автора CLIP-Interrogator v.2 (<a href="https://github.com/pharmapsychotic/clip-interrogator" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/888aff31e1d26dd2a6acf6afebbc34970aeb0118/src/images/icons/Social/github.svg" height="20" width="20" /></a> [@pharmapsychotic](https://github.com/pharmapsychotic/clip-interrogator)). Поясню почему именно эта имплементация, а не другуие. Во-первых, предложенная ссылка в самом задании на колаб (<a href="https://github.com/rupeshs/diffusionmagic/tree/main" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/888aff31e1d26dd2a6acf6afebbc34970aeb0118/src/images/icons/Social/github.svg" height="20" width="20" /></a> [diffusionmagic](https://github.com/rupeshs/diffusionmagic/tree/main)) не иммеет имплементации CLIP-Interrogator (по крайней мере мне таковой не удалось найти ни в веб интерфейсе при запуске, ни в самом репозитории). Почему я не использовал решение непосредственно из AUTOMATIC1111, так как в веб интерфейсе нет возможности получить промты сразу для батча картинок, тем более, что [могут возникнуть проблемы](https://github.com/camenduru/stable-diffusion-webui-colab#-important--according-to-the-official-statement-the-colab-free-of-charge-tier-is-not-available-for-the-stable-diffusion-webui--we-can-only-use-it-with-any-paid-plan-also-i-asked-the-colab-team-to-change-the-scary--message-httpsgithubcomgooglecolabcolabtoolsissues3591-and-official-statement-no-bans-planned-if-you-click-through-will-delete-the-vms-at-some-point) при запуске в бесплатной версии колаба (а они возникли, но об этом дальше).

Поэтому будем использовать имплементацию выше, тем более, что код можно изменить для получения описания для целого батча картинок и все это сразу записывать в файл (подробнее см. в ноутбуке). Эта имплементация, которая хоть и имеет некоторые ограничения по сравнению с AUTOMATIC1111 ([например](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#clip-interrogator), выбор топа слов из CLIP'a),  достаточно хорошо справляется с данными картинками и, например может отличить перевернутые картинки от обычных.

Точность описаний для большинства фотографий довольно высока. Но например, для повернутых изображений она начинает страдать (см. ниже), но справедливости ради стоит отметить, что то, что изображение повёрнуто и расположение кровати были угаланы правильно. Также в некоторых описаниях появляются объекты, которых в реальности на изображениях нет. Но в общем стилистика по описанию совпадает с тем, что изображенно. Причём стоит отметить, что после удаления базовых лейблов, отличных от нашей тематики, сами описания стали намного лучше (подробнее см. в ноутбуке).

Пример получившихся описаний:

<img src="data\imgs\exfmple of captions.png" width="775" height="300"/>

Если кластеризовать полученные описания по их эмбеддингам алгоритмом DBSCAN после применения t-SNE (так как многомерная кластеризация довольно сложна и трудозатаратна, ведь размерность пространства эмбеддингов составила 768), то в кластерах будут изображения довольно схожей тематики и стиля, и само описание примерно совпадает с тем, что изображено.

Пример кластеризации DBSCAN'ом дал 41 кластер (при гиперпараметрах $\varepsilon = 3$, min_samples $= 3$):

<img src="data\imgs\t-SNE&DBSCAN_clastering.png" width="375" height="250"/>

(интерактивный график см. в ноутбуке)

Ниже представлен пример картинок в одном из полученных кластеров; в качестве общего описания использовался промт, эмбеддинг которого был наиболее близким к усредненному эмбеддингу всех описаний внутри этого кластера.

<img src="data\imgs\all_together.png" width="775" height="300"/>


# Изменение изображения при помощи диффузионной модели 🖼️🔧🔃✅

Так как эта часть задания творческая, и точность результата сильно зависит от подаваемого на вход модели промта, то доверим эту ответсвенную часть задачи схожей модели, а именно GPT-3.5. Попробуем сначала описать суть задачи, а потом попросить сгенерировать промты для объектов-изображений. 

К сожалению, на момент написания этого текста у меня так и не получилось добиться удовлетворительного результата из-за непредвиденных обстоятельств. А именно мне не хватило времени использования предоставляемых вычислительных ресурсов в бесплатной версии Google Colab для изменения всех отобранных картинок. Так как согласно [официальному заявлению](https://twitter.com/thechrisperry/status/1649189902079381505) с недавнего времени колаб перестал поддерживать исполнение stable diffusion webUI для бесплатной подписки ([link1](https://github.com/googlecolab/colabtools/issues/3591), [link2](https://github.com/camenduru/stable-diffusion-webui-colab#-important--according-to-the-official-statement-the-colab-free-of-charge-tier-is-not-available-for-the-stable-diffusion-webui--we-can-only-use-it-with-any-paid-plan-also-i-asked-the-colab-team-to-change-the-scary--message-httpsgithubcomgooglecolabcolabtoolsissues3591-and-official-statement-no-bans-planned-if-you-click-through-will-delete-the-vms-at-some-point)). Если же использовать Hugging Face Spaces, то во всех моделях image-to-image, которые я нашел и смог использовать, не было общей настройки гиперпараметров и inpaint режима (а там где и был, то все равно отсутсвовала общая настройка).

Ниже приведены те изображения, результат изменения которых наиболее удачный. Все изображения (и промежуточные, и с плохим результатом) находятся в соответсвующих папках.

| Было | Стало |
|:----------:|:----------:|
| <img src="data\imgs for SDXL\6183644\6183644.png" width="205" height="205"/> | <img src="data\imgs for SDXL\6183644\img1.png" width="205" height="205"/> <img src="data\imgs for SDXL\6183644\img2.png" width="205" height="205"/>   |
| <img src="data\imgs for SDXL\6518180\6518180.png" width="205" height="205"/> | <img src="data\imgs for SDXL\6518180\img2.png" width="205" height="205"/> <img src="data\imgs for SDXL\6518180\img1_2.png" width="205" height="205"/>   |
| <img src="data\imgs for SDXL\6166037\6166037.png" width="205" height="205"/> | <img src="data\imgs for SDXL\6166037\img2_2.png" width="205" height=205/>
| <img src="data\imgs for SDXL\6267528\6267528.png" width="205" height="205"/> | <img src="data\imgs for SDXL\6267528\img1_1.png" width="205" height=205/> |
| <img src="data/imgs for SDXL/6373143/6373143.png" width="205" height="205"/> | <img src="data\imgs for SDXL\6373143\загруженное (4).png" width="205" height=205/> <img src="data\imgs for SDXL\6373143\00150-2424947932.png" width="205" height=205/> |

## Как сделать лучше 🚀

0. Очевидный отевт в виде картинки
    
    <img src="data\imgs\meme.png" width="255" height=255/>

А если серьезно, то так как мы не хотим затрагивать остальные элементы изображения, кроме выделенного, то, очевидно, что нужно использовать inpaint режим. Дальше я попробую привести ряд статей, которые позволили улучшить основной результат для диффузионных моделей, полученный в базовых статьях, перечисленных ниже:

>* Sohl-Dickstein, Jascha, et al. [Deep Unsupervised Learning Using Nonequilibrium Thermodynamics, 18 Nov. 2015](https://arxiv.org/abs/1503.03585).
>* Ho, Jonathan, et al. [Denoising Diffusion Probabilistic Models, 16 Dec. 2020](https://arxiv.org/abs/2006.11239).
>* Nichol, Alex, and Prafulla Dhariwal. [Improved Denoising Diffusion Probabilistic Models, 18 Feb. 2021](https://arxiv.org/abs/2102.09672).
>* Dhariwal, Prafulla, and Alex Nichol. [Diffusion Models Beat GANs on Image Synthesis, 1 June 2021](https://arxiv.org/abs/2105.05233).


1. Не отходя идейно далеко от пункта 0, можно попробовать составить ансамбль диффузионных моделей, что-то наподобие бустинга, когда каждая новая модель постепенно улучшает качество картинки, сгенерированной предыдущей моделью. Оказывается, такая схема называется каскадной диффузией: [Cascaded Diffusion Models for High Fidelity Image Generation, Ho et al., 17 Dec 2021](https://arxiv.org/abs/2106.15282)

2. Так как для использования условной генерации (conditional image generation: guided diffusion) нам нужен энкодер текста в эмбеддинги, то вместо CLIP'a, взятого в основной статье от OpenAI, можной попробовать использовать энкодеры других больших языковых моделей (например, использовать такие LLM как, GPT-4, BERT или T5-XXL). Примером такой идеи может служить следующая статья от гугла о диффузионной модели Imagen: [Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding, 23 May 2022](https://arxiv.org/abs/2205.11487), где как раз проверялось использование энкодеров от разных LLM (см. раздел 2.1), а также каскадной диффузии в виде двух super-resolution диффузионных моделей (см. раздел 2.4).


3. Как отдельной идей можно поробовать обучить CLIP на отдельных картинках-предметах (т.е. картинка только с одним предметом без фона), а дальше эту картинку, полученную из текстового запроса с помощью CLIP'a, вставлять на исходную картину, немного её изменив, чтобы она лаконично вписывалась в окружающий её фон (image composition task). Примером может быть недавно выпущенное приложение [Vispunk](https://vispunk.com/) (<a href="https://github.com/vispunk/vispunk-webui" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/888aff31e1d26dd2a6acf6afebbc34970aeb0118/src/images/icons/Social/github.svg" height="20" width="20" /></a>[github](https://github.com/vispunk/vispunk-webui))

4. Также можно просить не пользователя выделять объект на изображении, а заставить это делать модель. Тогда пользователю достаточно будет прописать точный промт, что на что он хочет заменить. Для сегментации объектов на изображении можно использовать недавно выпущенную модель SAM от MetaAI: [Segment Anything, Alexander Kirillov, Eric Mintun2, et al., 5 Apr 2023](https://arxiv.org/pdf/2304.02643.pdf).
5. Понятно, что можно также файнтюнить уже предобученную модель под собственную доменную область.
6. Многообразие различных улучшений и изменений, на самом деле достаточно велико, поэтому оставлю лишь ссылку на сборник наиболее релевантных (и недавно выпущенных) статей: <a href="https://github.com/diff-usion/Awesome-Diffusion-Models" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/888aff31e1d26dd2a6acf6afebbc34970aeb0118/src/images/icons/Social/github.svg" height="20" width="20" /></a> [Awesome-Diffusion-Models](https://github.com/diff-usion/Awesome-Diffusion-Models)

<!-- Secret: [Semi-Supervised Image Captioning with CLIP](https://arxiv.org/pdf/2306.15111.pdf) based on [this](https://arxiv.org/pdf/2111.09734.pdf) -->


### References:
1. [Diffusion Models | Paper Explanation | Math Explained](https://youtu.be/HoKDTa5jHvg?si=8jb5MHJcd37e4gQH)
2. [How diffusion models work: the math from scratch](https://theaisummer.com/diffusion-models/#cascade-diffusion-models)
3. [What are Diffusion Models?](https://lilianweng.github.io/posts/2021-07-11-diffusion-models/)
4. [How Diffusion Models Work](https://youtu.be/HWaadBNSsto?si=AOhC-T4Zfqulk35u)
5. [Awesome-Diffusion-Models](https://github.com/diff-usion/Awesome-Diffusion-Models)



