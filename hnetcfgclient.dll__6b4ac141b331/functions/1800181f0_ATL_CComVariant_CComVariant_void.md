# ATL::CComVariant::~CComVariant(void)

- ea: `0x1800181f0`
- end: `0x1800181f7`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002dacd`
- `0x18002dadf`
- `0x18002daf1`
- `0x18002db03`
- `0x18002db27`
- `0x18002db4b`
- `0x18002db5d`
- `0x18002db6f`
- `0x18002db81`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800181f0`

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
0x1800181f0  jmp     cs:__imp_VariantClear
```
