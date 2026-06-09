# CRchTxtPtr::ReplaceRangeFormatting(long,long,long,IUndoBuilder *,IAntiEvent * *,IAntiEvent * *,long,long,long,long,long)

- ea: `0x180018380`
- end: `0x1800193d2`
- name: `?ReplaceRangeFormatting@CRchTxtPtr@@AEAAJJJJPEAVIUndoBuilder@@PEAPEAVIAntiEvent@@1JJJJJ@Z`
- size: `4178`
- prototype: `int(CRchTxtPtr *__hidden this, int, int, int, struct IUndoBuilder *, struct IAntiEvent **, struct IAntiEvent **, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180017230`

## callees

- `0x180006570`
- `0x180018380`
- `0x1800193e0`
- `0x1800198c0`
- `0x180019940`
- `0x180019d74`
- `0x180019e20`
- `0x18001e3e0`
- `0x180025944`
- `0x18003d774`
- `0x180040be8`
- `0x18004db04`
- `0x18004e31c`
- `0x180093bbe`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CRchTxtPtr::ReplaceRangeFormatting(
        CRchTxtPtr *this,
        int a2,
        int a3,
        unsigned int a4,
        struct IUndoBuilder *a5,
        struct IAntiEvent **a6,
        struct IAntiEvent **a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12)
{
  int *v12; // rbx
  int v13; // r13d
  struct IUndoBuilder *v14; // r12
  unsigned int v15; // r10d
  int v16; // r14d
  __int64 v17; // rax
  int v18; // r15d
  CRchTxtPtr *v19; // rbp
  int v20; // eax
  struct IFormatCache *v21; // r11
  int v22; // r13d
  int v23; // esi
  int v24; // ecx
  struct IFormatCache *v25; // r15
  CArrayBase *v26; // rdx
  int v27; // r8d
  int v28; // ecx
  _DWORD *v29; // r9
  int v30; // ecx
  int v31; // edi
  signed int v32; // ebp
  CArrayBase *v33; // rdx
  int v34; // ecx
  int v35; // r8d
  _DWORD *v36; // r9
  __int64 v37; // r10
  int v38; // eax
  int v39; // ecx
  int v40; // r8d
  int v41; // r11d
  int v42; // eax
  int *v43; // rcx
  int v44; // ecx
  int v45; // eax
  int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  CArrayBase *v49; // r9
  int v50; // ecx
  int *v51; // r8
  int v52; // edx
  int v53; // ecx
  int v54; // r10d
  __int64 v55; // rdx
  CFormatRunPtr *v56; // rdi
  int v57; // r8d
  int v58; // ecx
  _DWORD *v59; // rdx
  int v60; // eax
  int v61; // esi
  struct IFormatCache *v62; // r12
  __int64 v63; // rcx
  int v64; // r8d
  int v65; // edx
  _DWORD *v66; // r9
  int v67; // edx
  int v68; // eax
  _DWORD *v69; // rcx
  int v70; // ecx
  int v71; // ebp
  signed int v72; // esi
  int v73; // ecx
  __int64 v74; // r8
  int v75; // eax
  int *v76; // r8
  int v77; // edx
  int v78; // eax
  __int64 v79; // r9
  int v80; // r10d
  CArrayBase *v82; // rcx
  int v83; // ebp
  int *v84; // rsi
  int *v85; // r12
  int v86; // eax
  int v87; // eax
  int v88; // edx
  int *v89; // rbp
  int v90; // r9d
  int v91; // edx
  __int16 *v92; // rdi
  unsigned int v93; // r14d
  int v94; // r15d
  __int64 v95; // rdx
  int v96; // ecx
  int v97; // r8d
  _DWORD *v98; // r9
  __int64 v99; // r9
  int v100; // eax
  int v101; // eax
  int v102; // ecx
  int v103; // r8d
  int v104; // r11d
  int v105; // eax
  int *v106; // rcx
  int v107; // ecx
  int v108; // eax
  int v109; // eax
  __int64 v110; // rcx
  int v111; // edx
  int v112; // r8d
  CArrayBase *v113; // rdi
  int v114; // eax
  unsigned __int64 v115; // r9
  int v116; // r10d
  __int16 *v117; // r9
  int v118; // eax
  int v119; // ecx
  _DWORD *v120; // rcx
  CArrayBase *v121; // rcx
  int v122; // edx
  int v123; // eax
  CArrayBase *v124; // rcx
  int v125; // edx
  int v126; // eax
  int *v127; // rax
  CArrayBase *v128; // rcx
  int v129; // edx
  int v130; // eax
  __int64 v131; // rcx
  __int16 *v132; // rax
  CArrayBase *v133; // rdx
  int v134; // ecx
  int v135; // eax
  int v136; // esi
  __int64 v137; // rax
  __int64 v138; // rdx
  CArrayBase *v139; // rcx
  int v140; // edx
  int v141; // eax
  _DWORD *v142; // rcx
  __int16 *v143; // rax
  int v144; // ebx
  _DWORD *v145; // rax
  CAntiEventDispenser *v146; // rcx
  unsigned __int64 v147; // rcx
  unsigned __int64 v148; // rdx
  void *v149; // rax
  int v150; // edx
  CArrayBase *v151; // rcx
  _DWORD *v152; // rax
  CAntiEventDispenser *v153; // rcx
  int v154; // [rsp+30h] [rbp-78h]
  int v155; // [rsp+34h] [rbp-74h]
  int v156; // [rsp+38h] [rbp-70h]
  int v157; // [rsp+3Ch] [rbp-6Ch]
  struct IFormatCache *v158; // [rsp+40h] [rbp-68h]
  struct IFormatCache *v159; // [rsp+48h] [rbp-60h]
  unsigned __int64 v160[11]; // [rsp+50h] [rbp-58h] BYREF

