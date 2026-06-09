# CreateAndAddInterface

- ea: `0x180004c80`
- end: `0x180005616`
- name: `CreateAndAddInterface`
- size: `2454`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002910`

## callees

- `0x180004c80`
- `0x18000e510`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800054f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800054f5`

## pseudocode

```c
__int64 __fastcall CreateAndAddInterface(__int64 a1, __int64 a2, __int64 *a3, _DWORD *a4)
{
  unsigned int v8; // ebx
  _BYTE *v9; // rax
  char *v10; // r14
  _BYTE *v11; // r9
  int v12; // ecx
  int jj; // edx
  int v14; // r8d
  int v15; // ecx
  int v16; // edi
  int v17; // esi
  HANDLE ProcessHeap; // rax
  char *v19; // rax
  __int64 v20; // rax
  int v22; // r15d
  _BYTE *v23; // rax
  _BYTE *v24; // r9
  int v25; // ecx
  int i; // edx
  int v27; // r8d
  int v28; // ecx
  int v29; // eax
  int v30; // ecx
  int v31; // edx
  _BYTE *v32; // r10
  int v33; // r8d
  int v34; // edx
  int v35; // eax
  int v36; // ecx
  _BYTE *v37; // r9
  int j; // r8d
  int v39; // edx
  int v40; // ecx
  int v41; // ecx
  _BYTE *v42; // r10
  int k; // edx
  char *v44; // r9
  int v45; // r8d
  int v46; // ecx
  int v47; // r8d
  int v48; // ecx
  int v49; // edx
  int v50; // ecx
  int v51; // ecx
  char *v52; // r10
  int m; // edx
  char *v54; // r9
  int v55; // r8d
  int v56; // ecx
  int v57; // edx
  int v58; // ecx
  char *v59; // r10
  int v60; // r8d
  int v61; // ecx
  int v62; // edx
  int v63; // ecx
  char *v64; // r8
  int v65; // r8d
  int v66; // ecx
  int v67; // edx
  int n; // ecx
  char *v69; // r9
  int v70; // r9d
  int v71; // edx
  int v72; // r8d
  int ii; // ecx
  char *v74; // r10
  int v75; // edx
  int v76; // r8d
  int v77; // ecx
  int v78; // r8d
  int v79; // edx
  int v80; // r8d
  int v81; // eax
  int v82; // ecx
  int v83; // edx
  _BYTE *v84; // r10
  int v85; // r8d
  int v86; // edx
  int v87; // eax
  int v88; // ecx
  _BYTE *v89; // r9
  int kk; // r8d
  int v91; // edx
  int v92; // ecx
  int v93; // ecx
  _BYTE *v94; // r10
  int mm; // edx
  char *v96; // r9
  int v97; // r8d
  int v98; // ecx
  int v99; // r8d
  int v100; // ecx
  int v101; // edx
  int v102; // ecx
  int v103; // ecx
  char *v104; // r10
  int nn; // edx
  char *v106; // r9
  int v107; // r8d
  int v108; // ecx
  int v109; // edx
  int v110; // ecx
  char *v111; // r10
  int v112; // r8d
  int v113; // ecx
  int v114; // edx
  int v115; // ecx
  char *v116; // r8
  int v117; // r8d
  int v118; // ecx
  int v119; // edx
  int i1; // ecx
  char *v121; // r9
  int v122; // r9d
  int v123; // edx
  int v124; // r8d
  int i2; // ecx
  char *v126; // r10
  int v127; // edx
  int v128; // r8d
  int v129; // ecx
  int v130; // r8d
  int v131; // edx
  int v132; // r8d
  int v133; // edi
  int v134; // esi
  HANDLE v135; // rax
  char *v136; // rax
  __int128 v137; // xmm0
  _QWORD *v138; // rcx
  __int64 v139; // rdx
  __int128 v140; // [rsp+20h] [rbp-18h]
  __int128 v141; // [rsp+20h] [rbp-18h]

  if ( *(_WORD *)a2 == 2 && *(char *)(a1 + 92) < 0 )
  {
    v22 = *(_DWORD *)(a2 + 4);
    v141 = 0;
    if ( !v22 )
    {
      v8 = 13;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_e9479874f405377c737bad9289013c01_Traceguids, 13);
      v10 = 0;
      goto LABEL_15;
    }
    v23 = *(_BYTE **)(a1 + 16);
    v10 = 0;
    if ( *v23 == 123 )
    {
      v24 = v23 + 1;
      v25 = 0;
      for ( i = 0; ; ++i )
      {
        v27 = (char)v24[i];
        if ( i >= 8 )
          break;
        if ( (unsigned int)(v27 - 48) > 9 )
        {
          v27 |= 0x20u;
          if ( (unsigned int)(v27 - 97) > 5 )
            goto LABEL_12;
          v28 = 16 * v25 - 87;
        }
        else
        {
          v28 = 16 * v25 - 48;
        }
        v25 = v27 + v28;
      }
      LODWORD(v141) = v25;
      if ( (_BYTE)v27 == 45 )
      {
        v29 = i + 1;
        v30 = 0;
        v31 = 0;
        v32 = &v24[v29];
        while ( 1 )
        {
          v33 = (char)v32[v30];
          if ( v30 >= 4 )
            break;
          if ( (unsigned int)(v33 - 48) > 9 )
          {
            v33 |= 0x20u;
            if ( (unsigned int)(v33 - 97) > 5 )
              goto LABEL_12;
            v34 = 16 * v31 - 87;
          }
          else
          {
            v34 = 16 * v31 - 48;
          }
          v31 = v33 + v34;
          ++v30;
        }
        if ( (_BYTE)v33 == 45 )
        {
          v35 = v30 + 1;
          WORD2(v141) = v31;
          v36 = 0;
          v37 = &v32[v35];
          for ( j = 0; ; ++j )
          {
            v39 = (char)v37[j];
            if ( j >= 4 )
              break;
            if ( (unsigned int)(v39 - 48) > 9 )
            {
              v39 |= 0x20u;
              if ( (unsigned int)(v39 - 97) > 5 )
                goto LABEL_12;
              v40 = 16 * v36 - 87;
            }
            else
            {
              v40 = 16 * v36 - 48;
            }
            v36 = v39 + v40;
          }
          if ( (_BYTE)v39 == 45 )
          {
            WORD3(v141) = v36;
            v41 = 0;
            v42 = &v37[j + 1];
            for ( k = 0; ; ++k )
            {
              v44 = &v42[k];
              if ( k >= 2 )
                break;
              v45 = *v44;
              if ( (unsigned int)(v45 - 48) > 9 )
              {
                v45 |= 0x20u;
                if ( (unsigned int)(v45 - 97) > 5 )
                  goto LABEL_12;
                v46 = 16 * v41 - 87;
              }
              else
              {
                v46 = 16 * v41 - 48;
              }
              v41 = v45 + v46;
            }
            BYTE8(v141) = v41;
            v47 = 0;
            v48 = 0;
            while ( 1 )
            {
              v49 = v44[v47];
              if ( v47 >= 2 )
                break;
              if ( (unsigned int)(v49 - 48) > 9 )
              {
                v49 |= 0x20u;
                if ( (unsigned int)(v49 - 97) > 5 )
                  goto LABEL_12;
                v50 = 16 * v48 - 87;
              }
              else
              {
                v50 = 16 * v48 - 48;
              }
              v48 = v49 + v50;
              ++v47;
            }
            if ( (_BYTE)v49 == 45 )
            {
              BYTE9(v141) = v48;
              v51 = 0;
              v52 = &v44[v47 + 1];
              for ( m = 0; ; ++m )
              {
                v54 = &v52[m];
                if ( m >= 2 )
                  break;
                v55 = *v54;
                if ( (unsigned int)(v55 - 48) > 9 )
                {
                  v55 |= 0x20u;
                  if ( (unsigned int)(v55 - 97) > 5 )
                    goto LABEL_12;
                  v56 = 16 * v51 - 87;
                }
                else
                {
                  v56 = 16 * v51 - 48;
                }
                v51 = v55 + v56;
              }
              BYTE10(v141) = v51;
              v57 = 0;
              v58 = 0;
              while ( 1 )
              {
                v59 = &v54[v57];
                if ( v57 >= 2 )
                  break;
                v60 = *v59;
                if ( (unsigned int)(v60 - 48) > 9 )
                {
                  v60 |= 0x20u;
                  if ( (unsigned int)(v60 - 97) > 5 )
                    goto LABEL_12;
                  v61 = 16 * v58 - 87;
                }
                else
                {
                  v61 = 16 * v58 - 48;
                }
                v58 = v60 + v61;
                ++v57;
              }
              BYTE11(v141) = v58;
              v62 = 0;
              v63 = 0;
              while ( 1 )
              {
                v64 = &v59[v62];
                if ( v62 >= 2 )
                  break;
                v65 = *v64;
                if ( (unsigned int)(v65 - 48) > 9 )
                {
                  v65 |= 0x20u;
                  if ( (unsigned int)(v65 - 97) > 5 )
                    goto LABEL_12;
                  v66 = 16 * v63 - 87;
                }
                else
                {
                  v66 = 16 * v63 - 48;
                }
                v63 = v65 + v66;
                ++v62;
              }
              BYTE12(v141) = v63;
              v67 = 0;
              for ( n = 0; ; ++n )
              {
                v69 = &v64[n];
                if ( n >= 2 )
                  break;
                v70 = *v69;
                if ( (unsigned int)(v70 - 48) > 9 )
                {
                  v70 |= 0x20u;
                  if ( (unsigned int)(v70 - 97) > 5 )
                    goto LABEL_12;
                  v71 = 16 * v67 - 87;
                }
                else
                {
                  v71 = 16 * v67 - 48;
                }
                v67 = v70 + v71;
              }
              BYTE13(v141) = v67;
              v72 = 0;
              for ( ii = 0; ; ++ii )
              {
                v74 = &v69[ii];
                if ( ii >= 2 )
                  break;
                v75 = *v74;
                if ( (unsigned int)(v75 - 48) > 9 )
                {
                  v75 |= 0x20u;
                  if ( (unsigned int)(v75 - 97) > 5 )
                    goto LABEL_12;
                  v76 = 16 * v72 - 87;
                }
                else
                {
                  v76 = 16 * v72 - 48;
                }
                v72 = v75 + v76;
              }
              BYTE14(v141) = v72;
              v77 = 0;
              v78 = 0;
              while ( 1 )
              {
                v79 = v74[v77];
                if ( v77 >= 2 )
                  break;
                if ( (unsigned int)(v79 - 48) > 9 )
                {
                  v79 |= 0x20u;
                  if ( (unsigned int)(v79 - 97) > 5 )
                    goto LABEL_12;
                  v80 = 16 * v78 - 87;
                }
                else
                {
                  v80 = 16 * v78 - 48;
                }
                v78 = v79 + v80;
                ++v77;
              }
              if ( (_BYTE)v79 == 125 )
                HIBYTE(v141) = v78;
            }
          }
        }
      }
    }
LABEL_12:
    if ( g_Mem_lModuleInitCount > 0 )
    {
      v16 = *(_DWORD *)(a1 + 100);
      v17 = *(_DWORD *)(a1 + 4);
      ProcessHeap = GetProcessHeap();
      v19 = (char *)HeapAlloc(ProcessHeap, 8u, 0x40u);
      if ( v19 )
      {
        v8 = 0;
        *((_QWORD *)v19 + 4) = 0;
        *((_DWORD *)v19 + 1) = 0;
        *((_DWORD *)v19 + 7) = 0;
        v10 = v19;
        *(_OWORD *)(v19 + 40) = v141;
        *(_DWORD *)v19 = v16;
        *((_DWORD *)v19 + 2) = v22;
        *((_DWORD *)v19 + 6) = v17;
        goto LABEL_15;
      }
    }
    v8 = 14;
    v138 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v139 = 26;
LABEL_193:
      WPP_SF_d(v138[2], v139, WPP_e9479874f405377c737bad9289013c01_Traceguids, 14);
    }
  }
  else
  {
    v8 = 13;
    if ( *(_WORD *)a2 != 23 || (*(_DWORD *)(a1 + 92) & 0x100) == 0 )
      return v8;
    v9 = *(_BYTE **)(a1 + 16);
    v10 = 0;
    v140 = 0;
    if ( *v9 == 123 )
    {
      v11 = v9 + 1;
      v12 = 0;
      for ( jj = 0; ; ++jj )
      {
        v14 = (char)v11[jj];
        if ( jj >= 8 )
          break;
        if ( (unsigned int)(v14 - 48) > 9 )
        {
          v14 |= 0x20u;
          if ( (unsigned int)(v14 - 97) > 5 )
            goto LABEL_176;
          v15 = 16 * v12 - 87;
        }
        else
        {
          v15 = 16 * v12 - 48;
        }
        v12 = v14 + v15;
      }
      LODWORD(v140) = v12;
      if ( (_BYTE)v14 == 45 )
      {
        v81 = jj + 1;
        v82 = 0;
        v83 = 0;
        v84 = &v11[v81];
        while ( 1 )
        {
          v85 = (char)v84[v82];
          if ( v82 >= 4 )
            break;
          if ( (unsigned int)(v85 - 48) > 9 )
          {
            v85 |= 0x20u;
            if ( (unsigned int)(v85 - 97) > 5 )
              goto LABEL_176;
            v86 = 16 * v83 - 87;
          }
          else
          {
            v86 = 16 * v83 - 48;
          }
          v83 = v85 + v86;
          ++v82;
        }
        if ( (_BYTE)v85 == 45 )
        {
          v87 = v82 + 1;
          WORD2(v140) = v83;
          v88 = 0;
          v89 = &v84[v87];
          for ( kk = 0; ; ++kk )
          {
            v91 = (char)v89[kk];
            if ( kk >= 4 )
              break;
            if ( (unsigned int)(v91 - 48) > 9 )
            {
              v91 |= 0x20u;
              if ( (unsigned int)(v91 - 97) > 5 )
                goto LABEL_176;
              v92 = 16 * v88 - 87;
            }
            else
            {
              v92 = 16 * v88 - 48;
            }
            v88 = v91 + v92;
          }
          if ( (_BYTE)v91 == 45 )
          {
            WORD3(v140) = v88;
            v93 = 0;
            v94 = &v89[kk + 1];
            for ( mm = 0; ; ++mm )
            {
              v96 = &v94[mm];
              if ( mm >= 2 )
                break;
              v97 = *v96;
              if ( (unsigned int)(v97 - 48) > 9 )
              {
                v97 |= 0x20u;
                if ( (unsigned int)(v97 - 97) > 5 )
                  goto LABEL_176;
                v98 = 16 * v93 - 87;
              }
              else
              {
                v98 = 16 * v93 - 48;
              }
              v93 = v97 + v98;
            }
            BYTE8(v140) = v93;
            v99 = 0;
            v100 = 0;
            while ( 1 )
            {
              v101 = v96[v99];
              if ( v99 >= 2 )
                break;
              if ( (unsigned int)(v101 - 48) > 9 )
              {
                v101 |= 0x20u;
                if ( (unsigned int)(v101 - 97) > 5 )
                  goto LABEL_176;
                v102 = 16 * v100 - 87;
              }
              else
              {
                v102 = 16 * v100 - 48;
              }
              v100 = v101 + v102;
              ++v99;
            }
            if ( (_BYTE)v101 == 45 )
            {
              BYTE9(v140) = v100;
              v103 = 0;
              v104 = &v96[v99 + 1];
              for ( nn = 0; ; ++nn )
              {
                v106 = &v104[nn];
                if ( nn >= 2 )
                  break;
                v107 = *v106;
                if ( (unsigned int)(v107 - 48) > 9 )
                {
                  v107 |= 0x20u;
                  if ( (unsigned int)(v107 - 97) > 5 )
                    goto LABEL_176;
                  v108 = 16 * v103 - 87;
                }
                else
                {
                  v108 = 16 * v103 - 48;
                }
                v103 = v107 + v108;
              }
              BYTE10(v140) = v103;
              v109 = 0;
              v110 = 0;
              while ( 1 )
              {
                v111 = &v106[v109];
                if ( v109 >= 2 )
                  break;
                v112 = *v111;
                if ( (unsigned int)(v112 - 48) > 9 )
                {
                  v112 |= 0x20u;
                  if ( (unsigned int)(v112 - 97) > 5 )
                    goto LABEL_176;
                  v113 = 16 * v110 - 87;
                }
                else
                {
                  v113 = 16 * v110 - 48;
                }
                v110 = v112 + v113;
                ++v109;
              }
              BYTE11(v140) = v110;
              v114 = 0;
              v115 = 0;
              while ( 1 )
              {
                v116 = &v111[v114];
                if ( v114 >= 2 )
                  break;
                v117 = *v116;
                if ( (unsigned int)(v117 - 48) > 9 )
                {
                  v117 |= 0x20u;
                  if ( (unsigned int)(v117 - 97) > 5 )
                    goto LABEL_176;
                  v118 = 16 * v115 - 87;
                }
                else
                {
                  v118 = 16 * v115 - 48;
                }
                v115 = v117 + v118;
                ++v114;
              }
              BYTE12(v140) = v115;
              v119 = 0;
              for ( i1 = 0; ; ++i1 )
              {
                v121 = &v116[i1];
                if ( i1 >= 2 )
                  break;
                v122 = *v121;
                if ( (unsigned int)(v122 - 48) > 9 )
                {
                  v122 |= 0x20u;
                  if ( (unsigned int)(v122 - 97) > 5 )
                    goto LABEL_176;
                  v123 = 16 * v119 - 87;
                }
                else
                {
                  v123 = 16 * v119 - 48;
                }
                v119 = v122 + v123;
              }
              BYTE13(v140) = v119;
              v124 = 0;
              for ( i2 = 0; ; ++i2 )
              {
                v126 = &v121[i2];
                if ( i2 >= 2 )
                  break;
                v127 = *v126;
                if ( (unsigned int)(v127 - 48) > 9 )
                {
                  v127 |= 0x20u;
                  if ( (unsigned int)(v127 - 97) > 5 )
                    goto LABEL_176;
                  v128 = 16 * v124 - 87;
                }
                else
                {
                  v128 = 16 * v124 - 48;
                }
                v124 = v127 + v128;
              }
              BYTE14(v140) = v124;
              v129 = 0;
              v130 = 0;
              while ( 1 )
              {
                v131 = v126[v129];
                if ( v129 >= 2 )
                  break;
                if ( (unsigned int)(v131 - 48) > 9 )
                {
                  v131 |= 0x20u;
                  if ( (unsigned int)(v131 - 97) > 5 )
                    goto LABEL_176;
                  v132 = 16 * v130 - 87;
                }
                else
                {
                  v132 = 16 * v130 - 48;
                }
                v130 = v131 + v132;
                ++v129;
              }
              if ( (_BYTE)v131 == 125 )
                HIBYTE(v140) = v130;
            }
          }
        }
      }
    }
LABEL_176:
    if ( g_Mem_lModuleInitCount > 0 )
    {
      v133 = *(_DWORD *)(a1 + 100);
      v134 = *(_DWORD *)(a1 + 4);
      v135 = GetProcessHeap();
      v136 = (char *)HeapAlloc(v135, 8u, 0x40u);
      if ( v136 )
      {
        *((_QWORD *)v136 + 4) = 0;
        v8 = 0;
        *((_DWORD *)v136 + 7) = 0;
        v10 = v136;
        *((_DWORD *)v136 + 1) = 1;
        *(_DWORD *)v136 = v133;
        *((_DWORD *)v136 + 6) = v134;
        v137 = *(_OWORD *)(a2 + 8);
        *(_OWORD *)(v136 + 40) = v140;
        *(_OWORD *)(v136 + 8) = v137;
        goto LABEL_15;
      }
    }
    v8 = 14;
    v138 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v139 = 27;
      goto LABEL_193;
    }
  }
LABEL_15:
  if ( !v8 )
  {
    v20 = *a3;
    ++*a4;
    *((_QWORD *)v10 + 4) = v20;
    *a3 = (__int64)v10;
  }
  return v8;
}

```

