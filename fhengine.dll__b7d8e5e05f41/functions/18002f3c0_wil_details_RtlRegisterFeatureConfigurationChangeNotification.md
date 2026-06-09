# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18002f3c0`
- end: `0x18002f424`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d84c`

## callees

- `0x18002e9b8`
- `0x18002f3c0`
- `0x180034010`

## string_xrefs

- `0x18002f3e4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18002f3c0  mov     [rsp+arg_0], rbx
0x18002f3c5  mov     [rsp+arg_8], rsi
0x18002f3ca  push    rdi
0x18002f3cb  sub     rsp, 30h
0x18002f3cf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002f3d6  mov     rbx, r9
0x18002f3d9  mov     rdi, rdx
0x18002f3dc  mov     rsi, rcx
0x18002f3df  test    rax, rax
0x18002f3e2  jnz     short loc_18002F403
0x18002f3e4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002f3eb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002f3f0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002f3f7  test    rax, rax
0x18002f3fa  jnz     short loc_18002F403
0x18002f3fc  mov     eax, 0C0000139h
0x18002f401  jmp     short loc_18002F414
0x18002f403  mov     r9, rbx
0x18002f406  xor     r8d, r8d
0x18002f409  mov     rdx, rdi
0x18002f40c  mov     rcx, rsi
0x18002f40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f414  mov     rbx, [rsp+38h+arg_0]
0x18002f419  mov     rsi, [rsp+38h+arg_8]
0x18002f41e  add     rsp, 30h
0x18002f422  pop     rdi
0x18002f423  retn
```
