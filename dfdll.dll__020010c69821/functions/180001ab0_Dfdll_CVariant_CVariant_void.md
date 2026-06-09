# Dfdll::CVariant::~CVariant(void)

- ea: `0x180001ab0`
- end: `0x180001ace`
- name: `??1CVariant@Dfdll@@UEAA@XZ`
- size: `30`
- prototype: `void __fastcall(Dfdll::CVariant *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001f062`
- `0x18001f182`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180001ac2`
- `OLEAUT32!__imp_VariantClear` at `0x180001ac2`

## pseudocode

```c
void __fastcall Dfdll::CVariant::~CVariant(Dfdll::CVariant *this)
{
  *(_QWORD *)this = &Dfdll::CVariant::`vftable';
  VariantClear((VARIANTARG *)((char *)this + 8));
}

```

## disassembly

```asm
0x180001ab0  sub     rsp, 28h
0x180001ab4  lea     rax, ??_7CVariant@Dfdll@@6B@; const Dfdll::CVariant::`vftable'
0x180001abb  mov     [rcx], rax
0x180001abe  add     rcx, 8; pvarg
0x180001ac2  call    cs:__imp_VariantClear
0x180001ac8  nop
0x180001ac9  add     rsp, 28h
0x180001acd  retn
```
