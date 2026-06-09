# wil_details_NtUpdateWnfStateData

- ea: `0x18000d1e4`
- end: `0x18000d26a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ac94`
- `0x18000cc78`

## callees

- `0x18000cc50`
- `0x18000d1e4`
- `0x180028010`

## string_xrefs

- `0x18000d208`: `NtUpdateWnfStateData`

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
0x18000d1e4  mov     [rsp+arg_0], rbx
0x18000d1e9  mov     [rsp+arg_8], rsi
0x18000d1ee  push    rdi
0x18000d1ef  sub     rsp, 40h
0x18000d1f3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d1fa  mov     ebx, r8d
0x18000d1fd  mov     rdi, rdx
0x18000d200  mov     rsi, rcx
0x18000d203  test    r10, r10
0x18000d206  jnz     short loc_18000D22A
0x18000d208  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d20f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d214  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d21b  mov     r10, rax
0x18000d21e  test    rax, rax
0x18000d221  jnz     short loc_18000D22A
0x18000d223  mov     eax, 0C0000139h
0x18000d228  jmp     short loc_18000D25A
0x18000d22a  mov     eax, [rsp+48h+arg_30]
0x18000d231  xor     r9d, r9d
0x18000d234  mov     [rsp+48h+var_18], eax
0x18000d238  mov     r8d, ebx
0x18000d23b  mov     eax, [rsp+48h+arg_28]
0x18000d23f  mov     rdx, rdi
0x18000d242  mov     [rsp+48h+var_20], eax
0x18000d246  mov     rcx, rsi
0x18000d249  mov     rax, r10
0x18000d24c  mov     [rsp+48h+var_28], 0
0x18000d255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d25a  mov     rbx, [rsp+48h+arg_0]
0x18000d25f  mov     rsi, [rsp+48h+arg_8]
0x18000d264  add     rsp, 40h
0x18000d268  pop     rdi
0x18000d269  retn
```
