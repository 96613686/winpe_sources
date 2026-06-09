# _CreatePropertyBag_::_1_::dtor$34

- ea: `0x14001d80d`
- end: `0x14001d819`
- name: `_CreatePropertyBag_::_1_::dtor$34`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400031a0`

## pseudocode

```c
void __fastcall CreatePropertyBag_::_1_::dtor_34(__int64 a1, __int64 a2)
{
  _variant_t::~_variant_t((VARIANTARG *)(a2 + 80));
}

```

## disassembly

```asm
0x14001d80d  lea     rcx, [rdx+50h]; this
0x14001d814  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
