# PortGetConfigKey

- ea: `0x180016ef0`
- end: `0x180016fd8`
- name: `PortGetConfigKey`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016d4c`

## callees

- `0x180016ef0`
- `0x180017048`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016fc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016fc5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016fa1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016fa1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016f6e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016f6e`

## string_xrefs

- `0x180016f0c`: `PortGetConfigKey: Entered: %ls`

## pseudocode

```c
__int64 __fastcall PortGetConfigKey(const wchar_t *a1, HKEY a2, __int64 a3)
{
  _DWORD *v5; // r8
  HKEY v6; // rcx
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  PortTrace("PortGetConfigKey: Entered: %ls", a1);
  if ( *v5 == 1 )
  {
    if ( RegQueryValueExW(a2, L"WanEndpoints", 0, 0, 0, 0) )
      goto LABEL_8;
    v6 = a2;
    goto LABEL_7;
  }
  if ( *v5 != 2 )
    return 0;
  dwDisposition = 0;
  if ( !RegCreateKeyExW(a2, L"Clients\\Ras", 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition) )
  {
    v6 = hKey;
LABEL_7:
    (*(void (__fastcall **)(HKEY, _QWORD))(a3 + 8))(v6, *(_QWORD *)(a3 + 16));
  }
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180016ef0  mov     [rsp+arg_0], rbx
0x180016ef5  push    rdi
0x180016ef6  sub     rsp, 50h
0x180016efa  mov     rdi, rdx
0x180016efd  mov     [rsp+58h+hKey], 0
0x180016f06  mov     rdx, rcx
0x180016f09  mov     rbx, r8
0x180016f0c  lea     rcx, aPortgetconfigk; "PortGetConfigKey: Entered: %ls"
0x180016f13  call    PortTrace
0x180016f18  mov     eax, [r8]
0x180016f1b  sub     eax, 1
0x180016f1e  jz      short loc_180016F7F
0x180016f20  cmp     eax, 1
0x180016f23  jnz     loc_180016FCB
0x180016f29  lea     rax, [rsp+58h+dwDisposition]
0x180016f2e  mov     [rsp+58h+dwDisposition], 0
0x180016f36  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180016f3b  lea     rdx, SubKey; "Clients\\Ras"
0x180016f42  lea     rax, [rsp+58h+hKey]
0x180016f47  xor     r9d, r9d; lpClass
0x180016f4a  mov     [rsp+58h+phkResult], rax; phkResult
0x180016f4f  xor     r8d, r8d; Reserved
0x180016f52  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180016f5b  mov     rcx, rdi; hKey
0x180016f5e  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180016f66  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180016f6e  call    cs:__imp_RegCreateKeyExW
0x180016f74  test    eax, eax
0x180016f76  jnz     short loc_180016FBB
0x180016f78  mov     rcx, [rsp+58h+hKey]
0x180016f7d  jmp     short loc_180016FAE
0x180016f7f  mov     qword ptr [rsp+58h+samDesired], 0; lpcbData
0x180016f88  lea     rdx, ValueName; "WanEndpoints"
0x180016f8f  xor     r9d, r9d; lpType
0x180016f92  mov     qword ptr [rsp+58h+dwOptions], 0; lpData
0x180016f9b  xor     r8d, r8d; lpReserved
0x180016f9e  mov     rcx, rdi; hKey
0x180016fa1  call    cs:__imp_RegQueryValueExW
0x180016fa7  test    eax, eax
0x180016fa9  jnz     short loc_180016FBB
0x180016fab  mov     rcx, rdi
0x180016fae  mov     rdx, [rbx+10h]
0x180016fb2  mov     rax, [rbx+8]
0x180016fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fbb  mov     rcx, [rsp+58h+hKey]; hKey
0x180016fc0  test    rcx, rcx
0x180016fc3  jz      short loc_180016FCB
0x180016fc5  call    cs:__imp_RegCloseKey
0x180016fcb  mov     rbx, [rsp+58h+arg_0]
0x180016fd0  xor     eax, eax
0x180016fd2  add     rsp, 50h
0x180016fd6  pop     rdi
0x180016fd7  retn
```
