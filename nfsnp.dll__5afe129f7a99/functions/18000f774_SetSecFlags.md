# SetSecFlags

- ea: `0x18000f774`
- end: `0x18000f893`
- name: `SetSecFlags`
- size: `287`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000f774`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f7ef`
- `msvcrt!wcscat_s` at `0x18000f7ef`
- `msvcrt!wcsncpy_s` at `0x18000f7d2`
- `msvcrt!wcsncpy_s` at `0x18000f7d2`
- `ADVAPI32!RegCloseKey` at `0x18000f865`
- `ADVAPI32!RegCloseKey` at `0x18000f865`
- `ADVAPI32!RegQueryValueExW` at `0x18000f854`
- `ADVAPI32!RegQueryValueExW` at `0x18000f854`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f816`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f816`

## string_xrefs

- `0x18000f7de`: `\Mount`

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
0x18000f774  push    rbp
0x18000f776  push    rbx
0x18000f777  push    rdi
0x18000f778  lea     rbp, [rsp-160h]
0x18000f780  sub     rsp, 260h
0x18000f787  mov     rax, cs:__security_cookie
0x18000f78e  xor     rax, rsp
0x18000f791  mov     [rbp+170h+var_20], rax
0x18000f798  mov     r9d, 103h; MaxCount
0x18000f79e  mov     [rsp+270h+hKey], 0
0x18000f7a7  mov     rdi, r8
0x18000f7aa  mov     dword ptr [rsp+270h+Data], 0Fh
0x18000f7b2  mov     rbx, rcx
0x18000f7b5  mov     [rsp+270h+cbData], 0
0x18000f7bd  xor     eax, eax
0x18000f7bf  lea     rcx, [rsp+270h+Destination]; Destination
0x18000f7c4  mov     r8, rdx; Source
0x18000f7c7  mov     [rbp+170h+var_2A], ax
0x18000f7ce  lea     edx, [r9+1]; SizeInWords
0x18000f7d2  call    cs:__imp_wcsncpy_s
0x18000f7d9  nop     dword ptr [rax+rax+00h]
0x18000f7de  lea     r8, aMount; "\\Mount"
0x18000f7e5  mov     edx, 104h; SizeInWords
0x18000f7ea  lea     rcx, [rsp+270h+Destination]; Destination
0x18000f7ef  call    cs:__imp_wcscat_s
0x18000f7f6  nop     dword ptr [rax+rax+00h]
0x18000f7fb  lea     rax, [rsp+270h+hKey]
0x18000f800  mov     r9d, 20019h; samDesired
0x18000f806  xor     r8d, r8d; ulOptions
0x18000f809  mov     [rsp+270h+phkResult], rax; phkResult
0x18000f80e  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000f813  mov     rcx, rbx; hKey
0x18000f816  call    cs:__imp_RegOpenKeyExW
0x18000f81d  nop     dword ptr [rax+rax+00h]
0x18000f822  test    eax, eax
0x18000f824  jnz     short loc_18000F871
0x18000f826  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f82b  lea     rax, [rsp+270h+cbData]
0x18000f830  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000f835  lea     rdx, aSecflavors; "SecFlavors"
0x18000f83c  lea     rax, [rsp+270h+Data]
0x18000f841  mov     [rsp+270h+cbData], 4
0x18000f849  xor     r9d, r9d; lpType
0x18000f84c  mov     [rsp+270h+phkResult], rax; lpData
0x18000f851  xor     r8d, r8d; lpReserved
0x18000f854  call    cs:__imp_RegQueryValueExW
0x18000f85b  nop     dword ptr [rax+rax+00h]
0x18000f860  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f865  call    cs:__imp_RegCloseKey
0x18000f86c  nop     dword ptr [rax+rax+00h]
0x18000f871  mov     eax, dword ptr [rsp+270h+Data]
0x18000f875  mov     [rdi+3Ch], eax
0x18000f878  mov     rcx, [rbp+170h+var_20]
0x18000f87f  xor     rcx, rsp; StackCookie
0x18000f882  call    __security_check_cookie
0x18000f887  add     rsp, 260h
0x18000f88e  pop     rdi
0x18000f88f  pop     rbx
0x18000f890  pop     rbp
0x18000f891  retn
```
