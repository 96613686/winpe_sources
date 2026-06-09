# CLogonTaskFramework::s_IsSpecialRoamingProfile(void)

- ea: `0x1400480b8`
- end: `0x140048394`
- name: `?s_IsSpecialRoamingProfile@CLogonTaskFramework@@CA_NXZ`
- size: `732`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140046e8c`

## callees

- `0x14001b2c8`
- `0x14001c028`
- `0x14001c330`
- `0x14001c440`
- `0x1400480b8`
- `0x14004856c`
- `0x1400485bc`
- `0x140048604`
- `0x1400488ac`
- `0x14010e160`
- `0x14010ed90`

## import_xrefs

- `ntdll!VerSetConditionMask` at `0x1400481ca`
- `ntdll!VerSetConditionMask` at `0x1400481ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140048127`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140048127`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x1400481f4`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x14004821b`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x1400481f4`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x14004821b`
- `USERENV!GetProfileType` at `0x140048244`
- `USERENV!GetProfileType` at `0x140048244`

## string_xrefs

- `0x140048264`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400482b2`: `shell\lib\logontasks\logontasks.cpp`
- `0x140048343`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c

```
