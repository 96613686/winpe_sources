# SetSecFlags

- ea: `0x18000e984`
- end: `0x18000ea84`
- name: `SetSecFlags`
- size: `256`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000be24`
- `0x18000e454`

## callees

- `0x18000e984`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000e9f9`
- `msvcrt!wcscat_s` at `0x18000e9f9`
- `msvcrt!wcsncpy_s` at `0x18000e9e2`
- `msvcrt!wcsncpy_s` at `0x18000e9e2`
- `ADVAPI32!RegCloseKey` at `0x18000ea5d`
- `ADVAPI32!RegCloseKey` at `0x18000ea5d`
- `ADVAPI32!RegQueryValueExW` at `0x18000ea52`
- `ADVAPI32!RegQueryValueExW` at `0x18000ea52`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea1a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ea1a`

## string_xrefs

- `0x18000e9e8`: `\Mount`

## pseudocode

```c
__int64 __fastcall SetSecFlags(HKEY hKey, wchar_t *Source, __int64 a3)
{
  __int64 result; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 15;
  cbData = 0;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    cbData = 4;
    RegQueryValueExW(hKeya, L"SecFlavors", 0, 0, Data, &cbData);
    RegCloseKey(hKeya);
  }
  result = *(unsigned int *)Data;
  *(_DWORD *)(a3 + 60) = *(_DWORD *)Data;
  return result;
}

```

## disassembly

```asm
0x18000e984  push    rbp
0x18000e986  push    rbx
0x18000e987  push    rdi
0x18000e988  lea     rbp, [rsp-160h]
0x18000e990  sub     rsp, 260h
0x18000e997  mov     rax, cs:__security_cookie
0x18000e99e  xor     rax, rsp
0x18000e9a1  mov     [rbp+170h+var_20], rax
0x18000e9a8  mov     r9d, 103h; MaxCount
0x18000e9ae  mov     [rsp+270h+hKey], 0
0x18000e9b7  mov     rdi, r8
0x18000e9ba  mov     dword ptr [rsp+270h+Data], 0Fh
0x18000e9c2  mov     rbx, rcx
0x18000e9c5  mov     [rsp+270h+cbData], 0
0x18000e9cd  xor     eax, eax
0x18000e9cf  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e9d4  mov     r8, rdx; Source
0x18000e9d7  mov     [rbp+170h+var_2A], ax
0x18000e9de  lea     edx, [r9+1]; SizeInWords
0x18000e9e2  call    cs:__imp_wcsncpy_s
0x18000e9e8  lea     r8, aMount; "\\Mount"
0x18000e9ef  mov     edx, 104h; SizeInWords
0x18000e9f4  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e9f9  call    cs:__imp_wcscat_s
0x18000e9ff  lea     rax, [rsp+270h+hKey]
0x18000ea04  mov     r9d, 20019h; samDesired
0x18000ea0a  xor     r8d, r8d; ulOptions
0x18000ea0d  mov     [rsp+270h+phkResult], rax; phkResult
0x18000ea12  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000ea17  mov     rcx, rbx; hKey
0x18000ea1a  call    cs:__imp_RegOpenKeyExW
0x18000ea20  test    eax, eax
0x18000ea22  jnz     short loc_18000EA63
0x18000ea24  mov     rcx, [rsp+270h+hKey]; hKey
0x18000ea29  lea     rax, [rsp+270h+cbData]
0x18000ea2e  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000ea33  lea     rdx, aSecflavors; "SecFlavors"
0x18000ea3a  lea     rax, [rsp+270h+Data]
0x18000ea3f  mov     [rsp+270h+cbData], 4
0x18000ea47  xor     r9d, r9d; lpType
0x18000ea4a  mov     [rsp+270h+phkResult], rax; lpData
0x18000ea4f  xor     r8d, r8d; lpReserved
0x18000ea52  call    cs:__imp_RegQueryValueExW
0x18000ea58  mov     rcx, [rsp+270h+hKey]; hKey
0x18000ea5d  call    cs:__imp_RegCloseKey
0x18000ea63  mov     eax, dword ptr [rsp+270h+Data]
0x18000ea67  mov     [rdi+3Ch], eax
0x18000ea6a  mov     rcx, [rbp+170h+var_20]
0x18000ea71  xor     rcx, rsp; StackCookie
0x18000ea74  call    __security_check_cookie
0x18000ea79  add     rsp, 260h
0x18000ea80  pop     rdi
0x18000ea81  pop     rbx
0x18000ea82  pop     rbp
0x18000ea83  retn
```
