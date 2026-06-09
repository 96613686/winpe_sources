# MapMUIFile

- ea: `0x140110c80`
- end: `0x140110d64`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x140110dac`
- `0x140110ec0`

## callees

- `0x140110c80`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140110cc3`
- `KERNEL32!CreateFileW` at `0x140110cc3`
- `KERNEL32!MapViewOfFile` at `0x140110d20`
- `KERNEL32!MapViewOfFile` at `0x140110d20`
- `KERNEL32!CreateFileMappingW` at `0x140110cf3`
- `KERNEL32!CreateFileMappingW` at `0x140110cf3`
- `KERNEL32!LoadLibraryExW` at `0x140110d4f`
- `KERNEL32!LoadLibraryExW` at `0x140110d4f`
- `KERNEL32!CloseHandle` at `0x140110cff`
- `KERNEL32!CloseHandle` at `0x140110d2c`
- `KERNEL32!CloseHandle` at `0x140110cff`
- `KERNEL32!CloseHandle` at `0x140110d2c`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140110c80  mov     [rsp+arg_0], rbx
0x140110c85  push    rdi
0x140110c86  sub     rsp, 40h
0x140110c8a  mov     eax, r8d
0x140110c8d  test    rcx, rcx
0x140110c90  jz      loc_140110D57
0x140110c96  test    edx, edx
0x140110c98  jz      loc_140110D44
0x140110c9e  xor     r9d, r9d; lpSecurityAttributes
0x140110ca1  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140110caa  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140110cb2  mov     edx, 80000000h; dwDesiredAccess
0x140110cb7  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140110cbf  lea     r8d, [r9+5]; dwShareMode
0x140110cc3  call    cs:__imp_CreateFileW
0x140110cc9  mov     rbx, rax
0x140110ccc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140110cd0  jz      loc_140110D57
0x140110cd6  xor     r9d, r9d; dwMaximumSizeHigh
0x140110cd9  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x140110ce2  xor     edx, edx; lpFileMappingAttributes
0x140110ce4  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x140110cec  mov     rcx, rax; hFile
0x140110cef  lea     r8d, [r9+8]; flProtect
0x140110cf3  call    cs:__imp_CreateFileMappingW
0x140110cf9  mov     rcx, rbx; hObject
0x140110cfc  mov     rdi, rax
0x140110cff  call    cs:__imp_CloseHandle
0x140110d05  test    rdi, rdi
0x140110d08  jz      short loc_140110D57
0x140110d0a  xor     r9d, r9d; dwFileOffsetLow
0x140110d0d  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x140110d16  xor     r8d, r8d; dwFileOffsetHigh
0x140110d19  mov     rcx, rdi; hFileMappingObject
0x140110d1c  lea     edx, [r9+1]; dwDesiredAccess
0x140110d20  call    cs:__imp_MapViewOfFile
0x140110d26  mov     rcx, rdi; hObject
0x140110d29  mov     rbx, rax
0x140110d2c  call    cs:__imp_CloseHandle
0x140110d32  mov     rcx, rbx
0x140110d35  or      rcx, 1; lpLibFileName
0x140110d39  neg     rbx
0x140110d3c  sbb     rax, rax
0x140110d3f  and     rax, rcx
0x140110d42  jmp     short loc_140110D59
0x140110d44  xor     r8d, r8d
0x140110d47  test    eax, eax
0x140110d49  setnz   r8b; dwFlags
0x140110d4d  xor     edx, edx; hFile
0x140110d4f  call    cs:__imp_LoadLibraryExW
0x140110d55  jmp     short loc_140110D59
0x140110d57  xor     eax, eax
0x140110d59  mov     rbx, [rsp+48h+arg_0]
0x140110d5e  add     rsp, 40h
0x140110d62  pop     rdi
0x140110d63  retn
```
