# AbortParse(IXMLNodeSource *,Exception *,Document *)

- ea: `0x1800f9778`
- end: `0x1800f9883`
- name: `?AbortParse@@YAJPEAUIXMLNodeSource@@PEAVException@@PEAVDocument@@@Z`
- size: `267`
- prototype: `int(struct IXMLNodeSource *, struct Exception *, struct Document *)`
- caller_count: `9`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180057b70`
- `0x1800f90c0`
- `0x1800f9210`
- `0x1800f9380`
- `0x1800f9530`
- `0x1800f991c`
- `0x1800f9c10`
- `0x1800f9d40`
- `0x1800f9e70`

## callees

- `0x18003cb74`
- `0x180064034`
- `0x18006dd8c`
- `0x1800f9778`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800f97f8`
- `msvcrt!_resetstkoflw` at `0x1800f97f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f984b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f984b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f97e6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f97e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f97ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f97ca`

## pseudocode

```c

```
