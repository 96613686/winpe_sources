# ATL::CComVariant::~CComVariant(void)

- ea: `0x180012680`
- end: `0x180012687`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800260a0`
- `0x180026276`
- `0x1800262ac`
- `0x1800262be`
- `0x1800262d0`
- `0x1800262e2`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180012680`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall ATL::CComVariant::~CComVariant(VARIANTARG *pvarg)
{
  return VariantClear(pvarg);
}

```

## disassembly

```asm
0x180012680  jmp     cs:__imp_VariantClear
```
