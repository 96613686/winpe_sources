# MapEapHostErrorToRasError

- ea: `0x18002adbc`
- end: `0x18002b422`
- name: `MapEapHostErrorToRasError`
- size: `1638`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180025b50`
- `0x1800261c0`
- `0x180028364`
- `0x18002a350`
- `0x18002a7e0`
- `0x18002b87c`

## callees

- `0x18002adbc`
- `0x18002bb54`
- `0x18002bb84`

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
0x18002adbc  mov     [rsp+arg_0], rbx
0x18002adc1  mov     [rsp+arg_8], rsi
0x18002adc6  push    rdi
0x18002adc7  sub     rsp, 20h
0x18002adcb  mov     ebx, ecx
0x18002adcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002add4  lea     rsi, WPP_GLOBAL_Control
0x18002addb  mov     dil, 2
0x18002adde  cmp     rcx, rsi
0x18002ade1  jz      short loc_18002AE07
0x18002ade3  test    [rcx+1Ch], dil
0x18002ade7  jz      short loc_18002AE07
0x18002ade9  cmp     byte ptr [rcx+19h], 6
0x18002aded  jb      short loc_18002AE07
0x18002adef  mov     rcx, [rcx+10h]
0x18002adf3  mov     edx, 4Fh ; 'O'
0x18002adf8  mov     r9d, ebx
0x18002adfb  call    WPP_SF_d
0x18002ae00  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae07  mov     eax, ebx
0x18002ae09  and     eax, 1FFF0000h
0x18002ae0e  cmp     eax, 420000h
0x18002ae13  jnz     loc_18002B3EE
0x18002ae19  mov     eax, 80420104h
0x18002ae1e  cmp     ebx, eax
0x18002ae20  ja      loc_18002B0B3
0x18002ae26  jz      loc_18002B083
0x18002ae2c  mov     eax, 80420017h
0x18002ae31  cmp     ebx, eax
0x18002ae33  ja      loc_18002AF43
0x18002ae39  jz      loc_18002B053
0x18002ae3f  cmp     ebx, 40420016h
0x18002ae45  jz      loc_18002AF13
0x18002ae4b  cmp     ebx, 40420110h
0x18002ae51  jz      short loc_18002AE83
0x18002ae53  cmp     ebx, 80420010h
0x18002ae59  jz      loc_18002B1A2
0x18002ae5f  cmp     ebx, 80420011h
0x18002ae65  jz      short loc_18002AEE3
0x18002ae67  cmp     ebx, 80420013h
0x18002ae6d  jz      short loc_18002AEB3
0x18002ae6f  cmp     ebx, 80420014h
0x18002ae75  jz      short loc_18002AE83
0x18002ae77  cmp     ebx, 80420015h
0x18002ae7d  jnz     loc_18002B2A2
0x18002ae83  cmp     rcx, rsi
0x18002ae86  jz      short loc_18002AEA9
0x18002ae88  test    [rcx+1Ch], dil
0x18002ae8c  jz      short loc_18002AEA9
0x18002ae8e  cmp     byte ptr [rcx+19h], 5
0x18002ae92  jb      short loc_18002AEA9
0x18002ae94  mov     rcx, [rcx+10h]
0x18002ae98  mov     edx, 53h ; 'S'
0x18002ae9d  call    WPP_SF_
0x18002aea2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aea9  mov     ebx, 2B3h
0x18002aeae  jmp     loc_18002B3EE
0x18002aeb3  cmp     rcx, rsi
0x18002aeb6  jz      short loc_18002AED9
0x18002aeb8  test    [rcx+1Ch], dil
0x18002aebc  jz      short loc_18002AED9
0x18002aebe  cmp     byte ptr [rcx+19h], 5
0x18002aec2  jb      short loc_18002AED9
0x18002aec4  mov     rcx, [rcx+10h]
0x18002aec8  mov     edx, 52h ; 'R'
0x18002aecd  call    WPP_SF_
0x18002aed2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aed9  mov     ebx, 344h
0x18002aede  jmp     loc_18002B3EE
0x18002aee3  cmp     rcx, rsi
0x18002aee6  jz      short loc_18002AF09
0x18002aee8  test    [rcx+1Ch], dil
0x18002aeec  jz      short loc_18002AF09
0x18002aeee  cmp     byte ptr [rcx+19h], 5
0x18002aef2  jb      short loc_18002AF09
0x18002aef4  mov     rcx, [rcx+10h]
0x18002aef8  mov     edx, 51h ; 'Q'
0x18002aefd  call    WPP_SF_
0x18002af02  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af09  mov     ebx, 352h
0x18002af0e  jmp     loc_18002B3EE
0x18002af13  cmp     rcx, rsi
0x18002af16  jz      short loc_18002AF39
0x18002af18  test    [rcx+1Ch], dil
0x18002af1c  jz      short loc_18002AF39
0x18002af1e  cmp     byte ptr [rcx+19h], 5
0x18002af22  jb      short loc_18002AF39
0x18002af24  mov     rcx, [rcx+10h]
0x18002af28  mov     edx, 54h ; 'T'
0x18002af2d  call    WPP_SF_
0x18002af32  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af39  mov     ebx, 32Ch
0x18002af3e  jmp     loc_18002B3EE
0x18002af43  cmp     ebx, 80420018h
0x18002af49  jz      loc_18002B053
0x18002af4f  cmp     ebx, 8042001Ah
0x18002af55  jz      loc_18002B023
0x18002af5b  cmp     ebx, 80420020h
0x18002af61  jz      loc_18002AFF3
0x18002af67  cmp     ebx, 80420100h
0x18002af6d  jz      loc_18002B1A2
0x18002af73  cmp     ebx, 80420101h
0x18002af79  jz      loc_18002B202
0x18002af7f  cmp     ebx, 80420102h
0x18002af85  jz      short loc_18002AFC3
0x18002af87  cmp     ebx, 80420103h
0x18002af8d  jnz     loc_18002B2A2
0x18002af93  cmp     rcx, rsi
0x18002af96  jz      short loc_18002AFB9
0x18002af98  test    [rcx+1Ch], dil
0x18002af9c  jz      short loc_18002AFB9
0x18002af9e  cmp     byte ptr [rcx+19h], 5
0x18002afa2  jb      short loc_18002AFB9
0x18002afa4  mov     rcx, [rcx+10h]
0x18002afa8  mov     edx, 5Ah ; 'Z'
0x18002afad  call    WPP_SF_
0x18002afb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afb9  mov     ebx, 357h
0x18002afbe  jmp     loc_18002B3EE
0x18002afc3  cmp     rcx, rsi
0x18002afc6  jz      short loc_18002AFE9
0x18002afc8  test    [rcx+1Ch], dil
0x18002afcc  jz      short loc_18002AFE9
0x18002afce  cmp     byte ptr [rcx+19h], 5
0x18002afd2  jb      short loc_18002AFE9
0x18002afd4  mov     rcx, [rcx+10h]
0x18002afd8  mov     edx, 59h ; 'Y'
0x18002afdd  call    WPP_SF_
0x18002afe2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afe9  mov     ebx, 356h
0x18002afee  jmp     loc_18002B3EE
0x18002aff3  cmp     rcx, rsi
0x18002aff6  jz      short loc_18002B019
0x18002aff8  test    [rcx+1Ch], dil
0x18002affc  jz      short loc_18002B019
0x18002affe  cmp     byte ptr [rcx+19h], 5
0x18002b002  jb      short loc_18002B019
0x18002b004  mov     rcx, [rcx+10h]
0x18002b008  mov     edx, 57h ; 'W'
0x18002b00d  call    WPP_SF_
0x18002b012  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b019  mov     ebx, 354h
0x18002b01e  jmp     loc_18002B3EE
0x18002b023  cmp     rcx, rsi
0x18002b026  jz      short loc_18002B049
0x18002b028  test    [rcx+1Ch], dil
0x18002b02c  jz      short loc_18002B049
0x18002b02e  cmp     byte ptr [rcx+19h], 5
0x18002b032  jb      short loc_18002B049
0x18002b034  mov     rcx, [rcx+10h]
0x18002b038  mov     edx, 56h ; 'V'
0x18002b03d  call    WPP_SF_
0x18002b042  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b049  mov     ebx, 353h
0x18002b04e  jmp     loc_18002B3EE
0x18002b053  cmp     rcx, rsi
0x18002b056  jz      short loc_18002B079
0x18002b058  test    [rcx+1Ch], dil
0x18002b05c  jz      short loc_18002B079
0x18002b05e  cmp     byte ptr [rcx+19h], 5
0x18002b062  jb      short loc_18002B079
0x18002b064  mov     rcx, [rcx+10h]
0x18002b068  mov     edx, 55h ; 'U'
0x18002b06d  call    WPP_SF_
0x18002b072  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b079  mov     ebx, 2D2h
0x18002b07e  jmp     loc_18002B3EE
0x18002b083  cmp     rcx, rsi
0x18002b086  jz      short loc_18002B0A9
0x18002b088  test    [rcx+1Ch], dil
0x18002b08c  jz      short loc_18002B0A9
0x18002b08e  cmp     byte ptr [rcx+19h], 5
0x18002b092  jb      short loc_18002B0A9
0x18002b094  mov     rcx, [rcx+10h]
0x18002b098  mov     edx, 5Bh ; '['
0x18002b09d  call    WPP_SF_
0x18002b0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0a9  mov     ebx, 358h
0x18002b0ae  jmp     loc_18002B3EE
0x18002b0b3  mov     eax, 80420204h
0x18002b0b8  cmp     ebx, eax
0x18002b0ba  ja      loc_18002B262
0x18002b0c0  jz      loc_18002B232
0x18002b0c6  cmp     ebx, 80420105h
0x18002b0cc  jz      loc_18002B202
0x18002b0d2  cmp     ebx, 80420111h
0x18002b0d8  jz      loc_18002AE83
0x18002b0de  cmp     ebx, 80420113h
0x18002b0e4  jz      loc_18002B1D2
0x18002b0ea  cmp     ebx, 80420200h
0x18002b0f0  jz      loc_18002B1A2
0x18002b0f6  cmp     ebx, 80420201h
0x18002b0fc  jz      short loc_18002B172
0x18002b0fe  cmp     ebx, 80420202h
0x18002b104  jz      short loc_18002B142
0x18002b106  cmp     ebx, 80420203h
0x18002b10c  jnz     loc_18002B2A2
0x18002b112  cmp     rcx, rsi
0x18002b115  jz      short loc_18002B138
0x18002b117  test    [rcx+1Ch], dil
0x18002b11b  jz      short loc_18002B138
0x18002b11d  cmp     byte ptr [rcx+19h], 5
0x18002b121  jb      short loc_18002B138
0x18002b123  mov     rcx, [rcx+10h]
0x18002b127  mov     edx, 5Eh ; '^'
0x18002b12c  call    WPP_SF_
0x18002b131  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b138  mov     ebx, 35Bh
0x18002b13d  jmp     loc_18002B3EE
0x18002b142  cmp     rcx, rsi
0x18002b145  jz      short loc_18002B168
0x18002b147  test    [rcx+1Ch], dil
0x18002b14b  jz      short loc_18002B168
0x18002b14d  cmp     byte ptr [rcx+19h], 5
0x18002b151  jb      short loc_18002B168
0x18002b153  mov     rcx, [rcx+10h]
0x18002b157  mov     edx, 5Dh ; ']'
0x18002b15c  call    WPP_SF_
0x18002b161  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b168  mov     ebx, 35Ah
0x18002b16d  jmp     loc_18002B3EE
0x18002b172  cmp     rcx, rsi
0x18002b175  jz      short loc_18002B198
0x18002b177  test    [rcx+1Ch], dil
0x18002b17b  jz      short loc_18002B198
0x18002b17d  cmp     byte ptr [rcx+19h], 5
0x18002b181  jb      short loc_18002B198
0x18002b183  mov     rcx, [rcx+10h]
0x18002b187  mov     edx, 5Ch ; '\'
0x18002b18c  call    WPP_SF_
0x18002b191  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b198  mov     ebx, 359h
0x18002b19d  jmp     loc_18002B3EE
0x18002b1a2  cmp     rcx, rsi
0x18002b1a5  jz      short loc_18002B1C8
0x18002b1a7  test    [rcx+1Ch], dil
0x18002b1ab  jz      short loc_18002B1C8
0x18002b1ad  cmp     byte ptr [rcx+19h], 5
0x18002b1b1  jb      short loc_18002B1C8
0x18002b1b3  mov     rcx, [rcx+10h]
0x18002b1b7  mov     edx, 50h ; 'P'
0x18002b1bc  call    WPP_SF_
0x18002b1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1c8  mov     ebx, 31Eh
0x18002b1cd  jmp     loc_18002B3EE
0x18002b1d2  cmp     rcx, rsi
0x18002b1d5  jz      short loc_18002B1F8
0x18002b1d7  test    [rcx+1Ch], dil
0x18002b1db  jz      short loc_18002B1F8
0x18002b1dd  cmp     byte ptr [rcx+19h], 5
0x18002b1e1  jb      short loc_18002B1F8
0x18002b1e3  mov     rcx, [rcx+10h]
0x18002b1e7  mov     edx, 66h ; 'f'
0x18002b1ec  call    WPP_SF_
0x18002b1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1f8  mov     ebx, 2FCh
0x18002b1fd  jmp     loc_18002B3EE
0x18002b202  cmp     rcx, rsi
0x18002b205  jz      short loc_18002B228
0x18002b207  test    [rcx+1Ch], dil
0x18002b20b  jz      short loc_18002B228
0x18002b20d  cmp     byte ptr [rcx+19h], 5
0x18002b211  jb      short loc_18002B228
0x18002b213  mov     rcx, [rcx+10h]
0x18002b217  mov     edx, 58h ; 'X'
0x18002b21c  call    WPP_SF_
0x18002b221  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b228  mov     ebx, 355h
0x18002b22d  jmp     loc_18002B3EE
0x18002b232  cmp     rcx, rsi
0x18002b235  jz      short loc_18002B258
0x18002b237  test    [rcx+1Ch], dil
0x18002b23b  jz      short loc_18002B258
0x18002b23d  cmp     byte ptr [rcx+19h], 5
0x18002b241  jb      short loc_18002B258
0x18002b243  mov     rcx, [rcx+10h]
0x18002b247  mov     edx, 5Fh ; '_'
0x18002b24c  call    WPP_SF_
0x18002b251  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b258  mov     ebx, 35Ch
0x18002b25d  jmp     loc_18002B3EE
0x18002b262  cmp     ebx, 80420300h
0x18002b268  jz      loc_18002B3C3
0x18002b26e  cmp     ebx, 80420301h
0x18002b274  jz      loc_18002B396
0x18002b27a  cmp     ebx, 80420302h
0x18002b280  jz      loc_18002B369
0x18002b286  cmp     ebx, 80420400h
0x18002b28c  jz      loc_18002B339
0x18002b292  cmp     ebx, 80420401h
0x18002b298  jz      short loc_18002B309
0x18002b29a  cmp     ebx, 80420406h
0x18002b2a0  jz      short loc_18002B2D9
0x18002b2a2  cmp     rcx, rsi
0x18002b2a5  jz      loc_18002B410
0x18002b2ab  test    [rcx+1Ch], dil
0x18002b2af  jz      loc_18002B3EE
0x18002b2b5  cmp     byte ptr [rcx+19h], 5
0x18002b2b9  jb      loc_18002B3EE
0x18002b2bf  mov     rcx, [rcx+10h]
  ... truncated ...
```
