# TFileMapping::Load(ushort const *,bool)

- ea: `0x1800113fc`
- end: `0x1800114b5`
- name: `?Load@TFileMapping@@QEAAJPEBG_N@Z`
- size: `185`
- prototype: `__int64 __fastcall(TFileMapping *this, LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180017114`
- `0x180017814`
- `0x180028868`

## callees

- `0x1800113fc`
- `0x1800116c8`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x18001149f`
- `KERNEL32!GetFileSize` at `0x18001149f`
- `KERNEL32!MapViewOfFile` at `0x180011490`
- `KERNEL32!MapViewOfFile` at `0x180011490`
- `KERNEL32!CreateFileMappingA` at `0x18001145f`
- `KERNEL32!CreateFileMappingA` at `0x18001145f`
- `KERNEL32!CreateFileW` at `0x180011433`
- `KERNEL32!CreateFileW` at `0x180011433`

## pseudocode

```c
__int64 __fastcall TFileMapping::Load(TFileMapping *this, LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  HANDLE FileMappingA; // rax
  unsigned int v5; // ebx
  LPVOID v6; // rax
  void *v7; // rcx

  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x10000000u, 0);
  *(_QWORD *)this = FileW;
  if ( FileW != (HANDLE)-1LL
    && (FileMappingA = CreateFileMappingA(FileW, 0, 2u, 0, 0, 0), (*((_QWORD *)this + 1) = FileMappingA) != 0) )
  {
    v5 = 0;
    v6 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
    v7 = *(void **)this;
    *((_QWORD *)this + 2) = v6;
    *((_DWORD *)this + 6) = GetFileSize(v7, 0);
  }
  else
  {
    v5 = -2147483644;
    TFileMapping::Unload(this);
  }
  return v5;
}

```

## disassembly

```asm
0x1800113fc  mov     [rsp+arg_0], rbx
0x180011401  push    rdi
0x180011402  sub     rsp, 40h
0x180011406  mov     rax, rdx
0x180011409  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180011412  mov     rdi, rcx
0x180011415  mov     [rsp+48h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x18001141d  mov     r8d, 3; dwShareMode
0x180011423  mov     rcx, rax; lpFileName
0x180011426  xor     r9d, r9d; lpSecurityAttributes
0x180011429  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001142e  mov     edx, 80000000h; dwDesiredAccess
0x180011433  call    cs:__imp_CreateFileW
0x180011439  mov     [rdi], rax
0x18001143c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011440  jz      short loc_18001146E
0x180011442  xor     r9d, r9d; dwMaximumSizeHigh
0x180011445  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18001144e  xor     edx, edx; lpFileMappingAttributes
0x180011450  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180011458  mov     rcx, rax; hFile
0x18001145b  lea     r8d, [r9+2]; flProtect
0x18001145f  call    cs:__imp_CreateFileMappingA
0x180011465  mov     [rdi+8], rax
0x180011469  test    rax, rax
0x18001146c  jnz     short loc_18001147D
0x18001146e  mov     rcx, rdi; this
0x180011471  mov     ebx, 80000004h
0x180011476  call    ?Unload@TFileMapping@@QEAAJXZ; TFileMapping::Unload(void)
0x18001147b  jmp     short loc_1800114A8
0x18001147d  xor     ebx, ebx
0x18001147f  xor     r9d, r9d; dwFileOffsetLow
0x180011482  xor     r8d, r8d; dwFileOffsetHigh
0x180011485  mov     qword ptr [rsp+48h+dwCreationDisposition], rbx; dwNumberOfBytesToMap
0x18001148a  mov     rcx, rax; hFileMappingObject
0x18001148d  lea     edx, [rbx+4]; dwDesiredAccess
0x180011490  call    cs:__imp_MapViewOfFile
0x180011496  mov     rcx, [rdi]; hFile
0x180011499  xor     edx, edx; lpFileSizeHigh
0x18001149b  mov     [rdi+10h], rax
0x18001149f  call    cs:__imp_GetFileSize
0x1800114a5  mov     [rdi+18h], eax
0x1800114a8  mov     eax, ebx
0x1800114aa  mov     rbx, [rsp+48h+arg_0]
0x1800114af  add     rsp, 40h
0x1800114b3  pop     rdi
0x1800114b4  retn
```
