# wil_details_NtUpdateWnfStateData

- ea: `0x180009934`
- end: `0x1800099ba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800067c8`
- `0x180009168`

## callees

- `0x180009140`
- `0x180009934`
- `0x180030010`

## string_xrefs

- `0x180009958`: `NtUpdateWnfStateData`

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
0x180009934  mov     [rsp+arg_0], rbx
0x180009939  mov     [rsp+arg_8], rsi
0x18000993e  push    rdi
0x18000993f  sub     rsp, 40h
0x180009943  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000994a  mov     ebx, r8d
0x18000994d  mov     rdi, rdx
0x180009950  mov     rsi, rcx
0x180009953  test    r10, r10
0x180009956  jnz     short loc_18000997A
0x180009958  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000995f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180009964  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000996b  mov     r10, rax
0x18000996e  test    rax, rax
0x180009971  jnz     short loc_18000997A
0x180009973  mov     eax, 0C0000139h
0x180009978  jmp     short loc_1800099AA
0x18000997a  mov     eax, [rsp+48h+arg_30]
0x180009981  xor     r9d, r9d
0x180009984  mov     [rsp+48h+var_18], eax
0x180009988  mov     r8d, ebx
0x18000998b  mov     eax, [rsp+48h+arg_28]
0x18000998f  mov     rdx, rdi
0x180009992  mov     [rsp+48h+var_20], eax
0x180009996  mov     rcx, rsi
0x180009999  mov     rax, r10
0x18000999c  mov     [rsp+48h+var_28], 0
0x1800099a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099aa  mov     rbx, [rsp+48h+arg_0]
0x1800099af  mov     rsi, [rsp+48h+arg_8]
0x1800099b4  add     rsp, 40h
0x1800099b8  pop     rdi
0x1800099b9  retn
```
