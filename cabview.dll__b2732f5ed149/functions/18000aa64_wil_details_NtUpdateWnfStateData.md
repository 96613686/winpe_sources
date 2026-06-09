# wil_details_NtUpdateWnfStateData

- ea: `0x18000aa64`
- end: `0x18000aaea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180007fe8`
- `0x18000a140`

## callees

- `0x18000a118`
- `0x18000aa64`
- `0x180013010`

## string_xrefs

- `0x18000aa88`: `NtUpdateWnfStateData`

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
0x18000aa64  mov     [rsp+arg_0], rbx
0x18000aa69  mov     [rsp+arg_8], rsi
0x18000aa6e  push    rdi
0x18000aa6f  sub     rsp, 40h
0x18000aa73  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000aa7a  mov     ebx, r8d
0x18000aa7d  mov     rdi, rdx
0x18000aa80  mov     rsi, rcx
0x18000aa83  test    r10, r10
0x18000aa86  jnz     short loc_18000AAAA
0x18000aa88  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000aa8f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000aa94  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000aa9b  mov     r10, rax
0x18000aa9e  test    rax, rax
0x18000aaa1  jnz     short loc_18000AAAA
0x18000aaa3  mov     eax, 0C0000139h
0x18000aaa8  jmp     short loc_18000AADA
0x18000aaaa  mov     eax, [rsp+48h+arg_30]
0x18000aab1  xor     r9d, r9d
0x18000aab4  mov     [rsp+48h+var_18], eax
0x18000aab8  mov     r8d, ebx
0x18000aabb  mov     eax, [rsp+48h+arg_28]
0x18000aabf  mov     rdx, rdi
0x18000aac2  mov     [rsp+48h+var_20], eax
0x18000aac6  mov     rcx, rsi
0x18000aac9  mov     rax, r10
0x18000aacc  mov     [rsp+48h+var_28], 0
0x18000aad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aada  mov     rbx, [rsp+48h+arg_0]
0x18000aadf  mov     rsi, [rsp+48h+arg_8]
0x18000aae4  add     rsp, 40h
0x18000aae8  pop     rdi
0x18000aae9  retn
```
