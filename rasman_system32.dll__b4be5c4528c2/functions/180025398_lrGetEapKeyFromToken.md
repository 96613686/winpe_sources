# lrGetEapKeyFromToken

- ea: `0x180025398`
- end: `0x180025479`
- name: `lrGetEapKeyFromToken`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024a50`

## callees

- `0x180025398`
- `0x1800254c4`
- `0x180025798`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002545b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002545b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800253f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800253f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002543b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002543b`

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
0x180025398  push    rbp
0x18002539a  push    rbx
0x18002539b  push    rdi
0x18002539c  mov     rbp, rsp
0x18002539f  sub     rsp, 60h
0x1800253a3  mov     rdi, rdx
0x1800253a6  mov     [rbp+lpSubKey], 0
0x1800253ae  lea     rdx, [rbp+lpSubKey]
0x1800253b2  mov     [rbp+hKey], 0
0x1800253ba  mov     [rbp+var_10], 0
0x1800253c2  mov     [rbp+dwDisposition], 0
0x1800253c9  call    GetSidFromToken
0x1800253ce  mov     ebx, eax
0x1800253d0  test    eax, eax
0x1800253d2  jnz     short loc_180025449
0x1800253d4  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800253d8  lea     rax, [rbp+hKey]
0x1800253dc  mov     r9d, 0F003Fh; samDesired
0x1800253e2  mov     [rsp+60h+phkResult], rax; phkResult
0x1800253e7  xor     r8d, r8d; ulOptions
0x1800253ea  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800253f1  call    cs:__imp_RegOpenKeyExW
0x1800253f8  nop     dword ptr [rax+rax+00h]
0x1800253fd  mov     ebx, eax
0x1800253ff  test    eax, eax
0x180025401  jnz     short loc_180025449
0x180025403  mov     rcx, [rbp+hKey]; hKey
0x180025407  lea     rax, [rbp+dwDisposition]
0x18002540b  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180025410  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\RAS EAP\\UserEapIn"...
0x180025417  lea     rax, [rbp+var_10]
0x18002541b  xor     r9d, r9d; lpClass
0x18002541e  mov     [rsp+60h+var_28], rax; phkResult
0x180025423  xor     r8d, r8d; Reserved
0x180025426  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002542f  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180025437  mov     dword ptr [rsp+60h+phkResult], ebx; dwOptions
0x18002543b  call    cs:__imp_RegCreateKeyExW
0x180025442  nop     dword ptr [rax+rax+00h]
0x180025447  mov     ebx, eax
0x180025449  mov     rcx, [rbp+lpSubKey]
0x18002544d  call    Free0
0x180025452  mov     rcx, [rbp+hKey]; hKey
0x180025456  test    rcx, rcx
0x180025459  jz      short loc_180025467
0x18002545b  call    cs:__imp_RegCloseKey
0x180025462  nop     dword ptr [rax+rax+00h]
0x180025467  mov     rax, [rbp+var_10]
0x18002546b  mov     [rdi], rax
0x18002546e  mov     eax, ebx
0x180025470  add     rsp, 60h
0x180025474  pop     rdi
0x180025475  pop     rbx
0x180025476  pop     rbp
0x180025477  retn
```
