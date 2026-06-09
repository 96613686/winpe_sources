# IcsIPv6GetPrefixSharingType(void)

- ea: `0x18000e3b0`
- end: `0x18000e4e7`
- name: `?IcsIPv6GetPrefixSharingType@@YA?AW4_ICS_IPV6_PREFIX_SHARING_TYPE@@XZ`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000c790`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000e3b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e472`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e472`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e40d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e40d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e4be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e4be`

## string_xrefs

- `0x18000e3db`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 IcsIPv6GetPrefixSharingType()
{
  __int64 result; // rax
  unsigned int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
  }
  hKey = 0;
  Data = 0;
  cbData = 0;
  Type = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
          0,
          0xF003Fu,
          &hKey)
    && ((cbData = 4, RegQueryValueExW(hKey, L"ICS_IPv6_AllowNoWWANInterface", 0, &Type, (LPBYTE)&Data, &cbData))
     || Type != 4)
    || (result = Data, (Data & 0xFFFFFFFD) != 0) )
  {
    result = 1;
    Data = 1;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    result = Data;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids,
      (unsigned int)result);
    return Data;
  }
  return result;
}

```

## disassembly

```asm
0x18000e3b0  push    rbx
0x18000e3b2  sub     rsp, 30h
0x18000e3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3bd  lea     rbx, WPP_GLOBAL_Control
0x18000e3c4  cmp     rcx, rbx
0x18000e3c7  jz      short loc_18000E3D9
0x18000e3c9  test    byte ptr [rcx+1Ch], 80h
0x18000e3cd  jz      short loc_18000E3D9
0x18000e3cf  cmp     byte ptr [rcx+19h], 6
0x18000e3d3  jnb     loc_18000E4CD
0x18000e3d9  xor     eax, eax
0x18000e3db  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18000e3e2  mov     [rsp+38h+hKey], rax
0x18000e3e7  mov     r9d, 0F003Fh; samDesired
0x18000e3ed  mov     [rsp+38h+Data], eax
0x18000e3f1  xor     r8d, r8d; ulOptions
0x18000e3f4  mov     [rsp+38h+cbData], eax
0x18000e3f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e3ff  mov     [rsp+38h+Type], eax
0x18000e403  lea     rax, [rsp+38h+hKey]
0x18000e408  mov     [rsp+38h+phkResult], rax; phkResult
0x18000e40d  call    cs:__imp_RegOpenKeyExW
0x18000e413  test    eax, eax
0x18000e415  jz      short loc_18000E442
0x18000e417  mov     eax, [rsp+38h+Data]
0x18000e41b  test    eax, 0FFFFFFFDh
0x18000e420  jnz     short loc_18000E47C
0x18000e422  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e427  test    rcx, rcx
0x18000e42a  jnz     loc_18000E4BE
0x18000e430  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e437  cmp     rcx, rbx
0x18000e43a  jnz     short loc_18000E487
0x18000e43c  add     rsp, 30h
0x18000e440  pop     rbx
0x18000e441  retn
0x18000e442  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e447  lea     rax, [rsp+38h+cbData]
0x18000e44c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000e451  lea     r9, [rsp+38h+Type]; lpType
0x18000e456  lea     rax, [rsp+38h+Data]
0x18000e45b  mov     [rsp+38h+cbData], 4
0x18000e463  xor     r8d, r8d; lpReserved
0x18000e466  mov     [rsp+38h+phkResult], rax; lpData
0x18000e46b  lea     rdx, aIcsIpv6Allowno; "ICS_IPv6_AllowNoWWANInterface"
0x18000e472  call    cs:__imp_RegQueryValueExW
0x18000e478  test    eax, eax
0x18000e47a  jz      short loc_18000E4B1
0x18000e47c  mov     eax, 1
0x18000e481  mov     [rsp+38h+Data], eax
0x18000e485  jmp     short loc_18000E422
0x18000e487  test    byte ptr [rcx+1Ch], 80h
0x18000e48b  jz      short loc_18000E43C
0x18000e48d  cmp     byte ptr [rcx+19h], 6
0x18000e491  jb      short loc_18000E43C
0x18000e493  mov     rcx, [rcx+10h]
0x18000e497  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000e49e  mov     edx, 42h ; 'B'
0x18000e4a3  mov     r9d, eax
0x18000e4a6  call    WPP_SF_d
0x18000e4ab  mov     eax, [rsp+38h+Data]
0x18000e4af  jmp     short loc_18000E43C
0x18000e4b1  cmp     [rsp+38h+Type], 4
0x18000e4b6  jz      loc_18000E417
0x18000e4bc  jmp     short loc_18000E47C
0x18000e4be  call    cs:__imp_RegCloseKey
0x18000e4c4  mov     eax, [rsp+38h+Data]
0x18000e4c8  jmp     loc_18000E430
0x18000e4cd  mov     rcx, [rcx+10h]
0x18000e4d1  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000e4d8  mov     edx, 41h ; 'A'
0x18000e4dd  call    WPP_SF_
0x18000e4e2  jmp     loc_18000E3D9
```
