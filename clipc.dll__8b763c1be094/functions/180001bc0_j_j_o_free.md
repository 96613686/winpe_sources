# j_j__o_free

- ea: `0x180001bc0`
- end: `0x180001bc5`
- name: `j_j__o_free`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a370`
- `0x18001a400`
- `0x180023820`
- `0x180023de4`

## callees

- `0x18000208c`

## pseudocode

```c
// attributes: thunk
__int64 j_j__o_free()
{
  return j__o_free();
}

```

## disassembly

```asm
0x180001bc0  jmp     j__o_free
```
