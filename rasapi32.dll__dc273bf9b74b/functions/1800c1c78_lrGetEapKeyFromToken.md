# lrGetEapKeyFromToken

- ea: `0x1800c1c78`
- end: `0x1800c1d46`
- name: `lrGetEapKeyFromToken`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c13d4`

## callees

- `0x18000b0f4`
- `0x18000c980`
- `0x1800c1c78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c1cd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c1cd1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c1d15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c1d15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1d2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c1d2f`

## pseudocode

```c
__int64 __fastcall lrGetEapKeyFromToken(void *a1, HKEY *a2)
{
  unsigned int SidFromToken; // ebx
  HKEY v5; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp+28h] BYREF
  LPCWSTR lpSubKey; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  lpSubKey = 0;
  hKey = 0;
  v5 = 0;
  dwDisposition = 0;
  SidFromToken = GetSidFromToken(a1, (HGLOBAL *)&lpSubKey);
  if ( !SidFromToken )
  {
    SidFromToken = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( !SidFromToken )
      SidFromToken = RegCreateKeyExW(
                       hKey,
                       L"Software\\Microsoft\\RAS EAP\\UserEapInfo",
                       0,
                       0,
                       0,
                       0xF003Fu,
                       0,
                       &v5,
                       &dwDisposition);
  }
  Free0(lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  *a2 = v5;
  return SidFromToken;
}

```

## disassembly

```asm
0x1800c1c78  push    rbp
0x1800c1c7a  push    rbx
0x1800c1c7b  push    rdi
0x1800c1c7c  mov     rbp, rsp
0x1800c1c7f  sub     rsp, 60h
0x1800c1c83  mov     rdi, rdx
0x1800c1c86  mov     [rbp+lpSubKey], 0
0x1800c1c8e  lea     rdx, [rbp+lpSubKey]
0x1800c1c92  mov     [rbp+hKey], 0
0x1800c1c9a  mov     [rbp+var_10], 0
0x1800c1ca2  mov     [rbp+dwDisposition], 0
0x1800c1ca9  call    GetSidFromToken
0x1800c1cae  mov     ebx, eax
0x1800c1cb0  test    eax, eax
0x1800c1cb2  jnz     short loc_1800C1D1D
0x1800c1cb4  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800c1cb8  lea     rax, [rbp+hKey]
0x1800c1cbc  mov     r9d, 0F003Fh; samDesired
0x1800c1cc2  mov     [rsp+60h+phkResult], rax; phkResult
0x1800c1cc7  xor     r8d, r8d; ulOptions
0x1800c1cca  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800c1cd1  call    cs:__imp_RegOpenKeyExW
0x1800c1cd7  mov     ebx, eax
0x1800c1cd9  test    eax, eax
0x1800c1cdb  jnz     short loc_1800C1D1D
0x1800c1cdd  mov     rcx, [rbp+hKey]; hKey
0x1800c1ce1  lea     rax, [rbp+dwDisposition]
0x1800c1ce5  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x1800c1cea  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\RAS EAP\\UserEapIn"...
0x1800c1cf1  lea     rax, [rbp+var_10]
0x1800c1cf5  xor     r9d, r9d; lpClass
0x1800c1cf8  mov     [rsp+60h+var_28], rax; phkResult
0x1800c1cfd  xor     r8d, r8d; Reserved
0x1800c1d00  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800c1d09  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x1800c1d11  mov     dword ptr [rsp+60h+phkResult], ebx; dwOptions
0x1800c1d15  call    cs:__imp_RegCreateKeyExW
0x1800c1d1b  mov     ebx, eax
0x1800c1d1d  mov     rcx, [rbp+lpSubKey]
0x1800c1d21  call    Free0
0x1800c1d26  mov     rcx, [rbp+hKey]; hKey
0x1800c1d2a  test    rcx, rcx
0x1800c1d2d  jz      short loc_1800C1D35
0x1800c1d2f  call    cs:__imp_RegCloseKey
0x1800c1d35  mov     rax, [rbp+var_10]
0x1800c1d39  mov     [rdi], rax
0x1800c1d3c  mov     eax, ebx
0x1800c1d3e  add     rsp, 60h
0x1800c1d42  pop     rdi
0x1800c1d43  pop     rbx
0x1800c1d44  pop     rbp
0x1800c1d45  retn
```
