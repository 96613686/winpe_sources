# wil_details_NtUpdateWnfStateData

- ea: `0x18002cc7c`
- end: `0x18002cd02`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180028978`
- `0x18002a04c`

## callees

- `0x18002a024`
- `0x18002cc7c`
- `0x18002f010`

## string_xrefs

- `0x18002cca0`: `NtUpdateWnfStateData`

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
0x18002cc7c  mov     [rsp+arg_0], rbx
0x18002cc81  mov     [rsp+arg_8], rsi
0x18002cc86  push    rdi
0x18002cc87  sub     rsp, 40h
0x18002cc8b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002cc92  mov     ebx, r8d
0x18002cc95  mov     rdi, rdx
0x18002cc98  mov     rsi, rcx
0x18002cc9b  test    r10, r10
0x18002cc9e  jnz     short loc_18002CCC2
0x18002cca0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002cca7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002ccac  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002ccb3  mov     r10, rax
0x18002ccb6  test    rax, rax
0x18002ccb9  jnz     short loc_18002CCC2
0x18002ccbb  mov     eax, 0C0000139h
0x18002ccc0  jmp     short loc_18002CCF2
0x18002ccc2  mov     eax, [rsp+48h+arg_30]
0x18002ccc9  xor     r9d, r9d
0x18002cccc  mov     [rsp+48h+var_18], eax
0x18002ccd0  mov     r8d, ebx
0x18002ccd3  mov     eax, [rsp+48h+arg_28]
0x18002ccd7  mov     rdx, rdi
0x18002ccda  mov     [rsp+48h+var_20], eax
0x18002ccde  mov     rcx, rsi
0x18002cce1  mov     rax, r10
0x18002cce4  mov     [rsp+48h+var_28], 0
0x18002cced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccf2  mov     rbx, [rsp+48h+arg_0]
0x18002ccf7  mov     rsi, [rsp+48h+arg_8]
0x18002ccfc  add     rsp, 40h
0x18002cd00  pop     rdi
0x18002cd01  retn
```
