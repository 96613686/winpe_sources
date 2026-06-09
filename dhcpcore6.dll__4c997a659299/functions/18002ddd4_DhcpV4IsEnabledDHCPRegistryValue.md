# DhcpV4IsEnabledDHCPRegistryValue

- ea: `0x18002ddd4`
- end: `0x18002de26`
- name: `DhcpV4IsEnabledDHCPRegistryValue`
- size: `82`
- prototype: `__int64 __fastcall(LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001be30`

## callees

- `0x180009f58`
- `0x180009fa8`
- `0x180017f44`
- `0x18002ddd4`

## string_xrefs

- `0x18002ddf0`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x18002de0b`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall DhcpV4IsEnabledDHCPRegistryValue(LPCWSTR a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  if ( (unsigned int)DhcpIsWCOSSystem(a1, a2, a3, a4) )
    return DhcpRegReadEnabledDhcpFromMultipleLocations(
             L"OSDATA\\Networking\\Dhcp\\Client4",
             L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
             a1);
  else
    return DhcpRegReadEnabledDhcp(L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces", a1, a2);
}

```

## disassembly

```asm
0x18002ddd4  mov     [rsp+arg_0], rbx
0x18002ddd9  push    rdi
0x18002ddda  sub     rsp, 20h
0x18002ddde  mov     rbx, rdx
0x18002dde1  mov     rdi, rcx
0x18002dde4  call    DhcpIsWCOSSystem
0x18002dde9  test    eax, eax
0x18002ddeb  jz      short loc_18002DE08
0x18002dded  mov     r9, rbx
0x18002ddf0  lea     rdx, aSystemCurrentc_10; "System\\CurrentControlSet\\Services\\Tc"...
0x18002ddf7  mov     r8, rdi; LPCWSTR
0x18002ddfa  lea     rcx, aOsdataNetworki; "OSDATA\\Networking\\Dhcp\\Client4"
0x18002de01  call    DhcpRegReadEnabledDhcpFromMultipleLocations
0x18002de06  jmp     short loc_18002DE1A
0x18002de08  mov     r8, rbx
0x18002de0b  lea     rcx, aSystemCurrentc_10; "System\\CurrentControlSet\\Services\\Tc"...
0x18002de12  mov     rdx, rdi; LPCWSTR
0x18002de15  call    DhcpRegReadEnabledDhcp
0x18002de1a  mov     rbx, [rsp+28h+arg_0]
0x18002de1f  add     rsp, 20h
0x18002de23  pop     rdi
0x18002de24  retn
```
