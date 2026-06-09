# wil_details_NtUpdateWnfStateData

- ea: `0x180016574`
- end: `0x1800165fa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800117d0`
- `0x1800137f8`

## callees

- `0x18000d400`
- `0x180016574`
- `0x18004b010`

## string_xrefs

- `0x180016598`: `NtUpdateWnfStateData`

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
0x180016574  mov     [rsp+arg_0], rbx
0x180016579  mov     [rsp+arg_8], rsi
0x18001657e  push    rdi
0x18001657f  sub     rsp, 40h
0x180016583  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001658a  mov     ebx, r8d
0x18001658d  mov     rdi, rdx
0x180016590  mov     rsi, rcx
0x180016593  test    r10, r10
0x180016596  jnz     short loc_1800165BA
0x180016598  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001659f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800165a4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800165ab  mov     r10, rax
0x1800165ae  test    rax, rax
0x1800165b1  jnz     short loc_1800165BA
0x1800165b3  mov     eax, 0C0000139h
0x1800165b8  jmp     short loc_1800165EA
0x1800165ba  mov     eax, [rsp+48h+arg_30]
0x1800165c1  xor     r9d, r9d
0x1800165c4  mov     [rsp+48h+var_18], eax
0x1800165c8  mov     r8d, ebx
0x1800165cb  mov     eax, [rsp+48h+arg_28]
0x1800165cf  mov     rdx, rdi
0x1800165d2  mov     [rsp+48h+var_20], eax
0x1800165d6  mov     rcx, rsi
0x1800165d9  mov     rax, r10
0x1800165dc  mov     [rsp+48h+var_28], 0
0x1800165e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ea  mov     rbx, [rsp+48h+arg_0]
0x1800165ef  mov     rsi, [rsp+48h+arg_8]
0x1800165f4  add     rsp, 40h
0x1800165f8  pop     rdi
0x1800165f9  retn
```
