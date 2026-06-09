# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180011900`
- end: `0x180011986`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012340`

## callees

- `0x18000fe34`
- `0x180011900`
- `0x180011c28`

## pseudocode

```c
_UNKNOWN **wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2,
        __int64 a3,
        ...)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  v4 = a2;
  LODWORD(v5) = *(_DWORD *)Feature_Capture_COMApartmentFix__descriptor;
  if ( (*(_DWORD *)Feature_Capture_COMApartmentFix__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 2;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x38A3681u,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64)va,
           v4,
           3u);
}

```

## disassembly

```asm
0x180011900  mov     [rsp+arg_8], rbx
0x180011905  mov     [rsp+arg_18], r9
0x18001190a  push    rdi
0x18001190b  sub     rsp, 40h
0x18001190f  mov     rax, cs:Feature_Capture_COMApartmentFix__descriptor
0x180011916  mov     rdi, rcx
0x180011919  movzx   ebx, dl
0x18001191c  mov     r8d, [rax]
0x18001191f  test    r8b, 4
0x180011923  jnz     short loc_180011937
0x180011925  lea     rdx, [rsp+48h+arg_0]
0x18001192a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_COMApartmentFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_COMApartmentFix>::GetCachedFeatureEnabledState(void)
0x18001192f  mov     r8, [rax]
0x180011932  mov     [rsp+48h+arg_0], r8
0x180011937  mov     r9d, r8d
0x18001193a  mov     [rsp+48h+var_18], 3
0x180011942  xor     eax, eax
0x180011944  shr     r9d, 0Bh
0x180011948  mov     dword ptr [rsp+48h+arg_18], eax
0x18001194c  lea     rcx, [rdi+8]
0x180011950  shr     r8d, 0Ah
0x180011954  lea     rax, [rsp+48h+arg_18]
0x180011959  and     r9d, 1
0x18001195d  mov     [rsp+48h+var_20], ebx
0x180011961  and     r8d, 1
0x180011965  mov     [rsp+48h+var_28], rax
0x18001196a  mov     edx, 38A3681h
0x18001196f  mov     word ptr [rsp+48h+arg_18+4], 2
0x180011976  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001197b  mov     rbx, [rsp+48h+arg_8]
0x180011980  add     rsp, 40h
0x180011984  pop     rdi
0x180011985  retn
```
