# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14007c06c`
- end: `0x14007c0a7`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140074a24`

## callees

- `0x14007bce0`
- `0x14007c06c`
- `0x140098010`

## string_xrefs

- `0x14007c081`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14007c06c  push    rbx
0x14007c06e  sub     rsp, 20h
0x14007c072  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14007c079  mov     rbx, rcx
0x14007c07c  test    rax, rax
0x14007c07f  jnz     short loc_14007C099
0x14007c081  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14007c088  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14007c08d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14007c094  test    rax, rax
0x14007c097  jz      short loc_14007C0A1
0x14007c099  mov     rcx, rbx
0x14007c09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c0a1  add     rsp, 20h
0x14007c0a5  pop     rbx
0x14007c0a6  retn
```
