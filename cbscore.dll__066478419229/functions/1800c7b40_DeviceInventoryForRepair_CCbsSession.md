# DeviceInventoryForRepair(CCbsSession *)

- ea: `0x1800c7b40`
- end: `0x1800c82d1`
- name: `?DeviceInventoryForRepair@@YAJPEAVCCbsSession@@@Z`
- size: `1937`
- prototype: `__int64 __fastcall(struct CCbsSession *this)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18015e85c`
- `0x1801d1838`

## callees

- `0x180013250`
- `0x180015420`
- `0x180019bdc`
- `0x180028e24`
- `0x18002a448`
- `0x180042448`
- `0x180056864`
- `0x18005ec58`
- `0x18008f280`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800b980c`
- `0x1800c7b40`
- `0x1800c82d8`
- `0x1800eb920`
- `0x180125964`
- `0x18012b630`
- `0x1801c1498`
- `0x1801ce3f0`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800c80fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800c80fa`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800c7d46`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800c7d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c804f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c81d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c804f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c81d4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800c803b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800c803b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800c81c0`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800c81c0`

## string_xrefs

- `0x1800c7d8d`: `Failed to load updateagent.dll`
- `0x1800c8203`: `Failed to move the temporary Device inventory file: {}`
- `0x1800c807e`: `Failed to create backup for Device Inventory file: {}`
- `0x1800c7cd4`: `Failed to get path to UpdateAgent.dll`
- `0x1800c7c18`: `Skipping device inventory generation during shutdown.`
- `0x1800c7c6e`: `Skipping device inventory generation during maintenance session.`
- `0x1800c7c7f`: `Skipping device inventory generation during startup.`
- `0x1800c7c9e`: `UpdateAgent.dll`
- `0x1800c80f0`: `UA_CreateDeviceInformation`
- `0x1800c814d`: `Unable to cleanup the temporary Device inventory file: {}`
- `0x1800c8173`: `Failed to execute CreateDeviceInformation from updateagent.dll`
- `0x1800c7f12`: `Servicing\Sessions\DeviceInventory.xml`
- `0x1800c7f83`: `Servicing\Sessions\DeviceInventory.xml`
- `0x1800c7f39`: `Servicing\Sessions\DeviceInventory.back.xml`
- `0x1800c7fab`: `Servicing\Sessions\DeviceInventory.back.xml`
- `0x1800c7ff7`: `DeviceInventory.tmp.xml`

## pseudocode

```c
__int64 __fastcall DeviceInventoryForRepair(struct CCbsSession *this)
{
  int v2; // edx
  wchar_t *v4; // rbx
  const char *v5; // rdx
  int Win32PathOfSiblingFile; // eax
  unsigned int v7; // r14d
  int v8; // edx
  const WCHAR *v9; // rax
  HMODULE Library; // rax
  HMODULE v11; // rsi
  signed int LastError; // edi
  int v13; // edx
  unsigned int v14; // eax
  CCbsSession *v15; // rcx
  int OfflineWindowsDirectory; // eax
  int v17; // edx
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  int OfflineServicingStackVersion; // eax
  int v21; // edx
  int v22; // eax
  int v23; // eax
  int WindowsDirectory; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  const WCHAR *v29; // rdi
  signed int v30; // esi
  int v31; // edx
  unsigned int v32; // eax
  unsigned __int64 v33; // r9
  __int64 v34; // rdx
  FARPROC ProcAddress; // rax
  wchar_t *v36; // r9
  const WCHAR *v37; // rbx
  int v38; // eax
  int v39; // edx
  signed int v40; // edi
  int v41; // edx
  unsigned int v42; // eax
  unsigned int v43; // [rsp+20h] [rbp-39h]
  unsigned int v44[2]; // [rsp+30h] [rbp-29h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-21h] BYREF
  int v46[2]; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v47[2]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v48; // [rsp+50h] [rbp-9h] BYREF
  LPCWSTR lpNewFileName; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+60h] [rbp+7h] BYREF
  __int128 v51; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v52; // [rsp+78h] [rbp+1Fh]
  wchar_t *v53; // [rsp+80h] [rbp+27h] BYREF
  LPCWSTR v54; // [rsp+88h] [rbp+2Fh] BYREF
  unsigned __int64 v55; // [rsp+90h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( this )
  {
    v4 = 0;
    hModule = 0;
    lpExistingFileName = 0;
    v54 = 0;
    lpNewFileName = 0;
    v48 = 0;
    v53 = 0;
    if ( vbRebootInProgress )
    {
      v5 = "Skipping device inventory generation during shutdown.";
LABEL_7:
      LogAdapter::TraceAtLevel<>(1, v5);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v53);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v48);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v54);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
      return 0;
    }
    if ( *((_BYTE *)this + 2321) )
    {
      v5 = "Skipping device inventory generation during maintenance session.";
      goto LABEL_7;
    }
    if ( *((_BYTE *)this + 1481) )
    {
      LogAdapter::TraceAtLevel<>(1, "Skipping device inventory generation during startup.");
LABEL_79:
      v7 = 0;
      goto LABEL_80;
    }
    v52 = 0;
    v51 = 0;
    Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(
                               DecompressDeltaFileIfNecessary,
                               L"UpdateAgent.dll",
                               &v51);
    v7 = Win32PathOfSiblingFile;
    if ( Win32PathOfSiblingFile < 0 )
    {
      LODWORD(v55) = Win32PathOfSiblingFile;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get path to UpdateAgent.dll");
        *(_QWORD *)v44 = &v55;
        LOBYTE(v8) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v8,
          3,
          (unsigned int)": {}",
          (__int64)v44);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE75,
        (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
        (const char *)v7,
        v43);
      goto LABEL_16;
    }
    v9 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v51);
    Library = LoadLibraryExW(v9, 0, 8u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &hModule,
      Library);
    v11 = hModule;
    if ( !hModule )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load updateagent.dll");
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        else
          v14 = LastError;
        LODWORD(v55) = v14;
        LOBYTE(v13) = 1;
        *(_QWORD *)v44 = &v55;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v13,
          3,
          (unsigned int)": {0}",
          (__int64)v44);
      }
      if ( LastError )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xE77,
               (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
               (const char *)(unsigned int)LastError,
               v43);
