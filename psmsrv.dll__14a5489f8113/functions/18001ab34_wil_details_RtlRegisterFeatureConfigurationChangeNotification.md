# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001ab34`
- end: `0x18001ab98`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180029860`

## callees

- `0x18001ab34`
- `0x18002a024`
- `0x18002f010`

## string_xrefs

- `0x18001ab58`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001ab34  mov     [rsp+arg_0], rbx
0x18001ab39  mov     [rsp+arg_8], rsi
0x18001ab3e  push    rdi
0x18001ab3f  sub     rsp, 30h
0x18001ab43  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001ab4a  mov     rbx, r9
0x18001ab4d  mov     rdi, rdx
0x18001ab50  mov     rsi, rcx
0x18001ab53  test    rax, rax
0x18001ab56  jnz     short loc_18001AB77
0x18001ab58  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001ab5f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001ab64  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001ab6b  test    rax, rax
0x18001ab6e  jnz     short loc_18001AB77
0x18001ab70  mov     eax, 0C0000139h
0x18001ab75  jmp     short loc_18001AB88
0x18001ab77  mov     r9, rbx
0x18001ab7a  xor     r8d, r8d
0x18001ab7d  mov     rdx, rdi
0x18001ab80  mov     rcx, rsi
0x18001ab83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab88  mov     rbx, [rsp+38h+arg_0]
0x18001ab8d  mov     rsi, [rsp+38h+arg_8]
0x18001ab92  add     rsp, 30h
0x18001ab96  pop     rdi
0x18001ab97  retn
```
