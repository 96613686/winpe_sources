# ATL::CComVariant::~CComVariant(void)

- ea: `0x1800139f0`
- end: `0x180013a06`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(ATL::CComVariant *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b770`

## callees

- `0x1800139f0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800139ff`

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
0x1800139f0  mov     eax, 0FFFh
0x1800139f5  cmp     [rcx], ax
0x1800139f8  jnz     short loc_1800139FF
0x1800139fa  mov     word ptr [rcx], 8
0x1800139ff  jmp     cs:__imp_VariantClear
```
