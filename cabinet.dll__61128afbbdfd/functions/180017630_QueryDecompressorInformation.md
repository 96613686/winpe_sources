# QueryDecompressorInformation

- ea: `0x180017630`
- end: `0x180017646`
- name: `QueryDecompressorInformation`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800175ac`

## pseudocode

```c
__int64 __fastcall QueryDecompressorInformation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return QueryCompressorOrDecompressorInformation(a1, a2, a3, a4, 0);
}

```

## disassembly

```asm
0x180017630  sub     rsp, 38h
0x180017634  mov     [rsp+38h+var_18], 0
0x18001763c  call    QueryCompressorOrDecompressorInformation
0x180017641  add     rsp, 38h
0x180017645  retn
```
