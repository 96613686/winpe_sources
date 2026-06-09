# LoadChangeUserClasses(ushort const *,ushort const *,int,int,void * *,void *)

- ea: `0x180011200`
- end: `0x180011cea`
- name: `?LoadChangeUserClasses@@YAJPEBG0HHPEAPEAXPEAX@Z`
- size: `2794`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, void **, HANDLE hToken)`
- caller_count: `5`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002bf94`
- `0x18002ed00`
- `0x18003735c`
- `0x1800393e4`
- `0x180039d6c`

## callees

- `0x180006d44`
- `0x180008200`
- `0x1800085cc`
- `0x180008ef4`
- `0x1800099f8`
- `0x18000a320`
- `0x180010f30`
- `0x1800111a0`
- `0x180011200`
- `0x180011e80`
- `0x180012320`
- `0x180016680`
- `0x180022b60`
- `0x180024964`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002e648`
- `0x18002f8e0`
- `0x1800350cc`
- `0x180035fe0`
- `0x1800377f0`
- `0x18003a730`
- `0x18003f42c`
- `0x180041e18`
- `0x1800486bc`
- `0x18004c394`
- `0x18004c554`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800112f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800112f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800112e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800113c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800112e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800113c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ba3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011288`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011398`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800115e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011288`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011398`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800115e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011316`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011830`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001184c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011316`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011830`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001184c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011bae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011683`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011683`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800119c9`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800119e3`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800119c9`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800119e3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180011a10`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180011a10`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180011562`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180011562`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180011429`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180011429`

## string_xrefs

- `0x1800112cd`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800114b0`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011702`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001172c`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001175c`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800117a6`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011800`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011885`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800118a5`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800118f0`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x18001193a`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011984`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800119f7`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011a25`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011a70`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011aea`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011b0f`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011b38`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011b7c`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011bc4`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011bdd`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011bf6`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011c37`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011c6f`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011c88`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011ca1`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011cba`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x180011cd3`: `onecore\ds\security\gina\profile\profsvc\usrclass.cpp`
- `0x1800114a1`: `Local Hive Directory Path: %ws`
- `0x1800117ee`: `Insufficient privileges on usrclass.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  char *v78[3]; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+A0h] [rbp-60h] BYREF
  HKEY p_lpMem; // [rsp+B8h] [rbp-48h] BYREF
  void ***v81; // [rsp+C0h] [rbp-40h]
  char v82; // [rsp+C8h] [rbp-38h]
  _BYTE v83[16]; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v84; // [rsp+E0h] [rbp-20h]
  char v85; // [rsp+E8h] [rbp-18h]
  _BYTE v86[24]; // [rsp+F0h] [rbp-10h] BYREF
  int v87; // [rsp+108h] [rbp+8h]
  _OWORD FileInformation[2]; // [rsp+120h] [rbp+20h] BYREF
  int v89; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v77 = a5;
  ProfileTelemetry::WatchCurrentThread(v83, "LoadUserClasses", "%ws", a1);
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
    if ( v87 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v86);
    if ( v85 )
    {
      v15 = v84;
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
            wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v83);
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
  v78[0] = 0;
  v78[1] = (char *)-1LL;
  v78[2] = (char *)-1LL;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, a1, v78);
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
                                  v78,
                                  L"\\Microsoft\\Windows\\",
                                  19);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v54 = 405;
    goto LABEL_94;
  }
  p_lpMem = 0;
  LOBYTE(v81) = 0;
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
  BasicProfileFolderPathAlloc = CreateNestedDirectory((const unsigned __int16 *)v78[0], 0);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\usrclass.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      (int)"Local Hive Directory Path: %ws",
      v78[0]);
    CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&p_lpMem);
    goto LABEL_27;
  }
  CAutoImpersonate::ResetImpersonation((CAutoImpersonate *)&p_lpMem);
  memset(lpFileName, 0, sizeof(lpFileName));
  v24 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
          lpFileName,
          L"%s\\UsrClass.dat",
          v78[0]);
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
  v89 = 0;
  v25 = lpFileName[0];
  FileAttributes = GetFileAttributesExW(lpFileName[0], GetFileExInfoStandard, FileInformation);
  if ( !FileAttributes || !hToken || (unsigned int)CheckFullAccessOnFile(hToken, v25) )
  {
    BasicProfileFolderPathAlloc = MountRegHive(v26, (const unsigned __int16 *)lpMem, v25, hKey, hToken, v77);
    if ( BasicProfileFolderPathAlloc >= 0 )
    {
      p_lpMem = (HKEY)&lpMem;
      v81 = &v77;
      v82 = 1;
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
            Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v78);
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
            wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v83);
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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v78);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v78);
  if ( v71 )
    RegCloseKey(v71);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
  if ( hKey )
    RegCloseKey(hKey);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v83);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180011200  mov     [rsp-8+arg_10], rbx
