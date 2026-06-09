# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000e8a8`
- end: `0x18000e90d`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d870`

## callees

- `0x180009fb8`
- `0x18000e8a8`
- `0x180039010`

## string_xrefs

- `0x18000e8cc`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000e8a8  mov     [rsp+arg_0], rbx
0x18000e8ad  mov     [rsp+arg_8], rsi
0x18000e8b2  push    rdi
0x18000e8b3  sub     rsp, 30h
0x18000e8b7  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000e8be  mov     rbx, r9
0x18000e8c1  mov     rdi, rdx
0x18000e8c4  mov     rsi, rcx
0x18000e8c7  test    rax, rax
0x18000e8ca  jnz     short loc_18000E8EB
0x18000e8cc  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000e8d3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e8d8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000e8df  test    rax, rax
0x18000e8e2  jnz     short loc_18000E8EB
0x18000e8e4  mov     eax, 0C0000139h
0x18000e8e9  jmp     short loc_18000E8FC
0x18000e8eb  mov     r9, rbx
0x18000e8ee  xor     r8d, r8d
0x18000e8f1  mov     rdx, rdi
0x18000e8f4  mov     rcx, rsi
0x18000e8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8fc  mov     rbx, [rsp+38h+arg_0]
0x18000e901  mov     rsi, [rsp+38h+arg_8]
0x18000e906  add     rsp, 30h
0x18000e90a  pop     rdi
0x18000e90b  retn
```
