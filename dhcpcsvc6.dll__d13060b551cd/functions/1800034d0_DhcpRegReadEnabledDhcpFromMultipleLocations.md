# DhcpRegReadEnabledDhcpFromMultipleLocations

- ea: `0x1800034d0`
- end: `0x18000358b`
- name: `DhcpRegReadEnabledDhcpFromMultipleLocations`
- size: `187`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180003240`

## callees

- `0x180002400`
- `0x1800034d0`
- `0x1800081c0`
- `0x1800082d0`
- `0x180008310`

## string_xrefs

- `0x180003521`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall DhcpRegReadEnabledDhcpFromMultipleLocations(__int64 a1, __int64 a2, const WCHAR *a3, _DWORD *a4)
{
  int v6; // ecx
  unsigned int EnabledDhcp; // ebx

  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 23, WPP_94d5010c5674399d06148e3a91870046_Traceguids, a3);
  EnabledDhcp = DhcpRegReadEnabledDhcp(L"OSDATA\\Networking\\Dhcp\\Client6", a3, a4);
  if ( EnabledDhcp )
  {
    if ( (xmmword_18000F160 & 0x10) != 0 )
      WPP_SF_SS(
        v6,
        24,
        (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
        (unsigned int)L"OSDATA\\Networking\\Dhcp\\Client6",
        (__int64)L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces");
    EnabledDhcp = DhcpRegReadEnabledDhcp(L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces", a3, a4);
  }
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_D(1028, 25, WPP_94d5010c5674399d06148e3a91870046_Traceguids, EnabledDhcp);
  return EnabledDhcp;
}

```

## disassembly

```asm
0x1800034d0  mov     [rsp+arg_0], rbx
0x1800034d5  mov     [rsp+arg_8], rsi
0x1800034da  push    rdi
0x1800034db  sub     rsp, 30h
0x1800034df  mov     rsi, r9
0x1800034e2  mov     rdi, r8
0x1800034e5  test    byte ptr cs:xmmword_18000F160, 10h
0x1800034ec  jz      short loc_180003502
0x1800034ee  mov     r9, r8
0x1800034f1  mov     edx, 17h
0x1800034f6  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800034fd  call    WPP_SF_S
0x180003502  mov     r8, rsi
0x180003505  lea     rcx, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client6"
0x18000350c  mov     rdx, rdi; LPCWSTR
0x18000350f  call    DhcpRegReadEnabledDhcp
0x180003514  mov     ebx, eax
0x180003516  test    eax, eax
0x180003518  jz      short loc_180003557
0x18000351a  test    byte ptr cs:xmmword_18000F160, 10h
0x180003521  lea     rbx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x180003528  jz      short loc_180003547
0x18000352a  mov     edx, 18h
0x18000352f  mov     [rsp+38h+var_18], rbx
0x180003534  lea     r9, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client6"
0x18000353b  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180003542  call    WPP_SF_SS
0x180003547  mov     r8, rsi
0x18000354a  mov     rdx, rdi; LPCWSTR
0x18000354d  mov     rcx, rbx; lpSubKey
0x180003550  call    DhcpRegReadEnabledDhcp
0x180003555  mov     ebx, eax
0x180003557  test    byte ptr cs:xmmword_18000F160, 10h
0x18000355e  jz      short loc_180003579
0x180003560  mov     edx, 19h
0x180003565  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000356c  mov     ecx, 404h
0x180003571  mov     r9d, ebx
0x180003574  call    WPP_SF_D
0x180003579  mov     rsi, [rsp+38h+arg_8]
0x18000357e  mov     eax, ebx
0x180003580  mov     rbx, [rsp+38h+arg_0]
0x180003585  add     rsp, 30h
0x180003589  pop     rdi
0x18000358a  retn
```
