# RtlpCreateSplitBlock

- ea: `0x1800050f0`
- end: `0x180005f63`
- name: `RtlpCreateSplitBlock`
- size: `3699`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800075c0`
- `0x18003c328`
- `0x18009f9f4`

## callees

- `0x180004350`
- `0x180004460`
- `0x1800050f0`
- `0x180005f70`
- `0x180007060`
- `0x1800070f0`
- `0x180007cd0`
- `0x180008124`
- `0x180008488`
- `0x18011c718`
- `0x1801625d0`

## pseudocode

```c
char __fastcall RtlpCreateSplitBlock(
        unsigned __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        char a4,
        char a5,
        __int16 a6,
        __int64 a7)
{
  unsigned __int64 v9; // rbp
  int v10; // r13d
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rdi
  _DWORD *v14; // r12
  unsigned __int64 v15; // r15
  _QWORD *v16; // r8
  __int64 *v17; // rdi
  unsigned __int64 v18; // rax
  int v19; // ebp
  int v20; // r12d
  _QWORD *v21; // r14
  _QWORD *v22; // rax
  int v23; // esi
  _DWORD *v24; // r13
  __int64 v25; // r8
  int v26; // esi
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // r8
  unsigned int v30; // edx
  __int64 v31; // r10
  int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // eax
  _QWORD *v35; // rsi
  int v36; // ecx
  unsigned __int16 v37; // ax
  __int64 *v38; // rax
  _QWORD *v39; // r15
  __int64 *v40; // rdi
  unsigned __int64 v41; // r14
  unsigned __int64 v42; // rax
  int v43; // ecx
  int v44; // edx
  unsigned int v45; // esi
  __int64 v46; // rax
  __int64 v47; // r12
  __int64 v48; // r13
  __int64 *v50; // r11
  __int64 *v51; // r8
  __int64 v52; // r10
  __int64 v53; // rax
  __int64 v54; // r9
  __int64 *v55; // r15
  unsigned __int64 v56; // rax
  unsigned __int64 v57; // rcx
  int v58; // ecx
  _QWORD *i; // r13
  int v60; // r12d
  int v61; // eax
  unsigned int v62; // edx
  int v63; // r9d
  unsigned int v64; // r13d
  __int64 v65; // rax
  __int64 *v66; // rax
  __int64 *v67; // r13
  __int64 *v68; // rax
  int v69; // edx
  char v70; // r8
  _DWORD *v71; // rdx
  char v72; // cl
  unsigned __int64 v73; // rsi
  __int64 v74; // r12
  unsigned __int64 v75; // r8
  unsigned __int64 v76; // rsi
  _QWORD *v77; // rdi
  _QWORD *v78; // r8
  int v79; // ecx
  __int64 *v80; // rax
  _QWORD *v81; // rdi
  __int64 **v82; // rdx
  unsigned __int64 v83; // rcx
  unsigned __int64 v84; // r8
  unsigned __int64 v85; // rdx
  _DWORD *v86; // r8
  _QWORD *v87; // rdi
  _QWORD *v88; // r8
  __int64 *v89; // rax
  _QWORD *v90; // r14
  __int64 *v91; // rdi
  unsigned __int64 v92; // r13
  unsigned __int64 v93; // rax
  int v94; // ecx
  int v95; // edx
  unsigned int v96; // esi
  __int64 v97; // rax
  __int64 v98; // r12
  __int64 v99; // r15
  int v100; // ecx
  unsigned __int16 v101; // ax
  int v102; // edx
  int v103; // r8d
  unsigned __int64 v104; // rdx
  _DWORD *v105; // r8
  _QWORD *v106; // rdi
  _QWORD *Entry; // r8
  __int64 *v108; // rax
  int v109; // ecx
  int v110; // [rsp+20h] [rbp-68h]
  __int64 v111; // [rsp+30h] [rbp-58h]
  __int64 *v112; // [rsp+38h] [rbp-50h]
  unsigned __int16 v113; // [rsp+90h] [rbp+8h]
  __int64 v114; // [rsp+98h] [rbp+10h]
  int v116; // [rsp+A8h] [rbp+20h]
  int v117; // [rsp+A8h] [rbp+20h]
  __int16 v118; // [rsp+A8h] [rbp+20h]
  __int16 v119; // [rsp+A8h] [rbp+20h]
  int v120; // [rsp+B8h] [rbp+30h]
  unsigned int v121; // [rsp+B8h] [rbp+30h]
  _DWORD *v122; // [rsp+C0h] [rbp+38h]
  __int64 **v123; // [rsp+C0h] [rbp+38h]
  __int16 v124; // [rsp+C0h] [rbp+38h]

  *(_BYTE *)(a3 + 15) = 0;
  v9 = a3;
  *(_BYTE *)(a3 + 10) = a4;
  v10 = 0;
  *(_WORD *)(a3 + 12) = *(_WORD *)(a1 + 140) ^ a6;
  v11 = *(_QWORD *)(a2 + 40);
  v116 = 0;
  if ( v11 == a2 )
  {
    LOBYTE(v12) = 0;
  }
  else
  {
    v12 = ((a3 - a2) >> 16) + 1;
    if ( v12 >= 0xFE )
      RtlpLogHeapFailure(3, v11, a3, a2, 0, 0);
  }
  *(_BYTE *)(v9 + 14) = v12;
  v13 = v9 + 16 * a7;
  *(_BYTE *)(v9 + 11) = 0;
  *(_WORD *)(v9 + 8) = a7;
  v14 = (_DWORD *)(v13 + 8);
  while ( ((*(_BYTE *)(v13 + 10) ^ (unsigned __int8)(*(_BYTE *)(a1 + 138) & (*(_DWORD *)(a1 + 124) >> 20))) & 1) == 0 )
  {
    if ( *(_DWORD *)(a1 + 124) )
    {
      *v14 ^= *(_DWORD *)(a1 + 136);
      if ( HIBYTE(*v14) != ((unsigned __int8)*v14 ^ (unsigned __int8)(BYTE1(*v14) ^ HIWORD(*v14))) )
        RtlpAnalyzeHeapFailure(a1, v9 + 16 * a7);
    }
    v50 = *(__int64 **)(v13 + 24);
    v51 = (__int64 *)(v13 + 16);
    v52 = *(_QWORD *)(v13 + 16);
    v111 = v52;
    v112 = v50;
    v53 = *v50;
    v54 = *(_QWORD *)(v52 + 8);
    if ( *v50 != v13 + 16 || v53 != v54 )
    {
      RtlpLogHeapFailure(13, a1, (_DWORD)v51, v54, v53, 0);
      v14 = (_DWORD *)(v13 + 8);
      goto LABEL_144;
    }
    *(_QWORD *)(a1 + 192) -= *(unsigned __int16 *)v14;
    v55 = *(__int64 **)(a1 + 312);
    if ( v55 )
    {
      v56 = *(unsigned __int16 *)v14;
      v113 = *(_WORD *)v14;
      while ( 1 )
      {
        v57 = *((unsigned int *)v55 + 2);
        if ( v56 < v57 )
        {
          v62 = (unsigned __int16)v56;
          v63 = v57 - 1;
          goto LABEL_100;
        }
        if ( !*v55 )
          break;
        v55 = (__int64 *)*v55;
        v56 = *(unsigned __int16 *)v14;
      }
      v62 = v57 - 1;
      v63 = v57 - 1;
LABEL_100:
      v64 = v62 - *((_DWORD *)v55 + 6);
      v121 = v64;
      v65 = 2 * v64;
      if ( !*((_DWORD *)v55 + 3) )
        v65 = v64;
      v114 = 8 * v65;
      v123 = (__int64 **)(8 * v65 + v55[6]);
      v66 = *v123;
      --*((_DWORD *)v55 + 4);
      if ( v62 == v63 )
        --*((_DWORD *)v55 + 5);
      if ( v66 == v51 )
      {
        v67 = (__int64 *)*v51;
        v68 = (__int64 *)v55[4];
        if ( !*v55 )
          LODWORD(v57) = v63;
        if ( v62 >= (unsigned int)v57 )
        {
          if ( v67 == v68 )
          {
            v70 = v121;
            *v123 = 0;
            v71 = (_DWORD *)(v55[5] + 4 * ((unsigned __int64)v121 >> 5));
LABEL_114:
            *v71 &= ~(1 << (v70 & 0x1F));
          }
          else
          {
            *v123 = v67;
          }
        }
        else
        {
          if ( v67 == v68 )
            goto LABEL_113;
          v69 = *((_DWORD *)v67 - 2);
          if ( *(_DWORD *)(a1 + 124) )
          {
            v69 ^= *(_DWORD *)(a1 + 136);
            v124 = v69;
            if ( HIBYTE(v69) != ((unsigned __int8)v69 ^ (unsigned __int8)(BYTE1(v69) ^ BYTE2(v69))) )
            {
              RtlpLogHeapFailure(3, a1, (_DWORD)v67 - 16, 0, 0, 0);
              v52 = v111;
              v50 = v112;
              LOWORD(v69) = v124;
            }
          }
          if ( v113 != (unsigned __int16)v69 )
          {
LABEL_113:
            v70 = v121;
            *(_QWORD *)(v114 + v55[6]) = 0;
            v71 = (_DWORD *)(v55[5] + 4 * ((unsigned __int64)v121 >> 5));
            goto LABEL_114;
          }
          *(_QWORD *)(v114 + v55[6]) = v67;
        }
      }
      v10 = v116;
    }
    *v50 = v52;
    *(_QWORD *)(v52 + 8) = v50;
    if ( (*(_BYTE *)(v13 + 10) & 8) == 0 || (unsigned __int8)RtlpCommitBlock(a1, v9 + 16 * a7) )
    {
      if ( a5 )
      {
        v72 = *(_BYTE *)(v13 + 10);
        if ( (v72 & 4) != 0 )
        {
          v73 = 16LL * *(unsigned __int16 *)(v13 + 8) - 32;
          if ( (v72 & 2) != 0 && v73 > 4 )
            v73 = 16LL * *(unsigned __int16 *)(v13 + 8) - 36;
          v74 = RtlCompareMemoryUlong(v13 + 32, v73, 4277075694LL);
          if ( v74 != v73 )
          {
            if ( NtCurrentPeb()->Ldr )
              DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
            else
              DbgPrint("HEAP: ");
            DbgPrint(
              "HEAP: Free Heap block %p modified at %p after it was freed\n",
              (const void *)(v9 + 16 * a7),
              (const void *)(v74 + v13 + 32));
            RtlpBreakPointHeap();
          }
        }
      }
      *(_BYTE *)(v9 + 10) = *(_BYTE *)(v13 + 10);
      v75 = a7 + *(unsigned __int16 *)(v13 + 8);
      if ( v75 > 0xFF00 )
      {
        RtlpInsertFreeBlock(a1, v9, v75);
        return 1;
      }
      v76 = (unsigned __int16)v75;
      *(_WORD *)(v9 + 8) = v75;
      *(_WORD *)(v9 + 16 * v75 + 12) = *(_WORD *)(a1 + 140) ^ v75;
      *(_BYTE *)(v9 + 15) = 0;
      if ( a5 )
      {
        *(_BYTE *)(v9 + 10) &= 0xF0u;
        if ( (*(_BYTE *)(a1 + 112) & 0x40) != 0 )
        {
          v104 = (16 * (unsigned __int64)(unsigned __int16)v75 - 32) >> 2;
          if ( v104 )
          {
            v105 = (_DWORD *)(v9 + 32);
            if ( (((_BYTE)v9 + 32) & 4) != 0 )
            {
              --v104;
              *v105 = -17891602;
              v105 = (_DWORD *)(v9 + 36);
            }
            memset64(v105, 0xFEEEFEEEFEEEFEEEuLL, v104 >> 1);
            if ( (v104 & 1) != 0 )
              v105[v104 - 1] = -17891602;
          }
          *(_BYTE *)(v9 + 10) |= 4u;
        }
        v106 = (_QWORD *)(a1 + 336);
        if ( *(_QWORD *)(a1 + 312) )
          Entry = (_QWORD *)RtlpFindEntry(a1, v76);
        else
          Entry = (_QWORD *)*v106;
        for ( ; v106 != Entry; Entry = (_QWORD *)*Entry )
        {
          if ( *(_DWORD *)(a1 + 124) )
          {
            v109 = *((_DWORD *)Entry - 2);
            if ( (v109 & *(_DWORD *)(a1 + 124)) != 0 )
              LOWORD(v109) = *(_WORD *)(a1 + 136) ^ v109;
          }
          else
          {
            LOWORD(v109) = *((_WORD *)Entry - 4);
          }
          if ( v76 <= (unsigned __int16)v109 )
            break;
        }
        v108 = (__int64 *)Entry[1];
        v81 = (_QWORD *)(v9 + 16);
        if ( (_QWORD *)*v108 == Entry )
        {
          *v81 = Entry;
          *(_QWORD *)(v9 + 24) = v108;
          *v108 = (__int64)v81;
          Entry[1] = v81;
        }
        else
        {
          RtlpLogHeapFailure(13, 0, (_DWORD)Entry, 0, *v108, 0);
        }
        *(_QWORD *)(a1 + 192) += *(unsigned __int16 *)(v9 + 8);
        v82 = *(__int64 ***)(a1 + 312);
        if ( !v82 )
          goto LABEL_53;
        v83 = *(unsigned __int16 *)(v9 + 8);
        while ( 1 )
        {
          v84 = *((unsigned int *)v82 + 2);
          if ( v83 < v84 )
            goto LABEL_195;
          if ( !*v82 )
            break;
          v82 = (__int64 **)*v82;
        }
LABEL_215:
        v103 = v84 - 1;
      }
      else
      {
        *(_BYTE *)(v9 + 10) = 0;
        v77 = (_QWORD *)(a1 + 336);
        if ( *(_QWORD *)(a1 + 312) )
          v78 = (_QWORD *)RtlpFindEntry(a1, (unsigned __int16)v75);
        else
          v78 = (_QWORD *)*v77;
        for ( ; v77 != v78; v78 = (_QWORD *)*v78 )
        {
          if ( *(_DWORD *)(a1 + 124) )
          {
            v79 = *((_DWORD *)v78 - 2);
            if ( (v79 & *(_DWORD *)(a1 + 124)) != 0 )
              LOWORD(v79) = *(_WORD *)(a1 + 136) ^ v79;
          }
          else
          {
            LOWORD(v79) = *((_WORD *)v78 - 4);
          }
          if ( v76 <= (unsigned __int16)v79 )
            break;
        }
        v80 = (__int64 *)v78[1];
        v81 = (_QWORD *)(v9 + 16);
        if ( (_QWORD *)*v80 == v78 )
        {
          *v81 = v78;
          *(_QWORD *)(v9 + 24) = v80;
          *v80 = (__int64)v81;
          v78[1] = v81;
        }
        else
        {
          RtlpLogHeapFailure(13, 0, (_DWORD)v78, 0, *v80, 0);
        }
        *(_QWORD *)(a1 + 192) += *(unsigned __int16 *)(v9 + 8);
        v82 = *(__int64 ***)(a1 + 312);
        if ( !v82 )
          goto LABEL_53;
        v83 = *(unsigned __int16 *)(v9 + 8);
        while ( 1 )
        {
          v84 = *((unsigned int *)v82 + 2);
          if ( v83 < v84 )
            break;
          if ( !*v82 )
            goto LABEL_215;
          v82 = (__int64 **)*v82;
        }
LABEL_195:
        v103 = v83;
      }
      v110 = v103;
      LOBYTE(v103) = 1;
      RtlpHeapAddListEntry(a1, (_DWORD)v82, v103, (_DWORD)v81, v110, v83);
      goto LABEL_53;
    }
    RtlpDeCommitFreeBlock(a1, v9 + 16 * a7, *(unsigned __int16 *)v14, 1);
LABEL_144:
    if ( v10 )
      return 0;
    v10 = 1;
    v116 = 1;
  }
  v15 = (unsigned __int16)a7;
  *(_WORD *)(v13 + 12) = *(_WORD *)(a1 + 140) ^ a7;
  *(_BYTE *)(v9 + 15) = 0;
  if ( a5 )
  {
    *(_BYTE *)(v9 + 10) &= 0xF0u;
    if ( (*(_BYTE *)(a1 + 112) & 0x40) != 0 )
    {
      v85 = (16 * (unsigned __int64)(unsigned __int16)a7 - 32) >> 2;
      if ( v85 )
      {
        v86 = (_DWORD *)(v9 + 32);
        if ( (((_BYTE)v9 + 32) & 4) != 0 )
        {
          --v85;
          *v86 = -17891602;
          v86 = (_DWORD *)(v9 + 36);
        }
        memset64(v86, 0xFEEEFEEEFEEEFEEEuLL, v85 >> 1);
        if ( (v85 & 1) != 0 )
          v86[v85 - 1] = -17891602;
      }
      *(_BYTE *)(v9 + 10) |= 4u;
    }
    v87 = (_QWORD *)(a1 + 336);
    if ( *(_QWORD *)(a1 + 312) )
      v88 = (_QWORD *)RtlpFindEntry(a1, (unsigned __int16)a7);
    else
      v88 = (_QWORD *)*v87;
    for ( ; v87 != v88; v88 = (_QWORD *)*v88 )
    {
      if ( *(_DWORD *)(a1 + 124) )
      {
        v100 = *((_DWORD *)v88 - 2);
        if ( (v100 & *(_DWORD *)(a1 + 124)) != 0 )
          v101 = v100 ^ *(_WORD *)(a1 + 136);
        else
          v101 = *((_DWORD *)v88 - 2);
      }
      else
      {
        v101 = *((_WORD *)v88 - 4);
      }
      if ( (unsigned __int16)a7 <= (unsigned __int64)v101 )
        break;
    }
    v89 = (__int64 *)v88[1];
    v90 = (_QWORD *)(v9 + 16);
    if ( (_QWORD *)*v89 == v88 )
    {
      *v90 = v88;
      *(_QWORD *)(v9 + 24) = v89;
      *v89 = (__int64)v90;
      v88[1] = v90;
    }
    else
    {
      RtlpLogHeapFailure(13, 0, (_DWORD)v88, 0, *v89, 0);
    }
    *(_QWORD *)(a1 + 192) += *(unsigned __int16 *)(v9 + 8);
    v91 = *(__int64 **)(a1 + 312);
    if ( !v91 )
      goto LABEL_53;
    v92 = *(unsigned __int16 *)(v9 + 8);
    while ( 1 )
    {
      v93 = *((unsigned int *)v91 + 2);
      if ( v92 < v93 )
        break;
      if ( !*v91 )
      {
        v94 = v93 - 1;
        v95 = v93 - 1;
        goto LABEL_170;
      }
      v91 = (__int64 *)*v91;
    }
    v94 = *(unsigned __int16 *)(v9 + 8);
    v95 = v93 - 1;
LABEL_170:
    ++*((_DWORD *)v91 + 4);
    v96 = v94 - *((_DWORD *)v91 + 6);
    v97 = 2 * v96;
    if ( !*((_DWORD *)v91 + 3) )
      v97 = v96;
    v98 = 8 * v97;
    v99 = *(_QWORD *)(8 * v97 + v91[6]);
    if ( v94 == v95 )
      ++*((_DWORD *)v91 + 5);
    if ( !v99 )
      goto LABEL_175;
    v102 = *(_DWORD *)(v99 - 8);
    if ( *(_DWORD *)(a1 + 124) )
    {
      v102 ^= *(_DWORD *)(a1 + 136);
      v119 = v102;
      if ( HIBYTE(v102) != ((unsigned __int8)v102 ^ (unsigned __int8)(BYTE1(v102) ^ BYTE2(v102))) )
      {
        RtlpLogHeapFailure(3, a1, v99 - 16, 0, 0, 0);
        LOWORD(v102) = v119;
      }
    }
    if ( (int)(v92 - (unsigned __int16)v102) <= 0 )
    {
LABEL_175:
      *(_QWORD *)(v98 + v91[6]) = v90;
      if ( !v99 )
        *(_DWORD *)(v91[5] + 4 * ((unsigned __int64)v96 >> 5)) |= 1 << (v96 & 0x1F);
    }
    goto LABEL_53;
  }
  *(_BYTE *)(v9 + 10) = 0;
  v16 = (_QWORD *)(a1 + 336);
  v17 = *(__int64 **)(a1 + 312);
  if ( !v17 )
  {
    v35 = (_QWORD *)*v16;
    goto LABEL_33;
  }
  while ( 1 )
  {
    v18 = *((unsigned int *)v17 + 2);
    if ( (unsigned __int16)a7 < v18 )
    {
      v19 = (unsigned __int16)a7;
      goto LABEL_12;
    }
    if ( !*v17 )
      break;
    v17 = (__int64 *)*v17;
  }
  v19 = v18 - 1;
LABEL_12:
  v20 = (unsigned __int16)a7;
  v117 = (unsigned __int16)a7;
  while ( 2 )
  {
    v21 = (_QWORD *)v17[4];
    v22 = (_QWORD *)v21[1];
    if ( v21 == v22 )
    {
      v35 = (_QWORD *)v17[4];
      v20 = v15;
      goto LABEL_31;
    }
    v23 = *((_DWORD *)v22 - 2);
    v24 = (_DWORD *)(a1 + 136);
    v120 = *((_DWORD *)v17 + 6);
    v122 = (_DWORD *)(a1 + 136);
    if ( *(_DWORD *)(a1 + 124) )
    {
      v23 ^= *v24;
      if ( HIBYTE(v23) == ((unsigned __int8)v23 ^ (unsigned __int8)(BYTE1(v23) ^ BYTE2(v23))) )
        v122 = (_DWORD *)(a1 + 136);
      else
        RtlpLogHeapFailure(3, a1, (_DWORD)v22 - 16, 0, 0, 0);
    }
    if ( (int)(v15 - (unsigned __int16)v23) > 0 )
    {
      v35 = v21;
      goto LABEL_31;
    }
    v25 = *v21 - 16LL;
    v26 = *(_DWORD *)(v25 + 8);
    if ( *(_DWORD *)(a1 + 124) )
    {
      v26 ^= *v24;
      if ( HIBYTE(v26) != ((unsigned __int8)v26 ^ (unsigned __int8)(BYTE1(v26) ^ BYTE2(v26))) )
        RtlpLogHeapFailure(3, a1, v25, 0, 0, 0);
    }
    if ( v20 - (unsigned __int16)v26 <= 0 )
    {
      v35 = (_QWORD *)*v21;
      goto LABEL_31;
    }
    v27 = (unsigned int)(v19 - v120);
    if ( *v17 || v19 != *((_DWORD *)v17 + 2) - 1 )
    {
      v28 = v17[5];
      v29 = (unsigned int)v27 >> 5;
      v30 = *(_DWORD *)(v28 + 4 * v29) & (-1 << (v19 - v120));
      v31 = v28 + 4 * v29;
      if ( v30 )
      {
LABEL_25:
        if ( (_WORD)v30 )
        {
          if ( (_BYTE)v30 )
            v32 = (unsigned __int8)RtlpBitsClearLow[(unsigned __int8)v30];
          else
            v32 = (unsigned __int8)RtlpBitsClearLow[BYTE1(v30)] + 8;
        }
        else if ( (v30 & 0xFF0000) != 0 )
        {
          v32 = (unsigned __int8)RtlpBitsClearLow[BYTE2(v30)] + 16;
        }
        else
        {
          v32 = (unsigned __int8)RtlpBitsClearLow[(unsigned __int64)v30 >> 24] + 24;
        }
        v33 = 32 * v29 + v32;
        v34 = 2 * v33;
        if ( !*((_DWORD *)v17 + 3) )
          v34 = v33;
        v35 = *(_QWORD **)(v17[6] + 8LL * v34);
        goto LABEL_31;
      }
      while ( (unsigned int)v29 <= ((unsigned int)(*((_DWORD *)v17 + 2) - *((_DWORD *)v17 + 6)) >> 5) - 1 )
      {
        v30 = *(_DWORD *)(v31 + 4);
        v31 += 4;
        LODWORD(v29) = v29 + 1;
        if ( v30 )
          goto LABEL_25;
      }
      v117 = v20;
LABEL_67:
      v17 = (__int64 *)*v17;
      v19 = *((_DWORD *)v17 + 6);
      continue;
    }
    break;
  }
  v35 = 0;
  if ( *((_DWORD *)v17 + 3) )
    v27 = (unsigned int)(2 * v27);
  for ( i = *(_QWORD **)(v17[6] + 8 * v27); v21 != i; i = (_QWORD *)*i )
  {
    v60 = *((_DWORD *)i - 2);
    if ( *(_DWORD *)(a1 + 124) )
    {
      v60 ^= *v122;
      if ( HIBYTE(v60) != ((unsigned __int8)v60 ^ (unsigned __int8)(BYTE1(v60) ^ BYTE2(v60))) )
        RtlpLogHeapFailure(3, a1, (_DWORD)i - 16, 0, 0, 0);
    }
    v61 = (unsigned __int16)v60;
    v20 = v117;
    if ( v117 - v61 <= 0 )
    {
      v35 = i;
      break;
    }
  }
LABEL_31:
  v117 = v20;
  if ( !v35 )
    goto LABEL_67;
  v9 = a3;
  v16 = (_QWORD *)(a1 + 336);
LABEL_33:
  while ( v16 != v35 )
  {
    if ( *(_DWORD *)(a1 + 124) )
    {
      v36 = *((_DWORD *)v35 - 2);
      if ( (v36 & *(_DWORD *)(a1 + 124)) != 0 )
        v37 = v36 ^ *(_WORD *)(a1 + 136);
      else
        v37 = *((_DWORD *)v35 - 2);
    }
    else
    {
      v37 = *((_WORD *)v35 - 4);
    }
    if ( v15 <= v37 )
      break;
    v35 = (_QWORD *)*v35;
  }
  v38 = (__int64 *)v35[1];
  v39 = (_QWORD *)(v9 + 16);
  if ( (_QWORD *)*v38 == v35 )
  {
    *v39 = v35;
    *(_QWORD *)(v9 + 24) = v38;
    *v38 = (__int64)v39;
    v35[1] = v39;
  }
  else
  {
    RtlpLogHeapFailure(13, 0, (_DWORD)v35, 0, *v38, 0);
  }
  *(_QWORD *)(a1 + 192) += *(unsigned __int16 *)(v9 + 8);
  v40 = *(__int64 **)(a1 + 312);
  if ( v40 )
  {
    v41 = *(unsigned __int16 *)(v9 + 8);
    while ( 1 )
    {
      v42 = *((unsigned int *)v40 + 2);
      if ( v41 < v42 )
      {
        v43 = *(unsigned __int16 *)(v9 + 8);
        v44 = v42 - 1;
        goto LABEL_46;
      }
      if ( !*v40 )
        break;
      v40 = (__int64 *)*v40;
    }
    v43 = v42 - 1;
    v44 = v42 - 1;
LABEL_46:
    ++*((_DWORD *)v40 + 4);
    v45 = v43 - *((_DWORD *)v40 + 6);
    v46 = 2 * v45;
    if ( !*((_DWORD *)v40 + 3) )
      v46 = v45;
    v47 = 8 * v46;
    v48 = *(_QWORD *)(8 * v46 + v40[6]);
    if ( v43 == v44 )
      ++*((_DWORD *)v40 + 5);
    if ( !v48 )
      goto LABEL_51;
    v58 = *(_DWORD *)(v48 - 8);
    if ( *(_DWORD *)(a1 + 124) )
    {
      v58 ^= *(_DWORD *)(a1 + 136);
      v118 = v58;
      if ( HIBYTE(v58) != ((unsigned __int8)v58 ^ (unsigned __int8)(BYTE1(v58) ^ BYTE2(v58))) )
      {
        RtlpLogHeapFailure(3, a1, v48 - 16, 0, 0, 0);
        LOWORD(v58) = v118;
      }
    }
    if ( (int)(v41 - (unsigned __int16)v58) <= 0 )
    {
LABEL_51:
      *(_QWORD *)(v47 + v40[6]) = v39;
      if ( !v48 )
        *(_DWORD *)(v40[5] + 4 * ((unsigned __int64)v45 >> 5)) |= 1 << (v45 & 0x1F);
    }
  }
LABEL_53:
  if ( *(_DWORD *)(a1 + 124) )
  {
    *(_BYTE *)(v9 + 11) = *(_BYTE *)(v9 + 8) ^ *(_BYTE *)(v9 + 9) ^ *(_BYTE *)(v9 + 10);
    *(_DWORD *)(v9 + 8) ^= *(_DWORD *)(a1 + 136);
  }
  return 1;
}

