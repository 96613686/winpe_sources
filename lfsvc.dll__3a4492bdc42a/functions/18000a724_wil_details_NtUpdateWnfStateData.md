# wil_details_NtUpdateWnfStateData

- ea: `0x18000a724`
- end: `0x18000a7aa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800086dc`
- `0x18000a3a8`

## callees

- `0x18000a380`
- `0x18000a724`
- `0x18000c010`

## string_xrefs

- `0x18000a748`: `NtUpdateWnfStateData`

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
0x18000a724  mov     [rsp+arg_0], rbx
0x18000a729  mov     [rsp+arg_8], rsi
0x18000a72e  push    rdi
0x18000a72f  sub     rsp, 40h
0x18000a733  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a73a  mov     ebx, r8d
0x18000a73d  mov     rdi, rdx
0x18000a740  mov     rsi, rcx
0x18000a743  test    r10, r10
0x18000a746  jnz     short loc_18000A76A
0x18000a748  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a74f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a754  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a75b  mov     r10, rax
0x18000a75e  test    rax, rax
0x18000a761  jnz     short loc_18000A76A
0x18000a763  mov     eax, 0C0000139h
0x18000a768  jmp     short loc_18000A79A
0x18000a76a  mov     eax, [rsp+48h+arg_30]
0x18000a771  xor     r9d, r9d
0x18000a774  mov     [rsp+48h+var_18], eax
0x18000a778  mov     r8d, ebx
0x18000a77b  mov     eax, [rsp+48h+arg_28]
0x18000a77f  mov     rdx, rdi
0x18000a782  mov     [rsp+48h+var_20], eax
0x18000a786  mov     rcx, rsi
0x18000a789  mov     rax, r10
0x18000a78c  mov     [rsp+48h+var_28], 0
0x18000a795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a79a  mov     rbx, [rsp+48h+arg_0]
0x18000a79f  mov     rsi, [rsp+48h+arg_8]
0x18000a7a4  add     rsp, 40h
0x18000a7a8  pop     rdi
0x18000a7a9  retn
```
