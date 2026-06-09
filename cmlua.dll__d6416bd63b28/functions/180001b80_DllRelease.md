# DllRelease

- ea: `0x180001b80`
- end: `0x180001b88`
- name: `DllRelease`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
void DllRelease()
{
  _InterlockedDecrement(&dword_18000C6C0);
}

```

## disassembly

```asm
0x180001b80  lock dec cs:dword_18000C6C0
0x180001b87  retn
```
