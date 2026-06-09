# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001b370`
- end: `0x18001b3d4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180019b94`

## callees

- `0x18001aca0`
- `0x18001b370`
- `0x180025010`

## string_xrefs

- `0x18001b394`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001b370  mov     [rsp+arg_0], rbx
0x18001b375  mov     [rsp+arg_8], rsi
0x18001b37a  push    rdi
0x18001b37b  sub     rsp, 30h
0x18001b37f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001b386  mov     rbx, r9
0x18001b389  mov     rdi, rdx
0x18001b38c  mov     rsi, rcx
0x18001b38f  test    rax, rax
0x18001b392  jnz     short loc_18001B3B3
0x18001b394  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001b39b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b3a0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001b3a7  test    rax, rax
0x18001b3aa  jnz     short loc_18001B3B3
0x18001b3ac  mov     eax, 0C0000139h
0x18001b3b1  jmp     short loc_18001B3C4
0x18001b3b3  mov     r9, rbx
0x18001b3b6  xor     r8d, r8d
0x18001b3b9  mov     rdx, rdi
0x18001b3bc  mov     rcx, rsi
0x18001b3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3c4  mov     rbx, [rsp+38h+arg_0]
0x18001b3c9  mov     rsi, [rsp+38h+arg_8]
0x18001b3ce  add     rsp, 30h
0x18001b3d2  pop     rdi
0x18001b3d3  retn
```