LABEL_16:
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v51);
LABEL_80:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v53);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v48);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v54);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
        return v7;
      }
LABEL_78:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v51);
      goto LABEL_79;
    }
    *(_QWORD *)v44 = 0;
    if ( (unsigned int)CCbsSession::IsOffline(this) )
    {
      OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(v15, &v53);
      v7 = OfflineWindowsDirectory;
      if ( OfflineWindowsDirectory < 0 )
      {
        LODWORD(v55) = OfflineWindowsDirectory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get offline windir");
          *(_QWORD *)v46 = &v55;
          LOBYTE(v17) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v17,
            3,
            (unsigned int)": {}",
            (__int64)v46);
        }
        v18 = 3711;
LABEL_30:
        v19 = v7;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
          (const char *)v19,
          v43);
LABEL_32:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v44);
        goto LABEL_16;
      }
      v55 = 0;
      OfflineServicingStackVersion = CCbsSession::GetOfflineServicingStackVersion(this, &v55);
      v7 = OfflineServicingStackVersion;
      if ( OfflineServicingStackVersion < 0 )
      {
        LODWORD(v55) = OfflineServicingStackVersion;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to get offline servicing stack version.");
          *(_QWORD *)v46 = &v55;
          LOBYTE(v21) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v21,
            3,
            (unsigned int)": {}",
            (__int64)v46);
        }
        v18 = 3714;
        goto LABEL_30;
      }
      if ( !v55 )
        goto LABEL_77;
      v4 = v53;
      v22 = SczAllocCombinePath2Sz(&lpExistingFileName, v53, L"Servicing\\Sessions\\DeviceInventory.xml");
      v7 = v22;
      if ( v22 < 0 )
      {
        v19 = (unsigned int)v22;
        v18 = 3723;
        goto LABEL_31;
      }
      v23 = SczAllocCombinePath2Sz(&lpNewFileName, v4, L"Servicing\\Sessions\\DeviceInventory.back.xml");
      v7 = v23;
      if ( v23 < 0 )
      {
        v19 = (unsigned int)v23;
        v18 = 3725;
        goto LABEL_31;
      }
    }
    else
    {
      WindowsDirectory = PathGetWindowsDirectory(v44, 0);
      v7 = WindowsDirectory;
      if ( WindowsDirectory < 0 )
      {
        v19 = (unsigned int)WindowsDirectory;
        v18 = 3729;
        goto LABEL_31;
      }
      v25 = SczAllocCombinePath2Sz(&lpExistingFileName, *(_QWORD *)v44, L"Servicing\\Sessions\\DeviceInventory.xml");
      v7 = v25;
      if ( v25 < 0 )
      {
        v19 = (unsigned int)v25;
        v18 = 3732;
        goto LABEL_31;
      }
      v26 = SczAllocCombinePath2Sz(&lpNewFileName, *(_QWORD *)v44, L"Servicing\\Sessions\\DeviceInventory.back.xml");
      v7 = v26;
      if ( v26 < 0 )
      {
        v19 = (unsigned int)v26;
        v18 = 3734;
        goto LABEL_31;
      }
    }
    v27 = SczAllocFromSz(&v48, *((_QWORD *)this + 138));
    v7 = v27;
    if ( v27 < 0 )
    {
      v19 = (unsigned int)v27;
      v18 = 3737;
      goto LABEL_31;
    }
    v28 = SczAllocCombinePath2Sz(&v54, v48, L"DeviceInventory.tmp.xml");
    v7 = v28;
    if ( v28 < 0 )
    {
      v19 = (unsigned int)v28;
      v18 = 3738;
      goto LABEL_31;
    }
    v29 = lpExistingFileName;
    if ( !(unsigned int)DoesFileExist(lpExistingFileName, 0) || CopyFileW(v29, lpNewFileName, 0) )
    {
      ProcAddress = GetProcAddress(v11, "UA_CreateDeviceInformation");
      v36 = v4;
      v37 = v54;
      v7 = ((__int64 (__fastcall *)(__int64, __int64, LPCWSTR, wchar_t *))ProcAddress)(2, v48, v54, v36);
      if ( (v7 & 0x80000000) != 0 )
      {
        if ( (unsigned int)DoesFileExist(v37, 0) )
        {
          *(_QWORD *)v47 = v37;
          v38 = CbsSetAttrAndDeleteFile(v37);
          if ( v38 < 0 )
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
              1,
              (unsigned int)v38,
              "Unable to cleanup the temporary Device inventory file: {}",
              v47);
        }
        LODWORD(v55) = v7;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to execute CreateDeviceInformation from updateagent.dll");
          *(_QWORD *)v47 = &v55;
          LOBYTE(v39) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v39,
            3,
            (unsigned int)": {}",
            (__int64)v47);
        }
        v18 = 3761;
        goto LABEL_30;
      }
      if ( !MoveFileExW(v37, v29, 1u) )
      {
        v40 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v47 = v37;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to move the temporary Device inventory file: {}",
            (__int64)v47);
          if ( v40 > 0 )
            v42 = (unsigned __int16)v40 | 0x80070000;
          else
            v42 = v40;
          LODWORD(v55) = v42;
          LOBYTE(v41) = 1;
          *(_QWORD *)v46 = &v55;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v41,
            3,
            (unsigned int)": {0}",
            (__int64)v46);
        }
        if ( v40 )
        {
          v33 = (unsigned int)v40;
          v34 = 3769;
          goto LABEL_61;
        }
      }
    }
    else
    {
      v30 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v46 = v29;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to create backup for Device Inventory file: {}",
          (__int64)v46);
        if ( v30 > 0 )
          v32 = (unsigned __int16)v30 | 0x80070000;
        else
          v32 = v30;
        LODWORD(v55) = v32;
        LOBYTE(v31) = 1;
        *(_QWORD *)v47 = &v55;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v31,
          3,
          (unsigned int)": {0}",
          (__int64)v47);
      }
      if ( v30 )
      {
        v33 = (unsigned int)v30;
        v34 = 3747;
LABEL_61:
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v34,
               (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
               (const char *)v33,
               v43);
        goto LABEL_32;
      }
    }
