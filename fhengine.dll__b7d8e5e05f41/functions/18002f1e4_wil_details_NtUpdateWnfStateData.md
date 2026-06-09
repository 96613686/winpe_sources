# wil_details_NtUpdateWnfStateData

- ea: `0x18002f1e4`
- end: `0x18002f26a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002c3d4`
- `0x18002e9e0`

## callees

- `0x18002e9b8`
- `0x18002f1e4`
- `0x180034010`

## string_xrefs

- `0x18002f208`: `NtUpdateWnfStateData`

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
0x18002f1e4  mov     [rsp+arg_0], rbx
0x18002f1e9  mov     [rsp+arg_8], rsi
0x18002f1ee  push    rdi
0x18002f1ef  sub     rsp, 40h
0x18002f1f3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002f1fa  mov     ebx, r8d
0x18002f1fd  mov     rdi, rdx
0x18002f200  mov     rsi, rcx
0x18002f203  test    r10, r10
0x18002f206  jnz     short loc_18002F22A
0x18002f208  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002f20f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002f214  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002f21b  mov     r10, rax
0x18002f21e  test    rax, rax
0x18002f221  jnz     short loc_18002F22A
0x18002f223  mov     eax, 0C0000139h
0x18002f228  jmp     short loc_18002F25A
0x18002f22a  mov     eax, [rsp+48h+arg_30]
0x18002f231  xor     r9d, r9d
0x18002f234  mov     [rsp+48h+var_18], eax
0x18002f238  mov     r8d, ebx
0x18002f23b  mov     eax, [rsp+48h+arg_28]
0x18002f23f  mov     rdx, rdi
0x18002f242  mov     [rsp+48h+var_20], eax
0x18002f246  mov     rcx, rsi
0x18002f249  mov     rax, r10
0x18002f24c  mov     [rsp+48h+var_28], 0
0x18002f255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f25a  mov     rbx, [rsp+48h+arg_0]
0x18002f25f  mov     rsi, [rsp+48h+arg_8]
0x18002f264  add     rsp, 40h
0x18002f268  pop     rdi
0x18002f269  retn
```
