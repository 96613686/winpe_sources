# CopyEventInfo

- ea: `0x180006770`
- end: `0x180007465`
- name: `CopyEventInfo`
- size: `3317`
- prototype: `LPVOID __fastcall(_DWORD *Src, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004fb0`

## callees

- `0x180006770`
- `0x180011fe0`
- `0x180023b05`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006de3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800067aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006937`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006937`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006929`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006799`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006929`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LPVOID __fastcall CopyEventInfo(_DWORD *Src, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // r15
  HANDLE ProcessHeap; // rax
  LPVOID result; // rax
  __int64 v10; // r12
  int v11; // eax
  unsigned int v12; // eax
  _DWORD *v13; // rdi
  __int64 v14; // rsi
  unsigned __int64 v15; // rbx
  char *v16; // rdx
  __int64 v17; // rcx
  _WORD *v18; // rax
  int StringSize; // ebx
  _DWORD *v20; // r8
  unsigned int v21; // r9d
  __int64 v22; // rsi
  __int64 v23; // rbp
  char *v24; // rbp
  __int64 v25; // rax
  _WORD *v26; // rdx
  unsigned __int64 v27; // rbx
  _DWORD *v28; // rdi
  __int64 v29; // rcx
  _WORD *v30; // rax
  HANDLE v31; // rax
  __int64 v32; // rax
  _WORD *v33; // rdx
  _DWORD *v34; // rdi
  __int64 v35; // rcx
  _WORD *v36; // rax
  __int64 v37; // rdi
  _DWORD *v38; // r14
  unsigned __int64 v39; // rbx
  char *v40; // rdx
  __int64 v41; // rcx
  _WORD *v42; // rax
  HANDLE v43; // rax
  char *v44; // rdx
  unsigned __int64 v45; // rbx
  _DWORD *v46; // rdi
  __int64 v47; // rcx
  _WORD *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  char *v51; // rdx
  unsigned __int64 v52; // rbx
  _DWORD *v53; // rdi
  __int64 v54; // rcx
  _WORD *v55; // rax
  _WORD *v56; // rdx
  unsigned __int64 v57; // rbx
  _DWORD *v58; // rdi
  __int64 v59; // rcx
  _WORD *v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  _WORD *v63; // rdx
  _DWORD *v64; // rdi
  unsigned __int64 v65; // rbx
  __int64 v66; // rcx
  _WORD *v67; // rax
  __int64 v68; // rax
  _WORD *v69; // rdx
  _DWORD *v70; // rdi
  unsigned __int64 v71; // rbx
  __int64 v72; // rcx
  _WORD *v73; // rax
  int v74; // r11d
  unsigned int v75; // r15d
  HANDLE v76; // rax
  char *v77; // rax
  __int64 v78; // r8
  _WORD *v79; // r11
  unsigned int v80; // r14d
  __int64 i; // r10
  unsigned int v82; // ecx
  __int64 v83; // rdi
  unsigned __int64 v84; // r8
  __int64 v85; // rcx
  _WORD *v86; // r9
  _WORD *v87; // rcx
  __int64 v88; // rax
  _DWORD *v89; // rdi
  int v90; // r9d
  int v91; // r10d
  __int64 v92; // r8
  _DWORD *v93; // rbx
  unsigned int v94; // edi
  char *v95; // rdx
  __int64 v96; // rax
  _WORD *v97; // rdx
  _DWORD *v98; // rdi
  unsigned __int64 v99; // rbx
  __int64 v100; // rcx
  _WORD *v101; // rax
  __int64 v102; // rax
  _WORD *v103; // rdx
  _DWORD *v104; // rdi
  unsigned __int64 v105; // rbx
  __int64 v106; // rcx
  _WORD *v107; // rax
  unsigned __int64 v108; // rbx
  __int64 v109; // rax
  unsigned int v110; // [rsp+20h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-40h]

  v5 = a3;
  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 8u, a4);
  v10 = (__int64)result;
  if ( result )
  {
    v11 = Src[25];
    if ( v11 )
      v12 = 24 * v11 + 112;
    else
      v12 = 136;
    memcpy_0((void *)v10, Src, v12);
    v13 = (_DWORD *)(v10 + 52);
    *(_OWORD *)(v10 + 32) = *(_OWORD *)a2;
    if ( v10 == -52 )
    {
      StringSize = 87;
      goto LABEL_19;
    }
    v14 = (unsigned int)Src[13];
    if ( a4 < (unsigned int)v14 )
    {
      StringSize = 87;
      goto LABEL_19;
    }
    LODWORD(v15) = 0;
    v16 = (char *)Src + v14;
    if ( !(_DWORD *)((char *)Src + v14) )
      goto LABEL_240;
    v17 = 0x7FFFFFFF;
    v18 = (_WORD *)((char *)Src + v14);
    while ( *v18 )
    {
      ++v18;
      if ( !--v17 )
      {
        StringSize = 87;
        goto LABEL_19;
      }
    }
    v15 = 2 * (0x80000000LL - v17);
    if ( v15 > 0xFFFFFFFF )
    {
LABEL_247:
      StringSize = 534;
      goto LABEL_19;
    }
    if ( (_DWORD)v15 )
    {
      if ( a4 >= (int)v15 + (int)v14 )
        memcpy_0((void *)(v14 + v10), v16, (unsigned int)v15);
      *v13 = v14;
    }
    else
    {
LABEL_240:
      *v13 = 0;
      if ( !v16 )
      {
LABEL_71:
        if ( *((_BYTE *)Src + 36) == *(_BYTE *)(a2 + 4) )
        {
          v49 = (unsigned int)Src[14];
          if ( (_DWORD)v49 )
          {
            v44 = (char *)Src + v49;
            goto LABEL_74;
          }
        }
        else
        {
          v44 = *(char **)(v5 + 8);
          if ( v44 )
          {
            LODWORD(v45) = *(_DWORD *)(v5 + 596);
LABEL_75:
            v46 = (_DWORD *)(v10 + 56);
            if ( v10 == -56 )
            {
              StringSize = 87;
              goto LABEL_19;
            }
            if ( a4 < (unsigned int)v14 )
            {
              StringSize = 87;
              goto LABEL_19;
            }
            if ( !v44 )
              goto LABEL_64;
            if ( (_DWORD)v45 )
              goto LABEL_22;
            v47 = 0x7FFFFFFF;
            v48 = v44;
            while ( *v48 )
            {
              ++v48;
              if ( !--v47 )
              {
                StringSize = 87;
                goto LABEL_19;
              }
            }
            v45 = 2 * (0x80000000LL - v47);
            if ( v45 > 0xFFFFFFFF )
              goto LABEL_247;
            if ( (_DWORD)v45 )
            {
LABEL_22:
              if ( a4 >= (int)v45 + (int)v14 )
                memcpy_0((void *)(v10 + (unsigned int)v14), v44, (unsigned int)v45);
              *v46 = v14;
            }
            else
            {
LABEL_64:
              *v46 = 0;
              if ( !v44 )
              {
LABEL_26:
                if ( *((_BYTE *)Src + 35) == *(_BYTE *)(a2 + 3) )
                {
                  v25 = (unsigned int)Src[15];
                  if ( (_DWORD)v25 )
                  {
                    v26 = (_WORD *)((char *)Src + v25);
LABEL_29:
                    LODWORD(v27) = 0;
LABEL_30:
                    v28 = (_DWORD *)(v10 + 60);
                    if ( v10 != -60 && a4 >= (unsigned int)v14 )
                    {
                      if ( !v26 )
                        goto LABEL_195;
                      if ( (_DWORD)v27 )
                      {
LABEL_171:
                        if ( a4 >= (int)v27 + (int)v14 )
                          memcpy_0((void *)(v10 + (unsigned int)v14), v26, (unsigned int)v27);
                        *v28 = v14;
                        goto LABEL_174;
                      }
                      v29 = 0x7FFFFFFF;
                      v30 = v26;
                      while ( *v30 )
                      {
                        ++v30;
                        if ( !--v29 )
                          goto LABEL_37;
                      }
                      v27 = 2 * (0x80000000LL - v29);
                      if ( v27 <= 0xFFFFFFFF )
                      {
                        if ( (_DWORD)v27 )
                          goto LABEL_171;
LABEL_195:
                        *v28 = 0;
                        if ( !v26 )
                        {
LABEL_175:
                          if ( *((_QWORD *)Src + 5) == *(_QWORD *)(a2 + 8) )
                          {
                            v109 = (unsigned int)Src[16];
                            lpMem = 0;
                            if ( (_DWORD)v109 )
                              v24 = (char *)Src + v109;
                            else
                              v24 = 0;
                            v80 = 0;
                          }
                          else
                          {
                            v26 = (_WORD *)*(unsigned int *)(v5 + 860);
                            if ( !(_DWORD)v26 )
                              goto LABEL_177;
                            StringSize = 0;
                            v90 = 0;
                            v91 = 0;
                            v74 = 0;
                            v92 = 0;
                            if ( (unsigned int)v26 < 2 )
                              goto LABEL_151;
                            do
                            {
                              v90 += *(_DWORD *)(v5 + 4 * v92 + 604);
                              v91 += *(_DWORD *)(v5 + 4LL * (unsigned int)(v92 + 1) + 604);
                              v92 = (unsigned int)(v92 + 2);
                            }
                            while ( (unsigned int)v92 < (int)v26 - 1 );
                            if ( (unsigned int)v92 < (unsigned int)v26 )
LABEL_151:
                              v74 = *(_DWORD *)(v5 + 4 * v92 + 604);
                            if ( v74 + v91 + v90 )
                            {
                              v75 = v74 + v91 + v90 + 2;
                              v76 = GetProcessHeap();
                              v77 = (char *)HeapAlloc(v76, 8u, v75);
                              v24 = v77;
                              if ( !v77 )
                                return (LPVOID)v10;
                              v78 = a3;
                              v79 = v77;
                              v80 = v75;
                              for ( i = 0; ; i = (unsigned int)(i + 1) )
                              {
                                v82 = *(_DWORD *)(v78 + 860);
                                if ( (unsigned int)i >= v82 )
                                  break;
                                v26 = *(_WORD **)(v78 + 8 * i + 24);
                                if ( v26 )
                                {
                                  v83 = v78 + 4 * i;
                                  if ( *(_DWORD *)(v83 + 604) > 2u )
                                  {
                                    v84 = (unsigned __int64)v75 >> 1;
                                    if ( !v84 )
                                      goto LABEL_63;
                                    v85 = 2147483646;
                                    v86 = v79;
                                    do
                                    {
                                      if ( !v85 )
                                        break;
                                      if ( !*v26 )
                                        break;
                                      *v86++ = *v26++;
                                      --v85;
                                      --v84;
                                    }
                                    while ( v84 );
                                    v87 = v86 - 1;
                                    if ( v84 )
                                      v87 = v86;
                                    *v87 = 0;
                                    if ( !v84 )
                                      goto LABEL_63;
                                    v88 = *(unsigned int *)(v83 + 604);
                                    v78 = a3;
                                    v75 -= v88;
                                    v79 = (_WORD *)((char *)v79 + v88);
                                  }
                                }
                              }
                              v5 = a3;
                              if ( v82 )
                                *v79 = 0;
                            }
                            else
                            {
LABEL_177:
                              v24 = 0;
                              v80 = 0;
                            }
                            lpMem = v24;
                          }
                          v89 = (_DWORD *)(v10 + 64);
                          v110 = v80;
                          if ( v10 == -64 )
                            goto LABEL_301;
                          v21 = a4;
                          if ( a4 < (unsigned int)v14 )
                            goto LABEL_301;
                          if ( !v24 )
                            goto LABEL_242;
                          if ( !v80 )
                          {
                            LOBYTE(v26) = 1;
                            StringSize = TdhpGetStringSize(v24, v26, &v110);
                            if ( StringSize )
                              goto LABEL_18;
                            v80 = v110;
                            v21 = a4;
                            if ( !v110 )
                              goto LABEL_242;
                          }
                          if ( v21 >= v80 + (unsigned int)v14 )
                          {
                            memcpy_0((void *)(v10 + (unsigned int)v14), v24, v80);
                            v21 = a4;
                          }
                          if ( v80 )
                          {
                            *v89 = v14;
                          }
                          else
                          {
LABEL_242:
                            *v89 = 0;
                            if ( !v24 )
                            {
LABEL_188:
                              v20 = Src;
                              if ( *((_WORD *)Src + 19) == *(_WORD *)(a2 + 6) )
                              {
                                v50 = (unsigned int)Src[17];
                                if ( (_DWORD)v50 )
                                {
                                  v51 = (char *)Src + v50;
                                  goto LABEL_87;
                                }
                              }
                              else
                              {
                                v51 = *(char **)(v5 + 536);
                                if ( v51 )
                                {
                                  LODWORD(v52) = *(_DWORD *)(v5 + 864);
                                  goto LABEL_88;
                                }
                              }
                              v51 = 0;
LABEL_87:
                              LODWORD(v52) = 0;
LABEL_88:
                              v53 = (_DWORD *)(v10 + 68);
                              if ( v10 == -68 || v21 < (unsigned int)v14 )
                                goto LABEL_301;
                              if ( !v51 )
                                goto LABEL_117;
                              if ( (_DWORD)v52 )
                                goto LABEL_98;
                              v54 = 0x7FFFFFFF;
                              v55 = v51;
                              while ( *v55 )
                              {
                                ++v55;
                                if ( !--v54 )
                                {
LABEL_60:
                                  StringSize = 87;
                                  goto LABEL_18;
                                }
                              }
                              v52 = 2 * (0x80000000LL - v54);
                              if ( v52 > 0xFFFFFFFF )
                                goto LABEL_237;
                              if ( (_DWORD)v52 )
                              {
LABEL_98:
                                if ( v21 >= (int)v52 + (int)v14 )
                                {
                                  memcpy_0((void *)(v10 + (unsigned int)v14), v51, (unsigned int)v52);
                                  v20 = Src;
                                  v21 = a4;
                                }
                                *v53 = v14;
                              }
                              else
                              {
LABEL_117:
                                *v53 = 0;
                                if ( !v51 )
                                  goto LABEL_102;
                              }
                              LODWORD(v14) = v52 + v14;
LABEL_102:
                              if ( *((_WORD *)v20 + 19) == *(_WORD *)(a2 + 6)
                                && *((_BYTE *)v20 + 37) == *(_BYTE *)(a2 + 5) )
                              {
                                v61 = (unsigned int)v20[18];
                                if ( (_DWORD)v61 )
                                {
                                  v56 = (_WORD *)((char *)v20 + v61);
                                  LODWORD(v57) = 0;
                                  goto LABEL_105;
                                }
                              }
                              else
                              {
                                v56 = *(_WORD **)(v5 + 544);
                                if ( v56 )
                                {
                                  LODWORD(v57) = *(_DWORD *)(v5 + 868);
LABEL_105:
                                  v58 = (_DWORD *)(v10 + 72);
                                  if ( v10 == -72 || v21 < (unsigned int)v14 )
                                    goto LABEL_301;
                                  if ( !v56 )
                                    goto LABEL_134;
                                  if ( (_DWORD)v57 )
                                    goto LABEL_120;
                                  v59 = 0x7FFFFFFF;
                                  v60 = v56;
                                  while ( *v60 )
                                  {
                                    ++v60;
                                    if ( !--v59 )
                                    {
                                      StringSize = 87;
                                      goto LABEL_18;
                                    }
                                  }
                                  v57 = 2 * (0x80000000LL - v59);
                                  if ( v57 > 0xFFFFFFFF )
                                  {
                                    StringSize = 534;
                                    goto LABEL_18;
                                  }
                                  if ( (_DWORD)v57 )
                                  {
LABEL_120:
                                    if ( v21 >= (int)v57 + (int)v14 )
                                    {
                                      memcpy_0((void *)(v10 + (unsigned int)v14), v56, (unsigned int)v57);
                                      v20 = Src;
                                      v21 = a4;
                                    }
                                    *v58 = v14;
                                  }
                                  else
                                  {
LABEL_134:
                                    *v58 = 0;
                                    if ( !v56 )
                                    {
LABEL_124:
                                      v62 = (unsigned int)v20[19];
                                      if ( (_DWORD)v62 )
                                        v63 = (_WORD *)((char *)v20 + v62);
                                      else
                                        v63 = 0;
                                      v64 = (_DWORD *)(v10 + 76);
                                      if ( v10 == -76 || v21 < (unsigned int)v14 )
                                        goto LABEL_301;
                                      LODWORD(v65) = 0;
                                      if ( !v63 )
                                        goto LABEL_244;
                                      v66 = 0x7FFFFFFF;
                                      v67 = v63;
                                      while ( *v67 )
                                      {
                                        ++v67;
                                        if ( !--v66 )
                                        {
                                          StringSize = 87;
                                          goto LABEL_18;
                                        }
                                      }
                                      v65 = 2 * (0x80000000LL - v66);
                                      if ( v65 > 0xFFFFFFFF )
                                        goto LABEL_237;
                                      if ( (_DWORD)v65 )
                                      {
                                        if ( v21 >= (int)v65 + (int)v14 )
                                        {
                                          memcpy_0((void *)(v10 + (unsigned int)v14), v63, (unsigned int)v65);
                                          v20 = Src;
                                          v21 = a4;
                                        }
                                        *v64 = v14;
                                      }
                                      else
                                      {
LABEL_244:
                                        *v64 = 0;
                                        if ( !v63 )
                                        {
LABEL_141:
                                          v68 = (unsigned int)v20[20];
                                          if ( (_DWORD)v68 )
                                            v69 = (_WORD *)((char *)v20 + v68);
                                          else
                                            v69 = 0;
                                          v70 = (_DWORD *)(v10 + 80);
                                          if ( v10 == -80 || v21 < (unsigned int)v14 )
                                            goto LABEL_301;
                                          LODWORD(v71) = 0;
                                          if ( !v69 )
                                            goto LABEL_267;
                                          v72 = 0x7FFFFFFF;
                                          v73 = v69;
                                          while ( *v73 )
                                          {
                                            ++v73;
                                            if ( !--v72 )
                                            {
                                              StringSize = 87;
                                              goto LABEL_18;
                                            }
                                          }
                                          v71 = 2 * (0x80000000LL - v72);
                                          if ( v71 > 0xFFFFFFFF )
                                            goto LABEL_237;
                                          if ( (_DWORD)v71 )
                                          {
                                            if ( v21 >= (int)v71 + (int)v14 )
                                            {
                                              memcpy_0((void *)(v10 + (unsigned int)v14), v69, (unsigned int)v71);
                                              v20 = Src;
                                              v21 = a4;
                                            }
                                            *v70 = v14;
                                          }
                                          else
                                          {
LABEL_267:
                                            *v70 = 0;
                                            if ( !v69 )
                                              goto LABEL_202;
                                          }
                                          LODWORD(v14) = v71 + v14;
LABEL_202:
                                          v93 = (_DWORD *)(v10 + 84);
                                          if ( v10 == -84 || v21 < (unsigned int)v14 )
                                            goto LABEL_301;
                                          v94 = v20[22];
                                          v95 = (char *)v20 + (unsigned int)v20[21];
                                          if ( v95 && v94 )
                                          {
                                            if ( v21 >= (unsigned int)v14 + v94 )
                                            {
                                              memcpy_0((void *)(v10 + (unsigned int)v14), v95, v94);
                                              v20 = Src;
                                              v21 = a4;
                                            }
                                            *v93 = v14;
                                          }
                                          else
                                          {
                                            *v93 = 0;
                                            if ( !v95 )
                                            {
LABEL_210:
                                              *(_DWORD *)(v10 + 88) = v20[22];
                                              v22 = ((_DWORD)v14 + 1) & 0xFFFFFFFE;
                                              v96 = (unsigned int)v20[23];
                                              if ( (_DWORD)v96 )
                                                v97 = (_WORD *)((char *)v20 + v96);
                                              else
                                                v97 = 0;
                                              v98 = (_DWORD *)(v10 + 92);
                                              if ( v10 != -92 && v21 >= (unsigned int)v22 )
                                              {
                                                LODWORD(v99) = 0;
                                                if ( !v97 )
                                                  goto LABEL_273;
                                                v100 = 0x7FFFFFFF;
                                                v101 = v97;
                                                while ( *v101 )
                                                {
                                                  ++v101;
                                                  if ( !--v100 )
                                                  {
                                                    StringSize = 87;
                                                    goto LABEL_18;
                                                  }
                                                }
                                                v99 = 2 * (0x80000000LL - v100);
                                                if ( v99 > 0xFFFFFFFF )
                                                  goto LABEL_237;
                                                if ( (_DWORD)v99 )
                                                {
                                                  if ( v21 >= (int)v99 + (int)v22 )
                                                  {
                                                    memcpy_0((void *)(v10 + v22), v97, (unsigned int)v99);
                                                    v20 = Src;
                                                    v21 = a4;
                                                  }
                                                  *v98 = v22;
                                                }
                                                else
                                                {
LABEL_273:
                                                  *v98 = 0;
                                                  if ( !v97 )
                                                  {
LABEL_226:
                                                    v102 = (unsigned int)v20[24];
                                                    if ( (_DWORD)v102 )
                                                      v103 = (_WORD *)((char *)v20 + v102);
                                                    else
                                                      v103 = 0;
                                                    v104 = (_DWORD *)(v10 + 96);
                                                    if ( v10 != -96 && v21 >= (unsigned int)v22 )
                                                    {
                                                      LODWORD(v105) = 0;
                                                      if ( !v103 )
                                                        goto LABEL_275;
                                                      v106 = 0x7FFFFFFF;
                                                      v107 = v103;
                                                      while ( *v107 )
                                                      {
                                                        ++v107;
                                                        if ( !--v106 )
                                                        {
                                                          StringSize = 87;
                                                          goto LABEL_18;
                                                        }
                                                      }
                                                      v105 = 2 * (0x80000000LL - v106);
                                                      if ( v105 <= 0xFFFFFFFF )
                                                      {
                                                        if ( (_DWORD)v105 )
                                                        {
                                                          if ( v21 >= (int)v105 + (int)v22 )
                                                          {
                                                            memcpy_0(
                                                              (void *)(v10 + (unsigned int)v22),
                                                              v103,
                                                              (unsigned int)v105);
                                                            v20 = Src;
                                                            v21 = a4;
                                                          }
                                                          *v104 = v22;
                                                          goto LABEL_52;
                                                        }
LABEL_275:
                                                        *v104 = 0;
                                                        if ( !v103 )
                                                        {
LABEL_53:
                                                          v23 = 0;
                                                          StringSize = 0;
                                                          if ( !*(_DWORD *)(v10 + 100) )
                                                            goto LABEL_18;
                                                          while ( 1 )
                                                          {
                                                            v37 = 6 * v23;
                                                            v38 = (_DWORD *)(24 * v23 + v10 + 116);
                                                            if ( !v38 || v21 < (unsigned int)v22 )
                                                              goto LABEL_301;
                                                            LODWORD(v39) = 0;
                                                            v40 = (char *)v20 + (unsigned int)v20[v37 + 29];
                                                            if ( v40 )
                                                            {
                                                              v41 = 0x7FFFFFFF;
                                                              v42 = (_WORD *)((char *)v20 + (unsigned int)v20[v37 + 29]);
                                                              while ( *v42 )
                                                              {
                                                                ++v42;
                                                                if ( !--v41 )
                                                                  goto LABEL_60;
                                                              }
                                                              v39 = 2 * (0x80000000LL - v41);
                                                              if ( v39 > 0xFFFFFFFF )
                                                                goto LABEL_237;
                                                              if ( (_DWORD)v39 )
                                                                break;
                                                            }
                                                            *v38 = 0;
                                                            if ( v40 )
                                                              goto LABEL_15;
LABEL_16:
                                                            if ( (v20[v37 + 28] & 1) != 0 )
                                                              goto LABEL_17;
                                                            v32 = (unsigned int)v20[v37 + 31];
                                                            if ( (_DWORD)v32 )
                                                              v33 = (_WORD *)((char *)v20 + v32);
                                                            else
                                                              v33 = 0;
                                                            v34 = (_DWORD *)(v10 + v37 * 4 + 124);
                                                            if ( !v34 || v21 < (unsigned int)v22 )
                                                              goto LABEL_301;
                                                            if ( v33 )
                                                            {
                                                              v35 = 0x7FFFFFFF;
                                                              v36 = v33;
                                                              while ( *v36 )
                                                              {
                                                                ++v36;
                                                                if ( !--v35 )
                                                                {
                                                                  StringSize = 87;
                                                                  goto LABEL_18;
                                                                }
                                                              }
                                                              v108 = 2 * (0x80000000LL - v35);
                                                              if ( v108 > 0xFFFFFFFF )
                                                                goto LABEL_237;
                                                              if ( (_DWORD)v108 )
                                                              {
                                                                if ( v21 >= (int)v108 + (int)v22 )
                                                                {
                                                                  memcpy_0(
                                                                    (void *)(v10 + (unsigned int)v22),
                                                                    v33,
                                                                    (unsigned int)v108);
                                                                  v21 = a4;
                                                                }
                                                                *v34 = v22;
LABEL_252:
                                                                LODWORD(v22) = v108 + v22;
                                                                goto LABEL_17;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              LODWORD(v108) = 0;
                                                            }
                                                            *v34 = 0;
                                                            if ( v33 )
                                                              goto LABEL_252;
LABEL_17:
                                                            StringSize = 0;
                                                            v23 = (unsigned int)(v23 + 1);
                                                            if ( (unsigned int)v23 >= *(_DWORD *)(v10 + 100) )
                                                              goto LABEL_18;
                                                            v20 = Src;
                                                          }
                                                          if ( v21 >= (int)v39 + (int)v22 )
                                                          {
                                                            memcpy_0(
                                                              (void *)(v10 + (unsigned int)v22),
                                                              v40,
                                                              (unsigned int)v39);
                                                            v20 = Src;
                                                            v21 = a4;
                                                          }
                                                          *v38 = v22;
LABEL_15:
                                                          LODWORD(v22) = v39 + v22;
                                                          goto LABEL_16;
                                                        }
LABEL_52:
                                                        LODWORD(v22) = v105 + v22;
                                                        goto LABEL_53;
                                                      }
LABEL_237:
                                                      StringSize = 534;
                                                      goto LABEL_18;
                                                    }
                                                    goto LABEL_301;
                                                  }
                                                }
                                                LODWORD(v22) = v99 + v22;
                                                goto LABEL_226;
                                              }
LABEL_301:
                                              StringSize = 87;
LABEL_18:
                                              v24 = (char *)lpMem;
                                              if ( lpMem )
                                              {
LABEL_63:
                                                v43 = GetProcessHeap();
                                                HeapFree(v43, 0, v24);
                                              }
LABEL_19:
                                              if ( !StringSize )
                                                return (LPVOID)v10;
                                              goto LABEL_37;
                                            }
                                          }
                                          LODWORD(v14) = v94 + v14;
                                          goto LABEL_210;
                                        }
                                      }
                                      LODWORD(v14) = v65 + v14;
                                      goto LABEL_141;
                                    }
                                  }
                                  LODWORD(v14) = v57 + v14;
                                  goto LABEL_124;
                                }
                              }
                              v56 = 0;
                              LODWORD(v57) = 0;
                              goto LABEL_105;
                            }
                          }
                          LODWORD(v14) = v80 + v14;
                          goto LABEL_188;
                        }
LABEL_174:
                        LODWORD(v14) = v27 + v14;
                        goto LABEL_175;
                      }
                    }
LABEL_37:
                    v31 = GetProcessHeap();
                    HeapFree(v31, 0, (LPVOID)v10);
                    return 0;
                  }
                }
                else
                {
                  v26 = *(_WORD **)(v5 + 16);
                  if ( v26 )
                  {
                    LODWORD(v27) = *(_DWORD *)(v5 + 600);
                    goto LABEL_30;
                  }
                }
                v26 = 0;
                goto LABEL_29;
              }
            }
            LODWORD(v14) = v45 + v14;
            goto LABEL_26;
          }
        }
        v44 = 0;
LABEL_74:
        LODWORD(v45) = 0;
        goto LABEL_75;
      }
    }
    LODWORD(v14) = v15 + v14;
    goto LABEL_71;
  }
  return result;
}

```

