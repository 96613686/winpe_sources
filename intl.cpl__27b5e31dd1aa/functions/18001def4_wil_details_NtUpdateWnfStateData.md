# wil_details_NtUpdateWnfStateData

- ea: `0x18001def4`
- end: `0x18001df7a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001c6f8`
- `0x18001d6d0`

## callees

- `0x1800072f0`
- `0x18001def4`
- `0x18002b010`

## string_xrefs

- `0x18001df18`: `NtUpdateWnfStateData`

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
0x18001def4  mov     [rsp+arg_0], rbx
0x18001def9  mov     [rsp+arg_8], rsi
0x18001defe  push    rdi
0x18001deff  sub     rsp, 40h
0x18001df03  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001df0a  mov     ebx, r8d
0x18001df0d  mov     rdi, rdx
0x18001df10  mov     rsi, rcx
0x18001df13  test    r10, r10
0x18001df16  jnz     short loc_18001DF3A
0x18001df18  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001df1f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001df24  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001df2b  mov     r10, rax
0x18001df2e  test    rax, rax
0x18001df31  jnz     short loc_18001DF3A
0x18001df33  mov     eax, 0C0000139h
0x18001df38  jmp     short loc_18001DF6A
0x18001df3a  mov     eax, [rsp+48h+arg_30]
0x18001df41  xor     r9d, r9d
0x18001df44  mov     [rsp+48h+var_18], eax
0x18001df48  mov     r8d, ebx
0x18001df4b  mov     eax, [rsp+48h+arg_28]
0x18001df4f  mov     rdx, rdi
0x18001df52  mov     [rsp+48h+var_20], eax
0x18001df56  mov     rcx, rsi
0x18001df59  mov     rax, r10
0x18001df5c  mov     [rsp+48h+var_28], 0
0x18001df65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df6a  mov     rbx, [rsp+48h+arg_0]
0x18001df6f  mov     rsi, [rsp+48h+arg_8]
0x18001df74  add     rsp, 40h
0x18001df78  pop     rdi
0x18001df79  retn
```
