# ATL::CComVariant::~CComVariant(void)

- ea: `0x180015224`
- end: `0x18001522b`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001aea1`
- `0x18001aeb3`
- `0x18001af1f`
- `0x18001af31`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180015224`

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
0x180015224  jmp     cs:__imp_VariantClear
```
