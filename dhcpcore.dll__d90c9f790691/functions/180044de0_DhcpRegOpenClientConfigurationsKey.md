# DhcpRegOpenClientConfigurationsKey

- ea: `0x180044de0`
- end: `0x180044eb8`
- name: `DhcpRegOpenClientConfigurationsKey`
- size: `216`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180036498`
- `0x180044d00`

## callees

- `0x1800069d0`
- `0x180044de0`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044e7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044e7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044e5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044e5a`

## string_xrefs

- `0x180044e40`: `OSDATA\Networking\Dhcp\Client4\Configurations`
- `0x180044e2e`: `System\CurrentControlSet\Services\Dhcp\Configurations`

## pseudocode

```c
__int64 __fastcall DhcpRegOpenClientConfigurationsKey(HKEY *a1)
{
  HKEY v2; // rcx
  unsigned int v3; // ebx
  BOOL IsWCOSSystem; // eax
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  phkResult = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_(1028, 38, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
    v2 = phkResult;
  }
  if ( a1 )
  {
    *a1 = 0;
    IsWCOSSystem = DhcpIsWCOSSystem();
    v5 = L"OSDATA\\Networking\\Dhcp\\Client4\\Configurations";
    if ( !IsWCOSSystem )
      v5 = L"System\\CurrentControlSet\\Services\\Dhcp\\Configurations";
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x2000000u, &phkResult);
    v2 = phkResult;
    v3 = v6;
    if ( !v6 )
    {
      *a1 = phkResult;
      v2 = 0;
      phkResult = 0;
    }
  }
  else
  {
    v3 = 87;
  }
  if ( v2 )
  {
    RegCloseKey(v2);
    phkResult = 0;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 39, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180044de0  mov     [rsp+arg_8], rbx
0x180044de5  push    rdi
0x180044de6  sub     rsp, 30h
0x180044dea  mov     rdi, rcx
0x180044ded  xor     ecx, ecx
0x180044def  mov     [rsp+38h+arg_0], rcx
0x180044df4  test    byte ptr cs:xmmword_1800616A0, 10h
0x180044dfb  jz      short loc_180044E16
0x180044dfd  lea     edx, [rcx+26h]
0x180044e00  mov     ecx, 404h
0x180044e05  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180044e0c  call    WPP_SF_
0x180044e11  mov     rcx, [rsp+38h+arg_0]
0x180044e16  test    rdi, rdi
0x180044e19  jnz     short loc_180044E20
0x180044e1b  lea     ebx, [rdi+57h]
0x180044e1e  jmp     short loc_180044E75
0x180044e20  mov     qword ptr [rdi], 0
0x180044e27  call    DhcpIsWCOSSystem
0x180044e2c  test    eax, eax
0x180044e2e  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Dh"...
0x180044e35  lea     rax, [rsp+38h+arg_0]
0x180044e3a  mov     r9d, 2000000h; samDesired
0x180044e40  lea     rdx, aOsdataNetworki_4; "OSDATA\\Networking\\Dhcp\\Client4\\Conf"...
0x180044e47  mov     [rsp+38h+phkResult], rax; phkResult
0x180044e4c  cmovz   rdx, rcx; lpSubKey
0x180044e50  xor     r8d, r8d; ulOptions
0x180044e53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044e5a  call    cs:__imp_RegOpenKeyExW
0x180044e60  mov     rcx, [rsp+38h+arg_0]
0x180044e65  mov     ebx, eax
0x180044e67  test    eax, eax
0x180044e69  jnz     short loc_180044E75
0x180044e6b  mov     [rdi], rcx
0x180044e6e  xor     ecx, ecx; hKey
0x180044e70  mov     [rsp+38h+arg_0], rcx
0x180044e75  test    rcx, rcx
0x180044e78  jz      short loc_180044E89
0x180044e7a  call    cs:__imp_RegCloseKey
0x180044e80  mov     [rsp+38h+arg_0], 0
0x180044e89  test    byte ptr cs:xmmword_1800616A0, 10h
0x180044e90  jz      short loc_180044EAB
0x180044e92  mov     edx, 27h ; '''
0x180044e97  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180044e9e  mov     ecx, 404h
0x180044ea3  mov     r9d, ebx
0x180044ea6  call    WPP_SF_D
0x180044eab  mov     eax, ebx
0x180044ead  mov     rbx, [rsp+38h+arg_8]
0x180044eb2  add     rsp, 30h
0x180044eb6  pop     rdi
0x180044eb7  retn
```
