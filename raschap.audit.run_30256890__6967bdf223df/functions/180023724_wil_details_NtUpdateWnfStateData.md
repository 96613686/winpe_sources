# wil_details_NtUpdateWnfStateData

- ea: `0x180023724`
- end: `0x1800237aa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180021754`
- `0x180023218`

## callees

- `0x1800231f0`
- `0x180023724`
- `0x180027010`

## string_xrefs

- `0x180023748`: `NtUpdateWnfStateData`

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
0x180023724  mov     [rsp+arg_0], rbx
0x180023729  mov     [rsp+arg_8], rsi
0x18002372e  push    rdi
0x18002372f  sub     rsp, 40h
0x180023733  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002373a  mov     ebx, r8d
0x18002373d  mov     rdi, rdx
0x180023740  mov     rsi, rcx
0x180023743  test    r10, r10
0x180023746  jnz     short loc_18002376A
0x180023748  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002374f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180023754  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002375b  mov     r10, rax
0x18002375e  test    rax, rax
0x180023761  jnz     short loc_18002376A
0x180023763  mov     eax, 0C0000139h
0x180023768  jmp     short loc_18002379A
0x18002376a  mov     eax, [rsp+48h+arg_30]
0x180023771  xor     r9d, r9d
0x180023774  mov     [rsp+48h+var_18], eax
0x180023778  mov     r8d, ebx
0x18002377b  mov     eax, [rsp+48h+arg_28]
0x18002377f  mov     rdx, rdi
0x180023782  mov     [rsp+48h+var_20], eax
0x180023786  mov     rcx, rsi
0x180023789  mov     rax, r10
0x18002378c  mov     [rsp+48h+var_28], 0
0x180023795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002379a  mov     rbx, [rsp+48h+arg_0]
0x18002379f  mov     rsi, [rsp+48h+arg_8]
0x1800237a4  add     rsp, 40h
0x1800237a8  pop     rdi
0x1800237a9  retn
```
