# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180036ad0`
- end: `0x180036b34`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180035e70`

## callees

- `0x18003667c`
- `0x180036ad0`
- `0x180039010`

## string_xrefs

- `0x180036af4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180036ad0  mov     [rsp+arg_0], rbx
0x180036ad5  mov     [rsp+arg_8], rsi
0x180036ada  push    rdi
0x180036adb  sub     rsp, 30h
0x180036adf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180036ae6  mov     rbx, r9
0x180036ae9  mov     rdi, rdx
0x180036aec  mov     rsi, rcx
0x180036aef  test    rax, rax
0x180036af2  jnz     short loc_180036B13
0x180036af4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180036afb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180036b00  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180036b07  test    rax, rax
0x180036b0a  jnz     short loc_180036B13
0x180036b0c  mov     eax, 0C0000139h
0x180036b11  jmp     short loc_180036B24
0x180036b13  mov     r9, rbx
0x180036b16  xor     r8d, r8d
0x180036b19  mov     rdx, rdi
0x180036b1c  mov     rcx, rsi
0x180036b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b24  mov     rbx, [rsp+38h+arg_0]
0x180036b29  mov     rsi, [rsp+38h+arg_8]
0x180036b2e  add     rsp, 30h
0x180036b32  pop     rdi
0x180036b33  retn
```
