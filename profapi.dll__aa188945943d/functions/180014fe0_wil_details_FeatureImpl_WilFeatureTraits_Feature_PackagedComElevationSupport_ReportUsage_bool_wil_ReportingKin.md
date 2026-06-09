# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180014fe0`
- end: `0x180015006`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `38`
- prototype: `__int64 *(__int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800159f4`

## callees

- `0x180012ec0`
- `0x180014fe0`

## pseudocode

```c
__int64 *wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::ReportUsage(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        ...)
{
  __int64 *result; // rax
  wil::details *v4; // rcx
  va_list va; // [rsp+48h] [rbp+20h] BYREF

  va_start(va, a3);
  result = Feature_PackagedComElevationSupport__descriptor;
  v4 = (wil::details *)*(unsigned int *)Feature_PackagedComElevationSupport__descriptor;
  if ( ((unsigned __int8)v4 & 4) == 0 )
    return wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(
             v4,
             (__int64 *)va);
  return result;
}

```

## disassembly

```asm
0x180014fe0  mov     [rsp+arg_18], r9
0x180014fe5  sub     rsp, 28h
0x180014fe9  mov     rax, cs:Feature_PackagedComElevationSupport__descriptor
0x180014ff0  mov     ecx, [rax]
0x180014ff2  test    cl, 4
0x180014ff5  jnz     short loc_180015001
0x180014ff7  lea     rdx, [rsp+28h+arg_18]
0x180014ffc  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetCachedFeatureEnabledState(void)
0x180015001  add     rsp, 28h
0x180015005  retn
```
