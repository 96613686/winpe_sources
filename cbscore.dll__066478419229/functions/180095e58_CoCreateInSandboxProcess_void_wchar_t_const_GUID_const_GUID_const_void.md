# CoCreateInSandboxProcess(void *,wchar_t const *,_GUID const &,_GUID const &,void * *)

- ea: `0x180095e58`
- end: `0x180096e3b`
- name: `?CoCreateInSandboxProcess@@YAJPEAXPEB_WAEBU_GUID@@2PEAPEAX@Z`
- size: `4067`
- prototype: `__int64 __fastcall(void *, const wchar_t *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180095950`

## callees

- `0x180010cc0`
- `0x180012fe4`
- `0x180013250`
- `0x1800150c0`
- `0x18002a448`
- `0x180033f58`
- `0x18003404c`
- `0x18004a680`
- `0x18004e2d4`
- `0x180095e34`
- `0x180095e58`
- `0x180096e44`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800d8090`
- `0x1800eb920`
- `0x1800ec920`
- `0x18012baa8`
- `0x18020beb8`
- `0x18020c004`
- `0x18020c2d4`
- `0x18020c504`
- `0x1802cf7cc`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18009613f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18009613f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180096064`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180096064`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180096109`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180096109`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180096718`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180096718`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800962db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800962db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009635c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009665e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800967b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009635c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009665e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800967b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800968c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096dc4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800968b2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800968b2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180096649`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180096649`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009631d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009650b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009631d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009650b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800962be`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180096bf7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800962be`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180096bf7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180096348`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180096537`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180096348`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180096537`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180096c20`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180096d2f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180096db4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180096c20`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180096d2f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180096db4`

## string_xrefs

- `0x18009637b`: `Could not duplicate ready event to sandbox`
- `0x180096566`: `Could not duplicate ready event to sandbox`
- `0x180096b83`: `Failed to open ready event`
- `0x180096c9e`: `Could not get self module file path`
- `0x180095f5e`: `Failed to impersonate`
- `0x18009616c`: `Self module file path malformed`
- `0x180095fee`: `Could not get AppContainer SID`
- `0x1800964ab`: `Failed to create shared section`
- `0x1800965ed`: `Could not replace sandbox command line`
- `0x180096898`: `Unable to cocreate in sandbox process, checking for possible exit codes`
- `0x180096b1e`: `Could not create proxy to sandbox`

## pseudocode

