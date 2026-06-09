# CbsUtilInstanceCreated

- ea: `0x140024a50`
- end: `0x140024a58`
- name: `CbsUtilInstanceCreated`
- size: `8`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void CbsUtilInstanceCreated()
{
  _InterlockedIncrement(&dword_1400504D4);
}

```

## disassembly

```asm
0x140024a50  lock inc cs:dword_1400504D4
0x140024a57  retn
```
