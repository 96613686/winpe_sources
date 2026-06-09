# MapItRO(void *)

- ea: `0x1800238d8`
- end: `0x180023965`
- name: `?MapItRO@@YA?AVMappedSpan@@PEAX@Z`
- size: `141`
- prototype: `struct MappedSpan __high(void *)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003c04`
- `0x180019480`
- `0x180019de0`
- `0x1801aa7b0`
- `0x1801aacd0`
- `0x1801ad7e8`
- `0x1801ad980`

## callees

- `0x1800238d8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800238f3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800238f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002393b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002393b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180023910`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180023910`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002392f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002392f`

## pseudocode

```c
_QWORD *__fastcall MapItRO(_QWORD *a1, void *a2)
{
  LPVOID v4; // rsi
  __int64 FileSize; // rbp
  HANDLE FileMappingW; // rax
  void *v7; // rdi

  if ( a2 )
  {
    v4 = 0;
    FileSize = GetFileSize(a2, 0);
    FileMappingW = CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
    v7 = FileMappingW;
    if ( FileMappingW )
    {
      v4 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      CloseHandle(v7);
    }
    *a1 = v4;
    a1[1] = FileSize;
  }
  else
  {
    *a1 = 0;
    a1[1] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800238d8  push    rbx
0x1800238da  push    rbp
0x1800238db  push    rsi
0x1800238dc  push    rdi
0x1800238dd  sub     rsp, 38h
0x1800238e1  mov     rdi, rdx
0x1800238e4  mov     rbx, rcx
0x1800238e7  test    rdx, rdx
0x1800238ea  jz      short loc_18002394A
0x1800238ec  xor     edx, edx; lpFileSizeHigh
0x1800238ee  mov     rcx, rdi; hFile
0x1800238f1  xor     esi, esi
0x1800238f3  call    cs:__imp_GetFileSize
0x1800238f9  xor     r9d, r9d; dwMaximumSizeHigh
0x1800238fc  mov     [rsp+58h+lpName], rsi; lpName
0x180023901  xor     edx, edx; lpFileMappingAttributes
0x180023903  mov     ebp, eax
0x180023905  lea     r8d, [rsi+2]; flProtect
0x180023909  mov     [rsp+58h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x18002390d  mov     rcx, rdi; hFile
0x180023910  call    cs:__imp_CreateFileMappingW
0x180023916  mov     rdi, rax
0x180023919  test    rax, rax
0x18002391c  jz      short loc_180023941
0x18002391e  xor     r9d, r9d; dwFileOffsetLow
0x180023921  mov     qword ptr [rsp+58h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x180023926  xor     r8d, r8d; dwFileOffsetHigh
0x180023929  lea     edx, [rsi+4]; dwDesiredAccess
0x18002392c  mov     rcx, rax; hFileMappingObject
0x18002392f  call    cs:__imp_MapViewOfFile
0x180023935  mov     rcx, rdi; hObject
0x180023938  mov     rsi, rax
0x18002393b  call    cs:__imp_CloseHandle
0x180023941  mov     [rbx], rsi
0x180023944  mov     [rbx+8], rbp
0x180023948  jmp     short loc_180023959
0x18002394a  mov     qword ptr [rcx], 0
0x180023951  mov     qword ptr [rcx+8], 0
0x180023959  mov     rax, rbx
0x18002395c  add     rsp, 38h
0x180023960  pop     rdi
0x180023961  pop     rsi
0x180023962  pop     rbp
0x180023963  pop     rbx
0x180023964  retn
```
