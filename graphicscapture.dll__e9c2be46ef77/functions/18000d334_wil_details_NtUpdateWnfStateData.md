# wil_details_NtUpdateWnfStateData

- ea: `0x18000d334`
- end: `0x18000d3ba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000acac`
- `0x18000cdd8`

## callees

- `0x18000cdb0`
- `0x18000d334`
- `0x180028010`

## string_xrefs

- `0x18000d358`: `NtUpdateWnfStateData`

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
0x18000d334  mov     [rsp+arg_0], rbx
0x18000d339  mov     [rsp+arg_8], rsi
0x18000d33e  push    rdi
0x18000d33f  sub     rsp, 40h
0x18000d343  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d34a  mov     ebx, r8d
0x18000d34d  mov     rdi, rdx
0x18000d350  mov     rsi, rcx
0x18000d353  test    r10, r10
0x18000d356  jnz     short loc_18000D37A
0x18000d358  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d35f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d364  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d36b  mov     r10, rax
0x18000d36e  test    rax, rax
0x18000d371  jnz     short loc_18000D37A
0x18000d373  mov     eax, 0C0000139h
0x18000d378  jmp     short loc_18000D3AA
0x18000d37a  mov     eax, [rsp+48h+arg_30]
0x18000d381  xor     r9d, r9d
0x18000d384  mov     [rsp+48h+var_18], eax
0x18000d388  mov     r8d, ebx
0x18000d38b  mov     eax, [rsp+48h+arg_28]
0x18000d38f  mov     rdx, rdi
0x18000d392  mov     [rsp+48h+var_20], eax
0x18000d396  mov     rcx, rsi
0x18000d399  mov     rax, r10
0x18000d39c  mov     [rsp+48h+var_28], 0
0x18000d3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3aa  mov     rbx, [rsp+48h+arg_0]
0x18000d3af  mov     rsi, [rsp+48h+arg_8]
0x18000d3b4  add     rsp, 40h
0x18000d3b8  pop     rdi
0x18000d3b9  retn
```
