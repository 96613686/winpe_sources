# DnsCreatePropertyKey

- ea: `0x180032c90`
- end: `0x180032d87`
- name: `DnsCreatePropertyKey`
- size: `247`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180032978`

## callees

- `0x180032c90`
- `0x180046ec0`
- `0x1800868b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032d7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032d7f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032cc4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032cc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032d0b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032d0b`

## pseudocode

```c
__int64 __fastcall DnsCreatePropertyKey(HKEY hKey, LPCWSTR lpSubKey, HKEY *a3)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  int v9; // edx
  HKEY hKeya; // [rsp+50h] [rbp-28h] BYREF

  hKeya = 0;
  *a3 = 0;
  v6 = RegDeleteTreeW(hKey, lpSubKey);
  v7 = v6;
  if ( (v6 & 0xFFFFFFFD) != 0 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_10;
    v9 = 159;
    goto LABEL_9;
  }
  v6 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKeya, 0);
  v7 = v6;
  if ( !v6 )
  {
    *a3 = hKeya;
    return v7;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v9 = 160;
LABEL_9:
    WPP_SF_DS(1035, v9, (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v6, (__int64)lpSubKey);
  }
LABEL_10:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v7;
}

```

## disassembly

```asm
0x180032c90  mov     [rsp+arg_18], rbx
0x180032c95  push    rbp
0x180032c96  push    rsi
0x180032c97  push    rdi
0x180032c98  sub     rsp, 60h
0x180032c9c  mov     rax, cs:__security_cookie
0x180032ca3  xor     rax, rsp
0x180032ca6  mov     [rsp+78h+var_20], rax
0x180032cab  mov     rsi, r8
0x180032cae  mov     [rsp+78h+hKey], 0
0x180032cb7  mov     rdi, rdx
0x180032cba  mov     qword ptr [r8], 0
0x180032cc1  mov     rbp, rcx
0x180032cc4  call    cs:__imp_RegDeleteTreeW
0x180032cca  mov     ebx, eax
0x180032ccc  test    eax, 0FFFFFFFDh
0x180032cd1  jnz     short loc_180032D3E
0x180032cd3  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180032cdc  lea     rax, [rsp+78h+hKey]
0x180032ce1  mov     [rsp+78h+phkResult], rax; phkResult
0x180032ce6  xor     r9d, r9d; lpClass
0x180032ce9  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180032cf2  xor     r8d, r8d; Reserved
0x180032cf5  mov     [rsp+78h+samDesired], 20006h; samDesired
0x180032cfd  mov     rdx, rdi; lpSubKey
0x180032d00  mov     rcx, rbp; hKey
0x180032d03  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180032d0b  call    cs:__imp_RegCreateKeyExW
0x180032d11  mov     ebx, eax
0x180032d13  test    eax, eax
0x180032d15  jnz     short loc_180032D4E
0x180032d17  mov     rax, [rsp+78h+hKey]
0x180032d1c  mov     [rsi], rax
0x180032d1f  mov     eax, ebx
0x180032d21  mov     rcx, [rsp+78h+var_20]
0x180032d26  xor     rcx, rsp; StackCookie
0x180032d29  call    __security_check_cookie
0x180032d2e  mov     rbx, [rsp+78h+arg_18]
0x180032d36  add     rsp, 60h
0x180032d3a  pop     rdi
0x180032d3b  pop     rsi
0x180032d3c  pop     rbp
0x180032d3d  retn
0x180032d3e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032d45  jz      short loc_180032D75
0x180032d47  mov     edx, 9Fh
0x180032d4c  jmp     short loc_180032D5C
0x180032d4e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032d55  jz      short loc_180032D75
0x180032d57  mov     edx, 0A0h
0x180032d5c  mov     r9d, eax
0x180032d5f  mov     qword ptr [rsp+78h+dwOptions], rdi
0x180032d64  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180032d6b  mov     ecx, 40Bh
0x180032d70  call    WPP_SF_DS
0x180032d75  mov     rcx, [rsp+78h+hKey]; hKey
0x180032d7a  test    rcx, rcx
0x180032d7d  jz      short loc_180032D1F
0x180032d7f  call    cs:__imp_RegCloseKey
0x180032d85  jmp     short loc_180032D1F
```
