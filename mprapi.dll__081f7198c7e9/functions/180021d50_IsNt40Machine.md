# IsNt40Machine

- ea: `0x180021d50`
- end: `0x180021e32`
- name: `IsNt40Machine`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009958`
- `0x180017700`

## callees

- `0x180021d50`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021e11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021e11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021db4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021db4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021de6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021de6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180021dfc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180021dfc`

## pseudocode

```c
LSTATUS __fastcall IsNt40Machine(HKEY a1, _DWORD *a2)
{
  LSTATUS result; // eax
  DWORD cbData; // [rsp+30h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+34h] [rbp-A4h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-A0h] BYREF
  WCHAR Data[64]; // [rsp+40h] [rbp-98h] BYREF

  Type = 1;
  cbData = 128;
  hKey = 0;
  if ( !a2 )
    return 87;
  *a2 = 0;
  result = RegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey);
  if ( !result )
  {
    if ( !RegQueryValueExW(hKey, L"CurrentBuildNumber", 0, &Type, (LPBYTE)Data, &cbData) && !lstrcmpW(Data, L"1381") )
      *a2 = 1;
    RegCloseKey(hKey);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180021d50  push    rbx
0x180021d52  sub     rsp, 0D0h
0x180021d59  mov     rax, cs:__security_cookie
0x180021d60  xor     rax, rsp
0x180021d63  mov     [rsp+0D8h+var_18], rax
0x180021d6b  mov     [rsp+0D8h+Type], 1
0x180021d73  mov     rbx, rdx
0x180021d76  mov     [rsp+0D8h+cbData], 80h
0x180021d7e  mov     [rsp+0D8h+hKey], 0
0x180021d87  test    rdx, rdx
0x180021d8a  jnz     short loc_180021D94
0x180021d8c  lea     eax, [rdx+57h]
0x180021d8f  jmp     loc_180021E19
0x180021d94  mov     dword ptr [rdx], 0
0x180021d9a  lea     rax, [rsp+0D8h+hKey]
0x180021d9f  lea     rdx, c_szWinVersionPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180021da6  mov     [rsp+0D8h+phkResult], rax; phkResult
0x180021dab  mov     r9d, 20019h; samDesired
0x180021db1  xor     r8d, r8d; ulOptions
0x180021db4  call    cs:__imp_RegOpenKeyExW
0x180021dba  test    eax, eax
0x180021dbc  jnz     short loc_180021E19
0x180021dbe  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180021dc3  lea     rax, [rsp+0D8h+cbData]
0x180021dc8  mov     [rsp+0D8h+lpcbData], rax; lpcbData
0x180021dcd  lea     r9, [rsp+0D8h+Type]; lpType
0x180021dd2  lea     rax, [rsp+0D8h+Data]
0x180021dd7  xor     r8d, r8d; lpReserved
0x180021dda  lea     rdx, c_szCurrentBuildNumber; "CurrentBuildNumber"
0x180021de1  mov     [rsp+0D8h+phkResult], rax; lpData
0x180021de6  call    cs:__imp_RegQueryValueExW
0x180021dec  test    eax, eax
0x180021dee  jnz     short loc_180021E0C
0x180021df0  lea     rdx, c_szNt40BuildNumber; "1381"
0x180021df7  lea     rcx, [rsp+0D8h+Data]; lpString1
0x180021dfc  call    cs:__imp_lstrcmpW
0x180021e02  test    eax, eax
0x180021e04  jnz     short loc_180021E0C
0x180021e06  mov     dword ptr [rbx], 1
0x180021e0c  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180021e11  call    cs:__imp_RegCloseKey
0x180021e17  xor     eax, eax
0x180021e19  mov     rcx, [rsp+0D8h+var_18]
0x180021e21  xor     rcx, rsp; StackCookie
0x180021e24  call    __security_check_cookie
0x180021e29  add     rsp, 0D0h
0x180021e30  pop     rbx
0x180021e31  retn
```
