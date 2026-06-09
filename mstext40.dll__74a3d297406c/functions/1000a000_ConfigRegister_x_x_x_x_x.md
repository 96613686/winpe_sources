# ConfigRegister(x,x,x,x,x)

- ea: `0x1000a000`
- end: `0x1000a005`
- name: `_ConfigRegister@20`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x10015100`

## pseudocode

```c
int __stdcall ConfigRegister(int a1, int a2, int a3, int a4, int a5)
{
  return 0;
}

```

## disassembly

```asm
0x1000a000  xor     eax, eax
0x1000a002  retn    14h
```
