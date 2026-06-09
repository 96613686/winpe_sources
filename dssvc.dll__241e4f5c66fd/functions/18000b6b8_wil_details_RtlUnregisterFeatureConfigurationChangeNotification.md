# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000b6b8`
- end: `0x18000b6f3`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007edc`

## callees

- `0x1800071f8`
- `0x18000b6b8`
- `0x18001c010`

## string_xrefs

- `0x18000b6cd`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000b6b8  push    rbx
0x18000b6ba  sub     rsp, 20h
0x18000b6be  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000b6c5  mov     rbx, rcx
0x18000b6c8  test    rax, rax
0x18000b6cb  jnz     short loc_18000B6E5
0x18000b6cd  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000b6d4  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b6d9  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000b6e0  test    rax, rax
0x18000b6e3  jz      short loc_18000B6ED
0x18000b6e5  mov     rcx, rbx
0x18000b6e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6ed  add     rsp, 20h
0x18000b6f1  pop     rbx
0x18000b6f2  retn
```
