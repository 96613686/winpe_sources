# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000b64c`
- end: `0x18000b6b0`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a5c0`

## callees

- `0x1800071f8`
- `0x18000b64c`
- `0x18001c010`

## string_xrefs

- `0x18000b670`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000b64c  mov     [rsp+arg_0], rbx
0x18000b651  mov     [rsp+arg_8], rsi
0x18000b656  push    rdi
0x18000b657  sub     rsp, 30h
0x18000b65b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b662  mov     rbx, r9
0x18000b665  mov     rdi, rdx
0x18000b668  mov     rsi, rcx
0x18000b66b  test    rax, rax
0x18000b66e  jnz     short loc_18000B68F
0x18000b670  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b677  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b67c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b683  test    rax, rax
0x18000b686  jnz     short loc_18000B68F
0x18000b688  mov     eax, 0C0000139h
0x18000b68d  jmp     short loc_18000B6A0
0x18000b68f  mov     r9, rbx
0x18000b692  xor     r8d, r8d
0x18000b695  mov     rdx, rdi
0x18000b698  mov     rcx, rsi
0x18000b69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a0  mov     rbx, [rsp+38h+arg_0]
0x18000b6a5  mov     rsi, [rsp+38h+arg_8]
0x18000b6aa  add     rsp, 30h
0x18000b6ae  pop     rdi
0x18000b6af  retn
```
