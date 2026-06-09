# CloseDecompressor

- ea: `0x180011750`
- end: `0x180011757`
- name: `CloseDecompressor`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011760`

## pseudocode

```c
__int64 __fastcall CloseDecompressor(__int64 a1)
{
  return CloseCompressorOrDecompressor(a1, 0);
}

```

## disassembly

```asm
0x180011750  xor     edx, edx
0x180011752  jmp     CloseCompressorOrDecompressor
```
