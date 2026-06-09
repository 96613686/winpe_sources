# ASN1BERDecOpenType

- ea: `0x1800026a0`
- end: `0x1800026a8`
- name: `ASN1BERDecOpenType`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800026b0`

## pseudocode

```c
__int64 __fastcall ASN1BERDecOpenType(__int64 a1, unsigned int *a2)
{
  return BERDecOpenType(a1, a2, 0);
}

```

## disassembly

```asm
0x1800026a0  xor     r8d, r8d
0x1800026a3  jmp     _BERDecOpenType
```
