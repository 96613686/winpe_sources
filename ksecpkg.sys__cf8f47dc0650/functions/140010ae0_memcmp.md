# memcmp

- ea: `0x140010ae0`
- end: `0x140010ba7`
- name: `memcmp`
- size: `199`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000561c`
- `0x1400078f8`
- `0x1400085dc`
- `0x140024008`
- `0x14002510c`
- `0x140025504`

## callees

- `0x140010ae0`

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
0x140010ae0  sub     rdx, rcx
0x140010ae3  cmp     r8, 8
0x140010ae7  jb      short loc_140010B0B
0x140010ae9  test    cl, 7
0x140010aec  jz      short loc_140010B02
0x140010aee  xchg    ax, ax
0x140010af0  mov     al, [rcx]
0x140010af2  cmp     al, [rcx+rdx]
0x140010af5  jnz     short loc_140010B23
0x140010af7  inc     rcx
0x140010afa  dec     r8
0x140010afd  test    cl, 7
0x140010b00  jnz     short loc_140010AF0
0x140010b02  mov     r9, r8
0x140010b05  shr     r9, 3
0x140010b09  jnz     short loc_140010B2A
0x140010b0b  test    r8, r8
0x140010b0e  jz      short loc_140010B1F
0x140010b10  mov     al, [rcx]
0x140010b12  cmp     al, [rcx+rdx]
0x140010b15  jnz     short loc_140010B23
0x140010b17  inc     rcx
0x140010b1a  dec     r8
0x140010b1d  jnz     short loc_140010B10
0x140010b1f  xor     rax, rax
0x140010b22  retn
0x140010b23  sbb     eax, eax
0x140010b25  sbb     eax, 0FFFFFFFFh
0x140010b28  retn
0x140010b2a  shr     r9, 2
0x140010b2e  jz      short loc_140010B67
0x140010b30  mov     rax, [rcx]
0x140010b33  cmp     rax, [rcx+rdx]
0x140010b37  jnz     short loc_140010B94
0x140010b39  mov     rax, [rcx+8]
0x140010b3d  cmp     rax, [rcx+rdx+8]
0x140010b42  jnz     short loc_140010B90
0x140010b44  mov     rax, [rcx+10h]
0x140010b48  cmp     rax, [rcx+rdx+10h]
0x140010b4d  jnz     short loc_140010B8C
0x140010b4f  mov     rax, [rcx+18h]
0x140010b53  cmp     rax, [rcx+rdx+18h]
0x140010b58  jnz     short loc_140010B88
0x140010b5a  add     rcx, 20h ; ' '
0x140010b5e  dec     r9
0x140010b61  jnz     short loc_140010B30
0x140010b63  and     r8, 1Fh
0x140010b67  mov     r9, r8
0x140010b6a  shr     r9, 3
0x140010b6e  jz      short loc_140010B0B
0x140010b70  mov     rax, [rcx]
0x140010b73  cmp     rax, [rcx+rdx]
0x140010b77  jnz     short loc_140010B94
0x140010b79  add     rcx, 8
0x140010b7d  dec     r9
0x140010b80  jnz     short loc_140010B70
0x140010b82  and     r8, 7
0x140010b86  jmp     short loc_140010B0B
0x140010b88  add     rcx, 8
0x140010b8c  add     rcx, 8
0x140010b90  add     rcx, 8
0x140010b94  mov     rcx, [rdx+rcx]
0x140010b98  bswap   rax
0x140010b9b  bswap   rcx
0x140010b9e  cmp     rax, rcx
0x140010ba1  sbb     eax, eax
0x140010ba3  sbb     eax, 0FFFFFFFFh
0x140010ba6  retn
```
