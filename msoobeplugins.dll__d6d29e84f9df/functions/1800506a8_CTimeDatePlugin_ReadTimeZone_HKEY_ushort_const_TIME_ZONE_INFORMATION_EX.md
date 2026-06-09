# CTimeDatePlugin::_ReadTimeZone(HKEY__ *,ushort const *,_TIME_ZONE_INFORMATION_EX *)

- ea: `0x1800506a8`
- end: `0x1800508f7`
- name: `?_ReadTimeZone@CTimeDatePlugin@@AEAAJPEAUHKEY__@@PEBGPEAU_TIME_ZONE_INFORMATION_EX@@@Z`
- size: `591`
- prototype: `int(CTimeDatePlugin *__hidden this, HKEY, const unsigned __int16 *, struct _TIME_ZONE_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180050408`

## callees

- `0x180003470`
- `0x180008b54`
- `0x1800506a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800508b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800508b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800506f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800506f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050748`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800507a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800507fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050865`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050748`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800507a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800507fe`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050865`

## pseudocode

```c

```
