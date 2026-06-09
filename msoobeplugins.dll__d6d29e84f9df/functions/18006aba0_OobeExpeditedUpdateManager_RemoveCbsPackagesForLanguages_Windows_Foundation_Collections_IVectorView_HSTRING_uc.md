# OobeExpeditedUpdateManager::RemoveCbsPackagesForLanguages(Windows::Foundation::Collections::IVectorView<HSTRING__ *> *,uchar *)

- ea: `0x18006aba0`
- end: `0x18006b4b7`
- name: `?RemoveCbsPackagesForLanguages@OobeExpeditedUpdateManager@@UEAAJPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAE@Z`
- size: `2327`
- prototype: `__int64 __fastcall(OobeExpeditedUpdateManager *this)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x1800067a8`
- `0x180008544`
- `0x18001ad08`
- `0x18001d004`
- `0x18001d024`
- `0x18001e9a4`
- `0x180023574`
- `0x18003e430`
- `0x18003e4d4`
- `0x18003e56c`
- `0x1800418d8`
- `0x180043c58`
- `0x180048340`
- `0x180048d38`
- `0x1800601b4`
- `0x18006142c`
- `0x180061ea0`
- `0x1800628a8`
- `0x180066350`
- `0x18006aba0`
- `0x18006c9b0`
- `0x180070d5c`
- `0x180070dd8`
- `0x180070eb8`
- `0x180071948`
- `0x18007198c`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18006addf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006ac60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006ac60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006abdd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006abdd`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x18006ad9a`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x18006ad9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ad91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006adaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ad91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006adaf`

## string_xrefs

- `0x18006ac30`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006ac95`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006ad40`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006aeea`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006afe7`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006b0b9`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006b17b`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006b23d`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006b350`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006b068`: `Expedited update - Remove CBS package: [%s]`
- `0x18006aea7`: `Expedited update - Remove CBS packages for languages: [%s]`
- `0x18006af17`: `Expedited update - Remove CBS packages for languages - Releasing CBS session after operation`
- `0x18006b01f`: `Expedited update - Remove CBS packages for languages - Releasing CBS session after operation`
- `0x18006b0fc`: `Expedited update - Remove CBS packages for languages - Releasing CBS session after operation`
- `0x18006b1c9`: `Expedited update - Remove CBS packages for languages - Releasing CBS session after operation`
- `0x18006b28b`: `Expedited update - Remove CBS packages for languages - Releasing CBS session after operation`
- `0x18006b37d`: `Expedited update - Remove CBS packages for languages - Releasing CBS session after operation`
- `0x18006b433`: `Expedited update - Remove CBS packages for languages - Releasing CBS session after operation`
- `0x18006b3f3`: `Expedited update - Remove CBS language packages is done`
- `0x18006b3e5`: `Expedited update - Remove CBS language packages is done [reboot = %d]`
- `0x18006b315`: `Expedited update  - Finalizing removal of [%d] CBS packages`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall OobeExpeditedUpdateManager::RemoveCbsPackagesForLanguages(RTL_SRWLOCK *this, __int64 a2, _BYTE *a3)
{
  RTL_SRWLOCK *v5; // rsi
  int Ptr; // edi
  int LanguagesFromCbsPackages; // eax
  unsigned int v8; // edi
  const char *v9; // r9
  __int64 result; // rax
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // ecx
  unsigned int i; // esi
  __int64 (__fastcall *v15)(__int64, _QWORD, HSTRING *); // rdi
  int v16; // eax
  unsigned int v17; // edi
  const WCHAR *StringRawBuffer; // rax
  PCWSTR v19; // rax
  int v20; // eax
  __int64 v21; // r8
  int v22; // r15d
  __int64 v23; // r13
  __int64 v24; // r14
  __int64 v25; // rax
  _QWORD *v26; // r12
  _QWORD *v27; // rax
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, __int64 *); // rdi
  int v30; // eax
  unsigned int v31; // edi
  __int64 v32; // rax
  int v33; // eax
  __int64 (__fastcall **v34)(HSTRING, GUID *, RTL_SRWLOCK **); // rax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  const char *v38; // r9
  void *v39; // rdx
  unsigned int v40; // r8d
  HSTRING *p_string; // [rsp+20h] [rbp-F8h]
  __int64 *v42; // [rsp+30h] [rbp-E8h] BYREF
  RTL_SRWLOCK *v43; // [rsp+38h] [rbp-E0h] BYREF
  _QWORD *j; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE *v45; // [rsp+48h] [rbp-D0h]
  RTL_SRWLOCK *v46; // [rsp+50h] [rbp-C8h]
  char v47; // [rsp+58h] [rbp-C0h]
  HSTRING string; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+68h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v50; // [rsp+70h] [rbp-A8h] BYREF
  unsigned int v51; // [rsp+78h] [rbp-A0h] BYREF
  __int128 v52; // [rsp+80h] [rbp-98h] BYREF
  __int64 v53; // [rsp+90h] [rbp-88h]
  _OWORD v54[2]; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v55[16]; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v45 = a3;
  *a3 = 0;
  v5 = this + 8;
  AcquireSRWLockShared(this + 8);
  v50 = v5;
  Ptr = (int)this[15].Ptr;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v50);
  try
  {
    if ( !Ptr )
    {
      UnattendLogW(0, L"No CBS language packages discovered previously, discovering packages now");
      v50 = 0;
      LanguagesFromCbsPackages = OobeExpeditedUpdateManager::FindLanguagesFromCbsPackages(this, 0, 0, &v50);
      v8 = LanguagesFromCbsPackages;
      if ( LanguagesFromCbsPackages < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x395,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)LanguagesFromCbsPackages,
          (int)p_string);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v50);
        return v8;
      }
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v50);
    }
    AcquireSRWLockExclusive(v5);
    v43 = v5;
    v51 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v51);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39E,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v11,
        (int)p_string);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v43);
      return v12;
    }
    v13 = v51;
    if ( !v51 )
    {
      v38 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_Hr(retaddr, v39, v40, v38, (int)p_string);
    }
    v52 = 0;
    v53 = 0;
    v54[0] = 0;
    v54[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v54[0]) = 0;
    for ( i = 0; i < v13; ++i )
    {
      string = 0;
      v15 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a2 + 48LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v16 = v15(a2, i, &string);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A7,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v16,
          (int)p_string);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        std::wstring::_Tidy_deallocate(v54);
        std::vector<std::wstring>::_Tidy(&v52);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v43);
        return v17;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( IsValidLocaleName(StringRawBuffer) )
      {
        v19 = WindowsGetStringRawBuffer(string, 0);
        std::wstring::wstring(v55, v19);
        v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&j,
          v20,
          v20 + 2 * v56,
          v20,
          _o_towlower);
        if ( *((_QWORD *)&v52 + 1) == v53 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v52, *((_QWORD *)&v52 + 1), v55);
        }
        else
        {
          std::wstring::wstring(*((_QWORD *)&v52 + 1), v55);
          *((_QWORD *)&v52 + 1) += 32LL;
        }
        std::wstring::append(v54, v55);
        if ( i < v51 - 1 )
          std::wstring::append(v54, L",");
        std::wstring::_Tidy_deallocate(v55);
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      v13 = v51;
    }
    v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
    UnattendLogW(0, L"Expedited update - Remove CBS packages for languages: [%s]", v21);
    v46 = this;
    v47 = 1;
    OobeExpeditedUpdateManager::_getCbsSession(this, &v42);
    if ( !v42 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C1,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)0x8000FFFFLL,
        (int)p_string);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl'::`2'::impl) )
      {
        UnattendLogW(0, L"Expedited update - Remove CBS packages for languages - Releasing CBS session after operation");
        OobeExpeditedUpdateManager::_releaseCbsSession((OobeExpeditedUpdateManager *)this);
      }
      std::wstring::_Tidy_deallocate(v54);
      std::vector<std::wstring>::_Tidy(&v52);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v43);
      return 2147549183LL;
    }
    v22 = 0;
    v23 = *((_QWORD *)&v52 + 1);
    v24 = v52;
