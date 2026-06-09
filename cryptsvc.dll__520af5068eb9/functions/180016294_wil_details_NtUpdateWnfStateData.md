# wil_details_NtUpdateWnfStateData

- ea: `0x180016294`
- end: `0x18001631a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800144bc`
- `0x180015a7c`

## callees

- `0x180015a54`
- `0x180016294`
- `0x180018010`

## string_xrefs

- `0x1800162b8`: `NtUpdateWnfStateData`

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
0x180016294  mov     [rsp+arg_0], rbx
0x180016299  mov     [rsp+arg_8], rsi
0x18001629e  push    rdi
0x18001629f  sub     rsp, 40h
0x1800162a3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800162aa  mov     ebx, r8d
0x1800162ad  mov     rdi, rdx
0x1800162b0  mov     rsi, rcx
0x1800162b3  test    r10, r10
0x1800162b6  jnz     short loc_1800162DA
0x1800162b8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800162bf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800162c4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800162cb  mov     r10, rax
0x1800162ce  test    rax, rax
0x1800162d1  jnz     short loc_1800162DA
0x1800162d3  mov     eax, 0C0000139h
0x1800162d8  jmp     short loc_18001630A
0x1800162da  mov     eax, [rsp+48h+arg_30]
0x1800162e1  xor     r9d, r9d
0x1800162e4  mov     [rsp+48h+var_18], eax
0x1800162e8  mov     r8d, ebx
0x1800162eb  mov     eax, [rsp+48h+arg_28]
0x1800162ef  mov     rdx, rdi
0x1800162f2  mov     [rsp+48h+var_20], eax
0x1800162f6  mov     rcx, rsi
0x1800162f9  mov     rax, r10
0x1800162fc  mov     [rsp+48h+var_28], 0
0x180016305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001630a  mov     rbx, [rsp+48h+arg_0]
0x18001630f  mov     rsi, [rsp+48h+arg_8]
0x180016314  add     rsp, 40h
0x180016318  pop     rdi
0x180016319  retn
```
