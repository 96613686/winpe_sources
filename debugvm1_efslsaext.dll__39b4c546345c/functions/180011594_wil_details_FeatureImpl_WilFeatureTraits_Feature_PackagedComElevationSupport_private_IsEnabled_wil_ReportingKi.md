# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(wil::ReportingKind)

- ea: `0x180011594`
- end: `0x1800115cf`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d300`

## callees

- `0x18000e6a8`
- `0x180011594`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(
        wil::details *a1)
{
  char v1; // bl
  wil::details *v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = a1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(
    a1,
    &v3);
  v1 = (unsigned __int8)v3 & 1;
  if ( (*(_DWORD *)Feature_PackagedComElevationSupport__descriptor & 4) == 0 )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(
      (wil::details *)Feature_PackagedComElevationSupport__descriptor,
      &v3);
  return v1;
}

```

## disassembly

```asm
0x180011594  mov     [rsp+arg_0], rcx
0x180011599  push    rbx
0x18001159a  sub     rsp, 20h
0x18001159e  lea     rdx, [rsp+28h+arg_0]
0x1800115a3  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(void)
0x1800115a8  mov     rcx, cs:Feature_PackagedComElevationSupport__descriptor
0x1800115af  mov     bl, byte ptr [rsp+28h+arg_0]
0x1800115b3  and     bl, 1
0x1800115b6  mov     edx, [rcx]
0x1800115b8  test    dl, 4
0x1800115bb  jnz     short loc_1800115C7
0x1800115bd  lea     rdx, [rsp+28h+arg_0]
0x1800115c2  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(void)
0x1800115c7  mov     al, bl
0x1800115c9  add     rsp, 20h
0x1800115cd  pop     rbx
0x1800115ce  retn
```
