# CloseCompressor

- ea: `0x180011710`
- end: `0x18001171a`
- name: `CloseCompressor`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011760`

## pseudocode

```c
__int64 __fastcall CloseCompressor(__int64 a1)
{
  return CloseCompressorOrDecompressor(a1, 1);
}

```

## disassembly

```asm
0x180011710  mov     edx, 1
0x180011715  jmp     CloseCompressorOrDecompressor
```