## disassembly

```asm
0x180006770  mov     [rsp+arg_18], r9d
0x180006775  mov     [rsp+arg_10], r8
0x18000677a  mov     [rsp+arg_0], rcx
0x18000677f  push    rbx
0x180006780  push    rbp
0x180006781  push    r12
0x180006783  push    r13
0x180006785  push    r14
0x180006787  push    r15
0x180006789  sub     rsp, 38h
0x18000678d  mov     ebp, r9d
0x180006790  mov     r15, r8
0x180006793  mov     r13, rdx
0x180006796  mov     r14, rcx
0x180006799  call    cs:__imp_GetProcessHeap
0x18000679f  mov     r8d, ebp; dwBytes
0x1800067a2  mov     edx, 8; dwFlags
0x1800067a7  mov     rcx, rax; hHeap
0x1800067aa  call    cs:__imp_HeapAlloc
0x1800067b0  mov     r12, rax
0x1800067b3  test    rax, rax
0x1800067b6  jz      loc_180007385
0x1800067bc  mov     eax, [r14+64h]
0x1800067c0  mov     [rsp+68h+var_38], rdi
0x1800067c5  test    eax, eax
0x1800067c7  jz      loc_180006A6E
0x1800067cd  lea     eax, [rax+rax*2]
0x1800067d0  lea     eax, ds:70h[rax*8]
0x1800067d7  mov     r8d, eax; Size
0x1800067da  mov     rdx, r14; Src
0x1800067dd  mov     rcx, r12; void *
0x1800067e0  mov     [rsp+68h+arg_8], rsi
0x1800067e5  call    memcpy_0
0x1800067ea  movups  xmm0, xmmword ptr [r13+0]
0x1800067ef  lea     rdi, [r12+34h]
0x1800067f4  movups  xmmword ptr [r12+20h], xmm0
0x1800067fa  test    rdi, rdi
0x1800067fd  jz      loc_18000738A
0x180006803  mov     esi, [r14+34h]
0x180006807  cmp     ebp, esi
0x180006809  jb      loc_180007394
0x18000680f  xor     ebx, ebx
0x180006811  lea     rdx, [rsi+r14]; Src
0x180006815  test    rdx, rdx
0x180006818  jz      loc_18000739E
0x18000681e  mov     ecx, 7FFFFFFFh
0x180006823  mov     rax, rdx
0x180006826  cmp     [rax], bx
0x180006829  jz      loc_1800071DB
0x18000682f  add     rax, 2
0x180006833  sub     rcx, 1
0x180006837  jnz     short loc_180006826
0x180006839  xor     eax, eax
0x18000683b  mov     ebx, 57h ; 'W'
0x180006840  test    rcx, rcx
0x180006843  cmovnz  ebx, eax
0x180006846  jmp     short loc_1800068A0
0x180006848  test    ebx, ebx
0x18000684a  jz      loc_18000718A
0x180006850  lea     eax, [rbx+rsi]
0x180006853  cmp     r9d, eax
0x180006856  jb      short loc_180006872
0x180006858  mov     ecx, esi
0x18000685a  add     rcx, r12; void *
0x18000685d  mov     r8d, ebx; Size
0x180006860  call    memcpy_0
0x180006865  mov     r8, [rsp+68h+arg_0]
0x18000686a  mov     r9d, [rsp+68h+arg_18]
0x180006872  mov     [r14], esi
0x180006875  add     esi, ebx
0x180006877  test    byte ptr [rdi+r8+70h], 1
0x18000687d  jz      loc_18000695C
0x180006883  xor     ebx, ebx
0x180006885  inc     ebp
0x180006887  cmp     ebp, [r12+64h]
0x18000688c  jb      loc_180007451
0x180006892  mov     rbp, [rsp+68h+lpMem]
0x180006897  test    rbp, rbp
0x18000689a  jnz     loc_180006A78
0x1800068a0  test    ebx, ebx
0x1800068a2  jnz     loc_180006929
0x1800068a8  jmp     loc_180006940
0x1800068ad  test    ebx, ebx
0x1800068af  jz      loc_180006A91
0x1800068b5  lea     eax, [rbx+rsi]
0x1800068b8  cmp     ebp, eax
0x1800068ba  jb      short loc_1800068C9
0x1800068bc  mov     ecx, esi
0x1800068be  add     rcx, r12; void *
0x1800068c1  mov     r8d, ebx; Size
0x1800068c4  call    memcpy_0
0x1800068c9  mov     [rdi], esi
0x1800068cb  add     esi, ebx
0x1800068cd  movzx   eax, byte ptr [r13+3]
0x1800068d2  cmp     [r14+23h], al
0x1800068d6  jnz     loc_1800073CF
0x1800068dc  mov     eax, [r14+3Ch]
0x1800068e0  test    eax, eax
0x1800068e2  jz      loc_180006A67
0x1800068e8  lea     rdx, [r14+rax]; Src
0x1800068ec  xor     ebx, ebx
0x1800068ee  lea     rdi, [r12+3Ch]
0x1800068f3  test    rdi, rdi
0x1800068f6  jz      short loc_180006929
0x1800068f8  cmp     ebp, esi
0x1800068fa  jb      short loc_180006929
0x1800068fc  test    rdx, rdx
0x1800068ff  jz      loc_180006FCE
0x180006905  test    ebx, ebx
0x180006907  jnz     loc_180006EB4
0x18000690d  mov     ecx, 7FFFFFFFh
0x180006912  mov     rax, rdx
0x180006915  cmp     word ptr [rax], 0
0x180006919  jz      loc_18000726B
0x18000691f  add     rax, 2
0x180006923  sub     rcx, 1
0x180006927  jnz     short loc_180006915
0x180006929  call    cs:__imp_GetProcessHeap
0x18000692f  mov     r8, r12; lpMem
0x180006932  xor     edx, edx; dwFlags
0x180006934  mov     rcx, rax; hHeap
0x180006937  call    cs:__imp_HeapFree
0x18000693d  xor     r12d, r12d
0x180006940  mov     rdi, [rsp+68h+var_38]
0x180006945  mov     rax, r12
0x180006948  mov     rsi, [rsp+68h+arg_8]
0x18000694d  add     rsp, 38h
0x180006951  pop     r15
0x180006953  pop     r14
0x180006955  pop     r13
0x180006957  pop     r12
0x180006959  pop     rbp
0x18000695a  pop     rbx
0x18000695b  retn
0x18000695c  mov     eax, [rdi+r8+7Ch]
0x180006961  test    eax, eax
0x180006963  jnz     loc_180007441
0x180006969  xor     edx, edx; Src
0x18000696b  add     rdi, 7Ch ; '|'
0x18000696f  add     rdi, r12
0x180006972  jz      loc_18000745B
0x180006978  cmp     r9d, esi
0x18000697b  jb      loc_18000745B
0x180006981  test    rdx, rdx
0x180006984  jz      loc_18000744A
0x18000698a  mov     ecx, 7FFFFFFFh
0x18000698f  mov     rax, rdx
0x180006992  cmp     word ptr [rax], 0
0x180006996  jz      loc_180007301
0x18000699c  add     rax, 2
0x1800069a0  sub     rcx, 1
0x1800069a4  jnz     short loc_180006992
0x1800069a6  xor     eax, eax
0x1800069a8  mov     ebx, 57h ; 'W'
0x1800069ad  test    rcx, rcx
0x1800069b0  cmovnz  ebx, eax
0x1800069b3  jmp     loc_180006892
0x1800069b8  test    ebx, ebx
0x1800069ba  jz      loc_180007343
0x1800069c0  lea     eax, [rbx+rsi]
0x1800069c3  cmp     r9d, eax
0x1800069c6  jb      short loc_1800069E2
0x1800069c8  mov     ecx, esi
0x1800069ca  add     rcx, r12; void *
0x1800069cd  mov     r8d, ebx; Size
0x1800069d0  call    memcpy_0
0x1800069d5  mov     r8, [rsp+68h+arg_0]
0x1800069da  mov     r9d, [rsp+68h+arg_18]
0x1800069e2  mov     [rdi], esi
0x1800069e4  add     esi, ebx
0x1800069e6  xor     ebp, ebp
0x1800069e8  xor     ebx, ebx
0x1800069ea  cmp     [r12+64h], ebx
0x1800069ef  jbe     loc_180006892
0x1800069f5  nop     word ptr [rax+rax+00000000h]
0x180006a00  lea     rcx, ds:0[rbp*2]
0x180006a08  add     rcx, rbp
0x180006a0b  lea     r14, [r12+74h]
0x180006a10  lea     rdi, ds:0[rcx*8]
0x180006a18  add     r14, rdi
0x180006a1b  jz      loc_18000745B
0x180006a21  cmp     r9d, esi
0x180006a24  jb      loc_18000745B
0x180006a2a  mov     edx, [rdi+r8+74h]
0x180006a2f  xor     ebx, ebx
0x180006a31  add     rdx, r8; Src
0x180006a34  jz      loc_18000718A
0x180006a3a  mov     ecx, 7FFFFFFFh
0x180006a3f  mov     rax, rdx
0x180006a42  cmp     [rax], bx
0x180006a45  jz      loc_18000716E
0x180006a4b  add     rax, 2
0x180006a4f  sub     rcx, 1
0x180006a53  jnz     short loc_180006A42
0x180006a55  xor     eax, eax
0x180006a57  mov     ebx, 57h ; 'W'
0x180006a5c  test    rcx, rcx
0x180006a5f  cmovnz  ebx, eax
0x180006a62  jmp     loc_180006892
0x180006a67  xor     edx, edx
0x180006a69  jmp     loc_1800068EC
0x180006a6e  mov     eax, 88h
0x180006a73  jmp     loc_1800067D7
0x180006a78  call    cs:__imp_GetProcessHeap
0x180006a7e  mov     r8, rbp; lpMem
0x180006a81  xor     edx, edx; dwFlags
0x180006a83  mov     rcx, rax; hHeap
0x180006a86  call    cs:__imp_HeapFree
0x180006a8c  jmp     loc_1800068A0
0x180006a91  mov     dword ptr [rdi], 0
0x180006a97  test    rdx, rdx
0x180006a9a  jnz     loc_1800068CB
0x180006aa0  jmp     loc_1800068CD
0x180006aa5  test    ebx, ebx
0x180006aa7  jz      loc_18000719F
0x180006aad  lea     eax, [rbx+rsi]
0x180006ab0  cmp     ebp, eax
0x180006ab2  jb      short loc_180006ACC
0x180006ab4  mov     r8d, ebx; Size
0x180006ab7  lea     rcx, [rsi+r12]; void *
0x180006abb  call    memcpy_0
0x180006ac0  mov     r8d, 80000000h
0x180006ac6  mov     r10d, 0FFFFFFFFh
0x180006acc  mov     [rdi], esi
0x180006ace  add     esi, ebx
0x180006ad0  movzx   eax, byte ptr [r13+4]
0x180006ad5  cmp     [r14+24h], al
0x180006ad9  jz      short loc_180006B46
0x180006adb  mov     rdx, [r15+8]
0x180006adf  test    rdx, rdx
0x180006ae2  jnz     loc_1800073AF
0x180006ae8  xor     edx, edx; Src
0x180006aea  xor     ebx, ebx
0x180006aec  lea     rdi, [r12+38h]
0x180006af1  test    rdi, rdi
0x180006af4  jz      loc_1800073BB
0x180006afa  cmp     ebp, esi
0x180006afc  jb      loc_1800073C5
0x180006b02  test    rdx, rdx
0x180006b05  jz      short loc_180006A91
0x180006b07  test    ebx, ebx
0x180006b09  jnz     loc_1800068B5
0x180006b0f  mov     ecx, 7FFFFFFFh
0x180006b14  mov     rax, rdx
0x180006b17  nop     word ptr [rax+rax+00000000h]
0x180006b20  cmp     word ptr [rax], 0
0x180006b24  jz      loc_180007258
0x180006b2a  add     rax, 2
0x180006b2e  sub     rcx, 1
0x180006b32  jnz     short loc_180006B20
0x180006b34  xor     eax, eax
0x180006b36  mov     ebx, 57h ; 'W'
0x180006b3b  test    rcx, rcx
0x180006b3e  cmovnz  ebx, eax
0x180006b41  jmp     loc_1800068A0
0x180006b46  mov     eax, [r14+38h]
0x180006b4a  test    eax, eax
0x180006b4c  jz      short loc_180006AE8
0x180006b4e  lea     rdx, [r14+rax]
0x180006b52  jmp     short loc_180006AEA
0x180006b54  mov     eax, [r8+44h]
0x180006b58  test    eax, eax
0x180006b5a  jnz     short loc_180006BA9
0x180006b5c  xor     edx, edx; Src
0x180006b5e  xor     ebx, ebx
0x180006b60  lea     rdi, [r12+44h]
0x180006b65  test    rdi, rdi
0x180006b68  jz      loc_18000745B
0x180006b6e  cmp     r9d, esi
0x180006b71  jb      loc_18000745B
0x180006b77  test    rdx, rdx
0x180006b7a  jz      loc_180006C77
0x180006b80  test    ebx, ebx
0x180006b82  jnz     short loc_180006BB7
0x180006b84  mov     ecx, 7FFFFFFFh
0x180006b89  mov     rax, rdx
0x180006b8c  nop     dword ptr [rax+00h]
0x180006b90  cmp     word ptr [rax], 0
0x180006b94  jz      loc_180007289
0x180006b9a  add     rax, 2
0x180006b9e  sub     rcx, 1
0x180006ba2  jnz     short loc_180006B90
0x180006ba4  jmp     loc_180006A55
0x180006ba9  lea     rdx, [r8+rax]
0x180006bad  jmp     short loc_180006B5E
0x180006baf  test    ebx, ebx
0x180006bb1  jz      loc_180006C77
0x180006bb7  lea     eax, [rbx+rsi]
0x180006bba  cmp     r9d, eax
0x180006bbd  jb      short loc_180006BD9
0x180006bbf  mov     ecx, esi
0x180006bc1  add     rcx, r12; void *
0x180006bc4  mov     r8d, ebx; Size
0x180006bc7  call    memcpy_0
0x180006bcc  mov     r8, [rsp+68h+arg_0]
0x180006bd1  mov     r9d, [rsp+68h+arg_18]
0x180006bd9  mov     [rdi], esi
0x180006bdb  add     esi, ebx
0x180006bdd  movzx   eax, word ptr [r13+6]
0x180006be2  cmp     [r8+26h], ax
  ... truncated ...
```
