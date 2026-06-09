# wil_details_NtUpdateWnfStateData

- ea: `0x18001664c`
- end: `0x1800166d2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180013530`
- `0x180015438`

## callees

- `0x180015410`
- `0x18001664c`
- `0x180020010`

## string_xrefs

- `0x180016670`: `NtUpdateWnfStateData`

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
0x18001664c  mov     [rsp+arg_0], rbx
0x180016651  mov     [rsp+arg_8], rsi
0x180016656  push    rdi
0x180016657  sub     rsp, 40h
0x18001665b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180016662  mov     ebx, r8d
0x180016665  mov     rdi, rdx
0x180016668  mov     rsi, rcx
0x18001666b  test    r10, r10
0x18001666e  jnz     short loc_180016692
0x180016670  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180016677  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001667c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180016683  mov     r10, rax
0x180016686  test    rax, rax
0x180016689  jnz     short loc_180016692
0x18001668b  mov     eax, 0C0000139h
0x180016690  jmp     short loc_1800166C2
0x180016692  mov     eax, [rsp+48h+arg_30]
0x180016699  xor     r9d, r9d
0x18001669c  mov     [rsp+48h+var_18], eax
0x1800166a0  mov     r8d, ebx
0x1800166a3  mov     eax, [rsp+48h+arg_28]
0x1800166a7  mov     rdx, rdi
0x1800166aa  mov     [rsp+48h+var_20], eax
0x1800166ae  mov     rcx, rsi
0x1800166b1  mov     rax, r10
0x1800166b4  mov     [rsp+48h+var_28], 0
0x1800166bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166c2  mov     rbx, [rsp+48h+arg_0]
0x1800166c7  mov     rsi, [rsp+48h+arg_8]
0x1800166cc  add     rsp, 40h
0x1800166d0  pop     rdi
0x1800166d1  retn
```
