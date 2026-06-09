# DebuggerSettings::ReadSettings(IXmlReader *,bool &)

- ea: `0x180378430`
- end: `0x180378612`
- name: `?ReadSettings@DebuggerSettings@@CAJPEAUIXmlReader@@AEA_N@Z`
- size: `482`
- prototype: `__int64 __fastcall(struct IXmlReader *, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1801bdf10`
- `0x180378618`

## callees

- `0x1801974a0`
- `0x180378430`
- `0x18037879c`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1803784d1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1803784d1`
- `api-ms-win-crt-convert-l1-1-0!wcstol` at `0x18037852f`
- `api-ms-win-crt-convert-l1-1-0!wcstol` at `0x18037852f`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18037859e`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18037859e`
- `dbghelp!SymSetExtendedOption` at `0x1803785ff`
- `dbghelp!SymSetExtendedOption` at `0x1803785ff`

## string_xrefs

- `0x180378595`: `DBGENG_ENABLE_NEGATIVE_AUTH_CACHE_FEATURE`
- `0x1803785d6`: `Symbols negative authentication cache feature setup by env var value, enabled: '%ls'`

## pseudocode

```c

```
