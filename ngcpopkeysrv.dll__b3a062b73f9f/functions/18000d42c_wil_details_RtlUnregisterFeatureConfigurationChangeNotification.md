# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000d42c`
- end: `0x18000d467`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007948`

## callees

- `0x18000cc50`
- `0x18000d42c`
- `0x180028010`

## string_xrefs

- `0x18000d441`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000d42c  push    rbx
0x18000d42e  sub     rsp, 20h
0x18000d432  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000d439  mov     rbx, rcx
0x18000d43c  test    rax, rax
0x18000d43f  jnz     short loc_18000D459
0x18000d441  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000d448  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d44d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000d454  test    rax, rax
0x18000d457  jz      short loc_18000D461
0x18000d459  mov     rcx, rbx
0x18000d45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d461  add     rsp, 20h
0x18000d465  pop     rbx
0x18000d466  retn
```
