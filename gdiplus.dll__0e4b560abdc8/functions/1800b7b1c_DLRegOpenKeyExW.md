# DLRegOpenKeyExW

- ea: `0x1800b7b1c`
- end: `0x1800b7baf`
- name: `DLRegOpenKeyExW`
- size: `147`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e0c6c`
- `0x180147b4c`
- `0x18014f654`
- `0x18014f7e0`
- `0x180150974`

## callees

- `0x1800b7b1c`
- `0x1800b7bb8`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7b57`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7b72`

## string_xrefs

- `0x1800b7b50`: `RegOpenKeyExW`

## pseudocode

```c
DWORD __fastcall DLRegOpenKeyExW(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 (__fastcall *v5)(__int64, __int64, _QWORD, _QWORD, __int64); // r10
  DWORD result; // eax

  v5 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64))qword_1801B3D60;
  if ( qword_1801B3D60 )
    return v5(a1, a2, 0, a4, a5);
  result = DLpLoadRegistryDll();
  if ( result )
    return result;
  qword_1801B3D60 = (__int64)GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  v5 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, __int64))qword_1801B3D60;
  if ( qword_1801B3D60 )
    return v5(a1, a2, 0, a4, a5);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800b7b1c  mov     [rsp+arg_0], rbx
0x1800b7b21  mov     [rsp+arg_8], rsi
0x1800b7b26  push    rdi
0x1800b7b27  sub     rsp, 30h
0x1800b7b2b  mov     r10, cs:qword_1801B3D60
0x1800b7b32  mov     ebx, r9d
0x1800b7b35  mov     rdi, rdx
0x1800b7b38  mov     rsi, rcx
0x1800b7b3b  test    r10, r10
0x1800b7b3e  jnz     short loc_1800B7B80
0x1800b7b40  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x1800b7b45  test    eax, eax
0x1800b7b47  jnz     short loc_1800B7B9E
0x1800b7b49  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800b7b50  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800b7b57  call    cs:__imp_GetProcAddress
0x1800b7b5e  nop     dword ptr [rax+rax+00h]
0x1800b7b63  mov     cs:qword_1801B3D60, rax
0x1800b7b6a  mov     r10, rax
0x1800b7b6d  test    rax, rax
0x1800b7b70  jnz     short loc_1800B7B80
0x1800b7b72  call    cs:__imp_GetLastError
0x1800b7b79  nop     dword ptr [rax+rax+00h]
0x1800b7b7e  jmp     short loc_1800B7B9E
0x1800b7b80  mov     rax, [rsp+38h+arg_20]
0x1800b7b85  mov     r9d, ebx
0x1800b7b88  mov     [rsp+38h+var_18], rax
0x1800b7b8d  xor     r8d, r8d
0x1800b7b90  mov     rax, r10
0x1800b7b93  mov     rdx, rdi
0x1800b7b96  mov     rcx, rsi
0x1800b7b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7b9e  mov     rbx, [rsp+38h+arg_0]
0x1800b7ba3  mov     rsi, [rsp+38h+arg_8]
0x1800b7ba8  add     rsp, 30h
0x1800b7bac  pop     rdi
0x1800b7bad  retn
```
