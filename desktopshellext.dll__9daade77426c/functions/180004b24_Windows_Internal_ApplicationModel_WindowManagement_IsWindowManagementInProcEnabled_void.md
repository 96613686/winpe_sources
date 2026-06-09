# Windows::Internal::ApplicationModel::WindowManagement::IsWindowManagementInProcEnabled(void)

- ea: `0x180004b24`
- end: `0x180004c72`
- name: `?IsWindowManagementInProcEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ`
- size: `334`
- prototype: `bool __fastcall(Windows::Internal::ApplicationModel::WindowManagement *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800034f0`

## callees

- `0x180004630`
- `0x180004b24`
- `0x180004c78`
- `0x180022df8`
- `0x18002b980`
- `0x18002b9ec`
- `0x180038324`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004bcf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180004bcf`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180004b40`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180004b40`

## string_xrefs

- `0x180004bb2`: `System\CurrentControlSet\Services\CoreUI`

## pseudocode

```c

```
