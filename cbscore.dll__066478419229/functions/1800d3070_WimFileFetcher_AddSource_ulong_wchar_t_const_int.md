# WimFileFetcher::AddSource(ulong,wchar_t const *,int *)

- ea: `0x1800d3070`
- end: `0x1800d3938`
- name: `?AddSource@WimFileFetcher@@UEAAJKPEB_WPEAH@Z`
- size: `2248`
- prototype: `__int64 __fastcall(WimFileFetcher *__hidden this, unsigned int, const wchar_t *, int *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180013250`
- `0x180015420`
- `0x180015640`
- `0x18002e280`
- `0x180033f58`
- `0x18003404c`
- `0x18004142c`
- `0x18004a680`
- `0x180055fc8`
- `0x18005eef0`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800d3070`
- `0x1800eb920`
- `0x1800fa80c`
- `0x18010e940`
- `0x1802adb7c`
- `0x1802adfec`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d3273`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d3273`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800d3193`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800d3193`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800d3169`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800d3169`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d3137`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d3137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d344b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d37df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d344b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d37df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d34ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d34ea`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800d3514`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800d3514`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d336c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d336c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d342f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d342f`

## string_xrefs

- `0x1800d3465`: `Could not open sandbox process handle`
- `0x1800d37f9`: `The alternate source path WIM file could not be opened`
- `0x1800d32e2`: `Failed to impersonate`
- `0x1800d30d2`: `No source path specified`
- `0x1800d3898`: `WIM file sources should be specified in the format "wim:<absolute file path>:<image index>"`
- `0x1800d31f4`: `Failed to expand relative path from client`
- `0x1800d371f`: `Failed to add a WIM file as an alternate sources path`
- `0x1800d35d1`: `Failed to communicate WIM file handle to sandbox process`
- `0x1800d32a3`: `Duplicate alternate sources path specifed, it is a duplicate of WIM source number: {}`

## pseudocode

