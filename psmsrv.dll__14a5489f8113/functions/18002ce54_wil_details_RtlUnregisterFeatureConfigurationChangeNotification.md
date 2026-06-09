# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18002ce54`
- end: `0x18002ce8f`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180019f38`

## callees

- `0x18002a024`
- `0x18002ce54`
- `0x18002f010`

## string_xrefs

- `0x18002ce69`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18002ce54  push    rbx
0x18002ce56  sub     rsp, 20h
0x18002ce5a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18002ce61  mov     rbx, rcx
0x18002ce64  test    rax, rax
0x18002ce67  jnz     short loc_18002CE81
0x18002ce69  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18002ce70  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002ce75  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18002ce7c  test    rax, rax
0x18002ce7f  jz      short loc_18002CE89
0x18002ce81  mov     rcx, rbx
0x18002ce84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce89  add     rsp, 20h
0x18002ce8d  pop     rbx
0x18002ce8e  retn
```
