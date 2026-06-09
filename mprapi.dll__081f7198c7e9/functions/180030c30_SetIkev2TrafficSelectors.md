# SetIkev2TrafficSelectors

- ea: `0x180030c30`
- end: `0x180030f94`
- name: `SetIkev2TrafficSelectors`
- size: `868`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180024c10`

## callees

- `0x180009868`
- `0x180030c30`
- `0x180030f9c`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030c9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030d22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030dab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030c9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030d22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030dab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030cdf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030d7c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030e0e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030e89`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030f06`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030cdf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030d7c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030e0e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030e89`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030f06`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180030d3a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180030dc3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180030d3a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180030dc3`

## pseudocode

```c
__int64 __fastcall SetIkev2TrafficSelectors(HKEY hKey, unsigned int *a2)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  char v6; // r15
  char v7; // di
  unsigned int v8; // edi
  unsigned int i; // edi
  HKEY v10; // rcx
  DWORD dwDisposition; // [rsp+50h] [rbp-19h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-11h] BYREF
  HKEY v14; // [rsp+60h] [rbp-9h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-1h] BYREF
  HKEY v16; // [rsp+70h] [rbp+7h] BYREF
  wchar_t pszDest[12]; // [rsp+78h] [rbp+Fh] BYREF

  hKeya = 0;
  phkResult = 0;
  v16 = 0;
  dwDisposition = 0;
  if ( !hKey )
    return 87;
  v5 = RegOpenKeyExW(hKey, L"TrafficSelectors", 0, 0x20019u, &hKeya);
  v4 = v5;
  if ( v5 == 2 )
  {
    v4 = RegCreateKeyExW(hKey, L"TrafficSelectors", 0, 0, 0, 0x3001Fu, 0, &hKeya, &dwDisposition);
    if ( v4 )
      goto LABEL_27;
    v6 = 0;
    v7 = 1;
  }
  else
  {
    if ( v5 )
      goto LABEL_27;
    v7 = 0;
    if ( RegOpenKeyExW(hKeya, L"Initiator", 0, 0x3001Fu, &phkResult) || !*a2 )
      goto LABEL_12;
    v6 = 1;
    v4 = RegDeleteTreeW(phkResult, 0);
    if ( v4 )
      goto LABEL_27;
  }
  v4 = RegCreateKeyExW(hKeya, L"Initiator", 0, 0, 0, 0x3001Fu, 0, &phkResult, &dwDisposition);
  if ( v4 )
    goto LABEL_27;
  if ( !v6 )
    goto LABEL_15;
LABEL_12:
  v4 = RegOpenKeyExW(hKeya, L"Responder", 0, 0x3001Fu, &v16);
  if ( v4 || !a2[1] || (v4 = RegDeleteTreeW(v16, 0), v7 = 1, !v4) )
  {
LABEL_15:
    if ( v7 != 1 || (v4 = RegCreateKeyExW(hKeya, L"Responder", 0, 0, 0, 0x3001Fu, 0, &v16, &dwDisposition)) == 0 )
    {
      if ( phkResult && v16 )
      {
        v8 = 0;
        if ( *a2 )
        {
          while ( 1 )
          {
            v14 = 0;
            StringCbPrintfW(pszDest, 0x18u, L"%d", v8);
            v4 = RegCreateKeyExW(phkResult, pszDest, 0, 0, 0, 0x3001Fu, 0, &v14, &dwDisposition);
            if ( v4 )
              break;
            ++v8;
            v4 = SetIkev2TrafficSelectorsRegParams(v14);
            if ( v8 >= *a2 )
              goto LABEL_22;
          }
        }
        else
        {
LABEL_22:
          for ( i = 0; i < a2[1]; v4 = SetIkev2TrafficSelectorsRegParams(v14) )
          {
            v14 = 0;
            StringCbPrintfW(pszDest, 0x18u, L"%d", i);
            v4 = RegCreateKeyExW(v16, pszDest, 0, 0, 0, 0x3001Fu, 0, &v14, &dwDisposition);
            if ( v4 )
              break;
            ++i;
          }
        }
      }
      else
      {
        v4 = 87;
      }
    }
  }
LABEL_27:
  v10 = hKeya;
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    v10 = 0;
    hKeya = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(v10);
    v10 = 0;
    hKeya = 0;
  }
  if ( v16 )
    RegCloseKey(v10);
  return v4;
}

```

