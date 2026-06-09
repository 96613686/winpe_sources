# FileGetContent

- ea: `0x180105958`
- end: `0x180105e39`
- name: `FileGetContent`
- size: `1249`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x18012cc74`

## callees

- `0x18002e280`
- `0x18004f454`
- `0x180055fc8`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1801026fc`
- `0x180105958`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105d09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105d8e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180105c95`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180105c95`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180105b4e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180105b4e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180105b7f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180105b7f`

## string_xrefs

- `0x180105daf`: `Failed to open file: {}`
- `0x1801059b7`: `No path specified`
- `0x180105a15`: `No read count result specified`
- `0x180105a86`: `Read count exceeds maximum size`
- `0x180105ae9`: `No read result specified`
- `0x180105d23`: `Failed to read from file`

## pseudocode

```c
__int64 __fastcall FileGetContent(const WCHAR *a1, __int64 a2, union _LARGE_INTEGER *a3, _QWORD *a4)
{
  union _LARGE_INTEGER v4; // r14
  unsigned int v7; // ebx
  int v8; // edx
  __int64 v9; // rdx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  HANDLE FileW; // rax
  HANDLE v14; // rbx
  signed int LastError; // ebx
  int v16; // edx
  DWORD v17; // eax
  __int64 v18; // rdx
  union _LARGE_INTEGER v19; // rsi
  __int64 v20; // r12
  DWORD v21; // r8d
  int v23; // edx
  unsigned int v24; // eax
  int v25; // edx
  unsigned int v26; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  HANDLE hFile; // [rsp+40h] [rbp-40h] BYREF
  __int64 v30; // [rsp+48h] [rbp-38h] BYREF
  DWORD *p_NumberOfBytesRead; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v32[2]; // [rsp+58h] [rbp-28h] BYREF
  const WCHAR *v33; // [rsp+60h] [rbp-20h] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-18h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v4.QuadPart = 0;
  v33 = a1;
  v30 = 0;
  FileSize.QuadPart = 0;
  if ( a1 )
  {
    if ( !a3 )
    {
      v7 = -2147467261;
      NumberOfBytesRead = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No read count result specified");
        hFile = &NumberOfBytesRead;
        LOBYTE(v10) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v10,
          3,
          (unsigned int)": {}",
          (__int64)&hFile);
      }
      v9 = 1729;
      goto LABEL_9;
    }
    if ( a3->QuadPart == -1 )
    {
      v7 = -2147024809;
      NumberOfBytesRead = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Read count exceeds maximum size");
        hFile = &NumberOfBytesRead;
        LOBYTE(v11) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)&hFile);
      }
      v9 = 1730;
      goto LABEL_9;
    }
    if ( !a4 )
    {
      v7 = -2147467261;
      NumberOfBytesRead = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No read result specified");
        hFile = &NumberOfBytesRead;
        LOBYTE(v12) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v12,
          3,
          (unsigned int)": {}",
          (__int64)&hFile);
      }
      v9 = 1731;
      goto LABEL_9;
    }
    hFile = 0;
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
      &hFile,
      FileW);
    v14 = hFile;
    if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to open file: {}",
          (__int64)&v33);
        if ( LastError > 0 )
          v26 = (unsigned __int16)LastError | 0x80070000;
        else
          v26 = LastError;
        LODWORD(p_NumberOfBytesRead) = v26;
        LOBYTE(v25) = 1;
        *(_QWORD *)v32 = &p_NumberOfBytesRead;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v25,
          3,
          (unsigned int)": {0}",
          (__int64)v32);
      }
      if ( LastError )
      {
        v18 = 1737;
        goto LABEL_56;
      }
    }
    else if ( GetFileSizeEx(hFile, &FileSize) )
    {
      v19 = FileSize;
      if ( a3->QuadPart && a3->QuadPart < (unsigned __int64)FileSize.QuadPart )
        v19 = *a3;
      if ( !Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(&v30, v19.QuadPart + 1) )
      {
        v7 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6DA,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)0x8007000ELL,
          dwCreationDispositiona);
