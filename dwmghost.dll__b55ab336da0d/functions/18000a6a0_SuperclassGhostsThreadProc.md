# SuperclassGhostsThreadProc

- ea: `0x18000a6a0`
- end: `0x18000a6a5`
- name: `SuperclassGhostsThreadProc`
- size: `5`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a5e8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall SuperclassGhostsThreadProc(LONG_PTR Parameter)
{
  return SuperclassGhosts(Parameter);
}

```

## disassembly

```asm
0x18000a6a0  jmp     SuperclassGhosts
```