LABEL_26:
    if ( v24 != v23 )
    {
      v25 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::_Try_emplace<std::wstring const &,>(
                         &this[13].Ptr,
                         (__int64)v55,
                         v24);
      v26 = *(_QWORD **)(v25 + 48);
      v27 = *(_QWORD **)(v25 + 56);
      for ( j = v27; ; v27 = j )
      {
        if ( v26 == v27 )
        {
          v24 += 32;
          goto LABEL_26;
        }
        v49 = 0;
        v28 = *v26;
        v29 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v26 + 64LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v49,
          0);
        v30 = v29(v28, &v49);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C9,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
            (const char *)(unsigned int)v30,
            (int)p_string);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v49);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl'::`2'::impl) )
          {
            UnattendLogW(
              0,
              L"Expedited update - Remove CBS packages for languages - Releasing CBS session after operation");
            OobeExpeditedUpdateManager::_releaseCbsSession((OobeExpeditedUpdateManager *)this);
          }
          goto LABEL_51;
        }
        UnattendLogW(0, L"Expedited update - Remove CBS package: [%s]", v49);
        string = 0;
        v32 = *v42;
        string = 0;
        p_string = &string;
        v33 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v32 + 48))(v42, 0, *v26, 0);
        v31 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3CE,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
            (const char *)(unsigned int)v33,
            (int)&string);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&string);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v49);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl'::`2'::impl) )
          {
            UnattendLogW(
              0,
              L"Expedited update - Remove CBS packages for languages - Releasing CBS session after operation");
            OobeExpeditedUpdateManager::_releaseCbsSession((OobeExpeditedUpdateManager *)this);
          }
          goto LABEL_51;
        }
        v50 = 0;
        v34 = *(__int64 (__fastcall ***)(HSTRING, GUID *, RTL_SRWLOCK **))string;
        v50 = 0;
        v35 = (*v34)(string, &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed, &v50);
        v31 = v35;
        if ( v35 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3D0,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
            (const char *)(unsigned int)v35,
            (int)&string);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v50);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&string);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v49);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl'::`2'::impl) )
          {
            UnattendLogW(
              0,
              L"Expedited update - Remove CBS packages for languages - Releasing CBS session after operation");
            OobeExpeditedUpdateManager::_releaseCbsSession((OobeExpeditedUpdateManager *)this);
          }
          goto LABEL_51;
        }
        v36 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int64, _QWORD))v50->Ptr + 11))(v50, 12, 0);
        v31 = v36;
        if ( v36 < 0 )
          break;
        ++v22;
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v50);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&string);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v49);
        ++v26;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D4,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v36,
        (int)&string);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v50);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&string);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v49);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl'::`2'::impl) )
      {
        UnattendLogW(0, L"Expedited update - Remove CBS packages for languages - Releasing CBS session after operation");
        OobeExpeditedUpdateManager::_releaseCbsSession((OobeExpeditedUpdateManager *)this);
      }
      goto LABEL_51;
    }
    if ( v22 > 0 )
    {
      UnattendLogW(0, L"Expedited update  - Finalizing removal of [%d] CBS packages", (unsigned int)v22);
      LODWORD(v49) = 0;
      v37 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v42 + 112))(v42, 0, &v49);
      v31 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3DE,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v37,
          (int)p_string);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl'::`2'::impl) )
        {
          UnattendLogW(
            0,
            L"Expedited update - Remove CBS packages for languages - Releasing CBS session after operation");
          OobeExpeditedUpdateManager::_releaseCbsSession((OobeExpeditedUpdateManager *)this);
        }
