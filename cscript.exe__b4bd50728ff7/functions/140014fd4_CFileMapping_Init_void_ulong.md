# CFileMapping::Init(void *,ulong)

- ea: `0x140014fd4`
- end: `0x140015070`
- name: `?Init@CFileMapping@@QEAAJPEAXK@Z`
- size: `156`
- prototype: `int(CFileMapping *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x140001edc`

## callees

- `0x140014fd4`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x140015059`
- `KERNEL32!MapViewOfFile` at `0x140015059`
- `KERNEL32!GetFileSize` at `0x140014ff5`
- `KERNEL32!GetFileSize` at `0x140014ff5`
- `KERNEL32!CreateFileMappingA` at `0x140015034`
- `KERNEL32!CreateFileMappingA` at `0x140015034`
- `KERNEL32!GetLastError` at `0x140015003`
- `KERNEL32!GetLastError` at `0x140015003`

## pseudocode

```c
int __fastcall CFileMapping::Init(CFileMapping *this, void *a2)
{
  int result; // eax
  DWORD dwMaximumSizeLow; // eax
  HANDLE FileMappingA; // rax
  LPVOID v6; // rax

  if ( a2 == (void *)-1LL )
    return -2147418113;
  *(_QWORD *)this = a2;
  dwMaximumSizeLow = GetFileSize(a2, 0);
  *((_DWORD *)this + 6) = dwMaximumSizeLow;
  if ( dwMaximumSizeLow != -1 )
  {
    if ( !dwMaximumSizeLow )
      return 0;
    FileMappingA = CreateFileMappingA(*(HANDLE *)this, 0, 2u, 0, dwMaximumSizeLow, 0);
    *((_QWORD *)this + 1) = FileMappingA;
    if ( FileMappingA )
    {
      v6 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
      *((_QWORD *)this + 2) = v6;
      if ( v6 )
        return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140014fd4  push    rbx
0x140014fd6  sub     rsp, 30h
0x140014fda  mov     rax, rdx
0x140014fdd  mov     rbx, rcx
0x140014fe0  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140014fe4  jnz     short loc_140014FED
0x140014fe6  mov     eax, 8000FFFFh
0x140014feb  jmp     short loc_14001506A
0x140014fed  mov     [rcx], rax
0x140014ff0  xor     edx, edx; lpFileSizeHigh
0x140014ff2  mov     rcx, rax; hFile
0x140014ff5  call    cs:__imp_GetFileSize
0x140014ffb  mov     [rbx+18h], eax
0x140014ffe  cmp     eax, 0FFFFFFFFh
0x140015001  jnz     short loc_140015017
0x140015003  call    cs:__imp_GetLastError
0x140015009  test    eax, eax
0x14001500b  jle     short loc_14001506A
0x14001500d  movzx   eax, ax
0x140015010  or      eax, 80070000h
0x140015015  jmp     short loc_14001506A
0x140015017  test    eax, eax
0x140015019  jz      short loc_140015068
0x14001501b  mov     rcx, [rbx]; hFile
0x14001501e  xor     r9d, r9d; dwMaximumSizeHigh
0x140015021  mov     [rsp+38h+lpName], 0; lpName
0x14001502a  xor     edx, edx; lpFileMappingAttributes
0x14001502c  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x140015030  lea     r8d, [r9+2]; flProtect
0x140015034  call    cs:__imp_CreateFileMappingA
0x14001503a  mov     [rbx+8], rax
0x14001503e  test    rax, rax
0x140015041  jz      short loc_140015003
0x140015043  xor     r9d, r9d; dwFileOffsetLow
0x140015046  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x14001504f  xor     r8d, r8d; dwFileOffsetHigh
0x140015052  mov     rcx, rax; hFileMappingObject
0x140015055  lea     edx, [r9+4]; dwDesiredAccess
0x140015059  call    cs:__imp_MapViewOfFile
0x14001505f  mov     [rbx+10h], rax
0x140015063  test    rax, rax
0x140015066  jz      short loc_140015003
0x140015068  xor     eax, eax
0x14001506a  add     rsp, 30h
0x14001506e  pop     rbx
0x14001506f  retn
```
