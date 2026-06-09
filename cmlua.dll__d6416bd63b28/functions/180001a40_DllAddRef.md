# DllAddRef

- ea: `0x180001a40`
- end: `0x180001a48`
- name: `DllAddRef`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
void DllAddRef()
{
  _InterlockedIncrement(&dword_18000C6C0);
}

```

## disassembly

```asm
0x180001a40  lock inc cs:dword_18000C6C0
0x180001a47  retn
```
