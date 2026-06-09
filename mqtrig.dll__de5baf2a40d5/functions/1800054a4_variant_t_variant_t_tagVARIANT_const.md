# _variant_t::_variant_t(tagVARIANT const &)

- ea: `0x1800054a4`
- end: `0x1800054e0`
- name: `??0_variant_t@@QEAA@AEBUtagVARIANT@@@Z`
- size: `60`
- prototype: `VARIANTARG *__fastcall(VARIANTARG *pvargDest, VARIANTARG *pvargSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005df4`

## callees

- `0x1800054a4`
- `0x180014920`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800054b4`
- `OLEAUT32!__imp_VariantInit` at `0x1800054b4`
- `OLEAUT32!__imp_VariantCopy` at `0x1800054c0`
- `OLEAUT32!__imp_VariantCopy` at `0x1800054c0`

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
0x1800054a4  mov     [rsp+arg_0], rbx
0x1800054a9  push    rdi
0x1800054aa  sub     rsp, 20h
0x1800054ae  mov     rbx, rdx
0x1800054b1  mov     rdi, rcx
0x1800054b4  call    cs:__imp_VariantInit
0x1800054ba  mov     rdx, rbx; pvargSrc
0x1800054bd  mov     rcx, rdi; pvargDest
0x1800054c0  call    cs:__imp_VariantCopy
0x1800054c6  test    eax, eax
0x1800054c8  jns     short loc_1800054D2
0x1800054ca  mov     ecx, eax; int
0x1800054cc  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800054d2  mov     rbx, [rsp+28h+arg_0]
0x1800054d7  mov     rax, rdi
0x1800054da  add     rsp, 20h
0x1800054de  pop     rdi
0x1800054df  retn
```
