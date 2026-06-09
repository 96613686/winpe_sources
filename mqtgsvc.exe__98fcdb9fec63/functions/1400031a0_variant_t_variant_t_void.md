# _variant_t::~_variant_t(void)

- ea: `0x1400031a0`
- end: `0x1400031bb`
- name: `??1_variant_t@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(VARIANTARG *this)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005e40`
- `0x14000655c`
- `0x14000858c`
- `0x140009358`
- `0x1400096ac`
- `0x1400097c4`
- `0x1400098f4`
- `0x140009994`
- `0x14000d648`
- `0x14001d0cc`
- `0x14001d0f8`
- `0x14001d124`
- `0x14001d4a7`
- `0x14001d51c`
- `0x14001d80d`
- `0x14001d81f`
- `0x14001d843`
- `0x14001dabf`
- `0x14001daf1`
- `0x14001db23`
- `0x14001db55`
- `0x14001db67`
- `0x14001db8b`
- `0x14001e358`
- `0x14001e37c`
- `0x14001f250`

## callees

- `0x1400031a0`
- `0x14000ec24`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1400031a4`
- `OLEAUT32!__imp_VariantClear` at `0x1400031a4`

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
0x1400031a0  sub     rsp, 28h
0x1400031a4  call    cs:__imp_VariantClear
0x1400031aa  test    eax, eax
0x1400031ac  jns     short loc_1400031B6
0x1400031ae  mov     ecx, eax; int
0x1400031b0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400031b6  add     rsp, 28h
0x1400031ba  retn
```
