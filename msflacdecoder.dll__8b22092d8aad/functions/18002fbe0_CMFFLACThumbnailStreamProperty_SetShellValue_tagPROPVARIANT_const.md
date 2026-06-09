# CMFFLACThumbnailStreamProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x18002fbe0`
- end: `0x18002fc2e`
- name: `?SetShellValue@CMFFLACThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `78`
- prototype: `int(CMFFLACThumbnailStreamProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002fbe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002fc18`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002fc18`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fbf9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fc07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fbf9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fc07`

## pseudocode

```c
int __fastcall CMFFLACThumbnailStreamProperty::SetShellValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  int result; // eax

  result = PropVariantClear(this + 4);
  if ( result >= 0 )
  {
    result = PropVariantClear(this + 5);
    if ( result >= 0 )
      return PropVariantCopy(this + 4, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18002fbe0  mov     [rsp+arg_0], rbx
0x18002fbe5  mov     [rsp+arg_8], rsi
0x18002fbea  push    rdi
0x18002fbeb  sub     rsp, 20h
0x18002fbef  mov     rdi, rcx
0x18002fbf2  mov     rsi, rdx
0x18002fbf5  add     rcx, 60h ; '`'; pvar
0x18002fbf9  call    cs:__imp_PropVariantClear
0x18002fbff  test    eax, eax
0x18002fc01  js      short loc_18002FC1E
0x18002fc03  lea     rcx, [rdi+78h]; pvar
0x18002fc07  call    cs:__imp_PropVariantClear
0x18002fc0d  test    eax, eax
0x18002fc0f  js      short loc_18002FC1E
0x18002fc11  mov     rdx, rsi; pvarSrc
0x18002fc14  lea     rcx, [rdi+60h]; pvarDest
0x18002fc18  call    cs:__imp_PropVariantCopy
0x18002fc1e  mov     rbx, [rsp+28h+arg_0]
0x18002fc23  mov     rsi, [rsp+28h+arg_8]
0x18002fc28  add     rsp, 20h
0x18002fc2c  pop     rdi
0x18002fc2d  retn
```
