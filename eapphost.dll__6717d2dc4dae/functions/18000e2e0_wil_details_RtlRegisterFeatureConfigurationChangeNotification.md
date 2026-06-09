# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000e2e0`
- end: `0x18000e344`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d280`

## callees

- `0x180009b70`
- `0x18000e2e0`
- `0x180038010`

## string_xrefs

- `0x18000e304`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000e2e0  mov     [rsp+arg_0], rbx
0x18000e2e5  mov     [rsp+arg_8], rsi
0x18000e2ea  push    rdi
0x18000e2eb  sub     rsp, 30h
0x18000e2ef  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000e2f6  mov     rbx, r9
0x18000e2f9  mov     rdi, rdx
0x18000e2fc  mov     rsi, rcx
0x18000e2ff  test    rax, rax
0x18000e302  jnz     short loc_18000E323
0x18000e304  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000e30b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e310  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000e317  test    rax, rax
0x18000e31a  jnz     short loc_18000E323
0x18000e31c  mov     eax, 0C0000139h
0x18000e321  jmp     short loc_18000E334
0x18000e323  mov     r9, rbx
0x18000e326  xor     r8d, r8d
0x18000e329  mov     rdx, rdi
0x18000e32c  mov     rcx, rsi
0x18000e32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e334  mov     rbx, [rsp+38h+arg_0]
0x18000e339  mov     rsi, [rsp+38h+arg_8]
0x18000e33e  add     rsp, 30h
0x18000e342  pop     rdi
0x18000e343  retn
```
