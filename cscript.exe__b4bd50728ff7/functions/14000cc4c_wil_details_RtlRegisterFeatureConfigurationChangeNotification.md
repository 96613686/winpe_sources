# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000cc4c`
- end: `0x14000ccb0`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c43c`

## callees

- `0x14000cbd8`
- `0x14000cc4c`
- `0x140017010`

## string_xrefs

- `0x14000cc70`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000cc4c  mov     [rsp+arg_0], rbx
0x14000cc51  mov     [rsp+arg_8], rsi
0x14000cc56  push    rdi
0x14000cc57  sub     rsp, 30h
0x14000cc5b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000cc62  mov     rbx, r9
0x14000cc65  mov     rdi, rdx
0x14000cc68  mov     rsi, rcx
0x14000cc6b  test    rax, rax
0x14000cc6e  jnz     short loc_14000CC8F
0x14000cc70  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000cc77  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000cc7c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000cc83  test    rax, rax
0x14000cc86  jnz     short loc_14000CC8F
0x14000cc88  mov     eax, 0C0000139h
0x14000cc8d  jmp     short loc_14000CCA0
0x14000cc8f  mov     r9, rbx
0x14000cc92  xor     r8d, r8d
0x14000cc95  mov     rdx, rdi
0x14000cc98  mov     rcx, rsi
0x14000cc9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cca0  mov     rbx, [rsp+38h+arg_0]
0x14000cca5  mov     rsi, [rsp+38h+arg_8]
0x14000ccaa  add     rsp, 30h
0x14000ccae  pop     rdi
0x14000ccaf  retn
```
