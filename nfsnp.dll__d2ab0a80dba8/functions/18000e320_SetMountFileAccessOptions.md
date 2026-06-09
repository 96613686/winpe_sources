# SetMountFileAccessOptions

- ea: `0x18000e320`
- end: `0x18000e44c`
- name: `SetMountFileAccessOptions`
- size: `300`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000be24`

## callees

- `0x18000e320`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000e3ad`
- `msvcrt!wcscat_s` at `0x18000e3ad`
- `msvcrt!wcsncpy_s` at `0x18000e399`
- `msvcrt!wcsncpy_s` at `0x18000e399`
- `ADVAPI32!RegCloseKey` at `0x18000e414`
- `ADVAPI32!RegCloseKey` at `0x18000e414`
- `ADVAPI32!RegQueryValueExW` at `0x18000e406`
- `ADVAPI32!RegQueryValueExW` at `0x18000e406`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e3ce`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e3ce`

## string_xrefs

- `0x18000e39f`: `\Mount`
- `0x18000e3e7`: `Access`

## pseudocode

```c
LSTATUS __fastcall SetMountFileAccessOptions(HKEY hKey, wchar_t *Source, __int64 a3)
{
  int v3; // esi
  LSTATUS v7; // r14d
  LSTATUS result; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Destination[264]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = 493;
  hKeya = 0;
  *(_DWORD *)Data = 493;
  cbData = 0;
  v7 = 13;
  memset_0(Destination, 0, 0x208u);
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  result = RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya);
  if ( !result )
  {
    cbData = 4;
    v7 = RegQueryValueExW(hKeya, L"Access", 0, 0, Data, &cbData);
    result = RegCloseKey(hKeya);
  }
  if ( !v7 )
    v3 = *(_DWORD *)Data;
  *(_DWORD *)(a3 + 32) = v3;
  return result;
}

```

## disassembly

```asm
0x18000e320  mov     [rsp-8+arg_18], rbx
0x18000e325  push    rbp
0x18000e326  push    rsi
0x18000e327  push    rdi
0x18000e328  push    r14
0x18000e32a  push    r15
0x18000e32c  lea     rbp, [rsp-160h]
0x18000e334  sub     rsp, 260h
0x18000e33b  mov     rax, cs:__security_cookie
0x18000e342  xor     rax, rsp
0x18000e345  mov     [rbp+180h+var_30], rax
0x18000e34c  mov     esi, 1EDh
0x18000e351  mov     [rsp+280h+hKey], 0
0x18000e35a  mov     r15, r8
0x18000e35d  mov     dword ptr [rsp+280h+Data], esi
0x18000e361  mov     rbx, rdx
0x18000e364  mov     [rsp+280h+cbData], 0
0x18000e36c  mov     rdi, rcx
0x18000e36f  xor     edx, edx; Val
0x18000e371  lea     r8d, [rsi+1Bh]; Size
0x18000e375  mov     r14d, 0Dh
0x18000e37b  lea     rcx, [rsp+280h+Destination]; void *
0x18000e380  call    memset_0
0x18000e385  mov     r9d, 103h; MaxCount
0x18000e38b  lea     rcx, [rsp+280h+Destination]; Destination
0x18000e390  mov     r8, rbx; Source
0x18000e393  lea     ebx, [r9+1]
0x18000e397  mov     edx, ebx; SizeInWords
0x18000e399  call    cs:__imp_wcsncpy_s
0x18000e39f  lea     r8, aMount; "\\Mount"
0x18000e3a6  mov     edx, ebx; SizeInWords
0x18000e3a8  lea     rcx, [rsp+280h+Destination]; Destination
0x18000e3ad  call    cs:__imp_wcscat_s
0x18000e3b3  lea     rax, [rsp+280h+hKey]
0x18000e3b8  mov     r9d, 20019h; samDesired
0x18000e3be  xor     r8d, r8d; ulOptions
0x18000e3c1  mov     [rsp+280h+phkResult], rax; phkResult
0x18000e3c6  lea     rdx, [rsp+280h+Destination]; lpSubKey
0x18000e3cb  mov     rcx, rdi; hKey
0x18000e3ce  call    cs:__imp_RegOpenKeyExW
0x18000e3d4  test    eax, eax
0x18000e3d6  jnz     short loc_18000E41A
0x18000e3d8  mov     rcx, [rsp+280h+hKey]; hKey
0x18000e3dd  lea     rax, [rsp+280h+cbData]
0x18000e3e2  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000e3e7  lea     rdx, aAccess; "Access"
0x18000e3ee  lea     rax, [rsp+280h+Data]
0x18000e3f3  mov     [rsp+280h+cbData], 4
0x18000e3fb  xor     r9d, r9d; lpType
0x18000e3fe  mov     [rsp+280h+phkResult], rax; lpData
0x18000e403  xor     r8d, r8d; lpReserved
0x18000e406  call    cs:__imp_RegQueryValueExW
0x18000e40c  mov     rcx, [rsp+280h+hKey]; hKey
0x18000e411  mov     r14d, eax
0x18000e414  call    cs:__imp_RegCloseKey
0x18000e41a  test    r14d, r14d
0x18000e41d  cmovz   esi, dword ptr [rsp+280h+Data]
0x18000e422  mov     [r15+20h], esi
0x18000e426  mov     rcx, [rbp+180h+var_30]
0x18000e42d  xor     rcx, rsp; StackCookie
0x18000e430  call    __security_check_cookie
0x18000e435  mov     rbx, [rsp+280h+arg_18]
0x18000e43d  add     rsp, 260h
0x18000e444  pop     r15
0x18000e446  pop     r14
0x18000e448  pop     rdi
0x18000e449  pop     rsi
0x18000e44a  pop     rbp
0x18000e44b  retn
```
