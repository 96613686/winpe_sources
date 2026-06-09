# GdiLoadType1Fonts

- ea: `0x18006c350`
- end: `0x18006c468`
- name: `GdiLoadType1Fonts`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18006c350`
- `0x18007ac50`
- `0x18007dcb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c442`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c442`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006c402`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006c402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c3a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c3a0`

## string_xrefs

- `0x18006c392`: `Software\Microsoft\Windows NT\CurrentVersion\Type 1 Installer\Type 1 Fonts`

## pseudocode

```c
LSTATUS GdiLoadType1Fonts()
{
  LSTATUS result; // eax
  DWORD i; // ebx
  LSTATUS v2; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[528]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Type 1 Installer\\Type 1 Fonts",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    for ( i = 0; ; ++i )
    {
      cchValueName = 260;
      cbData = 520;
      Type = 0;
      v2 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
      if ( v2 != 234 )
      {
        if ( v2 )
          return RegCloseKey(hKey);
        if ( (Type == 1 || Type == 7) && (cbData & 1) == 0 )
          AddType1Font(Data, cbData >> 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006c350  mov     [rsp-8+arg_0], rbx
0x18006c355  push    rbp
0x18006c356  lea     rbp, [rsp-390h]
0x18006c35e  sub     rsp, 490h
0x18006c365  mov     rax, cs:__security_cookie
0x18006c36c  xor     rax, rsp
0x18006c36f  mov     [rbp+390h+var_10], rax
0x18006c376  lea     rax, [rsp+490h+hKey]
0x18006c37b  mov     [rsp+490h+hKey], 0
0x18006c384  mov     r9d, 20019h; samDesired
0x18006c38a  mov     [rsp+490h+phkResult], rax; phkResult
0x18006c38f  xor     r8d, r8d; ulOptions
0x18006c392  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x18006c399  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006c3a0  call    cs:__imp_RegOpenKeyExW
0x18006c3a6  test    eax, eax
0x18006c3a8  jnz     loc_18006C448
0x18006c3ae  xor     ebx, ebx
0x18006c3b0  mov     rcx, [rsp+490h+hKey]; hKey
0x18006c3b5  lea     rax, [rsp+490h+cbData]
0x18006c3ba  mov     [rsp+490h+lpcbData], rax; lpcbData
0x18006c3bf  lea     r9, [rsp+490h+cchValueName]; lpcchValueName
0x18006c3c4  lea     rax, [rsp+490h+Data]
0x18006c3c9  mov     [rsp+490h+cchValueName], 104h
0x18006c3d1  mov     [rsp+490h+lpData], rax; lpData
0x18006c3d6  lea     r8, [rbp+390h+ValueName]; lpValueName
0x18006c3dd  lea     rax, [rsp+490h+Type]
0x18006c3e2  mov     [rsp+490h+cbData], 208h
0x18006c3ea  mov     [rsp+490h+lpType], rax; lpType
0x18006c3ef  mov     edx, ebx; dwIndex
0x18006c3f1  mov     [rsp+490h+phkResult], 0; lpReserved
0x18006c3fa  mov     [rsp+490h+Type], 0
0x18006c402  call    cs:__imp_RegEnumValueW
0x18006c408  cmp     eax, 0EAh
0x18006c40d  jz      short loc_18006C436
0x18006c40f  test    eax, eax
0x18006c411  jnz     short loc_18006C43D
0x18006c413  cmp     [rsp+490h+Type], 1
0x18006c418  jz      short loc_18006C421
0x18006c41a  cmp     [rsp+490h+Type], 7
0x18006c41f  jnz     short loc_18006C436
0x18006c421  mov     edx, [rsp+490h+cbData]
0x18006c425  test    dl, 1
0x18006c428  jnz     short loc_18006C436
0x18006c42a  shr     edx, 1
0x18006c42c  lea     rcx, [rsp+490h+Data]
0x18006c431  call    AddType1Font
0x18006c436  inc     ebx
0x18006c438  jmp     loc_18006C3B0
0x18006c43d  mov     rcx, [rsp+490h+hKey]; hKey
0x18006c442  call    cs:__imp_RegCloseKey
0x18006c448  mov     rcx, [rbp+390h+var_10]
0x18006c44f  xor     rcx, rsp; StackCookie
0x18006c452  call    __security_check_cookie
0x18006c457  mov     rbx, [rsp+490h+arg_0]
0x18006c45f  add     rsp, 490h
0x18006c466  pop     rbp
0x18006c467  retn
```
