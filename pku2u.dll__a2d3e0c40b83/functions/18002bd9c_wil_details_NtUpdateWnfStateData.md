# wil_details_NtUpdateWnfStateData

- ea: `0x18002bd9c`
- end: `0x18002be22`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180029754`
- `0x18002ae7c`

## callees

- `0x180027240`
- `0x18002bd9c`
- `0x180046010`

## string_xrefs

- `0x18002bdc0`: `NtUpdateWnfStateData`

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
0x18002bd9c  mov     [rsp+arg_0], rbx
0x18002bda1  mov     [rsp+arg_8], rsi
0x18002bda6  push    rdi
0x18002bda7  sub     rsp, 40h
0x18002bdab  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002bdb2  mov     ebx, r8d
0x18002bdb5  mov     rdi, rdx
0x18002bdb8  mov     rsi, rcx
0x18002bdbb  test    r10, r10
0x18002bdbe  jnz     short loc_18002BDE2
0x18002bdc0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002bdc7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002bdcc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002bdd3  mov     r10, rax
0x18002bdd6  test    rax, rax
0x18002bdd9  jnz     short loc_18002BDE2
0x18002bddb  mov     eax, 0C0000139h
0x18002bde0  jmp     short loc_18002BE12
0x18002bde2  mov     eax, [rsp+48h+arg_30]
0x18002bde9  xor     r9d, r9d
0x18002bdec  mov     [rsp+48h+var_18], eax
0x18002bdf0  mov     r8d, ebx
0x18002bdf3  mov     eax, [rsp+48h+arg_28]
0x18002bdf7  mov     rdx, rdi
0x18002bdfa  mov     [rsp+48h+var_20], eax
0x18002bdfe  mov     rcx, rsi
0x18002be01  mov     rax, r10
0x18002be04  mov     [rsp+48h+var_28], 0
0x18002be0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be12  mov     rbx, [rsp+48h+arg_0]
0x18002be17  mov     rsi, [rsp+48h+arg_8]
0x18002be1c  add     rsp, 40h
0x18002be20  pop     rdi
0x18002be21  retn
```
