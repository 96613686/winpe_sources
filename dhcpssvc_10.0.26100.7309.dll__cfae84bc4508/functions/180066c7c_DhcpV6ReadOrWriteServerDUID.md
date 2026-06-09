# DhcpV6ReadOrWriteServerDUID

- ea: `0x180066c7c`
- end: `0x180066e36`
- name: `DhcpV6ReadOrWriteServerDUID`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18006691c`

## callees

- `0x180002854`
- `0x18000323c`
- `0x180066ae4`
- `0x180066c7c`
- `0x180066f78`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180066d88`
- `ADVAPI32!RegCloseKey` at `0x180066d88`
- `ADVAPI32!RegOpenKeyExW` at `0x180066cf8`
- `ADVAPI32!RegOpenKeyExW` at `0x180066cf8`
- `ADVAPI32!RegQueryValueExW` at `0x180066d40`
- `ADVAPI32!RegQueryValueExW` at `0x180066d40`
- `ADVAPI32!RegSetValueExW` at `0x180066df5`
- `ADVAPI32!RegSetValueExW` at `0x180066df5`

## string_xrefs

- `0x180066cea`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 __fastcall DhcpV6ReadOrWriteServerDUID(__int64 a1, __int64 a2)
{
  HKEY v2; // rdi
  unsigned int ServerDuidFromRegistry; // ebx
  unsigned int v4; // eax
  DWORD v5; // eax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+54h] [rbp+Ch]
  __int64 cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  cbData = a2;
  v8 = HIDWORD(a1);
  hKey = 0;
  Type = 0;
  v2 = DhcpGlobalRegParam;
  if ( !DhcpV6GlobalServerId || (unsigned int)Size < 0x80 )
    return 87;
  ServerDuidFromRegistry = ReadServerDuidFromRegistry(DhcpGlobalRegParam, DhcpV6GlobalServerId, &Size);
  if ( ServerDuidFromRegistry )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
           0,
           0xF003Fu,
           &hKey) )
    {
      ServerDuidFromRegistry = DhcpV6MakeServerDuid(DhcpV6GlobalServerId, &Size);
      if ( ServerDuidFromRegistry )
        return ServerDuidFromRegistry;
      v5 = Size;
    }
    else
    {
      LODWORD(cbData) = Size;
      v4 = RegQueryValueExW(hKey, L"Dhcpv6DUID", 0, &Type, DhcpV6GlobalServerId, (LPDWORD)&cbData);
      ServerDuidFromRegistry = 13;
      if ( v4
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ee99ac8e335d39e55cb63cc3efe51871_Traceguids, v4);
      }
      RegCloseKey(hKey);
      if ( (unsigned int)(cbData - 1) > 0x7F )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ee99ac8e335d39e55cb63cc3efe51871_Traceguids);
        return ServerDuidFromRegistry;
      }
      v5 = (unsigned __int16)cbData;
      LODWORD(Size) = (unsigned __int16)cbData;
    }
    return (unsigned int)RegSetValueExW(v2, L"DhcpServerDUIDV6", 0, 3u, DhcpV6GlobalServerId, v5);
  }
  return ServerDuidFromRegistry;
}

