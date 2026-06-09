# wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(void)

- ea: `0x180026404`
- end: `0x18002643a`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAA_NXZ`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e728`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x18001f048`
- `0x18001f390`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x180022d90`

## callees

- `0x18001d678`
- `0x180024c98`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::__private_IsEnabled(wil::details *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::ReportUsage(a1, v3);
  return v2;
}

```

## disassembly

```asm
0x180026404  mov     [rsp+arg_0], rbx
0x180026409  push    rdi
0x18002640a  sub     rsp, 20h
0x18002640e  lea     rdx, [rsp+28h+arg_8]
0x180026413  mov     rdi, rcx
0x180026416  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::GetCachedFeatureEnabledState(void)
0x18002641b  mov     bl, byte ptr [rsp+28h+arg_8]
0x18002641f  mov     rcx, rdi
0x180026422  and     bl, 1
0x180026425  mov     dl, bl
0x180026427  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_3749982522@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_3749982522>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002642c  mov     al, bl
0x18002642e  mov     rbx, [rsp+28h+arg_0]
0x180026433  add     rsp, 20h
0x180026437  pop     rdi
0x180026438  retn
```
