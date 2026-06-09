# wil_details_NtUpdateWnfStateData

- ea: `0x180017d04`
- end: `0x180017d8a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180014cb8`
- `0x180017508`

## callees

- `0x18000f020`
- `0x180017d04`
- `0x180020010`

## string_xrefs

- `0x180017d28`: `NtUpdateWnfStateData`

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
0x180017d04  mov     [rsp+arg_0], rbx
0x180017d09  mov     [rsp+arg_8], rsi
0x180017d0e  push    rdi
0x180017d0f  sub     rsp, 40h
0x180017d13  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180017d1a  mov     ebx, r8d
0x180017d1d  mov     rdi, rdx
0x180017d20  mov     rsi, rcx
0x180017d23  test    r10, r10
0x180017d26  jnz     short loc_180017D4A
0x180017d28  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180017d2f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180017d34  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180017d3b  mov     r10, rax
0x180017d3e  test    rax, rax
0x180017d41  jnz     short loc_180017D4A
0x180017d43  mov     eax, 0C0000139h
0x180017d48  jmp     short loc_180017D7A
0x180017d4a  mov     eax, [rsp+48h+arg_30]
0x180017d51  xor     r9d, r9d
0x180017d54  mov     [rsp+48h+var_18], eax
0x180017d58  mov     r8d, ebx
0x180017d5b  mov     eax, [rsp+48h+arg_28]
0x180017d5f  mov     rdx, rdi
0x180017d62  mov     [rsp+48h+var_20], eax
0x180017d66  mov     rcx, rsi
0x180017d69  mov     rax, r10
0x180017d6c  mov     [rsp+48h+var_28], 0
0x180017d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d7a  mov     rbx, [rsp+48h+arg_0]
0x180017d7f  mov     rsi, [rsp+48h+arg_8]
0x180017d84  add     rsp, 40h
0x180017d88  pop     rdi
0x180017d89  retn
```
