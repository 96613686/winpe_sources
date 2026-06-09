# ReadSingleManifestFile

- ea: `0x1800b0d48`
- end: `0x1800b1121`
- name: `ReadSingleManifestFile`
- size: `985`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18012737c`

## callees

- `0x18003ee54`
- `0x180049bec`
- `0x180095924`
- `0x180095e34`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a02ec`
- `0x1800b0d48`
- `0x1800d0588`
- `0x1800eb920`
- `0x1801250c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1007`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b0ff7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b0ff7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b0dae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b0dae`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800b0e95`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800b0e95`

## string_xrefs

- `0x1800b1028`: `Failed to write file: %ws`
- `0x1800b0e27`: `Failed to open {}`

## pseudocode

```c
__int64 __fastcall ReadSingleManifestFile(char a1, const WCHAR *a2, __int64 a3, _DWORD *a4)
{
  unsigned int v7; // ebx
  HANDLE FileW; // rax
  HANDLE v9; // r14
  signed int v10; // eax
  signed int v11; // edi
  int v12; // edx
  __int64 v13; // rdx
  __int64 v14; // rcx
  signed int LastError; // edi
  int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  int v20; // edx
  int v21; // eax
  DWORD v22; // r8d
  void *v23; // rdx
  int v24; // edx
  int v25; // r8d
  int v26; // r9d
  int v27; // edx
  unsigned int v28; // eax
  int v29; // edx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-50h]
  unsigned int v32[2]; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-28h] BYREF
  const WCHAR *v34; // [rsp+50h] [rbp-20h] BYREF
  int v35; // [rsp+58h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+5Ch] [rbp-14h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v34 = a2;
  hFile = (HANDLE)-1LL;
  v7 = 1;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x2000000u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    FileW);
  v9 = hFile;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    FileSize.QuadPart = 0;
    if ( GetFileSizeEx(hFile, &FileSize) )
    {
      if ( FileSize.QuadPart > 0xFFFFFFFFLL )
      {
        v11 = -2147024809;
        v35 = -2147024809;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"File is too big {}",
            (__int64)&v34);
          *(_QWORD *)v32 = &v35;
          LOBYTE(v20) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v20,
            3,
            (unsigned int)": {}",
            (__int64)v32);
        }
        v13 = 2266;
        goto LABEL_12;
      }
      v21 = RtlReallocateLBlob(v14, FileSize.LowPart, a3);
      if ( v21 < 0 )
      {
        v19 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x8DB,
                (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
                (const char *)(unsigned int)v21,
                dwCreationDisposition);
        goto LABEL_23;
      }
      v22 = *(_DWORD *)(a3 + 8);
      v23 = *(void **)(a3 + 16);
      NumberOfBytesRead = 0;
      if ( ReadFile(v9, v23, v22, &NumberOfBytesRead, 0) )
      {
        if ( FileSize.QuadPart != NumberOfBytesRead )
        {
          v11 = -2147024809;
          v35 = -2147024809;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *,__int64,unsigned long>(
              (_DWORD)LogAdapter::g_Logger,
              v24,
              v25,
              v26,
              (__int64)&v34,
              (__int64)&FileSize,
              (__int64)&NumberOfBytesRead);
            *(_QWORD *)v32 = &v35;
            LOBYTE(v29) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v29,
              3,
              (unsigned int)": {}",
              (__int64)v32);
          }
          v13 = 2275;
          goto LABEL_12;
        }
        *(_QWORD *)a3 = NumberOfBytesRead;
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to write file: %ws",
            (__int64)&v34);
          if ( LastError > 0 )
            v28 = (unsigned __int16)LastError | 0x80070000;
          else
            v28 = LastError;
          v35 = v28;
          LOBYTE(v27) = 1;
          *(_QWORD *)v32 = &v35;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v27,
            3,
            (unsigned int)": {0}",
            (__int64)v32);
        }
        if ( LastError )
        {
          v18 = 2272;
          goto LABEL_22;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get size of file {}",
          (__int64)&v34);
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0x80070000;
        else
          v17 = LastError;
        v35 = v17;
        LOBYTE(v16) = 1;
        *(_QWORD *)v32 = &v35;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v16,
          3,
          (unsigned int)": {0}",
          (__int64)v32);
      }
      if ( LastError )
      {
        v18 = 2265;
LABEL_22:
        v19 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v18,
                (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
                (const char *)(unsigned int)LastError,
                dwCreationDisposition);
LABEL_23:
        v7 = v19;
        goto LABEL_44;
      }
    }
    v7 = 0;
    goto LABEL_44;
  }
  v10 = GetLastError();
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( !a1 || !a4 || !IsNotFound_HRESULT(v11) )
  {
    v35 = v11;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to open {}",
        (__int64)&v34);
      *(_QWORD *)v32 = &v35;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v32);
    }
    if ( v11 >= 0 )
      goto LABEL_13;
    v13 = 2261;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
      (const char *)(unsigned int)v11,
      dwCreationDisposition);
