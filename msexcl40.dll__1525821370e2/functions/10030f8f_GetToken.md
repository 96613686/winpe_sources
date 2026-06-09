# GetToken

- ea: `0x10030f8f`
- end: `0x100313c5`
- name: `GetToken`
- size: `1078`
- prototype: `HRESULT __stdcall(DWORD cPolicyChain, PPOLICY_ELEMENT pPolicyChain, PGENERIC_XML_TOKEN *securityToken, PINFORMATIONCARD_CRYPTO_HANDLE *phProofTokenCrypto)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10031545`

## callees

- `0x10030d60`
- `0x10030daf`
- `0x10030ddd`
- `0x10030e30`
- `0x10030f8f`

## pseudocode

```c
HRESULT __stdcall GetToken(
        DWORD cPolicyChain,
        PPOLICY_ELEMENT pPolicyChain,
        PGENERIC_XML_TOKEN *securityToken,
        PINFORMATIONCARD_CRYPTO_HANDLE *phProofTokenCrypto)
{
  _WORD *v4; // ecx
  _WORD *v5; // ebx
  unsigned __int16 Char; // ax
  unsigned int v7; // edi
  HRESULT result; // eax
  int v9; // ecx
  char v10; // cl
  int v11; // eax
  int v12; // ecx
  HRESULT v13; // [esp-8h] [ebp-10h]
  HRESULT v14; // [esp-8h] [ebp-10h]
  HRESULT v15; // [esp-8h] [ebp-10h]

  v5 = v4;
  Char = GetChar(0);
  v7 = Char;
  if ( !Char )
    return 51;
  v9 = Char;
  if ( Char > 0x48u )
  {
    if ( Char > 0x64u )
    {
      switch ( Char )
      {
        case 'e':
LABEL_96:
          if ( PeekChar(43, 0) == 1 )
          {
            ++dword_1003ABFC;
            result = ((_WORD)v7 == 101) + 43;
          }
          else
          {
            if ( PeekChar(45, 0) != 1 )
              goto LABEL_101;
            ++dword_1003ABFC;
            result = ((_WORD)v7 == 101) + 41;
          }
LABEL_100:
          if ( result )
            return result;
          goto LABEL_101;
        case 'g':
          goto LABEL_27;
        case 'h':
LABEL_89:
          v12 = PeekChar(104, 1);
          if ( v12 == 1 )
            ++dword_1003ABFC;
          byte_1003A772 |= 0x10u;
          result = 22;
          if ( v12 != 1 )
            result = 20;
          goto LABEL_100;
      }
      if ( Char != 109 )
      {
        if ( Char != 115 )
        {
          if ( Char != 121 )
            goto LABEL_101;
          goto LABEL_71;
        }
LABEL_76:
        v11 = PeekChar(115, 1);
        if ( v11 == 1 )
          ++dword_1003ABFC;
        byte_1003A772 |= 0x40u;
        result = 26 - (v11 != 1);
        goto LABEL_100;
      }
    }
    else
    {
      if ( Char == 100 )
        goto LABEL_55;
      if ( Char != 77 )
      {
        if ( Char != 83 )
        {
          if ( Char != 89 )
          {
            if ( Char == 91 || Char == 92 )
            {
LABEL_51:
              result = GetCommonToken(v7, v5);
              if ( result == 27 || result == 28 || result == 29 )
                byte_1003A772 |= 0x77u;
              goto LABEL_100;
            }
            if ( Char == 95 )
            {
              if ( PeekString(L";", 0) == 1 )
                goto LABEL_101;
              goto LABEL_51;
            }
            if ( Char != 97 )
              goto LABEL_101;
            if ( PeekString(L"m/pm", 0) == 1 )
            {
              v13 = 31;
              goto LABEL_31;
            }
            if ( PeekString(L"/p", 0) != 1 )
              goto LABEL_101;
            dword_1003ABFC += 2;
            v13 = 33;
LABEL_32:
            byte_1003A772 |= 0x10u;
            dword_1003AC04 = 1;
            return v13;
          }
LABEL_71:
          if ( PeekString(L"yyy", 1) != 1 )
          {
            if ( PeekChar(121, 1) != 1 )
              goto LABEL_101;
            ++dword_1003ABFC;
            v13 = 17;
LABEL_73:
            byte_1003A772 |= 4u;
            return v13;
          }
LABEL_72:
          dword_1003ABFC += 3;
          v13 = 18;
          goto LABEL_73;
        }
        goto LABEL_76;
      }
    }
    if ( PeekString(L"mmmm", 1) == 1 )
    {
      dword_1003ABFC += 4;
      v15 = 16;
    }
    else if ( PeekString(L"mmm", 1) == 1 )
    {
      dword_1003ABFC += 3;
      v15 = 15;
    }
    else if ( PeekString(L"mm", 1) == 1 )
    {
      dword_1003ABFC += 2;
      v15 = 14;
    }
    else if ( PeekChar(109, 1) == 1 )
    {
      ++dword_1003ABFC;
      v15 = 13;
    }
    else
    {
      v15 = 12;
    }
    byte_1003A772 |= 2u;
    result = v15;
    goto LABEL_100;
  }
  if ( Char == 72 )
    goto LABEL_89;
  result = 48;
  if ( v7 > 0x30 )
  {
    switch ( v7 )
    {
      case ';':
        return 50;
      case '?':
        return 39;
      case '@':
        return result;
    }
    if ( v7 != 65 )
    {
      if ( v7 != 68 )
      {
        if ( v7 != 69 )
        {
          if ( v7 != 71 )
            goto LABEL_101;
LABEL_27:
          if ( PeekString(L"eneral", 1) == 1 )
          {
            dword_1003ABFC += 6;
            return 36;
          }
          if ( PeekString(L"gge", 1) != 1 )
            goto LABEL_101;
          goto LABEL_72;
        }
        goto LABEL_96;
      }
LABEL_55:
      if ( PeekString(L"ddd", 1) == 1 )
      {
        dword_1003ABFC += 3;
        v14 = 11;
      }
      else
      {
        if ( PeekString(L"dd", 1) != 1 )
        {
          if ( PeekChar(100, 1) == 1 )
          {
            ++dword_1003ABFC;
            v14 = 9;
          }
          else
          {
            v14 = 8;
          }
          v10 = byte_1003A772 | 1;
          goto LABEL_64;
        }
        dword_1003ABFC += 2;
        v14 = 10;
      }
      v10 = byte_1003A772 | 8;
LABEL_64:
      result = v14;
      byte_1003A772 = v10;
      goto LABEL_100;
    }
    if ( PeekString(L"M/PM", 0) == 1 )
    {
      v13 = 30;
LABEL_31:
      dword_1003ABFC += 4;
      goto LABEL_32;
    }
    if ( PeekString(L"/P", 0) != 1 )
      goto LABEL_101;
    dword_1003ABFC += 2;
    v13 = 32;
    goto LABEL_32;
  }
  if ( v9 == 48 )
    return 37;
  switch ( v7 )
  {
    case '"':
      goto LABEL_51;
    case '#':
      return 38;
    case '%':
      return 45;
    case '*':
      goto LABEL_51;
    case ',':
      return 47;
    case '.':
      return 40;
  }
  if ( v7 != 47 )
  {
LABEL_101:
    *v5 = v7;
    v13 = 3;
    v5[1] = 0;
    return v13;
  }
  return 46;
}

```

