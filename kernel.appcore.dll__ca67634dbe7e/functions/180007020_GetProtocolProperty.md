# GetProtocolProperty

- ea: `0x180007020`
- end: `0x180007026`
- name: `GetProtocolProperty`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNELBASE!GetProtocolProperty` at `0x180007020`

## pseudocode

```c
// attributes: thunk
__int64 GetProtocolProperty()
{
  return __imp_GetProtocolProperty();
}

```

## disassembly

```asm
0x180007020  jmp     cs:__imp_GetProtocolProperty
```
