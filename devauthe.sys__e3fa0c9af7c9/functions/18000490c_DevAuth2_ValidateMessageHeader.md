# DevAuth2_ValidateMessageHeader

- ea: `0x18000490c`
- end: `0x1800049bc`
- name: `DevAuth2_ValidateMessageHeader`
- size: `176`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000409c`
- `0x180004368`
- `0x1800044a8`
- `0x180004594`

## callees

- `0x180003610`
- `0x18000490c`

## pseudocode

```c
_BOOL8 __fastcall DevAuth2_ValidateMessageHeader(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  char v4; // r11
  __int64 v5; // r10
  int v6; // eax
  bool v7; // zf

  v4 = a1;
  v5 = a3;
  switch ( (unsigned __int8)a1 )
  {
    case '!':
      if ( a4 != 40 )
        return 0;
      return v4 == *(_BYTE *)v5
          && *(_BYTE *)(v5 + 1) == 2
          && a4 - 4 == ((unsigned __int16)(*(_WORD *)(v5 + 2) << 8) | HIBYTE(*(unsigned __int16 *)(v5 + 2)));
    case '"':
      v6 = 0;
      v7 = a4 == 176;
      goto LABEL_14;
    case '#':
      v6 = 0;
      v7 = a4 == 772;
      goto LABEL_14;
    case '$':
      v6 = 0;
      v7 = a4 == 132;
      goto LABEL_14;
  }
  if ( (unsigned __int8)a1 != 37 )
  {
    if ( (unsigned __int8)a1 == 38 )
    {
      v6 = 0;
      v7 = a4 == 36;
      goto LABEL_14;
    }
    if ( (unsigned __int8)a1 != 39 )
    {
      v6 = DevAuthValidateMessageLength(a1, a4);
      goto LABEL_15;
    }
  }
  v6 = 0;
  v7 = a4 == 68;
LABEL_14:
  LOBYTE(v6) = v7;
LABEL_15:
  if ( !v6 )
    return 0;
  return v4 == *(_BYTE *)v5
      && *(_BYTE *)(v5 + 1) == 2
      && a4 - 4 == ((unsigned __int16)(*(_WORD *)(v5 + 2) << 8) | HIBYTE(*(unsigned __int16 *)(v5 + 2)));
}

```

## disassembly

```asm
0x18000490c  sub     rsp, 28h
0x180004910  movzx   r11d, cl
0x180004914  mov     r10, r8
0x180004917  mov     edx, r11d
0x18000491a  sub     edx, 21h ; '!'
0x18000491d  jz      short loc_180004988
0x18000491f  sub     edx, 1
0x180004922  jz      short loc_180004970
0x180004924  sub     edx, 1
0x180004927  jz      short loc_180004965
0x180004929  sub     edx, 1
0x18000492c  jz      short loc_18000495A
0x18000492e  sub     edx, 1
0x180004931  jz      short loc_18000494A
0x180004933  sub     edx, 1
0x180004936  jz      short loc_180004952
0x180004938  cmp     edx, 1
0x18000493b  jz      short loc_18000494A
0x18000493d  mov     edx, r9d
0x180004940  mov     cl, r11b
0x180004943  call    _DevAuthValidateMessageLength
0x180004948  jmp     short loc_18000497C
0x18000494a  xor     eax, eax
0x18000494c  cmp     r9d, 44h ; 'D'
0x180004950  jmp     short loc_180004979
0x180004952  xor     eax, eax
0x180004954  cmp     r9d, 24h ; '$'
0x180004958  jmp     short loc_180004979
0x18000495a  xor     eax, eax
0x18000495c  cmp     r9d, 84h
0x180004963  jmp     short loc_180004979
0x180004965  xor     eax, eax
0x180004967  cmp     r9d, 304h
0x18000496e  jmp     short loc_180004979
0x180004970  xor     eax, eax
0x180004972  cmp     r9d, 0B0h
0x180004979  setz    al
0x18000497c  test    eax, eax
0x18000497e  jnz     short loc_18000498E
0x180004980  xor     eax, eax
0x180004982  add     rsp, 28h
0x180004986  retn
0x180004988  cmp     r9d, 28h ; '('
0x18000498c  jnz     short loc_180004980
0x18000498e  cmp     r11b, [r10]
0x180004991  jnz     short loc_180004980
0x180004993  cmp     byte ptr [r10+1], 2
0x180004998  jnz     short loc_180004980
0x18000499a  movzx   eax, word ptr [r10+2]
0x18000499f  mov     ecx, eax
0x1800049a1  shl     ax, 8
0x1800049a5  movzx   eax, ax
0x1800049a8  shr     ecx, 8
0x1800049ab  or      ecx, eax
0x1800049ad  lea     eax, [r9-4]
0x1800049b1  cmp     eax, ecx
0x1800049b3  jnz     short loc_180004980
0x1800049b5  mov     eax, 1
0x1800049ba  jmp     short loc_180004982
```
