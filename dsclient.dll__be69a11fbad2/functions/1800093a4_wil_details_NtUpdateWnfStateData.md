# wil_details_NtUpdateWnfStateData

- ea: `0x1800093a4`
- end: `0x18000942a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180007520`
- `0x180008f68`

## callees

- `0x180008f40`
- `0x1800093a4`
- `0x18000a010`

## string_xrefs

- `0x1800093c8`: `NtUpdateWnfStateData`

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
0x1800093a4  mov     [rsp+arg_0], rbx
0x1800093a9  mov     [rsp+arg_8], rsi
0x1800093ae  push    rdi
0x1800093af  sub     rsp, 40h
0x1800093b3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800093ba  mov     ebx, r8d
0x1800093bd  mov     rdi, rdx
0x1800093c0  mov     rsi, rcx
0x1800093c3  test    r10, r10
0x1800093c6  jnz     short loc_1800093EA
0x1800093c8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800093cf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800093d4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800093db  mov     r10, rax
0x1800093de  test    rax, rax
0x1800093e1  jnz     short loc_1800093EA
0x1800093e3  mov     eax, 0C0000139h
0x1800093e8  jmp     short loc_18000941A
0x1800093ea  mov     eax, [rsp+48h+arg_30]
0x1800093f1  xor     r9d, r9d
0x1800093f4  mov     [rsp+48h+var_18], eax
0x1800093f8  mov     r8d, ebx
0x1800093fb  mov     eax, [rsp+48h+arg_28]
0x1800093ff  mov     rdx, rdi
0x180009402  mov     [rsp+48h+var_20], eax
0x180009406  mov     rcx, rsi
0x180009409  mov     rax, r10
0x18000940c  mov     [rsp+48h+var_28], 0
0x180009415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000941a  mov     rbx, [rsp+48h+arg_0]
0x18000941f  mov     rsi, [rsp+48h+arg_8]
0x180009424  add     rsp, 40h
0x180009428  pop     rdi
0x180009429  retn
```
