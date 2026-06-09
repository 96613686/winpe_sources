# wil_details_NtUpdateWnfStateData

- ea: `0x18000b474`
- end: `0x18000b4fa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180009b04`
- `0x18000aae0`

## callees

- `0x1800071f8`
- `0x18000b474`
- `0x18001c010`

## string_xrefs

- `0x18000b498`: `NtUpdateWnfStateData`

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
0x18000b474  mov     [rsp+arg_0], rbx
0x18000b479  mov     [rsp+arg_8], rsi
0x18000b47e  push    rdi
0x18000b47f  sub     rsp, 40h
0x18000b483  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b48a  mov     ebx, r8d
0x18000b48d  mov     rdi, rdx
0x18000b490  mov     rsi, rcx
0x18000b493  test    r10, r10
0x18000b496  jnz     short loc_18000B4BA
0x18000b498  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b49f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b4a4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b4ab  mov     r10, rax
0x18000b4ae  test    rax, rax
0x18000b4b1  jnz     short loc_18000B4BA
0x18000b4b3  mov     eax, 0C0000139h
0x18000b4b8  jmp     short loc_18000B4EA
0x18000b4ba  mov     eax, [rsp+48h+arg_30]
0x18000b4c1  xor     r9d, r9d
0x18000b4c4  mov     [rsp+48h+var_18], eax
0x18000b4c8  mov     r8d, ebx
0x18000b4cb  mov     eax, [rsp+48h+arg_28]
0x18000b4cf  mov     rdx, rdi
0x18000b4d2  mov     [rsp+48h+var_20], eax
0x18000b4d6  mov     rcx, rsi
0x18000b4d9  mov     rax, r10
0x18000b4dc  mov     [rsp+48h+var_28], 0
0x18000b4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ea  mov     rbx, [rsp+48h+arg_0]
0x18000b4ef  mov     rsi, [rsp+48h+arg_8]
0x18000b4f4  add     rsp, 40h
0x18000b4f8  pop     rdi
0x18000b4f9  retn
```
