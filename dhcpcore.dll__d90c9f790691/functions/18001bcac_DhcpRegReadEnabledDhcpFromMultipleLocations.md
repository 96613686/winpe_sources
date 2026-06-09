# DhcpRegReadEnabledDhcpFromMultipleLocations

- ea: `0x18001bcac`
- end: `0x18001bd6c`
- name: `DhcpRegReadEnabledDhcpFromMultipleLocations`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180007248`
- `0x180008240`

## callees

- `0x18000761c`
- `0x18001bcac`
- `0x18004d1a0`
- `0x18004d200`
- `0x18004e364`

## string_xrefs

- `0x18001bd02`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall DhcpRegReadEnabledDhcpFromMultipleLocations(__int64 a1, __int64 a2, const WCHAR *a3, _DWORD *a4)
{
  int v6; // ecx
  unsigned int EnabledDhcp; // ebx

  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_S(1028, 23, WPP_94d5010c5674399d06148e3a91870046_Traceguids, a3);
  EnabledDhcp = DhcpRegReadEnabledDhcp(L"OSDATA\\Networking\\Dhcp\\Client4", a3, a4);
  if ( EnabledDhcp )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_SS(
        v6,
        24,
        (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
        (unsigned int)L"OSDATA\\Networking\\Dhcp\\Client4",
        (__int64)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces");
    EnabledDhcp = DhcpRegReadEnabledDhcp(L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces", a3, a4);
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 25, WPP_94d5010c5674399d06148e3a91870046_Traceguids, EnabledDhcp);
  return EnabledDhcp;
}

```

## disassembly

```asm
0x18001bcac  mov     [rsp+arg_0], rbx
0x18001bcb1  mov     [rsp+arg_8], rsi
0x18001bcb6  push    rdi
0x18001bcb7  sub     rsp, 30h
0x18001bcbb  mov     rsi, r9
0x18001bcbe  mov     rdi, r8
0x18001bcc1  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001bcc8  jz      short loc_18001BCE3
0x18001bcca  mov     r9, r8
0x18001bccd  mov     edx, 17h
0x18001bcd2  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001bcd9  mov     ecx, 404h
0x18001bcde  call    WPP_SF_S
0x18001bce3  mov     r8, rsi
0x18001bce6  lea     rcx, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client4"
0x18001bced  mov     rdx, rdi; LPCWSTR
0x18001bcf0  call    DhcpRegReadEnabledDhcp
0x18001bcf5  mov     ebx, eax
0x18001bcf7  test    eax, eax
0x18001bcf9  jz      short loc_18001BD38
0x18001bcfb  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001bd02  lea     rbx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Tc"...
0x18001bd09  jz      short loc_18001BD28
0x18001bd0b  mov     edx, 18h
0x18001bd10  mov     [rsp+38h+var_18], rbx
0x18001bd15  lea     r9, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client4"
0x18001bd1c  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001bd23  call    WPP_SF_SS
0x18001bd28  mov     r8, rsi
0x18001bd2b  mov     rdx, rdi; LPCWSTR
0x18001bd2e  mov     rcx, rbx; lpSubKey
0x18001bd31  call    DhcpRegReadEnabledDhcp
0x18001bd36  mov     ebx, eax
0x18001bd38  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001bd3f  jz      short loc_18001BD5A
0x18001bd41  mov     edx, 19h
0x18001bd46  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18001bd4d  mov     ecx, 404h
0x18001bd52  mov     r9d, ebx
0x18001bd55  call    WPP_SF_D
0x18001bd5a  mov     rsi, [rsp+38h+arg_8]
0x18001bd5f  mov     eax, ebx
0x18001bd61  mov     rbx, [rsp+38h+arg_0]
0x18001bd66  add     rsp, 30h
0x18001bd6a  pop     rdi
0x18001bd6b  retn
```
