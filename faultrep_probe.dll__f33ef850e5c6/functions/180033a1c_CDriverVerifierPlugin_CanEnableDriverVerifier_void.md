# CDriverVerifierPlugin::CanEnableDriverVerifier(void)

- ea: `0x180033a1c`
- end: `0x180033ae5`
- name: `?CanEnableDriverVerifier@CDriverVerifierPlugin@@AEAAHXZ`
- size: `201`
- prototype: `__int64 __fastcall(CDriverVerifierPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033de0`

## callees

- `0x180002890`
- `0x180003474`
- `0x180009f00`
- `0x180033a1c`
- `0x180036e08`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180033a5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180033a5c`

## string_xrefs

- `0x180033a85`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\DriverVerifier`

## pseudocode

```c

```
