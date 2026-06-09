# CTxtPtr::FindEOP(long,long *)

- ea: `0x180024910`
- end: `0x18002542f`
- name: `?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z`
- size: `2847`
- prototype: `__int64 __fastcall(CTxtPtr *__hidden this, int, int *)`
- caller_count: `20`
- callee_count: `10`
- tags: ``

## callers

- `0x180002044`
- `0x180017860`
- `0x180018390`
- `0x180018c9c`
- `0x180018ea8`
- `0x18001d24c`
- `0x18001ebcc`
- `0x1800235f0`
- `0x180028064`
- `0x18003a000`
- `0x180043190`
- `0x1800442dc`
- `0x18004690c`
- `0x18006ea80`
- `0x180071980`
- `0x180072968`
- `0x180072e04`
- `0x1800731c8`
- `0x180073c50`
- `0x180074ce8`

## callees

- `0x1800064d0`
- `0x1800114d0`
- `0x1800165c0`
- `0x18001d7a8`
- `0x18001d8b0`
- `0x180023ce0`
- `0x180024910`
- `0x180026590`
- `0x180027f70`
- `0x180038020`

## pseudocode

```c
__int64 __fastcall CTxtPtr::FindEOP(CTxtPtr *this, int a2, unsigned __int64 a3)
{
  __int128 v3; // xmm0
  int v4; // eax
  unsigned int v5; // r14d
  int v6; // r11d
  CTxtPtr *v7; // rsi
  int v8; // ebx
  __int128 v9; // xmm1
  int v10; // edi
  int v11; // r15d
  int v12; // r13d
  CArrayBase *v13; // r12
  int v14; // eax
  void *v15; // rdx
  int v16; // r9d
  int v17; // r10d
  __int64 v18; // r8
  int v19; // ecx
  unsigned __int16 *v20; // rdx
  unsigned int v21; // r10d
  int i; // eax
  unsigned __int16 v23; // ax
  int v24; // r10d
  int v25; // r10d
  int v26; // ecx
  int v27; // r9d
  int *v28; // rcx
  int v29; // eax
  __int64 v30; // rax
  CArrayBase *v31; // r8
  int v32; // r9d
  int v33; // ecx
  int v34; // edi
  int v35; // r10d
  int v36; // r9d
  int *v37; // rdx
  int v38; // eax
  int v39; // edi
  CArrayBase *v40; // r11
  int v41; // ebx
  int *v42; // rdi
  int v43; // eax
  int *v44; // r10
  _DWORD *v45; // rdx
  int v46; // r8d
  _DWORD *v47; // r9
  int v48; // ebx
  unsigned __int16 *v49; // rcx
  int v50; // ebx
  int *v51; // r8
  int *v52; // r15
  int *v53; // r13
  int *v54; // r12
  _DWORD *v55; // rbx
  int v56; // edi
  _DWORD *v57; // r14
  int v58; // esi
  int v59; // ecx
  int v60; // ecx
  int v61; // r8d
  int *v62; // rdx
  int v63; // eax
  int v64; // r9d
  unsigned __int16 v65; // r14
  int *v66; // r12
  CArrayBase *v67; // r9
  int v68; // r10d
  int v69; // eax
  void *v70; // rdx
  int v71; // r8d
  unsigned __int16 *v72; // rdi
  int v73; // ecx
  int v74; // ecx
  unsigned __int16 Char; // di
  int v76; // ebx
  CArrayBase *v77; // rcx
  int v78; // r9d
  _DWORD *v79; // r10
  int v80; // r8d
  _DWORD *v81; // r8
  int v82; // r11d
  int v83; // eax
  int v84; // edx
  _DWORD *v85; // rax
  int *v87; // rcx
  int v88; // eax
  int v89; // ecx
  int v90; // eax
  int v91; // eax
  int v92; // ecx
  _DWORD *v93; // rax
  int v94; // eax
  int v95; // eax
  int v96; // edx
  int v97; // eax
  int v98; // eax
  const unsigned __int16 *PchReverse; // rax
  int v100; // ebx
  unsigned int v101; // [rsp+20h] [rbp-49h]
  int *v102; // [rsp+28h] [rbp-41h]
  int *v103; // [rsp+30h] [rbp-39h]
  CArrayBase *v104[2]; // [rsp+38h] [rbp-31h] BYREF
  int v105[4]; // [rsp+48h] [rbp-21h]
  _DWORD *v106; // [rsp+58h] [rbp-11h]
  _DWORD *v107; // [rsp+60h] [rbp-9h]
  int v108; // [rsp+68h] [rbp-1h]
  int *v109; // [rsp+70h] [rbp+7h]
  int v111; // [rsp+D8h] [rbp+6Fh]
  int v112; // [rsp+D8h] [rbp+6Fh]
  _DWORD *v113; // [rsp+E0h] [rbp+77h]
  int v114; // [rsp+E8h] [rbp+7Fh] BYREF

  v113 = (_DWORD *)a3;
  v111 = a2;
  v3 = *(_OWORD *)this;
  v4 = *((_DWORD *)this + 4);
  v5 = 0;
  v114 = 0;
  v6 = a2;
  v108 = v4;
  v7 = this;
  v8 = 1;
  v9 = *((_OWORD *)this + 1);
  *(_OWORD *)v104 = v3;
  *(_OWORD *)v105 = v9;
  if ( a2 < 0 )
  {
    v8 = -1;
    v98 = CTxtPtr::AdjustCpCRLF((CTxtPtr *)v104);
    v114 = v98;
    if ( !v98 )
    {
      if ( (unsigned int)CTxtPtr::IsAfterEOP(v7) )
      {
        v98 = CTxtPtr::BackupCpCRLF((CTxtPtr *)v104, 1);
        v114 = v98;
      }
      else
      {
        v98 = 0;
      }
    }
    v6 = v98 - v111;
    v111 = v98 - v111;
  }
  v10 = v105[0];
  v11 = HIDWORD(v104[1]);
  v12 = (int)v104[1];
  v13 = v104[0];
  do
  {
    if ( v6 <= 0 )
      break;
    if ( v8 <= 0 )
    {
      PchReverse = CTxtPtr::GetPchReverse((CTxtPtr *)v104, &v114, (int *)a3);
      v16 = v114;
      v18 = (__int64)PchReverse;
      v6 = v111;
      goto LABEL_20;
    }
    if ( !v13 || !*((_DWORD *)v13 + 2) )
    {
      v16 = 0;
LABEL_19:
      v18 = 0;
      goto LABEL_20;
    }
    v14 = *((_DWORD *)v13 + 2);
    if ( v14 > 0 && v12 < v14 && *(_QWORD *)v13 && v12 >= 0 )
      v15 = (void *)(*(_QWORD *)v13 + *((_DWORD *)v13 + 4) * v12);
    else
      v15 = 0;
    v16 = 0;
    if ( !v15 )
      goto LABEL_19;
    v17 = v11;
    if ( v11 != *(_DWORD *)v15 )
      goto LABEL_14;
    if ( v12 >= *((_DWORD *)v13 + 2) - 1 )
      goto LABEL_19;
    v15 = CArrayBase::Elem(v13, v12 + 1);
    if ( v15 )
    {
      v17 = 0;
LABEL_14:
      v18 = *((_QWORD *)v15 + 1) + 2LL * v17;
      v19 = *((_DWORD *)v15 + 4);
      if ( 2 * v17 >= v19 )
      {
        v16 = *(_DWORD *)v15 - v17;
        v18 += 2LL * (*((_DWORD *)v15 + 5) / 2 - *(_DWORD *)v15);
        if ( !v16 )
          v18 = 0;
      }
      else
      {
        v16 = v19 / 2 - v17;
        if ( v19 / 2 == v17 )
          v18 = 0;
      }
      goto LABEL_20;
    }
    v18 = 0;
LABEL_20:
    if ( !v18 )
      break;
    v20 = (unsigned __int16 *)(v18 - 2);
    v21 = v6;
    if ( v8 >= 0 )
      v20 = (unsigned __int16 *)v18;
    if ( v16 < v6 )
      v21 = v16;
    a3 = v21;
    v114 = v21;
    for ( i = v21; i; i = a3 )
    {
      if ( !v20 )
      {
        v23 = 9;
LABEL_29:
        v5 |= 0x100u;
        goto LABEL_30;
      }
      v23 = *v20;
      if ( *v20 == 9 )
        goto LABEL_29;
LABEL_30:
      if ( (unsigned int)v23 - 10 <= 3 || (v23 | 1) == 0x2029 )
      {
        v5 |= 0x200u;
        break;
      }
      a3 = (unsigned int)(a3 - 1);
      v114 = a3;
      v20 += v8;
    }
    v24 = v21 - a3;
    v6 -= v24;
    v111 = v6;
    if ( v13 )
    {
      a3 = *((unsigned int *)v13 + 2);
      if ( (_DWORD)a3 )
      {
        v25 = v8 * v24;
        v26 = v25 + v10;
        if ( v25 + v10 < v10 / 2 )
        {
          v104[1] = 0;
          if ( v26 <= 0 )
            v26 = 0;
          v95 = CRunPtrBase::AdvanceCp((CRunPtrBase *)v104, v26);
          v6 = v111;
          v10 = v95;
          v11 = HIDWORD(v104[1]);
          v12 = (int)v104[1];
          v13 = v104[0];
          v105[0] = v95;
        }
        else
        {
          v27 = v25;
          if ( v25 )
          {
            if ( v25 < 0 )
            {
              while ( v25 < 0 )
              {
                if ( -v25 <= v11 )
                {
                  v11 += v25;
                  HIDWORD(v104[1]) = v11;
LABEL_49:
                  v25 = 0;
                  break;
                }
                v25 += v11;
                if ( v12 <= 0 )
                {
                  v12 = 0;
                  v104[1] = 0;
                  v11 = 0;
                  break;
                }
                LODWORD(v104[1]) = --v12;
                if ( (int)a3 > 0 && v12 < (int)a3 && *(_QWORD *)v13 && v12 >= 0 )
                  v87 = (int *)(*(_QWORD *)v13 + *((_DWORD *)v13 + 4) * v12);
                else
                  v87 = 0;
                v11 = *v87;
                HIDWORD(v104[1]) = *v87;
              }
            }
            else
            {
              if ( (int)a3 > 0 && v12 < (int)a3 && *(_QWORD *)v13 && v12 >= 0 )
                v28 = (int *)(*(_QWORD *)v13 + *((_DWORD *)v13 + 4) * v12);
              else
                v28 = 0;
              while ( v25 > 0 )
              {
                v29 = *v28;
                v11 += v25;
                HIDWORD(v104[1]) = v11;
                if ( v11 < v29 )
                  goto LABEL_49;
                ++v12;
                v25 = v11 - v29;
                LODWORD(v104[1]) = v12;
                if ( v12 >= (int)a3 )
                {
                  v104[1] = (CArrayBase *)__PAIR64__(v29, --v12);
                  v11 = v29;
                  break;
                }
                v30 = *((int *)v13 + 4);
                v11 = 0;
                HIDWORD(v104[1]) = 0;
                v28 = (int *)((char *)v28 + v30);
              }
            }
            v27 -= v25;
          }
          v10 += v27;
          v105[0] = v10;
        }
      }
    }
  }
  while ( (v5 & 0x200) == 0 );
  v101 = v5;
  if ( (v5 & 0x200) == 0 && v10 && v10 != (unsigned int)CTxtPtr::GetTextLength(v7) )
    goto LABEL_136;
  v31 = *(CArrayBase **)v7;
  v32 = *((_DWORD *)v7 + 4);
  v112 = v32;
  if ( *(_QWORD *)v7 )
  {
    v33 = *((_DWORD *)v31 + 2);
    if ( v33 )
    {
      if ( v10 < v32 / 2 )
      {
        v96 = 0;
        *((_QWORD *)v7 + 1) = 0;
        if ( v10 > 0 )
          v96 = v10;
        v112 = CRunPtrBase::AdvanceCp(v7, v96);
        *((_DWORD *)v7 + 4) = v112;
      }
      else
      {
        v34 = v10 - v32;
        v35 = v34;
        if ( v34 )
        {
          if ( v34 < 0 )
          {
            while ( v34 < 0 )
            {
              v88 = *((_DWORD *)v7 + 3);
              v89 = v88 + v34;
              if ( -v34 <= v88 )
              {
                *((_DWORD *)v7 + 3) = v89;
                v34 = 0;
                break;
              }
              v90 = *((_DWORD *)v7 + 2);
              v34 = v89;
              if ( v90 <= 0 )
              {
                *((_QWORD *)v7 + 1) = 0;
                break;
              }
              v91 = v90 - 1;
              *((_DWORD *)v7 + 2) = v91;
              v92 = *((_DWORD *)v31 + 2);
              if ( v92 > 0 && v91 < v92 && *(_QWORD *)v31 && v91 >= 0 )
                v93 = (_DWORD *)(*(_QWORD *)v31 + *((_DWORD *)v31 + 4) * v91);
              else
                v93 = 0;
              *((_DWORD *)v7 + 3) = *v93;
            }
          }
          else
          {
            v36 = *((_DWORD *)v7 + 2);
            if ( v33 > 0 && v36 < v33 && *(_QWORD *)v31 && v36 >= 0 )
              v37 = (int *)(*(_QWORD *)v31 + *((_DWORD *)v31 + 4) * v36);
            else
              v37 = 0;
            while ( v34 > 0 )
            {
              v38 = *v37;
              *((_DWORD *)v7 + 3) += v34;
              v39 = *((_DWORD *)v7 + 3);
              if ( v39 < v38 )
              {
                v34 = 0;
                break;
              }
              v34 = v39 - v38;
              *((_DWORD *)v7 + 2) = v36 + 1;
              if ( v36 + 1 >= *((_DWORD *)v31 + 2) )
              {
                *((_DWORD *)v7 + 2) = v36;
                *((_DWORD *)v7 + 3) = v38;
                break;
              }
              *((_DWORD *)v7 + 3) = 0;
              ++v36;
              v37 = (int *)((char *)v37 + *((int *)v31 + 4));
            }
            v32 = v112;
          }
          v35 -= v34;
        }
        v112 = v35 + v32;
        *((_DWORD *)v7 + 4) = v35 + v32;
      }
    }
  }
  if ( v8 <= 0 )
    goto LABEL_136;
  v40 = *(CArrayBase **)v7;
  if ( !*(_QWORD *)v7 || (v41 = *((_DWORD *)v40 + 2), v42 = (int *)((char *)v40 + 8), !v41) )
  {
    v42 = (int *)((char *)v40 + 8);
LABEL_142:
    v44 = (int *)((char *)v7 + 8);
    v47 = (_DWORD *)((char *)v7 + 12);
    goto LABEL_143;
  }
  if ( v41 > 0 && (v43 = *((_DWORD *)v7 + 2), v44 = (int *)((char *)v7 + 8), v43 < v41) && *(_QWORD *)v40 && v43 >= 0 )
  {
    v45 = (_DWORD *)(*(_QWORD *)v40 + *((_DWORD *)v40 + 4) * v43);
  }
  else
  {
    v45 = 0;
    v44 = (int *)((char *)v7 + 8);
  }
  if ( !v45 )
    goto LABEL_142;
  v46 = *((_DWORD *)v7 + 3);
  v47 = (_DWORD *)((char *)v7 + 12);
  if ( v46 != *v45 )
    goto LABEL_82;
  if ( *v44 >= v41 - 1 )
    goto LABEL_143;
  v45 = CArrayBase::Elem(*(CArrayBase **)v7, *v44 + 1);
  if ( !v45 )
    goto LABEL_143;
  v46 = 0;
LABEL_82:
  v48 = v45[4];
  v49 = (unsigned __int16 *)(*((_QWORD *)v45 + 1) + 2LL * v46);
  if ( 2 * v46 >= v48 )
  {
    v50 = *v45;
    v49 += v45[5] / 2 - *v45;
  }
  else
  {
    v50 = v48 / 2;
  }
  if ( v50 == v46 || !v49 )
  {
LABEL_143:
    v65 = 0;
    v107 = v47;
    v102 = v44;
    v66 = v44;
    v106 = v47;
    v53 = v44;
    v103 = v44;
    v51 = v47;
    v109 = v47;
    v52 = v44;
    v114 = 0;
    if ( v40 )
      goto LABEL_87;
    goto LABEL_100;
  }
  v51 = v47;
  v114 = *v49;
  v52 = v44;
  v107 = v47;
  v53 = v44;
  v102 = v44;
  v106 = v47;
  v103 = v44;
  v109 = v47;
LABEL_87:
  v54 = v42;
  v55 = v47;
  v56 = *v42;
  v57 = v47;
  if ( v56 )
  {
    v58 = *((_DWORD *)v7 + 4);
    v59 = v58 + 1;
    if ( v58 + 1 < v58 / 2 )
    {
      v7 = this;
      *v44 = 0;
      *v47 = 0;
      if ( v59 <= 0 )
        v59 = 0;
      v97 = CRunPtrBase::AdvanceCp(this, v59);
      v65 = v114;
      v66 = v102;
      v53 = v103;
      *((_DWORD *)this + 4) = v97;
    }
    else
    {
      v60 = 1;
      v109 = v51;
      v61 = *v44;
      if ( v56 > 0 && v61 < v56 && *(_QWORD *)v40 && v61 >= 0 )
        v62 = (int *)(*(_QWORD *)v40 + *((_DWORD *)v40 + 4) * v61);
      else
        v62 = 0;
      while ( v60 > 0 )
      {
        v63 = *v62;
        *v55 += v60;
        if ( *v55 < v63 )
        {
          v60 = 0;
          break;
        }
        v60 = *v55 - v63;
        v64 = v61++;
        *v53 = v61;
        if ( v61 >= *v54 )
        {
          *v52 = v64;
          *v57 = v63;
          break;
        }
        *v57 = 0;
        v62 = (int *)((char *)v62 + *((int *)v40 + 4));
      }
      v65 = v114;
      v66 = v102;
      v53 = v103;
      *((_DWORD *)this + 4) = v58 - v60 + 1;
      v7 = this;
    }
  }
  else
  {
    v65 = v114;
    v66 = v102;
    v53 = v103;
  }
LABEL_100:
  v67 = *(CArrayBase **)v7;
  if ( !*(_QWORD *)v7 )
    goto LABEL_140;
  v68 = *((_DWORD *)v67 + 2);
  if ( !v68 )
    goto LABEL_140;
  if ( v68 > 0 && (v69 = *v52, *v52 < v68) && *(_QWORD *)v67 && v69 >= 0 )
    v70 = (void *)(*(_QWORD *)v67 + *((_DWORD *)v67 + 4) * v69);
  else
    v70 = 0;
  if ( !v70 )
    goto LABEL_140;
  v71 = *v109;
  if ( *v109 != *(_DWORD *)v70 )
    goto LABEL_109;
  if ( *v53 >= v68 - 1 )
    goto LABEL_140;
  v70 = CArrayBase::Elem(*(CArrayBase **)v7, *v53 + 1);
  if ( !v70 )
    goto LABEL_140;
  v71 = 0;
LABEL_109:
  v72 = (unsigned __int16 *)(*((_QWORD *)v70 + 1) + 2LL * v71);
  v73 = *((_DWORD *)v70 + 4);
  if ( 2 * v71 >= v73 )
  {
    v74 = *(_DWORD *)v70;
    v72 += *((_DWORD *)v70 + 5) / 2 - *(_DWORD *)v70;
  }
  else
  {
    v74 = v73 / 2;
  }
  if ( v74 != v71 && v72 )
    Char = *v72;
  else
LABEL_140:
    Char = 0;
  if ( v65 == 13 )
  {
    v76 = 0;
    if ( Char == 13 )
    {
      if ( *((_QWORD *)v7 + 3) )
        v94 = *((_DWORD *)v67 + 6);
      else
        v94 = 0;
      if ( *((_DWORD *)v7 + 4) < v94 )
      {
        v76 = 1;
        Char = CTxtPtr::NextChar(v7);
        goto LABEL_116;
      }
    }
    else
    {
LABEL_116:
      if ( Char == 10 )
      {
        CTxtPtr::AdvanceCp(v7, 1);
      }
      else if ( v76 )
      {
        v77 = *(CArrayBase **)v7;
        if ( *(_QWORD *)v7 )
        {
          if ( *((_DWORD *)v77 + 2) )
          {
            v78 = *((_DWORD *)v7 + 4);
            v79 = v106;
            v80 = v78 - 1;
            if ( v78 - 1 < v78 / 2 )
            {
              *v53 = 0;
              *v79 = 0;
              if ( v80 <= 0 )
                v80 = 0;
              *((_DWORD *)v7 + 4) = CRunPtrBase::AdvanceCp(v7, v80);
            }
            else
            {
              v81 = v107;
              v82 = -1;
              while ( v82 < 0 )
              {
                if ( -v82 <= *v79 )
                {
                  *v81 = *v79 + v82;
                  v82 = 0;
                  break;
                }
                v82 += *v79;
                if ( *v66 <= 0 )
                {
                  *v66 = 0;
                  *v81 = 0;
                  break;
                }
                v83 = *v66 - 1;
                *v66 = v83;
                v84 = *((_DWORD *)v77 + 2);
                if ( v84 > 0 && v83 < v84 && *(_QWORD *)v77 && v83 >= 0 )
                  v85 = (_DWORD *)(*(_QWORD *)v77 + *((_DWORD *)v77 + 4) * v83);
                else
                  v85 = 0;
                *v81 = *v85;
              }
              *((_DWORD *)v7 + 4) = v78 + ~v82;
            }
          }
        }
      }
    }
  }
  if ( (unsigned int)v65 - 55296 <= 0x3FF && (unsigned int)Char - 56320 <= 0x3FF )
    CTxtPtr::AdvanceCp(v7, 1);
  do
  {
    if ( (unsigned int)Char - 768 > 0x6F )
      break;
    v100 = *((_DWORD *)v7 + 4);
    Char = CTxtPtr::NextChar(v7);
  }
  while ( *((_DWORD *)v7 + 4) != v100 );
  v5 = v101 & 0xFFFFFF00 | (*((_DWORD *)v7 + 4) - v112);
LABEL_136:
  if ( v113 )
    *v113 = v5;
  return (unsigned int)(*((_DWORD *)v7 + 4) - v108);
}

```

