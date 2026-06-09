# GdiLoadType1Fonts

- ea: `0x180070db0`
- end: `0x180070edb`
- name: `GdiLoadType1Fonts`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180070db0`
- `0x18007f800`
- `0x180082910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070eae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070eae`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180070e68`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180070e68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070e00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070e00`

## string_xrefs

- `0x180070df2`: `Software\Microsoft\Windows NT\CurrentVersion\Type 1 Installer\Type 1 Fonts`

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
0x180070db0  mov     [rsp-8+arg_0], rbx
0x180070db5  push    rbp
0x180070db6  lea     rbp, [rsp-390h]
0x180070dbe  sub     rsp, 490h
0x180070dc5  mov     rax, cs:__security_cookie
0x180070dcc  xor     rax, rsp
0x180070dcf  mov     [rbp+390h+var_10], rax
0x180070dd6  lea     rax, [rsp+490h+hKey]
0x180070ddb  mov     [rsp+490h+hKey], 0
0x180070de4  mov     r9d, 20019h; samDesired
0x180070dea  mov     [rsp+490h+phkResult], rax; phkResult
0x180070def  xor     r8d, r8d; ulOptions
0x180070df2  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180070df9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180070e00  call    cs:__imp_RegOpenKeyExW
0x180070e07  nop     dword ptr [rax+rax+00h]
0x180070e0c  test    eax, eax
0x180070e0e  jnz     loc_180070EBA
0x180070e14  xor     ebx, ebx
0x180070e16  mov     rcx, [rsp+490h+hKey]; hKey
0x180070e1b  lea     rax, [rsp+490h+cbData]
0x180070e20  mov     [rsp+490h+lpcbData], rax; lpcbData
0x180070e25  lea     r9, [rsp+490h+cchValueName]; lpcchValueName
0x180070e2a  lea     rax, [rsp+490h+Data]
0x180070e2f  mov     [rsp+490h+cchValueName], 104h
0x180070e37  mov     [rsp+490h+lpData], rax; lpData
0x180070e3c  lea     r8, [rbp+390h+ValueName]; lpValueName
0x180070e43  lea     rax, [rsp+490h+Type]
0x180070e48  mov     [rsp+490h+cbData], 208h
0x180070e50  mov     [rsp+490h+lpType], rax; lpType
0x180070e55  mov     edx, ebx; dwIndex
0x180070e57  mov     [rsp+490h+phkResult], 0; lpReserved
0x180070e60  mov     [rsp+490h+Type], 0
0x180070e68  call    cs:__imp_RegEnumValueW
0x180070e6f  nop     dword ptr [rax+rax+00h]
0x180070e74  cmp     eax, 0EAh
0x180070e79  jz      short loc_180070EA2
0x180070e7b  test    eax, eax
0x180070e7d  jnz     short loc_180070EA9
0x180070e7f  cmp     [rsp+490h+Type], 1
0x180070e84  jz      short loc_180070E8D
0x180070e86  cmp     [rsp+490h+Type], 7
0x180070e8b  jnz     short loc_180070EA2
0x180070e8d  mov     edx, [rsp+490h+cbData]
0x180070e91  test    dl, 1
0x180070e94  jnz     short loc_180070EA2
0x180070e96  shr     edx, 1
0x180070e98  lea     rcx, [rsp+490h+Data]
0x180070e9d  call    AddType1Font
0x180070ea2  inc     ebx
0x180070ea4  jmp     loc_180070E16
0x180070ea9  mov     rcx, [rsp+490h+hKey]; hKey
0x180070eae  call    cs:__imp_RegCloseKey
0x180070eb5  nop     dword ptr [rax+rax+00h]
0x180070eba  mov     rcx, [rbp+390h+var_10]
0x180070ec1  xor     rcx, rsp; StackCookie
0x180070ec4  call    __security_check_cookie
0x180070ec9  mov     rbx, [rsp+490h+arg_0]
0x180070ed1  add     rsp, 490h
0x180070ed8  pop     rbp
0x180070ed9  retn
```
