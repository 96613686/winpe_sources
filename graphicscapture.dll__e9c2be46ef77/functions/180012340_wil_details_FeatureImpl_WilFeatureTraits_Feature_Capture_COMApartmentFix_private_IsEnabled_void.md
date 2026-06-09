# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::__private_IsEnabled(void)

- ea: `0x180012340`
- end: `0x180012375`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ebf0`
- `0x180010da0`
- `0x180019d50`

## callees

- `0x18000fe34`
- `0x180011900`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::__private_IsEnabled(
        wil::details *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::ReportUsage(a1, v3);
  return v2;
}

```

## disassembly

```asm
0x180012340  mov     [rsp+arg_0], rbx
0x180012345  push    rdi
0x180012346  sub     rsp, 20h
0x18001234a  lea     rdx, [rsp+28h+arg_8]
0x18001234f  mov     rdi, rcx
0x180012352  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCachedFeatureEnabledState(void)
0x180012357  mov     bl, byte ptr [rsp+28h+arg_8]
0x18001235b  mov     rcx, rdi
0x18001235e  and     bl, 1
0x180012361  mov     dl, bl
0x180012363  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180012368  mov     al, bl
0x18001236a  mov     rbx, [rsp+28h+arg_0]
0x18001236f  add     rsp, 20h
0x180012373  pop     rdi
0x180012374  retn
```
