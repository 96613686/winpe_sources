# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(wil::ReportingKind)

- ea: `0x1800159f4`
- end: `0x180015a17`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `35`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d00c`

## callees

- `0x180012ec0`
- `0x180014fe0`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(
    a1,
    &v2);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::ReportUsage();
  return v2 & 1;
}

```

## disassembly

```asm
0x1800159f4  mov     [rsp+arg_0], rcx
0x1800159f9  sub     rsp, 28h
0x1800159fd  lea     rdx, [rsp+28h+arg_0]
0x180015a02  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(void)
0x180015a07  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180015a0c  mov     al, byte ptr [rsp+28h+arg_0]
0x180015a10  and     al, 1
0x180015a12  add     rsp, 28h
0x180015a16  retn
```
