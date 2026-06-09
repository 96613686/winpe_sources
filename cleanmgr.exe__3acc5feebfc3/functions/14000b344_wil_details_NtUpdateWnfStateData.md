# wil_details_NtUpdateWnfStateData

- ea: `0x14000b344`
- end: `0x14000b3ca`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140008ff8`
- `0x14000a8c8`

## callees

- `0x140006980`
- `0x14000b344`
- `0x140018010`

## string_xrefs

- `0x14000b368`: `NtUpdateWnfStateData`

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
0x14000b344  mov     [rsp+arg_0], rbx
0x14000b349  mov     [rsp+arg_8], rsi
0x14000b34e  push    rdi
0x14000b34f  sub     rsp, 40h
0x14000b353  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000b35a  mov     ebx, r8d
0x14000b35d  mov     rdi, rdx
0x14000b360  mov     rsi, rcx
0x14000b363  test    r10, r10
0x14000b366  jnz     short loc_14000B38A
0x14000b368  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000b36f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000b374  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000b37b  mov     r10, rax
0x14000b37e  test    rax, rax
0x14000b381  jnz     short loc_14000B38A
0x14000b383  mov     eax, 0C0000139h
0x14000b388  jmp     short loc_14000B3BA
0x14000b38a  mov     eax, [rsp+48h+arg_30]
0x14000b391  xor     r9d, r9d
0x14000b394  mov     [rsp+48h+var_18], eax
0x14000b398  mov     r8d, ebx
0x14000b39b  mov     eax, [rsp+48h+arg_28]
0x14000b39f  mov     rdx, rdi
0x14000b3a2  mov     [rsp+48h+var_20], eax
0x14000b3a6  mov     rcx, rsi
0x14000b3a9  mov     rax, r10
0x14000b3ac  mov     [rsp+48h+var_28], 0
0x14000b3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b3ba  mov     rbx, [rsp+48h+arg_0]
0x14000b3bf  mov     rsi, [rsp+48h+arg_8]
0x14000b3c4  add     rsp, 40h
0x14000b3c8  pop     rdi
0x14000b3c9  retn
```
