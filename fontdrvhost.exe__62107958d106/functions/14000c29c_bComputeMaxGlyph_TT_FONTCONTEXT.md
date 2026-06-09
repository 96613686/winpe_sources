# bComputeMaxGlyph(_TT_FONTCONTEXT *)

- ea: `0x14000c29c`
- end: `0x14000cb48`
- name: `?bComputeMaxGlyph@@YAHPEAU_TT_FONTCONTEXT@@@Z`
- size: `2220`
- prototype: `__int64 __fastcall(struct _TT_FONTCONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14000c008`

## callees

- `0x140001384`
- `0x140001890`
- `0x14000c29c`
- `0x14000cf14`
- `0x14000e500`
- `0x14000ff80`
- `0x140049848`
- `0x14004a630`
- `0x14004a674`
- `0x14004a7b0`
- `0x1400521a0`
- `0x1400716f0`
- `0x140075de0`

## pseudocode

```c
__int64 __fastcall bComputeMaxGlyph(struct _TT_FONTCONTEXT *a1)
{
  __int64 v1; // rax
  __int64 v2; // r14
  __int64 v4; // r11
  __int64 v5; // rdx
  unsigned __int8 *v6; // rcx
  __int16 v7; // r8
  int v8; // r9d
  __int16 v9; // ax
  int v10; // r15d
  int v11; // r10d
  int v12; // r12d
  int v13; // ebx
  int v14; // esi
  int v15; // edx
  int v16; // edx
  int v17; // r13d
  int v18; // edx
  int v19; // r15d
  int fixed; // r14d
  int v21; // r9d
  int v22; // r10d
  int v23; // r9d
  int v24; // r10d
  int v25; // r12d
  int v26; // r9d
  int v27; // eax
  int v28; // ecx
  int v29; // ecx
  int v30; // r12d
  int v31; // eax
  unsigned int v32; // r14d
  int v33; // edx
  int v34; // eax
  int v35; // edx
  int v36; // r9d
  int v37; // r11d
  int v38; // r8d
  int v39; // esi
  int v40; // ecx
  int v41; // esi
  int v42; // ecx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // r15d
  int v49; // r13d
  int v50; // r12d
  __int64 v51; // rdx
  int v52; // ebx
  int v53; // r8d
  int v54; // esi
  int v55; // ecx
  int v56; // eax
  int v57; // eax
  int v58; // edx
  __int64 v59; // r9
  int v60; // r8d
  int v61; // ecx
  int v62; // eax
  bool v63; // zf
  char *v64; // rax
  int v65; // eax
  char *v66; // rcx
  __int64 v67; // rcx
  int v68; // ebx
  int v69; // r12d
  __int64 v70; // rcx
  float v71; // xmm2_4
  int v72; // edx
  int v73; // r8d
  float v74; // xmm0_4
  int v75; // eax
  int *v76; // rcx
  int v77; // eax
  __int64 v78; // rcx
  int v79; // eax
  __int64 v80; // rax
  __int64 v81; // rbx
  int v82; // eax
  int v83; // r11d
  signed int v84; // eax
  __int64 v85; // rdx
  int v86; // r9d
  unsigned __int16 v87; // dx
  unsigned int v88; // esi
  int v90; // [rsp+30h] [rbp-99h] BYREF
  int v91; // [rsp+34h] [rbp-95h] BYREF
  int v92; // [rsp+38h] [rbp-91h]
  int v93; // [rsp+3Ch] [rbp-8Dh]
  int v94; // [rsp+40h] [rbp-89h]
  __m128i si128; // [rsp+50h] [rbp-79h] BYREF
  int v96; // [rsp+60h] [rbp-69h]
  int v97; // [rsp+64h] [rbp-65h]
  int v98; // [rsp+68h] [rbp-61h]
  int v99; // [rsp+6Ch] [rbp-5Dh]
  int v100; // [rsp+70h] [rbp-59h]
  int v101; // [rsp+74h] [rbp-55h]
  int v102; // [rsp+78h] [rbp-51h]
  int v103; // [rsp+7Ch] [rbp-4Dh]
  int v104; // [rsp+80h] [rbp-49h]
  int v105; // [rsp+84h] [rbp-45h]
  int v106; // [rsp+88h] [rbp-41h]
  int v107; // [rsp+8Ch] [rbp-3Dh]
  int v108; // [rsp+90h] [rbp-39h] BYREF
  _DWORD v109[8]; // [rsp+94h] [rbp-35h]
  int v110; // [rsp+B4h] [rbp-15h]

  v1 = *((_QWORD *)a1 + 24);
  v2 = *((_QWORD *)a1 + 1);
  v4 = *(unsigned int *)(v1 + 16);
  v5 = *(_QWORD *)(v2 + 64);
  if ( !*(_DWORD *)(v1 + 64) )
  {
    v6 = 0;
LABEL_6:
    v9 = *(unsigned __int8 *)(v4 + v5 + 43);
    v8 = -(*(unsigned __int8 *)(v4 + v5 + 39) | (__int16)(*(unsigned __int8 *)(v4 + v5 + 38) << 8));
    v7 = *(unsigned __int8 *)(v4 + v5 + 42) << 8;
    goto LABEL_7;
  }
  v6 = (unsigned __int8 *)(v5 + *(unsigned int *)(v1 + 64));
  if ( !v6 || (*((_BYTE *)a1 + 116) & 3) == 0 )
    goto LABEL_6;
  v7 = v6[75];
  v8 = v6[77] | (__int16)(v6[76] << 8);
  v9 = v6[74] << 8;
LABEL_7:
  v10 = -(__int16)(v9 | v7);
  if ( v6 )
  {
    v11 = -(v6[69] | (__int16)(v6[68] << 8));
    v12 = -(v6[71] | (__int16)(v6[70] << 8));
  }
  else
  {
    v11 = 0;
    v12 = 0;
  }
  if ( v10 >= v8 )
    return 0;
  v13 = *(unsigned __int8 *)(v4 + v5 + 37) | (__int16)(*(unsigned __int8 *)(v4 + v5 + 36) << 8);
  v14 = *(unsigned __int8 *)(v4 + v5 + 41) | (__int16)(*(unsigned __int8 *)(v4 + v5 + 40) << 8);
  if ( (*((_DWORD *)a1 + 10) & 0x4000) != 0 )
  {
    v13 -= DWRITE_FixMul(v8, 22272);
    v14 -= DWRITE_FixMul(v10, v15);
  }
  if ( v13 >= v14 )
    return 0;
  if ( (-(__int64)(*(_DWORD *)(*(int *)(v2 + 644) + v2 + 444) != 0) & (*(int *)(v2 + 644) + v2 + 512)) != 0 )
  {
    v16 = (v14 - v13) / 2;
    if ( 0x7FFFFFFF - v16 >= v14 )
      v14 += v16;
    else
      v14 = 0x7FFFFFFF;
    if ( (int)(v16 + 0x80000000) <= v13 )
      v13 -= v16;
    else
      v13 = 0x80000000;
  }
  *(_QWORD *)((char *)a1 + 124) = 0;
  *((_DWORD *)a1 + 101) = 0;
  *((_QWORD *)a1 + 17) = 0;
  v17 = *((_DWORD *)a1 + 29);
  if ( (v17 & 9) == 1 )
  {
    v18 = v10;
    v90 = *((_DWORD *)a1 + 20);
    v19 = *((_DWORD *)a1 + 24);
    fixed = DWRITE_FixMul(v19, v18);
    v94 = DWRITE_FixMul(v19, v21);
    DWRITE_FixMul(v19, v22);
    v25 = DWRITE_FixMul(v19, v12);
    if ( v19 <= 0 )
    {
      v29 = v90;
      *((_DWORD *)a1 + 36) = fixed;
      *((_DWORD *)a1 + 37) = -v23;
      v27 = v25;
      *((_DWORD *)a1 + 40) = v23;
      v25 = v24;
      *((_DWORD *)a1 + 41) = fixed;
      v91 = v29;
      v93 = v19;
    }
    else
    {
      v92 = v24;
      vQuantizeXform(a1);
      v17 = *((_DWORD *)a1 + 29);
      if ( (v17 & 4) == 0 )
      {
        *((_DWORD *)a1 + 41) = v94;
        *((_DWORD *)a1 + 40) = fixed;
      }
      v26 = *((_DWORD *)a1 + 40);
      fixed = *((_DWORD *)a1 + 41);
      v27 = v92;
      *((_DWORD *)a1 + 36) = -v26;
      *((_DWORD *)a1 + 37) = fixed;
      v28 = *((_DWORD *)a1 + 24);
      v91 = *((_DWORD *)a1 + 20);
      v93 = v28;
      v94 = v26;
    }
    v30 = v25 - v27;
    v31 = *((_DWORD *)a1 + 31);
    *((_DWORD *)a1 + 102) = v30;
    if ( !v31 )
    {
      v31 = DWRITE_FixMul(v19, *(__int16 *)(*((_QWORD *)a1 + 1) + 496LL));
      *((_DWORD *)a1 + 31) = v31;
      if ( v31 < 0 )
      {
        v31 = -v31;
        *((_DWORD *)a1 + 31) = v31;
      }
    }
    v32 = fixed - v94;
    *((_DWORD *)a1 + 32) = CompDiv(*((unsigned int *)a1 + 12), 72LL * (v31 << 16));
    if ( v91 == v93 && v93 > 0 )
    {
      *((_DWORD *)a1 + 29) = v17 | 0x10;
      vFindHdmxTable(a1);
    }
    DWRITE_FixMul(16 * v13, v90);
    v34 = DWRITE_FixMul(16 * v14, v33);
    if ( v35 >= 0 )
    {
      v38 = v34;
      v34 = v36;
    }
    else
    {
      v38 = v36;
    }
    v39 = ((v38 + 15) >> 4) + 1;
    *((_DWORD *)a1 + 55) = 0;
    *((_DWORD *)a1 + 39) = v39;
    v40 = (v34 >> 4) - 2;
    *((_DWORD *)a1 + 64) = 0;
    v41 = v39 - v40;
    *((_DWORD *)a1 + 38) = v40;
    v42 = -1;
    *((_DWORD *)a1 + 50) = 0;
    v43 = 1;
    if ( v35 <= 0 )
      v43 = -1;
    if ( v19 <= 0 )
      v42 = 1;
    *((float *)a1 + 54) = (float)v43;
    *((float *)a1 + 65) = (float)v42;
    if ( v37 <= 0 || *((int *)a1 + 37) <= 0 )
    {
      v45 = *((_DWORD *)a1 + 37);
      if ( *((int *)a1 + 24) <= 0 )
        v46 = v37 - v45;
      else
        v46 = v45 - v37;
      v44 = v46 >> 1;
    }
    else
    {
      v44 = 0;
    }
    *((_DWORD *)a1 + 51) = v44;
  }
  else
  {
    v47 = *(unsigned __int16 *)(v2 + 396) >> 6;
    v48 = v10 - v47;
    si128.m128i_i64[0] = __PAIR64__(v48, v13);
    si128.m128i_i64[1] = __PAIR64__(v48, v14);
    v49 = v47 + v8;
    v105 = v47 + v12;
    v107 = v47 + v12;
    v96 = v13;
    v97 = v47 + v8;
    v98 = v14;
    v99 = v47 + v8;
    v100 = v13;
    v101 = v11 - v47;
    v102 = v14;
    v103 = v11 - v47;
    v104 = v13;
    v106 = v14;
    if ( !(unsigned int)bFDXform((char *)a1 + 56, &v108, &si128, 8) )
      return 0;
    v50 = v108;
    v51 = 1;
    v52 = v109[0];
    v53 = v108;
    v54 = v109[0];
    do
    {
      v55 = v109[2 * v51 - 1];
      v56 = v55;
      if ( v55 >= v50 )
        v56 = v50;
      v50 = v56;
      v57 = v109[2 * v51];
      if ( v55 <= v53 )
        v55 = v53;
      v53 = v55;
      if ( v57 < v52 )
        v52 = v109[2 * v51];
      if ( v57 > v54 )
        v54 = v109[2 * v51];
      ++v51;
    }
    while ( v51 != 4 );
    v58 = v110;
    v59 = 5;
    v60 = v110;
    v90 = v55;
    do
    {
      v61 = v109[2 * v59];
      v62 = v61;
      if ( v61 >= v58 )
        v62 = v58;
      v58 = v62;
      if ( v61 <= v60 )
        v61 = v60;
      ++v59;
      v60 = v61;
    }
    while ( v59 != 8 );
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffff000000000000000000000001);
    v63 = (*((_DWORD *)a1 + 10) & 0x2000) == 0;
    *((_DWORD *)a1 + 102) = ((v61 + 15) >> 4) - (v62 >> 4);
    v64 = v63 ? 0LL : (char *)a1 + 232;
    v65 = bXformUnitVector(
            (unsigned int)&si128,
            (int)a1 + 56,
            (int)a1 + 208,
            (int)a1 + 216,
            (__int64)v64,
            (__int64)a1 + 224);
    v63 = (*((_DWORD *)a1 + 10) & 0x2000) == 0;
    v92 = v65;
    v66 = v63 ? 0LL : (char *)a1 + 272;
    if ( ((unsigned int)bXformUnitVector(
                          (unsigned int)&si128.m128i_u32[2],
                          (int)a1 + 56,
                          (int)a1 + 248,
                          (int)a1 + 256,
                          (__int64)v66,
                          (__int64)a1 + 264)
        & v92) == 0 )
      return 0;
    v67 = (unsigned int)((v54 + 15) >> 4);
    v68 = v52 >> 4;
    v69 = v50 >> 4;
    v93 = v67;
    v41 = ((v90 + 15) >> 4) - v69;
    v92 = (v90 + 15) >> 4;
    v32 = v67 - v68;
    v91 = 0;
    bFToL(v67, &v91, 0);
    v90 = 0;
    bFToL(v70, &v90, 0);
    v71 = *((float *)a1 + 65);
    v72 = (15 - v91) >> 4;
    v73 = (v90 + 15) >> 4;
    *((_DWORD *)a1 + 36) = v72;
    *((_DWORD *)a1 + 37) = v73;
    *((_DWORD *)a1 + 72) = (int)(float)((float)(16 * v72) * *((float *)a1 + 64));
    *((_DWORD *)a1 + 73) = (int)(float)((float)(16 * v72) * v71);
    v74 = (float)(-16 * v73);
    *((_DWORD *)a1 + 74) = (int)(float)(v74 * *((float *)a1 + 64));
    *((_DWORD *)a1 + 75) = (int)(float)(v74 * v71);
    if ( v48 >= 0 || v49 <= 0 || v73 + v72 < 3 )
    {
      v90 = 0;
      bFToL((char *)a1 + 256, &v90, 0);
      v77 = (v90 >> 3) + 1;
      v90 = 0;
      *((_DWORD *)a1 + 50) = v77 >> 1;
      bFToL(v78, &v90, 0);
      v79 = v90;
      v76 = (int *)((char *)a1 + 204);
      *((_DWORD *)a1 + 51) = v90;
      v75 = ((v79 >> 3) + 1) >> 1;
    }
    else
    {
      v75 = 0;
      *((_DWORD *)a1 + 50) = 0;
      v76 = (int *)((char *)a1 + 204);
    }
    *v76 = v75;
    *((_DWORD *)a1 + 39) = v92;
    *((_DWORD *)a1 + 41) = v93;
    v80 = *((_QWORD *)a1 + 1);
    *((_DWORD *)a1 + 40) = v68;
    *((_DWORD *)a1 + 38) = v69;
    v81 = 72LL * *(unsigned __int16 *)(v80 + 396);
    CompDiv(*((unsigned int *)a1 + 12), v81 * *((int *)a1 + 24));
    v82 = CompDiv(*((unsigned int *)a1 + 11), v81 * *((int *)a1 + 23));
    v84 = iHipot(v82, v83);
    v85 = *((int *)a1 + 12);
    *((_DWORD *)a1 + 32) = v84;
    *((_DWORD *)a1 + 31) = ((unsigned int)CompDiv(72, v84 * v85) + 0x8000) >> 16;
  }
  v86 = *((_DWORD *)a1 + 10);
  if ( (v86 & 0x2000) != 0 )
    v87 = (2 * *((_DWORD *)a1 + 31) - 1) / 100 + 1;
  else
    v87 = 0;
  *((_WORD *)a1 + 200) = v87;
  if ( !v41 || !v32 )
    return 0;
  if ( (v86 & 0x2000) != 0 )
  {
    v41 += v87;
    v32 += v87;
  }
  v88 = (v41 + 7) & 0xFFFFFFF8;
  *((_DWORD *)a1 + 42) = v88;
  if ( v32 * (unsigned __int64)(unsigned int)((int)((v88 + 31) & 0xFFFFFFE0) / 8) > 0xFFFFFFFF )
    return 0;
  if ( (v86 & 0x10000000) != 0 )
    vSetClearTypeState__FONTCONTEXT(a1);
  else
    vSetGrayState__FONTCONTEXT(a1);
  *((_DWORD *)a1 + 30) = 0;
  *((_DWORD *)a1 + 43) = CJGD(v88, v32, a1);
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 1) + 388LL) & 0x40) != 0 && (*((_BYTE *)a1 + 116) & 0x11) == 0x11 )
    *((_DWORD *)a1 + 29) |= 0x40u;
  return 1;
}

```

