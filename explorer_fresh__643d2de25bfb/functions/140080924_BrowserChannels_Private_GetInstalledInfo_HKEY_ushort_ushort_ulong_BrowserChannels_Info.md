# BrowserChannels::Private::GetInstalledInfo(HKEY__ *,ushort *,ushort *,ulong,BrowserChannels::Info *)

- ea: `0x140080924`
- end: `0x140080a0a`
- name: `?GetInstalledInfo@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAG1KPEAUInfo@2@@Z`
- size: `230`
- prototype: `bool(BrowserChannels::Private *__hidden this, HKEY, unsigned __int16 *, unsigned __int16 *, unsigned int, struct BrowserChannels::Info *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, registry_config, installer_update`

## callers

- `0x14001db00`
- `0x14007a684`
- `0x14009cb68`

## callees

- `0x140080924`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400809cd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400809cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14008094e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14008094e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400809f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400809f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14008099b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14008099b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400809ba`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400809ba`

## pseudocode

```c

```
