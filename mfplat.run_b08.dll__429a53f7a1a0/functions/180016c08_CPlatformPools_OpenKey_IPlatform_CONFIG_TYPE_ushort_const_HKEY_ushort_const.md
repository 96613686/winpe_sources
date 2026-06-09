# CPlatformPools::OpenKey(IPlatform::CONFIG_TYPE,ushort const *,HKEY__ * *,ushort const * *)

- ea: `0x180016c08`
- end: `0x180016ebb`
- name: `?OpenKey@CPlatformPools@@QEAAJW4CONFIG_TYPE@IPlatform@@PEBGPEAPEAUHKEY__@@PEAPEBG@Z`
- size: `691`
- prototype: `int(CPlatformPools *__hidden this, enum IPlatform::CONFIG_TYPE, const unsigned __int16 *, HKEY *, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180016918`
- `0x180128770`

## callees

- `0x180016c08`
- `0x180016f88`
- `0x180016ff4`
- `0x18001721c`
- `0x180019124`
- `0x1800875a8`
- `0x180121581`
- `0x180128900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180016c57`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180016c57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016d95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016d95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016cc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016cc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016cb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016cb2`

## pseudocode

```c

```