## disassembly

```asm
0x180004c80  push    rbp
0x180004c82  push    rbx
0x180004c83  push    rsi
0x180004c84  push    rdi
0x180004c85  push    r12
0x180004c87  push    r13
0x180004c89  push    r14
0x180004c8b  push    r15
0x180004c8d  mov     rbp, rsp
0x180004c90  sub     rsp, 38h
0x180004c94  movzx   r10d, word ptr [rdx]
0x180004c98  mov     rsi, rcx
0x180004c9b  mov     ecx, 2
0x180004ca0  mov     r12, r9
0x180004ca3  mov     r13, r8
0x180004ca6  mov     r15, rdx
0x180004ca9  cmp     cx, r10w
0x180004cad  jz      loc_180004DA9
0x180004cb3  mov     ecx, 17h
0x180004cb8  mov     ebx, 0Dh
0x180004cbd  cmp     cx, r10w
0x180004cc1  jnz     loc_180004D96
0x180004cc7  test    dword ptr [rsi+5Ch], 100h
0x180004cce  jz      loc_180004D96
0x180004cd4  mov     rax, [rsi+10h]
0x180004cd8  xor     r14d, r14d
0x180004cdb  xorps   xmm0, xmm0
0x180004cde  movups  [rbp+var_18], xmm0
0x180004ce2  cmp     byte ptr [rax], 7Bh ; '{'
0x180004ce5  jnz     loc_1800054CE
0x180004ceb  lea     r9, [rax+1]
0x180004cef  mov     ecx, r14d
0x180004cf2  mov     edx, r14d
0x180004cf5  movsxd  rax, edx
0x180004cf8  movsx   r8d, byte ptr [rax+r9]
0x180004cfd  cmp     edx, 8
0x180004d00  jge     loc_180005187
0x180004d06  lea     eax, [r8-30h]
0x180004d0a  cmp     eax, 9
0x180004d0d  ja      loc_18000530B
0x180004d13  shl     ecx, 4
0x180004d16  add     ecx, 0FFFFFFD0h
0x180004d19  add     ecx, r8d
0x180004d1c  inc     edx
0x180004d1e  jmp     short loc_180004CF5
0x180004d20  cmp     dl, 7Dh ; '}'
0x180004d23  jnz     short loc_180004D29
0x180004d25  mov     byte ptr [rbp+var_18+0Fh], r8b
0x180004d29  cmp     cs:?g_Mem_lModuleInitCount@@3JA, r14d; long g_Mem_lModuleInitCount
0x180004d30  jle     loc_1800055A6
0x180004d36  mov     edi, [rsi+64h]
0x180004d39  mov     esi, [rsi+4]
0x180004d3c  call    cs:__imp_GetProcessHeap
0x180004d42  mov     edx, 8; dwFlags
0x180004d47  mov     r8d, 40h ; '@'; dwBytes
0x180004d4d  mov     rcx, rax; hHeap
0x180004d50  call    cs:__imp_HeapAlloc
0x180004d56  test    rax, rax
0x180004d59  jz      loc_1800055A6
0x180004d5f  movups  xmm0, [rbp+var_18]
0x180004d63  mov     ebx, r14d
0x180004d66  mov     [rax+20h], r14
0x180004d6a  mov     [rax+4], r14d
0x180004d6e  mov     [rax+1Ch], r14d
0x180004d72  mov     r14, rax
0x180004d75  movups  xmmword ptr [rax+28h], xmm0
0x180004d79  mov     [rax], edi
0x180004d7b  mov     [rax+8], r15d
0x180004d7f  mov     [rax+18h], esi
0x180004d82  test    ebx, ebx
0x180004d84  jnz     short loc_180004D96
0x180004d86  mov     rax, [r13+0]
0x180004d8a  inc     dword ptr [r12]
0x180004d8e  mov     [r14+20h], rax
0x180004d92  mov     [r13+0], r14
0x180004d96  mov     eax, ebx
0x180004d98  add     rsp, 38h
0x180004d9c  pop     r15
0x180004d9e  pop     r14
0x180004da0  pop     r13
0x180004da2  pop     r12
0x180004da4  pop     rdi
0x180004da5  pop     rsi
0x180004da6  pop     rbx
0x180004da7  pop     rbp
0x180004da8  retn
0x180004da9  test    byte ptr [rsi+5Ch], 80h
0x180004dad  jz      loc_180004CB3
0x180004db3  mov     r15d, [rdx+4]
0x180004db7  xorps   xmm0, xmm0
0x180004dba  movups  [rbp+var_18], xmm0
0x180004dbe  test    r15d, r15d
0x180004dc1  jz      loc_180005568
0x180004dc7  mov     rax, [rsi+10h]
0x180004dcb  xor     r14d, r14d
0x180004dce  cmp     byte ptr [rax], 7Bh ; '{'
0x180004dd1  jnz     loc_180004D29
0x180004dd7  lea     r9, [rax+1]
0x180004ddb  mov     ecx, r14d
0x180004dde  mov     edx, r14d
0x180004de1  movsxd  rax, edx
0x180004de4  movsx   r8d, byte ptr [rax+r9]
0x180004de9  cmp     edx, 8
0x180004dec  jge     short loc_180004E08
0x180004dee  lea     eax, [r8-30h]
0x180004df2  cmp     eax, 9
0x180004df5  ja      loc_180004F9B
0x180004dfb  shl     ecx, 4
0x180004dfe  add     ecx, 0FFFFFFD0h
0x180004e01  add     ecx, r8d
0x180004e04  inc     edx
0x180004e06  jmp     short loc_180004DE1
0x180004e08  mov     dword ptr [rbp+var_18], ecx
0x180004e0b  cmp     r8b, 2Dh ; '-'
0x180004e0f  jnz     loc_180004D29
0x180004e15  lea     eax, [rdx+1]
0x180004e18  mov     ecx, r14d
0x180004e1b  movsxd  r10, eax
0x180004e1e  mov     edx, r14d
0x180004e21  add     r10, r9
0x180004e24  nop     dword ptr [rax+00h]
0x180004e28  nop     dword ptr [rax+rax+00000000h]
0x180004e30  movsxd  rax, ecx
0x180004e33  movsx   r8d, byte ptr [rax+r10]
0x180004e38  cmp     ecx, 4
0x180004e3b  jge     short loc_180004E57
0x180004e3d  lea     eax, [r8-30h]
0x180004e41  cmp     eax, 9
0x180004e44  ja      loc_180004FB7
0x180004e4a  shl     edx, 4
0x180004e4d  add     edx, 0FFFFFFD0h
0x180004e50  add     edx, r8d
0x180004e53  inc     ecx
0x180004e55  jmp     short loc_180004E30
0x180004e57  cmp     r8b, 2Dh ; '-'
0x180004e5b  jnz     loc_180004D29
0x180004e61  lea     eax, [rcx+1]
0x180004e64  mov     word ptr [rbp+var_18+4], dx
0x180004e68  movsxd  r9, eax
0x180004e6b  mov     ecx, r14d
0x180004e6e  add     r9, r10
0x180004e71  mov     r8d, r14d
0x180004e74  nop     dword ptr [rax+00h]
0x180004e78  nop     dword ptr [rax+rax+00000000h]
0x180004e80  movsxd  rax, r8d
0x180004e83  movsx   edx, byte ptr [rax+r9]
0x180004e88  cmp     r8d, 4
0x180004e8c  jge     short loc_180004EA7
0x180004e8e  lea     eax, [rdx-30h]
0x180004e91  cmp     eax, 9
0x180004e94  ja      loc_180005009
0x180004e9a  shl     ecx, 4
0x180004e9d  add     ecx, 0FFFFFFD0h
0x180004ea0  add     ecx, edx
0x180004ea2  inc     r8d
0x180004ea5  jmp     short loc_180004E80
0x180004ea7  cmp     dl, 2Dh ; '-'
0x180004eaa  jnz     loc_180004D29
0x180004eb0  lea     eax, [r8+1]
0x180004eb4  mov     word ptr [rbp+var_18+6], cx
0x180004eb8  movsxd  r10, eax
0x180004ebb  mov     ecx, r14d
0x180004ebe  add     r10, r9
0x180004ec1  mov     edx, r14d
0x180004ec4  movsxd  r9, edx
0x180004ec7  add     r9, r10
0x180004eca  cmp     edx, 2
0x180004ecd  jge     short loc_180004EED
0x180004ecf  movsx   r8d, byte ptr [r9]
0x180004ed3  lea     eax, [r8-30h]
0x180004ed7  cmp     eax, 9
0x180004eda  ja      loc_180005023
0x180004ee0  shl     ecx, 4
0x180004ee3  add     ecx, 0FFFFFFD0h
0x180004ee6  add     ecx, r8d
0x180004ee9  inc     edx
0x180004eeb  jmp     short loc_180004EC4
0x180004eed  mov     byte ptr [rbp+var_18+8], cl
0x180004ef0  mov     r8d, r14d
0x180004ef3  mov     ecx, r14d
0x180004ef6  movsxd  rax, r8d
0x180004ef9  movsx   edx, byte ptr [rax+r9]
0x180004efe  cmp     r8d, 2
0x180004f02  jge     short loc_180004F1D
0x180004f04  lea     eax, [rdx-30h]
0x180004f07  cmp     eax, 9
0x180004f0a  ja      loc_18000503F
0x180004f10  shl     ecx, 4
0x180004f13  add     ecx, 0FFFFFFD0h
0x180004f16  add     ecx, edx
0x180004f18  inc     r8d
0x180004f1b  jmp     short loc_180004EF6
0x180004f1d  cmp     dl, 2Dh ; '-'
0x180004f20  jnz     loc_180004D29
0x180004f26  lea     eax, [r8+1]
0x180004f2a  mov     byte ptr [rbp+var_18+9], cl
0x180004f2d  movsxd  r10, eax
0x180004f30  mov     ecx, r14d
0x180004f33  add     r10, r9
0x180004f36  mov     edx, r14d
0x180004f39  nop     dword ptr [rax+00000000h]
0x180004f40  movsxd  r9, edx
0x180004f43  add     r9, r10
0x180004f46  cmp     edx, 2
0x180004f49  jge     short loc_180004F69
0x180004f4b  movsx   r8d, byte ptr [r9]
0x180004f4f  lea     eax, [r8-30h]
0x180004f53  cmp     eax, 9
0x180004f56  ja      loc_180005059
0x180004f5c  shl     ecx, 4
0x180004f5f  add     ecx, 0FFFFFFD0h
0x180004f62  add     ecx, r8d
0x180004f65  inc     edx
0x180004f67  jmp     short loc_180004F40
0x180004f69  mov     byte ptr [rbp+var_18+0Ah], cl
0x180004f6c  mov     edx, r14d
0x180004f6f  mov     ecx, r14d
0x180004f72  movsxd  r10, edx
0x180004f75  add     r10, r9
0x180004f78  cmp     edx, 2
0x180004f7b  jge     short loc_180004FD3
0x180004f7d  movsx   r8d, byte ptr [r10]
0x180004f81  lea     eax, [r8-30h]
0x180004f85  cmp     eax, 9
0x180004f88  ja      loc_180005075
0x180004f8e  shl     ecx, 4
0x180004f91  add     ecx, 0FFFFFFD0h
0x180004f94  add     ecx, r8d
0x180004f97  inc     edx
0x180004f99  jmp     short loc_180004F72
0x180004f9b  or      r8d, 20h
0x180004f9f  lea     eax, [r8-61h]
0x180004fa3  cmp     eax, 5
0x180004fa6  ja      loc_180004D29
0x180004fac  shl     ecx, 4
0x180004faf  add     ecx, 0FFFFFFA9h
0x180004fb2  jmp     loc_180004E01
0x180004fb7  or      r8d, 20h
0x180004fbb  lea     eax, [r8-61h]
0x180004fbf  cmp     eax, 5
0x180004fc2  ja      loc_180004D29
0x180004fc8  shl     edx, 4
0x180004fcb  add     edx, 0FFFFFFA9h
0x180004fce  jmp     loc_180004E50
0x180004fd3  mov     byte ptr [rbp+var_18+0Bh], cl
0x180004fd6  mov     edx, r14d
0x180004fd9  mov     ecx, r14d
0x180004fdc  movsxd  r8, edx
0x180004fdf  add     r8, r10
0x180004fe2  cmp     edx, 2
0x180004fe5  jge     loc_180005091
0x180004feb  movsx   r8d, byte ptr [r8]
0x180004fef  lea     eax, [r8-30h]
0x180004ff3  cmp     eax, 9
0x180004ff6  ja      loc_1800050BF
0x180004ffc  shl     ecx, 4
0x180004fff  add     ecx, 0FFFFFFD0h
0x180005002  add     ecx, r8d
0x180005005  inc     edx
0x180005007  jmp     short loc_180004FDC
0x180005009  or      edx, 20h
0x18000500c  lea     eax, [rdx-61h]
0x18000500f  cmp     eax, 5
0x180005012  ja      loc_180004D29
0x180005018  shl     ecx, 4
0x18000501b  add     ecx, 0FFFFFFA9h
0x18000501e  jmp     loc_180004EA0
0x180005023  or      r8d, 20h
0x180005027  lea     eax, [r8-61h]
0x18000502b  cmp     eax, 5
0x18000502e  ja      loc_180004D29
0x180005034  shl     ecx, 4
0x180005037  add     ecx, 0FFFFFFA9h
0x18000503a  jmp     loc_180004EE6
0x18000503f  or      edx, 20h
0x180005042  lea     eax, [rdx-61h]
0x180005045  cmp     eax, 5
0x180005048  ja      loc_180004D29
0x18000504e  shl     ecx, 4
0x180005051  add     ecx, 0FFFFFFA9h
0x180005054  jmp     loc_180004F16
0x180005059  or      r8d, 20h
0x18000505d  lea     eax, [r8-61h]
0x180005061  cmp     eax, 5
0x180005064  ja      loc_180004D29
0x18000506a  shl     ecx, 4
0x18000506d  add     ecx, 0FFFFFFA9h
0x180005070  jmp     loc_180004F62
0x180005075  or      r8d, 20h
0x180005079  lea     eax, [r8-61h]
0x18000507d  cmp     eax, 5
0x180005080  ja      loc_180004D29
0x180005086  shl     ecx, 4
0x180005089  add     ecx, 0FFFFFFA9h
0x18000508c  jmp     loc_180004F94
0x180005091  mov     byte ptr [rbp+var_18+0Ch], cl
0x180005094  mov     edx, r14d
0x180005097  mov     ecx, r14d
0x18000509a  movsxd  r9, ecx
0x18000509d  add     r9, r8
  ... truncated ...
```
