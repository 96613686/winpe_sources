# ACCESS_META_STORED_CONTEXT::~ACCESS_META_STORED_CONTEXT(void)

- ea: `0x180002e78`
- end: `0x180002edd`
- name: `??1ACCESS_META_STORED_CONTEXT@@EEAA@XZ`
- size: `101`
- prototype: `void __fastcall(ACCESS_META_STORED_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002f00`

## callees

- `0x1800010c8`
- `0x180002e78`
- `0x180002ee4`

## pseudocode

```c
void __fastcall ACCESS_META_STORED_CONTEXT::~ACCESS_META_STORED_CONTEXT(ACCESS_META_STORED_CONTEXT *this)
{
  __int64 v2; // rax
  void *v3; // r14
  __int64 v4; // rdi
  IP_RESTRICTION_LIST_ENTRY *i; // rbx

  *(_QWORD *)this = &ACCESS_META_STORED_CONTEXT::`vftable';
  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    v3 = (void *)(v2 - 8);
    v4 = *(_QWORD *)(v2 - 8);
    for ( i = (IP_RESTRICTION_LIST_ENTRY *)(v2 + (v4 << 8)); v4; --v4 )
    {
      i = (IP_RESTRICTION_LIST_ENTRY *)((char *)i - 256);
      IP_RESTRICTION_LIST_ENTRY::~IP_RESTRICTION_LIST_ENTRY(i);
    }
    operator delete(v3);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180002e78  push    rbx
0x180002e7a  push    rsi
0x180002e7b  push    rdi
0x180002e7c  push    r14
0x180002e7e  sub     rsp, 28h
0x180002e82  lea     rax, ??_7ACCESS_META_STORED_CONTEXT@@6B@; const ACCESS_META_STORED_CONTEXT::`vftable'
0x180002e89  mov     rsi, rcx
0x180002e8c  mov     [rcx], rax
0x180002e8f  mov     rax, [rcx+18h]
0x180002e93  test    rax, rax
0x180002e96  jz      short loc_180002ED3
0x180002e98  lea     r14, [rax-8]
0x180002e9c  mov     rdi, [r14]
0x180002e9f  mov     rbx, rdi
0x180002ea2  shl     rbx, 8
0x180002ea6  add     rbx, rax
0x180002ea9  test    rdi, rdi
0x180002eac  jz      short loc_180002EC3
0x180002eae  sub     rbx, 100h
0x180002eb5  mov     rcx, rbx; this
0x180002eb8  call    ??1IP_RESTRICTION_LIST_ENTRY@@QEAA@XZ; IP_RESTRICTION_LIST_ENTRY::~IP_RESTRICTION_LIST_ENTRY(void)
0x180002ebd  sub     rdi, 1
0x180002ec1  jnz     short loc_180002EAE
0x180002ec3  mov     rcx, r14; Block
0x180002ec6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ecb  mov     qword ptr [rsi+18h], 0
0x180002ed3  add     rsp, 28h
0x180002ed7  pop     r14
0x180002ed9  pop     rdi
0x180002eda  pop     rsi
0x180002edb  pop     rbx
0x180002edc  retn
```
