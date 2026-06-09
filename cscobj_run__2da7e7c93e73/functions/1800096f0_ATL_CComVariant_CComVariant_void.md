# ATL::CComVariant::~CComVariant(void)

- ea: `0x1800096f0`
- end: `0x1800096f7`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002ad50`
- `0x18002aed2`
- `0x18002af62`
- `0x18002af74`
- `0x18002af98`
- `0x18002afe0`
- `0x18002b004`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800096f0`

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
0x1800096f0  jmp     cs:__imp_VariantClear
```
