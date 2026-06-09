# LoadInjectorIfRequired

- ea: `0x180006958`
- end: `0x180006a1f`
- name: `LoadInjectorIfRequired`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800063bc`

## callees

- `0x180006850`
- `0x180006958`
- `0x180006fa4`
- `0x180044880`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800069a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800069a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800069d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800069d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006a04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006a04`

## pseudocode

```c
LSTATUS LoadInjectorIfRequired()
{
  DWORD cbData; // [rsp+30h] [rbp-50h] BYREF
  DWORD Type; // [rsp+34h] [rbp-4Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  BYTE Data[22]; // [rsp+40h] [rbp-40h] BYREF
  __int16 v5; // [rsp+56h] [rbp-2Ah]
  WCHAR LibFileName[12]; // [rsp+58h] [rbp-28h] BYREF

  hKey = 0;
  cbData = 24;
  Type = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN", 0, 1u, &hKey);
  if ( !RegQueryValueExW(hKey, L"NitsInjector", 0, &Type, Data, &cbData) && cbData == 24 )
  {
    v5 = 0;
    Wcslcpy(LibFileName, Data, 12);
    LoadInjector(LibFileName);
  }
  return RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180006958  push    rbp
0x18000695a  mov     rbp, rsp
0x18000695d  sub     rsp, 80h
0x180006964  mov     rax, cs:__security_cookie
0x18000696b  xor     rax, rsp
0x18000696e  mov     [rbp+var_10], rax
0x180006972  lea     rax, [rbp+hKey]
0x180006976  mov     [rbp+hKey], 0
0x18000697e  mov     r9d, 1; samDesired
0x180006984  mov     [rsp+80h+phkResult], rax; phkResult
0x180006989  xor     r8d, r8d; ulOptions
0x18000698c  mov     [rbp+cbData], 18h
0x180006993  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000699a  mov     [rbp+Type], 0
0x1800069a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800069a8  call    cs:__imp_RegOpenKeyExW
0x1800069ae  mov     rcx, [rbp+hKey]; hKey
0x1800069b2  lea     rax, [rbp+cbData]
0x1800069b6  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800069bb  lea     r9, [rbp+Type]; lpType
0x1800069bf  lea     rax, [rbp+Data]
0x1800069c3  xor     r8d, r8d; lpReserved
0x1800069c6  lea     rdx, ValueName; "NitsInjector"
0x1800069cd  mov     [rsp+80h+phkResult], rax; lpData
0x1800069d2  call    cs:__imp_RegQueryValueExW
0x1800069d8  test    eax, eax
0x1800069da  jnz     short loc_180006A00
0x1800069dc  cmp     [rbp+cbData], 18h
0x1800069e0  jnz     short loc_180006A00
0x1800069e2  lea     r8d, [rax+0Ch]
0x1800069e6  mov     [rbp+var_2A], ax
0x1800069ea  lea     rdx, [rbp+Data]
0x1800069ee  lea     rcx, [rbp+LibFileName]
0x1800069f2  call    Wcslcpy
0x1800069f7  lea     rcx, [rbp+LibFileName]; lpLibFileName
0x1800069fb  call    LoadInjector
0x180006a00  mov     rcx, [rbp+hKey]; hKey
0x180006a04  call    cs:__imp_RegCloseKey
0x180006a0a  mov     rcx, [rbp+var_10]
0x180006a0e  xor     rcx, rsp; StackCookie
0x180006a11  call    __security_check_cookie
0x180006a16  add     rsp, 80h
0x180006a1d  pop     rbp
0x180006a1e  retn
```
