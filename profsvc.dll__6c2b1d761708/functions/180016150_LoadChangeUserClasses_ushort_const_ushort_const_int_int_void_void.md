# LoadChangeUserClasses(ushort const *,ushort const *,int,int,void * *,void *)

- ea: `0x180016150`
- end: `0x180016cf3`
- name: `?LoadChangeUserClasses@@YAJPEBG0HHPEAPEAXPEAX@Z`
- size: `2979`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, void **, HANDLE hToken)`
- caller_count: `5`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f844`
- `0x180030050`
- `0x180030744`
- `0x180038798`
- `0x18003b26c`

## callees

- `0x180005dd0`
- `0x180006498`
- `0x18000721c`
- `0x180007b58`
- `0x18000d030`
- `0x18000e1a0`
- `0x180010c70`
- `0x1800130d0`
- `0x180016150`
- `0x180016ea0`
- `0x180017370`
- `0x180017520`
- `0x1800178bc`
- `0x180018030`
- `0x1800181c8`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x180035860`
- `0x1800358a0`
- `0x18003657c`
- `0x180038c38`
- `0x18003bc70`
- `0x180040bcc`
- `0x180043800`
- `0x18004a8b8`
- `0x18004f38c`
- `0x18004f564`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016253`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001635a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016253`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001635a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001623f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001629f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016346`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001623f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001629f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016bb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800161d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001630d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800165a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800161d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001630d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800165a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016278`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001632f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001637f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016489`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016809`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001682b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016bab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016278`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001632f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001637f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016489`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800164ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016809`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001682b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016bab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016650`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016650`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800169ae`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800169ce`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800169ae`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800169ce`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016a01`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016a01`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180016518`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180016518`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800163cd`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800163cd`

## string_xrefs

- `0x180016223`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001645a`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800166db`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016705`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016735`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001677f`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800167d9`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001686a`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001688a`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800168d5`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001691f`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016969`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800169e8`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016a1c`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016a67`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016ae1`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016b06`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016b2f`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016b73`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016bcd`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016be6`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016bff`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016c40`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016c78`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016c91`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016caa`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016cc3`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180016cdc`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001644b`: `Local Hive Directory Path: %ws`
- `0x1800167c7`: `Insufficient privileges on usrclass.dat`

## pseudocode

