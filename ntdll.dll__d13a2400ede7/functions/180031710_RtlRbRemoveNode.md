# RtlRbRemoveNode

- ea: `0x180031710`
- end: `0x18003251e`
- name: `RtlRbRemoveNode`
- size: `3598`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180030d40`
- `0x1800310d0`
- `0x180031140`
- `0x180032e58`
- `0x1800556dc`
- `0x180065d30`
- `0x180069678`
- `0x1800d6a08`
- `0x1800e8934`
- `0x18010b8d0`
- `0x180119170`
- `0x1801459b0`
- `0x180157f14`

## callees

- `0x180031710`
- `0x180141a60`

## pseudocode

```c
char __fastcall RtlRbRemoveNode(unsigned __int64 *a1, __int64 *a2)
{
  __int64 v2; // rbx
  char v5; // al
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int64 v10; // r15
  __int64 *v11; // rcx
  char v12; // r13
  unsigned __int64 v13; // rcx
  char v14; // al
  bool v15; // zf
  unsigned __int64 v16; // rax
  unsigned __int64 *v17; // r12
  __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // r14
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  unsigned int v30; // ebp
  unsigned __int64 v31; // rcx
  char v32; // cl
  __int64 v33; // r13
  __int64 v34; // r8
  unsigned __int64 v35; // rbx
  _QWORD *v36; // r12
  __int64 v37; // rax
  unsigned __int64 v38; // rax
  int v39; // r15d
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // r14
  __int64 v43; // rcx
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rax
  unsigned __int64 *v46; // r14
  unsigned __int64 v47; // rbp
  __int64 v48; // rdx
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rax
  char v54; // dl
  char v55; // cl
  __int64 v56; // rax
  char v57; // al
  unsigned __int64 v58; // rcx
  unsigned __int64 v59; // r14
  __int64 *v60; // rcx
  unsigned __int64 v61; // rcx
  char v62; // dl
  __int64 v63; // rax
  __int64 *v64; // rcx
  unsigned __int64 *v65; // r12
  unsigned __int64 v66; // rcx
  unsigned __int64 v67; // r14
  unsigned __int64 v68; // rcx
  char v69; // dl
  __int64 v70; // rax
  char v71; // r15
  unsigned __int64 v72; // rcx
  int v73; // r15d
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // r14
  __int64 v76; // rcx
  unsigned __int64 v77; // rax
  unsigned __int64 v78; // rax
  unsigned __int64 *v79; // r14
  unsigned __int64 v80; // rbp
  __int64 v81; // rax
  unsigned __int64 v82; // rcx
  unsigned __int64 v83; // r9
  unsigned __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rdx
  unsigned __int64 v87; // rcx
  unsigned __int64 v88; // rcx
  unsigned __int64 v89; // rax
  unsigned __int64 v90; // rcx
  unsigned __int64 v91; // rax
  unsigned __int64 v92; // r14
  __int64 v93; // rbp
  unsigned __int64 v94; // rax
  int v95; // r15d
  unsigned __int64 v96; // rcx
  __int64 v97; // r13
  __int64 v98; // r12
  __int64 v99; // rcx
  unsigned __int64 v100; // rcx
  unsigned __int64 v101; // rcx
  unsigned __int64 v102; // rax
  __int64 v103; // rbp
  __int64 v104; // rdx
  unsigned __int64 v105; // rax
  unsigned __int64 v106; // rcx
  unsigned __int64 v107; // rax
  unsigned __int64 v108; // rax
  unsigned __int64 v109; // rax
  unsigned int v111; // [rsp+80h] [rbp+8h]
  __int64 v112; // [rsp+88h] [rbp+10h] BYREF
  __int64 v113; // [rsp+90h] [rbp+18h]
  __int64 v114; // [rsp+98h] [rbp+20h]

  v2 = *a2;
  v112 = 0;
  v5 = *((_BYTE *)a1 + 8);
  if ( (v5 & 1) != 0 && v2 )
    v2 ^= (unsigned __int64)a2;
  v6 = a2[1];
  if ( (v5 & 1) != 0 && v6 )
    v6 ^= (unsigned __int64)a2;
  if ( !v2 )
  {
    v2 = v6;
    goto LABEL_5;
  }
  if ( v6 )
  {
    v10 = v6;
    v111 = 1;
    v7 = v6;
    v13 = *(_QWORD *)v6;
    v14 = v5 & 1;
    while ( v13 )
    {
      v7 = v10;
      if ( v14 )
        v10 ^= v13;
      else
        v10 = v13;
      v111 = 0;
      v13 = *(_QWORD *)v10;
    }
    v15 = v14 == 0;
    v16 = v2;
    if ( !v15 )
      v16 = v10 ^ v2;
    *(_QWORD *)v10 = v16;
    v17 = (unsigned __int64 *)(v2 + 16);
    v18 = *(_QWORD *)(v2 + 16);
    v19 = v18 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v19 )
      v19 ^= v2;
    if ( (__int64 *)v19 != a2 )
      RtlpRbReportFatalError(v19, a2, v2);
    if ( (a1[1] & 1) != 0 )
      v20 = v10 ^ v2;
    else
      v20 = v10;
    *v17 = v20 | v18 & 3;
    v21 = *(_QWORD *)(v6 + 16);
    v22 = v21 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v22 )
      v22 ^= v6;
    if ( (__int64 *)v22 != a2 )
      RtlpRbReportFatalError(v22, a2, v6);
    if ( (a1[1] & 1) != 0 )
      v23 = v10 ^ v6;
    else
      v23 = v10;
    v24 = v10 ^ v6;
    *(_QWORD *)(v6 + 16) = v23 | v21 & 3;
    v2 = *(_QWORD *)(v10 + 8);
    if ( (a1[1] & 1) != 0 && v2 )
    {
      v2 ^= v10;
    }
    else if ( (a1[1] & 1) == 0 )
    {
      v24 = v6;
    }
    *(_QWORD *)(v10 + 8) = v24;
    v25 = *(_QWORD *)(v10 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v25 )
      v25 ^= v10;
    if ( v25 != v7 && (v25 || v7 != v10) )
      RtlpRbReportFatalError(v25, v7, v10);
    v26 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
    v12 = *(_BYTE *)(v10 + 16);
    if ( (a1[1] & 1) != 0 && v26 )
    {
      v26 ^= (unsigned __int64)a2;
    }
    else if ( (a1[1] & 1) == 0 )
    {
      goto LABEL_37;
    }
    if ( v26 )
      v26 ^= v10;
