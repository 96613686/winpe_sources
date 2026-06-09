# CShortBlock_ReadSpectralData

- ea: `0x180079090`
- end: `0x180079800`
- name: `CShortBlock_ReadSpectralData`
- size: `1904`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18007d4e0`

## callees

- `0x1800021a8`
- `0x1800363f0`
- `0x180079090`
- `0x18007f140`
- `0x18007f270`

## pseudocode

```c
__int64 __fastcall CShortBlock_ReadSpectralData(int *a1, char *a2)
{
  float v2; // xmm0_4
  __int64 v3; // rax
  char *v4; // rsi
  __int64 *v6; // r8
  char v7; // cl
  __int64 v9; // rax
  __int64 v10; // rdx
  int v11; // ecx
  __int64 v12; // r14
  __int64 v13; // rax
  int v14; // r11d
  int v15; // edi
  int v16; // r9d
  int v17; // eax
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // r10
  __int64 v21; // rsi
  char v22; // al
  int v23; // r12d
  int v24; // ebp
  int v25; // r15d
  __int64 v26; // rsi
  unsigned int v27; // edi
  int v28; // ecx
  int v29; // eax
  int v30; // edi
  int v31; // r15d
  char v32; // cl
  int v33; // edx
  int v34; // r8d
  int v35; // eax
  int v36; // edi
  int v37; // edi
  __int64 v38; // rsi
  int Escape; // eax
  __int64 v40; // rdx
  int v41; // eax
  bool v42; // sf
  int v43; // edx
  int v44; // ecx
  int v45; // ecx
  int v46; // edx
  int v47; // edi
  int v48; // ebx
  int v49; // r12d
  int v50; // ecx
  int v51; // r15d
  __int64 v52; // rbp
  __int64 v53; // rdx
  __int64 v54; // rdi
  __int64 v55; // rcx
  int v56; // [rsp+20h] [rbp-88h]
  int v57; // [rsp+20h] [rbp-88h]
  int v58; // [rsp+24h] [rbp-84h]
  int v59; // [rsp+24h] [rbp-84h]
  int v60; // [rsp+28h] [rbp-80h]
  int v61; // [rsp+28h] [rbp-80h]
  int v62; // [rsp+2Ch] [rbp-7Ch]
  __int64 *v63; // [rsp+30h] [rbp-78h]
  int v64; // [rsp+38h] [rbp-70h]
  __int64 v65; // [rsp+40h] [rbp-68h]
  __int64 i; // [rsp+40h] [rbp-68h]
  __int64 v67; // [rsp+48h] [rbp-60h]
  __int64 v68; // [rsp+50h] [rbp-58h]
  __int64 v69; // [rsp+58h] [rbp-50h]
  __int64 v70; // [rsp+60h] [rbp-48h]
  int v72; // [rsp+C0h] [rbp+18h]
  int v73; // [rsp+C0h] [rbp+18h]
  int v74; // [rsp+C8h] [rbp+20h]
  int v75; // [rsp+C8h] [rbp+20h]

  v3 = 4LL * a2[31];
  v4 = a2;
  if ( a2[27] == 2 )
  {
    v6 = (__int64 *)(&off_18008B4A8)[v3];
    v7 = qword_18008B4A0[v3];
  }
  else
  {
    v6 = *(__int64 **)((char *)&off_18008B498 + v3 * 8);
    v7 = BYTE4(SamplingRateInfoTable[v3]);
  }
  v63 = v6;
  if ( v7 < a2[28] )
    return 19;
  v9 = *(_QWORD *)a2;
  v10 = *((_QWORD *)a2 + 1);
  v11 = 0;
  v12 = *((_QWORD *)v4 + 2);
  v70 = v9;
  v13 = 0;
  v68 = v10;
  do
  {
    v11 += 128;
    *(_QWORD *)(v12 + 4 * v13) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 8) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 16) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 24) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 32) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 40) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 48) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 56) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 64) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 72) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 80) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 88) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 96) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 104) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 112) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 120) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 128) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 136) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 144) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 152) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 160) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 168) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 176) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 184) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 192) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 200) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 208) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 216) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 224) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 232) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 240) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 248) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 256) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 264) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 272) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 280) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 288) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 296) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 304) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 312) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 320) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 328) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 336) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 344) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 352) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 360) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 368) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 376) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 384) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 392) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 400) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 408) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 416) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 424) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 432) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 440) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 448) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 456) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 464) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 472) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 480) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 488) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 496) = 0;
    *(_QWORD *)(v12 + 4 * v13 + 504) = 0;
    v13 += 128;
  }
  while ( v11 != 1024 );
  v14 = 0;
  v15 = 0;
  v56 = 0;
  v58 = 0;
  if ( v4[33] > 0 )
  {
    do
    {
      v16 = 0;
      v62 = 0;
      if ( v4[28] <= 0 )
      {
        v20 = v15;
      }
      else
      {
        v17 = 16 * v15;
        v60 = 16 * v15;
        do
        {
          v18 = v16 + v17;
          v19 = 0;
          v20 = v15;
          v69 = v18;
          v74 = 0;
          v21 = 16LL * *(char *)(v18 + v10);
          v67 = v21;
          v65 = v15;
          if ( a2[v15 + 34] > 0 )
          {
            do
            {
              v22 = *(_BYTE *)(v18 + v10);
              if ( v22 )
              {
                if ( (unsigned __int8)(v22 - 13) > 2u )
                {
                  v23 = HuffmanCodeBooks[v21];
                  v24 = *((__int16 *)v6 + v16);
                  v72 = v24;
                  if ( v24 < *((__int16 *)v6 + v16 + 1) )
                  {
                    v25 = (v14 + v19) << 7;
                    v64 = v25;
                    while ( 1 )
                    {
                      v26 = *(__int64 *)((char *)&qword_18008B618 + v21);
                      v27 = 0;
                      do
                      {
                        if ( (unsigned int)*a1 < 4 )
                          FillBitCache(a1, 4u);
                        v28 = *a1 - 4;
                        v27 = *(unsigned __int16 *)(v26
                                                  + 2LL * (v27 + (((unsigned int)a1[1] >> (*(_BYTE *)a1 - 4)) & 0xF)));
                        *a1 = v28;
                      }
                      while ( (v27 & 8) == 0 );
                      v21 = v67;
                      v29 = v27 & 3;
                      v30 = v27 >> 4;
                      v31 = v24 + v25;
                      *a1 = v28 + v29;
                      v32 = byte_18008B611[v67];
                      v33 = byte_18008B612[v67];
                      v34 = (1 << v32) - 1;
                      v35 = v30 & v34;
                      v36 = v30 >> v32;
                      *(_DWORD *)(v12 + 4LL * v31) = v35 - v33;
                      *(_DWORD *)(v12 + 4LL * v31 + 4) = (v34 & v36) - v33;
                      if ( HuffmanCodeBooks[v67] == 4 )
                      {
                        *(_DWORD *)(v12 + 4LL * v31 + 8) = (v34 & (v36 >> v32)) - v33;
                        *(_DWORD *)(v12 + 4LL * v31 + 12) = (v34 & (v36 >> v32 >> v32)) - v33;
                      }
                      if ( !byte_18008B612[v67] )
                      {
                        v37 = 0;
                        if ( v23 > 0 )
                        {
                          do
                          {
                            v38 = v31 + v37;
                            if ( *(_DWORD *)(v12 + 4 * v38) )
                            {
                              if ( !*a1 )
                                FillBitCache(a1, 1u);
                              if ( (((unsigned int)a1[1] >> --*a1) & 1) != 0 )
                                *(_DWORD *)(v12 + 4 * v38) = -*(_DWORD *)(v12 + 4 * v38);
                            }
                            ++v37;
                          }
                          while ( v37 < v23 );
                          v21 = v67;
                        }
                      }
                      v10 = v68;
                      if ( *(_BYTE *)(v69 + v68) == 11 )
                      {
                        Escape = CBlock_GetEscape(a1, *(unsigned int *)(v12 + 4LL * v31));
                        v40 = *(unsigned int *)(v12 + 4LL * v31 + 4);
                        *(_DWORD *)(v12 + 4LL * v31) = Escape;
                        v41 = CBlock_GetEscape(a1, v40);
                        v42 = -*(_DWORD *)(v12 + 4LL * v31) < 0;
                        v43 = -*(_DWORD *)(v12 + 4LL * v31);
                        *(_DWORD *)(v12 + 4LL * v31 + 4) = v41;
                        if ( v42 )
                          v43 = *(_DWORD *)(v12 + 4LL * v31);
                        if ( v43 > 0x1FFF )
                          return 3;
                        v44 = -v41;
                        if ( v41 > 0 )
                          v44 = v41;
                        if ( v44 > 0x1FFF )
                          return 3;
                        v10 = v68;
                      }
                      v6 = v63;
                      v24 = v23 + v72;
                      v16 = v62;
                      v25 = v64;
                      v72 = v24;
                      if ( v24 >= *((__int16 *)v63 + v62 + 1) )
                      {
                        v19 = v74;
                        v20 = v65;
                        v14 = v56;
                        break;
                      }
                    }
                  }
                }
              }
              v74 = ++v19;
              v18 = v69;
            }
            while ( v19 < a2[v20 + 34] );
            v15 = v58;
          }
          v4 = a2;
          v62 = ++v16;
          v17 = v60;
        }
        while ( v16 < a2[28] );
      }
      ++v15;
      v45 = v4[33];
      v14 += v4[v20 + 34];
      v56 = v14;
      v58 = v15;
    }
    while ( v15 < v45 );
    v57 = 0;
    v46 = 0;
    v73 = 0;
    v47 = 0;
    if ( (char)v45 > 0 )
    {
      do
      {
        v59 = 0;
        for ( i = v46; v59 < v4[i + 34]; v57 = v47 )
        {
          v48 = 0;
          v49 = 0;
          v75 = 0;
          if ( v4[28] <= 0 )
            goto LABEL_64;
          v50 = 16 * v46;
          v61 = 16 * v46;
          do
          {
            v48 = *((__int16 *)v6 + v49);
            if ( v48 < *((__int16 *)v6 + v49 + 1) )
            {
              v51 = v47 << 7;
              v52 = *(__int16 *)(v70 + 2LL * (v50 + v49));
              v53 = v52;
              do
              {
                v54 = v51 + v48;
                v55 = *(int *)(v12 + 4 * v54);
                if ( (_DWORD)v55 )
                {
                  if ( (unsigned int)(v55 + 192) > 0x155 || (unsigned int)(v52 + 96) > 0xB7 )
                  {
                    CBlock_Quantize_Impl(v55, (unsigned int)(v52 - 24));
                    v6 = v63;
                    v53 = v52;
                  }
                  else
                  {
                    v2 = *(float *)&dword_1800A3450[v55] * *(float *)&dword_1800A3830[v53];
                  }
                }
                else
                {
                  v2 = 0.0;
                }
                *(float *)(v12 + 4 * v54) = v2;
                ++v48;
              }
              while ( v48 < *((__int16 *)v6 + v49 + 1) );
              v49 = v75;
              v50 = v61;
              v47 = v57;
            }
            v4 = a2;
            v75 = ++v49;
          }
          while ( v49 < a2[28] );
          if ( v48 < 128 )
          {
LABEL_64:
            memset_0((void *)(v12 + 4LL * (v48 + (v47 << 7))), 0, 4LL * (128 - v48));
            v6 = v63;
          }
          ++v47;
          v46 = v73;
          ++v59;
        }
        v73 = ++v46;
      }
      while ( v46 < v4[33] );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180079090  mov     [rsp+arg_8], rdx
0x180079095  push    rbx
0x180079096  push    rsi
0x180079097  push    r13
0x180079099  sub     rsp, 90h
0x1800790a0  movsx   rax, byte ptr [rdx+1Fh]
0x1800790a5  lea     r13, __ImageBase
0x1800790ac  shl     rax, 5
0x1800790b0  mov     rsi, rdx
0x1800790b3  cmp     byte ptr [rdx+1Bh], 2
0x1800790b7  mov     rbx, rcx
0x1800790ba  jz      short loc_1800790CF
0x1800790bc  mov     r8, [rax+r13+8B498h]
0x1800790c4  movzx   ecx, byte ptr [rax+r13+8B494h]
0x1800790cd  jmp     short loc_1800790E0
0x1800790cf  mov     r8, [rax+r13+8B4A8h]
0x1800790d7  movzx   ecx, byte ptr [rax+r13+8B4A0h]
0x1800790e0  mov     [rsp+0A8h+var_78], r8
0x1800790e5  cmp     cl, [rdx+1Ch]
0x1800790e8  jge     short loc_1800790FC
0x1800790ea  mov     eax, 13h
0x1800790ef  add     rsp, 90h
0x1800790f6  pop     r13
0x1800790f8  pop     rsi
0x1800790f9  pop     rbx
0x1800790fa  retn
0x1800790fc  mov     rax, [rsi]
0x1800790ff  mov     rdx, [rdx+8]
0x180079103  mov     [rsp+0A8h+arg_0], rbp
0x18007910b  xor     ebp, ebp
0x18007910d  mov     [rsp+0A8h+var_20], rdi
0x180079115  mov     ecx, ebp
0x180079117  mov     [rsp+0A8h+var_30], r14
0x18007911c  mov     r14, [rsi+10h]
0x180079120  mov     [rsp+0A8h+var_48], rax
0x180079125  mov     eax, ebp
0x180079127  mov     [rsp+0A8h+var_58], rdx
0x18007912c  nop     dword ptr [rax+00h]
0x180079130  sub     ecx, 0FFFFFF80h
0x180079133  mov     [r14+rax*4], rbp
0x180079137  mov     [r14+rax*4+8], rbp
0x18007913c  mov     [r14+rax*4+10h], rbp
0x180079141  mov     [r14+rax*4+18h], rbp
0x180079146  mov     [r14+rax*4+20h], rbp
0x18007914b  mov     [r14+rax*4+28h], rbp
0x180079150  mov     [r14+rax*4+30h], rbp
0x180079155  mov     [r14+rax*4+38h], rbp
0x18007915a  mov     [r14+rax*4+40h], rbp
0x18007915f  mov     [r14+rax*4+48h], rbp
0x180079164  mov     [r14+rax*4+50h], rbp
0x180079169  mov     [r14+rax*4+58h], rbp
0x18007916e  mov     [r14+rax*4+60h], rbp
0x180079173  mov     [r14+rax*4+68h], rbp
0x180079178  mov     [r14+rax*4+70h], rbp
0x18007917d  mov     [r14+rax*4+78h], rbp
0x180079182  mov     [r14+rax*4+80h], rbp
0x18007918a  mov     [r14+rax*4+88h], rbp
0x180079192  mov     [r14+rax*4+90h], rbp
0x18007919a  mov     [r14+rax*4+98h], rbp
0x1800791a2  mov     [r14+rax*4+0A0h], rbp
0x1800791aa  mov     [r14+rax*4+0A8h], rbp
0x1800791b2  mov     [r14+rax*4+0B0h], rbp
0x1800791ba  mov     [r14+rax*4+0B8h], rbp
0x1800791c2  mov     [r14+rax*4+0C0h], rbp
0x1800791ca  mov     [r14+rax*4+0C8h], rbp
0x1800791d2  mov     [r14+rax*4+0D0h], rbp
0x1800791da  mov     [r14+rax*4+0D8h], rbp
0x1800791e2  mov     [r14+rax*4+0E0h], rbp
0x1800791ea  mov     [r14+rax*4+0E8h], rbp
0x1800791f2  mov     [r14+rax*4+0F0h], rbp
0x1800791fa  mov     [r14+rax*4+0F8h], rbp
0x180079202  mov     [r14+rax*4+100h], rbp
0x18007920a  mov     [r14+rax*4+108h], rbp
0x180079212  mov     [r14+rax*4+110h], rbp
0x18007921a  mov     [r14+rax*4+118h], rbp
0x180079222  mov     [r14+rax*4+120h], rbp
0x18007922a  mov     [r14+rax*4+128h], rbp
0x180079232  mov     [r14+rax*4+130h], rbp
0x18007923a  mov     [r14+rax*4+138h], rbp
0x180079242  mov     [r14+rax*4+140h], rbp
0x18007924a  mov     [r14+rax*4+148h], rbp
0x180079252  mov     [r14+rax*4+150h], rbp
0x18007925a  mov     [r14+rax*4+158h], rbp
0x180079262  mov     [r14+rax*4+160h], rbp
0x18007926a  mov     [r14+rax*4+168h], rbp
0x180079272  mov     [r14+rax*4+170h], rbp
0x18007927a  mov     [r14+rax*4+178h], rbp
0x180079282  mov     [r14+rax*4+180h], rbp
0x18007928a  mov     [r14+rax*4+188h], rbp
0x180079292  mov     [r14+rax*4+190h], rbp
0x18007929a  mov     [r14+rax*4+198h], rbp
0x1800792a2  mov     [r14+rax*4+1A0h], rbp
0x1800792aa  mov     [r14+rax*4+1A8h], rbp
0x1800792b2  mov     [r14+rax*4+1B0h], rbp
0x1800792ba  mov     [r14+rax*4+1B8h], rbp
0x1800792c2  mov     [r14+rax*4+1C0h], rbp
0x1800792ca  mov     [r14+rax*4+1C8h], rbp
0x1800792d2  mov     [r14+rax*4+1D0h], rbp
0x1800792da  mov     [r14+rax*4+1D8h], rbp
0x1800792e2  mov     [r14+rax*4+1E0h], rbp
0x1800792ea  mov     [r14+rax*4+1E8h], rbp
0x1800792f2  mov     [r14+rax*4+1F0h], rbp
0x1800792fa  mov     [r14+rax*4+1F8h], rbp
0x180079302  lea     rax, [rax+80h]
0x180079309  cmp     ecx, 400h
0x18007930f  jnz     loc_180079130
0x180079315  mov     r11d, ebp
0x180079318  mov     [rsp+0A8h+var_28], r12
0x180079320  mov     edi, ebp
0x180079322  mov     [rsp+0A8h+var_38], r15
0x180079327  mov     [rsp+0A8h+var_88], ebp
0x18007932b  mov     [rsp+0A8h+var_84], ebp
0x18007932f  cmp     [rsi+21h], bpl
0x180079333  jle     loc_1800797BA
0x180079339  nop     dword ptr [rax+00000000h]
0x180079340  cmp     byte ptr [rsi+1Ch], 0
0x180079344  mov     r9d, ebp
0x180079347  mov     [rsp+0A8h+var_7C], ebp
0x18007934b  jle     loc_1800795E2
0x180079351  mov     eax, edi
0x180079353  shl     eax, 4
0x180079356  mov     [rsp+0A8h+var_80], eax
0x18007935a  nop     word ptr [rax+rax+00h]
0x180079360  mov     r15, [rsp+0A8h+arg_8]
0x180079368  add     eax, r9d
0x18007936b  cdqe
0x18007936d  mov     ecx, ebp
0x18007936f  movsxd  r10, edi
0x180079372  mov     [rsp+0A8h+var_50], rax
0x180079377  mov     [rsp+0A8h+arg_18], ecx
0x18007937e  movsx   rsi, byte ptr [rax+rdx]
0x180079383  shl     rsi, 4
0x180079387  cmp     byte ptr [r10+r15+22h], 0
0x18007938d  mov     [rsp+0A8h+var_60], rsi
0x180079392  mov     [rsp+0A8h+var_68], r10
0x180079397  jle     loc_1800795BF
0x18007939d  nop     dword ptr [rax]
0x1800793a0  movzx   eax, byte ptr [rax+rdx]
0x1800793a4  test    al, al
0x1800793a6  jz      loc_180079595
0x1800793ac  sub     al, 0Dh
0x1800793ae  cmp     al, 2
0x1800793b0  jbe     loc_180079595
0x1800793b6  movsx   r12d, byte ptr [rsi+r13+8B610h]
0x1800793bf  lea     r15d, [r11+rcx]
0x1800793c3  movsxd  rax, r9d
0x1800793c6  movsx   ebp, word ptr [r8+rax*2]
0x1800793cb  movsx   eax, word ptr [r8+rax*2+2]
0x1800793d1  mov     [rsp+0A8h+arg_10], ebp
0x1800793d8  cmp     ebp, eax
0x1800793da  jge     loc_180079595
0x1800793e0  shl     r15d, 7
0x1800793e4  mov     [rsp+0A8h+var_70], r15d
0x1800793e9  nop     dword ptr [rax+00000000h]
0x1800793f0  mov     rsi, [rsi+r13+8B618h]
0x1800793f8  xor     edi, edi
0x1800793fa  nop     word ptr [rax+rax+00h]
0x180079400  cmp     dword ptr [rbx], 4
0x180079403  jnb     short loc_180079412
0x180079405  mov     edx, 4
0x18007940a  mov     rcx, rbx
0x18007940d  call    FillBitCache
0x180079412  mov     ecx, [rbx]
0x180079414  mov     eax, [rbx+4]
0x180079417  add     ecx, 0FFFFFFFCh
0x18007941a  shr     eax, cl
0x18007941c  and     eax, 0Fh
0x18007941f  add     eax, edi
0x180079421  movzx   edi, word ptr [rsi+rax*2]
0x180079425  mov     [rbx], ecx
0x180079427  test    dil, 8
0x18007942b  jz      short loc_180079400
0x18007942d  mov     rsi, [rsp+0A8h+var_60]
0x180079432  mov     eax, edi
0x180079434  and     eax, 3
0x180079437  shr     edi, 4
0x18007943a  add     eax, ecx
0x18007943c  add     r15d, ebp
0x18007943f  mov     [rbx], eax
0x180079441  mov     r8d, 1
0x180079447  movsx   ecx, byte ptr [rsi+r13+8B611h]
0x180079450  movsx   edx, byte ptr [rsi+r13+8B612h]
0x180079459  shl     r8d, cl
0x18007945c  dec     r8d
0x18007945f  movsxd  rbp, r15d
0x180079462  mov     eax, r8d
0x180079465  and     eax, edi
0x180079467  sar     edi, cl
0x180079469  sub     eax, edx
0x18007946b  mov     [r14+rbp*4], eax
0x18007946f  mov     eax, edi
0x180079471  and     eax, r8d
0x180079474  sub     eax, edx
0x180079476  mov     [r14+rbp*4+4], eax
0x18007947b  cmp     byte ptr [rsi+r13+8B610h], 4
0x180079484  jnz     short loc_1800794A0
0x180079486  sar     edi, cl
0x180079488  mov     eax, edi
0x18007948a  sar     edi, cl
0x18007948c  and     eax, r8d
0x18007948f  and     edi, r8d
0x180079492  sub     eax, edx
0x180079494  sub     edi, edx
0x180079496  mov     [r14+rbp*4+8], eax
0x18007949b  mov     [r14+rbp*4+0Ch], edi
0x1800794a0  cmp     byte ptr [rsi+r13+8B612h], 0
0x1800794a9  jnz     short loc_1800794F5
0x1800794ab  xor     edi, edi
0x1800794ad  test    r12d, r12d
0x1800794b0  jle     short loc_1800794F5
0x1800794b2  lea     eax, [r15+rdi]
0x1800794b6  movsxd  rsi, eax
0x1800794b9  cmp     dword ptr [r14+rsi*4], 0
0x1800794be  jz      short loc_1800794E9
0x1800794c0  cmp     dword ptr [rbx], 1
0x1800794c3  jnb     short loc_1800794D2
0x1800794c5  mov     edx, 1
0x1800794ca  mov     rcx, rbx
0x1800794cd  call    FillBitCache
0x1800794d2  dec     dword ptr [rbx]
0x1800794d4  mov     eax, [rbx+4]
0x1800794d7  mov     ecx, [rbx]
0x1800794d9  shr     eax, cl
0x1800794db  test    al, 1
0x1800794dd  jz      short loc_1800794E9
0x1800794df  mov     eax, [r14+rsi*4]
0x1800794e3  neg     eax
0x1800794e5  mov     [r14+rsi*4], eax
0x1800794e9  inc     edi
0x1800794eb  cmp     edi, r12d
0x1800794ee  jl      short loc_1800794B2
0x1800794f0  mov     rsi, [rsp+0A8h+var_60]
0x1800794f5  mov     rax, [rsp+0A8h+var_50]
0x1800794fa  mov     rdx, [rsp+0A8h+var_58]
0x1800794ff  cmp     byte ptr [rax+rdx], 0Bh
0x180079503  jnz     short loc_180079556
0x180079505  mov     edx, [r14+rbp*4]
0x180079509  mov     rcx, rbx
0x18007950c  call    CBlock_GetEscape
0x180079511  mov     edx, [r14+rbp*4+4]
0x180079516  mov     rcx, rbx
0x180079519  mov     [r14+rbp*4], eax
0x18007951d  call    CBlock_GetEscape
0x180079522  mov     edx, [r14+rbp*4]
0x180079526  neg     edx
0x180079528  mov     [r14+rbp*4+4], eax
0x18007952d  cmovs   edx, [r14+rbp*4]
0x180079532  cmp     edx, 1FFFh
0x180079538  jg      loc_1800796DC
0x18007953e  mov     ecx, eax
0x180079540  neg     ecx
0x180079542  cmovs   ecx, eax
0x180079545  cmp     ecx, 1FFFh
0x18007954b  jg      loc_1800796DC
0x180079551  mov     rdx, [rsp+0A8h+var_58]
0x180079556  mov     ebp, [rsp+0A8h+arg_10]
0x18007955d  mov     r8, [rsp+0A8h+var_78]
0x180079562  add     ebp, r12d
0x180079565  movsxd  r9, [rsp+0A8h+var_7C]
0x18007956a  mov     r15d, [rsp+0A8h+var_70]
0x18007956f  mov     [rsp+0A8h+arg_10], ebp
0x180079576  movsx   eax, word ptr [r8+r9*2+2]
0x18007957c  cmp     ebp, eax
0x18007957e  jl      loc_1800793F0
0x180079584  mov     ecx, [rsp+0A8h+arg_18]
0x18007958b  mov     r10, [rsp+0A8h+var_68]
0x180079590  mov     r11d, [rsp+0A8h+var_88]
0x180079595  mov     rax, [rsp+0A8h+arg_8]
0x18007959d  inc     ecx
0x18007959f  mov     [rsp+0A8h+arg_18], ecx
0x1800795a6  movsx   eax, byte ptr [r10+rax+22h]
0x1800795ac  cmp     ecx, eax
0x1800795ae  mov     rax, [rsp+0A8h+var_50]
0x1800795b3  jl      loc_1800793A0
0x1800795b9  mov     edi, [rsp+0A8h+var_84]
0x1800795bd  xor     ebp, ebp
0x1800795bf  mov     rsi, [rsp+0A8h+arg_8]
0x1800795c7  inc     r9d
0x1800795ca  mov     [rsp+0A8h+var_7C], r9d
0x1800795cf  movsx   eax, byte ptr [rsi+1Ch]
0x1800795d3  cmp     r9d, eax
0x1800795d6  mov     eax, [rsp+0A8h+var_80]
0x1800795da  jl      loc_180079360
0x1800795e0  jmp     short loc_1800795E5
0x1800795e2  movsxd  r10, edi
0x1800795e5  movsx   eax, byte ptr [r10+rsi+22h]
0x1800795eb  inc     edi
0x1800795ed  movsx   ecx, byte ptr [rsi+21h]
0x1800795f1  add     r11d, eax
0x1800795f4  mov     [rsp+0A8h+var_88], r11d
0x1800795f9  mov     [rsp+0A8h+var_84], edi
0x1800795fd  cmp     edi, ecx
0x1800795ff  jl      loc_180079340
0x180079605  mov     [rsp+0A8h+var_88], ebp
0x180079609  mov     edx, ebp
0x18007960b  mov     [rsp+0A8h+arg_10], edx
0x180079612  mov     edi, ebp
0x180079614  test    cl, cl
0x180079616  jle     loc_1800797BA
0x18007961c  nop     dword ptr [rax+00h]
  ... truncated ...
```
