# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x180012c98`
- end: `0x180012cd3`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a16c`

## callees

- `0x180012410`
- `0x180012c98`
- `0x180022010`

## string_xrefs

- `0x180012cad`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180012c98  push    rbx
0x180012c9a  sub     rsp, 20h
0x180012c9e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180012ca5  mov     rbx, rcx
0x180012ca8  test    rax, rax
0x180012cab  jnz     short loc_180012CC5
0x180012cad  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180012cb4  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012cb9  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180012cc0  test    rax, rax
0x180012cc3  jz      short loc_180012CCD
0x180012cc5  mov     rcx, rbx
0x180012cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ccd  add     rsp, 20h
0x180012cd1  pop     rbx
0x180012cd2  retn
```
