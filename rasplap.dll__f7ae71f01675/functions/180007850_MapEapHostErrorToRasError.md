# MapEapHostErrorToRasError

- ea: `0x180007850`
- end: `0x180007f66`
- name: `MapEapHostErrorToRasError`
- size: `1814`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007288`
- `0x180008234`

## callees

- `0x180007850`
- `0x180008518`
- `0x180008540`

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
            WPP_SF_(v4[2], 96, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 861;
          goto LABEL_158;
        case 0x80420301:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 97, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 862;
          goto LABEL_158;
        case 0x80420302:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 98, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 863;
          goto LABEL_158;
        case 0x80420400:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 99, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 864;
          goto LABEL_158;
        case 0x80420401:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 100, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
            v4 = WPP_GLOBAL_Control;
          }
          a1 = 865;
          goto LABEL_158;
        case 0x80420406:
          if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
          {
            WPP_SF_(v4[2], 101, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
        WPP_SF_(v4[2], 95, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
            WPP_SF_(v4[2], 102, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
                WPP_SF_(v4[2], 92, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
                v4 = WPP_GLOBAL_Control;
              }
              a1 = 857;
              goto LABEL_158;
            case 0x80420202:
              if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
              {
                WPP_SF_(v4[2], 93, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
                v4 = WPP_GLOBAL_Control;
              }
              a1 = 858;
              goto LABEL_158;
            case 0x80420203:
              if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
              {
                WPP_SF_(v4[2], 94, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
          WPP_SF_(v4[2], 80, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 798;
        goto LABEL_158;
      }
LABEL_17:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      {
        WPP_SF_(v4[2], 83, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
      WPP_SF_(v4[2], 91, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
          WPP_SF_(v4[2], 85, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 722;
        goto LABEL_158;
      case 0x8042001A:
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 86, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 851;
        goto LABEL_158;
      case 0x80420020:
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 87, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
          WPP_SF_(v4[2], 89, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        a1 = 854;
        goto LABEL_158;
      }
      if ( a1 == -2143158013 )
      {
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
        {
          WPP_SF_(v4[2], 90, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
      WPP_SF_(v4[2], 88, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
        WPP_SF_(v4[2], 84, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
        WPP_SF_(v4[2], 81, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
        v4 = WPP_GLOBAL_Control;
      }
      a1 = 850;
      goto LABEL_158;
    case 0x80420013:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      {
        WPP_SF_(v4[2], 82, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
    WPP_SF_(v4[2], 103, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
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
0x180007850  mov     [rsp+arg_0], rbx
0x180007855  mov     [rsp+arg_8], rsi
0x18000785a  push    rdi
0x18000785b  sub     rsp, 20h
0x18000785f  mov     ebx, ecx
0x180007861  mov     rcx, cs:WPP_GLOBAL_Control
0x180007868  lea     rsi, WPP_GLOBAL_Control
0x18000786f  mov     dil, 2
0x180007872  cmp     rcx, rsi
0x180007875  jz      short loc_18000789B
0x180007877  test    [rcx+1Ch], dil
0x18000787b  jz      short loc_18000789B
0x18000787d  cmp     byte ptr [rcx+19h], 6
0x180007881  jb      short loc_18000789B
0x180007883  mov     rcx, [rcx+10h]
0x180007887  mov     edx, 4Fh ; 'O'
0x18000788c  mov     r9d, ebx
0x18000788f  call    WPP_SF_d
0x180007894  mov     rcx, cs:WPP_GLOBAL_Control
0x18000789b  mov     eax, ebx
0x18000789d  and     eax, 1FFF0000h
0x1800078a2  cmp     eax, 420000h
0x1800078a7  jnz     loc_180007F32
0x1800078ad  mov     eax, 80420104h
0x1800078b2  cmp     ebx, eax
0x1800078b4  ja      loc_180007B91
0x1800078ba  jz      loc_180007B5A
0x1800078c0  mov     eax, 80420017h
0x1800078c5  cmp     ebx, eax
0x1800078c7  ja      loc_1800079F7
0x1800078cd  jz      loc_180007B23
0x1800078d3  cmp     ebx, 40420016h
0x1800078d9  jz      loc_1800079C0
0x1800078df  cmp     ebx, 40420110h
0x1800078e5  jz      short loc_18000791B
0x1800078e7  cmp     ebx, 80420010h
0x1800078ed  jz      loc_180007C99
0x1800078f3  cmp     ebx, 80420011h
0x1800078f9  jz      loc_180007989
0x1800078ff  cmp     ebx, 80420013h
0x180007905  jz      short loc_180007952
0x180007907  cmp     ebx, 80420014h
0x18000790d  jz      short loc_18000791B
0x18000790f  cmp     ebx, 80420015h
0x180007915  jnz     loc_180007DB5
0x18000791b  cmp     rcx, rsi
0x18000791e  jz      short loc_180007948
0x180007920  test    [rcx+1Ch], dil
0x180007924  jz      short loc_180007948
0x180007926  cmp     byte ptr [rcx+19h], 5
0x18000792a  jb      short loc_180007948
0x18000792c  mov     rcx, [rcx+10h]
0x180007930  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007937  mov     edx, 53h ; 'S'
0x18000793c  call    WPP_SF_
0x180007941  mov     rcx, cs:WPP_GLOBAL_Control
0x180007948  mov     ebx, 2B3h
0x18000794d  jmp     loc_180007F32
0x180007952  cmp     rcx, rsi
0x180007955  jz      short loc_18000797F
0x180007957  test    [rcx+1Ch], dil
0x18000795b  jz      short loc_18000797F
0x18000795d  cmp     byte ptr [rcx+19h], 5
0x180007961  jb      short loc_18000797F
0x180007963  mov     rcx, [rcx+10h]
0x180007967  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x18000796e  mov     edx, 52h ; 'R'
0x180007973  call    WPP_SF_
0x180007978  mov     rcx, cs:WPP_GLOBAL_Control
0x18000797f  mov     ebx, 344h
0x180007984  jmp     loc_180007F32
0x180007989  cmp     rcx, rsi
0x18000798c  jz      short loc_1800079B6
0x18000798e  test    [rcx+1Ch], dil
0x180007992  jz      short loc_1800079B6
0x180007994  cmp     byte ptr [rcx+19h], 5
0x180007998  jb      short loc_1800079B6
0x18000799a  mov     rcx, [rcx+10h]
0x18000799e  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x1800079a5  mov     edx, 51h ; 'Q'
0x1800079aa  call    WPP_SF_
0x1800079af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079b6  mov     ebx, 352h
0x1800079bb  jmp     loc_180007F32
0x1800079c0  cmp     rcx, rsi
0x1800079c3  jz      short loc_1800079ED
0x1800079c5  test    [rcx+1Ch], dil
0x1800079c9  jz      short loc_1800079ED
0x1800079cb  cmp     byte ptr [rcx+19h], 5
0x1800079cf  jb      short loc_1800079ED
0x1800079d1  mov     rcx, [rcx+10h]
0x1800079d5  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x1800079dc  mov     edx, 54h ; 'T'
0x1800079e1  call    WPP_SF_
0x1800079e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079ed  mov     ebx, 32Ch
0x1800079f2  jmp     loc_180007F32
0x1800079f7  cmp     ebx, 80420018h
0x1800079fd  jz      loc_180007B23
0x180007a03  cmp     ebx, 8042001Ah
0x180007a09  jz      loc_180007AEC
0x180007a0f  cmp     ebx, 80420020h
0x180007a15  jz      loc_180007AB5
0x180007a1b  cmp     ebx, 80420100h
0x180007a21  jz      loc_180007C99
0x180007a27  cmp     ebx, 80420101h
0x180007a2d  jz      loc_180007D07
0x180007a33  cmp     ebx, 80420102h
0x180007a39  jz      short loc_180007A7E
0x180007a3b  cmp     ebx, 80420103h
0x180007a41  jnz     loc_180007DB5
0x180007a47  cmp     rcx, rsi
0x180007a4a  jz      short loc_180007A74
0x180007a4c  test    [rcx+1Ch], dil
0x180007a50  jz      short loc_180007A74
0x180007a52  cmp     byte ptr [rcx+19h], 5
0x180007a56  jb      short loc_180007A74
0x180007a58  mov     rcx, [rcx+10h]
0x180007a5c  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007a63  mov     edx, 5Ah ; 'Z'
0x180007a68  call    WPP_SF_
0x180007a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a74  mov     ebx, 357h
0x180007a79  jmp     loc_180007F32
0x180007a7e  cmp     rcx, rsi
0x180007a81  jz      short loc_180007AAB
0x180007a83  test    [rcx+1Ch], dil
0x180007a87  jz      short loc_180007AAB
0x180007a89  cmp     byte ptr [rcx+19h], 5
0x180007a8d  jb      short loc_180007AAB
0x180007a8f  mov     rcx, [rcx+10h]
0x180007a93  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007a9a  mov     edx, 59h ; 'Y'
0x180007a9f  call    WPP_SF_
0x180007aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007aab  mov     ebx, 356h
0x180007ab0  jmp     loc_180007F32
0x180007ab5  cmp     rcx, rsi
0x180007ab8  jz      short loc_180007AE2
0x180007aba  test    [rcx+1Ch], dil
0x180007abe  jz      short loc_180007AE2
0x180007ac0  cmp     byte ptr [rcx+19h], 5
0x180007ac4  jb      short loc_180007AE2
0x180007ac6  mov     rcx, [rcx+10h]
0x180007aca  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007ad1  mov     edx, 57h ; 'W'
0x180007ad6  call    WPP_SF_
0x180007adb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ae2  mov     ebx, 354h
0x180007ae7  jmp     loc_180007F32
0x180007aec  cmp     rcx, rsi
0x180007aef  jz      short loc_180007B19
0x180007af1  test    [rcx+1Ch], dil
0x180007af5  jz      short loc_180007B19
0x180007af7  cmp     byte ptr [rcx+19h], 5
0x180007afb  jb      short loc_180007B19
0x180007afd  mov     rcx, [rcx+10h]
0x180007b01  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007b08  mov     edx, 56h ; 'V'
0x180007b0d  call    WPP_SF_
0x180007b12  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b19  mov     ebx, 353h
0x180007b1e  jmp     loc_180007F32
0x180007b23  cmp     rcx, rsi
0x180007b26  jz      short loc_180007B50
0x180007b28  test    [rcx+1Ch], dil
0x180007b2c  jz      short loc_180007B50
0x180007b2e  cmp     byte ptr [rcx+19h], 5
0x180007b32  jb      short loc_180007B50
0x180007b34  mov     rcx, [rcx+10h]
0x180007b38  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007b3f  mov     edx, 55h ; 'U'
0x180007b44  call    WPP_SF_
0x180007b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b50  mov     ebx, 2D2h
0x180007b55  jmp     loc_180007F32
0x180007b5a  cmp     rcx, rsi
0x180007b5d  jz      short loc_180007B87
0x180007b5f  test    [rcx+1Ch], dil
0x180007b63  jz      short loc_180007B87
0x180007b65  cmp     byte ptr [rcx+19h], 5
0x180007b69  jb      short loc_180007B87
0x180007b6b  mov     rcx, [rcx+10h]
0x180007b6f  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007b76  mov     edx, 5Bh ; '['
0x180007b7b  call    WPP_SF_
0x180007b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b87  mov     ebx, 358h
0x180007b8c  jmp     loc_180007F32
0x180007b91  mov     eax, 80420204h
0x180007b96  cmp     ebx, eax
0x180007b98  ja      loc_180007D75
0x180007b9e  jz      loc_180007D3E
0x180007ba4  cmp     ebx, 80420105h
0x180007baa  jz      loc_180007D07
0x180007bb0  cmp     ebx, 80420111h
0x180007bb6  jz      loc_18000791B
0x180007bbc  cmp     ebx, 80420113h
0x180007bc2  jz      loc_180007CD0
0x180007bc8  cmp     ebx, 80420200h
0x180007bce  jz      loc_180007C99
0x180007bd4  cmp     ebx, 80420201h
0x180007bda  jz      loc_180007C62
0x180007be0  cmp     ebx, 80420202h
0x180007be6  jz      short loc_180007C2B
0x180007be8  cmp     ebx, 80420203h
0x180007bee  jnz     loc_180007DB5
0x180007bf4  cmp     rcx, rsi
0x180007bf7  jz      short loc_180007C21
0x180007bf9  test    [rcx+1Ch], dil
0x180007bfd  jz      short loc_180007C21
0x180007bff  cmp     byte ptr [rcx+19h], 5
0x180007c03  jb      short loc_180007C21
0x180007c05  mov     rcx, [rcx+10h]
0x180007c09  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007c10  mov     edx, 5Eh ; '^'
0x180007c15  call    WPP_SF_
0x180007c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c21  mov     ebx, 35Bh
0x180007c26  jmp     loc_180007F32
0x180007c2b  cmp     rcx, rsi
0x180007c2e  jz      short loc_180007C58
0x180007c30  test    [rcx+1Ch], dil
0x180007c34  jz      short loc_180007C58
0x180007c36  cmp     byte ptr [rcx+19h], 5
0x180007c3a  jb      short loc_180007C58
0x180007c3c  mov     rcx, [rcx+10h]
0x180007c40  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007c47  mov     edx, 5Dh ; ']'
0x180007c4c  call    WPP_SF_
0x180007c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c58  mov     ebx, 35Ah
0x180007c5d  jmp     loc_180007F32
0x180007c62  cmp     rcx, rsi
0x180007c65  jz      short loc_180007C8F
0x180007c67  test    [rcx+1Ch], dil
0x180007c6b  jz      short loc_180007C8F
0x180007c6d  cmp     byte ptr [rcx+19h], 5
0x180007c71  jb      short loc_180007C8F
0x180007c73  mov     rcx, [rcx+10h]
0x180007c77  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007c7e  mov     edx, 5Ch ; '\'
0x180007c83  call    WPP_SF_
0x180007c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c8f  mov     ebx, 359h
0x180007c94  jmp     loc_180007F32
0x180007c99  cmp     rcx, rsi
0x180007c9c  jz      short loc_180007CC6
0x180007c9e  test    [rcx+1Ch], dil
0x180007ca2  jz      short loc_180007CC6
0x180007ca4  cmp     byte ptr [rcx+19h], 5
0x180007ca8  jb      short loc_180007CC6
0x180007caa  mov     rcx, [rcx+10h]
0x180007cae  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007cb5  mov     edx, 50h ; 'P'
0x180007cba  call    WPP_SF_
0x180007cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cc6  mov     ebx, 31Eh
0x180007ccb  jmp     loc_180007F32
0x180007cd0  cmp     rcx, rsi
0x180007cd3  jz      short loc_180007CFD
0x180007cd5  test    [rcx+1Ch], dil
0x180007cd9  jz      short loc_180007CFD
0x180007cdb  cmp     byte ptr [rcx+19h], 5
0x180007cdf  jb      short loc_180007CFD
0x180007ce1  mov     rcx, [rcx+10h]
0x180007ce5  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007cec  mov     edx, 66h ; 'f'
0x180007cf1  call    WPP_SF_
0x180007cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cfd  mov     ebx, 2FCh
0x180007d02  jmp     loc_180007F32
0x180007d07  cmp     rcx, rsi
0x180007d0a  jz      short loc_180007D34
0x180007d0c  test    [rcx+1Ch], dil
0x180007d10  jz      short loc_180007D34
0x180007d12  cmp     byte ptr [rcx+19h], 5
0x180007d16  jb      short loc_180007D34
0x180007d18  mov     rcx, [rcx+10h]
0x180007d1c  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007d23  mov     edx, 58h ; 'X'
0x180007d28  call    WPP_SF_
0x180007d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d34  mov     ebx, 355h
0x180007d39  jmp     loc_180007F32
0x180007d3e  cmp     rcx, rsi
0x180007d41  jz      short loc_180007D6B
0x180007d43  test    [rcx+1Ch], dil
0x180007d47  jz      short loc_180007D6B
0x180007d49  cmp     byte ptr [rcx+19h], 5
0x180007d4d  jb      short loc_180007D6B
0x180007d4f  mov     rcx, [rcx+10h]
0x180007d53  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180007d5a  mov     edx, 5Fh ; '_'
0x180007d5f  call    WPP_SF_
0x180007d64  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d6b  mov     ebx, 35Ch
0x180007d70  jmp     loc_180007F32
0x180007d75  cmp     ebx, 80420300h
0x180007d7b  jz      loc_180007F00
  ... truncated ...
```
