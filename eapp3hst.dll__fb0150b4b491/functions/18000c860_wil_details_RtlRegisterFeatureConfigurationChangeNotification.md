# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000c860`
- end: `0x18000c8c4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b5a0`

## callees

- `0x180003910`
- `0x18000c860`
- `0x180034010`

## string_xrefs

- `0x18000c884`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000c860  mov     [rsp+arg_0], rbx
0x18000c865  mov     [rsp+arg_8], rsi
0x18000c86a  push    rdi
0x18000c86b  sub     rsp, 30h
0x18000c86f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000c876  mov     rbx, r9
0x18000c879  mov     rdi, rdx
0x18000c87c  mov     rsi, rcx
0x18000c87f  test    rax, rax
0x18000c882  jnz     short loc_18000C8A3
0x18000c884  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000c88b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000c890  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000c897  test    rax, rax
0x18000c89a  jnz     short loc_18000C8A3
0x18000c89c  mov     eax, 0C0000139h
0x18000c8a1  jmp     short loc_18000C8B4
0x18000c8a3  mov     r9, rbx
0x18000c8a6  xor     r8d, r8d
0x18000c8a9  mov     rdx, rdi
0x18000c8ac  mov     rcx, rsi
0x18000c8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8b4  mov     rbx, [rsp+38h+arg_0]
0x18000c8b9  mov     rsi, [rsp+38h+arg_8]
0x18000c8be  add     rsp, 30h
0x18000c8c2  pop     rdi
0x18000c8c3  retn
```
