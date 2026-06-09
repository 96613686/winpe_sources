# DhcpV6IsEnabledDHCPRegistryValue

- ea: `0x180009f00`
- end: `0x180009f52`
- name: `DhcpV6IsEnabledDHCPRegistryValue`
- size: `82`
- prototype: `__int64 __fastcall(LPCWSTR)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180009a70`
- `0x1800157f4`
- `0x18001be30`

## callees

- `0x180009f00`
- `0x180009f58`
- `0x180009fa8`
- `0x180017f44`

## string_xrefs

- `0x180009f1c`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`
- `0x180009f3a`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall DhcpV6IsEnabledDHCPRegistryValue(LPCWSTR a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  if ( (unsigned int)DhcpIsWCOSSystem(a1, a2, a3, a4) )
    return DhcpRegReadEnabledDhcpFromMultipleLocations(
             L"OSDATA\\Networking\\Dhcp\\Client6",
             L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces",
             a1);
  else
    return DhcpRegReadEnabledDhcp(L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces", a1, a2);
}

```

## disassembly

```asm
0x180009f00  mov     [rsp+arg_0], rbx
0x180009f05  push    rdi
0x180009f06  sub     rsp, 20h
0x180009f0a  mov     rbx, rdx
0x180009f0d  mov     rdi, rcx
0x180009f10  call    DhcpIsWCOSSystem
0x180009f15  test    eax, eax
0x180009f17  jnz     short loc_180009F37
0x180009f19  mov     r8, rbx
0x180009f1c  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Tc"...
0x180009f23  mov     rdx, rdi; LPCWSTR
0x180009f26  call    DhcpRegReadEnabledDhcp
0x180009f2b  mov     rbx, [rsp+28h+arg_0]
0x180009f30  add     rsp, 20h
0x180009f34  pop     rdi
0x180009f35  retn
0x180009f37  mov     r9, rbx
0x180009f3a  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Tc"...
0x180009f41  mov     r8, rdi; LPCWSTR
0x180009f44  lea     rcx, aOsdataNetworki_1; "OSDATA\\Networking\\Dhcp\\Client6"
0x180009f4b  call    DhcpRegReadEnabledDhcpFromMultipleLocations
0x180009f50  jmp     short loc_180009F2B
```