```c
__int64 __fastcall CoCreateInSandboxProcess(
        void *a1,
        const wchar_t *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        void **a5)
{
  DWORD v6; // edi
  int v7; // edx
  __int64 v8; // rdx
  unsigned __int64 v9; // r9
  signed int v10; // eax
  int v11; // edx
  __int64 v12; // rdx
  __int64 InitPointer; // rax
  __int64 v14; // rcx
  signed int AppContainerSidFromName; // eax
  int v16; // edx
  signed int LastError; // edi
  int v18; // edx
  DWORD v19; // eax
  __int64 v20; // rdx
  DWORD ModuleFileNameW; // eax
  wchar_t *v22; // rax
  int v23; // edx
  int v24; // eax
  HANDLE *v25; // rbx
  HANDLE *v26; // rax
  signed int SandboxProcessSuspended; // eax
  int v28; // edx
  int SandboxSharedStruct; // eax
  __int64 v30; // r9
  __int64 v31; // rdx
  HANDLE EventW; // rax
  HANDLE v33; // rbx
  HANDLE v34; // rdi
  HANDLE CurrentProcess; // rax
  signed int v36; // edi
  int v37; // edx
  DWORD v38; // eax
  __int64 v39; // rdx
  const void *v40; // r15
  void *v41; // rsi
  int v42; // edx
  unsigned __int8 **v43; // rdi
  void **v44; // rax
  void *v45; // rdx
  signed int SharedSection; // eax
  int v47; // edx
  HANDLE v48; // rdi
  HANDLE v49; // rsi
  HANDLE v50; // rax
  int v51; // edx
  DWORD v52; // eax
  signed int v53; // eax
  int v54; // edx
  signed int v55; // edi
  int v56; // edx
  DWORD v57; // eax
  __int64 v58; // rdx
  __int64 v59; // r9
  DWORD v60; // eax
  int v61; // edx
  __int64 v62; // rdx
  int v63; // edx
  DWORD v64; // eax
  int v65; // edx
  int v66; // edx
  unsigned int v67; // eax
  int v68; // edx
  int v69; // edx
  int v70; // edx
  void **v71; // rax
  const struct _GUID *v72; // r8
  int v73; // eax
  int v74; // edx
  int v75; // eax
  int v76; // edx
  int v77; // edx
  unsigned int v78; // eax
  void *v79; // rdx
  int v80; // edx
  unsigned int v81; // eax
  void *v82; // rdx
  void *v84; // rdx
  unsigned int dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  LPCVOID lpBaseAddress; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hSourceHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v88; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hThread; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v90[2]; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v91; // [rsp+68h] [rbp-98h] BYREF
  HANDLE p_ExitCode; // [rsp+70h] [rbp-90h] BYREF
  HMODULE phModule; // [rsp+78h] [rbp-88h] BYREF
  HANDLE TargetHandle; // [rsp+80h] [rbp-80h] BYREF
  Windows::Detail *v95; // [rsp+88h] [rbp-78h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hProcess; // [rsp+98h] [rbp-68h] BYREF
  __int64 v98; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v99[2]; // [rsp+A8h] [rbp-58h] BYREF
  void *Src[2]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Filename[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v91 = 0;
  v95 = 0;
  hProcess = 0;
  hThread = 0;
  v88 = 0;
  lpBaseAddress = 0;
  hSourceHandle = 0;
  v98 = 0;
  if ( !a5 )
  {
    v6 = -2147467261;
    ExitCode = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No object instance result specified");
      p_ExitCode = &ExitCode;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)&p_ExitCode);
    }
    v8 = 265;
LABEL_5:
    v9 = v6;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
      (const char *)v9,
      dwDesiredAccess);
LABEL_155:
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v98);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hSourceHandle);
    if ( lpBaseAddress )
    {
      if ( !UnmapViewOfFile(lpBaseAddress) )
      {
        GetLastError();
        __fastfail(7u);
      }
      lpBaseAddress = 0;
    }
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v88);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hThread);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hProcess);
    if ( v95 )
    {
      Windows::Detail::CloseWithRtlFreeSid(v95, v82);
      v95 = 0;
    }
LABEL_161:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v91);
    return v6;
  }
  *a5 = 0;
  Src[0] = a1;
  LOBYTE(Src[1]) = 0;
  v10 = NestableImpersonator::Impersonate((NestableImpersonator *)Src);
  v6 = v10;
  if ( v10 < 0 )
  {
    ExitCode = v10;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to impersonate");
      p_ExitCode = &ExitCode;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&p_ExitCode);
    }
    v12 = 271;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
      (const char *)v6,
      dwDesiredAccess);
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)Src);
    goto LABEL_155;
  }
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v95);
  AppContainerSidFromName = GetAppContainerSidFromName(v14, InitPointer);
  v6 = AppContainerSidFromName;
  if ( AppContainerSidFromName < 0 )
  {
    ExitCode = AppContainerSidFromName;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not get AppContainer SID");
      p_ExitCode = &ExitCode;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)&p_ExitCode);
    }
    v12 = 274;
    goto LABEL_11;
  }
  ImpersonatorBase::Unimpersonate((ImpersonatorBase *)Src);
  memset_0(Filename, 0, 0x20Au);
  phModule = 0;
  if ( !GetModuleHandleExW(6u, &g_bCoCreateInSandboxProcess_ThisModuleMarker, &phModule) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not get self module handle");
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      else
        v19 = LastError;
      ExitCode = v19;
      LOBYTE(v18) = 1;
      p_ExitCode = &ExitCode;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v18,
        3,
        (unsigned int)": {0}",
        (__int64)&p_ExitCode);
    }
    if ( LastError )
    {
      v20 = 289;
LABEL_154:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v20,
             (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
             (const char *)(unsigned int)LastError,
             dwDesiredAccess);
      goto LABEL_155;
    }
    goto LABEL_162;
  }
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
  if ( ModuleFileNameW && (ModuleFileNameW != 261 || GetLastError() != 122) )
  {
    v22 = wcsrchr(Filename, 0x5Cu);
    if ( !v22 )
    {
      v6 = -2147418113;
      ExitCode = -2147418113;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Self module file path malformed");
        p_ExitCode = &ExitCode;
        LOBYTE(v23) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v23,
          3,
          (unsigned int)": {}",
          (__int64)&p_ExitCode);
      }
      v8 = 298;
      goto LABEL_5;
    }
    *v22 = 0;
    v24 = SczAllocCombinePath2Sz(&v91, Filename, L"TiFileFetcher.exe");
    v6 = v24;
    if ( v24 < 0 )
    {
      v9 = (unsigned int)v24;
      v8 = 301;
      goto LABEL_6;
    }
    v25 = (HANDLE *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&hThread);
    v26 = (HANDLE *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&hProcess);
    SandboxProcessSuspended = CreateSandboxProcessSuspended(a1, v91, (unsigned __int64)v95, v26, v25);
    v6 = SandboxProcessSuspended;
    if ( SandboxProcessSuspended < 0 )
    {
      ExitCode = SandboxProcessSuspended;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to start sandbox process");
        p_ExitCode = &ExitCode;
        LOBYTE(v28) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v28,
          3,
          (unsigned int)": {}",
          (__int64)&p_ExitCode);
      }
      v8 = 312;
      goto LABEL_5;
    }
    Src[0] = 0;
    Src[1] = 0;
    TargetHandle = 0;
    p_ExitCode = 0;
    SandboxSharedStruct = AllocateSandboxSharedStruct(Src);
    v6 = SandboxSharedStruct;
    if ( SandboxSharedStruct < 0 )
    {
      v30 = (unsigned int)SandboxSharedStruct;
      v31 = 329;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
        (const char *)v30,
        dwDesiredAccess);
LABEL_40:
      Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(Src);
      goto LABEL_41;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hSourceHandle, EventW);
    v33 = hSourceHandle;
    if ( !hSourceHandle || GetLastError() == 183 )
    {
      v36 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open ready event");
        if ( v36 > 0 )
          v78 = (unsigned __int16)v36 | 0x80070000;
        else
          v78 = v36;
        v99[0] = v78;
        LOBYTE(v77) = 1;
        *(_QWORD *)v90 = v99;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v77,
          3,
          (unsigned int)": {0}",
          (__int64)v90);
      }
      if ( v36 )
      {
        v39 = 335;
        goto LABEL_53;
      }
LABEL_137:
      Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(Src);
LABEL_138:
      if ( hProcess )
        TerminateProcess(hProcess, 0x80080005);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v98);
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hSourceHandle);
      if ( lpBaseAddress )
      {
        if ( !UnmapViewOfFile(lpBaseAddress) )
        {
          GetLastError();
          __fastfail(7u);
        }
        lpBaseAddress = 0;
      }
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v88);
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hThread);
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hProcess);
      if ( v95 )
      {
        Windows::Detail::CloseWithRtlFreeSid(v95, v79);
        v95 = 0;
      }
      v6 = 0;
      goto LABEL_161;
    }
    v34 = hProcess;
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(CurrentProcess, v33, v34, &TargetHandle, 2u, 0, 0) )
    {
      v36 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not duplicate ready event to sandbox");
        if ( v36 > 0 )
          v38 = (unsigned __int16)v36 | 0x80070000;
        else
          v38 = v36;
        ExitCode = v38;
        LOBYTE(v37) = 1;
        *(_QWORD *)v99 = &ExitCode;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v37,
          3,
          (unsigned int)": {0}",
          (__int64)v99);
      }
      if ( v36 )
      {
        v39 = 346;
LABEL_53:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v39,
               (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
               (const char *)(unsigned int)v36,
               dwDesiredAccess);
        goto LABEL_40;
      }
      goto LABEL_137;
    }
    v40 = Src[0];
    v41 = Src[1];
    *((_QWORD *)Src[0] + 2) = TargetHandle;
    if ( (unsigned __int64)v41 > 0xFFFFFFFF )
    {
      v6 = -2147418113;
      ExitCode = -2147418113;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Shared segment way too big");
        *(_QWORD *)v99 = &ExitCode;
        LOBYTE(v42) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v42,
          3,
          (unsigned int)": {}",
          (__int64)v99);
      }
      v30 = 2147549183LL;
      v31 = 351;
      goto LABEL_39;
    }
    v43 = (unsigned __int8 **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&lpBaseAddress);
    v44 = (void **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v88);
    SharedSection = CreateSharedSection((unsigned int)v41, v45, v44, v43);
    v6 = SharedSection;
    if ( SharedSection < 0 )
    {
      ExitCode = SharedSection;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create shared section");
        *(_QWORD *)v99 = &ExitCode;
        LOBYTE(v47) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v47,
          3,
          (unsigned int)": {}",
          (__int64)v99);
      }
      v30 = v6;
      v31 = 358;
      goto LABEL_39;
    }
    memcpy_0((void *)lpBaseAddress, v40, (size_t)v41);
    v48 = hProcess;
    v49 = v88;
    v50 = GetCurrentProcess();
    if ( !DuplicateHandle(v50, v49, v48, &p_ExitCode, 0xF001Fu, 0, 0) )
    {
      v36 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not duplicate ready event to sandbox");
        if ( v36 > 0 )
          v52 = (unsigned __int16)v36 | 0x80070000;
        else
          v52 = v36;
        ExitCode = v52;
        LOBYTE(v51) = 1;
        *(_QWORD *)v99 = &ExitCode;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v51,
          3,
          (unsigned int)": {0}",
          (__int64)v99);
      }
      if ( v36 )
      {
        v39 = 373;
        goto LABEL_53;
      }
      goto LABEL_137;
    }
    v53 = ReplaceCommandLineInProcessMemory(hProcess, (unsigned __int64)p_ExitCode);
    v6 = v53;
    if ( v53 < 0 )
    {
      ExitCode = v53;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not replace sandbox command line");
        *(_QWORD *)v99 = &ExitCode;
        LOBYTE(v54) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v54,
          3,
          (unsigned int)": {}",
          (__int64)v99);
      }
      v30 = v6;
      v31 = 376;
      goto LABEL_39;
    }
    Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(Src);
    *(_OWORD *)Src = 0;
    if ( ResumeThread(hThread) == -1 )
    {
      v55 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not resume sandbox process");
        if ( v55 > 0 )
          v57 = (unsigned __int16)v55 | 0x80070000;
        else
          v57 = v55;
        ExitCode = v57;
        LOBYTE(v56) = 1;
        *(_QWORD *)v99 = &ExitCode;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v56,
          3,
          (unsigned int)": {0}",
          (__int64)v99);
      }
      if ( !v55 )
        goto LABEL_138;
      v58 = 386;
      goto LABEL_82;
    }
    Src[0] = v33;
    Src[1] = hProcess;
    v60 = WaitForMultipleObjectsEx(2u, Src, 0, 0x7530u, 0);
    if ( v60 )
    {
      switch ( v60 )
      {
        case 1u:
          ExitCode = 0;
          LogAdapter::TraceAtLevel<>(2, "Unable to cocreate in sandbox process, checking for possible exit codes");
          if ( GetExitCodeProcess(hProcess, &ExitCode) )
          {
            v6 = ExitCode;
            if ( ExitCode == 259 )
            {
              v6 = -2147418113;
              v99[0] = -2147418113;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  LogAdapter::g_Logger,
                  0,
                  3,
                  "Sandbox exited but does not report as such");
                *(_QWORD *)v90 = v99;
                LOBYTE(v68) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v68,
                  3,
                  (unsigned int)": {}",
                  (__int64)v90);
              }
              v62 = 410;
            }
            else if ( ExitCode )
            {
              v99[0] = ExitCode;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Sandbox exited with error");
                *(_QWORD *)v90 = v99;
                LOBYTE(v70) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v70,
                  3,
                  (unsigned int)": {}",
                  (__int64)v90);
              }
              if ( (v6 & 0x80000000) == 0 )
                goto LABEL_41;
              v62 = 419;
            }
            else
            {
              v6 = -2147467259;
              v99[0] = -2147467259;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Sandbox exited without errors");
                *(_QWORD *)v90 = v99;
                LOBYTE(v69) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v69,
                  3,
                  (unsigned int)": {}",
                  (__int64)v90);
              }
              v62 = 414;
            }
            goto LABEL_91;
          }
          v55 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not query sandbox exit code");
            if ( v55 > 0 )
              v67 = (unsigned __int16)v55 | 0x80070000;
            else
              v67 = v55;
            v99[0] = v67;
            LOBYTE(v66) = 1;
            *(_QWORD *)v90 = v99;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v66,
              3,
              (unsigned int)": {0}",
              (__int64)v90);
          }
          if ( !v55 )
            goto LABEL_138;
          v58 = 405;
          break;
        case 0x102u:
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Waiting for sandbox timed out");
            *(_QWORD *)v99 = &ExitCode;
            ExitCode = -2147023436;
            LOBYTE(v65) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v65,
              3,
              (unsigned int)": {0}",
              (__int64)v99);
          }
          v59 = 1460;
          v58 = 425;
          goto LABEL_83;
        case 0xFFFFFFFF:
          v55 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Waiting for sandbox failed");
            if ( v55 > 0 )
              v64 = (unsigned __int16)v55 | 0x80070000;
            else
              v64 = v55;
            ExitCode = v64;
            LOBYTE(v63) = 1;
            *(_QWORD *)v99 = &ExitCode;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v63,
              3,
              (unsigned int)": {0}",
              (__int64)v99);
          }
          if ( !v55 )
            goto LABEL_138;
          v58 = 429;
          break;
        default:
          v6 = -2147418113;
          ExitCode = -2147418113;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Unexpected while waiting for sandbox");
            *(_QWORD *)v99 = &ExitCode;
            LOBYTE(v61) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v61,
              3,
              (unsigned int)": {}",
              (__int64)v99);
          }
          v62 = 433;
LABEL_91:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v62,
            (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
            (const char *)v6,
            dwDesiredAccess);
LABEL_41:
          if ( hProcess )
            TerminateProcess(hProcess, 0x80080005);
          goto LABEL_155;
      }
LABEL_82:
      v59 = (unsigned int)v55;
LABEL_83:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v58,
             (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
             (const char *)v59,
             dwDesiredAccess);
      goto LABEL_41;
    }
    v71 = (void **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v98);
    v73 = UnmarshalFactory((char *)lpBaseAddress + 28, *((unsigned int *)lpBaseAddress + 6), v72, v71);
    v6 = v73;
    if ( v73 >= 0 )
    {
      v75 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, void **))(*(_QWORD *)v98 + 24LL))(
              v98,
              0,
              &IID_IWimFileFetcherSandbox,
              a5);
      v6 = v75;
      if ( v75 >= 0 )
        goto LABEL_162;
      v99[0] = v75;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not create proxy to sandbox");
        *(_QWORD *)v90 = v99;
        LOBYTE(v76) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v76,
          3,
          (unsigned int)": {}",
          (__int64)v90);
      }
      v62 = 446;
    }
    else
    {
      v99[0] = v73;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not unmarshal sandbox factory");
        *(_QWORD *)v90 = v99;
        LOBYTE(v74) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v74,
          3,
          (unsigned int)": {}",
          (__int64)v90);
      }
      v62 = 444;
    }
    goto LABEL_91;
  }
  LastError = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not get self module file path");
    if ( LastError > 0 )
      v81 = (unsigned __int16)LastError | 0x80070000;
    else
      v81 = LastError;
    v99[0] = v81;
    LOBYTE(v80) = 1;
    *(_QWORD *)v90 = v99;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v80,
      3,
      (unsigned int)": {0}",
      (__int64)v90);
  }
  if ( LastError )
  {
    v20 = 294;
    goto LABEL_154;
  }
LABEL_162:
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v98);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hSourceHandle);
  if ( lpBaseAddress )
  {
    if ( !UnmapViewOfFile(lpBaseAddress) )
    {
      GetLastError();
      __fastfail(7u);
    }
    lpBaseAddress = 0;
  }
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v88);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hThread);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hProcess);
  if ( v95 )
  {
    Windows::Detail::CloseWithRtlFreeSid(v95, v84);
    v95 = 0;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v91);
  return 0;
}

```

