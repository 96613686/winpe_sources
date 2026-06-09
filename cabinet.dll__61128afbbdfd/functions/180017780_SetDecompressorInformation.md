# SetDecompressorInformation

- ea: `0x180017780`
- end: `0x180017796`
- name: `SetDecompressorInformation`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800176fc`

## pseudocode

```c
__int64 __fastcall SetDecompressorInformation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return SetCompressorOrDecompressorInformation(a1, a2, a3, a4, 0);
}

```

## disassembly

```asm
0x180017780  sub     rsp, 38h
0x180017784  mov     [rsp+38h+var_18], 0
0x18001778c  call    SetCompressorOrDecompressorInformation
0x180017791  add     rsp, 38h
0x180017795  retn
```
