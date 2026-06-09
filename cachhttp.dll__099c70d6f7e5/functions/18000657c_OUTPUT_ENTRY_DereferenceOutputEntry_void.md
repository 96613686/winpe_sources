# OUTPUT_ENTRY::DereferenceOutputEntry(void)

- ea: `0x18000657c`
- end: `0x1800065a9`
- name: `?DereferenceOutputEntry@OUTPUT_ENTRY@@QEAAXXZ`
- size: `45`
- prototype: `void __fastcall(OUTPUT_ENTRY *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002f20`
- `0x180004220`
- `0x180007470`

## callees

- `0x180005a4c`
- `0x180006338`
- `0x18000657c`

## pseudocode

```c
void __fastcall OUTPUT_ENTRY::DereferenceOutputEntry(OUTPUT_ENTRY *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      OUTPUT_ENTRY::~OUTPUT_ENTRY(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x18000657c  push    rbx
0x18000657e  sub     rsp, 20h
0x180006582  mov     rbx, rcx
0x180006585  or      eax, 0FFFFFFFFh
0x180006588  lock xadd [rcx], eax
0x18000658c  cmp     eax, 1
0x18000658f  jnz     short loc_1800065A3
0x180006591  test    rcx, rcx
0x180006594  jz      short loc_1800065A3
0x180006596  call    ??1OUTPUT_ENTRY@@AEAA@XZ; OUTPUT_ENTRY::~OUTPUT_ENTRY(void)
0x18000659b  mov     rcx, rbx; Block
0x18000659e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800065a3  add     rsp, 20h
0x1800065a7  pop     rbx
0x1800065a8  retn
```