```c
__int64 __fastcall WimFileFetcher::AddSource(RTL_SRWLOCK *this, char a2, const wchar_t *a3, int *a4)
{
  unsigned int v8; // ebx
  int v9; // edx
  RTL_SRWLOCK *v10; // rbx
  int v11; // eax
  __int64 v12; // rdx
  wchar_t *v13; // rax
  unsigned int v14; // r13d
  unsigned __int64 v15; // r9
  signed int v16; // eax
  int v17; // edx
  int v18; // eax
  char *i; // rbx
  __int64 v20; // rcx
  DWORD v21; // eax
  int v22; // eax
  int v23; // edx
  HANDLE FileW; // rax
  HANDLE v25; // r15
  PVOID v26; // rcx
  int v27; // r14d
  int v28; // eax
  int v29; // edx
  void *v30; // rbx
  signed int v31; // ebx
  int v32; // edx
  unsigned int v33; // eax
  __int64 v34; // rdx
  HANDLE CurrentProcess; // rax
  int v36; // edx
  unsigned int v37; // eax
  __int64 v38; // rbx
  int v39; // eax
  int v40; // edx
  unsigned int v41; // edx
  IFileFetcher::FileFetcherSource *v42; // r14
  char *v43; // rcx
  int v44; // eax
  unsigned int v45; // r15d
  unsigned int v46; // edx
  unsigned int v47; // edx
  int v48; // edx
  unsigned int v49; // edx
  signed int LastError; // ebx
  int v52; // edx
  unsigned int v53; // eax
  int v54; // edx
  int dwCreationDisposition; // [rsp+20h] [rbp-59h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-59h]
  IFileFetcher::FileFetcherSource *v57; // [rsp+40h] [rbp-39h] BYREF
  HANDLE hSourceHandle; // [rsp+48h] [rbp-31h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-29h] BYREF
  HANDLE Ptr; // [rsp+58h] [rbp-21h] BYREF
  char v61; // [rsp+60h] [rbp-19h]
  __int64 v62; // [rsp+68h] [rbp-11h] BYREF
  unsigned int v63[2]; // [rsp+70h] [rbp-9h] BYREF
  RTL_SRWLOCK *v64; // [rsp+78h] [rbp-1h] BYREF
  wchar_t *EndPtr; // [rsp+80h] [rbp+7h] BYREF
  int v66; // [rsp+88h] [rbp+Fh] BYREF
  DWORD dwProcessId; // [rsp+8Ch] [rbp+13h] BYREF
  LPCWSTR lpFileName; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( a4 )
    *a4 = 0;
  if ( !a3 )
  {
    v8 = -2147024809;
    dwProcessId = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No source path specified");
      EndPtr = (wchar_t *)&dwProcessId;
      LOBYTE(v9) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)&EndPtr);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return v8;
  }
  v10 = this + 2;
  Str = 0;
  lpFileName = 0;
  v62 = 0;
  AcquireSRWLockExclusive(this + 2);
  v64 = v10;
  v11 = SczAllocFromSz(&Str, a3);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = 406;
LABEL_13:
    v15 = (unsigned int)v11;
LABEL_89:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)v15,
      dwCreationDisposition);
    goto LABEL_90;
  }
  v13 = wcsrchr(Str, 0x3Au);
  if ( !v13 || (*v13 = 0, EndPtr = 0, v14 = wcstoul(v13 + 1, &EndPtr, 10), v14 - 1 > 0xFFFFFFFD) )
  {
    v8 = -2147024809;
    v66 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "WIM file sources should be specified in the format \"wim:<absolute file path>:<image index>\"");
      *(_QWORD *)v63 = &v66;
      LOBYTE(v54) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v54,
        3,
        (unsigned int)": {}",
        (__int64)v63);
    }
    v12 = 417;
    goto LABEL_88;
  }
  v11 = PathPrefix(&Str);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = 421;
    goto LABEL_13;
  }
  v16 = PathExpand((LPWSTR *)&lpFileName, Str);
  v8 = v16;
  if ( v16 < 0 )
  {
    dwProcessId = v16;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expand relative path from client");
      EndPtr = (wchar_t *)&dwProcessId;
      LOBYTE(v17) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v17,
        3,
        (unsigned int)": {}",
        (__int64)&EndPtr);
    }
    v12 = 423;
LABEL_88:
    v15 = v8;
    goto LABEL_89;
  }
  v18 = SczAllocFromSz(&v62, a3);
  v8 = v18;
  if ( v18 < 0 )
  {
    v15 = (unsigned int)v18;
    v12 = 428;
    goto LABEL_89;
  }
  for ( i = 0; i < this[6].Ptr; ++i )
  {
    if ( !(unsigned int)_o__wcsicmp(lpFileName, *(_QWORD *)(*((_QWORD *)this[8].Ptr + (_QWORD)i) + 8LL)) )
    {
      if ( i != (char *)0xFFFFFFFFLL )
      {
        v21 = (_DWORD)i + 1;
        v8 = 985090;
        dwProcessId = v21;
        LogAdapter::TraceAtLevelHr<long,int>(
          v20,
          985090,
          "Duplicate alternate sources path specifed, it is a duplicate of WIM source number: {}",
          &dwProcessId);
        goto LABEL_90;
      }
      break;
    }
  }
  Ptr = this[15].Ptr;
  hSourceHandle = 0;
  v61 = 0;
  v22 = NestableImpersonator::Impersonate((NestableImpersonator *)&Ptr);
  v8 = v22;
  if ( v22 < 0 )
  {
    v66 = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to impersonate");
      v57 = (IFileFetcher::FileFetcherSource *)&v66;
      LOBYTE(v23) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v23,
        3,
        (unsigned int)": {}",
        (__int64)&v57);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)v8,
      dwCreationDisposition);
LABEL_30:
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&Ptr);
LABEL_31:
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hSourceHandle);
LABEL_90:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v64);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v62);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
    return v8;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x48000000u, 0);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
    &hSourceHandle,
    FileW);
  v25 = hSourceHandle;
  if ( (char *)hSourceHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( a4 )
      *a4 = 1;
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "The alternate source path WIM file could not be opened");
      if ( LastError > 0 )
        v53 = (unsigned __int16)LastError | 0x80070000;
      else
        v53 = LastError;
      v66 = v53;
      LOBYTE(v52) = 1;
      *(_QWORD *)v63 = &v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v52,
        3,
        (unsigned int)": {0}",
        (__int64)v63);
    }
    if ( !LastError )
    {
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&Ptr);
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hSourceHandle);
      v8 = 0;
      goto LABEL_90;
    }
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1D1,
           (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
           (const char *)(unsigned int)LastError,
           dwCreationDispositiona);
    goto LABEL_30;
  }
  ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&Ptr);
  v26 = this[1].Ptr;
  v27 = 0;
  dwProcessId = 0;
  v28 = (*(__int64 (__fastcall **)(PVOID, DWORD *))(*(_QWORD *)v26 + 32LL))(v26, &dwProcessId);
  v8 = v28;
  if ( v28 < 0 )
  {
    v66 = v28;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get sandbox process id");
      v57 = (IFileFetcher::FileFetcherSource *)&v66;
      LOBYTE(v29) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v29,
        3,
        (unsigned int)": {}",
        (__int64)&v57);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)v8,
      dwCreationDispositiona);
    goto LABEL_31;
  }
  Ptr = OpenProcess(0x40u, 0, dwProcessId);
  v30 = Ptr;
  if ( !Ptr )
  {
    v31 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Could not open sandbox process handle");
      if ( v31 > 0 )
        v33 = (unsigned __int16)v31 | 0x80070000;
      else
        v33 = v31;
      v66 = v33;
      LOBYTE(v32) = 1;
      v57 = (IFileFetcher::FileFetcherSource *)&v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v32,
        3,
        (unsigned int)": {0}",
        (__int64)&v57);
    }
    if ( v31 )
    {
      v34 = 479;
LABEL_45:
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v34,
             (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
             (const char *)(unsigned int)v31,
             dwCreationDispositiona);
LABEL_46:
      Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&Ptr);
      goto LABEL_31;
    }
    goto LABEL_59;
  }
  EndPtr = 0;
  hSourceHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v25, v30, (LPHANDLE)&EndPtr, 0, 1, 3u) )
  {
    v31 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Could not duplicate WIM file handle into target process");
      if ( v31 > 0 )
        v37 = (unsigned __int16)v31 | 0x80070000;
      else
        v37 = v31;
      v66 = v37;
      LOBYTE(v36) = 1;
      v57 = (IFileFetcher::FileFetcherSource *)&v66;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v36,
        3,
        (unsigned int)": {0}",
        (__int64)&v57);
    }
    if ( v31 )
    {
      v34 = 491;
      goto LABEL_45;
    }
LABEL_59:
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&Ptr);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hSourceHandle);
    v8 = v27;
    goto LABEL_90;
  }
  v38 = v62;
  v39 = (*(__int64 (__fastcall **)(PVOID, __int64, wchar_t *, _QWORD))(*(_QWORD *)this[1].Ptr + 40LL))(
          this[1].Ptr,
          v62,
          EndPtr,
          v14);
  v27 = v39;
  if ( v39 < 0 )
  {
    v66 = v39;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to communicate WIM file handle to sandbox process");
      v57 = (IFileFetcher::FileFetcherSource *)&v66;
      LOBYTE(v40) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v40,
        3,
        (unsigned int)": {}",
        (__int64)&v57);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)(unsigned int)v27,
      dwCreationDispositiona);
    goto LABEL_59;
  }
  v57 = 0;
  if ( !Windows::AutoNewPtr<IFileFetcher::FileFetcherSource>::Allocate<>(&v57) )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
    if ( v57 )
      IFileFetcher::FileFetcherSource::`scalar deleting destructor'(v57, v41);
    goto LABEL_46;
  }
  v42 = v57;
  v43 = (char *)v57 + 8;
  *(_DWORD *)v57 = a2 & 0x20;
  v44 = SczAllocFromSz(v43, v38);
  v45 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)(unsigned int)v44,
      dwCreationDispositiona);
    if ( v42 )
      IFileFetcher::FileFetcherSource::`scalar deleting destructor'(v42, v46);
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&Ptr);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hSourceHandle);
    v8 = v45;
    goto LABEL_90;
  }
  v27 = CCbsPointerArray<CCbsTask::PackageTask *>::SwapOntoBack(&this[3], &v57);
  if ( v27 < 0 )
  {
    (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[1].Ptr + 56LL))(this[1].Ptr, v38);
    v66 = v27;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to add a WIM file as an alternate sources path");
      *(_QWORD *)v63 = &v66;
      LOBYTE(v48) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v48,
        3,
        (unsigned int)": {}",
        (__int64)v63);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
      (const char *)(unsigned int)v27,
      dwCreationDispositiona);
    if ( v57 )
      IFileFetcher::FileFetcherSource::`scalar deleting destructor'(v57, v49);
    goto LABEL_59;
  }
  if ( v57 )
    IFileFetcher::FileFetcherSource::`scalar deleting destructor'(v57, v47);
  Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&Ptr);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hSourceHandle);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v64);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v62);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
  return 0;
}

```

