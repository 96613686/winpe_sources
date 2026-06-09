# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000c8cc`
- end: `0x18000c907`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005fb0`

## callees

- `0x180003910`
- `0x18000c8cc`
- `0x180034010`

## string_xrefs

- `0x18000c8e1`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000c8cc  push    rbx
0x18000c8ce  sub     rsp, 20h
0x18000c8d2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000c8d9  mov     rbx, rcx
0x18000c8dc  test    rax, rax
0x18000c8df  jnz     short loc_18000C8F9
0x18000c8e1  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000c8e8  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c8ed  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000c8f4  test    rax, rax
0x18000c8f7  jz      short loc_18000C901
0x18000c8f9  mov     rcx, rbx
0x18000c8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c901  add     rsp, 20h
0x18000c905  pop     rbx
0x18000c906  retn
```
