# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::__private_IsEnabled(void)

- ea: `0x18000c5f4`
- end: `0x18000c68b`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180009a80`

## callees

- `0x180005fc4`
- `0x180009670`
- `0x18000c5f4`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_Servicing_HotpatchMonitoring_Service__descriptor;
  if ( (*(_DWORD *)Feature_Servicing_HotpatchMonitoring_Service__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 55856256, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x18000c5f4  mov     [rsp+arg_10], rbx
0x18000c5f9  push    rdi
0x18000c5fa  sub     rsp, 40h
0x18000c5fe  lea     rdx, [rsp+48h+arg_0]
0x18000c603  mov     rdi, rcx
0x18000c606  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCachedFeatureEnabledState(void)
0x18000c60b  mov     rax, cs:Feature_Servicing_HotpatchMonitoring_Service__descriptor
0x18000c612  mov     bl, byte ptr [rsp+48h+arg_0]
0x18000c616  and     bl, 1
0x18000c619  mov     r8d, [rax]
0x18000c61c  test    r8b, 4
0x18000c620  jnz     short loc_18000C637
0x18000c622  lea     rdx, [rsp+48h+arg_8]
0x18000c627  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetCachedFeatureEnabledState(void)
0x18000c62c  mov     rcx, [rax]
0x18000c62f  mov     [rsp+48h+arg_8], rcx
0x18000c634  mov     r8d, ecx
0x18000c637  mov     r9d, r8d
0x18000c63a  movzx   edx, bl
0x18000c63d  xor     eax, eax
0x18000c63f  shr     r9d, 0Bh
0x18000c643  mov     [rsp+48h+arg_0], eax
0x18000c647  lea     rcx, [rdi+8]
0x18000c64b  shr     r8d, 0Ah
0x18000c64f  lea     rax, [rsp+48h+arg_0]
0x18000c654  mov     [rsp+48h+var_18], 3
0x18000c65c  and     r9d, 1
0x18000c660  mov     [rsp+48h+var_20], edx
0x18000c664  and     r8d, 1
0x18000c668  mov     edx, 3544C80h
0x18000c66d  mov     [rsp+48h+var_28], rax
0x18000c672  mov     [rsp+48h+arg_4], 2
0x18000c679  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000c67e  mov     al, bl
0x18000c680  mov     rbx, [rsp+48h+arg_10]
0x18000c685  add     rsp, 40h
0x18000c689  pop     rdi
0x18000c68a  retn
```
