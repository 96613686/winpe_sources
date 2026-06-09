# OobeExpeditedUpdateManager::FindLanguagesFromCbsPackages(uchar,uint,Windows::Foundation::Collections::IVector<HSTRING__ *> * *)

- ea: `0x180066350`
- end: `0x1800672aa`
- name: `?FindLanguagesFromCbsPackages@OobeExpeditedUpdateManager@@UEAAJEIPEAPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z`
- size: `3930`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006aba0`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x18001d004`
- `0x18001e9a4`
- `0x180023574`
- `0x180039b04`
- `0x18003e430`
- `0x18003e478`
- `0x18003e4d4`
- `0x180040898`
- `0x180048340`
- `0x180048d38`
- `0x18004b734`
- `0x18004b76c`
- `0x18005cf54`
- `0x18005e5a4`
- `0x18005e958`
- `0x180060014`
- `0x1800602c8`
- `0x18006142c`
- `0x18006177c`
- `0x180061a18`
- `0x180061ea0`
- `0x1800627d8`
- `0x180063224`
- `0x180063360`
- `0x180063b08`
- `0x180066350`
- `0x180069d7c`
- `0x18006f488`
- `0x180070d5c`
- `0x180070eb8`
- `0x18007198c`
- `0x1800719b4`
- `0x180071d24`
- `0x180071d78`
- `0x180072534`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180066d25`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180066f2a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066930`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006694e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066a71`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066eec`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066930`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006694e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066a71`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180066eec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800663dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800663dc`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180066b66`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180067019`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180066b66`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180067019`

## string_xrefs

- `0x18006642d`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x180066495`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x1800665a8`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006664c`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x1800666f5`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x1800667bc`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x180066891`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x1800669b0`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x180067297`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x1800663c9`: `Expedited update - Find Language Packages`
- `0x1800663bb`: `Expedited update - Find Language Packages [%d, %d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall OobeExpeditedUpdateManager::FindLanguagesFromCbsPackages(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        wchar_t **a4)
{
  wchar_t **v4; // r12
  unsigned int v5; // r13d
  unsigned int v6; // edi
  __int64 v7; // rsi
  int v8; // r15d
  __int64 v9; // rcx
  const char *v10; // r9
  __int64 result; // rax
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  _QWORD *v15; // r12
  _QWORD *v16; // rcx
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, __int64, _QWORD **, int *); // rdi
  int v19; // eax
  _QWORD *v20; // rdi
  __int64 (__fastcall *v21)(_QWORD *, __int64 *); // rbx
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rax
  int v25; // eax
  unsigned int v26; // ebx
  __int64 (__fastcall **v27)(_QWORD, GUID *, __int64 *); // rax
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64, wchar_t **); // rbx
  int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64, wchar_t **); // rbx
  int v36; // eax
  unsigned int v37; // ebx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64, wchar_t **); // rbx
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rbx
  __int64 i; // r8
  __int64 v44; // rax
  __int64 v45; // rdi
  __int64 v46; // rdx
  __int64 v47; // rdx
  const WCHAR *v48; // rax
  __int64 v49; // rax
  char v50; // bl
  int v51; // edx
  __int64 v52; // rax
  unsigned int v53; // ebx
  __int64 v54; // r10
  __int64 v55; // r10
  int v56; // eax
  int v57; // r8d
  int v58; // r9d
  void *v59; // rbx
  __int64 v60; // rax
  __int64 *v61; // rbx
  __int64 v62; // rax
  int v63; // eax
  __int64 v64; // rbx
  __int64 j; // r8
  __int64 v66; // rax
  __int64 v67; // rdi
  __int64 v68; // rdx
  __int64 v69; // rdx
  const WCHAR *v70; // rax
  void *v71; // rbx
  __int64 v72; // rax
  __int64 *v73; // rbx
  __int64 v74; // rax
  _QWORD **v75; // rdi
  _QWORD *v76; // rbx
  wchar_t *v77; // r15
  void (__fastcall *v78)(wchar_t *, PVOID); // rsi
  char v79; // r8
  PVOID Reserved1; // rdx
  int *v81; // [rsp+20h] [rbp-2F8h]
  __int64 *v82; // [rsp+30h] [rbp-2E8h] BYREF
  __int64 v83; // [rsp+38h] [rbp-2E0h] BYREF
  int v84; // [rsp+40h] [rbp-2D8h]
  unsigned int v85; // [rsp+48h] [rbp-2D0h]
  WCHAR *v86; // [rsp+50h] [rbp-2C8h] BYREF
  wchar_t **v87; // [rsp+58h] [rbp-2C0h]
  _QWORD *v88; // [rsp+60h] [rbp-2B8h]
  __int64 v89; // [rsp+68h] [rbp-2B0h]
  wchar_t **v90; // [rsp+70h] [rbp-2A8h]
  _QWORD *v91; // [rsp+78h] [rbp-2A0h]
  __int128 v92; // [rsp+80h] [rbp-298h] BYREF
  __int64 v93; // [rsp+90h] [rbp-288h]
  __int128 v94; // [rsp+98h] [rbp-280h] BYREF
  __int64 v95; // [rsp+A8h] [rbp-270h]
  HSTRING_HEADER v96; // [rsp+B0h] [rbp-268h] BYREF
  char v97; // [rsp+D0h] [rbp-248h] BYREF
  char v98[8]; // [rsp+D8h] [rbp-240h] BYREF
  char v99; // [rsp+E0h] [rbp-238h] BYREF
  char v100[8]; // [rsp+E8h] [rbp-230h] BYREF
  char v101[16]; // [rsp+F0h] [rbp-228h] BYREF
  char v102[16]; // [rsp+100h] [rbp-218h] BYREF
  char v103[16]; // [rsp+110h] [rbp-208h] BYREF
  char v104[16]; // [rsp+120h] [rbp-1F8h] BYREF
  _QWORD v105[7]; // [rsp+130h] [rbp-1E8h] BYREF
  _QWORD v106[7]; // [rsp+168h] [rbp-1B0h] BYREF
  _QWORD *v107; // [rsp+1A0h] [rbp-178h] BYREF
  __int64 v108; // [rsp+1A8h] [rbp-170h] BYREF
  wchar_t *v109; // [rsp+1B0h] [rbp-168h] BYREF
  __int64 v110; // [rsp+1B8h] [rbp-160h] BYREF
  int v111[2]; // [rsp+1C0h] [rbp-158h] BYREF
  __int64 v112; // [rsp+1C8h] [rbp-150h] BYREF
  wchar_t *v113; // [rsp+1D0h] [rbp-148h] BYREF
  wchar_t *Str; // [rsp+1D8h] [rbp-140h] BYREF
  __int128 v115; // [rsp+1E0h] [rbp-138h] BYREF
  __int64 v116; // [rsp+1F0h] [rbp-128h]
  int v117; // [rsp+1F8h] [rbp-120h] BYREF
  _BYTE v118[16]; // [rsp+200h] [rbp-118h] BYREF
  __int64 v119; // [rsp+210h] [rbp-108h]
  _BYTE v120[32]; // [rsp+220h] [rbp-F8h] BYREF
  __int64 v121; // [rsp+240h] [rbp-D8h] BYREF
  char v122; // [rsp+248h] [rbp-D0h]
  __int128 v123; // [rsp+250h] [rbp-C8h]
  __int128 v124; // [rsp+260h] [rbp-B8h]
  __int64 v125; // [rsp+270h] [rbp-A8h]
  char v126; // [rsp+278h] [rbp-A0h]
  __int128 v127; // [rsp+280h] [rbp-98h]
  char v128; // [rsp+290h] [rbp-88h]
  __int64 v129; // [rsp+298h] [rbp-80h]
  __int64 v130; // [rsp+2A0h] [rbp-78h]
  char v131; // [rsp+2A8h] [rbp-70h]
  _BYTE v132[40]; // [rsp+2B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v4 = a4;
  v87 = a4;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  v89 = a1;
  v85 = a3;
  v90 = a4;
  v8 = 0;
  v84 = 0;
  *a4 = 0;
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2>::GetImpl'::`2'::impl) )
      UnattendLogW(0, L"Expedited update - Find Language Packages [%d, %d]", v6, v5);
    else
      UnattendLogW(0, L"Expedited update - Find Language Packages");
    AcquireSRWLockExclusive((PSRWLOCK)(v7 + 64));
    v83 = v7 + 64;
    if ( !(_BYTE)v6 && *(_DWORD *)(v7 + 120) )
    {
      UnattendLogW(0, L"CBS language packages discovered previously, skipping discovery");
LABEL_77:
      v109 = 0;
      Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
        v9,
        &v109);
      v75 = *(_QWORD ***)(v7 + 112);
      v76 = *v75;
      v77 = v109;
      while ( v76 != v75 )
      {
        v78 = *(void (__fastcall **)(wchar_t *, PVOID))(*(_QWORD *)v77 + 104LL);
        v86 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v76 + 2);
        Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v96, (const WCHAR **)&v86, v79)[1].Reserved.Reserved1;
        v78(v77, Reserved1);
        v76 = (_QWORD *)*v76;
      }
      v109 = 0;
      *v4 = v77;
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v109);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
      return 0;
    }
    OobeExpeditedUpdateManager::_getCbsSession(v7, &v82);
    if ( !v82 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2EB,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)0x8000FFFFLL,
        (int)v81);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
      return 2147549183LL;
    }
    v108 = 0;
    v12 = *v82;
    v108 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v12 + 56))(v82, 16, &v108);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2EE,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v13,
        (int)v81);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v108);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
      return v14;
    }
    v15 = (_QWORD *)(v7 + 104);
    v91 = (_QWORD *)(v7 + 104);
    v88 = (_QWORD *)(v7 + 104);
    v86 = (WCHAR *)(v7 + 104);
    std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::clear(v7 + 104);
    v16 = 0;
    v107 = 0;
    v117 = 0;
    while ( 1 )
    {
      v17 = v108;
      v18 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD **, int *))(*(_QWORD *)v108 + 24LL);
      v107 = 0;
      if ( v16 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v16 + 16LL))(v16, *v16);
      v19 = v18(v17, 1, &v107, &v117);
      if ( v19 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2F4,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v19,
          (int)v81);
      if ( v19 )
      {
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v107);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v108);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
        v4 = v87;
        goto LABEL_77;
      }
      v112 = 0;
      v20 = v107;
      v21 = *(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v107 + 64LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v112,
        0);
      v22 = v21(v20, &v112);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2F7,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v22,
          (int)v81);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v112);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v107);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v108);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
        return v23;
      }
      *(_QWORD *)v111 = 0;
      v24 = *v82;
      *(_QWORD *)v111 = 0;
      v81 = v111;
      v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *, _QWORD))(v24 + 48))(v82, 0, v107, 0);
      v26 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2FB,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v25,
          (int)v111);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v111);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v112);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v107);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v108);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
        return v26;
      }
      v110 = 0;
      v27 = **(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v111;
      v110 = 0;
      v28 = (*v27)(*(_QWORD *)v111, &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed, &v110);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2FD,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v28,
          (int)v111);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v110);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v111);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v112);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v107);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v108);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
        return v29;
      }
      Str = 0;
      v30 = v110;
      v31 = *(__int64 (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v110 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &Str,
        0);
      v32 = v31(v30, 54, &Str);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x301,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v32,
          (int)v111);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Str);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v110);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v111);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v112);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v107);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v108);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
        return v33;
      }
      v109 = 0;
      v34 = v110;
      v35 = *(__int64 (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v110 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v109,
        0);
      v36 = v35(v34, 55, &v109);
      v37 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x303,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v36,
          (int)v111);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v109);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Str);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v110);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v111);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v112);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v107);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v108);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
        return v37;
      }
      if ( wcsstr(Str, L"0") && wcsstr(v109, L"0") )
        break;
