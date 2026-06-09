# wil_details_NtUpdateWnfStateData

- ea: `0x18001e29c`
- end: `0x18001e323`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b344`
- `0x18001dea4`

## callees

- `0x18001de78`
- `0x18001e29c`
- `0x180030010`

## string_xrefs

- `0x18001e2c0`: `NtUpdateWnfStateData`

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
0x18001e29c  mov     [rsp+arg_0], rbx
0x18001e2a1  mov     [rsp+arg_8], rsi
0x18001e2a6  push    rdi
0x18001e2a7  sub     rsp, 40h
0x18001e2ab  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001e2b2  mov     ebx, r8d
0x18001e2b5  mov     rdi, rdx
0x18001e2b8  mov     rsi, rcx
0x18001e2bb  test    r10, r10
0x18001e2be  jnz     short loc_18001E2E2
0x18001e2c0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001e2c7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001e2cc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001e2d3  mov     r10, rax
0x18001e2d6  test    rax, rax
0x18001e2d9  jnz     short loc_18001E2E2
0x18001e2db  mov     eax, 0C0000139h
0x18001e2e0  jmp     short loc_18001E312
0x18001e2e2  mov     eax, [rsp+48h+arg_30]
0x18001e2e9  xor     r9d, r9d
0x18001e2ec  mov     [rsp+48h+var_18], eax
0x18001e2f0  mov     r8d, ebx
0x18001e2f3  mov     eax, [rsp+48h+arg_28]
0x18001e2f7  mov     rdx, rdi
0x18001e2fa  mov     [rsp+48h+var_20], eax
0x18001e2fe  mov     rcx, rsi
0x18001e301  mov     rax, r10
0x18001e304  mov     [rsp+48h+var_28], 0
0x18001e30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e312  mov     rbx, [rsp+48h+arg_0]
0x18001e317  mov     rsi, [rsp+48h+arg_8]
0x18001e31c  add     rsp, 40h
0x18001e320  pop     rdi
0x18001e321  retn
```
