# std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>::~unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>(void)

- ea: `0x180032cac`
- end: `0x180032cd5`
- name: `??1?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002cdac`
- `0x18003410c`
- `0x1800342ec`
- `0x180038d38`
- `0x18003b6f8`
- `0x18004aee4`
- `0x18004aef6`
- `0x18004b2b0`
- `0x18004b2c2`
- `0x18004b5f3`

## callees

- `0x180020828`
- `0x180032cac`
- `0x180033590`

## pseudocode

```c
void __fastcall std::unique_ptr<OPCODE_ENTRY>::~unique_ptr<OPCODE_ENTRY>(KEYWORD_ENTRY **a1)
{
  KEYWORD_ENTRY *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    KEYWORD_ENTRY::~KEYWORD_ENTRY(*a1);
    operator delete(v1, (const struct std::nothrow_t *)0x88);
  }
}

```

## disassembly

```asm
0x180032cac  push    rbx
0x180032cae  sub     rsp, 20h
0x180032cb2  mov     rbx, [rcx]
0x180032cb5  test    rbx, rbx
0x180032cb8  jz      short loc_180032CCF
0x180032cba  mov     rcx, rbx; this
0x180032cbd  call    ??1KEYWORD_ENTRY@@QEAA@XZ; KEYWORD_ENTRY::~KEYWORD_ENTRY(void)
0x180032cc2  mov     edx, 88h; struct std::nothrow_t *
0x180032cc7  mov     rcx, rbx; void *
0x180032cca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032ccf  add     rsp, 20h
0x180032cd3  pop     rbx
0x180032cd4  retn
```
