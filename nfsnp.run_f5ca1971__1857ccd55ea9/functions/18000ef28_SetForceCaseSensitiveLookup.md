# SetForceCaseSensitiveLookup

- ea: `0x18000ef28`
- end: `0x18000f06e`
- name: `SetForceCaseSensitiveLookup`
- size: `326`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c738`

## callees

- `0x18000ef28`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000efb2`
- `msvcrt!wcscat_s` at `0x18000efb2`
- `msvcrt!wcsncpy_s` at `0x18000ef98`
- `msvcrt!wcsncpy_s` at `0x18000ef98`
- `ADVAPI32!RegCloseKey` at `0x18000f028`
- `ADVAPI32!RegCloseKey` at `0x18000f028`
- `ADVAPI32!RegQueryValueExW` at `0x18000f017`
- `ADVAPI32!RegQueryValueExW` at `0x18000f017`
- `ADVAPI32!RegOpenKeyExW` at `0x18000efd9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000efd9`

## string_xrefs

- `0x18000efa4`: `\Mount`
- `0x18000eff8`: `NFSReaddir`

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
0x18000ef28  mov     [rsp-8+arg_18], rbx
0x18000ef2d  push    rbp
0x18000ef2e  push    rsi
0x18000ef2f  push    rdi
0x18000ef30  lea     rbp, [rsp-160h]
0x18000ef38  sub     rsp, 260h
0x18000ef3f  mov     rax, cs:__security_cookie
0x18000ef46  xor     rax, rsp
0x18000ef49  mov     [rbp+170h+var_20], rax
0x18000ef50  mov     rsi, r8
0x18000ef53  mov     [rsp+270h+hKey], 0
0x18000ef5c  mov     rbx, rdx
0x18000ef5f  mov     [rsp+270h+cbData], 0
0x18000ef67  mov     rdi, rcx
0x18000ef6a  mov     dword ptr [rsp+270h+Data], 1
0x18000ef72  xor     edx, edx; Val
0x18000ef74  lea     rcx, [rsp+270h+Destination]; void *
0x18000ef79  mov     r8d, 208h; Size
0x18000ef7f  call    memset_0
0x18000ef84  mov     r9d, 103h; MaxCount
0x18000ef8a  lea     rcx, [rsp+270h+Destination]; Destination
0x18000ef8f  mov     r8, rbx; Source
0x18000ef92  lea     ebx, [r9+1]
0x18000ef96  mov     edx, ebx; SizeInWords
0x18000ef98  call    cs:__imp_wcsncpy_s
0x18000ef9f  nop     dword ptr [rax+rax+00h]
0x18000efa4  lea     r8, aMount; "\\Mount"
0x18000efab  mov     edx, ebx; SizeInWords
0x18000efad  lea     rcx, [rsp+270h+Destination]; Destination
0x18000efb2  call    cs:__imp_wcscat_s
0x18000efb9  nop     dword ptr [rax+rax+00h]
0x18000efbe  lea     rax, [rsp+270h+hKey]
0x18000efc3  mov     r9d, 20019h; samDesired
0x18000efc9  xor     r8d, r8d; ulOptions
0x18000efcc  mov     [rsp+270h+phkResult], rax; phkResult
0x18000efd1  lea     rdx, [rsp+270h+Destination]; lpSubKey
0x18000efd6  mov     rcx, rdi; hKey
0x18000efd9  call    cs:__imp_RegOpenKeyExW
0x18000efe0  nop     dword ptr [rax+rax+00h]
0x18000efe5  test    eax, eax
0x18000efe7  jnz     short loc_18000F034
0x18000efe9  mov     rcx, [rsp+270h+hKey]; hKey
0x18000efee  lea     rax, [rsp+270h+cbData]
0x18000eff3  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18000eff8  lea     rdx, aNfsreaddir; "NFSReaddir"
0x18000efff  lea     rax, [rsp+270h+Data]
0x18000f004  mov     [rsp+270h+cbData], 4
0x18000f00c  xor     r9d, r9d; lpType
0x18000f00f  mov     [rsp+270h+phkResult], rax; lpData
0x18000f014  xor     r8d, r8d; lpReserved
0x18000f017  call    cs:__imp_RegQueryValueExW
0x18000f01e  nop     dword ptr [rax+rax+00h]
0x18000f023  mov     rcx, [rsp+270h+hKey]; hKey
0x18000f028  call    cs:__imp_RegCloseKey
0x18000f02f  nop     dword ptr [rax+rax+00h]
0x18000f034  cmp     dword ptr [rsp+270h+Data], 0
0x18000f039  mov     eax, [rsi+38h]
0x18000f03c  jz      short loc_18000F044
0x18000f03e  bts     eax, 8
0x18000f042  jmp     short loc_18000F048
0x18000f044  btr     eax, 8
0x18000f048  mov     [rsi+38h], eax
0x18000f04b  mov     rcx, [rbp+170h+var_20]
0x18000f052  xor     rcx, rsp; StackCookie
0x18000f055  call    __security_check_cookie
0x18000f05a  mov     rbx, [rsp+270h+arg_18]
0x18000f062  add     rsp, 260h
0x18000f069  pop     rdi
0x18000f06a  pop     rsi
0x18000f06b  pop     rbp
0x18000f06c  retn
```