LABEL_37:
    *(_QWORD *)(v10 + 16) &= 3uLL;
    *(_QWORD *)(v10 + 16) |= v26;
    *(_BYTE *)(v10 + 16) ^= (*((_BYTE *)a2 + 16) ^ *(_BYTE *)(v10 + 16)) & 1;
    v27 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v27 )
    {
      v62 = a1[1] & 1;
      if ( v62 )
        v27 ^= (unsigned __int64)a2;
      v63 = *(_QWORD *)(v27 + 8);
      if ( v62 && v63 )
        v64 = (__int64 *)(v63 ^ v27);
      else
        v64 = *(__int64 **)(v27 + 8);
      v8 = 0;
      if ( v64 == a2 )
        v8 = 8;
      v65 = (unsigned __int64 *)(v8 + v27);
      v66 = *(_QWORD *)(v8 + v27);
      if ( v62 && v66 )
        v66 ^= v27;
      if ( (__int64 *)v66 != a2 )
        RtlpRbReportFatalError(v66, a2, v27);
      if ( (a1[1] & 1) != 0 )
        v67 = v10 ^ v27;
      else
        v67 = v10;
      *v65 = v67;
      goto LABEL_44;
    }
    v28 = *a1;
    if ( (a1[1] & 1) != 0 )
    {
      if ( !v28 )
        goto LABEL_40;
      v28 ^= (unsigned __int64)a1;
    }
    if ( (__int64 *)v28 == a2 )
    {
      v8 = v10;
      if ( (a1[1] & 1) != 0 )
        v8 = (unsigned __int64)a1 ^ v10;
      *a1 = v8;
      goto LABEL_44;
    }
LABEL_40:
    RtlpRbReportFatalError(v28, a2, a1);
  }
  v6 = v2;
LABEL_5:
  v7 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
  LOBYTE(v8) = v5 & 1;
  if ( (_BYTE)v8 )
  {
    if ( !v7 )
    {
LABEL_130:
      if ( v2 )
        *(_QWORD *)(v2 + 16) = 0;
      v58 = *a1;
      if ( (a1[1] & 1) != 0 )
      {
        if ( !v58 )
          goto LABEL_134;
        v58 ^= (unsigned __int64)a1;
      }
      if ( (__int64 *)v58 == a2 )
      {
        if ( (a1[1] & 1) != 0 )
        {
          v59 = (unsigned __int64)a1 ^ v2;
          v8 = -v2;
          a1[1] = ((unsigned __int64)a1 ^ v2) & -(__int64)(v2 != 0);
          *((_BYTE *)a1 + 8) |= 1u;
        }
        else
        {
          a1[1] = v2;
          v59 = (unsigned __int64)a1 ^ v6;
        }
        if ( (a1[1] & 1) != 0 )
          v2 = v59 & -(__int64)(v2 != 0);
        *a1 = v2;
        return v8;
      }
LABEL_134:
      RtlpRbReportFatalError(v58, a2, a1);
    }
    v7 ^= (unsigned __int64)a2;
  }
  if ( !v7 )
    goto LABEL_130;
  v9 = *(_QWORD *)(v7 + 8);
  v10 = (unsigned __int64)a2;
  if ( (_BYTE)v8 && v9 )
    v11 = (__int64 *)(v9 ^ v7);
  else
    v11 = *(__int64 **)(v7 + 8);
  if ( v11 == a2 )
  {
    v111 = 1;
  }
  else
  {
    if ( (_BYTE)v8 && *(_QWORD *)v7 )
      v60 = (__int64 *)(*(_QWORD *)v7 ^ v7);
    else
      v60 = *(__int64 **)v7;
    if ( v60 != a2 )
      RtlpRbReportFatalError(v60, a2, v7);
    v111 = 0;
    v61 = a1[1];
    if ( (v61 & 1) != 0 )
    {
      if ( v61 == 1 )
        goto LABEL_11;
      v8 = v61 ^ ((unsigned __int64)a1 | 1);
    }
    else
    {
      v8 = a1[1];
    }
    if ( (__int64 *)v8 == a2 )
    {
      LOBYTE(v8) = a1[1] & 1;
      if ( v2 )
      {
        if ( !(_BYTE)v8 )
        {
          a1[1] = v2;
          goto LABEL_11;
        }
        v109 = v2;
      }
      else
      {
        if ( !(_BYTE)v8 )
        {
          a1[1] = v7;
          goto LABEL_11;
        }
        v109 = v7;
      }
      v8 = (unsigned __int64)a1 ^ v109;
      a1[1] = v8;
      *((_BYTE *)a1 + 8) |= 1u;
    }
  }
