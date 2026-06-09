# BackgroundAccessNotifier::OnBackgroundAccessChange(ushort const *,ushort const *,BACKGROUND_ACCESS_STATE)

- ea: `0x1800a1630`
- end: `0x1800a1928`
- name: `?OnBackgroundAccessChange@BackgroundAccessNotifier@@QEAAJPEBG0W4BACKGROUND_ACCESS_STATE@@@Z`
- size: `760`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, enum BACKGROUND_ACCESS_STATE)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800a1580`

## callees

- `0x18009d024`
- `0x1800a1114`
- `0x1800a1630`
- `0x1800a3420`
- `0x1800a3de8`
- `0x1800a41f0`
- `0x1800b120c`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `ntdll!RtlReportException` at `0x1800a1759`
- `ntdll!RtlReportException` at `0x1800a1820`
- `ntdll!RtlReportException` at `0x1800a1759`
- `ntdll!RtlReportException` at `0x1800a1820`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800a16de`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800a17a5`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800a16de`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800a17a5`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x1800a1848`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x1800a1848`

## pseudocode

```c

```
