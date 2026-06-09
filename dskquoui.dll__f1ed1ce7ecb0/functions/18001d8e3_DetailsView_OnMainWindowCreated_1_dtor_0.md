# _DetailsView::OnMainWindowCreated_::_1_::dtor$0

- ea: `0x18001d8e3`
- end: `0x18001d903`
- name: `_DetailsView::OnMainWindowCreated_::_1_::dtor$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001534`

## pseudocode

```c
void __fastcall DetailsView::OnMainWindowCreated_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 136));
}

```

## disassembly

```asm
0x18001d8e3  push    rbp
0x18001d8e5  sub     rsp, 20h
0x18001d8e9  mov     rbp, rdx
0x18001d8ec  mov     edx, 48h ; 'H'; unsigned __int64
0x18001d8f1  mov     rcx, [rbp+88h]; void *
0x18001d8f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d8fd  add     rsp, 20h
0x18001d901  pop     rbp
0x18001d902  retn
```