  v12 = (int *)((char *)this + 48);
  v13 = *((_DWORD *)this + 8);
  v14 = a5;
  v15 = a4;
  v159 = qword_1800A72C8;
  v16 = a3;
  v17 = *((_QWORD *)this + 6);
  v18 = a2;
  v155 = v13;
  v19 = this;
  if ( !v17 || !*(_DWORD *)(v17 + 8) )
    goto LABEL_69;
  v20 = *((_DWORD *)this + 14);
  v21 = qword_1800A72D0;
  v158 = qword_1800A72D0;
  v22 = v20 - 1;
  if ( v20 <= 0 )
    v22 = *((_DWORD *)this + 14);
  v23 = a12 + a2 + a11;
  if ( v23 > 0 )
  {
    if ( a5 )
    {
      CRunPtrBase::AdvanceCp((CRchTxtPtr *)((char *)this + 48), -a11);
      *a6 = CAntiEventDispenser::CreateReplaceFormattingAE(
              v146,
              *((struct CTxtEdit **)v19 + 5),
              (struct CFormatRunPtr *)v12,
              v23,
              v158,
              0);
      CRunPtrBase::AdvanceCp((CRunPtrBase *)v12, a11);
      v15 = a4;
      v21 = v158;
      v18 = a2;
    }
    if ( v18 )
    {
      CFormatRunPtr::Delete((CFormatRunPtr *)v12, v18, v21, 0);
      v15 = a4;
      v21 = v158;
    }
  }
  if ( v16 <= 1 )
  {
    if ( !v16 )
      goto LABEL_11;
    v24 = *((_QWORD *)v19 + 5) ? *(_DWORD *)(*((_QWORD *)v19 + 2) + 24LL) : 0;
    if ( v18 > v24 )
      goto LABEL_11;
  }
  v82 = *(CArrayBase **)v12;
  if ( !*(_QWORD *)v12 || !*((_DWORD *)v82 + 2) )
  {
    v92 = (__int16 *)CArrayBase::ArAdd(v82, 1, 0);
    v84 = v12 + 3;
LABEL_146:
    v25 = v158;
LABEL_147:
    (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))v25)(v25, a4);
    *(_QWORD *)v92 = 0;
    v92[2] = a4;
    v19 = this;
    *(_DWORD *)v92 = v16;
    *v84 = v16;
    goto LABEL_12;
  }
  v83 = v12[3];
  v84 = v12 + 3;
  v85 = v12 + 2;
  if ( !v83 )
  {
    v86 = *v85;
    *v84 = 0;
    if ( v86 <= 0 )
    {
      v83 = 0;
    }
    else
    {
      v87 = v86 - 1;
      *v85 = v87;
      v88 = *((_DWORD *)v82 + 2);
      if ( v88 > 0 && v87 < v88 && *(_QWORD *)v82 && v87 >= 0 )
        v89 = (int *)(*(_QWORD *)v82 + *((_DWORD *)v82 + 4) * v87);
      else
        v89 = 0;
      v83 = *v89;
      *v84 = v83;
    }
  }
  v90 = *((_DWORD *)v82 + 2);
  v91 = *v85;
  if ( v90 > 0 && v91 < v90 && *(_QWORD *)v82 && v91 >= 0 )
    v92 = (__int16 *)(*(_QWORD *)v82 + *((_DWORD *)v82 + 4) * v91);
  else
    v92 = 0;
  v93 = v92[2];
  v94 = *(_DWORD *)v92;
  if ( v15 != v93 )
  {
    if ( v83 == v94 && v91 < v90 - 1 )
    {
      if ( v90 )
      {
        v120 = v90 > 0 && v91 < v90 && *(_QWORD *)v82 && v91 >= 0
             ? (_DWORD *)(*(_QWORD *)v82 + *((_DWORD *)v82 + 4) * v91)
             : 0LL;
        if ( *v120 == *v84 )
          CRunPtrBase::NextRun((CRunPtrBase *)v12);
      }
      v121 = *(CArrayBase **)v12;
      v122 = *(_DWORD *)(*(_QWORD *)v12 + 8LL);
      if ( v122 > 0 && (v123 = *v85, *v85 < v122) && *(_QWORD *)v121 && v123 >= 0 )
        v92 = (__int16 *)(*(_QWORD *)v121 + *((_DWORD *)v121 + 4) * v123);
      else
        v92 = 0;
      if ( v92[2] == v15 )
      {
        v16 = a3;
        *(_DWORD *)v92 += a3;
        goto LABEL_138;
      }
      if ( !*((_DWORD *)this + 15) && (unsigned int)CRunPtrBase::PrevRun((CRunPtrBase *)v12) )
      {
        v124 = *(CArrayBase **)v12;
        v125 = *(_DWORD *)(*(_QWORD *)v12 + 8LL);
        if ( v125 > 0 && (v126 = *v85, *v85 < v125) && *(_QWORD *)v124 && v126 >= 0 )
          v127 = (int *)(*(_QWORD *)v124 + *((_DWORD *)v124 + 4) * v126);
        else
          v127 = 0;
        *v84 = *v127;
      }
    }
    if ( !v83 && *v85 > 0 && v15 == *(v92 - 2) )
    {
      v16 = a3;
      *((_DWORD *)v92 - 2) += a3;
      v19 = this;
      goto LABEL_11;
    }
    if ( !*(_DWORD *)v92 )
    {
      (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v21 + 8LL))(v21, (unsigned int)v92[2]);
LABEL_197:
      v16 = a3;
      goto LABEL_146;
    }
    v111 = 1;
    v154 = 1;
    if ( v83 )
    {
      if ( v83 < v94 )
        v111 = 2;
      v154 = v111;
    }
    v112 = *v85;
    v113 = *(CArrayBase **)v12;
    v157 = *v85;
    v114 = *(_DWORD *)(*(_QWORD *)v12 + 8LL);
    if ( *v85 >= v114 )
    {
      v132 = (__int16 *)CArrayBase::ArAdd(v113, v111, 0);
      v111 = v154;
      v117 = v132;
    }
    else
    {
      v115 = *((int *)v113 + 3);
      if ( v111 + v114 > (int)v115 )
      {
        v156 = v114 / 16 + 8;
        v147 = v115 + v156;
        if ( v147 < v115 )
          goto LABEL_303;
        v148 = *((int *)v113 + 4);
        v160[0] = v115 + v156;
        if ( (int)ULongLongMult(v147, v148, v160) < 0 )
          goto LABEL_303;
        v149 = CW32System::PvReAlloc(*(void **)v113, v160[0]);
        if ( !v149 )
          goto LABEL_303;
        v111 = v154;
        v112 = v157;
        *(_QWORD *)v113 = v149;
        *((_DWORD *)v113 + 3) += v156;
      }
      v116 = *((_DWORD *)v113 + 4);
      v117 = (__int16 *)(*(_QWORD *)v113 + v116 * v112);
      v118 = *((_DWORD *)v113 + 2);
      v160[0] = (unsigned __int64)v117;
      if ( v112 < v118 )
      {
        memmove_0((char *)v117 + v111 * v116, v117, v116 * (v118 - v112));
        v111 = v154;
        v117 = (__int16 *)v160[0];
      }
      *((_DWORD *)v113 + 2) += v111;
    }
    if ( v117 )
    {
      if ( !v83 )
      {
        v16 = a3;
        v92 = v117;
        goto LABEL_146;
      }
      v92 = v117 + 4;
      *((_DWORD *)v117 + 2) = a3;
      if ( *(_QWORD *)v12 )
      {
        v119 = *v85;
        if ( *v85 < *(_DWORD *)(*(_QWORD *)v12 + 8LL) - 1 )
        {
          *v84 = 0;
          *v85 = v119 + 1;
        }
      }
      if ( v111 == 2 )
      {
        *(_DWORD *)v117 = v83;
        *((_DWORD *)v117 + 4) = v94 - v83;
        v25 = v158;
        (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))v158)(v158, v93);
        v16 = a3;
        goto LABEL_147;
      }
      goto LABEL_197;
    }
