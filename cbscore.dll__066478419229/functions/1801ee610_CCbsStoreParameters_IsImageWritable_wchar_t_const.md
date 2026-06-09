# CCbsStoreParameters::IsImageWritable(wchar_t const *)

- ea: `0x1801ee610`
- end: `0x1801ee8c2`
- name: `?IsImageWritable@CCbsStoreParameters@@AEBAHPEB_W@Z`
- size: `690`
- prototype: `int(CCbsStoreParameters *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1801ed3ec`

## callees

- `0x180013250`
- `0x180015420`
- `0x180016d40`
- `0x180095924`
- `0x1800a8678`
- `0x1800ae508`
- `0x1800b2fbc`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800f648c`
- `0x1801ee610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ee819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ee819`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801ee6a8`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1801ee6a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ee755`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ee755`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801ee809`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801ee809`

## string_xrefs

- `0x1801ee649`: `No Windows directory specified`
- `0x1801ee865`: `read-only`
- `0x1801ee77d`: `Unable to open image volume: {}`
- `0x1801ee6bd`: `Unable to get the volume path for {}`

## pseudocode

```c
__int64 __fastcall CCbsStoreParameters::IsImageWritable(CCbsStoreParameters *this, const wchar_t *a2)
{
  const char **v3; // rdx
  int v4; // ecx
  int v5; // eax
  const WCHAR *v6; // rbx
  __int64 v7; // rcx
  char *FileW; // rax
  unsigned int v10; // ebx
  signed int LastError; // eax
  int v12; // edx
  const char *v13; // rax
  const char *v14; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v16; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned[6]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+70h] [rbp-90h] BYREF

  v16 = a2;
  if ( !a2 )
  {
    LogAdapter::TraceAtLevelHr<long,>(2, 2147942487LL, "No Windows directory specified");
    goto LABEL_3;
  }
  memset_0(szVolumePathName, 0, 0x20Au);
  if ( !GetVolumePathNameW(a2, szVolumePathName, 0x105u) )
  {
    LogAdapter::TraceAtLevelLastError<wchar_t const *>(2, "Unable to get the volume path for {}", &v16);
    goto LABEL_3;
  }
  lpFileName = 0;
  if ( szVolumePathName[0] == 92 )
    v5 = SczAllocFromSz(&lpFileName, szVolumePathName);
  else
    v5 = SczAllocConcat2Sz(&lpFileName, L"\\\\.\\", szVolumePathName);
  if ( v5 < 0 )
  {
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
LABEL_3:
    v4 = (int)LogAdapter::g_Logger;
    v14 = "writable";
    if ( LogAdapter::g_Logger )
      goto LABEL_20;
    return 1;
  }
  v6 = lpFileName;
  v7 = -1;
  do
    ++v7;
  while ( lpFileName[v7] );
  if ( v7 && lpFileName[v7 - 1] == 92 )
    lpFileName[v7 - 1] = 0;
  FileW = (char *)CreateFileW(v6, 0, 7u, 0, 3u, 0x2000000u, 0);
  v14 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    *(_QWORD *)BytesReturned = v6;
    LogAdapter::TraceAtLevelLastError<wchar_t const *>(2, "Unable to open image volume: {}", BytesReturned);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
    v4 = (int)LogAdapter::g_Logger;
    v14 = "writable";
    if ( LogAdapter::g_Logger )
    {
      v3 = &v14;
LABEL_20:
      LOBYTE(v3) = 1;
      LogAdapter::Logger::LogNumObjects<char const *>(
        v4,
        (_DWORD)v3,
        1,
        (unsigned int)"Offline image is {}",
        (__int64)&v14);
    }
    return 1;
  }
  BytesReturned[0] = 0;
  v10 = 1;
  if ( !DeviceIoControl(FileW, 0x70024u, 0, 0, 0, 0, BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError == -2147024877 )
      v10 = 0;
    else
      LogAdapter::TraceAtLevelIfFailed<long,>(
        2,
        (unsigned int)LastError,
        "Unable to determine if the volume is writable");
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  v13 = "writable";
  if ( !v10 )
    v13 = "read-only";
  v14 = v13;
  if ( LogAdapter::g_Logger )
  {
    LOBYTE(v12) = 1;
    LogAdapter::Logger::LogNumObjects<char const *>(
      (_DWORD)LogAdapter::g_Logger,
      v12,
      1,
      (unsigned int)"Offline image is {}",
      (__int64)&v14);
  }
  return v10;
}

```

## disassembly

