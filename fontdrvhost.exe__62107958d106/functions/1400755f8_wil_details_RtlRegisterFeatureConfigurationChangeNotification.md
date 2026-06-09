# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x1400755f8`
- end: `0x14007565c`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14007b3d0`

## callees

- `0x1400755f8`
- `0x14007bce0`
- `0x140098010`

## string_xrefs

- `0x14007561c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1400755f8  mov     [rsp+arg_0], rbx
0x1400755fd  mov     [rsp+arg_8], rsi
0x140075602  push    rdi
0x140075603  sub     rsp, 30h
0x140075607  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14007560e  mov     rbx, r9
0x140075611  mov     rdi, rdx
0x140075614  mov     rsi, rcx
0x140075617  test    rax, rax
0x14007561a  jnz     short loc_14007563B
0x14007561c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140075623  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140075628  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14007562f  test    rax, rax
0x140075632  jnz     short loc_14007563B
0x140075634  mov     eax, 0C0000139h
0x140075639  jmp     short loc_14007564C
0x14007563b  mov     r9, rbx
0x14007563e  xor     r8d, r8d
0x140075641  mov     rdx, rdi
0x140075644  mov     rcx, rsi
0x140075647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007564c  mov     rbx, [rsp+38h+arg_0]
0x140075651  mov     rsi, [rsp+38h+arg_8]
0x140075656  add     rsp, 30h
0x14007565a  pop     rdi
0x14007565b  retn
```
