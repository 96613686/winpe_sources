# wil_details_NtUpdateWnfStateData

- ea: `0x1800085ac`
- end: `0x180008632`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180005fc0`
- `0x1800082f8`

## callees

- `0x1800082d0`
- `0x1800085ac`
- `0x18001c010`

## string_xrefs

- `0x1800085d0`: `NtUpdateWnfStateData`

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
0x1800085ac  mov     [rsp+arg_0], rbx
0x1800085b1  mov     [rsp+arg_8], rsi
0x1800085b6  push    rdi
0x1800085b7  sub     rsp, 40h
0x1800085bb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800085c2  mov     ebx, r8d
0x1800085c5  mov     rdi, rdx
0x1800085c8  mov     rsi, rcx
0x1800085cb  test    r10, r10
0x1800085ce  jnz     short loc_1800085F2
0x1800085d0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800085d7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800085dc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800085e3  mov     r10, rax
0x1800085e6  test    rax, rax
0x1800085e9  jnz     short loc_1800085F2
0x1800085eb  mov     eax, 0C0000139h
0x1800085f0  jmp     short loc_180008622
0x1800085f2  mov     eax, [rsp+48h+arg_30]
0x1800085f9  xor     r9d, r9d
0x1800085fc  mov     [rsp+48h+var_18], eax
0x180008600  mov     r8d, ebx
0x180008603  mov     eax, [rsp+48h+arg_28]
0x180008607  mov     rdx, rdi
0x18000860a  mov     [rsp+48h+var_20], eax
0x18000860e  mov     rcx, rsi
0x180008611  mov     rax, r10
0x180008614  mov     [rsp+48h+var_28], 0
0x18000861d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008622  mov     rbx, [rsp+48h+arg_0]
0x180008627  mov     rsi, [rsp+48h+arg_8]
0x18000862c  add     rsp, 40h
0x180008630  pop     rdi
0x180008631  retn
```
