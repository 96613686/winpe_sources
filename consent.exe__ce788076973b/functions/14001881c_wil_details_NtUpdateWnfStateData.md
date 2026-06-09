# wil_details_NtUpdateWnfStateData

- ea: `0x14001881c`
- end: `0x1400188a2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140016e24`
- `0x140018030`

## callees

- `0x14000e99c`
- `0x14001881c`
- `0x14001f010`

## string_xrefs

- `0x140018840`: `NtUpdateWnfStateData`

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
0x14001881c  mov     [rsp+arg_0], rbx
0x140018821  mov     [rsp+arg_8], rsi
0x140018826  push    rdi
0x140018827  sub     rsp, 40h
0x14001882b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140018832  mov     ebx, r8d
0x140018835  mov     rdi, rdx
0x140018838  mov     rsi, rcx
0x14001883b  test    r10, r10
0x14001883e  jnz     short loc_140018862
0x140018840  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140018847  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001884c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140018853  mov     r10, rax
0x140018856  test    rax, rax
0x140018859  jnz     short loc_140018862
0x14001885b  mov     eax, 0C0000139h
0x140018860  jmp     short loc_140018892
0x140018862  mov     eax, [rsp+48h+arg_30]
0x140018869  xor     r9d, r9d
0x14001886c  mov     [rsp+48h+var_18], eax
0x140018870  mov     r8d, ebx
0x140018873  mov     eax, [rsp+48h+arg_28]
0x140018877  mov     rdx, rdi
0x14001887a  mov     [rsp+48h+var_20], eax
0x14001887e  mov     rcx, rsi
0x140018881  mov     rax, r10
0x140018884  mov     [rsp+48h+var_28], 0
0x14001888d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018892  mov     rbx, [rsp+48h+arg_0]
0x140018897  mov     rsi, [rsp+48h+arg_8]
0x14001889c  add     rsp, 40h
0x1400188a0  pop     rdi
0x1400188a1  retn
```
