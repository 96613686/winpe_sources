# CreateStateChangeNotification

- ea: `0x180006ab0`
- end: `0x180006ab6`
- name: `CreateStateChangeNotification`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!CreateStateChangeNotification` at `0x180006ab0`

## pseudocode

```c
// attributes: thunk
__int64 CreateStateChangeNotification()
{
  return __imp_CreateStateChangeNotification();
}

```

## disassembly

```asm
0x180006ab0  jmp     cs:__imp_CreateStateChangeNotification
```