```

## disassembly

```asm
0x180066c7c  mov     rax, rsp
0x180066c7f  mov     [rax+10h], rdx
0x180066c83  mov     [rax+8], rcx
0x180066c87  push    rbx
0x180066c88  push    rsi
0x180066c89  push    rdi
0x180066c8a  sub     rsp, 30h
0x180066c8e  and     qword ptr [rax+18h], 0
0x180066c93  and     dword ptr [rax+8], 0
0x180066c97  mov     rdx, cs:DhcpV6GlobalServerId
0x180066c9e  mov     rdi, cs:DhcpGlobalRegParam
0x180066ca5  test    rdx, rdx
0x180066ca8  jz      loc_180066E26
0x180066cae  cmp     cs:Size, 80h
0x180066cb8  jb      loc_180066E26
0x180066cbe  lea     r8, Size
0x180066cc5  mov     rcx, rdi
0x180066cc8  call    ReadServerDuidFromRegistry
0x180066ccd  mov     ebx, eax
0x180066ccf  test    eax, eax
0x180066cd1  jz      loc_180066E2B
0x180066cd7  lea     rax, [rsp+48h+hKey]
0x180066cdc  mov     r9d, 0F003Fh; samDesired
0x180066ce2  xor     r8d, r8d; ulOptions
0x180066ce5  mov     [rsp+48h+phkResult], rax; phkResult
0x180066cea  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x180066cf1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180066cf8  call    cs:__imp_RegOpenKeyExW
0x180066cff  nop     dword ptr [rax+rax+00h]
0x180066d04  test    eax, eax
0x180066d06  jnz     loc_180066E05
0x180066d0c  mov     eax, cs:Size
0x180066d12  lea     r9, [rsp+48h+Type]; lpType
0x180066d17  mov     rcx, [rsp+48h+hKey]; hKey
0x180066d1c  lea     rdx, aDhcpv6duid; "Dhcpv6DUID"
0x180066d23  mov     dword ptr [rsp+48h+cbData], eax
0x180066d27  xor     r8d, r8d; lpReserved
0x180066d2a  lea     rax, [rsp+48h+cbData]
0x180066d2f  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180066d34  mov     rax, cs:DhcpV6GlobalServerId
0x180066d3b  mov     [rsp+48h+phkResult], rax; lpData
0x180066d40  call    cs:__imp_RegQueryValueExW
0x180066d47  nop     dword ptr [rax+rax+00h]
0x180066d4c  mov     ebx, 0Dh
0x180066d51  lea     rsi, WPP_GLOBAL_Control
0x180066d58  test    eax, eax
0x180066d5a  jz      short loc_180066D83
0x180066d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d63  cmp     rcx, rsi
0x180066d66  jz      short loc_180066D83
0x180066d68  test    byte ptr [rcx+1Ch], 40h
0x180066d6c  jz      short loc_180066D83
0x180066d6e  mov     rcx, [rcx+10h]
0x180066d72  lea     r8, WPP_ee99ac8e335d39e55cb63cc3efe51871_Traceguids
0x180066d79  mov     edx, ebx
0x180066d7b  mov     r9d, eax
0x180066d7e  call    WPP_SF_D
0x180066d83  mov     rcx, [rsp+48h+hKey]; hKey
0x180066d88  call    cs:__imp_RegCloseKey
0x180066d8f  nop     dword ptr [rax+rax+00h]
0x180066d94  mov     ecx, dword ptr [rsp+48h+cbData]
0x180066d98  lea     eax, [rcx-1]
0x180066d9b  cmp     eax, 7Fh
0x180066d9e  jbe     short loc_180066DC9
0x180066da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180066da7  cmp     rcx, rsi
0x180066daa  jz      short loc_180066E2B
0x180066dac  test    byte ptr [rcx+1Ch], 40h
0x180066db0  jz      short loc_180066E2B
0x180066db2  mov     rcx, [rcx+10h]
0x180066db6  lea     r8, WPP_ee99ac8e335d39e55cb63cc3efe51871_Traceguids
0x180066dbd  mov     edx, 0Eh
0x180066dc2  call    WPP_SF_
0x180066dc7  jmp     short loc_180066E2B
0x180066dc9  movzx   eax, cx
0x180066dcc  mov     cs:Size, eax
0x180066dd2  mov     dword ptr [rsp+48h+lpcbData], eax; cbData
0x180066dd6  lea     rdx, aDhcpserverduid; "DhcpServerDUIDV6"
0x180066ddd  mov     rax, cs:DhcpV6GlobalServerId
0x180066de4  mov     r9d, 3; dwType
0x180066dea  xor     r8d, r8d; Reserved
0x180066ded  mov     [rsp+48h+phkResult], rax; lpData
0x180066df2  mov     rcx, rdi; hKey
0x180066df5  call    cs:__imp_RegSetValueExW
0x180066dfc  nop     dword ptr [rax+rax+00h]
0x180066e01  mov     ebx, eax
0x180066e03  jmp     short loc_180066E2B
0x180066e05  mov     rcx, cs:DhcpV6GlobalServerId
0x180066e0c  lea     rdx, Size
0x180066e13  call    DhcpV6MakeServerDuid
0x180066e18  mov     ebx, eax
0x180066e1a  test    eax, eax
0x180066e1c  jnz     short loc_180066E2B
0x180066e1e  mov     eax, cs:Size
0x180066e24  jmp     short loc_180066DD2
0x180066e26  mov     ebx, 57h ; 'W'
0x180066e2b  mov     eax, ebx
0x180066e2d  add     rsp, 30h
0x180066e31  pop     rdi
0x180066e32  pop     rsi
0x180066e33  pop     rbx
0x180066e34  retn
```