LABEL_11:
  v12 = *((_BYTE *)a2 + 16);
LABEL_44:
  if ( (a1[1] & 1) != 0 && v2 )
    v29 = v2 ^ v7;
  else
    v29 = v2;
  v30 = v111;
  *(_QWORD *)(v7 + 8LL * v111) = v29;
  if ( v2 )
  {
    v31 = *(_QWORD *)(v2 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v31 )
      v31 ^= v2;
    if ( v31 != v10 )
      RtlpRbReportFatalError(v31, v10, v2);
    if ( (a1[1] & 1) != 0 && v7 )
      v7 ^= v2;
    *(_QWORD *)(v2 + 16) = v7;
    return v8;
  }
  if ( (v12 & 1) != 0 )
    return v8;
  while ( 1 )
  {
    v32 = *((_BYTE *)a1 + 8);
    v33 = v30 ^ 1LL;
    v34 = v30;
    v113 = v30;
    v114 = v33;
    v35 = *(_QWORD *)(v7 + 8 * v33);
    if ( (v32 & 1) != 0 && v35 )
      v35 ^= v7;
    v36 = (_QWORD *)(v35 + 16);
    if ( (*(_BYTE *)(v35 + 16) & 1) != 0 )
    {
      v37 = *a1;
      if ( (a1[1] & 1) != 0 && v37 )
        v37 ^= (unsigned __int64)a1;
      v112 = v37;
      v38 = *v36 & 0xFFFFFFFFFFFFFFFCuLL;
      v39 = v32 & 1;
      if ( (v32 & 1) != 0 && v38 )
        v40 = v38 ^ v35;
      else
        v40 = *v36 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v40 != v7 )
        RtlpRbReportFatalError(v40, v7, v35);
      v41 = *(_QWORD *)(v7 + 8 * v33);
      if ( v39 && v41 )
        v41 ^= v7;
      if ( v41 != v35 )
        RtlpRbReportFatalError(v41, v35, v7);
      v42 = *(_QWORD *)(v7 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v39 )
      {
        if ( !v42 )
          goto LABEL_239;
        v42 ^= v7;
      }
      if ( v42 )
      {
        v43 = *(_QWORD *)(v42 + 8);
        if ( v39 && v43 )
          v44 = v43 ^ v42;
        else
          v44 = *(_QWORD *)(v42 + 8);
        if ( v44 == v7 )
        {
          if ( v39 )
            v45 = v35 ^ v42;
          else
            v45 = v35;
          *(_QWORD *)(v42 + 8) = v45;
        }
        else
        {
          if ( v39 && *(_QWORD *)v42 )
            v88 = *(_QWORD *)v42 ^ v42;
          else
            v88 = *(_QWORD *)v42;
          if ( v88 != v7 )
            RtlpRbReportFatalError(v88, v7, v42);
          if ( v39 )
            v89 = v35 ^ v42;
          else
            v89 = v35;
          *(_QWORD *)v42 = v89;
        }
        goto LABEL_84;
      }
LABEL_239:
      if ( v112 != v7 )
        RtlpRbReportFatalError(v112, v7, &v112);
      v112 = v35;
LABEL_84:
      if ( v39 && v42 )
        v42 ^= v35;
      *v36 &= 3uLL;
      *v36 |= v42;
      v34 = v113;
      v46 = (unsigned __int64 *)(v35 + 8 * v113);
      v47 = *v46;
      if ( v39 )
      {
        if ( !v47 )
        {
LABEL_96:
          if ( v39 && v47 )
            v47 ^= v7;
          *(_QWORD *)(v7 + 8 * v33) = v47;
          if ( v39 )
          {
            v35 ^= v7;
            *v46 = v35;
          }
          else
          {
            *v46 = v7;
          }
          *(_QWORD *)(v7 + 16) &= 3uLL;
          *(_QWORD *)(v7 + 16) |= v35;
          v52 = v112;
          if ( (a1[1] & 1) != 0 )
            v52 = ((unsigned __int64)a1 ^ v112) & -(__int64)(v112 != 0);
          *a1 = v52;
          *(_BYTE *)v36 &= ~1u;
          *(_BYTE *)(v7 + 16) |= 1u;
          v32 = *((_BYTE *)a1 + 8);
          v35 = *(_QWORD *)(v7 + 8 * v33);
          if ( (v32 & 1) != 0 && v35 )
            v35 ^= v7;
          v30 = v111;
          goto LABEL_103;
        }
        v47 ^= v35;
      }
      if ( v47 )
      {
        v48 = *(_QWORD *)(v47 + 16);
        v49 = v48 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v39 && v49 )
          v50 = v49 ^ v47;
        else
          v50 = *(_QWORD *)(v47 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v50 != v35 )
          RtlpRbReportFatalError(v50, v35, v47);
        if ( v39 )
          v51 = v7 ^ v47;
        else
          v51 = v7;
        *(_QWORD *)(v47 + 16) = v51 | v48 & 3;
      }
      goto LABEL_96;
    }
