# CComAutoCriticalSection::`vector deleting destructor'(uint)

- ea: `0x1800ad3e0`
- end: `0x1800ad41e`
- name: `??_ECComAutoCriticalSection@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(CComAutoCriticalSection *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180026e00`
- `0x1800ad3e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ad3fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ad3fd`

## pseudocode

```c
CComAutoCriticalSection *__fastcall CComAutoCriticalSection::`vector deleting destructor'(
        CComAutoCriticalSection *this,
        char a2)
{
  *(_QWORD *)this = &CComAutoCriticalSection::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800ad3e0  mov     [rsp+arg_0], rbx
0x1800ad3e5  push    rdi
0x1800ad3e6  sub     rsp, 20h
0x1800ad3ea  lea     rax, ??_7CComAutoCriticalSection@@6B@; const CComAutoCriticalSection::`vftable'
0x1800ad3f1  mov     rdi, rcx
0x1800ad3f4  mov     [rcx], rax
0x1800ad3f7  mov     ebx, edx
0x1800ad3f9  add     rcx, 8; lpCriticalSection
0x1800ad3fd  call    cs:__imp_DeleteCriticalSection
0x1800ad403  test    bl, 1
0x1800ad406  jz      short loc_1800AD410
0x1800ad408  mov     rcx, rdi; Block
0x1800ad40b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ad410  mov     rbx, [rsp+28h+arg_0]
0x1800ad415  mov     rax, rdi
0x1800ad418  add     rsp, 20h
0x1800ad41c  pop     rdi
0x1800ad41d  retn
```
