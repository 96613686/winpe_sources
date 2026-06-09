# DSUtils::IsHardLinkFile(void *,bool *)

- ea: `0x18001a518`
- end: `0x18001a5dd`
- name: `?IsHardLinkFile@DSUtils@@YAJPEAXPEA_N@Z`
- size: `197`
- prototype: `__int64 __fastcall(HANDLE hFile, _BYTE *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180019e70`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18001a518`
- `0x18001afe8`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a574`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001a56a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001a56a`

## string_xrefs

- `0x18001a58e`: `IsHardLinkFile: Failed to get file information HR=0x%x`
- `0x18001a59f`: `DSUtils::IsHardLinkFile`

## pseudocode

```c
__int64 __fastcall DSUtils::IsHardLinkFile(HANDLE hFile, _BYTE *a2, bool *a3)
{
  signed int v5; // ebx
  signed int LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  DSLogger *v11; // rax
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+30h] [rbp-48h] BYREF

  if ( !hFile )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2, a3);
  v5 = 0;
  *a2 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandle(hFile, &FileInformation) )
    goto LABEL_7;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  v11 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                      v8,
                      v7,
                      v9,
                      v10);
  DSLogger::LogError(
    v11,
    L"DSUtils::IsHardLinkFile",
    0x18Fu,
    L"IsHardLinkFile: Failed to get file information HR=0x%x",
    v5);
  if ( v5 >= 0 )
  {
LABEL_7:
    if ( FileInformation.nNumberOfLinks > 1 )
      *a2 = 1;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a518  mov     [rsp+arg_10], rbx
0x18001a51d  mov     [rsp+arg_18], rsi
0x18001a522  push    rdi
0x18001a523  sub     rsp, 70h
0x18001a527  mov     rax, cs:__security_cookie
0x18001a52e  xor     rax, rsp
0x18001a531  mov     [rsp+78h+var_10], rax
0x18001a536  mov     rdi, rdx
0x18001a539  mov     rsi, rcx
0x18001a53c  test    rcx, rcx
0x18001a53f  jnz     short loc_18001A546
0x18001a541  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001a546  xorps   xmm0, xmm0
0x18001a549  lea     rdx, [rsp+78h+FileInformation]; lpFileInformation
0x18001a54e  xor     eax, eax
0x18001a550  xor     ebx, ebx
0x18001a552  mov     rcx, rsi; hFile
0x18001a555  mov     [rdi], bl
0x18001a557  movups  xmmword ptr [rsp+78h+FileInformation.dwFileAttributes], xmm0
0x18001a55c  mov     [rsp+78h+FileInformation.nFileIndexLow], eax
0x18001a560  movups  xmmword ptr [rsp+78h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18001a565  movups  xmmword ptr [rsp+78h+FileInformation.nFileSizeHigh], xmm0
0x18001a56a  call    cs:__imp_GetFileInformationByHandle
0x18001a570  test    eax, eax
0x18001a572  jnz     short loc_18001A5B2
0x18001a574  call    cs:__imp_GetLastError
0x18001a57a  mov     ebx, eax
0x18001a57c  test    eax, eax
0x18001a57e  jle     short loc_18001A589
0x18001a580  movzx   ebx, ax
0x18001a583  or      ebx, 80070000h
0x18001a589  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a58e  lea     r9, aIshardlinkfile; "IsHardLinkFile: Failed to get file info"...
0x18001a595  mov     [rsp+78h+var_58], ebx
0x18001a599  mov     r8d, 18Fh; unsigned int
0x18001a59f  lea     rdx, aDsutilsIshardl; "DSUtils::IsHardLinkFile"
0x18001a5a6  mov     rcx, rax; this
0x18001a5a9  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001a5ae  test    ebx, ebx
0x18001a5b0  js      short loc_18001A5BC
0x18001a5b2  cmp     [rsp+78h+FileInformation.nNumberOfLinks], 1
0x18001a5b7  jbe     short loc_18001A5BC
0x18001a5b9  mov     byte ptr [rdi], 1
0x18001a5bc  mov     eax, ebx
0x18001a5be  mov     rcx, [rsp+78h+var_10]
0x18001a5c3  xor     rcx, rsp; StackCookie
0x18001a5c6  call    __security_check_cookie
0x18001a5cb  lea     r11, [rsp+78h+var_8]
0x18001a5d0  mov     rbx, [r11+20h]
0x18001a5d4  mov     rsi, [r11+28h]
0x18001a5d8  mov     rsp, r11
0x18001a5db  pop     rdi
0x18001a5dc  retn
```
