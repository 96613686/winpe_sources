# Connection::ReadConfigEntry(HKEY__ *,char *,char *,uchar *,uint)

- ea: `0x100747ba`
- end: `0x10074809`
- name: `?ReadConfigEntry@Connection@@AAEXPAUHKEY__@@PAD1PAEI@Z`
- size: `79`
- prototype: `void __thiscall(Connection *__hidden this, HKEY hKey, char *, LPCSTR lpValueName, LPBYTE lpData, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1007480f`

## callees

- `0x100747ba`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100747e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x100747e9`

## pseudocode

```c

```