## disassembly

```asm
0x1800d3070  mov     [rsp-8+arg_8], rbx
0x1800d3075  push    rbp
0x1800d3076  push    rsi
0x1800d3077  push    rdi
0x1800d3078  push    r12
0x1800d307a  push    r13
0x1800d307c  push    r14
0x1800d307e  push    r15
0x1800d3080  lea     rbp, [rsp-27h]
0x1800d3085  sub     rsp, 0A0h
0x1800d308c  mov     rax, cs:__security_cookie
0x1800d3093  xor     rax, rsp
0x1800d3096  mov     [rbp+57h+var_38], rax
0x1800d309a  xor     edi, edi
0x1800d309c  mov     r14, r9
0x1800d309f  mov     r15, r8
0x1800d30a2  mov     r12d, edx
0x1800d30a5  mov     rsi, rcx
0x1800d30a8  test    r9, r9
0x1800d30ab  jz      short loc_1800D30B0
0x1800d30ad  mov     [r9], edi
0x1800d30b0  test    r15, r15
0x1800d30b3  jnz     short loc_1800D3124
0x1800d30b5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d30bc  mov     ebx, 80070057h
0x1800d30c1  mov     [rbp+57h+dwProcessId], ebx
0x1800d30c4  test    rcx, rcx
0x1800d30c7  jz      short loc_1800D3107
0x1800d30c9  lea     edi, [r15+3]
0x1800d30cd  xor     edx, edx
0x1800d30cf  mov     r8d, edi
0x1800d30d2  lea     r9, aNoSourcePathSp; "No source path specified"
0x1800d30d9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d30de  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d30e5  lea     rax, [rbp+57h+dwProcessId]
0x1800d30e9  mov     [rbp+57h+EndPtr], rax
0x1800d30ed  lea     r9, asc_1802EE7AC; ": {}"
0x1800d30f4  lea     rax, [rbp+57h+EndPtr]
0x1800d30f8  mov     r8d, edi
0x1800d30fb  mov     dl, 1
0x1800d30fd  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; int
0x1800d3102  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d3107  mov     rcx, [rbp+5Fh]; this
0x1800d310b  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d3112  mov     r9d, ebx; char *
0x1800d3115  mov     edx, 18Bh; void *
0x1800d311a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d311f  jmp     loc_1800D390E
0x1800d3124  lea     rbx, [rcx+10h]
0x1800d3128  mov     [rbp+57h+Str], rdi
0x1800d312c  mov     rcx, rbx; SRWLock
0x1800d312f  mov     [rbp+57h+lpFileName], rdi
0x1800d3133  mov     [rbp+57h+var_68], rdi
0x1800d3137  call    cs:__imp_AcquireSRWLockExclusive
0x1800d313e  nop     dword ptr [rax+rax+00h]
0x1800d3143  mov     rdx, r15
0x1800d3146  mov     [rbp+57h+var_58], rbx
0x1800d314a  lea     rcx, [rbp+57h+Str]
0x1800d314e  call    SczAllocFromSz
0x1800d3153  mov     ebx, eax
0x1800d3155  test    eax, eax
0x1800d3157  jns     short loc_1800D3160
0x1800d3159  mov     edx, 196h
0x1800d315e  jmp     short loc_1800D31C2
0x1800d3160  mov     rcx, [rbp+57h+Str]; Str
0x1800d3164  mov     edx, 3Ah ; ':'; Ch
0x1800d3169  call    cs:__imp_wcsrchr
0x1800d3170  nop     dword ptr [rax+rax+00h]
0x1800d3175  test    rax, rax
0x1800d3178  jz      loc_1800D387F
0x1800d317e  lea     rcx, [rax+2]; String
0x1800d3182  mov     [rax], di
0x1800d3185  mov     r8d, 0Ah; Radix
0x1800d318b  mov     [rbp+57h+EndPtr], rdi
0x1800d318f  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800d3193  call    cs:__imp_wcstoul
0x1800d319a  nop     dword ptr [rax+rax+00h]
0x1800d319f  mov     r13d, eax
0x1800d31a2  lea     ecx, [rax-1]
0x1800d31a5  cmp     ecx, 0FFFFFFFDh
0x1800d31a8  ja      loc_1800D387F
0x1800d31ae  lea     rcx, [rbp+57h+Str]
0x1800d31b2  call    PathPrefix
0x1800d31b7  mov     ebx, eax
0x1800d31b9  test    eax, eax
0x1800d31bb  jns     short loc_1800D31CA
0x1800d31bd  mov     edx, 1A5h
0x1800d31c2  mov     r9d, eax
0x1800d31c5  jmp     loc_1800D38DA
0x1800d31ca  mov     rdx, [rbp+57h+Str]
0x1800d31ce  lea     rcx, [rbp+57h+lpFileName]
0x1800d31d2  mov     edi, 3
0x1800d31d7  mov     r8d, edi
0x1800d31da  call    PathExpand
0x1800d31df  mov     ebx, eax
0x1800d31e1  test    eax, eax
0x1800d31e3  jns     short loc_1800D3238
0x1800d31e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d31ec  mov     [rbp+57h+dwProcessId], eax
0x1800d31ef  test    rcx, rcx
0x1800d31f2  jz      short loc_1800D322E
0x1800d31f4  lea     r9, aFailedToExpand_1; "Failed to expand relative path from cli"...
0x1800d31fb  mov     r8d, edi
0x1800d31fe  xor     edx, edx
0x1800d3200  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d3205  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d320c  lea     rax, [rbp+57h+dwProcessId]
0x1800d3210  mov     [rbp+57h+EndPtr], rax
0x1800d3214  lea     r9, asc_1802EE7AC; ": {}"
0x1800d321b  lea     rax, [rbp+57h+EndPtr]
0x1800d321f  mov     r8d, edi
0x1800d3222  mov     dl, 1
0x1800d3224  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800d3229  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d322e  mov     edx, 1A7h
0x1800d3233  jmp     loc_1800D38D7
0x1800d3238  mov     rdx, r15
0x1800d323b  lea     rcx, [rbp+57h+var_68]
0x1800d323f  call    SczAllocFromSz
0x1800d3244  xor     r15d, r15d
0x1800d3247  mov     ebx, eax
0x1800d3249  test    eax, eax
0x1800d324b  jns     short loc_1800D325A
0x1800d324d  mov     r9d, eax
0x1800d3250  mov     edx, 1ACh
0x1800d3255  jmp     loc_1800D38DA
0x1800d325a  mov     rbx, r15
0x1800d325d  cmp     rbx, [rsi+30h]
0x1800d3261  jnb     short loc_1800D32B4
0x1800d3263  mov     rax, [rsi+40h]
0x1800d3267  mov     rcx, [rbp+57h+lpFileName]
0x1800d326b  mov     rdx, [rax+rbx*8]
0x1800d326f  mov     rdx, [rdx+8]
0x1800d3273  call    cs:__imp__o__wcsicmp
0x1800d327a  nop     dword ptr [rax+rax+00h]
0x1800d327f  test    eax, eax
0x1800d3281  jz      short loc_1800D3288
0x1800d3283  inc     rbx
0x1800d3286  jmp     short loc_1800D325D
0x1800d3288  mov     eax, 0FFFFFFFFh
0x1800d328d  cmp     rbx, rax
0x1800d3290  jz      short loc_1800D32B4
0x1800d3292  lea     eax, [rbx+1]
0x1800d3295  mov     ebx, 0F0802h
0x1800d329a  mov     edx, ebx
0x1800d329c  mov     [rbp+57h+dwProcessId], eax
0x1800d329f  lea     r9, [rbp+57h+dwProcessId]
0x1800d32a3  lea     r8, aDuplicateAlter; "Duplicate alternate sources path specif"...
0x1800d32aa  call    ??$TraceAtLevelHr@JH@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBH@Z; LogAdapter::TraceAtLevelHr<long,int>(LogAdapter::LogLevel,long,char const * const,int const &)
0x1800d32af  jmp     loc_1800D38EA
0x1800d32b4  mov     rax, [rsi+78h]
0x1800d32b8  lea     rcx, [rbp+57h+var_78]; this
0x1800d32bc  mov     [rbp+57h+var_78], rax
0x1800d32c0  mov     [rbp+57h+hSourceHandle], r15
0x1800d32c4  mov     [rbp+57h+var_70], r15b
0x1800d32c8  call    ?Impersonate@NestableImpersonator@@QEAAJXZ; NestableImpersonator::Impersonate(void)
0x1800d32cd  mov     ebx, eax
0x1800d32cf  test    eax, eax
0x1800d32d1  jns     short loc_1800D334B
0x1800d32d3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d32da  mov     [rbp+57h+var_48], eax
0x1800d32dd  test    rcx, rcx
0x1800d32e0  jz      short loc_1800D331C
0x1800d32e2  lea     r9, aFailedToImpers_3; "Failed to impersonate"
0x1800d32e9  mov     r8d, edi
0x1800d32ec  xor     edx, edx
0x1800d32ee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d32f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d32fa  lea     rax, [rbp+57h+var_48]
0x1800d32fe  mov     [rbp+57h+var_90], rax
0x1800d3302  lea     r9, asc_1802EE7AC; ": {}"
0x1800d3309  lea     rax, [rbp+57h+var_90]
0x1800d330d  mov     r8d, edi
0x1800d3310  mov     dl, 1
0x1800d3312  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; int
0x1800d3317  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d331c  mov     rcx, [rbp+5Fh]; this
0x1800d3320  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d3327  mov     r9d, ebx; char *
0x1800d332a  mov     edx, 1C0h; void *
0x1800d332f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3334  lea     rcx, [rbp+57h+var_78]; this
0x1800d3338  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x1800d333d  lea     rcx, [rbp+57h+hSourceHandle]
0x1800d3341  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800d3346  jmp     loc_1800D38EA
0x1800d334b  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800d334f  xor     r9d, r9d; lpSecurityAttributes
0x1800d3352  mov     [rsp+0D0h+hTemplateFile], r15; hTemplateFile
0x1800d3357  mov     edx, 80000000h; dwDesiredAccess
0x1800d335c  mov     [rsp+0D0h+dwFlagsAndAttributes], 48000000h; dwFlagsAndAttributes
0x1800d3364  mov     [rsp+0D0h+dwCreationDisposition], edi; dwCreationDisposition
0x1800d3368  lea     r8d, [r9+1]; dwShareMode
0x1800d336c  call    cs:__imp_CreateFileW
0x1800d3373  nop     dword ptr [rax+rax+00h]
0x1800d3378  mov     rdx, rax
0x1800d337b  lea     rcx, [rbp+57h+hSourceHandle]
0x1800d337f  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x1800d3384  mov     r15, [rbp+57h+hSourceHandle]
0x1800d3388  lea     rax, [r15-1]
0x1800d338c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d3390  ja      loc_1800D37D3
0x1800d3396  lea     rcx, [rbp+57h+var_78]; this
0x1800d339a  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x1800d339f  mov     rcx, [rsi+8]
0x1800d33a3  lea     rdx, [rbp+57h+dwProcessId]
0x1800d33a7  xor     r14d, r14d
0x1800d33aa  mov     [rbp+57h+dwProcessId], r14d
0x1800d33ae  mov     rax, [rcx]
0x1800d33b1  mov     rax, [rax+20h]
0x1800d33b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d33ba  mov     ebx, eax
0x1800d33bc  test    eax, eax
0x1800d33be  jns     short loc_1800D3426
0x1800d33c0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d33c7  mov     [rbp+57h+var_48], eax
0x1800d33ca  test    rcx, rcx
0x1800d33cd  jz      short loc_1800D3409
0x1800d33cf  lea     r9, aFailedToGetSan; "Failed to get sandbox process id"
0x1800d33d6  mov     r8d, edi
0x1800d33d9  xor     edx, edx
0x1800d33db  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d33e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d33e7  lea     rax, [rbp+57h+var_48]
0x1800d33eb  mov     [rbp+57h+var_90], rax
0x1800d33ef  lea     r9, asc_1802EE7AC; ": {}"
0x1800d33f6  lea     rax, [rbp+57h+var_90]
0x1800d33fa  mov     r8d, edi
0x1800d33fd  mov     dl, 1
0x1800d33ff  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; int
0x1800d3404  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d3409  mov     rcx, [rbp+5Fh]; this
0x1800d340d  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d3414  mov     r9d, ebx; char *
0x1800d3417  mov     edx, 1DAh; void *
0x1800d341c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3421  jmp     loc_1800D333D
0x1800d3426  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x1800d342a  xor     edx, edx; bInheritHandle
0x1800d342c  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800d342f  call    cs:__imp_OpenProcess
0x1800d3436  nop     dword ptr [rax+rax+00h]
0x1800d343b  mov     [rbp+57h+var_78], rax
0x1800d343f  mov     rbx, rax
0x1800d3442  test    rax, rax
0x1800d3445  jnz     loc_1800D34E2
0x1800d344b  call    cs:__imp_GetLastError
0x1800d3452  nop     dword ptr [rax+rax+00h]
0x1800d3457  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d345e  mov     ebx, eax
0x1800d3460  test    rcx, rcx
0x1800d3463  jz      short loc_1800D34B2
0x1800d3465  lea     r9, aCouldNotOpenSa; "Could not open sandbox process handle"
0x1800d346c  mov     r8d, edi
0x1800d346f  xor     edx, edx
0x1800d3471  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d3476  test    ebx, ebx
0x1800d3478  jg      short loc_1800D347E
0x1800d347a  mov     eax, ebx
0x1800d347c  jmp     short loc_1800D3486
0x1800d347e  movzx   eax, bx
0x1800d3481  or      eax, 80070000h
0x1800d3486  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d348d  lea     r9, a0; ": {0}"
0x1800d3494  mov     [rbp+57h+var_48], eax
0x1800d3497  mov     r8d, edi
0x1800d349a  lea     rax, [rbp+57h+var_48]
0x1800d349e  mov     dl, 1
0x1800d34a0  mov     [rbp+57h+var_90], rax
0x1800d34a4  lea     rax, [rbp+57h+var_90]
0x1800d34a8  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned int
0x1800d34ad  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d34b2  test    ebx, ebx
0x1800d34b4  jz      loc_1800D3623
0x1800d34ba  mov     edx, 1DFh; void *
0x1800d34bf  mov     rcx, [rbp+5Fh]; this
0x1800d34c3  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d34ca  mov     r9d, ebx; char *
0x1800d34cd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d34d2  mov     ebx, eax
0x1800d34d4  lea     rcx, [rbp+57h+var_78]
0x1800d34d8  call    ?Close@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800d34dd  jmp     loc_1800D333D
0x1800d34e2  mov     [rbp+57h+EndPtr], r14
0x1800d34e6  mov     [rbp+57h+hSourceHandle], r14
0x1800d34ea  call    cs:__imp_GetCurrentProcess
0x1800d34f1  nop     dword ptr [rax+rax+00h]
0x1800d34f6  mov     dword ptr [rsp+0D0h+hTemplateFile], edi; dwOptions
0x1800d34fa  lea     r9, [rbp+57h+EndPtr]; lpTargetHandle
0x1800d34fe  mov     rcx, rax; hSourceProcessHandle
0x1800d3501  mov     [rsp+0D0h+dwFlagsAndAttributes], 1; bInheritHandle
0x1800d3509  mov     r8, rbx; hTargetProcessHandle
0x1800d350c  mov     [rsp+0D0h+dwCreationDisposition], r14d; int
0x1800d3511  mov     rdx, r15; hSourceHandle
0x1800d3514  call    cs:__imp_DuplicateHandle
0x1800d351b  nop     dword ptr [rax+rax+00h]
0x1800d3520  test    eax, eax
0x1800d3522  jnz     short loc_1800D359D
0x1800d3524  call    cs:__imp_GetLastError
0x1800d352b  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
