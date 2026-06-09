# EliminateSubKey

- ea: `0x180025d5c`
- end: `0x180025eb6`
- name: `EliminateSubKey`
- size: `346`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180025ccc`
- `0x180025d5c`

## callees

- `0x1800017b0`
- `0x180025d5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025e62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025e62`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180025e4d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180025e4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025ded`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025ded`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180025e74`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180025e74`

## pseudocode

```c
LSTATUS __fastcall EliminateSubKey(HKEY hKey, LPCWSTR lpSubKey)
{
  LPCWSTR v4; // rax
  __int64 v5; // rcx
  LSTATUS result; // eax
  bool v7; // cc
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  if ( !lpSubKey )
    return -2147467259;
  v4 = lpSubKey;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  if ( !v5 || ((0x7FFFFFFF - v5) & -(__int64)(v5 != 0)) == 0 )
    return -2147467259;
  result = RegOpenKeyExW(hKey, lpSubKey, 0, 0x2000000u, &hKeya);
  v7 = result <= 0;
  if ( !result )
  {
    do
    {
      cchName = 260;
      ftLastWriteTime = 0;
    }
    while ( !RegEnumKeyExW(hKeya, 0, SubKey, &cchName, 0, 0, 0, &ftLastWriteTime)
         && !(unsigned int)EliminateSubKey(hKeya, SubKey) );
    RegCloseKey(hKeya);
    result = RegDeleteKeyW(hKey, lpSubKey);
    v7 = result <= 0;
  }
  if ( !v7 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025d5c  mov     [rsp-8+arg_10], rbx
0x180025d61  push    rbp
0x180025d62  push    rsi
0x180025d63  push    rdi
0x180025d64  lea     rbp, [rsp-180h]
0x180025d6c  sub     rsp, 280h
0x180025d73  mov     rax, cs:__security_cookie
0x180025d7a  xor     rax, rsp
0x180025d7d  mov     [rbp+190h+var_20], rax
0x180025d84  xor     esi, esi
0x180025d86  mov     rbx, rdx
0x180025d89  mov     [rsp+290h+hKey], rsi
0x180025d8e  mov     rdi, rcx
0x180025d91  test    rdx, rdx
0x180025d94  jz      loc_180025E8E
0x180025d9a  mov     edx, 7FFFFFFFh
0x180025d9f  mov     rax, rbx
0x180025da2  mov     ecx, edx
0x180025da4  cmp     [rax], si
0x180025da7  jz      short loc_180025DB3
0x180025da9  add     rax, 2
0x180025dad  sub     rcx, 1
0x180025db1  jnz     short loc_180025DA4
0x180025db3  sub     rdx, rcx
0x180025db6  mov     rax, rcx
0x180025db9  neg     rax
0x180025dbc  sbb     r8, r8
0x180025dbf  and     r8, rdx
0x180025dc2  test    rcx, rcx
0x180025dc5  jz      loc_180025E8E
0x180025dcb  test    r8, r8
0x180025dce  jz      loc_180025E8E
0x180025dd4  lea     rax, [rsp+290h+hKey]
0x180025dd9  mov     r9d, 2000000h; samDesired
0x180025ddf  xor     r8d, r8d; ulOptions
0x180025de2  mov     [rsp+290h+phkResult], rax; phkResult
0x180025de7  mov     rdx, rbx; lpSubKey
0x180025dea  mov     rcx, rdi; hKey
0x180025ded  call    cs:__imp_RegOpenKeyExW
0x180025df4  nop     dword ptr [rax+rax+00h]
0x180025df9  test    eax, eax
0x180025dfb  jnz     loc_180025E82
0x180025e01  jmp     short loc_180025E16
0x180025e03  mov     rcx, [rsp+290h+hKey]; hKey
0x180025e08  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180025e0d  call    EliminateSubKey
0x180025e12  test    eax, eax
0x180025e14  jnz     short loc_180025E5D
0x180025e16  mov     rcx, [rsp+290h+hKey]; hKey
0x180025e1b  lea     rax, [rsp+290h+ftLastWriteTime]
0x180025e20  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180025e25  lea     r9, [rsp+290h+cchName]; lpcchName
0x180025e2a  mov     [rsp+290h+lpcchClass], rsi; lpcchClass
0x180025e2f  lea     r8, [rsp+290h+SubKey]; lpName
0x180025e34  mov     [rsp+290h+lpClass], rsi; lpClass
0x180025e39  xor     edx, edx; dwIndex
0x180025e3b  mov     [rsp+290h+phkResult], rsi; lpReserved
0x180025e40  mov     [rsp+290h+cchName], 104h
0x180025e48  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], rsi
0x180025e4d  call    cs:__imp_RegEnumKeyExW
0x180025e54  nop     dword ptr [rax+rax+00h]
0x180025e59  test    eax, eax
0x180025e5b  jz      short loc_180025E03
0x180025e5d  mov     rcx, [rsp+290h+hKey]; hKey
0x180025e62  call    cs:__imp_RegCloseKey
0x180025e69  nop     dword ptr [rax+rax+00h]
0x180025e6e  mov     rdx, rbx; lpSubKey
0x180025e71  mov     rcx, rdi; hKey
0x180025e74  call    cs:__imp_RegDeleteKeyW
0x180025e7b  nop     dword ptr [rax+rax+00h]
0x180025e80  test    eax, eax
0x180025e82  jle     short loc_180025E93
0x180025e84  movzx   eax, ax
0x180025e87  or      eax, 80070000h
0x180025e8c  jmp     short loc_180025E93
0x180025e8e  mov     eax, 80004005h
0x180025e93  mov     rcx, [rbp+190h+var_20]
0x180025e9a  xor     rcx, rsp; StackCookie
0x180025e9d  call    __security_check_cookie
0x180025ea2  mov     rbx, [rsp+290h+arg_10]
0x180025eaa  add     rsp, 280h
0x180025eb1  pop     rdi
0x180025eb2  pop     rsi
0x180025eb3  pop     rbp
0x180025eb4  retn
```