## disassembly

```asm
0x14000c29c  push    rbp
0x14000c29e  push    rbx
0x14000c29f  push    rsi
0x14000c2a0  push    rdi
0x14000c2a1  push    r12
0x14000c2a3  push    r13
0x14000c2a5  push    r14
0x14000c2a7  push    r15
0x14000c2a9  lea     rbp, [rsp-1Fh]
0x14000c2ae  sub     rsp, 0E8h
0x14000c2b5  mov     rax, cs:__security_cookie
0x14000c2bc  xor     rax, rsp
0x14000c2bf  mov     [rbp+57h+var_50], rax
0x14000c2c3  mov     rax, [rcx+0C0h]
0x14000c2ca  xor     r13d, r13d
0x14000c2cd  mov     r14, [rcx+8]
0x14000c2d1  mov     rdi, rcx
0x14000c2d4  mov     r11d, [rax+10h]
0x14000c2d8  mov     rdx, [r14+40h]
0x14000c2dc  cmp     [rax+40h], r13d
0x14000c2e0  jz      short loc_14000C312
0x14000c2e2  mov     ecx, [rax+40h]
0x14000c2e5  add     rcx, rdx
0x14000c2e8  jz      short loc_14000C315
0x14000c2ea  test    byte ptr [rdi+74h], 3
0x14000c2ee  jz      short loc_14000C315
0x14000c2f0  movzx   eax, byte ptr [rcx+4Ch]
0x14000c2f4  movzx   r8d, byte ptr [rcx+4Bh]
0x14000c2f9  shl     ax, 8
0x14000c2fd  movsx   r9d, ax
0x14000c301  movzx   eax, byte ptr [rcx+4Dh]
0x14000c305  or      r9d, eax
0x14000c308  movzx   eax, byte ptr [rcx+4Ah]
0x14000c30c  shl     ax, 8
0x14000c310  jmp     short loc_14000C340
0x14000c312  mov     rcx, r13
0x14000c315  movzx   eax, byte ptr [r11+rdx+26h]
0x14000c31b  movzx   r8d, byte ptr [r11+rdx+2Ah]
0x14000c321  shl     ax, 8
0x14000c325  movsx   r9d, ax
0x14000c329  movzx   eax, byte ptr [r11+rdx+27h]
0x14000c32f  or      r9d, eax
0x14000c332  movzx   eax, byte ptr [r11+rdx+2Bh]
0x14000c338  neg     r9d
0x14000c33b  shl     r8w, 8
0x14000c340  or      r8w, ax
0x14000c344  movsx   r15d, r8w
0x14000c348  neg     r15d
0x14000c34b  test    rcx, rcx
0x14000c34e  jz      short loc_14000C37E
0x14000c350  movzx   eax, byte ptr [rcx+44h]
0x14000c354  shl     ax, 8
0x14000c358  movsx   r10d, ax
0x14000c35c  movzx   eax, byte ptr [rcx+45h]
0x14000c360  or      r10d, eax
0x14000c363  movzx   eax, byte ptr [rcx+46h]
0x14000c367  shl     ax, 8
0x14000c36b  neg     r10d
0x14000c36e  movsx   r12d, ax
0x14000c372  movzx   eax, byte ptr [rcx+47h]
0x14000c376  or      r12d, eax
0x14000c379  neg     r12d
0x14000c37c  jmp     short loc_14000C384
0x14000c37e  mov     r10d, r13d
0x14000c381  mov     r12d, r13d
0x14000c384  cmp     r15d, r9d
0x14000c387  jge     loc_14000CB26
0x14000c38d  movzx   eax, byte ptr [r11+rdx+24h]
0x14000c393  shl     ax, 8
0x14000c397  movsx   ebx, ax
0x14000c39a  movzx   eax, byte ptr [r11+rdx+25h]
0x14000c3a0  or      ebx, eax
0x14000c3a2  movzx   eax, byte ptr [r11+rdx+28h]
0x14000c3a8  shl     ax, 8
0x14000c3ac  movsx   esi, ax
0x14000c3af  movzx   eax, byte ptr [r11+rdx+29h]
0x14000c3b5  or      esi, eax
0x14000c3b7  test    dword ptr [rdi+28h], 4000h
0x14000c3be  jz      short loc_14000C3D9
0x14000c3c0  mov     edx, 5700h; int
0x14000c3c5  mov     ecx, r9d; int
0x14000c3c8  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c3cd  mov     ecx, r15d; int
0x14000c3d0  sub     ebx, eax
0x14000c3d2  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c3d7  sub     esi, eax
0x14000c3d9  cmp     ebx, esi
0x14000c3db  jge     loc_14000CB26
0x14000c3e1  movsxd  rcx, dword ptr [r14+284h]
0x14000c3e8  lea     rdx, [r14+200h]
0x14000c3ef  add     rdx, rcx
0x14000c3f2  mov     eax, [rcx+r14+1BCh]
0x14000c3fa  neg     eax
0x14000c3fc  sbb     rax, rax
0x14000c3ff  test    rdx, rax
0x14000c402  jz      short loc_14000C435
0x14000c404  mov     eax, esi
0x14000c406  sub     eax, ebx
0x14000c408  cdq
0x14000c409  sub     eax, edx
0x14000c40b  sar     eax, 1
0x14000c40d  mov     edx, eax
0x14000c40f  mov     eax, 7FFFFFFFh
0x14000c414  mov     ecx, eax
0x14000c416  sub     ecx, edx
0x14000c418  cmp     ecx, esi
0x14000c41a  jge     short loc_14000C420
0x14000c41c  mov     esi, eax
0x14000c41e  jmp     short loc_14000C422
0x14000c420  add     esi, edx
0x14000c422  lea     eax, [rdx-80000000h]
0x14000c428  cmp     eax, ebx
0x14000c42a  jle     short loc_14000C433
0x14000c42c  mov     ebx, 80000000h
0x14000c431  jmp     short loc_14000C435
0x14000c433  sub     ebx, edx
0x14000c435  mov     [rdi+7Ch], r13
0x14000c439  mov     [rdi+194h], r13d
0x14000c440  mov     [rdi+88h], r13
0x14000c447  mov     r13d, [rdi+74h]
0x14000c44b  mov     eax, r13d
0x14000c44e  and     al, 9
0x14000c450  cmp     al, 1
0x14000c452  jnz     loc_14000C67F
0x14000c458  mov     eax, [rdi+50h]
0x14000c45b  mov     edx, r15d; int
0x14000c45e  mov     [rsp+120h+var_F0], eax
0x14000c462  mov     eax, [rdi+60h]
0x14000c465  mov     ecx, eax; int
0x14000c467  mov     r15d, eax
0x14000c46a  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c46f  mov     ecx, r15d; int
0x14000c472  mov     edx, r9d; int
0x14000c475  mov     r14d, eax
0x14000c478  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c47d  mov     ecx, r15d; int
0x14000c480  mov     [rsp+120h+var_E0], eax
0x14000c484  mov     edx, r10d; int
0x14000c487  mov     r9d, eax
0x14000c48a  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c48f  mov     ecx, r15d; int
0x14000c492  mov     edx, r12d; int
0x14000c495  mov     r10d, eax
0x14000c498  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c49d  mov     r12d, eax
0x14000c4a0  test    r15d, r15d
0x14000c4a3  jle     short loc_14000C508
0x14000c4a5  mov     rcx, rdi; struct _TT_FONTCONTEXT *
0x14000c4a8  mov     [rsp+120h+var_E8], r10d
0x14000c4ad  call    ?vQuantizeXform@@YAXPEAU_TT_FONTCONTEXT@@@Z; vQuantizeXform(_TT_FONTCONTEXT *)
0x14000c4b2  mov     r13d, [rdi+74h]
0x14000c4b6  test    r13b, 4
0x14000c4ba  jnz     short loc_14000C4CD
0x14000c4bc  mov     eax, [rsp+120h+var_E0]
0x14000c4c0  mov     [rdi+0A4h], eax
0x14000c4c6  mov     [rdi+0A0h], r14d
0x14000c4cd  mov     r9d, [rdi+0A0h]
0x14000c4d4  mov     r11d, r9d
0x14000c4d7  mov     r14d, [rdi+0A4h]
0x14000c4de  neg     r11d
0x14000c4e1  mov     eax, [rsp+120h+var_E8]
0x14000c4e5  mov     [rdi+90h], r11d
0x14000c4ec  mov     [rdi+94h], r14d
0x14000c4f3  mov     edx, [rdi+50h]
0x14000c4f6  mov     ecx, [rdi+60h]
0x14000c4f9  mov     [rsp+120h+var_EC], edx
0x14000c4fd  mov     [rsp+120h+var_E4], ecx
0x14000c501  mov     [rsp+120h+var_E0], r9d
0x14000c506  jmp     short loc_14000C53E
0x14000c508  mov     ecx, [rsp+120h+var_F0]
0x14000c50c  mov     eax, r9d
0x14000c50f  neg     eax
0x14000c511  mov     [rdi+90h], r14d
0x14000c518  mov     [rdi+94h], eax
0x14000c51e  mov     r11d, r14d
0x14000c521  mov     eax, r12d
0x14000c524  mov     [rdi+0A0h], r9d
0x14000c52b  mov     r12d, r10d
0x14000c52e  mov     [rdi+0A4h], r14d
0x14000c535  mov     [rsp+120h+var_EC], ecx
0x14000c539  mov     [rsp+120h+var_E4], r15d
0x14000c53e  sub     r12d, eax
0x14000c541  mov     eax, [rdi+7Ch]
0x14000c544  mov     [rdi+198h], r12d
0x14000c54b  xor     r12d, r12d
0x14000c54e  test    eax, eax
0x14000c550  jnz     short loc_14000C571
0x14000c552  mov     rax, [rdi+8]
0x14000c556  mov     ecx, r15d; int
0x14000c559  movsx   edx, word ptr [rax+1F0h]; int
0x14000c560  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c565  mov     [rdi+7Ch], eax
0x14000c568  test    eax, eax
0x14000c56a  jns     short loc_14000C571
0x14000c56c  neg     eax
0x14000c56e  mov     [rdi+7Ch], eax
0x14000c571  mov     ecx, [rdi+30h]
0x14000c574  shl     eax, 10h
0x14000c577  cdqe
0x14000c579  lea     rdx, [rax+rax*8]
0x14000c57d  shl     rdx, 3
0x14000c581  call    CompDiv
0x14000c586  sub     r14d, [rsp+120h+var_E0]
0x14000c58b  mov     [rdi+80h], eax
0x14000c591  mov     eax, [rsp+120h+var_E4]
0x14000c595  cmp     [rsp+120h+var_EC], eax
0x14000c599  jnz     short loc_14000C5B6
0x14000c59b  test    eax, eax
0x14000c59d  jle     short loc_14000C5B6
0x14000c59f  or      r13d, 10h
0x14000c5a3  mov     rcx, rdi; struct _TT_FONTCONTEXT *
0x14000c5a6  mov     [rdi+74h], r13d
0x14000c5aa  call    ?vFindHdmxTable@@YAXPEAU_TT_FONTCONTEXT@@@Z; vFindHdmxTable(_TT_FONTCONTEXT *)
0x14000c5af  mov     r11d, [rdi+90h]
0x14000c5b6  mov     edx, [rsp+120h+var_F0]; int
0x14000c5ba  shl     ebx, 4
0x14000c5bd  mov     ecx, ebx; int
0x14000c5bf  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c5c4  shl     esi, 4
0x14000c5c7  mov     r9d, eax
0x14000c5ca  mov     ecx, esi; int
0x14000c5cc  call    ?DWRITE_FixMul@@YAHHH@Z; DWRITE_FixMul(int,int)
0x14000c5d1  test    edx, edx
0x14000c5d3  jns     short loc_14000C5DA
0x14000c5d5  mov     r8d, r9d
0x14000c5d8  jmp     short loc_14000C5E0
0x14000c5da  mov     r8d, eax
0x14000c5dd  mov     eax, r9d
0x14000c5e0  sar     eax, 4
0x14000c5e3  lea     esi, [r8+0Fh]
0x14000c5e7  sar     esi, 4
0x14000c5ea  mov     r13d, 1
0x14000c5f0  inc     esi
0x14000c5f2  mov     [rdi+0DCh], r12d
0x14000c5f9  mov     [rdi+9Ch], esi
0x14000c5ff  lea     ecx, [rax-2]
0x14000c602  mov     [rdi+100h], r12d
0x14000c609  sub     esi, ecx
0x14000c60b  mov     [rdi+98h], ecx
0x14000c611  or      ecx, 0FFFFFFFFh
0x14000c614  mov     [rdi+0C8h], r12d
0x14000c61b  test    edx, edx
0x14000c61d  mov     eax, r13d
0x14000c620  cmovle  eax, ecx
0x14000c623  test    r15d, r15d
0x14000c626  cmovle  ecx, r13d
0x14000c62a  movd    xmm0, eax
0x14000c62e  cvtdq2ps xmm0, xmm0
0x14000c631  movss   dword ptr [rdi+0D8h], xmm0
0x14000c639  movd    xmm0, ecx
0x14000c63d  cvtdq2ps xmm0, xmm0
0x14000c640  movss   dword ptr [rdi+104h], xmm0
0x14000c648  test    r11d, r11d
0x14000c64b  jle     short loc_14000C65B
0x14000c64d  cmp     [rdi+94h], r12d
0x14000c654  jle     short loc_14000C65B
0x14000c656  mov     eax, r12d
0x14000c659  jmp     short loc_14000C674
0x14000c65b  mov     eax, [rdi+94h]
0x14000c661  cmp     [rdi+60h], r12d
0x14000c665  jle     short loc_14000C66C
0x14000c667  sub     eax, r11d
0x14000c66a  jmp     short loc_14000C672
0x14000c66c  sub     r11d, eax
0x14000c66f  mov     eax, r11d
0x14000c672  sar     eax, 1
0x14000c674  mov     [rdi+0CCh], eax
0x14000c67a  jmp     loc_14000CA4E
0x14000c67f  movzx   eax, word ptr [r14+18Ch]
0x14000c687  lea     r8, [rbp+57h+var_D0]
0x14000c68b  shr     eax, 6
0x14000c68e  lea     r14, [rdi+38h]
0x14000c692  sub     r15d, eax
0x14000c695  mov     dword ptr [rbp+57h+var_D0], ebx
0x14000c698  sub     r10d, eax
0x14000c69b  mov     dword ptr [rbp+57h+var_D0+4], r15d
0x14000c69f  lea     rdx, [rbp+57h+var_90]
0x14000c6a3  mov     dword ptr [rbp+57h+var_D0+8], esi
0x14000c6a6  lea     ecx, [rax+r12]
0x14000c6aa  mov     dword ptr [rbp+57h+var_D0+0Ch], r15d
0x14000c6ae  lea     r13d, [rax+r9]
0x14000c6b2  mov     [rbp+57h+var_9C], ecx
0x14000c6b5  mov     [rbp+57h+var_94], ecx
0x14000c6b8  mov     r9d, 8
0x14000c6be  mov     rcx, r14
0x14000c6c1  mov     [rbp+57h+var_C0], ebx
0x14000c6c4  mov     [rbp+57h+var_BC], r13d
0x14000c6c8  mov     [rbp+57h+var_B8], esi
0x14000c6cb  mov     [rbp+57h+var_B4], r13d
0x14000c6cf  mov     [rbp+57h+var_B0], ebx
0x14000c6d2  mov     [rbp+57h+var_AC], r10d
0x14000c6d6  mov     [rbp+57h+var_A8], esi
0x14000c6d9  mov     [rbp+57h+var_A4], r10d
0x14000c6dd  mov     [rbp+57h+var_A0], ebx
0x14000c6e0  mov     [rbp+57h+var_98], esi
0x14000c6e3  call    bFDXform
0x14000c6e8  test    eax, eax
0x14000c6ea  jz      loc_14000CB26
0x14000c6f0  mov     r12d, [rbp+57h+var_90]
0x14000c6f4  mov     edx, 1
  ... truncated ...
```
