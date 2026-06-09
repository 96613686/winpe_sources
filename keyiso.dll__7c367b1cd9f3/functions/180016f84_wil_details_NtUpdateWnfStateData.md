# wil_details_NtUpdateWnfStateData

- ea: `0x180016f84`
- end: `0x18001700a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180014d94`
- `0x180016c18`

## callees

- `0x180016bf0`
- `0x180016f84`
- `0x180019010`

## string_xrefs

- `0x180016fa8`: `NtUpdateWnfStateData`

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
0x180016f84  mov     [rsp+arg_0], rbx
0x180016f89  mov     [rsp+arg_8], rsi
0x180016f8e  push    rdi
0x180016f8f  sub     rsp, 40h
0x180016f93  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180016f9a  mov     ebx, r8d
0x180016f9d  mov     rdi, rdx
0x180016fa0  mov     rsi, rcx
0x180016fa3  test    r10, r10
0x180016fa6  jnz     short loc_180016FCA
0x180016fa8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180016faf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180016fb4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180016fbb  mov     r10, rax
0x180016fbe  test    rax, rax
0x180016fc1  jnz     short loc_180016FCA
0x180016fc3  mov     eax, 0C0000139h
0x180016fc8  jmp     short loc_180016FFA
0x180016fca  mov     eax, [rsp+48h+arg_30]
0x180016fd1  xor     r9d, r9d
0x180016fd4  mov     [rsp+48h+var_18], eax
0x180016fd8  mov     r8d, ebx
0x180016fdb  mov     eax, [rsp+48h+arg_28]
0x180016fdf  mov     rdx, rdi
0x180016fe2  mov     [rsp+48h+var_20], eax
0x180016fe6  mov     rcx, rsi
0x180016fe9  mov     rax, r10
0x180016fec  mov     [rsp+48h+var_28], 0
0x180016ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ffa  mov     rbx, [rsp+48h+arg_0]
0x180016fff  mov     rsi, [rsp+48h+arg_8]
0x180017004  add     rsp, 40h
0x180017008  pop     rdi
0x180017009  retn
```
