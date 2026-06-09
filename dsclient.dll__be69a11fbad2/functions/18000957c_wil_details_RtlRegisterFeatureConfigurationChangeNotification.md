# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000957c`
- end: `0x1800095e0`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000806c`

## callees

- `0x180008f40`
- `0x18000957c`
- `0x18000a010`

## string_xrefs

- `0x1800095a0`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000957c  mov     [rsp+arg_0], rbx
0x180009581  mov     [rsp+arg_8], rsi
0x180009586  push    rdi
0x180009587  sub     rsp, 30h
0x18000958b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009592  mov     rbx, r9
0x180009595  mov     rdi, rdx
0x180009598  mov     rsi, rcx
0x18000959b  test    rax, rax
0x18000959e  jnz     short loc_1800095BF
0x1800095a0  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800095a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800095ac  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800095b3  test    rax, rax
0x1800095b6  jnz     short loc_1800095BF
0x1800095b8  mov     eax, 0C0000139h
0x1800095bd  jmp     short loc_1800095D0
0x1800095bf  mov     r9, rbx
0x1800095c2  xor     r8d, r8d
0x1800095c5  mov     rdx, rdi
0x1800095c8  mov     rcx, rsi
0x1800095cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d0  mov     rbx, [rsp+38h+arg_0]
0x1800095d5  mov     rsi, [rsp+38h+arg_8]
0x1800095da  add     rsp, 30h
0x1800095de  pop     rdi
0x1800095df  retn
```
