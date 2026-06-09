# ResetDecompressor

- ea: `0x1800176d0`
- end: `0x1800176d7`
- name: `ResetDecompressor`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180017660`

## pseudocode

```c
__int64 __fastcall ResetDecompressor(__int64 a1)
{
  return ResetCompressorOrDecompressor(a1, 0);
}

```

## disassembly

```asm
0x1800176d0  xor     edx, edx
0x1800176d2  jmp     ResetCompressorOrDecompressor
```
