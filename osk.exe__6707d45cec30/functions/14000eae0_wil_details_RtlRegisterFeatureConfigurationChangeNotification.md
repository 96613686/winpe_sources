# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000eae0`
- end: `0x14000eb44`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ab20`

## callees

- `0x14000d810`
- `0x14000eae0`
- `0x140027010`

## string_xrefs

- `0x14000eb04`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000eae0  mov     [rsp+arg_0], rbx
0x14000eae5  mov     [rsp+arg_8], rsi
0x14000eaea  push    rdi
0x14000eaeb  sub     rsp, 30h
0x14000eaef  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000eaf6  mov     rbx, r9
0x14000eaf9  mov     rdi, rdx
0x14000eafc  mov     rsi, rcx
0x14000eaff  test    rax, rax
0x14000eb02  jnz     short loc_14000EB23
0x14000eb04  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000eb0b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000eb10  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000eb17  test    rax, rax
0x14000eb1a  jnz     short loc_14000EB23
0x14000eb1c  mov     eax, 0C0000139h
0x14000eb21  jmp     short loc_14000EB34
0x14000eb23  mov     r9, rbx
0x14000eb26  xor     r8d, r8d
0x14000eb29  mov     rdx, rdi
0x14000eb2c  mov     rcx, rsi
0x14000eb2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb34  mov     rbx, [rsp+38h+arg_0]
0x14000eb39  mov     rsi, [rsp+38h+arg_8]
0x14000eb3e  add     rsp, 30h
0x14000eb42  pop     rdi
0x14000eb43  retn
```
