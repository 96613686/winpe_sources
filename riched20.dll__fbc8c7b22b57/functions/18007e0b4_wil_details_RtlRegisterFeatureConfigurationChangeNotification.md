# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18007e0b4`
- end: `0x18007e119`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18007c85c`

## callees

- `0x18007d698`
- `0x18007e0b4`
- `0x180095010`

## string_xrefs

- `0x18007e0d8`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18007e0b4  mov     [rsp+arg_0], rbx
0x18007e0b9  mov     [rsp+arg_8], rsi
0x18007e0be  push    rdi
0x18007e0bf  sub     rsp, 30h
0x18007e0c3  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18007e0ca  mov     rbx, r9
0x18007e0cd  mov     rdi, rdx
0x18007e0d0  mov     rsi, rcx
0x18007e0d3  test    rax, rax
0x18007e0d6  jnz     short loc_18007E0F7
0x18007e0d8  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18007e0df  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18007e0e4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18007e0eb  test    rax, rax
0x18007e0ee  jnz     short loc_18007E0F7
0x18007e0f0  mov     eax, 0C0000139h
0x18007e0f5  jmp     short loc_18007E108
0x18007e0f7  mov     r9, rbx
0x18007e0fa  xor     r8d, r8d
0x18007e0fd  mov     rdx, rdi
0x18007e100  mov     rcx, rsi
0x18007e103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e108  mov     rbx, [rsp+38h+arg_0]
0x18007e10d  mov     rsi, [rsp+38h+arg_8]
0x18007e112  add     rsp, 30h
0x18007e116  pop     rdi
0x18007e117  retn
```
