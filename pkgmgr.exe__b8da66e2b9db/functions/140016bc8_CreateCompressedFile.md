# CreateCompressedFile

- ea: `0x140016bc8`
- end: `0x140016dc0`
- name: `CreateCompressedFile`
- size: `504`
- prototype: `__int64 __fastcall(const WCHAR *, bool *, __int64, __int64, int, int, int, HANDLE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140013288`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x140016ac4`
- `0x140016bc8`
- `0x140016dc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016d79`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140016d6f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140016d6f`

## string_xrefs

- `0x140016c1f`: `No file path specified`

## pseudocode

```c
__int64 __fastcall CreateCompressedFile(
        const WCHAR *a1,
        bool *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        HANDLE *a8)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v12; // rdx
  int FileWithRetries; // eax
  __int64 v14; // rdx
  signed int LastError; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  int lpOutBuffer; // [rsp+20h] [rbp-58h]
  DWORD nOutBufferSize; // [rsp+28h] [rbp-50h]
  int lpBytesReturned; // [rsp+30h] [rbp-48h]
  int v21[2]; // [rsp+40h] [rbp-38h] BYREF
  const WCHAR *v22; // [rsp+48h] [rbp-30h] BYREF
  int v23; // [rsp+50h] [rbp-28h] BYREF
  __int16 InBuffer; // [rsp+54h] [rbp-24h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  InBuffer = 2;
  v22 = a1;
  BytesReturned = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    v23 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file path specified");
      *(_QWORD *)v21 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v10 = 1433;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v8);
    return v8;
  }
  if ( !a8 )
  {
    v8 = -2147467261;
    v23 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No file handle result specified");
      *(_QWORD *)v21 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v12,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v10 = 1434;
    goto LABEL_5;
  }
  FileWithRetries = CreateFileWithRetries(a1, a2, a3, a4, lpOutBuffer, nOutBufferSize, lpBytesReturned, a8);
  v8 = FileWithRetries;
  if ( FileWithRetries < 0 )
  {
    v23 = FileWithRetries;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed creating file {}",
        (__int64)&v22);
      *(_QWORD *)v21 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v14,
        3,
        (__int64)": {}",
        (__int64)v21);
    }
    v10 = 1440;
    goto LABEL_5;
  }
  if ( !DeviceIoControl(*a8, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError != -2147024895 && LastError != -2147024846 && LastError < 0 )
      LogAdapter::TraceAtLevelHr<long,wchar_t const *>(v16, LastError, v17, (__int64)&v22);
  }
  return 0;
}

```

## disassembly