LABEL_103:
    v53 = *(_QWORD *)v35;
    v54 = v32;
    v55 = v32 & 1;
    if ( *(_QWORD *)v35 )
    {
      if ( v55 )
        v53 ^= v35;
      if ( (*(_BYTE *)(v53 + 16) & 1) != 0 )
        break;
    }
    v56 = *(_QWORD *)(v35 + 8);
    if ( v56 )
    {
      if ( v55 )
        v56 ^= v35;
      if ( (*(_BYTE *)(v56 + 16) & 1) != 0 )
        break;
    }
    v57 = *(_BYTE *)(v7 + 16);
    if ( (v57 & 1) != 0 )
    {
      LOBYTE(v8) = v57 & 0xFE;
      *(_BYTE *)(v7 + 16) = v8;
      *(_BYTE *)(v35 + 16) |= 1u;
      return v8;
    }
    *(_BYTE *)(v35 + 16) |= 1u;
    v8 = *(_QWORD *)(v7 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 )
    {
      if ( !v8 )
        return v8;
      v8 ^= v7;
    }
    if ( !v8 )
      return v8;
    v86 = *(_QWORD *)(v8 + 8);
    if ( (a1[1] & 1) != 0 && v86 )
      v87 = v86 ^ v8;
    else
      v87 = *(_QWORD *)(v8 + 8);
    v15 = v87 == v7;
    v7 = v8;
    v30 = v15;
    v111 = v15;
  }
  v68 = *(_QWORD *)(v35 + 8 * v33);
  v69 = v54 & 1;
  if ( v69 )
  {
    if ( v68 )
    {
      v68 ^= v35;
      goto LABEL_167;
    }
LABEL_274:
    v92 = *(_QWORD *)(v35 + 8 * v34);
    if ( v69 && v92 )
      v92 ^= v35;
    *(_BYTE *)(v92 + 16) &= ~1u;
    v93 = v30 ^ 1;
    v94 = *(_QWORD *)(v92 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    v95 = a1[1] & 1;
    if ( (a1[1] & 1) != 0 && v94 )
      v96 = v94 ^ v92;
    else
      v96 = *(_QWORD *)(v92 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v96 != v35 )
      RtlpRbReportFatalError(v96, v35, v92);
    v97 = (unsigned int)v93 ^ 1LL;
    v98 = (unsigned int)v93;
    v99 = *(_QWORD *)(v35 + 8 * v97);
    if ( (a1[1] & 1) != 0 && v99 )
      v99 ^= v35;
    if ( v99 != v92 )
      RtlpRbReportFatalError(v99, v92, v35);
    v100 = *(_QWORD *)(v7 + 8 * v93);
    if ( (a1[1] & 1) != 0 && v100 )
      v100 ^= v7;
    if ( v100 != v35 )
      RtlpRbReportFatalError(v100, v35, v7);
    v101 = *(_QWORD *)(v35 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v101 )
      v101 ^= v35;
    if ( v101 != v7 )
      RtlpRbReportFatalError(v101, v7, v35);
    if ( (a1[1] & 1) == 0 )
    {
      *(_QWORD *)(v7 + 8 * v93) = v92;
      goto LABEL_290;
    }
    v102 = v7 ^ v92;
    *(_QWORD *)(v7 + 8 * v93) = v7 ^ v92;
    if ( !v7 )
LABEL_290:
      v102 = v7;
    *(_QWORD *)(v92 + 16) &= 3uLL;
    *(_QWORD *)(v92 + 16) |= v102;
    v103 = *(_QWORD *)(v92 + 8 * v93);
    if ( v95 )
    {
      if ( v103 )
      {
        v103 ^= v92;
        goto LABEL_294;
      }
    }
    else
    {
LABEL_294:
      if ( v103 )
      {
        v104 = *(_QWORD *)(v103 + 16);
        v105 = v104 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v95 && v105 )
          v106 = v105 ^ v103;
        else
          v106 = *(_QWORD *)(v103 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v106 != v92 )
          RtlpRbReportFatalError(v106, v92, v103);
        if ( v95 )
          v107 = v35 ^ v103;
        else
          v107 = v35;
        *(_QWORD *)(v103 + 16) = v107 | v104 & 3;
      }
    }
    if ( v95 && v103 )
      v103 ^= v35;
    *(_QWORD *)(v35 + 8 * v97) = v103;
    v108 = v92;
    if ( v95 )
    {
      v108 = v35 ^ v92;
      *(_QWORD *)(v92 + 8 * v98) = v35 ^ v92;
    }
    else
    {
      *(_QWORD *)(v92 + 8 * v98) = v35;
    }
    *(_QWORD *)(v35 + 16) &= 3uLL;
    v68 = v35;
    *(_QWORD *)(v35 + 16) |= v108;
    v35 = v92;
    v33 = v114;
  }
  else
  {
LABEL_167:
    if ( !v68 || (*(_BYTE *)(v68 + 16) & 1) == 0 )
      goto LABEL_274;
  }
  *(_BYTE *)(v35 + 16) ^= (*(_BYTE *)(v7 + 16) ^ *(_BYTE *)(v35 + 16)) & 1;
  *(_BYTE *)(v7 + 16) &= ~1u;
  *(_BYTE *)(v68 + 16) &= ~1u;
  v70 = *a1;
  if ( (a1[1] & 1) != 0 && v70 )
    v70 ^= (unsigned __int64)a1;
  v71 = *((_BYTE *)a1 + 8);
  v112 = v70;
  v72 = *(_QWORD *)(v35 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
  v73 = v71 & 1;
  if ( v73 && v72 )
    v72 ^= v35;
  if ( v72 != v7 )
    RtlpRbReportFatalError(v72, v7, v35);
  v74 = *(_QWORD *)(v7 + 8 * v33);
  if ( v73 && v74 )
    v74 ^= v7;
  if ( v74 != v35 )
    RtlpRbReportFatalError(v74, v35, v7);
  v75 = *(_QWORD *)(v7 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v73 )
  {
    if ( v75 )
    {
      v75 ^= v7;
      goto LABEL_177;
    }
  }
  else
  {
LABEL_177:
    if ( v75 )
    {
      v76 = *(_QWORD *)(v75 + 8);
      if ( v73 && v76 )
        v77 = v76 ^ v75;
      else
        v77 = *(_QWORD *)(v75 + 8);
      if ( v77 == v7 )
      {
        if ( v73 )
          v78 = v35 ^ v75;
        else
          v78 = v35;
        *(_QWORD *)(v75 + 8) = v78;
      }
      else
      {
        if ( v73 && *(_QWORD *)v75 )
          v90 = *(_QWORD *)v75 ^ v75;
        else
          v90 = *(_QWORD *)v75;
        if ( v90 != v7 )
          RtlpRbReportFatalError(v90, v7, v75);
        if ( v73 )
          v91 = v35 ^ v75;
        else
          v91 = v35;
        *(_QWORD *)v75 = v91;
      }
      goto LABEL_184;
    }
  }
  if ( v112 != v7 )
    RtlpRbReportFatalError(v112, v7, &v112);
  v112 = v35;
LABEL_184:
  if ( v73 && v75 )
    v75 ^= v35;
  *(_QWORD *)(v35 + 16) &= 3uLL;
  *(_QWORD *)(v35 + 16) |= v75;
  LOBYTE(v8) = v113;
  v79 = (unsigned __int64 *)(v35 + 8 * v113);
  v80 = *v79;
  if ( v73 )
  {
    if ( v80 )
    {
      v80 ^= v35;
      goto LABEL_188;
    }
  }
  else
  {
LABEL_188:
    if ( v80 )
    {
      v81 = *(_QWORD *)(v80 + 16);
      v82 = v81 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v73 && v82 )
        v83 = v82 ^ v80;
      else
        v83 = *(_QWORD *)(v80 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v83 != v35 )
        RtlpRbReportFatalError(v83, v35, v80);
      if ( v73 )
        v84 = v7 ^ v80;
      else
        v84 = v7;
      v8 = v84 | v81 & 3;
      *(_QWORD *)(v80 + 16) = v8;
    }
  }
  if ( v73 && v80 )
    v80 ^= v7;
  *(_QWORD *)(v7 + 8 * v33) = v80;
  if ( v73 )
  {
    v35 ^= v7;
    *v79 = v35;
  }
  else
  {
    *v79 = v7;
  }
  *(_QWORD *)(v7 + 16) &= 3uLL;
  *(_QWORD *)(v7 + 16) |= v35;
  v85 = v112;
  if ( (a1[1] & 1) != 0 )
  {
    LOBYTE(v8) = (unsigned __int8)a1 ^ v112;
    v85 = ((unsigned __int64)a1 ^ v112) & -(__int64)(v112 != 0);
  }
  *a1 = v85;
  return v8;
}

