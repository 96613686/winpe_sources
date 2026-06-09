# _VolumePropPage::CreateInstance_::_1_::dtor$0

- ea: `0x18001e125`
- end: `0x18001e142`
- name: `_VolumePropPage::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001534`

## pseudocode

```c
void __fastcall VolumePropPage::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 104));
}

```

## disassembly

```asm
0x18001e125  push    rbp
0x18001e127  sub     rsp, 20h
0x18001e12b  mov     rbp, rdx
0x18001e12e  mov     edx, 0B8h; unsigned __int64
0x18001e133  mov     rcx, [rbp+68h]; void *
0x18001e137  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e13c  add     rsp, 20h
0x18001e140  pop     rbp
0x18001e141  retn
```
