# FindLastWCharInStr(ushort const *,ushort)

- ea: `0x1400084f8`
- end: `0x140008529`
- name: `?FindLastWCharInStr@@YAPEBGPEBGG@Z`
- size: `49`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 *, unsigned __int16)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400058b4`
- `0x14000e830`
- `0x140012a00`
- `0x140012f20`

## callees

- `0x1400084f8`

## pseudocode

```c
const unsigned __int16 *__fastcall FindLastWCharInStr(const unsigned __int16 *a1, __int16 a2)
{
  const unsigned __int16 *v2; // r8
  const unsigned __int16 *result; // rax
  unsigned __int16 i; // r9
  const unsigned __int16 *v5; // rcx

  v2 = a1;
  result = 0;
  if ( a1 )
  {
    for ( i = *a1; i; i = *v2 )
    {
      v5 = v2;
      if ( i != a2 )
        v5 = result;
      ++v2;
      result = v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400084f8  xor     r10d, r10d
0x1400084fb  mov     r8, rcx
0x1400084fe  mov     eax, r10d
0x140008501  test    rcx, rcx
0x140008504  jz      short locret_140008528
0x140008506  movzx   r9d, word ptr [rcx]
0x14000850a  jmp     short loc_140008522
0x14000850c  cmp     r9w, dx
0x140008510  mov     rcx, r8
0x140008513  cmovnz  rcx, rax
0x140008517  add     r8, 2
0x14000851b  mov     rax, rcx
0x14000851e  movzx   r9d, word ptr [r8]
0x140008522  test    r9w, r9w
0x140008526  jnz     short loc_14000850C
0x140008528  retn
```
