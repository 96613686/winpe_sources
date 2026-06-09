# SetRetrans

- ea: `0x18000f64c`
- end: `0x18000f76b`
- name: `SetRetrans`
- size: `287`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000f64c`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f6c7`
- `msvcrt!wcscat_s` at `0x18000f6c7`
- `msvcrt!wcsncpy_s` at `0x18000f6aa`
- `msvcrt!wcsncpy_s` at `0x18000f6aa`
- `ADVAPI32!RegCloseKey` at `0x18000f73d`
- `ADVAPI32!RegCloseKey` at `0x18000f73d`
- `ADVAPI32!RegQueryValueExW` at `0x18000f72c`
- `ADVAPI32!RegQueryValueExW` at `0x18000f72c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f6ee`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f6ee`

## string_xrefs

- `0x18000f6b6`: `\Mount`

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
0x18000f64c  push    rbp
0x18000f64e  push    rbx
0x18000f64f  push    rdi
0x18000f650  lea     rbp, [rsp-160h]
0x18000f658  sub     rsp, 260h
0x18000f65f  mov     rax, cs:__security_cookie
0x18000f666  xor     rax, rsp
0x18000f669  mov     [rbp+170h+var_20], rax
0x18000f670  mov     r9d, 103h; MaxCount
0x18000f676  mov     [rsp+270h+hKey], 0
0x18000f67f  mov     rdi, r8
0x18000f682  mov     dword ptr [rsp+270h+Data], 5
0x18000f68a  mov     rbx, rcx
0x18000f68d  mov     [rsp+270h+cbData], 0
0x18000f695  xor     eax, eax
0x18000f697  lea     rcx, [rsp+270h+Destination]; Destination
0x18000f69c  mov     r8, rdx; Source
0x18000f69f  mov     [rbp+170h+var_2A], ax
0x18000f6a6  lea     edx, [r9+1]; SizeInWords
0x18000f6aa  call    cs:__imp_wcsncpy_s
0x18000f6b1  nop     dword ptr [rax+rax+00h]
0x18000f6b6  lea     r8, aMount; "\\Mount"
0x18000f6bd  mov     edx, 104h; SizeInWords
0x18000f6c2  lea     rcx, [rsp+270h+Destination]; Destination
0x18000f6c7  call    cs:__imp_wcscat_s
0x18000f6ce  nop     dword ptr [rax+rax+00h]
0x18000f6d3  lea     rax, [rsp+270h+hKey]
0x18000f6d8  mov     r9d, 20019h; samDesired
0x18000f6de  xor     r8d, r8d; ulOptions
0x18000f6e1  mov     [rsp+270h+phkResult], rax; phkResult
0x18000f6e6  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000f6eb  mov     rcx, rbx; hKey
0x18000f6ee  call    cs:__imp_RegOpenKeyExW
0x18000f6f5  nop     dword ptr [rax+rax+00h]
0x18000f6fa  test    eax, eax
0x18000f6fc  jnz     short loc_18000F749
0x18000f6fe  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f703  lea     rax, [rsp+270h+cbData]
0x18000f708  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000f70d  lea     rdx, aRetransmission; "Retransmissions"
0x18000f714  lea     rax, [rsp+270h+Data]
0x18000f719  mov     [rsp+270h+cbData], 4
0x18000f721  xor     r9d, r9d; lpType
0x18000f724  mov     [rsp+270h+phkResult], rax; lpData
0x18000f729  xor     r8d, r8d; lpReserved
0x18000f72c  call    cs:__imp_RegQueryValueExW
0x18000f733  nop     dword ptr [rax+rax+00h]
0x18000f738  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f73d  call    cs:__imp_RegCloseKey
0x18000f744  nop     dword ptr [rax+rax+00h]
0x18000f749  mov     eax, dword ptr [rsp+270h+Data]
0x18000f74d  mov     [rdi+18h], eax
0x18000f750  mov     rcx, [rbp+170h+var_20]
0x18000f757  xor     rcx, rsp; StackCookie
0x18000f75a  call    __security_check_cookie
0x18000f75f  add     rsp, 260h
0x18000f766  pop     rdi
0x18000f767  pop     rbx
0x18000f768  pop     rbp
0x18000f769  retn
```
