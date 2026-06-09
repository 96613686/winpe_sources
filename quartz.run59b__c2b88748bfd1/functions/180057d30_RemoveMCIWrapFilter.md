# RemoveMCIWrapFilter

- ea: `0x180057d30`
- end: `0x180057f20`
- name: `RemoveMCIWrapFilter`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800580c0`

## callees

- `0x1800388a0`
- `0x180057d30`
- `0x18005989c`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180057e02`
- `KERNEL32!CompareStringW` at `0x180057e02`
- `ADVAPI32!RegQueryValueExW` at `0x180057dd0`
- `ADVAPI32!RegQueryValueExW` at `0x180057dd0`
- `ADVAPI32!RegEnumValueW` at `0x180057e66`
- `ADVAPI32!RegEnumValueW` at `0x180057e66`
- `ADVAPI32!RegDeleteValueW` at `0x180057e1e`
- `ADVAPI32!RegDeleteValueW` at `0x180057e1e`
- `ADVAPI32!RegOpenKeyExW` at `0x180057d92`
- `ADVAPI32!RegOpenKeyExW` at `0x180057d92`
- `ADVAPI32!RegEnumKeyExW` at `0x180057eba`
- `ADVAPI32!RegEnumKeyExW` at `0x180057eba`
- `ADVAPI32!RegDeleteKeyW` at `0x180057ef2`
- `ADVAPI32!RegDeleteKeyW` at `0x180057ef2`
- `ADVAPI32!RegCloseKey` at `0x180057ed4`
- `ADVAPI32!RegCloseKey` at `0x180057ed4`

## pseudocode

```c
LSTATUS RemoveMCIWrapFilter()
{
  LSTATUS result; // eax
  char v1; // bl
  LSTATUS v2; // eax
  char v3; // dl
  char v4; // di
  char v5; // bl
  HKEY hKey[2]; // [rsp+40h] [rbp-29h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-19h] BYREF
  DWORD cchValueName; // [rsp+54h] [rbp-15h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-11h] BYREF
  WCHAR Data[40]; // [rsp+60h] [rbp-9h] BYREF

  *(GUID *)hKey = CLSID_MCIWrap;
  AMovieSetupUnregisterServer(hKey);
  hKey[0] = 0;
  result = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"cdaudio", 0, 0x2001Fu, hKey);
  if ( !result )
  {
    cbData = 78;
    if ( RegQueryValueExW(hKey[0], L"Source Filter", 0, 0, (LPBYTE)Data, &cbData)
      || (v1 = 1, CompareStringW(0x7Fu, 1u, Data, -1, L"{6B6D0808-9ADA-11d0-A520-00A0D10129C0}", -1) != 2) )
    {
      v1 = 0;
    }
    else
    {
      RegDeleteValueW(hKey[0], L"Source Filter");
    }
    cchValueName = 0;
    v2 = RegEnumValueW(hKey[0], 0, 0, &cchValueName, 0, 0, 0, 0);
    v3 = 0;
    if ( v2 == 259 )
      v3 = v1;
    v4 = v3;
    cchName = 0;
    v5 = 0;
    if ( RegEnumKeyExW(hKey[0], 0, 0, &cchName, 0, 0, 0, 0) == 259 )
      v5 = v4;
    result = RegCloseKey(hKey[0]);
    if ( v5 )
      return RegDeleteKeyW(HKEY_CLASSES_ROOT, L"cdaudio");
  }
  return result;
}

```

## disassembly