LABEL_75:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v109);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Str);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v110);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v111);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v112);
      v16 = v107;
    }
    v113 = 0;
    v38 = v110;
    v39 = *(__int64 (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v110 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v113,
      0);
    v40 = v39(v38, 35, &v113);
    v41 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30B,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v40,
        (int)v111);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v113);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v109);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Str);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v110);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v111);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v112);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v107);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v108);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v82);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v83);
      return v41;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2>::GetImpl'::`2'::impl) )
    {
      if ( wcsstr(v113, L"Language") )
      {
        std::wstring::wstring(v118, v113);
        v115 = 0;
        v116 = 0;
        v42 = 0;
        for ( i = 0; ; i = v45 + 1 )
        {
          v44 = std::wstring::find(v118, 126, i);
          v45 = v44;
          if ( v44 == -1 )
            break;
          v46 = std::wstring::substr(v118, v120, v42, v44 - v42);
          std::vector<std::wstring>::push_back(&v115, v46);
          std::wstring::_Tidy_deallocate(v120);
          v42 = v45 + 1;
        }
        v47 = std::wstring::substr(v118, v120, v42, -1);
        std::vector<std::wstring>::push_back(&v115, v47);
        std::wstring::_Tidy_deallocate(v120);
        if ( (unsigned __int64)((__int64)(*((_QWORD *)&v115 + 1) - v115) >> 5) > 3 )
        {
          v48 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v115 + 96);
          if ( IsValidLocaleName(v48) )
          {
            std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(v132);
            v121 = 0;
            v122 = 0;
            v123 = 0;
            v124 = 0;
            v125 = 0;
            v126 = 0;
            v127 = 0;
            v128 = 0;
            v129 = 0;
            v130 = 0;
            v131 = 0;
            if ( !(unsigned __int8)std::regex_match<std::char_traits<unsigned short>,std::allocator<unsigned short>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>>(
                                     v115,
                                     &v121,
                                     v132)
              || (v49 = std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
                          &v121,
                          v120,
                          1),
                  v8 |= 1u,
                  v84 = v8,
                  v50 = 1,
                  !(unsigned __int8)std::wstring::_Equal(v49, L"Language")) )
            {
              v50 = 0;
            }
            if ( (v8 & 1) != 0 )
            {
              v8 &= ~1u;
              v84 = v8;
              std::wstring::_Tidy_deallocate(v120);
            }
            if ( v50 )
            {
              std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
                &v121,
                v120,
                2);
              if ( *(_BYTE *)(std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::operator[](
                                &v121,
                                4)
                            + 16) )
              {
                v52 = std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
                        &v121,
                        &v96,
                        (unsigned int)(v51 - 1));
                std::wstring::append(v120, v52);
                std::wstring::_Tidy_deallocate(&v96);
              }
              v53 = allPayloadTypeValues;
              if ( v5 )
                v53 = v5;
              try
              {
                if ( (v53 & (unsigned int)PayloadTypeFromName(v120)) != 0 )
                {
                  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v115 + 96);
                  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
                  v56 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v55);
                  std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
                    (unsigned int)&v97,
                    v56,
                    v57,
                    v58,
                    _o_towlower);
                  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::find(
                                    v15,
                                    v98,
                                    v115 + 96) == *(_QWORD *)(v7 + 112) )
                  {
                    v92 = 0;
                    v93 = 0;
                    std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>(
                      v105,
                      v115 + 96,
                      (__int64 *)&v92);
                    std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::emplace<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>(
                      v88,
                      (__int64)v101,
                      v105);
                    std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>::~pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>(v105);
                    v59 = (void *)v92;
                    if ( (_QWORD)v92 )
                    {
                      std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
                        v92,
                        *((__int64 *)&v92 + 1));
                      std::_Deallocate<16>(v59, (struct std::nothrow_t *)((v93 - (_QWORD)v59) & 0xFFFFFFFFFFFFFFF8uLL));
                    }
                  }
                  v60 = std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::_Try_emplace<std::wstring const &,>(
                          v15,
                          (__int64)v102,
                          v115 + 96);
                  v61 = *(__int64 **)v60;
                  v62 = *(_QWORD *)(*(_QWORD *)v60 + 56LL);
                  if ( v62 == v61[8] )
                  {
                    std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy> const &>(
                      v61 + 6,
                      v62,
                      (__int64)&v107);
                  }
                  else
                  {
                    wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
                      v62,
                      &v107);
                    v61[7] += 8;
                  }
                }
              }
              catch ( std::invalid_argument )
              {
                v8 = v84;
                v7 = v89;
                v5 = v85;
                v87 = v90;
                v15 = v91;
              }
              std::wstring::_Tidy_deallocate(v120);
            }
            if ( (_QWORD)v123 )
            {
              std::_Deallocate<16>((void *)v123, (struct std::nothrow_t *)(8 * ((__int64)(v124 - v123) >> 3)));
              v123 = 0;
              *(_QWORD *)&v124 = 0;
            }
            std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v132);
          }
        }
