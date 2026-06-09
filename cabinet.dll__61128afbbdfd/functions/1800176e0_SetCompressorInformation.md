# SetCompressorInformation

- ea: `0x1800176e0`
- end: `0x1800176f6`
- name: `SetCompressorInformation`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800176fc`

## pseudocode

```c
__int64 __fastcall SetCompressorInformation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return SetCompressorOrDecompressorInformation(a1, a2, a3, a4, 1u);
}

```

## disassembly

```asm
0x1800176e0  sub     rsp, 38h
0x1800176e4  mov     [rsp+38h+var_18], 1
0x1800176ec  call    SetCompressorOrDecompressorInformation
0x1800176f1  add     rsp, 38h
0x1800176f5  retn
```
