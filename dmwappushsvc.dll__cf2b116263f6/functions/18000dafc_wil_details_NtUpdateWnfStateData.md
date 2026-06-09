# wil_details_NtUpdateWnfStateData

- ea: `0x18000dafc`
- end: `0x18000db82`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000aaec`
- `0x18000d20c`

## callees

- `0x180006060`
- `0x18000dafc`
- `0x180012010`

## string_xrefs

- `0x18000db20`: `NtUpdateWnfStateData`

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
0x18000dafc  mov     [rsp+arg_0], rbx
0x18000db01  mov     [rsp+arg_8], rsi
0x18000db06  push    rdi
0x18000db07  sub     rsp, 40h
0x18000db0b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000db12  mov     ebx, r8d
0x18000db15  mov     rdi, rdx
0x18000db18  mov     rsi, rcx
0x18000db1b  test    r10, r10
0x18000db1e  jnz     short loc_18000DB42
0x18000db20  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000db27  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000db2c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000db33  mov     r10, rax
0x18000db36  test    rax, rax
0x18000db39  jnz     short loc_18000DB42
0x18000db3b  mov     eax, 0C0000139h
0x18000db40  jmp     short loc_18000DB72
0x18000db42  mov     eax, [rsp+48h+arg_30]
0x18000db49  xor     r9d, r9d
0x18000db4c  mov     [rsp+48h+var_18], eax
0x18000db50  mov     r8d, ebx
0x18000db53  mov     eax, [rsp+48h+arg_28]
0x18000db57  mov     rdx, rdi
0x18000db5a  mov     [rsp+48h+var_20], eax
0x18000db5e  mov     rcx, rsi
0x18000db61  mov     rax, r10
0x18000db64  mov     [rsp+48h+var_28], 0
0x18000db6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db72  mov     rbx, [rsp+48h+arg_0]
0x18000db77  mov     rsi, [rsp+48h+arg_8]
0x18000db7c  add     rsp, 40h
0x18000db80  pop     rdi
0x18000db81  retn
```
