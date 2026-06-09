# ATL::CComVariant::~CComVariant(void)

- ea: `0x180005200`
- end: `0x180005216`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(VARIANTARG *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009ed8`

## callees

- `0x180005200`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000520f`

## pseudocode

```c
void __fastcall ATL::CComVariant::~CComVariant(VARIANTARG *this)
{
  if ( this->vt == 4095 )
    this->vt = 8;
  VariantClear(this);
}

```

## disassembly

```asm
0x180005200  mov     eax, 0FFFh
0x180005205  cmp     [rcx], ax
0x180005208  jnz     short loc_18000520F
0x18000520a  mov     word ptr [rcx], 8
0x18000520f  jmp     cs:__imp_VariantClear
```
