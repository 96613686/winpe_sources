# ATL::CComVariant::~CComVariant(void)

- ea: `0x18000ddf0`
- end: `0x18000ddf7`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `11`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180034b2c`
- `0x180034ce6`
- `0x180034f2a`
- `0x180035c39`
- `0x180035c4b`
- `0x180035c5d`
- `0x180035c6f`
- `0x180035fa9`
- `0x180035fbb`
- `0x180035fcd`
- `0x180035fdf`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000ddf0`

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
0x18000ddf0  jmp     cs:__imp_VariantClear
```