LABEL_51:
        std::wstring::_Tidy_deallocate(v54);
        std::vector<std::wstring>::_Tidy(&v52);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v43);
        return v31;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2>::GetImpl'::`2'::impl) )
      {
        *v45 = v49 & 1;
        UnattendLogW(0, L"Expedited update - Remove CBS language packages is done [reboot = %d]");
      }
      else
      {
        UnattendLogW(0, L"Expedited update - Remove CBS language packages is done");
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl'::`2'::impl) )
        OobeExpeditedUpdateManager::_releaseCbsSession((OobeExpeditedUpdateManager *)this);
    }
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl'::`2'::impl) )
    {
      UnattendLogW(0, L"Expedited update - Remove CBS packages for languages - Releasing CBS session after operation");
      OobeExpeditedUpdateManager::_releaseCbsSession((OobeExpeditedUpdateManager *)this);
    }
    std::wstring::_Tidy_deallocate(v54);
    std::vector<std::wstring>::_Tidy(&v52);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v43);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3FA,
                           (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18006aba0  push    rbx
0x18006aba2  push    rsi
0x18006aba3  push    rdi
0x18006aba4  push    r12
0x18006aba6  push    r13
0x18006aba8  push    r14
0x18006abaa  push    r15
0x18006abac  sub     rsp, 0E0h
0x18006abb3  mov     rax, cs:__security_cookie
0x18006abba  xor     rax, rsp
0x18006abbd  mov     [rsp+118h+var_40], rax
0x18006abc5  mov     [rsp+118h+var_D0], r8
0x18006abca  mov     r14, rdx
0x18006abcd  mov     rbx, rcx
0x18006abd0  xor     r15d, r15d
0x18006abd3  mov     [r8], r15b
0x18006abd6  lea     rsi, [rcx+40h]
0x18006abda  mov     rcx, rsi; SRWLock
0x18006abdd  call    cs:__imp_AcquireSRWLockShared
0x18006abe3  mov     [rsp+118h+var_A8], rsi
0x18006abe8  mov     edi, [rbx+78h]
0x18006abeb  lea     rcx, [rsp+118h+var_A8]
0x18006abf0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006abf5  test    edi, edi
0x18006abf7  jnz     short loc_18006AC5D
0x18006abf9  lea     rdx, aNoCbsLanguageP; "No CBS language packages discovered pre"...
0x18006ac00  xor     ecx, ecx
0x18006ac02  call    UnattendLogW
0x18006ac07  nop
0x18006ac08  mov     [rsp+118h+var_A8], r15
0x18006ac0d  lea     r9, [rsp+118h+var_A8]
0x18006ac12  xor     r8d, r8d
0x18006ac15  xor     edx, edx
0x18006ac17  mov     rcx, rbx
0x18006ac1a  call    ?FindLanguagesFromCbsPackages@OobeExpeditedUpdateManager@@UEAAJEIPEAPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z; OobeExpeditedUpdateManager::FindLanguagesFromCbsPackages(uchar,uint,Windows::Foundation::Collections::IVector<HSTRING__ *> * *)
0x18006ac1f  mov     edi, eax
0x18006ac21  test    eax, eax
0x18006ac23  jns     short loc_18006AC53
0x18006ac25  mov     rcx, [rsp+118h]; this
0x18006ac2d  mov     r9d, eax; char *
0x18006ac30  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006ac37  mov     edx, 395h; void *
0x18006ac3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ac41  nop
0x18006ac42  lea     rcx, [rsp+118h+var_A8]
0x18006ac47  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006ac4c  mov     eax, edi
0x18006ac4e  jmp     loc_18006B478
0x18006ac53  lea     rcx, [rsp+118h+var_A8]
0x18006ac58  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006ac5d  mov     rcx, rsi; SRWLock
0x18006ac60  call    cs:__imp_AcquireSRWLockExclusive
0x18006ac66  mov     [rsp+118h+var_E0], rsi
0x18006ac6b  mov     [rsp+118h+var_A0], r15d
0x18006ac70  mov     rax, [r14]
0x18006ac73  lea     rdx, [rsp+118h+var_A0]
0x18006ac78  mov     rcx, r14
0x18006ac7b  mov     rax, [rax+38h]
0x18006ac7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac84  mov     edi, eax
0x18006ac86  test    eax, eax
0x18006ac88  jns     short loc_18006ACB8
0x18006ac8a  mov     rcx, [rsp+118h]; this
0x18006ac92  mov     r9d, eax; char *
0x18006ac95  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006ac9c  mov     edx, 39Eh; void *
0x18006aca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006aca6  nop
0x18006aca7  lea     rcx, [rsp+118h+var_E0]
0x18006acac  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006acb1  mov     eax, edi
0x18006acb3  jmp     loc_18006B478
0x18006acb8  mov     ecx, [rsp+118h+var_A0]
0x18006acbc  test    ecx, ecx
0x18006acbe  jz      loc_18006B49B
0x18006acc4  xorps   xmm0, xmm0
0x18006acc7  movdqu  [rsp+118h+var_98], xmm0
0x18006acd0  mov     [rsp+118h+var_88], r15
0x18006acd8  movups  [rsp+118h+var_80], xmm0
0x18006ace0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006ace8  movdqu  [rsp+118h+var_70], xmm1
0x18006acf1  mov     word ptr [rsp+118h+var_80], r15w
0x18006acfa  mov     esi, r15d
0x18006acfd  cmp     esi, ecx
0x18006acff  jnb     loc_18006AE97
0x18006ad05  mov     [rsp+118h+string], r15
0x18006ad0a  mov     rax, [r14]
0x18006ad0d  mov     rdi, [rax+30h]
0x18006ad11  xor     edx, edx
0x18006ad13  lea     rcx, [rsp+118h+string]
0x18006ad18  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18006ad1d  lea     r8, [rsp+118h+string]
0x18006ad22  mov     edx, esi
0x18006ad24  mov     rcx, r14
0x18006ad27  mov     rax, rdi
0x18006ad2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad2f  mov     edi, eax
0x18006ad31  test    eax, eax
0x18006ad33  jns     short loc_18006AD8A
0x18006ad35  mov     rcx, [rsp+118h]; this
0x18006ad3d  mov     r9d, eax; char *
0x18006ad40  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006ad47  mov     edx, 3A7h; void *
0x18006ad4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ad51  nop
0x18006ad52  lea     rcx, [rsp+118h+string]; this
0x18006ad57  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006ad5c  nop
0x18006ad5d  lea     rcx, [rsp+118h+var_80]
0x18006ad65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ad6a  nop
0x18006ad6b  lea     rcx, [rsp+118h+var_98]
0x18006ad73  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18006ad78  nop
0x18006ad79  lea     rcx, [rsp+118h+var_E0]
0x18006ad7e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006ad83  mov     eax, edi
0x18006ad85  jmp     loc_18006B478
0x18006ad8a  xor     edx, edx; length
0x18006ad8c  mov     rcx, [rsp+118h+string]; string
0x18006ad91  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ad97  mov     rcx, rax; lpLocaleName
0x18006ad9a  call    cs:__imp_IsValidLocaleName
0x18006ada0  test    eax, eax
0x18006ada2  jz      loc_18006AE82
0x18006ada8  xor     edx, edx; length
0x18006adaa  mov     rcx, [rsp+118h+string]; string
0x18006adaf  call    cs:__imp_WindowsGetStringRawBuffer
0x18006adb5  mov     rdx, rax
0x18006adb8  lea     rcx, [rsp+118h+var_60]
0x18006adc0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006adc5  nop
0x18006adc6  lea     rcx, [rsp+118h+var_60]
0x18006adce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006add3  mov     rcx, [rsp+118h+var_50]
0x18006addb  lea     r8, [rax+rcx*2]
0x18006addf  mov     rcx, cs:__imp__o_towlower
0x18006ade6  mov     qword ptr [rsp+118h+var_F8], rcx
0x18006adeb  mov     r9, rax
0x18006adee  mov     rdx, rax
0x18006adf1  lea     rcx, [rsp+118h+var_D8]
0x18006adf6  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18006adfb  mov     rax, qword ptr [rsp+118h+var_98+8]
0x18006ae03  cmp     rax, [rsp+118h+var_88]
0x18006ae0b  jz      short loc_18006AE28
0x18006ae0d  lea     rdx, [rsp+118h+var_60]
0x18006ae15  mov     rcx, rax
0x18006ae18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006ae1d  add     qword ptr [rsp+118h+var_98+8], 20h ; ' '
0x18006ae26  jmp     short loc_18006AE40
0x18006ae28  lea     r8, [rsp+118h+var_60]
0x18006ae30  mov     rdx, rax
0x18006ae33  lea     rcx, [rsp+118h+var_98]
0x18006ae3b  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18006ae40  lea     rdx, [rsp+118h+var_60]
0x18006ae48  lea     rcx, [rsp+118h+var_80]
0x18006ae50  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18006ae55  mov     eax, [rsp+118h+var_A0]
0x18006ae59  dec     eax
0x18006ae5b  cmp     esi, eax
0x18006ae5d  jnb     short loc_18006AE74
0x18006ae5f  lea     rdx, asc_1800E7590; ","
0x18006ae66  lea     rcx, [rsp+118h+var_80]
0x18006ae6e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18006ae73  nop
0x18006ae74  lea     rcx, [rsp+118h+var_60]
0x18006ae7c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ae81  nop
0x18006ae82  lea     rcx, [rsp+118h+string]; this
0x18006ae87  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006ae8c  inc     esi
0x18006ae8e  mov     ecx, [rsp+118h+var_A0]
0x18006ae92  jmp     loc_18006ACFD
0x18006ae97  lea     rcx, [rsp+118h+var_80]
0x18006ae9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006aea4  mov     r8, rax
0x18006aea7  lea     rdx, aExpeditedUpdat_10; "Expedited update - Remove CBS packages "...
0x18006aeae  xor     ecx, ecx
0x18006aeb0  call    UnattendLogW
0x18006aeb5  mov     [rsp+118h+var_C8], rbx
0x18006aeba  mov     [rsp+118h+var_C0], 1
0x18006aebf  lea     rdx, [rsp+118h+var_E8]
0x18006aec4  mov     rcx, rbx
0x18006aec7  call    ?_getCbsSession@OobeExpeditedUpdateManager@@AEAA?AV?$com_ptr_t@UICbsSession9@@Uerr_returncode_policy@wil@@@wil@@XZ; OobeExpeditedUpdateManager::_getCbsSession(void)
0x18006aecc  nop
0x18006aecd  xor     esi, esi
0x18006aecf  cmp     [rsp+118h+var_E8], rsi
0x18006aed4  jnz     loc_18006AF5B
0x18006aeda  mov     rcx, [rsp+118h]; this
0x18006aee2  mov     edi, 8000FFFFh
0x18006aee7  mov     r9d, edi; char *
0x18006aeea  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006aef1  mov     edx, 3C1h; void *
0x18006aef6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006aefb  nop
0x18006aefc  lea     rcx, [rsp+118h+var_E8]
0x18006af01  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006af06  nop
0x18006af07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl(void)'::`2'::impl
0x18006af0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(void)
0x18006af13  test    al, al
0x18006af15  jz      short loc_18006AF2E
0x18006af17  lea     rdx, aExpeditedUpdat; "Expedited update - Remove CBS packages "...
0x18006af1e  xor     ecx, ecx
0x18006af20  call    UnattendLogW
0x18006af25  mov     rcx, rbx; this
0x18006af28  call    ?_releaseCbsSession@OobeExpeditedUpdateManager@@AEAAXXZ; OobeExpeditedUpdateManager::_releaseCbsSession(void)
0x18006af2d  nop
0x18006af2e  lea     rcx, [rsp+118h+var_80]
0x18006af36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006af3b  nop
0x18006af3c  lea     rcx, [rsp+118h+var_98]
0x18006af44  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18006af49  nop
0x18006af4a  lea     rcx, [rsp+118h+var_E0]
0x18006af4f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006af54  mov     eax, edi
0x18006af56  jmp     loc_18006B478
0x18006af5b  mov     r15d, esi
0x18006af5e  mov     r14, qword ptr [rsp+118h+var_98]
0x18006af66  mov     r13, qword ptr [rsp+118h+var_98+8]
0x18006af6e  cmp     r14, r13
0x18006af71  jz      loc_18006B309
0x18006af77  lea     rcx, [rbx+68h]
0x18006af7b  mov     r8, r14
0x18006af7e  lea     rdx, [rsp+118h+var_60]
0x18006af86  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18006af8b  mov     rax, [rax]
0x18006af8e  mov     r12, [rax+30h]
0x18006af92  mov     rax, [rax+38h]
0x18006af96  mov     [rsp+118h+var_D8], rax
0x18006af9b  cmp     r12, rax
0x18006af9e  jz      loc_18006B300
0x18006afa4  mov     [rsp+118h+var_B0], rsi
0x18006afa9  mov     rsi, [r12]
0x18006afad  mov     rax, [rsi]
0x18006afb0  mov     rdi, [rax+40h]
0x18006afb4  xor     edx, edx
0x18006afb6  lea     rcx, [rsp+118h+var_B0]
0x18006afbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006afc0  lea     rdx, [rsp+118h+var_B0]
0x18006afc5  mov     rcx, rsi
0x18006afc8  mov     rax, rdi
0x18006afcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006afd0  mov     edi, eax
0x18006afd2  xor     esi, esi
0x18006afd4  test    eax, eax
0x18006afd6  jns     loc_18006B063
0x18006afdc  mov     rcx, [rsp+118h]; this
0x18006afe4  mov     r9d, eax; char *
0x18006afe7  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006afee  mov     edx, 3C9h; void *
0x18006aff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006aff8  nop
0x18006aff9  lea     rcx, [rsp+118h+var_B0]
0x18006affe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006b003  nop
0x18006b004  lea     rcx, [rsp+118h+var_E8]
0x18006b009  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006b00e  nop
0x18006b00f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::GetImpl(void)'::`2'::impl
0x18006b016  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NDUPCbsSessionHandlingFix>::__private_IsEnabled(void)
0x18006b01b  test    al, al
0x18006b01d  jz      short loc_18006B036
0x18006b01f  lea     rdx, aExpeditedUpdat; "Expedited update - Remove CBS packages "...
0x18006b026  xor     ecx, ecx
0x18006b028  call    UnattendLogW
0x18006b02d  mov     rcx, rbx; this
0x18006b030  call    ?_releaseCbsSession@OobeExpeditedUpdateManager@@AEAAXXZ; OobeExpeditedUpdateManager::_releaseCbsSession(void)
0x18006b035  nop
0x18006b036  lea     rcx, [rsp+118h+var_80]
0x18006b03e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b043  nop
0x18006b044  lea     rcx, [rsp+118h+var_98]
0x18006b04c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18006b051  nop
0x18006b052  lea     rcx, [rsp+118h+var_E0]
0x18006b057  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006b05c  mov     eax, edi
0x18006b05e  jmp     loc_18006B478
0x18006b063  mov     r8, [rsp+118h+var_B0]
0x18006b068  lea     rdx, aExpeditedUpdat_1; "Expedited update - Remove CBS package: "...
0x18006b06f  xor     ecx, ecx
0x18006b071  call    UnattendLogW
0x18006b076  mov     [rsp+118h+string], rsi
0x18006b07b  mov     rcx, [rsp+118h+var_E8]
0x18006b080  mov     rax, [rcx]
0x18006b083  mov     [rsp+118h+string], rsi
0x18006b088  lea     rdx, [rsp+118h+string]
0x18006b08d  mov     qword ptr [rsp+118h+var_F8], rdx; int
0x18006b092  xor     r9d, r9d
0x18006b095  mov     r8, [r12]
0x18006b099  xor     edx, edx
0x18006b09b  mov     rax, [rax+30h]
0x18006b09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b0a4  mov     edi, eax
0x18006b0a6  test    eax, eax
0x18006b0a8  jns     loc_18006B140
0x18006b0ae  mov     rcx, [rsp+118h]; this
0x18006b0b6  mov     r9d, eax; char *
  ... truncated ...
```
