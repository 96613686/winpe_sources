# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000e34c`
- end: `0x18000e387`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a7fc`

## callees

- `0x180009b70`
- `0x18000e34c`
- `0x180038010`

## string_xrefs

- `0x18000e361`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 (*__fastcall wil_details_RtlUnregisterFeatureConfigurationChangeNotification(__int64 a1))(void)
{
  __int64 (*result)(void); // rax

  result = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
    return (__int64 (*)(void))((__int64 (__fastcall *)(__int64))result)(a1);
  result = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)result;
  if ( result )
    return (__int64 (*)(void))((__int64 (__fastcall *)(__int64))result)(a1);
  return result;
}

```

## disassembly

```asm
0x18000e34c  push    rbx
0x18000e34e  sub     rsp, 20h
0x18000e352  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000e359  mov     rbx, rcx
0x18000e35c  test    rax, rax
0x18000e35f  jnz     short loc_18000E379
0x18000e361  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000e368  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e36d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000e374  test    rax, rax
0x18000e377  jz      short loc_18000E381
0x18000e379  mov     rcx, rbx
0x18000e37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e381  add     rsp, 20h
0x18000e385  pop     rbx
0x18000e386  retn
```
