# std::default_delete<CAlpcView>::operator()(CAlpcView *)

- ea: `0x18001114c`
- end: `0x180011174`
- name: `??R?$default_delete@VCAlpcView@@@std@@QEBAXPEAVCAlpcView@@@Z`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000ad58`
- `0x18000b880`
- `0x18000bab0`
- `0x18001512c`
- `0x180015160`

## callees

- `0x18000d470`
- `0x18001114c`
- `0x180015368`

## pseudocode

```c
void __fastcall std::default_delete<CAlpcView>::operator()(__int64 a1, CAlpcView *a2)
{
  if ( a2 )
  {
    CAlpcView::~CAlpcView(a2);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18001114c  test    rdx, rdx
0x18001114f  jz      short locret_180011173
0x180011151  push    rbx
0x180011152  sub     rsp, 20h
0x180011156  mov     rcx, rdx; this
0x180011159  mov     rbx, rdx
0x18001115c  call    ??1CAlpcView@@QEAA@XZ; CAlpcView::~CAlpcView(void)
0x180011161  mov     edx, 30h ; '0'; unsigned __int64
0x180011166  mov     rcx, rbx; void *
0x180011169  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001116e  add     rsp, 20h
0x180011172  pop     rbx
0x180011173  retn
```
