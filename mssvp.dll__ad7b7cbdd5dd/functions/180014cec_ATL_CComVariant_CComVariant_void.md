# ATL::CComVariant::~CComVariant(void)

- ea: `0x180014cec`
- end: `0x180014cf3`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `16`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003a5fb`
- `0x18003a60d`
- `0x18003a643`
- `0x18003a667`
- `0x18003a7cb`
- `0x18003a7dd`
- `0x18003a7ef`
- `0x18003a813`
- `0x18003a825`
- `0x18003a875`
- `0x18003aa47`
- `0x18003aa59`
- `0x18003aa6b`
- `0x18003aa7d`
- `0x18003aac5`
- `0x18003aafb`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180014cec`

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
0x180014cec  jmp     cs:__imp_VariantClear
```
