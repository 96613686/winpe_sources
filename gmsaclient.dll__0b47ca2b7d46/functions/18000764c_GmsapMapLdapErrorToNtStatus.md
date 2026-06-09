# GmsapMapLdapErrorToNtStatus

- ea: `0x18000764c`
- end: `0x180007865`
- name: `GmsapMapLdapErrorToNtStatus`
- size: `537`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a38`
- `0x180006f68`
- `0x180007378`

## callees

- `0x18000764c`

## pseudocode

```c
__int64 __fastcall GmsapMapLdapErrorToNtStatus(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
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
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx

  if ( a1 <= 0x33 )
  {
    if ( a1 == 51 )
      return 3221226149LL;
    if ( a1 <= 0x10 )
    {
      if ( a1 != 16 )
      {
        if ( a1 <= 6 )
        {
          if ( a1 != 6 )
          {
            if ( !a1 )
              return 0;
            v1 = a1 - 1;
            if ( !v1 )
              return 3221225782LL;
            v2 = v1 - 1;
            if ( !v2 )
              return 3221225800LL;
            v3 = v2 - 1;
            if ( v3 )
            {
              if ( v3 == 1 )
                return 261;
              return 3221225473LL;
            }
            return 3221226000LL;
          }
          return 3221225473LL;
        }
        v5 = a1 - 7;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            v7 = v6 - 1;
            if ( !v7 )
              return 261;
            v8 = v7 - 1;
            if ( !v8 )
              return 261;
            v9 = v8 - 1;
            if ( !v9 )
              return 3221226177LL;
            goto LABEL_22;
          }
        }
        return 3221225506LL;
      }
      return 3221225485LL;
    }
    if ( a1 > 0x21 )
    {
      v15 = a1 - 34;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( !v16 )
          return 3221225473LL;
        v17 = v16 - 1;
        if ( !v17 )
          return 3221225473LL;
        v18 = v17 - 12;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( !v19 )
            return 3221225581LL;
          if ( v19 != 1 )
            return 3221225473LL;
        }
        return 3221225506LL;
      }
      return 3221226146LL;
    }
    if ( a1 == 33 )
      return 3221225473LL;
    v10 = a1 - 17;
    if ( !v10 )
      return 3221225473LL;
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 != 11 )
              return 3221225473LL;
            return 3221226021LL;
          }
          return 3221226146LL;
        }
        return 3221226500LL;
      }
    }
    return 3221225485LL;
  }
  if ( a1 <= 0x52 )
  {
    if ( a1 == 82 )
      return 3221225473LL;
    if ( a1 <= 0x43 )
    {
      if ( a1 == 67 )
        return 3221225506LL;
      v20 = a1 - 52;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( !v22 )
            return 3221225473LL;
          v23 = v22 - 10;
          if ( !v23 )
            return 3221225523LL;
          v9 = v23 - 1;
          if ( !v9 )
            return 3221226155LL;
LABEL_22:
          if ( v9 != 1 )
            return 3221225473LL;
          return 3221225659LL;
        }
      }
      return 3221226150LL;
    }
    v24 = a1 - 68;
    if ( !v24 )
      return 3221226500LL;
    v25 = v24 - 1;
    if ( !v25 )
      return 3221225506LL;
    v26 = v25 - 1;
    if ( v26 )
    {
      v27 = v26 - 1;
      if ( !v27 )
        return 3221225659LL;
      if ( v27 != 10 )
        return 3221225473LL;
      return 3221226150LL;
    }
    return 3221225507LL;
  }
  if ( a1 > 0x59 )
  {
    v33 = a1 - 90;
    if ( v33 )
    {
      v34 = v33 - 1;
      if ( v34 )
      {
        v35 = v34 - 1;
        if ( !v35 )
          return 3221225659LL;
        v36 = v35 - 1;
        if ( !v36 )
          return 3221226021LL;
        if ( v36 - 1 >= 2 )
          return 3221225473LL;
        return 3221225507LL;
      }
      return 3221226038LL;
    }
    else
    {
      return 3221225495LL;
    }
  }
  else
  {
    if ( a1 == 89 )
      return 3221225485LL;
    v28 = a1 - 83;
    if ( v28 && (v29 = v28 - 1) != 0 )
    {
      v30 = v29 - 1;
      if ( !v30 )
        return 3221226000LL;
      v31 = v30 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( !v32 )
          return 3221225485LL;
        if ( v32 != 1 )
          return 3221225473LL;
        return 3221225760LL;
      }
      else
      {
        return 3221225578LL;
      }
    }
    else
    {
      return 3221225668LL;
    }
  }
}

