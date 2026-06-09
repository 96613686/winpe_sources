# ExdiComponentCmd(_DOT_COMMAND *,DebugClient *)

- ea: `0x1801fb030`
- end: `0x1801fb1b4`
- name: `?ExdiComponentCmd@@YAXPEAU_DOT_COMMAND@@PEAVDebugClient@@@Z`
- size: `388`
- prototype: `void __fastcall(struct _DOT_COMMAND *, struct DebugClient *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800727b8`
- `0x1800b94c4`
- `0x1800c1150`
- `0x1800f2560`
- `0x1800f2998`
- `0x1801fb030`
- `0x180281aac`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_set_errno` at `0x1801fb0e0`
- `api-ms-win-crt-runtime-l1-1-0!_set_errno` at `0x1801fb0e0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801fb0fd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801fb10e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801fb0fd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801fb10e`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1801fb0ef`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1801fb0ef`

## string_xrefs

- `0x1801fb08d`: `component:`
- `0x1801fb180`: `This command passes the parameters directly through to an eXDI component.\nSee the documentation for your eXDI component for more information.\nNot all eXDI components have this function implemented\nValid parameters are:\ncomponent:*:<string>         Execute a Exdi component <string> function on all processor cores.\ncomponent:<n>:<string>       Execute a Exdi component <string> function on the processor core n (n-decimal number).\ntarget:*:<string>            Pass through the <string> function`

## pseudocode

```c

```
