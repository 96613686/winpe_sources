# SHIsThisComputerByNameOnly(ushort const *)

- ea: `0x18002a960`
- end: `0x18002aa3a`
- name: `?SHIsThisComputerByNameOnly@@YAHPEBG@Z`
- size: `218`
- prototype: `__int64 __fastcall(LPCWSTR pszStr2)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bea0`
- `0x18000c6f0`
- `0x180012340`
- `0x180014500`

## callees

- `0x1800254e0`
- `0x18002a960`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002a9fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002a9fc`
- `KERNEL32!GetComputerNameW` at `0x18002a9d1`
- `KERNEL32!GetComputerNameW` at `0x18002a9d1`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a995`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a9a9`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a9bd`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a9e3`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002aa0e`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a995`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a9a9`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a9bd`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a9e3`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002aa0e`

## pseudocode

```c
_BOOL8 __fastcall SHIsThisComputerByNameOnly(LPCWSTR pszStr2)
{
  DWORD nSize; // [rsp+20h] [rbp-238h] BYREF
  DWORD v4[3]; // [rsp+24h] [rbp-234h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  nSize = 260;
  v4[0] = 260;
  return !StrCmpICW(L"LOCALHOST", pszStr2)
      || !StrCmpICW(L"127.0.0.1", pszStr2)
      || !StrCmpICW(L"::1", pszStr2)
      || GetComputerNameW(Buffer, &nSize) && !StrCmpICW(Buffer, pszStr2)
      || GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, v4) && !StrCmpICW(Buffer, pszStr2);
}

```

## disassembly

```asm
0x18002a960  push    rbx
0x18002a962  sub     rsp, 250h
0x18002a969  mov     rax, cs:__security_cookie
0x18002a970  xor     rax, rsp
0x18002a973  mov     [rsp+258h+var_18], rax
0x18002a97b  mov     eax, 104h
0x18002a980  mov     rbx, rcx
0x18002a983  mov     rdx, rcx; pszStr2
0x18002a986  mov     [rsp+258h+nSize], eax
0x18002a98a  lea     rcx, aLocalhost; "LOCALHOST"
0x18002a991  mov     [rsp+258h+var_234], eax
0x18002a995  call    cs:__imp_StrCmpICW
0x18002a99b  test    eax, eax
0x18002a99d  jz      short loc_18002AA1C
0x18002a99f  mov     rdx, rbx; pszStr2
0x18002a9a2  lea     rcx, a127001; "127.0.0.1"
0x18002a9a9  call    cs:__imp_StrCmpICW
0x18002a9af  test    eax, eax
0x18002a9b1  jz      short loc_18002AA1C
0x18002a9b3  mov     rdx, rbx; pszStr2
0x18002a9b6  lea     rcx, a1; "::1"
0x18002a9bd  call    cs:__imp_StrCmpICW
0x18002a9c3  test    eax, eax
0x18002a9c5  jz      short loc_18002AA1C
0x18002a9c7  lea     rdx, [rsp+258h+nSize]; nSize
0x18002a9cc  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18002a9d1  call    cs:__imp_GetComputerNameW
0x18002a9d7  test    eax, eax
0x18002a9d9  jz      short loc_18002A9ED
0x18002a9db  mov     rdx, rbx; pszStr2
0x18002a9de  lea     rcx, [rsp+258h+Buffer]; pszStr1
0x18002a9e3  call    cs:__imp_StrCmpICW
0x18002a9e9  test    eax, eax
0x18002a9eb  jz      short loc_18002AA1C
0x18002a9ed  lea     r8, [rsp+258h+var_234]; nSize
0x18002a9f2  mov     ecx, 3; NameType
0x18002a9f7  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x18002a9fc  call    cs:__imp_GetComputerNameExW
0x18002aa02  test    eax, eax
0x18002aa04  jz      short loc_18002AA18
0x18002aa06  mov     rdx, rbx; pszStr2
0x18002aa09  lea     rcx, [rsp+258h+Buffer]; pszStr1
0x18002aa0e  call    cs:__imp_StrCmpICW
0x18002aa14  test    eax, eax
0x18002aa16  jz      short loc_18002AA1C
0x18002aa18  xor     eax, eax
0x18002aa1a  jmp     short loc_18002AA21
0x18002aa1c  mov     eax, 1
0x18002aa21  mov     rcx, [rsp+258h+var_18]
0x18002aa29  xor     rcx, rsp; StackCookie
0x18002aa2c  call    __security_check_cookie
0x18002aa31  add     rsp, 250h
0x18002aa38  pop     rbx
0x18002aa39  retn
```
