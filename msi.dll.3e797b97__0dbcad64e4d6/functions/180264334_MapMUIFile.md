# MapMUIFile

- ea: `0x180264334`
- end: `0x18026443d`
- name: `MapMUIFile`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800d2160`
- `0x180264490`

## callees

- `0x180264334`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x1802643ad`
- `KERNEL32!CreateFileMappingW` at `0x1802643ad`
- `KERNEL32!MapViewOfFile` at `0x1802643e6`
- `KERNEL32!MapViewOfFile` at `0x1802643e6`
- `KERNEL32!CloseHandle` at `0x1802643bf`
- `KERNEL32!CloseHandle` at `0x1802643f8`
- `KERNEL32!CloseHandle` at `0x1802643bf`
- `KERNEL32!CloseHandle` at `0x1802643f8`
- `KERNEL32!CreateFileW` at `0x180264377`
- `KERNEL32!CreateFileW` at `0x180264377`
- `KERNEL32!LoadLibraryExW` at `0x180264421`
- `KERNEL32!LoadLibraryExW` at `0x180264421`

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
0x180264334  mov     [rsp+arg_0], rbx
0x180264339  push    rdi
0x18026433a  sub     rsp, 40h
0x18026433e  mov     eax, r8d
0x180264341  test    rcx, rcx
0x180264344  jz      loc_18026442F
0x18026434a  test    edx, edx
0x18026434c  jz      loc_180264416
0x180264352  xor     r9d, r9d; lpSecurityAttributes
0x180264355  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18026435e  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180264366  mov     edx, 80000000h; dwDesiredAccess
0x18026436b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180264373  lea     r8d, [r9+5]; dwShareMode
0x180264377  call    cs:__imp_CreateFileW
0x18026437e  nop     dword ptr [rax+rax+00h]
0x180264383  mov     rbx, rax
0x180264386  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18026438a  jz      loc_18026442F
0x180264390  xor     r9d, r9d; dwMaximumSizeHigh
0x180264393  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18026439c  xor     edx, edx; lpFileMappingAttributes
0x18026439e  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1802643a6  mov     rcx, rax; hFile
0x1802643a9  lea     r8d, [r9+8]; flProtect
0x1802643ad  call    cs:__imp_CreateFileMappingW
0x1802643b4  nop     dword ptr [rax+rax+00h]
0x1802643b9  mov     rcx, rbx; hObject
0x1802643bc  mov     rdi, rax
0x1802643bf  call    cs:__imp_CloseHandle
0x1802643c6  nop     dword ptr [rax+rax+00h]
0x1802643cb  test    rdi, rdi
0x1802643ce  jz      short loc_18026442F
0x1802643d0  xor     r9d, r9d; dwFileOffsetLow
0x1802643d3  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1802643dc  xor     r8d, r8d; dwFileOffsetHigh
0x1802643df  mov     rcx, rdi; hFileMappingObject
0x1802643e2  lea     edx, [r9+1]; dwDesiredAccess
0x1802643e6  call    cs:__imp_MapViewOfFile
0x1802643ed  nop     dword ptr [rax+rax+00h]
0x1802643f2  mov     rcx, rdi; hObject
0x1802643f5  mov     rbx, rax
0x1802643f8  call    cs:__imp_CloseHandle
0x1802643ff  nop     dword ptr [rax+rax+00h]
0x180264404  mov     rcx, rbx
0x180264407  or      rcx, 1; lpLibFileName
0x18026440b  neg     rbx
0x18026440e  sbb     rax, rax
0x180264411  and     rax, rcx
0x180264414  jmp     short loc_180264431
0x180264416  xor     r8d, r8d
0x180264419  test    eax, eax
0x18026441b  setnz   r8b; dwFlags
0x18026441f  xor     edx, edx; hFile
0x180264421  call    cs:__imp_LoadLibraryExW
0x180264428  nop     dword ptr [rax+rax+00h]
0x18026442d  jmp     short loc_180264431
0x18026442f  xor     eax, eax
0x180264431  mov     rbx, [rsp+48h+arg_0]
0x180264436  add     rsp, 40h
0x18026443a  pop     rdi
0x18026443b  retn
```
