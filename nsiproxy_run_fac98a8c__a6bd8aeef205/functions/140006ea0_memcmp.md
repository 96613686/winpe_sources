# memcmp

- ea: `0x140006ea0`
- end: `0x140006f67`
- name: `memcmp`
- size: `199`
- prototype: `int __cdecl(const void *Buf1, const void *Buf2, size_t Size)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001880`

## callees

- `0x140006ea0`

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
0x140006ea0  sub     rdx, rcx
0x140006ea3  cmp     r8, 8
0x140006ea7  jb      short loc_140006ECB
0x140006ea9  test    cl, 7
0x140006eac  jz      short loc_140006EC2
0x140006eae  xchg    ax, ax
0x140006eb0  mov     al, [rcx]
0x140006eb2  cmp     al, [rcx+rdx]
0x140006eb5  jnz     short loc_140006EE3
0x140006eb7  inc     rcx
0x140006eba  dec     r8
0x140006ebd  test    cl, 7
0x140006ec0  jnz     short loc_140006EB0
0x140006ec2  mov     r9, r8
0x140006ec5  shr     r9, 3
0x140006ec9  jnz     short loc_140006EEA
0x140006ecb  test    r8, r8
0x140006ece  jz      short loc_140006EDF
0x140006ed0  mov     al, [rcx]
0x140006ed2  cmp     al, [rcx+rdx]
0x140006ed5  jnz     short loc_140006EE3
0x140006ed7  inc     rcx
0x140006eda  dec     r8
0x140006edd  jnz     short loc_140006ED0
0x140006edf  xor     rax, rax
0x140006ee2  retn
0x140006ee3  sbb     eax, eax
0x140006ee5  sbb     eax, 0FFFFFFFFh
0x140006ee8  retn
0x140006eea  shr     r9, 2
0x140006eee  jz      short loc_140006F27
0x140006ef0  mov     rax, [rcx]
0x140006ef3  cmp     rax, [rcx+rdx]
0x140006ef7  jnz     short loc_140006F54
0x140006ef9  mov     rax, [rcx+8]
0x140006efd  cmp     rax, [rcx+rdx+8]
0x140006f02  jnz     short loc_140006F50
0x140006f04  mov     rax, [rcx+10h]
0x140006f08  cmp     rax, [rcx+rdx+10h]
0x140006f0d  jnz     short loc_140006F4C
0x140006f0f  mov     rax, [rcx+18h]
0x140006f13  cmp     rax, [rcx+rdx+18h]
0x140006f18  jnz     short loc_140006F48
0x140006f1a  add     rcx, 20h ; ' '
0x140006f1e  dec     r9
0x140006f21  jnz     short loc_140006EF0
0x140006f23  and     r8, 1Fh
0x140006f27  mov     r9, r8
0x140006f2a  shr     r9, 3
0x140006f2e  jz      short loc_140006ECB
0x140006f30  mov     rax, [rcx]
0x140006f33  cmp     rax, [rcx+rdx]
0x140006f37  jnz     short loc_140006F54
0x140006f39  add     rcx, 8
0x140006f3d  dec     r9
0x140006f40  jnz     short loc_140006F30
0x140006f42  and     r8, 7
0x140006f46  jmp     short loc_140006ECB
0x140006f48  add     rcx, 8
0x140006f4c  add     rcx, 8
0x140006f50  add     rcx, 8
0x140006f54  mov     rcx, [rdx+rcx]
0x140006f58  bswap   rax
0x140006f5b  bswap   rcx
0x140006f5e  cmp     rax, rcx
0x140006f61  sbb     eax, eax
0x140006f63  sbb     eax, 0FFFFFFFFh
0x140006f66  retn
```
