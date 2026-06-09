# CloudExperienceHostAPI::OobeDisplayLanguagesCore::GetDisplayLanguages(Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeDisplayLanguage *> * *)

- ea: `0x180037480`
- end: `0x180037b62`
- name: `?GetDisplayLanguages@OobeDisplayLanguagesCore@CloudExperienceHostAPI@@UEAAJPEAPEAU?$IVectorView@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z`
- size: `1762`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800076b4`
- `0x1800076d4`
- `0x180009760`
- `0x180009814`
- `0x18000b098`
- `0x18000b200`
- `0x18000b7f8`
- `0x18000b9b8`
- `0x18000bc70`
- `0x180012e2c`
- `0x180015524`
- `0x180034edc`
- `0x18003523c`
- `0x1800359d8`
- `0x180036588`
- `0x1800365f0`
- `0x180037480`
- `0x180038854`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003756d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037646`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003756d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037646`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037532`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037532`

## string_xrefs

- `0x180037500`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180037550`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x1800375c9`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180037668`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x18003771d`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180037779`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180037834`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180037917`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x1800379c6`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x180037aab`: `shellcommon\shell\oobe\core\components\winrt\oobedisplaylanguagecore.cpp`
- `0x18003752b`: `coreglobconfig.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CloudExperienceHostAPI::OobeDisplayLanguagesCore::GetDisplayLanguages(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  CloudExperienceHostCoreTelemetry *v5; // rcx
  __int64 v6; // rcx
  __int64 result; // rax
  int v8; // eax
  unsigned int LastError; // ebx
  HMODULE Library; // rax
  const char *v11; // r9
  HMODULE v12; // rdi
  FARPROC ProcAddress; // rbx
  __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // r12
  __int64 v18; // rbx
  FARPROC v19; // r14
  const char *v20; // r9
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // r14d
  int v25; // eax
  __int64 v26; // rsi
  int v27; // eax
  unsigned int v28; // edi
  int v29; // eax
  unsigned int v30; // ebx
  int *v31; // [rsp+20h] [rbp-88h]
  __int64 v32; // [rsp+30h] [rbp-78h] BYREF
  __int64 v33; // [rsp+38h] [rbp-70h] BYREF
  int v34[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v35; // [rsp+48h] [rbp-60h] BYREF
  __int64 v36; // [rsp+50h] [rbp-58h] BYREF
  __int128 v37; // [rsp+58h] [rbp-50h] BYREF
  __int64 v38; // [rsp+68h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  unsigned int v40; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v41; // [rsp+B8h] [rbp+10h] BYREF
  HMODULE v42; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v43; // [rsp+C8h] [rbp+20h] BYREF

  if ( CloudExperienceHostCoreTelemetry::IsEnabled(a1, (unsigned __int64)a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v4,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(
      v5,
      "CloudExperienceHostAPI::OobeDisplayLanguagesCore::GetDisplayLanguages");
  }
  *a2 = 0;
  v6 = *(_QWORD *)(a1 + 56);
  if ( v6 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v6 + 48LL))(v6, a2);
  v43 = 0;
  v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeDisplayLanguage,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeDisplayLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeDisplayLanguage *>>>(
         0,
         &v43);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
      (const char *)(unsigned int)v8,
      (int)v31);
LABEL_15:
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
    return LastError;
  }
  v41 = 0;
  *(_QWORD *)v34 = 0;
  Library = LoadLibraryExW(L"coreglobconfig.dll", 0, 0x800u);
  v12 = Library;
  v42 = Library;
  if ( !Library )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5D,
                  (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
                  v11);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
    goto LABEL_15;
  }
  ProcAddress = GetProcAddress(Library, "GetSupportedDisplayLanguages");
  if ( !ProcAddress )
  {
    LastError = -2147418113;
    v14 = 2147549183LL;
    v15 = 101;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
      (const char *)v14,
      (int)v31);
    goto LABEL_14;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v41,
    0);
  v31 = v34;
  v16 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))ProcAddress)(59, 0, 0, &v41);
  LastError = v16;
  if ( v16 < 0 )
  {
    v14 = (unsigned int)v16;
    v15 = 108;
    goto LABEL_13;
  }
  try
  {
    VectorFromDelimitedStringNonConst(&v37, v41);
    v17 = *((_QWORD *)&v37 + 1);
    v26 = v37;
    v18 = v43;
    while ( v26 != v17 )
    {
      v19 = GetProcAddress(v12, "GetDisplayLanguageNativeName");
      if ( !v19 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
          (const char *)0x8000FFFFLL,
          (int)v31);
        if ( (_QWORD)v37 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v37, *((_QWORD *)&v37 + 1));
          std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFE0uLL);
          v37 = 0;
          v38 = 0;
        }
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
        return 2147549183LL;
      }
      v32 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v32,
        0);
      v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      v22 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *))v19)(v21, 1, &v32);
      if ( v22 >= 0 )
      {
        v35 = v32;
        v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
        v33 = 0;
        v23 = Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeDisplayLanguageCore,CloudExperienceHostAPI::OobeDisplayLanguageCore,unsigned short const *,unsigned short *>(
                &v33,
                &v36,
                &v35);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x86,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
            (const char *)(unsigned int)v23,
            (int)v31);
          wil::com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>(&v33);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
          if ( (_QWORD)v37 )
          {
            std::_Destroy_range<std::allocator<std::wstring>>(v37, *((_QWORD *)&v37 + 1));
            std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFE0uLL);
            v37 = 0;
            v38 = 0;
          }
          goto LABEL_26;
        }
        v25 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 104LL))(v18, v33);
        v24 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x87,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
            (const char *)(unsigned int)v25,
            (int)v31);
          wil::com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>(&v33);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
          if ( (_QWORD)v37 )
          {
            std::_Destroy_range<std::allocator<std::wstring>>(v37, *((_QWORD *)&v37 + 1));
            std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFE0uLL);
            v37 = 0;
            v38 = 0;
          }
LABEL_26:
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
          return v24;
        }
        wil::com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>(&v33);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
          (const char *)(unsigned int)v22,
          (int)v31);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
      v26 += 32;
    }
    v40 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v18 + 56LL))(v18, &v40);
    v28 = v27;
    if ( v27 >= 0 )
    {
      if ( !v40 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
          (const char *)0x8000FFFFLL,
          (int)v31);
        if ( (_QWORD)v37 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v37, *((_QWORD *)&v37 + 1));
          std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFE0uLL);
          v37 = 0;
          v38 = 0;
        }
        goto LABEL_20;
      }
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v18 + 64LL))(v18, a2);
      v30 = v29;
      if ( v29 >= 0 )
      {
        if ( (_QWORD)v37 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v37, *((_QWORD *)&v37 + 1));
          std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFE0uLL);
        }
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8F,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
          (const char *)(unsigned int)v29,
          (int)v31);
        if ( (_QWORD)v37 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v37, *((_QWORD *)&v37 + 1));
          std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFE0uLL);
          v37 = 0;
          v38 = 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
        result = v30;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
        (const char *)(unsigned int)v27,
        (int)v31);
      if ( (_QWORD)v37 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v37, *((_QWORD *)&v37 + 1));
        std::_Deallocate<16>(v37, (v38 - v37) & 0xFFFFFFFFFFFFFFE0uLL);
        v37 = 0;
        v38 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
      result = v28;
    }
  }
  catch ( ... )
  {
    v40 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x91,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobedisplaylanguagecore.cpp",
            v20);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v42);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
    wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v43);
    return v40;
  }
  return result;
}

```

