# DLRegCreateKeyExW

- ea: `0x18016bfe0`
- end: `0x18016c08c`
- name: `DLRegCreateKeyExW`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18014ea64`

## callees

- `0x1800b7bb8`
- `0x18016bfe0`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c013`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c02e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c02e`

## string_xrefs

- `0x18016c00c`: `RegCreateKeyExW`

## pseudocode

```c
DWORD __fastcall DLRegCreateKeyExW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 (__fastcall *v9)(__int64, __int64, _QWORD, _QWORD, _DWORD, int, _QWORD, __int64, __int64); // r10
  DWORD result; // eax

  v9 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _DWORD, int, _QWORD, __int64, __int64))qword_1801B3DA8;
  if ( qword_1801B3DA8 )
    return v9(a1, a2, 0, 0, 0, a6, 0, a8, a9);
  result = DLpLoadRegistryDll();
  if ( result )
    return result;
  qword_1801B3DA8 = (__int64)GetProcAddress(g_hInstRegistryDLL, "RegCreateKeyExW");
  v9 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _DWORD, int, _QWORD, __int64, __int64))qword_1801B3DA8;
  if ( qword_1801B3DA8 )
    return v9(a1, a2, 0, 0, 0, a6, 0, a8, a9);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18016bfe0  mov     [rsp+arg_0], rbx
0x18016bfe5  push    rdi
0x18016bfe6  sub     rsp, 50h
0x18016bfea  mov     r10, cs:qword_1801B3DA8
0x18016bff1  mov     rbx, rdx
0x18016bff4  mov     rdi, rcx
0x18016bff7  test    r10, r10
0x18016bffa  jnz     short loc_18016C03C
0x18016bffc  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18016c001  test    eax, eax
0x18016c003  jnz     short loc_18016C080
0x18016c005  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18016c00c  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x18016c013  call    cs:__imp_GetProcAddress
0x18016c01a  nop     dword ptr [rax+rax+00h]
0x18016c01f  mov     cs:qword_1801B3DA8, rax
0x18016c026  mov     r10, rax
0x18016c029  test    rax, rax
0x18016c02c  jnz     short loc_18016C03C
0x18016c02e  call    cs:__imp_GetLastError
0x18016c035  nop     dword ptr [rax+rax+00h]
0x18016c03a  jmp     short loc_18016C080
0x18016c03c  mov     rax, [rsp+58h+arg_40]
0x18016c044  xor     r9d, r9d
0x18016c047  mov     [rsp+58h+var_18], rax
0x18016c04c  xor     r8d, r8d
0x18016c04f  mov     rax, [rsp+58h+arg_38]
0x18016c057  mov     rdx, rbx
0x18016c05a  mov     [rsp+58h+var_20], rax
0x18016c05f  mov     rcx, rdi
0x18016c062  and     [rsp+58h+var_28], 0
0x18016c068  mov     eax, [rsp+58h+arg_28]
0x18016c06f  mov     [rsp+58h+var_30], eax
0x18016c073  mov     rax, r10
0x18016c076  and     [rsp+58h+var_38], 0
0x18016c07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c080  mov     rbx, [rsp+58h+arg_0]
0x18016c085  add     rsp, 50h
0x18016c089  pop     rdi
0x18016c08a  retn
```
