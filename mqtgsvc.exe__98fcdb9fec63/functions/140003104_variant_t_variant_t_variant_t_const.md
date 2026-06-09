# _variant_t::_variant_t(_variant_t const &)

- ea: `0x140003104`
- end: `0x140003140`
- name: `??0_variant_t@@QEAA@AEBV0@@Z`
- size: `60`
- prototype: `VARIANTARG *__fastcall(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000858c`
- `0x1400096ac`
- `0x140009e74`

## callees

- `0x140003104`
- `0x14000ec24`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140003114`
- `OLEAUT32!__imp_VariantInit` at `0x140003114`
- `OLEAUT32!__imp_VariantCopy` at `0x140003120`
- `OLEAUT32!__imp_VariantCopy` at `0x140003120`

## pseudocode

```c
VARIANTARG *__fastcall _variant_t::_variant_t(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)
{
  HRESULT v4; // eax

  VariantInit(pvargDest);
  v4 = VariantCopy(pvargDest, pvargSrc);
  if ( v4 < 0 )
    _com_issue_error(v4);
  return pvargDest;
}

```

## disassembly

```asm
0x140003104  mov     [rsp+arg_0], rbx
0x140003109  push    rdi
0x14000310a  sub     rsp, 20h
0x14000310e  mov     rbx, rdx
0x140003111  mov     rdi, rcx
0x140003114  call    cs:__imp_VariantInit
0x14000311a  mov     rdx, rbx; pvargSrc
0x14000311d  mov     rcx, rdi; pvargDest
0x140003120  call    cs:__imp_VariantCopy
0x140003126  test    eax, eax
0x140003128  jns     short loc_140003132
0x14000312a  mov     ecx, eax; int
0x14000312c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140003132  mov     rbx, [rsp+28h+arg_0]
0x140003137  mov     rax, rdi
0x14000313a  add     rsp, 20h
0x14000313e  pop     rdi
0x14000313f  retn
```
