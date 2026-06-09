# IcsIPv6GetPrefixSharingType(void)

- ea: `0x18000ee80`
- end: `0x18000efca`
- name: `?IcsIPv6GetPrefixSharingType@@YA?AW4_ICS_IPV6_PREFIX_SHARING_TYPE@@XZ`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000d0e0`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000ee80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eedd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eedd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef9b`

## string_xrefs

- `0x18000eeab`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
0x18000ee80  push    rbx
0x18000ee82  sub     rsp, 30h
0x18000ee86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee8d  lea     rbx, WPP_GLOBAL_Control
0x18000ee94  cmp     rcx, rbx
0x18000ee97  jz      short loc_18000EEA9
0x18000ee99  test    byte ptr [rcx+1Ch], 80h
0x18000ee9d  jz      short loc_18000EEA9
0x18000ee9f  cmp     byte ptr [rcx+19h], 6
0x18000eea3  jnb     loc_18000EFB0
0x18000eea9  xor     eax, eax
0x18000eeab  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18000eeb2  mov     [rsp+38h+hKey], rax
0x18000eeb7  mov     r9d, 0F003Fh; samDesired
0x18000eebd  mov     [rsp+38h+Data], eax
0x18000eec1  xor     r8d, r8d; ulOptions
0x18000eec4  mov     [rsp+38h+cbData], eax
0x18000eec8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000eecf  mov     [rsp+38h+Type], eax
0x18000eed3  lea     rax, [rsp+38h+hKey]
0x18000eed8  mov     [rsp+38h+phkResult], rax; phkResult
0x18000eedd  call    cs:__imp_RegOpenKeyExW
0x18000eee4  nop     dword ptr [rax+rax+00h]
0x18000eee9  test    eax, eax
0x18000eeeb  jz      short loc_18000EF19
0x18000eeed  mov     eax, [rsp+38h+Data]
0x18000eef1  test    eax, 0FFFFFFFDh
0x18000eef6  jnz     short loc_18000EF59
0x18000eef8  mov     rcx, [rsp+38h+hKey]; hKey
0x18000eefd  test    rcx, rcx
0x18000ef00  jnz     loc_18000EF9B
0x18000ef06  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef0d  cmp     rcx, rbx
0x18000ef10  jnz     short loc_18000EF64
0x18000ef12  add     rsp, 30h
0x18000ef16  pop     rbx
0x18000ef17  retn
0x18000ef19  mov     rcx, [rsp+38h+hKey]; hKey
0x18000ef1e  lea     rax, [rsp+38h+cbData]
0x18000ef23  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000ef28  lea     r9, [rsp+38h+Type]; lpType
0x18000ef2d  lea     rax, [rsp+38h+Data]
0x18000ef32  mov     [rsp+38h+cbData], 4
0x18000ef3a  xor     r8d, r8d; lpReserved
0x18000ef3d  mov     [rsp+38h+phkResult], rax; lpData
0x18000ef42  lea     rdx, aIcsIpv6Allowno; "ICS_IPv6_AllowNoWWANInterface"
0x18000ef49  call    cs:__imp_RegQueryValueExW
0x18000ef50  nop     dword ptr [rax+rax+00h]
0x18000ef55  test    eax, eax
0x18000ef57  jz      short loc_18000EF8E
0x18000ef59  mov     eax, 1
0x18000ef5e  mov     [rsp+38h+Data], eax
0x18000ef62  jmp     short loc_18000EEF8
0x18000ef64  test    byte ptr [rcx+1Ch], 80h
0x18000ef68  jz      short loc_18000EF12
0x18000ef6a  cmp     byte ptr [rcx+19h], 6
0x18000ef6e  jb      short loc_18000EF12
0x18000ef70  mov     rcx, [rcx+10h]
0x18000ef74  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000ef7b  mov     edx, 42h ; 'B'
0x18000ef80  mov     r9d, eax
0x18000ef83  call    WPP_SF_d
0x18000ef88  mov     eax, [rsp+38h+Data]
0x18000ef8c  jmp     short loc_18000EF12
0x18000ef8e  cmp     [rsp+38h+Type], 4
0x18000ef93  jz      loc_18000EEED
0x18000ef99  jmp     short loc_18000EF59
0x18000ef9b  call    cs:__imp_RegCloseKey
0x18000efa2  nop     dword ptr [rax+rax+00h]
0x18000efa7  mov     eax, [rsp+38h+Data]
0x18000efab  jmp     loc_18000EF06
0x18000efb0  mov     rcx, [rcx+10h]
0x18000efb4  lea     r8, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x18000efbb  mov     edx, 41h ; 'A'
0x18000efc0  call    WPP_SF_
0x18000efc5  jmp     loc_18000EEA9
```
