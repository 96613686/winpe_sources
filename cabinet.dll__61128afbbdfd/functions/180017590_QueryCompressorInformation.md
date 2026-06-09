# QueryCompressorInformation

- ea: `0x180017590`
- end: `0x1800175a6`
- name: `QueryCompressorInformation`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800175ac`

## pseudocode

```c
__int64 __fastcall QueryCompressorInformation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return QueryCompressorOrDecompressorInformation(a1, a2, a3, a4, 1u);
}

```

## disassembly

```asm
0x180017590  sub     rsp, 38h
0x180017594  mov     [rsp+38h+var_18], 1
0x18001759c  call    QueryCompressorOrDecompressorInformation
0x1800175a1  add     rsp, 38h
0x1800175a5  retn
```
