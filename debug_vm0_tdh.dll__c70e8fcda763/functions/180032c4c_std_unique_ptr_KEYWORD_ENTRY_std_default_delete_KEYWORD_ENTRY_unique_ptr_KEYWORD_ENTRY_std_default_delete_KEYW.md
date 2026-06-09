# std::unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>>::~unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>>(void)

- ea: `0x180032c4c`
- end: `0x180032c75`
- name: `??1?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001bdb8`
- `0x18002cd3c`
- `0x180033f84`
- `0x180038228`
- `0x180038498`
- `0x18004a608`
- `0x18004b22a`
- `0x18004b23c`

## callees

- `0x180020828`
- `0x180032c4c`
- `0x180033590`

## pseudocode

```c
void __fastcall std::unique_ptr<KEYWORD_ENTRY>::~unique_ptr<KEYWORD_ENTRY>(KEYWORD_ENTRY **a1)
{
  KEYWORD_ENTRY *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    KEYWORD_ENTRY::~KEYWORD_ENTRY(*a1);
    operator delete(v1, (const struct std::nothrow_t *)0x78);
  }
}

```

## disassembly

```asm
0x180032c4c  push    rbx
0x180032c4e  sub     rsp, 20h
0x180032c52  mov     rbx, [rcx]
0x180032c55  test    rbx, rbx
0x180032c58  jz      short loc_180032C6F
0x180032c5a  mov     rcx, rbx; this
0x180032c5d  call    ??1KEYWORD_ENTRY@@QEAA@XZ; KEYWORD_ENTRY::~KEYWORD_ENTRY(void)
0x180032c62  mov     edx, 78h ; 'x'; struct std::nothrow_t *
0x180032c67  mov     rcx, rbx; void *
0x180032c6a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032c6f  add     rsp, 20h
0x180032c73  pop     rbx
0x180032c74  retn
```
