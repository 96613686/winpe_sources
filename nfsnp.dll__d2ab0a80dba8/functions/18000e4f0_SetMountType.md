# SetMountType

- ea: `0x18000e4f0`
- end: `0x18000e5eb`
- name: `SetMountType`
- size: `251`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000be24`
- `0x18000e454`

## callees

- `0x18000e4f0`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000e565`
- `msvcrt!wcscat_s` at `0x18000e565`
- `msvcrt!wcsncpy_s` at `0x18000e54e`
- `msvcrt!wcsncpy_s` at `0x18000e54e`
- `ADVAPI32!RegCloseKey` at `0x18000e5c1`
- `ADVAPI32!RegCloseKey` at `0x18000e5c1`
- `ADVAPI32!RegQueryValueExW` at `0x18000e5b6`
- `ADVAPI32!RegQueryValueExW` at `0x18000e5b6`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e586`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e586`

## string_xrefs

- `0x18000e554`: `\Mount`
- `0x18000e59f`: `MountType`

## pseudocode

```c
__int64 __fastcall SetMountType(HKEY hKey, wchar_t *Source, __int64 a3)
{
  __int64 result; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 1;
  cbData = 4;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    RegQueryValueExW(hKeya, L"MountType", 0, 0, Data, &cbData);
    RegCloseKey(hKeya);
  }
  result = *(unsigned int *)Data;
  *(_DWORD *)(*(_QWORD *)a3 + 28LL) = *(_DWORD *)Data;
  return result;
}

```

## disassembly

```asm
0x18000e4f0  push    rbp
0x18000e4f2  push    rbx
0x18000e4f3  push    rdi
0x18000e4f4  lea     rbp, [rsp-160h]
0x18000e4fc  sub     rsp, 260h
0x18000e503  mov     rax, cs:__security_cookie
0x18000e50a  xor     rax, rsp
0x18000e50d  mov     [rbp+170h+var_20], rax
0x18000e514  mov     r9d, 103h; MaxCount
0x18000e51a  mov     [rsp+270h+hKey], 0
0x18000e523  mov     rdi, r8
0x18000e526  mov     dword ptr [rsp+270h+Data], 1
0x18000e52e  mov     rbx, rcx
0x18000e531  mov     [rsp+270h+cbData], 4
0x18000e539  xor     eax, eax
0x18000e53b  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e540  mov     r8, rdx; Source
0x18000e543  mov     [rbp+170h+var_2A], ax
0x18000e54a  lea     edx, [r9+1]; SizeInWords
0x18000e54e  call    cs:__imp_wcsncpy_s
0x18000e554  lea     r8, aMount; "\\Mount"
0x18000e55b  mov     edx, 104h; SizeInWords
0x18000e560  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e565  call    cs:__imp_wcscat_s
0x18000e56b  lea     rax, [rsp+270h+hKey]
0x18000e570  mov     r9d, 20019h; samDesired
0x18000e576  xor     r8d, r8d; ulOptions
0x18000e579  mov     [rsp+270h+phkResult], rax; phkResult
0x18000e57e  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000e583  mov     rcx, rbx; hKey
0x18000e586  call    cs:__imp_RegOpenKeyExW
0x18000e58c  test    eax, eax
0x18000e58e  jnz     short loc_18000E5C7
0x18000e590  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e595  lea     rax, [rsp+270h+cbData]
0x18000e59a  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000e59f  lea     rdx, aMounttype; "MountType"
0x18000e5a6  lea     rax, [rsp+270h+Data]
0x18000e5ab  xor     r9d, r9d; lpType
0x18000e5ae  xor     r8d, r8d; lpReserved
0x18000e5b1  mov     [rsp+270h+phkResult], rax; lpData
0x18000e5b6  call    cs:__imp_RegQueryValueExW
0x18000e5bc  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e5c1  call    cs:__imp_RegCloseKey
0x18000e5c7  mov     rcx, [rdi]
0x18000e5ca  mov     eax, dword ptr [rsp+270h+Data]
0x18000e5ce  mov     [rcx+1Ch], eax
0x18000e5d1  mov     rcx, [rbp+170h+var_20]
0x18000e5d8  xor     rcx, rsp; StackCookie
0x18000e5db  call    __security_check_cookie
0x18000e5e0  add     rsp, 260h
0x18000e5e7  pop     rdi
0x18000e5e8  pop     rbx
0x18000e5e9  pop     rbp
0x18000e5ea  retn
```
