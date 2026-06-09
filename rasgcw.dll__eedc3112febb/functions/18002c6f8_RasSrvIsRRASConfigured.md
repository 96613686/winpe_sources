# RasSrvIsRRASConfigured

- ea: `0x18002c6f8`
- end: `0x18002c836`
- name: `RasSrvIsRRASConfigured`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001ff4c`

## callees

- `0x18002c6f8`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c80d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c80d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c7ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c7ba`
- `KERNEL32!RegQueryValueExW` at `0x18002c7f4`
- `KERNEL32!RegQueryValueExW` at `0x18002c7f4`

## string_xrefs

- `0x18002c71d`: `SYSTEM\CurrentControlSet\Services\RemoteAccess`
- `0x18002c766`: `ConfigurationFlags`

## pseudocode

```c
__int64 __fastcall RasSrvIsRRASConfigured(_DWORD *a1)
{
  unsigned int v3; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-59h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-55h] BYREF
  DWORD Type; // [rsp+38h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-49h] BYREF
  WCHAR ValueName[20]; // [rsp+48h] [rbp-41h] BYREF
  WCHAR SubKey[48]; // [rsp+70h] [rbp-19h] BYREF

  wcscpy(SubKey, L"SYSTEM\\CurrentControlSet\\Services\\RemoeAccess");
  hKey = 0;
  wcscpy(ValueName, L"ConfigurationFags");
  if ( !a1 )
    return 87;
  *a1 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Fu, &hKey);
  if ( !v3 )
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData);
    *a1 = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18002c6f8  mov     [rsp-8+arg_8], rbx
0x18002c6fd  mov     [rsp-8+arg_10], rdi
0x18002c702  push    rbp
0x18002c703  lea     rbp, [rsp-57h]
0x18002c708  sub     rsp, 0E0h
0x18002c70f  mov     rax, cs:__security_cookie
0x18002c716  xor     rax, rsp
0x18002c719  mov     [rbp+57h+var_10], rax
0x18002c71d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18002c724  mov     rdi, rcx
0x18002c727  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\RemoteAcces"...
0x18002c72e  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x18002c732  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\RemoteAccess"
0x18002c739  movaps  [rbp+57h+var_60], xmm1
0x18002c73d  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\RemoteAccess"
0x18002c744  movaps  [rbp+57h+var_50], xmm0
0x18002c748  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\RemoteAccess"
0x18002c74f  movaps  [rbp+57h+var_30], xmm0
0x18002c753  movaps  [rbp+57h+var_40], xmm1
0x18002c757  mov     [rbp+57h+hKey], 0
0x18002c75f  movups  xmm1, xmmword ptr cs:aSystemCurrentc+4Eh; "eAccess"
0x18002c766  movups  xmm0, xmmword ptr cs:aConfigurationf; "ConfigurationFlags"
0x18002c76d  movups  [rbp+57h+var_30+0Eh], xmm1
0x18002c771  movups  xmm1, xmmword ptr cs:aConfigurationf+10h; "ationFlags"
0x18002c778  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x18002c77c  movsd   xmm0, qword ptr cs:aConfigurationf+1Eh; "ags"
0x18002c784  movups  [rbp+57h+var_88], xmm1
0x18002c788  movsd   qword ptr [rbp+57h+var_88+0Eh], xmm0
0x18002c78d  test    rcx, rcx
0x18002c790  jnz     short loc_18002C797
0x18002c792  lea     eax, [rcx+57h]
0x18002c795  jmp     short loc_18002C815
0x18002c797  mov     dword ptr [rcx], 0
0x18002c79d  lea     rax, [rbp+57h+hKey]
0x18002c7a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c7a8  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002c7ad  mov     r9d, 2001Fh; samDesired
0x18002c7b3  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18002c7b7  xor     r8d, r8d; ulOptions
0x18002c7ba  call    cs:__imp_RegOpenKeyExW
0x18002c7c0  mov     ebx, eax
0x18002c7c2  test    eax, eax
0x18002c7c4  jnz     short loc_18002C804
0x18002c7c6  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c7ca  lea     r9, [rbp+57h+Type]; lpType
0x18002c7ce  mov     [rbp+57h+Type], eax
0x18002c7d1  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18002c7d5  mov     dword ptr [rbp+57h+Data], eax
0x18002c7d8  xor     r8d, r8d; lpReserved
0x18002c7db  lea     rax, [rbp+57h+cbData]
0x18002c7df  mov     [rbp+57h+cbData], 4
0x18002c7e6  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18002c7eb  lea     rax, [rbp+57h+Data]
0x18002c7ef  mov     [rsp+0E0h+phkResult], rax; lpData
0x18002c7f4  call    cs:__imp_RegQueryValueExW
0x18002c7fa  xor     eax, eax
0x18002c7fc  cmp     dword ptr [rbp+57h+Data], eax
0x18002c7ff  setnz   al
0x18002c802  mov     [rdi], eax
0x18002c804  mov     rcx, [rbp+57h+hKey]; hKey
0x18002c808  test    rcx, rcx
0x18002c80b  jz      short loc_18002C813
0x18002c80d  call    cs:__imp_RegCloseKey
0x18002c813  mov     eax, ebx
0x18002c815  mov     rcx, [rbp+57h+var_10]
0x18002c819  xor     rcx, rsp; StackCookie
0x18002c81c  call    __security_check_cookie
0x18002c821  lea     r11, [rsp+0E0h+var_s0]
0x18002c829  mov     rbx, [r11+18h]
0x18002c82d  mov     rdi, [r11+20h]
0x18002c831  mov     rsp, r11
0x18002c834  pop     rbp
0x18002c835  retn
```