```asm
0x180057d30  mov     [rsp-8+arg_0], rbx
0x180057d35  mov     [rsp-8+arg_8], rdi
0x180057d3a  push    rbp
0x180057d3b  lea     rbp, [rsp-57h]
0x180057d40  sub     rsp, 0C0h
0x180057d47  mov     rax, cs:__security_cookie
0x180057d4e  xor     rax, rsp
0x180057d51  mov     [rbp+57h+var_10], rax
0x180057d55  movups  xmm0, xmmword ptr cs:CLSID_MCIWrap.Data1
0x180057d5c  lea     rcx, [rbp+57h+hKey]
0x180057d60  movdqu  xmmword ptr [rbp+57h+hKey], xmm0
0x180057d65  call    AMovieSetupUnregisterServer
0x180057d6a  lea     rax, [rbp+57h+hKey]
0x180057d6e  mov     [rbp+57h+hKey], 0
0x180057d76  mov     r9d, 2001Fh; samDesired
0x180057d7c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180057d81  xor     r8d, r8d; ulOptions
0x180057d84  lea     rdx, aCdaudio; "cdaudio"
0x180057d8b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180057d92  call    cs:__imp_RegOpenKeyExW
0x180057d99  nop     dword ptr [rax+rax+00h]
0x180057d9e  test    eax, eax
0x180057da0  jnz     loc_180057EFE
0x180057da6  mov     rcx, [rbp+57h+hKey]; hKey
0x180057daa  lea     rax, [rbp+57h+cbData]
0x180057dae  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180057db3  lea     rdx, aSourceFilter; "Source Filter"
0x180057dba  lea     rax, [rbp+57h+Data]
0x180057dbe  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x180057dc5  xor     r9d, r9d; lpType
0x180057dc8  mov     [rsp+0C0h+phkResult], rax; lpData
0x180057dcd  xor     r8d, r8d; lpReserved
0x180057dd0  call    cs:__imp_RegQueryValueExW
0x180057dd7  nop     dword ptr [rax+rax+00h]
0x180057ddc  test    eax, eax
0x180057dde  jnz     short loc_180057E2C
0x180057de0  or      r9d, 0FFFFFFFFh; cchCount1
0x180057de4  lea     rax, String2; "{6B6D0808-9ADA-11d0-A520-00A0D10129C0}"
0x180057deb  mov     dword ptr [rsp+0C0h+lpcbData], r9d; cchCount2
0x180057df0  lea     r8, [rbp+57h+Data]; lpString1
0x180057df4  mov     [rsp+0C0h+phkResult], rax; lpString2
0x180057df9  lea     ebx, [r9+2]
0x180057dfd  mov     edx, ebx; dwCmpFlags
0x180057dff  lea     ecx, [rbx+7Eh]; Locale
0x180057e02  call    cs:__imp_CompareStringW
0x180057e09  nop     dword ptr [rax+rax+00h]
0x180057e0e  cmp     eax, 2
0x180057e11  jnz     short loc_180057E2C
0x180057e13  mov     rcx, [rbp+57h+hKey]; hKey
0x180057e17  lea     rdx, aSourceFilter; "Source Filter"
0x180057e1e  call    cs:__imp_RegDeleteValueW
0x180057e25  nop     dword ptr [rax+rax+00h]
0x180057e2a  jmp     short loc_180057E2E
0x180057e2c  xor     bl, bl
0x180057e2e  mov     rcx, [rbp+57h+hKey]; hKey
0x180057e32  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180057e36  mov     [rsp+0C0h+var_88], 0; lpcbData
0x180057e3f  xor     r8d, r8d; lpValueName
0x180057e42  mov     [rsp+0C0h+lpData], 0; lpData
0x180057e4b  xor     edx, edx; dwIndex
0x180057e4d  mov     [rsp+0C0h+lpcbData], 0; lpType
0x180057e56  mov     [rsp+0C0h+phkResult], 0; lpReserved
0x180057e5f  mov     [rbp+57h+cchValueName], 0
0x180057e66  call    cs:__imp_RegEnumValueW
0x180057e6d  nop     dword ptr [rax+rax+00h]
0x180057e72  xor     edx, edx
0x180057e74  mov     [rsp+0C0h+var_88], 0; lpftLastWriteTime
0x180057e7d  cmp     eax, 103h
0x180057e82  movzx   ecx, bl
0x180057e85  mov     [rsp+0C0h+lpData], 0; lpcchClass
0x180057e8e  lea     r9, [rbp+57h+cchName]; lpcchName
0x180057e92  cmovz   edx, ecx
0x180057e95  mov     [rsp+0C0h+lpcbData], 0; lpClass
0x180057e9e  mov     rcx, [rbp+57h+hKey]; hKey
0x180057ea2  xor     r8d, r8d; lpName
0x180057ea5  movzx   edi, dl
0x180057ea8  xor     edx, edx; dwIndex
0x180057eaa  mov     [rbp+57h+cchName], 0
0x180057eb1  mov     [rsp+0C0h+phkResult], 0; lpReserved
0x180057eba  call    cs:__imp_RegEnumKeyExW
0x180057ec1  nop     dword ptr [rax+rax+00h]
0x180057ec6  mov     rcx, [rbp+57h+hKey]; hKey
0x180057eca  xor     ebx, ebx
0x180057ecc  cmp     eax, 103h
0x180057ed1  cmovz   ebx, edi
0x180057ed4  call    cs:__imp_RegCloseKey
0x180057edb  nop     dword ptr [rax+rax+00h]
0x180057ee0  test    bl, bl
0x180057ee2  jz      short loc_180057EFE
0x180057ee4  lea     rdx, aCdaudio; "cdaudio"
0x180057eeb  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180057ef2  call    cs:__imp_RegDeleteKeyW
0x180057ef9  nop     dword ptr [rax+rax+00h]
0x180057efe  mov     rcx, [rbp+57h+var_10]
0x180057f02  xor     rcx, rsp; StackCookie
0x180057f05  call    __security_check_cookie
0x180057f0a  lea     r11, [rsp+0C0h+var_s0]
0x180057f12  mov     rbx, [r11+10h]
0x180057f16  mov     rdi, [r11+18h]
0x180057f1a  mov     rsp, r11
0x180057f1d  pop     rbp
0x180057f1e  retn
```
