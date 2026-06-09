# GetNextToken(ushort const * &,unsigned __int64 &)

- ea: `0x1400053a0`
- end: `0x140005489`
- name: `?GetNextToken@@YAPEBGAEAPEBGAEA_K@Z`
- size: `233`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011e4`

## callees

- `0x1400053a0`

## pseudocode

```c
const unsigned __int16 *__fastcall GetNextToken(const unsigned __int16 **a1, unsigned __int64 *a2)
{
  const unsigned __int16 *v2; // rax
  unsigned __int16 v5; // r8
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r10
  bool v8; // r11
  char v9; // cl
  unsigned __int16 v10; // ax
  const unsigned __int16 *result; // rax

  v2 = *a1;
  *a2 = 0;
  if ( !v2 )
    return 0;
  v5 = *v2;
  if ( !*v2 )
    return 0;
  while ( v5 == 32 || v5 == 9 )
  {
    *a1 = ++v2;
    v6 = v2;
    v5 = *v2;
    if ( !*v2 )
      goto LABEL_8;
  }
  v5 = *v2;
  v6 = v2;
LABEL_8:
  if ( !v5 )
    return 0;
  v7 = v6 + 1;
  v8 = 0;
  for ( *a1 = v6 + 1; ; *a1 = v7 )
  {
    v10 = *v7;
    if ( !*v7 )
      break;
    if ( v10 == 32 || (v9 = 0, v10 == 9) )
      v9 = 1;
    if ( v9 || v10 == 34 )
    {
      if ( v5 == 34 )
      {
        if ( v10 == 34 )
          goto LABEL_25;
      }
      else if ( v10 == 34 )
      {
        v8 = !v8;
      }
      else if ( v9 && !v8 )
      {
        goto LABEL_27;
      }
    }
    ++v7;
  }
  if ( v5 != 34 )
    goto LABEL_27;
LABEL_25:
  if ( **a1 )
    ++*a1;
LABEL_27:
  result = v6;
  *a2 = *a1 - v6;
  return result;
}

```

## disassembly

```asm
0x1400053a0  push    rbx
0x1400053a2  push    rsi
0x1400053a3  push    rdi
0x1400053a4  mov     rax, [rcx]
0x1400053a7  xor     edi, edi
0x1400053a9  mov     [rdx], rdi
0x1400053ac  mov     rbx, rdx
0x1400053af  mov     r9, rcx
0x1400053b2  test    rax, rax
0x1400053b5  jz      loc_140005483
0x1400053bb  movzx   r8d, word ptr [rax]
0x1400053bf  test    r8w, r8w
0x1400053c3  jz      loc_140005483
0x1400053c9  cmp     r8w, 20h ; ' '
0x1400053ce  jz      short loc_1400053D7
0x1400053d0  cmp     r8w, 9
0x1400053d5  jnz     short loc_1400053ED
0x1400053d7  add     rax, 2
0x1400053db  mov     [rcx], rax
0x1400053de  mov     rdx, rax
0x1400053e1  movzx   r8d, word ptr [rax]
0x1400053e5  test    r8w, r8w
0x1400053e9  jnz     short loc_1400053C9
0x1400053eb  jmp     short loc_1400053F4
0x1400053ed  movzx   r8d, word ptr [rax]
0x1400053f1  mov     rdx, rax
0x1400053f4  test    r8w, r8w
0x1400053f8  jz      loc_140005483
0x1400053fe  lea     r10, [rdx+2]
0x140005402  mov     r11b, dil
0x140005405  mov     [rcx], r10
0x140005408  mov     esi, 22h ; '"'
0x14000540d  jmp     short loc_140005454
0x14000540f  cmp     ax, 20h ; ' '
0x140005413  jz      short loc_14000541E
0x140005415  mov     cl, dil
0x140005418  cmp     ax, 9
0x14000541c  jnz     short loc_140005420
0x14000541e  mov     cl, 1
0x140005420  test    cl, cl
0x140005422  jnz     short loc_140005429
0x140005424  cmp     si, ax
0x140005427  jnz     short loc_14000544D
0x140005429  cmp     si, r8w
0x14000542d  jz      short loc_140005448
0x14000542f  cmp     si, ax
0x140005432  jnz     short loc_14000543D
0x140005434  test    r11b, r11b
0x140005437  setz    r11b
0x14000543b  jmp     short loc_14000544D
0x14000543d  test    cl, cl
0x14000543f  jz      short loc_14000544D
0x140005441  test    r11b, r11b
0x140005444  jz      short loc_140005472
0x140005446  jmp     short loc_14000544D
0x140005448  cmp     si, ax
0x14000544b  jz      short loc_140005463
0x14000544d  add     r10, 2
0x140005451  mov     [r9], r10
0x140005454  movzx   eax, word ptr [r10]
0x140005458  test    ax, ax
0x14000545b  jnz     short loc_14000540F
0x14000545d  cmp     si, r8w
0x140005461  jnz     short loc_140005472
0x140005463  mov     rcx, [r9]
0x140005466  cmp     [rcx], di
0x140005469  jz      short loc_140005472
0x14000546b  add     rcx, 2
0x14000546f  mov     [r9], rcx
0x140005472  mov     rcx, [r9]
0x140005475  mov     rax, rdx
0x140005478  sub     rcx, rdx
0x14000547b  sar     rcx, 1
0x14000547e  mov     [rbx], rcx
0x140005481  jmp     short loc_140005485
0x140005483  xor     eax, eax
0x140005485  pop     rdi
0x140005486  pop     rsi
0x140005487  pop     rbx
0x140005488  retn
```
