# EndpointDlp::WindowsPlatformApi::ProcessDlpUserEvaluationIds(void)

- ea: `0x180065aac`
- end: `0x180066130`
- name: `?ProcessDlpUserEvaluationIds@WindowsPlatformApi@EndpointDlp@@AEAAXXZ`
- size: `1668`
- prototype: `void __fastcall(EndpointDlp::WindowsPlatformApi *__hidden this)`
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config`

## callers

- `0x1800bb210`
- `0x180180dd0`

## callees

- `0x180002c84`
- `0x1800058a4`
- `0x18001f980`
- `0x18002140c`
- `0x180024930`
- `0x180024ac0`
- `0x18002c150`
- `0x1800301a0`
- `0x180034420`
- `0x180038450`
- `0x18003ac80`
- `0x180040290`
- `0x180065aac`
- `0x180066480`
- `0x180067384`
- `0x18006782c`
- `0x180070e30`
- `0x1800ad914`
- `0x1800b8f00`
- `0x1800b8f2c`
- `0x1800cb88c`
- `0x180102c74`
- `0x1801034d4`
- `0x1801035d0`
- `0x180103640`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18023a290`
- `0x18023a310`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180065b84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180065ce9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180065b84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180065ce9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180065d39`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180065d39`
- `ADVAPI32!RegCloseKey` at `0x180065be9`
- `ADVAPI32!RegCloseKey` at `0x180065c88`
- `ADVAPI32!RegCloseKey` at `0x180065d60`
- `ADVAPI32!RegCloseKey` at `0x180066102`
- `ADVAPI32!RegCloseKey` at `0x180065be9`
- `ADVAPI32!RegCloseKey` at `0x180065c88`
- `ADVAPI32!RegCloseKey` at `0x180065d60`
- `ADVAPI32!RegCloseKey` at `0x180066102`

## string_xrefs

- `0x180065c37`: `Failed to enumerate evaluation id registry sub keys`
- `0x180065def`: `Failed to open user evaluation id key`
- `0x180065e96`: `Failed to read user evaluation id value`
- `0x180065b42`: `Failed to open user evaluation id registry key`

## pseudocode

```c

```
