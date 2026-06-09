# wil_details_NtUpdateWnfStateData

- ea: `0x18001b5c4`
- end: `0x18001b64a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180019b5c`
- `0x18001ada0`

## callees

- `0x18000faa0`
- `0x18001b5c4`
- `0x180022010`

## string_xrefs

- `0x18001b5e8`: `NtUpdateWnfStateData`

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
0x18001b5c4  mov     [rsp+arg_0], rbx
0x18001b5c9  mov     [rsp+arg_8], rsi
0x18001b5ce  push    rdi
0x18001b5cf  sub     rsp, 40h
0x18001b5d3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001b5da  mov     ebx, r8d
0x18001b5dd  mov     rdi, rdx
0x18001b5e0  mov     rsi, rcx
0x18001b5e3  test    r10, r10
0x18001b5e6  jnz     short loc_18001B60A
0x18001b5e8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001b5ef  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b5f4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001b5fb  mov     r10, rax
0x18001b5fe  test    rax, rax
0x18001b601  jnz     short loc_18001B60A
0x18001b603  mov     eax, 0C0000139h
0x18001b608  jmp     short loc_18001B63A
0x18001b60a  mov     eax, [rsp+48h+arg_30]
0x18001b611  xor     r9d, r9d
0x18001b614  mov     [rsp+48h+var_18], eax
0x18001b618  mov     r8d, ebx
0x18001b61b  mov     eax, [rsp+48h+arg_28]
0x18001b61f  mov     rdx, rdi
0x18001b622  mov     [rsp+48h+var_20], eax
0x18001b626  mov     rcx, rsi
0x18001b629  mov     rax, r10
0x18001b62c  mov     [rsp+48h+var_28], 0
0x18001b635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b63a  mov     rbx, [rsp+48h+arg_0]
0x18001b63f  mov     rsi, [rsp+48h+arg_8]
0x18001b644  add     rsp, 40h
0x18001b648  pop     rdi
0x18001b649  retn
```
