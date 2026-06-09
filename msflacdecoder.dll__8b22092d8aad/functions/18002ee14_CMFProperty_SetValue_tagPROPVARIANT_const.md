# CMFProperty::SetValue(tagPROPVARIANT const &)

- ea: `0x18002ee14`
- end: `0x18002ee49`
- name: `?SetValue@CMFProperty@@AEAAJAEBUtagPROPVARIANT@@@Z`
- size: `53`
- prototype: `int(CMFProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002ebf0`

## callees

- `0x18002ee14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002ee38`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002ee38`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ee28`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002ee28`

## pseudocode

```c
int __fastcall CMFProperty::SetValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  PROPVARIANT *v2; // rbx
  int result; // eax

  v2 = this + 4;
  result = PropVariantClear(this + 4);
  if ( result >= 0 )
    return PropVariantCopy(v2, a2);
  return result;
}

```

## disassembly

```asm
0x18002ee14  mov     [rsp+arg_0], rbx
0x18002ee19  push    rdi
0x18002ee1a  sub     rsp, 20h
0x18002ee1e  lea     rbx, [rcx+60h]
0x18002ee22  mov     rdi, rdx
0x18002ee25  mov     rcx, rbx; pvar
0x18002ee28  call    cs:__imp_PropVariantClear
0x18002ee2e  test    eax, eax
0x18002ee30  js      short loc_18002EE3E
0x18002ee32  mov     rdx, rdi; pvarSrc
0x18002ee35  mov     rcx, rbx; pvarDest
0x18002ee38  call    cs:__imp_PropVariantCopy
0x18002ee3e  mov     rbx, [rsp+28h+arg_0]
0x18002ee43  add     rsp, 20h
0x18002ee47  pop     rdi
0x18002ee48  retn
```
