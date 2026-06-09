# OpenLsaKey

- ea: `0x18002748c`
- end: `0x1800275a1`
- name: `OpenLsaKey`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002762c`

## callees

- `0x18002748c`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800274ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800274ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027529`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027529`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027571`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027571`

## pseudocode

```c
HKEY OpenLsaKey()
{
  const WCHAR *v0; // rbx
  DWORD pcbData; // [rsp+50h] [rbp-238h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-230h] BYREF
  _BYTE pvData[528]; // [rsp+60h] [rbp-228h] BYREF

  pcbData = 260;
  phkResult = 0;
  v0 = (const WCHAR *)pvData;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Lsa",
         L"RedirectionKey",
         2u,
         0,
         pvData,
         &pcbData) )
  {
    v0 = L"System\\CurrentControlSet\\Control\\Lsa";
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0x2001Fu, &phkResult) == 2
    && v0 != L"System\\CurrentControlSet\\Control\\Lsa" )
  {
    RegCreateKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18002748c  mov     [rsp+arg_0], rbx
0x180027491  mov     [rsp+arg_8], rbp
0x180027496  push    rsi
0x180027497  sub     rsp, 280h
0x18002749e  mov     rax, cs:__security_cookie
0x1800274a5  xor     rax, rsp
0x1800274a8  mov     [rsp+288h+var_18], rax
0x1800274b0  lea     rax, [rsp+288h+var_238]
0x1800274b5  mov     [rsp+288h+var_238], 104h
0x1800274bd  mov     [rsp+288h+pcbData], rax; pcbData
0x1800274c2  lea     rsi, aSystemCurrentc_11; "System\\CurrentControlSet\\Control\\Lsa"
0x1800274c9  lea     rax, [rsp+288h+var_228]
0x1800274ce  mov     [rsp+288h+phkResult], 0
0x1800274d7  mov     [rsp+288h+pvData], rax; pvData
0x1800274dc  lea     r8, aRedirectionkey; "RedirectionKey"
0x1800274e3  mov     rbp, 0FFFFFFFF80000002h
0x1800274ea  mov     [rsp+288h+pdwType], 0; pdwType
0x1800274f3  mov     r9d, 2; dwFlags
0x1800274f9  mov     rdx, rsi; lpSubKey
0x1800274fc  mov     rcx, rbp; hkey
0x1800274ff  call    cs:__imp_RegGetValueW
0x180027505  lea     rbx, [rsp+288h+var_228]
0x18002750a  mov     r9d, 2001Fh; samDesired
0x180027510  test    eax, eax
0x180027512  mov     rcx, rbp; hKey
0x180027515  lea     rax, [rsp+288h+phkResult]
0x18002751a  cmovnz  rbx, rsi
0x18002751e  mov     [rsp+288h+pdwType], rax; phkResult
0x180027523  mov     rdx, rbx; lpSubKey
0x180027526  xor     r8d, r8d; ulOptions
0x180027529  call    cs:__imp_RegOpenKeyExW
0x18002752f  cmp     eax, 2
0x180027532  jnz     short loc_180027577
0x180027534  cmp     rbx, rsi
0x180027537  jz      short loc_180027577
0x180027539  mov     [rsp+288h+lpdwDisposition], 0; lpdwDisposition
0x180027542  lea     rax, [rsp+288h+phkResult]
0x180027547  mov     [rsp+288h+var_250], rax; phkResult
0x18002754c  xor     r9d, r9d; lpClass
0x18002754f  mov     [rsp+288h+pcbData], 0; lpSecurityAttributes
0x180027558  xor     r8d, r8d; Reserved
0x18002755b  mov     dword ptr [rsp+288h+pvData], 2001Fh; samDesired
0x180027563  mov     rdx, rbx; lpSubKey
0x180027566  mov     rcx, rbp; hKey
0x180027569  mov     dword ptr [rsp+288h+pdwType], 0; dwOptions
0x180027571  call    cs:__imp_RegCreateKeyExW
0x180027577  mov     rax, [rsp+288h+phkResult]
0x18002757c  mov     rcx, [rsp+288h+var_18]
0x180027584  xor     rcx, rsp; StackCookie
0x180027587  call    __security_check_cookie
0x18002758c  lea     r11, [rsp+288h+var_8]
0x180027594  mov     rbx, [r11+10h]
0x180027598  mov     rbp, [r11+18h]
0x18002759c  mov     rsp, r11
0x18002759f  pop     rsi
0x1800275a0  retn
```
