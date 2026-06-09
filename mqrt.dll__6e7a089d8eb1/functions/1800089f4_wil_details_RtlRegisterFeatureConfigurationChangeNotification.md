# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x1800089f4`
- end: `0x180008a58`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007800`

## callees

- `0x180008288`
- `0x1800089f4`
- `0x180026010`

## string_xrefs

- `0x180008a18`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800089f4  mov     [rsp+arg_0], rbx
0x1800089f9  mov     [rsp+arg_8], rsi
0x1800089fe  push    rdi
0x1800089ff  sub     rsp, 30h
0x180008a03  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008a0a  mov     rbx, r9
0x180008a0d  mov     rdi, rdx
0x180008a10  mov     rsi, rcx
0x180008a13  test    rax, rax
0x180008a16  jnz     short loc_180008A37
0x180008a18  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180008a1f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180008a24  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180008a2b  test    rax, rax
0x180008a2e  jnz     short loc_180008A37
0x180008a30  mov     eax, 0C0000139h
0x180008a35  jmp     short loc_180008A48
0x180008a37  mov     r9, rbx
0x180008a3a  xor     r8d, r8d
0x180008a3d  mov     rdx, rdi
0x180008a40  mov     rcx, rsi
0x180008a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a48  mov     rbx, [rsp+38h+arg_0]
0x180008a4d  mov     rsi, [rsp+38h+arg_8]
0x180008a52  add     rsp, 30h
0x180008a56  pop     rdi
0x180008a57  retn
```