```

## disassembly

```asm
0x18000764c  cmp     ecx, 33h ; '3'
0x18000764f  ja      loc_180007769
0x180007655  jz      loc_180007762
0x18000765b  cmp     ecx, 10h
0x18000765e  ja      loc_1800076E8
0x180007664  jz      loc_180007818
0x18000766a  cmp     ecx, 6
0x18000766d  ja      short loc_1800076B1
0x18000766f  jz      loc_1800077D3
0x180007675  test    ecx, ecx
0x180007677  jz      short loc_1800076AD
0x180007679  sub     ecx, 1
0x18000767c  jz      short loc_1800076A6
0x18000767e  sub     ecx, 1
0x180007681  jz      short loc_18000769F
0x180007683  sub     ecx, 1
0x180007686  jz      short loc_180007698
0x180007688  sub     ecx, 1
0x18000768b  jnz     loc_1800077D3
0x180007691  mov     eax, 105h
0x180007696  retn
0x180007698  mov     eax, 0C0000210h
0x18000769d  retn
0x18000769f  mov     eax, 0C0000148h
0x1800076a4  retn
0x1800076a6  mov     eax, 0C0000136h
0x1800076ab  retn
0x1800076ad  xor     eax, eax
0x1800076af  retn
0x1800076b1  sub     ecx, 7
0x1800076b4  jz      short loc_1800076E1
0x1800076b6  sub     ecx, 1
0x1800076b9  jz      short loc_1800076E1
0x1800076bb  sub     ecx, 1
0x1800076be  jz      short loc_180007691
0x1800076c0  sub     ecx, 1
0x1800076c3  jz      short loc_180007691
0x1800076c5  sub     ecx, 1
0x1800076c8  jz      short loc_1800076DA
0x1800076ca  cmp     ecx, 1
0x1800076cd  jnz     loc_1800077D3
0x1800076d3  mov     eax, 0C00000BBh
0x1800076d8  retn
0x1800076da  mov     eax, 0C00002C1h
0x1800076df  retn
0x1800076e1  mov     eax, 0C0000022h
0x1800076e6  retn
0x1800076e8  cmp     ecx, 21h ; '!'
0x1800076eb  ja      short loc_180007733
0x1800076ed  jz      loc_1800077D3
0x1800076f3  sub     ecx, 11h
0x1800076f6  jz      loc_1800077D3
0x1800076fc  sub     ecx, 1
0x1800076ff  jz      loc_180007818
0x180007705  sub     ecx, 1
0x180007708  jz      loc_180007818
0x18000770e  sub     ecx, 1
0x180007711  jz      loc_1800077E1
0x180007717  sub     ecx, 1
0x18000771a  jz      short loc_18000772C
0x18000771c  cmp     ecx, 0Bh
0x18000771f  jnz     loc_1800077D3
0x180007725  mov     eax, 0C0000225h
0x18000772a  retn
0x18000772c  mov     eax, 0C00002A2h
0x180007731  retn
0x180007733  sub     ecx, 22h ; '"'
0x180007736  jz      short loc_18000772C
0x180007738  sub     ecx, 1
0x18000773b  jz      loc_1800077D3
0x180007741  sub     ecx, 1
0x180007744  jz      loc_1800077D3
0x18000774a  sub     ecx, 0Ch
0x18000774d  jz      short loc_1800076E1
0x18000774f  sub     ecx, 1
0x180007752  jz      short loc_18000775B
0x180007754  cmp     ecx, 1
0x180007757  jnz     short loc_1800077D3
0x180007759  jmp     short loc_1800076E1
0x18000775b  mov     eax, 0C000006Dh
0x180007760  retn
0x180007762  mov     eax, 0C00002A5h
0x180007767  retn
0x180007769  cmp     ecx, 52h ; 'R'
0x18000776c  ja      short loc_1800077E8
0x18000776e  jz      short loc_1800077D3
0x180007770  cmp     ecx, 43h ; 'C'
0x180007773  ja      short loc_1800077AD
0x180007775  jz      loc_1800076E1
0x18000777b  sub     ecx, 34h ; '4'
0x18000777e  jz      short loc_1800077A6
0x180007780  sub     ecx, 1
0x180007783  jz      short loc_1800077A6
0x180007785  sub     ecx, 1
0x180007788  jz      short loc_1800077D3
0x18000778a  sub     ecx, 0Ah
0x18000778d  jz      short loc_18000779F
0x18000778f  sub     ecx, 1
0x180007792  jnz     loc_1800076CA
0x180007798  mov     eax, 0C00002ABh
0x18000779d  retn
0x18000779f  mov     eax, 0C0000033h
0x1800077a4  retn
0x1800077a6  mov     eax, 0C00002A6h
0x1800077ab  retn
0x1800077ad  sub     ecx, 44h ; 'D'
0x1800077b0  jz      short loc_1800077E1
0x1800077b2  sub     ecx, 1
0x1800077b5  jz      loc_1800076E1
0x1800077bb  sub     ecx, 1
0x1800077be  jz      short loc_1800077DA
0x1800077c0  sub     ecx, 1
0x1800077c3  jz      loc_1800076D3
0x1800077c9  sub     ecx, 9
0x1800077cc  jz      short loc_1800077D3
0x1800077ce  cmp     ecx, 1
0x1800077d1  jz      short loc_1800077A6
0x1800077d3  mov     eax, 0C0000001h
0x1800077d8  retn
0x1800077da  mov     eax, 0C0000023h
0x1800077df  retn
0x1800077e1  mov     eax, 0C0000404h
0x1800077e6  retn
0x1800077e8  cmp     ecx, 59h ; 'Y'
0x1800077eb  ja      short loc_18000782D
0x1800077ed  jz      short loc_180007818
0x1800077ef  sub     ecx, 53h ; 'S'
0x1800077f2  jz      short loc_180007826
0x1800077f4  sub     ecx, 1
0x1800077f7  jz      short loc_180007826
0x1800077f9  sub     ecx, 1
0x1800077fc  jz      loc_180007698
0x180007802  sub     ecx, 1
0x180007805  jz      short loc_18000781F
0x180007807  sub     ecx, 1
0x18000780a  jz      short loc_180007818
0x18000780c  cmp     ecx, 1
0x18000780f  jnz     short loc_1800077D3
0x180007811  mov     eax, 0C0000120h
0x180007816  retn
0x180007818  mov     eax, 0C000000Dh
0x18000781d  retn
0x18000781f  mov     eax, 0C000006Ah
0x180007824  retn
0x180007826  mov     eax, 0C00000C4h
0x18000782b  retn
0x18000782d  sub     ecx, 5Ah ; 'Z'
0x180007830  jz      short loc_18000785F
0x180007832  sub     ecx, 1
0x180007835  jz      short loc_180007858
0x180007837  sub     ecx, 1
0x18000783a  jz      loc_1800076D3
0x180007840  sub     ecx, 1
0x180007843  jz      loc_180007725
0x180007849  sub     ecx, 1
0x18000784c  jz      short loc_1800077DA
0x18000784e  cmp     ecx, 1
0x180007851  jz      short loc_1800077DA
0x180007853  jmp     loc_1800077D3
0x180007858  mov     eax, 0C0000236h
0x18000785d  retn
0x18000785f  mov     eax, 0C0000017h
0x180007864  retn
```
