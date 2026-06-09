# CUserProfileRoamingProvider::_CopyExclusionListFolders(ushort const *,ulong)

- ea: `0x180007bd0`
- end: `0x180008250`
- name: `?_CopyExclusionListFolders@CUserProfileRoamingProvider@@AEAAJPEBGK@Z`
- size: `1664`
- prototype: `__int64 __fastcall(WCHAR *this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x180006a80`
- `0x180006a9c`
- `0x180007468`
- `0x180007bd0`
- `0x180008b1c`
- `0x180008b54`
- `0x18000a520`
- `0x18000c534`
- `0x18000c7f4`
- `0x18000ccfc`
- `0x18000fca8`
- `0x18001134c`
- `0x180011394`
- `0x180011478`
- `0x180011498`
- `0x180013dc0`
- `0x180015568`
- `0x180016b68`
- `0x18001d96c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000815f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000815f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008178`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007d1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007d1a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007cbc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007cbc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007d52`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000818e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007d52`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000818e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007eb6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007ee0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007eb6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007ee0`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180007f79`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180008016`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180007f79`
- `USERENV!__imp_CopyProfileDirectoryEx2` at `0x180008016`
- `USERENV!__imp_GetLongProfilePathName` at `0x180007e38`
- `USERENV!__imp_GetLongProfilePathName` at `0x180007ea1`
- `USERENV!__imp_GetLongProfilePathName` at `0x180007e38`
- `USERENV!__imp_GetLongProfilePathName` at `0x180007ea1`
- `SHELL32!SHGetKnownFolderPath` at `0x180008064`
- `SHELL32!SHGetKnownFolderPath` at `0x180008064`

## string_xrefs

