# OrchestratorDeleteInstanceVariables_0

- ea: `0x180002ca0`
- end: `0x180002ca6`
- name: `OrchestratorDeleteInstanceVariables_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `DeclaredConfigurationAPI!OrchestratorDeleteInstanceVariables` at `0x180002ca0`

## pseudocode

```c
// attributes: thunk
__int64 OrchestratorDeleteInstanceVariables_0()
{
  return OrchestratorDeleteInstanceVariables();
}

```

## disassembly

```asm
0x180002ca0  jmp     cs:__imp_OrchestratorDeleteInstanceVariables
```
