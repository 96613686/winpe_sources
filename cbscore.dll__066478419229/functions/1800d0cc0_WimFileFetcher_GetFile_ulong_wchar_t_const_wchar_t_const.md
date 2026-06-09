# WimFileFetcher::GetFile(ulong,wchar_t const *,wchar_t const *)

- ea: `0x1800d0cc0`
- end: `0x1800d12fa`
- name: `?GetFile@WimFileFetcher@@UEAAJKPEB_W0@Z`
- size: `1594`
- prototype: `__int64 __fastcall(WimFileFetcher *__hidden this, unsigned int, const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000b46c`
- `0x180013250`
- `0x180016d40`
- `0x18002e280`
- `0x180033f58`
- `0x18003404c`
- `0x180042448`
- `0x180057c28`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800d0cc0`
- `0x1800eb920`
- `0x1800ed7f8`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800d0f2a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800d0f2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d0ddb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d0ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d109d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d109d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1230`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d1158`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d1158`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800d1220`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800d1220`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800d1089`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800d1089`

## string_xrefs

- `0x1800d124a`: `Failed to move sandboxed file`
- `0x1800d1191`: `Could not assert exclusive access to the file found in the sandbox`
- `0x1800d10bc`: `Failed to set sandboxed file access rights`
- `0x1800d0d14`: `No file path specified`
- `0x1800d0e78`: `Failed to impersonate`
- `0x1800d0d88`: `No target path specified`
- `0x1800d0f6b`: `Failed to create file working directory subdirectories`

## pseudocode

