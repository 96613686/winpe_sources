# SetMountFileAccessOptions

- ea: `0x18000f074`
- end: `0x18000f1bf`
- name: `SetMountFileAccessOptions`
- size: `331`
- prototype: `LSTATUS __fastcall(HKEY hKey, wchar_t *Source, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c738`

## callees

- `0x18000f074`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f107`
- `msvcrt!wcscat_s` at `0x18000f107`
- `msvcrt!wcsncpy_s` at `0x18000f0ed`
- `msvcrt!wcsncpy_s` at `0x18000f0ed`
- `ADVAPI32!RegCloseKey` at `0x18000f180`
- `ADVAPI32!RegCloseKey` at `0x18000f180`
- `ADVAPI32!RegQueryValueExW` at `0x18000f16c`
- `ADVAPI32!RegQueryValueExW` at `0x18000f16c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f12e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f12e`

## string_xrefs

- `0x18000f0f9`: `\Mount`
- `0x18000f14d`: `Access`

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
0x18000f074  mov     [rsp-8+arg_18], rbx
0x18000f079  push    rbp
0x18000f07a  push    rsi
0x18000f07b  push    rdi
0x18000f07c  push    r14
0x18000f07e  push    r15
0x18000f080  lea     rbp, [rsp-160h]
0x18000f088  sub     rsp, 260h
0x18000f08f  mov     rax, cs:__security_cookie
0x18000f096  xor     rax, rsp
0x18000f099  mov     [rbp+180h+var_30], rax
0x18000f0a0  mov     esi, 1EDh
0x18000f0a5  mov     [rsp+280h+hKey], 0
0x18000f0ae  mov     r15, r8
0x18000f0b1  mov     dword ptr [rsp+280h+Data], esi
0x18000f0b5  mov     rbx, rdx
0x18000f0b8  mov     [rsp+280h+cbData], 0
0x18000f0c0  mov     rdi, rcx
0x18000f0c3  xor     edx, edx; Val
0x18000f0c5  lea     r8d, [rsi+1Bh]; Size
0x18000f0c9  mov     r14d, 0Dh
0x18000f0cf  lea     rcx, [rsp+280h+Destination]; void *
0x18000f0d4  call    memset_0
0x18000f0d9  mov     r9d, 103h; MaxCount
0x18000f0df  lea     rcx, [rsp+280h+Destination]; Destination
0x18000f0e4  mov     r8, rbx; Source
0x18000f0e7  lea     ebx, [r9+1]
0x18000f0eb  mov     edx, ebx; SizeInWords
0x18000f0ed  call    cs:__imp_wcsncpy_s
0x18000f0f4  nop     dword ptr [rax+rax+00h]
0x18000f0f9  lea     r8, aMount; "\\Mount"
0x18000f100  mov     edx, ebx; SizeInWords
0x18000f102  lea     rcx, [rsp+280h+Destination]; Destination
0x18000f107  call    cs:__imp_wcscat_s
0x18000f10e  nop     dword ptr [rax+rax+00h]
0x18000f113  lea     rax, [rsp+280h+hKey]
0x18000f118  mov     r9d, 20019h; samDesired
0x18000f11e  xor     r8d, r8d; ulOptions
0x18000f121  mov     [rsp+280h+phkResult], rax; phkResult
0x18000f126  lea     rdx, [rsp+280h+Destination]; lpSubKey
0x18000f12b  mov     rcx, rdi; hKey
0x18000f12e  call    cs:__imp_RegOpenKeyExW
0x18000f135  nop     dword ptr [rax+rax+00h]
0x18000f13a  test    eax, eax
0x18000f13c  jnz     short loc_18000F18C
0x18000f13e  mov     rcx, [rsp+280h+hKey]; hKey
0x18000f143  lea     rax, [rsp+280h+cbData]
0x18000f148  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000f14d  lea     rdx, aAccess; "Access"
0x18000f154  lea     rax, [rsp+280h+Data]
0x18000f159  mov     [rsp+280h+cbData], 4
0x18000f161  xor     r9d, r9d; lpType
0x18000f164  mov     [rsp+280h+phkResult], rax; lpData
0x18000f169  xor     r8d, r8d; lpReserved
0x18000f16c  call    cs:__imp_RegQueryValueExW
0x18000f173  nop     dword ptr [rax+rax+00h]
0x18000f178  mov     rcx, [rsp+280h+hKey]; hKey
0x18000f17d  mov     r14d, eax
0x18000f180  call    cs:__imp_RegCloseKey
0x18000f187  nop     dword ptr [rax+rax+00h]
0x18000f18c  test    r14d, r14d
0x18000f18f  cmovz   esi, dword ptr [rsp+280h+Data]
0x18000f194  mov     [r15+20h], esi
0x18000f198  mov     rcx, [rbp+180h+var_30]
0x18000f19f  xor     rcx, rsp; StackCookie
0x18000f1a2  call    __security_check_cookie
0x18000f1a7  mov     rbx, [rsp+280h+arg_18]
0x18000f1af  add     rsp, 260h
0x18000f1b6  pop     r15
0x18000f1b8  pop     r14
0x18000f1ba  pop     rdi
0x18000f1bb  pop     rsi
0x18000f1bc  pop     rbp
0x18000f1bd  retn
```
