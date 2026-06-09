# deformat

- ea: `0x18001af58`
- end: `0x18001b86e`
- name: `deformat`
- size: `2326`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a330`
- `0x18001ac40`

## callees

- `0x180001580`
- `0x180001eb0`
- `0x18001af58`

## pseudocode

```c
unsigned __int64 __fastcall deformat(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  _DWORD *v4; // rbx
  __int64 v6; // rdi
  char *v7; // rdx
  char v8; // cl
  char **v9; // r14
  char *v10; // r15
  __int64 v11; // r12
  int v12; // r13d
  __int64 v13; // rsi
  __int64 v14; // r10
  unsigned __int8 *v15; // r8
  int v16; // edx
  char v17; // r9
  int v18; // edi
  int v19; // r11d
  int v20; // edx
  unsigned __int8 *v21; // r10
  int v22; // r8d
  unsigned int v23; // r8d
  int v24; // edx
  char v25; // cl
  unsigned __int64 v26; // rax
  int v27; // edx
  char v28; // cl
  __int64 v29; // rcx
  int v30; // edx
  unsigned __int64 v31; // rbx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  _DWORD *v36; // rax
  __int64 v37; // rcx
  char *v38; // rbx
  int v39; // r8d
  char v40; // r9
  int v41; // eax
  unsigned __int64 result; // rax
  __int64 **v43; // rsi
  unsigned __int64 *v44; // r11
  __int64 *v45; // r10
  unsigned __int8 **v46; // rdi
  char v47; // r8
  __int64 v48; // r13
  unsigned __int8 *v49; // r15
  int v50; // r14d
  int v51; // r12d
  unsigned int v52; // r9d
  int v53; // edx
  char v54; // cl
  unsigned __int64 v55; // rax
  int v56; // edx
  char v57; // cl
  __int64 v58; // rcx
  int v59; // edx
  unsigned __int64 v60; // rbx
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // rcx
  unsigned __int64 v64; // rdx
  __int64 *v65; // rax
  _QWORD *v66; // rcx
  unsigned __int64 *v67; // rcx
  int v68; // r9d
  char v69; // r8
  int v70; // eax
  bool v71; // zf
  __int64 **v72; // r12
  unsigned __int8 ***v73; // r15
  __int64 *j; // r10
  unsigned __int8 **v75; // rbx
  char v76; // r8
  __int64 v77; // r13
  unsigned __int8 *v78; // rdi
  int v79; // r11d
  int v80; // esi
  unsigned int v81; // r9d
  int v82; // edx
  char v83; // cl
  int v84; // edx
  char v85; // cl
  __int64 v86; // rcx
  int v87; // edx
  unsigned __int64 v88; // r14
  int v89; // eax
  __int64 v90; // rcx
  unsigned __int64 v91; // rdx
  unsigned int v92; // r9d
  char v93; // r8
  _DWORD *v94; // [rsp+20h] [rbp-E0h]
  char *v96; // [rsp+30h] [rbp-D0h]
  BOOL v97; // [rsp+38h] [rbp-C8h]
  __int64 i; // [rsp+38h] [rbp-C8h]
  int v99; // [rsp+40h] [rbp-C0h]
  int v100; // [rsp+44h] [rbp-BCh]
  __int64 v102; // [rsp+50h] [rbp-B0h]
  __int64 k; // [rsp+50h] [rbp-B0h]
  unsigned __int64 *v104; // [rsp+58h] [rbp-A8h]
  __int64 v105; // [rsp+60h] [rbp-A0h]
  _QWORD *v106; // [rsp+68h] [rbp-98h]
  _QWORD v107[7]; // [rsp+70h] [rbp-90h] BYREF
  char v108; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v109[31]; // [rsp+B0h] [rbp-50h] BYREF
  char v110; // [rsp+1A8h] [rbp+A8h] BYREF
  char v111; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = a3;
  v105 = a2;
  v6 = a1;
  v94 = a3;
  memset_0(v107, 0, 0x40u);
  memset_0(v109, 0, 0x100u);
  v100 = 0;
  v106 = v109;
  v7 = (char *)(a2 + 3);
  v102 = a2 + 3;
  v104 = (unsigned __int64 *)&v110;
  v99 = 5;
  v96 = &v111;
  while ( 2 )
  {
    if ( (unsigned __int64)v7 < *(_QWORD *)v6 || (unsigned __int64)&v7[-*(_QWORD *)v6] > *(unsigned int *)(v6 + 8) )
    {
      v8 = -1;
      v9 = (char **)v107;
      v10 = &v108;
    }
    else
    {
      v8 = *v7;
      v9 = (char **)v107;
      v10 = &v108;
      v97 = 0;
      if ( (*v7 & 0xF0) == 0 )
        goto LABEL_9;
    }
    v100 = 1;
    v97 = (v8 & 0x70) == 112;
LABEL_9:
    v11 = a1;
    v12 = v8 & 0xF;
    v13 = 0;
    while ( 2 )
    {
      v14 = (unsigned __int8)offset2[4 * v13];
      v15 = (unsigned __int8 *)(v14 + v105);
      if ( (unsigned __int64)(v14 + v105) < *(_QWORD *)v11
        || (unsigned __int64)&v15[-*(_QWORD *)v11] >= *(unsigned int *)(v11 + 8) )
      {
        v16 = 0xFFFF;
      }
      else
      {
        v16 = v15[1] + (*v15 << 8);
      }
      v17 = 20;
      v18 = (unsigned int)v13 < 4 ? 5 : 3;
      v19 = (unsigned __int16)VLDecodeZigOffset720[v12 + (v16 & 0x70)];
      *v4 = (__int16)v16;
      v20 = v16 << 28;
      v21 = (unsigned __int8 *)(v105 + 2 + v14);
      if ( (unsigned __int64)v21 < *(_QWORD *)v11
        || (unsigned __int64)&v21[-*(_QWORD *)v11] >= *(unsigned int *)(v11 + 8) )
      {
        v22 = 0xFFFF;
      }
      else
      {
        v22 = v21[1] + (*v21 << 8);
      }
      v23 = v20 + (v22 << 12);
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v17 < 16 && v18 > 0 )
          {
            v21 += 2;
            if ( (unsigned __int64)v21 < *(_QWORD *)v11
              || (unsigned __int64)&v21[-*(_QWORD *)v11] >= *(unsigned int *)(v11 + 8) )
            {
              v24 = 0xFFFF;
            }
            else
            {
              v24 = v21[1] + (*v21 << 8);
            }
            v25 = 16 - v17;
            v17 += 16;
            v23 += v24 << v25;
            --v18;
            if ( v19 >= 1664 )
              v19 = 0;
          }
          v26 = (unsigned __int64)v23 >> 22;
          v27 = VLDecodeTableRoot[v26];
          v28 = VLDecodeTableRoot[v26] & 0xF;
          if ( !v28 )
            break;
LABEL_36:
          v17 -= v28;
          if ( v17 < 0 )
            goto LABEL_40;
          v23 <<= v28;
          v33 = v27 >> 8;
          v19 += (v27 >> 4) & 0x3F;
          if ( BYTE1(v27) > 3u )
          {
            v34 = v19++;
            v35 = (unsigned __int8)nzigtable[2 * v34];
            v94[v35] = v33 << byte_180022A61[2 * v34];
            *(_BYTE *)((v35 >> 3) + a4) = v35 & 7;
          }
        }
        if ( v27 > 0 )
          break;
        if ( !VLDecodeTableRoot[v26] )
        {
          v32 = (v23 >> 19) - 7936;
          v27 = VLDecodeTableExtra[v32];
          v28 = VLDecodeTableExtra[v32] & 0xF;
          goto LABEL_36;
        }
        v17 -= 16;
        if ( v17 < 0 )
        {
          v28 = 16;
LABEL_40:
          v17 += v28;
LABEL_41:
          v36 = v94;
          v37 = a4;
          *v9++ = v96;
          *((_DWORD *)v96 + 4) = v23;
          v96[22] = v17;
          *((_WORD *)v96 + 10) = v19;
          *(_QWORD *)v96 = v94;
          *((_QWORD *)v96 + 1) = a4;
          v38 = v96 + 24;
          v96 += 24;
          goto LABEL_51;
        }
        v29 = v19;
        v30 = (v23 >> 15) & 0x3FC;
        v31 = (unsigned __int8)nzigtable[2 * v19];
        if ( (v23 & 0x10000) != 0 )
          v30 = -v30;
        v23 <<= 16;
        v11 = a1;
        ++v19;
        v94[v31] = v30 << byte_180022A61[2 * v29];
        *(_BYTE *)((v31 >> 3) + a4) = v31 & 7;
      }
      if ( v17 < 4 )
        goto LABEL_41;
      v39 = 16 * v23;
      v40 = v17 - 4;
      if ( v40 <= 16 )
      {
        v41 = v39;
      }
      else
      {
        v40 -= 16;
        v21 -= 2;
        ++v18;
        v41 = v39 & (-1 << (32 - v40));
      }
      if ( v40 || v18 )
      {
        *(_QWORD *)v10 = v96;
        v10 -= 8;
        *((_DWORD *)v96 + 3) = v41;
        v96[16] = v40;
        *((_DWORD *)v96 + 2) = v18;
        *(_QWORD *)v96 = v21;
        v38 = v96 + 24;
        v96 += 24;
      }
      else
      {
        v38 = v96;
      }
      v37 = a4;
      v36 = v94;
