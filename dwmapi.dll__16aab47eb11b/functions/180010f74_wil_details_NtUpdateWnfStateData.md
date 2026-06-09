# wil_details_NtUpdateWnfStateData

- ea: `0x180010f74`
- end: `0x180010ffa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000fc30`
- `0x180010b20`

## callees

- `0x180009b4c`
- `0x180010f74`
- `0x180017010`

## string_xrefs

- `0x180010f98`: `NtUpdateWnfStateData`

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
0x180010f74  mov     [rsp+arg_0], rbx
0x180010f79  mov     [rsp+arg_8], rsi
0x180010f7e  push    rdi
0x180010f7f  sub     rsp, 40h
0x180010f83  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180010f8a  mov     ebx, r8d
0x180010f8d  mov     rdi, rdx
0x180010f90  mov     rsi, rcx
0x180010f93  test    r10, r10
0x180010f96  jnz     short loc_180010FBA
0x180010f98  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180010f9f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180010fa4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180010fab  mov     r10, rax
0x180010fae  test    rax, rax
0x180010fb1  jnz     short loc_180010FBA
0x180010fb3  mov     eax, 0C0000139h
0x180010fb8  jmp     short loc_180010FEA
0x180010fba  mov     eax, [rsp+48h+arg_30]
0x180010fc1  xor     r9d, r9d
0x180010fc4  mov     [rsp+48h+var_18], eax
0x180010fc8  mov     r8d, ebx
0x180010fcb  mov     eax, [rsp+48h+arg_28]
0x180010fcf  mov     rdx, rdi
0x180010fd2  mov     [rsp+48h+var_20], eax
0x180010fd6  mov     rcx, rsi
0x180010fd9  mov     rax, r10
0x180010fdc  mov     [rsp+48h+var_28], 0
0x180010fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fea  mov     rbx, [rsp+48h+arg_0]
0x180010fef  mov     rsi, [rsp+48h+arg_8]
0x180010ff4  add     rsp, 40h
0x180010ff8  pop     rdi
0x180010ff9  retn
```