```asm
0x1801ee610  push    rbp
0x1801ee612  push    rbx
0x1801ee613  push    rsi
0x1801ee614  push    rdi
0x1801ee615  lea     rbp, [rsp-198h]
0x1801ee61d  sub     rsp, 298h
0x1801ee624  mov     rax, cs:__security_cookie
0x1801ee62b  xor     rax, rsp
0x1801ee62e  mov     [rbp+1B0h+var_30], rax
0x1801ee635  xor     edi, edi
0x1801ee637  mov     [rsp+2B0h+var_260], rdx
0x1801ee63c  mov     rbx, rdx
0x1801ee63f  mov     esi, 1
0x1801ee644  test    rdx, rdx
0x1801ee647  jnz     short loc_1801EE688
0x1801ee649  lea     r8, aNoWindowsDirec; "No Windows directory specified"
0x1801ee650  mov     edx, 80070057h
0x1801ee655  lea     ecx, [rbx+2]
0x1801ee658  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801ee65d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ee664  lea     rax, aWritable; "writable"
0x1801ee66b  mov     [rsp+2B0h+var_270], rax
0x1801ee670  test    rcx, rcx
0x1801ee673  jz      loc_1801EE7D6
0x1801ee679  lea     rax, [rsp+2B0h+var_270]
0x1801ee67e  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax
0x1801ee683  jmp     loc_1801EE7C4
0x1801ee688  xor     edx, edx; Val
0x1801ee68a  lea     rcx, [rsp+2B0h+szVolumePathName]; void *
0x1801ee68f  mov     r8d, 20Ah; Size
0x1801ee695  call    memset_0
0x1801ee69a  mov     r8d, 105h; cchBufferLength
0x1801ee6a0  lea     rdx, [rsp+2B0h+szVolumePathName]; lpszVolumePathName
0x1801ee6a5  mov     rcx, rbx; lpszFileName
0x1801ee6a8  call    cs:__imp_GetVolumePathNameW
0x1801ee6af  nop     dword ptr [rax+rax+00h]
0x1801ee6b4  test    eax, eax
0x1801ee6b6  jnz     short loc_1801EE6CE
0x1801ee6b8  lea     r8, [rsp+2B0h+var_260]
0x1801ee6bd  lea     rdx, aUnableToGetThe_1; "Unable to get the volume path for {}"
0x1801ee6c4  lea     ecx, [rax+2]
0x1801ee6c7  call    ??$TraceAtLevelLastError@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelLastError<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801ee6cc  jmp     short loc_1801EE65D
0x1801ee6ce  cmp     [rsp+2B0h+szVolumePathName], 5Ch ; '\'
0x1801ee6d4  lea     rcx, [rsp+2B0h+lpFileName]
0x1801ee6d9  mov     [rsp+2B0h+lpFileName], rdi
0x1801ee6de  jnz     short loc_1801EE6EC
0x1801ee6e0  lea     rdx, [rsp+2B0h+szVolumePathName]
0x1801ee6e5  call    SczAllocFromSz
0x1801ee6ea  jmp     short loc_1801EE6FD
0x1801ee6ec  lea     r8, [rsp+2B0h+szVolumePathName]
0x1801ee6f1  lea     rdx, asc_18035DD90; "\\\\.\\"
0x1801ee6f8  call    SczAllocConcat2Sz
0x1801ee6fd  test    eax, eax
0x1801ee6ff  jns     short loc_1801EE710
0x1801ee701  lea     rcx, [rsp+2B0h+lpFileName]
0x1801ee706  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801ee70b  jmp     loc_1801EE65D
0x1801ee710  mov     rbx, [rsp+2B0h+lpFileName]
0x1801ee715  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801ee719  inc     rcx
0x1801ee71c  cmp     [rbx+rcx*2], di
0x1801ee720  jnz     short loc_1801EE719
0x1801ee722  test    rcx, rcx
0x1801ee725  jz      short loc_1801EE734
0x1801ee727  cmp     word ptr [rbx+rcx*2-2], 5Ch ; '\'
0x1801ee72d  jnz     short loc_1801EE734
0x1801ee72f  mov     [rbx+rcx*2-2], di
0x1801ee734  xor     r9d, r9d; lpSecurityAttributes
0x1801ee737  mov     [rsp+2B0h+hTemplateFile], rdi; hTemplateFile
0x1801ee73c  mov     [rsp+2B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1801ee744  xor     edx, edx; dwDesiredAccess
0x1801ee746  mov     rcx, rbx; lpFileName
0x1801ee749  mov     [rsp+2B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1801ee751  lea     r8d, [r9+7]; dwShareMode
0x1801ee755  call    cs:__imp_CreateFileW
0x1801ee75c  nop     dword ptr [rax+rax+00h]
0x1801ee761  mov     [rsp+2B0h+var_270], rax
0x1801ee766  lea     rcx, [rax+1]
0x1801ee76a  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1801ee771  jnz     short loc_1801EE7DD
0x1801ee773  lea     r8, [rsp+2B0h+BytesReturned]
0x1801ee778  mov     qword ptr [rsp+2B0h+BytesReturned], rbx
0x1801ee77d  lea     rdx, aUnableToOpenIm; "Unable to open image volume: {}"
0x1801ee784  mov     ecx, 2
0x1801ee789  call    ??$TraceAtLevelLastError@PEB_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelLastError<wchar_t const *>(LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801ee78e  lea     rcx, [rsp+2B0h+var_270]
0x1801ee793  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801ee798  lea     rcx, [rsp+2B0h+lpFileName]
0x1801ee79d  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801ee7a2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ee7a9  lea     rax, aWritable; "writable"
0x1801ee7b0  mov     [rsp+2B0h+var_270], rax
0x1801ee7b5  test    rcx, rcx
0x1801ee7b8  jz      short loc_1801EE7D6
0x1801ee7ba  lea     rdx, [rsp+2B0h+var_270]
0x1801ee7bf  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rdx
0x1801ee7c4  lea     r9, aOfflineImageIs; "Offline image is {}"
0x1801ee7cb  mov     r8d, esi
0x1801ee7ce  mov     dl, sil
0x1801ee7d1  call    ??$LogNumObjects@PEBD@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEBD@Z; LogAdapter::Logger::LogNumObjects<char const *>(bool,LogAdapter::LogLevel,char const * const,char const * const &)
0x1801ee7d6  mov     eax, esi
0x1801ee7d8  jmp     loc_1801EE8A6
0x1801ee7dd  mov     [rsp+2B0h+lpOverlapped], rdi; lpOverlapped
0x1801ee7e2  lea     rcx, [rsp+2B0h+BytesReturned]
0x1801ee7e7  mov     [rsp+2B0h+hTemplateFile], rcx; lpBytesReturned
0x1801ee7ec  xor     r9d, r9d; nInBufferSize
0x1801ee7ef  mov     [rsp+2B0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x1801ee7f3  mov     rcx, rax; hDevice
0x1801ee7f6  xor     r8d, r8d; lpInBuffer
0x1801ee7f9  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rdi; lpOutBuffer
0x1801ee7fe  mov     edx, 70024h; dwIoControlCode
0x1801ee803  mov     [rsp+2B0h+BytesReturned], edi
0x1801ee807  mov     ebx, esi
0x1801ee809  call    cs:__imp_DeviceIoControl
0x1801ee810  nop     dword ptr [rax+rax+00h]
0x1801ee815  test    eax, eax
0x1801ee817  jnz     short loc_1801EE84F
0x1801ee819  call    cs:__imp_GetLastError
0x1801ee820  nop     dword ptr [rax+rax+00h]
0x1801ee825  test    eax, eax
0x1801ee827  jle     short loc_1801EE831
0x1801ee829  movzx   eax, ax
0x1801ee82c  or      eax, 80070000h
0x1801ee831  cmp     eax, 80070013h
0x1801ee836  jnz     short loc_1801EE83C
0x1801ee838  mov     ebx, edi
0x1801ee83a  jmp     short loc_1801EE84F
0x1801ee83c  lea     r8, aUnableToDeterm_8; "Unable to determine if the volume is wr"...
0x1801ee843  mov     edx, eax
0x1801ee845  mov     ecx, 2
0x1801ee84a  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801ee84f  lea     rcx, [rsp+2B0h+var_270]
0x1801ee854  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801ee859  lea     rcx, [rsp+2B0h+lpFileName]
0x1801ee85e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801ee863  test    ebx, ebx
0x1801ee865  lea     rcx, aReadOnly; "read-only"
0x1801ee86c  lea     rax, aWritable; "writable"
0x1801ee873  cmovz   rax, rcx
0x1801ee877  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ee87e  mov     [rsp+2B0h+var_270], rax
0x1801ee883  test    rcx, rcx
0x1801ee886  jz      short loc_1801EE8A4
0x1801ee888  lea     rax, [rsp+2B0h+var_270]
0x1801ee88d  mov     r8d, esi
0x1801ee890  lea     r9, aOfflineImageIs; "Offline image is {}"
0x1801ee897  mov     qword ptr [rsp+2B0h+dwCreationDisposition], rax
0x1801ee89c  mov     dl, sil
0x1801ee89f  call    ??$LogNumObjects@PEBD@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEBD@Z; LogAdapter::Logger::LogNumObjects<char const *>(bool,LogAdapter::LogLevel,char const * const,char const * const &)
0x1801ee8a4  mov     eax, ebx
0x1801ee8a6  mov     rcx, [rbp+1B0h+var_30]
0x1801ee8ad  xor     rcx, rsp; StackCookie
0x1801ee8b0  call    __security_check_cookie
0x1801ee8b5  add     rsp, 298h
0x1801ee8bc  pop     rdi
0x1801ee8bd  pop     rsi
0x1801ee8be  pop     rbx
0x1801ee8bf  pop     rbp
0x1801ee8c0  retn
```
