# D3D12PIXEventsReplaceBlock

- ea: `0x180010760`
- end: `0x180010765`
- name: `D3D12PIXEventsReplaceBlock`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180012e30`

## pseudocode

```c
// attributes: thunk
LARGE_INTEGER __fastcall D3D12PIXEventsReplaceBlock(char a1)
{
  return PIXEventsReplaceBlockImpl(a1);
}

```

## disassembly

```asm
0x180010760  jmp     ?PIXEventsReplaceBlockImpl@@YA_K_N@Z; PIXEventsReplaceBlockImpl(bool)
```