0x180011205  push    rbp
0x180011206  push    rsi
0x180011207  push    rdi
0x180011208  push    r12
0x18001120a  push    r13
0x18001120c  push    r14
0x18001120e  push    r15
0x180011210  lea     rbp, [rsp-50h]
0x180011215  sub     rsp, 150h
0x18001121c  mov     rax, cs:__security_cookie
0x180011223  xor     rax, rsp
0x180011226  mov     [rbp+80h+var_38], rax
0x18001122a  mov     esi, r9d
0x18001122d  mov     r15d, r8d
0x180011230  mov     r12, rdx
0x180011233  mov     rdi, rcx
0x180011236  mov     rax, [rbp+80h+arg_20]
0x18001123d  mov     [rbp+80h+var_100], rax
0x180011241  mov     r14, [rbp+80h+hToken]
0x180011248  mov     r9, rcx
0x18001124b  lea     r8, aWs; "%ws"
0x180011252  lea     rdx, aLoaduserclasse; "LoadUserClasses"
0x180011259  lea     rcx, [rbp+80h+var_B0]
0x18001125d  call    ?WatchCurrentThread@ProfileTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; ProfileTelemetry::WatchCurrentThread(char const *,char const *,...)
0x180011262  nop
0x180011263  xor     r13d, r13d
0x180011266  mov     [rsp+180h+hKey], r13
0x18001126b  lea     rax, [rsp+180h+hKey]
0x180011270  mov     [rsp+180h+phkResult], rax; unsigned int
0x180011275  mov     r9d, 20019h; samDesired
0x18001127b  xor     r8d, r8d; ulOptions
0x18001127e  mov     rdx, rdi; lpSubKey
0x180011281  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180011288  call    cs:__imp_RegOpenKeyExW
0x18001128e  test    eax, eax
0x180011290  jnz     loc_180011722
0x180011296  mov     [rsp+180h+lpMem], r13
0x18001129b  mov     [rsp+180h+var_110], r13
0x1800112a0  mov     [rsp+180h+var_108], r13
0x1800112a5  mov     r8, rdi
0x1800112a8  lea     rdx, aSClasses; "%s_Classes"
0x1800112af  lea     rcx, [rsp+180h+lpMem]
0x1800112b4  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800112b9  mov     ebx, eax
0x1800112bb  test    eax, eax
0x1800112bd  jns     loc_180011374
0x1800112c3  mov     rcx, [rbp+88h]; this
0x1800112ca  mov     r9d, eax; char *
0x1800112cd  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800112d4  mov     edx, 180h; void *
0x1800112d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112de  nop
0x1800112df  mov     rdi, [rsp+180h+lpMem]
0x1800112e4  test    rdi, rdi
0x1800112e7  jz      short loc_180011302
0x1800112e9  call    cs:__imp_GetProcessHeap
0x1800112ef  mov     rcx, rax; hHeap
0x1800112f2  mov     r8, rdi; lpMem
0x1800112f5  xor     edx, edx; dwFlags
0x1800112f7  call    cs:__imp_HeapFree
0x1800112fd  mov     [rsp+180h+lpMem], r13
0x180011302  mov     [rsp+180h+var_110], r13
0x180011307  mov     [rsp+180h+var_108], r13
0x18001130c  mov     rcx, [rsp+180h+hKey]; hKey
0x180011311  test    rcx, rcx
0x180011314  jz      short loc_18001131D
0x180011316  call    cs:__imp_RegCloseKey
0x18001131c  nop
0x18001131d  cmp     [rbp+80h+var_78], 0
0x180011321  jz      short loc_18001132D
0x180011323  lea     rcx, [rbp+80h+var_90]; this
0x180011327  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001132c  nop
0x18001132d  cmp     [rbp+80h+var_98], 0
0x180011331  jz      short loc_18001134B
0x180011333  mov     rdi, [rbp+80h+var_A0]
0x180011337  call    cs:__imp_GetProcessHeap
0x18001133d  mov     r8, rdi; lpMem
0x180011340  xor     edx, edx; dwFlags
0x180011342  mov     rcx, rax; hHeap
0x180011345  call    cs:__imp_HeapFree
0x18001134b  mov     eax, ebx
0x18001134d  mov     rcx, [rbp+80h+var_38]
0x180011351  xor     rcx, rsp; StackCookie
0x180011354  call    __security_check_cookie
0x180011359  mov     rbx, [rsp+180h+arg_10]
0x180011361  add     rsp, 150h
0x180011368  pop     r15
0x18001136a  pop     r14
0x18001136c  pop     r13
0x18001136e  pop     r12
0x180011370  pop     rdi
0x180011371  pop     rsi
0x180011372  pop     rbp
0x180011373  retn
0x180011374  mov     [rsp+180h+var_130], r13
0x180011379  lea     rax, [rsp+180h+var_130]
0x18001137e  mov     [rsp+180h+phkResult], rax; int
0x180011383  mov     r9d, 20019h; samDesired
0x180011389  xor     r8d, r8d; ulOptions
0x18001138c  mov     rdx, [rsp+180h+lpMem]; lpSubKey
0x180011391  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180011398  call    cs:__imp_RegOpenKeyExW
0x18001139e  test    eax, eax
0x1800113a0  jnz     short loc_180011409
0x1800113a2  test    esi, esi
0x1800113a4  jnz     loc_180011AB0
0x1800113aa  mov     rcx, [rsp+180h+var_130]; hKey
0x1800113af  test    rcx, rcx
0x1800113b2  jz      short loc_1800113BB
0x1800113b4  call    cs:__imp_RegCloseKey
0x1800113ba  nop
0x1800113bb  mov     rbx, [rsp+180h+lpMem]
0x1800113c0  test    rbx, rbx
0x1800113c3  jz      short loc_1800113DE
0x1800113c5  call    cs:__imp_GetProcessHeap
0x1800113cb  mov     rcx, rax; hHeap
0x1800113ce  mov     r8, rbx; lpMem
0x1800113d1  xor     edx, edx; dwFlags
0x1800113d3  call    cs:__imp_HeapFree
0x1800113d9  mov     [rsp+180h+lpMem], r13
0x1800113de  mov     [rsp+180h+var_110], r13
0x1800113e3  mov     [rsp+180h+var_108], r13
0x1800113e8  mov     rcx, [rsp+180h+hKey]; hKey
0x1800113ed  test    rcx, rcx
0x1800113f0  jz      short loc_1800113F9
0x1800113f2  call    cs:__imp_RegCloseKey
0x1800113f8  nop
0x1800113f9  lea     rcx, [rbp+80h+var_B0]; this
0x1800113fd  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180011402  xor     eax, eax
0x180011404  jmp     loc_18001134D
0x180011409  mov     [rbp+80h+var_F8], r13
0x18001140d  mov     [rbp+80h+var_F0], 0FFFFFFFFFFFFFFFFh
0x180011415  mov     [rbp+80h+var_E8], 0FFFFFFFFFFFFFFFFh
0x18001141d  lea     r8, [rbp+80h+var_F8]
0x180011421  mov     rdx, rdi
0x180011424  mov     ecx, 6
0x180011429  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x18001142f  mov     ebx, eax
0x180011431  test    eax, eax
0x180011433  js      loc_180011ADE
0x180011439  mov     r8d, 13h
0x18001143f  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\"
0x180011446  lea     rcx, [rbp+80h+var_F8]
0x18001144a  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001144f  mov     ebx, eax
0x180011451  test    eax, eax
0x180011453  js      loc_180011AE5
0x180011459  mov     [rbp+80h+var_C8], r13
0x18001145d  mov     byte ptr [rbp+80h+var_C0], 0
0x180011461  test    r14, r14
0x180011464  jz      short loc_18001147C
0x180011466  mov     rdx, r14; void *
0x180011469  lea     rcx, [rbp+80h+var_C8]; this
0x18001146d  call    ?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z; CAutoImpersonate::ImpersonateUser(void *)
0x180011472  mov     ebx, eax
0x180011474  test    eax, eax
0x180011476  js      loc_180011B05
0x18001147c  xor     edx, edx; lpSecurityAttributes
0x18001147e  mov     rcx, [rbp+80h+var_F8]; unsigned __int16 *
0x180011482  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x180011487  mov     ebx, eax
0x180011489  test    eax, eax
0x18001148b  jns     loc_180011512
0x180011491  mov     rcx, [rbp+88h]; this
0x180011498  mov     rdx, [rbp+80h+var_F8]
0x18001149c  mov     qword ptr [rsp+180h+samDesired], rdx; char *
0x1800114a1  lea     rax, aLocalHiveDirec; "Local Hive Directory Path: %ws"
0x1800114a8  mov     [rsp+180h+phkResult], rax; int
0x1800114ad  mov     r9d, ebx; char *
0x1800114b0  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800114b7  mov     edx, 19Fh; void *
0x1800114bc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800114c1  lea     rcx, [rbp+80h+var_C8]; this
0x1800114c5  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x1800114ca  nop
0x1800114cb  lea     rcx, [rbp+80h+var_F8]
0x1800114cf  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800114d4  nop
0x1800114d5  mov     rcx, [rsp+180h+var_130]; hKey
0x1800114da  test    rcx, rcx
0x1800114dd  jz      short loc_1800114E6
0x1800114df  call    cs:__imp_RegCloseKey
0x1800114e5  nop
0x1800114e6  lea     rcx, [rsp+180h+lpMem]
0x1800114eb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800114f0  nop
0x1800114f1  mov     rcx, [rsp+180h+hKey]; hKey
0x1800114f6  test    rcx, rcx
0x1800114f9  jz      short loc_180011502
0x1800114fb  call    cs:__imp_RegCloseKey
0x180011501  nop
0x180011502  lea     rcx, [rbp+80h+var_B0]; this
0x180011506  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001150b  mov     eax, ebx
0x18001150d  jmp     loc_18001134D
0x180011512  lea     rcx, [rbp+80h+var_C8]; this
0x180011516  call    ?ResetImpersonation@CAutoImpersonate@@QEAAXXZ; CAutoImpersonate::ResetImpersonation(void)
0x18001151b  mov     [rbp+80h+lpFileName], r13
0x18001151f  mov     [rbp+80h+var_D8], r13
0x180011523  mov     [rbp+80h+var_D0], r13
0x180011527  mov     r8, [rbp+80h+var_F8]
0x18001152b  lea     rdx, aSUsrclassDat; "%s\\UsrClass.dat"
0x180011532  lea     rcx, [rbp+80h+lpFileName]
0x180011536  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001153b  mov     ebx, eax
0x18001153d  test    eax, eax
0x18001153f  js      loc_180011B2E
0x180011545  xorps   xmm0, xmm0
0x180011548  xor     eax, eax
0x18001154a  movups  [rbp+80h+FileInformation], xmm0
0x18001154e  movups  [rbp+80h+var_50], xmm0
0x180011552  mov     [rbp+80h+var_40], eax
0x180011555  lea     r8, [rbp+80h+FileInformation]; lpFileInformation
0x180011559  xor     edx, edx; fInfoLevelId
0x18001155b  mov     rsi, [rbp+80h+lpFileName]
0x18001155f  mov     rcx, rsi; lpFileName
0x180011562  call    cs:__imp_GetFileAttributesExW
0x180011568  mov     r13d, eax
0x18001156b  test    eax, eax
0x18001156d  jnz     loc_180011B58
0x180011573  mov     rax, [rbp+80h+var_100]
0x180011577  mov     qword ptr [rsp+180h+samDesired], rax; void **
0x18001157c  mov     [rsp+180h+phkResult], r14; int
0x180011581  mov     r9, [rsp+180h+hKey]; HKEY
0x180011586  mov     r8, rsi; unsigned __int16 *
0x180011589  mov     rdx, [rsp+180h+lpMem]; unsigned __int16 *
0x18001158e  call    ?MountRegHive@@YAJPEAUHKEY__@@PEBG10PEAXPEAPEAX@Z; MountRegHive(HKEY__ *,ushort const *,ushort const *,HKEY__ *,void *,void * *)
0x180011593  mov     ebx, eax
0x180011595  test    eax, eax
0x180011597  js      loc_1800116D6
0x18001159d  lea     rax, [rsp+180h+lpMem]
0x1800115a2  mov     [rbp+80h+var_C8], rax
0x1800115a6  lea     rax, [rbp+80h+var_100]
0x1800115aa  mov     [rbp+80h+var_C0], rax
0x1800115ae  mov     [rbp+80h+var_B8], 1
0x1800115b2  mov     r14, [rsp+180h+var_130]
0x1800115b7  test    r14, r14
0x1800115ba  jnz     loc_180011BA3
0x1800115c0  mov     [rsp+180h+var_130], 0
0x1800115c9  lea     rax, [rsp+180h+var_130]
0x1800115ce  mov     [rsp+180h+phkResult], rax; int
0x1800115d3  mov     r9d, 60019h; samDesired
0x1800115d9  xor     r8d, r8d; ulOptions
0x1800115dc  mov     rdx, [rsp+180h+lpMem]; lpSubKey
0x1800115e1  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800115e8  call    cs:__imp_RegOpenKeyExW
0x1800115ee  test    eax, eax
0x1800115f0  jnz     loc_18001189B
0x1800115f6  mov     [rsp+180h+var_128], al
0x1800115fa  lea     r8, [rsp+180h+var_128]; bool *
0x1800115ff  mov     rdx, rdi; unsigned __int16 *
0x180011602  mov     rcx, [rsp+180h+var_130]; HKEY
0x180011607  call    ?IsUserSecuritySetInKey@@YAJPEAUHKEY__@@PEBGPEA_N@Z; IsUserSecuritySetInKey(HKEY__ *,ushort const *,bool *)
0x18001160c  mov     ebx, eax
0x18001160e  test    eax, eax
0x180011610  js      loc_180011752
0x180011616  test    r13d, r13d
0x180011619  jz      loc_180011C0C
0x18001161f  test    r15d, r15d
0x180011622  jnz     loc_180011C0C
0x180011628  cmp     [rsp+180h+var_128], r15b
0x18001162d  jz      loc_180011C0C
0x180011633  mov     rdx, [rsp+180h+var_130]; hKey
0x180011638  mov     rcx, rdi; unsigned __int16 *
0x18001163b  call    ?TestSetDefaultClassHiveAppContainerSecurity@@YAJPEBGPEAUHKEY__@@@Z; TestSetDefaultClassHiveAppContainerSecurity(ushort const *,HKEY__ *)
0x180011640  mov     ebx, eax
0x180011642  test    eax, eax
0x180011644  js      loc_1800118E6
0x18001164a  xor     r13d, r13d
0x18001164d  mov     [rbp+80h+var_C8], r13
0x180011651  mov     [rsp+180h+lpdwDisposition], r13; lpdwDisposition
0x180011656  lea     rax, [rbp+80h+var_C8]
0x18001165a  mov     [rsp+180h+var_148], rax; phkResult
0x18001165f  mov     [rsp+180h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180011664  mov     [rsp+180h+samDesired], 2001Fh; samDesired
0x18001166c  mov     dword ptr [rsp+180h+phkResult], r13d; int
0x180011671  xor     r9d, r9d; lpClass
0x180011674  xor     r8d, r8d; Reserved
0x180011677  lea     rdx, aLocalSettings; "Local Settings"
0x18001167e  mov     rcx, [rsp+180h+var_130]; hKey
0x180011683  call    cs:__imp_RegCreateKeyExW
0x180011689  mov     rcx, [rbp+88h]; this
0x180011690  test    eax, eax
0x180011692  jnz     loc_180011CB7
0x180011698  mov     rcx, [rbp+80h+var_C8]; hKey
0x18001169c  test    rcx, rcx
0x18001169f  jz      short loc_1800116A7
0x1800116a1  call    cs:__imp_RegCloseKey
0x1800116a7  mov     rdx, rdi; unsigned __int16 *
0x1800116aa  mov     rcx, [rsp+180h+hKey]; hKey
0x1800116af  call    ?MapUserClassesIntoUserHive@@YAJPEAUHKEY__@@PEBG@Z; MapUserClassesIntoUserHive(HKEY__ *,ushort const *)
0x1800116b4  mov     ebx, eax
0x1800116b6  test    eax, eax
0x1800116b8  js      loc_180011A66
0x1800116be  lea     rcx, [rbp+80h+lpFileName]
0x1800116c2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800116c7  nop
  ... truncated ...
```
