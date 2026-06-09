# CImageAllocator::CreateDIB(long,tagDIBDATA &)

- ea: `0x1801423bc`
- end: `0x1801424ad`
- name: `?CreateDIB@CImageAllocator@@IEAAJJAEAUtagDIBDATA@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(CImageAllocator *__hidden this, int, struct tagDIBDATA *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800a35e8`
- `0x180141f98`

## callees

- `0x1801423bc`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x1801423f2`
- `KERNEL32!CreateFileMappingW` at `0x1801423f2`
- `KERNEL32!CloseHandle` at `0x18014247f`
- `KERNEL32!CloseHandle` at `0x18014247f`
- `KERNEL32!GetLastError` at `0x18014248b`
- `KERNEL32!GetLastError` at `0x18014248b`
- `GDI32!CreateDIBSection` at `0x180142430`
- `GDI32!CreateDIBSection` at `0x180142430`
- `GDI32!GetObjectW` at `0x18014246c`
- `GDI32!GetObjectW` at `0x18014246c`

## pseudocode

```c
__int64 __fastcall CImageAllocator::CreateDIB(CImageAllocator *this, DWORD a2, struct tagDIBDATA *a3)
{
  HANDLE hSection; // rdi
  HBITMAP v6; // rax
  void *ppvBits; // [rsp+58h] [rbp+20h] BYREF

  ppvBits = 0;
  hSection = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, a2, 0);
  if ( hSection )
  {
    v6 = CreateDIBSection(
           0,
           (const BITMAPINFO *)(*(_QWORD *)(*((_QWORD *)this + 20) + 80LL) + 48LL),
           0,
           &ppvBits,
           hSection,
           0);
    if ( v6 && ppvBits )
    {
      *((_QWORD *)a3 + 16) = ppvBits;
      *((_QWORD *)a3 + 14) = v6;
      *((_QWORD *)a3 + 15) = hSection;
      *(_DWORD *)a3 = 1;
      GetObjectW(v6, 104, (char *)a3 + 8);
      return 0;
    }
    CloseHandle(hSection);
  }
  return GetLastError() | 0x80070000;
}

```

## disassembly

```asm
0x1801423bc  mov     rax, rsp
0x1801423bf  mov     [rax+8], rbx
0x1801423c3  mov     [rax+10h], rsi
0x1801423c7  push    rdi
0x1801423c8  sub     rsp, 30h
0x1801423cc  xor     r9d, r9d; dwMaximumSizeHigh
0x1801423cf  mov     qword ptr [rax-10h], 0
0x1801423d7  mov     rbx, r8
0x1801423da  mov     [rax-18h], edx
0x1801423dd  mov     rsi, rcx
0x1801423e0  mov     qword ptr [rax+20h], 0
0x1801423e8  xor     edx, edx; lpFileMappingAttributes
0x1801423ea  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1801423ee  lea     r8d, [r9+4]; flProtect
0x1801423f2  call    cs:__imp_CreateFileMappingW
0x1801423f9  nop     dword ptr [rax+rax+00h]
0x1801423fe  mov     rdi, rax
0x180142401  test    rax, rax
0x180142404  jz      loc_18014248B
0x18014240a  mov     rax, [rsi+0A0h]
0x180142411  lea     r9, [rsp+38h+ppvBits]; ppvBits
0x180142416  mov     [rsp+38h+offset], 0; offset
0x18014241e  xor     r8d, r8d; usage
0x180142421  xor     ecx, ecx; hdc
0x180142423  mov     [rsp+38h+hSection], rdi; hSection
0x180142428  mov     rdx, [rax+50h]
0x18014242c  add     rdx, 30h ; '0'; pbmi
0x180142430  call    cs:__imp_CreateDIBSection
0x180142437  nop     dword ptr [rax+rax+00h]
0x18014243c  test    rax, rax
0x18014243f  jz      short loc_18014247C
0x180142441  mov     rcx, [rsp+38h+ppvBits]
0x180142446  test    rcx, rcx
0x180142449  jz      short loc_18014247C
0x18014244b  mov     [rbx+80h], rcx
0x180142452  lea     r8, [rbx+8]; pv
0x180142456  mov     rcx, rax; h
0x180142459  mov     [rbx+70h], rax
0x18014245d  mov     edx, 68h ; 'h'; c
0x180142462  mov     [rbx+78h], rdi
0x180142466  mov     dword ptr [rbx], 1
0x18014246c  call    cs:__imp_GetObjectW
0x180142473  nop     dword ptr [rax+rax+00h]
0x180142478  xor     eax, eax
0x18014247a  jmp     short loc_18014249C
0x18014247c  mov     rcx, rdi; hObject
0x18014247f  call    cs:__imp_CloseHandle
0x180142486  nop     dword ptr [rax+rax+00h]
0x18014248b  call    cs:__imp_GetLastError
0x180142492  nop     dword ptr [rax+rax+00h]
0x180142497  or      eax, 80070000h
0x18014249c  mov     rbx, [rsp+38h+arg_0]
0x1801424a1  mov     rsi, [rsp+38h+arg_8]
0x1801424a6  add     rsp, 30h
0x1801424aa  pop     rdi
0x1801424ab  retn
```
