# RasSrvIsRRASConfigured

- ea: `0x18003e758`
- end: `0x18003e896`
- name: `RasSrvIsRRASConfigured`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002df10`
- `0x18002e070`

## callees

- `0x18003e758`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e81a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e81a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e86d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e86d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e854`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e854`

## string_xrefs

- `0x18003e77d`: `SYSTEM\CurrentControlSet\Services\RemoteAccess`
- `0x18003e7c6`: `ConfigurationFlags`

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
0x18003e758  mov     [rsp-8+arg_8], rbx
0x18003e75d  mov     [rsp-8+arg_10], rdi
0x18003e762  push    rbp
0x18003e763  lea     rbp, [rsp-57h]
0x18003e768  sub     rsp, 0E0h
0x18003e76f  mov     rax, cs:__security_cookie
0x18003e776  xor     rax, rsp
0x18003e779  mov     [rbp+57h+var_10], rax
0x18003e77d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18003e784  mov     rdi, rcx
0x18003e787  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\RemoteAcces"...
0x18003e78e  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x18003e792  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\RemoteAccess"
0x18003e799  movaps  [rbp+57h+var_60], xmm1
0x18003e79d  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\RemoteAccess"
0x18003e7a4  movaps  [rbp+57h+var_50], xmm0
0x18003e7a8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\RemoteAccess"
0x18003e7af  movaps  [rbp+57h+var_30], xmm0
0x18003e7b3  movaps  [rbp+57h+var_40], xmm1
0x18003e7b7  mov     [rbp+57h+hKey], 0
0x18003e7bf  movups  xmm1, xmmword ptr cs:aSystemCurrentc+4Eh; "eAccess"
0x18003e7c6  movups  xmm0, xmmword ptr cs:aConfigurationf; "ConfigurationFlags"
0x18003e7cd  movups  [rbp+57h+var_30+0Eh], xmm1
0x18003e7d1  movups  xmm1, xmmword ptr cs:aConfigurationf+10h; "ationFlags"
0x18003e7d8  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x18003e7dc  movsd   xmm0, qword ptr cs:aConfigurationf+1Eh; "ags"
0x18003e7e4  movups  [rbp+57h+var_88], xmm1
0x18003e7e8  movsd   qword ptr [rbp+57h+var_88+0Eh], xmm0
0x18003e7ed  test    rcx, rcx
0x18003e7f0  jnz     short loc_18003E7F7
0x18003e7f2  lea     eax, [rcx+57h]
0x18003e7f5  jmp     short loc_18003E875
0x18003e7f7  mov     dword ptr [rcx], 0
0x18003e7fd  lea     rax, [rbp+57h+hKey]
0x18003e801  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e808  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003e80d  mov     r9d, 2001Fh; samDesired
0x18003e813  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18003e817  xor     r8d, r8d; ulOptions
0x18003e81a  call    cs:__imp_RegOpenKeyExW
0x18003e820  mov     ebx, eax
0x18003e822  test    eax, eax
0x18003e824  jnz     short loc_18003E864
0x18003e826  mov     rcx, [rbp+57h+hKey]; hKey
0x18003e82a  lea     r9, [rbp+57h+Type]; lpType
0x18003e82e  mov     [rbp+57h+Type], eax
0x18003e831  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18003e835  mov     dword ptr [rbp+57h+Data], eax
0x18003e838  xor     r8d, r8d; lpReserved
0x18003e83b  lea     rax, [rbp+57h+cbData]
0x18003e83f  mov     [rbp+57h+cbData], 4
0x18003e846  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x18003e84b  lea     rax, [rbp+57h+Data]
0x18003e84f  mov     [rsp+0E0h+phkResult], rax; lpData
0x18003e854  call    cs:__imp_RegQueryValueExW
0x18003e85a  xor     eax, eax
0x18003e85c  cmp     dword ptr [rbp+57h+Data], eax
0x18003e85f  setnz   al
0x18003e862  mov     [rdi], eax
0x18003e864  mov     rcx, [rbp+57h+hKey]; hKey
0x18003e868  test    rcx, rcx
0x18003e86b  jz      short loc_18003E873
0x18003e86d  call    cs:__imp_RegCloseKey
0x18003e873  mov     eax, ebx
0x18003e875  mov     rcx, [rbp+57h+var_10]
0x18003e879  xor     rcx, rsp; StackCookie
0x18003e87c  call    __security_check_cookie
0x18003e881  lea     r11, [rsp+0E0h+var_s0]
0x18003e889  mov     rbx, [r11+18h]
0x18003e88d  mov     rdi, [r11+20h]
0x18003e891  mov     rsp, r11
0x18003e894  pop     rbp
0x18003e895  retn
```
