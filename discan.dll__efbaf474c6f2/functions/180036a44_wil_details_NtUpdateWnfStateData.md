# wil_details_NtUpdateWnfStateData

- ea: `0x180036a44`
- end: `0x180036aca`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180034cfc`
- `0x1800366a4`

## callees

- `0x18003667c`
- `0x180036a44`
- `0x180039010`

## string_xrefs

- `0x180036a68`: `NtUpdateWnfStateData`

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
0x180036a44  mov     [rsp+arg_0], rbx
0x180036a49  mov     [rsp+arg_8], rsi
0x180036a4e  push    rdi
0x180036a4f  sub     rsp, 40h
0x180036a53  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180036a5a  mov     ebx, r8d
0x180036a5d  mov     rdi, rdx
0x180036a60  mov     rsi, rcx
0x180036a63  test    r10, r10
0x180036a66  jnz     short loc_180036A8A
0x180036a68  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180036a6f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180036a74  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180036a7b  mov     r10, rax
0x180036a7e  test    rax, rax
0x180036a81  jnz     short loc_180036A8A
0x180036a83  mov     eax, 0C0000139h
0x180036a88  jmp     short loc_180036ABA
0x180036a8a  mov     eax, [rsp+48h+arg_30]
0x180036a91  xor     r9d, r9d
0x180036a94  mov     [rsp+48h+var_18], eax
0x180036a98  mov     r8d, ebx
0x180036a9b  mov     eax, [rsp+48h+arg_28]
0x180036a9f  mov     rdx, rdi
0x180036aa2  mov     [rsp+48h+var_20], eax
0x180036aa6  mov     rcx, rsi
0x180036aa9  mov     rax, r10
0x180036aac  mov     [rsp+48h+var_28], 0
0x180036ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036aba  mov     rbx, [rsp+48h+arg_0]
0x180036abf  mov     rsi, [rsp+48h+arg_8]
0x180036ac4  add     rsp, 40h
0x180036ac8  pop     rdi
0x180036ac9  retn
```
