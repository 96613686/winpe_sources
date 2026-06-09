# wil_details_NtUpdateWnfStateData

- ea: `0x18001628c`
- end: `0x180016312`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800155c4`
- `0x180015ed0`

## callees

- `0x18000d720`
- `0x18001628c`
- `0x180027010`

## string_xrefs

- `0x1800162b0`: `NtUpdateWnfStateData`

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
0x18001628c  mov     [rsp+arg_0], rbx
0x180016291  mov     [rsp+arg_8], rsi
0x180016296  push    rdi
0x180016297  sub     rsp, 40h
0x18001629b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800162a2  mov     ebx, r8d
0x1800162a5  mov     rdi, rdx
0x1800162a8  mov     rsi, rcx
0x1800162ab  test    r10, r10
0x1800162ae  jnz     short loc_1800162D2
0x1800162b0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800162b7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800162bc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800162c3  mov     r10, rax
0x1800162c6  test    rax, rax
0x1800162c9  jnz     short loc_1800162D2
0x1800162cb  mov     eax, 0C0000139h
0x1800162d0  jmp     short loc_180016302
0x1800162d2  mov     eax, [rsp+48h+arg_30]
0x1800162d9  xor     r9d, r9d
0x1800162dc  mov     [rsp+48h+var_18], eax
0x1800162e0  mov     r8d, ebx
0x1800162e3  mov     eax, [rsp+48h+arg_28]
0x1800162e7  mov     rdx, rdi
0x1800162ea  mov     [rsp+48h+var_20], eax
0x1800162ee  mov     rcx, rsi
0x1800162f1  mov     rax, r10
0x1800162f4  mov     [rsp+48h+var_28], 0
0x1800162fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016302  mov     rbx, [rsp+48h+arg_0]
0x180016307  mov     rsi, [rsp+48h+arg_8]
0x18001630c  add     rsp, 40h
0x180016310  pop     rdi
0x180016311  retn
```
