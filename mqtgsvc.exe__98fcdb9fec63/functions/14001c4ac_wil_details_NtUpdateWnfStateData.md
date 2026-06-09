# wil_details_NtUpdateWnfStateData

- ea: `0x14001c4ac`
- end: `0x14001c532`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140019eb8`
- `0x14001c0b0`

## callees

- `0x14001c088`
- `0x14001c4ac`
- `0x140020010`

## string_xrefs

- `0x14001c4d0`: `NtUpdateWnfStateData`

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
0x14001c4ac  mov     [rsp+arg_0], rbx
0x14001c4b1  mov     [rsp+arg_8], rsi
0x14001c4b6  push    rdi
0x14001c4b7  sub     rsp, 40h
0x14001c4bb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14001c4c2  mov     ebx, r8d
0x14001c4c5  mov     rdi, rdx
0x14001c4c8  mov     rsi, rcx
0x14001c4cb  test    r10, r10
0x14001c4ce  jnz     short loc_14001C4F2
0x14001c4d0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14001c4d7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001c4dc  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14001c4e3  mov     r10, rax
0x14001c4e6  test    rax, rax
0x14001c4e9  jnz     short loc_14001C4F2
0x14001c4eb  mov     eax, 0C0000139h
0x14001c4f0  jmp     short loc_14001C522
0x14001c4f2  mov     eax, [rsp+48h+arg_30]
0x14001c4f9  xor     r9d, r9d
0x14001c4fc  mov     [rsp+48h+var_18], eax
0x14001c500  mov     r8d, ebx
0x14001c503  mov     eax, [rsp+48h+arg_28]
0x14001c507  mov     rdx, rdi
0x14001c50a  mov     [rsp+48h+var_20], eax
0x14001c50e  mov     rcx, rsi
0x14001c511  mov     rax, r10
0x14001c514  mov     [rsp+48h+var_28], 0
0x14001c51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c522  mov     rbx, [rsp+48h+arg_0]
0x14001c527  mov     rsi, [rsp+48h+arg_8]
0x14001c52c  add     rsp, 40h
0x14001c530  pop     rdi
0x14001c531  retn
```
