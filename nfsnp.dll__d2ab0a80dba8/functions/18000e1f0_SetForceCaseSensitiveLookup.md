# SetForceCaseSensitiveLookup

- ea: `0x18000e1f0`
- end: `0x18000e317`
- name: `SetForceCaseSensitiveLookup`
- size: `295`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000be24`

## callees

- `0x18000e1f0`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000e274`
- `msvcrt!wcscat_s` at `0x18000e274`
- `msvcrt!wcsncpy_s` at `0x18000e260`
- `msvcrt!wcsncpy_s` at `0x18000e260`
- `ADVAPI32!RegCloseKey` at `0x18000e2d8`
- `ADVAPI32!RegCloseKey` at `0x18000e2d8`
- `ADVAPI32!RegQueryValueExW` at `0x18000e2cd`
- `ADVAPI32!RegQueryValueExW` at `0x18000e2cd`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e295`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e295`

## string_xrefs

- `0x18000e266`: `\Mount`
- `0x18000e2ae`: `NFSReaddir`

## pseudocode

```c
unsigned int __fastcall SetForceCaseSensitiveLookup(HKEY hKey, wchar_t *Source, __int64 a3)
{
  int v6; // eax
  unsigned int result; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  cbData = 0;
  *(_DWORD *)Data = 1;
  memset_0(Destination, 0, 0x208u);
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    cbData = 4;
    RegQueryValueExW(hKeya, L"NFSReaddir", 0, 0, Data, &cbData);
    RegCloseKey(hKeya);
  }
  v6 = *(_DWORD *)(a3 + 56);
  if ( *(_DWORD *)Data )
    result = v6 | 0x100;
  else
    result = v6 & 0xFFFFFEFF;
  *(_DWORD *)(a3 + 56) = result;
  return result;
}

```

## disassembly

```asm
0x18000e1f0  mov     [rsp-8+arg_18], rbx
0x18000e1f5  push    rbp
0x18000e1f6  push    rsi
0x18000e1f7  push    rdi
0x18000e1f8  lea     rbp, [rsp-160h]
0x18000e200  sub     rsp, 260h
0x18000e207  mov     rax, cs:__security_cookie
0x18000e20e  xor     rax, rsp
0x18000e211  mov     [rbp+170h+var_20], rax
0x18000e218  mov     rsi, r8
0x18000e21b  mov     [rsp+270h+hKey], 0
0x18000e224  mov     rbx, rdx
0x18000e227  mov     [rsp+270h+cbData], 0
0x18000e22f  mov     rdi, rcx
0x18000e232  mov     dword ptr [rsp+270h+Data], 1
0x18000e23a  xor     edx, edx; Val
0x18000e23c  lea     rcx, [rsp+270h+Destination]; void *
0x18000e241  mov     r8d, 208h; Size
0x18000e247  call    memset_0
0x18000e24c  mov     r9d, 103h; MaxCount
0x18000e252  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e257  mov     r8, rbx; Source
0x18000e25a  lea     ebx, [r9+1]
0x18000e25e  mov     edx, ebx; SizeInWords
0x18000e260  call    cs:__imp_wcsncpy_s
0x18000e266  lea     r8, aMount; "\\Mount"
0x18000e26d  mov     edx, ebx; SizeInWords
0x18000e26f  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e274  call    cs:__imp_wcscat_s
0x18000e27a  lea     rax, [rsp+270h+hKey]
0x18000e27f  mov     r9d, 20019h; samDesired
0x18000e285  xor     r8d, r8d; ulOptions
0x18000e288  mov     [rsp+270h+phkResult], rax; phkResult
0x18000e28d  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000e292  mov     rcx, rdi; hKey
0x18000e295  call    cs:__imp_RegOpenKeyExW
0x18000e29b  test    eax, eax
0x18000e29d  jnz     short loc_18000E2DE
0x18000e29f  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e2a4  lea     rax, [rsp+270h+cbData]
0x18000e2a9  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000e2ae  lea     rdx, aNfsreaddir; "NFSReaddir"
0x18000e2b5  lea     rax, [rsp+270h+Data]
0x18000e2ba  mov     [rsp+270h+cbData], 4
0x18000e2c2  xor     r9d, r9d; lpType
0x18000e2c5  mov     [rsp+270h+phkResult], rax; lpData
0x18000e2ca  xor     r8d, r8d; lpReserved
0x18000e2cd  call    cs:__imp_RegQueryValueExW
0x18000e2d3  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e2d8  call    cs:__imp_RegCloseKey
0x18000e2de  cmp     dword ptr [rsp+270h+Data], 0
0x18000e2e3  mov     eax, [rsi+38h]
0x18000e2e6  jz      short loc_18000E2EE
0x18000e2e8  bts     eax, 8
0x18000e2ec  jmp     short loc_18000E2F2
0x18000e2ee  btr     eax, 8
0x18000e2f2  mov     [rsi+38h], eax
0x18000e2f5  mov     rcx, [rbp+170h+var_20]
0x18000e2fc  xor     rcx, rsp; StackCookie
0x18000e2ff  call    __security_check_cookie
0x18000e304  mov     rbx, [rsp+270h+arg_18]
0x18000e30c  add     rsp, 260h
0x18000e313  pop     rdi
0x18000e314  pop     rsi
0x18000e315  pop     rbp
0x18000e316  retn
```
