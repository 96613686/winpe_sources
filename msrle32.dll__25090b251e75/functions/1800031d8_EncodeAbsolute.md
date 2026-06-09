# EncodeAbsolute

- ea: `0x1800031d8`
- end: `0x180003282`
- name: `EncodeAbsolute`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003288`

## callees

- `0x1800031d8`

## pseudocode

```c
_WORD *__fastcall EncodeAbsolute(_WORD *a1, int a2, _WORD *a3, unsigned int a4, unsigned int *a5)
{
  int v5; // r10d
  __int16 v6; // ax
  _BYTE *v8; // r8

  if ( a2 >= 3 )
  {
    if ( a4 >= 2 )
    {
      *a3++ = (_WORD)a2 << 8;
      a4 -= 2;
      while ( a4 >= 2 )
      {
        a2 -= 2;
        *a3++ = *a1++;
        a4 -= 2;
        if ( a2 < 2 )
        {
          if ( !a2 )
            goto LABEL_5;
          if ( a4 >= 2 )
          {
            *(_BYTE *)a3 = *(_BYTE *)a1;
            v8 = (char *)a3 + 1;
            *v8 = 0;
            a3 = v8 + 1;
            a4 -= 2;
            goto LABEL_5;
          }
          return 0;
        }
      }
    }
  }
  else
  {
    v5 = 0;
    if ( a2 <= 0 )
    {
LABEL_5:
      *a5 = a4;
      return a3;
    }
    while ( a4 >= 2 )
    {
      v6 = *(unsigned __int8 *)a1;
      a4 -= 2;
      a1 = (_WORD *)((char *)a1 + 1);
      ++v5;
      *a3++ = (v6 << 8) | 1;
      if ( v5 >= a2 )
        goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800031d8  cmp     edx, 3
0x1800031db  jge     short loc_180003220
0x1800031dd  xor     r10d, r10d
0x1800031e0  test    edx, edx
0x1800031e2  jle     short loc_180003214
0x1800031e4  lea     r11d, [r10+1]
0x1800031e8  cmp     r9d, 2
0x1800031ec  jb      loc_18000327F
0x1800031f2  movzx   eax, byte ptr [rcx]
0x1800031f5  add     r9d, 0FFFFFFFEh
0x1800031f9  shl     ax, 8
0x1800031fd  add     rcx, r11
0x180003200  or      ax, r11w
0x180003204  add     r10d, r11d
0x180003207  mov     [r8], ax
0x18000320b  add     r8, 2
0x18000320f  cmp     r10d, edx
0x180003212  jl      short loc_1800031E8
0x180003214  mov     rax, [rsp+arg_20]
0x180003219  mov     [rax], r9d
0x18000321c  mov     rax, r8
0x18000321f  retn
0x180003220  cmp     r9d, 2
0x180003224  jb      short loc_18000327F
0x180003226  movzx   eax, dx
0x180003229  shl     ax, 8
0x18000322d  mov     [r8], ax
0x180003231  add     r8, 2
0x180003235  add     r9d, 0FFFFFFFEh
0x180003239  cmp     r9d, 2
0x18000323d  jb      short loc_18000327F
0x18000323f  movzx   eax, word ptr [rcx]
0x180003242  sub     edx, 2
0x180003245  mov     [r8], ax
0x180003249  add     rcx, 2
0x18000324d  add     r8, 2
0x180003251  add     r9d, 0FFFFFFFEh
0x180003255  cmp     edx, 2
0x180003258  jge     short loc_180003239
0x18000325a  xor     r10d, r10d
0x18000325d  test    edx, edx
0x18000325f  jz      short loc_180003214
0x180003261  cmp     r9d, 2
0x180003265  jb      short loc_18000327F
0x180003267  mov     al, [rcx]
0x180003269  lea     r11d, [r10+1]
0x18000326d  mov     [r8], al
0x180003270  add     r8, r11
0x180003273  mov     [r8], r10b
0x180003276  add     r8, r11
0x180003279  add     r9d, 0FFFFFFFEh
0x18000327d  jmp     short loc_180003214
0x18000327f  xor     eax, eax
0x180003281  retn
```
