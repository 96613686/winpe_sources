# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x180024974`
- end: `0x1800249af`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a990`

## callees

- `0x180024618`
- `0x180024974`
- `0x180027010`

## string_xrefs

- `0x180024989`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180024974  push    rbx
0x180024976  sub     rsp, 20h
0x18002497a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180024981  mov     rbx, rcx
0x180024984  test    rax, rax
0x180024987  jnz     short loc_1800249A1
0x180024989  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180024990  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180024995  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18002499c  test    rax, rax
0x18002499f  jz      short loc_1800249A9
0x1800249a1  mov     rcx, rbx
0x1800249a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249a9  add     rsp, 20h
0x1800249ad  pop     rbx
0x1800249ae  retn
```
