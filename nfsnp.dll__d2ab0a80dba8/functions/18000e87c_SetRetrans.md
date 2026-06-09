# SetRetrans

- ea: `0x18000e87c`
- end: `0x18000e97c`
- name: `SetRetrans`
- size: `256`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000be24`
- `0x18000e454`

## callees

- `0x18000e87c`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000e8f1`
- `msvcrt!wcscat_s` at `0x18000e8f1`
- `msvcrt!wcsncpy_s` at `0x18000e8da`
- `msvcrt!wcsncpy_s` at `0x18000e8da`
- `ADVAPI32!RegCloseKey` at `0x18000e955`
- `ADVAPI32!RegCloseKey` at `0x18000e955`
- `ADVAPI32!RegQueryValueExW` at `0x18000e94a`
- `ADVAPI32!RegQueryValueExW` at `0x18000e94a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e912`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e912`

## string_xrefs

- `0x18000e8e0`: `\Mount`

## pseudocode

```c
__int64 __fastcall SetRetrans(HKEY hKey, wchar_t *Source, __int64 a3)
{
  __int64 result; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  *(_DWORD *)Data = 5;
  cbData = 0;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    cbData = 4;
    RegQueryValueExW(hKeya, L"Retransmissions", 0, 0, Data, &cbData);
    RegCloseKey(hKeya);
  }
  result = *(unsigned int *)Data;
  *(_DWORD *)(a3 + 24) = *(_DWORD *)Data;
  return result;
}

```

## disassembly

```asm
0x18000e87c  push    rbp
0x18000e87e  push    rbx
0x18000e87f  push    rdi
0x18000e880  lea     rbp, [rsp-160h]
0x18000e888  sub     rsp, 260h
0x18000e88f  mov     rax, cs:__security_cookie
0x18000e896  xor     rax, rsp
0x18000e899  mov     [rbp+170h+var_20], rax
0x18000e8a0  mov     r9d, 103h; MaxCount
0x18000e8a6  mov     [rsp+270h+hKey], 0
0x18000e8af  mov     rdi, r8
0x18000e8b2  mov     dword ptr [rsp+270h+Data], 5
0x18000e8ba  mov     rbx, rcx
0x18000e8bd  mov     [rsp+270h+cbData], 0
0x18000e8c5  xor     eax, eax
0x18000e8c7  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e8cc  mov     r8, rdx; Source
0x18000e8cf  mov     [rbp+170h+var_2A], ax
0x18000e8d6  lea     edx, [r9+1]; SizeInWords
0x18000e8da  call    cs:__imp_wcsncpy_s
0x18000e8e0  lea     r8, aMount; "\\Mount"
0x18000e8e7  mov     edx, 104h; SizeInWords
0x18000e8ec  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e8f1  call    cs:__imp_wcscat_s
0x18000e8f7  lea     rax, [rsp+270h+hKey]
0x18000e8fc  mov     r9d, 20019h; samDesired
0x18000e902  xor     r8d, r8d; ulOptions
0x18000e905  mov     [rsp+270h+phkResult], rax; phkResult
0x18000e90a  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000e90f  mov     rcx, rbx; hKey
0x18000e912  call    cs:__imp_RegOpenKeyExW
0x18000e918  test    eax, eax
0x18000e91a  jnz     short loc_18000E95B
0x18000e91c  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e921  lea     rax, [rsp+270h+cbData]
0x18000e926  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000e92b  lea     rdx, aRetransmission; "Retransmissions"
0x18000e932  lea     rax, [rsp+270h+Data]
0x18000e937  mov     [rsp+270h+cbData], 4
0x18000e93f  xor     r9d, r9d; lpType
0x18000e942  mov     [rsp+270h+phkResult], rax; lpData
0x18000e947  xor     r8d, r8d; lpReserved
0x18000e94a  call    cs:__imp_RegQueryValueExW
0x18000e950  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e955  call    cs:__imp_RegCloseKey
0x18000e95b  mov     eax, dword ptr [rsp+270h+Data]
0x18000e95f  mov     [rdi+18h], eax
0x18000e962  mov     rcx, [rbp+170h+var_20]
0x18000e969  xor     rcx, rsp; StackCookie
0x18000e96c  call    __security_check_cookie
0x18000e971  add     rsp, 260h
0x18000e978  pop     rdi
0x18000e979  pop     rbx
0x18000e97a  pop     rbp
0x18000e97b  retn
```
