# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)

- ea: `0x18001085c`
- end: `0x1800108f3`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: `unsigned __int8 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000b47c`
- `0x18000b7f0`
- `0x18000b870`
- `0x18000da9c`
- `0x1800111b0`
- `0x180011500`
- `0x180012194`

## callees

- `0x18000ca64`
- `0x18000fa2c`
- `0x18001085c`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_56494824__descriptor;
  if ( (*(_DWORD *)Feature_56494824__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 1;
  wil::details::ReportUsageToService(a1 + 8, 56494824, (v4 >> 10) & 1, (v4 >> 11) & 1, &v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x18001085c  mov     [rsp+arg_10], rbx
0x180010861  push    rdi
0x180010862  sub     rsp, 40h
0x180010866  lea     rdx, [rsp+48h+arg_0]
0x18001086b  mov     rdi, rcx
0x18001086e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(void)
0x180010873  mov     rax, cs:Feature_56494824__descriptor
0x18001087a  mov     bl, byte ptr [rsp+48h+arg_0]
0x18001087e  and     bl, 1
0x180010881  mov     r8d, [rax]
0x180010884  test    r8b, 4
0x180010888  jnz     short loc_18001089F
0x18001088a  lea     rdx, [rsp+48h+arg_8]
0x18001088f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(void)
0x180010894  mov     rcx, [rax]
0x180010897  mov     [rsp+48h+arg_8], rcx
0x18001089c  mov     r8d, ecx
0x18001089f  mov     r9d, r8d
0x1800108a2  movzx   edx, bl
0x1800108a5  xor     eax, eax
0x1800108a7  shr     r9d, 0Bh
0x1800108ab  mov     [rsp+48h+arg_0], eax
0x1800108af  lea     rcx, [rdi+8]
0x1800108b3  shr     r8d, 0Ah
0x1800108b7  lea     rax, [rsp+48h+arg_0]
0x1800108bc  mov     [rsp+48h+var_18], 3
0x1800108c4  and     r9d, 1
0x1800108c8  mov     [rsp+48h+var_20], edx
0x1800108cc  and     r8d, 1
0x1800108d0  mov     edx, 35E0AE8h
0x1800108d5  mov     [rsp+48h+var_28], rax
0x1800108da  mov     [rsp+48h+arg_4], 1
0x1800108e1  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800108e6  mov     al, bl
0x1800108e8  mov     rbx, [rsp+48h+arg_10]
0x1800108ed  add     rsp, 40h
0x1800108f1  pop     rdi
0x1800108f2  retn
```