```

## disassembly

```asm
0x180031710  mov     rax, rsp
0x180031713  push    rbx
0x180031714  push    rbp
0x180031715  push    rsi
0x180031716  push    rdi
0x180031717  push    r12
0x180031719  push    r13
0x18003171b  push    r14
0x18003171d  push    r15
0x18003171f  sub     rsp, 38h
0x180031723  mov     rbx, [rdx]
0x180031726  mov     rsi, rcx
0x180031729  mov     qword ptr [rax+10h], 0
0x180031731  mov     rbp, rdx
0x180031734  movzx   eax, byte ptr [rcx+8]
0x180031738  mov     ecx, eax
0x18003173a  and     ecx, 1
0x18003173d  jnz     loc_18003198F
0x180031743  mov     r14, [rdx+8]
0x180031747  test    ecx, ecx
0x180031749  jnz     loc_1800319A0
0x18003174f  test    rbx, rbx
0x180031752  jnz     short loc_1800317A0
0x180031754  mov     rbx, r14
0x180031757  mov     rdi, [rdx+10h]
0x18003175b  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18003175f  and     al, 1
0x180031761  jnz     loc_180031C68
0x180031767  test    rdi, rdi
0x18003176a  jz      loc_180031C71
0x180031770  mov     rdx, [rdi+8]
0x180031774  mov     r15, rbp
0x180031777  test    al, al
0x180031779  jnz     loc_180031D17
0x18003177f  mov     rcx, rdx
0x180031782  cmp     rcx, rbp
0x180031785  jnz     loc_180031CBB
0x18003178b  mov     ecx, 1
0x180031790  mov     [rsp+78h+arg_0], ecx
0x180031797  mov     r13b, [rbp+10h]
0x18003179b  jmp     loc_180031915
0x1800317a0  test    r14, r14
0x1800317a3  jz      loc_180031970
0x1800317a9  mov     ecx, 1
0x1800317ae  mov     r15, r14
0x1800317b1  mov     [rsp+78h+arg_0], ecx
0x1800317b8  mov     rdi, r14
0x1800317bb  mov     rcx, [r14]
0x1800317be  and     al, 1
0x1800317c0  test    rcx, rcx
0x1800317c3  jnz     loc_1800319B1
0x1800317c9  test    al, al
0x1800317cb  mov     rax, rbx
0x1800317ce  jnz     loc_180031BD6
0x1800317d4  mov     [r15], rax
0x1800317d7  lea     r12, [rbx+10h]
0x1800317db  mov     rax, [r12]
0x1800317df  mov     rcx, rax
0x1800317e2  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800317e6  test    byte ptr [rsi+8], 1
0x1800317ea  jnz     loc_180031C19
0x1800317f0  cmp     rcx, rbp
0x1800317f3  jz      short loc_180031801
0x1800317f5  mov     r8, rbx
0x1800317f8  call    RtlpRbReportFatalError
0x1800317fd  mov     rax, [r12]
0x180031801  test    byte ptr [rsi+8], 1
0x180031805  jnz     loc_180031BDE
0x18003180b  mov     rbx, r15
0x18003180e  and     eax, 3
0x180031811  or      rax, rbx
0x180031814  mov     [r12], rax
0x180031818  mov     rdx, [r14+10h]
0x18003181c  mov     rcx, rdx
0x18003181f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180031823  test    byte ptr [rsi+8], 1
0x180031827  jnz     loc_180031C2A
0x18003182d  cmp     rcx, rbp
0x180031830  jz      short loc_180031841
0x180031832  mov     r8, r14
0x180031835  mov     rdx, rbp
0x180031838  call    RtlpRbReportFatalError
0x18003183d  mov     rdx, [r14+10h]
0x180031841  test    byte ptr [rsi+8], 1
0x180031845  jnz     loc_180031BE6
0x18003184b  mov     rcx, r14
0x18003184e  mov     rax, r15
0x180031851  xor     rcx, r15
0x180031854  and     edx, 3
0x180031857  or      rdx, rax
0x18003185a  mov     [r14+10h], rdx
0x18003185e  mov     al, [rsi+8]
0x180031861  mov     rbx, [r15+8]
0x180031865  and     al, 1
0x180031867  jnz     loc_180031C3B
0x18003186d  test    al, al
0x18003186f  jnz     short loc_180031874
0x180031871  mov     rcx, r14
0x180031874  mov     [r15+8], rcx
0x180031878  mov     rcx, [r15+10h]
0x18003187c  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180031880  test    byte ptr [rsi+8], 1
0x180031884  jnz     loc_180031C4C
0x18003188a  cmp     rcx, rdi
0x18003188d  jz      short loc_1800318A4
0x18003188f  test    rcx, rcx
0x180031892  jnz     short loc_180031899
0x180031894  cmp     rdi, r15
0x180031897  jz      short loc_1800318A4
0x180031899  mov     r8, r15
0x18003189c  mov     rdx, rdi
0x18003189f  call    RtlpRbReportFatalError
0x1800318a4  mov     rax, [rbp+10h]
0x1800318a8  mov     cl, [rsi+8]
0x1800318ab  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800318af  mov     r13b, [r15+10h]
0x1800318b3  and     cl, 1
0x1800318b6  jnz     loc_180031C5D
0x1800318bc  test    cl, cl
0x1800318be  jnz     loc_180031BF7
0x1800318c4  and     qword ptr [r15+10h], 3
0x1800318c9  or      [r15+10h], rax
0x1800318cd  mov     al, [r15+10h]
0x1800318d1  xor     al, [rbp+10h]
0x1800318d4  and     al, 1
0x1800318d6  xor     [r15+10h], al
0x1800318da  mov     r14, [rbp+10h]
0x1800318de  and     r14, 0FFFFFFFFFFFFFFFCh
0x1800318e2  jnz     loc_180031D2B
0x1800318e8  test    byte ptr [rsi+8], 1
0x1800318ec  mov     rcx, [rsi]
0x1800318ef  jnz     loc_18003237D
0x1800318f5  cmp     rcx, rbp
0x1800318f8  jz      short loc_180031905
0x1800318fa  mov     r8, rsi
0x1800318fd  mov     rdx, rbp
0x180031900  call    RtlpRbReportFatalError
0x180031905  test    byte ptr [rsi+8], 1
0x180031909  mov     rax, r15
0x18003190c  jnz     loc_18003244D
0x180031912  mov     [rsi], rax
0x180031915  test    byte ptr [rsi+8], 1
0x180031919  jnz     short loc_180031978
0x18003191b  mov     rcx, rbx
0x18003191e  mov     ebp, [rsp+78h+arg_0]
0x180031925  mov     [rdi+rbp*8], rcx
0x180031929  test    rbx, rbx
0x18003192c  jz      loc_1800319D0
0x180031932  mov     rcx, [rbx+10h]
0x180031936  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18003193a  test    byte ptr [rsi+8], 1
0x18003193e  jnz     loc_180031C08
0x180031944  cmp     rcx, r15
0x180031947  jz      short loc_180031954
0x180031949  mov     r8, rbx
0x18003194c  mov     rdx, r15
0x18003194f  call    RtlpRbReportFatalError
0x180031954  test    byte ptr [rsi+8], 1
0x180031958  jnz     short loc_180031985
0x18003195a  mov     [rbx+10h], rdi
0x18003195e  add     rsp, 38h
0x180031962  pop     r15
0x180031964  pop     r14
0x180031966  pop     r13
0x180031968  pop     r12
0x18003196a  pop     rdi
0x18003196b  pop     rsi
0x18003196c  pop     rbp
0x18003196d  pop     rbx
0x18003196e  retn
0x180031970  mov     r14, rbx
0x180031973  jmp     loc_180031757
0x180031978  test    rbx, rbx
0x18003197b  jz      short loc_18003191B
0x18003197d  mov     rcx, rdi
0x180031980  xor     rcx, rbx
0x180031983  jmp     short loc_18003191E
0x180031985  test    rdi, rdi
0x180031988  jz      short loc_18003195A
0x18003198a  xor     rdi, rbx
0x18003198d  jmp     short loc_18003195A
0x18003198f  test    rbx, rbx
0x180031992  jz      loc_180031743
0x180031998  xor     rbx, rbp
0x18003199b  jmp     loc_180031743
0x1800319a0  test    r14, r14
0x1800319a3  jz      loc_18003174F
0x1800319a9  xor     r14, rbp
0x1800319ac  jmp     loc_18003174F
0x1800319b1  mov     rdi, r15
0x1800319b4  test    al, al
0x1800319b6  jnz     loc_180031F2C
0x1800319bc  mov     r15, rcx
0x1800319bf  xor     ecx, ecx
0x1800319c1  mov     [rsp+78h+arg_0], ecx
0x1800319c8  mov     rcx, [r15]
0x1800319cb  jmp     loc_1800317C0
0x1800319d0  test    r13b, 1
0x1800319d4  jnz     short loc_18003195E
0x1800319d6  movzx   ecx, byte ptr [rsi+8]
0x1800319da  mov     r13d, ebp
0x1800319dd  xor     r13, 1
0x1800319e1  mov     r8d, ebp
0x1800319e4  mov     [rsp+78h+arg_10], r8
0x1800319ec  mov     [rsp+78h+arg_18], r13
0x1800319f4  mov     rbx, [rdi+r13*8]
0x1800319f8  test    cl, 1
0x1800319fb  jnz     loc_180031F1B
0x180031a01  lea     r12, [rbx+10h]
0x180031a05  test    byte ptr [r12], 1
0x180031a0a  jz      loc_180031B83
0x180031a10  test    byte ptr [rsi+8], 1
0x180031a14  mov     rax, [rsi]
0x180031a17  jnz     loc_180032421
0x180031a1d  mov     [rsp+78h+arg_8], rax
0x180031a25  mov     r15d, ecx
0x180031a28  mov     rax, [r12]
0x180031a2c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180031a30  and     r15d, 1
0x180031a34  jnz     loc_18003201F
0x180031a3a  mov     rcx, rax
0x180031a3d  cmp     rcx, rdi
0x180031a40  jz      short loc_180031A4D
0x180031a42  mov     r8, rbx
0x180031a45  mov     rdx, rdi
0x180031a48  call    RtlpRbReportFatalError
0x180031a4d  mov     rcx, [rdi+r13*8]
0x180031a51  test    r15d, r15d
0x180031a54  jnz     loc_180032033
0x180031a5a  cmp     rcx, rbx
0x180031a5d  jz      short loc_180031A6A
0x180031a5f  mov     r8, rdi
0x180031a62  mov     rdx, rbx
0x180031a65  call    RtlpRbReportFatalError
0x180031a6a  mov     r14, [rdi+10h]
0x180031a6e  and     r14, 0FFFFFFFFFFFFFFFCh
0x180031a72  test    r15d, r15d
0x180031a75  jnz     loc_180032071
0x180031a7b  test    r14, r14
0x180031a7e  jz      loc_18003207A
0x180031a84  mov     rcx, [r14+8]
0x180031a88  test    r15d, r15d
0x180031a8b  jnz     loc_1800320E4
0x180031a91  mov     rax, rcx
0x180031a94  cmp     rax, rdi
0x180031a97  jnz     loc_180031FD6
0x180031a9d  test    r15d, r15d
0x180031aa0  jnz     loc_18003216A
0x180031aa6  mov     rax, rbx
0x180031aa9  mov     [r14+8], rax
0x180031aad  test    r15d, r15d
0x180031ab0  jnz     loc_180031FB4
0x180031ab6  and     qword ptr [r12], 3
0x180031abb  or      [r12], r14
0x180031abf  mov     r8, [rsp+78h+arg_10]
0x180031ac7  lea     r14, [rbx+r8*8]
0x180031acb  mov     rbp, [r14]
0x180031ace  test    r15d, r15d
0x180031ad1  jz      short loc_180031ADB
0x180031ad3  test    rbp, rbp
0x180031ad6  jz      short loc_180031B29
0x180031ad8  xor     rbp, rbx
0x180031adb  test    rbp, rbp
0x180031ade  jz      short loc_180031B29
0x180031ae0  mov     rdx, [rbp+10h]
0x180031ae4  mov     rax, rdx
0x180031ae7  and     rax, 0FFFFFFFFFFFFFFFCh
0x180031aeb  test    r15d, r15d
0x180031aee  jnz     loc_180032055
0x180031af4  mov     rcx, rax
0x180031af7  cmp     rcx, rbx
0x180031afa  jz      short loc_180031B13
0x180031afc  mov     r8, rbp
0x180031aff  mov     rdx, rbx
0x180031b02  call    RtlpRbReportFatalError
0x180031b07  mov     rdx, [rbp+10h]
0x180031b0b  mov     r8, [rsp+78h+arg_10]
0x180031b13  test    r15d, r15d
0x180031b16  jnz     loc_180031F59
0x180031b1c  mov     rax, rdi
0x180031b1f  and     edx, 3
0x180031b22  or      rdx, rax
0x180031b25  mov     [rbp+10h], rdx
0x180031b29  test    r15d, r15d
0x180031b2c  jnz     loc_180031F48
0x180031b32  mov     [rdi+r13*8], rbp
0x180031b36  test    r15d, r15d
0x180031b39  jnz     loc_180031F3D
0x180031b3f  mov     [r14], rdi
0x180031b42  and     qword ptr [rdi+10h], 3
0x180031b47  or      [rdi+10h], rbx
0x180031b4b  test    byte ptr [rsi+8], 1
0x180031b4f  mov     rcx, [rsp+78h+arg_8]
0x180031b57  jnz     loc_180032499
0x180031b5d  mov     rax, rsi
0x180031b60  mov     [rax], rcx
0x180031b63  and     byte ptr [r12], 0FEh
0x180031b68  or      byte ptr [rdi+10h], 1
0x180031b6c  mov     cl, [rsi+8]
0x180031b6f  mov     rbx, [rdi+r13*8]
  ... truncated ...
```
