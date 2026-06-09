# CPackage::InitVerbEnum(tagOLEVERB *,ulong)

- ea: `0x1800092d0`
- end: `0x18000934f`
- name: `?InitVerbEnum@CPackage@@IEAAJPEAUtagOLEVERB@@K@Z`
- size: `127`
- prototype: `__int64 __fastcall(CPackage *this, struct tagOLEVERB *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005470`

## callees

- `0x1800092d0`
- `0x18000a718`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000930b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000930b`

## pseudocode

```c
__int64 __fastcall CPackage::InitVerbEnum(CPackage *this, struct tagOLEVERB *a2, int a3)
{
  _DWORD *v3; // rdi
  __int64 i; // rsi
  __int64 result; // rax

  v3 = (_DWORD *)((char *)this + 216);
  if ( *((_QWORD *)this + 28) )
  {
    for ( i = 0; (unsigned int)i < *v3; i = (unsigned int)(i + 1) )
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 28) + 24 * i + 8));
    operator delete(*((void **)this + 28));
  }
  result = 0;
  *((_QWORD *)this + 28) = a2;
  *v3 = a3;
  *((_DWORD *)this + 55) = 0;
  if ( !a2 )
    return 2147500037LL;
  return result;
}

```

## disassembly

```asm
0x1800092d0  push    rbx
0x1800092d2  push    rbp
0x1800092d3  push    rsi
0x1800092d4  push    rdi
0x1800092d5  push    r14
0x1800092d7  sub     rsp, 20h
0x1800092db  cmp     qword ptr [rcx+0E0h], 0
0x1800092e3  lea     rdi, [rcx+0D8h]
0x1800092ea  mov     r14d, r8d
0x1800092ed  mov     rbp, rdx
0x1800092f0  mov     rbx, rcx
0x1800092f3  jz      short loc_180009323
0x1800092f5  xor     esi, esi
0x1800092f7  cmp     [rdi], esi
0x1800092f9  jbe     short loc_180009317
0x1800092fb  mov     rcx, [rbx+0E0h]
0x180009302  lea     rdx, [rsi+rsi*2]
0x180009306  mov     rcx, [rcx+rdx*8+8]; pv
0x18000930b  call    cs:__imp_CoTaskMemFree
0x180009311  inc     esi
0x180009313  cmp     esi, [rdi]
0x180009315  jb      short loc_1800092FB
0x180009317  mov     rcx, [rbx+0E0h]; lpMem
0x18000931e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009323  xor     eax, eax
0x180009325  mov     [rbx+0E0h], rbp
0x18000932c  test    rbp, rbp
0x18000932f  mov     [rdi], r14d
0x180009332  mov     ecx, 80004005h
0x180009337  mov     dword ptr [rbx+0DCh], 0
0x180009341  cmovz   eax, ecx
0x180009344  add     rsp, 20h
0x180009348  pop     r14
0x18000934a  pop     rdi
0x18000934b  pop     rsi
0x18000934c  pop     rbp
0x18000934d  pop     rbx
0x18000934e  retn
```
