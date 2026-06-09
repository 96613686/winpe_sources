# RasRpcUnloadDll

- ea: `0x180023a50`
- end: `0x180023a56`
- name: `RasRpcUnloadDll`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 RasRpcUnloadDll()
{
  return 50;
}

```

## disassembly

```asm
0x180023a50  mov     eax, 32h ; '2'
0x180023a55  retn
```
