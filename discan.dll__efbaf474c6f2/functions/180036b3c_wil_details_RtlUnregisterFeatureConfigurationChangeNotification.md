# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x180036b3c`
- end: `0x180036b77`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180032320`

## callees

- `0x18003667c`
- `0x180036b3c`
- `0x180039010`

## string_xrefs

- `0x180036b51`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180036b3c  push    rbx
0x180036b3e  sub     rsp, 20h
0x180036b42  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180036b49  mov     rbx, rcx
0x180036b4c  test    rax, rax
0x180036b4f  jnz     short loc_180036B69
0x180036b51  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180036b58  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180036b5d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180036b64  test    rax, rax
0x180036b67  jz      short loc_180036B71
0x180036b69  mov     rcx, rbx
0x180036b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b71  add     rsp, 20h
0x180036b75  pop     rbx
0x180036b76  retn
```
