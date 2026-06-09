# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000ac3c`
- end: `0x18000aca0`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800094f0`

## callees

- `0x18000a118`
- `0x18000ac3c`
- `0x180013010`

## string_xrefs

- `0x18000ac60`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000ac3c  mov     [rsp+arg_0], rbx
0x18000ac41  mov     [rsp+arg_8], rsi
0x18000ac46  push    rdi
0x18000ac47  sub     rsp, 30h
0x18000ac4b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000ac52  mov     rbx, r9
0x18000ac55  mov     rdi, rdx
0x18000ac58  mov     rsi, rcx
0x18000ac5b  test    rax, rax
0x18000ac5e  jnz     short loc_18000AC7F
0x18000ac60  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000ac67  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ac6c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000ac73  test    rax, rax
0x18000ac76  jnz     short loc_18000AC7F
0x18000ac78  mov     eax, 0C0000139h
0x18000ac7d  jmp     short loc_18000AC90
0x18000ac7f  mov     r9, rbx
0x18000ac82  xor     r8d, r8d
0x18000ac85  mov     rdx, rdi
0x18000ac88  mov     rcx, rsi
0x18000ac8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac90  mov     rbx, [rsp+38h+arg_0]
0x18000ac95  mov     rsi, [rsp+38h+arg_8]
0x18000ac9a  add     rsp, 30h
0x18000ac9e  pop     rdi
0x18000ac9f  retn
```
