# wil_details_NtUpdateWnfStateData

- ea: `0x18000e9e4`
- end: `0x18000ea6a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ae3c`
- `0x18000dd98`

## callees

- `0x18000dd70`
- `0x18000e9e4`
- `0x18002d010`

## string_xrefs

- `0x18000ea08`: `NtUpdateWnfStateData`

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
0x18000e9e4  mov     [rsp+arg_0], rbx
0x18000e9e9  mov     [rsp+arg_8], rsi
0x18000e9ee  push    rdi
0x18000e9ef  sub     rsp, 40h
0x18000e9f3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e9fa  mov     ebx, r8d
0x18000e9fd  mov     rdi, rdx
0x18000ea00  mov     rsi, rcx
0x18000ea03  test    r10, r10
0x18000ea06  jnz     short loc_18000EA2A
0x18000ea08  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000ea0f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ea14  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000ea1b  mov     r10, rax
0x18000ea1e  test    rax, rax
0x18000ea21  jnz     short loc_18000EA2A
0x18000ea23  mov     eax, 0C0000139h
0x18000ea28  jmp     short loc_18000EA5A
0x18000ea2a  mov     eax, [rsp+48h+arg_30]
0x18000ea31  xor     r9d, r9d
0x18000ea34  mov     [rsp+48h+var_18], eax
0x18000ea38  mov     r8d, ebx
0x18000ea3b  mov     eax, [rsp+48h+arg_28]
0x18000ea3f  mov     rdx, rdi
0x18000ea42  mov     [rsp+48h+var_20], eax
0x18000ea46  mov     rcx, rsi
0x18000ea49  mov     rax, r10
0x18000ea4c  mov     [rsp+48h+var_28], 0
0x18000ea55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea5a  mov     rbx, [rsp+48h+arg_0]
0x18000ea5f  mov     rsi, [rsp+48h+arg_8]
0x18000ea64  add     rsp, 40h
0x18000ea68  pop     rdi
0x18000ea69  retn
```
