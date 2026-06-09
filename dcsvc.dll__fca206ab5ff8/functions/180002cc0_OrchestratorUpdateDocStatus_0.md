# OrchestratorUpdateDocStatus_0

- ea: `0x180002cc0`
- end: `0x180002cc6`
- name: `OrchestratorUpdateDocStatus_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update`

## import_xrefs

- `DeclaredConfigurationAPI!OrchestratorUpdateDocStatus` at `0x180002cc0`

## pseudocode

```c
// attributes: thunk
__int64 OrchestratorUpdateDocStatus_0()
{
  return OrchestratorUpdateDocStatus();
}

```

## disassembly

```asm
0x180002cc0  jmp     cs:__imp_OrchestratorUpdateDocStatus
```
