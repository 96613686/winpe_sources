# BfsGetRootDirectory

- ea: `0x14001e008`
- end: `0x14001e010`
- name: `BfsGetRootDirectory`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140008ecc`
- `0x14000cb34`

## pseudocode

```c
HANDLE BfsGetRootDirectory()
{
  return gBfsRootDirectory;
}

```

## disassembly

```asm
0x14001e008  mov     rax, cs:gBfsRootDirectory
0x14001e00f  retn
```
