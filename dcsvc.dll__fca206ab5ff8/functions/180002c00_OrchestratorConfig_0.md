# OrchestratorConfig_0

- ea: `0x180002c00`
- end: `0x180002c06`
- name: `OrchestratorConfig_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `DeclaredConfigurationAPI!OrchestratorConfig` at `0x180002c00`

## pseudocode

```c
// attributes: thunk
__int64 OrchestratorConfig_0()
{
  return OrchestratorConfig();
}

```

## disassembly

```asm
0x180002c00  jmp     cs:__imp_OrchestratorConfig
```
