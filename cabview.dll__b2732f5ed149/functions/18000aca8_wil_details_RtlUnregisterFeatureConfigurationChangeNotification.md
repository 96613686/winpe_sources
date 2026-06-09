# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000aca8`
- end: `0x18000ace3`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180004034`

## callees

- `0x18000a118`
- `0x18000aca8`
- `0x180013010`

## string_xrefs

- `0x18000acbd`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000aca8  push    rbx
0x18000acaa  sub     rsp, 20h
0x18000acae  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000acb5  mov     rbx, rcx
0x18000acb8  test    rax, rax
0x18000acbb  jnz     short loc_18000ACD5
0x18000acbd  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000acc4  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000acc9  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000acd0  test    rax, rax
0x18000acd3  jz      short loc_18000ACDD
0x18000acd5  mov     rcx, rbx
0x18000acd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acdd  add     rsp, 20h
0x18000ace1  pop     rbx
0x18000ace2  retn
```
