# wil_details_NtUpdateWnfStateData

- ea: `0x14007bfe0`
- end: `0x14007c066`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14007a20c`
- `0x14007bd08`

## callees

- `0x14007bce0`
- `0x14007bfe0`
- `0x140098010`

## string_xrefs

- `0x14007c004`: `NtUpdateWnfStateData`

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
0x14007bfe0  mov     [rsp+arg_0], rbx
0x14007bfe5  mov     [rsp+arg_8], rsi
0x14007bfea  push    rdi
0x14007bfeb  sub     rsp, 40h
0x14007bfef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14007bff6  mov     ebx, r8d
0x14007bff9  mov     rdi, rdx
0x14007bffc  mov     rsi, rcx
0x14007bfff  test    r10, r10
0x14007c002  jnz     short loc_14007C026
0x14007c004  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14007c00b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14007c010  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14007c017  mov     r10, rax
0x14007c01a  test    rax, rax
0x14007c01d  jnz     short loc_14007C026
0x14007c01f  mov     eax, 0C0000139h
0x14007c024  jmp     short loc_14007C056
0x14007c026  mov     eax, [rsp+48h+arg_30]
0x14007c02d  xor     r9d, r9d
0x14007c030  mov     [rsp+48h+var_18], eax
0x14007c034  mov     r8d, ebx
0x14007c037  mov     eax, [rsp+48h+arg_28]
0x14007c03b  mov     rdx, rdi
0x14007c03e  mov     [rsp+48h+var_20], eax
0x14007c042  mov     rcx, rsi
0x14007c045  mov     rax, r10
0x14007c048  mov     [rsp+48h+var_28], 0
0x14007c051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007c056  mov     rbx, [rsp+48h+arg_0]
0x14007c05b  mov     rsi, [rsp+48h+arg_8]
0x14007c060  add     rsp, 40h
0x14007c064  pop     rdi
0x14007c065  retn
```
