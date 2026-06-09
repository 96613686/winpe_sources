# wil_details_NtUpdateWnfStateData

- ea: `0x180026fe0`
- end: `0x180027066`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002590c`
- `0x180026d2c`

## callees

- `0x18001d960`
- `0x180026fe0`
- `0x18003b010`

## string_xrefs

- `0x180027004`: `NtUpdateWnfStateData`

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
0x180026fe0  mov     [rsp+arg_0], rbx
0x180026fe5  mov     [rsp+arg_8], rsi
0x180026fea  push    rdi
0x180026feb  sub     rsp, 40h
0x180026fef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180026ff6  mov     ebx, r8d
0x180026ff9  mov     rdi, rdx
0x180026ffc  mov     rsi, rcx
0x180026fff  test    r10, r10
0x180027002  jnz     short loc_180027026
0x180027004  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002700b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180027010  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180027017  mov     r10, rax
0x18002701a  test    rax, rax
0x18002701d  jnz     short loc_180027026
0x18002701f  mov     eax, 0C0000139h
0x180027024  jmp     short loc_180027056
0x180027026  mov     eax, [rsp+48h+arg_30]
0x18002702d  xor     r9d, r9d
0x180027030  mov     [rsp+48h+var_18], eax
0x180027034  mov     r8d, ebx
0x180027037  mov     eax, [rsp+48h+arg_28]
0x18002703b  mov     rdx, rdi
0x18002703e  mov     [rsp+48h+var_20], eax
0x180027042  mov     rcx, rsi
0x180027045  mov     rax, r10
0x180027048  mov     [rsp+48h+var_28], 0
0x180027051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027056  mov     rbx, [rsp+48h+arg_0]
0x18002705b  mov     rsi, [rsp+48h+arg_8]
0x180027060  add     rsp, 40h
0x180027064  pop     rdi
0x180027065  retn
```
