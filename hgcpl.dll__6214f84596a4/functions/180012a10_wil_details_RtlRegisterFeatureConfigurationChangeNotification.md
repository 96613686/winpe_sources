# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180012a10`
- end: `0x180012a74`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180011e18`

## callees

- `0x180006b70`
- `0x180012a10`
- `0x18001a010`

## string_xrefs

- `0x180012a34`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180012a10  mov     [rsp+arg_0], rbx
0x180012a15  mov     [rsp+arg_8], rsi
0x180012a1a  push    rdi
0x180012a1b  sub     rsp, 30h
0x180012a1f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180012a26  mov     rbx, r9
0x180012a29  mov     rdi, rdx
0x180012a2c  mov     rsi, rcx
0x180012a2f  test    rax, rax
0x180012a32  jnz     short loc_180012A53
0x180012a34  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180012a3b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012a40  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180012a47  test    rax, rax
0x180012a4a  jnz     short loc_180012A53
0x180012a4c  mov     eax, 0C0000139h
0x180012a51  jmp     short loc_180012A64
0x180012a53  mov     r9, rbx
0x180012a56  xor     r8d, r8d
0x180012a59  mov     rdx, rdi
0x180012a5c  mov     rcx, rsi
0x180012a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a64  mov     rbx, [rsp+38h+arg_0]
0x180012a69  mov     rsi, [rsp+38h+arg_8]
0x180012a6e  add     rsp, 30h
0x180012a72  pop     rdi
0x180012a73  retn
```
