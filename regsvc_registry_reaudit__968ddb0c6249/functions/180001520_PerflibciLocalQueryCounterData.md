# PerflibciLocalQueryCounterData

- ea: `0x180001520`
- end: `0x180002803`
- name: `PerflibciLocalQueryCounterData`
- size: `4835`
- prototype: `__int64 __fastcall(struct _PERF_QUERY *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x180015250`
- `0x180018c80`

## callees

- `0x180001520`
- `0x180002dd0`
- `0x180004b00`
- `0x180004e40`
- `0x180005da0`
- `0x180006f40`
- `0x180006fd0`
- `0x180008042`
- `0x180008050`
- `0x18000aaa0`
- `0x18000fea0`
- `0x180015b1c`
- `0x1800161a4`
- `0x18001e431`

## import_xrefs

- `ntdll!NtQueryPerformanceCounter` at `0x180001645`
- `ntdll!NtQueryPerformanceCounter` at `0x180001645`
- `ntdll!NtSetInformationThread` at `0x180001949`
- `ntdll!NtSetInformationThread` at `0x180001949`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000162b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000162b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001635`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001635`

## pseudocode

```c
__int64 __fastcall PerflibciLocalQueryCounterData(struct _PERF_QUERY *a1, _BYTE *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v4; // r14d
  _BYTE *v5; // r13
  struct _PERF_QUERY *v6; // rbp
  __int64 result; // rax
  __int64 v8; // rcx
  ULONG v9; // r12d
  __int64 v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  unsigned int v13; // r15d
  bool v14; // di
  __int64 *v15; // rbx
  int v16; // r9d
  unsigned int v17; // edx
  unsigned int *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // edi
  unsigned int *v21; // r14
  unsigned int v22; // eax
  unsigned int v23; // edx
  __int64 v24; // rsi
  __int64 v25; // rax
  unsigned int *v26; // r12
  __int64 v27; // rcx
  __int64 v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  ULONG v31; // ebp
  __int64 v32; // r15
  unsigned int v33; // r9d
  struct _PERF_INSTANCE_HEADER *v34; // r10
  ULONG Size; // edx
  bool v36; // cc
  unsigned int v37; // r8d
  unsigned int j; // edx
  ULONG v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // r12d
  unsigned int v42; // esi
  __int64 v43; // rdi
  __int64 v44; // rbx
  int v45; // eax
  __int64 v46; // r13
  __int64 CounterSet; // rax
  __int64 v48; // r14
  __int64 v49; // r9
  __int64 v50; // rax
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // r15d
  struct _PERF_INSTANCE_HEADER *v54; // rdx
  struct _PERF_COUNTER_DATA *v55; // r8
  ULONG v56; // eax
  void *v57; // r15
  __int64 v58; // rax
  void *v59; // rcx
  void *v60; // r15
  __int64 v61; // rax
  void *v62; // rcx
  int v63; // eax
  __int64 v64; // rdx
  __int64 v65; // r8
  unsigned int v66; // r14d
  int v67; // eax
  _DWORD *v68; // rdx
  int v69; // r8d
  unsigned __int16 v70; // r10
  char v71; // dl
  int v72; // edx
  unsigned __int64 v73; // r11
  _BYTE *v74; // r10
  int v75; // eax
  _LARGE_INTEGER v76; // rcx
  int v77; // eax
  int v78; // eax
  __int64 v79; // r15
  _DWORD *v80; // r8
  unsigned int v81; // edx
  unsigned int v82; // ecx
  unsigned int v83; // edx
  __int64 v84; // rcx
  __int64 v85; // rax
  __int64 *v86; // rcx
  unsigned int v87; // eax
  void *v88; // rcx
  __int64 v89; // rax
  __int64 *v90; // rdx
  unsigned int v91; // ecx
  char v92; // r8
  union _LARGE_INTEGER v93; // r10
  int v94; // r11d
  unsigned int v95; // r10d
  unsigned int v96; // r8d
  _DWORD *v97; // rsi
  _DWORD *v98; // rax
  int k; // ecx
  _QWORD *v100; // r15
  unsigned int v101; // esi
  unsigned int *v102; // r12
  _QWORD *v103; // r14
  unsigned int v104; // ecx
  unsigned int *v105; // rdx
  unsigned int v106; // r13d
  size_t v107; // r8
  _LARGE_INTEGER v108; // r8
  unsigned int v109; // eax
  __int64 v110; // r9
  unsigned int v111; // edx
  _DWORD *v112; // rcx
  __int64 v113; // rbp
  __int64 *v114; // rsi
  _DWORD *v115; // rbx
  int v116; // r8d
  unsigned int v117; // r10d
  __int64 v118; // r9
  __int64 v119; // r12
  int v120; // r9d
  _DWORD *v121; // rcx
  __int64 v122; // rcx
  double v123; // xmm0_8
  double v124; // xmm1_8
  double v125; // xmm0_8
  __int64 v126; // rax
  __int64 v127; // r13
  unsigned int v128; // eax
  __int64 v129; // r12
  unsigned int v130; // ebx
  unsigned __int16 *v131; // r11
  _DWORD *v132; // r11
  _DWORD *QuadPart; // r10
  unsigned int v134; // ebp
  __int64 v135; // rdi
  __int64 v136; // rbx
  _DWORD *v137; // r14
  unsigned int v138; // r15d
  _DWORD *v139; // r10
  int v140; // ecx
  int v141; // ecx
  int v142; // ecx
  int v143; // eax
  int v144; // eax
  int v145; // eax
  unsigned __int64 v146; // rcx
  double v147; // xmm1_8
  double v148; // xmm0_8
  unsigned __int64 v149; // rcx
  int v150; // eax
  int v151; // [rsp+20h] [rbp-E8h]
  char v152; // [rsp+40h] [rbp-C8h]
  bool v153; // [rsp+41h] [rbp-C7h]
  char v154; // [rsp+41h] [rbp-C7h]
  ULONG i; // [rsp+44h] [rbp-C4h]
  unsigned int v156; // [rsp+44h] [rbp-C4h]
  unsigned int v157; // [rsp+48h] [rbp-C0h]
  unsigned int *v158; // [rsp+50h] [rbp-B8h]
  unsigned int v159; // [rsp+50h] [rbp-B8h]
  int v160; // [rsp+50h] [rbp-B8h]
  unsigned int v161; // [rsp+60h] [rbp-A8h]
  int v162; // [rsp+60h] [rbp-A8h]
  union _LARGE_INTEGER Frequency; // [rsp+68h] [rbp-A0h] BYREF
  _LARGE_INTEGER Counter; // [rsp+70h] [rbp-98h] BYREF
  void *Block; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v166; // [rsp+80h] [rbp-88h] BYREF
  __int64 *v167; // [rsp+88h] [rbp-80h]
  _DWORD *v168; // [rsp+90h] [rbp-78h]
  int ThreadInformation; // [rsp+98h] [rbp-70h] BYREF
  __int64 v170; // [rsp+A0h] [rbp-68h]
  __int64 v171; // [rsp+A8h] [rbp-60h]

  v4 = a3;
  Block = 0;
  v5 = a2;
  v166 = 0;
  v6 = a1;
  ThreadInformation = 0;
  if ( !a4 )
    return 87;
  *a4 = 0;
  if ( a3 )
  {
    if ( !a2 )
      return 87;
    *a2 = 0;
    a2[a3 - 1] = 0;
  }
  PerflibciNotifyQuery(a1);
  if ( !*((_QWORD *)v6 + 5) )
    return 14;
  v8 = 0;
  v9 = 0;
  for ( i = 0; (unsigned int)v8 < *((_DWORD *)v6 + 12); v8 = (unsigned int)(v8 + 1) )
  {
    v10 = *((_QWORD *)v6 + 5);
    v11 = 32LL * (unsigned int)v8;
    v12 = (*(_BYTE *)(v11 + v10 + 24) & 8) == 0;
    *(_QWORD *)(v11 + v10 + 16) = 232;
    if ( v12 )
      *(_QWORD *)(v11 + v10 + 8) = 0;
  }
  v13 = 48;
  v153 = PerfpBoostPriority(v8, &ThreadInformation);
  v14 = v153;
  if ( v4 < 0x30 )
  {
    v157 = 8;
  }
  else
  {
    v157 = 0;
    Counter.QuadPart = 0;
    Frequency.QuadPart = 0;
    *(_QWORD *)v5 = 0;
    GetSystemTime((LPSYSTEMTIME)v5 + 2);
    GetSystemTimeAsFileTime((LPFILETIME)v5 + 2);
    NtQueryPerformanceCounter(&Counter, &Frequency);
    *((_LARGE_INTEGER *)v5 + 1) = Counter;
    *((union _LARGE_INTEGER *)v5 + 3) = Frequency;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_98cc76a206513ba905b421ef2a045de0_Traceguids);
  PerfpCollectKernelData(v6);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_98cc76a206513ba905b421ef2a045de0_Traceguids);
  v15 = (__int64 *)*((_QWORD *)v6 + 3);
  if ( v15 )
  {
    while ( 1 )
    {
      if ( *(_DWORD *)(v15[1] + 32) != 1 && (*((_BYTE *)v15 + 36) & 4) == 0 )
      {
        v16 = *((_DWORD *)v6 + 23);
        v166 = 0x2000;
        if ( !(unsigned int)PerfpSendNotification(
                              v15[6],
                              (*((unsigned __int16 *)v15 + 16) << 16) | 4u,
                              v15[2],
                              *((_DWORD *)v15 + 7) + v16,
                              (__int64)&Block,
                              (__int64)&v166) )
        {
          v17 = 8;
          if ( v166 > 8 )
          {
            while ( 1 )
            {
              v18 = (unsigned int *)((char *)Block + v17);
              v158 = v18;
              v17 += *v18;
              v19 = v18[3];
              v161 = v17;
              if ( v19 == 4203 )
              {
                *((_DWORD *)v15 + 9) |= 4u;
                goto LABEL_62;
              }
              if ( !v19 )
                break;
LABEL_62:
              if ( v17 >= v166 )
                goto LABEL_63;
            }
            v20 = 16;
            while ( 2 )
            {
              if ( v20 >= *v18 )
              {
LABEL_61:
                v17 = v161;
                goto LABEL_62;
              }
              v21 = (unsigned int *)((char *)v18 + v20);
              v22 = v21[3];
              if ( v22 >= *((_DWORD *)v6 + 12) )
                goto LABEL_60;
              v23 = v21[1];
              v24 = *((_QWORD *)v6 + 5) + 32LL * v22;
              if ( !v23 )
                goto LABEL_106;
              if ( v23 == 1 )
              {
                v60 = *(void **)(v24 + 8);
                v61 = operator new(v21[5]);
                *(_QWORD *)(v24 + 8) = v61;
                if ( v61 )
                {
                  operator delete(v60);
                  v62 = *(void **)(v24 + 8);
                  *(_DWORD *)(v24 + 16) = *v21;
                  *(_DWORD *)(v24 + 20) = v21[1];
                  memcpy_0(v62, v21 + 4, v21[5]);
                  v18 = v158;
                  v9 = i;
                  if ( *(_DWORD *)(v24 + 16) )
                    *(_DWORD *)(v24 + 16) = 0;
                  goto LABEL_60;
                }
                v18 = v158;
                v9 = i;
                if ( v60 )
                {
                  *(_QWORD *)(v24 + 8) = v60;
                  goto LABEL_60;
                }
              }
              else
              {
                if ( v23 != 2 )
                {
                  if ( v23 == 4 )
                  {
                    if ( v21[5] )
                    {
                      if ( *(_QWORD *)(v24 + 8) || (v50 = operator new(24), (*(_QWORD *)(v24 + 8) = v50) != 0) )
                      {
                        v51 = *v21;
                        *(_DWORD *)(v24 + 16) = *v21;
                        *(_DWORD *)(v24 + 20) = v21[1];
                        if ( v51 )
                          *(_DWORD *)(v24 + 16) = 0;
                        v52 = v21[4];
                        if ( v52 > 8 )
                        {
                          v53 = 8;
                          do
                          {
                            v54 = (struct _PERF_INSTANCE_HEADER *)((char *)v21 + v53 + 16);
                            v53 += v54->Size;
                            if ( v53 <= v52 )
                            {
                              v55 = (struct _PERF_COUNTER_DATA *)((char *)v21 + v53 + 16);
                              v53 += v55->dwSize;
                              if ( v53 <= v52 )
                              {
                                if ( ((*(_DWORD *)(v24 + 24) - 4) & 0xFFFFFFF7) == 0 )
                                {
                                  v56 = v9++;
                                  v54->InstanceId = v56;
                                }
                                PerflibciFindOutputInstance(
                                  *(struct PERFLIBCI_MULTI_INSTS **)(v24 + 8),
                                  v54,
                                  v55,
                                  v55->dwSize,
                                  v151);
                              }
                            }
                            v52 = v21[4];
                          }
                          while ( v53 < v52 );
                          i = v9;
                        }
                      }
                      else
                      {
                        *(_QWORD *)(v24 + 16) = 14;
                      }
                    }
                  }
                  else
                  {
                    if ( v23 == 6 )
                    {
                      v25 = v21[4];
                      v26 = (unsigned int *)((char *)v21 + v25 + 16);
                      if ( v26[1] )
                      {
                        if ( *(_QWORD *)(v24 + 8) )
                          goto LABEL_43;
                        v27 = (unsigned int)(v25 + 24);
                        if ( (unsigned int)v25 < (unsigned int)v27 )
                        {
                          v28 = operator new(v27);
                          *(_QWORD *)(v24 + 8) = v28;
                          if ( v28 )
                          {
                            *(_QWORD *)(v28 + 16) = v28 + 24;
                            memcpy_0((void *)(v28 + 24), v21 + 4, v21[4]);
                          }
                        }
                        if ( *(_QWORD *)(v24 + 8) )
                        {
LABEL_43:
                          v29 = *v21;
                          *(_DWORD *)(v24 + 16) = *v21;
                          *(_DWORD *)(v24 + 20) = v21[1];
                          if ( v29 )
                            *(_DWORD *)(v24 + 16) = 0;
                          v30 = *v26;
                          if ( *v26 > 8 )
                          {
                            v31 = i;
                            LODWORD(v32) = 8;
                            do
                            {
                              v33 = 0;
                              v34 = (struct _PERF_INSTANCE_HEADER *)((char *)v26 + (unsigned int)v32);
                              Size = v34->Size;
                              v32 = (unsigned int)(v34->Size + v32);
                              v36 = (unsigned int)v32 <= v30;
                              if ( (unsigned int)v32 < v30 )
                              {
                                v37 = v21[5];
                                for ( j = 0; j < v37; v33 += *(unsigned int *)((char *)v26 + v33 + v32 + 4) )
                                  ++j;
                                Size = v34->Size;
                                LODWORD(v32) = v33 + v32;
                                v36 = (unsigned int)v32 <= v30;
                              }
                              if ( v36 && v33 )
                              {
                                if ( ((*(_DWORD *)(v24 + 24) - 4) & 0xFFFFFFF7) == 0 )
                                {
                                  v39 = v31++;
                                  v34->InstanceId = v39;
                                }
                                PerflibciFindOutputInstance(
                                  *(struct PERFLIBCI_MULTI_INSTS **)(v24 + 8),
                                  v34,
                                  (struct _PERF_COUNTER_DATA *)((char *)v34 + Size),
                                  v33,
                                  v151);
                              }
                              v30 = *v26;
                            }
                            while ( (unsigned int)v32 < *v26 );
                            i = v31;
                            v6 = a1;
                          }
                        }
                        else
                        {
                          *(_QWORD *)(v24 + 16) = 14;
                        }
                      }
                      v9 = i;
                      goto LABEL_59;
                    }
LABEL_106:
                    if ( (v23 & 0xFFFFFFFD) != 0 )
                      *v21 = 13;
                    v63 = *(_DWORD *)(v24 + 16);
                    if ( v63 )
                    {
                      if ( v63 != *v21 )
                      {
                        v12 = (*(_BYTE *)(v24 + 24) & 8) == 0;
                        *(_DWORD *)(v24 + 16) = *v21;
                        *(_DWORD *)(v24 + 20) = v21[1];
                        if ( v12 )
                          *(_QWORD *)(v24 + 8) = 0;
                      }
                    }
                  }
LABEL_59:
                  v18 = v158;
LABEL_60:
                  v40 = v21[2];
                  v20 += v40;
                  if ( !v40 )
                    goto LABEL_61;
                  continue;
                }
                v57 = *(void **)(v24 + 8);
                v58 = operator new(v21[2]);
                *(_QWORD *)(v24 + 8) = v58;
                if ( v58 )
                {
                  operator delete(v57);
                  v59 = *(void **)(v24 + 8);
                  *(_DWORD *)(v24 + 16) = *v21;
                  *(_DWORD *)(v24 + 20) = v21[1];
                  memcpy_0(v59, v21, v21[2]);
                  v18 = v158;
                  if ( *(_DWORD *)(v24 + 16) )
                    *(_DWORD *)(v24 + 16) = 0;
                  goto LABEL_60;
                }
                v18 = v158;
                if ( v57 )
                {
                  *(_QWORD *)(v24 + 8) = v57;
                  goto LABEL_60;
                }
              }
              break;
            }
            *(_QWORD *)(v24 + 16) = 14;
            goto LABEL_60;
          }
LABEL_63:
          operator delete(Block);
        }
      }
      v15 = (__int64 *)*v15;
      if ( !v15 )
      {
        v14 = v153;
        v13 = 48;
        v5 = a2;
        v4 = a3;
        break;
      }
    }
  }
  if ( v14 )
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &ThreadInformation, 4u);
  v41 = 0;
  v42 = 0;
  v162 = 0;
  if ( *((_DWORD *)v6 + 12) )
  {
    while ( 1 )
    {
      v43 = *((_QWORD *)v6 + 5);
      v44 = 32LL * v42;
      v171 = v44;
      v45 = *(_DWORD *)(v44 + v43 + 20);
      if ( v45 != 4 )
      {
        switch ( v45 )
        {
          case 0:
            goto LABEL_122;
          case 1:
            v68 = *(_DWORD **)(v44 + v43 + 8);
            if ( !v68 )
            {
LABEL_113:
              if ( (unsigned __int64)v13 + 16 <= v4 )
              {
                *(_QWORD *)&v5[v13] = 232;
                *(_QWORD *)&v5[v13 + 8] = 16;
LABEL_127:
                v13 += 16;
                goto LABEL_304;
              }
LABEL_126:
              v157 = 8;
              goto LABEL_127;
            }
            v69 = v68[1] + 16;
            v66 = v69 + v13;
            if ( v69 + v13 <= a3 )
            {
              *(_DWORD *)&v5[v13] = *(_DWORD *)(v44 + v43 + 16);
              *(_DWORD *)&v5[v13 + 4] = *(_DWORD *)(v44 + v43 + 20);
              *(_DWORD *)&v5[v13 + 8] = v69;
              *(_DWORD *)&v5[v13 + 12] = 0;
              memcpy_0(&v5[v13 + 16], v68, (unsigned int)v68[1]);
              goto LABEL_118;
            }
LABEL_117:
            v157 = 8;
LABEL_118:
            v13 = v66;
            operator delete(*(void **)(v44 + v43 + 8));
            v4 = a3;
            *(_QWORD *)(v44 + v43 + 8) = 0;
            goto LABEL_304;
          case 2:
            v64 = *(_QWORD *)(v44 + v43 + 8);
            if ( !v64 )
              goto LABEL_113;
            v65 = *(unsigned int *)(v64 + 8);
            v66 = v65 + v13;
            if ( (unsigned int)v65 + v13 > a3 )
              goto LABEL_117;
            *(_DWORD *)&v5[v13] = *(_DWORD *)(v44 + v43 + 16);
            v67 = *(_DWORD *)(v44 + v43 + 20);
            *(_DWORD *)&v5[v13 + 8] = v65;
            *(_DWORD *)&v5[v13 + 4] = v67;
            *(_DWORD *)&v5[v13 + 12] = 0;
            memcpy_0(&v5[v13 + 16], (const void *)(v64 + 16), v65 - 16);
            goto LABEL_118;
        }
        if ( v45 != 6 )
        {
LABEL_122:
          if ( (v45 & 0xFFFFFFF9) != 0 )
            *(_DWORD *)(v44 + v43 + 16) = 13;
          if ( (unsigned __int64)v13 + 16 <= v4 )
          {
            *(_QWORD *)&v5[v13] = *(unsigned int *)(v44 + v43 + 16);
            *(_QWORD *)&v5[v13 + 8] = 16;
            goto LABEL_127;
          }
          goto LABEL_126;
        }
      }
      v46 = *(_QWORD *)(v44 + v43);
      Block = 0;
      v170 = v46;
      v167 = 0;
      if ( !v46 )
        break;
      CounterSet = PerflibciCreateOrFindCounterSet((void *)v46, 0, 0, 0);
      v48 = CounterSet;
      if ( !CounterSet || (*(_BYTE *)(CounterSet + 88) & 4) == 0 )
        goto LABEL_130;
      LOBYTE(v49) = 1;
      v152 = 1;
      if ( *(_DWORD *)(v46 + 24) == -1 )
        v41 = *(_DWORD *)(CounterSet + 128);
      else
        v41 = 1;
LABEL_131:
      if ( *(_DWORD *)(v46 + 20) > 0x28u && PerflibciWildcardInstance((const unsigned __int16 *)(v46 + 40)) )
      {
        v71 = 1;
        v154 = 1;
        if ( (_BYTE)v49 )
        {
          v72 = *(unsigned __int16 *)(v46 + 40) - v70;
          if ( !v72 )
            v72 = *(unsigned __int16 *)(v46 + 42);
          v12 = v72 == 0;
          v71 = 1;
          LOBYTE(v49) = v12;
          v152 = v12;
        }
      }
      else
      {
        v71 = 0;
        v154 = 0;
      }
      v73 = a3;
      v74 = a2;
      if ( (unsigned __int64)v13 + 16 > a3 )
      {
        v78 = 8;
        Counter.QuadPart = 0;
        v157 = 8;
      }
      else
      {
        v75 = *(_DWORD *)(v44 + v43 + 16);
        v76.QuadPart = (LONGLONG)&a2[v13];
        Counter = v76;
        *(_DWORD *)v76.QuadPart = v75;
        *(_QWORD *)(v76.QuadPart + 8) = 16;
        if ( v71 )
          v77 = *(_DWORD *)(v44 + v43 + 20);
        else
          v77 = (*(_DWORD *)(v44 + v43 + 20) == 6) + 1;
        *(_DWORD *)(v76.QuadPart + 4) = v77;
        v78 = v157;
      }
      v156 = v13 + 16;
      v79 = *(_QWORD *)(v44 + v43 + 8);
      if ( *(_DWORD *)(v44 + v43 + 20) != 6 )
        goto LABEL_153;
      if ( !v79 )
      {
        v78 = 13;
        v157 = 13;
LABEL_153:
        v83 = v156;
        goto LABEL_154;
      }
      v80 = *(_DWORD **)(v79 + 16);
      v81 = v156;
      Block = v80;
      v82 = *v80;
      if ( *v80 + v156 > a3 )
      {
        v157 = 8;
      }
      else
      {
        memcpy_0(&a2[v156], Block, v82);
        v80 = Block;
        LOBYTE(v49) = v152;
        v81 = v156;
        v73 = a3;
        v82 = *(_DWORD *)Block;
        v74 = a2;
      }
      if ( Counter.QuadPart )
        *(_DWORD *)(Counter.QuadPart + 8) += v82;
      v83 = *v80 + v81;
      v78 = v157;
      v156 = v83;
LABEL_154:
      if ( (_BYTE)v49 )
      {
        v84 = *((_QWORD *)v6 + 7);
        v167 = 0;
        if ( !v84 )
          goto LABEL_188;
        v85 = *(unsigned int *)(v46 + 32);
        if ( *((_DWORD *)v6 + 16) <= (unsigned int)v85 )
        {
          v78 = v157;
LABEL_188:
          LOBYTE(v49) = 0;
          v152 = 0;
          goto LABEL_166;
        }
        v86 = (__int64 *)(16 * v85 + v84);
        v167 = v86;
        v87 = *((_DWORD *)v86 + 2);
        if ( v87 < v41 )
        {
          operator delete((void *)*v86);
          v86 = v167;
          v87 = 0;
          *v167 = 0;
          *((_DWORD *)v86 + 2) = 0;
        }
        v88 = (void *)*v86;
        if ( v88 )
        {
          memset_0(v88, 0, 24LL * v87);
          v90 = v167;
        }
        else
        {
          v89 = operator new(saturated_mul(v41, 0x18u));
          v90 = v167;
          v91 = 0;
          if ( v89 )
            v91 = v41;
          *((_DWORD *)v167 + 2) = v91;
          *v90 = v89;
        }
        v49 = *v90;
        if ( *v90 )
        {
          v41 = 0;
          *((_DWORD *)v90 + 3) = 0;
          v94 = *(_DWORD *)(v46 + 24);
          if ( v94 == -1 )
          {
            if ( Block )
            {
              v95 = *((_DWORD *)Block + 1);
              v96 = 0;
              if ( v95 )
                goto LABEL_174;
            }
          }
          else
          {
            v95 = 1;
            v96 = 0;
LABEL_174:
            v97 = Block;
            do
            {
              if ( *(_DWORD *)(v46 + 24) == -1 )
                v94 = v97[v96 + 2];
              v98 = *(_DWORD **)(v48 + 120);
              for ( k = *(_DWORD *)(v48 + 128); k; --k )
              {
                if ( v94 == *v98 )
                {
                  *(_DWORD *)(v49 + 8) = *v98;
                  v90 = v167;
                  *(_DWORD *)(v49 + 12) = v98[8];
                  v49 += 24;
                  ++*((_DWORD *)v90 + 3);
                  goto LABEL_183;
                }
                v98 += 14;
              }
              v90 = v167;
LABEL_183:
              ++v96;
            }
            while ( v96 < v95 );
            v42 = v162;
          }
          v12 = *((_DWORD *)v90 + 3) == 0;
          v83 = v156;
          v73 = a3;
          v74 = a2;
          v78 = v157;
          if ( v12 )
          {
            LOBYTE(v49) = 0;
            v152 = 0;
          }
          else
          {
            LOBYTE(v49) = v152;
          }
          goto LABEL_167;
        }
        v83 = v156;
        v73 = a3;
        v74 = a2;
        v78 = v157;
        v152 = 0;
      }
LABEL_166:
      v41 = 0;
LABEL_167:
      v92 = v154;
      if ( v154 )
      {
        if ( (unsigned __int64)v83 + 8 > v73 )
        {
          v78 = 8;
          v93.QuadPart = 0;
          v157 = 8;
        }
        else
        {
          v78 = v157;
          v93.QuadPart = (LONGLONG)&v74[v83];
          *(_QWORD *)v93.QuadPart = 8;
        }
        Frequency = v93;
        if ( Counter.QuadPart )
          *(_DWORD *)(Counter.QuadPart + 8) += 8;
        v156 = v83 + 8;
      }
      else
      {
        v93.QuadPart = 0;
        Frequency.QuadPart = 0;
      }
      if ( *(_QWORD *)(v44 + v43 + 8) )
      {
        v100 = *(_QWORD **)v79;
        if ( v100 )
        {
          v101 = v156;
          while ( 1 )
          {
            v102 = (unsigned int *)v100[4];
            v103 = (_QWORD *)v100[3];
            if ( !v102 )
              goto LABEL_263;
            v104 = v102[2];
            v105 = v102 + 2;
            v106 = *v102;
            v159 = v104;
            if ( !v92 )
              goto LABEL_208;
            v107 = v104 + v106;
            if ( (unsigned int)v107 + v101 > a3 )
            {
              v157 = 8;
              if ( v93.QuadPart )
              {
                ++*(_DWORD *)(v93.QuadPart + 4);
                *(_DWORD *)v93.QuadPart += v106 + *v105;
                v109 = *v105;
              }
              else
              {
                v109 = v102[2];
              }
              v108 = Counter;
              if ( !Counter.QuadPart )
                goto LABEL_207;
            }
            else
            {
              memcpy_0(&a2[v101], v105, v107);
              v93 = Frequency;
              v105 = v102 + 2;
              v108 = Counter;
              v104 = v159;
              LOBYTE(v49) = v152;
              ++*(_DWORD *)(Frequency.QuadPart + 4);
              *(_DWORD *)v93.QuadPart += v106 + v102[2];
              v109 = v102[2];
            }
            *(_DWORD *)(v108.QuadPart + 8) += v106 + v109;
LABEL_207:
            v92 = v154;
            v101 += v106 + *v105;
            v78 = v157;
            v156 = v101;
LABEL_208:
            if ( !(_BYTE)v49 || v78 )
              goto LABEL_263;
            v110 = 0;
            v160 = 0;
            v168 = (unsigned int *)((char *)v102 + v104 + 8);
            v111 = 0;
            if ( !v106 )
              goto LABEL_262;
            v112 = v168;
            v113 = v170;
            v114 = v167;
            v115 = Block;
            while ( 1 )
            {
              v116 = *(_DWORD *)(v113 + 24);
              if ( v116 == -1 && v115 && (unsigned int)v110 < v115[1] )
                v116 = v115[v110 + 2];
              if ( v114 )
              {
                if ( v116 != -1 )
                {
                  if ( *v114 )
                  {
                    v117 = *((_DWORD *)v114 + 3);
                    if ( v117 )
                    {
                      v118 = 0;
                      while ( 1 )
                      {
                        v119 = *v114 + 24 * v118;
                        if ( *(_DWORD *)(v119 + 8) == v116 )
                          break;
                        v118 = (unsigned int)(v118 + 1);
                        if ( (unsigned int)v118 >= v117 )
                          goto LABEL_257;
                      }
                      if ( v119 )
                      {
                        v120 = *(_DWORD *)(v119 + 16);
                        v121 = v168;
                        if ( !v120 )
                          *(_DWORD *)(v119 + 20) = *v168;
                        if ( *v121 == 4 )
                        {
                          v122 = (unsigned int)v121[2];
                        }
                        else if ( *v121 == 8 )
                        {
                          v122 = *((_QWORD *)v121 + 1);
                        }
                        else
                        {
                          v122 = 0;
                        }
                        if ( *(_DWORD *)(v119 + 12) == 1 || *(_DWORD *)(v119 + 12) == 2 )
                        {
                          if ( v122 < 0 )
                            v125 = (double)(int)(v122 & 1 | ((unsigned __int64)v122 >> 1))
                                 + (double)(int)(v122 & 1 | ((unsigned __int64)v122 >> 1));
                          else
                            v125 = (double)(int)v122;
                          v123 = v125 + *(double *)v119;
                          goto LABEL_255;
                        }
                        if ( *(_DWORD *)(v119 + 12) != 3 )
                        {
                          if ( *(_DWORD *)(v119 + 12) != 4 )
                            goto LABEL_256;
                          if ( v120 )
                          {
                            if ( v122 < 0 )
                              v123 = (double)(int)(v122 & 1 | ((unsigned __int64)v122 >> 1))
                                   + (double)(int)(v122 & 1 | ((unsigned __int64)v122 >> 1));
                            else
                              v123 = (double)(int)v122;
                            if ( v123 <= *(double *)v119 )
                              goto LABEL_256;
LABEL_255:
                            *(double *)v119 = v123;
                            goto LABEL_256;
                          }
LABEL_243:
                          if ( v122 < 0 )
                            v123 = (double)(int)(v122 & 1 | ((unsigned __int64)v122 >> 1))
                                 + (double)(int)(v122 & 1 | ((unsigned __int64)v122 >> 1));
                          else
                            v123 = (double)(int)v122;
                          goto LABEL_255;
                        }
                        if ( !v120 )
                          goto LABEL_243;
                        if ( v122 < 0 )
                          v124 = (double)(int)(v122 & 1 | ((unsigned __int64)v122 >> 1))
                               + (double)(int)(v122 & 1 | ((unsigned __int64)v122 >> 1));
                        else
                          v124 = (double)(int)v122;
                        if ( *(double *)v119 > v124 )
                          *(double *)v119 = v124;
LABEL_256:
                        *(_DWORD *)(v119 + 16) = v120 + 1;
                      }
LABEL_257:
                      v112 = v168;
                      LODWORD(v110) = v160;
                    }
                  }
                }
              }
              v126 = (unsigned int)v112[1];
              v111 += v126;
              if ( v111 >= v106 || v111 < (unsigned int)v126 )
                break;
              v110 = (unsigned int)(v110 + 1);
              v112 = (_DWORD *)((char *)v112 + v126);
              v160 = v110;
              v168 = v112;
            }
            v44 = v171;
            v6 = a1;
            v101 = v156;
            v92 = v154;
            v93 = Frequency;
LABEL_262:
            v78 = v157;
            LOBYTE(v49) = v152;
LABEL_263:
            if ( (*(_BYTE *)(v44 + v43 + 24) & 8) == 0 )
            {
              operator delete(v100);
              LOBYTE(v49) = v152;
              v92 = v154;
              v93 = Frequency;
              v78 = v157;
            }
            v100 = v103;
            if ( !v103 )
            {
              v42 = v162;
              v41 = 0;
              v73 = a3;
              break;
            }
          }
        }
        if ( (*(_BYTE *)(v44 + v43 + 24) & 8) == 0 )
        {
          operator delete(*(void **)(v44 + v43 + 8));
          LOBYTE(v49) = v152;
          v92 = v154;
          v73 = a3;
          *(_QWORD *)(v44 + v43 + 8) = 0;
        }
      }
      if ( (_BYTE)v49
        && (v127 = *((_QWORD *)v6 + 7)) != 0
        && (v128 = *(_DWORD *)(v170 + 32), *((_DWORD *)v6 + 16) > v128) )
      {
        v129 = 2LL * v128;
        if ( *(_QWORD *)(v127 + 16LL * v128) && *(_DWORD *)(v127 + 16LL * v128 + 12) )
        {
          v4 = a3;
          if ( v92 )
          {
            v130 = v156 + 24;
            if ( v156 + 24 > a3 )
            {
              v157 = 8;
              v13 = v156 + 24;
              v156 += 24;
            }
            else
            {
              v131 = (unsigned __int16 *)&a2[v156];
              *(_QWORD *)v131 = 24;
              StringCchCopyW(v131 + 4, 7u, L"_Total");
              v156 += 24;
              v13 = v130;
              if ( !v132 )
                goto LABEL_281;
              QuadPart = (_DWORD *)Frequency.QuadPart;
              if ( Frequency.QuadPart )
              {
                ++*(_DWORD *)(Frequency.QuadPart + 4);
                *QuadPart += *v132;
              }
              if ( Counter.QuadPart )
              {
                *(_DWORD *)(Counter.QuadPart + 8) += *v132;
                v73 = a3;
              }
              else
              {
LABEL_281:
                v73 = a3;
              }
            }
          }
          else
          {
            v13 = v156;
          }
          if ( *(_DWORD *)(v127 + 8 * v129 + 12) )
          {
            v134 = 0;
            while ( 1 )
            {
              v135 = *(_QWORD *)(v127 + 8 * v129);
              v136 = 3LL * v134;
              if ( v13 + (unsigned __int64)((*(_DWORD *)(v135 + 24LL * v134 + 20) + 7) & 0xFFFFFFF8) + 8 > v73 )
              {
                v157 = 8;
                goto LABEL_299;
              }
              v137 = &a2[v13];
              v138 = ((*(_DWORD *)(v135 + 24LL * v134 + 20) + 7) & 0xFFFFFFF8) + 8;
              memset_0(v137, 0, v138);
              v139 = (_DWORD *)Frequency.QuadPart;
              *v137 = *(_DWORD *)(v135 + 24LL * v134 + 20);
              v137[1] = v138;
              if ( v139 )
                *v139 += v138;
              if ( Counter.QuadPart )
                *(_DWORD *)(Counter.QuadPart + 8) += v137[1];
              v140 = *(_DWORD *)(v135 + 24LL * v134 + 12);
              if ( !v140 )
              {
LABEL_322:
                v150 = *(_DWORD *)(v135 + 24LL * v134 + 20);
                if ( v150 != 4 )
                {
                  v13 = v156;
                  v73 = a3;
                  if ( v150 == 8 )
                    *((_QWORD *)v137 + 1) = 0;
                  goto LABEL_299;
                }
                v137[2] = 0;
                goto LABEL_298;
              }
              v141 = v140 - 1;
              if ( v141 )
              {
                v142 = v141 - 1;
                if ( !v142 )
                {
                  v145 = *(_DWORD *)(v135 + 24LL * v134 + 20);
                  if ( v145 != 4 )
                  {
                    if ( v145 == 8 )
                    {
                      v146 = 0;
                      v147 = *(double *)(v135 + 24LL * v134) / (double)*(int *)(v135 + 24LL * v134 + 16);
                      if ( v147 >= 9.223372036854776e18 )
                      {
                        v147 = v147 - 9.223372036854776e18;
                        if ( v147 < 9.223372036854776e18 )
                          v146 = 0x8000000000000000uLL;
                      }
                      *((_QWORD *)v137 + 1) = v146 + (unsigned int)(int)v147;
                    }
                    goto LABEL_298;
                  }
                  v144 = (int)(*(double *)(v135 + 24LL * v134) / (double)*(int *)(v135 + 24LL * v134 + 16));
                  goto LABEL_297;
                }
                if ( (unsigned int)(v142 - 1) > 1 )
                  goto LABEL_322;
              }
              v143 = *(_DWORD *)(v135 + 24LL * v134 + 20);
              if ( v143 != 4 )
              {
                if ( v143 == 8 )
                {
                  v148 = *(double *)(v135 + 24LL * v134);
                  v149 = 0;
                  if ( v148 >= 9.223372036854776e18 )
                  {
                    v148 = v148 - 9.223372036854776e18;
                    if ( v148 < 9.223372036854776e18 )
                      v149 = 0x8000000000000000uLL;
                  }
                  *((_QWORD *)v137 + 1) = v149 + (unsigned int)(int)v148;
                }
                goto LABEL_298;
              }
              v144 = (int)*(double *)(v135 + 24LL * v134);
LABEL_297:
              v137[2] = v144;
LABEL_298:
              v13 = v156;
              v73 = a3;
LABEL_299:
              ++v134;
              v13 += ((*(_DWORD *)(v135 + 8 * v136 + 20) + 7) & 0xFFFFFFF8) + 8;
              v156 = v13;
              if ( v134 >= *(_DWORD *)(v127 + 8 * v129 + 12) )
              {
                v42 = v162;
                v6 = a1;
                goto LABEL_301;
              }
            }
          }
        }
        else
        {
          v13 = v156;
LABEL_301:
          v4 = a3;
        }
        v41 = 0;
      }
      else
      {
        v13 = v156;
        v4 = a3;
      }
      v5 = a2;
LABEL_304:
      v162 = ++v42;
      if ( v42 >= *((_DWORD *)v6 + 12) )
        goto LABEL_305;
    }
    v48 = 0;
LABEL_130:
    LOBYTE(v49) = 0;
    v152 = 0;
    goto LABEL_131;
  }
LABEL_305:
  result = v157;
  if ( (v157 & 0xFFFFFFF7) == 0 )
  {
    if ( v4 >= 0x30 )
    {
      *(_DWORD *)v5 = v13;
      *((_DWORD *)v5 + 1) = *((_DWORD *)v6 + 12);
    }
    *a4 = v13;
  }
  return result;
}

```

