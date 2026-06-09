# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18001646c`
- end: `0x1800164a7`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d008`

## callees

- `0x180015a54`
- `0x18001646c`
- `0x180018010`

## string_xrefs

- `0x180016481`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18001646c  push    rbx
0x18001646e  sub     rsp, 20h
0x180016472  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180016479  mov     rbx, rcx
0x18001647c  test    rax, rax
0x18001647f  jnz     short loc_180016499
0x180016481  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180016488  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001648d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180016494  test    rax, rax
0x180016497  jz      short loc_1800164A1
0x180016499  mov     rcx, rbx
0x18001649c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164a1  add     rsp, 20h
0x1800164a5  pop     rbx
0x1800164a6  retn
```