## disassembly

```asm
0x180095e58  push    rbp
0x180095e5a  push    rbx
0x180095e5b  push    rsi
0x180095e5c  push    rdi
0x180095e5d  push    r12
0x180095e5f  push    r13
0x180095e61  push    r14
0x180095e63  push    r15
0x180095e65  lea     rbp, [rsp-1E8h]
0x180095e6d  sub     rsp, 2E8h
0x180095e74  mov     rax, cs:__security_cookie
0x180095e7b  xor     rax, rsp
0x180095e7e  mov     [rbp+220h+var_50], rax
0x180095e85  mov     r14, [rbp+220h+arg_20]
0x180095e8c  xor     r12d, r12d
0x180095e8f  mov     [rsp+320h+var_2B8], r12
0x180095e94  mov     rsi, rcx
0x180095e97  mov     [rbp+220h+var_298], r12
0x180095e9b  mov     [rbp+220h+hProcess], r12
0x180095e9f  mov     [rsp+320h+hThread], r12
0x180095ea4  mov     [rsp+320h+var_2D0], r12
0x180095ea9  mov     [rsp+320h+lpBaseAddress], r12
0x180095eae  mov     [rsp+320h+hSourceHandle], r12
0x180095eb3  mov     [rbp+220h+var_280], r12
0x180095eb7  test    r14, r14
0x180095eba  jnz     short loc_180095F30
0x180095ebc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180095ec3  mov     edi, 80004003h
0x180095ec8  mov     [rbp+220h+ExitCode], edi
0x180095ecb  test    rcx, rcx
0x180095ece  jz      short loc_180095F10
0x180095ed0  lea     ebx, [r14+3]
0x180095ed4  xor     edx, edx
0x180095ed6  mov     r8d, ebx
0x180095ed9  lea     r9, aNoObjectInstan; "No object instance result specified"
0x180095ee0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180095ee5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180095eec  lea     rax, [rbp+220h+ExitCode]
0x180095ef0  mov     [rsp+320h+var_2B0], rax
0x180095ef5  lea     r9, asc_1802EE7AC; ": {}"
0x180095efc  lea     rax, [rsp+320h+var_2B0]
0x180095f01  mov     r8d, ebx
0x180095f04  mov     dl, 1
0x180095f06  mov     qword ptr [rsp+320h+dwDesiredAccess], rax; int
0x180095f0b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180095f10  mov     edx, 109h; void *
0x180095f15  mov     r9d, edi; char *
0x180095f18  mov     rcx, [rbp+228h]; this
0x180095f1f  lea     r8, aOnecoreBaseCbs_150; "onecore\\base\\cbs\\core\\sandboxhelper"...
0x180095f26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095f2b  jmp     loc_180096D12
0x180095f30  lea     rcx, [rbp+220h+Src]; this
0x180095f34  mov     [r14], r12
0x180095f37  mov     [rbp+220h+Src], rsi
0x180095f3b  mov     byte ptr [rbp+220h+Src+8], r12b
0x180095f3f  call    ?Impersonate@NestableImpersonator@@QEAAJXZ; NestableImpersonator::Impersonate(void)
0x180095f44  mov     edi, eax
0x180095f46  test    eax, eax
0x180095f48  jns     short loc_180095FC3
0x180095f4a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180095f51  mov     [rbp+220h+ExitCode], eax
0x180095f54  test    rcx, rcx
0x180095f57  jz      short loc_180095F9A
0x180095f59  mov     ebx, 3
0x180095f5e  lea     r9, aFailedToImpers_3; "Failed to impersonate"
0x180095f65  mov     r8d, ebx
0x180095f68  xor     edx, edx
0x180095f6a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180095f6f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180095f76  lea     rax, [rbp+220h+ExitCode]
0x180095f7a  mov     [rsp+320h+var_2B0], rax
0x180095f7f  lea     r9, asc_1802EE7AC; ": {}"
0x180095f86  lea     rax, [rsp+320h+var_2B0]
0x180095f8b  mov     r8d, ebx
0x180095f8e  mov     dl, 1
0x180095f90  mov     qword ptr [rsp+320h+dwDesiredAccess], rax; int
0x180095f95  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180095f9a  mov     edx, 10Fh; void *
0x180095f9f  mov     rcx, [rbp+228h]; this
0x180095fa6  lea     r8, aOnecoreBaseCbs_150; "onecore\\base\\cbs\\core\\sandboxhelper"...
0x180095fad  mov     r9d, edi; char *
0x180095fb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095fb5  lea     rcx, [rbp+220h+Src]; this
0x180095fb9  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x180095fbe  jmp     loc_180096D12
0x180095fc3  lea     rcx, [rbp+220h+var_298]
0x180095fc7  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x180095fcc  mov     rdx, rax
0x180095fcf  call    GetAppContainerSidFromName
0x180095fd4  mov     edi, eax
0x180095fd6  test    eax, eax
0x180095fd8  jns     short loc_180096034
0x180095fda  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180095fe1  mov     [rbp+220h+ExitCode], eax
0x180095fe4  test    rcx, rcx
0x180095fe7  jz      short loc_18009602A
0x180095fe9  mov     ebx, 3
0x180095fee  lea     r9, aCouldNotGetApp; "Could not get AppContainer SID"
0x180095ff5  mov     r8d, ebx
0x180095ff8  xor     edx, edx
0x180095ffa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180095fff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180096006  lea     rax, [rbp+220h+ExitCode]
0x18009600a  mov     [rsp+320h+var_2B0], rax
0x18009600f  lea     r9, asc_1802EE7AC; ": {}"
0x180096016  lea     rax, [rsp+320h+var_2B0]
0x18009601b  mov     r8d, ebx
0x18009601e  mov     dl, 1
0x180096020  mov     qword ptr [rsp+320h+dwDesiredAccess], rax
0x180096025  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009602a  mov     edx, 112h
0x18009602f  jmp     loc_180095F9F
0x180096034  lea     rcx, [rbp+220h+Src]; this
0x180096038  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x18009603d  xor     edx, edx; Val
0x18009603f  lea     rcx, [rbp+220h+Filename]; void *
0x180096043  mov     r8d, 20Ah; Size
0x180096049  call    memset_0
0x18009604e  lea     r8, [rsp+320h+phModule]; phModule
0x180096053  mov     [rsp+320h+phModule], r12
0x180096058  lea     rdx, ?g_bCoCreateInSandboxProcess_ThisModuleMarker@@3HA; lpModuleName
0x18009605f  mov     ecx, 6; dwFlags
0x180096064  call    cs:__imp_GetModuleHandleExW
0x18009606b  nop     dword ptr [rax+rax+00h]
0x180096070  test    eax, eax
0x180096072  jnz     loc_1800960F8
0x180096078  call    cs:__imp_GetLastError
0x18009607f  nop     dword ptr [rax+rax+00h]
0x180096084  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009608b  mov     edi, eax
0x18009608d  test    rcx, rcx
0x180096090  jz      short loc_1800960E6
0x180096092  mov     ebx, 3
0x180096097  lea     r9, aCouldNotGetSel_0; "Could not get self module handle"
0x18009609e  mov     r8d, ebx
0x1800960a1  xor     edx, edx
0x1800960a3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800960a8  test    edi, edi
0x1800960aa  jg      short loc_1800960B0
0x1800960ac  mov     eax, edi
0x1800960ae  jmp     short loc_1800960B8
0x1800960b0  movzx   eax, di
0x1800960b3  or      eax, 80070000h
0x1800960b8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800960bf  lea     r9, a0; ": {0}"
0x1800960c6  mov     [rbp+220h+ExitCode], eax
0x1800960c9  mov     r8d, ebx
0x1800960cc  lea     rax, [rbp+220h+ExitCode]
0x1800960d0  mov     dl, 1
0x1800960d2  mov     [rsp+320h+var_2B0], rax
0x1800960d7  lea     rax, [rsp+320h+var_2B0]
0x1800960dc  mov     qword ptr [rsp+320h+dwDesiredAccess], rax
0x1800960e1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800960e6  test    edi, edi
0x1800960e8  jz      loc_180096D97
0x1800960ee  mov     edx, 121h
0x1800960f3  jmp     loc_180096CFA
0x1800960f8  mov     rcx, [rsp+320h+phModule]; hModule
0x1800960fd  lea     rdx, [rbp+220h+Filename]; lpFilename
0x180096101  mov     ebx, 105h
0x180096106  mov     r8d, ebx; nSize
0x180096109  call    cs:__imp_GetModuleFileNameW
0x180096110  nop     dword ptr [rax+rax+00h]
0x180096115  test    eax, eax
0x180096117  jz      loc_180096C7F
0x18009611d  cmp     eax, ebx
0x18009611f  jnz     short loc_180096136
0x180096121  call    cs:__imp_GetLastError
0x180096128  nop     dword ptr [rax+rax+00h]
0x18009612d  cmp     eax, 7Ah ; 'z'
0x180096130  jz      loc_180096C7F
0x180096136  mov     edx, 5Ch ; '\'; Ch
0x18009613b  lea     rcx, [rbp+220h+Filename]; Str
0x18009613f  call    cs:__imp_wcsrchr
0x180096146  nop     dword ptr [rax+rax+00h]
0x18009614b  test    rax, rax
0x18009614e  jnz     short loc_1800961AD
0x180096150  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180096157  mov     edi, 8000FFFFh
0x18009615c  mov     [rbp+220h+ExitCode], edi
0x18009615f  test    rcx, rcx
0x180096162  jz      short loc_1800961A3
0x180096164  lea     ebx, [rax+3]
0x180096167  xor     edx, edx
0x180096169  mov     r8d, ebx
0x18009616c  lea     r9, aSelfModuleFile; "Self module file path malformed"
0x180096173  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180096178  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009617f  lea     rax, [rbp+220h+ExitCode]
0x180096183  mov     [rsp+320h+var_2B0], rax
0x180096188  lea     r9, asc_1802EE7AC; ": {}"
0x18009618f  lea     rax, [rsp+320h+var_2B0]
0x180096194  mov     r8d, ebx
0x180096197  mov     dl, 1
0x180096199  mov     qword ptr [rsp+320h+dwDesiredAccess], rax
0x18009619e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800961a3  mov     edx, 12Ah
0x1800961a8  jmp     loc_180095F15
0x1800961ad  lea     r8, aTifilefetcherE; "TiFileFetcher.exe"
0x1800961b4  mov     [rax], r12w
0x1800961b8  lea     rdx, [rbp+220h+Filename]
0x1800961bc  lea     rcx, [rsp+320h+var_2B8]
0x1800961c1  call    SczAllocCombinePath2Sz
0x1800961c6  mov     edi, eax
0x1800961c8  test    eax, eax
0x1800961ca  jns     short loc_1800961D9
0x1800961cc  mov     r9d, eax
0x1800961cf  mov     edx, 12Dh
0x1800961d4  jmp     loc_180095F18
0x1800961d9  lea     rcx, [rsp+320h+hThread]
0x1800961de  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1800961e3  lea     rcx, [rbp+220h+hProcess]
0x1800961e7  mov     rbx, rax
0x1800961ea  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1800961ef  mov     r8, [rbp+220h+var_298]
0x1800961f3  mov     r9, rax
0x1800961f6  mov     rdx, [rsp+320h+var_2B8]
0x1800961fb  mov     rcx, rsi
0x1800961fe  mov     qword ptr [rsp+320h+dwDesiredAccess], rbx; int
0x180096203  call    CreateSandboxProcessSuspended
0x180096208  mov     edi, eax
0x18009620a  test    eax, eax
0x18009620c  jns     short loc_180096268
0x18009620e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180096215  mov     [rbp+220h+ExitCode], eax
0x180096218  test    rcx, rcx
0x18009621b  jz      short loc_18009625E
0x18009621d  mov     ebx, 3
0x180096222  lea     r9, aFailedToStartS; "Failed to start sandbox process"
0x180096229  mov     r8d, ebx
0x18009622c  xor     edx, edx
0x18009622e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180096233  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009623a  lea     rax, [rbp+220h+ExitCode]
0x18009623e  mov     [rsp+320h+var_2B0], rax
0x180096243  lea     r9, asc_1802EE7AC; ": {}"
0x18009624a  lea     rax, [rsp+320h+var_2B0]
0x18009624f  mov     r8d, ebx
0x180096252  mov     dl, 1
0x180096254  mov     qword ptr [rsp+320h+dwDesiredAccess], rax
0x180096259  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18009625e  mov     edx, 138h
0x180096263  jmp     loc_180095F15
0x180096268  lea     rcx, [rbp+220h+Src]
0x18009626c  mov     [rbp+220h+Src], r12
0x180096270  mov     [rbp+220h+Src+8], r12
0x180096274  mov     [rbp+220h+TargetHandle], r12
0x180096278  mov     [rsp+320h+var_2B0], r12
0x18009627d  call    ?AllocateSandboxSharedStruct@@YAJPEAV?$AutoHeapBlockPtr@USandboxSharedStruct@@@Windows@@@Z; AllocateSandboxSharedStruct(Windows::AutoHeapBlockPtr<SandboxSharedStruct> *)
0x180096282  mov     edi, eax
0x180096284  test    eax, eax
0x180096286  jns     short loc_1800962CF
0x180096288  mov     r9d, eax; char *
0x18009628b  mov     edx, 149h; void *
0x180096290  mov     rcx, [rbp+228h]; this
0x180096297  lea     r8, aOnecoreBaseCbs_150; "onecore\\base\\cbs\\core\\sandboxhelper"...
0x18009629e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800962a3  lea     rcx, [rbp+220h+Src]
0x1800962a7  call    ?Close@?$AutoPointerAndSizeBase@PEAU_ACL@@V?$AutoHeapBlockPtr@U_ACL@@@Windows@@@Windows@@QEAAXXZ; Windows::AutoPointerAndSizeBase<_ACL *,Windows::AutoHeapBlockPtr<_ACL>>::Close(void)
0x1800962ac  mov     rcx, [rbp+220h+hProcess]; hProcess
0x1800962b0  test    rcx, rcx
0x1800962b3  jz      loc_180096D12
0x1800962b9  mov     edx, 80080005h; uExitCode
0x1800962be  call    cs:__imp_TerminateProcess
0x1800962c5  nop     dword ptr [rax+rax+00h]
0x1800962ca  jmp     loc_180096D12
0x1800962cf  xor     r9d, r9d; lpName
0x1800962d2  xor     r8d, r8d; bInitialState
0x1800962d5  xor     ecx, ecx; lpEventAttributes
0x1800962d7  lea     edx, [r9+1]; bManualReset
0x1800962db  call    cs:__imp_CreateEventW
0x1800962e2  nop     dword ptr [rax+rax+00h]
0x1800962e7  mov     rdx, rax
0x1800962ea  lea     rcx, [rsp+320h+hSourceHandle]
0x1800962ef  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800962f4  mov     rbx, [rsp+320h+hSourceHandle]
0x1800962f9  test    rbx, rbx
0x1800962fc  jz      loc_180096B64
0x180096302  call    cs:__imp_GetLastError
0x180096309  nop     dword ptr [rax+rax+00h]
0x18009630e  cmp     eax, 0B7h
0x180096313  jz      loc_180096B64
0x180096319  mov     rdi, [rbp+220h+hProcess]
0x18009631d  call    cs:__imp_GetCurrentProcess
0x180096324  nop     dword ptr [rax+rax+00h]
0x180096329  mov     [rsp+320h+dwOptions], r12d; dwOptions
0x18009632e  lea     r9, [rbp+220h+TargetHandle]; lpTargetHandle
0x180096332  mov     rcx, rax; hSourceProcessHandle
0x180096335  mov     [rsp+320h+bInheritHandle], r12d; bInheritHandle
0x18009633a  mov     r8, rdi; hTargetProcessHandle
0x18009633d  mov     [rsp+320h+dwDesiredAccess], 2; dwDesiredAccess
0x180096345  mov     rdx, rbx; hSourceHandle
0x180096348  call    cs:__imp_DuplicateHandle
0x18009634f  nop     dword ptr [rax+rax+00h]
0x180096354  test    eax, eax
0x180096356  jnz     loc_1800963F2
0x18009635c  call    cs:__imp_GetLastError
0x180096363  nop     dword ptr [rax+rax+00h]
0x180096368  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18009636f  mov     edi, eax
  ... truncated ...
```
