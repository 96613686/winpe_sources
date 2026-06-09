# wil_details_NtUpdateWnfStateData

- ea: `0x18000a4c0`
- end: `0x18000a546`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800083d8`
- `0x18000a168`

## callees

- `0x18000a140`
- `0x18000a4c0`
- `0x18000c010`

## string_xrefs

- `0x18000a4e4`: `NtUpdateWnfStateData`

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
0x18000a4c0  mov     [rsp+arg_0], rbx
0x18000a4c5  mov     [rsp+arg_8], rsi
0x18000a4ca  push    rdi
0x18000a4cb  sub     rsp, 40h
0x18000a4cf  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a4d6  mov     ebx, r8d
0x18000a4d9  mov     rdi, rdx
0x18000a4dc  mov     rsi, rcx
0x18000a4df  test    r10, r10
0x18000a4e2  jnz     short loc_18000A506
0x18000a4e4  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a4eb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a4f0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a4f7  mov     r10, rax
0x18000a4fa  test    rax, rax
0x18000a4fd  jnz     short loc_18000A506
0x18000a4ff  mov     eax, 0C0000139h
0x18000a504  jmp     short loc_18000A536
0x18000a506  mov     eax, [rsp+48h+arg_30]
0x18000a50d  xor     r9d, r9d
0x18000a510  mov     [rsp+48h+var_18], eax
0x18000a514  mov     r8d, ebx
0x18000a517  mov     eax, [rsp+48h+arg_28]
0x18000a51b  mov     rdx, rdi
0x18000a51e  mov     [rsp+48h+var_20], eax
0x18000a522  mov     rcx, rsi
0x18000a525  mov     rax, r10
0x18000a528  mov     [rsp+48h+var_28], 0
0x18000a531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a536  mov     rbx, [rsp+48h+arg_0]
0x18000a53b  mov     rsi, [rsp+48h+arg_8]
0x18000a540  add     rsp, 40h
0x18000a544  pop     rdi
0x18000a545  retn
```