```c
__int64 __fastcall WimFileFetcher::GetFile(RTL_SRWLOCK *this, int a2, const wchar_t *a3, const wchar_t *a4)
{
  unsigned int v8; // edi
  int v9; // edx
  __int64 v10; // rdx
  int v11; // edx
  RTL_SRWLOCK *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  int v17; // edx
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  int v20; // eax
  wchar_t *v21; // rbx
  wchar_t *v22; // rax
  wchar_t *v23; // r14
  int Directory; // eax
  int v25; // edx
  int v26; // eax
  int v27; // edx
  __int64 v28; // rax
  int v29; // eax
  const WCHAR *v30; // rdi
  signed int LastError; // ebx
  int v32; // edx
  unsigned int v33; // eax
  signed int v34; // ebx
  int v35; // edx
  unsigned int v36; // eax
  __int64 v37; // rdx
  int v38; // edx
  unsigned int v39; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-39h]
  unsigned int v43[2]; // [rsp+40h] [rbp-19h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-11h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v46[2]; // [rsp+58h] [rbp-1h] BYREF
  char v47; // [rsp+60h] [rbp+7h]
  __int64 v48; // [rsp+68h] [rbp+Fh] BYREF
  RTL_SRWLOCK *v49; // [rsp+70h] [rbp+17h] BYREF
  int v50; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( a3 )
  {
    if ( !a4 )
    {
      v8 = -2147024809;
      v50 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No target path specified");
        Str = (wchar_t *)&v50;
        LOBYTE(v11) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)&Str);
      }
      v10 = 762;
      goto LABEL_5;
    }
    v12 = this + 2;
    Str = 0;
    v48 = 0;
    AcquireSRWLockShared(this + 2);
    v49 = v12;
    if ( (a2 & 0xFFFFFFEE) != 0 )
    {
      v8 = -2147024809;
      v13 = 770;
      v14 = 2147942487LL;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
        (const char *)v14,
        dwCreationDisposition);
      goto LABEL_69;
    }
    if ( (a2 & 1) != 0 )
    {
      v8 = -2147024894;
LABEL_69:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v49);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v48);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&Str);
      return v8;
    }
    v15 = SczAllocConcat2Sz(&v48, L"Windows\\", a3);
    v8 = v15;
    if ( v15 < 0 )
    {
      v14 = (unsigned int)v15;
      v13 = 782;
      goto LABEL_16;
    }
    *(RTL_SRWLOCK *)v46 = this[15];
    v47 = 0;
    v16 = NestableImpersonator::Impersonate((NestableImpersonator *)v46);
    v8 = v16;
    if ( v16 < 0 )
    {
      v50 = v16;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to impersonate");
        *(_QWORD *)v43 = &v50;
        LOBYTE(v17) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v17,
          3,
          (unsigned int)": {}",
          (__int64)v43);
      }
      v18 = 787;
LABEL_21:
      v19 = v8;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
        (const char *)v19,
        dwCreationDisposition);
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)v46);
      goto LABEL_69;
    }
    v20 = SczAllocConcat2Sz(&Str, this[11].Ptr, a4);
    v8 = v20;
    if ( v20 < 0 )
    {
      v19 = (unsigned int)v20;
      v18 = 790;
      goto LABEL_22;
    }
    v21 = Str;
    if ( (a2 & 0x10) != 0 && (unsigned int)DoesFileExist(Str, 0) )
    {
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)v46);
LABEL_68:
      v8 = 0;
      goto LABEL_69;
    }
    v22 = wcsrchr(v21, 0x5Cu);
    v23 = v22;
    if ( v22 )
    {
      *v22 = 0;
      Directory = RecursivelyCreateDirectory(v21, 0);
      v8 = Directory;
      if ( Directory < 0 )
      {
        v50 = Directory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to create file working directory subdirectories");
          *(_QWORD *)v43 = &v50;
          LOBYTE(v25) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v25,
            3,
            (unsigned int)": {}",
            (__int64)v43);
        }
        v18 = 804;
        goto LABEL_21;
      }
      *v23 = 92;
    }
    ImpersonatorBase::Unimpersonate((ImpersonatorBase *)v46);
    v26 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[1].Ptr + 48LL))(this[1].Ptr, v48);
    v8 = v26;
    if ( v26 < 0 )
    {
      v50 = v26;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to GetFile from WIM sandbox process");
        *(_QWORD *)v43 = &v50;
        LOBYTE(v27) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v27,
          3,
          (unsigned int)": {}",
          (__int64)v43);
      }
      v14 = v8;
      v13 = 809;
      goto LABEL_16;
    }
    lpFileName = 0;
    v28 = FileFromPath(v48);
    v29 = SczAllocConcat2Sz(&lpFileName, this[12].Ptr, v28);
    v8 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x331,
        (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
        (const char *)(unsigned int)v29,
        dwCreationDisposition);
LABEL_40:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      goto LABEL_69;
    }
    v30 = lpFileName;
    if ( !SetFileSecurityW(lpFileName, 0x17u, this[13].Ptr) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set sandboxed file access rights");
        if ( LastError > 0 )
          v33 = (unsigned __int16)LastError | 0x80070000;
        else
          v33 = LastError;
        v50 = v33;
        LOBYTE(v32) = 1;
        *(_QWORD *)v43 = &v50;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v32,
          3,
          (unsigned int)": {0}",
          (__int64)v43);
      }
      if ( LastError )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x339,
               (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
               (const char *)(unsigned int)LastError,
               dwCreationDisposition);
        goto LABEL_40;
      }
LABEL_67:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      goto LABEL_68;
    }
    *(_QWORD *)v43 = CreateFileW(v30, 0x80000000, 0, 0, 3u, 0x48000000u, 0);
    if ( ((*(_QWORD *)v43 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v43);
      if ( !MoveFileExW(v30, v21, 0) )
      {
        v34 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to move sandboxed file");
          if ( v34 > 0 )
            v39 = (unsigned __int16)v34 | 0x80070000;
          else
            v39 = v34;
          v50 = v39;
          LOBYTE(v38) = 1;
          *(_QWORD *)v46 = &v50;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v38,
            3,
            (unsigned int)": {0}",
            (__int64)v46);
        }
        if ( v34 )
        {
          v37 = 844;
          goto LABEL_57;
        }
      }
    }
    else
    {
      v34 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Could not assert exclusive access to the file found in the sandbox");
        if ( v34 > 0 )
          v36 = (unsigned __int16)v34 | 0x80070000;
        else
          v36 = v34;
        v50 = v36;
        LOBYTE(v35) = 1;
        *(_QWORD *)v46 = &v50;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v35,
          3,
          (unsigned int)": {0}",
          (__int64)v46);
      }
      if ( v34 )
      {
        v37 = 840;
LABEL_57:
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v37,
               (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
               (const char *)(unsigned int)v34,
               dwCreationDispositiona);
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v43);
        goto LABEL_40;
      }
    }
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v43);
    goto LABEL_67;
  }
  v8 = -2147024809;
  v50 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No file path specified");
    Str = (wchar_t *)&v50;
    LOBYTE(v9) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v9,
      3,
      (unsigned int)": {}",
      (__int64)&Str);
  }
  v10 = 761;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\cbs\\core\\filefetcher.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return v8;
}

```

