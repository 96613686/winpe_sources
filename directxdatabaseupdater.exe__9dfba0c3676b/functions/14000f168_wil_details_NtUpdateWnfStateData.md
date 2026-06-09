# wil_details_NtUpdateWnfStateData

- ea: `0x14000f168`
- end: `0x14000f1ee`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140009d04`
- `0x14000ed68`

## callees

- `0x14000ed40`
- `0x14000f168`
- `0x14001a010`

## string_xrefs

- `0x14000f18c`: `NtUpdateWnfStateData`

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
0x14000f168  mov     [rsp+arg_0], rbx
0x14000f16d  mov     [rsp+arg_8], rsi
0x14000f172  push    rdi
0x14000f173  sub     rsp, 40h
0x14000f177  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000f17e  mov     ebx, r8d
0x14000f181  mov     rdi, rdx
0x14000f184  mov     rsi, rcx
0x14000f187  test    r10, r10
0x14000f18a  jnz     short loc_14000F1AE
0x14000f18c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000f193  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000f198  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000f19f  mov     r10, rax
0x14000f1a2  test    rax, rax
0x14000f1a5  jnz     short loc_14000F1AE
0x14000f1a7  mov     eax, 0C0000139h
0x14000f1ac  jmp     short loc_14000F1DE
0x14000f1ae  mov     eax, [rsp+48h+arg_30]
0x14000f1b5  xor     r9d, r9d
0x14000f1b8  mov     [rsp+48h+var_18], eax
0x14000f1bc  mov     r8d, ebx
0x14000f1bf  mov     eax, [rsp+48h+arg_28]
0x14000f1c3  mov     rdx, rdi
0x14000f1c6  mov     [rsp+48h+var_20], eax
0x14000f1ca  mov     rcx, rsi
0x14000f1cd  mov     rax, r10
0x14000f1d0  mov     [rsp+48h+var_28], 0
0x14000f1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1de  mov     rbx, [rsp+48h+arg_0]
0x14000f1e3  mov     rsi, [rsp+48h+arg_8]
0x14000f1e8  add     rsp, 40h
0x14000f1ec  pop     rdi
0x14000f1ed  retn
```
