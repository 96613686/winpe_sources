# wil_details_RtlUnregisterFeatureConfigurationChangeNotification

- ea: `0x14000c410`
- end: `0x14000c44b`
- name: `wil_details_RtlUnregisterFeatureConfigurationChangeNotification`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140004788`

## callees

- `0x14000bcc4`
- `0x14000c410`
- `0x140010010`

## string_xrefs

- `0x14000c425`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000c410  push    rbx
0x14000c412  sub     rsp, 20h
0x14000c416  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000c41d  mov     rbx, rcx
0x14000c420  test    rax, rax
0x14000c423  jnz     short loc_14000C43D
0x14000c425  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000c42c  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000c431  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000c438  test    rax, rax
0x14000c43b  jz      short loc_14000C445
0x14000c43d  mov     rcx, rbx
0x14000c440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c445  add     rsp, 20h
0x14000c449  pop     rbx
0x14000c44a  retn
```
