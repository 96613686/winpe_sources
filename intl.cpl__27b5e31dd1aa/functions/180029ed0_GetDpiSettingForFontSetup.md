# GetDpiSettingForFontSetup

- ea: `0x180029ed0`
- end: `0x180029fea`
- name: `GetDpiSettingForFontSetup`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180007cec`

## callees

- `0x180029eb4`
- `0x180029ed0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029f13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029f8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029f13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029f8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029f45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029fbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029f45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029fbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029fd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029f63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029fd4`

## pseudocode

```c
LSTATUS __fastcall GetDpiSettingForFontSetup(HKEY a1, unsigned int *a2)
{
  int v3; // edi
  unsigned int NormalizedDPI; // eax
  LSTATUS result; // eax
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  *a2 = 96;
  hKey = 0;
  cbData = 0;
  if ( RegOpenKeyExW(a1, L"Microsoft\\Windows NT\\CurrentVersion\\FontDPI", 0, 1u, &hKey) )
    goto LABEL_5;
  cbData = 4;
  v3 = 0;
  if ( !RegQueryValueExW(hKey, L"LogPixels", 0, 0, (LPBYTE)a2, &cbData) )
  {
    NormalizedDPI = GetNormalizedDPI(*a2);
    *a2 = NormalizedDPI;
    LOBYTE(v3) = NormalizedDPI != 96;
  }
  result = RegCloseKey(hKey);
  if ( !v3 )
  {
LABEL_5:
    result = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Hardware Profiles\\Current\\Software\\Fonts",
               0,
               1u,
               &hKey);
    if ( !result )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"LogPixels", 0, 0, (LPBYTE)a2, &cbData) )
        *a2 = GetNormalizedDPI(*a2);
      return RegCloseKey(hKey);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029ed0  mov     [rsp-8+arg_0], rbx
0x180029ed5  mov     [rsp-8+arg_18], rdi
0x180029eda  push    rbp
0x180029edb  mov     rbp, rsp
0x180029ede  sub     rsp, 30h
0x180029ee2  mov     rbx, rdx
0x180029ee5  mov     dword ptr [rdx], 60h ; '`'
0x180029eeb  lea     rax, [rbp+hKey]
0x180029eef  mov     [rbp+hKey], 0
0x180029ef7  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows NT\\CurrentVersion\\"...
0x180029efe  mov     [rsp+30h+phkResult], rax; phkResult
0x180029f03  mov     r9d, 1; samDesired
0x180029f09  mov     [rbp+cbData], 0
0x180029f10  xor     r8d, r8d; ulOptions
0x180029f13  call    cs:__imp_RegOpenKeyExW
0x180029f19  test    eax, eax
0x180029f1b  jnz     short loc_180029F6D
0x180029f1d  mov     rcx, [rbp+hKey]; hKey
0x180029f21  lea     rax, [rbp+cbData]
0x180029f25  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180029f2a  lea     rdx, aLogpixels; "LogPixels"
0x180029f31  xor     r9d, r9d; lpType
0x180029f34  mov     [rsp+30h+phkResult], rbx; lpData
0x180029f39  xor     r8d, r8d; lpReserved
0x180029f3c  mov     [rbp+cbData], 4
0x180029f43  xor     edi, edi
0x180029f45  call    cs:__imp_RegQueryValueExW
0x180029f4b  test    eax, eax
0x180029f4d  jnz     short loc_180029F5F
0x180029f4f  mov     ecx, [rbx]; unsigned int
0x180029f51  call    ?GetNormalizedDPI@@YAKK@Z; GetNormalizedDPI(ulong)
0x180029f56  cmp     eax, 60h ; '`'
0x180029f59  mov     [rbx], eax
0x180029f5b  setnz   dil
0x180029f5f  mov     rcx, [rbp+hKey]; hKey
0x180029f63  call    cs:__imp_RegCloseKey
0x180029f69  test    edi, edi
0x180029f6b  jnz     short loc_180029FDA
0x180029f6d  lea     rax, [rbp+hKey]
0x180029f71  mov     r9d, 1; samDesired
0x180029f77  xor     r8d, r8d; ulOptions
0x180029f7a  mov     [rsp+30h+phkResult], rax; phkResult
0x180029f7f  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Hardware Pro"...
0x180029f86  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029f8d  call    cs:__imp_RegOpenKeyExW
0x180029f93  test    eax, eax
0x180029f95  jnz     short loc_180029FDA
0x180029f97  mov     rcx, [rbp+hKey]; hKey
0x180029f9b  lea     rax, [rbp+cbData]
0x180029f9f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180029fa4  lea     rdx, aLogpixels; "LogPixels"
0x180029fab  xor     r9d, r9d; lpType
0x180029fae  mov     [rsp+30h+phkResult], rbx; lpData
0x180029fb3  xor     r8d, r8d; lpReserved
0x180029fb6  mov     [rbp+cbData], 4
0x180029fbd  call    cs:__imp_RegQueryValueExW
0x180029fc3  test    eax, eax
0x180029fc5  jnz     short loc_180029FD0
0x180029fc7  mov     ecx, [rbx]; unsigned int
0x180029fc9  call    ?GetNormalizedDPI@@YAKK@Z; GetNormalizedDPI(ulong)
0x180029fce  mov     [rbx], eax
0x180029fd0  mov     rcx, [rbp+hKey]; hKey
0x180029fd4  call    cs:__imp_RegCloseKey
0x180029fda  mov     rbx, [rsp+30h+arg_0]
0x180029fdf  mov     rdi, [rsp+30h+arg_18]
0x180029fe4  add     rsp, 30h
0x180029fe8  pop     rbp
0x180029fe9  retn
```
