# Django Sprint Kılavuzu

## Geliştirme Ortamının Kurulması

Katılımcılardan, etkinliğe gelmeden önce geliştirme ortamlarını hazır
etmelerini bekliyoruz. Etkinlik süresince bunun için ayrı zaman
ayrılmayacaktır.

Öncelikle GitHub üzerinde [Django kaynak kodunu][dj-gh] forklayıp geliştirmeye
başlayabilirsiniz.

* Eğer Vagrant'a aşinaysanız; üzerinde çalışacağınız ticketlar birden fazla
  Django sürümünü kapsıyorsa veya ORM gibi birden fazla veritabanı kurulumu
  gerektiren bir ticket üzerinde çalışıyorsanız [djangocore-box][dj-box]'u
  kullanabilirsiniz.

[dj-gh]: https://github.com/django/django
[dj-box]: https://github.com/jphalip/djangocore-box

* Elle kurulum için tek ihtiyacınız [Virtualenv][dj-venv]:

  ```sh
  $ git clone git@github.com:<KULLANICI_ADINIZ>/django.git
  $ cd django
  $ # 1.7+ sürümlerde --no-site-packages opsiyonunu kullanmanıza gerek yok
  $ virtualenv venv
  $ source venv/bin/activate.sh
  ```

[dj-venv]: http://www.virtualenv.org/

* [Virtualenvwrapper][dj-vw]'ı kullanırsanız hayatınız daha da kolaylaşabilir:

  ```sh
  $ git clone git@github.com:<KULLANICI_ADINIZ>/django.git
  $ mkvirtualenv djangosprint
  ```

  Sanal geliştirme ortamından çıkmak için `deactivate`, mevcut geliştirme
  ortamlarını listelemek için `workon`, `mkvirtualenv` ile oluşturduğunuz bir
  geliştirme ortamına geçmek içinse `workon <geliştirme ortamının adı>`
  komutlarını verebilirsiniz.

[dj-vw]: http://virtualenvwrapper.readthedocs.org/en/latest/

* Gerek virtualenv, gerekse virtualenvwrapper kullandığınız çözümlerde

  ```sh
  $ pip install -e <DJANGO_DIZINI>
  ```

  komutu ile lokalinizdeki Django kodunu sanal geliştirme ortamınızda
  kullanmaya başlayabilirsiniz.


## Geliştirmeye başlamadan önce

1. Daha önce bir açık kaynak projenin geliştirilmesinde görev almadıysanız ya
   da Django'nun geliştirme sürecine yabancıysanız öncelikle
   [Advice for new contributors][dj-newbie] belgesini okuyun.

### Önemli Bağlantılar

* [Django kaynak kodu](https://github.com/django/django)
* [Django tracker](https://code.djangoproject.com/query)

[dj-newbie]: https://docs.djangoproject.com/en/dev/internals/contributing/new-contributors/


## Workflow

**Not:** Bu belgede listelenen ticketlardan biri üzerinde çalışmak zorunda
değilsiniz ancak ne üzerinde çalıştığınızı [İş Bölümü][dj-is] sayfasına
eklemeninizi bekliyoruz.

1. Çalışmak istediğiniz bir ya da birden fazla ticket'ın numarasını Wiki'deki
   [İş Bölümü][dj-is] sayfasında yazmanız birden fazla kişinin aynı ticket
   üzerinde çalışmasını engellemek adına faydalı olacaktır.

[dj-is]: https://github.com/pyistanbul/sprints/wiki/%C4%B0%C5%9F-B%C3%B6l%C3%BCm%C3%BC


## Ticketlar

* ["Easy Pickings" tickets](https://code.djangoproject.com/query?status=!closed&easy=1)
* ["Easy Pickings" tickets whose owner is nobody or anonymous](https://code.djangoproject.com/query?owner=nobody&status=new&easy=1&or&status=assigned&status=new&owner=anonymous&easy=1&col=id&col=summary&col=status&col=owner&col=type&col=component&order=priority)
* https://code.djangoproject.com/ticket/16134
* https://code.djangoproject.com/ticket/16350
* https://code.djangoproject.com/ticket/16350
* https://code.djangoproject.com/ticket/15654

### Eklenebilecek Fikirler

* [Güncel Fikirler][dj-ideas]

**Not:** Django tracker'ında bulunmayan herhangi bir fikriniz varsa ya da boş zamanı
olan başka bir katılımcının üzerinde çalışmasını istiyorsanız
[Fikirler][dj-ideas] sayfasına ekleyebilirsiniz.

[dj-ideas]: https://github.com/pyistanbul/sprints/wiki/Fikirler

### Faydalı Trac Sorguları

* [Unit test eksiği olan ticketlar][dj-unittest]
* [Merge edilmesi için ilgili belgelerin güncellenmesi veya eklenmesi gereken
  ticketlar][dj-doc]

[dj-unittest]:
https://code.djangoproject.com/query?status=!closed&needs_tests=1&stage=Accepted&order=priority
[dj-doc]:
https://code.djangoproject.com/query?status=!closed&needs_better_patch=0&needs_tests=0&needs_docs=1&has_patch=1&stage=Accepted&order=priority


## İletişim

Türkçe iletişim için Freenode üzerindeki `#pyistanbul`, resmi ve İngilizce
iletişim için ise yine Freenode üzerindeki `#django-sprint` kanalını
kullanabilirsiniz.

IRC komutlarına için [bu bağlantıyı][dj-irc] kullanabilirsiniz. Freenode'a
girmek için değil ama kanallara girebilmek için kayıtlı bir nick gerekmektedir.

    /msg nickserv register [password] [your@email.address.com]

ile kullanıcı adınızı kaydedebilir, daha sonra kanal içerisinde

    /msg nickserv identify [password]

ile giriş yapabilirsiniz. Çoğu IRC client bu adımı sizin yerinize otomatik
olarak yapıyor. İlk kayıtta e-posta adresinize gelen komutu IRC üzerinde
çalıştırarak e-postanızı onaylayabilirsiniz.

[dj-irc]:
http://meta.wikimedia.org/wiki/IRC_instructions#Register_your_nickname.2C_identify.2C_and_enforce
