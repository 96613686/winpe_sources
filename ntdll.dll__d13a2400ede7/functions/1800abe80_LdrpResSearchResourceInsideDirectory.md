# LdrpResSearchResourceInsideDirectory

- ea: `0x1800abe80`
- end: `0x1800ad12a`
- name: `LdrpResSearchResourceInsideDirectory`
- size: `4778`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800aa698`
- `0x1800ab4f0`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x18006f0d0`
- `0x1800ab094`
- `0x1800ab1f8`
- `0x1800abe80`
- `0x1800ae518`
- `0x180103f84`
- `0x1801072a0`
- `0x180162810`

## string_xrefs

- `0x1800abf5b`: `LdrpResSearchResourceInsideDirectory Enter`
- `0x1800abf74`: `LdrpResSearchResourceInsideDirectory Exit`

## pseudocode

```c
__int64 __fastcall LdrpResSearchResourceInsideDirectory(
        unsigned __int64 a1,
        char *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        __int64 a5,
        _DWORD *a6,
        unsigned __int64 a7,
        unsigned int a8,
        unsigned __int16 *a9,
        unsigned __int64 *a10,
        unsigned __int64 *a11,
        int a12,
        _WORD *a13)
{
  unsigned __int64 v13; // r12
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  int v22; // ebx
  bool v23; // r15
  HANDLE v24; // r10
  unsigned __int64 v25; // r9
  unsigned __int64 v26; // r14
  unsigned int *v27; // r13
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r8
  int v30; // ebx
  unsigned int v31; // ebx
  unsigned __int64 v32; // r11
  unsigned __int64 v33; // rbx
  __int16 v34; // ax
  int v35; // eax
  unsigned __int64 v36; // r13
  unsigned __int64 v37; // r11
  __int64 Heap_0; // r14
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rax
  __int64 v44; // rax
  unsigned __int64 v45; // rsi
  _DWORD *v46; // r14
  int i; // r10d
  unsigned int v48; // r8d
  unsigned __int64 v49; // r11
  int j; // r10d
  __int64 v51; // rcx
  int k; // r10d
  unsigned __int64 v53; // r10
  __int64 result; // rax
  unsigned __int64 v55; // r12
  unsigned __int64 v56; // r13
  unsigned __int64 v57; // r14
  unsigned __int8 v58; // r15
  unsigned __int64 v59; // rax
  unsigned int SectionSize; // eax
  __int64 v61; // rcx
  unsigned __int64 *v62; // r10
  unsigned __int64 v63; // r10
  unsigned __int64 v64; // r13
  int v65; // r12d
  __int64 v66; // rax
  __int64 v67; // r14
  bool v68; // zf
  __int64 v69; // rax
  int v70; // eax
  __int64 v71; // r14
  __int64 v72; // rdx
  __int64 v73; // rcx
  int v74; // [rsp+40h] [rbp-1A8h]
  __int64 v75; // [rsp+48h] [rbp-1A0h]
  unsigned int v76; // [rsp+50h] [rbp-198h]
  unsigned __int64 v77; // [rsp+58h] [rbp-190h]
  int v78; // [rsp+60h] [rbp-188h]
  unsigned int *v79; // [rsp+68h] [rbp-180h]
  char v81; // [rsp+81h] [rbp-167h]
  unsigned __int64 v83; // [rsp+90h] [rbp-158h]
  int v85; // [rsp+B0h] [rbp-138h] BYREF
  unsigned int v86; // [rsp+B4h] [rbp-134h]
  __int16 v87; // [rsp+B8h] [rbp-130h]
  unsigned int v88; // [rsp+BCh] [rbp-12Ch]
  HANDLE Handle; // [rsp+C0h] [rbp-128h]
  __int64 v90; // [rsp+C8h] [rbp-120h]
  int v91; // [rsp+D0h] [rbp-118h]
  int v92; // [rsp+D4h] [rbp-114h]
  int v93; // [rsp+D8h] [rbp-110h]
  int v94; // [rsp+DCh] [rbp-10Ch]
  unsigned __int64 v95; // [rsp+E0h] [rbp-108h]
  __int64 v96; // [rsp+E8h] [rbp-100h]
  _WORD *v97; // [rsp+F0h] [rbp-F8h]
  unsigned __int64 v98; // [rsp+F8h] [rbp-F0h]
  __int16 v99; // [rsp+100h] [rbp-E8h]
  unsigned __int64 v100; // [rsp+108h] [rbp-E0h]
  unsigned __int64 v101; // [rsp+110h] [rbp-D8h]
  __int64 v102; // [rsp+118h] [rbp-D0h]
  unsigned __int64 v103; // [rsp+120h] [rbp-C8h]
  __int64 v104; // [rsp+128h] [rbp-C0h]
  __int64 v105; // [rsp+130h] [rbp-B8h]
  unsigned __int64 *v106; // [rsp+138h] [rbp-B0h]
  __int64 v107; // [rsp+140h] [rbp-A8h]
  _QWORD v108[2]; // [rsp+148h] [rbp-A0h] BYREF
  _QWORD v109[2]; // [rsp+158h] [rbp-90h] BYREF
  int v110; // [rsp+168h] [rbp-80h]
  unsigned __int64 *v111; // [rsp+170h] [rbp-78h]
  unsigned __int64 v112; // [rsp+178h] [rbp-70h]
  unsigned __int64 v113; // [rsp+180h] [rbp-68h]
  __int128 v114; // [rsp+188h] [rbp-60h]
  __int128 v115; // [rsp+198h] [rbp-50h] BYREF

  v13 = a4;
  Handle = a2;
  v96 = a5;
  v106 = a10;
  v111 = a11;
  v97 = a13;
  v85 = 0;
  v114 = 0;
  v91 = 0;
  v83 = 0;
  v115 = 0;
  v75 = 0;
  v88 = 0;
  v108[0] = 5636180;
  v108[1] = L"LdrpResSearchResourceInsideDirectory Enter";
  v109[0] = 5505106;
  v109[1] = L"LdrpResSearchResourceInsideDirectory Exit";
  if ( (unsigned int)RtlGetCurrentServiceSessionId(a1, a2, a3, a4) )
    v20 = (__int64)NtCurrentPeb()->SharedData + 555;
  else
    v20 = 2147353477;
  if ( (*(_BYTE *)v20 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v20, v17, v18, v19) )
      v73 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v73 = 2147353476;
    LdrpTraceLoadMUIDll(v108, *(unsigned __int8 *)v73);
  }
  if ( !v13 )
    return 3221225485LL;
  if ( !a5 )
    return 3221225485LL;
  v21 = a7;
  if ( !a7 || a8 - 1 > 3 )
    return 3221225485LL;
  v22 = a12;
  if ( (a12 & 0x8000) != 0 )
  {
    if ( (unsigned __int64)(a2 - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a6 )
      return 3221225485LL;
    v21 = a7;
  }
  v23 = (a12 & 0x800) != 0 && (a12 & 0x8000) != 0;
  if ( (a12 & 0x1000) != 0 && !a3 )
    return 3221225485LL;
  if ( !v23 && !a1 )
    return 3221225485LL;
  v24 = Handle;
  if ( v23 && !Handle )
    return 3221225485LL;
  v25 = a8;
  v26 = v13;
  v27 = 0;
  v79 = 0;
  v77 = 0;
  v28 = (unsigned __int64)v97;
  if ( v97 )
    *v97 = 0;
LABEL_16:
  if ( !v26 )
    goto LABEL_17;
  v35 = v25;
  v25 = (unsigned int)(v25 - 1);
  v86 = v25;
  v110 = v25;
  if ( !v35 )
    goto LABEL_17;
  v29 = *(_QWORD *)v21;
  v83 = *(_QWORD *)v21;
  v100 = *(_QWORD *)v21;
  if ( (_DWORD)v25 || a8 != 3 )
  {
    v36 = v77;
  }
  else
  {
    v36 = v26;
    v77 = v26;
    v112 = v26;
    v21 = (unsigned __int64)a9;
    if ( !a9 )
    {
      v31 = -1073741811;
      goto LABEL_51;
    }
    v91 = *a9;
    v99 = v91;
    v28 = 0;
    v88 = 0;
    v87 = 0;
    if ( (~(_BYTE)v22 & 4) != 0 )
    {
      v29 = a9[2];
      v83 = v29;
      v100 = v29;
    }
  }
  if ( v23 )
  {
    result = LdrpResReadFile(v24);
    v74 = result;
    if ( (int)result < 0 )
      return result;
    v25 = v86;
    goto LABEL_157;
  }
  if ( (a12 & 0x1000) == 0 )
  {
LABEL_157:
    v28 = a3;
    v37 = a1;
    goto LABEL_158;
  }
  v21 = v26 + 24;
  if ( v26 + 24 < v26 )
    goto LABEL_50;
  v37 = a1;
  v28 = a3;
  if ( v21 > a3 + (a1 & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    v31 = -1073741701;
    goto LABEL_51;
  }
LABEL_158:
  v21 = WORD6(v114);
  if ( !v23 )
    v21 = *(unsigned __int16 *)(v26 + 12);
  v76 = v21;
  if ( (_DWORD)v21 && (a12 & 0x1000) != 0 )
  {
    v90 = 8 * v21;
    v21 = v26 + 8 * v21 + 16;
    if ( v21 < v26 )
    {
      v31 = -1073741701;
      goto LABEL_51;
    }
    if ( v21 > v28 + (v37 & 0xFFFFFFFFFFFFFFFCuLL) )
    {
      v31 = -1073741701;
      goto LABEL_51;
    }
    v21 = v76;
  }
  v29 = v26 + 16;
  v90 = v26 + 16;
  v98 = v26 + 16;
  v63 = v83;
  if ( (v83 & 0xFFFFFFFFFFFF0000uLL) == 0 )
  {
    if ( (_DWORD)v21 )
    {
      if ( (a12 & 0x1000) != 0 && v29 + (int)v21 < v29 )
      {
        v31 = -1073741701;
        goto LABEL_51;
      }
      v29 += 8LL * (int)v21;
      v90 = v29;
      v98 = v29;
    }
    v21 = HIWORD(v114);
    if ( !v23 )
      v21 = *(unsigned __int16 *)(v26 + 14);
    v76 = v21;
    if ( (a12 & 0x1000) != 0 )
    {
      v108[0] = 8LL * (unsigned int)v21;
      v28 = 0xFFFFFFFFLL;
      if ( v108[0] > 0xFFFFFFFF )
        goto LABEL_50;
      v28 = v29 + (unsigned int)(8 * v21);
      if ( v28 < v29 )
      {
        v31 = -1073741701;
        goto LABEL_51;
      }
      if ( v28 > a3 + (v37 & 0xFFFFFFFFFFFFFFFCuLL) )
      {
        v31 = -1073741701;
        goto LABEL_51;
      }
      v21 = (unsigned int)v21;
    }
  }
  if ( !(_DWORD)v21 )
    goto LABEL_42;
  if ( !v23 )
    goto LABEL_176;
  if ( v75 )
  {
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v75);
    v107 = 0;
    LODWORD(v21) = v76;
  }
  Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, 8LL * (int)v21);
  v75 = Heap_0;
  v107 = Heap_0;
  if ( !Heap_0 )
  {
    v31 = -1073741801;
    goto LABEL_52;
  }
  result = LdrpResReadFile(Handle);
  v74 = result;
  if ( (int)result >= 0 )
  {
    v29 = Heap_0;
    v90 = Heap_0;
    v98 = Heap_0;
LABEL_175:
    v63 = v83;
    v21 = v76;
LABEL_176:
    if ( v36 && (v22 & 0x20) != 0 )
    {
      v26 = 0;
      v27 = (unsigned int *)(v13 + *(unsigned int *)(v29 + 4));
      v79 = v27;
      if ( (a12 & 0x1000) != 0 )
      {
        if ( (unsigned __int64)v27 < v13 )
        {
          v31 = -1073741701;
          goto LABEL_51;
        }
      }
      else
      {
        v79 = (unsigned int *)(v13 + *(unsigned int *)(v29 + 4));
      }
      v29 = *(unsigned int *)v29;
      v100 = v29;
      v25 = v86;
      goto LABEL_18;
    }
LABEL_177:
    v26 = 0;
    v64 = v29;
    v98 = v29;
    v28 = v29 + 8 * ((int)v21 - 1LL);
    v101 = v28;
    v65 = v21;
    while ( 1 )
    {
      if ( v64 > v28 )
      {
        v13 = a4;
        goto LABEL_187;
      }
      LODWORD(v66) = (int)v21 >> 1;
      v78 = (int)v21 >> 1;
      if ( !((int)v21 >> 1) )
      {
        v68 = v65 == 0;
        v13 = a4;
        if ( v68 )
          goto LABEL_187;
        result = LdrpResCompareResourceNames(a1, Handle, a3, v63, a4, v64, v22, &v85, v74);
        v74 = result;
        if ( (int)result < 0 )
          return result;
        if ( v85 )
        {
LABEL_187:
          v27 = v79;
          goto LABEL_188;
        }
        v69 = *(unsigned int *)(v64 + 4);
        if ( (int)v69 < 0 )
        {
          if ( (a12 & 0x1000) == 0 )
          {
            v26 = a4 + (v69 & 0xFFFFFFFF7FFFFFFFuLL);
            goto LABEL_187;
          }
          if ( v77 )
          {
            v31 = -1073741701;
            goto LABEL_51;
          }
          LODWORD(v69) = v69 & 0x7FFFFFFF;
          v26 = v69 + a4;
          if ( v69 + a4 < a4 )
            goto LABEL_50;
          goto LABEL_187;
        }
        if ( (a12 & 0x1000) == 0 )
        {
          v27 = (unsigned int *)(a4 + v69);
          v79 = (unsigned int *)(a4 + v69);
          goto LABEL_188;
        }
        v21 = v77;
        if ( !v77 )
        {
          v31 = -1073741701;
          goto LABEL_51;
        }
        v27 = (unsigned int *)(a4 + v69);
        v79 = (unsigned int *)(a4 + v69);
        if ( a4 + v69 < a4 )
          goto LABEL_50;
LABEL_189:
        if ( !v21 || v27 )
        {
LABEL_215:
          v21 = a7 + 8;
          a7 = v21;
          v113 = v21;
          v25 = v86;
          v24 = Handle;
          goto LABEL_16;
        }
        if ( (v22 & 4) == 0 )
        {
          v28 = v88;
          LOWORD(v28) = v88 + 1;
          v88 = v28;
          v87 = v28;
          if ( (unsigned __int16)v28 < (__int16)v91 )
          {
            v63 = a9[4 * (unsigned __int16)v28 + 2];
            v83 = v63;
            v100 = v63;
            LODWORD(v21) = v76;
            v29 = v90;
            goto LABEL_177;
          }
          if ( !*((_BYTE *)a9 + 516) )
          {
            v22 |= 0x20u;
            v29 = v90;
            v36 = v77;
            goto LABEL_175;
          }
          goto LABEL_215;
        }
        v25 = v86;
LABEL_17:
        v29 = v83;
LABEL_18:
        v30 = v22 & 2;
        if ( v27 && !v30 )
        {
          if ( (a12 & 0x1000) == 0 )
          {
            v25 = a1;
            v32 = a3;
            goto LABEL_28;
          }
          if ( (unsigned __int64)v27 <= v13
            || (v25 = a1, v32 = a3, v21 = a3 + (a1 & 0xFFFFFFFFFFFFFFFCuLL), (unsigned __int64)(v27 + 4) > v21) )
          {
LABEL_102:
            v31 = -1073741701;
            goto LABEL_51;
          }
LABEL_28:
          v28 = (unsigned __int64)v97;
          if ( v97 )
            *v97 = v29;
          v33 = v25 & 0xFFFFFFFFFFFFFFFCuLL;
          v21 = v25 & 1;
          v97 = (_WORD *)v21;
          if ( (v25 & 1) == 0 && !v23 )
          {
            v45 = 0;
            v103 = 0;
LABEL_119:
            v55 = v27[1];
            if ( (a12 & 0x1000) != 0 )
            {
              v28 = *v27;
              if ( v28 < v45 )
                goto LABEL_50;
              v56 = (unsigned int)v28 - v45;
              if ( v56 < a4 - v25 )
                goto LABEL_102;
              if ( v56 > a3 )
                goto LABEL_102;
              if ( !(_DWORD)v55 )
                goto LABEL_102;
              v57 = (unsigned int)v55;
              if ( v55 > a3 || v55 + v56 > a3 )
                goto LABEL_102;
              v58 = !v21 && !v23;
              v21 = LdrpSectionTableFromVirtualAddress(v33, a3, v96, (_DWORD)a6, v28, (a12 & 0x1000) != 0, v58);
              if ( !v21 )
              {
                v31 = -1073741701;
                goto LABEL_51;
              }
              v25 = (unsigned __int64)v79;
              v59 = *v79;
              v29 = v55 + v59;
              if ( v55 + v59 < v59 )
                goto LABEL_102;
              SectionSize = LdrpGetSectionSize(v21, v58);
              v21 = *(unsigned int *)(v61 + 12);
              v28 = v21 + SectionSize;
              if ( v28 < v21 )
                goto LABEL_102;
              if ( v29 > v28 )
              {
                v31 = -1073741701;
                goto LABEL_51;
              }
            }
            else
            {
              v56 = 0;
              v57 = v55;
              v25 = (unsigned __int64)v79;
            }
            v62 = v106;
            if ( v106 )
            {
              if ( (a12 & 0x1000) != 0 )
              {
                v21 = v33 + v56;
                if ( v33 + v56 < v33 )
                  goto LABEL_50;
                v28 = a3;
                if ( v21 > a3 + (v33 & 0xFFFFFFFFFFFFFFFCuLL) )
                  goto LABEL_50;
                *v106 = v21;
                v57 = v55;
LABEL_143:
                v29 = (unsigned __int64)v111;
                if ( v111 )
                {
                  if ( (a12 & 0x1000) != 0 && v62 )
                  {
                    v21 = *v62 + v57;
                    if ( v21 < *v62 )
                    {
                      v31 = -1073741701;
                      goto LABEL_51;
                    }
                    if ( v21 > v28 + v33 )
                    {
                      v31 = -1073741701;
                      goto LABEL_51;
                    }
                  }
                  *v111 = v57;
                }
                v31 = 0;
                goto LABEL_51;
              }
              *v106 = v33 + *(unsigned int *)v25 - v45;
            }
            v28 = a3;
            goto LABEL_143;
          }
          v29 = v96;
          v34 = *(_WORD *)(v96 + 24);
          v21 = 267;
          if ( v34 != 267 )
          {
            v21 = 523;
            if ( v34 == 523 )
            {
              v28 = *(unsigned int *)(v96 + 152);
LABEL_62:
              if ( (_DWORD)v28 )
              {
                if ( (a12 & 0x1000) != 0 )
                {
                  if ( (unsigned int)v28 + v33 < v33 )
                    goto LABEL_50;
                  if ( (unsigned int)v28 + v33 < v13 )
                  {
                    v31 = -1073741701;
                    goto LABEL_51;
                  }
                }
                v45 = v33 + (unsigned int)v28 - v13;
                v103 = v45;
                v94 = 0;
                v21 = (unsigned __int64)a6;
                v46 = a6;
                v105 = (__int64)a6;
                if ( a6
                  || (v71 = *(unsigned __int16 *)(v96 + 20) + 24LL,
                      v68 = v96 + v71 == 0,
                      v46 = (_DWORD *)(v96 + v71),
                      v105 = (__int64)v46,
                      !v68) )
                {
                  for ( i = 0; ; ++i )
                  {
                    v94 = i;
                    if ( i >= *(unsigned __int16 *)(v29 + 6) )
                      break;
                    if ( !v21 && (a12 & 0x1000) != 0 )
                    {
                      v21 = v32 + (v25 & 0xFFFFFFFFFFFFFFFCuLL);
                      if ( (unsigned __int64)(v46 + 10) > v21 )
                        goto LABEL_102;
                      v21 = (unsigned __int64)a6;
                    }
                    v48 = v46[3];
                    if ( (unsigned int)v28 >= v48 )
                    {
                      v29 = v46[4] + v48;
                      if ( (unsigned int)v28 < (unsigned int)v29 )
                      {
                        if ( v23 )
                        {
                          result = LdrpResReadFile(Handle);
                          if ( (int)result < 0 )
                            return result;
                          v27 = (unsigned int *)&v115;
                          v79 = (unsigned int *)&v115;
                        }
                        v25 = *v27;
                        if ( (unsigned int)v25 <= v46[2] )
                        {
LABEL_118:
                          v25 = a1;
                          v21 = (unsigned __int64)v97;
                          goto LABEL_119;
                        }
                        v49 = (unsigned int)v46[3];
                        v93 = 0;
                        v21 = (unsigned __int64)a6;
                        v28 = (unsigned __int64)a6;
                        v104 = (__int64)a6;
                        if ( a6 || (v28 = *(unsigned __int16 *)(v96 + 20) + v96 + 24, (v104 = v28) != 0) )
                        {
                          for ( j = 0; ; ++j )
                          {
                            v93 = j;
                            if ( j >= *(unsigned __int16 *)(v96 + 6) )
                              break;
                            if ( !v21 && (a12 & 0x1000) != 0 )
                            {
                              v21 = a3 + (v33 & 0xFFFFFFFFFFFFFFFCuLL);
                              if ( v28 + 40 > v21 )
                                break;
                            }
                            v29 = *(unsigned int *)(v28 + 12);
                            if ( (unsigned int)v25 >= (unsigned int)v29
                              && (unsigned int)v25 < (int)v29 + *(_DWORD *)(v28 + 16) )
                            {
                              v92 = 0;
                              v51 = (__int64)a6;
                              v28 = (unsigned __int64)a6;
                              v102 = (__int64)a6;
                              if ( a6
                                || (v72 = *(unsigned __int16 *)(v96 + 20) + 24LL,
                                    v68 = v96 + v72 == 0,
                                    v28 = v96 + v72,
                                    v102 = v28,
                                    !v68) )
                              {
                                for ( k = 0; ; ++k )
                                {
                                  v92 = k;
                                  if ( k >= *(unsigned __int16 *)(v96 + 6)
                                    || !v51 && (a12 & 0x1000) != 0 && v28 + 40 > a3 + (v33 & 0xFFFFFFFFFFFFFFFCuLL) )
                                  {
                                    break;
                                  }
                                  v25 = *(unsigned int *)(v28 + 12);
                                  if ( (unsigned int)v29 >= (unsigned int)v25
                                    && (unsigned int)v29 < (int)v25 + *(_DWORD *)(v28 + 16) )
                                  {
                                    v53 = v29;
                                    v29 = (unsigned int)v25;
                                    if ( (a12 & 0x1000) == 0 )
                                      goto LABEL_94;
                                    v21 = v33 + v53 - v25;
                                    if ( v21 < v33 )
                                      goto LABEL_50;
                                    if ( v21 + *(unsigned int *)(v28 + 20) >= v21 )
                                    {
LABEL_94:
                                      v25 = v33
                                          + v53
                                          + *(unsigned int *)(v28 + 20)
                                          - (unsigned __int64)(unsigned int)v25;
                                      goto LABEL_95;
                                    }
                                    v31 = -1073741701;
                                    goto LABEL_51;
                                  }
                                  v28 += 40LL;
                                  v102 = v28;
                                  v51 = (__int64)a6;
                                }
                              }
                              v28 = 0;
                              v25 = 0;
LABEL_95:
                              v29 = v28 + 12;
                              v28 = v49;
                              if ( (a12 & 0x1000) != 0 )
                              {
                                v21 = *(unsigned int *)v29;
                                if ( v21 < v49 )
                                  goto LABEL_50;
                                v21 -= v49;
                                if ( v21 < v25 - v13 )
                                {
                                  v31 = -1073741701;
                                  goto LABEL_51;
                                }
                              }
                              v45 += v13 + *(unsigned int *)v29 - v49 - v25;
                              v103 = v45;
                              goto LABEL_118;
                            }
                            v28 += 40LL;
                            v104 = v28;
                            v21 = (unsigned __int64)a6;
                          }
                        }
                        goto LABEL_102;
                      }
                    }
                    v46 += 10;
                    v105 = (__int64)v46;
                    v29 = v96;
                  }
                }
                goto LABEL_102;
              }
            }
            v31 = -1073741687;
            goto LABEL_51;
          }
          v28 = *(unsigned int *)(v96 + 136);
          goto LABEL_62;
        }
        if ( v26 && v30 )
        {
          if ( (a12 & 0x1000) != 0 )
          {
            v21 = v26 + 24;
            if ( v26 + 24 < v26 )
            {
              v31 = -1073741701;
              goto LABEL_51;
            }
            v28 = a1;
            v29 = a3;
            if ( v21 > a3 + (a1 & 0xFFFFFFFFFFFFFFFCuLL) )
            {
              v31 = -1073741701;
              goto LABEL_51;
            }
          }
          else
          {
            v28 = a1;
            v29 = a3;
          }
          if ( v106 )
          {
            if ( (a12 & 0x1000) != 0 )
            {
              v28 &= 0xFFFFFFFFFFFFFFFCuLL;
              if ( v26 < v28 )
                goto LABEL_50;
              if ( v26 > v28 + v29 )
              {
                v31 = -1073741701;
                goto LABEL_51;
              }
            }
            *v106 = v26;
          }
          v31 = 0;
          goto LABEL_51;
        }
LABEL_42:
        switch ( a8 - (_DWORD)v25 )
        {
          case 1u:
            v31 = -1073741686;
            break;
          case 2u:
            v31 = -1073741685;
            break;
          case 3u:
            v31 = -1073741308;
            break;
          default:
            v31 = -1073741811;
            break;
        }
        goto LABEL_51;
      }
      v95 = v64;
      v81 = v65 & 1;
      v65 = v66 - 1;
      v66 = (int)v66;
      if ( (v21 & 1) == 0 )
        v66 = v65;
      v95 = v64 + 8 * v66;
      result = LdrpResCompareResourceNames(a1, Handle, a3, v63, a4, v95, v22, &v85, v74);
      v74 = result;
      if ( (int)result < 0 )
        return result;
      if ( !v85 )
      {
        v21 = *(unsigned int *)(v95 + 4);
        if ( (v21 & 0x80000000) != 0LL )
        {
          if ( (a12 & 0x1000) == 0 )
          {
            v67 = (unsigned int)v21;
            LODWORD(v67) = v21 & 0x7FFFFFFF;
            v13 = a4;
            v26 = a4 + v67;
            goto LABEL_187;
          }
          if ( v77 )
          {
            v31 = -1073741701;
          }
          else
          {
            LODWORD(v21) = v21 & 0x7FFFFFFF;
            v13 = a4;
            v26 = v21 + a4;
            if ( v21 + a4 >= a4 )
              goto LABEL_187;
LABEL_50:
            v31 = -1073741701;
          }
LABEL_51:
          Heap_0 = v75;
LABEL_52:
          if ( Heap_0 )
          {
            RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
            v107 = 0;
          }
          if ( (unsigned int)RtlGetCurrentServiceSessionId(v21, v28, v29, v25) )
            v43 = (__int64)NtCurrentPeb()->SharedData + 555;
          else
            v43 = 2147353477;
          if ( (*(_BYTE *)v43 & 1) != 0 )
          {
            if ( (unsigned int)RtlGetCurrentServiceSessionId(v40, v39, v41, v42) )
              v44 = (__int64)NtCurrentPeb()->SharedData + 554;
            else
              v44 = 2147353476;
            LdrpTraceLoadMUIDll(v109, *(unsigned __int8 *)v44);
          }
          return v31;
        }
        if ( (a12 & 0x1000) != 0 )
        {
          if ( !v77 )
          {
            v31 = -1073741701;
            goto LABEL_51;
          }
          v13 = a4;
          v27 = (unsigned int *)(a4 + v21);
          v79 = (unsigned int *)(a4 + v21);
          if ( a4 + v21 < a4 )
            goto LABEL_50;
        }
        else
        {
          v13 = a4;
          v27 = (unsigned int *)(a4 + v21);
          v79 = (unsigned int *)(a4 + v21);
        }
LABEL_188:
        v21 = v77;
        goto LABEL_189;
      }
      if ( v85 >= 0 )
        break;
      v28 = v95 - 8;
      v101 = v95 - 8;
      if ( v81 )
      {
        v70 = v78;
LABEL_217:
        LODWORD(v21) = v70;
        v65 = v70;
        goto LABEL_218;
      }
      LODWORD(v21) = v65;
LABEL_218:
      v63 = v83;
    }
    v64 = v95 + 8;
    v98 = v95 + 8;
    v70 = v78;
    v28 = v101;
    goto LABEL_217;
  }
  return result;
}

```

