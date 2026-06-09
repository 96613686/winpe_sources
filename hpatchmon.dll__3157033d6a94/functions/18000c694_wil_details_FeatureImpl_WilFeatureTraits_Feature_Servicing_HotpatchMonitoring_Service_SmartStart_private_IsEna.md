# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::__private_IsEnabled(void)

- ea: `0x18000c694`
- end: `0x18000c72b`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180009a80`

## callees

- `0x1800060a4`
- `0x180009670`
- `0x18000c694`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_Servicing_HotpatchMonitoring_Service_SmartStart__descriptor;
  if ( (*(_DWORD *)Feature_Servicing_HotpatchMonitoring_Service_SmartStart__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 57894640, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x18000c694  mov     [rsp+arg_10], rbx
0x18000c699  push    rdi
0x18000c69a  sub     rsp, 40h
0x18000c69e  lea     rdx, [rsp+48h+arg_0]
0x18000c6a3  mov     rdi, rcx
0x18000c6a6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCachedFeatureEnabledState(void)
0x18000c6ab  mov     rax, cs:Feature_Servicing_HotpatchMonitoring_Service_SmartStart__descriptor
0x18000c6b2  mov     bl, byte ptr [rsp+48h+arg_0]
0x18000c6b6  and     bl, 1
0x18000c6b9  mov     r8d, [rax]
0x18000c6bc  test    r8b, 4
0x18000c6c0  jnz     short loc_18000C6D7
0x18000c6c2  lea     rdx, [rsp+48h+arg_8]
0x18000c6c7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetCachedFeatureEnabledState(void)
0x18000c6cc  mov     rcx, [rax]
0x18000c6cf  mov     [rsp+48h+arg_8], rcx
0x18000c6d4  mov     r8d, ecx
0x18000c6d7  mov     r9d, r8d
0x18000c6da  movzx   edx, bl
0x18000c6dd  xor     eax, eax
0x18000c6df  shr     r9d, 0Bh
0x18000c6e3  mov     [rsp+48h+arg_0], eax
0x18000c6e7  lea     rcx, [rdi+8]
0x18000c6eb  shr     r8d, 0Ah
0x18000c6ef  lea     rax, [rsp+48h+arg_0]
0x18000c6f4  mov     [rsp+48h+var_18], 3
0x18000c6fc  and     r9d, 1
0x18000c700  mov     [rsp+48h+var_20], edx
0x18000c704  and     r8d, 1
0x18000c708  mov     edx, 37366F0h
0x18000c70d  mov     [rsp+48h+var_28], rax
0x18000c712  mov     [rsp+48h+arg_4], 2
0x18000c719  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000c71e  mov     al, bl
0x18000c720  mov     rbx, [rsp+48h+arg_10]
0x18000c725  add     rsp, 40h
0x18000c729  pop     rdi
0x18000c72a  retn
```
