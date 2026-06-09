# FastEncoderDeflate

- ea: `0x180001010`
- end: `0x180001a10`
- name: `FastEncoderDeflate`
- size: `2560`
- prototype: `__int64 __fastcall(__int64, int, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800028e0`

## callees

- `0x180001010`
- `0x180001a20`
- `0x180001b90`
- `0x180006ac9`

## pseudocode

```c
__int64 __fastcall FastEncoderDeflate(__int64 a1, int a2, int a3, int a4, int a5)
{
  int v5; // r9d
  __int64 v6; // r10
  unsigned int *v7; // rbp
  int *v8; // rsi
  __int64 v9; // rdi
  void **v10; // r14
  bool v11; // zf
  __int64 v12; // r15
  _WORD *v13; // r12
  int v14; // edx
  int v15; // r11d
  unsigned int v16; // r13d
  unsigned int v17; // r8d
  char *v18; // r10
  __int64 v19; // r8
  __int64 v20; // rax
  int v21; // edx
  char v22; // r10
  int v23; // r8d
  int v24; // ebx
  int v25; // ebp
  int v26; // eax
  unsigned int v27; // ebp
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 result; // rax
  int i; // r11d
  _BYTE *v32; // r14
  __int64 v33; // rdx
  int v34; // r14d
  unsigned int v35; // r9d
  unsigned int v36; // r8d
  unsigned int v37; // edx
  int v38; // r9d
  unsigned int v39; // edx
  __int64 v40; // rax
  unsigned int v41; // r8d
  int Match; // r9d
  char v43; // cl
  __int64 v44; // r8
  unsigned int v45; // eax
  int v46; // r9d
  __int64 v47; // r11
  __int64 v48; // rdx
  __int64 v49; // rax
  __int16 v50; // cx
  size_t v51; // rbx
  int v52; // eax
  __int64 v53; // rax
  int v54; // edx
  int v55; // ecx
  __int64 v56; // rax
  int v57; // ecx
  unsigned int v58; // r8d
  unsigned int v59; // ebx
  unsigned int v60; // r11d
  unsigned int v61; // edx
  unsigned int v62; // edx
  int v63; // r8d
  unsigned int v64; // r10d
  unsigned int v65; // r11d
  __int64 v66; // rax
  unsigned int v67; // r10d
  int v68; // ecx
  __int64 v69; // r10
  int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // r10d
  unsigned int v73; // r9d
  unsigned int v74; // edx
  int v75; // r8d
  unsigned int v76; // edx
  unsigned int v77; // r8d
  __int64 v78; // rax
  unsigned int v79; // r9d
  char v80; // cl
  __int64 v81; // r9
  unsigned int v82; // eax
  unsigned int v83; // r10d
  unsigned int v84; // edx
  int v85; // [rsp+40h] [rbp-88h]
  unsigned int v86; // [rsp+44h] [rbp-84h] BYREF
  _WORD *v87; // [rsp+48h] [rbp-80h]
  __int64 v88; // [rsp+50h] [rbp-78h]
  char *v89; // [rsp+58h] [rbp-70h]
  void **v90; // [rsp+60h] [rbp-68h]
  unsigned int *v91; // [rsp+68h] [rbp-60h]
  int *v92; // [rsp+70h] [rbp-58h]

  v5 = a2;
  v6 = a1;
  v7 = (unsigned int *)(a1 + 64);
  v8 = (int *)(a1 + 68);
  v9 = *(_QWORD *)(a1 + 96);
  v10 = (void **)(a1 + 40);
  v11 = *(_DWORD *)(v9 + 37644) == 0;
  v90 = (void **)(a1 + 40);
  v91 = (unsigned int *)(a1 + 64);
  v92 = (int *)(a1 + 68);
  if ( v11 )
  {
    v51 = g_FastEncoderTreeLength;
    *(_DWORD *)(v9 + 37644) = 1;
    memcpy_0(*v10, g_FastEncoderTreeStructureData, v51);
    v52 = g_FastEncoderPostTreeBitbuf;
    *v10 = (char *)*v10 + v51;
    v6 = a1;
    v5 = a2;
    *v7 = v52;
    *v8 = g_FastEncoderPostTreeBitcount;
  }
  else
  {
    v90 = (void **)(a1 + 40);
    v91 = (unsigned int *)(a1 + 64);
    v92 = (int *)(a1 + 68);
  }
  v12 = *(int *)(v6 + 32);
  v13 = *v10;
  v14 = *(_DWORD *)(v6 + 36);
  v15 = *v8;
  v16 = *v7;
  v87 = *v10;
  v85 = v15;
  if ( (int)v12 < v14 )
  {
    v17 = (16 * *(unsigned __int8 *)(v12 + v9)) ^ *(unsigned __int8 *)(v12 + v9 + 1);
    v88 = v17;
    while ( 1 )
    {
      if ( (unsigned __int64)v13 >= *(_QWORD *)(v6 + 56) )
      {
LABEL_22:
        v10 = v90;
        v7 = v91;
        v8 = v92;
        break;
      }
      v18 = (char *)((int)v12 + v9);
      if ( v14 - (int)v12 > 3 )
      {
        v19 = (unsigned __int8)v18[2] ^ (16 * v17);
        v89 = (char *)((int)v12 + v9);
        v88 = v19;
        v20 = v19 & 0x7FF;
        v21 = *(unsigned __int16 *)(v9 + 2 * v20 + 33546);
        *(_WORD *)(v9 + 2 * v20 + 33546) = v12;
        *(_WORD *)(v9 + 2 * (v12 & 0x1FFF) + 16646) = v21;
        if ( (_WORD)v21 )
        {
          v22 = *v18;
          v23 = v5;
          v24 = 0;
          v25 = 0;
          v26 = v21;
          if ( v21 > (int)v12 - 0x2000 )
          {
            do
            {
              if ( *(_BYTE *)(v24 + v26 + v9) == v22 )
              {
                for ( i = 0; i < 258; i += 6 )
                {
                  v32 = (_BYTE *)(v9 + i + v26);
                  v33 = i + (int)v12;
                  if ( *(_BYTE *)(v33 + v9) != *v32 )
                    break;
                  if ( *(_BYTE *)(v33 + v9 + 1) != v32[1] )
                  {
                    ++i;
                    break;
                  }
                  if ( *(_BYTE *)(v33 + v9 + 2) != v32[2] )
                  {
                    i += 2;
                    break;
                  }
                  if ( *(_BYTE *)(v33 + v9 + 3) != v32[3] )
                  {
                    i += 3;
                    break;
                  }
                  if ( *(_BYTE *)(v33 + v9 + 4) != v32[4] )
                  {
                    i += 4;
                    break;
                  }
                  if ( *(_BYTE *)(v33 + v9 + 5) != v32[5] )
                  {
                    i += 5;
                    break;
                  }
                }
                if ( i > v24 )
                {
                  v24 = i;
                  v25 = v26;
                  if ( i > a5 )
                    break;
                  v22 = *(_BYTE *)(i + (int)v12 + v9);
                }
              }
              if ( !--v23 )
                break;
              v26 = *(unsigned __int16 *)(v9 + 2LL * (v26 & 0x1FFF) + 16646);
            }
            while ( v26 > (int)v12 - 0x2000 );
            v13 = v87;
            v15 = v85;
          }
          v27 = v12 - v25 - 1;
          if ( v24 == 3 && v27 >= 0x4000 )
            v24 = 0;
          v6 = a1;
          if ( v24 + (int)v12 > *(_DWORD *)(a1 + 36) )
            v24 = *(_DWORD *)(a1 + 36) - v12;
          if ( v24 >= 3 )
          {
            v34 = v12 + 1;
            if ( v24 > a3 )
            {
              LODWORD(v12) = v12 + 1;
              v35 = dword_180007E18[v24];
              v36 = v35 & 0x1F;
              v37 = v35 >> 5;
              if ( v36 > 0x10 )
              {
                v83 = v16 | ((unsigned __int16)v37 << v15);
                if ( v15 + 16 < 16 )
                {
                  v15 += 16;
                }
                else
                {
                  *v13++ = v83;
                  v87 = v13;
                  v83 >>= 16;
                }
                v84 = v35 >> 21;
                v38 = v15 + v36 - 16;
                v39 = v83 | (v84 << v15);
                v6 = a1;
                if ( v38 >= 16 )
                {
LABEL_45:
                  *(_BYTE *)v13 = v39;
                  v38 -= 16;
                  *((_BYTE *)v13++ + 1) = BYTE1(v39);
                  v39 >>= 16;
                  v87 = v13;
                }
              }
              else
              {
                v38 = v36 + v15;
                v39 = v16 | (v37 << v15);
                if ( (int)(v36 + v15) >= 16 )
                  goto LABEL_45;
              }
              v40 = (v27 >> 7) + 256;
              if ( v27 < 0x100 )
                v40 = v27;
              v41 = g_FastEncoderDistanceCodeInfo[*((unsigned __int8 *)g_DistLookup + v40)];
              v16 = v39 | (v41 >> 8 << v38);
              v15 = v38 + (v41 & 0xF);
              v85 = v15;
              if ( v15 >= 16 )
              {
                *(_BYTE *)v13 = v16;
                v15 -= 16;
                *((_BYTE *)v13++ + 1) = BYTE1(v16);
                v87 = v13;
                v16 >>= 16;
                v85 = v15;
              }
              Match = v24;
              if ( (v41 & 0xF0) != 0 )
              {
                v43 = v15;
                v44 = (unsigned __int8)v41 >> 4;
                v15 += v44;
                v85 = v15;
                v45 = v16 | ((v27 & g_BitMask[v44]) << v43);
                v16 = v45;
                if ( v15 >= 16 )
                {
                  *(_BYTE *)v13 = v45;
                  v15 -= 16;
                  *((_BYTE *)v13++ + 1) = BYTE1(v45);
                  v87 = v13;
                  v16 = HIWORD(v45);
                  v85 = v15;
                }
              }
LABEL_53:
              if ( *(_DWORD *)(v6 + 36) - (int)v12 > Match )
              {
                v46 = Match - 1;
                if ( v46 > 0 )
                {
                  LODWORD(v47) = v88;
                  do
                  {
                    --v46;
                    v48 = v12 & 0x1FFF;
                    v47 = (16 * (_DWORD)v47) ^ (unsigned int)*(unsigned __int8 *)((int)v12 + v9 + 2);
                    v49 = v47 & 0x7FF;
                    v50 = *(_WORD *)(v9 + 2 * v49 + 33546);
                    *(_WORD *)(v9 + 2 * v49 + 33546) = v12;
                    LODWORD(v12) = v12 + 1;
                    *(_WORD *)(v9 + 2 * v48 + 16646) = v50;
                  }
                  while ( v46 > 0 );
                  v88 = v47;
                  v15 = v85;
                }
              }
              else
              {
                LODWORD(v12) = Match + v12 - 1;
              }
              goto LABEL_21;
            }
            v86 = 0;
            v53 = ((16 * (_DWORD)v88) ^ (unsigned __int8)v89[3]) & 0x7FF;
            v88 = (16 * (_DWORD)v88) ^ (unsigned int)(unsigned __int8)v89[3];
            v54 = *(unsigned __int16 *)(v9 + 2 * v53 + 33546);
            *(_WORD *)(v9 + 2 * v53 + 33546) = v34;
            *(_WORD *)(v9 + 2LL * (v34 & 0x1FFF) + 16646) = v54;
            if ( (_WORD)v54 )
            {
              v55 = a2;
              if ( v24 >= a4 )
                v55 = a2 >> 2;
              Match = FastEncoderFindMatch(v9, (int)v9 + 16646, v34, v54, (__int64)&v86, v55, a5);
              if ( (int)v12 + Match + 1 > *(_DWORD *)(a1 + 36) )
                Match = *(_DWORD *)(a1 + 36) - v34;
              if ( Match > v24 )
              {
                v56 = (unsigned __int8)*v89;
                v57 = (g_FastEncoderLiteralCodeInfo[v56] & 0x1F) + v85;
                v58 = v16 | ((unsigned int)g_FastEncoderLiteralCodeInfo[v56] >> 5 << v85);
                if ( v57 >= 16 )
                {
                  *(_BYTE *)v13 = v58;
                  v57 -= 16;
                  *((_BYTE *)v13++ + 1) = BYTE1(v58);
                  v87 = v13;
                  v58 >>= 16;
                }
                v59 = dword_180007E18[Match];
                v60 = v59 & 0x1F;
                v61 = v59 >> 5;
                if ( v60 > 0x10 )
                {
                  v64 = v58 | ((unsigned __int16)v61 << v57);
                  if ( v57 + 16 < 16 )
                  {
                    v57 += 16;
                  }
                  else
                  {
                    *v13++ = v64;
                    v87 = v13;
                    v64 >>= 16;
                  }
                  v63 = v57 + v60 - 16;
                  v62 = v64 | (v59 >> 21 << v57);
                  if ( v63 < 16 )
                    goto LABEL_80;
                }
                else
                {
                  v62 = v58 | (v61 << v57);
                  v63 = v60 + v57;
                  if ( (int)(v60 + v57) < 16 )
                    goto LABEL_80;
                }
                *(_BYTE *)v13 = v62;
                v63 -= 16;
                *((_BYTE *)v13++ + 1) = BYTE1(v62);
                v62 >>= 16;
                v87 = v13;
LABEL_80:
                v65 = v86;
                v66 = (v86 >> 7) + 256;
                if ( v86 < 0x100 )
                  v66 = v86;
                v67 = g_FastEncoderDistanceCodeInfo[*((unsigned __int8 *)g_DistLookup + v66)];
                v16 = v62 | (v67 >> 8 << v63);
                v68 = v63 + (v67 & 0xF);
                v85 = v68;
                if ( v68 >= 16 )
                {
                  *v13++ = v16;
                  v87 = v13;
                  v16 >>= 16;
                  v85 = v68 - 16;
                }
                if ( (v67 & 0xF0) != 0 )
                {
                  v69 = (unsigned __int8)v67 >> 4;
                  v70 = v65 & g_BitMask[v69];
                  v15 = v69 + v85;
                  v71 = v16 | (v70 << v85);
                  v85 = v15;
                  v16 = v71;
                  if ( v15 >= 16 )
                  {
                    *(_BYTE *)v13 = v71;
                    v15 -= 16;
                    *((_BYTE *)v13++ + 1) = BYTE1(v71);
                    v87 = v13;
                    v16 = HIWORD(v71);
                    v85 = v15;
                  }
                }
                else
                {
                  v15 = v85;
                }
                v6 = a1;
                LODWORD(v12) = v12 + 2;
                goto LABEL_53;
              }
              v15 = v85;
            }
            v72 = dword_180007E18[v24];
            v73 = v72 & 0x1F;
            v74 = v72 >> 5;
            if ( v73 > 0x10 )
            {
              v77 = v16 | ((unsigned __int16)v74 << v15);
              if ( v15 + 16 < 16 )
              {
                v15 += 16;
              }
              else
              {
                *v13++ = v77;
                v87 = v13;
                v77 >>= 16;
              }
              v76 = v77 | (v72 >> 21 << v15);
              v75 = v15 + v73 - 16;
              if ( v75 < 16 )
                goto LABEL_98;
            }
            else
            {
              v75 = v73 + v15;
              v76 = v16 | (v74 << v15);
              if ( (int)(v73 + v15) < 16 )
                goto LABEL_98;
            }
            *(_BYTE *)v13 = v76;
            v75 -= 16;
            *((_BYTE *)v13++ + 1) = BYTE1(v76);
            v76 >>= 16;
            v87 = v13;
LABEL_98:
            v78 = (v27 >> 7) + 256;
            if ( v27 < 0x100 )
              v78 = v27;
            v79 = g_FastEncoderDistanceCodeInfo[*((unsigned __int8 *)g_DistLookup + v78)];
            v16 = v76 | (v79 >> 8 << v75);
            v15 = v75 + (v79 & 0xF);
            v85 = v15;
            if ( v15 >= 16 )
            {
              *(_BYTE *)v13 = v16;
              v15 -= 16;
              *((_BYTE *)v13++ + 1) = BYTE1(v16);
              v87 = v13;
              v16 >>= 16;
              v85 = v15;
            }
            if ( (v79 & 0xF0) != 0 )
            {
              v80 = v15;
              v81 = (unsigned __int8)v79 >> 4;
              v15 += v81;
              v85 = v15;
              v82 = v16 | ((v27 & g_BitMask[v81]) << v80);
              v16 = v82;
              if ( v15 >= 16 )
              {
                *(_BYTE *)v13 = v82;
                v15 -= 16;
                *((_BYTE *)v13++ + 1) = BYTE1(v82);
                v87 = v13;
                v16 = HIWORD(v82);
                v85 = v15;
              }
            }
            v6 = a1;
            Match = v24 - 1;
            LODWORD(v12) = v12 + 2;
            goto LABEL_53;
          }
          v18 = v89;
        }
      }
      v28 = (unsigned int)g_FastEncoderLiteralCodeInfo[(unsigned __int8)*v18] >> 5 << v15;
      v15 += g_FastEncoderLiteralCodeInfo[(unsigned __int8)*v18] & 0x1F;
      v29 = v16 | v28;
      v85 = v15;
      v16 = v29;
      if ( v15 >= 16 )
      {
        *(_BYTE *)v13 = v29;
        v15 -= 16;
        *((_BYTE *)v13++ + 1) = BYTE1(v29);
        v87 = v13;
        v16 = HIWORD(v29);
        v85 = v15;
      }
      v6 = a1;
      LODWORD(v12) = v12 + 1;
LABEL_21:
      v14 = *(_DWORD *)(v6 + 36);
      v17 = v88;
      v5 = a2;
      if ( (int)v12 >= v14 )
        goto LABEL_22;
    }
  }
  *v7 = v16;
  v11 = (_DWORD)v12 == *(_DWORD *)(v6 + 36);
  result = 2;
  *v10 = v13;
  if ( v11 )
    result = 0;
  *(_DWORD *)(v6 + 32) = v12;
  *v8 = v15;
  *(_DWORD *)v6 = result;
  if ( (_DWORD)v12 == 0x4000 )
    return FastEncoderMoveWindows(v6);
  return result;
}

```

