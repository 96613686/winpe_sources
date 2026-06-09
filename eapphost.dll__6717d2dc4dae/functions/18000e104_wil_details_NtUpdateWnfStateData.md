# wil_details_NtUpdateWnfStateData

- ea: `0x18000e104`
- end: `0x18000e18a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c768`
- `0x18000d79c`

## callees

- `0x180009b70`
- `0x18000e104`
- `0x180038010`

## string_xrefs

- `0x18000e128`: `NtUpdateWnfStateData`

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
0x18000e104  mov     [rsp+arg_0], rbx
0x18000e109  mov     [rsp+arg_8], rsi
0x18000e10e  push    rdi
0x18000e10f  sub     rsp, 40h
0x18000e113  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e11a  mov     ebx, r8d
0x18000e11d  mov     rdi, rdx
0x18000e120  mov     rsi, rcx
0x18000e123  test    r10, r10
0x18000e126  jnz     short loc_18000E14A
0x18000e128  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e12f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e134  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e13b  mov     r10, rax
0x18000e13e  test    rax, rax
0x18000e141  jnz     short loc_18000E14A
0x18000e143  mov     eax, 0C0000139h
0x18000e148  jmp     short loc_18000E17A
0x18000e14a  mov     eax, [rsp+48h+arg_30]
0x18000e151  xor     r9d, r9d
0x18000e154  mov     [rsp+48h+var_18], eax
0x18000e158  mov     r8d, ebx
0x18000e15b  mov     eax, [rsp+48h+arg_28]
0x18000e15f  mov     rdx, rdi
0x18000e162  mov     [rsp+48h+var_20], eax
0x18000e166  mov     rcx, rsi
0x18000e169  mov     rax, r10
0x18000e16c  mov     [rsp+48h+var_28], 0
0x18000e175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e17a  mov     rbx, [rsp+48h+arg_0]
0x18000e17f  mov     rsi, [rsp+48h+arg_8]
0x18000e184  add     rsp, 40h
0x18000e188  pop     rdi
0x18000e189  retn
```
