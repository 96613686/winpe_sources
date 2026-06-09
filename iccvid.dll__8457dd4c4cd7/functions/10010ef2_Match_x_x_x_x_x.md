# Match(x,x,x,x,x)

- ea: `0x10010ef2`
- end: `0x1001133b`
- name: `_Match@20`
- size: `1097`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10010735`
- `0x10011341`

## callees

- `0x10010ef2`

## pseudocode

```c
unsigned int __fastcall Match(
        unsigned int *a1,
        unsigned __int8 *a2,
        __int16 a3,
        unsigned __int16 a4,
        unsigned __int8 a5)
{
  unsigned int v5; // edx
  __int16 v6; // kr04_2
  unsigned __int8 *v7; // ebx
  __int16 v8; // ax
  unsigned int v9; // esi
  int v10; // edi
  unsigned __int16 v11; // cx
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // dx
  int v14; // kr00_4
  int v15; // ecx
  unsigned int v16; // edx
  bool v17; // cf
  unsigned __int16 v18; // cx
  unsigned __int16 v19; // si
  unsigned __int16 v20; // cx
  unsigned __int16 v21; // di
  int v22; // eax
  unsigned __int8 *v23; // edi
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  _BYTE *v29; // ecx
  int v30; // edx
  int v31; // edx
  int v32; // edx
  int v33; // edx
  int v34; // edx
  unsigned __int8 *v35; // esi
  int v36; // edx
  int v37; // edx
  int v38; // edx
  int v39; // edx
  int v40; // edx
  unsigned int v42; // [esp+Ch] [ebp-38h]
  unsigned __int8 *v43; // [esp+18h] [ebp-2Ch]
  unsigned __int16 v45; // [esp+20h] [ebp-24h]
  int v46; // [esp+20h] [ebp-24h]
  unsigned __int16 v47; // [esp+24h] [ebp-20h]
  unsigned int v48; // [esp+2Ch] [ebp-18h]
  int v50; // [esp+34h] [ebp-10h]
  unsigned int v51; // [esp+38h] [ebp-Ch]
  _BYTE *v52; // [esp+38h] [ebp-Ch]
  __int16 v53; // [esp+3Ch] [ebp-8h]
  unsigned __int8 v54; // [esp+43h] [ebp-1h]

  v54 = 0;
  v5 = a1[1];
  v42 = *a1;
  v6 = v5;
  v7 = &a2[460 * BYTE2(v5)];
  if ( ((unsigned __int8)(a5 ^ v7[7]) & (a5 | 1)) == 0 )
  {
    v8 = a3;
    v53 = a3;
    v9 = dword_1000170C[(unsigned __int8)*a1 - *v7]
       + dword_1000170C[HIBYTE(*a1) - v7[3]]
       + dword_1000170C[(unsigned __int8)BYTE1(*a1) - v7[1]]
       + dword_1000170C[(unsigned __int8)BYTE2(*a1) - v7[2]]
       + 4 * (dword_1000170C[(unsigned __int8)a1[1] - v7[4]] + dword_1000170C[BYTE1(v5) - v7[5]]);
    goto LABEL_4;
  }
  v8 = a3;
  v9 = 0x7FFFFFFF;
  v50 = 0x7FFFFFFF;
  v10 = 0x7FFFFFFF;
  v53 = a3;
LABEL_25:
  v29 = v7 + 6;
  v52 = v7 + 6;
  while ( 1 )
  {
    --v53;
    if ( !v8 )
      break;
    v7 = a2;
    a2 += 460;
    v29 = v52;
    v8 = v53;
    if ( ((unsigned __int8)(a5 ^ v7[7]) & (a5 | 1)) == 0 )
    {
      v8 = v53;
      if ( v7[6] != *v52 )
      {
        v8 = v53;
        v29 = v52;
        v30 = 4 * (dword_1000170C[(unsigned __int8)v6 - v7[4]] + dword_1000170C[HIBYTE(v6) - v7[5]]) - v10;
        if ( v30 < 0 )
        {
          v9 = v50;
          v8 = v53;
          v31 = dword_1000170C[(unsigned __int8)*a1 - *v7] + v30;
          v29 = v52;
          if ( v31 <= 0 )
          {
            v8 = v53;
            v32 = dword_1000170C[BYTE1(v42) - v7[1]] + v31;
            v29 = v52;
            if ( v32 <= 0 )
            {
              v8 = v53;
              v33 = dword_1000170C[BYTE2(v42) - v7[2]] + v32;
              v29 = v52;
              if ( v33 <= 0 )
              {
                v8 = v53;
                v34 = dword_1000170C[HIBYTE(v42) - v7[3]] + v33;
                v29 = v52;
                if ( v34 <= 0 )
                {
                  if ( v34 < 0 || (v8 = v53, v7[6] < v54) )
                  {
                    v9 = v34 + v10;
                    while ( 1 )
                    {
                      v8 = v53;
LABEL_4:
                      v50 = v9;
                      v11 = a4;
                      v10 = v9;
                      v43 = v7;
                      v51 = v9;
                      v54 = v7[6];
                      if ( !a4 || v9 > 0x3FFF )
                        goto LABEL_25;
                      v48 = 4 * v9;
                      if ( 4 * v9 < *((unsigned __int16 *)v7 + 22) )
                      {
                        *((_BYTE *)a1 + 6) = v7[6];
                        return v9;
                      }
                      if ( 4 * v9 <= *(unsigned __int16 *)&v7[8 * a4 + 36] )
                      {
                        v12 = a4;
                        v13 = 0;
                        v47 = a4;
                        v45 = 0;
                        do
                        {
                          v14 = v13 - 1 + v12;
                          v15 = (unsigned __int16)(v14 / 2);
                          v16 = *(unsigned __int16 *)&v7[8 * v15 + 44];
                          v17 = v48 < v16;
                          v18 = v15 + 1;
                          if ( v48 < v16 )
                            v18 = v45;
                          v19 = v18;
                          v20 = v47;
                          v13 = v19;
                          v45 = v19;
                          if ( v17 )
                            v20 = v14 / 2;
                          v12 = v20;
                          v47 = v20;
                        }
                        while ( v20 > v19 );
                        v21 = v20;
                        v11 = a4;
                        if ( v12 < a4 )
                        {
                          while ( v21 )
                          {
                            v35 = *(unsigned __int8 **)&v7[8 * --v21 + 48];
                            v36 = 4
                                * (dword_1000170C[(unsigned __int8)v6 - v35[4]] + dword_1000170C[HIBYTE(v6) - v35[5]])
                                - v51;
                            if ( v36 < 0 )
                            {
                              v37 = dword_1000170C[(unsigned __int8)*a1 - *v35] + v36;
                              if ( v37 <= 0 )
                              {
                                v38 = dword_1000170C[BYTE1(v42) - v35[1]] + v37;
                                if ( v38 <= 0 )
                                {
                                  v39 = dword_1000170C[BYTE2(v42) - v35[2]] + v38;
                                  if ( v39 <= 0 )
                                  {
                                    v40 = dword_1000170C[HIBYTE(v42) - v35[3]] + v39;
                                    if ( v40 <= 0 && (v40 < 0 || v35[6] < v54) )
                                    {
                                      v51 += v40;
                                      v43 = *(unsigned __int8 **)&v7[8 * v21 + 48];
                                      v54 = v35[6];
                                    }
                                  }
                                }
                              }
                            }
                          }
                          *((_BYTE *)a1 + 6) = v43[6];
                          return v51;
                        }
                        v9 = v50;
                        v10 = v51;
                      }
                      LOWORD(v22) = 0;
                      v46 = 0;
                      if ( !v11 )
                      {
LABEL_24:
                        v8 = v53;
                        goto LABEL_25;
                      }
                      while ( 1 )
                      {
                        v23 = *(unsigned __int8 **)&v7[8 * (unsigned __int16)v22 + 48];
                        v24 = 4 * (dword_1000170C[(unsigned __int8)v6 - v23[4]] + dword_1000170C[HIBYTE(v6) - v23[5]])
                            - v9;
                        if ( v24 < 0 )
                        {
                          v9 = v50;
                          v25 = dword_1000170C[(unsigned __int8)*a1 - *v23] + v24;
                          if ( v25 < 0 )
                          {
                            v26 = dword_1000170C[BYTE1(v42) - v23[1]] + v25;
                            if ( v26 < 0 )
                            {
                              v27 = dword_1000170C[BYTE2(v42) - v23[2]] + v26;
                              if ( v27 < 0 )
                              {
                                v28 = dword_1000170C[HIBYTE(v42) - v23[3]] + v27;
                                if ( v28 < 0 )
                                  break;
                              }
                            }
                          }
                        }
                        v22 = v46 + 1;
                        v46 = v22;
                        if ( (unsigned __int16)v22 >= a4 )
                        {
                          v10 = v51;
                          goto LABEL_24;
                        }
                      }
                      v9 = v28 + v50;
                      v7 = *(unsigned __int8 **)&v7[8 * (unsigned __int16)v22 + 48];
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  *((_BYTE *)a1 + 6) = *v29;
  return v9;
}

```

## disassembly

```asm
0x10010ef2  mov     edi, edi
0x10010ef4  push    ebp
0x10010ef5  mov     ebp, esp
0x10010ef7  sub     esp, 38h
0x10010efa  push    ebx
0x10010efb  push    esi
0x10010efc  push    edi
0x10010efd  mov     edi, ecx
0x10010eff  mov     esi, edx
0x10010f01  mov     cl, [ebp+arg_8]
0x10010f04  xor     dl, dl
0x10010f06  mov     [ebp+var_1], dl
0x10010f09  or      cl, 1
0x10010f0c  mov     [ebp+var_28], esi
0x10010f0f  mov     eax, [edi]
0x10010f11  mov     edx, [edi+4]
0x10010f14  mov     [ebp+var_38], eax
0x10010f17  mov     eax, edx
0x10010f19  shr     eax, 10h
0x10010f1c  movzx   eax, al
0x10010f1f  imul    ebx, eax, 1CCh
0x10010f25  mov     [ebp+var_14], edi
0x10010f28  mov     [ebp+var_1C], edx
0x10010f2b  mov     [ebp+var_34], edx
0x10010f2e  mov     byte ptr [ebp+var_30], cl
0x10010f31  add     ebx, esi
0x10010f33  mov     al, [ebx+7]
0x10010f36  xor     al, [ebp+arg_8]
0x10010f39  test    cl, al
0x10010f3b  jz      short loc_10010F52
0x10010f3d  mov     eax, [ebp+arg_0]
0x10010f40  mov     esi, 7FFFFFFFh
0x10010f45  mov     [ebp+var_10], esi
0x10010f48  mov     edi, esi
0x10010f4a  mov     dword ptr [ebp+var_8], eax
0x10010f4d  jmp     loc_1001113D
0x10010f52  movzx   eax, byte ptr [ebx+5]
0x10010f56  mov     ecx, [edi+4]
0x10010f59  shr     edx, 8
0x10010f5c  movzx   ecx, cl
0x10010f5f  movzx   edx, dl
0x10010f62  sub     edx, eax
0x10010f64  movzx   eax, byte ptr [ebx+4]
0x10010f68  sub     ecx, eax
0x10010f6a  mov     eax, [edi]
0x10010f6c  shr     eax, 10h
0x10010f6f  mov     edx, ds:dword_1000170C[edx*4]
0x10010f76  add     edx, ds:dword_1000170C[ecx*4]
0x10010f7d  movzx   ecx, al
0x10010f80  movzx   eax, byte ptr [ebx+2]
0x10010f84  sub     ecx, eax
0x10010f86  mov     eax, ds:dword_1000170C[ecx*4]
0x10010f8d  lea     esi, [eax+edx*4]
0x10010f90  mov     edx, [edi]
0x10010f92  mov     eax, edx
0x10010f94  shr     eax, 8
0x10010f97  movzx   ecx, al
0x10010f9a  movzx   eax, byte ptr [ebx+1]
0x10010f9e  sub     ecx, eax
0x10010fa0  movzx   eax, byte ptr [ebx+3]
0x10010fa4  add     esi, ds:dword_1000170C[ecx*4]
0x10010fab  mov     ecx, edx
0x10010fad  shr     ecx, 18h
0x10010fb0  sub     ecx, eax
0x10010fb2  movzx   eax, byte ptr [ebx]
0x10010fb5  add     esi, ds:dword_1000170C[ecx*4]
0x10010fbc  movzx   ecx, dl
0x10010fbf  sub     ecx, eax
0x10010fc1  mov     eax, [ebp+arg_0]
0x10010fc4  mov     dword ptr [ebp+var_8], eax
0x10010fc7  add     esi, ds:dword_1000170C[ecx*4]
0x10010fce  mov     [ebp+var_10], esi
0x10010fd1  mov     cx, [ebp+arg_4]
0x10010fd5  mov     edi, esi
0x10010fd7  mov     dl, [ebx+6]
0x10010fda  mov     [ebp+var_2C], ebx
0x10010fdd  mov     [ebp+var_C], edi
0x10010fe0  mov     [ebp+var_1], dl
0x10010fe3  test    cx, cx
0x10010fe6  jz      loc_1001113D
0x10010fec  cmp     esi, 3FFFh
0x10010ff2  ja      loc_1001113D
0x10010ff8  mov     eax, esi
0x10010ffa  shl     eax, 2
0x10010ffd  mov     [ebp+var_18], eax
0x10011000  movzx   eax, word ptr [ebx+2Ch]
0x10011004  cmp     [ebp+var_18], eax
0x10011007  jb      loc_10011322
0x1001100d  movzx   eax, cx
0x10011010  mov     edx, esi
0x10011012  shl     edx, 2
0x10011015  movzx   eax, word ptr [ebx+eax*8+24h]
0x1001101a  cmp     edx, eax
0x1001101c  ja      short loc_10011088
0x1001101e  movzx   eax, cx
0x10011021  xor     edx, edx
0x10011023  mov     [ebp+var_20], eax
0x10011026  mov     [ebp+var_24], edx
0x10011029  movzx   eax, ax
0x1001102c  movzx   ecx, dx
0x1001102f  dec     ecx
0x10011030  add     eax, ecx
0x10011032  cdq
0x10011033  sub     eax, edx
0x10011035  sar     eax, 1
0x10011037  movzx   edi, ax
0x1001103a  mov     ecx, edi
0x1001103c  movzx   edx, word ptr [ebx+ecx*8+2Ch]
0x10011041  lea     eax, [ecx+1]
0x10011044  cmp     [ebp+var_18], edx
0x10011047  movzx   ecx, ax
0x1001104a  mov     eax, [ebp+var_24]
0x1001104d  movzx   eax, ax
0x10011050  cmovb   ecx, eax
0x10011053  mov     eax, [ebp+var_20]
0x10011056  movzx   esi, cx
0x10011059  movzx   ecx, ax
0x1001105c  mov     edx, esi
0x1001105e  mov     eax, edi
0x10011060  mov     [ebp+var_24], edx
0x10011063  cmovb   ecx, eax
0x10011066  movzx   eax, cx
0x10011069  mov     ecx, eax
0x1001106b  mov     [ebp+var_20], eax
0x1001106e  cmp     cx, si
0x10011071  ja      short loc_10011029
0x10011073  mov     edi, ecx
0x10011075  mov     cx, [ebp+arg_4]
0x10011079  cmp     di, cx
0x1001107c  jb      loc_10011308
0x10011082  mov     esi, [ebp+var_10]
0x10011085  mov     edi, [ebp+var_C]
0x10011088  xor     eax, eax
0x1001108a  xor     edx, edx
0x1001108c  mov     [ebp+var_24], eax
0x1001108f  cmp     dx, cx
0x10011092  jnb     loc_1001113A
0x10011098  movzx   edx, byte ptr [ebp+var_34+1]
0x1001109c  mov     ecx, [ebp+var_1C]
0x1001109f  movzx   eax, ax
0x100110a2  movzx   ecx, cl
0x100110a5  mov     edi, [ebx+eax*8+30h]
0x100110a9  movzx   eax, byte ptr [edi+5]
0x100110ad  sub     edx, eax
0x100110af  movzx   eax, byte ptr [edi+4]
0x100110b3  sub     ecx, eax
0x100110b5  mov     edx, ds:dword_1000170C[edx*4]
0x100110bc  add     edx, ds:dword_1000170C[ecx*4]
0x100110c3  shl     edx, 2
0x100110c6  sub     edx, esi
0x100110c8  jns     short loc_10011126
0x100110ca  mov     esi, [ebp+var_14]
0x100110cd  movzx   eax, byte ptr [edi]
0x100110d0  mov     ecx, [esi]
0x100110d2  mov     esi, [ebp+var_10]
0x100110d5  movzx   ecx, cl
0x100110d8  sub     ecx, eax
0x100110da  add     edx, ds:dword_1000170C[ecx*4]
0x100110e1  jns     short loc_10011126
0x100110e3  mov     ecx, [ebp+var_38+1]
0x100110e6  movzx   eax, byte ptr [edi+1]
0x100110ea  movzx   ecx, cl
0x100110ed  sub     ecx, eax
0x100110ef  add     edx, ds:dword_1000170C[ecx*4]
0x100110f6  jns     short loc_10011126
0x100110f8  mov     ecx, [ebp+var_38+2]
0x100110fb  movzx   eax, byte ptr [edi+2]
0x100110ff  movzx   ecx, cl
0x10011102  sub     ecx, eax
0x10011104  add     edx, ds:dword_1000170C[ecx*4]
0x1001110b  jns     short loc_10011126
0x1001110d  mov     ecx, [ebp+var_38+3]
0x10011110  movzx   eax, byte ptr [edi+3]
0x10011114  movzx   ecx, cl
0x10011117  sub     ecx, eax
0x10011119  add     edx, ds:dword_1000170C[ecx*4]
0x10011120  js      loc_1001124A
0x10011126  mov     eax, [ebp+var_24]
0x10011129  inc     eax
0x1001112a  mov     [ebp+var_24], eax
0x1001112d  cmp     ax, [ebp+arg_4]
0x10011131  jb      loc_10011098
0x10011137  mov     edi, [ebp+var_C]
0x1001113a  mov     eax, dword ptr [ebp+var_8]
0x1001113d  lea     ecx, [ebx+6]
0x10011140  mov     [ebp+var_C], ecx
0x10011143  mov     dl, [ebp+arg_8]
0x10011146  dec     dword ptr [ebp+var_8]
0x10011149  test    ax, ax
0x1001114c  jz      loc_1001132A
0x10011152  mov     eax, [ebp+var_28]
0x10011155  mov     ebx, eax
0x10011157  mov     ecx, [ebp+var_30]
0x1001115a  add     eax, 1CCh
0x1001115f  mov     [ebp+var_28], eax
0x10011162  mov     al, [ebx+7]
0x10011165  xor     al, dl
0x10011167  test    cl, al
0x10011169  mov     ecx, [ebp+var_C]
0x1001116c  mov     eax, dword ptr [ebp+var_8]
0x1001116f  jnz     short loc_10011146
0x10011171  mov     al, [ebx+6]
0x10011174  cmp     al, [ecx]
0x10011176  mov     eax, dword ptr [ebp+var_8]
0x10011179  jz      short loc_10011146
0x1001117b  movzx   eax, byte ptr [ebx+5]
0x1001117f  movzx   edx, byte ptr [ebp+var_34+1]
0x10011183  mov     ecx, [ebp+var_1C]
0x10011186  sub     edx, eax
0x10011188  movzx   eax, byte ptr [ebx+4]
0x1001118c  movzx   ecx, cl
0x1001118f  sub     ecx, eax
0x10011191  mov     eax, dword ptr [ebp+var_8]
0x10011194  mov     edx, ds:dword_1000170C[edx*4]
0x1001119b  add     edx, ds:dword_1000170C[ecx*4]
0x100111a2  mov     ecx, [ebp+var_C]
0x100111a5  shl     edx, 2
0x100111a8  sub     edx, edi
0x100111aa  jns     short loc_10011143
0x100111ac  mov     esi, [ebp+var_14]
0x100111af  movzx   eax, byte ptr [ebx]
0x100111b2  mov     ecx, [esi]
0x100111b4  mov     esi, [ebp+var_10]
0x100111b7  movzx   ecx, cl
0x100111ba  sub     ecx, eax
0x100111bc  mov     eax, dword ptr [ebp+var_8]
0x100111bf  add     edx, ds:dword_1000170C[ecx*4]
0x100111c6  mov     ecx, [ebp+var_C]
0x100111c9  test    edx, edx
0x100111cb  jg      loc_10011143
0x100111d1  mov     ecx, [ebp+var_38+1]
0x100111d4  movzx   eax, byte ptr [ebx+1]
0x100111d8  movzx   ecx, cl
0x100111db  sub     ecx, eax
0x100111dd  mov     eax, dword ptr [ebp+var_8]
0x100111e0  add     edx, ds:dword_1000170C[ecx*4]
0x100111e7  mov     ecx, [ebp+var_C]
0x100111ea  test    edx, edx
0x100111ec  jg      loc_10011143
0x100111f2  mov     ecx, [ebp+var_38+2]
0x100111f5  movzx   eax, byte ptr [ebx+2]
0x100111f9  movzx   ecx, cl
0x100111fc  sub     ecx, eax
0x100111fe  mov     eax, dword ptr [ebp+var_8]
0x10011201  add     edx, ds:dword_1000170C[ecx*4]
0x10011208  mov     ecx, [ebp+var_C]
0x1001120b  test    edx, edx
0x1001120d  jg      loc_10011143
0x10011213  mov     ecx, [ebp+var_38+3]
0x10011216  movzx   eax, byte ptr [ebx+3]
0x1001121a  movzx   ecx, cl
0x1001121d  sub     ecx, eax
0x1001121f  mov     eax, dword ptr [ebp+var_8]
0x10011222  add     edx, ds:dword_1000170C[ecx*4]
0x10011229  mov     ecx, [ebp+var_C]
0x1001122c  test    edx, edx
0x1001122e  jg      loc_10011143
0x10011234  js      short loc_10011245
0x10011236  mov     al, [ebx+6]
0x10011239  cmp     al, [ebp+var_1]
0x1001123c  mov     eax, dword ptr [ebp+var_8]
0x1001123f  jnb     loc_10011143
0x10011245  lea     esi, [edx+edi]
0x10011248  jmp     short loc_1001124E
0x1001124a  add     esi, edx
0x1001124c  mov     ebx, edi
0x1001124e  mov     eax, dword ptr [ebp+var_8]
0x10011251  jmp     loc_10010FCE
0x10011256  movzx   edx, byte ptr [ebp+var_34+1]
0x1001125a  add     edi, 0FFFFh
0x10011260  mov     ecx, [ebp+var_1C]
0x10011263  movzx   eax, di
0x10011266  movzx   ecx, cl
0x10011269  mov     esi, [ebx+eax*8+30h]
0x1001126d  mov     [ebp+var_30], esi
0x10011270  movzx   eax, byte ptr [esi+5]
0x10011274  sub     edx, eax
0x10011276  movzx   eax, byte ptr [esi+4]
0x1001127a  sub     ecx, eax
0x1001127c  mov     edx, ds:dword_1000170C[edx*4]
0x10011283  add     edx, ds:dword_1000170C[ecx*4]
0x1001128a  shl     edx, 2
0x1001128d  sub     edx, [ebp+var_C]
0x10011290  jns     short loc_10011308
0x10011292  movzx   eax, byte ptr [esi]
0x10011295  mov     esi, [ebp+var_14]
0x10011298  mov     ecx, [esi]
0x1001129a  mov     esi, [ebp+var_30]
0x1001129d  movzx   ecx, cl
0x100112a0  sub     ecx, eax
0x100112a2  add     edx, ds:dword_1000170C[ecx*4]
0x100112a9  test    edx, edx
0x100112ab  jg      short loc_10011308
0x100112ad  mov     ecx, [ebp+var_38+1]
0x100112b0  movzx   eax, byte ptr [esi+1]
0x100112b4  movzx   ecx, cl
0x100112b7  sub     ecx, eax
0x100112b9  add     edx, ds:dword_1000170C[ecx*4]
0x100112c0  test    edx, edx
0x100112c2  jg      short loc_10011308
  ... truncated ...
```
