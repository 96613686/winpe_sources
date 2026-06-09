# COSKUtils::IsLockScreen(void)

- ea: `0x14001b450`
- end: `0x14001b492`
- name: `?IsLockScreen@COSKUtils@@SA_NXZ`
- size: `66`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140007f54`
- `0x14001b7bc`

## callees

- `0x14001b450`
- `0x14001b498`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x14001b479`
- `USER32!SystemParametersInfoW` at `0x14001b479`

## pseudocode

```c
bool __fastcall COSKUtils::IsLockScreen(__int64 a1, __int64 a2)
{
  BOOL v2; // eax
  int pvParam; // [rsp+30h] [rbp+8h] BYREF

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck>::GetImpl'::`2'::impl,
    a2);
  pvParam = 0;
  v2 = SystemParametersInfoW(0xAAu, 0, &pvParam, 0);
  if ( v2 )
    return pvParam;
  return v2;
}

```

## disassembly

```asm
0x14001b450  sub     rsp, 28h
0x14001b454  mov     dl, 1
0x14001b456  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck> `wil::Feature<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck>::GetImpl(void)'::`2'::impl
0x14001b45d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OSK_LockscreenCheck>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14001b462  xor     r9d, r9d; fWinIni
0x14001b465  mov     [rsp+28h+pvParam], 0
0x14001b46d  lea     r8, [rsp+28h+pvParam]; pvParam
0x14001b472  xor     edx, edx; uiParam
0x14001b474  mov     ecx, 0AAh; uiAction
0x14001b479  call    cs:__imp_SystemParametersInfoW
0x14001b47f  test    eax, eax
0x14001b481  jz      short loc_14001B487
0x14001b483  mov     eax, [rsp+28h+pvParam]
0x14001b487  cmp     eax, 1
0x14001b48a  setz    al
0x14001b48d  add     rsp, 28h
0x14001b491  retn
```
