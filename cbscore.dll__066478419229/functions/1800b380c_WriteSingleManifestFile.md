# WriteSingleManifestFile

- ea: `0x1800b380c`
- end: `0x1800b3b34`
- name: `WriteSingleManifestFile`
- size: `808`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18012737c`
- `0x18012af70`

## callees

- `0x180013250`
- `0x1800261e0`
- `0x18002a448`
- `0x180093c4c`
- `0x180095924`
- `0x180095e34`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a02ec`
- `0x1800b380c`
- `0x1800eb920`
- `0x1801049a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b399b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b399b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3a6a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b3a56`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b3a56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b396f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b396f`

## string_xrefs

- `0x1800b3a95`: `Failed to write file: %ws`
- `0x1800b39c6`: `Failed to open file: {}`

## pseudocode

```c
__int64 __fastcall WriteSingleManifestFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // edi
  int v6; // edx
  int v7; // eax
  int v8; // eax
  HANDLE FileW; // rax
  HANDLE v10; // rdi
  signed int LastError; // edi
  int v12; // edx
  unsigned int v13; // eax
  __int64 v14; // rdx
  DWORD v15; // r8d
  const void *v16; // rdx
  int v17; // edx
  unsigned int v18; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-39h]
  HANDLE hFile; // [rsp+40h] [rbp-19h] BYREF
  int v23[2]; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v24[2]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v25; // [rsp+58h] [rbp-1h] BYREF
  __int64 v26; // [rsp+60h] [rbp+7h] BYREF
  int v27; // [rsp+68h] [rbp+Fh] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp+17h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v26 = a1;
  v25 = a3;
  if ( *(_QWORD *)a4 <= 0xFFFFFFFF )
  {
    *(_QWORD *)v23 = 0;
    v7 = SczAllocCombinePath2Sz(v23, a2, a1);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F3,
        (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
        (const char *)(unsigned int)v7,
        dwCreationDisposition);
LABEL_29:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v23);
      return v5;
    }
    lpFileName = 0;
    v8 = SczAllocFormatted(&lpFileName, L"%ws.%ws", *(_QWORD *)v23, v25);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F6,
        (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
        (const char *)(unsigned int)v8,
        dwCreationDisposition);
LABEL_9:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
      goto LABEL_29;
    }
    hFile = (HANDLE)-1LL;
    FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    v10 = hFile;
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v15 = *(_DWORD *)a4;
      v16 = *(const void **)(a4 + 16);
      NumberOfBytesWritten = 0;
      if ( WriteFile(hFile, v16, v15, &NumberOfBytesWritten, 0) )
      {
        WOFCompressFile(v10, 1, 0);
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
            (__int64)&lpFileName);
          if ( LastError > 0 )
            v18 = (unsigned __int16)LastError | 0x80070000;
          else
            v18 = LastError;
          v27 = v18;
          LOBYTE(v17) = 1;
          *(_QWORD *)v24 = &v27;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v17,
            3,
            (unsigned int)": {0}",
            (__int64)v24);
        }
        if ( LastError )
        {
          v14 = 2307;
          goto LABEL_18;
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
          (unsigned int)"Failed to open file: {}",
          (__int64)&lpFileName);
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        else
          v13 = LastError;
        v27 = v13;
        LOBYTE(v12) = 1;
        *(_QWORD *)v24 = &v27;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v12,
          3,
          (unsigned int)": {0}",
          (__int64)v24);
      }
      if ( LastError )
      {
        v14 = 2302;
LABEL_18:
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v14,
               (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
               (const char *)(unsigned int)LastError,
               dwCreationDispositiona);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        goto LABEL_9;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    v5 = 0;
    goto LABEL_29;
  }
  v5 = -2147024809;
  v27 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"File is too big {}.{}",
      (__int64)&v26,
      (__int64)&v25);
    *(_QWORD *)v23 = &v27;
    LOBYTE(v6) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v6,
      3,
      (unsigned int)": {}",
      (__int64)v23);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8F0,
    (unsigned int)"onecore\\base\\cbs\\core\\helper.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return v5;
}

