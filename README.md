# login_with-facabo
avvalo pip install social-auth-app-django paketini ornatib olamiz

keyin esa settings.py ga kirib install_appsga  'social_django', qushib qo'yamiz qoyamiz


keyin migratsiya qilib olamzi python manage.py migrate
keyin settings.py middlware ga 'social_django.middleware.SocialAuthExceptionMiddleware', ushbu commandani qo'shib qo'yamiz
keyin templatesni oxiriga  
'social_django.context_processors.backends',  # <-- Here
'social_django.context_processors.login_redirect' shuni qo'shamiz

settings.py ga ushbu commanda qo'shiladi;
AUTHENTICATION_BACKENDS = (
    'social_core.backends.facebook.FacebookOAuth2',
    'django.contrib.auth.backends.ModelBackend',
)

urls.pyga   path('oauth/', include('social_django.urls', namespace='social')),

setings.py
SOCIAL_AUTH_FACEBOOK_KEY = '123456789'  # App ID
SOCIAL_AUTH_FACEBOOK_SECRET = '123456789wdds'  # App Secret
quyiladi bu facebook saytidan kirib olinadi devolpers.faccebook saytidan