LABEL_303:
    v16 = a3;
    v150 = *v85;
    v151 = *(CArrayBase **)v12;
    *v84 += a3;
    v152 = CArrayBase::Elem(v151, v150);
    v19 = this;
    *v152 += a3;
    goto LABEL_11;
  }
  v16 = a3;
  *(_DWORD *)v92 = v94 + a3;
LABEL_138:
  v19 = this;
  *v84 = v16 + *((_DWORD *)this + 15);
LABEL_11:
  v25 = v158;
LABEL_12:
  if ( (a2 || v16) && (v26 = *(CArrayBase **)v12) != 0 && (v27 = *((_DWORD *)v26 + 2)) != 0 )
  {
    v28 = *((_DWORD *)v19 + 14);
    if ( v27 > 0 && v28 < v27 && *(_QWORD *)v26 && v28 >= 0 )
      v29 = (_DWORD *)(*(_QWORD *)v26 + *((_DWORD *)v26 + 4) * v28);
    else
      v29 = 0;
    if ( *v29 == *((_DWORD *)v19 + 15) && v28 < v27 - 1 )
      *((_QWORD *)v19 + 7) = (unsigned int)(v28 + 1);
    v30 = v12[2];
    if ( v22 - v30 >= 0 )
      v31 = v22 - v30;
    else
      v31 = v30 - v22;
    v32 = (((v22 - v30) >> 31) & 0xFFFFFFFE) + 1;
    if ( !*((_DWORD *)v26 + 2) )
      CRunPtrBase::SetRun((CRunPtrBase *)v12, v30 + v32, 0);
    if ( v31 )
    {
      while ( 1 )
      {
        v33 = *(CArrayBase **)v12;
        v34 = v12[2];
        v35 = *(_DWORD *)(*(_QWORD *)v12 + 8LL);
        if ( v35 > 0 && v34 < v35 && *(_QWORD *)v33 && v34 >= 0 )
          v36 = (_DWORD *)(*(_QWORD *)v33 + *((_DWORD *)v33 + 4) * v34);
        else
          v36 = 0;
        if ( !*v36 && !v34 && v35 - 1 > 0 )
        {
          if ( v32 > 0 )
            CRunPtrBase::PrevRun((CRunPtrBase *)v12);
          v128 = *(CArrayBase **)v12;
          v129 = *(_DWORD *)(*(_QWORD *)v12 + 8LL);
          if ( v129 > 0 && (v130 = v12[2], v130 < v129) && *(_QWORD *)v128 && v130 >= 0 )
            v131 = *(_QWORD *)v128 + *((_DWORD *)v128 + 4) * v130;
          else
            v131 = 0;
          (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v25 + 8LL))(
            v25,
            (unsigned int)*(__int16 *)(v131 + 4));
          CArrayBase::Remove(*(CArrayBase **)v12, v12[2], 1);
          goto LABEL_55;
        }
        if ( v35 > 0 && v34 < v35 && *(_QWORD *)v33 && v34 >= 0 )
        {
          v37 = *(_QWORD *)v33 + *((_DWORD *)v33 + 4) * v34;
        }
        else
        {
          if ( !v33 )
            goto LABEL_56;
          v37 = 0;
          if ( !v35 )
            goto LABEL_56;
        }
        v38 = v34 + v32;
        if ( v34 + v32 >= v35 )
        {
          v39 = 0;
          v38 = v35 - 1;
        }
        else
        {
          v39 = 1;
        }
        v12[3] = 0;
        v40 = 0;
        v41 = 0;
        if ( v38 >= 0 )
        {
          v40 = v38;
          v41 = v39;
        }
        v12[2] = v40;
        v42 = *((_DWORD *)v33 + 2);
        if ( v42 > 0 && v40 < v42 && *(_QWORD *)v33 )
          v43 = (int *)(*(_QWORD *)v33 + *((_DWORD *)v33 + 4) * v40);
        else
          v43 = 0;
        v44 = *v43;
        v45 = 0;
        if ( v44 <= 0 )
          v45 = v44;
        v12[3] = v45;
        if ( !v41 )
          goto LABEL_56;
        v46 = *((_DWORD *)v33 + 2);
        if ( v46 > 0 && v40 < v46 && *(_QWORD *)v33 )
          v47 = *(_QWORD *)v33 + *((_DWORD *)v33 + 4) * v40;
        else
          v47 = 0;
        if ( *(_WORD *)(v37 + 4) == *(_WORD *)(v47 + 4)
          && *(_BYTE *)(v37 + 6) == *(_BYTE *)(v47 + 6)
          && ((*(_BYTE *)(v37 + 7) ^ *(_BYTE *)(v47 + 7)) & 1) == 0 )
        {
          break;
        }
LABEL_55:
        if ( !--v31 )
          goto LABEL_56;
      }
      if ( v32 > 0 )
        CRunPtrBase::PrevRun((CRunPtrBase *)v12);
      v133 = *(CArrayBase **)v12;
      v134 = v12[2];
      v135 = *(_DWORD *)(*(_QWORD *)v12 + 8LL);
      if ( v135 > 0 && v134 < v135 && *(_QWORD *)v133 && v134 >= 0 )
      {
        v136 = *(_DWORD *)(*((_DWORD *)v133 + 4) * v134 + *(_QWORD *)v133);
        v137 = *(_QWORD *)v133;
      }
      else
      {
        v136 = MEMORY[0];
        if ( v135 <= 0 || v134 >= v135 || (v137 = *(_QWORD *)v133) == 0 || v134 < 0 )
        {
          v138 = 0;
LABEL_247:
          (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v25 + 8LL))(
            v25,
            (unsigned int)*(__int16 *)(v138 + 4));
          CArrayBase::Remove(*(CArrayBase **)v12, v12[2], 1);
          v139 = *(CArrayBase **)v12;
          v140 = *(_DWORD *)(*(_QWORD *)v12 + 8LL);
          if ( v140 > 0 && (v141 = v12[2], v141 < v140) && *(_QWORD *)v139 && v141 >= 0 )
            v142 = (_DWORD *)(*(_QWORD *)v139 + *((_DWORD *)v139 + 4) * v141);
          else
            v142 = 0;
          *v142 += v136;
          goto LABEL_55;
        }
      }
      v138 = v137 + *((_DWORD *)v133 + 4) * v134;
      goto LABEL_247;
    }