## disassembly

```asm
0x180030c30  mov     [rsp-8+arg_10], rbx
0x180030c35  mov     [rsp-8+arg_18], rsi
0x180030c3a  push    rbp
0x180030c3b  push    rdi
0x180030c3c  push    r12
0x180030c3e  push    r14
0x180030c40  push    r15
0x180030c42  lea     rbp, [rsp-37h]
0x180030c47  sub     rsp, 0A0h
0x180030c4e  mov     rax, cs:__security_cookie
0x180030c55  xor     rax, rsp
0x180030c58  mov     [rbp+57h+var_30], rax
0x180030c5c  xor     r12d, r12d
0x180030c5f  mov     rsi, rdx
0x180030c62  mov     [rbp+57h+hKey], r12
0x180030c66  mov     rdi, rcx
0x180030c69  mov     [rbp+57h+var_58], r12
0x180030c6d  mov     [rbp+57h+var_50], r12
0x180030c71  mov     [rbp+57h+dwDisposition], r12d
0x180030c75  test    rcx, rcx
0x180030c78  jnz     short loc_180030C82
0x180030c7a  lea     ebx, [rcx+57h]
0x180030c7d  jmp     loc_180030F6A
0x180030c82  lea     rax, [rbp+57h+hKey]
0x180030c86  mov     r9d, 20019h; samDesired
0x180030c8c  xor     r8d, r8d; ulOptions
0x180030c8f  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180030c94  lea     rdx, aTrafficselecto; "TrafficSelectors"
0x180030c9b  call    cs:__imp_RegOpenKeyExW
0x180030ca1  mov     ebx, eax
0x180030ca3  cmp     eax, 2
0x180030ca6  jnz     short loc_180030CF7
0x180030ca8  lea     rax, [rbp+57h+dwDisposition]
0x180030cac  mov     r14d, 3001Fh
0x180030cb2  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180030cb7  lea     rdx, aTrafficselecto; "TrafficSelectors"
0x180030cbe  lea     rax, [rbp+57h+hKey]
0x180030cc2  xor     r9d, r9d; lpClass
0x180030cc5  mov     [rsp+0C0h+var_88], rax; phkResult
0x180030cca  xor     r8d, r8d; Reserved
0x180030ccd  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180030cd2  mov     rcx, rdi; hKey
0x180030cd5  mov     [rsp+0C0h+samDesired], r14d; samDesired
0x180030cda  mov     dword ptr [rsp+0C0h+phkResult], r12d; dwOptions
0x180030cdf  call    cs:__imp_RegCreateKeyExW
0x180030ce5  mov     ebx, eax
0x180030ce7  test    eax, eax
0x180030ce9  jnz     loc_180030F35
0x180030cef  mov     r15b, r12b
0x180030cf2  mov     dil, 1
0x180030cf5  jmp     short loc_180030D4A
0x180030cf7  test    eax, eax
0x180030cf9  jnz     loc_180030F35
0x180030cff  mov     rcx, [rbp+57h+hKey]; hKey
0x180030d03  lea     rax, [rbp+57h+var_58]
0x180030d07  mov     r14d, 3001Fh
0x180030d0d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180030d12  mov     r9d, r14d; samDesired
0x180030d15  lea     rdx, aInitiator; "Initiator"
0x180030d1c  xor     r8d, r8d; ulOptions
0x180030d1f  mov     dil, r12b
0x180030d22  call    cs:__imp_RegOpenKeyExW
0x180030d28  test    eax, eax
0x180030d2a  jnz     short loc_180030D91
0x180030d2c  cmp     [rsi], r12d
0x180030d2f  jz      short loc_180030D91
0x180030d31  mov     rcx, [rbp+57h+var_58]; hKey
0x180030d35  xor     edx, edx; lpSubKey
0x180030d37  mov     r15b, 1
0x180030d3a  call    cs:__imp_RegDeleteTreeW
0x180030d40  mov     ebx, eax
0x180030d42  test    eax, eax
0x180030d44  jnz     loc_180030F35
0x180030d4a  mov     rcx, [rbp+57h+hKey]; hKey
0x180030d4e  lea     rax, [rbp+57h+dwDisposition]
0x180030d52  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180030d57  lea     rdx, aInitiator; "Initiator"
0x180030d5e  lea     rax, [rbp+57h+var_58]
0x180030d62  xor     r9d, r9d; lpClass
0x180030d65  mov     [rsp+0C0h+var_88], rax; phkResult
0x180030d6a  xor     r8d, r8d; Reserved
0x180030d6d  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180030d72  mov     [rsp+0C0h+samDesired], r14d; samDesired
0x180030d77  mov     dword ptr [rsp+0C0h+phkResult], r12d; dwOptions
0x180030d7c  call    cs:__imp_RegCreateKeyExW
0x180030d82  mov     ebx, eax
0x180030d84  test    eax, eax
0x180030d86  jnz     loc_180030F35
0x180030d8c  test    r15b, r15b
0x180030d8f  jz      short loc_180030DD6
0x180030d91  mov     rcx, [rbp+57h+hKey]; hKey
0x180030d95  lea     rax, [rbp+57h+var_50]
0x180030d99  mov     r9d, r14d; samDesired
0x180030d9c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180030da1  xor     r8d, r8d; ulOptions
0x180030da4  lea     rdx, aResponder; "Responder"
0x180030dab  call    cs:__imp_RegOpenKeyExW
0x180030db1  mov     ebx, eax
0x180030db3  test    eax, eax
0x180030db5  jnz     short loc_180030DD6
0x180030db7  cmp     [rsi+4], r12d
0x180030dbb  jz      short loc_180030DD6
0x180030dbd  mov     rcx, [rbp+57h+var_50]; hKey
0x180030dc1  xor     edx, edx; lpSubKey
0x180030dc3  call    cs:__imp_RegDeleteTreeW
0x180030dc9  mov     ebx, eax
0x180030dcb  mov     dil, 1
0x180030dce  test    eax, eax
0x180030dd0  jnz     loc_180030F35
0x180030dd6  cmp     dil, 1
0x180030dda  jnz     short loc_180030E1E
0x180030ddc  mov     rcx, [rbp+57h+hKey]; hKey
0x180030de0  lea     rax, [rbp+57h+dwDisposition]
0x180030de4  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180030de9  lea     rdx, aResponder; "Responder"
0x180030df0  lea     rax, [rbp+57h+var_50]
0x180030df4  xor     r9d, r9d; lpClass
0x180030df7  mov     [rsp+0C0h+var_88], rax; phkResult
0x180030dfc  xor     r8d, r8d; Reserved
0x180030dff  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180030e04  mov     [rsp+0C0h+samDesired], r14d; samDesired
0x180030e09  mov     dword ptr [rsp+0C0h+phkResult], r12d; dwOptions
0x180030e0e  call    cs:__imp_RegCreateKeyExW
0x180030e14  mov     ebx, eax
0x180030e16  test    eax, eax
0x180030e18  jnz     loc_180030F35
0x180030e1e  cmp     [rbp+57h+var_58], r12
0x180030e22  jz      loc_180030F30
0x180030e28  cmp     [rbp+57h+var_50], r12
0x180030e2c  jz      loc_180030F30
0x180030e32  mov     edi, r12d
0x180030e35  mov     r15d, 18h
0x180030e3b  cmp     [rsi], r12d
0x180030e3e  jbe     short loc_180030EB4
0x180030e40  mov     r9d, edi
0x180030e43  mov     [rbp+57h+var_60], r12
0x180030e47  lea     r8, aD; "%d"
0x180030e4e  mov     rdx, r15; cbDest
0x180030e51  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180030e55  call    StringCbPrintfW
0x180030e5a  mov     rcx, [rbp+57h+var_58]; hKey
0x180030e5e  lea     rax, [rbp+57h+dwDisposition]
0x180030e62  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180030e67  lea     rdx, [rbp+57h+pszDest]; lpSubKey
0x180030e6b  lea     rax, [rbp+57h+var_60]
0x180030e6f  xor     r9d, r9d; lpClass
0x180030e72  mov     [rsp+0C0h+var_88], rax; phkResult
0x180030e77  xor     r8d, r8d; Reserved
0x180030e7a  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180030e7f  mov     [rsp+0C0h+samDesired], r14d; samDesired
0x180030e84  mov     dword ptr [rsp+0C0h+phkResult], r12d; dwOptions
0x180030e89  call    cs:__imp_RegCreateKeyExW
0x180030e8f  mov     ebx, eax
0x180030e91  test    eax, eax
0x180030e93  jnz     loc_180030F35
0x180030e99  mov     rcx, [rbp+57h+var_60]; hKey
0x180030e9d  mov     eax, edi
0x180030e9f  imul    rdx, rax, 34h ; '4'
0x180030ea3  add     rdx, [rsi+8]
0x180030ea7  call    SetIkev2TrafficSelectorsRegParams
0x180030eac  inc     edi
0x180030eae  mov     ebx, eax
0x180030eb0  cmp     edi, [rsi]
0x180030eb2  jb      short loc_180030E40
0x180030eb4  mov     edi, r12d
0x180030eb7  cmp     [rsi+4], r12d
0x180030ebb  jbe     short loc_180030F35
0x180030ebd  mov     r9d, edi
0x180030ec0  mov     [rbp+57h+var_60], r12
0x180030ec4  lea     r8, aD; "%d"
0x180030ecb  mov     rdx, r15; cbDest
0x180030ece  lea     rcx, [rbp+57h+pszDest]; pszDest
0x180030ed2  call    StringCbPrintfW
0x180030ed7  mov     rcx, [rbp+57h+var_50]; hKey
0x180030edb  lea     rax, [rbp+57h+dwDisposition]
0x180030edf  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180030ee4  lea     rdx, [rbp+57h+pszDest]; lpSubKey
0x180030ee8  lea     rax, [rbp+57h+var_60]
0x180030eec  xor     r9d, r9d; lpClass
0x180030eef  mov     [rsp+0C0h+var_88], rax; phkResult
0x180030ef4  xor     r8d, r8d; Reserved
0x180030ef7  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180030efc  mov     [rsp+0C0h+samDesired], r14d; samDesired
0x180030f01  mov     dword ptr [rsp+0C0h+phkResult], r12d; dwOptions
0x180030f06  call    cs:__imp_RegCreateKeyExW
0x180030f0c  mov     ebx, eax
0x180030f0e  test    eax, eax
0x180030f10  jnz     short loc_180030F35
0x180030f12  mov     rcx, [rbp+57h+var_60]; hKey
0x180030f16  mov     eax, edi
0x180030f18  imul    rdx, rax, 34h ; '4'
0x180030f1c  add     rdx, [rsi+10h]
0x180030f20  call    SetIkev2TrafficSelectorsRegParams
0x180030f25  inc     edi
0x180030f27  mov     ebx, eax
0x180030f29  cmp     edi, [rsi+4]
0x180030f2c  jb      short loc_180030EBD
0x180030f2e  jmp     short loc_180030F35
0x180030f30  mov     ebx, 57h ; 'W'
0x180030f35  mov     rcx, [rbp+57h+hKey]; hKey
0x180030f39  test    rcx, rcx
0x180030f3c  jz      short loc_180030F4B
0x180030f3e  call    cs:__imp_RegCloseKey
0x180030f44  mov     rcx, r12; hKey
0x180030f47  mov     [rbp+57h+hKey], rcx
0x180030f4b  cmp     [rbp+57h+var_58], r12
0x180030f4f  jz      short loc_180030F5E
0x180030f51  call    cs:__imp_RegCloseKey
0x180030f57  mov     rcx, r12; hKey
0x180030f5a  mov     [rbp+57h+hKey], rcx
0x180030f5e  cmp     [rbp+57h+var_50], r12
0x180030f62  jz      short loc_180030F6A
0x180030f64  call    cs:__imp_RegCloseKey
0x180030f6a  mov     eax, ebx
0x180030f6c  mov     rcx, [rbp+57h+var_30]
0x180030f70  xor     rcx, rsp; StackCookie
0x180030f73  call    __security_check_cookie
0x180030f78  lea     r11, [rsp+0C0h+var_20]
0x180030f80  mov     rbx, [r11+40h]
0x180030f84  mov     rsi, [r11+48h]
0x180030f88  mov     rsp, r11
0x180030f8b  pop     r15
0x180030f8d  pop     r14
0x180030f8f  pop     r12
0x180030f91  pop     rdi
0x180030f92  pop     rbp
0x180030f93  retn
```
