# wil_details_NtUpdateWnfStateData

- ea: `0x180016074`
- end: `0x1800160fa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180014d54`
- `0x180015b8c`

## callees

- `0x18000bd6c`
- `0x180016074`
- `0x180018010`

## string_xrefs

- `0x180016098`: `NtUpdateWnfStateData`

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
0x180016074  mov     [rsp+arg_0], rbx
0x180016079  mov     [rsp+arg_8], rsi
0x18001607e  push    rdi
0x18001607f  sub     rsp, 40h
0x180016083  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001608a  mov     ebx, r8d
0x18001608d  mov     rdi, rdx
0x180016090  mov     rsi, rcx
0x180016093  test    r10, r10
0x180016096  jnz     short loc_1800160BA
0x180016098  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001609f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800160a4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800160ab  mov     r10, rax
0x1800160ae  test    rax, rax
0x1800160b1  jnz     short loc_1800160BA
0x1800160b3  mov     eax, 0C0000139h
0x1800160b8  jmp     short loc_1800160EA
0x1800160ba  mov     eax, [rsp+48h+arg_30]
0x1800160c1  xor     r9d, r9d
0x1800160c4  mov     [rsp+48h+var_18], eax
0x1800160c8  mov     r8d, ebx
0x1800160cb  mov     eax, [rsp+48h+arg_28]
0x1800160cf  mov     rdx, rdi
0x1800160d2  mov     [rsp+48h+var_20], eax
0x1800160d6  mov     rcx, rsi
0x1800160d9  mov     rax, r10
0x1800160dc  mov     [rsp+48h+var_28], 0
0x1800160e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ea  mov     rbx, [rsp+48h+arg_0]
0x1800160ef  mov     rsi, [rsp+48h+arg_8]
0x1800160f4  add     rsp, 40h
0x1800160f8  pop     rdi
0x1800160f9  retn
```
