# operator delete(void *)

- ea: `0x180004fbc`
- end: `0x180004fc1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003010`
- `0x1800036d0`
- `0x180003950`
- `0x180003db0`
- `0x180003fb0`
- `0x180004000`
- `0x180004150`
- `0x180004220`
- `0x1800047e0`
- `0x180006680`
- `0x180008a60`
- `0x180008bec`
- `0x180008fb0`
- `0x180008ff0`
- `0x180009580`
- `0x1800099d0`
- `0x180009c40`

## callees

- `0x1800054d6`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180004fbc  jmp     free_0
```
