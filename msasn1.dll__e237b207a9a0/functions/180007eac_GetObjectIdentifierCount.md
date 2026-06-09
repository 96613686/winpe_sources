# GetObjectIdentifierCount

- ea: `0x180007eac`
- end: `0x180007ebb`
- name: `GetObjectIdentifierCount`
- size: `15`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800074e0`
- `0x18000a490`

## callees

- `0x180007eac`

## pseudocode

```c
__int64 __fastcall GetObjectIdentifierCount(_QWORD *a1)
{
  __int64 result; // rax

  result = 0;
  while ( a1 )
  {
    a1 = (_QWORD *)*a1;
    result = (unsigned int)(result + 1);
  }
  return result;
}

```

## disassembly

```asm
0x180007eac  xor     eax, eax
0x180007eae  jmp     short loc_180007EB5
0x180007eb0  mov     rcx, [rcx]
0x180007eb3  inc     eax
0x180007eb5  test    rcx, rcx
0x180007eb8  jnz     short loc_180007EB0
0x180007eba  retn
```
