# BrowserChannels::Private::GetInstalledInfo(HKEY__ *,ushort *,ushort *,ulong,BrowserChannels::Info *)

- ea: `0x14007b354`
- end: `0x14007b41b`
- name: `?GetInstalledInfo@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAG1KPEAUInfo@2@@Z`
- size: `199`
- prototype: `bool(BrowserChannels::Private *__hidden this, HKEY, unsigned __int16 *, unsigned __int16 *, unsigned int, struct BrowserChannels::Info *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, registry_config, installer_update`

## callers

- `0x140013150`
- `0x1400751d8`
- `0x14009759c`

## callees

- `0x14007b354`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14007b3eb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14007b3eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007b408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14007b408`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007b37e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14007b37e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007b3c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007b3c5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14007b3de`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14007b3de`

## pseudocode

```c

```
