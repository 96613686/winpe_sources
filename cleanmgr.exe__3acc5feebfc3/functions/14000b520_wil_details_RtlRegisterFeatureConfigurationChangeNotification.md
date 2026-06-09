# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000b520`
- end: `0x14000b584`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140009764`

## callees

- `0x140006980`
- `0x14000b520`
- `0x140018010`

## string_xrefs

- `0x14000b544`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000b520  mov     [rsp+arg_0], rbx
0x14000b525  mov     [rsp+arg_8], rsi
0x14000b52a  push    rdi
0x14000b52b  sub     rsp, 30h
0x14000b52f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000b536  mov     rbx, r9
0x14000b539  mov     rdi, rdx
0x14000b53c  mov     rsi, rcx
0x14000b53f  test    rax, rax
0x14000b542  jnz     short loc_14000B563
0x14000b544  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000b54b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000b550  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000b557  test    rax, rax
0x14000b55a  jnz     short loc_14000B563
0x14000b55c  mov     eax, 0C0000139h
0x14000b561  jmp     short loc_14000B574
0x14000b563  mov     r9, rbx
0x14000b566  xor     r8d, r8d
0x14000b569  mov     rdx, rdi
0x14000b56c  mov     rcx, rsi
0x14000b56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b574  mov     rbx, [rsp+38h+arg_0]
0x14000b579  mov     rsi, [rsp+38h+arg_8]
0x14000b57e  add     rsp, 30h
0x14000b582  pop     rdi
0x14000b583  retn
```
