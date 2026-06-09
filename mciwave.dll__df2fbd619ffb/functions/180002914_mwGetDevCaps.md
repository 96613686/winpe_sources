# mwGetDevCaps

- ea: `0x180002914`
- end: `0x1800029ed`
- name: `mwGetDevCaps`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003614`

## callees

- `0x180002914`

## pseudocode

```c
__int64 __fastcall mwGetDevCaps(__int64 a1, int a2, __int64 a3)
{
  unsigned int v3; // edx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  int v15; // eax

  v3 = a2 & 0xFFFFFFFC;
  if ( !v3 )
    return 273;
  v4 = *(_DWORD *)(a3 + 12);
  if ( !v4 )
    return 273;
  if ( v3 == 256 && *(_DWORD *)(a3 + 12) == (*(_DWORD *)(a3 + 12) & 0x400F) )
  {
    if ( v4 > 6 )
    {
      v10 = v4 - 7;
      if ( !v10 )
        goto LABEL_26;
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( !v12 )
          goto LABEL_12;
        v13 = v12 - 16376;
        if ( v13 )
        {
          if ( v13 != 1 )
            return 274;
          v15 = cWaveOutMax;
        }
        else
        {
          v15 = cWaveInMax;
        }
        *(_DWORD *)(a3 + 8) = v15;
        return 0;
      }
      v9 = cWaveOutMax;
    }
    else
    {
      if ( v4 == 6 )
        goto LABEL_12;
      v5 = v4 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( !v6 )
          goto LABEL_12;
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( !v8 )
          {
            *(_DWORD *)(a3 + 8) = 34210314;
            return 0x10000;
          }
          if ( v8 == 1 )
          {
LABEL_12:
            *(_DWORD *)(a3 + 8) = 34865153;
            return 0x10000;
          }
          return 274;
        }
LABEL_26:
        *(_DWORD *)(a3 + 8) = 34799616;
        return 0x10000;
      }
      v9 = cWaveInMax;
    }
    *(_DWORD *)(a3 + 8) = v9 != 0 ? 34865153 : 34799616;
    return 0x10000;
  }
  return 259;
}

```

## disassembly

```asm
0x180002914  and     edx, 0FFFFFFFCh
0x180002917  jz      loc_1800029E7
0x18000291d  mov     ecx, [r8+0Ch]
0x180002921  test    ecx, ecx
0x180002923  jz      loc_1800029E7
0x180002929  cmp     edx, 100h
0x18000292f  jnz     loc_1800029E1
0x180002935  mov     eax, ecx
0x180002937  and     eax, 400Fh
0x18000293c  cmp     ecx, eax
0x18000293e  jnz     loc_1800029E1
0x180002944  cmp     ecx, 6
0x180002947  ja      short loc_180002994
0x180002949  jz      short loc_180002964
0x18000294b  sub     ecx, 1
0x18000294e  jz      short loc_180002978
0x180002950  sub     ecx, 1
0x180002953  jz      short loc_180002964
0x180002955  sub     ecx, 1
0x180002958  jz      short loc_1800029D3
0x18000295a  sub     ecx, 1
0x18000295d  jz      short loc_18000296E
0x18000295f  cmp     ecx, 1
0x180002962  jnz     short loc_1800029B0
0x180002964  mov     dword ptr [r8+8], 2140001h
0x18000296c  jmp     short loc_1800029DB
0x18000296e  mov     dword ptr [r8+8], 20A020Ah
0x180002976  jmp     short loc_1800029DB
0x180002978  mov     eax, cs:cWaveInMax
0x18000297e  neg     eax
0x180002980  sbb     ecx, ecx
0x180002982  and     ecx, 10001h
0x180002988  add     ecx, 2130000h
0x18000298e  mov     [r8+8], ecx
0x180002992  jmp     short loc_1800029DB
0x180002994  sub     ecx, 7
0x180002997  jz      short loc_1800029D3
0x180002999  sub     ecx, 1
0x18000299c  jz      short loc_1800029CB
0x18000299e  sub     ecx, 1
0x1800029a1  jz      short loc_180002964
0x1800029a3  sub     ecx, 3FF8h
0x1800029a9  jz      short loc_1800029BE
0x1800029ab  cmp     ecx, 1
0x1800029ae  jz      short loc_1800029B6
0x1800029b0  mov     eax, 112h
0x1800029b5  retn
0x1800029b6  mov     eax, cs:cWaveOutMax
0x1800029bc  jmp     short loc_1800029C4
0x1800029be  mov     eax, cs:cWaveInMax
0x1800029c4  mov     [r8+8], eax
0x1800029c8  xor     eax, eax
0x1800029ca  retn
0x1800029cb  mov     eax, cs:cWaveOutMax
0x1800029d1  jmp     short loc_18000297E
0x1800029d3  mov     dword ptr [r8+8], 2130000h
0x1800029db  mov     eax, 10000h
0x1800029e0  retn
0x1800029e1  mov     eax, 103h
0x1800029e6  retn
0x1800029e7  mov     eax, 111h
0x1800029ec  retn
```
