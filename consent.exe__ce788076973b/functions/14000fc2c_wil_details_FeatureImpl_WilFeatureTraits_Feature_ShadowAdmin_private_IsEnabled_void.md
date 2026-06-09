# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)

- ea: `0x14000fc2c`
- end: `0x14000fc61`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cfdc`
- `0x140015c28`
- `0x140015d68`
- `0x14001a080`
- `0x14001bdf0`
- `0x14001c528`

## callees

- `0x14000e9c4`
- `0x140015090`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(__int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::ReportUsage(a1, v3);
  return v2;
}

```

## disassembly

```asm
0x14000fc2c  mov     [rsp+arg_0], rbx
0x14000fc31  push    rdi
0x14000fc32  sub     rsp, 20h
0x14000fc36  lea     rdx, [rsp+28h+arg_8]
0x14000fc3b  mov     rdi, rcx
0x14000fc3e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::GetCachedFeatureEnabledState(void)
0x14000fc43  mov     bl, [rsp+28h+arg_8]
0x14000fc47  mov     rcx, rdi
0x14000fc4a  and     bl, 1
0x14000fc4d  mov     dl, bl
0x14000fc4f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000fc54  mov     al, bl
0x14000fc56  mov     rbx, [rsp+28h+arg_0]
0x14000fc5b  add     rsp, 20h
0x14000fc5f  pop     rdi
0x14000fc60  retn
```
