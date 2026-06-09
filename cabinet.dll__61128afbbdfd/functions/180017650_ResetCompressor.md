# ResetCompressor

- ea: `0x180017650`
- end: `0x18001765a`
- name: `ResetCompressor`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180017660`

## pseudocode

```c
__int64 __fastcall ResetCompressor(__int64 a1)
{
  return ResetCompressorOrDecompressor(a1, 1);
}

```

## disassembly

```asm
0x180017650  mov     edx, 1
0x180017655  jmp     ResetCompressorOrDecompressor
```
