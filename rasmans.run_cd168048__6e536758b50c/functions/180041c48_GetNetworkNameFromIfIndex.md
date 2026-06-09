# GetNetworkNameFromIfIndex

- ea: `0x180041c48`
- end: `0x180042366`
- name: `GetNetworkNameFromIfIndex`
- size: `1822`
- prototype: `__int64 __fastcall(NET_IFINDEX InterfaceIndex)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000d600`
- `0x18000e8a4`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180041c48`
- `0x18004bc44`
- `0x1800e8e72`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18004218a`
- `msvcrt!wcscpy_s` at `0x18004218a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004216d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004216d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042290`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042290`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180041ce8`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180041ce8`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x180041d43`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x180041d43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041e30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041e30`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041d8b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041d8b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800422cb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800422cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800421de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800421de`
- `OLEAUT32!__imp_VariantInit` at `0x180042074`
- `OLEAUT32!__imp_VariantInit` at `0x180042074`

## pseudocode

```c

```
