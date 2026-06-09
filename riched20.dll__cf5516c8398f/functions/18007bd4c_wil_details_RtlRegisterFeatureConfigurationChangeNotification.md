# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18007bd4c`
- end: `0x18007bdb0`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18007a4ac`

## callees

- `0x18007b348`
- `0x18007bd4c`
- `0x180092010`

## string_xrefs

- `0x18007bd70`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18007bd4c  mov     [rsp+arg_0], rbx
0x18007bd51  mov     [rsp+arg_8], rsi
0x18007bd56  push    rdi
0x18007bd57  sub     rsp, 30h
0x18007bd5b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18007bd62  mov     rbx, r9
0x18007bd65  mov     rdi, rdx
0x18007bd68  mov     rsi, rcx
0x18007bd6b  test    rax, rax
0x18007bd6e  jnz     short loc_18007BD8F
0x18007bd70  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18007bd77  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18007bd7c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18007bd83  test    rax, rax
0x18007bd86  jnz     short loc_18007BD8F
0x18007bd88  mov     eax, 0C0000139h
0x18007bd8d  jmp     short loc_18007BDA0
0x18007bd8f  mov     r9, rbx
0x18007bd92  xor     r8d, r8d
0x18007bd95  mov     rdx, rdi
0x18007bd98  mov     rcx, rsi
0x18007bd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bda0  mov     rbx, [rsp+38h+arg_0]
0x18007bda5  mov     rsi, [rsp+38h+arg_8]
0x18007bdaa  add     rsp, 30h
0x18007bdae  pop     rdi
0x18007bdaf  retn
```
