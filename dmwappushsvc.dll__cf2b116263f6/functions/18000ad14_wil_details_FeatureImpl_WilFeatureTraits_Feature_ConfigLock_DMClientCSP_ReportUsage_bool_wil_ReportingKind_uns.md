# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18000ad14`
- end: `0x18000ad8d`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigLock_DMClientCSP@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `121`
- prototype: `__int64(wil::details *, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000b384`

## callees

- `0x1800088d4`
- `0x18000ad14`
- `0x18000ad94`

## pseudocode

```c
__int64 wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::ReportUsage(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        ...)
{
  int v4; // ebx
  __int64 v5; // r8
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  v4 = (unsigned __int8)a2;
  LODWORD(v5) = *(_DWORD *)Feature_ConfigLock_DMClientCSP__descriptor;
  if ( (*(_DWORD *)Feature_ConfigLock_DMClientCSP__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 3;
  return wil::details::ReportUsageToService(
           (char *)a1 + 8,
           a2,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64 *)va,
           v4);
}

```

## disassembly

```asm
0x18000ad14  mov     [rsp+arg_8], rbx
0x18000ad19  mov     [rsp+arg_18], r9
0x18000ad1e  push    rdi
0x18000ad1f  sub     rsp, 40h
0x18000ad23  mov     rax, cs:Feature_ConfigLock_DMClientCSP__descriptor
0x18000ad2a  mov     rdi, rcx
0x18000ad2d  movzx   ebx, dl
0x18000ad30  mov     r8d, [rax]
0x18000ad33  test    r8b, 4
0x18000ad37  jnz     short loc_18000AD4B
0x18000ad39  lea     rdx, [rsp+48h+arg_0]
0x18000ad3e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigLock_DMClientCSP@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::GetCachedFeatureEnabledState(void)
0x18000ad43  mov     r8, [rax]
0x18000ad46  mov     [rsp+48h+arg_0], r8
0x18000ad4b  mov     r9d, r8d
0x18000ad4e  mov     [rsp+48h+var_20], ebx
0x18000ad52  xor     eax, eax
0x18000ad54  shr     r9d, 0Bh
0x18000ad58  mov     dword ptr [rsp+48h+arg_18], eax
0x18000ad5c  lea     rcx, [rdi+8]
0x18000ad60  shr     r8d, 0Ah
0x18000ad64  lea     rax, [rsp+48h+arg_18]
0x18000ad69  and     r9d, 1
0x18000ad6d  mov     [rsp+48h+var_28], rax
0x18000ad72  and     r8d, 1
0x18000ad76  mov     word ptr [rsp+48h+arg_18+4], 3
0x18000ad7d  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000ad82  mov     rbx, [rsp+48h+arg_8]
0x18000ad87  add     rsp, 40h
0x18000ad8b  pop     rdi
0x18000ad8c  retn
```