## disassembly

```asm
0x1800d0cc0  mov     [rsp-8+arg_8], rbx
0x1800d0cc5  push    rbp
0x1800d0cc6  push    rsi
0x1800d0cc7  push    rdi
0x1800d0cc8  push    r14
0x1800d0cca  push    r15
0x1800d0ccc  lea     rbp, [rsp-37h]
0x1800d0cd1  sub     rsp, 90h
0x1800d0cd8  mov     rax, cs:__security_cookie
0x1800d0cdf  xor     rax, rsp
0x1800d0ce2  mov     [rbp+57h+var_30], rax
0x1800d0ce6  mov     r15, r9
0x1800d0ce9  mov     rdi, r8
0x1800d0cec  mov     r14d, edx
0x1800d0cef  mov     rsi, rcx
0x1800d0cf2  test    r8, r8
0x1800d0cf5  jnz     short loc_1800D0D66
0x1800d0cf7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0cfe  mov     edi, 80070057h
0x1800d0d03  mov     [rbp+57h+var_38], edi
0x1800d0d06  test    rcx, rcx
0x1800d0d09  jz      short loc_1800D0D49
0x1800d0d0b  lea     esi, [r8+3]
0x1800d0d0f  xor     edx, edx
0x1800d0d11  mov     r8d, esi
0x1800d0d14  lea     r9, aNoFilePathSpec; "No file path specified"
0x1800d0d1b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d0d20  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0d27  lea     rax, [rbp+57h+var_38]
0x1800d0d2b  mov     [rbp+57h+Str], rax
0x1800d0d2f  lea     r9, asc_1802EE7AC; ": {}"
0x1800d0d36  lea     rax, [rbp+57h+Str]
0x1800d0d3a  mov     r8d, esi
0x1800d0d3d  mov     dl, 1
0x1800d0d3f  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x1800d0d44  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d0d49  mov     edx, 2F9h; void *
0x1800d0d4e  mov     rcx, [rbp+5Fh]; this
0x1800d0d52  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d0d59  mov     r9d, edi; char *
0x1800d0d5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0d61  jmp     loc_1800D12D4
0x1800d0d66  test    r15, r15
0x1800d0d69  jnz     short loc_1800D0DC4
0x1800d0d6b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0d72  mov     edi, 80070057h
0x1800d0d77  mov     [rbp+57h+var_38], edi
0x1800d0d7a  test    rcx, rcx
0x1800d0d7d  jz      short loc_1800D0DBD
0x1800d0d7f  lea     esi, [r15+3]
0x1800d0d83  xor     edx, edx
0x1800d0d85  mov     r8d, esi
0x1800d0d88  lea     r9, aNoTargetPathSp; "No target path specified"
0x1800d0d8f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d0d94  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0d9b  lea     rax, [rbp+57h+var_38]
0x1800d0d9f  mov     [rbp+57h+Str], rax
0x1800d0da3  lea     r9, asc_1802EE7AC; ": {}"
0x1800d0daa  lea     rax, [rbp+57h+Str]
0x1800d0dae  mov     r8d, esi
0x1800d0db1  mov     dl, 1
0x1800d0db3  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800d0db8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d0dbd  mov     edx, 2FAh
0x1800d0dc2  jmp     short loc_1800D0D4E
0x1800d0dc4  lea     rbx, [rcx+10h]
0x1800d0dc8  mov     [rbp+57h+Str], 0
0x1800d0dd0  mov     rcx, rbx; SRWLock
0x1800d0dd3  mov     [rbp+57h+var_48], 0
0x1800d0ddb  call    cs:__imp_AcquireSRWLockShared
0x1800d0de2  nop     dword ptr [rax+rax+00h]
0x1800d0de7  mov     [rbp+57h+var_40], rbx
0x1800d0deb  test    r14d, 0FFFFFFEEh
0x1800d0df2  jz      short loc_1800D0E03
0x1800d0df4  mov     edi, 80070057h
0x1800d0df9  mov     edx, 302h
0x1800d0dfe  mov     r9d, edi
0x1800d0e01  jmp     short loc_1800D0E34
0x1800d0e03  test    r14b, 1
0x1800d0e07  jz      short loc_1800D0E13
0x1800d0e09  mov     edi, 80070002h
0x1800d0e0e  jmp     loc_1800D12B9
0x1800d0e13  mov     r8, rdi
0x1800d0e16  lea     rdx, aWindows; "Windows\\"
0x1800d0e1d  lea     rcx, [rbp+57h+var_48]
0x1800d0e21  call    SczAllocConcat2Sz
0x1800d0e26  mov     edi, eax
0x1800d0e28  test    eax, eax
0x1800d0e2a  jns     short loc_1800D0E49
0x1800d0e2c  mov     r9d, eax; char *
0x1800d0e2f  mov     edx, 30Eh; void *
0x1800d0e34  mov     rcx, [rbp+5Fh]; this
0x1800d0e38  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d0e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0e44  jmp     loc_1800D12B9
0x1800d0e49  mov     rax, [rsi+78h]
0x1800d0e4d  lea     rcx, [rbp+57h+var_58]; this
0x1800d0e51  mov     qword ptr [rbp+57h+var_58], rax
0x1800d0e55  mov     [rbp+57h+var_50], 0
0x1800d0e59  call    ?Impersonate@NestableImpersonator@@QEAAJXZ; NestableImpersonator::Impersonate(void)
0x1800d0e5e  mov     edi, eax
0x1800d0e60  test    eax, eax
0x1800d0e62  jns     short loc_1800D0ED8
0x1800d0e64  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0e6b  mov     [rbp+57h+var_38], eax
0x1800d0e6e  test    rcx, rcx
0x1800d0e71  jz      short loc_1800D0EB2
0x1800d0e73  mov     esi, 3
0x1800d0e78  lea     r9, aFailedToImpers_3; "Failed to impersonate"
0x1800d0e7f  mov     r8d, esi
0x1800d0e82  xor     edx, edx
0x1800d0e84  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d0e89  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0e90  lea     rax, [rbp+57h+var_38]
0x1800d0e94  mov     qword ptr [rbp+57h+var_70], rax
0x1800d0e98  lea     r9, asc_1802EE7AC; ": {}"
0x1800d0e9f  lea     rax, [rbp+57h+var_70]
0x1800d0ea3  mov     r8d, esi
0x1800d0ea6  mov     dl, 1
0x1800d0ea8  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x1800d0ead  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d0eb2  mov     edx, 313h; void *
0x1800d0eb7  mov     r9d, edi; char *
0x1800d0eba  mov     rcx, [rbp+5Fh]; this
0x1800d0ebe  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d0ec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0eca  lea     rcx, [rbp+57h+var_58]; this
0x1800d0ece  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x1800d0ed3  jmp     loc_1800D12B9
0x1800d0ed8  mov     rdx, [rsi+58h]
0x1800d0edc  lea     rcx, [rbp+57h+Str]
0x1800d0ee0  mov     r8, r15
0x1800d0ee3  call    SczAllocConcat2Sz
0x1800d0ee8  mov     edi, eax
0x1800d0eea  test    eax, eax
0x1800d0eec  jns     short loc_1800D0EF8
0x1800d0eee  mov     r9d, eax
0x1800d0ef1  mov     edx, 316h
0x1800d0ef6  jmp     short loc_1800D0EBA
0x1800d0ef8  mov     rbx, [rbp+57h+Str]
0x1800d0efc  test    r14b, 10h
0x1800d0f00  jz      short loc_1800D0F1E
0x1800d0f02  xor     edx, edx
0x1800d0f04  mov     rcx, rbx
0x1800d0f07  call    DoesFileExist
0x1800d0f0c  test    eax, eax
0x1800d0f0e  jz      short loc_1800D0F1E
0x1800d0f10  lea     rcx, [rbp+57h+var_58]; this
0x1800d0f14  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x1800d0f19  jmp     loc_1800D12B7
0x1800d0f1e  mov     r15d, 5Ch ; '\'
0x1800d0f24  mov     rcx, rbx; Str
0x1800d0f27  mov     edx, r15d; Ch
0x1800d0f2a  call    cs:__imp_wcsrchr
0x1800d0f31  nop     dword ptr [rax+rax+00h]
0x1800d0f36  mov     r14, rax
0x1800d0f39  test    rax, rax
0x1800d0f3c  jz      short loc_1800D0FAE
0x1800d0f3e  xor     ecx, ecx
0x1800d0f40  xor     edx, edx
0x1800d0f42  mov     [rax], cx
0x1800d0f45  mov     rcx, rbx
0x1800d0f48  call    RecursivelyCreateDirectory
0x1800d0f4d  mov     edi, eax
0x1800d0f4f  test    eax, eax
0x1800d0f51  jns     short loc_1800D0FAA
0x1800d0f53  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0f5a  mov     [rbp+57h+var_38], eax
0x1800d0f5d  test    rcx, rcx
0x1800d0f60  jz      short loc_1800D0FA0
0x1800d0f62  lea     esi, [r15-59h]
0x1800d0f66  xor     edx, edx
0x1800d0f68  mov     r8d, esi
0x1800d0f6b  lea     r9, aFailedToCreate_65; "Failed to create file working directory"...
0x1800d0f72  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d0f77  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0f7e  lea     rax, [rbp+57h+var_38]
0x1800d0f82  mov     qword ptr [rbp+57h+var_70], rax
0x1800d0f86  lea     r9, asc_1802EE7AC; ": {}"
0x1800d0f8d  lea     rax, [rbp+57h+var_70]
0x1800d0f91  mov     r8d, esi
0x1800d0f94  mov     dl, 1
0x1800d0f96  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800d0f9b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d0fa0  mov     edx, 324h
0x1800d0fa5  jmp     loc_1800D0EB7
0x1800d0faa  mov     [r14], r15w
0x1800d0fae  lea     rcx, [rbp+57h+var_58]; this
0x1800d0fb2  call    ?Unimpersonate@ImpersonatorBase@@QEAAXXZ; ImpersonatorBase::Unimpersonate(void)
0x1800d0fb7  mov     rcx, [rsi+8]
0x1800d0fbb  mov     rdx, [rbp+57h+var_48]
0x1800d0fbf  mov     rax, [rcx]
0x1800d0fc2  mov     rax, [rax+30h]
0x1800d0fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0fcb  mov     edi, eax
0x1800d0fcd  test    eax, eax
0x1800d0fcf  jns     short loc_1800D102C
0x1800d0fd1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0fd8  mov     [rbp+57h+var_38], eax
0x1800d0fdb  test    rcx, rcx
0x1800d0fde  jz      short loc_1800D101F
0x1800d0fe0  mov     esi, 3
0x1800d0fe5  lea     r9, aFailedToGetfil; "Failed to GetFile from WIM sandbox proc"...
0x1800d0fec  mov     r8d, esi
0x1800d0fef  xor     edx, edx
0x1800d0ff1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d0ff6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d0ffd  lea     rax, [rbp+57h+var_38]
0x1800d1001  mov     qword ptr [rbp+57h+var_70], rax
0x1800d1005  lea     r9, asc_1802EE7AC; ": {}"
0x1800d100c  lea     rax, [rbp+57h+var_70]
0x1800d1010  mov     r8d, esi
0x1800d1013  mov     dl, 1
0x1800d1015  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800d101a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d101f  mov     r9d, edi
0x1800d1022  mov     edx, 329h
0x1800d1027  jmp     loc_1800D0E34
0x1800d102c  mov     rcx, [rbp+57h+var_48]
0x1800d1030  mov     [rbp+57h+lpFileName], 0
0x1800d1038  call    FileFromPath
0x1800d103d  mov     rdx, [rsi+60h]
0x1800d1041  lea     rcx, [rbp+57h+lpFileName]
0x1800d1045  mov     r8, rax
0x1800d1048  call    SczAllocConcat2Sz
0x1800d104d  mov     edi, eax
0x1800d104f  test    eax, eax
0x1800d1051  jns     short loc_1800D1079
0x1800d1053  mov     rcx, [rbp+5Fh]; this
0x1800d1057  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d105e  mov     r9d, eax; char *
0x1800d1061  mov     edx, 331h; void *
0x1800d1066  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d106b  lea     rcx, [rbp+57h+lpFileName]
0x1800d106f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800d1074  jmp     loc_1800D12B9
0x1800d1079  mov     rdi, [rbp+57h+lpFileName]
0x1800d107d  mov     edx, 17h; SecurityInformation
0x1800d1082  mov     r8, [rsi+68h]; pSecurityDescriptor
0x1800d1086  mov     rcx, rdi; lpFileName
0x1800d1089  call    cs:__imp_SetFileSecurityW
0x1800d1090  nop     dword ptr [rax+rax+00h]
0x1800d1095  test    eax, eax
0x1800d1097  jnz     loc_1800D1130
0x1800d109d  call    cs:__imp_GetLastError
0x1800d10a4  nop     dword ptr [rax+rax+00h]
0x1800d10a9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d10b0  mov     ebx, eax
0x1800d10b2  test    rcx, rcx
0x1800d10b5  jz      short loc_1800D1109
0x1800d10b7  mov     esi, 3
0x1800d10bc  lea     r9, aFailedToSetSan; "Failed to set sandboxed file access rig"...
0x1800d10c3  mov     r8d, esi
0x1800d10c6  xor     edx, edx
0x1800d10c8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d10cd  test    ebx, ebx
0x1800d10cf  jg      short loc_1800D10D5
0x1800d10d1  mov     eax, ebx
0x1800d10d3  jmp     short loc_1800D10DD
0x1800d10d5  movzx   eax, bx
0x1800d10d8  or      eax, 80070000h
0x1800d10dd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d10e4  lea     r9, a0; ": {0}"
0x1800d10eb  mov     [rbp+57h+var_38], eax
0x1800d10ee  mov     r8d, esi
0x1800d10f1  lea     rax, [rbp+57h+var_38]
0x1800d10f5  mov     dl, 1
0x1800d10f7  mov     qword ptr [rbp+57h+var_70], rax
0x1800d10fb  lea     rax, [rbp+57h+var_70]
0x1800d10ff  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; unsigned int
0x1800d1104  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d1109  test    ebx, ebx
0x1800d110b  jz      loc_1800D12AE
0x1800d1111  mov     rcx, [rbp+5Fh]; this
0x1800d1115  lea     r8, aOnecoreBaseCbs_111; "onecore\\base\\cbs\\core\\filefetcher.c"...
0x1800d111c  mov     r9d, ebx; char *
0x1800d111f  mov     edx, 339h; void *
0x1800d1124  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d1129  mov     edi, eax
0x1800d112b  jmp     loc_1800D106B
0x1800d1130  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1800d1139  mov     esi, 3
0x1800d113e  mov     [rsp+0B0h+dwFlagsAndAttributes], 48000000h; dwFlagsAndAttributes
0x1800d1146  xor     r9d, r9d; lpSecurityAttributes
0x1800d1149  xor     r8d, r8d; dwShareMode
0x1800d114c  mov     [rsp+0B0h+dwCreationDisposition], esi; dwCreationDisposition
0x1800d1150  mov     edx, 80000000h; dwDesiredAccess
0x1800d1155  mov     rcx, rdi; lpFileName
0x1800d1158  call    cs:__imp_CreateFileW
0x1800d115f  nop     dword ptr [rax+rax+00h]
0x1800d1164  mov     qword ptr [rbp+57h+var_70], rax
0x1800d1168  inc     rax
0x1800d116b  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800d1171  jnz     loc_1800D120E
0x1800d1177  call    cs:__imp_GetLastError
0x1800d117e  nop     dword ptr [rax+rax+00h]
0x1800d1183  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d118a  mov     ebx, eax
0x1800d118c  test    rcx, rcx
0x1800d118f  jz      short loc_1800D11DE
  ... truncated ...
```