## disassembly

```asm
0x180037480  push    rbx
0x180037482  push    rsi
0x180037483  push    rdi
0x180037484  push    r12
0x180037486  push    r13
0x180037488  push    r14
0x18003748a  push    r15
0x18003748c  sub     rsp, 70h
0x180037490  mov     r15, rdx
0x180037493  mov     rbx, rcx
0x180037496  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18003749b  xor     r13d, r13d
0x18003749e  test    al, al
0x1800374a0  jz      short loc_1800374BA
0x1800374a2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x1800374a9  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x1800374ae  lea     rdx, aCloudexperienc_46; "CloudExperienceHostAPI::OobeDisplayLang"...
0x1800374b5  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x1800374ba  mov     [r15], r13
0x1800374bd  mov     rcx, [rbx+38h]
0x1800374c1  test    rcx, rcx
0x1800374c4  jz      short loc_1800374DA
0x1800374c6  mov     rax, [rcx]
0x1800374c9  mov     rdx, r15
0x1800374cc  mov     rax, [rax+30h]
0x1800374d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374d5  jmp     loc_180037B52
0x1800374da  mov     [rsp+0A8h+arg_18], r13
0x1800374e2  lea     rdx, [rsp+0A8h+arg_18]
0x1800374ea  call    ??$CreateExternalObjectVector@UIOobeDisplayLanguage@CloudExperienceHostAPI@@V?$Vector@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@4567@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@4567@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeDisplayLanguage,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeDisplayLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeDisplayLanguage *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeDisplayLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeDisplayLanguage *>> * *)
0x1800374ef  mov     ebx, eax
0x1800374f1  test    eax, eax
0x1800374f3  jns     short loc_180037516
0x1800374f5  mov     rcx, [rsp+0A8h]; this
0x1800374fd  mov     r9d, eax; char *
0x180037500  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180037507  mov     edx, 51h ; 'Q'; void *
0x18003750c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037511  jmp     loc_1800375FA
0x180037516  mov     [rsp+0A8h+arg_8], r13
0x18003751e  mov     qword ptr [rsp+0A8h+var_68], r13
0x180037523  xor     edx, edx; hFile
0x180037525  mov     r8d, 800h; dwFlags
0x18003752b  lea     rcx, aCoreglobconfig; "coreglobconfig.dll"
0x180037532  call    cs:__imp_LoadLibraryExW
0x180037538  mov     rdi, rax
0x18003753b  mov     [rsp+0A8h+arg_10], rax
0x180037543  test    rax, rax
0x180037546  jnz     short loc_180037563
0x180037548  mov     rcx, [rsp+0A8h]; this
0x180037550  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180037557  lea     edx, [rax+5Dh]; void *
0x18003755a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003755f  mov     ebx, eax
0x180037561  jmp     short loc_1800375DE
0x180037563  lea     rdx, aGetsupporteddi; "GetSupportedDisplayLanguages"
0x18003756a  mov     rcx, rdi; hModule
0x18003756d  call    cs:__imp_GetProcAddress
0x180037573  mov     rbx, rax
0x180037576  test    rax, rax
0x180037579  jnz     short loc_180037588
0x18003757b  mov     ebx, 8000FFFFh
0x180037580  mov     r9d, ebx
0x180037583  lea     edx, [rax+65h]
0x180037586  jmp     short loc_1800375C9
0x180037588  xor     edx, edx
0x18003758a  lea     rcx, [rsp+0A8h+arg_8]
0x180037592  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180037597  mov     ecx, 3Bh ; ';'
0x18003759c  lea     rax, [rsp+0A8h+var_68]
0x1800375a1  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x1800375a6  lea     r9, [rsp+0A8h+arg_8]
0x1800375ae  xor     r8d, r8d
0x1800375b1  xor     edx, edx
0x1800375b3  mov     rax, rbx
0x1800375b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375bb  mov     ebx, eax
0x1800375bd  test    eax, eax
0x1800375bf  jns     short loc_18003760E
0x1800375c1  mov     r9d, eax; char *
0x1800375c4  mov     edx, 6Ch ; 'l'; void *
0x1800375c9  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800375d0  mov     rcx, [rsp+0A8h]; this
0x1800375d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800375dd  nop
0x1800375de  lea     rcx, [rsp+0A8h+arg_10]
0x1800375e6  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800375eb  nop
0x1800375ec  lea     rcx, [rsp+0A8h+arg_8]
0x1800375f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800375f9  nop
0x1800375fa  lea     rcx, [rsp+0A8h+arg_18]
0x180037602  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180037607  mov     eax, ebx
0x180037609  jmp     loc_180037B52
0x18003760e  mov     rdx, [rsp+0A8h+arg_8]
0x180037616  lea     rcx, [rsp+0A8h+var_50]
0x18003761b  call    ?VectorFromDelimitedStringNonConst@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGG@Z; VectorFromDelimitedStringNonConst(ushort const *,ushort)
0x180037620  nop
0x180037621  mov     rsi, qword ptr [rsp+0A8h+var_50]
0x180037626  mov     r12, qword ptr [rsp+0A8h+var_50+8]
0x18003762b  mov     rbx, [rsp+0A8h+arg_18]
0x180037633  cmp     rsi, r12
0x180037636  jz      loc_1800378E3
0x18003763c  lea     rdx, aGetdisplaylang; "GetDisplayLanguageNativeName"
0x180037643  mov     rcx, rdi; hModule
0x180037646  call    cs:__imp_GetProcAddress
0x18003764c  mov     r14, rax
0x18003764f  test    rax, rax
0x180037652  jnz     loc_1800376E0
0x180037658  mov     rcx, [rsp+0A8h]; this
0x180037660  mov     ebx, 8000FFFFh
0x180037665  mov     r9d, ebx; char *
0x180037668  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003766f  lea     edx, [rax+78h]; void *
0x180037672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037677  nop
0x180037678  mov     rcx, qword ptr [rsp+0A8h+var_50]
0x18003767d  test    rcx, rcx
0x180037680  jz      short loc_1800376B0
0x180037682  mov     rdx, qword ptr [rsp+0A8h+var_50+8]
0x180037687  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18003768c  mov     rcx, qword ptr [rsp+0A8h+var_50]
0x180037691  mov     rdx, [rsp+0A8h+var_40]
0x180037696  sub     rdx, rcx
0x180037699  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18003769d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800376a2  xorps   xmm0, xmm0
0x1800376a5  movdqu  [rsp+0A8h+var_50], xmm0
0x1800376ab  mov     [rsp+0A8h+var_40], r13
0x1800376b0  lea     rcx, [rsp+0A8h+arg_10]
0x1800376b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800376bd  nop
0x1800376be  lea     rcx, [rsp+0A8h+arg_8]
0x1800376c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800376cb  nop
0x1800376cc  lea     rcx, [rsp+0A8h+arg_18]
0x1800376d4  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800376d9  mov     eax, ebx
0x1800376db  jmp     loc_180037B52
0x1800376e0  mov     [rsp+0A8h+var_78], r13
0x1800376e5  xor     edx, edx
0x1800376e7  lea     rcx, [rsp+0A8h+var_78]
0x1800376ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800376f1  mov     rcx, rsi
0x1800376f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800376f9  lea     r8, [rsp+0A8h+var_78]
0x1800376fe  mov     edx, 1
0x180037703  mov     rcx, rax
0x180037706  mov     rax, r14
0x180037709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003770e  mov     rcx, [rsp+0A8h]; this
0x180037716  test    eax, eax
0x180037718  jns     short loc_180037733
0x18003771a  mov     r9d, eax; char *
0x18003771d  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180037724  mov     edx, 7Fh; void *
0x180037729  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003772e  jmp     loc_1800378D0
0x180037733  mov     rax, [rsp+0A8h+var_78]
0x180037738  mov     [rsp+0A8h+var_60], rax
0x18003773d  mov     rcx, rsi
0x180037740  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037745  mov     [rsp+0A8h+var_58], rax
0x18003774a  mov     [rsp+0A8h+var_70], r13
0x18003774f  lea     r8, [rsp+0A8h+var_60]
0x180037754  lea     rdx, [rsp+0A8h+var_58]
0x180037759  lea     rcx, [rsp+0A8h+var_70]
0x18003775e  call    ??$MakeAndInitialize@VOobeDisplayLanguageCore@CloudExperienceHostAPI@@V12@PEBGPEAG@Details@WRL@Microsoft@@YAJPEAPEAVOobeDisplayLanguageCore@CloudExperienceHostAPI@@$$QEAPEBG$$QEAPEAG@Z; Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeDisplayLanguageCore,CloudExperienceHostAPI::OobeDisplayLanguageCore,ushort const *,ushort *>(CloudExperienceHostAPI::OobeDisplayLanguageCore * *,ushort const * &&,ushort * &&)
0x180037763  mov     r14d, eax
0x180037766  test    eax, eax
0x180037768  jns     loc_18003780A
0x18003776e  mov     rcx, [rsp+0A8h]; this
0x180037776  mov     r9d, eax; char *
0x180037779  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x180037780  mov     edx, 86h; void *
0x180037785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003778a  nop
0x18003778b  lea     rcx, [rsp+0A8h+var_70]
0x180037790  call    ??1?$com_ptr_t@VOobeDisplayLanguageCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>(void)
0x180037795  nop
0x180037796  lea     rcx, [rsp+0A8h+var_78]
0x18003779b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800377a0  nop
0x1800377a1  mov     rcx, qword ptr [rsp+0A8h+var_50]
0x1800377a6  test    rcx, rcx
0x1800377a9  jz      short loc_1800377D9
0x1800377ab  mov     rdx, qword ptr [rsp+0A8h+var_50+8]
0x1800377b0  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800377b5  mov     rcx, qword ptr [rsp+0A8h+var_50]
0x1800377ba  mov     rdx, [rsp+0A8h+var_40]
0x1800377bf  sub     rdx, rcx
0x1800377c2  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800377c6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800377cb  xorps   xmm0, xmm0
0x1800377ce  movdqu  [rsp+0A8h+var_50], xmm0
0x1800377d4  mov     [rsp+0A8h+var_40], r13
0x1800377d9  lea     rcx, [rsp+0A8h+arg_10]
0x1800377e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800377e6  nop
0x1800377e7  lea     rcx, [rsp+0A8h+arg_8]
0x1800377ef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800377f4  nop
0x1800377f5  lea     rcx, [rsp+0A8h+arg_18]
0x1800377fd  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x180037802  mov     eax, r14d
0x180037805  jmp     loc_180037B52
0x18003780a  mov     rax, [rbx]
0x18003780d  mov     rdx, [rsp+0A8h+var_70]
0x180037812  mov     rcx, rbx
0x180037815  mov     rax, [rax+68h]
0x180037819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003781e  mov     r14d, eax
0x180037821  test    eax, eax
0x180037823  jns     loc_1800378C5
0x180037829  mov     rcx, [rsp+0A8h]; this
0x180037831  mov     r9d, eax; char *
0x180037834  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003783b  mov     edx, 87h; void *
0x180037840  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037845  nop
0x180037846  lea     rcx, [rsp+0A8h+var_70]
0x18003784b  call    ??1?$com_ptr_t@VOobeDisplayLanguageCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>(void)
0x180037850  nop
0x180037851  lea     rcx, [rsp+0A8h+var_78]
0x180037856  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003785b  nop
0x18003785c  mov     rcx, qword ptr [rsp+0A8h+var_50]
0x180037861  test    rcx, rcx
0x180037864  jz      short loc_180037894
0x180037866  mov     rdx, qword ptr [rsp+0A8h+var_50+8]
0x18003786b  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180037870  mov     rcx, qword ptr [rsp+0A8h+var_50]
0x180037875  mov     rdx, [rsp+0A8h+var_40]
0x18003787a  sub     rdx, rcx
0x18003787d  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180037881  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180037886  xorps   xmm0, xmm0
0x180037889  movdqu  [rsp+0A8h+var_50], xmm0
0x18003788f  mov     [rsp+0A8h+var_40], r13
0x180037894  lea     rcx, [rsp+0A8h+arg_10]
0x18003789c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800378a1  nop
0x1800378a2  lea     rcx, [rsp+0A8h+arg_8]
0x1800378aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800378af  nop
0x1800378b0  lea     rcx, [rsp+0A8h+arg_18]
0x1800378b8  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x1800378bd  mov     eax, r14d
0x1800378c0  jmp     loc_180037B52
0x1800378c5  lea     rcx, [rsp+0A8h+var_70]
0x1800378ca  call    ??1?$com_ptr_t@VOobeDisplayLanguageCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::OobeDisplayLanguageCore,wil::err_exception_policy>(void)
0x1800378cf  nop
0x1800378d0  lea     rcx, [rsp+0A8h+var_78]
0x1800378d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800378da  add     rsi, 20h ; ' '
0x1800378de  jmp     loc_180037633
0x1800378e3  mov     [rsp+0A8h+arg_0], r13d
0x1800378eb  mov     rax, [rbx]
0x1800378ee  lea     rdx, [rsp+0A8h+arg_0]
0x1800378f6  mov     rcx, rbx
0x1800378f9  mov     rax, [rax+38h]
0x1800378fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037902  mov     edi, eax
0x180037904  test    eax, eax
0x180037906  jns     loc_180037991
0x18003790c  mov     rcx, [rsp+0A8h]; this
0x180037914  mov     r9d, eax; char *
0x180037917  lea     r8, aShellcommonShe_18; "shellcommon\\shell\\oobe\\core\\compone"...
0x18003791e  mov     edx, 8Ch; void *
0x180037923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037928  nop
0x180037929  mov     rcx, qword ptr [rsp+0A8h+var_50]
0x18003792e  test    rcx, rcx
0x180037931  jz      short loc_180037961
0x180037933  mov     rdx, qword ptr [rsp+0A8h+var_50+8]
0x180037938  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18003793d  mov     rcx, qword ptr [rsp+0A8h+var_50]
0x180037942  mov     rdx, [rsp+0A8h+var_40]
0x180037947  sub     rdx, rcx
0x18003794a  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18003794e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180037953  xorps   xmm0, xmm0
0x180037956  movdqu  [rsp+0A8h+var_50], xmm0
0x18003795c  mov     [rsp+0A8h+var_40], r13
0x180037961  lea     rcx, [rsp+0A8h+arg_10]
0x180037969  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18003796e  nop
0x18003796f  lea     rcx, [rsp+0A8h+arg_8]
0x180037977  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003797c  nop
0x18003797d  lea     rcx, [rsp+0A8h+arg_18]
0x180037985  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18003798a  mov     eax, edi
0x18003798c  jmp     loc_180037B52
0x180037991  cmp     [rsp+0A8h+arg_0], r13d
0x180037999  jbe     loc_180037A9B
0x18003799f  mov     rax, [rbx]
0x1800379a2  mov     rdx, r15
0x1800379a5  mov     rcx, rbx
  ... truncated ...
```
