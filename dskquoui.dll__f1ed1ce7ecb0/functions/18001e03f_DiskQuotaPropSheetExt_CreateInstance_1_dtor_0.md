# _DiskQuotaPropSheetExt::CreateInstance_::_1_::dtor$0

- ea: `0x18001e03f`
- end: `0x18001e05c`
- name: `_DiskQuotaPropSheetExt::CreateInstance_::_1_::dtor$0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180001534`

## pseudocode

```c
void __fastcall DiskQuotaPropSheetExt::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x18001e03f  push    rbp
0x18001e041  sub     rsp, 20h
0x18001e045  mov     rbp, rdx
0x18001e048  mov     edx, 50h ; 'P'; unsigned __int64
0x18001e04d  mov     rcx, [rbp+48h]; void *
0x18001e051  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e056  add     rsp, 20h
0x18001e05a  pop     rbp
0x18001e05b  retn
```
