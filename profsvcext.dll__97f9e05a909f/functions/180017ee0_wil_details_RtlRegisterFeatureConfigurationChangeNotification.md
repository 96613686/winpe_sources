# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180017ee0`
- end: `0x180017f44`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180015634`

## callees

- `0x18000f020`
- `0x180017ee0`
- `0x180020010`

## string_xrefs

- `0x180017f04`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180017ee0  mov     [rsp+arg_0], rbx
0x180017ee5  mov     [rsp+arg_8], rsi
0x180017eea  push    rdi
0x180017eeb  sub     rsp, 30h
0x180017eef  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180017ef6  mov     rbx, r9
0x180017ef9  mov     rdi, rdx
0x180017efc  mov     rsi, rcx
0x180017eff  test    rax, rax
0x180017f02  jnz     short loc_180017F23
0x180017f04  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180017f0b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180017f10  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180017f17  test    rax, rax
0x180017f1a  jnz     short loc_180017F23
0x180017f1c  mov     eax, 0C0000139h
0x180017f21  jmp     short loc_180017F34
0x180017f23  mov     r9, rbx
0x180017f26  xor     r8d, r8d
0x180017f29  mov     rdx, rdi
0x180017f2c  mov     rcx, rsi
0x180017f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f34  mov     rbx, [rsp+38h+arg_0]
0x180017f39  mov     rsi, [rsp+38h+arg_8]
0x180017f3e  add     rsp, 30h
0x180017f42  pop     rdi
0x180017f43  retn
```
