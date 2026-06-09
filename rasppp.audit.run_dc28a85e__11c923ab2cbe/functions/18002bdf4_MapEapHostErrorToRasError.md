# MapEapHostErrorToRasError

- ea: `0x18002bdf4`
- end: `0x18002c45b`
- name: `MapEapHostErrorToRasError`
- size: `1639`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180026900`
- `0x180026fa0`
- `0x180029244`
- `0x18002b304`
- `0x18002b7d4`
- `0x18002c8d0`

## callees

- `0x18002bdf4`
- `0x18002cbac`
- `0x18002cbe4`

## pseudocode

```c
__int64 __fastcall MapEapHostErrorToRasError(unsigned int a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, a3, a1);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (a1 & 0x1FFF0000) != 0x420000 )
    goto LABEL_158;
  if ( a1 > 0x80420104 )
  {
    if ( a1 > 0x80420204 )
    {
      switch ( a1 )
      {
        case 0x80420300:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 96);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 861;
          goto LABEL_158;
        case 0x80420301:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 97);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 862;
          goto LABEL_158;
        case 0x80420302:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 98);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 863;
          goto LABEL_158;
        case 0x80420400:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 99);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 864;
          goto LABEL_158;
        case 0x80420401:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 100);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 865;
          goto LABEL_158;
        case 0x80420406:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 101);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 866;
          goto LABEL_158;
      }
      goto LABEL_124;
    }
    if ( a1 == -2143157756 )
    {
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      {
        WPP_SF_(v4[2], 95);
        v4 = WPP_GLOBAL_Control;
      }
      a1 = 860;
      goto LABEL_158;
    }
    if ( a1 != -2143158011 )
    {
      if ( a1 != -2143157999 )
      {
        if ( a1 == -2143157997 )
        {
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 102);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 764;
          goto LABEL_158;
        }
        if ( a1 != -2143157760 )
        {
          switch ( a1 )
          {
            case 0x80420201:
              if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
              {
                WPP_SF_(v4[2], 92);
                v4 = WPP_GLOBAL_Control;
              }
              a1 = 857;
              goto LABEL_158;
            case 0x80420202:
              if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
              {
                WPP_SF_(v4[2], 93);
                v4 = WPP_GLOBAL_Control;
              }
              a1 = 858;
              goto LABEL_158;
            case 0x80420203:
              if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
              {
                WPP_SF_(v4[2], 94);
                v4 = WPP_GLOBAL_Control;
              }
              a1 = 859;
              goto LABEL_158;
          }
          goto LABEL_124;
        }
LABEL_98:
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 80);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 798;
        goto LABEL_158;
      }
LABEL_17:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      {
        WPP_SF_(v4[2], 83);
        v4 = WPP_GLOBAL_Control;
      }
      a1 = 691;
      goto LABEL_158;
    }
    goto LABEL_108;
  }
  if ( a1 == -2143158012 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    {
      WPP_SF_(v4[2], 91);
      v4 = WPP_GLOBAL_Control;
    }
    a1 = 856;
    goto LABEL_158;
  }
  if ( a1 > 0x80420017 )
  {
    switch ( a1 )
    {
      case 0x80420018:
LABEL_64:
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 85);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 722;
        goto LABEL_158;
      case 0x8042001A:
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 86);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 851;
        goto LABEL_158;
      case 0x80420020:
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 87);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 852;
        goto LABEL_158;
      case 0x80420100:
        goto LABEL_98;
    }
    if ( a1 != -2143158015 )
    {
      if ( a1 == -2143158014 )
      {
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 89);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 854;
        goto LABEL_158;
      }
      if ( a1 == -2143158013 )
      {
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 90);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 855;
        goto LABEL_158;
      }
      goto LABEL_124;
    }
