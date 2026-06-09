# wil_details_NtUpdateWnfStateData

- ea: `0x180017d80`
- end: `0x180017e06`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180014fe0`
- `0x1800177a4`

## callees

- `0x18001777c`
- `0x180017d80`
- `0x180023010`

## string_xrefs

- `0x180017da4`: `NtUpdateWnfStateData`

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
0x180017d80  mov     [rsp+arg_0], rbx
0x180017d85  mov     [rsp+arg_8], rsi
0x180017d8a  push    rdi
0x180017d8b  sub     rsp, 40h
0x180017d8f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180017d96  mov     ebx, r8d
0x180017d99  mov     rdi, rdx
0x180017d9c  mov     rsi, rcx
0x180017d9f  test    r10, r10
0x180017da2  jnz     short loc_180017DC6
0x180017da4  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180017dab  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180017db0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180017db7  mov     r10, rax
0x180017dba  test    rax, rax
0x180017dbd  jnz     short loc_180017DC6
0x180017dbf  mov     eax, 0C0000139h
0x180017dc4  jmp     short loc_180017DF6
0x180017dc6  mov     eax, [rsp+48h+arg_30]
0x180017dcd  xor     r9d, r9d
0x180017dd0  mov     [rsp+48h+var_18], eax
0x180017dd4  mov     r8d, ebx
0x180017dd7  mov     eax, [rsp+48h+arg_28]
0x180017ddb  mov     rdx, rdi
0x180017dde  mov     [rsp+48h+var_20], eax
0x180017de2  mov     rcx, rsi
0x180017de5  mov     rax, r10
0x180017de8  mov     [rsp+48h+var_28], 0
0x180017df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017df6  mov     rbx, [rsp+48h+arg_0]
0x180017dfb  mov     rsi, [rsp+48h+arg_8]
0x180017e00  add     rsp, 40h
0x180017e04  pop     rdi
0x180017e05  retn
```
