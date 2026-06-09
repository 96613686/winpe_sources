# FileStream::Commit(ulong)

- ea: `0x180006780`
- end: `0x180006783`
- name: `?Commit@FileStream@@UEAAJK@Z`
- size: `3`
- prototype: `__int64 __fastcall(FileStream *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001764`

## pseudocode

```c
__int64 __fastcall FileStream::Commit(FileStream *this)
{
  return 0;
}

```

## disassembly

```asm
0x180006780  xor     eax, eax
0x180006782  retn
```