## disassembly

```asm
0x180024910  mov     [rsp-8+arg_10], r8
0x180024915  mov     [rsp-8+arg_8], edx
0x180024919  mov     [rsp-8+arg_0], rcx
0x18002491e  push    rbp
0x18002491f  push    rbx
0x180024920  push    rsi
0x180024921  push    rdi
0x180024922  push    r12
0x180024924  push    r13
0x180024926  push    r14
0x180024928  push    r15
0x18002492a  lea     rbp, [rsp-1Fh]
0x18002492f  sub     rsp, 88h
0x180024936  movups  xmm0, xmmword ptr [rcx]
0x180024939  mov     eax, [rcx+10h]
0x18002493c  xor     r14d, r14d
0x18002493f  mov     [rbp+57h+arg_18], 0
0x180024946  mov     r11d, edx
0x180024949  mov     [rbp+57h+var_58], eax
0x18002494c  mov     rsi, rcx
0x18002494f  mov     ebx, 1
0x180024954  movups  xmm1, xmmword ptr [rcx+10h]
0x180024958  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18002495c  movups  xmmword ptr [rbp+57h+var_78], xmm1
0x180024960  test    edx, edx
0x180024962  js      loc_1800252EF
0x180024968  mov     edi, [rbp+57h+var_78]
0x18002496b  mov     r15d, dword ptr [rbp+57h+var_88+0Ch]
0x18002496f  mov     r13d, dword ptr [rbp+57h+var_88+8]
0x180024973  mov     r12, [rbp+57h+var_88]
0x180024977  test    r11d, r11d
0x18002497a  jle     loc_180024B78
0x180024980  test    ebx, ebx
0x180024982  jle     loc_18002533B
0x180024988  test    r12, r12
0x18002498b  jz      loc_180024A1E
0x180024991  cmp     dword ptr [r12+8], 0
0x180024997  jz      loc_180024A1E
0x18002499d  mov     eax, [r12+8]
0x1800249a2  test    eax, eax
0x1800249a4  jle     loc_1800252AC
0x1800249aa  cmp     r13d, eax
0x1800249ad  jge     loc_1800252AC
0x1800249b3  mov     rcx, [r12]
0x1800249b7  test    rcx, rcx
0x1800249ba  jz      loc_1800252AC
0x1800249c0  test    r13d, r13d
0x1800249c3  js      loc_1800252AC
0x1800249c9  mov     eax, r13d
0x1800249cc  imul    eax, [r12+10h]
0x1800249d2  movsxd  rdx, eax
0x1800249d5  add     rdx, rcx
0x1800249d8  xor     r9d, r9d
0x1800249db  test    rdx, rdx
0x1800249de  jz      short loc_180024A21
0x1800249e0  mov     r10d, r15d
0x1800249e3  cmp     r15d, [rdx]
0x1800249e6  jz      loc_180025196
0x1800249ec  mov     rax, [rdx+8]
0x1800249f0  movsxd  rcx, r10d
0x1800249f3  lea     r8, [rax+rcx*2]
0x1800249f7  mov     ecx, [rdx+10h]
0x1800249fa  lea     eax, [r10+r10]
0x1800249fe  cmp     eax, ecx
0x180024a00  jge     loc_180025044
0x180024a06  mov     eax, ecx
0x180024a08  xor     ecx, ecx
0x180024a0a  cdq
0x180024a0b  sub     eax, edx
0x180024a0d  sar     eax, 1
0x180024a0f  mov     r9d, eax
0x180024a12  sub     r9d, r10d
0x180024a15  test    r9d, r9d
0x180024a18  cmovz   r8, rcx
0x180024a1c  jmp     short loc_180024A24
0x180024a1e  xor     r9d, r9d
0x180024a21  xor     r8d, r8d
0x180024a24  test    r8, r8
0x180024a27  jz      loc_180024B78
0x180024a2d  test    ebx, ebx
0x180024a2f  lea     rdx, [r8-2]
0x180024a33  mov     r10d, r11d
0x180024a36  cmovns  rdx, r8
0x180024a3a  cmp     r9d, r11d
0x180024a3d  cmovl   r10d, r9d
0x180024a41  mov     r8d, r10d
0x180024a44  mov     [rbp+57h+arg_18], r10d
0x180024a48  mov     eax, r10d
0x180024a4b  nop     dword ptr [rax+rax+00h]
0x180024a50  test    eax, eax
0x180024a52  jz      short loc_180024A9C
0x180024a54  test    rdx, rdx
0x180024a57  jz      loc_180025358
0x180024a5d  movzx   eax, word ptr [rdx]
0x180024a60  cmp     ax, 9
0x180024a64  jnz     short loc_180024A6B
0x180024a66  bts     r14d, 8
0x180024a6b  movzx   ecx, ax
0x180024a6e  sub     ecx, 0Ah
0x180024a71  cmp     ecx, 3
0x180024a74  jbe     short loc_180024A97
0x180024a76  or      ax, 1
0x180024a7a  mov     ecx, 2029h
0x180024a7f  cmp     ax, cx
0x180024a82  jz      short loc_180024A97
0x180024a84  movsxd  rax, ebx
0x180024a87  dec     r8d
0x180024a8a  mov     [rbp+57h+arg_18], r8d
0x180024a8e  lea     rdx, [rdx+rax*2]
0x180024a92  mov     eax, r8d
0x180024a95  jmp     short loc_180024A50
0x180024a97  bts     r14d, 9
0x180024a9c  sub     r10d, r8d
0x180024a9f  sub     r11d, r10d
0x180024aa2  mov     [rbp+57h+arg_8], r11d
0x180024aa6  test    r12, r12
0x180024aa9  jz      loc_180024B6D
0x180024aaf  mov     r8d, [r12+8]
0x180024ab4  test    r8d, r8d
0x180024ab7  jz      loc_180024B6D
0x180024abd  imul    r10d, ebx
0x180024ac1  mov     eax, edi
0x180024ac3  cdq
0x180024ac4  sub     eax, edx
0x180024ac6  sar     eax, 1
0x180024ac8  lea     ecx, [r10+rdi]
0x180024acc  cmp     ecx, eax
0x180024ace  jl      loc_1800251F2
0x180024ad4  mov     r9d, r10d
0x180024ad7  test    r10d, r10d
0x180024ada  jz      loc_180024B67
0x180024ae0  js      loc_180025097
0x180024ae6  test    r8d, r8d
0x180024ae9  jle     loc_1800252CD
0x180024aef  cmp     r13d, r8d
0x180024af2  jge     loc_1800252CD
0x180024af8  mov     rdx, [r12]
0x180024afc  test    rdx, rdx
0x180024aff  jz      loc_1800252CD
0x180024b05  test    r13d, r13d
0x180024b08  js      loc_1800252CD
0x180024b0e  mov     eax, r13d
0x180024b11  imul    eax, [r12+10h]
0x180024b17  movsxd  rcx, eax
0x180024b1a  add     rcx, rdx
0x180024b1d  nop     dword ptr [rax]
0x180024b20  test    r10d, r10d
0x180024b23  jle     short loc_180024B64
0x180024b25  mov     eax, [rcx]
0x180024b27  add     r15d, r10d
0x180024b2a  mov     dword ptr [rbp+57h+var_88+0Ch], r15d
0x180024b2e  mov     r10d, r15d
0x180024b31  cmp     r15d, eax
0x180024b34  jl      short loc_180024B61
0x180024b36  inc     r13d
0x180024b39  sub     r10d, eax
0x180024b3c  mov     dword ptr [rbp+57h+var_88+8], r13d
0x180024b40  cmp     r13d, r8d
0x180024b43  jge     loc_18002501B
0x180024b49  movsxd  rax, dword ptr [r12+10h]
0x180024b4e  xor     r15d, r15d
0x180024b51  mov     dword ptr [rbp+57h+var_88+0Ch], r15d
0x180024b55  add     rcx, rax
0x180024b58  jmp     short loc_180024B20
0x180024b5a  add     r15d, r10d
0x180024b5d  mov     dword ptr [rbp+57h+var_88+0Ch], r15d
0x180024b61  xor     r10d, r10d
0x180024b64  sub     r9d, r10d
0x180024b67  add     edi, r9d
0x180024b6a  mov     [rbp+57h+var_78], edi
0x180024b6d  bt      r14d, 9
0x180024b72  jnb     loc_180024977
0x180024b78  mov     [rbp+57h+var_A0], r14d
0x180024b7c  bt      r14d, 9
0x180024b81  jnb     loc_180025371
0x180024b87  mov     r8, [rsi]
0x180024b8a  mov     r9d, [rsi+10h]
0x180024b8e  mov     [rbp+57h+arg_8], r9d
0x180024b92  test    r8, r8
0x180024b95  jz      loc_180024C4E
0x180024b9b  mov     ecx, [r8+8]
0x180024b9f  test    ecx, ecx
0x180024ba1  jz      loc_180024C4E
0x180024ba7  mov     eax, r9d
0x180024baa  cdq
0x180024bab  sub     eax, edx
0x180024bad  sar     eax, 1
0x180024baf  cmp     edi, eax
0x180024bb1  jl      loc_180025222
0x180024bb7  sub     edi, r9d
0x180024bba  mov     r10d, edi
0x180024bbd  jz      loc_180024C43
0x180024bc3  test    edi, edi
0x180024bc5  js      loc_180025101
0x180024bcb  mov     r9d, [rsi+8]
0x180024bcf  test    ecx, ecx
0x180024bd1  jle     loc_1800252D4
0x180024bd7  cmp     r9d, ecx
0x180024bda  jge     loc_1800252D4
0x180024be0  mov     rcx, [r8]
0x180024be3  test    rcx, rcx
0x180024be6  jz      loc_1800252D4
0x180024bec  test    r9d, r9d
0x180024bef  js      loc_1800252D4
0x180024bf5  mov     eax, r9d
0x180024bf8  imul    eax, [r8+10h]
0x180024bfd  movsxd  rdx, eax
0x180024c00  add     rdx, rcx
0x180024c03  xor     r11d, r11d
0x180024c06  test    edi, edi
0x180024c08  jle     short loc_180024C3C
0x180024c0a  mov     eax, [rdx]
0x180024c0c  add     [rsi+0Ch], edi
0x180024c0f  mov     edi, [rsi+0Ch]
0x180024c12  cmp     edi, eax
0x180024c14  jl      short loc_180024C39
0x180024c16  lea     ecx, [r9+1]
0x180024c1a  sub     edi, eax
0x180024c1c  mov     [rsi+8], ecx
0x180024c1f  cmp     ecx, [r8+8]
0x180024c23  jge     loc_18002502D
0x180024c29  mov     [rsi+0Ch], r11d
0x180024c2d  mov     r9d, ecx
0x180024c30  movsxd  rax, dword ptr [r8+10h]
0x180024c34  add     rdx, rax
0x180024c37  jmp     short loc_180024C06
0x180024c39  mov     edi, r11d
0x180024c3c  mov     r9d, [rbp+57h+arg_8]
0x180024c40  sub     r10d, edi
0x180024c43  add     r9d, r10d
0x180024c46  mov     [rbp+57h+arg_8], r9d
0x180024c4a  mov     [rsi+10h], r9d
0x180024c4e  test    ebx, ebx
0x180024c50  jle     loc_180024F9B
0x180024c56  mov     r11, [rsi]
0x180024c59  test    r11, r11
0x180024c5c  jz      loc_180024FD8
0x180024c62  mov     ebx, [r11+8]
0x180024c66  lea     rdi, [r11+8]
0x180024c6a  test    ebx, ebx
0x180024c6c  jz      loc_180024FD8
0x180024c72  jle     loc_1800252BA
0x180024c78  mov     eax, [rsi+8]
0x180024c7b  lea     r10, [rsi+8]
0x180024c7f  cmp     eax, ebx
0x180024c81  jge     loc_1800252BA
0x180024c87  mov     rcx, [r11]
0x180024c8a  test    rcx, rcx
0x180024c8d  jz      loc_1800252BA
0x180024c93  test    eax, eax
0x180024c95  js      loc_1800252BA
0x180024c9b  imul    eax, [r11+10h]
0x180024ca0  movsxd  rdx, eax
0x180024ca3  add     rdx, rcx
0x180024ca6  test    rdx, rdx
0x180024ca9  jz      loc_180024FDC
0x180024caf  mov     r8d, [rsi+0Ch]
0x180024cb3  lea     r9, [rsi+0Ch]
0x180024cb7  cmp     r8d, [rdx]
0x180024cba  jz      loc_1800251C6
0x180024cc0  mov     rax, [rdx+8]
0x180024cc4  mov     ebx, [rdx+10h]
0x180024cc7  movsxd  rcx, r8d
0x180024cca  lea     rcx, [rax+rcx*2]
0x180024cce  lea     eax, [r8+r8]
0x180024cd2  cmp     eax, ebx
0x180024cd4  jge     loc_180025069
0x180024cda  mov     eax, ebx
0x180024cdc  cdq
0x180024cdd  sub     eax, edx
0x180024cdf  sar     eax, 1
0x180024ce1  mov     ebx, eax
0x180024ce3  sub     ebx, r8d
0x180024ce6  test    ebx, ebx
0x180024ce8  jz      loc_180024FE4
0x180024cee  test    rcx, rcx
0x180024cf1  jz      loc_180024FE4
0x180024cf7  movzx   eax, word ptr [rcx]
0x180024cfa  mov     r8, r9
0x180024cfd  mov     [rbp+57h+arg_18], eax
0x180024d00  mov     r15, r10
0x180024d03  mov     [rbp+57h+var_60], r9
0x180024d07  mov     r13, r10
0x180024d0a  mov     [rbp+57h+var_98], r10
0x180024d0e  mov     [rbp+57h+var_68], r9
0x180024d12  mov     [rbp+57h+var_90], r10
0x180024d16  mov     [rbp+57h+var_50], r9
0x180024d1a  mov     r12, rdi
0x180024d1d  mov     rbx, r9
0x180024d20  mov     edi, [rdi]
0x180024d22  mov     r14, r9
0x180024d25  test    edi, edi
0x180024d27  jz      loc_180025399
0x180024d2d  mov     esi, [rsi+10h]
0x180024d30  mov     eax, esi
0x180024d32  cdq
0x180024d33  sub     eax, edx
0x180024d35  sar     eax, 1
0x180024d37  lea     ecx, [rsi+1]
0x180024d3a  cmp     ecx, eax
  ... truncated ...
```
