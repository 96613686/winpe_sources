# CompareSequence

- ea: `0x140013ba4`
- end: `0x140013bb1`
- name: `CompareSequence`
- size: `13`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013c74`
- `0x1400152b0`
- `0x1400154b8`
- `0x140015bbc`
- `0x140015d00`
- `0x140015fa8`
- `0x14001b8a0`

## callees

- `0x140013ba4`

## pseudocode

```c
__int64 __fastcall CompareSequence(__int16 a1, __int16 a2)
{
  unsigned __int16 v2; // cx

  v2 = a1 - a2;
  if ( v2 )
    return v2;
  else
    return 0;
}

```

## disassembly

```asm
0x140013ba4  sub     cx, dx
0x140013ba7  jnz     short loc_140013BAD
0x140013ba9  xor     eax, eax
0x140013bab  retn
0x140013bad  movzx   eax, cx
0x140013bb0  retn
```
