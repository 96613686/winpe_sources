# wil_details_NtUpdateWnfStateData

- ea: `0x180008968`
- end: `0x1800089ee`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000653c`
- `0x1800082b0`

## callees

- `0x180008288`
- `0x180008968`
- `0x180026010`

## string_xrefs

- `0x18000898c`: `NtUpdateWnfStateData`

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
0x180008968  mov     [rsp+arg_0], rbx
0x18000896d  mov     [rsp+arg_8], rsi
0x180008972  push    rdi
0x180008973  sub     rsp, 40h
0x180008977  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000897e  mov     ebx, r8d
0x180008981  mov     rdi, rdx
0x180008984  mov     rsi, rcx
0x180008987  test    r10, r10
0x18000898a  jnz     short loc_1800089AE
0x18000898c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180008993  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180008998  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000899f  mov     r10, rax
0x1800089a2  test    rax, rax
0x1800089a5  jnz     short loc_1800089AE
0x1800089a7  mov     eax, 0C0000139h
0x1800089ac  jmp     short loc_1800089DE
0x1800089ae  mov     eax, [rsp+48h+arg_30]
0x1800089b5  xor     r9d, r9d
0x1800089b8  mov     [rsp+48h+var_18], eax
0x1800089bc  mov     r8d, ebx
0x1800089bf  mov     eax, [rsp+48h+arg_28]
0x1800089c3  mov     rdx, rdi
0x1800089c6  mov     [rsp+48h+var_20], eax
0x1800089ca  mov     rcx, rsi
0x1800089cd  mov     rax, r10
0x1800089d0  mov     [rsp+48h+var_28], 0
0x1800089d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089de  mov     rbx, [rsp+48h+arg_0]
0x1800089e3  mov     rsi, [rsp+48h+arg_8]
0x1800089e8  add     rsp, 40h
0x1800089ec  pop     rdi
0x1800089ed  retn
```
