# ISAMDBTaskList()

- ea: `0x100147c0`
- end: `0x100147c6`
- name: `_ISAMDBTaskList@0`
- size: `6`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x10011d90`

## pseudocode

```c
int __stdcall ISAMDBTaskList()
{
  return dword_10040FBC;
}

```

## disassembly

```asm
0x100147c0  mov     eax, dword_10040FBC
0x100147c5  retn
```
