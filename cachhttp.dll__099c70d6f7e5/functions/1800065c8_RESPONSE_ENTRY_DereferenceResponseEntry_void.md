# RESPONSE_ENTRY::DereferenceResponseEntry(void)

- ea: `0x1800065c8`
- end: `0x1800065f6`
- name: `?DereferenceResponseEntry@RESPONSE_ENTRY@@QEAAXXZ`
- size: `46`
- prototype: `void __fastcall(RESPONSE_ENTRY *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002f20`
- `0x180004220`
- `0x1800064b0`
- `0x1800064bc`
- `0x1800064fc`
- `0x180007d40`

## callees

- `0x180005a4c`
- `0x1800065c8`
- `0x180007b08`

## pseudocode

```c
void __fastcall RESPONSE_ENTRY::DereferenceResponseEntry(RESPONSE_ENTRY *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      RESPONSE_ENTRY::~RESPONSE_ENTRY(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x1800065c8  push    rbx
0x1800065ca  sub     rsp, 20h
0x1800065ce  mov     rbx, rcx
0x1800065d1  or      eax, 0FFFFFFFFh
0x1800065d4  lock xadd [rcx+8], eax
0x1800065d9  cmp     eax, 1
0x1800065dc  jnz     short loc_1800065F0
0x1800065de  test    rcx, rcx
0x1800065e1  jz      short loc_1800065F0
0x1800065e3  call    ??1RESPONSE_ENTRY@@AEAA@XZ; RESPONSE_ENTRY::~RESPONSE_ENTRY(void)
0x1800065e8  mov     rcx, rbx; Block
0x1800065eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800065f0  add     rsp, 20h
0x1800065f4  pop     rbx
0x1800065f5  retn
```
