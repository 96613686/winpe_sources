# CCbsStoreParameters::UnloadOfflineRegistryKey(CCbsStoreParameters::OFFLINE_REGISTRY_KEY *)

- ea: `0x1800b4188`
- end: `0x1800b4418`
- name: `?UnloadOfflineRegistryKey@CCbsStoreParameters@@AEAAJPEAUOFFLINE_REGISTRY_KEY@1@@Z`
- size: `656`
- prototype: `int(CCbsStoreParameters *__hidden this, struct CCbsStoreParameters::OFFLINE_REGISTRY_KEY *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180043bf8`
- `0x1800b40a4`
- `0x1801ee9d8`

## callees

- `0x1800461c8`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b4188`
- `0x1800b4498`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800fe364`
- `0x18010c194`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b4309`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b4309`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800b4239`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800b4239`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b4278`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b4278`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800b42bd`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800b42bd`

## string_xrefs

- `0x1800b4257`: `Unable to flush offline registry: {}.`
- `0x1800b42e9`: `Unloading offline registry hive: {}`
- `0x1800b437a`: `Force unloading offline registry hive: {}`
- `0x1800b4294`: `Unable to close offline registry: {}.`
- `0x1800b4325`: `Unable to unload offline registry: {}.`
- `0x1800b43ae`: `Failed to unload offline registry: {}`

## pseudocode

```c

```
