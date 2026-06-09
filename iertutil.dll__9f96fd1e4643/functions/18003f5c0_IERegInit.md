# IERegInit

- ea: `0x18003f5c0`
- end: `0x18003f6f9`
- name: `IERegInit`
- size: `313`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ee9c`
- `0x18003f340`
- `0x180067958`
- `0x180067a90`
- `0x180067b70`
- `0x180067e60`
- `0x1800686a0`

## callees

- `0x18003f5c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f60a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f63f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f674`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f6a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f6dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f60a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f63f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f674`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f6a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f6dd`

## pseudocode

```c
LSTATUS IERegInit()
{
  LSTATUS result; // eax
  LSTATUS v1; // eax
  HKEY v2; // rcx
  LSTATUS v3; // eax
  HKEY v4; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  LSTATUS v7; // eax
  HKEY v8; // r8
  HKEY v9; // rcx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  phkResult = 0;
  result = _InterlockedCompareExchange(&dword_18029A1B8, 1, 0);
  if ( !result )
  {
    v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies", 0, 0x20019u, &phkResult);
    v2 = 0;
    if ( !v1 )
      v2 = phkResult;
    qword_18029A190 = (__int64)v2;
    v3 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Policies", 0, 0x20019u, &phkResult);
    v4 = 0;
    if ( !v3 )
      v4 = phkResult;
    qword_18029A198 = (__int64)v4;
    v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software", 0, 0x20019u, &phkResult);
    v6 = 0;
    if ( !v5 )
      v6 = phkResult;
    qword_18029A1A0 = (__int64)v6;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &phkResult);
    v8 = 0;
    if ( !v7 )
      v8 = phkResult;
    qword_18029A1A8 = (__int64)v8;
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20219u, &phkResult);
    v9 = 0;
    if ( !result )
      v9 = phkResult;
    qword_18029A1B0 = (__int64)v9;
  }
  return result;
}

```

## disassembly

```asm
0x18003f5c0  push    rbp
0x18003f5c2  sub     rsp, 30h
0x18003f5c6  mov     [rsp+38h+arg_0], 0
0x18003f5cf  mov     ecx, 1
0x18003f5d4  xor     eax, eax
0x18003f5d6  lock cmpxchg cs:dword_18029A1B8, ecx
0x18003f5de  jz      short loc_18003F5E6
0x18003f5e0  add     rsp, 30h
0x18003f5e4  pop     rbp
0x18003f5e5  retn
0x18003f5e6  lea     rax, [rsp+38h+arg_0]
0x18003f5eb  mov     rbp, 0FFFFFFFF80000002h
0x18003f5f2  mov     rcx, rbp; hKey
0x18003f5f5  mov     [rsp+38h+phkResult], rax; phkResult
0x18003f5fa  mov     r9d, 20019h; samDesired
0x18003f600  lea     rdx, aSoftwarePolici_19; "Software\\Policies"
0x18003f607  xor     r8d, r8d; ulOptions
0x18003f60a  call    cs:__imp_RegOpenKeyExW
0x18003f610  xor     ecx, ecx
0x18003f612  lea     rdx, aSoftwarePolici_19; "Software\\Policies"
0x18003f619  test    eax, eax
0x18003f61b  mov     r9d, 20019h; samDesired
0x18003f621  lea     rax, [rsp+38h+arg_0]
0x18003f626  cmovz   rcx, [rsp+38h+arg_0]
0x18003f62c  xor     r8d, r8d; ulOptions
0x18003f62f  mov     cs:qword_18029A190, rcx
0x18003f636  lea     rcx, [rbp-1]; hKey
0x18003f63a  mov     [rsp+38h+phkResult], rax; phkResult
0x18003f63f  call    cs:__imp_RegOpenKeyExW
0x18003f645  xor     ecx, ecx
0x18003f647  lea     rdx, aSoftware_1; "Software"
0x18003f64e  test    eax, eax
0x18003f650  mov     r9d, 20019h; samDesired
0x18003f656  lea     rax, [rsp+38h+arg_0]
0x18003f65b  cmovz   rcx, [rsp+38h+arg_0]
0x18003f661  xor     r8d, r8d; ulOptions
0x18003f664  mov     cs:qword_18029A198, rcx
0x18003f66b  lea     rcx, [rbp-1]; hKey
0x18003f66f  mov     [rsp+38h+phkResult], rax; phkResult
0x18003f674  call    cs:__imp_RegOpenKeyExW
0x18003f67a  xor     ecx, ecx
0x18003f67c  lea     rdx, aSoftware_1; "Software"
0x18003f683  test    eax, eax
0x18003f685  mov     r9d, 20019h; samDesired
0x18003f68b  lea     rax, [rsp+38h+arg_0]
0x18003f690  cmovz   rcx, [rsp+38h+arg_0]
0x18003f696  xor     r8d, r8d; ulOptions
0x18003f699  mov     cs:qword_18029A1A0, rcx
0x18003f6a0  mov     rcx, rbp; hKey
0x18003f6a3  mov     [rsp+38h+phkResult], rax; phkResult
0x18003f6a8  call    cs:__imp_RegOpenKeyExW
0x18003f6ae  xor     r8d, r8d
0x18003f6b1  lea     rdx, aSoftware_1; "Software"
0x18003f6b8  test    eax, eax
0x18003f6ba  mov     r9d, 20219h; samDesired
0x18003f6c0  lea     rax, [rsp+38h+arg_0]
0x18003f6c5  mov     rcx, rbp; hKey
0x18003f6c8  cmovz   r8, [rsp+38h+arg_0]
0x18003f6ce  mov     cs:qword_18029A1A8, r8
0x18003f6d5  xor     r8d, r8d; ulOptions
0x18003f6d8  mov     [rsp+38h+phkResult], rax; phkResult
0x18003f6dd  call    cs:__imp_RegOpenKeyExW
0x18003f6e3  xor     ecx, ecx
0x18003f6e5  test    eax, eax
0x18003f6e7  cmovz   rcx, [rsp+38h+arg_0]
0x18003f6ed  mov     cs:qword_18029A1B0, rcx
0x18003f6f4  jmp     loc_18003F5E0
```
