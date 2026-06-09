# DhcpV6ReadOrWriteServerDUID

- ea: `0x180066a38`
- end: `0x180066bf8`
- name: `DhcpV6ReadOrWriteServerDUID`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800666e0`

## callees

- `0x18000282c`
- `0x180003228`
- `0x1800668a0`
- `0x180066a38`
- `0x180066d10`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180066b4a`
- `ADVAPI32!RegCloseKey` at `0x180066b4a`
- `ADVAPI32!RegOpenKeyExW` at `0x180066aba`
- `ADVAPI32!RegOpenKeyExW` at `0x180066aba`
- `ADVAPI32!RegQueryValueExW` at `0x180066b02`
- `ADVAPI32!RegQueryValueExW` at `0x180066b02`
- `ADVAPI32!RegSetValueExW` at `0x180066bb7`
- `ADVAPI32!RegSetValueExW` at `0x180066bb7`

## string_xrefs

- `0x180066aac`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
  v2 = DhcpGlobalRegParam;
  hKey = 0;
  Type = 0;
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
0x180066a38  mov     rax, rsp
0x180066a3b  mov     [rax+10h], rdx
0x180066a3f  mov     [rax+8], rcx
0x180066a43  push    rbx
0x180066a44  push    rsi
0x180066a45  push    rdi
0x180066a46  sub     rsp, 30h
0x180066a4a  mov     rdx, cs:DhcpV6GlobalServerId
0x180066a51  mov     rdi, cs:DhcpGlobalRegParam
0x180066a58  mov     qword ptr [rax+18h], 0
0x180066a60  mov     dword ptr [rax+8], 0
0x180066a67  test    rdx, rdx
0x180066a6a  jz      loc_180066BE8
0x180066a70  cmp     cs:Size, 80h
0x180066a7a  jb      loc_180066BE8
0x180066a80  lea     r8, Size
0x180066a87  mov     rcx, rdi
0x180066a8a  call    ReadServerDuidFromRegistry
0x180066a8f  mov     ebx, eax
0x180066a91  test    eax, eax
0x180066a93  jz      loc_180066BED
0x180066a99  lea     rax, [rsp+48h+hKey]
0x180066a9e  mov     r9d, 0F003Fh; samDesired
0x180066aa4  xor     r8d, r8d; ulOptions
0x180066aa7  mov     [rsp+48h+phkResult], rax; phkResult
0x180066aac  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x180066ab3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180066aba  call    cs:__imp_RegOpenKeyExW
0x180066ac1  nop     dword ptr [rax+rax+00h]
0x180066ac6  test    eax, eax
0x180066ac8  jnz     loc_180066BC7
0x180066ace  mov     eax, cs:Size
0x180066ad4  lea     r9, [rsp+48h+Type]; lpType
0x180066ad9  mov     rcx, [rsp+48h+hKey]; hKey
0x180066ade  lea     rdx, aDhcpv6duid; "Dhcpv6DUID"
0x180066ae5  mov     dword ptr [rsp+48h+cbData], eax
0x180066ae9  xor     r8d, r8d; lpReserved
0x180066aec  lea     rax, [rsp+48h+cbData]
0x180066af1  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180066af6  mov     rax, cs:DhcpV6GlobalServerId
0x180066afd  mov     [rsp+48h+phkResult], rax; lpData
0x180066b02  call    cs:__imp_RegQueryValueExW
0x180066b09  nop     dword ptr [rax+rax+00h]
0x180066b0e  mov     ebx, 0Dh
0x180066b13  lea     rsi, WPP_GLOBAL_Control
0x180066b1a  test    eax, eax
0x180066b1c  jz      short loc_180066B45
0x180066b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180066b25  cmp     rcx, rsi
0x180066b28  jz      short loc_180066B45
0x180066b2a  test    byte ptr [rcx+1Ch], 40h
0x180066b2e  jz      short loc_180066B45
0x180066b30  mov     rcx, [rcx+10h]
0x180066b34  lea     r8, WPP_ee99ac8e335d39e55cb63cc3efe51871_Traceguids
0x180066b3b  mov     edx, ebx
0x180066b3d  mov     r9d, eax
0x180066b40  call    WPP_SF_D
0x180066b45  mov     rcx, [rsp+48h+hKey]; hKey
0x180066b4a  call    cs:__imp_RegCloseKey
0x180066b51  nop     dword ptr [rax+rax+00h]
0x180066b56  mov     ecx, dword ptr [rsp+48h+cbData]
0x180066b5a  lea     eax, [rcx-1]
0x180066b5d  cmp     eax, 7Fh
0x180066b60  jbe     short loc_180066B8B
0x180066b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180066b69  cmp     rcx, rsi
0x180066b6c  jz      short loc_180066BED
0x180066b6e  test    byte ptr [rcx+1Ch], 40h
0x180066b72  jz      short loc_180066BED
0x180066b74  mov     rcx, [rcx+10h]
0x180066b78  lea     r8, WPP_ee99ac8e335d39e55cb63cc3efe51871_Traceguids
0x180066b7f  mov     edx, 0Eh
0x180066b84  call    WPP_SF_
0x180066b89  jmp     short loc_180066BED
0x180066b8b  movzx   eax, cx
0x180066b8e  mov     cs:Size, eax
0x180066b94  mov     dword ptr [rsp+48h+lpcbData], eax; cbData
0x180066b98  lea     rdx, aDhcpserverduid; "DhcpServerDUIDV6"
0x180066b9f  mov     rax, cs:DhcpV6GlobalServerId
0x180066ba6  mov     r9d, 3; dwType
0x180066bac  xor     r8d, r8d; Reserved
0x180066baf  mov     [rsp+48h+phkResult], rax; lpData
0x180066bb4  mov     rcx, rdi; hKey
0x180066bb7  call    cs:__imp_RegSetValueExW
0x180066bbe  nop     dword ptr [rax+rax+00h]
0x180066bc3  mov     ebx, eax
0x180066bc5  jmp     short loc_180066BED
0x180066bc7  mov     rcx, cs:DhcpV6GlobalServerId
0x180066bce  lea     rdx, Size
0x180066bd5  call    DhcpV6MakeServerDuid
0x180066bda  mov     ebx, eax
0x180066bdc  test    eax, eax
0x180066bde  jnz     short loc_180066BED
0x180066be0  mov     eax, cs:Size
0x180066be6  jmp     short loc_180066B94
0x180066be8  mov     ebx, 57h ; 'W'
0x180066bed  mov     eax, ebx
0x180066bef  add     rsp, 30h
0x180066bf3  pop     rdi
0x180066bf4  pop     rsi
0x180066bf5  pop     rbx
0x180066bf6  retn
```