LABEL_73:
        std::vector<std::wstring>::_Tidy(&v115);
        std::wstring::_Tidy_deallocate(v118);
      }
    }
    else if ( wcsstr(v113, L"Language") )
    {
      std::wstring::wstring(v118, v113);
      v63 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v118);
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)&v99,
        v63,
        v63 + 2 * v119,
        v63,
        _o_towlower);
      v115 = 0;
      v116 = 0;
      v64 = 0;
      for ( j = 0; ; j = v67 + 1 )
      {
        v66 = std::wstring::find(v118, 126, j);
        v67 = v66;
        if ( v66 == -1 )
          break;
        v68 = std::wstring::substr(v118, &v96, v64, v66 - v64);
        std::vector<std::wstring>::push_back(&v115, v68);
        std::wstring::_Tidy_deallocate(&v96);
        v64 = v67 + 1;
      }
      v69 = std::wstring::substr(v118, &v96, v64, -1);
      std::vector<std::wstring>::push_back(&v115, v69);
      std::wstring::_Tidy_deallocate(&v96);
      if ( (unsigned __int64)((__int64)(*((_QWORD *)&v115 + 1) - v115) >> 5) > 3 )
      {
        v70 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v115 + 96);
        if ( IsValidLocaleName(v70) )
        {
          if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::find(
                            v15,
                            v100,
                            v115 + 96) == *(_QWORD *)(v7 + 112) )
          {
            v94 = 0;
            v95 = 0;
            std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>(
              v106,
              v115 + 96,
              (__int64 *)&v94);
            std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::emplace<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>(
              v86,
              (__int64)v103,
              v106);
            std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>::~pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>(v106);
            v71 = (void *)v94;
            if ( (_QWORD)v94 )
            {
              std::_Destroy_range<std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>>(
                v94,
                *((__int64 *)&v94 + 1));
              std::_Deallocate<16>(v71, (struct std::nothrow_t *)((v95 - (_QWORD)v71) & 0xFFFFFFFFFFFFFFF8uLL));
            }
          }
          v72 = std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::_Try_emplace<std::wstring const &,>(
                  v15,
                  (__int64)v104,
                  v115 + 96);
          v73 = *(__int64 **)v72;
          v74 = *(_QWORD *)(*(_QWORD *)v72 + 56LL);
          if ( v74 == v73[8] )
          {
            std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy> const &>(
              v73 + 6,
              v74,
              (__int64)&v107);
          }
          else
          {
            wil::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>::com_ptr_t<CloudExperienceHostAPI::IOobeXmlAdapter,wil::err_exception_policy>(
              v74,
              &v107);
            v73[7] += 8;
          }
        }
      }
      goto LABEL_73;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v113);
    goto LABEL_75;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x381,
                           (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180066350  push    rbx
0x180066352  push    rsi
0x180066353  push    rdi
0x180066354  push    r12
0x180066356  push    r13
0x180066358  push    r14
0x18006635a  push    r15
0x18006635c  sub     rsp, 2E0h
0x180066363  mov     rax, cs:__security_cookie
0x18006636a  xor     rax, rsp
0x18006636d  mov     [rsp+318h+var_40], rax
0x180066375  mov     r12, r9
0x180066378  mov     [rsp+318h+var_2C0], r9
0x18006637d  mov     r13d, r8d
0x180066380  movzx   edi, dl
0x180066383  mov     rsi, rcx
0x180066386  mov     [rsp+318h+var_2B0], rcx
0x18006638b  mov     [rsp+318h+var_2D0], r8d
0x180066390  mov     [rsp+318h+var_2A8], r9
0x180066395  xor     r14d, r14d
0x180066398  mov     r15d, r14d
0x18006639b  mov     [rsp+318h+var_2D8], r14d
0x1800663a0  mov     [r9], r14
0x1800663a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NDUPLanguageRemovalV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NDUPLanguageRemovalV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2> `wil::Feature<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2>::GetImpl(void)'::`2'::impl
0x1800663aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NDUPLanguageRemovalV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NDUPLanguageRemovalV2>::__private_IsEnabled(void)
0x1800663af  xor     ecx, ecx
0x1800663b1  test    al, al
0x1800663b3  jz      short loc_1800663C9
0x1800663b5  mov     r8d, edi
0x1800663b8  mov     r9d, r13d
0x1800663bb  lea     rdx, aExpeditedUpdat_8; "Expedited update - Find Language Packag"...
0x1800663c2  call    UnattendLogW
0x1800663c7  jmp     short loc_1800663D5
0x1800663c9  lea     rdx, aExpeditedUpdat_4; "Expedited update - Find Language Packag"...
0x1800663d0  call    UnattendLogW
0x1800663d5  lea     rbx, [rsi+40h]
0x1800663d9  mov     rcx, rbx; SRWLock
0x1800663dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800663e2  mov     [rsp+318h+var_2E0], rbx
0x1800663e7  test    dil, dil
0x1800663ea  jnz     short loc_180066405
0x1800663ec  cmp     [rsi+78h], r14d
0x1800663f0  jz      short loc_180066405
0x1800663f2  lea     rdx, aCbsLanguagePac; "CBS language packages discovered previo"...
0x1800663f9  xor     ecx, ecx
0x1800663fb  call    UnattendLogW
0x180066400  jmp     loc_1800671DF
0x180066405  lea     rdx, [rsp+318h+var_2E8]
0x18006640a  mov     rcx, rsi
0x18006640d  call    ?_getCbsSession@OobeExpeditedUpdateManager@@AEAA?AV?$com_ptr_t@UICbsSession9@@Uerr_returncode_policy@wil@@@wil@@XZ; OobeExpeditedUpdateManager::_getCbsSession(void)
0x180066412  nop
0x180066413  mov     rcx, [rsp+318h+var_2E8]
0x180066418  test    rcx, rcx
0x18006641b  jnz     short loc_18006645B
0x18006641d  mov     rcx, [rsp+318h]; this
0x180066425  mov     ebx, 8000FFFFh
0x18006642a  mov     r9d, ebx; char *
0x18006642d  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x180066434  mov     edx, 2EBh; void *
0x180066439  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006643e  nop
0x18006643f  lea     rcx, [rsp+318h+var_2E8]
0x180066444  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180066449  nop
0x18006644a  lea     rcx, [rsp+318h+var_2E0]
0x18006644f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180066454  mov     eax, ebx
0x180066456  jmp     loc_180067271
0x18006645b  mov     [rsp+318h+var_170], r14
0x180066463  mov     rax, [rcx]
0x180066466  mov     [rsp+318h+var_170], r14
0x18006646e  lea     r8, [rsp+318h+var_170]
0x180066476  mov     edx, 10h
0x18006647b  mov     rax, [rax+38h]
0x18006647f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066484  mov     ebx, eax
0x180066486  test    eax, eax
0x180066488  jns     short loc_1800664D1
0x18006648a  mov     rcx, [rsp+318h]; this
0x180066492  mov     r9d, eax; char *
0x180066495  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006649c  mov     edx, 2EEh; void *
0x1800664a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800664a6  nop
0x1800664a7  lea     rcx, [rsp+318h+var_170]
0x1800664af  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800664b4  nop
0x1800664b5  lea     rcx, [rsp+318h+var_2E8]
0x1800664ba  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800664bf  nop
0x1800664c0  lea     rcx, [rsp+318h+var_2E0]
0x1800664c5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800664ca  mov     eax, ebx
0x1800664cc  jmp     loc_180067271
0x1800664d1  lea     r12, [rsi+68h]
0x1800664d5  mov     [rsp+318h+var_2A0], r12
0x1800664da  mov     [rsp+318h+var_2B8], r12
0x1800664df  mov     [rsp+318h+var_2C8], r12
0x1800664e4  mov     rcx, r12
0x1800664e7  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UICbsIdentity@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::vector<wil::com_ptr_t<ICbsIdentity,wil::err_returncode_policy>>>>,0>>::clear(void)
0x1800664ec  mov     rcx, r14
0x1800664ef  mov     [rsp+318h+var_178], rcx
0x1800664f7  mov     [rsp+318h+var_120], r14d
0x1800664ff  mov     rbx, [rsp+318h+var_170]
0x180066507  mov     rax, [rbx]
0x18006650a  mov     rdi, [rax+18h]
0x18006650e  mov     [rsp+318h+var_178], r14
0x180066516  test    rcx, rcx
0x180066519  jz      short loc_180066528
0x18006651b  mov     rdx, [rcx]
0x18006651e  mov     rax, [rdx+10h]
0x180066522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066527  nop
0x180066528  lea     r9, [rsp+318h+var_120]
0x180066530  lea     r8, [rsp+318h+var_178]
0x180066538  mov     edx, 1
0x18006653d  mov     rcx, rbx
0x180066540  mov     rax, rdi
0x180066543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066548  mov     rcx, [rsp+318h]; this
0x180066550  test    eax, eax
0x180066552  js      loc_180067294
0x180066558  jnz     loc_1800671B4
0x18006655e  mov     [rsp+318h+var_150], r14
0x180066566  mov     rdi, [rsp+318h+var_178]
0x18006656e  mov     rax, [rdi]
0x180066571  mov     rbx, [rax+40h]
0x180066575  xor     edx, edx
0x180066577  lea     rcx, [rsp+318h+var_150]
0x18006657f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180066584  lea     rdx, [rsp+318h+var_150]
0x18006658c  mov     rcx, rdi
0x18006658f  mov     rax, rbx
0x180066592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066597  mov     ebx, eax
0x180066599  test    eax, eax
0x18006659b  jns     short loc_180066600
0x18006659d  mov     rcx, [rsp+318h]; this
0x1800665a5  mov     r9d, eax; char *
0x1800665a8  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800665af  mov     edx, 2F7h; void *
0x1800665b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800665b9  nop
0x1800665ba  lea     rcx, [rsp+318h+var_150]
0x1800665c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800665c7  nop
0x1800665c8  lea     rcx, [rsp+318h+var_178]
0x1800665d0  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800665d5  nop
0x1800665d6  lea     rcx, [rsp+318h+var_170]
0x1800665de  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800665e3  nop
0x1800665e4  lea     rcx, [rsp+318h+var_2E8]
0x1800665e9  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800665ee  nop
0x1800665ef  lea     rcx, [rsp+318h+var_2E0]
0x1800665f4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800665f9  mov     eax, ebx
0x1800665fb  jmp     loc_180067271
0x180066600  mov     qword ptr [rsp+318h+var_158], r14
0x180066608  mov     rcx, [rsp+318h+var_2E8]
0x18006660d  mov     rax, [rcx]
0x180066610  mov     qword ptr [rsp+318h+var_158], r14
0x180066618  lea     rdx, [rsp+318h+var_158]
0x180066620  mov     qword ptr [rsp+318h+var_2F8], rdx; int
0x180066625  xor     r9d, r9d
0x180066628  mov     r8, [rsp+318h+var_178]
0x180066630  xor     edx, edx
0x180066632  mov     rax, [rax+30h]
0x180066636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006663b  mov     ebx, eax
0x18006663d  test    eax, eax
0x18006663f  jns     short loc_1800666B2
0x180066641  mov     rcx, [rsp+318h]; this
0x180066649  mov     r9d, eax; char *
0x18006664c  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x180066653  mov     edx, 2FBh; void *
0x180066658  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006665d  nop
0x18006665e  lea     rcx, [rsp+318h+var_158]
0x180066666  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006666b  nop
0x18006666c  lea     rcx, [rsp+318h+var_150]
0x180066674  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180066679  nop
0x18006667a  lea     rcx, [rsp+318h+var_178]
0x180066682  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180066687  nop
0x180066688  lea     rcx, [rsp+318h+var_170]
0x180066690  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180066695  nop
0x180066696  lea     rcx, [rsp+318h+var_2E8]
0x18006669b  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800666a0  nop
0x1800666a1  lea     rcx, [rsp+318h+var_2E0]
0x1800666a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800666ab  mov     eax, ebx
0x1800666ad  jmp     loc_180067271
0x1800666b2  mov     [rsp+318h+var_160], r14
0x1800666ba  mov     rcx, qword ptr [rsp+318h+var_158]
0x1800666c2  mov     rax, [rcx]
0x1800666c5  mov     [rsp+318h+var_160], r14
0x1800666cd  lea     r8, [rsp+318h+var_160]
0x1800666d5  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x1800666dc  mov     rax, [rax]
0x1800666df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666e4  mov     ebx, eax
0x1800666e6  test    eax, eax
0x1800666e8  jns     short loc_180066769
0x1800666ea  mov     rcx, [rsp+318h]; this
0x1800666f2  mov     r9d, eax; char *
0x1800666f5  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800666fc  mov     edx, 2FDh; void *
0x180066701  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066706  nop
0x180066707  lea     rcx, [rsp+318h+var_160]
0x18006670f  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180066714  nop
0x180066715  lea     rcx, [rsp+318h+var_158]
0x18006671d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180066722  nop
0x180066723  lea     rcx, [rsp+318h+var_150]
0x18006672b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180066730  nop
0x180066731  lea     rcx, [rsp+318h+var_178]
0x180066739  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006673e  nop
0x18006673f  lea     rcx, [rsp+318h+var_170]
0x180066747  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006674c  nop
0x18006674d  lea     rcx, [rsp+318h+var_2E8]
0x180066752  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180066757  nop
0x180066758  lea     rcx, [rsp+318h+var_2E0]
0x18006675d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180066762  mov     eax, ebx
0x180066764  jmp     loc_180067271
0x180066769  mov     [rsp+318h+Str], r14
0x180066771  mov     rdi, [rsp+318h+var_160]
0x180066779  mov     rax, [rdi]
0x18006677c  mov     rbx, [rax+20h]
0x180066780  xor     edx, edx
0x180066782  lea     rcx, [rsp+318h+Str]
0x18006678a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006678f  lea     r8, [rsp+318h+Str]
0x180066797  mov     edx, 36h ; '6'
0x18006679c  mov     rcx, rdi
0x18006679f  mov     rax, rbx
0x1800667a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667a7  mov     ebx, eax
0x1800667a9  test    eax, eax
0x1800667ab  jns     loc_18006683E
0x1800667b1  mov     rcx, [rsp+318h]; this
0x1800667b9  mov     r9d, eax; char *
0x1800667bc  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800667c3  mov     edx, 301h; void *
0x1800667c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800667cd  nop
0x1800667ce  lea     rcx, [rsp+318h+Str]
0x1800667d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800667db  nop
0x1800667dc  lea     rcx, [rsp+318h+var_160]
0x1800667e4  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800667e9  nop
0x1800667ea  lea     rcx, [rsp+318h+var_158]
0x1800667f2  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800667f7  nop
0x1800667f8  lea     rcx, [rsp+318h+var_150]
0x180066800  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180066805  nop
0x180066806  lea     rcx, [rsp+318h+var_178]
0x18006680e  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180066813  nop
0x180066814  lea     rcx, [rsp+318h+var_170]
0x18006681c  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180066821  nop
0x180066822  lea     rcx, [rsp+318h+var_2E8]
0x180066827  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006682c  nop
0x18006682d  lea     rcx, [rsp+318h+var_2E0]
0x180066832  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180066837  mov     eax, ebx
0x180066839  jmp     loc_180067271
0x18006683e  mov     [rsp+318h+var_168], r14
0x180066846  mov     rdi, [rsp+318h+var_160]
0x18006684e  mov     rax, [rdi]
0x180066851  mov     rbx, [rax+20h]
0x180066855  xor     edx, edx
0x180066857  lea     rcx, [rsp+318h+var_168]
0x18006685f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180066864  lea     r8, [rsp+318h+var_168]
0x18006686c  mov     edx, 37h ; '7'
0x180066871  mov     rcx, rdi
0x180066874  mov     rax, rbx
0x180066877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006687c  mov     ebx, eax
0x18006687e  test    eax, eax
0x180066880  jns     loc_180066921
0x180066886  mov     rcx, [rsp+318h]; this
0x18006688e  mov     r9d, eax; char *
  ... truncated ...
```
