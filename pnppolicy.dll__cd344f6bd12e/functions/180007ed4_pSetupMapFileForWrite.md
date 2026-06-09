# pSetupMapFileForWrite

- ea: `0x180007ed4`
- end: `0x180007f67`
- name: `pSetupMapFileForWrite`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x1800052c4`

## callees

- `0x180007ed4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007f3e`
- `KERNEL32!MapViewOfFile` at `0x180007f21`
- `KERNEL32!MapViewOfFile` at `0x180007f21`
- `KERNEL32!CreateFileMappingW` at `0x180007f00`
- `KERNEL32!CreateFileMappingW` at `0x180007f00`

## pseudocode

```c
__int64 __fastcall pSetupMapFileForWrite(void *a1, DWORD a2, HANDLE *a3, _QWORD *a4)
{
  SIZE_T dwNumberOfBytesToMap; // rbx
  HANDLE FileMappingW; // rax
  LPVOID v8; // rax
  DWORD LastError; // ebx

  dwNumberOfBytesToMap = a2;
  FileMappingW = CreateFileMappingW(a1, 0, 4u, 0, a2, 0);
  *a3 = FileMappingW;
  if ( FileMappingW )
  {
    v8 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, dwNumberOfBytesToMap);
    *a4 = v8;
    if ( v8 )
      return 0;
    LastError = GetLastError();
    CloseHandle(*a3);
    *a3 = 0;
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180007ed4  mov     rax, rsp
0x180007ed7  mov     [rax+8], rbx
0x180007edb  mov     [rax+10h], rsi
0x180007edf  push    rdi
0x180007ee0  sub     rsp, 30h
0x180007ee4  mov     ebx, edx
0x180007ee6  mov     rsi, r9
0x180007ee9  xor     r9d, r9d; dwMaximumSizeHigh
0x180007eec  mov     qword ptr [rax-10h], 0
0x180007ef4  mov     rdi, r8
0x180007ef7  mov     [rax-18h], ebx
0x180007efa  xor     edx, edx; lpFileMappingAttributes
0x180007efc  lea     r8d, [r9+4]; flProtect
0x180007f00  call    cs:__imp_CreateFileMappingW
0x180007f06  mov     [rdi], rax
0x180007f09  test    rax, rax
0x180007f0c  jz      short loc_180007F4D
0x180007f0e  xor     r9d, r9d; dwFileOffsetLow
0x180007f11  mov     [rsp+38h+dwNumberOfBytesToMap], rbx; dwNumberOfBytesToMap
0x180007f16  xor     r8d, r8d; dwFileOffsetHigh
0x180007f19  mov     edx, 0F001Fh; dwDesiredAccess
0x180007f1e  mov     rcx, rax; hFileMappingObject
0x180007f21  call    cs:__imp_MapViewOfFile
0x180007f27  mov     [rsi], rax
0x180007f2a  test    rax, rax
0x180007f2d  jz      short loc_180007F33
0x180007f2f  xor     eax, eax
0x180007f31  jmp     short loc_180007F57
0x180007f33  call    cs:__imp_GetLastError
0x180007f39  mov     rcx, [rdi]; hObject
0x180007f3c  mov     ebx, eax
0x180007f3e  call    cs:__imp_CloseHandle
0x180007f44  mov     qword ptr [rdi], 0
0x180007f4b  jmp     short loc_180007F55
0x180007f4d  call    cs:__imp_GetLastError
0x180007f53  mov     ebx, eax
0x180007f55  mov     eax, ebx
0x180007f57  mov     rbx, [rsp+38h+arg_0]
0x180007f5c  mov     rsi, [rsp+38h+arg_8]
0x180007f61  add     rsp, 30h
0x180007f65  pop     rdi
0x180007f66  retn
```
