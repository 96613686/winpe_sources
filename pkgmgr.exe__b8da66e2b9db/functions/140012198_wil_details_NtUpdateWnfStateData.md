# wil_details_NtUpdateWnfStateData

- ea: `0x140012198`
- end: `0x14001221e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000fca4`
- `0x14001096c`

## callees

- `0x1400066b0`
- `0x140012198`
- `0x14002a010`

## string_xrefs

- `0x1400121bc`: `NtUpdateWnfStateData`

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
0x140012198  mov     [rsp+arg_0], rbx
0x14001219d  mov     [rsp+arg_8], rsi
0x1400121a2  push    rdi
0x1400121a3  sub     rsp, 40h
0x1400121a7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400121ae  mov     ebx, r8d
0x1400121b1  mov     rdi, rdx
0x1400121b4  mov     rsi, rcx
0x1400121b7  test    r10, r10
0x1400121ba  jnz     short loc_1400121DE
0x1400121bc  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1400121c3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400121c8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1400121cf  mov     r10, rax
0x1400121d2  test    rax, rax
0x1400121d5  jnz     short loc_1400121DE
0x1400121d7  mov     eax, 0C0000139h
0x1400121dc  jmp     short loc_14001220E
0x1400121de  mov     eax, [rsp+48h+arg_30]
0x1400121e5  xor     r9d, r9d
0x1400121e8  mov     [rsp+48h+var_18], eax
0x1400121ec  mov     r8d, ebx
0x1400121ef  mov     eax, [rsp+48h+arg_28]
0x1400121f3  mov     rdx, rdi
0x1400121f6  mov     [rsp+48h+var_20], eax
0x1400121fa  mov     rcx, rsi
0x1400121fd  mov     rax, r10
0x140012200  mov     [rsp+48h+var_28], 0
0x140012209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001220e  mov     rbx, [rsp+48h+arg_0]
0x140012213  mov     rsi, [rsp+48h+arg_8]
0x140012218  add     rsp, 40h
0x14001221c  pop     rdi
0x14001221d  retn
```
