# WriteTile(x,x,x)

- ea: `0x10012218`
- end: `0x10012733`
- name: `_WriteTile@12`
- size: `1307`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100042f3`

## callees

- `0x10012218`

## pseudocode

```c
unsigned __int8 *__fastcall WriteTile(int a1, int a2, int a3)
{
  int v3; // edi
  int v4; // ebx
  __int16 v5; // ax
  __int16 v6; // cx
  _BYTE *v7; // esi
  int v8; // ecx
  _BYTE *v9; // edx
  _BYTE *v10; // eax
  int v11; // edi
  int v12; // ebx
  char v13; // cl
  int v14; // eax
  int v15; // edx
  bool v16; // zf
  int v17; // edx
  _BYTE *v18; // edx
  int v19; // edi
  int v20; // eax
  int v21; // ebx
  _BYTE *v22; // edi
  _BYTE *v23; // esi
  int v24; // ebx
  unsigned int v25; // ebx
  unsigned int v26; // eax
  unsigned __int8 *v27; // edi
  int v28; // eax
  _BYTE *v29; // esi
  int v30; // edx
  int i; // ecx
  char v32; // al
  _BYTE *v33; // edx
  int v34; // eax
  _WORD *v35; // eax
  _BYTE *v36; // eax
  int v37; // eax
  int v38; // edi
  char v39; // cl
  _BYTE *v40; // edx
  int v41; // ebx
  int v42; // eax
  bool v43; // cc
  int v44; // ebx
  unsigned int v45; // esi
  int v46; // ecx
  unsigned __int8 *v47; // esi
  int v48; // edx
  _BYTE *v50; // [esp+Ch] [ebp-2Ch]
  int v51; // [esp+Ch] [ebp-2Ch]
  int v52; // [esp+10h] [ebp-28h]
  int v53; // [esp+14h] [ebp-24h]
  int v54; // [esp+14h] [ebp-24h]
  unsigned __int8 *v55; // [esp+14h] [ebp-24h]
  int v56; // [esp+18h] [ebp-20h]
  _WORD *v57; // [esp+18h] [ebp-20h]
  int v58; // [esp+18h] [ebp-20h]
  _BYTE *v59; // [esp+1Ch] [ebp-1Ch]
  int v60; // [esp+1Ch] [ebp-1Ch]
  int v61; // [esp+1Ch] [ebp-1Ch]
  int v62; // [esp+1Ch] [ebp-1Ch]
  int v63; // [esp+20h] [ebp-18h]
  int v64; // [esp+20h] [ebp-18h]
  _WORD *v65; // [esp+20h] [ebp-18h]
  int v66; // [esp+24h] [ebp-14h]
  int v67; // [esp+24h] [ebp-14h]
  _BYTE *v68; // [esp+24h] [ebp-14h]
  int v69; // [esp+28h] [ebp-10h]
  _BYTE *v70; // [esp+28h] [ebp-10h]
  _BYTE *v73; // [esp+30h] [ebp-8h]
  _WORD *v74; // [esp+30h] [ebp-8h]
  char v75; // [esp+37h] [ebp-1h]

  v3 = 0;
  *(_DWORD *)(a3 + 4) = 0;
  v4 = 0;
  v5 = *(_WORD *)(a1 + 78);
  HIBYTE(v6) = v5;
  v69 = 0;
  LOBYTE(v6) = HIBYTE(v5);
  v66 = 0;
  *(_WORD *)(a3 + 10) = v6;
  HIBYTE(v6) = *(_WORD *)(a2 + 6);
  v56 = 0;
  LOBYTE(v6) = HIBYTE(*(_WORD *)(a2 + 6));
  *(_WORD *)(a3 + 8) = v6;
  v7 = (_BYTE *)(a3 + 12);
  v8 = a1;
  do
  {
    v9 = *(_BYTE **)(v8 + v3 + 124);
    v10 = v9;
    v53 = *(__int16 *)(v8 + v3 + 132);
    v11 = 0;
    v59 = v9;
    v63 = -1;
    if ( v53 > 0 )
    {
      v12 = -1;
      do
      {
        v13 = v10[7];
        if ( (v13 & 1) == 0 )
        {
          v14 = v11;
          if ( (v13 & 4) == 0 )
            v14 = v12;
          v12 = v14;
          v10 = v59;
        }
        ++v11;
        v10 += 460;
        v59 = v10;
      }
      while ( v11 < v53 );
      v8 = a1;
      v63 = v12;
      v4 = v69;
    }
    if ( *(_BYTE *)(a2 + 10) == 16 )
    {
      v15 = 6 * v63 + 10;
      v16 = (*(_BYTE *)(v8 + 106) & 4) == 0;
      v8 = a1;
      if ( !v16 )
        v15 = (4 * v63 + 8) | 0x4000000;
      v17 = dword_10003D00[v66] | v15;
      v7[3] = v17;
      *v7 = HIBYTE(v17);
      v7[1] = BYTE2(v17);
      v7[2] = BYTE1(v17);
      v7 += 4;
      v18 = *(_BYTE **)(a1 + v56 + 124);
      v19 = v63 + 1;
      if ( v63 != -1 )
      {
        do
        {
          --v19;
          *v7 = *v18;
          v7[1] = v18[1];
          v7[2] = v18[2];
          v7[3] = v18[3];
          if ( (*(_BYTE *)(a1 + 106) & 4) != 0 )
          {
            v7 -= 2;
          }
          else
          {
            v7[4] = v18[4] ^ 0x80;
            v7[5] = v18[5] ^ 0x80;
          }
          v7 += 6;
          v18 += 460;
        }
        while ( v19 );
      }
    }
    else
    {
      v50 = v7;
      v20 = 0;
      v60 = 0;
      v21 = v69;
      v22 = v7 + 4;
      v64 = 0;
      v23 = v7 + 8;
      v54 = 256;
      do
      {
        v21 *= 2;
        v75 = v9[7];
        if ( (v75 & 1) == 0 && (v75 & 4) != 0 )
        {
          *v23 = *v9;
          v23[1] = v9[1];
          v23[2] = v9[2];
          v23[3] = v9[3];
          if ( (*(_BYTE *)(a1 + 106) & 4) != 0 )
          {
            v23 -= 2;
          }
          else
          {
            v23[4] = v9[4] ^ 0x80;
            v23[5] = v9[5] ^ 0x80;
          }
          v20 = v64;
          v21 |= 1u;
          v23 += 6;
          ++v60;
        }
        v64 = ++v20;
        if ( v20 == 32 )
        {
          v22[3] = v21;
          *v22 = HIBYTE(v21);
          v22[1] = BYTE2(v21);
          v22[2] = BYTE1(v21);
          v22 = v23;
          v23 += 4;
          v20 = 0;
          v64 = 0;
        }
        v9 += 460;
        --v54;
      }
      while ( v54 );
      v69 = v21;
      v24 = 6 * (v60 + 6);
      if ( (*(_BYTE *)(a1 + 106) & 4) != 0 )
        v24 = (4 * v60 + 36) | 0x4000000;
      v25 = dword_10003CF8[v66] | v24;
      *v50 = HIBYTE(v25);
      v50[1] = BYTE2(v25);
      v26 = v25 >> 8;
      v7 = v23 - 4;
      v50[3] = v25;
      v4 = v69;
      v50[2] = v26;
      v8 = a1;
    }
    v3 = v56 + 24;
    ++v66;
    v56 += 24;
  }
  while ( v66 <= 1 );
  v27 = v7;
  v28 = 0;
  v29 = v7 + 4;
  v55 = v27;
  if ( *(_BYTE *)(v8 + 82) )
  {
    *v27 = 49;
    v33 = v29;
    v29 += 4;
    v68 = *(_BYTE **)(v8 + 128);
    v58 = *(_DWORD *)(v8 + 152);
    v65 = *(_WORD **)(v8 + 108);
    v74 = *(_WORD **)(v8 + 112);
    v51 = 0;
    v70 = v33;
    if ( *(int *)(a2 + 12) > 0 )
    {
      do
      {
        v4 *= 2;
        v40 = v70;
        if ( *v65 )
        {
          v41 = v4 | 1;
          v62 = v28 + 1;
          if ( v28 == 31 )
          {
            v70 = v29;
            *v40 = HIBYTE(v41);
            v40[1] = BYTE2(v41);
            v29 += 4;
            v40[2] = BYTE1(v41);
            v40[3] = v41;
            v62 = 0;
          }
          v4 = 2 * v41;
          v40 = v70;
          if ( *v74 )
          {
            *v29 = v68[6];
            v29[1] = v68[14];
            v29[2] = v68[22];
            v29[3] = v68[30];
            v29 += 4;
            v68 += 32;
            v4 |= 1u;
          }
          else
          {
            v42 = v58;
            v58 += 8;
            *v29++ = *(_BYTE *)(v42 + 6);
          }
          v28 = v62;
        }
        if ( ++v28 == 32 )
        {
          v70 = v29;
          v29 += 4;
          *v40 = HIBYTE(v4);
          v40[1] = BYTE2(v4);
          v40[2] = BYTE1(v4);
          v28 = 0;
          v40[3] = v4;
        }
        ++v65;
        ++v74;
        v43 = v51 + 1 < *(_DWORD *)(a2 + 12);
        v33 = v70;
        ++v51;
      }
      while ( v43 );
      if ( v28 )
      {
        v39 = 32 - v28;
        goto LABEL_60;
      }
    }
LABEL_61:
    v29 = v33;
    goto LABEL_62;
  }
  if ( *(_DWORD *)(v8 + 120) )
  {
    v67 = 0;
    v33 = v29;
    *v27 = 48;
    v29 += 4;
    v73 = *(_BYTE **)(v8 + 128);
    v61 = *(_DWORD *)(v8 + 152);
    v57 = *(_WORD **)(v8 + 112);
    v34 = *(_DWORD *)(a2 + 12);
    if ( v34 )
    {
      do
      {
        v52 = v34 - 1;
        v4 *= 2;
        v35 = v57++;
        if ( *v35 )
        {
          *v29 = v73[6];
          v29[1] = v73[14];
          v29[2] = v73[22];
          v36 = v73;
          v73 += 32;
          v29[3] = v36[30];
          v29 += 4;
          v4 |= 1u;
        }
        else
        {
          v37 = v61;
          v61 += 8;
          *v29++ = *(_BYTE *)(v37 + 6);
        }
        v38 = v67 + 1;
        v67 = v38;
        if ( v38 == 32 )
        {
          v33[3] = v4;
          *v33 = HIBYTE(v4);
          v33[1] = BYTE2(v4);
          v33[2] = BYTE1(v4);
          v33 = v29;
          v29 += 4;
          v38 = 0;
          v67 = 0;
        }
        v34 = v52;
      }
      while ( v52 );
      v16 = v38 == 0;
      v27 = v55;
      if ( !v16 )
      {
        v39 = 32 - v67;
LABEL_60:
        v44 = v4 << v39;
        *v33 = HIBYTE(v44);
        v33[1] = BYTE2(v44);
        v33[3] = v44;
        v33[2] = BYTE1(v44);
        goto LABEL_62;
      }
    }
    goto LABEL_61;
  }
  *v27 = 50;
  v30 = *(_DWORD *)(v8 + 152);
  for ( i = *(_DWORD *)(a2 + 12); i; --i )
  {
    v32 = *(_BYTE *)(v30 + 6);
    v30 += 8;
    *v29++ = v32;
  }
LABEL_62:
  v45 = (v29 - v27 + 1) & 0xFFFFFFFE;
  v46 = v45 | (*v27 << 24);
  v27[3] = v45;
  *v27 = HIBYTE(v46);
  v27[1] = BYTE2(v46);
  v27[2] = BYTE1(v46);
  v47 = &v27[v45 - a3];
  v48 = (unsigned int)v47 | (*(unsigned __int8 *)(a2 + 10) << 24);
  *(_BYTE *)(a3 + 3) = (_BYTE)v47;
  *(_BYTE *)a3 = HIBYTE(v48);
  *(_BYTE *)(a3 + 1) = BYTE2(v48);
  *(_BYTE *)(a3 + 2) = BYTE1(v48);
  return v47;
}

