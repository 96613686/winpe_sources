# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14000eb4c`
- end: `0x14000eb87`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140005138`

## callees

- `0x14000d810`
- `0x14000eb4c`
- `0x140027010`

## string_xrefs

- `0x14000eb61`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000eb4c  push    rbx
0x14000eb4e  sub     rsp, 20h
0x14000eb52  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000eb59  mov     rbx, rcx
0x14000eb5c  test    rax, rax
0x14000eb5f  jnz     short loc_14000EB79
0x14000eb61  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000eb68  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000eb6d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000eb74  test    rax, rax
0x14000eb77  jz      short loc_14000EB81
0x14000eb79  mov     rcx, rbx
0x14000eb7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb81  add     rsp, 20h
0x14000eb85  pop     rbx
0x14000eb86  retn
```
