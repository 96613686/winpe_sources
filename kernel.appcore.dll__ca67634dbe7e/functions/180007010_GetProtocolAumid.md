# GetProtocolAumid

- ea: `0x180007010`
- end: `0x180007016`
- name: `GetProtocolAumid`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNELBASE!GetProtocolAumid` at `0x180007010`

## pseudocode

```c
// attributes: thunk
__int64 GetProtocolAumid()
{
  return __imp_GetProtocolAumid();
}

```

## disassembly

```asm
0x180007010  jmp     cs:__imp_GetProtocolAumid
```