```

## disassembly

```asm
0x1800b380c  push    rbp
0x1800b380e  push    rbx
0x1800b380f  push    rsi
0x1800b3810  push    rdi
0x1800b3811  lea     rbp, [rsp-3Fh]
0x1800b3816  sub     rsp, 98h
0x1800b381d  mov     rax, cs:__security_cookie
0x1800b3824  xor     rax, rsp
0x1800b3827  mov     [rbp+57h+var_30], rax
0x1800b382b  mov     eax, 0FFFFFFFFh
0x1800b3830  mov     [rbp+57h+var_50], rcx
0x1800b3834  mov     rsi, r9
0x1800b3837  mov     [rbp+57h+var_58], r8
0x1800b383b  cmp     [r9], rax
0x1800b383e  jbe     loc_1800B38C6
0x1800b3844  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b384b  mov     edi, 80070057h
0x1800b3850  mov     [rbp+57h+var_48], edi
0x1800b3853  test    rcx, rcx
0x1800b3856  jz      short loc_1800B38A9
0x1800b3858  lea     rax, [rbp+57h+var_58]
0x1800b385c  mov     esi, 3
0x1800b3861  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax
0x1800b3866  lea     r9, aFileIsTooBig_0; "File is too big {}.{}"
0x1800b386d  lea     rax, [rbp+57h+var_50]
0x1800b3871  mov     r8d, esi
0x1800b3874  xor     edx, edx
0x1800b3876  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800b387b  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800b3880  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b3887  lea     rax, [rbp+57h+var_48]
0x1800b388b  mov     qword ptr [rbp+57h+var_68], rax
0x1800b388f  lea     r9, asc_1802EE7AC; ": {}"
0x1800b3896  lea     rax, [rbp+57h+var_68]
0x1800b389a  mov     r8d, esi
0x1800b389d  mov     dl, 1
0x1800b389f  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x1800b38a4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b38a9  mov     rcx, [rbp+5Fh]; this
0x1800b38ad  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b38b4  mov     r9d, edi; char *
0x1800b38b7  mov     edx, 8F0h; void *
0x1800b38bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b38c1  jmp     loc_1800B3B19
0x1800b38c6  mov     r8, rcx
0x1800b38c9  xor     ebx, ebx
0x1800b38cb  lea     rcx, [rbp+57h+var_68]
0x1800b38cf  mov     qword ptr [rbp+57h+var_68], rbx
0x1800b38d3  call    SczAllocCombinePath2Sz
0x1800b38d8  mov     edi, eax
0x1800b38da  test    eax, eax
0x1800b38dc  jns     short loc_1800B38FB
0x1800b38de  mov     rcx, [rbp+5Fh]; this
0x1800b38e2  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b38e9  mov     r9d, eax; char *
0x1800b38ec  mov     edx, 8F3h; void *
0x1800b38f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b38f6  jmp     loc_1800B3B10
0x1800b38fb  mov     r9, [rbp+57h+var_58]
0x1800b38ff  lea     rdx, aWsWs_2; "%ws.%ws"
0x1800b3906  mov     r8, qword ptr [rbp+57h+var_68]
0x1800b390a  lea     rcx, [rbp+57h+lpFileName]
0x1800b390e  mov     [rbp+57h+lpFileName], rbx
0x1800b3912  call    SczAllocFormatted
0x1800b3917  mov     edi, eax
0x1800b3919  test    eax, eax
0x1800b391b  jns     short loc_1800B3943
0x1800b391d  mov     rcx, [rbp+5Fh]; this
0x1800b3921  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b3928  mov     r9d, eax; char *
0x1800b392b  mov     edx, 8F6h; void *
0x1800b3930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3935  lea     rcx, [rbp+57h+lpFileName]
0x1800b3939  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b393e  jmp     loc_1800B3B10
0x1800b3943  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800b3947  xor     r9d, r9d; lpSecurityAttributes
0x1800b394a  mov     [rsp+0B0h+hTemplateFile], rbx; hTemplateFile
0x1800b394f  xor     r8d, r8d; dwShareMode
0x1800b3952  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b395a  mov     edx, 40000000h; dwDesiredAccess
0x1800b395f  mov     [rsp+0B0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800b3967  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x1800b396f  call    cs:__imp_CreateFileW
0x1800b3976  nop     dword ptr [rax+rax+00h]
0x1800b397b  mov     rdx, rax
0x1800b397e  lea     rcx, [rbp+57h+hFile]
0x1800b3982  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b3987  mov     rdi, [rbp+57h+hFile]
0x1800b398b  lea     rax, [rdi+1]
0x1800b398f  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b3995  jnz     loc_1800B3A40
0x1800b399b  call    cs:__imp_GetLastError
0x1800b39a2  nop     dword ptr [rax+rax+00h]
0x1800b39a7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b39ae  mov     edi, eax
0x1800b39b0  test    rcx, rcx
0x1800b39b3  jz      short loc_1800B3A10
0x1800b39b5  lea     rax, [rbp+57h+lpFileName]
0x1800b39b9  mov     esi, 3
0x1800b39be  mov     r8d, esi
0x1800b39c1  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800b39c6  lea     r9, aFailedToOpenFi_1; "Failed to open file: {}"
0x1800b39cd  xor     edx, edx
0x1800b39cf  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b39d4  test    edi, edi
0x1800b39d6  jg      short loc_1800B39DC
0x1800b39d8  mov     eax, edi
0x1800b39da  jmp     short loc_1800B39E4
0x1800b39dc  movzx   eax, di
0x1800b39df  or      eax, 80070000h
0x1800b39e4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b39eb  lea     r9, a0; ": {0}"
0x1800b39f2  mov     [rbp+57h+var_48], eax
0x1800b39f5  mov     r8d, esi
0x1800b39f8  lea     rax, [rbp+57h+var_48]
0x1800b39fc  mov     dl, 1
0x1800b39fe  mov     qword ptr [rbp+57h+var_60], rax
0x1800b3a02  lea     rax, [rbp+57h+var_60]
0x1800b3a06  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; unsigned int
0x1800b3a0b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b3a10  test    edi, edi
0x1800b3a12  jz      loc_1800B3AFC
0x1800b3a18  mov     edx, 8FEh; void *
0x1800b3a1d  mov     rcx, [rbp+5Fh]; this
0x1800b3a21  lea     r8, aOnecoreBaseCbs_64; "onecore\\base\\cbs\\core\\helper.cpp"
0x1800b3a28  mov     r9d, edi; char *
0x1800b3a2b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b3a30  lea     rcx, [rbp+57h+hFile]
0x1800b3a34  mov     edi, eax
0x1800b3a36  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b3a3b  jmp     loc_1800B3935
0x1800b3a40  mov     r8d, [rsi]; nNumberOfBytesToWrite
0x1800b3a43  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800b3a47  mov     rdx, [rsi+10h]; lpBuffer
0x1800b3a4b  mov     rcx, rdi; hFile
0x1800b3a4e  mov     [rbp+57h+NumberOfBytesWritten], ebx
0x1800b3a51  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rbx; lpOverlapped
0x1800b3a56  call    cs:__imp_WriteFile
0x1800b3a5d  nop     dword ptr [rax+rax+00h]
0x1800b3a62  test    eax, eax
0x1800b3a64  jnz     loc_1800B3AED
0x1800b3a6a  call    cs:__imp_GetLastError
0x1800b3a71  nop     dword ptr [rax+rax+00h]
0x1800b3a76  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b3a7d  mov     edi, eax
0x1800b3a7f  test    rcx, rcx
0x1800b3a82  jz      short loc_1800B3ADF
0x1800b3a84  lea     rax, [rbp+57h+lpFileName]
0x1800b3a88  mov     esi, 3
0x1800b3a8d  mov     r8d, esi
0x1800b3a90  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800b3a95  lea     r9, aFailedToWriteF_3; "Failed to write file: %ws"
0x1800b3a9c  xor     edx, edx
0x1800b3a9e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b3aa3  test    edi, edi
0x1800b3aa5  jg      short loc_1800B3AAB
0x1800b3aa7  mov     eax, edi
0x1800b3aa9  jmp     short loc_1800B3AB3
0x1800b3aab  movzx   eax, di
0x1800b3aae  or      eax, 80070000h
0x1800b3ab3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b3aba  lea     r9, a0; ": {0}"
0x1800b3ac1  mov     [rbp+57h+var_48], eax
0x1800b3ac4  mov     r8d, esi
0x1800b3ac7  lea     rax, [rbp+57h+var_48]
0x1800b3acb  mov     dl, 1
0x1800b3acd  mov     qword ptr [rbp+57h+var_60], rax
0x1800b3ad1  lea     rax, [rbp+57h+var_60]
0x1800b3ad5  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x1800b3ada  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b3adf  test    edi, edi
0x1800b3ae1  jz      short loc_1800B3AFC
0x1800b3ae3  mov     edx, 903h
0x1800b3ae8  jmp     loc_1800B3A1D
0x1800b3aed  xor     r8d, r8d; unsigned int *
0x1800b3af0  mov     rcx, rdi; void *
0x1800b3af3  lea     edx, [r8+1]; int
0x1800b3af7  call    ?WOFCompressFile@@YAJPEAXHPEAK@Z; WOFCompressFile(void *,int,ulong *)
0x1800b3afc  lea     rcx, [rbp+57h+hFile]
0x1800b3b00  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b3b05  lea     rcx, [rbp+57h+lpFileName]
0x1800b3b09  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b3b0e  mov     edi, ebx
0x1800b3b10  lea     rcx, [rbp+57h+var_68]
0x1800b3b14  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b3b19  mov     eax, edi
0x1800b3b1b  mov     rcx, [rbp+57h+var_30]
0x1800b3b1f  xor     rcx, rsp; StackCookie
0x1800b3b22  call    __security_check_cookie
0x1800b3b27  add     rsp, 98h
0x1800b3b2e  pop     rdi
0x1800b3b2f  pop     rsi
0x1800b3b30  pop     rbx
0x1800b3b31  pop     rbp
0x1800b3b32  retn
```
