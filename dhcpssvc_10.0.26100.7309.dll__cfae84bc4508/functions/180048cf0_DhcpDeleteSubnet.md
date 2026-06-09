# DhcpDeleteSubnet

- ea: `0x180048cf0`
- end: `0x180049073`
- name: `DhcpDeleteSubnet`
- size: `899`
- prototype: `DWORD __stdcall(WCHAR *ServerIpAddress, DHCP_IP_ADDRESS SubnetAddress, DHCP_FORCE_FLAG ForceFlag)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x18004bc40`

## callees

- `0x18000323c`
- `0x1800068b8`
- `0x18000a090`
- `0x18001ceb4`
- `0x180033c80`
- `0x180048cf0`
- `0x18007f86c`
- `0x1800882b8`
- `0x18008a754`
- `0x180092b24`
- `0x180092eac`
- `0x1800930bc`
- `0x18009602c`
- `0x180096080`
- `0x180098670`
- `0x1800a2520`
- `0x1800a91b0`
- `0x1800c8f30`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180048ef7`
- `msvcrt!wcscpy_s` at `0x180048ef7`
- `KERNEL32!LocalFree` at `0x180048da1`
- `KERNEL32!LocalFree` at `0x180048da1`
- `KERNEL32!EnterCriticalSection` at `0x180048f68`
- `KERNEL32!EnterCriticalSection` at `0x180048f68`
- `KERNEL32!LeaveCriticalSection` at `0x180048fcd`
- `KERNEL32!LeaveCriticalSection` at `0x180048fcd`
- `KERNEL32!HeapFree` at `0x180048fb5`
- `KERNEL32!HeapFree` at `0x180048fb5`

## string_xrefs

- `0x180048e85`: `DhcpDeleteSubnet`

## pseudocode

```c

```
