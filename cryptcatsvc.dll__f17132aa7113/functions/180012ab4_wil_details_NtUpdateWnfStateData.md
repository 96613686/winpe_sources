# wil_details_NtUpdateWnfStateData

- ea: `0x180012ab4`
- end: `0x180012b3a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180010508`
- `0x180012438`

## callees

- `0x180012410`
- `0x180012ab4`
- `0x180022010`

## string_xrefs

- `0x180012ad8`: `NtUpdateWnfStateData`

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
0x180012ab4  mov     [rsp+arg_0], rbx
0x180012ab9  mov     [rsp+arg_8], rsi
0x180012abe  push    rdi
0x180012abf  sub     rsp, 40h
0x180012ac3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180012aca  mov     ebx, r8d
0x180012acd  mov     rdi, rdx
0x180012ad0  mov     rsi, rcx
0x180012ad3  test    r10, r10
0x180012ad6  jnz     short loc_180012AFA
0x180012ad8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180012adf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012ae4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180012aeb  mov     r10, rax
0x180012aee  test    rax, rax
0x180012af1  jnz     short loc_180012AFA
0x180012af3  mov     eax, 0C0000139h
0x180012af8  jmp     short loc_180012B2A
0x180012afa  mov     eax, [rsp+48h+arg_30]
0x180012b01  xor     r9d, r9d
0x180012b04  mov     [rsp+48h+var_18], eax
0x180012b08  mov     r8d, ebx
0x180012b0b  mov     eax, [rsp+48h+arg_28]
0x180012b0f  mov     rdx, rdi
0x180012b12  mov     [rsp+48h+var_20], eax
0x180012b16  mov     rcx, rsi
0x180012b19  mov     rax, r10
0x180012b1c  mov     [rsp+48h+var_28], 0
0x180012b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b2a  mov     rbx, [rsp+48h+arg_0]
0x180012b2f  mov     rsi, [rsp+48h+arg_8]
0x180012b34  add     rsp, 40h
0x180012b38  pop     rdi
0x180012b39  retn
```
