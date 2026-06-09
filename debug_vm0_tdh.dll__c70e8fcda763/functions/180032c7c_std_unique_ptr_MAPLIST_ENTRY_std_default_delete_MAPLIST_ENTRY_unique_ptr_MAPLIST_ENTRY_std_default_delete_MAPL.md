# std::unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>>::~unique_ptr<MAPLIST_ENTRY,std::default_delete<MAPLIST_ENTRY>>(void)

- ea: `0x180032c7c`
- end: `0x180032ca5`
- name: `??1?$unique_ptr@VMAPLIST_ENTRY@@U?$default_delete@VMAPLIST_ENTRY@@@std@@@std@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002cd74`
- `0x180038a44`
- `0x180039780`
- `0x18004a1e0`
- `0x18004af08`
- `0x18004b28c`
- `0x18004b29e`
- `0x18004b2ee`
- `0x18004b300`

## callees

- `0x180020828`
- `0x180032c7c`
- `0x180033624`

## pseudocode

```c
void __fastcall std::unique_ptr<MAPLIST_ENTRY>::~unique_ptr<MAPLIST_ENTRY>(MAPLIST_ENTRY **a1)
{
  MAPLIST_ENTRY *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    MAPLIST_ENTRY::~MAPLIST_ENTRY(*a1);
    operator delete(v1, (const struct std::nothrow_t *)0x88);
  }
}

```

## disassembly

```asm
0x180032c7c  push    rbx
0x180032c7e  sub     rsp, 20h
0x180032c82  mov     rbx, [rcx]
0x180032c85  test    rbx, rbx
0x180032c88  jz      short loc_180032C9F
0x180032c8a  mov     rcx, rbx; this
0x180032c8d  call    ??1MAPLIST_ENTRY@@QEAA@XZ; MAPLIST_ENTRY::~MAPLIST_ENTRY(void)
0x180032c92  mov     edx, 88h; struct std::nothrow_t *
0x180032c97  mov     rcx, rbx; void *
0x180032c9a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032c9f  add     rsp, 20h
0x180032ca3  pop     rbx
0x180032ca4  retn
```
