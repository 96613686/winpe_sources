# _anonymous_namespace_::_Set_delete_flag

- ea: `0x18000a394`
- end: `0x18000a40b`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `DWORD __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ab1c`

## callees

- `0x18000a394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3fb`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000a3b4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000a3f1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000a3b4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000a3f1`

## pseudocode

```c
DWORD __fastcall anonymous_namespace_::_Set_delete_flag(HANDLE hFile)
{
  DWORD result; // eax
  char v3; // [rsp+38h] [rbp+10h] BYREF
  int FileInformation; // [rsp+40h] [rbp+18h] BYREF

  FileInformation = 3;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    return 0;
  result = GetLastError();
  if ( result == 1 || result != 5 && (result == 50 || result == 87) )
  {
    v3 = 1;
    if ( !SetFileInformationByHandle(hFile, FileDispositionInfo, &v3, 1u) )
      return GetLastError();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a394  push    rbx
0x18000a396  sub     rsp, 20h
0x18000a39a  mov     r9d, 4; dwBufferSize
0x18000a3a0  mov     [rsp+28h+FileInformation], 3
0x18000a3a8  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x18000a3ad  mov     rbx, rcx
0x18000a3b0  lea     edx, [r9+11h]; FileInformationClass
0x18000a3b4  call    cs:__imp_SetFileInformationByHandle
0x18000a3ba  test    eax, eax
0x18000a3bc  jnz     short loc_18000A403
0x18000a3be  call    cs:__imp_GetLastError
0x18000a3c4  mov     ecx, eax
0x18000a3c6  sub     ecx, 1
0x18000a3c9  jz      short loc_18000A3DA
0x18000a3cb  sub     ecx, 4
0x18000a3ce  jz      short loc_18000A405
0x18000a3d0  sub     ecx, 2Dh ; '-'
0x18000a3d3  jz      short loc_18000A3DA
0x18000a3d5  cmp     ecx, 25h ; '%'
0x18000a3d8  jnz     short loc_18000A405
0x18000a3da  mov     r9d, 1; dwBufferSize
0x18000a3e0  mov     [rsp+28h+arg_8], 1
0x18000a3e5  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x18000a3ea  mov     rcx, rbx; hFile
0x18000a3ed  lea     edx, [r9+3]; FileInformationClass
0x18000a3f1  call    cs:__imp_SetFileInformationByHandle
0x18000a3f7  test    eax, eax
0x18000a3f9  jnz     short loc_18000A403
0x18000a3fb  call    cs:__imp_GetLastError
0x18000a401  jmp     short loc_18000A405
0x18000a403  xor     eax, eax
0x18000a405  add     rsp, 20h
0x18000a409  pop     rbx
0x18000a40a  retn
```
