# DhcpV4IsEnabledDHCPRegistryValue

- ea: `0x180007248`
- end: `0x18000728b`
- name: `DhcpV4IsEnabledDHCPRegistryValue`
- size: `67`
- prototype: `__int64 __fastcall(LPCWSTR, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800026fc`
- `0x180035c70`

## callees

- `0x1800069d0`
- `0x180007248`
- `0x18000761c`
- `0x18001bcac`

## string_xrefs

- `0x180007264`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall DhcpV4IsEnabledDHCPRegistryValue(LPCWSTR a1, _DWORD *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx

  if ( DhcpIsWCOSSystem() )
    return DhcpRegReadEnabledDhcpFromMultipleLocations(v5, v4, a1, a2);
  else
    return DhcpRegReadEnabledDhcp(L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces", a1, a2);
}

```

## disassembly

```asm
0x180007248  mov     [rsp+arg_0], rbx
0x18000724d  push    rdi
0x18000724e  sub     rsp, 20h
0x180007252  mov     rbx, rdx
0x180007255  mov     rdi, rcx
0x180007258  call    DhcpIsWCOSSystem
0x18000725d  test    eax, eax
0x18000725f  jnz     short loc_18000727E
0x180007261  mov     r8, rbx
0x180007264  lea     rcx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Tc"...
0x18000726b  mov     rdx, rdi; LPCWSTR
0x18000726e  call    DhcpRegReadEnabledDhcp
0x180007273  mov     rbx, [rsp+28h+arg_0]
0x180007278  add     rsp, 20h
0x18000727c  pop     rdi
0x18000727d  retn
0x18000727e  mov     r9, rbx
0x180007281  mov     r8, rdi
0x180007284  call    DhcpRegReadEnabledDhcpFromMultipleLocations
0x180007289  jmp     short loc_180007273
```
