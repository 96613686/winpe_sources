# _variant_t::~_variant_t(void)

- ea: `0x18000774c`
- end: `0x180007767`
- name: `??1_variant_t@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(_variant_t *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e672`
- `0x18000e70a`
- `0x18000e788`
- `0x18000ea2b`
- `0x18000ed31`
- `0x18000f0b0`

## callees

- `0x18000774c`
- `0x18000db68`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180007750`
- `OLEAUT32!__imp_VariantClear` at `0x180007750`

## pseudocode

```c
void __fastcall _variant_t::~_variant_t(VARIANTARG *this)
{
  HRESULT v1; // eax

  v1 = VariantClear(this);
  if ( v1 < 0 )
    _com_issue_error(v1);
}

```

## disassembly

```asm
0x18000774c  sub     rsp, 28h
0x180007750  call    cs:__imp_VariantClear
0x180007756  test    eax, eax
0x180007758  js      short loc_18000775F
0x18000775a  add     rsp, 28h
0x18000775e  retn
0x18000775f  mov     ecx, eax; int
0x180007761  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
