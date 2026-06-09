# DhcpDeleteSubnet

- ea: `0x1800489f0`
- end: `0x180048ce4`
- name: `DhcpDeleteSubnet`
- size: `756`
- prototype: `DWORD __stdcall(WCHAR *ServerIpAddress, DHCP_IP_ADDRESS SubnetAddress, DHCP_FORCE_FLAG ForceFlag)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18004b800`

## callees

- `0x180003228`
- `0x1800068e4`
- `0x18001c45c`
- `0x1800332a8`
- `0x1800489f0`
- `0x18005dd50`
- `0x18007f72c`
- `0x180088260`
- `0x18008a778`
- `0x180092d24`
- `0x180093084`
- `0x1800932a8`
- `0x180096254`
- `0x1800962b0`
- `0x180098930`
- `0x1800a3234`
- `0x1800a9ec4`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180048b6d`
- `msvcrt!wcscpy_s` at `0x180048b6d`
- `KERNEL32!EnterCriticalSection` at `0x180048be5`
- `KERNEL32!EnterCriticalSection` at `0x180048be5`
- `KERNEL32!LeaveCriticalSection` at `0x180048c4a`
- `KERNEL32!LeaveCriticalSection` at `0x180048c4a`
- `KERNEL32!HeapFree` at `0x180048c32`
- `KERNEL32!HeapFree` at `0x180048c32`

## string_xrefs

- `0x180048afb`: `DhcpDeleteSubnet`

## pseudocode

```c

```
