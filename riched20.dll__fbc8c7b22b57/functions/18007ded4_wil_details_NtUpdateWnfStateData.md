# wil_details_NtUpdateWnfStateData

- ea: `0x18007ded4`
- end: `0x18007df5b`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18007baf0`
- `0x18007d6c4`

## callees

- `0x18007d698`
- `0x18007ded4`
- `0x180095010`

## string_xrefs

- `0x18007def8`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)wil_details_GetNtDllProcedureAddress("NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18007ded4  mov     [rsp+arg_0], rbx
0x18007ded9  mov     [rsp+arg_8], rsi
0x18007dede  push    rdi
0x18007dedf  sub     rsp, 40h
0x18007dee3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18007deea  mov     ebx, r8d
0x18007deed  mov     rdi, rdx
0x18007def0  mov     rsi, rcx
0x18007def3  test    r10, r10
0x18007def6  jnz     short loc_18007DF1A
0x18007def8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18007deff  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18007df04  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18007df0b  mov     r10, rax
0x18007df0e  test    rax, rax
0x18007df11  jnz     short loc_18007DF1A
0x18007df13  mov     eax, 0C0000139h
0x18007df18  jmp     short loc_18007DF4A
0x18007df1a  mov     eax, [rsp+48h+arg_30]
0x18007df21  xor     r9d, r9d
0x18007df24  mov     [rsp+48h+var_18], eax
0x18007df28  mov     r8d, ebx
0x18007df2b  mov     eax, [rsp+48h+arg_28]
0x18007df2f  mov     rdx, rdi
0x18007df32  mov     [rsp+48h+var_20], eax
0x18007df36  mov     rcx, rsi
0x18007df39  mov     rax, r10
0x18007df3c  mov     [rsp+48h+var_28], 0
0x18007df45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007df4a  mov     rbx, [rsp+48h+arg_0]
0x18007df4f  mov     rsi, [rsp+48h+arg_8]
0x18007df54  add     rsp, 40h
0x18007df58  pop     rdi
0x18007df59  retn
```
