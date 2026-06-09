# SetTimeout

- ea: `0x18000ebc4`
- end: `0x18000ecc4`
- name: `SetTimeout`
- size: `256`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000be24`
- `0x18000e454`

## callees

- `0x18000ebc4`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000ec39`
- `msvcrt!wcscat_s` at `0x18000ec39`
- `msvcrt!wcsncpy_s` at `0x18000ec22`
- `msvcrt!wcsncpy_s` at `0x18000ec22`
- `ADVAPI32!RegCloseKey` at `0x18000ec9d`
- `ADVAPI32!RegCloseKey` at `0x18000ec9d`
- `ADVAPI32!RegQueryValueExW` at `0x18000ec92`
- `ADVAPI32!RegQueryValueExW` at `0x18000ec92`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ec5a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ec5a`

## string_xrefs

- `0x18000ec28`: `\Mount`

## pseudocode

```c
__int64 __fastcall SetTimeout(HKEY hKey, wchar_t *Source, __int64 a3)
{
  __int64 result; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 8;
  cbData = 0;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    cbData = 4;
    RegQueryValueExW(hKeya, L"Timeout", 0, 0, Data, &cbData);
    RegCloseKey(hKeya);
  }
  result = *(unsigned int *)Data;
  *(_DWORD *)(a3 + 20) = *(_DWORD *)Data;
  return result;
}

```

## disassembly

```asm
0x18000ebc4  push    rbp
0x18000ebc6  push    rbx
0x18000ebc7  push    rdi
0x18000ebc8  lea     rbp, [rsp-160h]
0x18000ebd0  sub     rsp, 260h
0x18000ebd7  mov     rax, cs:__security_cookie
0x18000ebde  xor     rax, rsp
0x18000ebe1  mov     [rbp+170h+var_20], rax
0x18000ebe8  mov     r9d, 103h; MaxCount
0x18000ebee  mov     [rsp+270h+hKey], 0
0x18000ebf7  mov     rdi, r8
0x18000ebfa  mov     dword ptr [rsp+270h+Data], 8
0x18000ec02  mov     rbx, rcx
0x18000ec05  mov     [rsp+270h+cbData], 0
0x18000ec0d  xor     eax, eax
0x18000ec0f  lea     rcx, [rsp+270h+Destination]; Destination
0x18000ec14  mov     r8, rdx; Source
0x18000ec17  mov     [rbp+170h+var_2A], ax
0x18000ec1e  lea     edx, [r9+1]; SizeInWords
0x18000ec22  call    cs:__imp_wcsncpy_s
0x18000ec28  lea     r8, aMount; "\\Mount"
0x18000ec2f  mov     edx, 104h; SizeInWords
0x18000ec34  lea     rcx, [rsp+270h+Destination]; Destination
0x18000ec39  call    cs:__imp_wcscat_s
0x18000ec3f  lea     rax, [rsp+270h+hKey]
0x18000ec44  mov     r9d, 20019h; samDesired
0x18000ec4a  xor     r8d, r8d; ulOptions
0x18000ec4d  mov     [rsp+270h+phkResult], rax; phkResult
0x18000ec52  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000ec57  mov     rcx, rbx; hKey
0x18000ec5a  call    cs:__imp_RegOpenKeyExW
0x18000ec60  test    eax, eax
0x18000ec62  jnz     short loc_18000ECA3
0x18000ec64  mov     rcx, [rsp+270h+hKey]; hKey
0x18000ec69  lea     rax, [rsp+270h+cbData]
0x18000ec6e  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000ec73  lea     rdx, aTimeout; "Timeout"
0x18000ec7a  lea     rax, [rsp+270h+Data]
0x18000ec7f  mov     [rsp+270h+cbData], 4
0x18000ec87  xor     r9d, r9d; lpType
0x18000ec8a  mov     [rsp+270h+phkResult], rax; lpData
0x18000ec8f  xor     r8d, r8d; lpReserved
0x18000ec92  call    cs:__imp_RegQueryValueExW
0x18000ec98  mov     rcx, [rsp+270h+hKey]; hKey
0x18000ec9d  call    cs:__imp_RegCloseKey
0x18000eca3  mov     eax, dword ptr [rsp+270h+Data]
0x18000eca7  mov     [rdi+14h], eax
0x18000ecaa  mov     rcx, [rbp+170h+var_20]
0x18000ecb1  xor     rcx, rsp; StackCookie
0x18000ecb4  call    __security_check_cookie
0x18000ecb9  add     rsp, 260h
0x18000ecc0  pop     rdi
0x18000ecc1  pop     rbx
0x18000ecc2  pop     rbp
0x18000ecc3  retn
```
