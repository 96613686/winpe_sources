# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::__private_IsEnabled(void)

- ea: `0x18000c52c`
- end: `0x18000c561`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000c200`

## callees

- `0x18000b9d0`
- `0x18000beac`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::__private_IsEnabled(
        __int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetCachedFeatureEnabledState(
    a1,
    &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::ReportUsage(
    a1,
    v3);
  return v2;
}

```

## disassembly

```asm
0x18000c52c  mov     [rsp+arg_0], rbx
0x18000c531  push    rdi
0x18000c532  sub     rsp, 20h
0x18000c536  lea     rdx, [rsp+28h+arg_8]
0x18000c53b  mov     rdi, rcx
0x18000c53e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetCachedFeatureEnabledState(void)
0x18000c543  mov     bl, [rsp+28h+arg_8]
0x18000c547  mov     rcx, rdi
0x18000c54a  and     bl, 1
0x18000c54d  mov     dl, bl
0x18000c54f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000c554  mov     al, bl
0x18000c556  mov     rbx, [rsp+28h+arg_0]
0x18000c55b  add     rsp, 20h
0x18000c55f  pop     rdi
0x18000c560  retn
```