LABEL_51:
      result = (unsigned __int64)(v36 + 64);
      a4 = v37 + 8;
      v13 = (unsigned int)(v13 + 1);
      v94 = (_DWORD *)result;
      if ( (int)v13 < 6 )
      {
        v4 = (_DWORD *)result;
        continue;
      }
      break;
    }
    v96 = v38;
    if ( v97 )
    {
      v67 = v104;
      goto LABEL_97;
    }
    *v9 = 0;
    v43 = (__int64 **)v107;
    *(_QWORD *)v10 = 0;
    v44 = (unsigned __int64 *)&v108;
    v45 = (__int64 *)v107[0];
LABEL_79:
    if ( v45 )
    {
      v46 = (unsigned __int8 **)*v44;
      if ( *v44 )
      {
        v47 = *((_BYTE *)v46 + 16) + *((_BYTE *)v45 + 22);
        v48 = *v45;
        v49 = *v46;
        v50 = *((unsigned __int16 *)v45 + 10);
        v51 = *((_DWORD *)v46 + 2);
        v52 = *((_DWORD *)v45 + 4) + (*((_DWORD *)v46 + 3) >> *((_BYTE *)v45 + 22));
        for ( i = v45[1]; ; *(_BYTE *)((v60 >> 3) + i) = v60 & 7 )
        {
          while ( 1 )
          {
            if ( v47 < 16 && v51 > 0 )
            {
              v49 += 2;
              if ( (unsigned __int64)v49 < *(_QWORD *)a1
                || (unsigned __int64)&v49[-*(_QWORD *)a1] >= *(unsigned int *)(a1 + 8) )
              {
                v53 = 0xFFFF;
              }
              else
              {
                v53 = v49[1] + (*v49 << 8);
              }
              v54 = 16 - v47;
              v47 += 16;
              v52 += v53 << v54;
              --v51;
              if ( v50 >= 1664 )
                v50 = 0;
            }
            v55 = (unsigned __int64)v52 >> 22;
            v56 = VLDecodeTableRoot[v55];
            v57 = VLDecodeTableRoot[v55] & 0xF;
            if ( !v57 )
              break;
LABEL_72:
            v47 -= v57;
            if ( v47 < 0 )
              goto LABEL_76;
            v52 <<= v57;
            v62 = v56 >> 8;
            v50 += (v56 >> 4) & 0x3F;
            if ( BYTE1(v56) > 3u )
            {
              v63 = v50++;
              v64 = (unsigned __int8)nzigtable[2 * v63];
              *(_DWORD *)(v48 + 4 * v64) = v62 << byte_180022A61[2 * v63];
              *(_BYTE *)((v64 >> 3) + i) = v64 & 7;
            }
          }
          if ( v56 > 0 )
          {
            if ( v47 < 4 )
              goto LABEL_77;
            v68 = 16 * v52;
            v69 = v47 - 4;
            if ( v69 <= 16 )
            {
              v70 = v68;
            }
            else
            {
              v69 -= 16;
              v49 -= 2;
              ++v51;
              v70 = v68 & (-1 << (32 - v69));
            }
            if ( v69 || v51 )
            {
              *((_DWORD *)v46 + 3) = v70;
              *((_BYTE *)v46 + 16) = v69;
              *v46 = v49;
              *((_DWORD *)v46 + 2) = v51;
            }
            else
            {
              --v44;
            }
            ++v43;
LABEL_78:
            v45 = *v43;
            goto LABEL_79;
          }
          if ( !VLDecodeTableRoot[v55] )
          {
            v61 = (v52 >> 19) - 7936;
            v56 = VLDecodeTableExtra[v61];
            v57 = VLDecodeTableExtra[v61] & 0xF;
            goto LABEL_72;
          }
          v47 -= 16;
          if ( v47 < 0 )
          {
            v57 = 16;
LABEL_76:
            v47 += v57;
LABEL_77:
            *((_DWORD *)v45 + 4) = v52;
            --v44;
            *((_BYTE *)v45 + 22) = v47;
            *((_WORD *)v45 + 10) = v50;
            goto LABEL_78;
          }
          v58 = v50;
          v59 = (v52 >> 15) & 0x3FC;
          v60 = (unsigned __int8)nzigtable[2 * v50];
          if ( (v52 & 0x10000) != 0 )
            v59 = -v59;
          v52 <<= 16;
          v46 = (unsigned __int8 **)*v44;
          ++v50;
          *(_DWORD *)(v48 + 4 * v60) = v59 << byte_180022A61[2 * v58];
        }
      }
    }
    v65 = *v43;
    if ( *v43 )
    {
      v66 = v106;
      do
      {
        *v66 = v65;
        v65 = *++v43;
        ++v66;
      }
      while ( *v43 );
      v106 = v66;
    }
    result = *v44;
    v67 = v104;
    if ( *v44 )
    {
      do
      {
        *v67 = result;
        result = *--v44;
        --v67;
      }
      while ( *v44 );
      v104 = v67;
    }
