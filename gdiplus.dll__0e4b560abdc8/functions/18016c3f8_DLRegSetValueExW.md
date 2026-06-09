# DLRegSetValueExW

- ea: `0x18016c3f8`
- end: `0x18016c493`
- name: `DLRegSetValueExW`
- size: `155`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18014ea64`
- `0x18014f7e0`
- `0x180150b30`

## callees

- `0x1800b7bb8`
- `0x18016c3f8`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c433`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18016c433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18016c44e`

## string_xrefs

- `0x18016c42c`: `RegSetValueExW`

## pseudocode

```c
DWORD __fastcall DLRegSetValueExW(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, int a6)
{
  __int64 (__fastcall *v6)(__int64, __int64, _QWORD, _QWORD, __int64, int); // r10
  DWORD result; // eax

  v6 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64, int))qword_1801B3DA0;
  if ( qword_1801B3DA0 )
    return v6(a1, a2, 0, a4, a5, a6);
  result = DLpLoadRegistryDll();
  if ( result )
    return result;
  qword_1801B3DA0 = (__int64)GetProcAddress(g_hInstRegistryDLL, "RegSetValueExW");
  v6 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64, int))qword_1801B3DA0;
  if ( qword_1801B3DA0 )
    return v6(a1, a2, 0, a4, a5, a6);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18016c3f8  mov     [rsp+arg_0], rbx
0x18016c3fd  mov     [rsp+arg_8], rsi
0x18016c402  push    rdi
0x18016c403  sub     rsp, 40h
0x18016c407  mov     r10, cs:qword_1801B3DA0
0x18016c40e  mov     ebx, r9d
0x18016c411  mov     rdi, rdx
0x18016c414  mov     rsi, rcx
0x18016c417  test    r10, r10
0x18016c41a  jnz     short loc_18016C45C
0x18016c41c  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18016c421  test    eax, eax
0x18016c423  jnz     short loc_18016C482
0x18016c425  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18016c42c  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x18016c433  call    cs:__imp_GetProcAddress
0x18016c43a  nop     dword ptr [rax+rax+00h]
0x18016c43f  mov     cs:qword_1801B3DA0, rax
0x18016c446  mov     r10, rax
0x18016c449  test    rax, rax
0x18016c44c  jnz     short loc_18016C45C
0x18016c44e  call    cs:__imp_GetLastError
0x18016c455  nop     dword ptr [rax+rax+00h]
0x18016c45a  jmp     short loc_18016C482
0x18016c45c  mov     eax, [rsp+48h+arg_28]
0x18016c460  mov     r9d, ebx
0x18016c463  mov     [rsp+48h+var_20], eax
0x18016c467  xor     r8d, r8d
0x18016c46a  mov     rax, [rsp+48h+arg_20]
0x18016c46f  mov     rdx, rdi
0x18016c472  mov     [rsp+48h+var_28], rax
0x18016c477  mov     rcx, rsi
0x18016c47a  mov     rax, r10
0x18016c47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c482  mov     rbx, [rsp+48h+arg_0]
0x18016c487  mov     rsi, [rsp+48h+arg_8]
0x18016c48c  add     rsp, 40h
0x18016c490  pop     rdi
0x18016c491  retn
```
