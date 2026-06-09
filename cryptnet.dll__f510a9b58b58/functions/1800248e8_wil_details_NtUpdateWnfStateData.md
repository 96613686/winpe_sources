# wil_details_NtUpdateWnfStateData

- ea: `0x1800248e8`
- end: `0x18002496e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180023198`
- `0x180024640`

## callees

- `0x180024618`
- `0x1800248e8`
- `0x180027010`

## string_xrefs

- `0x18002490c`: `NtUpdateWnfStateData`

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
0x1800248e8  mov     [rsp+arg_0], rbx
0x1800248ed  mov     [rsp+arg_8], rsi
0x1800248f2  push    rdi
0x1800248f3  sub     rsp, 40h
0x1800248f7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800248fe  mov     ebx, r8d
0x180024901  mov     rdi, rdx
0x180024904  mov     rsi, rcx
0x180024907  test    r10, r10
0x18002490a  jnz     short loc_18002492E
0x18002490c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180024913  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180024918  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002491f  mov     r10, rax
0x180024922  test    rax, rax
0x180024925  jnz     short loc_18002492E
0x180024927  mov     eax, 0C0000139h
0x18002492c  jmp     short loc_18002495E
0x18002492e  mov     eax, [rsp+48h+arg_30]
0x180024935  xor     r9d, r9d
0x180024938  mov     [rsp+48h+var_18], eax
0x18002493c  mov     r8d, ebx
0x18002493f  mov     eax, [rsp+48h+arg_28]
0x180024943  mov     rdx, rdi
0x180024946  mov     [rsp+48h+var_20], eax
0x18002494a  mov     rcx, rsi
0x18002494d  mov     rax, r10
0x180024950  mov     [rsp+48h+var_28], 0
0x180024959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002495e  mov     rbx, [rsp+48h+arg_0]
0x180024963  mov     rsi, [rsp+48h+arg_8]
0x180024968  add     rsp, 40h
0x18002496c  pop     rdi
0x18002496d  retn
```
