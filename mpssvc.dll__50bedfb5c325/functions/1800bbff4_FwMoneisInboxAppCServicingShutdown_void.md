# FwMoneisInboxAppCServicingShutdown(void)

- ea: `0x1800bbff4`
- end: `0x1800bc0a3`
- name: `?FwMoneisInboxAppCServicingShutdown@@YAXXZ`
- size: `175`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800bf660`

## callees

- `0x18000a710`
- `0x1800bbff4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc07e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc07e`
- `fwbase!FwTriggerUnregisterWait` at `0x1800bc019`
- `fwbase!FwTriggerUnregisterWait` at `0x1800bc019`
- `fwbase!FwCriticalSectionDestroy` at `0x1800bc091`
- `fwbase!FwCriticalSectionDestroy` at `0x1800bc091`
- `fwbase!FwRegNotifyDestroy` at `0x1800bc003`
- `fwbase!FwRegNotifyDestroy` at `0x1800bc003`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800bc06b`
- `FWPolicyIOMgr!FwSidAndAttributesFree` at `0x1800bc06b`

## pseudocode

```c

```