LABEL_56:
    v13 = v155;
    *((_QWORD *)v12 + 1) = 0;
    v48 = v16 + v155;
    if ( v16 + v155 )
    {
      v49 = *(CArrayBase **)v12;
      if ( *(_QWORD *)v12 )
      {
        v50 = *((_DWORD *)v49 + 2);
        if ( v50 )
        {
          if ( v48 < 0 )
          {
            *((_QWORD *)v12 + 1) = 0;
          }
          else
          {
            if ( v50 <= 0 || (v51 = *(int **)v49) == 0 )
              v51 = 0;
            v52 = 0;
            while ( v48 > 0 )
            {
              v53 = *v51;
              v12[3] = v48;
              if ( v48 < v53 )
                break;
              v54 = v52++;
              v12[2] = v52;
              if ( v52 >= *((_DWORD *)v49 + 2) )
              {
                v12[2] = v54;
                v12[3] = v53;
                break;
              }
              v48 -= v53;
              v12[3] = 0;
              v51 = (int *)((char *)v51 + *((int *)v49 + 4));
            }
          }
        }
      }
    }
  }
  else
  {
    v13 = v155;
  }
  v14 = a5;
  v18 = a2;
LABEL_69:
  v55 = *((_QWORD *)this + 8);
  v56 = (CRchTxtPtr *)((char *)this + 64);
  if ( v55 )
  {
    v57 = *(_DWORD *)(v55 + 8);
    if ( v57 )
    {
      v58 = *((_DWORD *)this + 18);
      if ( v57 > 0 && v58 < v57 && *(_QWORD *)v55 && v58 >= 0 )
        v59 = (_DWORD *)(*(_QWORD *)v55 + *(_DWORD *)(v55 + 16) * v58);
      else
        v59 = 0;
      if ( *v59 == *((_DWORD *)this + 19) && v58 < v57 - 1 )
      {
        *((_DWORD *)this + 19) = 0;
        *((_DWORD *)this + 18) = v58 + 1;
      }
      v60 = *((_DWORD *)this + 18);
      v61 = v60 - 1;
      if ( v60 <= 0 )
        v61 = *((_DWORD *)this + 18);
      if ( v18 )
      {
        if ( v14 )
        {
          *(_OWORD *)v160 = *(_OWORD *)v56;
          CRunPtrBase::AdvanceCp((CRunPtrBase *)v160, a9);
          v62 = v159;
          *a7 = CAntiEventDispenser::CreateReplaceFormattingAE(
                  v153,
                  *((struct CTxtEdit **)this + 5),
                  (struct CFormatRunPtr *)v160,
                  a10 - a9,
                  v159,
                  1);
        }
        else
        {
          v62 = v159;
        }
        CFormatRunPtr::Delete(v56, v18, v62, a8);
      }
      else
      {
        v62 = v159;
      }
      v63 = *(_QWORD *)v56;
      if ( *(_QWORD *)v56 )
      {
        v64 = *(_DWORD *)(v63 + 8);
        if ( v64 )
        {
          v65 = *((_DWORD *)this + 18);
          if ( v64 > 0 && v65 < v64 && *(_QWORD *)v63 && v65 >= 0 )
            v66 = (_DWORD *)(*(_QWORD *)v63 + *(_DWORD *)(v63 + 16) * v65);
          else
            v66 = 0;
          if ( *v66 == *((_DWORD *)this + 19) && v65 < v64 - 1 )
            *((_QWORD *)this + 9) = (unsigned int)(v65 + 1);
          v67 = *(_DWORD *)(v63 + 8);
          if ( v67 > 0 && (v68 = *((_DWORD *)this + 18), v68 < v67) && *(_QWORD *)v63 && v68 >= 0 )
            v69 = (_DWORD *)(*(_QWORD *)v63 + *(_DWORD *)(v63 + 16) * v68);
          else
            v69 = 0;
          *v69 += v16;
          *((_DWORD *)this + 19) += v16;
          if ( v18 || v16 )
          {
            v70 = *((_DWORD *)this + 18);
            if ( v61 - v70 >= 0 )
              v71 = v61 - v70;
            else
              v71 = v70 - v61;
            v72 = (((v61 - v70) >> 31) & 0xFFFFFFFE) + 1;
            if ( !*(_QWORD *)v56 || !*(_DWORD *)(*(_QWORD *)v56 + 8LL) )
              CRunPtrBase::SetRun(v56, v70 + v72, 0);
            for ( ; v71; --v71 )
            {
              v95 = *(_QWORD *)v56;
              v96 = *((_DWORD *)this + 18);
              v97 = *(_DWORD *)(*(_QWORD *)v56 + 8LL);
              if ( v97 > 0 && v96 < v97 && *(_QWORD *)v95 && v96 >= 0 )
                v98 = (_DWORD *)(*(_QWORD *)v95 + *(_DWORD *)(v95 + 16) * v96);
              else
                v98 = 0;
              if ( *v98 || v96 || v97 - 1 <= 0 )
              {
                if ( v97 > 0 && v96 < v97 && *(_QWORD *)v95 && v96 >= 0 )
                {
                  v99 = *(_QWORD *)v95 + *(_DWORD *)(v95 + 16) * v96;
                  v100 = *((_DWORD *)this + 18);
                }
                else
                {
                  v99 = 0;
                  v100 = *((_DWORD *)this + 18);
                  if ( !v95 || !v97 )
                    break;
                }
                v101 = v72 + v100;
                if ( v101 >= v97 )
                {
                  v102 = 0;
                  v101 = v97 - 1;
                }
                else
                {
                  v102 = 1;
                }
                *((_DWORD *)this + 19) = 0;
                v103 = 0;
                v104 = 0;
                if ( v101 >= 0 )
                {
                  v103 = v101;
                  v104 = v102;
                }
                *((_DWORD *)this + 18) = v103;
                v105 = *(_DWORD *)(v95 + 8);
                if ( v105 > 0 && v103 < v105 && *(_QWORD *)v95 )
                  v106 = (int *)(*(_QWORD *)v95 + *(_DWORD *)(v95 + 16) * v103);
                else
                  v106 = 0;
                v107 = *v106;
                v108 = 0;
                if ( v107 <= 0 )
                  v108 = v107;
                *((_DWORD *)this + 19) = v108;
                if ( !v104 )
                  break;
                v109 = *(_DWORD *)(v95 + 8);
                if ( v109 > 0 && v103 < v109 && *(_QWORD *)v95 )
                  v110 = *(_QWORD *)v95 + *(_DWORD *)(v95 + 16) * v103;
                else
                  v110 = 0;
                if ( *(_WORD *)(v99 + 4) == *(_WORD *)(v110 + 4)
                  && *(_BYTE *)(v99 + 6) == *(_BYTE *)(v110 + 6)
                  && ((*(_BYTE *)(v99 + 7) ^ *(_BYTE *)(v110 + 7)) & 1) == 0 )
                {
                  if ( v72 > 0 )
                    CRunPtrBase::PrevRun(v56);
                  v143 = (__int16 *)CArrayBase::Elem(*((CArrayBase **)this + 8), *((_DWORD *)this + 18));
                  v144 = *(_DWORD *)v143;
                  (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v62 + 8LL))(
                    v62,
                    (unsigned int)v143[2]);
                  CArrayBase::Remove(*((CArrayBase **)this + 8), *((_DWORD *)this + 18), 1);
                  v145 = CArrayBase::Elem(*((CArrayBase **)this + 8), *((_DWORD *)this + 18));
                  *v145 += v144;
                }
              }
              else
              {
                if ( v72 > 0 )
                  CRunPtrBase::PrevRun(v56);
                CFormatRunPtr::Remove(v56, 1, v62);
              }
            }
            v73 = v16 + v13;
            *((_QWORD *)this + 9) = 0;
            if ( v16 + v13 )
            {
              v74 = *(_QWORD *)v56;
              if ( *(_QWORD *)v56 )
              {
                v75 = *(_DWORD *)(v74 + 8);
                if ( v75 )
                {
                  if ( v73 < 0 )
                  {
                    *((_QWORD *)this + 9) = 0;
                  }
                  else
                  {
                    if ( v75 <= 0 || (v76 = *(int **)v74) == 0 )
                      v76 = 0;
                    v77 = 0;
                    while ( v73 > 0 )
                    {
                      v78 = *v76;
                      *((_DWORD *)this + 19) = v73;
                      if ( v73 < v78 )
                        break;
                      v79 = *(_QWORD *)v56;
                      v80 = v77++;
                      *((_DWORD *)this + 18) = v77;
                      if ( v77 >= *(_DWORD *)(v79 + 8) )
                      {
                        *((_DWORD *)this + 18) = v80;
                        *((_DWORD *)this + 19) = v78;
                        return (unsigned int)v16;
                      }
                      v73 -= v78;
                      *((_DWORD *)this + 19) = 0;
                      v76 = (int *)((char *)v76 + *(int *)(v79 + 16));
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180018380  mov     [rsp+arg_18], r9d
0x180018385  mov     [rsp+arg_10], r8d
0x18001838a  mov     [rsp+arg_8], edx
0x18001838e  mov     [rsp+arg_0], rcx
0x180018393  push    rbx
0x180018394  push    rbp
0x180018395  push    rsi
0x180018396  push    rdi
0x180018397  push    r12
0x180018399  push    r13
0x18001839b  push    r14
0x18001839d  push    r15
0x18001839f  sub     rsp, 68h
0x1800183a3  mov     rax, cs:qword_1800A72C8
0x1800183aa  lea     rbx, [rcx+30h]
0x1800183ae  mov     r13d, [rcx+20h]
0x1800183b2  xor     esi, esi
0x1800183b4  mov     r12, [rsp+0A8h+arg_20]
0x1800183bc  mov     r10d, r9d
0x1800183bf  mov     [rsp+0A8h+var_60], rax
0x1800183c4  mov     r14d, r8d
0x1800183c7  mov     rax, [rbx]
0x1800183ca  mov     r15d, edx
0x1800183cd  mov     [rsp+0A8h+var_74], r13d
0x1800183d2  mov     rbp, rcx
0x1800183d5  test    rax, rax
0x1800183d8  jz      loc_1800186AC
0x1800183de  cmp     [rax+8], esi
0x1800183e1  jz      loc_1800186AC
0x1800183e7  mov     eax, [rcx+38h]
0x1800183ea  test    eax, eax
0x1800183ec  mov     edi, [rsp+0A8h+arg_50]
0x1800183f3  mov     r11, cs:qword_1800A72D0
0x1800183fa  mov     [rsp+0A8h+var_68], r11
0x1800183ff  lea     r13d, [rax-1]
0x180018403  cmovle  r13d, eax
0x180018407  lea     esi, [rdx+rdi]
0x18001840a  add     esi, [rsp+0A8h+arg_58]
0x180018411  test    esi, esi
0x180018413  jg      loc_1800189A7
0x180018419  cmp     r14d, 1
0x18001841d  jg      loc_1800188BE
0x180018423  test    r14d, r14d
0x180018426  jz      short loc_180018443
0x180018428  cmp     qword ptr [rbp+28h], 0
0x18001842d  jz      loc_1800190F3
0x180018433  mov     rax, [rbp+10h]
0x180018437  mov     ecx, [rax+18h]
0x18001843a  cmp     r15d, ecx
0x18001843d  jle     loc_1800188BE
0x180018443  mov     r15, [rsp+0A8h+var_68]
0x180018448  cmp     [rsp+0A8h+arg_8], 0
0x180018450  jz      loc_1800188B0
0x180018456  mov     rdx, [rbx]
0x180018459  test    rdx, rdx
0x18001845c  jz      loc_180018695
0x180018462  mov     r8d, [rdx+8]
0x180018466  test    r8d, r8d
0x180018469  jz      loc_180018695
0x18001846f  mov     ecx, [rbp+38h]
0x180018472  jle     loc_1800190C1
0x180018478  cmp     ecx, r8d
0x18001847b  jge     loc_1800190C1
0x180018481  mov     r10, [rdx]
0x180018484  test    r10, r10
0x180018487  jz      loc_1800190C1
0x18001848d  test    ecx, ecx
0x18001848f  js      loc_1800190C1
0x180018495  mov     eax, ecx
0x180018497  imul    eax, [rdx+10h]
0x18001849b  movsxd  r9, eax
0x18001849e  add     r9, r10
0x1800184a1  xor     esi, esi
0x1800184a3  mov     eax, [rbp+3Ch]
0x1800184a6  cmp     [r9], eax
0x1800184a9  jnz     short loc_1800184BC
0x1800184ab  lea     eax, [r8-1]
0x1800184af  cmp     ecx, eax
0x1800184b1  jge     short loc_1800184BC
0x1800184b3  lea     eax, [rcx+1]
0x1800184b6  mov     [rbp+3Ch], esi
0x1800184b9  mov     [rbp+38h], eax
0x1800184bc  mov     ecx, [rbx+8]
0x1800184bf  mov     eax, r13d
0x1800184c2  sub     eax, ecx
0x1800184c4  jns     loc_1800188A9
0x1800184ca  mov     edi, ecx
0x1800184cc  sub     edi, r13d
0x1800184cf  sar     eax, 1Fh
0x1800184d2  and     eax, 0FFFFFFFEh
0x1800184d5  cmp     dword ptr [rdx+8], 0
0x1800184d9  lea     ebp, [rax+1]
0x1800184dc  jz      loc_180019302
0x1800184e2  test    edi, edi
0x1800184e4  jz      loc_180018624
0x1800184ea  mov     rdx, [rbx]
0x1800184ed  mov     ecx, [rbx+8]
0x1800184f0  mov     r8d, [rdx+8]
0x1800184f4  test    r8d, r8d
0x1800184f7  jle     loc_18001909F
0x1800184fd  cmp     ecx, r8d
0x180018500  jge     loc_18001909F
0x180018506  mov     r10, [rdx]
0x180018509  test    r10, r10
0x18001850c  jz      loc_18001909F
0x180018512  test    ecx, ecx
0x180018514  js      loc_18001909F
0x18001851a  mov     eax, ecx
0x18001851c  imul    eax, [rdx+10h]
0x180018520  movsxd  r9, eax
0x180018523  add     r9, r10
0x180018526  cmp     dword ptr [r9], 0
0x18001852a  jz      loc_180018E9C
0x180018530  test    r8d, r8d
0x180018533  jle     loc_1800190A7
0x180018539  cmp     ecx, r8d
0x18001853c  jge     loc_1800190A7
0x180018542  mov     r9, [rdx]
0x180018545  test    r9, r9
0x180018548  jz      loc_1800190A7
0x18001854e  test    ecx, ecx
0x180018550  js      loc_1800190A7
0x180018556  mov     eax, ecx
0x180018558  imul    eax, [rdx+10h]
0x18001855c  movsxd  r10, eax
0x18001855f  add     r10, r9
0x180018562  lea     eax, [rcx+rbp]
0x180018565  cmp     eax, r8d
0x180018568  jge     loc_180019322
0x18001856e  mov     ecx, 1
0x180018573  test    eax, eax
0x180018575  mov     [rbx+0Ch], esi
0x180018578  mov     r8d, esi
0x18001857b  mov     r11d, esi
0x18001857e  cmovns  r8d, eax
0x180018582  cmovns  r11d, ecx
0x180018586  mov     [rbx+8], r8d
0x18001858a  mov     eax, [rdx+8]
0x18001858d  test    eax, eax
0x18001858f  jle     loc_1800190CB
0x180018595  cmp     r8d, eax
0x180018598  jge     loc_1800190CB
0x18001859e  mov     r9, [rdx]
0x1800185a1  test    r9, r9
0x1800185a4  jz      loc_1800190CB
0x1800185aa  test    r8d, r8d
0x1800185ad  js      loc_1800190CB
0x1800185b3  mov     eax, r8d
0x1800185b6  imul    eax, [rdx+10h]
0x1800185ba  movsxd  rcx, eax
0x1800185bd  add     rcx, r9
0x1800185c0  mov     ecx, [rcx]
0x1800185c2  mov     eax, esi
0x1800185c4  test    ecx, ecx
0x1800185c6  cmovle  eax, ecx
0x1800185c9  mov     [rbx+0Ch], eax
0x1800185cc  test    r11d, r11d
0x1800185cf  jz      short loc_180018622
0x1800185d1  mov     eax, [rdx+8]
0x1800185d4  test    eax, eax
0x1800185d6  jle     loc_1800190DB
0x1800185dc  cmp     r8d, eax
0x1800185df  jge     loc_1800190DB
0x1800185e5  mov     rax, [rdx]
0x1800185e8  test    rax, rax
0x1800185eb  jz      loc_1800190DB
0x1800185f1  test    r8d, r8d
0x1800185f4  js      loc_1800190DB
0x1800185fa  imul    r8d, [rdx+10h]
0x1800185ff  movsxd  rcx, r8d
0x180018602  add     rcx, rax
0x180018605  movzx   eax, word ptr [rcx+4]
0x180018609  cmp     [r10+4], ax
0x18001860e  jz      loc_180018F2F
0x180018614  mov     esi, 0
0x180018619  sub     edi, 1
0x18001861c  jnz     loc_1800184EA
0x180018622  xor     esi, esi
0x180018624  mov     r13d, [rsp+0A8h+var_74]
0x180018629  mov     qword ptr [rbx+8], 0
0x180018631  lea     eax, [r14+r13]
0x180018635  test    eax, eax
0x180018637  jz      short loc_18001869C
0x180018639  mov     r9, [rbx]
0x18001863c  test    r9, r9
0x18001863f  jz      short loc_18001869C
0x180018641  mov     ecx, [r9+8]
0x180018645  test    ecx, ecx
0x180018647  jz      short loc_18001869C
0x180018649  test    eax, eax
0x18001864b  js      loc_180018B84
0x180018651  test    ecx, ecx
0x180018653  jle     loc_1800190D3
0x180018659  mov     r8, [r9]
0x18001865c  test    r8, r8
0x18001865f  jz      loc_1800190D3
0x180018665  mov     edx, esi
0x180018667  test    eax, eax
0x180018669  jle     short loc_18001869C
0x18001866b  mov     ecx, [r8]
0x18001866e  mov     [rbx+0Ch], eax
0x180018671  cmp     eax, ecx
0x180018673  jl      short loc_18001869C
0x180018675  mov     r10d, edx
0x180018678  inc     edx
0x18001867a  mov     [rbx+8], edx
0x18001867d  cmp     edx, [r9+8]
0x180018681  jge     loc_18001899B
0x180018687  sub     eax, ecx
0x180018689  mov     [rbx+0Ch], esi
0x18001868c  movsxd  rcx, dword ptr [r9+10h]
0x180018690  add     r8, rcx
0x180018693  jmp     short loc_180018667
0x180018695  mov     r13d, [rsp+0A8h+var_74]
0x18001869a  xor     esi, esi
0x18001869c  mov     r12, [rsp+0A8h+arg_20]
0x1800186a4  mov     r15d, [rsp+0A8h+arg_8]
0x1800186ac  mov     rbp, [rsp+0A8h+arg_0]
0x1800186b4  mov     rdx, [rbp+40h]
0x1800186b8  lea     rdi, [rbp+40h]
0x1800186bc  test    rdx, rdx
0x1800186bf  jz      loc_180018894
0x1800186c5  mov     r8d, [rdx+8]
0x1800186c9  test    r8d, r8d
0x1800186cc  jz      loc_180018894
0x1800186d2  mov     ecx, [rdi+8]
0x1800186d5  jle     loc_1800190EB
0x1800186db  cmp     ecx, r8d
0x1800186de  jge     loc_1800190EB
0x1800186e4  mov     r9, [rdx]
0x1800186e7  test    r9, r9
0x1800186ea  jz      loc_1800190EB
0x1800186f0  test    ecx, ecx
0x1800186f2  js      loc_1800190EB
0x1800186f8  mov     eax, ecx
0x1800186fa  imul    eax, [rdx+10h]
0x1800186fe  movsxd  rdx, eax
0x180018701  add     rdx, r9
0x180018704  mov     eax, [rdi+0Ch]
0x180018707  cmp     [rdx], eax
0x180018709  jnz     short loc_18001871C
0x18001870b  lea     eax, [r8-1]
0x18001870f  cmp     ecx, eax
0x180018711  jge     short loc_18001871C
0x180018713  lea     eax, [rcx+1]
0x180018716  mov     [rdi+0Ch], esi
0x180018719  mov     [rdi+8], eax
0x18001871c  mov     eax, [rbp+48h]
0x18001871f  test    eax, eax
0x180018721  lea     esi, [rax-1]
0x180018724  cmovle  esi, eax
0x180018727  test    r15d, r15d
0x18001872a  jnz     loc_180018E5B
0x180018730  mov     r12, [rsp+0A8h+var_60]
0x180018735  mov     rcx, [rdi]
0x180018738  test    rcx, rcx
0x18001873b  jz      loc_180018894
0x180018741  mov     r8d, [rcx+8]
0x180018745  test    r8d, r8d
0x180018748  jz      loc_180018894
0x18001874e  mov     edx, [rdi+8]
0x180018751  jle     loc_180019125
0x180018757  cmp     edx, r8d
0x18001875a  jge     loc_180019125
0x180018760  mov     r10, [rcx]
0x180018763  test    r10, r10
0x180018766  jz      loc_180019125
0x18001876c  test    edx, edx
0x18001876e  js      loc_180019125
0x180018774  mov     eax, edx
0x180018776  imul    eax, [rcx+10h]
0x18001877a  movsxd  r9, eax
0x18001877d  add     r9, r10
0x180018780  xor     ebx, ebx
0x180018782  mov     eax, [rdi+0Ch]
0x180018785  cmp     [r9], eax
0x180018788  jnz     short loc_18001879B
0x18001878a  lea     eax, [r8-1]
0x18001878e  cmp     edx, eax
0x180018790  jge     short loc_18001879B
0x180018792  lea     eax, [rdx+1]
0x180018795  mov     [rdi+0Ch], ebx
0x180018798  mov     [rdi+8], eax
0x18001879b  mov     edx, [rcx+8]
0x18001879e  test    edx, edx
0x1800187a0  jle     loc_1800190FA
0x1800187a6  mov     eax, [rdi+8]
0x1800187a9  cmp     eax, edx
0x1800187ab  jge     loc_1800190FA
0x1800187b1  mov     rdx, [rcx]
0x1800187b4  test    rdx, rdx
0x1800187b7  jz      loc_1800190FA
0x1800187bd  test    eax, eax
0x1800187bf  js      loc_1800190FA
0x1800187c5  imul    eax, [rcx+10h]
0x1800187c9  movsxd  rcx, eax
0x1800187cc  add     rcx, rdx
0x1800187cf  add     [rcx], r14d
0x1800187d2  add     [rbp+4Ch], r14d
0x1800187d6  test    r15d, r15d
  ... truncated ...
```
