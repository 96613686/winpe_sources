# _variant_t::_variant_t(tagVARIANT const &)

- ea: `0x180047b30`
- end: `0x180047b6c`
- name: `??0_variant_t@@QEAA@AEBUtagVARIANT@@@Z`
- size: `60`
- prototype: `void __fastcall(_variant_t *this, const tagVARIANT *varSrc)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180048378`
- `0x180048558`

## callees

- `0x1800471bc`
- `0x180047b30`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180047b40`
- `OLEAUT32!__imp_VariantInit` at `0x180047b40`
- `OLEAUT32!__imp_VariantCopy` at `0x180047b4c`
- `OLEAUT32!__imp_VariantCopy` at `0x180047b4c`

## pseudocode

```c
void __fastcall _variant_t::_variant_t(_variant_t *this, const tagVARIANT *varSrc)
{
  int v4; // eax

  VariantInit(this);
  v4 = VariantCopy(this, varSrc);
  if ( v4 < 0 )
    _com_issue_error(v4);
}

```

## disassembly

```asm
0x180047b30  mov     [rsp+arg_0], rbx
0x180047b35  push    rdi
0x180047b36  sub     rsp, 20h
0x180047b3a  mov     rbx, varSrc
0x180047b3d  mov     rdi, this
0x180047b40  call    cs:__imp_VariantInit
0x180047b46  mov     varSrc, rbx; pvargSrc
0x180047b49  mov     this, rdi; pvargDest
0x180047b4c  call    cs:__imp_VariantCopy
0x180047b52  test    eax, eax
0x180047b54  jns     short loc_180047B5E
0x180047b56  mov     ecx, eax; hr
0x180047b58  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180047b5e  mov     rbx, [rsp+28h+arg_0]
0x180047b63  mov     rax, rdi
0x180047b66  add     rsp, 20h
0x180047b6a  pop     rdi
0x180047b6b  retn
```