## disassembly

```asm
0x180001520  mov     rax, rsp
0x180001523  mov     [rax+20h], r9
0x180001527  mov     [rax+18h], r8d
0x18000152b  mov     [rax+10h], rdx
0x18000152f  mov     [rax+8], rcx
0x180001533  push    rbx
0x180001534  push    rbp
0x180001535  push    r13
0x180001537  push    r14
0x180001539  sub     rsp, 0E8h
0x180001540  xor     ebx, ebx
0x180001542  mov     r14d, r8d
0x180001545  mov     [rsp+108h+Block], rbx
0x18000154a  mov     r13, rdx
0x18000154d  mov     [rax-88h], ebx
0x180001553  mov     rbp, rcx
0x180001556  mov     [rax-70h], ebx
0x180001559  test    r9, r9
0x18000155c  jnz     short loc_180001571
0x18000155e  mov     eax, 57h ; 'W'
0x180001563  add     rsp, 0E8h
0x18000156a  pop     r14
0x18000156c  pop     r13
0x18000156e  pop     rbp
0x18000156f  pop     rbx
0x180001570  retn
0x180001571  mov     [r9], ebx
0x180001574  test    r14d, r14d
0x180001577  jz      short loc_180001587
0x180001579  test    r13, r13
0x18000157c  jz      short loc_18000155E
0x18000157e  lea     eax, [r8-1]
0x180001582  mov     [rdx], bl
0x180001584  mov     [rax+rdx], bl
0x180001587  call    ?PerflibciNotifyQuery@@YAXPEAU_PERF_QUERY@@@Z; PerflibciNotifyQuery(_PERF_QUERY *)
0x18000158c  cmp     [rbp+28h], rbx
0x180001590  jnz     short loc_18000159C
0x180001592  mov     eax, 0Eh
0x180001597  jmp     loc_1800026E2
0x18000159c  mov     ecx, ebx
0x18000159e  mov     [rsp+108h+var_28], rsi
0x1800015a6  mov     [rsp+108h+var_30], rdi
0x1800015ae  mov     [rsp+108h+var_38], r12
0x1800015b6  mov     r12d, ebx
0x1800015b9  mov     [rsp+108h+var_40], r15
0x1800015c1  mov     [rsp+108h+var_C4], ebx
0x1800015c5  cmp     [rbp+30h], ebx
0x1800015c8  jbe     short loc_1800015F6
0x1800015ca  nop     word ptr [rax+rax+00h]
0x1800015d0  mov     rdx, [rbp+28h]
0x1800015d4  mov     eax, ecx
0x1800015d6  shl     rax, 5
0x1800015da  test    byte ptr [rax+rdx+18h], 8
0x1800015df  mov     qword ptr [rax+rdx+10h], 0E8h
0x1800015e8  jnz     short loc_1800015EF
0x1800015ea  mov     [rax+rdx+8], rbx
0x1800015ef  inc     ecx; int
0x1800015f1  cmp     ecx, [rbp+30h]
0x1800015f4  jb      short loc_1800015D0
0x1800015f6  lea     rdx, [rsp+108h+ThreadInformation]; int *
0x1800015fe  call    ?PerfpBoostPriority@@YAEJPEAJ@Z; PerfpBoostPriority(long,long *)
0x180001603  mov     r15d, 30h ; '0'
0x180001609  mov     [rsp+108h+var_C7], al
0x18000160d  movzx   edi, al
0x180001610  cmp     r14d, r15d
0x180001613  jb      short loc_18000165F
0x180001615  lea     rcx, [r13+20h]; lpSystemTime
0x180001619  mov     [rsp+108h+var_C0], ebx
0x18000161d  mov     qword ptr [rsp+108h+Counter], rbx
0x180001622  mov     qword ptr [rsp+108h+Frequency], rbx
0x180001627  mov     [r13+0], rbx
0x18000162b  call    cs:__imp_GetSystemTime
0x180001631  lea     rcx, [r13+10h]; lpSystemTimeAsFileTime
0x180001635  call    cs:__imp_GetSystemTimeAsFileTime
0x18000163b  lea     rdx, [rsp+108h+Frequency]; Frequency
0x180001640  lea     rcx, [rsp+108h+Counter]; Counter
0x180001645  call    cs:__imp_NtQueryPerformanceCounter
0x18000164b  mov     rax, qword ptr [rsp+108h+Counter]
0x180001650  mov     [r13+8], rax
0x180001654  mov     rax, qword ptr [rsp+108h+Frequency]
0x180001659  mov     [r13+18h], rax
0x18000165d  jmp     short loc_180001667
0x18000165f  mov     [rsp+108h+var_C0], 8
0x180001667  mov     rcx, cs:WPP_GLOBAL_Control
0x18000166e  test    byte ptr [rcx+1Ch], 8
0x180001672  jz      short loc_18000168F
0x180001674  cmp     byte ptr [rcx+19h], 4
0x180001678  jb      short loc_18000168F
0x18000167a  mov     rcx, [rcx+10h]
0x18000167e  lea     r8, WPP_98cc76a206513ba905b421ef2a045de0_Traceguids
0x180001685  mov     edx, 0Ah
0x18000168a  call    WPP_SF_
0x18000168f  mov     rcx, rbp; struct _PERF_QUERY *
0x180001692  call    ?PerfpCollectKernelData@@YAKPEAU_PERF_QUERY@@@Z; PerfpCollectKernelData(_PERF_QUERY *)
0x180001697  mov     rcx, cs:WPP_GLOBAL_Control
0x18000169e  test    byte ptr [rcx+1Ch], 8
0x1800016a2  jz      short loc_1800016BF
0x1800016a4  cmp     byte ptr [rcx+19h], 4
0x1800016a8  jb      short loc_1800016BF
0x1800016aa  mov     rcx, [rcx+10h]
0x1800016ae  lea     r8, WPP_98cc76a206513ba905b421ef2a045de0_Traceguids
0x1800016b5  mov     edx, 0Bh
0x1800016ba  call    WPP_SF_
0x1800016bf  mov     rbx, [rbp+18h]
0x1800016c3  test    rbx, rbx
0x1800016c6  jz      loc_18000192A
0x1800016cc  xor     r13d, r13d
0x1800016cf  mov     rax, [rbx+8]
0x1800016d3  cmp     dword ptr [rax+20h], 1
0x1800016d7  jz      loc_180001903
0x1800016dd  test    byte ptr [rbx+24h], 4
0x1800016e1  jnz     loc_180001903
0x1800016e7  mov     r9d, [rbp+5Ch]
0x1800016eb  lea     rax, [rsp+108h+var_88]
0x1800016f3  mov     [rsp+108h+var_88], 2000h
0x1800016fe  movzx   edx, word ptr [rbx+20h]
0x180001702  add     r9d, [rbx+1Ch]
0x180001706  mov     r8, [rbx+10h]
0x18000170a  mov     rcx, [rbx+30h]
0x18000170e  mov     qword ptr [rsp+108h+var_E0], rax
0x180001713  lea     rax, [rsp+108h+Block]
0x180001718  shl     edx, 10h
0x18000171b  or      edx, 4
0x18000171e  mov     [rsp+108h+var_E8], rax; int
0x180001723  call    PerfpSendNotification
0x180001728  test    eax, eax
0x18000172a  jnz     loc_180001903
0x180001730  mov     edx, 8
0x180001735  cmp     [rsp+108h+var_88], edx
0x18000173c  jbe     loc_1800018F9
0x180001742  mov     rcx, [rsp+108h+Block]
0x180001747  mov     eax, edx
0x180001749  add     rcx, rax
0x18000174c  mov     [rsp+108h+var_B8], rcx
0x180001751  add     edx, [rcx]
0x180001753  mov     eax, [rcx+0Ch]
0x180001756  mov     [rsp+108h+var_A8], edx
0x18000175a  cmp     eax, 106Bh
0x18000175f  jnz     short loc_18000176A
0x180001761  or      dword ptr [rbx+24h], 4
0x180001765  jmp     loc_1800018EC
0x18000176a  test    eax, eax
0x18000176c  jnz     loc_1800018EC
0x180001772  mov     edi, 10h
0x180001777  cmp     edi, [rcx]
0x180001779  jnb     loc_1800018E8
0x18000177f  mov     r14d, edi
0x180001782  add     r14, rcx
0x180001785  mov     eax, [r14+0Ch]
0x180001789  cmp     eax, [rbp+30h]
0x18000178c  jnb     loc_1800018DA
0x180001792  mov     edx, [r14+4]
0x180001796  mov     esi, eax
0x180001798  shl     rsi, 5
0x18000179c  mov     ecx, edx
0x18000179e  add     rsi, [rbp+28h]
0x1800017a2  test    edx, edx
0x1800017a4  jz      loc_180001BE3
0x1800017aa  sub     ecx, 1
0x1800017ad  jz      loc_180001B65
0x1800017b3  sub     ecx, 1
0x1800017b6  jz      loc_180001AFF
0x1800017bc  sub     ecx, 2
0x1800017bf  jz      loc_180001A4A
0x1800017c5  cmp     ecx, 2
0x1800017c8  jnz     loc_180001BE3
0x1800017ce  mov     eax, [r14+10h]
0x1800017d2  lea     r13, [r14+10h]
0x1800017d6  cmp     dword ptr [rax+r13+4], 0
0x1800017dc  lea     r12, [rax+r13]
0x1800017e0  jz      loc_1800018CD
0x1800017e6  cmp     qword ptr [rsi+8], 0
0x1800017eb  jnz     short loc_180001821
0x1800017ed  lea     ecx, [rax+18h]
0x1800017f0  cmp     eax, ecx
0x1800017f2  jnb     short loc_180001816
0x1800017f4  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x1800017f9  mov     [rsi+8], rax
0x1800017fd  test    rax, rax
0x180001800  jz      short loc_180001816
0x180001802  lea     rcx, [rax+18h]; void *
0x180001806  mov     rdx, r13; Src
0x180001809  mov     [rax+10h], rcx
0x18000180d  mov     r8d, [r13+0]; Size
0x180001811  call    memcpy_0
0x180001816  cmp     qword ptr [rsi+8], 0
0x18000181b  jz      loc_180001A3D
0x180001821  mov     ecx, [r14]
0x180001824  mov     [rsi+10h], ecx
0x180001827  mov     eax, [r14+4]
0x18000182b  mov     [rsi+14h], eax
0x18000182e  test    ecx, ecx
0x180001830  jz      short loc_180001839
0x180001832  mov     dword ptr [rsi+10h], 0
0x180001839  mov     ecx, [r12]
0x18000183d  cmp     ecx, 8
0x180001840  jbe     loc_1800018CD
0x180001846  mov     ebp, [rsp+108h+var_C4]
0x18000184a  mov     r15d, 8
0x180001850  mov     r10d, r15d
0x180001853  xor     r9d, r9d
0x180001856  add     r10, r12
0x180001859  mov     edx, [r10]
0x18000185c  add     r15d, edx
0x18000185f  cmp     r15d, ecx
0x180001862  jnb     short loc_18000188A
0x180001864  mov     r8d, [r13+4]
0x180001868  xor     edx, edx
0x18000186a  test    r8d, r8d
0x18000186d  jz      short loc_180001881
0x18000186f  mov     eax, r9d
0x180001872  inc     edx
0x180001874  add     rax, r12
0x180001877  add     r9d, [rax+r15+4]; unsigned int
0x18000187c  cmp     edx, r8d
0x18000187f  jb      short loc_18000186F
0x180001881  mov     edx, [r10]
0x180001884  add     r15d, r9d
0x180001887  cmp     r15d, ecx
0x18000188a  ja      short loc_1800018B8
0x18000188c  test    r9d, r9d
0x18000188f  jz      short loc_1800018B8
0x180001891  mov     eax, [rsi+18h]
0x180001894  sub     eax, 4
0x180001897  test    eax, 0FFFFFFF7h
0x18000189c  jnz     short loc_1800018A6
0x18000189e  mov     eax, ebp
0x1800018a0  inc     ebp
0x1800018a2  mov     [r10+4], eax
0x1800018a6  mov     rcx, [rsi+8]; struct PERFLIBCI_MULTI_INSTS *
0x1800018aa  mov     r8d, edx
0x1800018ad  mov     rdx, r10; struct _PERF_INSTANCE_HEADER *
0x1800018b0  add     r8, r10; struct _PERF_COUNTER_DATA *
0x1800018b3  call    ?PerflibciFindOutputInstance@@YAPEAUPERFLIBCI_RED_BLACK_NODE@@PEAUPERFLIBCI_MULTI_INSTS@@PEAU_PERF_INSTANCE_HEADER@@PEAU_PERF_COUNTER_DATA@@KH@Z; PerflibciFindOutputInstance(PERFLIBCI_MULTI_INSTS *,_PERF_INSTANCE_HEADER *,_PERF_COUNTER_DATA *,ulong,int)
0x1800018b8  mov     ecx, [r12]
0x1800018bc  cmp     r15d, ecx
0x1800018bf  jb      short loc_180001850
0x1800018c1  mov     [rsp+108h+var_C4], ebp
0x1800018c5  mov     rbp, [rsp+108h+arg_0]
0x1800018cd  mov     r12d, [rsp+108h+var_C4]
0x1800018d2  xor     r13d, r13d
0x1800018d5  mov     rcx, [rsp+108h+var_B8]
0x1800018da  mov     eax, [r14+8]
0x1800018de  add     edi, eax
0x1800018e0  test    eax, eax
0x1800018e2  jnz     loc_180001777
0x1800018e8  mov     edx, [rsp+108h+var_A8]
0x1800018ec  cmp     edx, [rsp+108h+var_88]
0x1800018f3  jb      loc_180001742
0x1800018f9  mov     rcx, [rsp+108h+Block]; Block
0x1800018fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001903  mov     rbx, [rbx]
0x180001906  test    rbx, rbx
0x180001909  jnz     loc_1800016CF
0x18000190f  movzx   edi, [rsp+108h+var_C7]
0x180001914  mov     r15d, 30h ; '0'
0x18000191a  mov     r13, [rsp+108h+arg_8]
0x180001922  mov     r14d, [rsp+108h+arg_10]
0x18000192a  test    dil, dil
0x18000192d  jz      short loc_18000194F
0x18000192f  mov     r9d, 4; ThreadInformationLength
0x180001935  lea     r8, [rsp+108h+ThreadInformation]; ThreadInformation
0x18000193d  mov     edx, 2; ThreadInformationClass
0x180001942  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180001949  call    cs:__imp_NtSetInformationThread
0x18000194f  xor     r12d, r12d
0x180001952  mov     esi, r12d
0x180001955  mov     [rsp+108h+var_A8], r12d
0x18000195a  cmp     [rbp+30h], r12d
0x18000195e  jbe     loc_18000269B
0x180001964  movaps  [rsp+108h+var_58], xmm6
0x18000196c  mov     r10d, 2Ah ; '*'
0x180001972  movsd   xmm6, cs:__real@43e0000000000000
0x18000197a  nop     word ptr [rax+rax+00h]
0x180001980  mov     rdi, [rbp+28h]
0x180001984  mov     ebx, esi
0x180001986  shl     rbx, 5
0x18000198a  mov     [rsp+108h+var_60], rbx
0x180001992  mov     eax, [rbx+rdi+14h]
0x180001996  cmp     eax, 4
0x180001999  jz      short loc_1800019C0
0x18000199b  mov     ecx, eax
0x18000199d  test    eax, eax
0x18000199f  jz      loc_180001D1E
0x1800019a5  sub     ecx, 1
0x1800019a8  jz      loc_180001CCA
0x1800019ae  sub     ecx, 1
0x1800019b1  jz      loc_180001C2A
0x1800019b7  cmp     ecx, 4
0x1800019ba  jnz     loc_180001D1E
0x1800019c0  mov     r13, [rbx+rdi]
0x1800019c4  mov     [rsp+108h+Block], r12
0x1800019c9  mov     [rsp+108h+var_68], r13
0x1800019d1  mov     [rsp+108h+var_80], r12
0x1800019d9  test    r13, r13
0x1800019dc  jz      loc_180001D72
0x1800019e2  mov     [rsp+108h+var_D8], r12d; int
0x1800019e7  xor     r9d, r9d
0x1800019ea  mov     [rsp+108h+var_E0], r12w; __int16
0x1800019f0  xor     r8d, r8d
  ... truncated ...
```
