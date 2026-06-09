# wil_details_NtUpdateWnfStateData

- ea: `0x18000b5c8`
- end: `0x18000b64e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180009474`
- `0x18000b2c0`

## callees

- `0x18000b298`
- `0x18000b5c8`
- `0x180031010`

## string_xrefs

- `0x18000b5ec`: `NtUpdateWnfStateData`

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
0x18000b5c8  mov     [rsp+arg_0], rbx
0x18000b5cd  mov     [rsp+arg_8], rsi
0x18000b5d2  push    rdi
0x18000b5d3  sub     rsp, 40h
0x18000b5d7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b5de  mov     ebx, r8d
0x18000b5e1  mov     rdi, rdx
0x18000b5e4  mov     rsi, rcx
0x18000b5e7  test    r10, r10
0x18000b5ea  jnz     short loc_18000B60E
0x18000b5ec  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b5f3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b5f8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b5ff  mov     r10, rax
0x18000b602  test    rax, rax
0x18000b605  jnz     short loc_18000B60E
0x18000b607  mov     eax, 0C0000139h
0x18000b60c  jmp     short loc_18000B63E
0x18000b60e  mov     eax, [rsp+48h+arg_30]
0x18000b615  xor     r9d, r9d
0x18000b618  mov     [rsp+48h+var_18], eax
0x18000b61c  mov     r8d, ebx
0x18000b61f  mov     eax, [rsp+48h+arg_28]
0x18000b623  mov     rdx, rdi
0x18000b626  mov     [rsp+48h+var_20], eax
0x18000b62a  mov     rcx, rsi
0x18000b62d  mov     rax, r10
0x18000b630  mov     [rsp+48h+var_28], 0
0x18000b639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63e  mov     rbx, [rsp+48h+arg_0]
0x18000b643  mov     rsi, [rsp+48h+arg_8]
0x18000b648  add     rsp, 40h
0x18000b64c  pop     rdi
0x18000b64d  retn
```
