# wil_details_NtUpdateWnfStateData

- ea: `0x18001e264`
- end: `0x18001e2ea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b4a0`
- `0x18001d978`

## callees

- `0x18001d950`
- `0x18001e264`
- `0x180043010`

## string_xrefs

- `0x18001e288`: `NtUpdateWnfStateData`

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
0x18001e264  mov     [rsp+arg_0], rbx
0x18001e269  mov     [rsp+arg_8], rsi
0x18001e26e  push    rdi
0x18001e26f  sub     rsp, 40h
0x18001e273  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001e27a  mov     ebx, r8d
0x18001e27d  mov     rdi, rdx
0x18001e280  mov     rsi, rcx
0x18001e283  test    r10, r10
0x18001e286  jnz     short loc_18001E2AA
0x18001e288  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001e28f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001e294  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001e29b  mov     r10, rax
0x18001e29e  test    rax, rax
0x18001e2a1  jnz     short loc_18001E2AA
0x18001e2a3  mov     eax, 0C0000139h
0x18001e2a8  jmp     short loc_18001E2DA
0x18001e2aa  mov     eax, [rsp+48h+arg_30]
0x18001e2b1  xor     r9d, r9d
0x18001e2b4  mov     [rsp+48h+var_18], eax
0x18001e2b8  mov     r8d, ebx
0x18001e2bb  mov     eax, [rsp+48h+arg_28]
0x18001e2bf  mov     rdx, rdi
0x18001e2c2  mov     [rsp+48h+var_20], eax
0x18001e2c6  mov     rcx, rsi
0x18001e2c9  mov     rax, r10
0x18001e2cc  mov     [rsp+48h+var_28], 0
0x18001e2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2da  mov     rbx, [rsp+48h+arg_0]
0x18001e2df  mov     rsi, [rsp+48h+arg_8]
0x18001e2e4  add     rsp, 40h
0x18001e2e8  pop     rdi
0x18001e2e9  retn
```