LABEL_97:
    v105 += 80;
    v7 = (char *)(v102 + 80);
    v71 = v99-- == 1;
    v4 = v94;
    v102 += 80;
    if ( !v71 )
    {
      v6 = a1;
      continue;
    }
    break;
  }
  if ( !v100 )
  {
    result = (unsigned __int64)v106;
    v72 = (__int64 **)v109;
    v73 = (unsigned __int8 ***)&v110;
    *v106 = 0;
    *v67 = 0;
    for ( j = (__int64 *)v109[0]; ; j = *v72 )
    {
      if ( !j )
        return result;
      v75 = *v73;
      if ( !*v73 )
        return result;
      v76 = *((_BYTE *)v75 + 16) + *((_BYTE *)j + 22);
      v77 = *j;
      v78 = *v75;
      v79 = *((unsigned __int16 *)j + 10);
      v80 = *((_DWORD *)v75 + 2);
      v81 = *((_DWORD *)j + 4) + (*((_DWORD *)v75 + 3) >> *((_BYTE *)j + 22));
      for ( k = j[1]; ; *(_BYTE *)((v88 >> 3) + k) = v88 & 7 )
      {
        while ( 1 )
        {
          if ( v76 < 16 && v80 > 0 )
          {
            v78 += 2;
            if ( (unsigned __int64)v78 < *(_QWORD *)a1
              || (unsigned __int64)&v78[-*(_QWORD *)a1] >= *(unsigned int *)(a1 + 8) )
            {
              v82 = 0xFFFF;
            }
            else
            {
              v82 = v78[1] + (*v78 << 8);
            }
            v83 = 16 - v76;
            v76 += 16;
            v81 += v82 << v83;
            --v80;
            if ( v79 >= 1664 )
              v79 = 0;
          }
          result = (unsigned __int64)v81 >> 22;
          v84 = VLDecodeTableRoot[result];
          v85 = VLDecodeTableRoot[result] & 0xF;
          if ( !v85 )
            break;
LABEL_118:
          v76 -= v85;
          if ( v76 < 0 )
            goto LABEL_122;
          v81 <<= v85;
          v89 = v84 >> 8;
          v79 += (v84 >> 4) & 0x3F;
          if ( BYTE1(v84) > 3u )
          {
            v90 = v79++;
            v91 = (unsigned __int8)nzigtable[2 * v90];
            *(_DWORD *)(v77 + 4 * v91) = v89 << byte_180022A61[2 * v90];
            *(_BYTE *)((v91 >> 3) + k) = v91 & 7;
          }
        }
        if ( v84 > 0 )
          break;
        if ( !VLDecodeTableRoot[result] )
        {
          result = (v81 >> 19) - 7936;
          v84 = VLDecodeTableExtra[result];
          v85 = VLDecodeTableExtra[result] & 0xF;
          goto LABEL_118;
        }
        v76 -= 16;
        if ( v76 < 0 )
        {
          v85 = 16;
LABEL_122:
          v76 += v85;
LABEL_123:
          *((_DWORD *)j + 4) = v81;
          --v73;
          *((_BYTE *)j + 22) = v76;
          *((_WORD *)j + 10) = v79;
          goto LABEL_124;
        }
        v86 = v79;
        v87 = (v81 >> 15) & 0x3FC;
        v88 = (unsigned __int8)nzigtable[2 * v79];
        if ( (v81 & 0x10000) != 0 )
          v87 = -v87;
        v81 <<= 16;
        v75 = *v73;
        ++v79;
        *(_DWORD *)(v77 + 4 * v88) = v87 << byte_180022A61[2 * v86];
      }
      if ( v76 < 4 )
        goto LABEL_123;
      v92 = 16 * v81;
      v93 = v76 - 4;
      if ( v93 <= 16 )
      {
        result = v92;
      }
      else
      {
        v93 -= 16;
        v78 -= 2;
        ++v80;
        result = v92 & (-1 << (32 - v93));
      }
      if ( v93 || v80 )
      {
        *((_DWORD *)v75 + 3) = result;
        *((_BYTE *)v75 + 16) = v93;
        *v75 = v78;
        *((_DWORD *)v75 + 2) = v80;
      }
      else
      {
        --v73;
      }
      ++v72;
LABEL_124:
      ;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001af58  mov     [rsp-8+arg_0], rbx
0x18001af5d  push    rbp
0x18001af5e  push    rsi
0x18001af5f  push    rdi
0x18001af60  push    r12
0x18001af62  push    r13
0x18001af64  push    r14
0x18001af66  push    r15
0x18001af68  lea     rbp, [rsp-390h]
0x18001af70  sub     rsp, 490h
0x18001af77  mov     rax, cs:__security_cookie
0x18001af7e  xor     rax, rsp
0x18001af81  mov     [rbp+3C0h+var_40], rax
0x18001af88  mov     rbx, r8
0x18001af8b  mov     [rsp+4C0h+var_460], rdx
0x18001af90  mov     rsi, rdx
0x18001af93  mov     [rsp+4C0h+var_478], rcx
0x18001af98  xor     edx, edx; Val
0x18001af9a  mov     [rsp+4C0h+var_498], r9
0x18001af9f  mov     rdi, rcx
0x18001afa2  mov     [rsp+4C0h+var_4A0], rbx
0x18001afa7  lea     rcx, [rsp+4C0h+var_450]; void *
0x18001afac  lea     r8d, [rdx+40h]; Size
0x18001afb0  call    memset_0
0x18001afb5  xor     edx, edx; Val
0x18001afb7  lea     rcx, [rbp+3C0h+var_410]; void *
0x18001afbb  mov     r8d, 100h; Size
0x18001afc1  call    memset_0
0x18001afc6  lea     rax, [rbp+3C0h+var_410]
0x18001afca  mov     [rsp+4C0h+var_47C], 0
0x18001afd2  mov     [rsp+4C0h+var_458], rax
0x18001afd7  lea     rdx, [rsi+3]
0x18001afdb  lea     rax, [rbp+3C0h+var_318]
0x18001afe2  mov     [rsp+4C0h+var_470], rdx
0x18001afe7  mov     [rsp+4C0h+var_468], rax
0x18001afec  lea     r11, cs:180000000h
0x18001aff3  lea     rax, [rbp+3C0h+var_310]
0x18001affa  mov     [rsp+4C0h+var_480], 5
0x18001b002  mov     [rsp+4C0h+var_490], rax
0x18001b007  jmp     short loc_18001B00E
0x18001b009  mov     rdi, [rsp+4C0h+var_478]
0x18001b00e  cmp     rdx, [rdi]
0x18001b011  jb      short loc_18001B03B
0x18001b013  mov     eax, [rdi+8]
0x18001b016  mov     rcx, rdx
0x18001b019  sub     rcx, [rdi]
0x18001b01c  cmp     rcx, rax
0x18001b01f  ja      short loc_18001B03B
0x18001b021  mov     cl, [rdx]
0x18001b023  lea     r14, [rsp+4C0h+var_450]
0x18001b028  xor     r12d, r12d
0x18001b02b  lea     r15, [rbp+3C0h+var_418]
0x18001b02f  mov     dword ptr [rsp+4C0h+var_488], r12d
0x18001b034  test    cl, 0F0h
0x18001b037  jz      short loc_18001B060
0x18001b039  jmp     short loc_18001B046
0x18001b03b  mov     cl, 0FFh
0x18001b03d  lea     r14, [rsp+4C0h+var_450]
0x18001b042  lea     r15, [rbp+3C0h+var_418]
0x18001b046  xor     r12d, r12d
0x18001b049  mov     [rsp+4C0h+var_47C], 1
0x18001b051  mov     al, cl
0x18001b053  and     al, 70h
0x18001b055  cmp     al, 70h ; 'p'
0x18001b057  setz    r12b
0x18001b05b  mov     dword ptr [rsp+4C0h+var_488], r12d
0x18001b060  mov     r12, [rsp+4C0h+var_478]
0x18001b065  movzx   r13d, cl
0x18001b069  and     r13d, 0Fh
0x18001b06d  xor     esi, esi
0x18001b06f  jmp     short loc_18001B074
0x18001b071  mov     rbx, rax
0x18001b074  movzx   r10d, rva offset2[r11+rsi*4]
0x18001b07d  mov     r8, [rsp+4C0h+var_460]
0x18001b082  add     r8, r10
0x18001b085  cmp     r8, [r12]
0x18001b089  jb      short loc_18001B0AC
0x18001b08b  mov     eax, [r12+8]
0x18001b090  mov     rcx, r8
0x18001b093  sub     rcx, [r12]
0x18001b097  cmp     rcx, rax
0x18001b09a  jnb     short loc_18001B0AC
0x18001b09c  movzx   edx, byte ptr [r8]
0x18001b0a0  movzx   eax, byte ptr [r8+1]
0x18001b0a5  shl     edx, 8
0x18001b0a8  add     edx, eax
0x18001b0aa  jmp     short loc_18001B0B1
0x18001b0ac  mov     edx, 0FFFFh
0x18001b0b1  mov     eax, edx
0x18001b0b3  cmp     esi, 4
0x18001b0b6  mov     r9b, 14h
0x18001b0b9  sbb     edi, edi
0x18001b0bb  and     eax, 70h
0x18001b0be  add     eax, r13d
0x18001b0c1  and     edi, 2
0x18001b0c4  add     edi, 3
0x18001b0c7  movzx   r11d, rva VLDecodeZigOffset720[r11+rax*2]
0x18001b0d0  movsx   eax, dx
0x18001b0d3  mov     [rbx], eax
0x18001b0d5  mov     rax, [rsp+4C0h+var_460]
0x18001b0da  add     rax, 2
0x18001b0de  shl     edx, 1Ch
0x18001b0e1  add     r10, rax
0x18001b0e4  cmp     r10, [r12]
0x18001b0e8  jb      short loc_18001B10D
0x18001b0ea  mov     eax, [r12+8]
0x18001b0ef  mov     rcx, r10
0x18001b0f2  sub     rcx, [r12]
0x18001b0f6  cmp     rcx, rax
0x18001b0f9  jnb     short loc_18001B10D
0x18001b0fb  movzx   r8d, byte ptr [r10]
0x18001b0ff  movzx   eax, byte ptr [r10+1]
0x18001b104  shl     r8d, 8
0x18001b108  add     r8d, eax
0x18001b10b  jmp     short loc_18001B113
0x18001b10d  mov     r8d, 0FFFFh
0x18001b113  shl     r8d, 0Ch
0x18001b117  add     r8d, edx
0x18001b11a  lea     rbx, cs:180000000h
0x18001b121  cmp     r9b, 10h
0x18001b125  jge     short loc_18001B17E
0x18001b127  test    edi, edi
0x18001b129  jle     short loc_18001B17E
0x18001b12b  add     r10, 2
0x18001b12f  cmp     r10, [r12]
0x18001b133  jb      short loc_18001B156
0x18001b135  mov     eax, [r12+8]
0x18001b13a  mov     rcx, r10
0x18001b13d  sub     rcx, [r12]
0x18001b141  cmp     rcx, rax
0x18001b144  jnb     short loc_18001B156
0x18001b146  movzx   edx, byte ptr [r10]
0x18001b14a  movzx   eax, byte ptr [r10+1]
0x18001b14f  shl     edx, 8
0x18001b152  add     edx, eax
0x18001b154  jmp     short loc_18001B15B
0x18001b156  mov     edx, 0FFFFh
0x18001b15b  movsx   eax, r9b
0x18001b15f  mov     ecx, 10h
0x18001b164  sub     ecx, eax
0x18001b166  add     r9b, 10h
0x18001b16a  shl     edx, cl
0x18001b16c  xor     eax, eax
0x18001b16e  add     r8d, edx
0x18001b171  dec     edi
0x18001b173  cmp     r11d, 680h
0x18001b17a  cmovge  r11d, eax
0x18001b17e  mov     eax, r8d
0x18001b181  shr     rax, 16h
0x18001b185  movsx   edx, rva VLDecodeTableRoot[rbx+rax*2]
0x18001b18d  mov     ecx, edx
0x18001b18f  and     ecx, 0Fh
0x18001b192  jnz     loc_18001B220
0x18001b198  test    edx, edx
0x18001b19a  jg      loc_18001B2AF
0x18001b1a0  jz      short loc_18001B208
0x18001b1a2  add     r9b, 0F0h
0x18001b1a6  js      loc_18001B272
0x18001b1ac  mov     edx, r8d
0x18001b1af  movsxd  rcx, r11d
0x18001b1b2  shr     edx, 0Fh
0x18001b1b5  and     edx, 3FCh
0x18001b1bb  movzx   ebx, rva nzigtable[rbx+rcx*2]
0x18001b1c3  bt      r8d, 10h
0x18001b1c8  jnb     short loc_18001B1CC
0x18001b1ca  neg     edx
0x18001b1cc  lea     r12, cs:180000000h
0x18001b1d3  shl     r8d, 10h
0x18001b1d7  mov     cl, rva byte_180022A61[r12+rcx*2]
0x18001b1df  mov     rax, rbx
0x18001b1e2  mov     r12, [rsp+4C0h+var_478]
0x18001b1e7  inc     r11d
0x18001b1ea  shl     edx, cl
0x18001b1ec  mov     rcx, [rsp+4C0h+var_4A0]
0x18001b1f1  mov     [rcx+rbx*4], edx
0x18001b1f4  and     bl, 7
0x18001b1f7  mov     rcx, [rsp+4C0h+var_498]
0x18001b1fc  shr     rax, 3
0x18001b200  mov     [rax+rcx], bl
0x18001b203  jmp     loc_18001B11A
0x18001b208  mov     eax, r8d
0x18001b20b  shr     eax, 13h
0x18001b20e  sub     eax, 1F00h
0x18001b213  movsx   edx, rva VLDecodeTableExtra[rbx+rax*2]
0x18001b21b  mov     ecx, edx
0x18001b21d  and     ecx, 0Fh
0x18001b220  sub     r9b, cl
0x18001b223  js      short loc_18001B277
0x18001b225  sar     edx, 4
0x18001b228  mov     eax, edx
0x18001b22a  shl     r8d, cl
0x18001b22d  and     edx, 3Fh
0x18001b230  sar     eax, 4
0x18001b233  add     r11d, edx
0x18001b236  cmp     al, 3
0x18001b238  jbe     loc_18001B121
0x18001b23e  movsxd  rcx, r11d
0x18001b241  inc     r11d
0x18001b244  movzx   edx, rva nzigtable[rbx+rcx*2]
0x18001b24c  mov     cl, rva byte_180022A61[rbx+rcx*2]
0x18001b253  shl     eax, cl
0x18001b255  mov     rcx, [rsp+4C0h+var_4A0]
0x18001b25a  mov     [rcx+rdx*4], eax
0x18001b25d  mov     al, dl
0x18001b25f  mov     rcx, [rsp+4C0h+var_498]
0x18001b264  and     al, 7
0x18001b266  shr     rdx, 3
0x18001b26a  mov     [rdx+rcx], al
0x18001b26d  jmp     loc_18001B121
0x18001b272  mov     ecx, 10h
0x18001b277  add     r9b, cl
0x18001b27a  mov     rbx, [rsp+4C0h+var_490]
0x18001b27f  mov     rax, [rsp+4C0h+var_4A0]
0x18001b284  mov     rcx, [rsp+4C0h+var_498]
0x18001b289  mov     [r14], rbx
0x18001b28c  add     r14, 8
0x18001b290  mov     [rbx+10h], r8d
0x18001b294  mov     [rbx+16h], r9b
0x18001b298  mov     [rbx+14h], r11w
0x18001b29d  mov     [rbx], rax
0x18001b2a0  mov     [rbx+8], rcx
0x18001b2a4  add     rbx, 18h
0x18001b2a8  mov     [rsp+4C0h+var_490], rbx
0x18001b2ad  jmp     short loc_18001B321
0x18001b2af  cmp     r9b, 4
0x18001b2b3  jl      short loc_18001B27A
0x18001b2b5  shl     r8d, 4
0x18001b2b9  sub     r9b, 4
0x18001b2bd  cmp     r9b, 10h
0x18001b2c1  jle     short loc_18001B2E2
0x18001b2c3  sub     r9b, 10h
0x18001b2c7  mov     ecx, 20h ; ' '
0x18001b2cc  movsx   eax, r9b
0x18001b2d0  sub     r10, 2
0x18001b2d4  sub     ecx, eax
0x18001b2d6  inc     edi
0x18001b2d8  or      eax, 0FFFFFFFFh
0x18001b2db  shl     eax, cl
0x18001b2dd  and     eax, r8d
0x18001b2e0  jmp     short loc_18001B2E5
0x18001b2e2  mov     eax, r8d
0x18001b2e5  test    r9b, r9b
0x18001b2e8  jnz     short loc_18001B2EE
0x18001b2ea  test    edi, edi
0x18001b2ec  jz      short loc_18001B312
0x18001b2ee  mov     rbx, [rsp+4C0h+var_490]
0x18001b2f3  mov     [r15], rbx
0x18001b2f6  sub     r15, 8
0x18001b2fa  mov     [rbx+0Ch], eax
0x18001b2fd  mov     [rbx+10h], r9b
0x18001b301  mov     [rbx+8], edi
0x18001b304  mov     [rbx], r10
0x18001b307  add     rbx, 18h
0x18001b30b  mov     [rsp+4C0h+var_490], rbx
0x18001b310  jmp     short loc_18001B317
0x18001b312  mov     rbx, [rsp+4C0h+var_490]
0x18001b317  mov     rcx, [rsp+4C0h+var_498]
0x18001b31c  mov     rax, [rsp+4C0h+var_4A0]
0x18001b321  add     rcx, 8
0x18001b325  lea     r11, cs:180000000h
0x18001b32c  add     rax, 100h
0x18001b332  mov     [rsp+4C0h+var_498], rcx
0x18001b337  inc     esi
0x18001b339  mov     [rsp+4C0h+var_4A0], rax
0x18001b33e  cmp     esi, 6
0x18001b341  jl      loc_18001B071
0x18001b347  cmp     dword ptr [rsp+4C0h+var_488], 0
0x18001b34c  mov     [rsp+4C0h+var_490], rbx
0x18001b351  jnz     loc_18001B5D3
0x18001b357  mov     qword ptr [r14], 0
0x18001b35e  lea     rsi, [rsp+4C0h+var_450]
0x18001b363  mov     qword ptr [r15], 0
0x18001b36a  lea     r11, [rbp+3C0h+var_418]
0x18001b36e  mov     r10, [rsp+4C0h+var_450]
0x18001b373  jmp     loc_18001B520
0x18001b378  mov     rdi, [r11]
0x18001b37b  test    rdi, rdi
0x18001b37e  jz      loc_18001B529
0x18001b384  mov     cl, [r10+16h]
0x18001b388  mov     r9d, [rdi+0Ch]
0x18001b38c  mov     r8b, cl
0x18001b38f  add     r8b, [rdi+10h]
0x18001b393  mov     rbx, [r10+8]
0x18001b397  mov     r13, [r10]
0x18001b39a  mov     r15, [rdi]
0x18001b39d  movzx   r14d, word ptr [r10+14h]
0x18001b3a2  mov     r12d, [rdi+8]
0x18001b3a6  shr     r9d, cl
0x18001b3a9  add     r9d, [r10+10h]
0x18001b3ad  mov     [rsp+4C0h+var_488], rbx
0x18001b3b2  lea     rbx, cs:180000000h
0x18001b3b9  cmp     r8b, 10h
0x18001b3bd  jge     short loc_18001B419
0x18001b3bf  test    r12d, r12d
0x18001b3c2  jle     short loc_18001B419
0x18001b3c4  mov     rax, [rsp+4C0h+var_478]
0x18001b3c9  add     r15, 2
0x18001b3cd  cmp     r15, [rax]
0x18001b3d0  jb      short loc_18001B3F0
0x18001b3d2  mov     rcx, r15
  ... truncated ...
```
