# MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)

- ea: `0x18000cbac`
- end: `0x18000cc14`
- name: `?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z`
- size: `104`
- prototype: `bool(const wchar_t *, HKEY, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f220`

## callees

- `0x18000cbac`
- `0x18001ff2c`
- `0x180020064`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000cbd8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000cbd8`

## pseudocode

```c

```
