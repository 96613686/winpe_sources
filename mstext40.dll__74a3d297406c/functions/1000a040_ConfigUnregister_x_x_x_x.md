# ConfigUnregister(x,x,x,x)

- ea: `0x1000a040`
- end: `0x1000a045`
- name: `_ConfigUnregister@16`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x100151e0`

## pseudocode

```c
int __stdcall ConfigUnregister(int a1, int a2, int a3, int a4)
{
  return 0;
}

```

## disassembly

```asm
0x1000a040  xor     eax, eax
0x1000a042  retn    10h
```
