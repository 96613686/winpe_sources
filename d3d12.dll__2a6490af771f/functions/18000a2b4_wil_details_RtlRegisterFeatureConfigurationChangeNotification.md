# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000a2b4`
- end: `0x18000a318`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180002c64`

## callees

- `0x18000a2b4`
- `0x18000a398`
- `0x180015010`

## string_xrefs

- `0x18000a2d8`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000a2b4  mov     [rsp+arg_0], rbx
0x18000a2b9  mov     [rsp+arg_8], rsi
0x18000a2be  push    rdi
0x18000a2bf  sub     rsp, 30h
0x18000a2c3  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a2ca  mov     rbx, r9
0x18000a2cd  mov     rdi, rdx
0x18000a2d0  mov     rsi, rcx
0x18000a2d3  test    rax, rax
0x18000a2d6  jnz     short loc_18000A2F7
0x18000a2d8  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a2df  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a2e4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a2eb  test    rax, rax
0x18000a2ee  jnz     short loc_18000A2F7
0x18000a2f0  mov     eax, 0C0000139h
0x18000a2f5  jmp     short loc_18000A308
0x18000a2f7  mov     r9, rbx
0x18000a2fa  xor     r8d, r8d
0x18000a2fd  mov     rdx, rdi
0x18000a300  mov     rcx, rsi
0x18000a303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a308  mov     rbx, [rsp+38h+arg_0]
0x18000a30d  mov     rsi, [rsp+38h+arg_8]
0x18000a312  add     rsp, 30h
0x18000a316  pop     rdi
0x18000a317  retn
```
