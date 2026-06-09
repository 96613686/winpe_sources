# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000d3c0`
- end: `0x18000d424`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c170`

## callees

- `0x18000cc50`
- `0x18000d3c0`
- `0x180028010`

## string_xrefs

- `0x18000d3e4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000d3c0  mov     [rsp+arg_0], rbx
0x18000d3c5  mov     [rsp+arg_8], rsi
0x18000d3ca  push    rdi
0x18000d3cb  sub     rsp, 30h
0x18000d3cf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000d3d6  mov     rbx, r9
0x18000d3d9  mov     rdi, rdx
0x18000d3dc  mov     rsi, rcx
0x18000d3df  test    rax, rax
0x18000d3e2  jnz     short loc_18000D403
0x18000d3e4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000d3eb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d3f0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000d3f7  test    rax, rax
0x18000d3fa  jnz     short loc_18000D403
0x18000d3fc  mov     eax, 0C0000139h
0x18000d401  jmp     short loc_18000D414
0x18000d403  mov     r9, rbx
0x18000d406  xor     r8d, r8d
0x18000d409  mov     rdx, rdi
0x18000d40c  mov     rcx, rsi
0x18000d40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d414  mov     rbx, [rsp+38h+arg_0]
0x18000d419  mov     rsi, [rsp+38h+arg_8]
0x18000d41e  add     rsp, 30h
0x18000d422  pop     rdi
0x18000d423  retn
```
