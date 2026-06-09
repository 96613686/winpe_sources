# SetProtocolProperty

- ea: `0x180007560`
- end: `0x180007566`
- name: `SetProtocolProperty`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNELBASE!SetProtocolProperty` at `0x180007560`

## pseudocode

```c
// attributes: thunk
__int64 SetProtocolProperty()
{
  return __imp_SetProtocolProperty();
}

```

## disassembly

```asm
0x180007560  jmp     cs:__imp_SetProtocolProperty
```