```

## disassembly

```asm
0x1800050f0  mov     [rsp+arg_10], r8
0x1800050f5  push    rbx
0x1800050f6  push    rbp
0x1800050f7  push    rsi
0x1800050f8  push    rdi
0x1800050f9  push    r12
0x1800050fb  push    r13
0x1800050fd  push    r14
0x1800050ff  push    r15
0x180005101  sub     rsp, 48h
0x180005105  movzx   eax, word ptr [rsp+88h+arg_28]
0x18000510d  xor     r10d, r10d
0x180005110  mov     r14, [rsp+88h+arg_30]
0x180005118  mov     rbx, rcx
0x18000511b  mov     [r8+0Fh], r10b
0x18000511f  mov     rbp, r8
0x180005122  mov     [r8+0Ah], r9b
0x180005126  mov     r13d, r10d
0x180005129  xor     ax, [rcx+8Ch]
0x180005130  mov     [r8+0Ch], ax
0x180005135  mov     rcx, [rdx+28h]
0x180005139  mov     [rsp+88h+arg_18], r10d
0x180005141  cmp     rcx, rdx
0x180005144  jz      loc_180005573
0x18000514a  mov     rdi, r8
0x18000514d  sub     rdi, rdx
0x180005150  shr     rdi, 10h
0x180005154  inc     rdi
0x180005157  cmp     rdi, 0FEh
0x18000515e  jnb     loc_180005A62
0x180005164  mov     [rbp+0Eh], dil
0x180005168  mov     r15d, 1
0x18000516e  mov     rdi, r14
0x180005171  movzx   esi, r14w
0x180005175  shl     rdi, 4
0x180005179  add     rdi, rbp
0x18000517c  mov     [rbp+0Bh], r13b
0x180005180  mov     [rbp+8], si
0x180005184  lea     r12, [rdi+8]
0x180005188  movzx   eax, byte ptr [rbx+8Ah]
0x18000518f  mov     edx, [rbx+7Ch]
0x180005192  mov     ecx, edx
0x180005194  shr     ecx, 14h
0x180005197  and     ecx, eax
0x180005199  movzx   eax, byte ptr [rdi+0Ah]
0x18000519d  xor     ecx, eax
0x18000519f  test    cl, 1
0x1800051a2  jz      loc_1800054B1
0x1800051a8  movzx   eax, si
0x1800051ab  mov     r15, rsi
0x1800051ae  xor     ax, [rbx+8Ch]
0x1800051b5  cmp     [rsp+88h+arg_20], 0
0x1800051bd  mov     [rdi+0Ch], ax
0x1800051c1  mov     byte ptr [rbp+0Fh], 0
0x1800051c5  jnz     loc_180005A81
0x1800051cb  mov     byte ptr [rbp+0Ah], 0
0x1800051cf  lea     r8, [rbx+150h]
0x1800051d6  mov     rdi, [rbx+138h]
0x1800051dd  test    rdi, rdi
0x1800051e0  jz      loc_180005A5A
0x1800051e6  mov     eax, [rdi+8]
0x1800051e9  cmp     r15, rax
0x1800051ec  jb      short loc_1800051FF
0x1800051ee  mov     rcx, [rdi]
0x1800051f1  test    rcx, rcx
0x1800051f4  jz      loc_1800055A0
0x1800051fa  mov     rdi, rcx
0x1800051fd  jmp     short loc_1800051E6
0x1800051ff  mov     rbp, r15
0x180005202  mov     r12d, r15d
0x180005205  mov     [rsp+88h+arg_18], r15d
0x18000520d  mov     r14, [rdi+20h]
0x180005211  mov     rax, [r14+8]
0x180005215  cmp     r14, rax
0x180005218  jz      loc_1800056FF
0x18000521e  mov     esi, [rax-8]
0x180005221  lea     r8, [rax-10h]
0x180005225  cmp     dword ptr [rbx+7Ch], 0
0x180005229  lea     r13, [rbx+88h]
0x180005230  mov     ecx, [rdi+18h]
0x180005233  mov     [rsp+88h+arg_28], ecx
0x18000523a  mov     [rsp+88h+arg_30], r13
0x180005242  jz      short loc_180005281
0x180005244  xor     esi, [r13+0]
0x180005248  mov     ecx, esi
0x18000524a  mov     eax, esi
0x18000524c  shr     eax, 8
0x18000524f  shr     ecx, 10h
0x180005252  xor     cl, al
0x180005254  mov     eax, esi
0x180005256  shr     eax, 18h
0x180005259  xor     cl, sil
0x18000525c  cmp     al, cl
0x18000525e  jz      loc_180005E7A
0x180005264  xor     r10d, r10d
0x180005267  xor     r9d, r9d
0x18000526a  mov     [rsp+88h+var_60], r10
0x18000526f  mov     rdx, rbx
0x180005272  mov     ecx, 3
0x180005277  mov     [rsp+88h+var_68], r10
0x18000527c  call    RtlpLogHeapFailure
0x180005281  movzx   eax, si
0x180005284  mov     ecx, r15d
0x180005287  sub     ecx, eax
0x180005289  test    ecx, ecx
0x18000528b  jg      loc_18000570A
0x180005291  mov     r8, [r14]
0x180005294  add     r8, 0FFFFFFFFFFFFFFF0h
0x180005298  mov     esi, [r8+8]
0x18000529c  cmp     dword ptr [rbx+7Ch], 0
0x1800052a0  jz      short loc_1800052DA
0x1800052a2  xor     esi, [r13+0]
0x1800052a6  mov     ecx, esi
0x1800052a8  mov     eax, esi
0x1800052aa  shr     eax, 8
0x1800052ad  shr     ecx, 10h
0x1800052b0  xor     cl, al
0x1800052b2  mov     eax, esi
0x1800052b4  shr     eax, 18h
0x1800052b7  xor     cl, sil
0x1800052ba  cmp     al, cl
0x1800052bc  jz      short loc_1800052DA
0x1800052be  xor     eax, eax
0x1800052c0  xor     r9d, r9d
0x1800052c3  mov     [rsp+88h+var_60], rax
0x1800052c8  mov     rdx, rbx
0x1800052cb  mov     ecx, 3
0x1800052d0  mov     [rsp+88h+var_68], rax
0x1800052d5  call    RtlpLogHeapFailure
0x1800052da  movzx   eax, si
0x1800052dd  mov     ecx, r12d
0x1800052e0  sub     ecx, eax
0x1800052e2  test    ecx, ecx
0x1800052e4  jle     loc_1800056C5
0x1800052ea  mov     ecx, ebp
0x1800052ec  sub     ecx, [rsp+88h+arg_28]
0x1800052f3  cmp     qword ptr [rdi], 0
0x1800052f7  jnz     short loc_180005306
0x1800052f9  mov     eax, [rdi+8]
0x1800052fc  dec     eax
0x1800052fe  cmp     ebp, eax
0x180005300  jz      loc_18000561B
0x180005306  mov     r9d, [rdi+8]
0x18000530a  mov     r8d, ecx
0x18000530d  sub     r9d, [rdi+18h]
0x180005311  mov     edx, 0FFFFFFFFh
0x180005316  mov     rax, [rdi+28h]
0x18000531a  shr     r8d, 5
0x18000531e  shr     r9d, 5
0x180005322  dec     r9d
0x180005325  shl     edx, cl
0x180005327  and     edx, [rax+r8*4]
0x18000532b  lea     r10, [rax+r8*4]
0x18000532f  jz      loc_180005712
0x180005335  mov     ecx, edx
0x180005337  test    dx, dx
0x18000533a  jnz     loc_18000557B
0x180005340  test    edx, 0FF0000h
0x180005346  jnz     loc_1800056CD
0x18000534c  shr     rcx, 18h
0x180005350  lea     rax, RtlpBitsClearLow; "\b"
0x180005357  movzx   ecx, byte ptr [rcx+rax]
0x18000535b  add     ecx, 18h
0x18000535e  shl     r8d, 5
0x180005362  add     ecx, r8d
0x180005365  cmp     dword ptr [rdi+0Ch], 0
0x180005369  lea     eax, [rcx+rcx]
0x18000536c  cmovz   eax, ecx
0x18000536f  mov     ecx, eax
0x180005371  mov     rax, [rdi+30h]
0x180005375  mov     rsi, [rax+rcx*8]
0x180005379  mov     [rsp+88h+arg_18], r12d
0x180005381  test    rsi, rsi
0x180005384  jz      loc_180005568
0x18000538a  mov     rbp, [rsp+88h+arg_10]
0x180005392  lea     r8, [rbx+150h]
0x180005399  cmp     r8, rsi
0x18000539c  jz      short loc_1800053CA
0x18000539e  cmp     dword ptr [rbx+7Ch], 0
0x1800053a2  jz      loc_180005612
0x1800053a8  mov     ecx, [rsi-8]
0x1800053ab  test    [rbx+7Ch], ecx
0x1800053ae  jz      loc_180005EB6
0x1800053b4  movzx   eax, word ptr [rbx+88h]
0x1800053bb  xor     ax, cx
0x1800053be  movzx   eax, ax
0x1800053c1  cmp     r15, rax
0x1800053c4  ja      loc_1800056E7
0x1800053ca  mov     rax, [rsi+8]
0x1800053ce  lea     r15, [rbp+10h]
0x1800053d2  mov     rcx, [rax]
0x1800053d5  cmp     rcx, rsi
0x1800053d8  jnz     loc_1800059EF
0x1800053de  mov     [r15], rsi
0x1800053e1  mov     [r15+8], rax
0x1800053e5  mov     [rax], r15
0x1800053e8  mov     [rsi+8], r15
0x1800053ec  movzx   eax, word ptr [rbp+8]
0x1800053f0  add     [rbx+0C0h], rax
0x1800053f7  mov     rdi, [rbx+138h]
0x1800053fe  test    rdi, rdi
0x180005401  jz      short loc_180005481
0x180005403  movzx   r14d, word ptr [rbp+8]
0x180005408  mov     eax, [rdi+8]
0x18000540b  cmp     r14, rax
0x18000540e  jb      short loc_180005421
0x180005410  mov     rcx, [rdi]
0x180005413  test    rcx, rcx
0x180005416  jz      loc_180005596
0x18000541c  mov     rdi, rcx
0x18000541f  jmp     short loc_180005408
0x180005421  mov     ecx, r14d
0x180005424  lea     edx, [rax-1]
0x180005427  inc     dword ptr [rdi+10h]
0x18000542a  mov     esi, ecx
0x18000542c  sub     esi, [rdi+18h]
0x18000542f  cmp     dword ptr [rdi+0Ch], 0
0x180005433  lea     eax, [rsi+rsi]
0x180005436  cmovz   eax, esi
0x180005439  lea     r12, ds:0[rax*8]
0x180005441  mov     rax, [rdi+30h]
0x180005445  mov     r13, [r12+rax]
0x180005449  cmp     ecx, edx
0x18000544b  jnz     short loc_180005450
0x18000544d  inc     dword ptr [rdi+14h]
0x180005450  test    r13, r13
0x180005453  jnz     loc_1800055A8
0x180005459  mov     rax, [rdi+30h]
0x18000545d  mov     [r12+rax], r15
0x180005461  test    r13, r13
0x180005464  jnz     short loc_180005481
0x180005466  mov     rax, [rdi+28h]
0x18000546a  mov     edi, 1
0x18000546f  mov     edx, esi
0x180005471  and     esi, 1Fh
0x180005474  shr     rdx, 5
0x180005478  movzx   ecx, sil
0x18000547c  shl     edi, cl
0x18000547e  or      [rax+rdx*4], edi
0x180005481  cmp     dword ptr [rbx+7Ch], 0
0x180005485  jz      short loc_18000549D
0x180005487  movzx   eax, byte ptr [rbp+0Ah]
0x18000548b  xor     al, [rbp+9]
0x18000548e  xor     al, [rbp+8]
0x180005491  mov     [rbp+0Bh], al
0x180005494  mov     eax, [rbx+88h]
0x18000549a  xor     [rbp+8], eax
0x18000549d  mov     al, 1
0x18000549f  add     rsp, 48h
0x1800054a3  pop     r15
0x1800054a5  pop     r14
0x1800054a7  pop     r13
0x1800054a9  pop     r12
0x1800054ab  pop     rdi
0x1800054ac  pop     rsi
0x1800054ad  pop     rbp
0x1800054ae  pop     rbx
0x1800054af  retn
0x1800054b1  test    edx, edx
0x1800054b3  jz      short loc_1800054E3
0x1800054b5  mov     eax, [rbx+88h]
0x1800054bb  xor     [r12], eax
0x1800054bf  mov     edx, [r12]
0x1800054c3  mov     ecx, edx
0x1800054c5  shr     ecx, 10h
0x1800054c8  mov     eax, edx
0x1800054ca  shr     eax, 8
0x1800054cd  xor     cl, al
0x1800054cf  xor     cl, dl
0x1800054d1  shr     edx, 18h
0x1800054d4  cmp     dl, cl
0x1800054d6  jz      short loc_1800054E3
0x1800054d8  mov     rdx, rdi
0x1800054db  mov     rcx, rbx
0x1800054de  call    RtlpAnalyzeHeapFailure
0x1800054e3  mov     r11, [rdi+18h]
0x1800054e7  lea     r8, [rdi+10h]
0x1800054eb  mov     r10, [r8]
0x1800054ee  mov     [rsp+88h+var_58], r10
0x1800054f3  mov     [rsp+88h+var_50], r11
0x1800054f8  mov     rax, [r11]
0x1800054fb  mov     r9, [r10+8]
0x1800054ff  cmp     rax, r8
0x180005502  jnz     loc_180005A14
0x180005508  cmp     rax, r9
0x18000550b  jnz     loc_180005A14
0x180005511  movzx   eax, word ptr [r12]
0x180005516  sub     [rbx+0C0h], rax
0x18000551d  mov     r15, [rbx+138h]
0x180005524  test    r15, r15
0x180005527  jz      loc_180005863
0x18000552d  movzx   eax, word ptr [r12]
0x180005532  mov     [rsp+88h+arg_0], rax
0x18000553a  mov     ecx, [r15+8]
0x18000553e  cmp     rax, rcx
0x180005541  jb      loc_180005730
0x180005547  mov     rax, [r15]
0x18000554a  test    rax, rax
0x18000554d  jz      loc_180005A4F
0x180005553  mov     r15, rax
  ... truncated ...
```
