# CreateDecompressor

- ea: `0x180011f50`
- end: `0x180011f58`
- name: `CreateDecompressor`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011f60`

## pseudocode

```c
__int64 __fastcall CreateDecompressor(int a1, __int64 a2, __int64 *a3)
{
  return CreateCompressorOrDecompressor(a1, a2, a3, 0);
}

```

## disassembly

```asm
0x180011f50  xor     r9d, r9d
0x180011f53  jmp     CreateCompressorOrDecompressor
```
