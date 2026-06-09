# SetTimeout

- ea: `0x18000f9f4`
- end: `0x18000fb13`
- name: `SetTimeout`
- size: `287`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000f9f4`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000fa6f`
- `msvcrt!wcscat_s` at `0x18000fa6f`
- `msvcrt!wcsncpy_s` at `0x18000fa52`
- `msvcrt!wcsncpy_s` at `0x18000fa52`
- `ADVAPI32!RegCloseKey` at `0x18000fae5`
- `ADVAPI32!RegCloseKey` at `0x18000fae5`
- `ADVAPI32!RegQueryValueExW` at `0x18000fad4`
- `ADVAPI32!RegQueryValueExW` at `0x18000fad4`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fa96`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fa96`

## string_xrefs

- `0x18000fa5e`: `\Mount`

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
0x18000f9f4  push    rbp
0x18000f9f6  push    rbx
0x18000f9f7  push    rdi
0x18000f9f8  lea     rbp, [rsp-160h]
0x18000fa00  sub     rsp, 260h
0x18000fa07  mov     rax, cs:__security_cookie
0x18000fa0e  xor     rax, rsp
0x18000fa11  mov     [rbp+170h+var_20], rax
0x18000fa18  mov     r9d, 103h; MaxCount
0x18000fa1e  mov     [rsp+270h+hKey], 0
0x18000fa27  mov     rdi, r8
0x18000fa2a  mov     dword ptr [rsp+270h+Data], 8
0x18000fa32  mov     rbx, rcx
0x18000fa35  mov     [rsp+270h+cbData], 0
0x18000fa3d  xor     eax, eax
0x18000fa3f  lea     rcx, [rsp+270h+Destination]; Destination
0x18000fa44  mov     r8, rdx; Source
0x18000fa47  mov     [rbp+170h+var_2A], ax
0x18000fa4e  lea     edx, [r9+1]; SizeInWords
0x18000fa52  call    cs:__imp_wcsncpy_s
0x18000fa59  nop     dword ptr [rax+rax+00h]
0x18000fa5e  lea     r8, aMount; "\\Mount"
0x18000fa65  mov     edx, 104h; SizeInWords
0x18000fa6a  lea     rcx, [rsp+270h+Destination]; Destination
0x18000fa6f  call    cs:__imp_wcscat_s
0x18000fa76  nop     dword ptr [rax+rax+00h]
0x18000fa7b  lea     rax, [rsp+270h+hKey]
0x18000fa80  mov     r9d, 20019h; samDesired
0x18000fa86  xor     r8d, r8d; ulOptions
0x18000fa89  mov     [rsp+270h+phkResult], rax; phkResult
0x18000fa8e  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000fa93  mov     rcx, rbx; hKey
0x18000fa96  call    cs:__imp_RegOpenKeyExW
0x18000fa9d  nop     dword ptr [rax+rax+00h]
0x18000faa2  test    eax, eax
0x18000faa4  jnz     short loc_18000FAF1
0x18000faa6  mov     rcx, [rsp+270h+hKey]; hKey
0x18000faab  lea     rax, [rsp+270h+cbData]
0x18000fab0  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000fab5  lea     rdx, aTimeout; "Timeout"
0x18000fabc  lea     rax, [rsp+270h+Data]
0x18000fac1  mov     [rsp+270h+cbData], 4
0x18000fac9  xor     r9d, r9d; lpType
0x18000facc  mov     [rsp+270h+phkResult], rax; lpData
0x18000fad1  xor     r8d, r8d; lpReserved
0x18000fad4  call    cs:__imp_RegQueryValueExW
0x18000fadb  nop     dword ptr [rax+rax+00h]
0x18000fae0  mov     rcx, [rsp+270h+hKey]; hKey
0x18000fae5  call    cs:__imp_RegCloseKey
0x18000faec  nop     dword ptr [rax+rax+00h]
0x18000faf1  mov     eax, dword ptr [rsp+270h+Data]
0x18000faf5  mov     [rdi+14h], eax
0x18000faf8  mov     rcx, [rbp+170h+var_20]
0x18000faff  xor     rcx, rsp; StackCookie
0x18000fb02  call    __security_check_cookie
0x18000fb07  add     rsp, 260h
0x18000fb0e  pop     rdi
0x18000fb0f  pop     rbx
0x18000fb10  pop     rbp
0x18000fb11  retn
```
