# wil_details_NtUpdateWnfStateData

- ea: `0x1800090b8`
- end: `0x18000913e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180006a38`
- `0x180008de0`

## callees

- `0x180008db8`
- `0x1800090b8`
- `0x180029010`

## string_xrefs

- `0x1800090dc`: `NtUpdateWnfStateData`

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
0x1800090b8  mov     [rsp+arg_0], rbx
0x1800090bd  mov     [rsp+arg_8], rsi
0x1800090c2  push    rdi
0x1800090c3  sub     rsp, 40h
0x1800090c7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800090ce  mov     ebx, r8d
0x1800090d1  mov     rdi, rdx
0x1800090d4  mov     rsi, rcx
0x1800090d7  test    r10, r10
0x1800090da  jnz     short loc_1800090FE
0x1800090dc  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800090e3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800090e8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800090ef  mov     r10, rax
0x1800090f2  test    rax, rax
0x1800090f5  jnz     short loc_1800090FE
0x1800090f7  mov     eax, 0C0000139h
0x1800090fc  jmp     short loc_18000912E
0x1800090fe  mov     eax, [rsp+48h+arg_30]
0x180009105  xor     r9d, r9d
0x180009108  mov     [rsp+48h+var_18], eax
0x18000910c  mov     r8d, ebx
0x18000910f  mov     eax, [rsp+48h+arg_28]
0x180009113  mov     rdx, rdi
0x180009116  mov     [rsp+48h+var_20], eax
0x18000911a  mov     rcx, rsi
0x18000911d  mov     rax, r10
0x180009120  mov     [rsp+48h+var_28], 0
0x180009129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000912e  mov     rbx, [rsp+48h+arg_0]
0x180009133  mov     rsi, [rsp+48h+arg_8]
0x180009138  add     rsp, 40h
0x18000913c  pop     rdi
0x18000913d  retn
```
