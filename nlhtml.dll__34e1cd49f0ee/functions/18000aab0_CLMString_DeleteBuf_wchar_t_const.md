# CLMString::DeleteBuf(wchar_t const *)

- ea: `0x18000aab0`
- end: `0x18000aaeb`
- name: `?DeleteBuf@CLMString@@IEAAXPEB_W@Z`
- size: `59`
- prototype: `void __fastcall(CLMString *__hidden this, const wchar_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800064c4`
- `0x180008690`
- `0x18000aef4`
- `0x18000af28`
- `0x18000bea0`
- `0x18000c5f0`
- `0x18000d240`
- `0x180011530`
- `0x18001f53c`
- `0x180022488`

## callees

- `0x18000aab0`
- `0x18001bf18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000aac7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000aac7`

## pseudocode

```c
void __fastcall CLMString::DeleteBuf(CLMString *this, wchar_t *a2)
{
  wchar_t *v3; // rcx

  v3 = (wchar_t *)*((_QWORD *)this + 1);
  if ( v3 && v3 != a2 )
  {
    free(v3);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl) )
      *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000aab0  push    rbx
0x18000aab2  sub     rsp, 20h
0x18000aab6  mov     rbx, rcx
0x18000aab9  mov     rcx, [rcx+8]; Block
0x18000aabd  test    rcx, rcx
0x18000aac0  jz      short loc_18000AAE5
0x18000aac2  cmp     rcx, rdx
0x18000aac5  jz      short loc_18000AAE5
0x18000aac7  call    cs:__imp_free
0x18000aacd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x18000aad4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x18000aad9  test    al, al
0x18000aadb  jz      short loc_18000AAE5
0x18000aadd  mov     qword ptr [rbx+8], 0
0x18000aae5  add     rsp, 20h
0x18000aae9  pop     rbx
0x18000aaea  retn
```
