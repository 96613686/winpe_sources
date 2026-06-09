# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000b654`
- end: `0x18000b6b8`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a344`

## callees

- `0x18000b298`
- `0x18000b654`
- `0x180031010`

## string_xrefs

- `0x18000b678`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000b654  mov     [rsp+arg_0], rbx
0x18000b659  mov     [rsp+arg_8], rsi
0x18000b65e  push    rdi
0x18000b65f  sub     rsp, 30h
0x18000b663  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b66a  mov     rbx, r9
0x18000b66d  mov     rdi, rdx
0x18000b670  mov     rsi, rcx
0x18000b673  test    rax, rax
0x18000b676  jnz     short loc_18000B697
0x18000b678  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b67f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b684  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b68b  test    rax, rax
0x18000b68e  jnz     short loc_18000B697
0x18000b690  mov     eax, 0C0000139h
0x18000b695  jmp     short loc_18000B6A8
0x18000b697  mov     r9, rbx
0x18000b69a  xor     r8d, r8d
0x18000b69d  mov     rdx, rdi
0x18000b6a0  mov     rcx, rsi
0x18000b6a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a8  mov     rbx, [rsp+38h+arg_0]
0x18000b6ad  mov     rsi, [rsp+38h+arg_8]
0x18000b6b2  add     rsp, 30h
0x18000b6b6  pop     rdi
0x18000b6b7  retn
```
