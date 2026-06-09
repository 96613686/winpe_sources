# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000d57c`
- end: `0x18000d5b7`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007c84`

## callees

- `0x18000cdb0`
- `0x18000d57c`
- `0x180028010`

## string_xrefs

- `0x18000d591`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000d57c  push    rbx
0x18000d57e  sub     rsp, 20h
0x18000d582  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000d589  mov     rbx, rcx
0x18000d58c  test    rax, rax
0x18000d58f  jnz     short loc_18000D5A9
0x18000d591  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000d598  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d59d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000d5a4  test    rax, rax
0x18000d5a7  jz      short loc_18000D5B1
0x18000d5a9  mov     rcx, rbx
0x18000d5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5b1  add     rsp, 20h
0x18000d5b5  pop     rbx
0x18000d5b6  retn
```
