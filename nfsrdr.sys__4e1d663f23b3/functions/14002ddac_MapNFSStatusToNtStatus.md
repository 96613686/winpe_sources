# MapNFSStatusToNtStatus

- ea: `0x14002ddac`
- end: `0x14002deba`
- name: `MapNFSStatusToNtStatus`
- size: `270`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x1400029d0`
- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x1400132cc`
- `0x140023dd0`
- `0x14002a5f0`
- `0x14002a9e0`
- `0x14002b138`

## callees

- `0x14002ddac`

## pseudocode

```c
__int64 __fastcall MapNFSStatusToNtStatus(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  __int64 result; // rax
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx

  if ( a1 <= 0x3F )
  {
    if ( a1 == 63 )
      return 3221225734LL;
    if ( a1 > 0x13 )
    {
      v8 = a1 - 20;
      if ( !v8 )
        return 3221225731LL;
      v9 = v8 - 1;
      if ( !v9 )
        return 3221225658LL;
      v10 = v9 - 1;
      if ( !v10 )
        return 3221225624LL;
      v11 = v10 - 5;
      if ( !v11 )
        return 3221225599LL;
      v12 = v11 - 1;
      if ( !v12 )
        return 3221225599LL;
      v6 = v12 - 2;
      if ( !v6 )
        return 3221225634LL;
LABEL_44:
      result = 3221225473LL;
      if ( v6 != 1 )
        return result;
      return 3221225668LL;
    }
    if ( a1 != 19 )
    {
      if ( !a1 )
        return 0;
      v1 = a1 - 1;
      if ( !v1 )
        return 3221225506LL;
      v2 = v1 - 1;
      if ( !v2 )
        return 3221225487LL;
      v3 = v2 - 3;
      if ( !v3 )
        return 3221225861LL;
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 7;
        if ( v5 )
        {
          v6 = v5 - 4;
          if ( !v6 )
            return 3221225525LL;
          goto LABEL_44;
        }
        return 3221225506LL;
      }
    }
    return 3221225486LL;
  }
  if ( a1 > 0x2713 )
  {
    v17 = a1 - 10004;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v6 = v19 - 1;
          if ( v6 )
            goto LABEL_44;
        }
      }
    }
  }
  else if ( a1 != 10003 )
  {
    v13 = a1 - 66;
    if ( !v13 )
      return 3221225729LL;
    v14 = v13 - 3;
    if ( !v14 )
      return 3221225540LL;
    v15 = v14 - 1;
    if ( !v15 )
      return 3221225480LL;
    v16 = v15 - 1;
    if ( v16 )
    {
      v6 = v16 - 9930;
      if ( v6 )
        goto LABEL_44;
      return 3221225480LL;
    }
  }
  return 3221225668LL;
}

```

## disassembly

```asm
0x14002ddac  cmp     ecx, 3Fh ; '?'
0x14002ddaf  ja      loc_14002DE57
0x14002ddb5  jz      loc_14002DE50
0x14002ddbb  cmp     ecx, 13h
0x14002ddbe  ja      short loc_14002DE0F
0x14002ddc0  jz      short loc_14002DE08
0x14002ddc2  test    ecx, ecx
0x14002ddc4  jz      short loc_14002DE04
0x14002ddc6  sub     ecx, 1
0x14002ddc9  jz      short loc_14002DDFD
0x14002ddcb  sub     ecx, 1
0x14002ddce  jz      short loc_14002DDF6
0x14002ddd0  sub     ecx, 3
0x14002ddd3  jz      short loc_14002DDEF
0x14002ddd5  sub     ecx, 1
0x14002ddd8  jz      short loc_14002DE08
0x14002ddda  sub     ecx, 7
0x14002dddd  jz      short loc_14002DDFD
0x14002dddf  sub     ecx, 4
0x14002dde2  jnz     loc_14002DEAA
0x14002dde8  mov     eax, 0C0000035h
0x14002dded  retn
0x14002ddef  mov     eax, 0C0000185h
0x14002ddf4  retn
0x14002ddf6  mov     eax, 0C000000Fh
0x14002ddfb  retn
0x14002ddfd  mov     eax, 0C0000022h
0x14002de02  retn
0x14002de04  xor     eax, eax
0x14002de06  retn
0x14002de08  mov     eax, 0C000000Eh
0x14002de0d  retn
0x14002de0f  sub     ecx, 14h
0x14002de12  jz      short loc_14002DE49
0x14002de14  sub     ecx, 1
0x14002de17  jz      short loc_14002DE42
0x14002de19  sub     ecx, 1
0x14002de1c  jz      short loc_14002DE3B
0x14002de1e  sub     ecx, 5
0x14002de21  jz      short loc_14002DE34
0x14002de23  sub     ecx, 1
0x14002de26  jz      short loc_14002DE34
0x14002de28  sub     ecx, 2
0x14002de2b  jnz     short loc_14002DEAA
0x14002de2d  mov     eax, 0C00000A2h
0x14002de32  retn
0x14002de34  mov     eax, 0C000007Fh
0x14002de39  retn
0x14002de3b  mov     eax, 0C0000098h
0x14002de40  retn
0x14002de42  mov     eax, 0C00000BAh
0x14002de47  retn
0x14002de49  mov     eax, 0C0000103h
0x14002de4e  retn
0x14002de50  mov     eax, 0C0000106h
0x14002de55  retn
0x14002de57  mov     eax, 2713h
0x14002de5c  cmp     ecx, eax
0x14002de5e  ja      short loc_14002DE93
0x14002de60  jz      short loc_14002DEB4
0x14002de62  sub     ecx, 42h ; 'B'
0x14002de65  jz      short loc_14002DE8C
0x14002de67  sub     ecx, 3
0x14002de6a  jz      short loc_14002DE85
0x14002de6c  sub     ecx, 1
0x14002de6f  jz      short loc_14002DE7E
0x14002de71  sub     ecx, 1
0x14002de74  jz      short loc_14002DEB4
0x14002de76  sub     ecx, 26CAh
0x14002de7c  jnz     short loc_14002DEAA
0x14002de7e  mov     eax, 0C0000008h
0x14002de83  retn
0x14002de85  mov     eax, 0C0000044h
0x14002de8a  retn
0x14002de8c  mov     eax, 0C0000101h
0x14002de91  retn
0x14002de93  sub     ecx, 2714h
0x14002de99  jz      short loc_14002DEB4
0x14002de9b  sub     ecx, 1
0x14002de9e  jz      short loc_14002DEB4
0x14002dea0  sub     ecx, 1
0x14002dea3  jz      short loc_14002DEB4
0x14002dea5  sub     ecx, 1
0x14002dea8  jz      short loc_14002DEB4
0x14002deaa  mov     eax, 0C0000001h
0x14002deaf  cmp     ecx, 1
0x14002deb2  jnz     short locret_14002DEB9
0x14002deb4  mov     eax, 0C00000C4h
0x14002deb9  retn
```
