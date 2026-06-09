# DhcpRegReadEnabledDhcpFromMultipleLocations

- ea: `0x180004170`
- end: `0x180004230`
- name: `DhcpRegReadEnabledDhcpFromMultipleLocations`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800021a0`

## callees

- `0x180002940`
- `0x180004170`
- `0x1800127f0`
- `0x180012a00`
- `0x180012ad0`

## string_xrefs

- `0x1800041c6`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall DhcpRegReadEnabledDhcpFromMultipleLocations(__int64 a1, __int64 a2, const WCHAR *a3, _DWORD *a4)
{
  int v6; // ecx
  unsigned int EnabledDhcp; // ebx

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 23, WPP_94d5010c5674399d06148e3a91870046_Traceguids, a3);
  EnabledDhcp = DhcpRegReadEnabledDhcp(L"OSDATA\\Networking\\Dhcp\\Client4", a3, a4);
  if ( EnabledDhcp )
  {
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_SS(
        v6,
        24,
        (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
        (unsigned int)L"OSDATA\\Networking\\Dhcp\\Client4",
        (__int64)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces");
    EnabledDhcp = DhcpRegReadEnabledDhcp(L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces", a3, a4);
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 25, WPP_94d5010c5674399d06148e3a91870046_Traceguids, EnabledDhcp);
  return EnabledDhcp;
}

```

## disassembly

```asm
0x180004170  mov     [rsp+arg_0], rbx
0x180004175  mov     [rsp+arg_8], rsi
0x18000417a  push    rdi
0x18000417b  sub     rsp, 30h
0x18000417f  mov     rsi, r9
0x180004182  mov     rdi, r8
0x180004185  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000418c  jz      short loc_1800041A7
0x18000418e  mov     r9, r8
0x180004191  mov     edx, 17h
0x180004196  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000419d  mov     ecx, 404h
0x1800041a2  call    WPP_SF_S
0x1800041a7  mov     r8, rsi
0x1800041aa  lea     rcx, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client4"
0x1800041b1  mov     rdx, rdi; LPCWSTR
0x1800041b4  call    DhcpRegReadEnabledDhcp
0x1800041b9  mov     ebx, eax
0x1800041bb  test    eax, eax
0x1800041bd  jz      short loc_1800041FC
0x1800041bf  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800041c6  lea     rbx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x1800041cd  jz      short loc_1800041EC
0x1800041cf  mov     edx, 18h
0x1800041d4  mov     [rsp+38h+var_18], rbx
0x1800041d9  lea     r9, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client4"
0x1800041e0  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800041e7  call    WPP_SF_SS
0x1800041ec  mov     r8, rsi
0x1800041ef  mov     rdx, rdi; LPCWSTR
0x1800041f2  mov     rcx, rbx; lpSubKey
0x1800041f5  call    DhcpRegReadEnabledDhcp
0x1800041fa  mov     ebx, eax
0x1800041fc  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180004203  jz      short loc_18000421E
0x180004205  mov     edx, 19h
0x18000420a  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180004211  mov     ecx, 404h
0x180004216  mov     r9d, ebx
0x180004219  call    WPP_SF_d
0x18000421e  mov     rsi, [rsp+38h+arg_8]
0x180004223  mov     eax, ebx
0x180004225  mov     rbx, [rsp+38h+arg_0]
0x18000422a  add     rsp, 30h
0x18000422e  pop     rdi
0x18000422f  retn
```
