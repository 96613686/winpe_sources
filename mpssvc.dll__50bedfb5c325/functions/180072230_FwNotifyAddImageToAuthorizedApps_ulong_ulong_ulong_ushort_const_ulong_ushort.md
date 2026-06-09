# FwNotifyAddImageToAuthorizedApps(ulong,ulong,ulong,ushort const *,ulong,ushort * *)

- ea: `0x180072230`
- end: `0x1800724f9`
- name: `?FwNotifyAddImageToAuthorizedApps@@YAJKKKPEBGKPEAPEAG@Z`
- size: `713`
- prototype: `int(unsigned int, unsigned int, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180053eb4`

## callees

- `0x180039644`
- `0x18003d708`
- `0x180054ea8`
- `0x180072230`
- `0x180072500`
- `0x1800729c0`
- `0x180073488`
- `0x18007c114`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800723aa`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800723aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800723d4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800723d4`
- `fwbase!FwStringBuild` at `0x180072411`
- `fwbase!FwStringBuild` at `0x180072411`
- `fwbase!FwReportReturnError` at `0x180072487`
- `fwbase!FwReportReturnError` at `0x1800724bd`
- `fwbase!FwReportReturnError` at `0x180072487`
- `fwbase!FwReportReturnError` at `0x1800724bd`
- `fwbase!FwFree` at `0x180072457`
- `fwbase!FwFree` at `0x1800724a4`
- `fwbase!FwFree` at `0x180072457`
- `fwbase!FwFree` at `0x1800724a4`

## pseudocode

```c

```