```c
__int64 __fastcall LoadChangeUserClasses(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        void **a5,
        HANDLE hToken)
{
  unsigned int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  void *v15; // rdi
  HANDLE v16; // rax
  void *v18; // rbx
  HANDLE v19; // rax
  int BasicProfileFolderPathAlloc; // ebx
  int v21; // eax
  HKEY v22; // rcx
  HKEY v23; // rcx
  int v24; // eax
  const unsigned __int16 *v25; // rsi
  HKEY v26; // rcx
  BOOL FileAttributes; // r13d
  HKEY v28; // r14
  unsigned int v29; // eax
  int v30; // eax
  int v31; // eax
  unsigned int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rcx
  int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  const char *v48; // r9
  __int64 v49; // rcx
  int v50; // eax
  __int64 v51; // rcx
  int v52; // eax
  int v53; // eax
  __int64 v54; // rdx
  DWORD LastError; // ebx
  int v56; // eax
  int v57; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultd; // [rsp+20h] [rbp-E0h]
  int phkResulte; // [rsp+20h] [rbp-E0h]
  int phkResultf; // [rsp+20h] [rbp-E0h]
  int phkResultg; // [rsp+20h] [rbp-E0h]
  int phkResulth; // [rsp+20h] [rbp-E0h]
  int phkResulti; // [rsp+20h] [rbp-E0h]
  int phkResultj; // [rsp+20h] [rbp-E0h]
  int phkResultk; // [rsp+20h] [rbp-E0h]
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  HKEY v71; // [rsp+50h] [rbp-B0h] BYREF
  bool v72; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  __int64 v75; // [rsp+70h] [rbp-90h]
  __int64 v76; // [rsp+78h] [rbp-88h]
  void **v77; // [rsp+80h] [rbp-80h] BYREF
  char *v78; // [rsp+88h] [rbp-78h] BYREF
  __int64 v79; // [rsp+90h] [rbp-70h]
  __int64 v80; // [rsp+98h] [rbp-68h]
  LPCWSTR lpFileName[3]; // [rsp+A0h] [rbp-60h] BYREF
  HKEY p_lpMem; // [rsp+B8h] [rbp-48h] BYREF
  void ***v83; // [rsp+C0h] [rbp-40h]
  char v84; // [rsp+C8h] [rbp-38h]
  _BYTE v85[16]; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v86; // [rsp+E0h] [rbp-20h]
  char v87; // [rsp+E8h] [rbp-18h]
  _BYTE v88[24]; // [rsp+F0h] [rbp-10h] BYREF
  int v89; // [rsp+108h] [rbp+8h]
  _OWORD FileInformation[2]; // [rsp+120h] [rbp+20h] BYREF
  int v91; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v77 = a5;
  ProfileTelemetry::WatchCurrentThread(v85, "LoadUserClasses", "%ws", a1);
  hKey = 0;
  v10 = RegOpenKeyExW(HKEY_USERS, a1, 0, 0x20019u, &hKey);
  if ( v10 )
  {
    BasicProfileFolderPathAlloc = wil::details::in1diag3::Return_Win32(
                                    retaddr,
                                    (void *)0x17D,
                                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
                                    (const char *)v10,
                                    phkResult);
    v23 = hKey;
    if ( !hKey )
      goto LABEL_31;
    goto LABEL_30;
  }
  lpMem = 0;
  v75 = 0;
  v76 = 0;
  v11 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          &lpMem,
          L"%s_Classes",
          a1);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)v11,
      phkResult);
    v13 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      lpMem = 0;
    }
    v75 = 0;
    v76 = 0;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v89 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v88);
    if ( v87 )
    {
      v15 = v86;
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v15);
    }
    return v12;
  }
  v71 = 0;
  if ( !RegOpenKeyExW(HKEY_USERS, (LPCWSTR)lpMem, 0, 0x20019u, &v71) )
  {
    if ( a4 )
    {
      v53 = ValidateUserClassesHive(hKey, (const unsigned __int16 *)lpMem, v77, a4, (int *)&p_lpMem);
      BasicProfileFolderPathAlloc = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
          (const char *)(unsigned int)v53,
          phkResultk);
        v22 = v71;
        if ( !v71 )
        {
LABEL_29:
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
          v23 = hKey;
          if ( !hKey )
          {
LABEL_31:
            wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v85);
            return (unsigned int)BasicProfileFolderPathAlloc;
          }
LABEL_30:
          RegCloseKey(v23);
          goto LABEL_31;
        }
LABEL_28:
        RegCloseKey(v22);
        goto LABEL_29;
      }
    }
    goto LABEL_14;
  }
  v78 = 0;
  v79 = 0;
  v80 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v78);
  v79 = -1;
  v80 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, a1, &v78);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v54 = 402;
LABEL_94:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v54,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      phkResulta);
    goto LABEL_27;
  }
  BasicProfileFolderPathAlloc = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                                  &v78,
                                  L"\\Microsoft\\Windows\\",
                                  19);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v54 = 405;
    goto LABEL_94;
  }
  p_lpMem = 0;
  LOBYTE(v83) = 0;
  if ( hToken )
  {
    v21 = CAutoImpersonate::ImpersonateUser((CAutoImpersonate *)&p_lpMem, hToken);
    BasicProfileFolderPathAlloc = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
        (const char *)(unsigned int)v21,
        phkResulta);
      CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&p_lpMem);
      goto LABEL_27;
    }
  }
  BasicProfileFolderPathAlloc = CreateNestedDirectory((const unsigned __int16 *)v78, 0);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      (int)"Local Hive Directory Path: %ws",
      v78);
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&p_lpMem);
    goto LABEL_27;
  }
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&p_lpMem);
  memset(lpFileName, 0, sizeof(lpFileName));
  v24 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          lpFileName,
          L"%s\\UsrClass.dat",
          v78);
  BasicProfileFolderPathAlloc = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)v24,
      phkResulta);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
    goto LABEL_27;
  }
  memset(FileInformation, 0, sizeof(FileInformation));
  v91 = 0;
  v25 = lpFileName[0];
  FileAttributes = GetFileAttributesExW(lpFileName[0], GetFileExInfoStandard, FileInformation);
  if ( !FileAttributes || !hToken || (unsigned int)CheckFullAccessOnFile(hToken, v25) )
  {
    BasicProfileFolderPathAlloc = MountRegHive(v26, (const unsigned __int16 *)lpMem, v25, hKey, hToken, v77);
    if ( BasicProfileFolderPathAlloc >= 0 )
    {
      p_lpMem = (HKEY)&lpMem;
      v83 = &v77;
      v84 = 1;
      v28 = v71;
      if ( v71 )
      {
        LastError = GetLastError();
        RegCloseKey(v28);
        SetLastError(LastError);
      }
      v71 = 0;
      v29 = RegOpenKeyExW(HKEY_USERS, (LPCWSTR)lpMem, 0, 0x60019u, &v71);
      if ( v29 )
      {
        BasicProfileFolderPathAlloc = wil::details::in1diag3::Return_Win32(
                                        retaddr,
                                        (void *)0x1C8,
                                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
                                        (const char *)v29,
                                        phkResultc);
        v39 = UnmountRegHive(v38, lpMem, 0, v77);
        if ( v39 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C0,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)(unsigned int)v39,
            phkResultf);
        goto LABEL_89;
      }
      v72 = 0;
      v30 = IsUserSecuritySetInKey(v71, a1, &v72);
      BasicProfileFolderPathAlloc = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CC,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
          (const char *)(unsigned int)v30,
          phkResultc);
        v35 = UnmountRegHive(v34, lpMem, 0, v77);
        if ( v35 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C0,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)(unsigned int)v35,
            phkResulte);
        goto LABEL_89;
      }
      if ( FileAttributes && !a3 && v72 )
      {
        v31 = TestSetDefaultClassHiveAppContainerSecurity(a1, v71);
        BasicProfileFolderPathAlloc = v31;
        if ( v31 >= 0 )
        {
LABEL_43:
          p_lpMem = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &p_lpMem,
            0);
          v32 = RegCreateKeyExW(v71, L"Local Settings", 0, 0, 0, 0x2001Fu, 0, &p_lpMem, 0);
          if ( v32 )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x1F6,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
              (const char *)v32,
              phkResultd);
          if ( p_lpMem )
            RegCloseKey(p_lpMem);
          v33 = MapUserClassesIntoUserHive(hKey, a1);
          BasicProfileFolderPathAlloc = v33;
          if ( v33 >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v78);
LABEL_14:
            if ( v71 )
              RegCloseKey(v71);
            v18 = lpMem;
            if ( lpMem )
            {
              v19 = GetProcessHeap();
              HeapFree(v19, 0, v18);
              lpMem = 0;
            }
            v75 = 0;
            v76 = 0;
            if ( hKey )
              RegCloseKey(hKey);
            wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v85);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1FA,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)(unsigned int)v33,
            phkResultd);
          v52 = UnmountRegHive(v51, lpMem, 0, v77);
          if ( v52 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1C0,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
              (const char *)(unsigned int)v52,
              phkResultj);
          goto LABEL_89;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E8,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
          (const char *)(unsigned int)v31,
          phkResultc);
        v41 = UnmountRegHive(v40, lpMem, 0, v77);
        if ( v41 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C0,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)(unsigned int)v41,
            phkResultg);
      }
      else
      {
        if ( a2 )
        {
          v57 = SetDefaultChangeOwnerHiveSecurity(a2, a1, v71);
          BasicProfileFolderPathAlloc = v57;
          if ( v57 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DB,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
              (const char *)(unsigned int)v57,
              phkResultc);
            v45 = UnmountRegHive(v44, lpMem, 0, v77);
            if ( v45 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1C0,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
                (const char *)(unsigned int)v45,
                phkResulti);
            goto LABEL_89;
          }
        }
        else
        {
          v56 = SetDefaultUserClassHiveSecurity_(
                  a1,
                  v71,
                  (int (*)(HKEY, void *, void *, int, int))_ApplySecurityToRegistryTree);
          BasicProfileFolderPathAlloc = v56;
          if ( v56 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D6,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
              (const char *)(unsigned int)v56,
              phkResultc);
            v43 = UnmountRegHive(v42, lpMem, 0, v77);
            if ( v43 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1C0,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
                (const char *)(unsigned int)v43,
                phkResulth);
            goto LABEL_89;
          }
        }
        v46 = RegFlushKey(v71);
        if ( v46 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1E0,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)v46,
            phkResultc);
        v47 = RegFlushKey(hKey);
        if ( v47 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1E1,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)v47,
            phkResultc);
        if ( SetFileAttributesW(v25, 2u) )
          goto LABEL_43;
        BasicProfileFolderPathAlloc = wil::details::in1diag3::Return_GetLastError(
                                        retaddr,
                                        (void *)0x1E4,
                                        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
                                        v48);
        v50 = UnmountRegHive(v49, lpMem, 0, v77);
        if ( v50 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C0,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
            (const char *)(unsigned int)v50,
            phkResultc);
      }
LABEL_89:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
      goto LABEL_27;
    }
    if ( BasicProfileFolderPathAlloc != -2147023446 && BasicProfileFolderPathAlloc != -2147023887 )
    {
      v37 = LogProcessesWithOpenFileHandles(v25, 1);
      if ( v37 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B8,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
          (const char *)(unsigned int)v37,
          phkResultb);
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      (int)"Hive Key Name: %ws",
      (const char *)lpMem);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
LABEL_27:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v78);
    v22 = v71;
    if ( !v71 )
      goto LABEL_29;
    goto LABEL_28;
  }
  v36 = LogProcessesWithOpenFileHandles(v25, 1);
  if ( v36 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)v36,
      phkResulta);
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x1B0,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
    (const char *)0x80004005LL,
    (int)"Insufficient privileges on usrclass.dat",
    samDesired);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v78);
  if ( v71 )
    RegCloseKey(v71);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
  if ( hKey )
    RegCloseKey(hKey);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v85);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180016150  mov     [rsp-8+arg_10], rbx
0x180016155  push    rbp
0x180016156  push    rsi
0x180016157  push    rdi
0x180016158  push    r12
0x18001615a  push    r13
0x18001615c  push    r14
0x18001615e  push    r15
0x180016160  lea     rbp, [rsp-50h]
0x180016165  sub     rsp, 150h
0x18001616c  mov     rax, cs:__security_cookie
0x180016173  xor     rax, rsp
0x180016176  mov     [rbp+80h+var_38], rax
0x18001617a  mov     esi, r9d
0x18001617d  mov     r15d, r8d
0x180016180  mov     r12, rdx
0x180016183  mov     rdi, rcx
0x180016186  mov     rax, [rbp+80h+arg_20]
0x18001618d  mov     [rbp+80h+var_100], rax
0x180016191  mov     r14, [rbp+80h+hToken]
0x180016198  mov     r9, rcx
0x18001619b  lea     r8, aWs; "%ws"
0x1800161a2  lea     rdx, aLoaduserclasse; "LoadUserClasses"
0x1800161a9  lea     rcx, [rbp+80h+var_B0]
0x1800161ad  call    ?WatchCurrentThread@ProfileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; ProfileTelemetry::WatchCurrentThread(char const *,char const *,...)
0x1800161b2  nop
0x1800161b3  xor     r13d, r13d
0x1800161b6  mov     [rsp+180h+hKey], r13
0x1800161bb  lea     rax, [rsp+180h+hKey]
0x1800161c0  mov     [rsp+180h+phkResult], rax; unsigned int
0x1800161c5  mov     r9d, 20019h; samDesired
0x1800161cb  xor     r8d, r8d; ulOptions
0x1800161ce  mov     rdx, rdi; lpSubKey
0x1800161d1  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800161d8  call    cs:__imp_RegOpenKeyExW
0x1800161df  nop     dword ptr [rax+rax+00h]
0x1800161e4  test    eax, eax
0x1800161e6  jnz     loc_1800166FB
0x1800161ec  mov     [rsp+180h+lpMem], r13
0x1800161f1  mov     [rsp+180h+var_110], r13
0x1800161f6  mov     [rsp+180h+var_108], r13
0x1800161fb  mov     r8, rdi
0x1800161fe  lea     rdx, aSClasses; "%s_Classes"
0x180016205  lea     rcx, [rsp+180h+lpMem]
0x18001620a  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001620f  mov     ebx, eax
0x180016211  test    eax, eax
0x180016213  jns     loc_1800162E9
0x180016219  mov     rcx, [rbp+88h]; this
0x180016220  mov     r9d, eax; char *
0x180016223  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001622a  mov     edx, 180h; void *
0x18001622f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016234  nop
0x180016235  mov     rdi, [rsp+180h+lpMem]
0x18001623a  test    rdi, rdi
0x18001623d  jz      short loc_180016264
0x18001623f  call    cs:__imp_GetProcessHeap
0x180016246  nop     dword ptr [rax+rax+00h]
0x18001624b  mov     rcx, rax; hHeap
0x18001624e  mov     r8, rdi; lpMem
0x180016251  xor     edx, edx; dwFlags
0x180016253  call    cs:__imp_HeapFree
0x18001625a  nop     dword ptr [rax+rax+00h]
0x18001625f  mov     [rsp+180h+lpMem], r13
0x180016264  mov     [rsp+180h+var_110], r13
0x180016269  mov     [rsp+180h+var_108], r13
0x18001626e  mov     rcx, [rsp+180h+hKey]; hKey
0x180016273  test    rcx, rcx
0x180016276  jz      short loc_180016285
0x180016278  call    cs:__imp_RegCloseKey
0x18001627f  nop     dword ptr [rax+rax+00h]
0x180016284  nop
0x180016285  cmp     [rbp+80h+var_78], 0
0x180016289  jz      short loc_180016295
0x18001628b  lea     rcx, [rbp+80h+var_90]; this
0x18001628f  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180016294  nop
0x180016295  cmp     [rbp+80h+var_98], 0
0x180016299  jz      short loc_1800162BF
0x18001629b  mov     rdi, [rbp+80h+var_A0]
0x18001629f  call    cs:__imp_GetProcessHeap
0x1800162a6  nop     dword ptr [rax+rax+00h]
0x1800162ab  mov     r8, rdi; lpMem
0x1800162ae  xor     edx, edx; dwFlags
0x1800162b0  mov     rcx, rax; hHeap
0x1800162b3  call    cs:__imp_HeapFree
0x1800162ba  nop     dword ptr [rax+rax+00h]
0x1800162bf  mov     eax, ebx
0x1800162c1  mov     rcx, [rbp+80h+var_38]
0x1800162c5  xor     rcx, rsp; StackCookie
0x1800162c8  call    __security_check_cookie
0x1800162cd  mov     rbx, [rsp+180h+arg_10]
0x1800162d5  add     rsp, 150h
0x1800162dc  pop     r15
0x1800162de  pop     r14
0x1800162e0  pop     r13
0x1800162e2  pop     r12
0x1800162e4  pop     rdi
0x1800162e5  pop     rsi
0x1800162e6  pop     rbp
0x1800162e7  retn
0x1800162e9  mov     [rsp+180h+var_130], r13
0x1800162ee  lea     rax, [rsp+180h+var_130]
0x1800162f3  mov     [rsp+180h+phkResult], rax; int
0x1800162f8  mov     r9d, 20019h; samDesired
0x1800162fe  xor     r8d, r8d; ulOptions
0x180016301  mov     rdx, [rsp+180h+lpMem]; lpSubKey
0x180016306  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001630d  call    cs:__imp_RegOpenKeyExW
0x180016314  nop     dword ptr [rax+rax+00h]
0x180016319  test    eax, eax
0x18001631b  jnz     short loc_18001639C
0x18001631d  test    esi, esi
0x18001631f  jnz     loc_180016AA7
0x180016325  mov     rcx, [rsp+180h+var_130]; hKey
0x18001632a  test    rcx, rcx
0x18001632d  jz      short loc_18001633C
0x18001632f  call    cs:__imp_RegCloseKey
0x180016336  nop     dword ptr [rax+rax+00h]
0x18001633b  nop
0x18001633c  mov     rbx, [rsp+180h+lpMem]
0x180016341  test    rbx, rbx
0x180016344  jz      short loc_18001636B
0x180016346  call    cs:__imp_GetProcessHeap
0x18001634d  nop     dword ptr [rax+rax+00h]
0x180016352  mov     rcx, rax; hHeap
0x180016355  mov     r8, rbx; lpMem
0x180016358  xor     edx, edx; dwFlags
0x18001635a  call    cs:__imp_HeapFree
0x180016361  nop     dword ptr [rax+rax+00h]
0x180016366  mov     [rsp+180h+lpMem], r13
0x18001636b  mov     [rsp+180h+var_110], r13
0x180016370  mov     [rsp+180h+var_108], r13
0x180016375  mov     rcx, [rsp+180h+hKey]; hKey
0x18001637a  test    rcx, rcx
0x18001637d  jz      short loc_18001638C
0x18001637f  call    cs:__imp_RegCloseKey
0x180016386  nop     dword ptr [rax+rax+00h]
0x18001638b  nop
0x18001638c  lea     rcx, [rbp+80h+var_B0]; this
0x180016390  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180016395  xor     eax, eax
0x180016397  jmp     loc_1800162C1
0x18001639c  mov     [rbp+80h+var_F8], r13
0x1800163a0  mov     [rbp+80h+var_F0], r13
0x1800163a4  mov     [rbp+80h+var_E8], r13
0x1800163a8  lea     rcx, [rbp+80h+var_F8]
0x1800163ac  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800163b1  mov     [rbp+80h+var_F0], 0FFFFFFFFFFFFFFFFh
0x1800163b9  mov     [rbp+80h+var_E8], 0FFFFFFFFFFFFFFFFh
0x1800163c1  lea     r8, [rbp+80h+var_F8]
0x1800163c5  mov     rdx, rdi
0x1800163c8  mov     ecx, 6
0x1800163cd  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x1800163d4  nop     dword ptr [rax+rax+00h]
0x1800163d9  mov     ebx, eax
0x1800163db  test    eax, eax
0x1800163dd  js      loc_180016AD5
0x1800163e3  mov     r8d, 13h
0x1800163e9  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\"
0x1800163f0  lea     rcx, [rbp+80h+var_F8]
0x1800163f4  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800163f9  mov     ebx, eax
0x1800163fb  test    eax, eax
0x1800163fd  js      loc_180016ADC
0x180016403  mov     [rbp+80h+var_C8], r13
0x180016407  mov     byte ptr [rbp+80h+var_C0], 0
0x18001640b  test    r14, r14
0x18001640e  jz      short loc_180016426
0x180016410  mov     rdx, r14; void *
0x180016413  lea     rcx, [rbp+80h+var_C8]; this
0x180016417  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x18001641c  mov     ebx, eax
0x18001641e  test    eax, eax
0x180016420  js      loc_180016AFC
0x180016426  xor     edx, edx; lpSecurityAttributes
0x180016428  mov     rcx, [rbp+80h+var_F8]; unsigned __int16 *
0x18001642c  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x180016431  mov     ebx, eax
0x180016433  test    eax, eax
0x180016435  jns     loc_1800164C8
0x18001643b  mov     rcx, [rbp+88h]; this
0x180016442  mov     rdx, [rbp+80h+var_F8]
0x180016446  mov     qword ptr [rsp+180h+samDesired], rdx; char *
0x18001644b  lea     rax, aLocalHiveDirec; "Local Hive Directory Path: %ws"
0x180016452  mov     [rsp+180h+phkResult], rax; int
0x180016457  mov     r9d, ebx; char *
0x18001645a  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x180016461  mov     edx, 19Fh; void *
0x180016466  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001646b  lea     rcx, [rbp+80h+var_C8]; this
0x18001646f  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x180016474  nop
0x180016475  lea     rcx, [rbp+80h+var_F8]
0x180016479  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001647e  nop
0x18001647f  mov     rcx, [rsp+180h+var_130]; hKey
0x180016484  test    rcx, rcx
0x180016487  jz      short loc_180016496
0x180016489  call    cs:__imp_RegCloseKey
0x180016490  nop     dword ptr [rax+rax+00h]
0x180016495  nop
0x180016496  lea     rcx, [rsp+180h+lpMem]
0x18001649b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800164a0  nop
0x1800164a1  mov     rcx, [rsp+180h+hKey]; hKey
0x1800164a6  test    rcx, rcx
0x1800164a9  jz      short loc_1800164B8
0x1800164ab  call    cs:__imp_RegCloseKey
0x1800164b2  nop     dword ptr [rax+rax+00h]
0x1800164b7  nop
0x1800164b8  lea     rcx, [rbp+80h+var_B0]; this
0x1800164bc  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800164c1  mov     eax, ebx
0x1800164c3  jmp     loc_1800162C1
0x1800164c8  lea     rcx, [rbp+80h+var_C8]; this
0x1800164cc  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800164d1  mov     [rbp+80h+lpFileName], r13
0x1800164d5  mov     [rbp+80h+var_D8], r13
0x1800164d9  mov     [rbp+80h+var_D0], r13
0x1800164dd  mov     r8, [rbp+80h+var_F8]
0x1800164e1  lea     rdx, aSUsrclassDat; "%s\\UsrClass.dat"
0x1800164e8  lea     rcx, [rbp+80h+lpFileName]
0x1800164ec  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800164f1  mov     ebx, eax
0x1800164f3  test    eax, eax
0x1800164f5  js      loc_180016B25
0x1800164fb  xorps   xmm0, xmm0
0x1800164fe  xor     eax, eax
0x180016500  movups  [rbp+80h+FileInformation], xmm0
0x180016504  movups  [rbp+80h+var_50], xmm0
0x180016508  mov     [rbp+80h+var_40], eax
0x18001650b  lea     r8, [rbp+80h+FileInformation]; lpFileInformation
0x18001650f  xor     edx, edx; fInfoLevelId
0x180016511  mov     rsi, [rbp+80h+lpFileName]
0x180016515  mov     rcx, rsi; lpFileName
0x180016518  call    cs:__imp_GetFileAttributesExW
0x18001651f  nop     dword ptr [rax+rax+00h]
0x180016524  mov     r13d, eax
0x180016527  test    eax, eax
0x180016529  jnz     loc_180016B4F
0x18001652f  mov     rax, [rbp+80h+var_100]
0x180016533  mov     qword ptr [rsp+180h+samDesired], rax; void **
0x180016538  mov     [rsp+180h+phkResult], r14; int
0x18001653d  mov     r9, [rsp+180h+hKey]; HKEY
0x180016542  mov     r8, rsi; unsigned __int16 *
0x180016545  mov     rdx, [rsp+180h+lpMem]; unsigned __int16 *
0x18001654a  call    ?MountRegHive@@YAJPEAUHKEY__@@PEBG10PEAXPEAPEAX@Z; MountRegHive(HKEY__ *,ushort const *,ushort const *,HKEY__ *,void *,void * *)
0x18001654f  mov     ebx, eax
0x180016551  test    eax, eax
0x180016553  js      loc_1800166AF
0x180016559  lea     rax, [rsp+180h+lpMem]
0x18001655e  mov     [rbp+80h+var_C8], rax
0x180016562  lea     rax, [rbp+80h+var_100]
0x180016566  mov     [rbp+80h+var_C0], rax
0x18001656a  mov     [rbp+80h+var_B8], 1
0x18001656e  mov     r14, [rsp+180h+var_130]
0x180016573  test    r14, r14
0x180016576  jnz     loc_180016B9A
0x18001657c  mov     [rsp+180h+var_130], 0
0x180016585  lea     rax, [rsp+180h+var_130]
0x18001658a  mov     [rsp+180h+phkResult], rax; int
0x18001658f  mov     r9d, 60019h; samDesired
0x180016595  xor     r8d, r8d; ulOptions
0x180016598  mov     rdx, [rsp+180h+lpMem]; lpSubKey
0x18001659d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800165a4  call    cs:__imp_RegOpenKeyExW
0x1800165ab  nop     dword ptr [rax+rax+00h]
0x1800165b0  test    eax, eax
0x1800165b2  jnz     loc_180016880
0x1800165b8  mov     [rsp+180h+var_128], al
0x1800165bc  lea     r8, [rsp+180h+var_128]; bool *
0x1800165c1  mov     rdx, rdi; unsigned __int16 *
0x1800165c4  mov     rcx, [rsp+180h+var_130]; HKEY
0x1800165c9  call    ?IsUserSecuritySetInKey@@YAJPEAUHKEY__@@PEBGPEA_N@Z; IsUserSecuritySetInKey(HKEY__ *,ushort const *,bool *)
0x1800165ce  mov     ebx, eax
0x1800165d0  test    eax, eax
0x1800165d2  js      loc_18001672B
0x1800165d8  test    r13d, r13d
0x1800165db  jz      loc_180016C15
0x1800165e1  test    r15d, r15d
0x1800165e4  jnz     loc_180016C15
0x1800165ea  cmp     [rsp+180h+var_128], r15b
0x1800165ef  jz      loc_180016C15
0x1800165f5  mov     rdx, [rsp+180h+var_130]; hKey
0x1800165fa  mov     rcx, rdi; unsigned __int16 *
0x1800165fd  call    ?TestSetDefaultClassHiveAppContainerSecurity@@YAJPEBGPEAUHKEY__@@@Z; TestSetDefaultClassHiveAppContainerSecurity(ushort const *,HKEY__ *)
0x180016602  mov     ebx, eax
0x180016604  test    eax, eax
0x180016606  js      loc_1800168CB
0x18001660c  xor     r13d, r13d
0x18001660f  mov     [rbp+80h+var_C8], r13
0x180016613  xor     edx, edx
0x180016615  lea     rcx, [rbp+80h+var_C8]
0x180016619  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001661e  mov     [rsp+180h+lpdwDisposition], r13; lpdwDisposition
0x180016623  lea     rax, [rbp+80h+var_C8]
0x180016627  mov     [rsp+180h+var_148], rax; phkResult
0x18001662c  mov     [rsp+180h+lpSecurityAttributes], r13; lpSecurityAttributes
  ... truncated ...
```
