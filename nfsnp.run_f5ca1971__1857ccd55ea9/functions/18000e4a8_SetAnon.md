# SetAnon

- ea: `0x18000e4a8`
- end: `0x18000e5ec`
- name: `SetAnon`
- size: `324`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c738`
- `0x18000f1c8`

## callees

- `0x18000e4a8`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000e532`
- `msvcrt!wcscat_s` at `0x18000e532`
- `msvcrt!wcsncpy_s` at `0x18000e518`
- `msvcrt!wcsncpy_s` at `0x18000e518`
- `ADVAPI32!RegCloseKey` at `0x18000e5a8`
- `ADVAPI32!RegCloseKey` at `0x18000e5a8`
- `ADVAPI32!RegQueryValueExW` at `0x18000e597`
- `ADVAPI32!RegQueryValueExW` at `0x18000e597`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e559`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e559`

## string_xrefs

- `0x18000e578`: `MountAsAnonymousUser`
- `0x18000e524`: `\Mount`

## pseudocode

```c
__int64 __fastcall SetAnon(HKEY hKey, wchar_t *Source, __int64 a3)
{
  int v6; // eax
  __int64 result; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  memset_0(Destination, 0, 0x208u);
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    cbData = 4;
    RegQueryValueExW(hKeya, L"MountAsAnonymousUser", 0, 0, Data, &cbData);
    RegCloseKey(hKeya);
  }
  v6 = *(_DWORD *)(a3 + 56);
  if ( *(_DWORD *)Data )
    result = v6 | 2u;
  else
    result = v6 & 0xFFFFFFFD;
  *(_DWORD *)(a3 + 56) = result;
  return result;
}

```

## disassembly

```asm
0x18000e4a8  mov     [rsp-8+arg_18], rbx
0x18000e4ad  push    rbp
0x18000e4ae  push    rsi
0x18000e4af  push    rdi
0x18000e4b0  lea     rbp, [rsp-160h]
0x18000e4b8  sub     rsp, 260h
0x18000e4bf  mov     rax, cs:__security_cookie
0x18000e4c6  xor     rax, rsp
0x18000e4c9  mov     [rbp+170h+var_20], rax
0x18000e4d0  mov     rsi, r8
0x18000e4d3  mov     [rsp+270h+hKey], 0
0x18000e4dc  mov     rbx, rdx
0x18000e4df  mov     [rsp+270h+cbData], 0
0x18000e4e7  mov     rdi, rcx
0x18000e4ea  mov     dword ptr [rsp+270h+Data], 0
0x18000e4f2  xor     edx, edx; Val
0x18000e4f4  lea     rcx, [rsp+270h+Destination]; void *
0x18000e4f9  mov     r8d, 208h; Size
0x18000e4ff  call    memset_0
0x18000e504  mov     r9d, 103h; MaxCount
0x18000e50a  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e50f  mov     r8, rbx; Source
0x18000e512  lea     ebx, [r9+1]
0x18000e516  mov     edx, ebx; SizeInWords
0x18000e518  call    cs:__imp_wcsncpy_s
0x18000e51f  nop     dword ptr [rax+rax+00h]
0x18000e524  lea     r8, aMount; "\\Mount"
0x18000e52b  mov     edx, ebx; SizeInWords
0x18000e52d  lea     rcx, [rsp+270h+Destination]; Destination
0x18000e532  call    cs:__imp_wcscat_s
0x18000e539  nop     dword ptr [rax+rax+00h]
0x18000e53e  lea     rax, [rsp+270h+hKey]
0x18000e543  mov     r9d, 20019h; samDesired
0x18000e549  xor     r8d, r8d; ulOptions
0x18000e54c  mov     [rsp+270h+phkResult], rax; phkResult
0x18000e551  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000e556  mov     rcx, rdi; hKey
0x18000e559  call    cs:__imp_RegOpenKeyExW
0x18000e560  nop     dword ptr [rax+rax+00h]
0x18000e565  test    eax, eax
0x18000e567  jnz     short loc_18000E5B4
0x18000e569  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e56e  lea     rax, [rsp+270h+cbData]
0x18000e573  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000e578  lea     rdx, aMountasanonymo; "MountAsAnonymousUser"
0x18000e57f  lea     rax, [rsp+270h+Data]
0x18000e584  mov     [rsp+270h+cbData], 4
0x18000e58c  xor     r9d, r9d; lpType
0x18000e58f  mov     [rsp+270h+phkResult], rax; lpData
0x18000e594  xor     r8d, r8d; lpReserved
0x18000e597  call    cs:__imp_RegQueryValueExW
0x18000e59e  nop     dword ptr [rax+rax+00h]
0x18000e5a3  mov     rcx, [rsp+270h+hKey]; hKey
0x18000e5a8  call    cs:__imp_RegCloseKey
0x18000e5af  nop     dword ptr [rax+rax+00h]
0x18000e5b4  cmp     dword ptr [rsp+270h+Data], 0
0x18000e5b9  mov     eax, [rsi+38h]
0x18000e5bc  jz      short loc_18000E5C3
0x18000e5be  or      eax, 2
0x18000e5c1  jmp     short loc_18000E5C6
0x18000e5c3  and     eax, 0FFFFFFFDh
0x18000e5c6  mov     [rsi+38h], eax
0x18000e5c9  mov     rcx, [rbp+170h+var_20]
0x18000e5d0  xor     rcx, rsp; StackCookie
0x18000e5d3  call    __security_check_cookie
0x18000e5d8  mov     rbx, [rsp+270h+arg_18]
0x18000e5e0  add     rsp, 260h
0x18000e5e7  pop     rdi
0x18000e5e8  pop     rsi
0x18000e5e9  pop     rbp
0x18000e5ea  retn
```
