# DotEtwTrace(_DOT_COMMAND *,DebugClient *)

- ea: `0x1801f13c0`
- end: `0x1801f194b`
- name: `?DotEtwTrace@@YAXPEAU_DOT_COMMAND@@PEAVDebugClient@@@Z`
- size: `1419`
- prototype: `void __fastcall(struct _DOT_COMMAND *, struct DebugClient *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800727b8`
- `0x1800a14cc`
- `0x1800b94c4`
- `0x1800cac48`
- `0x1800ce308`
- `0x1800ee86c`
- `0x1800ee8a4`
- `0x1800f1750`
- `0x1801eb220`
- `0x1801eb840`
- `0x1801f13c0`
- `0x1801fb6f4`
- `0x1801fb760`
- `0x180280968`
- `0x180281aac`
- `0x1803a2c10`
- `0x1803a2ce8`
- `0x1803a2e2c`
- `0x1803a37d8`
- `0x1803a39a0`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f144d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f1495`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f14b7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f14dc`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f1524`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f159f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f15e1`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f144d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f1495`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f14b7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f14dc`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f1524`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f159f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801f15e1`

## string_xrefs

- `0x1801f1620`: `The command is valid only on Win8 or later OS versions.\n`
- `0x1801f181c`: `Session has already started, please stop current session \nusing .etwtrace -stop before starting a new one\n`
- `0x1801f16ad`: `Etw breakpoints allow you to break on an event. The break is currently asynchronous and for the debugged process,  unless the processId is passed in. The debugger is broken into once the ETW buffer has been flushed and the event has been consumed.\n  Add a breakpoint: .etwtrace -break add <{ProviderGuid}> <eventId> optional: <processId>\n  Clear breakpoint: .etwtrace -break clear <bpId> \n  List breakpoints: .etwtrace -break list\n`
- `0x1801f1927`: `This command allows the user to begin an ETW trace and see the output in the\ndebugger window.\nValid parameters are:\n-start <path_to_file.xml>  Starts trace session configured via WPR xml.\n-stop                      Stops the trace session.\n-help                      Display this help.\n-break                     Break on specific ETW event. See '.etwtrace -break help' for more options.\n`

## pseudocode

```c

```
