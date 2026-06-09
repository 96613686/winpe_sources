# RtlStringExValidateDestW

- ea: `0x180009228`
- end: `0x180009251`
- name: `RtlStringExValidateDestW`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f00`
- `0x18000908c`

## callees

- `0x180009228`

## pseudocode

```c
__int64 __fastcall RtlStringExValidateDestW(__int64 a1, unsigned __int64 a2, __int64 a3, __int16 a4)
{
  __int64 result; // rax

  result = 0;
  if ( (a4 & 0x100) != 0 )
  {
    if ( a1 || !a2 )
    {
LABEL_6:
      if ( a2 <= 0x7FFFFFFF )
        return result;
    }
  }
  else if ( a2 )
  {
    goto LABEL_6;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180009228  xor     eax, eax
0x18000922a  bt      r9d, 8
0x18000922f  jnb     short loc_18000923D
0x180009231  test    rcx, rcx
0x180009234  jnz     short loc_180009242
0x180009236  test    rdx, rdx
0x180009239  jnz     short loc_18000924B
0x18000923b  jmp     short loc_180009242
0x18000923d  test    rdx, rdx
0x180009240  jz      short loc_18000924B
0x180009242  cmp     rdx, 7FFFFFFFh
0x180009249  jbe     short locret_180009250
0x18000924b  mov     eax, 0C000000Dh
0x180009250  retn
```
