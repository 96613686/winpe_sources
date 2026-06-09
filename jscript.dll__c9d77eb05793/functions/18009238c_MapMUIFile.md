# MapMUIFile

- ea: `0x18009238c`
- end: `0x180092470`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800924b8`
- `0x1800925d0`

## callees

- `0x18009238c`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18009245b`
- `KERNEL32!LoadLibraryExW` at `0x18009245b`
- `KERNEL32!CreateFileW` at `0x1800923cf`
- `KERNEL32!CreateFileW` at `0x1800923cf`
- `KERNEL32!CreateFileMappingW` at `0x1800923ff`
- `KERNEL32!CreateFileMappingW` at `0x1800923ff`
- `KERNEL32!MapViewOfFile` at `0x18009242c`
- `KERNEL32!MapViewOfFile` at `0x18009242c`
- `KERNEL32!CloseHandle` at `0x18009240b`
- `KERNEL32!CloseHandle` at `0x180092438`
- `KERNEL32!CloseHandle` at `0x18009240b`
- `KERNEL32!CloseHandle` at `0x180092438`

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
0x18009238c  mov     [rsp+arg_0], rbx
0x180092391  push    rdi
0x180092392  sub     rsp, 40h
0x180092396  mov     eax, r8d
0x180092399  test    rcx, rcx
0x18009239c  jz      loc_180092463
0x1800923a2  test    edx, edx
0x1800923a4  jz      loc_180092450
0x1800923aa  xor     r9d, r9d; lpSecurityAttributes
0x1800923ad  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800923b6  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800923be  mov     edx, 80000000h; dwDesiredAccess
0x1800923c3  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800923cb  lea     r8d, [r9+5]; dwShareMode
0x1800923cf  call    cs:__imp_CreateFileW
0x1800923d5  mov     rbx, rax
0x1800923d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800923dc  jz      loc_180092463
0x1800923e2  xor     r9d, r9d; dwMaximumSizeHigh
0x1800923e5  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1800923ee  xor     edx, edx; lpFileMappingAttributes
0x1800923f0  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800923f8  mov     rcx, rax; hFile
0x1800923fb  lea     r8d, [r9+8]; flProtect
0x1800923ff  call    cs:__imp_CreateFileMappingW
0x180092405  mov     rcx, rbx; hObject
0x180092408  mov     rdi, rax
0x18009240b  call    cs:__imp_CloseHandle
0x180092411  test    rdi, rdi
0x180092414  jz      short loc_180092463
0x180092416  xor     r9d, r9d; dwFileOffsetLow
0x180092419  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180092422  xor     r8d, r8d; dwFileOffsetHigh
0x180092425  mov     rcx, rdi; hFileMappingObject
0x180092428  lea     edx, [r9+1]; dwDesiredAccess
0x18009242c  call    cs:__imp_MapViewOfFile
0x180092432  mov     rcx, rdi; hObject
0x180092435  mov     rbx, rax
0x180092438  call    cs:__imp_CloseHandle
0x18009243e  mov     rcx, rbx
0x180092441  or      rcx, 1; lpLibFileName
0x180092445  neg     rbx
0x180092448  sbb     rax, rax
0x18009244b  and     rax, rcx
0x18009244e  jmp     short loc_180092465
0x180092450  xor     r8d, r8d
0x180092453  test    eax, eax
0x180092455  setnz   r8b; dwFlags
0x180092459  xor     edx, edx; hFile
0x18009245b  call    cs:__imp_LoadLibraryExW
0x180092461  jmp     short loc_180092465
0x180092463  xor     eax, eax
0x180092465  mov     rbx, [rsp+48h+arg_0]
0x18009246a  add     rsp, 40h
0x18009246e  pop     rdi
0x18009246f  retn
```