- `0x180007d2d`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180007da3`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180007fa2`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180007fdf`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x18000803f`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180008075`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800080a5`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800080d6`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180008140`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800081b9`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x1800081eb`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180008217`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180007f92`: `Failed to copy <%ws> to <%ws>.`
- `0x18000802f`: `Failed to copy <%ws> to <%ws>.`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_CopyExclusionListFolders(
        WCHAR *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned int v3; // r15d
  const unsigned __int16 *v6; // rax
  const unsigned __int16 *v7; // rsi
  unsigned int ExclusionList; // ebx
  __int64 v9; // rdx
  const unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // rsi
  const unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdi
  __int64 v14; // rdx
  bool v15; // r14
  HRESULT Instance; // eax
  struct IKnownFolderManagerVtbl *lpVtbl; // rax
  const unsigned __int16 *v18; // rdx
  void *v19; // rcx
  int v20; // r12d
  CUserProfileRoamingProvider *v21; // r14
  const unsigned __int16 *v22; // rdx
  const WCHAR *v23; // r13
  const WCHAR *v24; // rbx
  unsigned int LongProfilePathName; // eax
  const WCHAR *v26; // r12
  const WCHAR *v27; // rbx
  unsigned int v28; // eax
  DWORD FileAttributesW; // eax
  char v30; // bl
  int v31; // r15d
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  int v35; // eax
  HRESULT v36; // eax
  __int64 v37; // rax
  __int64 v38; // rax
  void *v39; // rcx
  void *v40; // rcx
  int ppv; // [rsp+20h] [rbp-99h]
  int ppva; // [rsp+20h] [rbp-99h]
  int v44; // [rsp+40h] [rbp-79h]
  const WCHAR *v45; // [rsp+48h] [rbp-71h] BYREF
  const WCHAR *v46; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v47; // [rsp+58h] [rbp-61h]
  LPVOID pv; // [rsp+60h] [rbp-59h] BYREF
  bool v49; // [rsp+68h] [rbp-51h]
  struct IKnownFolderManager *v50; // [rsp+70h] [rbp-49h] BYREF
  unsigned int v51; // [rsp+78h] [rbp-41h] BYREF
  PWSTR ppszPath; // [rsp+80h] [rbp-39h] BYREF
  BOOL v53; // [rsp+88h] [rbp-31h]
  const unsigned __int16 *v54; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int16 *v55; // [rsp+98h] [rbp-21h] BYREF
  char v56[8]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-11h] BYREF
  char v58[8]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-1h] BYREF
  KNOWNFOLDERID rfid; // [rsp+C0h] [rbp+7h] BYREF
  char v61; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v3 = a3;
  v47 = a3;
  ppszPath = this;
  if ( !a2 || !*a2 )
  {
    ExclusionList = -2147024809;
    v9 = 1508;
    goto LABEL_77;
  }
  v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 72LL))(*((_QWORD *)this + 1));
  v7 = v6;
  if ( !v6 || !*v6 )
  {
    ExclusionList = -2147024735;
    v9 = 1512;
    goto LABEL_77;
  }
  ExclusionList = CUserProfileRoamingProvider::_GetExclusionList((CUserProfileRoamingProvider *)this);
  if ( (ExclusionList & 0x80000000) != 0 )
  {
    v9 = 1517;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)ExclusionList,
      ppv);
    return ExclusionList;
  }
  v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1));
  v11 = ConvertExclusionList(v7, v10);
  v54 = v11;
  if ( !v11 )
  {
    ExclusionList = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F1,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)0x80004005LL,
      ppv);
    goto LABEL_73;
  }
  v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 104LL))(*((_QWORD *)this + 1));
  v13 = ConvertExclusionList(a2, v12);
  v55 = v13;
  if ( !v13 )
  {
    ExclusionList = -2147467259;
    v14 = 1524;
    goto LABEL_71;
  }
  ExclusionList = CoInitializeEx(0, 4u);
  if ( (int)(ExclusionList + 0x80000000) >= 0 && ExclusionList != -2147417850 )
  {
    v14 = 1534;
LABEL_71:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)ExclusionList,
      ppv);
    goto LABEL_72;
  }
  v15 = ExclusionList != -2147417850;
  v53 = ExclusionList != -2147417850;
  v49 = ExclusionList != -2147417850;
  v50 = 0;
  Instance = CoCreateInstance(
               &CLSID_KnownFolderManager,
               0,
               1u,
               &GUID_8be2d872_86aa_4d47_b776_32cca40c7018,
               (LPVOID *)&v50);
  ExclusionList = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x609,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    goto LABEL_14;
  }
  pv = 0;
  v51 = 0;
  lpVtbl = v50->lpVtbl;
  *(_QWORD *)&rfid.Data1 = &pv;
  *(_QWORD *)rfid.Data4 = 0;
  v61 = 1;
  ExclusionList = ((__int64 (__fastcall *)(struct IKnownFolderManager *, unsigned __int8 *, unsigned int *))lpVtbl->GetFolderIds)(
                    v50,
                    rfid.Data4,
                    &v51);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&rfid);
  if ( (ExclusionList & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60E,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)ExclusionList,
      ppva);
    v19 = pv;
    pv = 0;
    if ( v19 )
      CoTaskMemFree(v19);
    goto LABEL_14;
  }
  v20 = 0;
  v44 = 0;
  if ( !*v13 )
    goto LABEL_65;
  v21 = (CUserProfileRoamingProvider *)ppszPath;
  while ( *v11 )
  {
    v45 = 0;
    if ( (unsigned int)StringIsPrefixed(v13, v18) )
    {
      v23 = v13;
    }
    else
    {
      v57 = 0;
      v24 = v45;
      if ( v45 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v56);
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v24);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v56);
      }
      v45 = 0;
      LongProfilePathName = GetLongProfilePathName(v13, &v45, &v57);
      if ( LongProfilePathName )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x634,
          (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)LongProfilePathName,
          ppva);
        goto LABEL_55;
      }
      v23 = v45;
    }
    v46 = 0;
    if ( (unsigned int)StringIsPrefixed(v11, v22) )
    {
      v26 = v11;
    }
    else
    {
      v59 = 0;
      v27 = v46;
      if ( v46 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v58);
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v27);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v58);
      }
      v46 = 0;
      v28 = GetLongProfilePathName(v11, &v46, &v59);
      if ( v28 )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x64A,
          (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)v28,
          ppva);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
        goto LABEL_56;
      }
      v26 = v46;
    }
    if ( GetFileAttributesW(v26) != -1
      || (FileAttributesW = GetFileAttributesW(v23), v30 = FileAttributesW, FileAttributesW == -1)
      || (FileAttributesW & 0x410) != 0x10
      || (FileAttributesW & 0x4000) != 0 && (v3 & 0x44000) != 0
      || (v31 = v3 & 0x20000) != 0 && (FileAttributesW & 0x4000) != 0
      || (rfid = 0,
          !CUserProfileRoamingProvider::_IsNonRedirectedKnownFolder(v21, v50, (struct _GUID *)pv, v51, v11, &rfid)) )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
      v20 = v44;
      goto LABEL_56;
    }
    if ( v31 && (v30 & 4) == 0 )
    {
      v47 |= 0x200000u;
      v32 = CopyProfileDirectoryEx2(v13, v11, v47, 0, 0, 0);
      wil::details::in1diag3::Log_GetLastErrorIfMsg(
        retaddr,
        (void *)0x688,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(v32 == 0),
        (bool)"Failed to copy <%ws> to <%ws>.",
        (const char *)v13);
LABEL_51:
      v20 = v44;
      goto LABEL_52;
    }
    v33 = v47;
    v34 = CopyRupDirectory(v23, v26, (v47 >> 15) & 1);
    if ( v34 >= 0 )
    {
      v35 = CopyProfileDirectoryEx2(v13, v11, v33, 0, 0, 0);
      wil::details::in1diag3::Log_GetLastErrorIfMsg(
        retaddr,
        (void *)0x697,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(v35 == 0),
        (bool)"Failed to copy <%ws> to <%ws>.",
        (const char *)v13);
      ppszPath = 0;
      v36 = SHGetKnownFolderPath(&rfid, 0x8800u, 0, &ppszPath);
      if ( v36 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x69C,
          (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
          (const char *)(unsigned int)v36);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
      goto LABEL_51;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x691,
      (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
      (const char *)(unsigned int)v34);
    v20 = ++v44;
LABEL_52:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
LABEL_55:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
LABEL_56:
    v37 = -1;
    do
      ++v37;
    while ( v13[v37] );
    v13 += v37 + 1;
    v38 = -1;
    do
      ++v38;
    while ( v11[v38] );
    v11 += v38 + 1;
    v3 = v47;
    if ( !*v13 )
      break;
  }
  v15 = v53;
  if ( !v20 )
  {
LABEL_65:
    v40 = pv;
    pv = 0;
    if ( v40 )
      CoTaskMemFree(v40);
    wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v50);
    if ( v15 )
      CoUninitialize();
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
    return 0;
  }
  ExclusionList = -2147024597;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6A8,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
    (const char *)0x8007012BLL,
    ppva);
  v39 = pv;
  pv = 0;
  if ( v39 )
    CoTaskMemFree(v39);
