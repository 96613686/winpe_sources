# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x140012288`
- end: `0x1400122c3`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `FARPROC __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000e654`

## callees

- `0x1400066b0`
- `0x140012288`
- `0x14002a010`

## string_xrefs

- `0x14001229d`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x140012288  push    rbx
0x14001228a  sub     rsp, 20h
0x14001228e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140012295  mov     rbx, rcx
0x140012298  test    rax, rax
0x14001229b  jnz     short loc_1400122B5
0x14001229d  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1400122a4  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400122a9  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1400122b0  test    rax, rax
0x1400122b3  jz      short loc_1400122BD
0x1400122b5  mov     rcx, rbx
0x1400122b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400122bd  add     rsp, 20h
0x1400122c1  pop     rbx
0x1400122c2  retn
```
