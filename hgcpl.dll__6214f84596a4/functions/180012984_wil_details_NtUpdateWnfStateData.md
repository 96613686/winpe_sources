# wil_details_NtUpdateWnfStateData

- ea: `0x180012984`
- end: `0x180012a0a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180011974`
- `0x1800126d0`

## callees

- `0x180006b70`
- `0x180012984`
- `0x18001a010`

## string_xrefs

- `0x1800129a8`: `NtUpdateWnfStateData`

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
0x180012984  mov     [rsp+arg_0], rbx
0x180012989  mov     [rsp+arg_8], rsi
0x18001298e  push    rdi
0x18001298f  sub     rsp, 40h
0x180012993  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001299a  mov     ebx, r8d
0x18001299d  mov     rdi, rdx
0x1800129a0  mov     rsi, rcx
0x1800129a3  test    r10, r10
0x1800129a6  jnz     short loc_1800129CA
0x1800129a8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800129af  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800129b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800129bb  mov     r10, rax
0x1800129be  test    rax, rax
0x1800129c1  jnz     short loc_1800129CA
0x1800129c3  mov     eax, 0C0000139h
0x1800129c8  jmp     short loc_1800129FA
0x1800129ca  mov     eax, [rsp+48h+arg_30]
0x1800129d1  xor     r9d, r9d
0x1800129d4  mov     [rsp+48h+var_18], eax
0x1800129d8  mov     r8d, ebx
0x1800129db  mov     eax, [rsp+48h+arg_28]
0x1800129df  mov     rdx, rdi
0x1800129e2  mov     [rsp+48h+var_20], eax
0x1800129e6  mov     rcx, rsi
0x1800129e9  mov     rax, r10
0x1800129ec  mov     [rsp+48h+var_28], 0
0x1800129f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129fa  mov     rbx, [rsp+48h+arg_0]
0x1800129ff  mov     rsi, [rsp+48h+arg_8]
0x180012a04  add     rsp, 40h
0x180012a08  pop     rdi
0x180012a09  retn
```