LABEL_13:
    v7 = v11;
    goto LABEL_44;
  }
  *a4 |= 1u;
LABEL_44:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return v7;
}

```

## disassembly

```asm
0x1800b0d48  push    rbp
0x1800b0d4a  push    rbx
0x1800b0d4b  push    rsi
0x1800b0d4c  push    rdi
0x1800b0d4d  push    r13
0x1800b0d4f  push    r14
0x1800b0d51  push    r15
0x1800b0d53  mov     rbp, rsp
0x1800b0d56  sub     rsp, 70h
0x1800b0d5a  mov     rax, cs:__security_cookie
0x1800b0d61  xor     rax, rsp
0x1800b0d64  mov     [rbp+var_8], rax
0x1800b0d68  mov     rax, rdx
0x1800b0d6b  mov     [rbp+var_20], rdx
0x1800b0d6f  mov     r13d, 3
0x1800b0d75  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1800b0d7e  mov     rsi, r9
0x1800b0d81  mov     [rsp+70h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800b0d89  mov     rdi, r8
0x1800b0d8c  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800b0d94  mov     r15b, cl
0x1800b0d97  mov     [rsp+70h+dwCreationDisposition], r13d; int
0x1800b0d9c  lea     ebx, [r13-2]
0x1800b0da0  xor     r9d, r9d; lpSecurityAttributes
0x1800b0da3  mov     r8d, ebx; dwShareMode
0x1800b0da6  mov     edx, 80000000h; dwDesiredAccess
0x1800b0dab  mov     rcx, rax; lpFileName
0x1800b0dae  call    cs:__imp_CreateFileW
0x1800b0db5  nop     dword ptr [rax+rax+00h]
0x1800b0dba  mov     rdx, rax
0x1800b0dbd  lea     rcx, [rbp+hFile]
0x1800b0dc1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b0dc6  mov     r14, [rbp+hFile]
0x1800b0dca  lea     rax, [r14+1]
0x1800b0dce  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b0dd4  jnz     loc_1800B0E86
0x1800b0dda  call    cs:__imp_GetLastError
0x1800b0de1  nop     dword ptr [rax+rax+00h]
0x1800b0de6  mov     edi, eax
0x1800b0de8  test    eax, eax
0x1800b0dea  jle     short loc_1800B0DF5
0x1800b0dec  movzx   edi, ax
0x1800b0def  or      edi, 80070000h
0x1800b0df5  test    r15b, r15b
0x1800b0df8  jz      short loc_1800B0E11
0x1800b0dfa  test    rsi, rsi
0x1800b0dfd  jz      short loc_1800B0E11
0x1800b0dff  mov     ecx, edi; int
0x1800b0e01  call    ?IsNotFound_HRESULT@@YA_NJ@Z; IsNotFound_HRESULT(long)
0x1800b0e06  test    al, al
0x1800b0e08  jz      short loc_1800B0E11
0x1800b0e0a  or      [rsi], ebx
0x1800b0e0c  jmp     loc_1800B10FA
0x1800b0e11  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0e18  mov     [rbp+var_18], edi
0x1800b0e1b  test    rcx, rcx
0x1800b0e1e  jz      short loc_1800B0E63
0x1800b0e20  lea     rax, [rbp+var_20]
0x1800b0e24  mov     r8d, r13d
0x1800b0e27  lea     r9, aFailedToOpen; "Failed to open {}"
0x1800b0e2e  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800b0e33  xor     edx, edx
0x1800b0e35  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b0e3a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0e41  lea     rax, [rbp+var_18]
0x1800b0e45  mov     qword ptr [rbp+var_30], rax
0x1800b0e49  lea     r9, asc_1802EE7AC; ": {}"
0x1800b0e50  lea     rax, [rbp+var_30]
0x1800b0e54  mov     r8d, r13d
0x1800b0e57  mov     dl, bl
0x1800b0e59  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; int
0x1800b0e5e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b0e63  test    edi, edi
0x1800b0e65  jns     short loc_1800B0E7F
0x1800b0e67  mov     edx, 8D5h; void *
0x1800b0e6c  mov     rcx, [rbp+38h]; this
0x1800b0e70  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b0e77  mov     r9d, edi; char *
0x1800b0e7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b0e7f  mov     ebx, edi
0x1800b0e81  jmp     loc_1800B10FA
0x1800b0e86  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800b0e8a  mov     qword ptr [rbp+FileSize], 0
0x1800b0e92  mov     rcx, r14; hFile
0x1800b0e95  call    cs:__imp_GetFileSizeEx
0x1800b0e9c  nop     dword ptr [rax+rax+00h]
0x1800b0ea1  test    eax, eax
0x1800b0ea3  jnz     loc_1800B0F40
0x1800b0ea9  call    cs:__imp_GetLastError
0x1800b0eb0  nop     dword ptr [rax+rax+00h]
0x1800b0eb5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0ebc  mov     edi, eax
0x1800b0ebe  test    rcx, rcx
0x1800b0ec1  jz      short loc_1800B0F19
0x1800b0ec3  lea     rax, [rbp+var_20]
0x1800b0ec7  mov     r8d, r13d
0x1800b0eca  lea     r9, aFailedToGetSiz_0; "Failed to get size of file {}"
0x1800b0ed1  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800b0ed6  xor     edx, edx
0x1800b0ed8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b0edd  test    edi, edi
0x1800b0edf  jg      short loc_1800B0EE5
0x1800b0ee1  mov     eax, edi
0x1800b0ee3  jmp     short loc_1800B0EED
0x1800b0ee5  movzx   eax, di
0x1800b0ee8  or      eax, 80070000h
0x1800b0eed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0ef4  lea     r9, a0; ": {0}"
0x1800b0efb  mov     [rbp+var_18], eax
0x1800b0efe  mov     r8d, r13d
0x1800b0f01  lea     rax, [rbp+var_18]
0x1800b0f05  mov     dl, bl
0x1800b0f07  mov     qword ptr [rbp+var_30], rax
0x1800b0f0b  lea     rax, [rbp+var_30]
0x1800b0f0f  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; unsigned int
0x1800b0f14  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b0f19  test    edi, edi
0x1800b0f1b  jz      loc_1800B10F8
0x1800b0f21  mov     edx, 8D9h; void *
0x1800b0f26  mov     rcx, [rbp+38h]; this
0x1800b0f2a  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b0f31  mov     r9d, edi; char *
0x1800b0f34  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b0f39  mov     ebx, eax
0x1800b0f3b  jmp     loc_1800B10FA
0x1800b0f40  mov     eax, 0FFFFFFFFh
0x1800b0f45  cmp     qword ptr [rbp+FileSize], rax
0x1800b0f49  jle     short loc_1800B0FAC
0x1800b0f4b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0f52  mov     edi, 80070057h
0x1800b0f57  mov     [rbp+var_18], edi
0x1800b0f5a  test    rcx, rcx
0x1800b0f5d  jz      short loc_1800B0FA2
0x1800b0f5f  lea     rax, [rbp+var_20]
0x1800b0f63  mov     r8d, r13d
0x1800b0f66  lea     r9, aFileIsTooBig; "File is too big {}"
0x1800b0f6d  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800b0f72  xor     edx, edx
0x1800b0f74  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b0f79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0f80  lea     rax, [rbp+var_18]
0x1800b0f84  mov     qword ptr [rbp+var_30], rax
0x1800b0f88  lea     r9, asc_1802EE7AC; ": {}"
0x1800b0f8f  lea     rax, [rbp+var_30]
0x1800b0f93  mov     r8d, r13d
0x1800b0f96  mov     dl, bl
0x1800b0f98  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800b0f9d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b0fa2  mov     edx, 8DAh
0x1800b0fa7  jmp     loc_1800B0E6C
0x1800b0fac  mov     edx, dword ptr [rbp+FileSize]
0x1800b0faf  mov     r8, rdi
0x1800b0fb2  call    RtlReallocateLBlob
0x1800b0fb7  test    eax, eax
0x1800b0fb9  jns     short loc_1800B0FD8
0x1800b0fbb  mov     rcx, [rbp+38h]; this
0x1800b0fbf  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b0fc6  mov     r9d, eax; char *
0x1800b0fc9  mov     edx, 8DBh; void *
0x1800b0fce  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800b0fd3  jmp     loc_1800B0F39
0x1800b0fd8  mov     r8d, [rdi+8]; nNumberOfBytesToRead
0x1800b0fdc  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800b0fe0  mov     rdx, [rdi+10h]; lpBuffer
0x1800b0fe4  mov     rcx, r14; hFile
0x1800b0fe7  mov     [rbp+NumberOfBytesRead], 0
0x1800b0fee  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800b0ff7  call    cs:__imp_ReadFile
0x1800b0ffe  nop     dword ptr [rax+rax+00h]
0x1800b1003  test    eax, eax
0x1800b1005  jnz     short loc_1800B1085
0x1800b1007  call    cs:__imp_GetLastError
0x1800b100e  nop     dword ptr [rax+rax+00h]
0x1800b1013  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b101a  mov     edi, eax
0x1800b101c  test    rcx, rcx
0x1800b101f  jz      short loc_1800B1077
0x1800b1021  lea     rax, [rbp+var_20]
0x1800b1025  mov     r8d, r13d
0x1800b1028  lea     r9, aFailedToWriteF_3; "Failed to write file: %ws"
0x1800b102f  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800b1034  xor     edx, edx
0x1800b1036  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b103b  test    edi, edi
0x1800b103d  jg      short loc_1800B1043
0x1800b103f  mov     eax, edi
0x1800b1041  jmp     short loc_1800B104B
0x1800b1043  movzx   eax, di
0x1800b1046  or      eax, 80070000h
0x1800b104b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b1052  lea     r9, a0; ": {0}"
0x1800b1059  mov     [rbp+var_18], eax
0x1800b105c  mov     r8d, r13d
0x1800b105f  lea     rax, [rbp+var_18]
0x1800b1063  mov     dl, bl
0x1800b1065  mov     qword ptr [rbp+var_30], rax
0x1800b1069  lea     rax, [rbp+var_30]
0x1800b106d  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800b1072  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b1077  test    edi, edi
0x1800b1079  jz      short loc_1800B10F8
0x1800b107b  mov     edx, 8E0h
0x1800b1080  jmp     loc_1800B0F26
0x1800b1085  mov     eax, [rbp+NumberOfBytesRead]
0x1800b1088  cmp     qword ptr [rbp+FileSize], rax
0x1800b108c  jz      short loc_1800B10F5
0x1800b108e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b1095  mov     edi, 80070057h
0x1800b109a  mov     [rbp+var_18], edi
0x1800b109d  test    rcx, rcx
0x1800b10a0  jz      short loc_1800B10EB
0x1800b10a2  lea     rax, [rbp+NumberOfBytesRead]
0x1800b10a6  mov     [rsp+70h+hTemplateFile], rax
0x1800b10ab  lea     rax, [rbp+FileSize]
0x1800b10af  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x1800b10b4  lea     rax, [rbp+var_20]
0x1800b10b8  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800b10bd  call    ??$LogNumObjects@PEB_W_JK@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEB_JAEBK@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,__int64,ulong>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,__int64 const &,ulong const &)
0x1800b10c2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b10c9  lea     rax, [rbp+var_18]
0x1800b10cd  mov     qword ptr [rbp+var_30], rax
0x1800b10d1  lea     r9, asc_1802EE7AC; ": {}"
0x1800b10d8  lea     rax, [rbp+var_30]
0x1800b10dc  mov     r8d, r13d
0x1800b10df  mov     dl, bl
0x1800b10e1  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800b10e6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b10eb  mov     edx, 8E3h
0x1800b10f0  jmp     loc_1800B0E6C
0x1800b10f5  mov     [rdi], rax
0x1800b10f8  xor     ebx, ebx
0x1800b10fa  lea     rcx, [rbp+hFile]
0x1800b10fe  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b1103  mov     eax, ebx
0x1800b1105  mov     rcx, [rbp+var_8]
0x1800b1109  xor     rcx, rsp; StackCookie
0x1800b110c  call    __security_check_cookie
0x1800b1111  add     rsp, 70h
0x1800b1115  pop     r15
0x1800b1117  pop     r14
0x1800b1119  pop     r13
0x1800b111b  pop     rdi
0x1800b111c  pop     rsi
0x1800b111d  pop     rbx
0x1800b111e  pop     rbp
0x1800b111f  retn
```
