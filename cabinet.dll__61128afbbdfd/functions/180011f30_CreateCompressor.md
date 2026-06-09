# CreateCompressor

- ea: `0x180011f30`
- end: `0x180011f3b`
- name: `CreateCompressor`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011f60`

## pseudocode

```c
__int64 __fastcall CreateCompressor(int a1, __int64 a2, __int64 *a3)
{
  return CreateCompressorOrDecompressor(a1, a2, a3, 1);
}

```

## disassembly

```asm
0x180011f30  mov     r9d, 1
0x180011f36  jmp     CreateCompressorOrDecompressor
```