## disassembly

```asm
0x180001010  mov     rax, rsp
0x180001013  mov     [rax+20h], r9d
0x180001017  mov     [rax+18h], r8d
0x18000101b  mov     [rax+10h], edx
0x18000101e  mov     [rax+8], rcx
0x180001022  sub     rsp, 0C8h
0x180001029  mov     [rax-8], rbx
0x18000102d  mov     r9d, edx
0x180001030  mov     [rax-10h], rbp
0x180001034  mov     r10, rcx
0x180001037  mov     [rax-18h], rsi
0x18000103b  lea     rbp, [rcx+40h]
0x18000103f  mov     [rax-20h], rdi
0x180001043  lea     rsi, [rcx+44h]
0x180001047  mov     rdi, [rcx+60h]
0x18000104b  mov     [rax-28h], r12
0x18000104f  mov     [rax-30h], r13
0x180001053  mov     [rax-38h], r14
0x180001057  lea     r14, [rcx+28h]
0x18000105b  cmp     dword ptr [rdi+930Ch], 0
0x180001062  mov     [rax-40h], r15
0x180001066  mov     [rsp+0C8h+var_68], r14
0x18000106b  mov     [rsp+0C8h+var_60], rbp
0x180001070  mov     [rsp+0C8h+var_58], rsi
0x180001075  jz      loc_180001550
0x18000107b  mov     [rsp+0C8h+var_68], r14
0x180001080  mov     [rsp+0C8h+var_60], rbp
0x180001085  mov     [rsp+0C8h+var_58], rsi
0x18000108a  movsxd  r15, dword ptr [r10+20h]
0x18000108e  mov     r12, [r14]
0x180001091  mov     edx, [r10+24h]
0x180001095  mov     r11d, [rsi]
0x180001098  mov     r13d, [rbp+0]
0x18000109c  mov     [rsp+0C8h+var_80], r12
0x1800010a1  mov     [rsp+0C8h+var_88], r11d
0x1800010a6  cmp     r15d, edx
0x1800010a9  jge     loc_180001255
0x1800010af  movzx   r8d, byte ptr [r15+rdi+1]
0x1800010b5  lea     r14, cs:180000000h
0x1800010bc  movzx   ecx, byte ptr [r15+rdi]
0x1800010c1  shl     ecx, 4
0x1800010c4  xor     r8d, ecx
0x1800010c7  mov     [rsp+0C8h+var_78], r8
0x1800010cc  nop     dword ptr [rax+00h]
0x1800010d0  cmp     r12, [r10+38h]
0x1800010d4  jnb     loc_180001246
0x1800010da  movsxd  rcx, r15d
0x1800010dd  sub     edx, r15d
0x1800010e0  lea     r10, [rcx+rdi]
0x1800010e4  cmp     edx, 3
0x1800010e7  jle     loc_1800011D2
0x1800010ed  movzx   eax, byte ptr [r10+2]
0x1800010f2  and     ecx, 1FFFh
0x1800010f8  shl     r8d, 4
0x1800010fc  xor     r8d, eax
0x1800010ff  mov     [rsp+0C8h+var_70], r10
0x180001104  mov     eax, r8d
0x180001107  mov     [rsp+0C8h+var_78], r8
0x18000110c  and     eax, 7FFh
0x180001111  movzx   edx, word ptr [rdi+rax*2+830Ah]
0x180001119  mov     [rdi+rax*2+830Ah], r15w
0x180001122  mov     [rdi+rcx*2+4106h], dx
0x18000112a  test    dx, dx
0x18000112d  jz      loc_1800011D2
0x180001133  movzx   r10d, byte ptr [r10]
0x180001137  mov     r8d, r9d
0x18000113a  lea     r9d, [r15-2000h]
0x180001141  xor     ebx, ebx
0x180001143  xor     ebp, ebp
0x180001145  mov     eax, edx
0x180001147  cmp     edx, r9d
0x18000114a  jle     short loc_180001199
0x18000114c  mov     r12d, [rsp+0C8h+arg_20]
0x180001154  nop     dword ptr [rax+00h]
0x180001158  nop     dword ptr [rax+rax+00000000h]
0x180001160  lea     ecx, [rbx+rax]
0x180001163  movsxd  rdx, ecx
0x180001166  cmp     [rdx+rdi], r10b
0x18000116a  jz      loc_1800012C9
0x180001170  sub     r8d, 1
0x180001174  jz      short loc_180001188
0x180001176  and     eax, 1FFFh
0x18000117b  movzx   eax, word ptr [rdi+rax*2+4106h]
0x180001183  cmp     eax, r9d
0x180001186  jg      short loc_180001160
0x180001188  mov     r12, [rsp+0C8h+var_80]
0x18000118d  lea     r14, cs:180000000h
0x180001194  mov     r11d, [rsp+0C8h+var_88]
0x180001199  mov     eax, r15d
0x18000119c  sub     eax, ebp
0x18000119e  lea     ebp, [rax-1]
0x1800011a1  cmp     ebx, 3
0x1800011a4  jz      loc_18000133C
0x1800011aa  mov     r10, [rsp+0C8h+arg_0]
0x1800011b2  lea     eax, [rbx+r15]
0x1800011b6  mov     ecx, [r10+24h]
0x1800011ba  sub     ecx, r15d
0x1800011bd  cmp     eax, [r10+24h]
0x1800011c1  cmovg   ebx, ecx
0x1800011c4  cmp     ebx, 3
0x1800011c7  jge     loc_18000137A
0x1800011cd  mov     r10, [rsp+0C8h+var_70]
0x1800011d2  movzx   eax, byte ptr [r10]
0x1800011d6  mov     ecx, r11d
0x1800011d9  mov     edx, ds:rva g_FastEncoderLiteralCodeInfo[r14+rax*4]
0x1800011e1  mov     eax, edx
0x1800011e3  shr     eax, 5
0x1800011e6  and     edx, 1Fh
0x1800011e9  shl     eax, cl
0x1800011eb  add     r11d, edx
0x1800011ee  or      eax, r13d
0x1800011f1  mov     [rsp+0C8h+var_88], r11d
0x1800011f6  mov     r13d, eax
0x1800011f9  cmp     r11d, 10h
0x1800011fd  jl      short loc_180001221
0x1800011ff  mov     [r12], r13b
0x180001203  add     r11d, 0FFFFFFF0h
0x180001207  shr     eax, 8
0x18000120a  mov     [r12+1], al
0x18000120f  add     r12, 2
0x180001213  mov     [rsp+0C8h+var_80], r12
0x180001218  shr     r13d, 10h
0x18000121c  mov     [rsp+0C8h+var_88], r11d
0x180001221  mov     r10, [rsp+0C8h+arg_0]
0x180001229  inc     r15d
0x18000122c  mov     edx, [r10+24h]
0x180001230  mov     r8, [rsp+0C8h+var_78]
0x180001235  mov     r9d, [rsp+0C8h+arg_8]
0x18000123d  cmp     r15d, edx
0x180001240  jl      loc_1800010D0
0x180001246  mov     r14, [rsp+0C8h+var_68]
0x18000124b  mov     rbp, [rsp+0C8h+var_60]
0x180001250  mov     rsi, [rsp+0C8h+var_58]
0x180001255  xor     ecx, ecx
0x180001257  mov     [rbp+0], r13d
0x18000125b  cmp     r15d, [r10+24h]
0x18000125f  mov     eax, 2
0x180001264  mov     [r14], r12
0x180001267  cmovz   eax, ecx
0x18000126a  mov     [r10+20h], r15d
0x18000126e  mov     [rsi], r11d
0x180001271  cmp     r15d, 4000h
0x180001278  mov     [r10], eax
0x18000127b  mov     r14, [rsp+0C8h+var_38]
0x180001283  mov     r13, [rsp+0C8h+var_30]
0x18000128b  mov     r12, [rsp+0C8h+var_28]
0x180001293  mov     rdi, [rsp+0C8h+var_20]
0x18000129b  mov     rsi, [rsp+0C8h+var_18]
0x1800012a3  mov     rbp, [rsp+0C8h+var_10]
0x1800012ab  mov     rbx, [rsp+0C8h+var_8]
0x1800012b3  mov     r15, [rsp+0C8h+var_40]
0x1800012bb  jz      loc_180001A03
0x1800012c1  add     rsp, 0C8h
0x1800012c8  retn
0x1800012c9  xor     r11d, r11d
0x1800012cc  lea     ecx, [r11+rax]
0x1800012d0  movsxd  r14, ecx
0x1800012d3  lea     ecx, [r11+r15]
0x1800012d7  add     r14, rdi
0x1800012da  movsxd  rdx, ecx
0x1800012dd  movzx   ecx, byte ptr [r14]
0x1800012e1  cmp     [rdx+rdi], cl
0x1800012e4  jnz     short loc_180001352
0x1800012e6  movzx   ecx, byte ptr [r14+1]
0x1800012eb  cmp     [rdx+rdi+1], cl
0x1800012ef  jnz     short loc_18000134F
0x1800012f1  movzx   ecx, byte ptr [r14+2]
0x1800012f6  cmp     [rdx+rdi+2], cl
0x1800012fa  jnz     loc_1800014C2
0x180001300  movzx   ecx, byte ptr [r14+3]
0x180001305  cmp     [rdx+rdi+3], cl
0x180001309  jnz     loc_1800014CB
0x18000130f  movzx   ecx, byte ptr [r14+4]
0x180001314  cmp     [rdx+rdi+4], cl
0x180001318  jnz     loc_1800014D4
0x18000131e  movzx   ecx, byte ptr [r14+5]
0x180001323  cmp     [rdx+rdi+5], cl
0x180001327  jnz     loc_1800014DD
0x18000132d  add     r11d, 6
0x180001331  cmp     r11d, 102h
0x180001338  jl      short loc_1800012CC
0x18000133a  jmp     short loc_180001352
0x18000133c  cmp     ebp, 4000h
0x180001342  jb      loc_1800011AA
0x180001348  xor     ebx, ebx
0x18000134a  jmp     loc_1800011AA
0x18000134f  inc     r11d
0x180001352  cmp     r11d, ebx
0x180001355  jle     loc_180001170
0x18000135b  mov     ebx, r11d
0x18000135e  mov     ebp, eax
0x180001360  cmp     r11d, r12d
0x180001363  jg      loc_180001188
0x180001369  lea     ecx, [r11+r15]
0x18000136d  movsxd  rdx, ecx
0x180001370  movzx   r10d, byte ptr [rdx+rdi]
0x180001375  jmp     loc_180001170
0x18000137a  lea     r14d, [r15+1]
0x18000137e  cmp     ebx, [rsp+0C8h+arg_10]
0x180001385  jle     loc_18000159C
0x18000138b  movsxd  rax, ebx
0x18000138e  mov     r15d, r14d
0x180001391  lea     r14, cs:180000000h
0x180001398  mov     ecx, r11d
0x18000139b  mov     r9d, ds:rva dword_180007E18[r14+rax*4]
0x1800013a3  mov     r8d, r9d
0x1800013a6  mov     edx, r9d
0x1800013a9  and     r8d, 1Fh
0x1800013ad  shr     edx, 5
0x1800013b0  cmp     r8d, 10h
0x1800013b4  ja      loc_1800019A3
0x1800013ba  shl     edx, cl
0x1800013bc  lea     r9d, [r8+r11]
0x1800013c0  or      edx, r13d
0x1800013c3  cmp     r9d, 10h
0x1800013c7  jl      short loc_1800013E7
0x1800013c9  mov     [r12], dl
0x1800013cd  mov     eax, edx
0x1800013cf  shr     eax, 8
0x1800013d2  add     r9d, 0FFFFFFF0h
0x1800013d6  mov     [r12+1], al
0x1800013db  add     r12, 2
0x1800013df  shr     edx, 10h
0x1800013e2  mov     [rsp+0C8h+var_80], r12
0x1800013e7  mov     eax, ebp
0x1800013e9  shr     eax, 7
0x1800013ec  add     eax, 100h
0x1800013f1  cmp     ebp, 100h
0x1800013f7  cmovb   eax, ebp
0x1800013fa  movzx   ecx, byte ptr [rax+r14+0AB20h]
0x180001403  mov     r8d, ds:rva g_FastEncoderDistanceCodeInfo[r14+rcx*4]
0x18000140b  mov     r13d, r8d
0x18000140e  shr     r13d, 8
0x180001412  mov     ecx, r9d
0x180001415  shl     r13d, cl
0x180001418  mov     r11d, r8d
0x18000141b  and     r11d, 0Fh
0x18000141f  or      r13d, edx
0x180001422  add     r11d, r9d
0x180001425  mov     [rsp+0C8h+var_88], r11d
0x18000142a  cmp     r11d, 10h
0x18000142e  jl      short loc_180001455
0x180001430  mov     [r12], r13b
0x180001434  mov     eax, r13d
0x180001437  shr     eax, 8
0x18000143a  add     r11d, 0FFFFFFF0h
0x18000143e  mov     [r12+1], al
0x180001443  add     r12, 2
0x180001447  mov     [rsp+0C8h+var_80], r12
0x18000144c  shr     r13d, 10h
0x180001450  mov     [rsp+0C8h+var_88], r11d
0x180001455  mov     r9d, ebx
0x180001458  test    r8b, 0F0h
0x18000145c  jz      short loc_1800014AB
0x18000145e  shr     r8d, 4
0x180001462  mov     ecx, r11d
0x180001465  and     r8d, 0Fh
0x180001469  add     r11d, r8d
0x18000146c  mov     [rsp+0C8h+var_88], r11d
0x180001471  mov     eax, ds:rva g_BitMask[r14+r8*4]
0x180001479  and     eax, ebp
0x18000147b  shl     eax, cl
0x18000147d  or      eax, r13d
0x180001480  mov     r13d, eax
0x180001483  cmp     r11d, 10h
0x180001487  jl      short loc_1800014AB
0x180001489  mov     [r12], r13b
0x18000148d  add     r11d, 0FFFFFFF0h
0x180001491  shr     eax, 8
0x180001494  mov     [r12+1], al
0x180001499  add     r12, 2
0x18000149d  mov     [rsp+0C8h+var_80], r12
0x1800014a2  shr     r13d, 10h
0x1800014a6  mov     [rsp+0C8h+var_88], r11d
0x1800014ab  mov     eax, [r10+24h]
0x1800014af  sub     eax, r15d
0x1800014b2  cmp     eax, r9d
0x1800014b5  jg      short loc_1800014E6
0x1800014b7  dec     r15d
0x1800014ba  add     r15d, r9d
0x1800014bd  jmp     loc_18000122C
0x1800014c2  add     r11d, 2
0x1800014c6  jmp     loc_180001352
0x1800014cb  add     r11d, 3
0x1800014cf  jmp     loc_180001352
0x1800014d4  add     r11d, 4
0x1800014d8  jmp     loc_180001352
0x1800014dd  add     r11d, 5
0x1800014e1  jmp     loc_180001352
0x1800014e6  dec     r9d
0x1800014e9  test    r9d, r9d
0x1800014ec  jle     loc_18000122C
0x1800014f2  mov     r11, [rsp+0C8h+var_78]
0x1800014f7  nop     word ptr [rax+rax+00000000h]
0x180001500  movsxd  rdx, r15d
0x180001503  dec     r9d
0x180001506  shl     r11d, 4
0x18000150a  movzx   eax, byte ptr [rdx+rdi+2]
0x18000150f  and     edx, 1FFFh
0x180001515  xor     eax, r11d
  ... truncated ...
```