## disassembly

```asm
0x1800abe80  mov     r11, rsp
0x1800abe83  push    rbx
0x1800abe84  push    rsi
0x1800abe85  push    rdi
0x1800abe86  push    r12
0x1800abe88  push    r13
0x1800abe8a  push    r14
0x1800abe8c  push    r15
0x1800abe8e  sub     rsp, 1B0h
0x1800abe95  mov     rax, cs:__security_cookie
0x1800abe9c  xor     rax, rsp
0x1800abe9f  mov     [rsp+1E8h+var_40], rax
0x1800abea7  mov     r12, r9
0x1800abeaa  mov     [rsp+1E8h+var_148], r9
0x1800abeb2  mov     r13, r8
0x1800abeb5  mov     [rsp+1E8h+var_170], r8
0x1800abeba  mov     rdi, rdx
0x1800abebd  mov     [rsp+1E8h+Handle], rdx
0x1800abec5  mov     r14, rcx
0x1800abec8  mov     [rsp+1E8h+var_160], rcx
0x1800abed0  mov     rbx, [rsp+1E8h+arg_20]
0x1800abed8  mov     [rsp+1E8h+var_100], rbx
0x1800abee0  mov     r15, [rsp+1E8h+arg_28]
0x1800abee8  mov     [rsp+1E8h+var_150], r15
0x1800abef0  mov     rax, [rsp+1E8h+arg_48]
0x1800abef8  mov     [rsp+1E8h+var_B0], rax
0x1800abf00  mov     rax, [rsp+1E8h+arg_50]
0x1800abf08  mov     [rsp+1E8h+var_78], rax
0x1800abf10  mov     rax, [rsp+1E8h+arg_60]
0x1800abf18  mov     [rsp+1E8h+var_F8], rax
0x1800abf20  xor     eax, eax
0x1800abf22  mov     [rsp+1E8h+var_138], eax
0x1800abf29  xorps   xmm0, xmm0
0x1800abf2c  movups  xmmword ptr [r11-60h], xmm0
0x1800abf31  mov     [rsp+1E8h+var_118], eax
0x1800abf38  mov     [r11-158h], rax
0x1800abf3f  movups  xmmword ptr [r11-50h], xmm0
0x1800abf44  mov     [rsp+1E8h+var_1A0], rax
0x1800abf49  mov     [rsp+1E8h+var_12C], eax
0x1800abf50  mov     qword ptr [r11-0A0h], 560054h
0x1800abf5b  lea     rax, aLdrpressearchr; "LdrpResSearchResourceInsideDirectory En"...
0x1800abf62  mov     [r11-98h], rax
0x1800abf69  mov     qword ptr [r11-90h], 540052h
0x1800abf74  lea     rax, aLdrpressearchr_1; "LdrpResSearchResourceInsideDirectory Ex"...
0x1800abf7b  mov     [r11-88h], rax
0x1800abf82  call    RtlGetCurrentServiceSessionId
0x1800abf87  test    eax, eax
0x1800abf89  jnz     loc_1800AD07D
0x1800abf8f  mov     ecx, 7FFE0385h
0x1800abf94  test    byte ptr [rcx], 1
0x1800abf97  jnz     loc_1800AD099
0x1800abf9d  test    r12, r12
0x1800abfa0  jz      loc_1800AD0D7
0x1800abfa6  test    rbx, rbx
0x1800abfa9  jz      loc_1800AD0D7
0x1800abfaf  mov     rcx, [rsp+1E8h+arg_30]
0x1800abfb7  test    rcx, rcx
0x1800abfba  jz      loc_1800AD0D7
0x1800abfc0  mov     esi, [rsp+1E8h+arg_38]
0x1800abfc7  lea     eax, [rsi-1]
0x1800abfca  cmp     eax, 3
0x1800abfcd  ja      loc_1800AD0D7
0x1800abfd3  mov     ebx, [rsp+1E8h+arg_58]
0x1800abfda  mov     eax, ebx
0x1800abfdc  and     eax, 8000h
0x1800abfe1  jnz     loc_1800AD0F3
0x1800abfe7  mov     edi, ebx
0x1800abfe9  and     edi, 1000h
0x1800abfef  setnz   [rsp+1E8h+var_168]
0x1800abff7  bt      ebx, 0Bh
0x1800abffb  jb      loc_1800AD10F
0x1800ac001  xor     r15b, r15b
0x1800ac004  test    edi, edi
0x1800ac006  jnz     loc_1800AD0CE
0x1800ac00c  test    r15b, r15b
0x1800ac00f  jz      loc_1800AD0E1
0x1800ac015  mov     r10, [rsp+1E8h+Handle]
0x1800ac01d  cmp     r15b, 1
0x1800ac021  jz      loc_1800AD11F
0x1800ac027  mov     r9d, esi
0x1800ac02a  mov     r14, r12
0x1800ac02d  xor     r13d, r13d
0x1800ac030  mov     [rsp+1E8h+var_180], r13
0x1800ac035  mov     [rsp+1E8h+var_190], r13
0x1800ac03a  mov     rdx, [rsp+1E8h+var_F8]
0x1800ac042  test    rdx, rdx
0x1800ac045  jz      short loc_1800AC04C
0x1800ac047  xor     eax, eax
0x1800ac049  mov     [rdx], ax
0x1800ac04c  test    r14, r14
0x1800ac04f  jnz     loc_1800AC13B
0x1800ac055  mov     r8, [rsp+1E8h+var_158]
0x1800ac05d  and     ebx, 2
0x1800ac060  test    r13, r13
0x1800ac063  jnz     short loc_1800AC0C1
0x1800ac065  test    r14, r14
0x1800ac068  jz      loc_1800AC1CA
0x1800ac06e  test    ebx, ebx
0x1800ac070  jz      loc_1800AC1CA
0x1800ac076  test    edi, edi
0x1800ac078  jz      loc_1800AC5A9
0x1800ac07e  lea     rcx, [r14+18h]
0x1800ac082  cmp     rcx, r14
0x1800ac085  jb      loc_1800AC57F
0x1800ac08b  mov     rdx, [rsp+1E8h+var_160]
0x1800ac093  mov     rax, rdx
0x1800ac096  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800ac09a  mov     r8, [rsp+1E8h+var_170]
0x1800ac09f  add     rax, r8
0x1800ac0a2  cmp     rcx, rax
0x1800ac0a5  jbe     loc_1800AC5B6
0x1800ac0ab  mov     [rsp+1E8h+var_140], 0
0x1800ac0b7  mov     ebx, 0C000007Bh
0x1800ac0bc  jmp     loc_1800AC26A
0x1800ac0c1  test    ebx, ebx
0x1800ac0c3  jnz     short loc_1800AC065
0x1800ac0c5  test    edi, edi
0x1800ac0c7  jnz     loc_1800AC543
0x1800ac0cd  mov     r9, [rsp+1E8h+var_160]
0x1800ac0d5  mov     r11, [rsp+1E8h+var_170]
0x1800ac0da  mov     rdx, [rsp+1E8h+var_F8]
0x1800ac0e2  test    rdx, rdx
0x1800ac0e5  jz      short loc_1800AC0EB
0x1800ac0e7  mov     [rdx], r8w
0x1800ac0eb  mov     rbx, r9
0x1800ac0ee  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800ac0f2  mov     rcx, r9
0x1800ac0f5  and     ecx, 1
0x1800ac0f8  mov     [rsp+1E8h+var_F8], rcx
0x1800ac100  jz      loc_1800AC62C
0x1800ac106  mov     r8, [rsp+1E8h+var_100]
0x1800ac10e  movzx   eax, word ptr [r8+18h]
0x1800ac113  mov     ecx, 10Bh
0x1800ac118  cmp     ax, cx
0x1800ac11b  jz      loc_1800AC302
0x1800ac121  mov     ecx, 20Bh
0x1800ac126  cmp     ax, cx
0x1800ac129  jnz     loc_1800AC81D
0x1800ac12f  mov     edx, [r8+98h]
0x1800ac136  jmp     loc_1800AC309
0x1800ac13b  mov     eax, r9d
0x1800ac13e  dec     r9d
0x1800ac141  mov     [rsp+1E8h+var_134], r9d
0x1800ac149  mov     [rsp+1E8h+var_80], r9d
0x1800ac151  test    eax, eax
0x1800ac153  jz      loc_1800AC055
0x1800ac159  mov     r8, [rcx]
0x1800ac15c  mov     [rsp+1E8h+var_158], r8
0x1800ac164  mov     [rsp+1E8h+var_E0], r8
0x1800ac16c  test    r9d, r9d
0x1800ac16f  jz      short loc_1800AC1EF
0x1800ac171  mov     r13, [rsp+1E8h+var_190]
0x1800ac176  test    r15b, r15b
0x1800ac179  jnz     loc_1800AC830
0x1800ac17f  test    edi, edi
0x1800ac181  jz      loc_1800AC866
0x1800ac187  lea     rcx, [r14+18h]
0x1800ac18b  cmp     rcx, r14
0x1800ac18e  jb      loc_1800AC265
0x1800ac194  mov     r11, [rsp+1E8h+var_160]
0x1800ac19c  mov     rax, r11
0x1800ac19f  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800ac1a3  mov     rdx, [rsp+1E8h+var_170]
0x1800ac1a8  add     rax, rdx
0x1800ac1ab  cmp     rcx, rax
0x1800ac1ae  jbe     loc_1800AC873
0x1800ac1b4  mov     ebx, 0C000007Bh
0x1800ac1b9  jmp     loc_1800AC26A
0x1800ac1be  mov     [rsp+1E8h+var_140], 0
0x1800ac1ca  sub     esi, r9d
0x1800ac1cd  sub     esi, 1
0x1800ac1d0  jz      loc_1800AC539
0x1800ac1d6  sub     esi, 1
0x1800ac1d9  jz      loc_1800AC59F
0x1800ac1df  cmp     esi, 1
0x1800ac1e2  jnz     loc_1800ACE6A
0x1800ac1e8  mov     ebx, 0C0000204h
0x1800ac1ed  jmp     short loc_1800AC26A
0x1800ac1ef  cmp     esi, 3
0x1800ac1f2  jnz     loc_1800AC171
0x1800ac1f8  mov     r13, r14
0x1800ac1fb  mov     [rsp+1E8h+var_190], r14
0x1800ac200  mov     [rsp+1E8h+var_70], r14
0x1800ac208  mov     rcx, [rsp+1E8h+arg_40]
0x1800ac210  test    rcx, rcx
0x1800ac213  jz      loc_1800ACEB1
0x1800ac219  movzx   eax, word ptr [rcx]
0x1800ac21c  mov     [rsp+1E8h+var_118], eax
0x1800ac223  mov     [rsp+1E8h+var_E8], ax
0x1800ac22b  xor     eax, eax
0x1800ac22d  movzx   edx, ax
0x1800ac230  mov     [rsp+1E8h+var_12C], edx
0x1800ac237  mov     [rsp+1E8h+var_130], ax
0x1800ac23f  mov     eax, ebx
0x1800ac241  not     eax
0x1800ac243  test    al, 4
0x1800ac245  jz      loc_1800AC176
0x1800ac24b  movzx   r8d, word ptr [rcx+4]
0x1800ac250  mov     [rsp+1E8h+var_158], r8
0x1800ac258  mov     [rsp+1E8h+var_E0], r8
0x1800ac260  jmp     loc_1800AC176
0x1800ac265  mov     ebx, 0C000007Bh
0x1800ac26a  mov     [rsp+1E8h+var_1A8], ebx
0x1800ac26e  mov     r14, [rsp+1E8h+var_1A0]
0x1800ac273  test    r14, r14
0x1800ac276  jz      short loc_1800AC29B
0x1800ac278  mov     rcx, gs:60h
0x1800ac281  mov     r8, r14
0x1800ac284  xor     edx, edx
0x1800ac286  mov     rcx, [rcx+30h]
0x1800ac28a  call    RtlFreeHeap_0
0x1800ac28f  mov     [rsp+1E8h+var_A8], 0
0x1800ac29b  call    RtlGetCurrentServiceSessionId
0x1800ac2a0  test    eax, eax
0x1800ac2a2  jnz     short loc_1800AC2EA
0x1800ac2a4  mov     eax, 7FFE0385h
0x1800ac2a9  test    byte ptr [rax], 1
0x1800ac2ac  jz      loc_1800AD04F
0x1800ac2b2  call    RtlGetCurrentServiceSessionId
0x1800ac2b7  test    eax, eax
0x1800ac2b9  jz      loc_1800AC595
0x1800ac2bf  mov     rax, gs:60h
0x1800ac2c8  mov     rax, [rax+90h]
0x1800ac2cf  add     rax, 22Ah
0x1800ac2d5  movzx   edx, byte ptr [rax]
0x1800ac2d8  lea     rcx, [rsp+1E8h+var_90]
0x1800ac2e0  call    LdrpTraceLoadMUIDll
0x1800ac2e5  jmp     loc_1800AD04F
0x1800ac2ea  mov     rax, gs:60h
0x1800ac2f3  mov     rax, [rax+90h]
0x1800ac2fa  add     rax, 22Bh
0x1800ac300  jmp     short loc_1800AC2A9
0x1800ac302  mov     edx, [r8+88h]
0x1800ac309  test    edx, edx
0x1800ac30b  jz      loc_1800AC81D
0x1800ac311  mov     esi, edx
0x1800ac313  test    edi, edi
0x1800ac315  jnz     loc_1800AC7FD
0x1800ac31b  sub     rsi, r12
0x1800ac31e  add     rsi, rbx
0x1800ac321  mov     [rsp+1E8h+var_C8], rsi
0x1800ac329  mov     [rsp+1E8h+var_10C], 0
0x1800ac334  mov     rcx, [rsp+1E8h+var_150]
0x1800ac33c  mov     r14, rcx
0x1800ac33f  mov     [rsp+1E8h+var_B8], rcx
0x1800ac347  test    rcx, rcx
0x1800ac34a  jz      loc_1800ACF63
0x1800ac350  xor     r10d, r10d
0x1800ac353  mov     [rsp+1E8h+var_10C], r10d
0x1800ac35b  movzx   eax, word ptr [r8+6]
0x1800ac360  cmp     r10d, eax
0x1800ac363  jge     loc_1800AC56C
0x1800ac369  test    rcx, rcx
0x1800ac36c  jnz     short loc_1800AC391
0x1800ac36e  test    edi, edi
0x1800ac370  jz      short loc_1800AC391
0x1800ac372  mov     rcx, rbx
0x1800ac375  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800ac379  add     rcx, r11
0x1800ac37c  lea     rax, [r14+28h]
0x1800ac380  cmp     rax, rcx
0x1800ac383  ja      loc_1800AC56C
0x1800ac389  mov     rcx, [rsp+1E8h+var_150]
0x1800ac391  mov     r8d, [r14+0Ch]
0x1800ac395  cmp     edx, r8d
0x1800ac398  jb      loc_1800ACEBB
0x1800ac39e  add     r8d, [r14+10h]
0x1800ac3a2  cmp     edx, r8d
0x1800ac3a5  jnb     loc_1800ACEBB
0x1800ac3ab  test    r15b, r15b
0x1800ac3ae  jnz     loc_1800AC5EB
0x1800ac3b4  mov     r9d, [r13+0]
0x1800ac3b8  cmp     r9d, [r14+8]
0x1800ac3bc  jbe     loc_1800AC658
0x1800ac3c2  mov     r11d, [r14+0Ch]
0x1800ac3c6  mov     [rsp+1E8h+var_110], 0
0x1800ac3d1  mov     rcx, [rsp+1E8h+var_150]
0x1800ac3d9  mov     rdx, rcx
0x1800ac3dc  mov     [rsp+1E8h+var_C0], rcx
0x1800ac3e4  mov     r14, [rsp+1E8h+var_100]
0x1800ac3ec  test    rcx, rcx
0x1800ac3ef  jz      loc_1800ACF82
0x1800ac3f5  xor     r10d, r10d
0x1800ac3f8  mov     [rsp+1E8h+var_110], r10d
0x1800ac400  movzx   eax, word ptr [r14+6]
0x1800ac405  cmp     r10d, eax
0x1800ac408  jge     loc_1800AC56C
0x1800ac40e  test    rcx, rcx
0x1800ac411  jnz     short loc_1800AC430
0x1800ac413  test    edi, edi
0x1800ac415  jz      short loc_1800AC430
0x1800ac417  mov     rcx, rbx
0x1800ac41a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800ac41e  add     rcx, [rsp+1E8h+var_170]
0x1800ac423  lea     rax, [rdx+28h]
0x1800ac427  cmp     rax, rcx
0x1800ac42a  ja      loc_1800AC56C
0x1800ac430  mov     r8d, [rdx+0Ch]
0x1800ac434  cmp     r9d, r8d
0x1800ac437  jb      loc_1800ACEF3
  ... truncated ...
```
