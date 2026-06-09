# OrchestratorUpdate_0

- ea: `0x180002cd0`
- end: `0x180002cd6`
- name: `OrchestratorUpdate_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update`

## import_xrefs

- `DeclaredConfigurationAPI!OrchestratorUpdate` at `0x180002cd0`

## pseudocode

```c
// attributes: thunk
__int64 OrchestratorUpdate_0()
{
  return OrchestratorUpdate();
}

```

## disassembly

```asm
0x180002cd0  jmp     cs:__imp_OrchestratorUpdate
```
