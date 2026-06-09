# CLMString::DeleteBuf(wchar_t const *)

- ea: `0x180005720`
- end: `0x18000575b`
- name: `?DeleteBuf@CLMString@@IEAAXPEB_W@Z`
- size: `59`
- prototype: `void __fastcall(CLMString *__hidden this, const wchar_t *)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180003970`
- `0x1800048f0`
- `0x180004f60`
- `0x1800052a0`
- `0x1800055b0`
- `0x1800055f0`
- `0x180006454`
- `0x180006cd0`
- `0x180007078`
- `0x180007158`
- `0x1800071c0`
- `0x18000b3a0`
- `0x18000cc1c`
- `0x18000e4c8`

## callees

- `0x180005720`
- `0x18001e25c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005737`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005737`

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
0x180005720  push    rbx
0x180005722  sub     rsp, 20h
0x180005726  mov     rbx, rcx
0x180005729  mov     rcx, [rcx+8]; Block
0x18000572d  test    rcx, rcx
0x180005730  jz      short loc_180005755
0x180005732  cmp     rcx, rdx
0x180005735  jz      short loc_180005755
0x180005737  call    cs:__imp_free
0x18000573d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x180005744  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x180005749  test    al, al
0x18000574b  jz      short loc_180005755
0x18000574d  mov     qword ptr [rbx+8], 0
0x180005755  add     rsp, 20h
0x180005759  pop     rbx
0x18000575a  retn
```
