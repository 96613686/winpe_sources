# ATL::CComVariant::~CComVariant(void)

- ea: `0x180005460`
- end: `0x180005476`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(VARIANTARG *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e670`
- `0x18001e690`
- `0x18001f174`
- `0x18001f186`
- `0x18001f198`

## callees

- `0x180005460`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000546f`

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
0x180005460  mov     eax, 0FFFh
0x180005465  cmp     [rcx], ax
0x180005468  jnz     short loc_18000546F
0x18000546a  mov     word ptr [rcx], 8
0x18000546f  jmp     cs:__imp_VariantClear
```
