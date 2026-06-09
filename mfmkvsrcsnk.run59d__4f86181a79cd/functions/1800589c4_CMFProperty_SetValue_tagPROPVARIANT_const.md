# CMFProperty::SetValue(tagPROPVARIANT const &)

- ea: `0x1800589c4`
- end: `0x180058a06`
- name: `?SetValue@CMFProperty@@AEAAJAEBUtagPROPVARIANT@@@Z`
- size: `66`
- prototype: `int(CMFProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800586a0`

## callees

- `0x1800589c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800589ee`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800589ee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800589d8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800589d8`

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
0x1800589c4  mov     [rsp+arg_0], rbx
0x1800589c9  push    rdi
0x1800589ca  sub     rsp, 20h
0x1800589ce  lea     rbx, [rcx+60h]
0x1800589d2  mov     rdi, rdx
0x1800589d5  mov     rcx, rbx; pvar
0x1800589d8  call    cs:__imp_PropVariantClear
0x1800589df  nop     dword ptr [rax+rax+00h]
0x1800589e4  test    eax, eax
0x1800589e6  js      short loc_1800589FA
0x1800589e8  mov     rdx, rdi; pvarSrc
0x1800589eb  mov     rcx, rbx; pvarDest
0x1800589ee  call    cs:__imp_PropVariantCopy
0x1800589f5  nop     dword ptr [rax+rax+00h]
0x1800589fa  mov     rbx, [rsp+28h+arg_0]
0x1800589ff  add     rsp, 20h
0x180058a03  pop     rdi
0x180058a04  retn
```
