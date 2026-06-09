# CMFProperty::SetValue(tagPROPVARIANT const &)

- ea: `0x180056504`
- end: `0x180056539`
- name: `?SetValue@CMFProperty@@AEAAJAEBUtagPROPVARIANT@@@Z`
- size: `53`
- prototype: `int(CMFProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800561f0`

## callees

- `0x180056504`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180056528`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180056528`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056518`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056518`

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
0x180056504  mov     [rsp+arg_0], rbx
0x180056509  push    rdi
0x18005650a  sub     rsp, 20h
0x18005650e  lea     rbx, [rcx+60h]
0x180056512  mov     rdi, rdx
0x180056515  mov     rcx, rbx; pvar
0x180056518  call    cs:__imp_PropVariantClear
0x18005651e  test    eax, eax
0x180056520  js      short loc_18005652E
0x180056522  mov     rdx, rdi; pvarSrc
0x180056525  mov     rcx, rbx; pvarDest
0x180056528  call    cs:__imp_PropVariantCopy
0x18005652e  mov     rbx, [rsp+28h+arg_0]
0x180056533  add     rsp, 20h
0x180056537  pop     rdi
0x180056538  retn
```
