# memcmp

- ea: `0x140002ee0`
- end: `0x140002fa7`
- name: `memcmp`
- size: `199`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140010f68`
- `0x1400140cc`
- `0x140015090`
- `0x1400164dc`

## callees

- `0x140002ee0`

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
0x140002ee0  sub     rdx, rcx
0x140002ee3  cmp     r8, 8
0x140002ee7  jb      short loc_140002F0B
0x140002ee9  test    cl, 7
0x140002eec  jz      short loc_140002F02
0x140002eee  xchg    ax, ax
0x140002ef0  mov     al, [rcx]
0x140002ef2  cmp     al, [rcx+rdx]
0x140002ef5  jnz     short loc_140002F23
0x140002ef7  inc     rcx
0x140002efa  dec     r8
0x140002efd  test    cl, 7
0x140002f00  jnz     short loc_140002EF0
0x140002f02  mov     r9, r8
0x140002f05  shr     r9, 3
0x140002f09  jnz     short loc_140002F2A
0x140002f0b  test    r8, r8
0x140002f0e  jz      short loc_140002F1F
0x140002f10  mov     al, [rcx]
0x140002f12  cmp     al, [rcx+rdx]
0x140002f15  jnz     short loc_140002F23
0x140002f17  inc     rcx
0x140002f1a  dec     r8
0x140002f1d  jnz     short loc_140002F10
0x140002f1f  xor     rax, rax
0x140002f22  retn
0x140002f23  sbb     eax, eax
0x140002f25  sbb     eax, 0FFFFFFFFh
0x140002f28  retn
0x140002f2a  shr     r9, 2
0x140002f2e  jz      short loc_140002F67
0x140002f30  mov     rax, [rcx]
0x140002f33  cmp     rax, [rcx+rdx]
0x140002f37  jnz     short loc_140002F94
0x140002f39  mov     rax, [rcx+8]
0x140002f3d  cmp     rax, [rcx+rdx+8]
0x140002f42  jnz     short loc_140002F90
0x140002f44  mov     rax, [rcx+10h]
0x140002f48  cmp     rax, [rcx+rdx+10h]
0x140002f4d  jnz     short loc_140002F8C
0x140002f4f  mov     rax, [rcx+18h]
0x140002f53  cmp     rax, [rcx+rdx+18h]
0x140002f58  jnz     short loc_140002F88
0x140002f5a  add     rcx, 20h ; ' '
0x140002f5e  dec     r9
0x140002f61  jnz     short loc_140002F30
0x140002f63  and     r8, 1Fh
0x140002f67  mov     r9, r8
0x140002f6a  shr     r9, 3
0x140002f6e  jz      short loc_140002F0B
0x140002f70  mov     rax, [rcx]
0x140002f73  cmp     rax, [rcx+rdx]
0x140002f77  jnz     short loc_140002F94
0x140002f79  add     rcx, 8
0x140002f7d  dec     r9
0x140002f80  jnz     short loc_140002F70
0x140002f82  and     r8, 7
0x140002f86  jmp     short loc_140002F0B
0x140002f88  add     rcx, 8
0x140002f8c  add     rcx, 8
0x140002f90  add     rcx, 8
0x140002f94  mov     rcx, [rdx+rcx]
0x140002f98  bswap   rax
0x140002f9b  bswap   rcx
0x140002f9e  cmp     rax, rcx
0x140002fa1  sbb     eax, eax
0x140002fa3  sbb     eax, 0FFFFFFFFh
0x140002fa6  retn
```
