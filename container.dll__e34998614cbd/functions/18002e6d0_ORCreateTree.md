# ORCreateTree

- ea: `0x18002e6d0`
- end: `0x18002ee66`
- name: `ORCreateTree`
- size: `1942`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e14c`

## callees

- `0x180003542`
- `0x18000354e`
- `0x18000362c`
- `0x18002ccd4`
- `0x18002e6d0`
- `0x18002ee6c`
- `0x18002f034`
- `0x18002f7f8`
- `0x18002f9dc`
- `0x18002fabc`
- `0x18002fc5c`
- `0x18002fcd4`
- `0x18002fd30`
- `0x18002fee4`

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
0x18002e6d0  push    rbp
0x18002e6d2  push    rbx
0x18002e6d3  push    rsi
0x18002e6d4  push    rdi
0x18002e6d5  push    r12
0x18002e6d7  push    r13
0x18002e6d9  push    r14
0x18002e6db  push    r15
0x18002e6dd  mov     rbp, rsp
0x18002e6e0  sub     rsp, 58h
0x18002e6e4  xor     r11d, r11d
0x18002e6e7  xorps   xmm0, xmm0
0x18002e6ea  mov     [rbp+var_38], r11
0x18002e6ee  mov     rdi, rcx
0x18002e6f1  mov     cs:BinCount, r11d
0x18002e6f8  mov     r12d, r11d
0x18002e6fb  mov     cs:BinLength, r11d
0x18002e702  movups  [rbp+var_20], xmm0
0x18002e706  test    rcx, rcx
0x18002e709  jnz     short loc_18002E710
0x18002e70b  lea     ebx, [rcx+57h]
0x18002e70e  jmp     short loc_18002E78B
0x18002e710  call    ORValidateBaseBlock
0x18002e715  test    al, al
0x18002e717  jz      short loc_18002E786
0x18002e719  mov     r14, [rdi+10h]
0x18002e71d  mov     rdx, rdi
0x18002e720  mov     [rbp+arg_18], r14
0x18002e724  lea     r10, [r14+1000h]
0x18002e72b  mov     rcx, r10
0x18002e72e  call    ORValidateBinHeader
0x18002e733  test    al, al
0x18002e735  jz      short loc_18002E786
0x18002e737  mov     ebx, [r14+28h]
0x18002e73b  mov     esi, 1
0x18002e740  mov     r11d, [r10+8]
0x18002e744  add     rbx, r14
0x18002e747  mov     cs:BinCount, 1
0x18002e751  mov     cs:BinLength, r11d
0x18002e758  mov     eax, [r10+8]
0x18002e75c  add     r10, rax
0x18002e75f  cmp     r10, rbx
0x18002e762  ja      short loc_18002E7C7
0x18002e764  mov     rdx, rdi
0x18002e767  mov     rcx, r10
0x18002e76a  call    ORValidateBinHeader
0x18002e76f  add     r11d, [r10+8]
0x18002e773  inc     esi
0x18002e775  mov     cs:BinCount, esi
0x18002e77b  mov     cs:BinLength, r11d
0x18002e782  test    al, al
0x18002e784  jnz     short loc_18002E758
0x18002e786  mov     ebx, 3F9h
0x18002e78b  lea     rdx, [rbp+var_38]
0x18002e78f  mov     rcx, rdi
0x18002e792  call    ORFreeOrNop
0x18002e797  test    ebx, ebx
0x18002e799  jz      short loc_18002E7B3
0x18002e79b  mov     rcx, r12
0x18002e79e  call    ORFreeTree
0x18002e7a3  mov     rcx, rdi
0x18002e7a6  mov     qword ptr [rdi+38h], 0
0x18002e7ae  call    ORFreeSecurityCellList
0x18002e7b3  mov     eax, ebx
0x18002e7b5  add     rsp, 58h
0x18002e7b9  pop     r15
0x18002e7bb  pop     r14
0x18002e7bd  pop     r13
0x18002e7bf  pop     r12
0x18002e7c1  pop     rdi
0x18002e7c2  pop     rsi
0x18002e7c3  pop     rbx
0x18002e7c4  pop     rbp
0x18002e7c5  retn
0x18002e7c7  mov     ecx, [r14+24h]
0x18002e7cb  mov     rdx, r14
0x18002e7ce  call    ORConvertOffsetToAbsolute
0x18002e7d3  mov     rbx, rax
0x18002e7d6  test    rax, rax
0x18002e7d9  jz      short loc_18002E786
0x18002e7db  cmp     [rax], r12d
0x18002e7de  jg      short loc_18002E786
0x18002e7e0  xor     edx, edx
0x18002e7e2  mov     rcx, rdi
0x18002e7e5  call    ORAllocNode
0x18002e7ea  mov     [rbp+arg_10], rax
0x18002e7ee  mov     r12, rax
0x18002e7f1  test    rax, rax
0x18002e7f4  jnz     short loc_18002E7FB
0x18002e7f6  lea     ebx, [rax+8]
0x18002e7f9  jmp     short loc_18002E78B
0x18002e7fb  mov     [rdi+38h], r12
0x18002e7ff  lea     r11, [rbx+4]
0x18002e803  mov     rcx, rbx
0x18002e806  mov     [rax+28h], r11
0x18002e80a  call    ORIsKeyNodeValid
0x18002e80f  test    al, al
0x18002e811  jz      loc_18002E786
0x18002e817  movzx   eax, word ptr [r11+2]
0x18002e81c  mov     ecx, 380h
0x18002e821  and     ax, cx
0x18002e824  mov     [r12+22h], ax
0x18002e82a  mov     eax, [rbx+38h]
0x18002e82d  shr     eax, 14h
0x18002e830  and     ax, 0Eh
0x18002e834  mov     [r12+24h], ax
0x18002e83a  mov     eax, 0FC7Fh
0x18002e83f  and     [rbx+6], ax
0x18002e843  mov     rax, [r12+28h]
0x18002e848  and     dword ptr [rax+34h], 0FF1FFFFFh
0x18002e84f  lea     rax, [rbp+var_20]
0x18002e853  mov     [r12], rax
0x18002e857  lea     rax, [rbp+var_20]
0x18002e85b  mov     [r12+8], rax
0x18002e860  mov     qword ptr [rbp+var_20], r12
0x18002e864  mov     qword ptr [rbp+var_20+8], r12
0x18002e868  mov     r15, qword ptr [rbp+var_20]
0x18002e86c  lea     rax, [rbp+var_20]
0x18002e870  cmp     r15, rax
0x18002e873  jz      loc_18002EE5F
0x18002e879  lea     rax, [rbp+var_20]
0x18002e87d  cmp     [r15+8], rax
0x18002e881  jnz     loc_18002EE58
0x18002e887  mov     rax, [r15]
0x18002e88a  cmp     [rax+8], r15
0x18002e88e  jnz     loc_18002EE58
0x18002e894  mov     qword ptr [rbp+var_20], rax
0x18002e898  lea     rcx, [rbp+var_20]
0x18002e89c  mov     [rax+8], rcx
0x18002e8a0  mov     rsi, [r15+28h]
0x18002e8a4  mov     dword ptr [r15+1Ch], 746Eh
0x18002e8ac  mov     [r15+10h], rdi
0x18002e8b0  mov     [rbp+var_28], rsi
0x18002e8b4  mov     ecx, [rsi+30h]
0x18002e8b7  cmp     ecx, 0FFFFFFFFh
0x18002e8ba  jz      short loc_18002E8DE
0x18002e8bc  mov     rdx, r14
0x18002e8bf  call    ORConvertOffsetToAbsolute
0x18002e8c4  test    rax, rax
0x18002e8c7  jz      loc_18002E786
0x18002e8cd  cmp     dword ptr [rax], 0
0x18002e8d0  jg      loc_18002E786
0x18002e8d6  add     rax, 4
0x18002e8da  mov     [r15+78h], rax
0x18002e8de  cmp     r15, r12
0x18002e8e1  jnz     short loc_18002E8F8
0x18002e8e3  mov     rdx, rsi
0x18002e8e6  mov     rcx, rdi
0x18002e8e9  call    ORCreateSecurityDescriptorsList
0x18002e8ee  mov     ebx, eax
0x18002e8f0  test    eax, eax
0x18002e8f2  jnz     loc_18002E78B
0x18002e8f8  mov     rdx, [rdi+10h]
0x18002e8fc  mov     ecx, [rsi+2Ch]
0x18002e8ff  call    ORConvertOffsetToAbsolute
0x18002e904  test    rax, rax
0x18002e907  jz      short loc_18002E938
0x18002e909  cmp     dword ptr [rax], 0
0x18002e90c  jg      short loc_18002E938
0x18002e90e  lea     r8, [rdi+40h]
0x18002e912  lea     rcx, [rax+4]
0x18002e916  mov     rax, [r8]
0x18002e919  jmp     short loc_18002E923
0x18002e91b  mov     rax, [rax]
0x18002e91e  cmp     rax, r8
0x18002e921  jz      short loc_18002E92C
0x18002e923  mov     rdx, rax
0x18002e926  cmp     rcx, [rax+10h]
0x18002e92a  jnz     short loc_18002E91B
0x18002e92c  xor     eax, eax
0x18002e92e  cmp     rcx, [rdx+10h]
0x18002e932  cmovz   rax, rdx
0x18002e936  jmp     short loc_18002E93A
0x18002e938  xor     eax, eax
0x18002e93a  mov     [r15+60h], rax
0x18002e93e  test    rax, rax
0x18002e941  jz      loc_18002E786
0x18002e947  mov     eax, [rsi+24h]
0x18002e94a  lea     r13, [r15+80h]
0x18002e951  mov     [r15+88h], r13
0x18002e958  mov     [r13+0], r13
0x18002e95c  mov     [rbp+arg_8], eax
0x18002e95f  test    eax, eax
0x18002e961  jz      loc_18002EBA5
0x18002e967  mov     ecx, [rsi+28h]
0x18002e96a  mov     rdx, r14
0x18002e96d  call    ORConvertOffsetToAbsolute
0x18002e972  mov     [rbp+var_30], rax
0x18002e976  mov     r12, rax
0x18002e979  test    rax, rax
0x18002e97c  jz      loc_18002EE41
0x18002e982  cmp     dword ptr [rax], 0
0x18002e985  jg      loc_18002EE41
0x18002e98b  xor     esi, esi
0x18002e98d  mov     [rbp+arg_0], esi
0x18002e990  mov     edx, 10h; Alignment
0x18002e995  lea     ecx, [rdx+20h]; Size
0x18002e998  call    _o__aligned_malloc_0
0x18002e99d  mov     rbx, rax
0x18002e9a0  test    rax, rax
0x18002e9a3  jz      loc_18002EE4A
0x18002e9a9  mov     ecx, [r12+rsi*4+4]
0x18002e9ae  mov     rdx, r14
0x18002e9b1  call    ORConvertOffsetToAbsolute
0x18002e9b6  mov     [rbx+10h], rax
0x18002e9ba  mov     qword ptr [rbx+20h], 0
0x18002e9c2  mov     qword ptr [rbx+28h], 0
0x18002e9ca  lea     rcx, [rax+4]
0x18002e9ce  mov     [rbx+18h], rcx
0x18002e9d2  test    rax, rax
0x18002e9d5  jz      loc_18002EE39
0x18002e9db  mov     edx, [rax]
0x18002e9dd  test    edx, edx
0x18002e9df  jg      loc_18002EE39
0x18002e9e5  movzx   eax, word ptr [rcx+2]
0x18002e9e9  neg     edx
0x18002e9eb  add     eax, 14h
0x18002e9ee  cmp     eax, edx
0x18002e9f0  ja      loc_18002EE39
0x18002e9f6  mov     eax, 6B76h
0x18002e9fb  cmp     [rcx], ax
0x18002e9fe  jnz     loc_18002EE39
0x18002ea04  cmp     dword ptr [rcx+4], 0
0x18002ea08  jnz     short loc_18002EA14
0x18002ea0a  cmp     dword ptr [rcx+8], 0FFFFFFFFh
0x18002ea0e  jnz     loc_18002EE39
0x18002ea14  mov     rax, [r13+8]
0x18002ea18  cmp     [rax], r13
0x18002ea1b  jnz     loc_18002EE58
0x18002ea21  mov     [rbx], r13
0x18002ea24  mov     [rbx+8], rax
0x18002ea28  mov     [rax], rbx
0x18002ea2b  mov     [r13+8], rbx
0x18002ea2f  mov     rcx, [rbx+18h]
0x18002ea33  mov     r8d, [rcx+4]
0x18002ea37  test    r8d, r8d
0x18002ea3a  jnz     short loc_18002EA49
0x18002ea3c  mov     qword ptr [rbx+28h], 0
0x18002ea44  jmp     loc_18002EB93
0x18002ea49  cmp     r8d, 80000000h
0x18002ea50  jb      short loc_18002EA5B
0x18002ea52  lea     rax, [rcx+8]
0x18002ea56  jmp     loc_18002EB8F
0x18002ea5b  mov     rax, [rdi+10h]
0x18002ea5f  mov     edx, [rax+14h]
0x18002ea62  mov     eax, [rax+18h]
0x18002ea65  add     eax, 0FFFFF000h
0x18002ea6a  shl     edx, 0Ch
0x18002ea6d  add     edx, eax
0x18002ea6f  cmp     edx, 4
0x18002ea72  jb      loc_18002EB6E
0x18002ea78  cmp     r8d, 3FD8h
0x18002ea7f  jbe     loc_18002EB6E
0x18002ea85  mov     ecx, [rcx+8]
0x18002ea88  mov     rdx, r14
0x18002ea8b  call    ORConvertOffsetToAbsolute
0x18002ea90  test    rax, rax
0x18002ea93  jz      loc_18002EE41
0x18002ea99  cmp     dword ptr [rax], 0
0x18002ea9c  jg      loc_18002EE41
0x18002eaa2  lea     rsi, [rax+4]
0x18002eaa6  mov     eax, 6264h
0x18002eaab  cmp     [rsi], ax
0x18002eaae  jnz     loc_18002EE41
0x18002eab4  xor     eax, eax
0x18002eab6  cmp     ax, [rsi+2]
0x18002eaba  jz      loc_18002EE41
0x18002eac0  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x18002eac4  jz      loc_18002EE41
0x18002eaca  movzx   eax, word ptr [rsi+2]
0x18002eace  mov     edx, 10h; Alignment
0x18002ead3  lea     r12, ds:8[rax*8]
0x18002eadb  mov     rcx, r12; Size
0x18002eade  call    _o__aligned_malloc_0
0x18002eae3  mov     r14, rax
0x18002eae6  test    rax, rax
0x18002eae9  jz      loc_18002EE4A
0x18002eaef  mov     r8, r12; Size
0x18002eaf2  xor     edx, edx; Val
0x18002eaf4  mov     rcx, rax; void *
0x18002eaf7  call    memset_0
0x18002eafc  mov     r11, [rbp+arg_18]
0x18002eb00  mov     [r14], rsi
0x18002eb03  mov     rdx, r11
0x18002eb06  mov     ecx, [rsi+4]
0x18002eb09  call    ORConvertOffsetToAbsolute
0x18002eb0e  mov     r10, rax
0x18002eb11  test    rax, rax
0x18002eb14  jz      loc_18002EE41
0x18002eb1a  cmp     dword ptr [rax], 0
0x18002eb1d  jg      loc_18002EE41
0x18002eb23  xor     r8d, r8d
0x18002eb26  xor     ecx, ecx
0x18002eb28  cmp     cx, [rsi+2]
0x18002eb2c  jnb     short loc_18002EB5E
0x18002eb2e  mov     ecx, [r10+r8*4+4]
0x18002eb33  mov     rdx, r11
0x18002eb36  call    ORConvertOffsetToAbsolute
0x18002eb3b  test    rax, rax
0x18002eb3e  jz      loc_18002EE41
  ... truncated ...
```
