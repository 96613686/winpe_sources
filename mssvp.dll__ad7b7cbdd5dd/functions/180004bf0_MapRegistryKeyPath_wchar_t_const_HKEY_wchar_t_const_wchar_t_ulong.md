# MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)

- ea: `0x180004bf0`
- end: `0x180004c58`
- name: `?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z`
- size: `104`
- prototype: `bool(const wchar_t *, HKEY, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005754`

## callees

- `0x180004bf0`
- `0x18003833c`
- `0x180038474`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180004c1c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180004c1c`

## pseudocode

```c

```
