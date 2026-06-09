# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18000e914`
- end: `0x18000e950`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ac70`

## callees

- `0x180009fb8`
- `0x18000e914`
- `0x180039010`

## string_xrefs

- `0x18000e929`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000e914  push    rbx
0x18000e916  sub     rsp, 20h
0x18000e91a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000e921  mov     rbx, rcx
0x18000e924  test    rax, rax
0x18000e927  jnz     short loc_18000E941
0x18000e929  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000e930  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e935  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000e93c  test    rax, rax
0x18000e93f  jz      short loc_18000E949
0x18000e941  mov     rcx, rbx
0x18000e944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e949  add     rsp, 20h
0x18000e94d  pop     rbx
0x18000e94e  retn
```