```

## disassembly

```asm
0x10012218  mov     edi, edi
0x1001221a  push    ebp
0x1001221b  mov     ebp, esp
0x1001221d  sub     esp, 2Ch
0x10012220  push    ebx
0x10012221  push    esi
0x10012222  mov     esi, [ebp+arg_0]
0x10012225  xor     eax, eax
0x10012227  mov     [ebp+var_8], ecx
0x1001222a  push    edi
0x1001222b  xor     edi, edi
0x1001222d  mov     [ebp+var_C], edx
0x10012230  mov     [esi+4], eax
0x10012233  mov     ebx, edi
0x10012235  mov     ax, [ecx+4Eh]
0x10012239  mov     ch, al
0x1001223b  mov     [ebp+var_10], ebx
0x1001223e  mov     cl, ah
0x10012240  mov     [ebp+var_14], edi
0x10012243  mov     [esi+0Ah], cx
0x10012247  mov     ax, [edx+6]
0x1001224b  mov     ch, al
0x1001224d  mov     [ebp+var_20], edi
0x10012250  mov     cl, ah
0x10012252  mov     [esi+8], cx
0x10012256  add     esi, 0Ch
0x10012259  mov     ecx, [ebp+var_8]
0x1001225c  mov     edx, [ecx+edi+7Ch]
0x10012260  mov     eax, edx
0x10012262  movsx   edi, word ptr [ecx+edi+84h]
0x1001226a  mov     [ebp+var_24], edi
0x1001226d  xor     edi, edi
0x1001226f  mov     [ebp+var_2C], edx
0x10012272  mov     [ebp+var_1C], eax
0x10012275  mov     [ebp+var_18], 0FFFFFFFFh
0x1001227c  cmp     [ebp+var_24], edi
0x1001227f  jle     short loc_100122B8
0x10012281  mov     ebx, [ebp+var_18]
0x10012284  mov     edx, [ebp+var_24]
0x10012287  mov     cl, [eax+7]
0x1001228a  mov     [ebp+var_1], cl
0x1001228d  test    cl, 1
0x10012290  jnz     short loc_1001229F
0x10012292  test    cl, 4
0x10012295  mov     eax, edi
0x10012297  cmovz   eax, ebx
0x1001229a  mov     ebx, eax
0x1001229c  mov     eax, [ebp+var_1C]
0x1001229f  inc     edi
0x100122a0  add     eax, 1CCh
0x100122a5  mov     [ebp+var_1C], eax
0x100122a8  cmp     edi, edx
0x100122aa  jl      short loc_10012287
0x100122ac  mov     ecx, [ebp+var_8]
0x100122af  mov     edx, [ebp+var_2C]
0x100122b2  mov     [ebp+var_18], ebx
0x100122b5  mov     ebx, [ebp+var_10]
0x100122b8  mov     eax, [ebp+var_C]
0x100122bb  cmp     byte ptr [eax+0Ah], 10h
0x100122bf  jnz     loc_1001235F
0x100122c5  mov     edi, [ebp+var_18]
0x100122c8  imul    edx, edi, 6
0x100122cb  lea     eax, ds:8[edi*4]
0x100122d2  or      eax, 4000000h
0x100122d7  add     edx, 0Ah
0x100122da  test    byte ptr [ecx+6Ah], 4
0x100122de  mov     ecx, [ebp+var_8]
0x100122e1  cmovnz  edx, eax
0x100122e4  mov     eax, [ebp+var_14]
0x100122e7  or      edx, ds:dword_10003D00[eax*4]
0x100122ee  mov     eax, edx
0x100122f0  mov     [esi+3], dl
0x100122f3  shr     eax, 18h
0x100122f6  mov     [esi], al
0x100122f8  mov     eax, edx
0x100122fa  shr     eax, 10h
0x100122fd  mov     [esi+1], al
0x10012300  mov     eax, edx
0x10012302  mov     edx, [ebp+var_20]
0x10012305  shr     eax, 8
0x10012308  mov     [esi+2], al
0x1001230b  add     esi, 4
0x1001230e  mov     edx, [ecx+edx+7Ch]
0x10012312  add     edi, 1
0x10012315  jz      loc_1001245E
0x1001231b  mov     al, [edx]
0x1001231d  dec     edi
0x1001231e  mov     [esi], al
0x10012320  mov     al, [edx+1]
0x10012323  mov     [esi+1], al
0x10012326  mov     al, [edx+2]
0x10012329  mov     [esi+2], al
0x1001232c  mov     al, [edx+3]
0x1001232f  mov     [esi+3], al
0x10012332  test    byte ptr [ecx+6Ah], 4
0x10012336  jz      short loc_1001233D
0x10012338  sub     esi, 2
0x1001233b  jmp     short loc_1001234D
0x1001233d  mov     al, [edx+4]
0x10012340  xor     al, 80h
0x10012342  mov     [esi+4], al
0x10012345  mov     al, [edx+5]
0x10012348  xor     al, 80h
0x1001234a  mov     [esi+5], al
0x1001234d  add     esi, 6
0x10012350  add     edx, 1CCh
0x10012356  test    edi, edi
0x10012358  jnz     short loc_1001231B
0x1001235a  jmp     loc_1001245E
0x1001235f  xor     ebx, ebx
0x10012361  mov     [ebp+var_2C], esi
0x10012364  mov     eax, ebx
0x10012366  mov     [ebp+var_1C], ebx
0x10012369  mov     ebx, [ebp+var_10]
0x1001236c  lea     edi, [esi+4]
0x1001236f  mov     [ebp+var_18], eax
0x10012372  lea     esi, [edi+4]
0x10012375  mov     [ebp+var_24], 100h
0x1001237c  mov     cl, [edx+7]
0x1001237f  add     ebx, ebx
0x10012381  mov     [ebp+var_1], cl
0x10012384  test    cl, 1
0x10012387  mov     ecx, [ebp+var_8]
0x1001238a  jnz     short loc_100123CF
0x1001238c  test    [ebp+var_1], 4
0x10012390  jz      short loc_100123CF
0x10012392  mov     al, [edx]
0x10012394  mov     [esi], al
0x10012396  mov     al, [edx+1]
0x10012399  mov     [esi+1], al
0x1001239c  mov     al, [edx+2]
0x1001239f  mov     [esi+2], al
0x100123a2  mov     al, [edx+3]
0x100123a5  mov     [esi+3], al
0x100123a8  test    byte ptr [ecx+6Ah], 4
0x100123ac  jz      short loc_100123B3
0x100123ae  sub     esi, 2
0x100123b1  jmp     short loc_100123C3
0x100123b3  mov     al, [edx+4]
0x100123b6  xor     al, 80h
0x100123b8  mov     [esi+4], al
0x100123bb  mov     al, [edx+5]
0x100123be  xor     al, 80h
0x100123c0  mov     [esi+5], al
0x100123c3  mov     eax, [ebp+var_18]
0x100123c6  or      ebx, 1
0x100123c9  add     esi, 6
0x100123cc  inc     [ebp+var_1C]
0x100123cf  inc     eax
0x100123d0  mov     [ebp+var_18], eax
0x100123d3  cmp     eax, 20h ; ' '
0x100123d6  jnz     short loc_100123FC
0x100123d8  mov     eax, ebx
0x100123da  mov     [edi+3], bl
0x100123dd  shr     eax, 18h
0x100123e0  mov     [edi], al
0x100123e2  mov     eax, ebx
0x100123e4  shr     eax, 10h
0x100123e7  mov     [edi+1], al
0x100123ea  mov     eax, ebx
0x100123ec  shr     eax, 8
0x100123ef  mov     [edi+2], al
0x100123f2  mov     edi, esi
0x100123f4  add     esi, 4
0x100123f7  xor     eax, eax
0x100123f9  mov     [ebp+var_18], eax
0x100123fc  add     edx, 1CCh
0x10012402  sub     [ebp+var_24], 1
0x10012406  jnz     loc_1001237C
0x1001240c  mov     dl, [ecx+6Ah]
0x1001240f  mov     eax, [ebp+var_1C]
0x10012412  mov     [ebp+var_10], ebx
0x10012415  lea     ecx, ds:24h[eax*4]
0x1001241c  add     eax, 6
0x1001241f  imul    ebx, eax, 6
0x10012422  or      ecx, 4000000h
0x10012428  mov     eax, [ebp+var_14]
0x1001242b  test    dl, 4
0x1001242e  cmovnz  ebx, ecx
0x10012431  mov     ecx, [ebp+var_2C]
0x10012434  or      ebx, ds:dword_10003CF8[eax*4]
0x1001243b  mov     eax, ebx
0x1001243d  shr     eax, 18h
0x10012440  mov     [ecx], al
0x10012442  mov     eax, ebx
0x10012444  shr     eax, 10h
0x10012447  mov     [ecx+1], al
0x1001244a  mov     eax, ebx
0x1001244c  shr     eax, 8
0x1001244f  sub     esi, 4
0x10012452  mov     [ecx+3], bl
0x10012455  mov     ebx, [ebp+var_10]
0x10012458  mov     [ecx+2], al
0x1001245b  mov     ecx, [ebp+var_8]
0x1001245e  mov     eax, [ebp+var_14]
0x10012461  mov     edi, [ebp+var_20]
0x10012464  inc     eax
0x10012465  add     edi, 18h
0x10012468  mov     [ebp+var_14], eax
0x1001246b  mov     [ebp+var_20], edi
0x1001246e  cmp     eax, 1
0x10012471  jle     loc_1001225C
0x10012477  mov     edi, esi
0x10012479  xor     eax, eax
0x1001247b  add     esi, 4
0x1001247e  mov     [ebp+var_24], edi
0x10012481  cmp     [ecx+52h], al
0x10012484  jnz     loc_10012591
0x1001248a  cmp     [ecx+78h], eax
0x1001248d  jnz     short loc_100124B9
0x1001248f  mov     eax, [ebp+var_C]
0x10012492  mov     byte ptr [edi], 32h ; '2'
0x10012495  mov     edx, [ecx+98h]
0x1001249b  mov     ecx, [eax+0Ch]
0x1001249e  test    ecx, ecx
0x100124a0  jz      loc_100126D5
0x100124a6  mov     al, [edx+6]
0x100124a9  lea     edx, [edx+8]
0x100124ac  mov     [esi], al
0x100124ae  inc     esi
0x100124af  sub     ecx, 1
0x100124b2  jnz     short loc_100124A6
0x100124b4  jmp     loc_100126D5
0x100124b9  mov     [ebp+var_14], eax
0x100124bc  mov     edx, esi
0x100124be  mov     byte ptr [edi], 30h ; '0'
0x100124c1  add     esi, 4
0x100124c4  mov     eax, [ecx+80h]
0x100124ca  mov     [ebp+var_8], eax
0x100124cd  mov     eax, [ecx+98h]
0x100124d3  mov     [ebp+var_1C], eax
0x100124d6  mov     eax, [ecx+70h]
0x100124d9  mov     [ebp+var_20], eax
0x100124dc  mov     eax, [ebp+var_C]
0x100124df  mov     eax, [eax+0Ch]
0x100124e2  test    eax, eax
0x100124e4  jz      loc_100126D3
0x100124ea  push    20h ; ' '
0x100124ec  pop     ecx
0x100124ed  dec     eax
0x100124ee  lea     edi, [esi+1]
0x100124f1  mov     [ebp+var_28], eax
0x100124f4  add     ebx, ebx
0x100124f6  mov     eax, [ebp+var_20]
0x100124f9  add     [ebp+var_20], 2
0x100124fd  mov     [ebp+var_2C], edi
0x10012500  mov     ax, [eax]
0x10012503  test    ax, ax
0x10012506  jz      short loc_10012535
0x10012508  mov     eax, [ebp+var_8]
0x1001250b  mov     al, [eax+6]
0x1001250e  mov     [esi], al
0x10012510  mov     eax, [ebp+var_8]
0x10012513  mov     al, [eax+0Eh]
0x10012516  mov     [edi], al
0x10012518  mov     eax, [ebp+var_8]
0x1001251b  mov     al, [eax+16h]
0x1001251e  mov     [esi+2], al
0x10012521  mov     eax, [ebp+var_8]
0x10012524  add     [ebp+var_8], ecx
0x10012527  mov     al, [eax+1Eh]
0x1001252a  mov     [esi+3], al
0x1001252d  add     esi, 4
0x10012530  or      ebx, 1
0x10012533  jmp     short loc_10012544
0x10012535  mov     eax, [ebp+var_1C]
0x10012538  add     [ebp+var_1C], 8
0x1001253c  mov     al, [eax+6]
0x1001253f  mov     [esi], al
0x10012541  mov     esi, [ebp+var_2C]
0x10012544  mov     edi, [ebp+var_14]
0x10012547  inc     edi
0x10012548  mov     [ebp+var_14], edi
0x1001254b  cmp     edi, ecx
0x1001254d  jnz     short loc_10012573
0x1001254f  mov     eax, ebx
0x10012551  mov     [edx+3], bl
0x10012554  shr     eax, 18h
0x10012557  mov     [edx], al
0x10012559  mov     eax, ebx
0x1001255b  shr     eax, 10h
0x1001255e  mov     [edx+1], al
0x10012561  mov     eax, ebx
0x10012563  shr     eax, 8
0x10012566  mov     [edx+2], al
0x10012569  mov     edx, esi
0x1001256b  add     esi, 4
0x1001256e  xor     edi, edi
0x10012570  mov     [ebp+var_14], edi
0x10012573  mov     eax, [ebp+var_28]
0x10012576  test    eax, eax
0x10012578  jnz     loc_100124ED
0x1001257e  test    edi, edi
0x10012580  mov     edi, [ebp+var_24]
0x10012583  jz      loc_100126D3
0x10012589  sub     ecx, [ebp+var_14]
0x1001258c  jmp     loc_100126B5
0x10012591  mov     byte ptr [edi], 31h ; '1'
0x10012594  mov     edx, esi
0x10012596  mov     edi, [ecx+80h]
  ... truncated ...
```
