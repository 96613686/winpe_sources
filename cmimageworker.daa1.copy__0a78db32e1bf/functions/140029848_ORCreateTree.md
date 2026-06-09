# ORCreateTree

- ea: `0x140029848`
- end: `0x140029fde`
- name: `ORCreateTree`
- size: `1942`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022fe0`
- `0x1400234b0`

## callees

- `0x1400029c6`
- `0x1400029d2`
- `0x140002b2c`
- `0x140023b78`
- `0x140026cac`
- `0x140026fa8`
- `0x140027088`
- `0x1400272d0`
- `0x140027348`
- `0x140028e6c`
- `0x140029020`
- `0x140029848`
- `0x140029fe4`
- `0x14002a1ac`

## pseudocode

```c
__int64 __fastcall ORCreateTree(_QWORD *a1)
{
  __int64 v2; // r12
  unsigned int v3; // ebx
  __int64 v4; // r14
  __int64 v5; // r10
  int v6; // esi
  int v7; // r11d
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // r10
  char v10; // al
  int v11; // r11d
  int v12; // r11d
  int *v14; // rax
  int *v15; // rbx
  __int64 v16; // rax
  __int64 v17; // r11
  __int64 v18; // r15
  __int64 v19; // rax
  _DWORD *v20; // rsi
  __int64 v21; // rcx
  int *v22; // rax
  int *v23; // rax
  int *v24; // rcx
  _QWORD *v25; // rax
  _QWORD *v26; // rdx
  _QWORD *v27; // rax
  unsigned int v28; // eax
  __int64 v29; // r13
  int *v30; // rax
  int *v31; // r12
  __int64 v32; // rsi
  _QWORD *v33; // rbx
  __int64 v34; // rax
  _QWORD *v35; // rax
  __int64 v36; // rcx
  unsigned int v37; // r8d
  int *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rsi
  size_t v41; // r12
  __int64 *v42; // rax
  __int64 *v43; // r14
  int *v44; // rax
  __int64 v45; // r11
  int *v46; // r10
  __int64 i; // r8
  int *v48; // rax
  __int64 v49; // r8
  int *v50; // rax
  unsigned int v51; // r13d
  void *v52; // rax
  _QWORD *v53; // r12
  __int64 v54; // rax
  __int64 v55; // r9
  __int64 v56; // rsi
  __int64 v57; // rax
  __int64 v58; // r8
  __int16 v59; // ax
  __int64 v60; // rbx
  __int64 j; // r11
  __int64 v62; // rax
  __int64 v63; // r10
  int v64; // r11d
  unsigned __int64 v65; // rbx
  unsigned __int64 v66; // r11
  __int64 k; // r14
  __int64 v68; // rax
  __int64 v69; // r10
  __int64 v70; // r11
  __int64 v71; // r11
  __int64 m; // r10
  __int64 v73; // rax
  __int64 v74; // r10
  __int64 v75; // rbx
  unsigned __int64 v76; // r8
  __int64 v77; // rax
  __int64 v78; // r10
  __int64 v79; // r8
  unsigned __int64 v80; // r11
  __int64 v81; // rsi
  int *v82; // rcx
  __int64 v83; // rax
  _QWORD *v84; // rbx
  __int64 v85; // rdx
  _QWORD *v86; // rax
  void *v87; // [rsp+20h] [rbp-38h] BYREF
  int *v88; // [rsp+28h] [rbp-30h]
  _DWORD *v89; // [rsp+30h] [rbp-28h]
  _OWORD v90[2]; // [rsp+38h] [rbp-20h] BYREF
  int v91; // [rsp+A0h] [rbp+48h]
  unsigned int v92; // [rsp+A8h] [rbp+50h]
  __int64 v93; // [rsp+B0h] [rbp+58h]
  __int64 v94; // [rsp+B8h] [rbp+60h]

  v87 = 0;
  BinCount = 0;
  v2 = 0;
  BinLength = 0;
  v90[0] = 0;
  if ( !a1 )
  {
    v3 = 87;
    goto LABEL_9;
  }
  if ( !(unsigned __int8)ORValidateBaseBlock(a1) )
    goto LABEL_8;
  v4 = a1[2];
  v94 = v4;
  if ( !(unsigned __int8)ORValidateBinHeader(v4 + 4096, a1) )
    goto LABEL_8;
  v6 = 1;
  v7 = *(_DWORD *)(v5 + 8);
  v8 = v4 + *(unsigned int *)(v4 + 40);
  BinCount = 1;
  BinLength = v7;
  while ( 1 )
  {
    v9 = *(unsigned int *)(v5 + 8) + v5;
    if ( v9 > v8 )
      break;
    v10 = ORValidateBinHeader(v9, a1);
    v12 = *(_DWORD *)(v5 + 8) + v11;
    BinCount = ++v6;
    BinLength = v12;
    if ( !v10 )
      goto LABEL_8;
  }
  v14 = (int *)ORConvertOffsetToAbsolute(*(unsigned int *)(v4 + 36), v4);
  v15 = v14;
  if ( !v14 || *v14 > 0 )
    goto LABEL_8;
  v16 = ORAllocNode(a1, 0);
  v93 = v16;
  v2 = v16;
  if ( !v16 )
  {
    v3 = 8;
    goto LABEL_9;
  }
  a1[7] = v16;
  *(_QWORD *)(v16 + 40) = v15 + 1;
  if ( !(unsigned __int8)ORIsKeyNodeValid(v15) )
    goto LABEL_8;
  *(_WORD *)(v2 + 34) = *(_WORD *)(v17 + 2) & 0x380;
  *(_WORD *)(v2 + 36) = ((unsigned int)v15[14] >> 20) & 0xE;
  *((_WORD *)v15 + 3) &= 0xFC7Fu;
  *(_DWORD *)(*(_QWORD *)(v2 + 40) + 52LL) &= 0xFF1FFFFF;
  *(_QWORD *)v2 = v90;
  *(_QWORD *)(v2 + 8) = v90;
  *(_QWORD *)&v90[0] = v2;
  *((_QWORD *)&v90[0] + 1) = v2;
  while ( 1 )
  {
    v18 = *(_QWORD *)&v90[0];
    if ( *(_OWORD **)&v90[0] == v90 )
      break;
    if ( *(_OWORD **)(*(_QWORD *)&v90[0] + 8LL) != v90
      || (v19 = **(_QWORD **)&v90[0], *(_QWORD *)(**(_QWORD **)&v90[0] + 8LL) != *(_QWORD *)&v90[0]) )
    {
LABEL_110:
      __fastfail(3u);
    }
    *(_QWORD *)&v90[0] = **(_QWORD **)&v90[0];
    *(_QWORD *)(v19 + 8) = v90;
    v20 = *(_DWORD **)(v18 + 40);
    *(_DWORD *)(v18 + 28) = 29806;
    *(_QWORD *)(v18 + 16) = a1;
    v89 = v20;
    v21 = (unsigned int)v20[12];
    if ( (_DWORD)v21 != -1 )
    {
      v22 = (int *)ORConvertOffsetToAbsolute(v21, v4);
      if ( !v22 || *v22 > 0 )
        goto LABEL_8;
      *(_QWORD *)(v18 + 120) = v22 + 1;
    }
    if ( v18 == v2 )
    {
      v3 = ORCreateSecurityDescriptorsList((__int64)a1, (__int64)v20);
      if ( v3 )
        goto LABEL_9;
    }
    v23 = (int *)ORConvertOffsetToAbsolute((unsigned int)v20[11], a1[2]);
    if ( v23 && *v23 <= 0 )
    {
      v24 = v23 + 1;
      v25 = (_QWORD *)a1[8];
      do
      {
        v26 = v25;
        if ( v24 == (int *)v25[2] )
          break;
        v25 = (_QWORD *)*v25;
      }
      while ( v25 != a1 + 8 );
      v27 = 0;
      if ( v24 == (int *)v26[2] )
        v27 = v26;
    }
    else
    {
      v27 = 0;
    }
    *(_QWORD *)(v18 + 96) = v27;
    if ( !v27 )
      goto LABEL_8;
    v28 = v20[9];
    v29 = v18 + 128;
    *(_QWORD *)(v18 + 136) = v18 + 128;
    *(_QWORD *)(v18 + 128) = v18 + 128;
    v92 = v28;
    if ( v28 )
    {
      v30 = (int *)ORConvertOffsetToAbsolute((unsigned int)v20[10], v4);
      v88 = v30;
      v31 = v30;
      if ( v30 && *v30 <= 0 )
      {
        v32 = 0;
        v91 = 0;
        while ( 1 )
        {
          v33 = o__aligned_malloc_0(0x30u, 0x10u);
          if ( !v33 )
            goto LABEL_109;
          v34 = ORConvertOffsetToAbsolute((unsigned int)v31[v32 + 1], v4);
          v33[2] = v34;
          v33[4] = 0;
          v33[5] = 0;
          v33[3] = v34 + 4;
          if ( !v34
            || *(int *)v34 > 0
            || (unsigned int)*(unsigned __int16 *)(v34 + 6) + 20 > -*(_DWORD *)v34
            || *(_WORD *)(v34 + 4) != 27510
            || !*(_DWORD *)(v34 + 8) && *(_DWORD *)(v34 + 12) != -1 )
          {
            aligned_free(v33);
            break;
          }
          v35 = *(_QWORD **)(v18 + 136);
          if ( *v35 != v29 )
            goto LABEL_110;
          *v33 = v29;
          v33[1] = v35;
          *v35 = v33;
          *(_QWORD *)(v18 + 136) = v33;
          v36 = v33[3];
          v37 = *(_DWORD *)(v36 + 4);
          if ( v37 )
          {
            if ( v37 >= 0x80000000 )
            {
              v38 = (int *)(v36 + 8);
LABEL_71:
              v33[5] = v38;
              goto LABEL_72;
            }
            if ( (unsigned int)(*(_DWORD *)(a1[2] + 24LL) - 4096 + (*(_DWORD *)(a1[2] + 20LL) << 12)) < 4
              || v37 <= 0x3FD8 )
            {
              v50 = (int *)ORConvertOffsetToAbsolute(*(unsigned int *)(v36 + 8), v4);
              if ( !v50 || *v50 > 0 )
                break;
              v38 = v50 + 1;
              goto LABEL_71;
            }
            v39 = ORConvertOffsetToAbsolute(*(unsigned int *)(v36 + 8), v4);
            if ( !v39 )
              break;
            if ( *(int *)v39 > 0 )
              break;
            v40 = v39 + 4;
            if ( *(_WORD *)(v39 + 4) != 25188 || !*(_WORD *)(v39 + 6) || *(_DWORD *)(v39 + 8) == -1 )
              break;
            v41 = 8LL * *(unsigned __int16 *)(v39 + 6) + 8;
            v42 = (__int64 *)o__aligned_malloc_0(v41, 0x10u);
            v43 = v42;
            if ( !v42 )
              goto LABEL_109;
            memset_0(v42, 0, v41);
            *v43 = v40;
            v44 = (int *)ORConvertOffsetToAbsolute(*(unsigned int *)(v40 + 4), v94);
            v46 = v44;
            if ( !v44 || *v44 > 0 )
              break;
            for ( i = 0; (unsigned int)i < *(unsigned __int16 *)(v40 + 2); i = (unsigned int)(v49 + 1) )
            {
              v48 = (int *)ORConvertOffsetToAbsolute((unsigned int)v46[i + 1], v45);
              if ( !v48 || *v48 > 0 )
                goto LABEL_108;
              v43[v49 + 1] = (__int64)v48;
            }
            LODWORD(v32) = v91;
            v31 = v88;
            v33[4] = v43;
            v4 = v45;
          }
          else
          {
            v33[5] = 0;
          }
LABEL_72:
          v32 = (unsigned int)(v32 + 1);
          v91 = v32;
          if ( (unsigned int)v32 >= v92 )
          {
            v20 = v89;
            goto LABEL_74;
          }
        }
      }
LABEL_108:
      v2 = v93;
LABEL_8:
      v3 = 1017;
      goto LABEL_9;
    }
LABEL_74:
    v51 = v20[5];
    if ( v51 )
    {
      ORFreeOrNop(a1, &v87);
      v52 = o__aligned_malloc_0(8LL * v51, 0x10u);
      v87 = v52;
      v53 = v52;
      if ( !v52 )
      {
LABEL_109:
        v2 = v93;
        v3 = 8;
        goto LABEL_9;
      }
      memset_0(v52, 0, 8LL * v51);
      v54 = ORConvertOffsetToAbsolute((unsigned int)v20[7], v4);
      v55 = v54;
      if ( !v54 || *(int *)v54 > 0 )
        goto LABEL_108;
      if ( *(_WORD *)(v54 + 4) == 26994 )
      {
        v56 = 0;
        if ( *(_WORD *)(v54 + 6) )
        {
          do
          {
            v57 = ORConvertOffsetToAbsolute(*(unsigned int *)(v55 + 4 * v56 + 8), v4);
            v58 = v57;
            if ( !v57 || *(int *)v57 > 0 )
              goto LABEL_108;
            v59 = *(_WORD *)(v57 + 4);
            if ( v59 == 26988 )
            {
              v60 = a1[2];
              for ( j = 0; (unsigned int)j < *(unsigned __int16 *)(v58 + 6); j = (unsigned int)(v64 + 1) )
              {
                v62 = ORConvertOffsetToAbsolute(*(unsigned int *)(v58 + 4 * j + 8), v60);
                v53[v63] = v62;
              }
            }
            else if ( ((v59 - 26220) & 0xFDFF) == 0 )
            {
              v65 = *(unsigned __int16 *)(v58 + 6);
              v66 = 0;
              for ( k = a1[2]; v66 < v65; v66 = v70 + 1 )
              {
                v68 = ORConvertOffsetToAbsolute(*(unsigned int *)(v58 + 8 * v66 + 8), k);
                v53[v69] = v68;
              }
              v4 = v94;
            }
            v56 = (unsigned int)(v56 + 1);
          }
          while ( (unsigned int)v56 < *(unsigned __int16 *)(v55 + 6) );
        }
      }
      if ( ((*(_WORD *)(v55 + 4) - 26220) & 0xFDFF) != 0 )
      {
        if ( *(_WORD *)(v55 + 4) == 26988 )
        {
          v71 = a1[2];
          for ( m = 0; (unsigned int)m < *(unsigned __int16 *)(v55 + 6); m = (unsigned int)(v74 + 1) )
          {
            v73 = ORConvertOffsetToAbsolute(*(unsigned int *)(v55 + 4 * m + 8), v71);
            v53[v74] = v73;
          }
        }
      }
      else
      {
        v75 = a1[2];
        v76 = 0;
        if ( *(_WORD *)(v55 + 6) )
        {
          do
          {
            v77 = ORConvertOffsetToAbsolute(*(unsigned int *)(v55 + 8 * v76 + 8), v75);
            v53[v78] = v77;
            v76 = v79 + 1;
          }
          while ( v76 < v80 );
        }
      }
      v81 = 0;
      do
      {
        v82 = (int *)v53[v81];
        if ( !v82 || *v82 > 0 || !(unsigned __int8)ORIsKeyNodeValid(v82) )
          goto LABEL_108;
        v83 = ORAllocNode(a1, v18);
        v84 = (_QWORD *)v83;
        if ( !v83 )
          goto LABEL_109;
        *(_QWORD *)(v83 + 160) = v53[v81];
        v85 = v53[v81] + 4LL;
        *(_QWORD *)(v83 + 40) = v85;
        *(_WORD *)(v83 + 34) = *(_WORD *)(v85 + 2) & 0x380;
        *(_WORD *)(v83 + 36) = (*(_DWORD *)(v85 + 52) >> 20) & 0xE;
        *(_WORD *)(v85 + 2) &= 0xFC7Fu;
        *(_DWORD *)(*(_QWORD *)(v83 + 40) + 52LL) &= 0xFF1FFFFF;
        ORInsertTreeNodeIntoSubkeyList(v18, v83);
        v86 = (_QWORD *)*((_QWORD *)&v90[0] + 1);
        if ( **((_OWORD ***)&v90[0] + 1) != v90 )
          goto LABEL_110;
        v84[1] = *((_QWORD *)&v90[0] + 1);
        *v84 = v90;
        v81 = (unsigned int)(v81 + 1);
        *v86 = v84;
        *((_QWORD *)&v90[0] + 1) = v84;
      }
      while ( (unsigned int)v81 < v51 );
      v4 = v94;
    }
    v2 = v93;
  }
  v3 = 0;
LABEL_9:
  ORFreeOrNop(a1, &v87);
  if ( v3 )
  {
    ORFreeTree(v2);
    a1[7] = 0;
    ORFreeSecurityCellList(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x140029848  push    rbp
0x14002984a  push    rbx
0x14002984b  push    rsi
0x14002984c  push    rdi
0x14002984d  push    r12
0x14002984f  push    r13
0x140029851  push    r14
0x140029853  push    r15
0x140029855  mov     rbp, rsp
0x140029858  sub     rsp, 58h
0x14002985c  xor     r11d, r11d
0x14002985f  xorps   xmm0, xmm0
0x140029862  mov     [rbp+var_38], r11
0x140029866  mov     rdi, rcx
0x140029869  mov     cs:BinCount, r11d
0x140029870  mov     r12d, r11d
0x140029873  mov     cs:BinLength, r11d
0x14002987a  movups  [rbp+var_20], xmm0
0x14002987e  test    rcx, rcx
0x140029881  jnz     short loc_140029888
0x140029883  lea     ebx, [rcx+57h]
0x140029886  jmp     short loc_140029903
0x140029888  call    ORValidateBaseBlock
0x14002988d  test    al, al
0x14002988f  jz      short loc_1400298FE
0x140029891  mov     r14, [rdi+10h]
0x140029895  mov     rdx, rdi
0x140029898  mov     [rbp+arg_18], r14
0x14002989c  lea     r10, [r14+1000h]
0x1400298a3  mov     rcx, r10
0x1400298a6  call    ORValidateBinHeader
0x1400298ab  test    al, al
0x1400298ad  jz      short loc_1400298FE
0x1400298af  mov     ebx, [r14+28h]
0x1400298b3  mov     esi, 1
0x1400298b8  mov     r11d, [r10+8]
0x1400298bc  add     rbx, r14
0x1400298bf  mov     cs:BinCount, 1
0x1400298c9  mov     cs:BinLength, r11d
0x1400298d0  mov     eax, [r10+8]
0x1400298d4  add     r10, rax
0x1400298d7  cmp     r10, rbx
0x1400298da  ja      short loc_14002993F
0x1400298dc  mov     rdx, rdi
0x1400298df  mov     rcx, r10
0x1400298e2  call    ORValidateBinHeader
0x1400298e7  add     r11d, [r10+8]
0x1400298eb  inc     esi
0x1400298ed  mov     cs:BinCount, esi
0x1400298f3  mov     cs:BinLength, r11d
0x1400298fa  test    al, al
0x1400298fc  jnz     short loc_1400298D0
0x1400298fe  mov     ebx, 3F9h
0x140029903  lea     rdx, [rbp+var_38]
0x140029907  mov     rcx, rdi
0x14002990a  call    ORFreeOrNop
0x14002990f  test    ebx, ebx
0x140029911  jz      short loc_14002992B
0x140029913  mov     rcx, r12
0x140029916  call    ORFreeTree
0x14002991b  mov     rcx, rdi
0x14002991e  mov     qword ptr [rdi+38h], 0
0x140029926  call    ORFreeSecurityCellList
0x14002992b  mov     eax, ebx
0x14002992d  add     rsp, 58h
0x140029931  pop     r15
0x140029933  pop     r14
0x140029935  pop     r13
0x140029937  pop     r12
0x140029939  pop     rdi
0x14002993a  pop     rsi
0x14002993b  pop     rbx
0x14002993c  pop     rbp
0x14002993d  retn
0x14002993f  mov     ecx, [r14+24h]
0x140029943  mov     rdx, r14
0x140029946  call    ORConvertOffsetToAbsolute
0x14002994b  mov     rbx, rax
0x14002994e  test    rax, rax
0x140029951  jz      short loc_1400298FE
0x140029953  cmp     [rax], r12d
0x140029956  jg      short loc_1400298FE
0x140029958  xor     edx, edx
0x14002995a  mov     rcx, rdi
0x14002995d  call    ORAllocNode
0x140029962  mov     [rbp+arg_10], rax
0x140029966  mov     r12, rax
0x140029969  test    rax, rax
0x14002996c  jnz     short loc_140029973
0x14002996e  lea     ebx, [rax+8]
0x140029971  jmp     short loc_140029903
0x140029973  mov     [rdi+38h], r12
0x140029977  lea     r11, [rbx+4]
0x14002997b  mov     rcx, rbx
0x14002997e  mov     [rax+28h], r11
0x140029982  call    ORIsKeyNodeValid
0x140029987  test    al, al
0x140029989  jz      loc_1400298FE
0x14002998f  movzx   eax, word ptr [r11+2]
0x140029994  mov     ecx, 380h
0x140029999  and     ax, cx
0x14002999c  mov     [r12+22h], ax
0x1400299a2  mov     eax, [rbx+38h]
0x1400299a5  shr     eax, 14h
0x1400299a8  and     ax, 0Eh
0x1400299ac  mov     [r12+24h], ax
0x1400299b2  mov     eax, 0FC7Fh
0x1400299b7  and     [rbx+6], ax
0x1400299bb  mov     rax, [r12+28h]
0x1400299c0  and     dword ptr [rax+34h], 0FF1FFFFFh
0x1400299c7  lea     rax, [rbp+var_20]
0x1400299cb  mov     [r12], rax
0x1400299cf  lea     rax, [rbp+var_20]
0x1400299d3  mov     [r12+8], rax
0x1400299d8  mov     qword ptr [rbp+var_20], r12
0x1400299dc  mov     qword ptr [rbp+var_20+8], r12
0x1400299e0  mov     r15, qword ptr [rbp+var_20]
0x1400299e4  lea     rax, [rbp+var_20]
0x1400299e8  cmp     r15, rax
0x1400299eb  jz      loc_140029FD7
0x1400299f1  lea     rax, [rbp+var_20]
0x1400299f5  cmp     [r15+8], rax
0x1400299f9  jnz     loc_140029FD0
0x1400299ff  mov     rax, [r15]
0x140029a02  cmp     [rax+8], r15
0x140029a06  jnz     loc_140029FD0
0x140029a0c  mov     qword ptr [rbp+var_20], rax
0x140029a10  lea     rcx, [rbp+var_20]
0x140029a14  mov     [rax+8], rcx
0x140029a18  mov     rsi, [r15+28h]
0x140029a1c  mov     dword ptr [r15+1Ch], 746Eh
0x140029a24  mov     [r15+10h], rdi
0x140029a28  mov     [rbp+var_28], rsi
0x140029a2c  mov     ecx, [rsi+30h]
0x140029a2f  cmp     ecx, 0FFFFFFFFh
0x140029a32  jz      short loc_140029A56
0x140029a34  mov     rdx, r14
0x140029a37  call    ORConvertOffsetToAbsolute
0x140029a3c  test    rax, rax
0x140029a3f  jz      loc_1400298FE
0x140029a45  cmp     dword ptr [rax], 0
0x140029a48  jg      loc_1400298FE
0x140029a4e  add     rax, 4
0x140029a52  mov     [r15+78h], rax
0x140029a56  cmp     r15, r12
0x140029a59  jnz     short loc_140029A70
0x140029a5b  mov     rdx, rsi
0x140029a5e  mov     rcx, rdi
0x140029a61  call    ORCreateSecurityDescriptorsList
0x140029a66  mov     ebx, eax
0x140029a68  test    eax, eax
0x140029a6a  jnz     loc_140029903
0x140029a70  mov     rdx, [rdi+10h]
0x140029a74  mov     ecx, [rsi+2Ch]
0x140029a77  call    ORConvertOffsetToAbsolute
0x140029a7c  test    rax, rax
0x140029a7f  jz      short loc_140029AB0
0x140029a81  cmp     dword ptr [rax], 0
0x140029a84  jg      short loc_140029AB0
0x140029a86  lea     r8, [rdi+40h]
0x140029a8a  lea     rcx, [rax+4]
0x140029a8e  mov     rax, [r8]
0x140029a91  jmp     short loc_140029A9B
0x140029a93  mov     rax, [rax]
0x140029a96  cmp     rax, r8
0x140029a99  jz      short loc_140029AA4
0x140029a9b  mov     rdx, rax
0x140029a9e  cmp     rcx, [rax+10h]
0x140029aa2  jnz     short loc_140029A93
0x140029aa4  xor     eax, eax
0x140029aa6  cmp     rcx, [rdx+10h]
0x140029aaa  cmovz   rax, rdx
0x140029aae  jmp     short loc_140029AB2
0x140029ab0  xor     eax, eax
0x140029ab2  mov     [r15+60h], rax
0x140029ab6  test    rax, rax
0x140029ab9  jz      loc_1400298FE
0x140029abf  mov     eax, [rsi+24h]
0x140029ac2  lea     r13, [r15+80h]
0x140029ac9  mov     [r15+88h], r13
0x140029ad0  mov     [r13+0], r13
0x140029ad4  mov     [rbp+arg_8], eax
0x140029ad7  test    eax, eax
0x140029ad9  jz      loc_140029D1D
0x140029adf  mov     ecx, [rsi+28h]
0x140029ae2  mov     rdx, r14
0x140029ae5  call    ORConvertOffsetToAbsolute
0x140029aea  mov     [rbp+var_30], rax
0x140029aee  mov     r12, rax
0x140029af1  test    rax, rax
0x140029af4  jz      loc_140029FB9
0x140029afa  cmp     dword ptr [rax], 0
0x140029afd  jg      loc_140029FB9
0x140029b03  xor     esi, esi
0x140029b05  mov     [rbp+arg_0], esi
0x140029b08  mov     edx, 10h; Alignment
0x140029b0d  lea     ecx, [rdx+20h]; Size
0x140029b10  call    _o__aligned_malloc_0
0x140029b15  mov     rbx, rax
0x140029b18  test    rax, rax
0x140029b1b  jz      loc_140029FC2
0x140029b21  mov     ecx, [r12+rsi*4+4]
0x140029b26  mov     rdx, r14
0x140029b29  call    ORConvertOffsetToAbsolute
0x140029b2e  mov     [rbx+10h], rax
0x140029b32  mov     qword ptr [rbx+20h], 0
0x140029b3a  mov     qword ptr [rbx+28h], 0
0x140029b42  lea     rcx, [rax+4]
0x140029b46  mov     [rbx+18h], rcx
0x140029b4a  test    rax, rax
0x140029b4d  jz      loc_140029FB1
0x140029b53  mov     edx, [rax]
0x140029b55  test    edx, edx
0x140029b57  jg      loc_140029FB1
0x140029b5d  movzx   eax, word ptr [rcx+2]
0x140029b61  neg     edx
0x140029b63  add     eax, 14h
0x140029b66  cmp     eax, edx
0x140029b68  ja      loc_140029FB1
0x140029b6e  mov     eax, 6B76h
0x140029b73  cmp     [rcx], ax
0x140029b76  jnz     loc_140029FB1
0x140029b7c  cmp     dword ptr [rcx+4], 0
0x140029b80  jnz     short loc_140029B8C
0x140029b82  cmp     dword ptr [rcx+8], 0FFFFFFFFh
0x140029b86  jnz     loc_140029FB1
0x140029b8c  mov     rax, [r13+8]
0x140029b90  cmp     [rax], r13
0x140029b93  jnz     loc_140029FD0
0x140029b99  mov     [rbx], r13
0x140029b9c  mov     [rbx+8], rax
0x140029ba0  mov     [rax], rbx
0x140029ba3  mov     [r13+8], rbx
0x140029ba7  mov     rcx, [rbx+18h]
0x140029bab  mov     r8d, [rcx+4]
0x140029baf  test    r8d, r8d
0x140029bb2  jnz     short loc_140029BC1
0x140029bb4  mov     qword ptr [rbx+28h], 0
0x140029bbc  jmp     loc_140029D0B
0x140029bc1  cmp     r8d, 80000000h
0x140029bc8  jb      short loc_140029BD3
0x140029bca  lea     rax, [rcx+8]
0x140029bce  jmp     loc_140029D07
0x140029bd3  mov     rax, [rdi+10h]
0x140029bd7  mov     edx, [rax+14h]
0x140029bda  mov     eax, [rax+18h]
0x140029bdd  add     eax, 0FFFFF000h
0x140029be2  shl     edx, 0Ch
0x140029be5  add     edx, eax
0x140029be7  cmp     edx, 4
0x140029bea  jb      loc_140029CE6
0x140029bf0  cmp     r8d, 3FD8h
0x140029bf7  jbe     loc_140029CE6
0x140029bfd  mov     ecx, [rcx+8]
0x140029c00  mov     rdx, r14
0x140029c03  call    ORConvertOffsetToAbsolute
0x140029c08  test    rax, rax
0x140029c0b  jz      loc_140029FB9
0x140029c11  cmp     dword ptr [rax], 0
0x140029c14  jg      loc_140029FB9
0x140029c1a  lea     rsi, [rax+4]
0x140029c1e  mov     eax, 6264h
0x140029c23  cmp     [rsi], ax
0x140029c26  jnz     loc_140029FB9
0x140029c2c  xor     eax, eax
0x140029c2e  cmp     ax, [rsi+2]
0x140029c32  jz      loc_140029FB9
0x140029c38  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x140029c3c  jz      loc_140029FB9
0x140029c42  movzx   eax, word ptr [rsi+2]
0x140029c46  mov     edx, 10h; Alignment
0x140029c4b  lea     r12, ds:8[rax*8]
0x140029c53  mov     rcx, r12; Size
0x140029c56  call    _o__aligned_malloc_0
0x140029c5b  mov     r14, rax
0x140029c5e  test    rax, rax
0x140029c61  jz      loc_140029FC2
0x140029c67  mov     r8, r12; Size
0x140029c6a  xor     edx, edx; Val
0x140029c6c  mov     rcx, rax; void *
0x140029c6f  call    memset_0
0x140029c74  mov     r11, [rbp+arg_18]
0x140029c78  mov     [r14], rsi
0x140029c7b  mov     rdx, r11
0x140029c7e  mov     ecx, [rsi+4]
0x140029c81  call    ORConvertOffsetToAbsolute
0x140029c86  mov     r10, rax
0x140029c89  test    rax, rax
0x140029c8c  jz      loc_140029FB9
0x140029c92  cmp     dword ptr [rax], 0
0x140029c95  jg      loc_140029FB9
0x140029c9b  xor     r8d, r8d
0x140029c9e  xor     ecx, ecx
0x140029ca0  cmp     cx, [rsi+2]
0x140029ca4  jnb     short loc_140029CD6
0x140029ca6  mov     ecx, [r10+r8*4+4]
0x140029cab  mov     rdx, r11
0x140029cae  call    ORConvertOffsetToAbsolute
0x140029cb3  test    rax, rax
0x140029cb6  jz      loc_140029FB9
  ... truncated ...
```