## disassembly

```asm
0x10030f8f  mov     edi, edi
0x10030f91  push    ebx
0x10030f92  mov     ebx, ecx
0x10030f94  xor     ecx, ecx
0x10030f96  push    edi
0x10030f97  call    GetChar
0x10030f9c  movzx   edi, ax
0x10030f9f  test    di, di
0x10030fa2  jnz     short loc_10030FAC
0x10030fa4  push    33h ; '3'
0x10030fa6  pop     eax
0x10030fa7  jmp     loc_100313C2
0x10030fac  mov     ecx, edi
0x10030fae  push    esi
0x10030faf  cmp     ecx, 48h ; 'H'
0x10030fb2  ja      loc_100310DF
0x10030fb8  jz      loc_10031326
0x10030fbe  push    30h ; '0'
0x10030fc0  pop     eax
0x10030fc1  cmp     ecx, eax
0x10030fc3  ja      short loc_10031023
0x10030fc5  jz      short loc_1003101C
0x10030fc7  sub     ecx, 22h ; '"'
0x10030fca  jz      loc_10031174
0x10030fd0  sub     ecx, 1
0x10030fd3  jz      short loc_10031015
0x10030fd5  dec     ecx
0x10030fd6  sub     ecx, 1
0x10030fd9  jz      short loc_1003100E
0x10030fdb  sub     ecx, 5
0x10030fde  jz      loc_10031174
0x10030fe4  dec     ecx
0x10030fe5  sub     ecx, 1
0x10030fe8  jz      short loc_10031007
0x10030fea  dec     ecx
0x10030feb  sub     ecx, 1
0x10030fee  jz      short loc_10031000
0x10030ff0  sub     ecx, 1
0x10030ff3  jnz     loc_100313B5
0x10030ff9  push    2Eh ; '.'
0x10030ffb  jmp     loc_100313C0
0x10031000  push    28h ; '('
0x10031002  jmp     loc_100313C0
0x10031007  push    2Fh ; '/'
0x10031009  jmp     loc_100313C0
0x1003100e  push    2Dh ; '-'
0x10031010  jmp     loc_100313C0
0x10031015  push    26h ; '&'
0x10031017  jmp     loc_100313C0
0x1003101c  push    25h ; '%'
0x1003101e  jmp     loc_100313C0
0x10031023  sub     ecx, 3Bh ; ';'
0x10031026  jz      loc_100310D8
0x1003102c  sub     ecx, 4
0x1003102f  jz      loc_100310D1
0x10031035  sub     ecx, 1
0x10031038  jz      loc_100313C1
0x1003103e  sub     ecx, 1
0x10031041  jz      short loc_10031084
0x10031043  sub     ecx, 3
0x10031046  jz      loc_1003119C
0x1003104c  sub     ecx, 1
0x1003104f  jz      loc_10031368
0x10031055  dec     ecx
0x10031056  sub     ecx, 1
0x10031059  jnz     loc_100313B5
0x1003105f  xor     esi, esi
0x10031061  mov     ecx, offset aEneral; "eneral"
0x10031066  inc     esi
0x10031067  mov     edx, esi
0x10031069  call    PeekString
0x1003106e  cmp     eax, esi
0x10031070  jnz     loc_10031353
0x10031076  add     dword_1003ABFC, 6
0x1003107d  push    24h ; '$'
0x1003107f  jmp     loc_100313C0
0x10031084  xor     edx, edx
0x10031086  mov     ecx, offset aMPm; "M/PM"
0x1003108b  call    PeekString
0x10031090  xor     esi, esi
0x10031092  inc     esi
0x10031093  cmp     eax, esi
0x10031095  jnz     short loc_100310B2
0x10031097  push    1Eh
0x10031099  add     dword_1003ABFC, 4
0x100310a0  or      byte_1003A772, 10h
0x100310a7  mov     dword_1003AC04, esi
0x100310ad  jmp     loc_100313C0
0x100310b2  xor     edx, edx
0x100310b4  mov     ecx, offset aP; "/P"
0x100310b9  call    PeekString
0x100310be  cmp     eax, esi
0x100310c0  jnz     loc_100313B5
0x100310c6  add     dword_1003ABFC, 2
0x100310cd  push    20h ; ' '
0x100310cf  jmp     short loc_100310A0
0x100310d1  push    27h ; '''
0x100310d3  jmp     loc_100313C0
0x100310d8  push    32h ; '2'
0x100310da  jmp     loc_100313C0
0x100310df  cmp     ecx, 64h ; 'd'
0x100310e2  ja      loc_1003120D
0x100310e8  jz      loc_1003119C
0x100310ee  sub     ecx, 4Dh ; 'M'
0x100310f1  jz      loc_100312AB
0x100310f7  sub     ecx, 6
0x100310fa  jz      loc_10031280
0x10031100  sub     ecx, 6
0x10031103  jz      loc_1003123C
0x10031109  dec     ecx
0x1003110a  sub     ecx, 1
0x1003110d  jz      short loc_10031174
0x1003110f  sub     ecx, 1
0x10031112  jz      short loc_10031174
0x10031114  sub     ecx, 3
0x10031117  jz      short loc_1003115F
0x10031119  dec     ecx
0x1003111a  sub     ecx, 1
0x1003111d  jnz     loc_100313B5
0x10031123  xor     edx, edx
0x10031125  mov     ecx, offset aMPm_0; "m/pm"
0x1003112a  call    PeekString
0x1003112f  xor     esi, esi
0x10031131  inc     esi
0x10031132  cmp     eax, esi
0x10031134  jnz     short loc_1003113D
0x10031136  push    1Fh
0x10031138  jmp     loc_10031099
0x1003113d  xor     edx, edx
0x1003113f  mov     ecx, offset aP_0; "/p"
0x10031144  call    PeekString
0x10031149  cmp     eax, esi
0x1003114b  jnz     loc_100313B5
0x10031151  add     dword_1003ABFC, 2
0x10031158  push    21h ; '!'
0x1003115a  jmp     loc_100310A0
0x1003115f  xor     edx, edx
0x10031161  mov     ecx, offset asc_10004CC4; ";"
0x10031166  call    PeekString
0x1003116b  cmp     eax, 1
0x1003116e  jz      loc_100313B5
0x10031174  mov     edx, ebx
0x10031176  mov     ecx, edi
0x10031178  call    GetCommonToken
0x1003117d  cmp     eax, 1Bh
0x10031180  jz      short loc_10031190
0x10031182  cmp     eax, 1Ch
0x10031185  jz      short loc_10031190
0x10031187  cmp     eax, 1Dh
0x1003118a  jnz     loc_100313B1
0x10031190  or      byte_1003A772, 77h
0x10031197  jmp     loc_100313B1
0x1003119c  xor     esi, esi
0x1003119e  mov     ecx, offset aDdd; "ddd"
0x100311a3  inc     esi
0x100311a4  mov     edx, esi
0x100311a6  call    PeekString
0x100311ab  cmp     eax, esi
0x100311ad  jnz     short loc_100311C3
0x100311af  add     dword_1003ABFC, 3
0x100311b6  push    0Bh
0x100311b8  mov     cl, byte_1003A772
0x100311be  or      cl, 8
0x100311c1  jmp     short loc_10031201
0x100311c3  mov     edx, esi
0x100311c5  mov     ecx, offset aDd; "dd"
0x100311ca  call    PeekString
0x100311cf  cmp     eax, esi
0x100311d1  jnz     short loc_100311DE
0x100311d3  add     dword_1003ABFC, 2
0x100311da  push    0Ah
0x100311dc  jmp     short loc_100311B8
0x100311de  push    64h ; 'd'
0x100311e0  mov     edx, esi
0x100311e2  pop     ecx
0x100311e3  call    PeekChar
0x100311e8  mov     cl, byte_1003A772
0x100311ee  cmp     eax, esi
0x100311f0  jnz     short loc_100311FC
0x100311f2  inc     dword_1003ABFC
0x100311f8  push    9
0x100311fa  jmp     short loc_100311FE
0x100311fc  push    8
0x100311fe  or      cl, 1
0x10031201  pop     eax
0x10031202  mov     byte_1003A772, cl
0x10031208  jmp     loc_100313B1
0x1003120d  sub     ecx, 65h ; 'e'
0x10031210  jz      loc_10031368
0x10031216  dec     ecx
0x10031217  sub     ecx, 1
0x1003121a  jz      loc_1003105F
0x10031220  sub     ecx, 1
0x10031223  jz      loc_10031326
0x10031229  sub     ecx, 5
0x1003122c  jz      short loc_100312AB
0x1003122e  sub     ecx, 6
0x10031231  jz      short loc_10031280
0x10031233  sub     ecx, 6
0x10031236  jnz     loc_100313B5
0x1003123c  xor     esi, esi
0x1003123e  mov     ecx, offset aYyy; "yyy"
0x10031243  inc     esi
0x10031244  mov     edx, esi
0x10031246  call    PeekString
0x1003124b  cmp     eax, esi
0x1003124d  jnz     short loc_10031264
0x1003124f  add     dword_1003ABFC, 3
0x10031256  push    12h
0x10031258  or      byte_1003A772, 4
0x1003125f  jmp     loc_100313C0
0x10031264  push    79h ; 'y'
0x10031266  mov     edx, esi
0x10031268  pop     ecx
0x10031269  call    PeekChar
0x1003126e  cmp     eax, esi
0x10031270  jnz     loc_100313B5
0x10031276  inc     dword_1003ABFC
0x1003127c  push    11h
0x1003127e  jmp     short loc_10031258
0x10031280  xor     esi, esi
0x10031282  push    73h ; 's'
0x10031284  inc     esi
0x10031285  mov     edx, esi
0x10031287  pop     ecx
0x10031288  call    PeekChar
0x1003128d  cmp     eax, esi
0x1003128f  jnz     short loc_10031297
0x10031291  inc     dword_1003ABFC
0x10031297  or      byte_1003A772, 40h
0x1003129e  dec     eax
0x1003129f  neg     eax
0x100312a1  sbb     eax, eax
0x100312a3  add     eax, 1Ah
0x100312a6  jmp     loc_100313B1
0x100312ab  xor     esi, esi
0x100312ad  mov     ecx, offset aMmmm_0; "mmmm"
0x100312b2  inc     esi
0x100312b3  mov     edx, esi
0x100312b5  call    PeekString
0x100312ba  cmp     eax, esi
0x100312bc  jnz     short loc_100312C9
0x100312be  add     dword_1003ABFC, 4
0x100312c5  push    10h
0x100312c7  jmp     short loc_10031319
0x100312c9  mov     edx, esi
0x100312cb  mov     ecx, offset aMmm; "mmm"
0x100312d0  call    PeekString
0x100312d5  cmp     eax, esi
0x100312d7  jnz     short loc_100312E4
0x100312d9  add     dword_1003ABFC, 3
0x100312e0  push    0Fh
0x100312e2  jmp     short loc_10031319
0x100312e4  mov     edx, esi
0x100312e6  mov     ecx, offset aMm; "mm"
0x100312eb  call    PeekString
0x100312f0  cmp     eax, esi
0x100312f2  jnz     short loc_100312FF
0x100312f4  add     dword_1003ABFC, 2
0x100312fb  push    0Eh
0x100312fd  jmp     short loc_10031319
0x100312ff  push    6Dh ; 'm'
0x10031301  mov     edx, esi
0x10031303  pop     ecx
0x10031304  call    PeekChar
0x10031309  cmp     eax, esi
0x1003130b  jnz     short loc_10031317
0x1003130d  inc     dword_1003ABFC
0x10031313  push    0Dh
0x10031315  jmp     short loc_10031319
0x10031317  push    0Ch
0x10031319  or      byte_1003A772, 2
0x10031320  pop     eax
0x10031321  jmp     loc_100313B1
0x10031326  xor     esi, esi
0x10031328  push    68h ; 'h'
0x1003132a  inc     esi
0x1003132b  mov     edx, esi
0x1003132d  pop     ecx
0x1003132e  call    PeekChar
0x10031333  mov     ecx, eax
0x10031335  cmp     ecx, esi
0x10031337  jnz     short loc_1003133F
0x10031339  inc     dword_1003ABFC
0x1003133f  or      byte_1003A772, 10h
0x10031346  cmp     ecx, esi
0x10031348  push    16h
0x1003134a  pop     eax
0x1003134b  push    14h
0x1003134d  pop     edx
0x1003134e  cmovnz  eax, edx
0x10031351  jmp     short loc_100313B1
0x10031353  mov     edx, esi
0x10031355  mov     ecx, offset aGge; "gge"
0x1003135a  call    PeekString
0x1003135f  cmp     eax, esi
0x10031361  jnz     short loc_100313B5
0x10031363  jmp     loc_1003124F
0x10031368  push    2Bh ; '+'
0x1003136a  xor     edx, edx
  ... truncated ...
```
