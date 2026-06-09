# OrchestratorDelete_0

- ea: `0x180002c20`
- end: `0x180002c26`
- name: `OrchestratorDelete_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `DeclaredConfigurationAPI!OrchestratorDelete` at `0x180002c20`

## pseudocode

```c
// attributes: thunk
__int64 OrchestratorDelete_0()
{
  return OrchestratorDelete();
}

```

## disassembly

```asm
0x180002c20  jmp     cs:__imp_OrchestratorDelete
```
