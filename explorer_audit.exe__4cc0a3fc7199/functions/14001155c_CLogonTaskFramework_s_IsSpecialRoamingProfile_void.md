# CLogonTaskFramework::s_IsSpecialRoamingProfile(void)

- ea: `0x14001155c`
- end: `0x140011815`
- name: `?s_IsSpecialRoamingProfile@CLogonTaskFramework@@CA_NXZ`
- size: `697`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140010924`

## callees

- `0x14001155c`
- `0x1400119c8`
- `0x140011a10`
- `0x140011a54`
- `0x140011cc8`
- `0x14001687c`
- `0x140016b10`
- `0x140016c10`
- `0x14001eba8`
- `0x1401040e0`
- `0x140104ce0`

## import_xrefs

- `ntdll!VerSetConditionMask` at `0x140011664`
- `ntdll!VerSetConditionMask` at `0x140011664`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400115cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400115cb`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140011688`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x1400116a9`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140011688`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x1400116a9`
- `USERENV!GetProfileType` at `0x1400116cc`
- `USERENV!GetProfileType` at `0x1400116cc`

## string_xrefs

- `0x1400116e6`: `shell\lib\logontasks\logontasks.cpp`
- `0x140011734`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400117c5`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c

```
