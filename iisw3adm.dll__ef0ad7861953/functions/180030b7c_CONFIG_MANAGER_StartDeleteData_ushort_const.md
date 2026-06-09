# CONFIG_MANAGER::StartDeleteData(ushort const *)

- ea: `0x180030b7c`
- end: `0x180030c97`
- name: `?StartDeleteData@CONFIG_MANAGER@@QEAAXPEBG@Z`
- size: `283`
- prototype: `void __fastcall(CONFIG_MANAGER *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ea9c`

## callees

- `0x180001234`
- `0x180001274`
- `0x180002bbc`
- `0x1800074b0`
- `0x1800077e8`
- `0x180007b60`
- `0x180030b7c`
- `0x18006101a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c1e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180030c80`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180030c80`
- `iisutil!PuDbgPrintError` at `0x180030c6d`
- `iisutil!PuDbgPrintError` at `0x180030c6d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180030bfd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180030bfd`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180030c07`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180030c07`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180030c77`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180030c77`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x180030c14`
- `iisutil!?FastAppend@MULTISZ@@QEAAHPEBG@Z` at `0x180030c14`

## string_xrefs

- `0x180030c62`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\changeprocessor.cxx`
- `0x180030c42`: `Couldn't queue DeleteDataThreadItemWorkItem\n`
- `0x180030c54`: `CHANGE_PROCESSOR::StartDeleteData`

## pseudocode

```c

```
