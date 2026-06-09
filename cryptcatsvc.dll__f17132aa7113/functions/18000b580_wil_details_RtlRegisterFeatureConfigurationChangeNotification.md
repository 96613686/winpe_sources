# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000b580`
- end: `0x18000b5e4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180011a10`

## callees

- `0x18000b580`
- `0x180012410`
- `0x180022010`

## string_xrefs

- `0x18000b5a4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000b580  mov     [rsp+arg_0], rbx
0x18000b585  mov     [rsp+arg_8], rsi
0x18000b58a  push    rdi
0x18000b58b  sub     rsp, 30h
0x18000b58f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b596  mov     rbx, r9
0x18000b599  mov     rdi, rdx
0x18000b59c  mov     rsi, rcx
0x18000b59f  test    rax, rax
0x18000b5a2  jnz     short loc_18000B5C3
0x18000b5a4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b5ab  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b5b0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b5b7  test    rax, rax
0x18000b5ba  jnz     short loc_18000B5C3
0x18000b5bc  mov     eax, 0C0000139h
0x18000b5c1  jmp     short loc_18000B5D4
0x18000b5c3  mov     r9, rbx
0x18000b5c6  xor     r8d, r8d
0x18000b5c9  mov     rdx, rdi
0x18000b5cc  mov     rcx, rsi
0x18000b5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5d4  mov     rbx, [rsp+38h+arg_0]
0x18000b5d9  mov     rsi, [rsp+38h+arg_8]
0x18000b5de  add     rsp, 30h
0x18000b5e2  pop     rdi
0x18000b5e3  retn
```
