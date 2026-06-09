# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x18001e13c`
- end: `0x18001e177`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800191d0`

## callees

- `0x1800072f0`
- `0x18001e13c`
- `0x18002b010`

## string_xrefs

- `0x18001e151`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18001e13c  push    rbx
0x18001e13e  sub     rsp, 20h
0x18001e142  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18001e149  mov     rbx, rcx
0x18001e14c  test    rax, rax
0x18001e14f  jnz     short loc_18001E169
0x18001e151  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18001e158  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001e15d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18001e164  test    rax, rax
0x18001e167  jz      short loc_18001E171
0x18001e169  mov     rcx, rbx
0x18001e16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e171  add     rsp, 20h
0x18001e175  pop     rbx
0x18001e176  retn
```