LABEL_108:
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    {
      WPP_SF_(v4[2], 88);
      v4 = WPP_GLOBAL_Control;
    }
    a1 = 853;
    goto LABEL_158;
  }
  switch ( a1 )
  {
    case 0x80420017:
      goto LABEL_64;
    case 0x40420016u:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      {
        WPP_SF_(v4[2], 84);
        v4 = WPP_GLOBAL_Control;
      }
      a1 = 812;
      goto LABEL_158;
    case 0x40420110u:
      goto LABEL_17;
    case 0x80420010:
      goto LABEL_98;
    case 0x80420011:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      {
        WPP_SF_(v4[2], 81);
        v4 = WPP_GLOBAL_Control;
      }
      a1 = 850;
      goto LABEL_158;
    case 0x80420013:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      {
        WPP_SF_(v4[2], 82);
        v4 = WPP_GLOBAL_Control;
      }
      a1 = 836;
      goto LABEL_158;
    case 0x80420014:
    case 0x80420015:
      goto LABEL_17;
  }
LABEL_124:
  if ( v4 == &WPP_GLOBAL_Control )
    return a1;
  if ( (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
  {
    WPP_SF_(v4[2], 103);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_158:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 104, a3, a1);
  return a1;
}

```

## disassembly

```asm
0x18002bdf4  mov     [rsp+arg_0], rbx
0x18002bdf9  mov     [rsp+arg_8], rsi
0x18002bdfe  push    rdi
0x18002bdff  sub     rsp, 20h
0x18002be03  mov     ebx, ecx
0x18002be05  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be0c  lea     rsi, WPP_GLOBAL_Control
0x18002be13  mov     dil, 2
0x18002be16  cmp     rcx, rsi
0x18002be19  jz      short loc_18002BE3F
0x18002be1b  test    [rcx+1Ch], dil
0x18002be1f  jz      short loc_18002BE3F
0x18002be21  cmp     byte ptr [rcx+19h], 6
0x18002be25  jb      short loc_18002BE3F
0x18002be27  mov     rcx, [rcx+10h]
0x18002be2b  mov     edx, 4Fh ; 'O'
0x18002be30  mov     r9d, ebx
0x18002be33  call    WPP_SF_d
0x18002be38  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be3f  mov     eax, ebx
0x18002be41  and     eax, 1FFF0000h
0x18002be46  cmp     eax, 420000h
0x18002be4b  jnz     loc_18002C426
0x18002be51  mov     eax, 80420104h
0x18002be56  cmp     ebx, eax
0x18002be58  ja      loc_18002C0EB
0x18002be5e  jz      loc_18002C0BB
0x18002be64  mov     eax, 80420017h
0x18002be69  cmp     ebx, eax
0x18002be6b  ja      loc_18002BF7B
0x18002be71  jz      loc_18002C08B
0x18002be77  cmp     ebx, 40420016h
0x18002be7d  jz      loc_18002BF4B
0x18002be83  cmp     ebx, 40420110h
0x18002be89  jz      short loc_18002BEBB
0x18002be8b  cmp     ebx, 80420010h
0x18002be91  jz      loc_18002C1DA
0x18002be97  cmp     ebx, 80420011h
0x18002be9d  jz      short loc_18002BF1B
0x18002be9f  cmp     ebx, 80420013h
0x18002bea5  jz      short loc_18002BEEB
0x18002bea7  cmp     ebx, 80420014h
0x18002bead  jz      short loc_18002BEBB
0x18002beaf  cmp     ebx, 80420015h
0x18002beb5  jnz     loc_18002C2DA
0x18002bebb  cmp     rcx, rsi
0x18002bebe  jz      short loc_18002BEE1
0x18002bec0  test    [rcx+1Ch], dil
0x18002bec4  jz      short loc_18002BEE1
0x18002bec6  cmp     byte ptr [rcx+19h], 5
0x18002beca  jb      short loc_18002BEE1
0x18002becc  mov     rcx, [rcx+10h]
0x18002bed0  mov     edx, 53h ; 'S'
0x18002bed5  call    WPP_SF_
0x18002beda  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bee1  mov     ebx, 2B3h
0x18002bee6  jmp     loc_18002C426
0x18002beeb  cmp     rcx, rsi
0x18002beee  jz      short loc_18002BF11
0x18002bef0  test    [rcx+1Ch], dil
0x18002bef4  jz      short loc_18002BF11
0x18002bef6  cmp     byte ptr [rcx+19h], 5
0x18002befa  jb      short loc_18002BF11
0x18002befc  mov     rcx, [rcx+10h]
0x18002bf00  mov     edx, 52h ; 'R'
0x18002bf05  call    WPP_SF_
0x18002bf0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf11  mov     ebx, 344h
0x18002bf16  jmp     loc_18002C426
0x18002bf1b  cmp     rcx, rsi
0x18002bf1e  jz      short loc_18002BF41
0x18002bf20  test    [rcx+1Ch], dil
0x18002bf24  jz      short loc_18002BF41
0x18002bf26  cmp     byte ptr [rcx+19h], 5
0x18002bf2a  jb      short loc_18002BF41
0x18002bf2c  mov     rcx, [rcx+10h]
0x18002bf30  mov     edx, 51h ; 'Q'
0x18002bf35  call    WPP_SF_
0x18002bf3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf41  mov     ebx, 352h
0x18002bf46  jmp     loc_18002C426
0x18002bf4b  cmp     rcx, rsi
0x18002bf4e  jz      short loc_18002BF71
0x18002bf50  test    [rcx+1Ch], dil
0x18002bf54  jz      short loc_18002BF71
0x18002bf56  cmp     byte ptr [rcx+19h], 5
0x18002bf5a  jb      short loc_18002BF71
0x18002bf5c  mov     rcx, [rcx+10h]
0x18002bf60  mov     edx, 54h ; 'T'
0x18002bf65  call    WPP_SF_
0x18002bf6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf71  mov     ebx, 32Ch
0x18002bf76  jmp     loc_18002C426
0x18002bf7b  cmp     ebx, 80420018h
0x18002bf81  jz      loc_18002C08B
0x18002bf87  cmp     ebx, 8042001Ah
0x18002bf8d  jz      loc_18002C05B
0x18002bf93  cmp     ebx, 80420020h
0x18002bf99  jz      loc_18002C02B
0x18002bf9f  cmp     ebx, 80420100h
0x18002bfa5  jz      loc_18002C1DA
0x18002bfab  cmp     ebx, 80420101h
0x18002bfb1  jz      loc_18002C23A
0x18002bfb7  cmp     ebx, 80420102h
0x18002bfbd  jz      short loc_18002BFFB
0x18002bfbf  cmp     ebx, 80420103h
0x18002bfc5  jnz     loc_18002C2DA
0x18002bfcb  cmp     rcx, rsi
0x18002bfce  jz      short loc_18002BFF1
0x18002bfd0  test    [rcx+1Ch], dil
0x18002bfd4  jz      short loc_18002BFF1
0x18002bfd6  cmp     byte ptr [rcx+19h], 5
0x18002bfda  jb      short loc_18002BFF1
0x18002bfdc  mov     rcx, [rcx+10h]
0x18002bfe0  mov     edx, 5Ah ; 'Z'
0x18002bfe5  call    WPP_SF_
0x18002bfea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bff1  mov     ebx, 357h
0x18002bff6  jmp     loc_18002C426
0x18002bffb  cmp     rcx, rsi
0x18002bffe  jz      short loc_18002C021
0x18002c000  test    [rcx+1Ch], dil
0x18002c004  jz      short loc_18002C021
0x18002c006  cmp     byte ptr [rcx+19h], 5
0x18002c00a  jb      short loc_18002C021
0x18002c00c  mov     rcx, [rcx+10h]
0x18002c010  mov     edx, 59h ; 'Y'
0x18002c015  call    WPP_SF_
0x18002c01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c021  mov     ebx, 356h
0x18002c026  jmp     loc_18002C426
0x18002c02b  cmp     rcx, rsi
0x18002c02e  jz      short loc_18002C051
0x18002c030  test    [rcx+1Ch], dil
0x18002c034  jz      short loc_18002C051
0x18002c036  cmp     byte ptr [rcx+19h], 5
0x18002c03a  jb      short loc_18002C051
0x18002c03c  mov     rcx, [rcx+10h]
0x18002c040  mov     edx, 57h ; 'W'
0x18002c045  call    WPP_SF_
0x18002c04a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c051  mov     ebx, 354h
0x18002c056  jmp     loc_18002C426
0x18002c05b  cmp     rcx, rsi
0x18002c05e  jz      short loc_18002C081
0x18002c060  test    [rcx+1Ch], dil
0x18002c064  jz      short loc_18002C081
0x18002c066  cmp     byte ptr [rcx+19h], 5
0x18002c06a  jb      short loc_18002C081
0x18002c06c  mov     rcx, [rcx+10h]
0x18002c070  mov     edx, 56h ; 'V'
0x18002c075  call    WPP_SF_
0x18002c07a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c081  mov     ebx, 353h
0x18002c086  jmp     loc_18002C426
0x18002c08b  cmp     rcx, rsi
0x18002c08e  jz      short loc_18002C0B1
0x18002c090  test    [rcx+1Ch], dil
0x18002c094  jz      short loc_18002C0B1
0x18002c096  cmp     byte ptr [rcx+19h], 5
0x18002c09a  jb      short loc_18002C0B1
0x18002c09c  mov     rcx, [rcx+10h]
0x18002c0a0  mov     edx, 55h ; 'U'
0x18002c0a5  call    WPP_SF_
0x18002c0aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0b1  mov     ebx, 2D2h
0x18002c0b6  jmp     loc_18002C426
0x18002c0bb  cmp     rcx, rsi
0x18002c0be  jz      short loc_18002C0E1
0x18002c0c0  test    [rcx+1Ch], dil
0x18002c0c4  jz      short loc_18002C0E1
0x18002c0c6  cmp     byte ptr [rcx+19h], 5
0x18002c0ca  jb      short loc_18002C0E1
0x18002c0cc  mov     rcx, [rcx+10h]
0x18002c0d0  mov     edx, 5Bh ; '['
0x18002c0d5  call    WPP_SF_
0x18002c0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0e1  mov     ebx, 358h
0x18002c0e6  jmp     loc_18002C426
0x18002c0eb  mov     eax, 80420204h
0x18002c0f0  cmp     ebx, eax
0x18002c0f2  ja      loc_18002C29A
0x18002c0f8  jz      loc_18002C26A
0x18002c0fe  cmp     ebx, 80420105h
0x18002c104  jz      loc_18002C23A
0x18002c10a  cmp     ebx, 80420111h
0x18002c110  jz      loc_18002BEBB
0x18002c116  cmp     ebx, 80420113h
0x18002c11c  jz      loc_18002C20A
0x18002c122  cmp     ebx, 80420200h
0x18002c128  jz      loc_18002C1DA
0x18002c12e  cmp     ebx, 80420201h
0x18002c134  jz      short loc_18002C1AA
0x18002c136  cmp     ebx, 80420202h
0x18002c13c  jz      short loc_18002C17A
0x18002c13e  cmp     ebx, 80420203h
0x18002c144  jnz     loc_18002C2DA
0x18002c14a  cmp     rcx, rsi
0x18002c14d  jz      short loc_18002C170
0x18002c14f  test    [rcx+1Ch], dil
0x18002c153  jz      short loc_18002C170
0x18002c155  cmp     byte ptr [rcx+19h], 5
0x18002c159  jb      short loc_18002C170
0x18002c15b  mov     rcx, [rcx+10h]
0x18002c15f  mov     edx, 5Eh ; '^'
0x18002c164  call    WPP_SF_
0x18002c169  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c170  mov     ebx, 35Bh
0x18002c175  jmp     loc_18002C426
0x18002c17a  cmp     rcx, rsi
0x18002c17d  jz      short loc_18002C1A0
0x18002c17f  test    [rcx+1Ch], dil
0x18002c183  jz      short loc_18002C1A0
0x18002c185  cmp     byte ptr [rcx+19h], 5
0x18002c189  jb      short loc_18002C1A0
0x18002c18b  mov     rcx, [rcx+10h]
0x18002c18f  mov     edx, 5Dh ; ']'
0x18002c194  call    WPP_SF_
0x18002c199  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1a0  mov     ebx, 35Ah
0x18002c1a5  jmp     loc_18002C426
0x18002c1aa  cmp     rcx, rsi
0x18002c1ad  jz      short loc_18002C1D0
0x18002c1af  test    [rcx+1Ch], dil
0x18002c1b3  jz      short loc_18002C1D0
0x18002c1b5  cmp     byte ptr [rcx+19h], 5
0x18002c1b9  jb      short loc_18002C1D0
0x18002c1bb  mov     rcx, [rcx+10h]
0x18002c1bf  mov     edx, 5Ch ; '\'
0x18002c1c4  call    WPP_SF_
0x18002c1c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1d0  mov     ebx, 359h
0x18002c1d5  jmp     loc_18002C426
0x18002c1da  cmp     rcx, rsi
0x18002c1dd  jz      short loc_18002C200
0x18002c1df  test    [rcx+1Ch], dil
0x18002c1e3  jz      short loc_18002C200
0x18002c1e5  cmp     byte ptr [rcx+19h], 5
0x18002c1e9  jb      short loc_18002C200
0x18002c1eb  mov     rcx, [rcx+10h]
0x18002c1ef  mov     edx, 50h ; 'P'
0x18002c1f4  call    WPP_SF_
0x18002c1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c200  mov     ebx, 31Eh
0x18002c205  jmp     loc_18002C426
0x18002c20a  cmp     rcx, rsi
0x18002c20d  jz      short loc_18002C230
0x18002c20f  test    [rcx+1Ch], dil
0x18002c213  jz      short loc_18002C230
0x18002c215  cmp     byte ptr [rcx+19h], 5
0x18002c219  jb      short loc_18002C230
0x18002c21b  mov     rcx, [rcx+10h]
0x18002c21f  mov     edx, 66h ; 'f'
0x18002c224  call    WPP_SF_
0x18002c229  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c230  mov     ebx, 2FCh
0x18002c235  jmp     loc_18002C426
0x18002c23a  cmp     rcx, rsi
0x18002c23d  jz      short loc_18002C260
0x18002c23f  test    [rcx+1Ch], dil
0x18002c243  jz      short loc_18002C260
0x18002c245  cmp     byte ptr [rcx+19h], 5
0x18002c249  jb      short loc_18002C260
0x18002c24b  mov     rcx, [rcx+10h]
0x18002c24f  mov     edx, 58h ; 'X'
0x18002c254  call    WPP_SF_
0x18002c259  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c260  mov     ebx, 355h
0x18002c265  jmp     loc_18002C426
0x18002c26a  cmp     rcx, rsi
0x18002c26d  jz      short loc_18002C290
0x18002c26f  test    [rcx+1Ch], dil
0x18002c273  jz      short loc_18002C290
0x18002c275  cmp     byte ptr [rcx+19h], 5
0x18002c279  jb      short loc_18002C290
0x18002c27b  mov     rcx, [rcx+10h]
0x18002c27f  mov     edx, 5Fh ; '_'
0x18002c284  call    WPP_SF_
0x18002c289  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c290  mov     ebx, 35Ch
0x18002c295  jmp     loc_18002C426
0x18002c29a  cmp     ebx, 80420300h
0x18002c2a0  jz      loc_18002C3FB
0x18002c2a6  cmp     ebx, 80420301h
0x18002c2ac  jz      loc_18002C3CE
0x18002c2b2  cmp     ebx, 80420302h
0x18002c2b8  jz      loc_18002C3A1
0x18002c2be  cmp     ebx, 80420400h
0x18002c2c4  jz      loc_18002C371
0x18002c2ca  cmp     ebx, 80420401h
0x18002c2d0  jz      short loc_18002C341
0x18002c2d2  cmp     ebx, 80420406h
0x18002c2d8  jz      short loc_18002C311
0x18002c2da  cmp     rcx, rsi
0x18002c2dd  jz      loc_18002C448
0x18002c2e3  test    [rcx+1Ch], dil
0x18002c2e7  jz      loc_18002C426
0x18002c2ed  cmp     byte ptr [rcx+19h], 5
0x18002c2f1  jb      loc_18002C426
0x18002c2f7  mov     rcx, [rcx+10h]
  ... truncated ...
```
