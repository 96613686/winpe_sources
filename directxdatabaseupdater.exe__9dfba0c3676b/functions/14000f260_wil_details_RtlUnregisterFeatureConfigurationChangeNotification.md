# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14000f260`
- end: `0x14000f29b`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140005e74`

## callees

- `0x14000ed40`
- `0x14000f260`
- `0x14001a010`

## string_xrefs

- `0x14000f275`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
FARPROC __fastcall wil_details_RtlUnregisterFeatureConfigurationChangeNotification(__int64 a1)
{
  FARPROC result; // rax

  result = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  result = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a1);
  return result;
}

```

## disassembly

```asm
0x14000f260  push    rbx
0x14000f262  sub     rsp, 20h
0x14000f266  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000f26d  mov     rbx, rcx
0x14000f270  test    rax, rax
0x14000f273  jnz     short loc_14000F28D
0x14000f275  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000f27c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000f281  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000f288  test    rax, rax
0x14000f28b  jz      short loc_14000F295
0x14000f28d  mov     rcx, rbx
0x14000f290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f295  add     rsp, 20h
0x14000f299  pop     rbx
0x14000f29a  retn
```
