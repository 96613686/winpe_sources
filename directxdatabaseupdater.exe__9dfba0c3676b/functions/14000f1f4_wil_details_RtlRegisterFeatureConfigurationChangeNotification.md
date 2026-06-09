# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000f1f4`
- end: `0x14000f258`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d530`

## callees

- `0x14000ed40`
- `0x14000f1f4`
- `0x14001a010`

## string_xrefs

- `0x14000f218`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000f1f4  mov     [rsp+arg_0], rbx
0x14000f1f9  mov     [rsp+arg_8], rsi
0x14000f1fe  push    rdi
0x14000f1ff  sub     rsp, 30h
0x14000f203  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000f20a  mov     rbx, r9
0x14000f20d  mov     rdi, rdx
0x14000f210  mov     rsi, rcx
0x14000f213  test    rax, rax
0x14000f216  jnz     short loc_14000F237
0x14000f218  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000f21f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000f224  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000f22b  test    rax, rax
0x14000f22e  jnz     short loc_14000F237
0x14000f230  mov     eax, 0C0000139h
0x14000f235  jmp     short loc_14000F248
0x14000f237  mov     r9, rbx
0x14000f23a  xor     r8d, r8d
0x14000f23d  mov     rdx, rdi
0x14000f240  mov     rcx, rsi
0x14000f243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f248  mov     rbx, [rsp+38h+arg_0]
0x14000f24d  mov     rsi, [rsp+38h+arg_8]
0x14000f252  add     rsp, 30h
0x14000f256  pop     rdi
0x14000f257  retn
```
