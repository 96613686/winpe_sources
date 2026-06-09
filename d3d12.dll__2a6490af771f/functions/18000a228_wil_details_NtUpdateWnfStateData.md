# wil_details_NtUpdateWnfStateData

- ea: `0x18000a228`
- end: `0x18000a2ae`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000436c`
- `0x18000e350`

## callees

- `0x18000a228`
- `0x18000a398`
- `0x180015010`

## string_xrefs

- `0x18000a24c`: `NtUpdateWnfStateData`

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
0x18000a228  mov     [rsp+arg_0], rbx
0x18000a22d  mov     [rsp+arg_8], rsi
0x18000a232  push    rdi
0x18000a233  sub     rsp, 40h
0x18000a237  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a23e  mov     ebx, r8d
0x18000a241  mov     rdi, rdx
0x18000a244  mov     rsi, rcx
0x18000a247  test    r10, r10
0x18000a24a  jnz     short loc_18000A26E
0x18000a24c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a253  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a258  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a25f  mov     r10, rax
0x18000a262  test    rax, rax
0x18000a265  jnz     short loc_18000A26E
0x18000a267  mov     eax, 0C0000139h
0x18000a26c  jmp     short loc_18000A29E
0x18000a26e  mov     eax, [rsp+48h+arg_30]
0x18000a275  xor     r9d, r9d
0x18000a278  mov     [rsp+48h+var_18], eax
0x18000a27c  mov     r8d, ebx
0x18000a27f  mov     eax, [rsp+48h+arg_28]
0x18000a283  mov     rdx, rdi
0x18000a286  mov     [rsp+48h+var_20], eax
0x18000a28a  mov     rcx, rsi
0x18000a28d  mov     rax, r10
0x18000a290  mov     [rsp+48h+var_28], 0
0x18000a299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29e  mov     rbx, [rsp+48h+arg_0]
0x18000a2a3  mov     rsi, [rsp+48h+arg_8]
0x18000a2a8  add     rsp, 40h
0x18000a2ac  pop     rdi
0x18000a2ad  retn
```
