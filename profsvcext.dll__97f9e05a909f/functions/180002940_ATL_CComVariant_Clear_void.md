# ATL::CComVariant::Clear(void)

- ea: `0x180002940`
- end: `0x180002958`
- name: `?Clear@CComVariant@ATL@@QEAAJXZ`
- size: `24`
- prototype: `HRESULT __fastcall(VARIANTARG *this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001898`
- `0x1800019b0`
- `0x180002320`
- `0x1800025b0`
- `0x1800079f0`
- `0x18000f6f0`
- `0x1800101f4`
- `0x18001a5a8`
- `0x18001a91c`

## callees

- `0x180002940`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000294a`

## pseudocode

```c
HRESULT __fastcall ATL::CComVariant::Clear(VARIANTARG *this)
{
  if ( this->vt == 4095 )
    this->vt = 8;
  return VariantClear(this);
}

```

## disassembly

```asm
0x180002940  mov     eax, 0FFFh
0x180002945  cmp     [rcx], ax
0x180002948  jz      short loc_180002951
0x18000294a  jmp     cs:__imp_VariantClear
0x180002951  mov     word ptr [rcx], 8
0x180002956  jmp     short loc_18000294A
```
