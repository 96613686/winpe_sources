# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180008638`
- end: `0x18000869c`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180006c58`

## callees

- `0x1800082d0`
- `0x180008638`
- `0x18001c010`

## string_xrefs

- `0x18000865c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180008638  mov     [rsp+arg_0], rbx
0x18000863d  mov     [rsp+arg_8], rsi
0x180008642  push    rdi
0x180008643  sub     rsp, 30h
0x180008647  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000864e  mov     rbx, r9
0x180008651  mov     rdi, rdx
0x180008654  mov     rsi, rcx
0x180008657  test    rax, rax
0x18000865a  jnz     short loc_18000867B
0x18000865c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180008663  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180008668  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000866f  test    rax, rax
0x180008672  jnz     short loc_18000867B
0x180008674  mov     eax, 0C0000139h
0x180008679  jmp     short loc_18000868C
0x18000867b  mov     r9, rbx
0x18000867e  xor     r8d, r8d
0x180008681  mov     rdx, rdi
0x180008684  mov     rcx, rsi
0x180008687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000868c  mov     rbx, [rsp+38h+arg_0]
0x180008691  mov     rsi, [rsp+38h+arg_8]
0x180008696  add     rsp, 30h
0x18000869a  pop     rdi
0x18000869b  retn
```