LABEL_14:
  wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(&v50);
  if ( v15 )
    CoUninitialize();
LABEL_72:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v55);
LABEL_73:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
  return ExclusionList;
}

```

## disassembly

```asm
0x180007bd0  mov     [rsp-8+arg_18], rbx
0x180007bd5  push    rbp
0x180007bd6  push    rsi
0x180007bd7  push    rdi
0x180007bd8  push    r12
0x180007bda  push    r13
0x180007bdc  push    r14
0x180007bde  push    r15
0x180007be0  lea     rbp, [rsp-27h]
0x180007be5  sub     rsp, 0E0h
0x180007bec  mov     rax, cs:__security_cookie
0x180007bf3  xor     rax, rsp
0x180007bf6  mov     [rbp+57h+var_38], rax
0x180007bfa  mov     r15d, r8d
0x180007bfd  mov     [rbp+57h+var_B8], r8d
0x180007c01  mov     rdi, rdx
0x180007c04  mov     r14, rcx
0x180007c07  mov     [rbp+57h+ppszPath], rcx
0x180007c0b  xor     r13d, r13d
0x180007c0e  test    rdx, rdx
0x180007c11  jz      loc_18000820A
0x180007c17  cmp     [rdx], r13w
0x180007c1b  jz      loc_18000820A
0x180007c21  mov     rcx, [rcx+8]
0x180007c25  mov     rax, [rcx]
0x180007c28  mov     rax, [rax+48h]
0x180007c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c31  mov     rsi, rax
0x180007c34  test    rax, rax
0x180007c37  jz      loc_1800081FE
0x180007c3d  cmp     [rax], r13w
0x180007c41  jz      loc_1800081FE
0x180007c47  mov     rcx, r14; this
0x180007c4a  call    ?_GetExclusionList@CUserProfileRoamingProvider@@AEAAJXZ; CUserProfileRoamingProvider::_GetExclusionList(void)
0x180007c4f  mov     ebx, eax
0x180007c51  test    eax, eax
0x180007c53  jns     short loc_180007C5F
0x180007c55  mov     edx, 5EDh
0x180007c5a  jmp     loc_180008214
0x180007c5f  mov     rcx, [r14+8]
0x180007c63  mov     rax, [rcx]
0x180007c66  mov     rax, [rax+68h]
0x180007c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c6f  mov     rdx, rax; unsigned __int16 *
0x180007c72  mov     rcx, rsi; unsigned __int16 *
0x180007c75  call    ?ConvertExclusionList@@YAPEAGPEBG0@Z; ConvertExclusionList(ushort const *,ushort const *)
0x180007c7a  mov     rsi, rax
0x180007c7d  mov     [rbp+57h+var_80], rax
0x180007c81  test    rax, rax
0x180007c84  jz      loc_1800081DF
0x180007c8a  mov     rcx, [r14+8]
0x180007c8e  mov     rdx, [rcx]
0x180007c91  mov     rax, [rdx+68h]
0x180007c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c9a  mov     rdx, rax; unsigned __int16 *
0x180007c9d  mov     rcx, rdi; unsigned __int16 *
0x180007ca0  call    ?ConvertExclusionList@@YAPEAGPEBG0@Z; ConvertExclusionList(ushort const *,ushort const *)
0x180007ca5  mov     rdi, rax
0x180007ca8  mov     [rbp+57h+var_78], rax
0x180007cac  test    rax, rax
0x180007caf  jz      loc_1800081AC
0x180007cb5  mov     edx, 4; dwCoInit
0x180007cba  xor     ecx, ecx; pvReserved
0x180007cbc  call    cs:__imp_CoInitializeEx
0x180007cc2  mov     ebx, eax
0x180007cc4  mov     eax, 80000000h
0x180007cc9  lea     ecx, [rbx+rax]
0x180007ccc  mov     edx, 80010106h
0x180007cd1  test    eax, ecx
0x180007cd3  jnz     short loc_180007CE3
0x180007cd5  cmp     ebx, edx
0x180007cd7  jz      short loc_180007CE3
0x180007cd9  mov     edx, 5FEh
0x180007cde  jmp     loc_1800081B6
0x180007ce3  mov     r12d, 1
0x180007ce9  mov     r14d, r12d
0x180007cec  cmp     ebx, edx
0x180007cee  cmovz   r14d, r13d
0x180007cf2  mov     [rbp+57h+var_88], r14d
0x180007cf6  mov     [rbp+57h+var_A8], r14b
0x180007cfa  mov     [rbp+57h+var_A0], r13
0x180007cfe  lea     rax, [rbp+57h+var_A0]
0x180007d02  mov     [rsp+110h+ppv], rax; int
0x180007d07  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x180007d0e  mov     r8d, r12d; dwClsContext
0x180007d11  xor     edx, edx; pUnkOuter
0x180007d13  lea     rcx, CLSID_KnownFolderManager; rclsid
0x180007d1a  call    cs:__imp_CoCreateInstance
0x180007d20  mov     ebx, eax
0x180007d22  test    eax, eax
0x180007d24  jns     short loc_180007D5D
0x180007d26  mov     rcx, [rbp+5Fh]; this
0x180007d2a  mov     r9d, eax; char *
0x180007d2d  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007d34  mov     edx, 609h; void *
0x180007d39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d3e  nop
0x180007d3f  lea     rcx, [rbp+57h+var_A0]
0x180007d43  call    ??1?$com_ptr_t@UIOfflineFilesCache@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>::~com_ptr_t<IOfflineFilesCache,wil::err_returncode_policy>(void)
0x180007d48  nop
0x180007d49  test    r14b, r14b
0x180007d4c  jz      loc_1800081CA
0x180007d52  call    cs:__imp_CoUninitialize
0x180007d58  jmp     loc_1800081CA
0x180007d5d  mov     [rbp+57h+pv], r13
0x180007d61  mov     [rbp+57h+var_98], r13d
0x180007d65  mov     rcx, [rbp+57h+var_A0]
0x180007d69  mov     rax, [rcx]
0x180007d6c  lea     rdx, [rbp+57h+pv]
0x180007d70  mov     qword ptr [rbp+57h+rfid.Data1], rdx
0x180007d74  mov     qword ptr [rbp+57h+rfid.Data4], r13
0x180007d78  mov     [rbp+57h+var_40], r12b
0x180007d7c  lea     r8, [rbp+57h+var_98]
0x180007d80  lea     rdx, [rbp+57h+rfid.Data4]
0x180007d84  mov     rax, [rax+28h]
0x180007d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8d  mov     ebx, eax
0x180007d8f  lea     rcx, [rbp+57h+rfid]
0x180007d93  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180007d98  test    ebx, ebx
0x180007d9a  jns     short loc_180007DCE
0x180007d9c  mov     rcx, [rbp+5Fh]; this
0x180007da0  mov     r9d, ebx; char *
0x180007da3  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007daa  mov     edx, 60Eh; void *
0x180007daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007db4  nop
0x180007db5  mov     rcx, [rbp+57h+pv]; pv
0x180007db9  mov     [rbp+57h+pv], r13
0x180007dbd  test    rcx, rcx
0x180007dc0  jz      short loc_180007DC9
0x180007dc2  call    cs:__imp_CoTaskMemFree
0x180007dc8  nop
0x180007dc9  jmp     loc_180007D3F
0x180007dce  mov     r12d, r13d
0x180007dd1  mov     [rbp+57h+var_D0], r13d
0x180007dd5  cmp     [rdi], r13w
0x180007dd9  jz      loc_18000816B
0x180007ddf  mov     r14, [rbp+57h+ppszPath]
0x180007de3  cmp     [rsi], r13w
0x180007de7  jz      loc_18000812B
0x180007ded  mov     [rbp+57h+var_C8], r13
0x180007df1  mov     rcx, rdi; unsigned __int16 *
0x180007df4  call    ?StringIsPrefixed@@YAHPEBG0@Z; StringIsPrefixed(ushort const *,ushort const *)
0x180007df9  test    eax, eax
0x180007dfb  jz      short loc_180007E02
0x180007dfd  mov     r13, rdi
0x180007e00  jmp     short loc_180007E4A
0x180007e02  mov     [rbp+57h+var_68], r13
0x180007e06  mov     rbx, [rbp+57h+var_C8]
0x180007e0a  test    rbx, rbx
0x180007e0d  jz      short loc_180007E29
0x180007e0f  lea     rcx, [rbp+57h+var_70]; this
0x180007e13  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007e18  mov     rcx, rbx
0x180007e1b  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180007e20  lea     rcx, [rbp+57h+var_70]; this
0x180007e24  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007e29  mov     [rbp+57h+var_C8], r13
0x180007e2d  lea     r8, [rbp+57h+var_68]
0x180007e31  lea     rdx, [rbp+57h+var_C8]
0x180007e35  mov     rcx, rdi
0x180007e38  call    cs:__imp_GetLongProfilePathName
0x180007e3e  test    eax, eax
0x180007e40  jnz     loc_1800080CF
0x180007e46  mov     r13, [rbp+57h+var_C8]
0x180007e4a  mov     [rbp+57h+var_C0], 0
0x180007e52  mov     rcx, rsi; unsigned __int16 *
0x180007e55  call    ?StringIsPrefixed@@YAHPEBG0@Z; StringIsPrefixed(ushort const *,ushort const *)
0x180007e5a  test    eax, eax
0x180007e5c  jz      short loc_180007E63
0x180007e5e  mov     r12, rsi
0x180007e61  jmp     short loc_180007EB3
0x180007e63  mov     [rbp+57h+var_58], 0
0x180007e6b  mov     rbx, [rbp+57h+var_C0]
0x180007e6f  test    rbx, rbx
0x180007e72  jz      short loc_180007E8E
0x180007e74  lea     rcx, [rbp+57h+var_60]; this
0x180007e78  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007e7d  mov     rcx, rbx
0x180007e80  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180007e85  lea     rcx, [rbp+57h+var_60]; this
0x180007e89  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007e8e  mov     [rbp+57h+var_C0], 0
0x180007e96  lea     r8, [rbp+57h+var_58]
0x180007e9a  lea     rdx, [rbp+57h+var_C0]
0x180007e9e  mov     rcx, rsi
0x180007ea1  call    cs:__imp_GetLongProfilePathName
0x180007ea7  test    eax, eax
0x180007ea9  jnz     loc_18000809E
0x180007eaf  mov     r12, [rbp+57h+var_C0]
0x180007eb3  mov     rcx, r12; lpFileName
0x180007eb6  call    cs:__imp_GetFileAttributesW
0x180007ebc  cmp     eax, 0FFFFFFFFh
0x180007ebf  jz      short loc_180007EDD
0x180007ec1  lea     rcx, [rbp+57h+var_C0]
0x180007ec5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007eca  nop
0x180007ecb  lea     rcx, [rbp+57h+var_C8]
0x180007ecf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180007ed4  mov     r12d, [rbp+57h+var_D0]
0x180007ed8  jmp     loc_1800080CA
0x180007edd  mov     rcx, r13; lpFileName
0x180007ee0  call    cs:__imp_GetFileAttributesW
0x180007ee6  mov     ebx, eax
0x180007ee8  cmp     eax, 0FFFFFFFFh
0x180007eeb  jz      short loc_180007EC1
0x180007eed  and     eax, 410h
0x180007ef2  cmp     eax, 10h
0x180007ef5  jnz     short loc_180007EC1
0x180007ef7  test    r15d, 44000h
0x180007efe  setz    cl
0x180007f01  bt      ebx, 0Eh
0x180007f05  setnb   al
0x180007f08  or      cl, al
0x180007f0a  jz      short loc_180007EC1
0x180007f0c  and     r15d, 20000h
0x180007f13  jz      short loc_180007F1B
0x180007f15  bt      ebx, 0Eh
0x180007f19  jb      short loc_180007EC1
0x180007f1b  xorps   xmm0, xmm0
0x180007f1e  movups  xmmword ptr [rbp+57h+rfid.Data1], xmm0
0x180007f22  lea     rax, [rbp+57h+rfid]
0x180007f26  mov     [rsp+110h+var_E8], rax; struct _GUID *
0x180007f2b  mov     [rsp+110h+ppv], rsi; int
0x180007f30  mov     r9d, [rbp+57h+var_98]; unsigned int
0x180007f34  mov     r8, [rbp+57h+pv]; struct _GUID *
0x180007f38  mov     rdx, [rbp+57h+var_A0]; struct IKnownFolderManager *
0x180007f3c  mov     rcx, r14; this
0x180007f3f  call    ?_IsNonRedirectedKnownFolder@CUserProfileRoamingProvider@@AEAA_NPEAUIKnownFolderManager@@PEAU_GUID@@IPEBG1@Z; CUserProfileRoamingProvider::_IsNonRedirectedKnownFolder(IKnownFolderManager *,_GUID *,uint,ushort const *,_GUID *)
0x180007f44  test    al, al
0x180007f46  jz      loc_180007EC1
0x180007f4c  test    r15d, r15d
0x180007f4f  jz      short loc_180007FB8
0x180007f51  test    bl, 4
0x180007f54  jnz     short loc_180007FB8
0x180007f56  mov     ebx, [rbp+57h+var_B8]
0x180007f59  bts     ebx, 15h
0x180007f5d  mov     [rbp+57h+var_B8], ebx
0x180007f60  xor     r13d, r13d
0x180007f63  mov     [rsp+110h+var_E8], r13
0x180007f68  mov     [rsp+110h+ppv], r13
0x180007f6d  xor     r9d, r9d
0x180007f70  mov     r8d, ebx
0x180007f73  mov     rdx, rsi
0x180007f76  mov     rcx, rdi
0x180007f79  call    cs:__imp_CopyProfileDirectoryEx2
0x180007f7f  test    eax, eax
0x180007f81  setz    al
0x180007f84  mov     rcx, [rbp+5Fh]; this
0x180007f88  mov     [rsp+110h+var_E0], rsi
0x180007f8d  mov     [rsp+110h+var_E8], rdi; char *
0x180007f92  lea     rdx, aFailedToCopyWs; "Failed to copy <%ws> to <%ws>."
0x180007f99  mov     [rsp+110h+ppv], rdx; bool
0x180007f9e  movzx   r9d, al; char *
0x180007fa2  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007fa9  mov     edx, 688h; void *
0x180007fae  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180007fb3  jmp     loc_18000808F
0x180007fb8  mov     ebx, [rbp+57h+var_B8]
0x180007fbb  mov     r8d, ebx
0x180007fbe  shr     r8d, 0Fh
0x180007fc2  and     r8d, 1; int
0x180007fc6  mov     rdx, r12; unsigned __int16 *
0x180007fc9  mov     rcx, r13; unsigned __int16 *
0x180007fcc  call    ?CopyRupDirectory@@YAJPEBG0H@Z; CopyRupDirectory(ushort const *,ushort const *,int)
0x180007fd1  mov     rcx, [rbp+5Fh]; this
0x180007fd5  xor     r13d, r13d
0x180007fd8  test    eax, eax
0x180007fda  jns     short loc_180008000
0x180007fdc  mov     r9d, eax; char *
0x180007fdf  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180007fe6  mov     edx, 691h; void *
0x180007feb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007ff0  mov     r12d, [rbp+57h+var_D0]
0x180007ff4  inc     r12d
0x180007ff7  mov     [rbp+57h+var_D0], r12d
0x180007ffb  jmp     loc_180008093
0x180008000  mov     [rsp+110h+var_E8], r13
0x180008005  mov     [rsp+110h+ppv], r13
0x18000800a  xor     r9d, r9d
0x18000800d  mov     r8d, ebx
0x180008010  mov     rdx, rsi
0x180008013  mov     rcx, rdi
0x180008016  call    cs:__imp_CopyProfileDirectoryEx2
0x18000801c  test    eax, eax
0x18000801e  setz    al
0x180008021  mov     rcx, [rbp+5Fh]; this
0x180008025  mov     [rsp+110h+var_E0], rsi
0x18000802a  mov     [rsp+110h+var_E8], rdi; char *
0x18000802f  lea     rdx, aFailedToCopyWs; "Failed to copy <%ws> to <%ws>."
0x180008036  mov     [rsp+110h+ppv], rdx; int
0x18000803b  movzx   r9d, al; char *
0x18000803f  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180008046  mov     edx, 697h; void *
0x18000804b  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180008050  mov     [rbp+57h+ppszPath], r13
0x180008054  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x180008058  xor     r8d, r8d; hToken
0x18000805b  mov     edx, 8800h; dwFlags
  ... truncated ...
```
