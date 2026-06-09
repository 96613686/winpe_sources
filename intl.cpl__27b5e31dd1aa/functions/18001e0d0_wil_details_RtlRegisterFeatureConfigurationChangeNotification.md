# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001e0d0`
- end: `0x18001e134`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d1b0`

## callees

- `0x1800072f0`
- `0x18001e0d0`
- `0x18002b010`

## string_xrefs

- `0x18001e0f4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001e0d0  mov     [rsp+arg_0], rbx
0x18001e0d5  mov     [rsp+arg_8], rsi
0x18001e0da  push    rdi
0x18001e0db  sub     rsp, 30h
0x18001e0df  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001e0e6  mov     rbx, r9
0x18001e0e9  mov     rdi, rdx
0x18001e0ec  mov     rsi, rcx
0x18001e0ef  test    rax, rax
0x18001e0f2  jnz     short loc_18001E113
0x18001e0f4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001e0fb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001e100  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001e107  test    rax, rax
0x18001e10a  jnz     short loc_18001E113
0x18001e10c  mov     eax, 0C0000139h
0x18001e111  jmp     short loc_18001E124
0x18001e113  mov     r9, rbx
0x18001e116  xor     r8d, r8d
0x18001e119  mov     rdx, rdi
0x18001e11c  mov     rcx, rsi
0x18001e11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e124  mov     rbx, [rsp+38h+arg_0]
0x18001e129  mov     rsi, [rsp+38h+arg_8]
0x18001e12e  add     rsp, 30h
0x18001e132  pop     rdi
0x18001e133  retn
```
