# StatusFromResultAndError

- ea: `0x140013b10`
- end: `0x140013b9d`
- name: `StatusFromResultAndError`
- size: `141`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400128bc`
- `0x140012b20`
- `0x140012dc4`
- `0x140012f5c`

## callees

- `0x140013b10`

## pseudocode

```c
__int64 __fastcall StatusFromResultAndError(unsigned __int16 a1, __int16 a2)
{
  if ( a1 <= 6u )
  {
    if ( a1 == 6 )
      return 3221299239LL;
    if ( a1 == 1 )
      return 3221299241LL;
    if ( a1 != 2 )
    {
      if ( a1 == 3 || (unsigned int)a1 - 4 <= 1 )
        return 3221299243LL;
      return 3221299241LL;
    }
    if ( a2 == 1 || a2 == 2 || a2 == 3 || a2 == 4 )
      return 3221299243LL;
    if ( a2 != 7 )
      return 3221299234LL;
    return 3221299237LL;
  }
  switch ( a1 )
  {
    case 7u:
      return 3221299243LL;
    case 8u:
      return 3221299237LL;
    case 9u:
    case 0xAu:
      return 3221299243LL;
  }
  if ( a1 != 11 )
    return 3221299241LL;
  return 3221299242LL;
}

```

## disassembly

```asm
0x140013b10  movzx   r8d, cx
0x140013b14  cmp     r8d, 6
0x140013b18  ja      short loc_140013B6B
0x140013b1a  jz      short loc_140013B64
0x140013b1c  sub     r8d, 1
0x140013b20  jz      short loc_140013B89
0x140013b22  sub     r8d, 1
0x140013b26  jz      short loc_140013B41
0x140013b28  sub     r8d, 1
0x140013b2c  jz      short loc_140013B3A
0x140013b2e  sub     r8d, 1
0x140013b32  jz      short loc_140013B3A
0x140013b34  cmp     r8d, 1
0x140013b38  jnz     short loc_140013B89
0x140013b3a  mov     eax, 0C001202Bh
0x140013b3f  retn
0x140013b41  movzx   ecx, dx
0x140013b44  sub     ecx, 1
0x140013b47  jz      short loc_140013B3A
0x140013b49  sub     ecx, 1
0x140013b4c  jz      short loc_140013B3A
0x140013b4e  sub     ecx, 1
0x140013b51  jz      short loc_140013B3A
0x140013b53  sub     ecx, 1
0x140013b56  jz      short loc_140013B3A
0x140013b58  cmp     ecx, 3
0x140013b5b  jz      short loc_140013B97
0x140013b5d  mov     eax, 0C0012022h
0x140013b62  retn
0x140013b64  mov     eax, 0C0012027h
0x140013b69  retn
0x140013b6b  sub     r8d, 7
0x140013b6f  jz      short loc_140013B3A
0x140013b71  sub     r8d, 1
0x140013b75  jz      short loc_140013B97
0x140013b77  sub     r8d, 1
0x140013b7b  jz      short loc_140013B3A
0x140013b7d  sub     r8d, 1
0x140013b81  jz      short loc_140013B3A
0x140013b83  cmp     r8d, 1
0x140013b87  jz      short loc_140013B90
0x140013b89  mov     eax, 0C0012029h
0x140013b8e  retn
0x140013b90  mov     eax, 0C001202Ah
0x140013b95  retn
0x140013b97  mov     eax, 0C0012025h
0x140013b9c  retn
```