LABEL_77:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v44);
    goto LABEL_78;
  }
  LODWORD(v55) = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No session specified.");
    hModule = (HMODULE)&v55;
    LOBYTE(v2) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v2,
      3,
      (unsigned int)": {}",
      (__int64)&hModule);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE53,
    (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
    (const char *)0x80070057LL,
    v43);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800c7b40  mov     [rsp-8+arg_8], rbx
0x1800c7b45  mov     [rsp-8+arg_10], rsi
0x1800c7b4a  push    rbp
0x1800c7b4b  push    rdi
0x1800c7b4c  push    r14
0x1800c7b4e  lea     rbp, [rsp-47h]
0x1800c7b53  sub     rsp, 0A0h
0x1800c7b5a  mov     rax, cs:__security_cookie
0x1800c7b61  xor     rax, rsp
0x1800c7b64  mov     [rbp+57h+var_18], rax
0x1800c7b68  mov     rdi, rcx
0x1800c7b6b  test    rcx, rcx
0x1800c7b6e  jnz     short loc_1800C7BE2
0x1800c7b70  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7b77  mov     edi, 80070057h
0x1800c7b7c  mov     dword ptr [rbp+57h+var_20], edi
0x1800c7b7f  test    rcx, rcx
0x1800c7b82  jz      short loc_1800C7BC3
0x1800c7b84  mov     ebx, 3
0x1800c7b89  lea     r9, aNoSessionSpeci; "No session specified."
0x1800c7b90  mov     r8d, ebx
0x1800c7b93  xor     edx, edx
0x1800c7b95  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7b9a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7ba1  lea     rax, [rbp+57h+var_20]
0x1800c7ba5  mov     [rbp+57h+hModule], rax
0x1800c7ba9  lea     r9, asc_1802EE7AC; ": {}"
0x1800c7bb0  lea     rax, [rbp+57h+hModule]
0x1800c7bb4  mov     r8d, ebx
0x1800c7bb7  mov     dl, 1
0x1800c7bb9  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800c7bbe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7bc3  mov     rcx, [rbp+5Fh]; this
0x1800c7bc7  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800c7bce  mov     r9d, edi; char *
0x1800c7bd1  mov     edx, 0E53h; void *
0x1800c7bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7bdb  mov     eax, edi
0x1800c7bdd  jmp     loc_1800C82AC
0x1800c7be2  xor     ebx, ebx
0x1800c7be4  mov     [rbp+57h+hModule], 0
0x1800c7bec  cmp     cs:?vbRebootInProgress@@3HA, ebx; int vbRebootInProgress
0x1800c7bf2  mov     [rbp+57h+lpExistingFileName], 0
0x1800c7bfa  mov     [rbp+57h+var_28], 0
0x1800c7c02  mov     [rbp+57h+lpNewFileName], 0
0x1800c7c0a  mov     [rbp+57h+var_60], 0
0x1800c7c12  mov     [rbp+57h+var_30], rbx
0x1800c7c16  jz      short loc_1800C7C66
0x1800c7c18  lea     rdx, aSkippingDevice; "Skipping device inventory generation du"...
0x1800c7c1f  mov     ecx, 1
0x1800c7c24  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800c7c29  lea     rcx, [rbp+57h+var_30]
0x1800c7c2d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c7c32  lea     rcx, [rbp+57h+var_60]
0x1800c7c36  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c7c3b  lea     rcx, [rbp+57h+lpNewFileName]
0x1800c7c3f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c7c44  lea     rcx, [rbp+57h+var_28]
0x1800c7c48  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c7c4d  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800c7c51  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c7c56  lea     rcx, [rbp+57h+hModule]
0x1800c7c5a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800c7c5f  xor     eax, eax
0x1800c7c61  jmp     loc_1800C82AC
0x1800c7c66  cmp     [rcx+911h], bl
0x1800c7c6c  jz      short loc_1800C7C77
0x1800c7c6e  lea     rdx, aSkippingDevice_1; "Skipping device inventory generation du"...
0x1800c7c75  jmp     short loc_1800C7C1F
0x1800c7c77  cmp     [rcx+5C9h], bl
0x1800c7c7d  jz      short loc_1800C7C95
0x1800c7c7f  lea     rdx, aSkippingDevice_0; "Skipping device inventory generation du"...
0x1800c7c86  mov     ecx, 1
0x1800c7c8b  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800c7c90  jmp     loc_1800C8270
0x1800c7c95  xorps   xmm0, xmm0
0x1800c7c98  lea     r8, [rbp+57h+var_48]
0x1800c7c9c  xor     eax, eax
0x1800c7c9e  lea     rdx, aUpdateagentDll_1; "UpdateAgent.dll"
0x1800c7ca5  lea     rcx, DecompressDeltaFileIfNecessary
0x1800c7cac  mov     [rbp+57h+var_38], rax
0x1800c7cb0  movups  [rbp+57h+var_48], xmm0
0x1800c7cb4  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x1800c7cb9  mov     r14d, eax
0x1800c7cbc  test    eax, eax
0x1800c7cbe  jns     short loc_1800C7D34
0x1800c7cc0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7cc7  mov     dword ptr [rbp+57h+var_20], eax
0x1800c7cca  test    rcx, rcx
0x1800c7ccd  jz      short loc_1800C7D0E
0x1800c7ccf  mov     ebx, 3
0x1800c7cd4  lea     r9, aFailedToGetPat_0; "Failed to get path to UpdateAgent.dll"
0x1800c7cdb  mov     r8d, ebx
0x1800c7cde  xor     edx, edx
0x1800c7ce0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7ce5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7cec  lea     rax, [rbp+57h+var_20]
0x1800c7cf0  mov     qword ptr [rbp+57h+var_80], rax
0x1800c7cf4  lea     r9, asc_1802EE7AC; ": {}"
0x1800c7cfb  lea     rax, [rbp+57h+var_80]
0x1800c7cff  mov     r8d, ebx
0x1800c7d02  mov     dl, 1
0x1800c7d04  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800c7d09  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7d0e  mov     rcx, [rbp+5Fh]; this
0x1800c7d12  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800c7d19  mov     r9d, r14d; char *
0x1800c7d1c  mov     edx, 0E75h; void *
0x1800c7d21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7d26  lea     rcx, [rbp+57h+var_48]
0x1800c7d2a  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800c7d2f  jmp     loc_1800C8273
0x1800c7d34  lea     rcx, [rbp+57h+var_48]
0x1800c7d38  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x1800c7d3d  xor     edx, edx; hFile
0x1800c7d3f  mov     rcx, rax; lpLibFileName
0x1800c7d42  lea     r8d, [rdx+8]; dwFlags
0x1800c7d46  call    cs:__imp_LoadLibraryExW
0x1800c7d4d  nop     dword ptr [rax+rax+00h]
0x1800c7d52  mov     rdx, rax
0x1800c7d55  lea     rcx, [rbp+57h+hModule]
0x1800c7d59  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800c7d5e  mov     rsi, [rbp+57h+hModule]
0x1800c7d62  test    rsi, rsi
0x1800c7d65  jnz     loc_1800C7DFD
0x1800c7d6b  call    cs:__imp_GetLastError
0x1800c7d72  nop     dword ptr [rax+rax+00h]
0x1800c7d77  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7d7e  mov     edi, eax
0x1800c7d80  test    rcx, rcx
0x1800c7d83  jz      short loc_1800C7DD5
0x1800c7d85  lea     ebx, [rsi+3]
0x1800c7d88  xor     edx, edx
0x1800c7d8a  mov     r8d, ebx
0x1800c7d8d  lea     r9, aFailedToLoadUp; "Failed to load updateagent.dll"
0x1800c7d94  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7d99  test    edi, edi
0x1800c7d9b  jg      short loc_1800C7DA1
0x1800c7d9d  mov     eax, edi
0x1800c7d9f  jmp     short loc_1800C7DA9
0x1800c7da1  movzx   eax, di
0x1800c7da4  or      eax, 80070000h
0x1800c7da9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7db0  lea     r9, a0; ": {0}"
0x1800c7db7  mov     dword ptr [rbp+57h+var_20], eax
0x1800c7dba  mov     r8d, ebx
0x1800c7dbd  lea     rax, [rbp+57h+var_20]
0x1800c7dc1  mov     dl, 1
0x1800c7dc3  mov     qword ptr [rbp+57h+var_80], rax
0x1800c7dc7  lea     rax, [rbp+57h+var_80]
0x1800c7dcb  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x1800c7dd0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7dd5  test    edi, edi
0x1800c7dd7  jz      loc_1800C8267
0x1800c7ddd  mov     rcx, [rbp+5Fh]; this
0x1800c7de1  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800c7de8  mov     r9d, edi; char *
0x1800c7deb  mov     edx, 0E77h; void *
0x1800c7df0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c7df5  mov     r14d, eax
0x1800c7df8  jmp     loc_1800C7D26
0x1800c7dfd  mov     rcx, rdi; this
0x1800c7e00  mov     qword ptr [rbp+57h+var_80], rbx
0x1800c7e04  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x1800c7e09  test    eax, eax
0x1800c7e0b  jz      loc_1800C7F60
0x1800c7e11  lea     rdx, [rbp+57h+var_30]; wchar_t **
0x1800c7e15  call    ?GetOfflineWindowsDirectory@CCbsSession@@QEBAJPEAPEA_W@Z; CCbsSession::GetOfflineWindowsDirectory(wchar_t * *)
0x1800c7e1a  mov     r14d, eax
0x1800c7e1d  test    eax, eax
0x1800c7e1f  jns     short loc_1800C7E95
0x1800c7e21  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7e28  mov     dword ptr [rbp+57h+var_20], eax
0x1800c7e2b  test    rcx, rcx
0x1800c7e2e  jz      short loc_1800C7E6F
0x1800c7e30  mov     ebx, 3
0x1800c7e35  lea     r9, aFailedToGetOff_11; "Failed to get offline windir"
0x1800c7e3c  mov     r8d, ebx
0x1800c7e3f  xor     edx, edx
0x1800c7e41  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7e46  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7e4d  lea     rax, [rbp+57h+var_20]
0x1800c7e51  mov     qword ptr [rbp+57h+var_70], rax
0x1800c7e55  lea     r9, asc_1802EE7AC; ": {}"
0x1800c7e5c  lea     rax, [rbp+57h+var_70]
0x1800c7e60  mov     r8d, ebx
0x1800c7e63  mov     dl, 1
0x1800c7e65  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800c7e6a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7e6f  mov     edx, 0E7Fh; void *
0x1800c7e74  mov     r9d, r14d; char *
0x1800c7e77  mov     rcx, [rbp+5Fh]; this
0x1800c7e7b  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800c7e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7e87  lea     rcx, [rbp+57h+var_80]
0x1800c7e8b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800c7e90  jmp     loc_1800C7D26
0x1800c7e95  lea     rdx, [rbp+57h+var_20]; unsigned __int64 *
0x1800c7e99  mov     [rbp+57h+var_20], rbx
0x1800c7e9d  mov     rcx, rdi; this
0x1800c7ea0  call    ?GetOfflineServicingStackVersion@CCbsSession@@QEBAJPEA_K@Z; CCbsSession::GetOfflineServicingStackVersion(unsigned __int64 *)
0x1800c7ea5  mov     r14d, eax
0x1800c7ea8  test    eax, eax
0x1800c7eaa  jns     short loc_1800C7F04
0x1800c7eac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7eb3  mov     dword ptr [rbp+57h+var_20], eax
0x1800c7eb6  test    rcx, rcx
0x1800c7eb9  jz      short loc_1800C7EFA
0x1800c7ebb  mov     ebx, 3
0x1800c7ec0  lea     r9, aFailedToGetOff_6; "Failed to get offline servicing stack v"...
0x1800c7ec7  mov     r8d, ebx
0x1800c7eca  xor     edx, edx
0x1800c7ecc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800c7ed1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800c7ed8  lea     rax, [rbp+57h+var_20]
0x1800c7edc  mov     qword ptr [rbp+57h+var_70], rax
0x1800c7ee0  lea     r9, asc_1802EE7AC; ": {}"
0x1800c7ee7  lea     rax, [rbp+57h+var_70]
0x1800c7eeb  mov     r8d, ebx
0x1800c7eee  mov     dl, 1
0x1800c7ef0  mov     qword ptr [rsp+0B0h+var_90], rax
0x1800c7ef5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800c7efa  mov     edx, 0E82h
0x1800c7eff  jmp     loc_1800C7E74
0x1800c7f04  cmp     [rbp+57h+var_20], rbx
0x1800c7f08  jz      loc_1800C825E
0x1800c7f0e  mov     rbx, [rbp+57h+var_30]
0x1800c7f12  lea     r8, aServicingSessi_2; "Servicing\\Sessions\\DeviceInventory.xm"...
0x1800c7f19  mov     rdx, rbx
0x1800c7f1c  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800c7f20  call    SczAllocCombinePath2Sz
0x1800c7f25  mov     r14d, eax
0x1800c7f28  test    eax, eax
0x1800c7f2a  jns     short loc_1800C7F39
0x1800c7f2c  mov     r9d, eax
0x1800c7f2f  mov     edx, 0E8Bh
0x1800c7f34  jmp     loc_1800C7E77
0x1800c7f39  lea     r8, aServicingSessi_0; "Servicing\\Sessions\\DeviceInventory.ba"...
0x1800c7f40  mov     rdx, rbx
0x1800c7f43  lea     rcx, [rbp+57h+lpNewFileName]
0x1800c7f47  call    SczAllocCombinePath2Sz
0x1800c7f4c  mov     r14d, eax
0x1800c7f4f  test    eax, eax
0x1800c7f51  jns     short loc_1800C7FCF
0x1800c7f53  mov     r9d, eax
0x1800c7f56  mov     edx, 0E8Dh
0x1800c7f5b  jmp     loc_1800C7E77
0x1800c7f60  xor     edx, edx
0x1800c7f62  lea     rcx, [rbp+57h+var_80]
0x1800c7f66  call    PathGetWindowsDirectory
0x1800c7f6b  mov     r14d, eax
0x1800c7f6e  test    eax, eax
0x1800c7f70  jns     short loc_1800C7F7F
0x1800c7f72  mov     r9d, eax
0x1800c7f75  mov     edx, 0E91h
0x1800c7f7a  jmp     loc_1800C7E77
0x1800c7f7f  mov     rdx, qword ptr [rbp+57h+var_80]
0x1800c7f83  lea     r8, aServicingSessi_2; "Servicing\\Sessions\\DeviceInventory.xm"...
0x1800c7f8a  lea     rcx, [rbp+57h+lpExistingFileName]
0x1800c7f8e  call    SczAllocCombinePath2Sz
0x1800c7f93  mov     r14d, eax
0x1800c7f96  test    eax, eax
0x1800c7f98  jns     short loc_1800C7FA7
0x1800c7f9a  mov     r9d, eax
0x1800c7f9d  mov     edx, 0E94h
0x1800c7fa2  jmp     loc_1800C7E77
0x1800c7fa7  mov     rdx, qword ptr [rbp+57h+var_80]
0x1800c7fab  lea     r8, aServicingSessi_0; "Servicing\\Sessions\\DeviceInventory.ba"...
0x1800c7fb2  lea     rcx, [rbp+57h+lpNewFileName]
0x1800c7fb6  call    SczAllocCombinePath2Sz
0x1800c7fbb  mov     r14d, eax
0x1800c7fbe  test    eax, eax
0x1800c7fc0  jns     short loc_1800C7FCF
0x1800c7fc2  mov     r9d, eax
0x1800c7fc5  mov     edx, 0E96h
0x1800c7fca  jmp     loc_1800C7E77
0x1800c7fcf  mov     rdx, [rdi+450h]
0x1800c7fd6  lea     rcx, [rbp+57h+var_60]
0x1800c7fda  call    SczAllocFromSz
0x1800c7fdf  mov     r14d, eax
0x1800c7fe2  test    eax, eax
0x1800c7fe4  jns     short loc_1800C7FF3
0x1800c7fe6  mov     r9d, eax
0x1800c7fe9  mov     edx, 0E99h
0x1800c7fee  jmp     loc_1800C7E77
0x1800c7ff3  mov     rdx, [rbp+57h+var_60]
0x1800c7ff7  lea     r8, aDeviceinventor_0; "DeviceInventory.tmp.xml"
0x1800c7ffe  lea     rcx, [rbp+57h+var_28]
0x1800c8002  call    SczAllocCombinePath2Sz
0x1800c8007  mov     r14d, eax
0x1800c800a  test    eax, eax
0x1800c800c  jns     short loc_1800C801B
0x1800c800e  mov     r9d, eax
0x1800c8011  mov     edx, 0E9Ah
0x1800c8016  jmp     loc_1800C7E77
0x1800c801b  mov     rdi, [rbp+57h+lpExistingFileName]
0x1800c801f  xor     edx, edx
0x1800c8021  mov     rcx, rdi
0x1800c8024  call    DoesFileExist
0x1800c8029  test    eax, eax
  ... truncated ...
```
