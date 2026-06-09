# wil_details_NtUpdateWnfStateData

- ea: `0x18000e6c8`
- end: `0x18000e74f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ccb4`
- `0x18000dd04`

## callees

- `0x180009fb8`
- `0x18000e6c8`
- `0x180039010`

## string_xrefs

- `0x18000e6ec`: `NtUpdateWnfStateData`

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
0x18000e6c8  mov     [rsp+arg_0], rbx
0x18000e6cd  mov     [rsp+arg_8], rsi
0x18000e6d2  push    rdi
0x18000e6d3  sub     rsp, 40h
0x18000e6d7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e6de  mov     ebx, r8d
0x18000e6e1  mov     rdi, rdx
0x18000e6e4  mov     rsi, rcx
0x18000e6e7  test    r10, r10
0x18000e6ea  jnz     short loc_18000E70E
0x18000e6ec  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e6f3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e6f8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e6ff  mov     r10, rax
0x18000e702  test    rax, rax
0x18000e705  jnz     short loc_18000E70E
0x18000e707  mov     eax, 0C0000139h
0x18000e70c  jmp     short loc_18000E73E
0x18000e70e  mov     eax, [rsp+48h+arg_30]
0x18000e715  xor     r9d, r9d
0x18000e718  mov     [rsp+48h+var_18], eax
0x18000e71c  mov     r8d, ebx
0x18000e71f  mov     eax, [rsp+48h+arg_28]
0x18000e723  mov     rdx, rdi
0x18000e726  mov     [rsp+48h+var_20], eax
0x18000e72a  mov     rcx, rsi
0x18000e72d  mov     rax, r10
0x18000e730  mov     [rsp+48h+var_28], 0
0x18000e739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e73e  mov     rbx, [rsp+48h+arg_0]
0x18000e743  mov     rsi, [rsp+48h+arg_8]
0x18000e748  add     rsp, 40h
0x18000e74c  pop     rdi
0x18000e74d  retn
```
