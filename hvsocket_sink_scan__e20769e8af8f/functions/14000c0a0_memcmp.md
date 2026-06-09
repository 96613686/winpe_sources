# memcmp

- ea: `0x14000c0a0`
- end: `0x14000c167`
- name: `memcmp`
- size: `199`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x1400012d0`
- `0x140001310`
- `0x140002f34`
- `0x140004f2c`
- `0x14000695c`
- `0x140018130`
- `0x140018350`
- `0x14001a148`
- `0x14001a790`
- `0x14001a9f0`
- `0x14001b98c`
- `0x14001bd20`
- `0x14001c2d0`
- `0x14001cf60`
- `0x14001d568`
- `0x14001d728`
- `0x14001daa0`
- `0x14001dcf8`
- `0x14001e1c0`
- `0x14001e5ac`
- `0x14001f540`
- `0x14001f5e4`
- `0x140020124`
- `0x14002052c`
- `0x140021ec0`
- `0x1400222b0`
- `0x140022634`
- `0x14002672c`
- `0x1400267c8`

## callees

- `0x14000c0a0`

## pseudocode

```c
int __cdecl memcmp(const void *Buf1, const void *Buf2, size_t Size)
{
  signed __int64 v3; // rdx
  bool v4; // cf
  size_t v6; // r9
  unsigned __int64 v7; // rax
  size_t v8; // r9

  v3 = (_BYTE *)Buf2 - (_BYTE *)Buf1;
  if ( Size < 8 )
    goto LABEL_6;
  for ( ; ((unsigned __int8)Buf1 & 7) != 0; --Size )
  {
    v4 = *(_BYTE *)Buf1 < *((_BYTE *)Buf1 + v3);
    if ( *(_BYTE *)Buf1 != *((_BYTE *)Buf1 + v3) )
      return -v4 - (v4 - 1);
    Buf1 = (char *)Buf1 + 1;
  }
  if ( !(Size >> 3) )
  {
LABEL_6:
    if ( !Size )
      return 0;
    while ( 1 )
    {
      v4 = *(_BYTE *)Buf1 < *((_BYTE *)Buf1 + v3);
      if ( *(_BYTE *)Buf1 != *((_BYTE *)Buf1 + v3) )
        break;
      Buf1 = (char *)Buf1 + 1;
      if ( !--Size )
        return 0;
    }
    return -v4 - (v4 - 1);
  }
  v6 = Size >> 5;
  if ( Size >> 5 )
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)Buf1;
      if ( *(_QWORD *)Buf1 != *(_QWORD *)((char *)Buf1 + v3) )
        break;
      v7 = *((_QWORD *)Buf1 + 1);
      if ( v7 != *(_QWORD *)((char *)Buf1 + v3 + 8) )
        goto LABEL_24;
      v7 = *((_QWORD *)Buf1 + 2);
      if ( v7 != *(_QWORD *)((char *)Buf1 + v3 + 16) )
        goto LABEL_23;
      v7 = *((_QWORD *)Buf1 + 3);
      if ( v7 != *(_QWORD *)((char *)Buf1 + v3 + 24) )
      {
        Buf1 = (char *)Buf1 + 8;
LABEL_23:
        Buf1 = (char *)Buf1 + 8;
LABEL_24:
        Buf1 = (char *)Buf1 + 8;
        break;
      }
      Buf1 = (char *)Buf1 + 32;
      if ( !--v6 )
      {
        Size &= 0x1Fu;
        goto LABEL_18;
      }
    }
  }
  else
  {
LABEL_18:
    v8 = Size >> 3;
    if ( !(Size >> 3) )
      goto LABEL_6;
    while ( 1 )
    {
      v7 = *(_QWORD *)Buf1;
      if ( *(_QWORD *)Buf1 != *(_QWORD *)((char *)Buf1 + v3) )
        break;
      Buf1 = (char *)Buf1 + 8;
      if ( !--v8 )
      {
        Size &= 7u;
        goto LABEL_6;
      }
    }
  }
  v4 = _byteswap_uint64(v7) < _byteswap_uint64(*(_QWORD *)((char *)Buf1 + v3));
  return -v4 - (v4 - 1);
}

```

## disassembly

```asm
0x14000c0a0  sub     rdx, rcx
0x14000c0a3  cmp     r8, 8
0x14000c0a7  jb      short loc_14000C0CB
0x14000c0a9  test    cl, 7
0x14000c0ac  jz      short loc_14000C0C2
0x14000c0ae  xchg    ax, ax
0x14000c0b0  mov     al, [rcx]
0x14000c0b2  cmp     al, [rcx+rdx]
0x14000c0b5  jnz     short loc_14000C0E3
0x14000c0b7  inc     rcx
0x14000c0ba  dec     r8
0x14000c0bd  test    cl, 7
0x14000c0c0  jnz     short loc_14000C0B0
0x14000c0c2  mov     r9, r8
0x14000c0c5  shr     r9, 3
0x14000c0c9  jnz     short loc_14000C0EA
0x14000c0cb  test    r8, r8
0x14000c0ce  jz      short loc_14000C0DF
0x14000c0d0  mov     al, [rcx]
0x14000c0d2  cmp     al, [rcx+rdx]
0x14000c0d5  jnz     short loc_14000C0E3
0x14000c0d7  inc     rcx
0x14000c0da  dec     r8
0x14000c0dd  jnz     short loc_14000C0D0
0x14000c0df  xor     rax, rax
0x14000c0e2  retn
0x14000c0e3  sbb     eax, eax
0x14000c0e5  sbb     eax, 0FFFFFFFFh
0x14000c0e8  retn
0x14000c0ea  shr     r9, 2
0x14000c0ee  jz      short loc_14000C127
0x14000c0f0  mov     rax, [rcx]
0x14000c0f3  cmp     rax, [rcx+rdx]
0x14000c0f7  jnz     short loc_14000C154
0x14000c0f9  mov     rax, [rcx+8]
0x14000c0fd  cmp     rax, [rcx+rdx+8]
0x14000c102  jnz     short loc_14000C150
0x14000c104  mov     rax, [rcx+10h]
0x14000c108  cmp     rax, [rcx+rdx+10h]
0x14000c10d  jnz     short loc_14000C14C
0x14000c10f  mov     rax, [rcx+18h]
0x14000c113  cmp     rax, [rcx+rdx+18h]
0x14000c118  jnz     short loc_14000C148
0x14000c11a  add     rcx, 20h ; ' '
0x14000c11e  dec     r9
0x14000c121  jnz     short loc_14000C0F0
0x14000c123  and     r8, 1Fh
0x14000c127  mov     r9, r8
0x14000c12a  shr     r9, 3
0x14000c12e  jz      short loc_14000C0CB
0x14000c130  mov     rax, [rcx]
0x14000c133  cmp     rax, [rcx+rdx]
0x14000c137  jnz     short loc_14000C154
0x14000c139  add     rcx, 8
0x14000c13d  dec     r9
0x14000c140  jnz     short loc_14000C130
0x14000c142  and     r8, 7
0x14000c146  jmp     short loc_14000C0CB
0x14000c148  add     rcx, 8
0x14000c14c  add     rcx, 8
0x14000c150  add     rcx, 8
0x14000c154  mov     rcx, [rdx+rcx]
0x14000c158  bswap   rax
0x14000c15b  bswap   rcx
0x14000c15e  cmp     rax, rcx
0x14000c161  sbb     eax, eax
0x14000c163  sbb     eax, 0FFFFFFFFh
0x14000c166  retn
```
