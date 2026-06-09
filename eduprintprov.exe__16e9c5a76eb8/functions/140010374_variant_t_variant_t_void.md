# _variant_t::~_variant_t(void)

- ea: `0x140010374`
- end: `0x14001037b`
- name: `??1_variant_t@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x14001365b`
- `0x14001366d`
- `0x14001367f`
- `0x140013691`
- `0x140013720`
- `0x1400137e6`
- `0x1400137f8`
- `0x14001380a`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x140010374`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall _variant_t::~_variant_t(VARIANTARG *pvarg)
{
  return VariantClear(pvarg);
}

```

## disassembly

```asm
0x140010374  jmp     cs:__imp_VariantClear
```
