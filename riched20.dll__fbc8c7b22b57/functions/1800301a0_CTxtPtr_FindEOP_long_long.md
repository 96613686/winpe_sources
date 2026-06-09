# CTxtPtr::FindEOP(long,long *)

- ea: `0x1800301a0`
- end: `0x180030cce`
- name: `?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z`
- size: `2862`
- prototype: `__int64 __fastcall(CTxtPtr *__hidden this, int, int *)`
- caller_count: `20`
- callee_count: `10`
- tags: ``

## callers

- `0x1800020c4`
- `0x180016700`
- `0x180017230`
- `0x180017ad0`
- `0x180017cdc`
- `0x18001c5e4`
- `0x18001eb2c`
- `0x1800238dc`
- `0x18002ee70`
- `0x18003b170`
- `0x180044230`
- `0x1800453dc`
- `0x180047998`
- `0x1800708e0`
- `0x180073890`
- `0x180074898`
- `0x180074d50`
- `0x180075114`
- `0x180075bc0`
- `0x180076cd8`

## callees

- `0x180006570`
- `0x180010260`
- `0x180015448`
- `0x18001e3e0`
- `0x18001f120`
- `0x18001f230`
- `0x18002f560`
- `0x1800301a0`
- `0x180031e30`
- `0x180038dc0`

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
0x1800301a0  mov     [rsp-8+arg_10], r8
0x1800301a5  mov     [rsp-8+arg_8], edx
0x1800301a9  mov     [rsp-8+arg_0], rcx
0x1800301ae  push    rbp
0x1800301af  push    rbx
0x1800301b0  push    rsi
0x1800301b1  push    rdi
0x1800301b2  push    r12
0x1800301b4  push    r13
0x1800301b6  push    r14
0x1800301b8  push    r15
0x1800301ba  lea     rbp, [rsp-1Fh]
0x1800301bf  sub     rsp, 88h
0x1800301c6  movups  xmm0, xmmword ptr [rcx]
0x1800301c9  mov     eax, [rcx+10h]
0x1800301cc  xor     r14d, r14d
0x1800301cf  mov     [rbp+57h+arg_18], 0
0x1800301d6  mov     r11d, edx
0x1800301d9  mov     [rbp+57h+var_58], eax
0x1800301dc  mov     rsi, rcx
0x1800301df  mov     ebx, 1
0x1800301e4  movups  xmm1, xmmword ptr [rcx+10h]
0x1800301e8  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1800301ec  movups  xmmword ptr [rbp+57h+var_78], xmm1
0x1800301f0  test    edx, edx
0x1800301f2  js      loc_180030B8E
0x1800301f8  mov     edi, [rbp+57h+var_78]
0x1800301fb  mov     r15d, dword ptr [rbp+57h+var_88+0Ch]
0x1800301ff  mov     r13d, dword ptr [rbp+57h+var_88+8]
0x180030203  mov     r12, [rbp+57h+var_88]
0x180030207  test    r11d, r11d
0x18003020a  jle     loc_180030408
0x180030210  test    ebx, ebx
0x180030212  jle     loc_180030BDA
0x180030218  test    r12, r12
0x18003021b  jz      loc_1800302AE
0x180030221  cmp     dword ptr [r12+8], 0
0x180030227  jz      loc_1800302AE
0x18003022d  mov     eax, [r12+8]
0x180030232  test    eax, eax
0x180030234  jle     loc_180030B4B
0x18003023a  cmp     r13d, eax
0x18003023d  jge     loc_180030B4B
0x180030243  mov     rcx, [r12]
0x180030247  test    rcx, rcx
0x18003024a  jz      loc_180030B4B
0x180030250  test    r13d, r13d
0x180030253  js      loc_180030B4B
0x180030259  mov     eax, r13d
0x18003025c  imul    eax, [r12+10h]
0x180030262  movsxd  rdx, eax
0x180030265  add     rdx, rcx
0x180030268  xor     r9d, r9d
0x18003026b  test    rdx, rdx
0x18003026e  jz      short loc_1800302B1
0x180030270  mov     r10d, r15d
0x180030273  cmp     r15d, [rdx]
0x180030276  jz      loc_180030A35
0x18003027c  mov     rax, [rdx+8]
0x180030280  movsxd  rcx, r10d
0x180030283  lea     r8, [rax+rcx*2]
0x180030287  mov     ecx, [rdx+10h]
0x18003028a  lea     eax, [r10+r10]
0x18003028e  cmp     eax, ecx
0x180030290  jge     loc_1800308D5
0x180030296  mov     eax, ecx
0x180030298  xor     ecx, ecx
0x18003029a  cdq
0x18003029b  sub     eax, edx
0x18003029d  sar     eax, 1
0x18003029f  mov     r9d, eax
0x1800302a2  sub     r9d, r10d
0x1800302a5  test    r9d, r9d
0x1800302a8  cmovz   r8, rcx
0x1800302ac  jmp     short loc_1800302B4
0x1800302ae  xor     r9d, r9d
0x1800302b1  xor     r8d, r8d
0x1800302b4  test    r8, r8
0x1800302b7  jz      loc_180030408
0x1800302bd  test    ebx, ebx
0x1800302bf  lea     rdx, [r8-2]
0x1800302c3  mov     r10d, r11d
0x1800302c6  cmovns  rdx, r8
0x1800302ca  cmp     r9d, r11d
0x1800302cd  cmovl   r10d, r9d
0x1800302d1  mov     r8d, r10d
0x1800302d4  mov     [rbp+57h+arg_18], r10d
0x1800302d8  mov     eax, r10d
0x1800302db  nop     dword ptr [rax+rax+00h]
0x1800302e0  test    eax, eax
0x1800302e2  jz      short loc_18003032C
0x1800302e4  test    rdx, rdx
0x1800302e7  jz      loc_180030BF7
0x1800302ed  movzx   eax, word ptr [rdx]
0x1800302f0  cmp     ax, 9
0x1800302f4  jnz     short loc_1800302FB
0x1800302f6  bts     r14d, 8
0x1800302fb  movzx   ecx, ax
0x1800302fe  sub     ecx, 0Ah
0x180030301  cmp     ecx, 3
0x180030304  jbe     short loc_180030327
0x180030306  or      ax, 1
0x18003030a  mov     ecx, 2029h
0x18003030f  cmp     ax, cx
0x180030312  jz      short loc_180030327
0x180030314  movsxd  rax, ebx
0x180030317  dec     r8d
0x18003031a  mov     [rbp+57h+arg_18], r8d
0x18003031e  lea     rdx, [rdx+rax*2]
0x180030322  mov     eax, r8d
0x180030325  jmp     short loc_1800302E0
0x180030327  bts     r14d, 9
0x18003032c  sub     r10d, r8d
0x18003032f  sub     r11d, r10d
0x180030332  mov     [rbp+57h+arg_8], r11d
0x180030336  test    r12, r12
0x180030339  jz      loc_1800303FD
0x18003033f  mov     r8d, [r12+8]
0x180030344  test    r8d, r8d
0x180030347  jz      loc_1800303FD
0x18003034d  imul    r10d, ebx
0x180030351  mov     eax, edi
0x180030353  cdq
0x180030354  sub     eax, edx
0x180030356  sar     eax, 1
0x180030358  lea     ecx, [r10+rdi]
0x18003035c  cmp     ecx, eax
0x18003035e  jl      loc_180030A91
0x180030364  mov     r9d, r10d
0x180030367  test    r10d, r10d
0x18003036a  jz      loc_1800303F7
0x180030370  js      loc_180030930
0x180030376  test    r8d, r8d
0x180030379  jle     loc_180030B6C
0x18003037f  cmp     r13d, r8d
0x180030382  jge     loc_180030B6C
0x180030388  mov     rdx, [r12]
0x18003038c  test    rdx, rdx
0x18003038f  jz      loc_180030B6C
0x180030395  test    r13d, r13d
0x180030398  js      loc_180030B6C
0x18003039e  mov     eax, r13d
0x1800303a1  imul    eax, [r12+10h]
0x1800303a7  movsxd  rcx, eax
0x1800303aa  add     rcx, rdx
0x1800303ad  nop     dword ptr [rax]
0x1800303b0  test    r10d, r10d
0x1800303b3  jle     short loc_1800303F4
0x1800303b5  mov     eax, [rcx]
0x1800303b7  add     r15d, r10d
0x1800303ba  mov     dword ptr [rbp+57h+var_88+0Ch], r15d
0x1800303be  mov     r10d, r15d
0x1800303c1  cmp     r15d, eax
0x1800303c4  jl      short loc_1800303F1
0x1800303c6  inc     r13d
0x1800303c9  sub     r10d, eax
0x1800303cc  mov     dword ptr [rbp+57h+var_88+8], r13d
0x1800303d0  cmp     r13d, r8d
0x1800303d3  jge     loc_1800308AC
0x1800303d9  movsxd  rax, dword ptr [r12+10h]
0x1800303de  xor     r15d, r15d
0x1800303e1  mov     dword ptr [rbp+57h+var_88+0Ch], r15d
0x1800303e5  add     rcx, rax
0x1800303e8  jmp     short loc_1800303B0
0x1800303ea  add     r15d, r10d
0x1800303ed  mov     dword ptr [rbp+57h+var_88+0Ch], r15d
0x1800303f1  xor     r10d, r10d
0x1800303f4  sub     r9d, r10d
0x1800303f7  add     edi, r9d
0x1800303fa  mov     [rbp+57h+var_78], edi
0x1800303fd  bt      r14d, 9
0x180030402  jnb     loc_180030207
0x180030408  mov     [rbp+57h+var_A0], r14d
0x18003040c  bt      r14d, 9
0x180030411  jnb     loc_180030C10
0x180030417  mov     r8, [rsi]
0x18003041a  mov     r9d, [rsi+10h]
0x18003041e  mov     [rbp+57h+arg_8], r9d
0x180030422  test    r8, r8
0x180030425  jz      loc_1800304DE
0x18003042b  mov     ecx, [r8+8]
0x18003042f  test    ecx, ecx
0x180030431  jz      loc_1800304DE
0x180030437  mov     eax, r9d
0x18003043a  cdq
0x18003043b  sub     eax, edx
0x18003043d  sar     eax, 1
0x18003043f  cmp     edi, eax
0x180030441  jl      loc_180030AC1
0x180030447  sub     edi, r9d
0x18003044a  mov     r10d, edi
0x18003044d  jz      loc_1800304D3
0x180030453  test    edi, edi
0x180030455  js      loc_1800309A0
0x18003045b  mov     r9d, [rsi+8]
0x18003045f  test    ecx, ecx
0x180030461  jle     loc_180030B73
0x180030467  cmp     r9d, ecx
0x18003046a  jge     loc_180030B73
0x180030470  mov     rcx, [r8]
0x180030473  test    rcx, rcx
0x180030476  jz      loc_180030B73
0x18003047c  test    r9d, r9d
0x18003047f  js      loc_180030B73
0x180030485  mov     eax, r9d
0x180030488  imul    eax, [r8+10h]
0x18003048d  movsxd  rdx, eax
0x180030490  add     rdx, rcx
0x180030493  xor     r11d, r11d
0x180030496  test    edi, edi
0x180030498  jle     short loc_1800304CC
0x18003049a  mov     eax, [rdx]
0x18003049c  add     [rsi+0Ch], edi
0x18003049f  mov     edi, [rsi+0Ch]
0x1800304a2  cmp     edi, eax
0x1800304a4  jl      short loc_1800304C9
0x1800304a6  lea     ecx, [r9+1]
0x1800304aa  sub     edi, eax
0x1800304ac  mov     [rsi+8], ecx
0x1800304af  cmp     ecx, [r8+8]
0x1800304b3  jge     loc_1800308BE
0x1800304b9  mov     [rsi+0Ch], r11d
0x1800304bd  mov     r9d, ecx
0x1800304c0  movsxd  rax, dword ptr [r8+10h]
0x1800304c4  add     rdx, rax
0x1800304c7  jmp     short loc_180030496
0x1800304c9  mov     edi, r11d
0x1800304cc  mov     r9d, [rbp+57h+arg_8]
0x1800304d0  sub     r10d, edi
0x1800304d3  add     r9d, r10d
0x1800304d6  mov     [rbp+57h+arg_8], r9d
0x1800304da  mov     [rsi+10h], r9d
0x1800304de  test    ebx, ebx
0x1800304e0  jle     loc_18003082B
0x1800304e6  mov     r11, [rsi]
0x1800304e9  test    r11, r11
0x1800304ec  jz      loc_180030869
0x1800304f2  mov     ebx, [r11+8]
0x1800304f6  lea     rdi, [r11+8]
0x1800304fa  test    ebx, ebx
0x1800304fc  jz      loc_180030869
0x180030502  jle     loc_180030B59
0x180030508  mov     eax, [rsi+8]
0x18003050b  lea     r10, [rsi+8]
0x18003050f  cmp     eax, ebx
0x180030511  jge     loc_180030B59
0x180030517  mov     rcx, [r11]
0x18003051a  test    rcx, rcx
0x18003051d  jz      loc_180030B59
0x180030523  test    eax, eax
0x180030525  js      loc_180030B59
0x18003052b  imul    eax, [r11+10h]
0x180030530  movsxd  rdx, eax
0x180030533  add     rdx, rcx
0x180030536  test    rdx, rdx
0x180030539  jz      loc_18003086D
0x18003053f  mov     r8d, [rsi+0Ch]
0x180030543  lea     r9, [rsi+0Ch]
0x180030547  cmp     r8d, [rdx]
0x18003054a  jz      loc_180030A65
0x180030550  mov     rax, [rdx+8]
0x180030554  mov     ebx, [rdx+10h]
0x180030557  movsxd  rcx, r8d
0x18003055a  lea     rcx, [rax+rcx*2]
0x18003055e  lea     eax, [r8+r8]
0x180030562  cmp     eax, ebx
0x180030564  jge     loc_1800308FA
0x18003056a  mov     eax, ebx
0x18003056c  cdq
0x18003056d  sub     eax, edx
0x18003056f  sar     eax, 1
0x180030571  mov     ebx, eax
0x180030573  sub     ebx, r8d
0x180030576  test    ebx, ebx
0x180030578  jz      loc_180030875
0x18003057e  test    rcx, rcx
0x180030581  jz      loc_180030875
0x180030587  movzx   eax, word ptr [rcx]
0x18003058a  mov     r8, r9
0x18003058d  mov     [rbp+57h+arg_18], eax
0x180030590  mov     r15, r10
0x180030593  mov     [rbp+57h+var_60], r9
0x180030597  mov     r13, r10
0x18003059a  mov     [rbp+57h+var_98], r10
0x18003059e  mov     [rbp+57h+var_68], r9
0x1800305a2  mov     [rbp+57h+var_90], r10
0x1800305a6  mov     [rbp+57h+var_50], r9
0x1800305aa  mov     r12, rdi
0x1800305ad  mov     rbx, r9
0x1800305b0  mov     edi, [rdi]
0x1800305b2  mov     r14, r9
0x1800305b5  test    edi, edi
0x1800305b7  jz      loc_180030C38
0x1800305bd  mov     esi, [rsi+10h]
0x1800305c0  mov     eax, esi
0x1800305c2  cdq
0x1800305c3  sub     eax, edx
0x1800305c5  sar     eax, 1
0x1800305c7  lea     ecx, [rsi+1]
0x1800305ca  cmp     ecx, eax
  ... truncated ...
```
