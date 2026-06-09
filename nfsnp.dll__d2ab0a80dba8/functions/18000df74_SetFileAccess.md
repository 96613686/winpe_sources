# SetFileAccess

- ea: `0x18000df74`
- end: `0x18000e08d`
- name: `SetFileAccess`
- size: `281`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000be24`
- `0x18000e454`

## callees

- `0x18000df74`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000dff8`
- `msvcrt!wcscat_s` at `0x18000dff8`
- `msvcrt!wcsncpy_s` at `0x18000dfe1`
- `msvcrt!wcsncpy_s` at `0x18000dfe1`
- `ADVAPI32!RegCloseKey` at `0x18000e062`
- `ADVAPI32!RegCloseKey` at `0x18000e062`
- `ADVAPI32!RegQueryValueExW` at `0x18000e055`
- `ADVAPI32!RegQueryValueExW` at `0x18000e055`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e01d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e01d`

## string_xrefs

- `0x18000e036`: `Access`

## pseudocode

```c
LSTATUS __fastcall SetFileAccess(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  LSTATUS v5; // edi
  LSTATUS result; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = 493;
  hKey = 0;
  *(_DWORD *)Data = 493;
  cbData = 0;
  v5 = 13;
  memset_0(Destination, 0, 0x208u);
  wcsncpy_s(Destination, 0x104u, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default", 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Defaults");
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Destination, 0, 0x20019u, &hKey);
  if ( !result )
  {
    cbData = 4;
    v5 = RegQueryValueExW(hKey, L"Access", 0, 0, Data, &cbData);
    result = RegCloseKey(hKey);
  }
  if ( !v5 )
    v3 = *(_DWORD *)Data;
  *(_DWORD *)(a3 + 32) = v3;
  return result;
}

```

## disassembly

```asm
0x18000df74  push    rbp
0x18000df76  push    rbx
0x18000df77  push    rsi
0x18000df78  push    rdi
0x18000df79  lea     rbp, [rsp-168h]
0x18000df81  sub     rsp, 268h
0x18000df88  mov     rax, cs:__security_cookie
0x18000df8f  xor     rax, rsp
0x18000df92  mov     [rbp+180h+var_30], rax
0x18000df99  mov     ebx, 1EDh
0x18000df9e  mov     [rsp+280h+hKey], 0
0x18000dfa7  mov     rsi, r8
0x18000dfaa  mov     dword ptr [rsp+280h+Data], ebx
0x18000dfae  xor     edx, edx; Val
0x18000dfb0  mov     [rsp+280h+cbData], 0
0x18000dfb8  lea     rcx, [rsp+280h+Destination]; void *
0x18000dfbd  mov     edi, 0Dh
0x18000dfc2  lea     r8d, [rbx+1Bh]; Size
0x18000dfc6  call    memset_0
0x18000dfcb  mov     r9d, 103h; MaxCount
0x18000dfd1  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000dfd8  lea     rcx, [rsp+280h+Destination]; Destination
0x18000dfdd  lea     edx, [r9+1]; SizeInWords
0x18000dfe1  call    cs:__imp_wcsncpy_s
0x18000dfe7  lea     r8, aDefaults; "\\Defaults"
0x18000dfee  mov     edx, 104h; SizeInWords
0x18000dff3  lea     rcx, [rsp+280h+Destination]; Destination
0x18000dff8  call    cs:__imp_wcscat_s
0x18000dffe  lea     rax, [rsp+280h+hKey]
0x18000e003  mov     r9d, 20019h; samDesired
0x18000e009  xor     r8d, r8d; ulOptions
0x18000e00c  mov     [rsp+280h+phkResult], rax; phkResult
0x18000e011  lea     rdx, [rsp+280h+Destination]; lpSubKey
0x18000e016  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e01d  call    cs:__imp_RegOpenKeyExW
0x18000e023  test    eax, eax
0x18000e025  jnz     short loc_18000E068
0x18000e027  mov     rcx, [rsp+280h+hKey]; hKey
0x18000e02c  lea     rax, [rsp+280h+cbData]
0x18000e031  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000e036  lea     rdx, aAccess; "Access"
0x18000e03d  lea     rax, [rsp+280h+Data]
0x18000e042  mov     [rsp+280h+cbData], 4
0x18000e04a  xor     r9d, r9d; lpType
0x18000e04d  mov     [rsp+280h+phkResult], rax; lpData
0x18000e052  xor     r8d, r8d; lpReserved
0x18000e055  call    cs:__imp_RegQueryValueExW
0x18000e05b  mov     rcx, [rsp+280h+hKey]; hKey
0x18000e060  mov     edi, eax
0x18000e062  call    cs:__imp_RegCloseKey
0x18000e068  test    edi, edi
0x18000e06a  cmovz   ebx, dword ptr [rsp+280h+Data]
0x18000e06f  mov     [rsi+20h], ebx
0x18000e072  mov     rcx, [rbp+180h+var_30]
0x18000e079  xor     rcx, rsp; StackCookie
0x18000e07c  call    __security_check_cookie
0x18000e081  add     rsp, 268h
0x18000e088  pop     rdi
0x18000e089  pop     rsi
0x18000e08a  pop     rbx
0x18000e08b  pop     rbp
0x18000e08c  retn
```
