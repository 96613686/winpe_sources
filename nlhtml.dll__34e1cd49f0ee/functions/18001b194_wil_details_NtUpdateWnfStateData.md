# wil_details_NtUpdateWnfStateData

- ea: `0x18001b194`
- end: `0x18001b21a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180018ef8`
- `0x18001acc8`

## callees

- `0x18001aca0`
- `0x18001b194`
- `0x180025010`

## string_xrefs

- `0x18001b1b8`: `NtUpdateWnfStateData`

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
0x18001b194  mov     [rsp+arg_0], rbx
0x18001b199  mov     [rsp+arg_8], rsi
0x18001b19e  push    rdi
0x18001b19f  sub     rsp, 40h
0x18001b1a3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001b1aa  mov     ebx, r8d
0x18001b1ad  mov     rdi, rdx
0x18001b1b0  mov     rsi, rcx
0x18001b1b3  test    r10, r10
0x18001b1b6  jnz     short loc_18001B1DA
0x18001b1b8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001b1bf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b1c4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001b1cb  mov     r10, rax
0x18001b1ce  test    rax, rax
0x18001b1d1  jnz     short loc_18001B1DA
0x18001b1d3  mov     eax, 0C0000139h
0x18001b1d8  jmp     short loc_18001B20A
0x18001b1da  mov     eax, [rsp+48h+arg_30]
0x18001b1e1  xor     r9d, r9d
0x18001b1e4  mov     [rsp+48h+var_18], eax
0x18001b1e8  mov     r8d, ebx
0x18001b1eb  mov     eax, [rsp+48h+arg_28]
0x18001b1ef  mov     rdx, rdi
0x18001b1f2  mov     [rsp+48h+var_20], eax
0x18001b1f6  mov     rcx, rsi
0x18001b1f9  mov     rax, r10
0x18001b1fc  mov     [rsp+48h+var_28], 0
0x18001b205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b20a  mov     rbx, [rsp+48h+arg_0]
0x18001b20f  mov     rsi, [rsp+48h+arg_8]
0x18001b214  add     rsp, 40h
0x18001b218  pop     rdi
0x18001b219  retn
```
