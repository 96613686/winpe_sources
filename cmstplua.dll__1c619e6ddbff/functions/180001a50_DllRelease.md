# DllRelease

- ea: `0x180001a50`
- end: `0x180001a58`
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
  _InterlockedDecrement(&dword_180006640);
}

```

## disassembly

```asm
0x180001a50  lock dec cs:dword_180006640
0x180001a57  retn
```
