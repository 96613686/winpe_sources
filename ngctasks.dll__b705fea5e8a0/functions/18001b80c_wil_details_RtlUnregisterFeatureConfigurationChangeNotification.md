# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18001b80c`
- end: `0x18001b847`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001794c`

## callees

- `0x18000faa0`
- `0x18001b80c`
- `0x180022010`

## string_xrefs

- `0x18001b821`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18001b80c  push    rbx
0x18001b80e  sub     rsp, 20h
0x18001b812  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18001b819  mov     rbx, rcx
0x18001b81c  test    rax, rax
0x18001b81f  jnz     short loc_18001B839
0x18001b821  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18001b828  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b82d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18001b834  test    rax, rax
0x18001b837  jz      short loc_18001B841
0x18001b839  mov     rcx, rbx
0x18001b83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b841  add     rsp, 20h
0x18001b845  pop     rbx
0x18001b846  retn
```
