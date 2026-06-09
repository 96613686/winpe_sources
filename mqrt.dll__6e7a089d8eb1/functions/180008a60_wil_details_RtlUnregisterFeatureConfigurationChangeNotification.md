# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x180008a60`
- end: `0x180008a9b`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800038e0`

## callees

- `0x180008288`
- `0x180008a60`
- `0x180026010`

## string_xrefs

- `0x180008a75`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180008a60  push    rbx
0x180008a62  sub     rsp, 20h
0x180008a66  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180008a6d  mov     rbx, rcx
0x180008a70  test    rax, rax
0x180008a73  jnz     short loc_180008A8D
0x180008a75  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180008a7c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180008a81  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180008a88  test    rax, rax
0x180008a8b  jz      short loc_180008A95
0x180008a8d  mov     rcx, rbx
0x180008a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a95  add     rsp, 20h
0x180008a99  pop     rbx
0x180008a9a  retn
```