```asm
0x140016bc8  push    rbp
0x140016bca  push    rbx
0x140016bcb  push    rdi
0x140016bcc  push    r14
0x140016bce  mov     rbp, rsp
0x140016bd1  sub     rsp, 78h
0x140016bd5  mov     rax, cs:__security_cookie
0x140016bdc  xor     rax, rsp
0x140016bdf  mov     [rbp+var_18], rax
0x140016be3  mov     rdi, [rbp+arg_38]
0x140016be7  mov     r14d, 2
0x140016bed  mov     [rbp+InBuffer], r14w
0x140016bf2  mov     [rbp+var_30], rcx
0x140016bf6  mov     [rbp+BytesReturned], 0
0x140016bfd  test    rcx, rcx
0x140016c00  jnz     short loc_140016C71
0x140016c02  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016c09  mov     ebx, 80070057h
0x140016c0e  mov     [rbp+var_28], ebx
0x140016c11  test    rcx, rcx
0x140016c14  jz      short loc_140016C52
0x140016c16  lea     edi, [r14+1]
0x140016c1a  xor     edx, edx
0x140016c1c  mov     r8d, edi
0x140016c1f  lea     r9, aNoFilePathSpec; "No file path specified"
0x140016c26  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016c2b  lea     rcx, [rbp+var_38]
0x140016c2f  mov     r8d, edi
0x140016c32  mov     [rsp+78h+lpOutBuffer], rcx; int
0x140016c37  lea     rax, [rbp+var_28]
0x140016c3b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016c42  lea     r9, asc_14002D4FC; ": {}"
0x140016c49  mov     qword ptr [rbp+var_38], rax
0x140016c4d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016c52  mov     edx, 599h; void *
0x140016c57  mov     rcx, [rbp+20h]; this
0x140016c5b  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140016c62  mov     r9d, ebx; char *
0x140016c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016c6a  mov     eax, ebx
0x140016c6c  jmp     loc_140016DAA
0x140016c71  test    rdi, rdi
0x140016c74  jnz     short loc_140016CCE
0x140016c76  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016c7d  mov     ebx, 80004003h
0x140016c82  mov     [rbp+var_28], ebx
0x140016c85  test    rcx, rcx
0x140016c88  jz      short loc_140016CC7
0x140016c8a  mov     edi, 3
0x140016c8f  lea     r9, aNoFileHandleRe; "No file handle result specified"
0x140016c96  mov     r8d, edi
0x140016c99  xor     edx, edx
0x140016c9b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016ca0  lea     rcx, [rbp+var_38]
0x140016ca4  mov     r8d, edi
0x140016ca7  mov     [rsp+78h+lpOutBuffer], rcx
0x140016cac  lea     rax, [rbp+var_28]
0x140016cb0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016cb7  lea     r9, asc_14002D4FC; ": {}"
0x140016cbe  mov     qword ptr [rbp+var_38], rax
0x140016cc2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016cc7  mov     edx, 59Ah
0x140016ccc  jmp     short loc_140016C57
0x140016cce  mov     [rsp+78h+lpOverlapped], rdi
0x140016cd3  call    CreateFileWithRetries
0x140016cd8  mov     ebx, eax
0x140016cda  test    eax, eax
0x140016cdc  jns     short loc_140016D3D
0x140016cde  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016ce5  mov     [rbp+var_28], eax
0x140016ce8  test    rcx, rcx
0x140016ceb  jz      short loc_140016D33
0x140016ced  lea     rax, [rbp+var_30]
0x140016cf1  mov     edi, 3
0x140016cf6  mov     r8d, edi
0x140016cf9  mov     [rsp+78h+lpOutBuffer], rax
0x140016cfe  lea     r9, aFailedCreating_1; "Failed creating file {}"
0x140016d05  xor     edx, edx
0x140016d07  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140016d0c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016d13  lea     rax, [rbp+var_28]
0x140016d17  mov     qword ptr [rbp+var_38], rax
0x140016d1b  lea     r9, asc_14002D4FC; ": {}"
0x140016d22  lea     rax, [rbp+var_38]
0x140016d26  mov     r8d, edi
0x140016d29  mov     [rsp+78h+lpOutBuffer], rax
0x140016d2e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016d33  mov     edx, 5A0h
0x140016d38  jmp     loc_140016C57
0x140016d3d  mov     rcx, [rdi]; hDevice
0x140016d40  lea     rax, [rbp+BytesReturned]
0x140016d44  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x140016d4d  lea     r8, [rbp+InBuffer]; lpInBuffer
0x140016d51  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x140016d56  mov     r9d, r14d; nInBufferSize
0x140016d59  mov     [rsp+78h+nOutBufferSize], 0; nOutBufferSize
0x140016d61  mov     edx, 9C040h; dwIoControlCode
0x140016d66  mov     [rsp+78h+lpOutBuffer], 0; lpOutBuffer
0x140016d6f  call    cs:__imp_DeviceIoControl
0x140016d75  test    eax, eax
0x140016d77  jnz     short loc_140016DA8
0x140016d79  call    cs:__imp_GetLastError
0x140016d7f  test    eax, eax
0x140016d81  jle     short loc_140016D8B
0x140016d83  movzx   eax, ax
0x140016d86  or      eax, 80070000h
0x140016d8b  cmp     eax, 80070001h
0x140016d90  jz      short loc_140016DA8
0x140016d92  cmp     eax, 80070032h
0x140016d97  jz      short loc_140016DA8
0x140016d99  test    eax, eax
0x140016d9b  jns     short loc_140016DA8
0x140016d9d  lea     r9, [rbp+var_30]
0x140016da1  mov     edx, eax
0x140016da3  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x140016da8  xor     eax, eax
0x140016daa  mov     rcx, [rbp+var_18]
0x140016dae  xor     rcx, rsp; StackCookie
0x140016db1  call    __security_check_cookie
0x140016db6  add     rsp, 78h
0x140016dba  pop     r14
0x140016dbc  pop     rdi
0x140016dbd  pop     rbx
0x140016dbe  pop     rbp
0x140016dbf  retn
```