LABEL_57:
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
        goto LABEL_58;
      }
      v20 = v30;
      if ( v19.QuadPart )
      {
        while ( 1 )
        {
          v21 = v19.QuadPart - v4.QuadPart <= 0xFFFFFFFFuLL ? v19.LowPart - v4.LowPart : -1;
          NumberOfBytesRead = v21;
          if ( !ReadFile(v14, (LPVOID)(v4.QuadPart + v20), v21, &NumberOfBytesRead, 0) )
            break;
          if ( NumberOfBytesRead )
          {
            v4.QuadPart += NumberOfBytesRead;
            if ( v4.QuadPart < (unsigned __int64)v19.QuadPart )
              continue;
          }
          goto LABEL_39;
        }
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to read from file");
          if ( LastError > 0 )
            v24 = (unsigned __int16)LastError | 0x80070000;
          else
            v24 = LastError;
          LODWORD(p_NumberOfBytesRead) = v24;
          LOBYTE(v23) = 1;
          *(_QWORD *)v32 = &p_NumberOfBytesRead;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v23,
            3,
            (unsigned int)": {0}",
            (__int64)v32);
        }
        if ( !LastError )
        {
          Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
          v7 = 0;
          goto LABEL_58;
        }
        v18 = 1775;
        goto LABEL_56;
      }
LABEL_39:
      *(_BYTE *)(v20 + v19.QuadPart) = 0;
      *a4 = v20;
      *a3 = v4;
      v30 = 0;
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
          (unsigned int)"Failed to get size of the file: {}",
          (__int64)&v33);
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0x80070000;
        else
          v17 = LastError;
        NumberOfBytesRead = v17;
        LOBYTE(v16) = 1;
        p_NumberOfBytesRead = &NumberOfBytesRead;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v16,
          3,
          (unsigned int)": {0}",
          (__int64)&p_NumberOfBytesRead);
      }
      if ( LastError )
      {
        v18 = 1740;
LABEL_56:
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v18,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)(unsigned int)LastError,
               dwCreationDispositiona);
        goto LABEL_57;
      }
    }
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&hFile);
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v30);
    return 0;
  }
  v7 = -2147024809;
  NumberOfBytesRead = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path specified");
    hFile = &NumberOfBytesRead;
    LOBYTE(v8) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v8,
      3,
      (unsigned int)": {}",
      (__int64)&hFile);
  }
  v9 = 1728;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v7,
    dwCreationDisposition);
LABEL_58:
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(&v30);
  return v7;
}

