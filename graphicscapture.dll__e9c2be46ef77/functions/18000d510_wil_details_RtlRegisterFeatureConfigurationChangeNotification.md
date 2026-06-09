# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000d510`
- end: `0x18000d574`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c120`

## callees

- `0x18000cdb0`
- `0x18000d510`
- `0x180028010`

## string_xrefs

- `0x18000d534`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (*NtDllProcedureAddress)(void); // rax

  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))NtDllProcedureAddress)(a1, a2, 0, a4);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))NtDllProcedureAddress)(a1, a2, 0, a4);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000d510  mov     [rsp+arg_0], rbx
0x18000d515  mov     [rsp+arg_8], rsi
0x18000d51a  push    rdi
0x18000d51b  sub     rsp, 30h
0x18000d51f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000d526  mov     rbx, r9
0x18000d529  mov     rdi, rdx
0x18000d52c  mov     rsi, rcx
0x18000d52f  test    rax, rax
0x18000d532  jnz     short loc_18000D553
0x18000d534  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000d53b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d540  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000d547  test    rax, rax
0x18000d54a  jnz     short loc_18000D553
0x18000d54c  mov     eax, 0C0000139h
0x18000d551  jmp     short loc_18000D564
0x18000d553  mov     r9, rbx
0x18000d556  xor     r8d, r8d
0x18000d559  mov     rdx, rdi
0x18000d55c  mov     rcx, rsi
0x18000d55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d564  mov     rbx, [rsp+38h+arg_0]
0x18000d569  mov     rsi, [rsp+38h+arg_8]
0x18000d56e  add     rsp, 30h
0x18000d572  pop     rdi
0x18000d573  retn
```
