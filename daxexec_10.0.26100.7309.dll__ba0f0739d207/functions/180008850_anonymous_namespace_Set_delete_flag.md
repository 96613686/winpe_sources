# _anonymous_namespace_::_Set_delete_flag

- ea: `0x180008850`
- end: `0x1800088c7`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008f68`

## callees

- `0x180008850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000887a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000887a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088b7`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180008870`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800088ad`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180008870`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800088ad`

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
0x180008850  push    rbx
0x180008852  sub     rsp, 20h
0x180008856  mov     r9d, 4; dwBufferSize
0x18000885c  mov     [rsp+28h+FileInformation], 3
0x180008864  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x180008869  mov     rbx, rcx
0x18000886c  lea     edx, [r9+11h]; FileInformationClass
0x180008870  call    cs:__imp_SetFileInformationByHandle
0x180008876  test    eax, eax
0x180008878  jnz     short loc_1800088BF
0x18000887a  call    cs:__imp_GetLastError
0x180008880  mov     ecx, eax
0x180008882  sub     ecx, 1
0x180008885  jz      short loc_180008896
0x180008887  sub     ecx, 4
0x18000888a  jz      short loc_1800088C1
0x18000888c  sub     ecx, 2Dh ; '-'
0x18000888f  jz      short loc_180008896
0x180008891  cmp     ecx, 25h ; '%'
0x180008894  jnz     short loc_1800088C1
0x180008896  mov     r9d, 1; dwBufferSize
0x18000889c  mov     [rsp+28h+arg_8], 1
0x1800088a1  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x1800088a6  mov     rcx, rbx; hFile
0x1800088a9  lea     edx, [r9+3]; FileInformationClass
0x1800088ad  call    cs:__imp_SetFileInformationByHandle
0x1800088b3  test    eax, eax
0x1800088b5  jnz     short loc_1800088BF
0x1800088b7  call    cs:__imp_GetLastError
0x1800088bd  jmp     short loc_1800088C1
0x1800088bf  xor     eax, eax
0x1800088c1  add     rsp, 20h
0x1800088c5  pop     rbx
0x1800088c6  retn
```
