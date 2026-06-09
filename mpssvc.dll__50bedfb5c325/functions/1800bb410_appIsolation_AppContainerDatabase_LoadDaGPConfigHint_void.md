# appIsolation::AppContainerDatabase::LoadDaGPConfigHint(void)

- ea: `0x1800bb410`
- end: `0x1800bb51b`
- name: `?LoadDaGPConfigHint@AppContainerDatabase@appIsolation@@QEAAKXZ`
- size: `267`
- prototype: `unsigned int __fastcall(appIsolation::AppContainerDatabase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800981a0`
- `0x1800beee0`

## callees

- `0x1800192e0`
- `0x1800729c0`
- `0x1800bb410`

## import_xrefs

- `fwbase!FwRegQueryNumKeys` at `0x1800bb4c7`
- `fwbase!FwRegQueryNumKeys` at `0x1800bb4c7`
- `fwbase!FwRegOpenKey` at `0x1800bb4a6`
- `fwbase!FwRegOpenKey` at `0x1800bb4a6`
- `fwbase!FwRegCloseKey` at `0x1800bb4f4`
- `fwbase!FwRegCloseKey` at `0x1800bb4f4`
- `fwbase!FwCriticalSectionEnter` at `0x1800bb477`
- `fwbase!FwCriticalSectionEnter` at `0x1800bb477`
- `fwbase!FwCriticalSectionLeave` at `0x1800bb4e3`
- `fwbase!FwCriticalSectionLeave` at `0x1800bb4e3`

## string_xrefs

- `0x1800bb498`: `SOFTWARE\Policies\Microsoft\Windows NT\DNSClient\DnsPolicyConfig`

## pseudocode

```c

```
