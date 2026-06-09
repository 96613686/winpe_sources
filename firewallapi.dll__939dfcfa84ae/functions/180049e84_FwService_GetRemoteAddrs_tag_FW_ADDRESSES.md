# FwService::GetRemoteAddrs(_tag_FW_ADDRESSES *)

- ea: `0x180049e84`
- end: `0x180049fc7`
- name: `?GetRemoteAddrs@FwService@@AEAAJPEAU_tag_FW_ADDRESSES@@@Z`
- size: `323`
- prototype: `int(FwService *__hidden this, struct _tag_FW_ADDRESSES *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18004a5e0`
- `0x18004a6d0`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x180049e84`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180049f5e`
- `fwbase!FwReportReturnError` at `0x180049f91`
- `fwbase!FwReportReturnError` at `0x180049f5e`
- `fwbase!FwReportReturnError` at `0x180049f91`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180049f0b`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180049f6f`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180049f0b`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180049f6f`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x180049ef4`
- `FWPolicyIOMgr!FwUniteWFAddressesContents` at `0x180049ef4`

## string_xrefs

- `0x180049f57`: `FwService::GetRemoteAddrs`
- `0x180049f8a`: `FwService::GetRemoteAddrs`

## pseudocode

```c

```
