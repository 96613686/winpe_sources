# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001aff0`
- end: `0x18001b054`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180023f20`

## callees

- `0x18001aff0`
- `0x180024618`
- `0x180027010`

## string_xrefs

- `0x18001b014`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC NtDllProcedureAddress; // rax

  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
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
0x18001aff0  mov     [rsp+arg_0], rbx
0x18001aff5  mov     [rsp+arg_8], rsi
0x18001affa  push    rdi
0x18001affb  sub     rsp, 30h
0x18001afff  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001b006  mov     rbx, r9
0x18001b009  mov     rdi, rdx
0x18001b00c  mov     rsi, rcx
0x18001b00f  test    rax, rax
0x18001b012  jnz     short loc_18001B033
0x18001b014  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001b01b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b020  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001b027  test    rax, rax
0x18001b02a  jnz     short loc_18001B033
0x18001b02c  mov     eax, 0C0000139h
0x18001b031  jmp     short loc_18001B044
0x18001b033  mov     r9, rbx
0x18001b036  xor     r8d, r8d
0x18001b039  mov     rdx, rdi
0x18001b03c  mov     rcx, rsi
0x18001b03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b044  mov     rbx, [rsp+38h+arg_0]
0x18001b049  mov     rsi, [rsp+38h+arg_8]
0x18001b04e  add     rsp, 30h
0x18001b052  pop     rdi
0x18001b053  retn
```
