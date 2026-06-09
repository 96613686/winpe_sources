# DSUtils::DeleteFileOnClose(void *)

- ea: `0x180019fe8`
- end: `0x18001a066`
- name: `?DeleteFileOnClose@DSUtils@@YAJPEAX@Z`
- size: `126`
- prototype: `__int64 __fastcall(HANDLE hFile, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d3e4`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x180019fe8`
- `0x18001afe8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a01f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a01f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001a015`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18001a015`

## string_xrefs

- `0x18001a039`: `DSUtils::DeleteFileOnClose: Failed to SetFileDispositionInfo. hr=0x%x`
- `0x18001a04a`: `DSUtils::DeleteFileOnClose`

## pseudocode

```c
__int64 __fastcall DSUtils::DeleteFileOnClose(HANDLE hFile, void *a2, __int64 a3)
{
  unsigned int v4; // ebx
  signed int LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  DSLogger *v9; // rax
  char FileInformation; // [rsp+40h] [rbp+8h] BYREF

  if ( !hFile )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2, a3);
  v4 = 0;
  FileInformation = 1;
  if ( !SetFileInformationByHandle(hFile, FileDispositionInfo, &FileInformation, 1u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v9 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                       v7,
                       v6,
                       v8);
    DSLogger::LogError(
      v9,
      L"DSUtils::DeleteFileOnClose",
      0x296u,
      L"DSUtils::DeleteFileOnClose: Failed to SetFileDispositionInfo. hr=0x%x",
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180019fe8  mov     [rsp+arg_8], rbx
0x180019fed  push    rdi
0x180019fee  sub     rsp, 30h
0x180019ff2  mov     rdi, rcx
0x180019ff5  test    rcx, rcx
0x180019ff8  jnz     short loc_180019FFF
0x180019ffa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019fff  xor     ebx, ebx
0x18001a001  mov     [rsp+38h+FileInformation], 1
0x18001a006  lea     r8, [rsp+38h+FileInformation]; lpFileInformation
0x18001a00b  mov     rcx, rdi; hFile
0x18001a00e  lea     r9d, [rbx+1]; dwBufferSize
0x18001a012  lea     edx, [rbx+4]; FileInformationClass
0x18001a015  call    cs:__imp_SetFileInformationByHandle
0x18001a01b  test    eax, eax
0x18001a01d  jnz     short loc_18001A059
0x18001a01f  call    cs:__imp_GetLastError
0x18001a025  mov     ebx, eax
0x18001a027  test    eax, eax
0x18001a029  jle     short loc_18001A034
0x18001a02b  movzx   ebx, ax
0x18001a02e  or      ebx, 80070000h
0x18001a034  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a039  lea     r9, aDsutilsDeletef; "DSUtils::DeleteFileOnClose: Failed to S"...
0x18001a040  mov     [rsp+38h+var_18], ebx
0x18001a044  mov     r8d, 296h; unsigned int
0x18001a04a  lea     rdx, aDsutilsDeletef_0; "DSUtils::DeleteFileOnClose"
0x18001a051  mov     rcx, rax; this
0x18001a054  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001a059  mov     eax, ebx
0x18001a05b  mov     rbx, [rsp+38h+arg_8]
0x18001a060  add     rsp, 30h
0x18001a064  pop     rdi
0x18001a065  retn
```