```

## disassembly

```asm
0x180105958  mov     [rsp-38h+arg_8], rbx
0x18010595d  push    rbp
0x18010595e  push    rsi
0x18010595f  push    rdi
0x180105960  push    r12
0x180105962  push    r13
0x180105964  push    r14
0x180105966  push    r15
0x180105968  mov     rbp, rsp
0x18010596b  sub     rsp, 80h
0x180105972  mov     rax, cs:__security_cookie
0x180105979  xor     rax, rsp
0x18010597c  mov     [rbp+var_8], rax
0x180105980  xor     r14d, r14d
0x180105983  mov     [rbp+var_20], rcx
0x180105987  mov     [rbp+var_38], r14
0x18010598b  mov     r13, r9
0x18010598e  mov     qword ptr [rbp+FileSize], r14
0x180105992  mov     r15, r8
0x180105995  test    rcx, rcx
0x180105998  jnz     short loc_1801059F3
0x18010599a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801059a1  mov     ebx, 80070057h
0x1801059a6  mov     [rbp+NumberOfBytesRead], ebx
0x1801059a9  test    rcx, rcx
0x1801059ac  jz      short loc_1801059EC
0x1801059ae  lea     edi, [r14+3]
0x1801059b2  xor     edx, edx
0x1801059b4  mov     r8d, edi
0x1801059b7  lea     r9, aNoPathSpecifie; "No path specified"
0x1801059be  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801059c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801059ca  lea     rax, [rbp+NumberOfBytesRead]
0x1801059ce  mov     [rbp+hFile], rax
0x1801059d2  lea     r9, asc_1802EE7AC; ": {}"
0x1801059d9  lea     rax, [rbp+hFile]
0x1801059dd  mov     r8d, edi
0x1801059e0  mov     dl, 1
0x1801059e2  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x1801059e7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801059ec  mov     edx, 6C0h
0x1801059f1  jmp     short loc_180105A4F
0x1801059f3  test    r15, r15
0x1801059f6  jnz     short loc_180105A67
0x1801059f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801059ff  mov     ebx, 80004003h
0x180105a04  mov     [rbp+NumberOfBytesRead], ebx
0x180105a07  test    rcx, rcx
0x180105a0a  jz      short loc_180105A4A
0x180105a0c  lea     edi, [r15+3]
0x180105a10  xor     edx, edx
0x180105a12  mov     r8d, edi
0x180105a15  lea     r9, aNoReadCountRes; "No read count result specified"
0x180105a1c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180105a21  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105a28  lea     rax, [rbp+NumberOfBytesRead]
0x180105a2c  mov     [rbp+hFile], rax
0x180105a30  lea     r9, asc_1802EE7AC; ": {}"
0x180105a37  lea     rax, [rbp+hFile]
0x180105a3b  mov     r8d, edi
0x180105a3e  mov     dl, 1
0x180105a40  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x180105a45  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105a4a  mov     edx, 6C1h; void *
0x180105a4f  mov     rcx, [rbp+38h]; this
0x180105a53  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180105a5a  mov     r9d, ebx; char *
0x180105a5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105a62  jmp     loc_180105E29
0x180105a67  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180105a6b  jb      short loc_180105AC7
0x180105a6d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105a74  mov     ebx, 80070057h
0x180105a79  mov     [rbp+NumberOfBytesRead], ebx
0x180105a7c  test    rcx, rcx
0x180105a7f  jz      short loc_180105AC0
0x180105a81  mov     edi, 3
0x180105a86  lea     r9, aReadCountExcee; "Read count exceeds maximum size"
0x180105a8d  mov     r8d, edi
0x180105a90  xor     edx, edx
0x180105a92  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180105a97  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105a9e  lea     rax, [rbp+NumberOfBytesRead]
0x180105aa2  mov     [rbp+hFile], rax
0x180105aa6  lea     r9, asc_1802EE7AC; ": {}"
0x180105aad  lea     rax, [rbp+hFile]
0x180105ab1  mov     r8d, edi
0x180105ab4  mov     dl, 1
0x180105ab6  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x180105abb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105ac0  mov     edx, 6C2h
0x180105ac5  jmp     short loc_180105A4F
0x180105ac7  test    r13, r13
0x180105aca  jnz     short loc_180105B28
0x180105acc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105ad3  mov     ebx, 80004003h
0x180105ad8  mov     [rbp+NumberOfBytesRead], ebx
0x180105adb  test    rcx, rcx
0x180105ade  jz      short loc_180105B1E
0x180105ae0  lea     edi, [r13+3]
0x180105ae4  xor     edx, edx
0x180105ae6  mov     r8d, edi
0x180105ae9  lea     r9, aNoReadResultSp; "No read result specified"
0x180105af0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180105af5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105afc  lea     rax, [rbp+NumberOfBytesRead]
0x180105b00  mov     [rbp+hFile], rax
0x180105b04  lea     r9, asc_1802EE7AC; ": {}"
0x180105b0b  lea     rax, [rbp+hFile]
0x180105b0f  mov     r8d, edi
0x180105b12  mov     dl, 1
0x180105b14  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x180105b19  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105b1e  mov     edx, 6C3h
0x180105b23  jmp     loc_180105A4F
0x180105b28  mov     edi, 3
0x180105b2d  mov     [rsp+80h+hTemplateFile], r14; hTemplateFile
0x180105b32  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180105b3a  xor     r9d, r9d; lpSecurityAttributes
0x180105b3d  mov     edx, 80000000h; dwDesiredAccess
0x180105b42  mov     [rbp+hFile], r14
0x180105b46  mov     [rsp+80h+dwCreationDisposition], edi; int
0x180105b4a  lea     r8d, [rdi-2]; dwShareMode
0x180105b4e  call    cs:__imp_CreateFileW
0x180105b55  nop     dword ptr [rax+rax+00h]
0x180105b5a  mov     rdx, rax
0x180105b5d  lea     rcx, [rbp+hFile]
0x180105b61  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x180105b66  mov     rbx, [rbp+hFile]
0x180105b6a  lea     rax, [rbx-1]
0x180105b6e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180105b72  ja      loc_180105D8E
0x180105b78  lea     rdx, [rbp+FileSize]; lpFileSize
0x180105b7c  mov     rcx, rbx; hFile
0x180105b7f  call    cs:__imp_GetFileSizeEx
0x180105b86  nop     dword ptr [rax+rax+00h]
0x180105b8b  test    eax, eax
0x180105b8d  jnz     loc_180105C15
0x180105b93  call    cs:__imp_GetLastError
0x180105b9a  nop     dword ptr [rax+rax+00h]
0x180105b9f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105ba6  mov     ebx, eax
0x180105ba8  test    rcx, rcx
0x180105bab  jz      short loc_180105C03
0x180105bad  lea     rax, [rbp+var_20]
0x180105bb1  mov     r8d, edi
0x180105bb4  lea     r9, aFailedToGetSiz_1; "Failed to get size of the file: {}"
0x180105bbb  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x180105bc0  xor     edx, edx
0x180105bc2  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180105bc7  test    ebx, ebx
0x180105bc9  jg      short loc_180105BCF
0x180105bcb  mov     eax, ebx
0x180105bcd  jmp     short loc_180105BD7
0x180105bcf  movzx   eax, bx
0x180105bd2  or      eax, 80070000h
0x180105bd7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105bde  lea     r9, a0; ": {0}"
0x180105be5  mov     [rbp+NumberOfBytesRead], eax
0x180105be8  mov     r8d, edi
0x180105beb  lea     rax, [rbp+NumberOfBytesRead]
0x180105bef  mov     dl, 1
0x180105bf1  mov     [rbp+var_30], rax
0x180105bf5  lea     rax, [rbp+var_30]
0x180105bf9  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x180105bfe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105c03  test    ebx, ebx
0x180105c05  jz      loc_180105CCD
0x180105c0b  mov     edx, 6CCh
0x180105c10  jmp     loc_180105E0B
0x180105c15  mov     rsi, qword ptr [rbp+FileSize]
0x180105c19  cmp     [r15], r14
0x180105c1c  jz      short loc_180105C25
0x180105c1e  cmp     [r15], rsi
0x180105c21  cmovb   rsi, [r15]
0x180105c25  lea     rdx, [rsi+1]
0x180105c29  lea     rcx, [rbp+var_38]
0x180105c2d  call    ?AllocateWithTotalSize@?$AutoNewWithUnsizedArrayPtr@U_BACKING_REGION_OUTPUT@@@Windows@@QEAAPEAU_BACKING_REGION_OUTPUT@@_K@Z; Windows::AutoNewWithUnsizedArrayPtr<_BACKING_REGION_OUTPUT>::AllocateWithTotalSize(unsigned __int64)
0x180105c32  test    rax, rax
0x180105c35  jnz     short loc_180105C59
0x180105c37  mov     rcx, [rbp+38h]; this
0x180105c3b  lea     r8, aOnecoreBaseCbs_105; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180105c42  mov     ebx, 8007000Eh
0x180105c47  mov     edx, 6DAh; void *
0x180105c4c  mov     r9d, ebx; char *
0x180105c4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105c54  jmp     loc_180105E20
0x180105c59  mov     r12, [rbp+var_38]
0x180105c5d  test    rsi, rsi
0x180105c60  jz      short loc_180105CB9
0x180105c62  mov     ecx, 0FFFFFFFFh
0x180105c67  mov     rax, rsi
0x180105c6a  sub     rax, r14
0x180105c6d  cmp     rax, rcx
0x180105c70  jbe     short loc_180105C77
0x180105c72  mov     r8d, ecx
0x180105c75  jmp     short loc_180105C7D
0x180105c77  mov     r8d, esi
0x180105c7a  sub     r8d, r14d; nNumberOfBytesToRead
0x180105c7d  lea     rdx, [r14+r12]; lpBuffer
0x180105c81  mov     [rbp+NumberOfBytesRead], r8d
0x180105c85  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180105c89  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOverlapped
0x180105c92  mov     rcx, rbx; hFile
0x180105c95  call    cs:__imp_ReadFile
0x180105c9c  nop     dword ptr [rax+rax+00h]
0x180105ca1  test    eax, eax
0x180105ca3  jz      short loc_180105D09
0x180105ca5  mov     eax, [rbp+NumberOfBytesRead]
0x180105ca8  test    eax, eax
0x180105caa  jz      short loc_180105CB9
0x180105cac  add     r14, rax
0x180105caf  mov     ecx, 0FFFFFFFFh
0x180105cb4  cmp     r14, rsi
0x180105cb7  jb      short loc_180105C67
0x180105cb9  mov     byte ptr [r12+rsi], 0
0x180105cbe  mov     [r13+0], r12
0x180105cc2  mov     [r15], r14
0x180105cc5  mov     [rbp+var_38], 0
0x180105ccd  lea     rcx, [rbp+hFile]
0x180105cd1  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180105cd6  lea     rcx, [rbp+var_38]
0x180105cda  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x180105cdf  xor     eax, eax
0x180105ce1  mov     rcx, [rbp+var_8]
0x180105ce5  xor     rcx, rsp; StackCookie
0x180105ce8  call    __security_check_cookie
0x180105ced  mov     rbx, [rsp+80h+arg_8]
0x180105cf5  add     rsp, 80h
0x180105cfc  pop     r15
0x180105cfe  pop     r14
0x180105d00  pop     r13
0x180105d02  pop     r12
0x180105d04  pop     rdi
0x180105d05  pop     rsi
0x180105d06  pop     rbp
0x180105d07  retn
0x180105d09  call    cs:__imp_GetLastError
0x180105d10  nop     dword ptr [rax+rax+00h]
0x180105d15  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105d1c  mov     ebx, eax
0x180105d1e  test    rcx, rcx
0x180105d21  jz      short loc_180105D70
0x180105d23  lea     r9, aFailedToReadFr; "Failed to read from file"
0x180105d2a  mov     r8d, edi
0x180105d2d  xor     edx, edx
0x180105d2f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180105d34  test    ebx, ebx
0x180105d36  jg      short loc_180105D3C
0x180105d38  mov     eax, ebx
0x180105d3a  jmp     short loc_180105D44
0x180105d3c  movzx   eax, bx
0x180105d3f  or      eax, 80070000h
0x180105d44  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105d4b  lea     r9, a0; ": {0}"
0x180105d52  mov     dword ptr [rbp+var_30], eax
0x180105d55  mov     r8d, edi
0x180105d58  lea     rax, [rbp+var_30]
0x180105d5c  mov     dl, 1
0x180105d5e  mov     qword ptr [rbp+var_28], rax
0x180105d62  lea     rax, [rbp+var_28]
0x180105d66  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x180105d6b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105d70  test    ebx, ebx
0x180105d72  jz      short loc_180105D7E
0x180105d74  mov     edx, 6EFh
0x180105d79  jmp     loc_180105E0B
0x180105d7e  lea     rcx, [rbp+hFile]
0x180105d82  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180105d87  xor     ebx, ebx
0x180105d89  jmp     loc_180105E29
0x180105d8e  call    cs:__imp_GetLastError
0x180105d95  nop     dword ptr [rax+rax+00h]
0x180105d9a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105da1  mov     ebx, eax
0x180105da3  test    rcx, rcx
0x180105da6  jz      short loc_180105DFE
0x180105da8  lea     rax, [rbp+var_20]
0x180105dac  mov     r8d, edi
0x180105daf  lea     r9, aFailedToOpenFi_1; "Failed to open file: {}"
0x180105db6  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x180105dbb  xor     edx, edx
0x180105dbd  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180105dc2  test    ebx, ebx
0x180105dc4  jg      short loc_180105DCA
0x180105dc6  mov     eax, ebx
0x180105dc8  jmp     short loc_180105DD2
0x180105dca  movzx   eax, bx
0x180105dcd  or      eax, 80070000h
0x180105dd2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180105dd9  lea     r9, a0; ": {0}"
0x180105de0  mov     dword ptr [rbp+var_30], eax
0x180105de3  mov     r8d, edi
0x180105de6  lea     rax, [rbp+var_30]
0x180105dea  mov     dl, 1
0x180105dec  mov     qword ptr [rbp+var_28], rax
0x180105df0  lea     rax, [rbp+var_28]
0x180105df4  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned int
0x180105df9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180105dfe  test    ebx, ebx
  ... truncated ...
```
