# RtlRbRemoveNode

- ea: `0x180032410`
- end: `0x18003321e`
- name: `RtlRbRemoveNode`
- size: `3598`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180031a40`
- `0x180031dd0`
- `0x180031e40`
- `0x180033b58`
- `0x180049130`
- `0x18004ca78`
- `0x180075f34`
- `0x1800d2758`
- `0x1800e82d4`
- `0x18010a330`
- `0x180118680`
- `0x180145020`
- `0x180157584`

## callees

- `0x180032410`
- `0x1801410d0`

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
0x180032410  mov     rax, rsp
0x180032413  push    rbx
0x180032414  push    rbp
0x180032415  push    rsi
0x180032416  push    rdi
0x180032417  push    r12
0x180032419  push    r13
0x18003241b  push    r14
0x18003241d  push    r15
0x18003241f  sub     rsp, 38h
0x180032423  mov     rbx, [rdx]
0x180032426  mov     rsi, rcx
0x180032429  mov     qword ptr [rax+10h], 0
0x180032431  mov     rbp, rdx
0x180032434  movzx   eax, byte ptr [rcx+8]
0x180032438  mov     ecx, eax
0x18003243a  and     ecx, 1
0x18003243d  jnz     loc_18003268F
0x180032443  mov     r14, [rdx+8]
0x180032447  test    ecx, ecx
0x180032449  jnz     loc_1800326A0
0x18003244f  test    rbx, rbx
0x180032452  jnz     short loc_1800324A0
0x180032454  mov     rbx, r14
0x180032457  mov     rdi, [rdx+10h]
0x18003245b  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18003245f  and     al, 1
0x180032461  jnz     loc_180032968
0x180032467  test    rdi, rdi
0x18003246a  jz      loc_180032971
0x180032470  mov     rdx, [rdi+8]
0x180032474  mov     r15, rbp
0x180032477  test    al, al
0x180032479  jnz     loc_180032A17
0x18003247f  mov     rcx, rdx
0x180032482  cmp     rcx, rbp
0x180032485  jnz     loc_1800329BB
0x18003248b  mov     ecx, 1
0x180032490  mov     [rsp+78h+arg_0], ecx
0x180032497  mov     r13b, [rbp+10h]
0x18003249b  jmp     loc_180032615
0x1800324a0  test    r14, r14
0x1800324a3  jz      loc_180032670
0x1800324a9  mov     ecx, 1
0x1800324ae  mov     r15, r14
0x1800324b1  mov     [rsp+78h+arg_0], ecx
0x1800324b8  mov     rdi, r14
0x1800324bb  mov     rcx, [r14]
0x1800324be  and     al, 1
0x1800324c0  test    rcx, rcx
0x1800324c3  jnz     loc_1800326B1
0x1800324c9  test    al, al
0x1800324cb  mov     rax, rbx
0x1800324ce  jnz     loc_1800328D6
0x1800324d4  mov     [r15], rax
0x1800324d7  lea     r12, [rbx+10h]
0x1800324db  mov     rax, [r12]
0x1800324df  mov     rcx, rax
0x1800324e2  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800324e6  test    byte ptr [rsi+8], 1
0x1800324ea  jnz     loc_180032919
0x1800324f0  cmp     rcx, rbp
0x1800324f3  jz      short loc_180032501
0x1800324f5  mov     r8, rbx
0x1800324f8  call    RtlpRbReportFatalError
0x1800324fd  mov     rax, [r12]
0x180032501  test    byte ptr [rsi+8], 1
0x180032505  jnz     loc_1800328DE
0x18003250b  mov     rbx, r15
0x18003250e  and     eax, 3
0x180032511  or      rax, rbx
0x180032514  mov     [r12], rax
0x180032518  mov     rdx, [r14+10h]
0x18003251c  mov     rcx, rdx
0x18003251f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180032523  test    byte ptr [rsi+8], 1
0x180032527  jnz     loc_18003292A
0x18003252d  cmp     rcx, rbp
0x180032530  jz      short loc_180032541
0x180032532  mov     r8, r14
0x180032535  mov     rdx, rbp
0x180032538  call    RtlpRbReportFatalError
0x18003253d  mov     rdx, [r14+10h]
0x180032541  test    byte ptr [rsi+8], 1
0x180032545  jnz     loc_1800328E6
0x18003254b  mov     rcx, r14
0x18003254e  mov     rax, r15
0x180032551  xor     rcx, r15
0x180032554  and     edx, 3
0x180032557  or      rdx, rax
0x18003255a  mov     [r14+10h], rdx
0x18003255e  mov     al, [rsi+8]
0x180032561  mov     rbx, [r15+8]
0x180032565  and     al, 1
0x180032567  jnz     loc_18003293B
0x18003256d  test    al, al
0x18003256f  jnz     short loc_180032574
0x180032571  mov     rcx, r14
0x180032574  mov     [r15+8], rcx
0x180032578  mov     rcx, [r15+10h]
0x18003257c  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180032580  test    byte ptr [rsi+8], 1
0x180032584  jnz     loc_18003294C
0x18003258a  cmp     rcx, rdi
0x18003258d  jz      short loc_1800325A4
0x18003258f  test    rcx, rcx
0x180032592  jnz     short loc_180032599
0x180032594  cmp     rdi, r15
0x180032597  jz      short loc_1800325A4
0x180032599  mov     r8, r15
0x18003259c  mov     rdx, rdi
0x18003259f  call    RtlpRbReportFatalError
0x1800325a4  mov     rax, [rbp+10h]
0x1800325a8  mov     cl, [rsi+8]
0x1800325ab  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800325af  mov     r13b, [r15+10h]
0x1800325b3  and     cl, 1
0x1800325b6  jnz     loc_18003295D
0x1800325bc  test    cl, cl
0x1800325be  jnz     loc_1800328F7
0x1800325c4  and     qword ptr [r15+10h], 3
0x1800325c9  or      [r15+10h], rax
0x1800325cd  mov     al, [r15+10h]
0x1800325d1  xor     al, [rbp+10h]
0x1800325d4  and     al, 1
0x1800325d6  xor     [r15+10h], al
0x1800325da  mov     r14, [rbp+10h]
0x1800325de  and     r14, 0FFFFFFFFFFFFFFFCh
0x1800325e2  jnz     loc_180032A2B
0x1800325e8  test    byte ptr [rsi+8], 1
0x1800325ec  mov     rcx, [rsi]
0x1800325ef  jnz     loc_18003307D
0x1800325f5  cmp     rcx, rbp
0x1800325f8  jz      short loc_180032605
0x1800325fa  mov     r8, rsi
0x1800325fd  mov     rdx, rbp
0x180032600  call    RtlpRbReportFatalError
0x180032605  test    byte ptr [rsi+8], 1
0x180032609  mov     rax, r15
0x18003260c  jnz     loc_18003314D
0x180032612  mov     [rsi], rax
0x180032615  test    byte ptr [rsi+8], 1
0x180032619  jnz     short loc_180032678
0x18003261b  mov     rcx, rbx
0x18003261e  mov     ebp, [rsp+78h+arg_0]
0x180032625  mov     [rdi+rbp*8], rcx
0x180032629  test    rbx, rbx
0x18003262c  jz      loc_1800326D0
0x180032632  mov     rcx, [rbx+10h]
0x180032636  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18003263a  test    byte ptr [rsi+8], 1
0x18003263e  jnz     loc_180032908
0x180032644  cmp     rcx, r15
0x180032647  jz      short loc_180032654
0x180032649  mov     r8, rbx
0x18003264c  mov     rdx, r15
0x18003264f  call    RtlpRbReportFatalError
0x180032654  test    byte ptr [rsi+8], 1
0x180032658  jnz     short loc_180032685
0x18003265a  mov     [rbx+10h], rdi
0x18003265e  add     rsp, 38h
0x180032662  pop     r15
0x180032664  pop     r14
0x180032666  pop     r13
0x180032668  pop     r12
0x18003266a  pop     rdi
0x18003266b  pop     rsi
0x18003266c  pop     rbp
0x18003266d  pop     rbx
0x18003266e  retn
0x180032670  mov     r14, rbx
0x180032673  jmp     loc_180032457
0x180032678  test    rbx, rbx
0x18003267b  jz      short loc_18003261B
0x18003267d  mov     rcx, rdi
0x180032680  xor     rcx, rbx
0x180032683  jmp     short loc_18003261E
0x180032685  test    rdi, rdi
0x180032688  jz      short loc_18003265A
0x18003268a  xor     rdi, rbx
0x18003268d  jmp     short loc_18003265A
0x18003268f  test    rbx, rbx
0x180032692  jz      loc_180032443
0x180032698  xor     rbx, rbp
0x18003269b  jmp     loc_180032443
0x1800326a0  test    r14, r14
0x1800326a3  jz      loc_18003244F
0x1800326a9  xor     r14, rbp
0x1800326ac  jmp     loc_18003244F
0x1800326b1  mov     rdi, r15
0x1800326b4  test    al, al
0x1800326b6  jnz     loc_180032C2C
0x1800326bc  mov     r15, rcx
0x1800326bf  xor     ecx, ecx
0x1800326c1  mov     [rsp+78h+arg_0], ecx
0x1800326c8  mov     rcx, [r15]
0x1800326cb  jmp     loc_1800324C0
0x1800326d0  test    r13b, 1
0x1800326d4  jnz     short loc_18003265E
0x1800326d6  movzx   ecx, byte ptr [rsi+8]
0x1800326da  mov     r13d, ebp
0x1800326dd  xor     r13, 1
0x1800326e1  mov     r8d, ebp
0x1800326e4  mov     [rsp+78h+arg_10], r8
0x1800326ec  mov     [rsp+78h+arg_18], r13
0x1800326f4  mov     rbx, [rdi+r13*8]
0x1800326f8  test    cl, 1
0x1800326fb  jnz     loc_180032C1B
0x180032701  lea     r12, [rbx+10h]
0x180032705  test    byte ptr [r12], 1
0x18003270a  jz      loc_180032883
0x180032710  test    byte ptr [rsi+8], 1
0x180032714  mov     rax, [rsi]
0x180032717  jnz     loc_180033121
0x18003271d  mov     [rsp+78h+arg_8], rax
0x180032725  mov     r15d, ecx
0x180032728  mov     rax, [r12]
0x18003272c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180032730  and     r15d, 1
0x180032734  jnz     loc_180032D1F
0x18003273a  mov     rcx, rax
0x18003273d  cmp     rcx, rdi
0x180032740  jz      short loc_18003274D
0x180032742  mov     r8, rbx
0x180032745  mov     rdx, rdi
0x180032748  call    RtlpRbReportFatalError
0x18003274d  mov     rcx, [rdi+r13*8]
0x180032751  test    r15d, r15d
0x180032754  jnz     loc_180032D33
0x18003275a  cmp     rcx, rbx
0x18003275d  jz      short loc_18003276A
0x18003275f  mov     r8, rdi
0x180032762  mov     rdx, rbx
0x180032765  call    RtlpRbReportFatalError
0x18003276a  mov     r14, [rdi+10h]
0x18003276e  and     r14, 0FFFFFFFFFFFFFFFCh
0x180032772  test    r15d, r15d
0x180032775  jnz     loc_180032D71
0x18003277b  test    r14, r14
0x18003277e  jz      loc_180032D7A
0x180032784  mov     rcx, [r14+8]
0x180032788  test    r15d, r15d
0x18003278b  jnz     loc_180032DE4
0x180032791  mov     rax, rcx
0x180032794  cmp     rax, rdi
0x180032797  jnz     loc_180032CD6
0x18003279d  test    r15d, r15d
0x1800327a0  jnz     loc_180032E6A
0x1800327a6  mov     rax, rbx
0x1800327a9  mov     [r14+8], rax
0x1800327ad  test    r15d, r15d
0x1800327b0  jnz     loc_180032CB4
0x1800327b6  and     qword ptr [r12], 3
0x1800327bb  or      [r12], r14
0x1800327bf  mov     r8, [rsp+78h+arg_10]
0x1800327c7  lea     r14, [rbx+r8*8]
0x1800327cb  mov     rbp, [r14]
0x1800327ce  test    r15d, r15d
0x1800327d1  jz      short loc_1800327DB
0x1800327d3  test    rbp, rbp
0x1800327d6  jz      short loc_180032829
0x1800327d8  xor     rbp, rbx
0x1800327db  test    rbp, rbp
0x1800327de  jz      short loc_180032829
0x1800327e0  mov     rdx, [rbp+10h]
0x1800327e4  mov     rax, rdx
0x1800327e7  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800327eb  test    r15d, r15d
0x1800327ee  jnz     loc_180032D55
0x1800327f4  mov     rcx, rax
0x1800327f7  cmp     rcx, rbx
0x1800327fa  jz      short loc_180032813
0x1800327fc  mov     r8, rbp
0x1800327ff  mov     rdx, rbx
0x180032802  call    RtlpRbReportFatalError
0x180032807  mov     rdx, [rbp+10h]
0x18003280b  mov     r8, [rsp+78h+arg_10]
0x180032813  test    r15d, r15d
0x180032816  jnz     loc_180032C59
0x18003281c  mov     rax, rdi
0x18003281f  and     edx, 3
0x180032822  or      rdx, rax
0x180032825  mov     [rbp+10h], rdx
0x180032829  test    r15d, r15d
0x18003282c  jnz     loc_180032C48
0x180032832  mov     [rdi+r13*8], rbp
0x180032836  test    r15d, r15d
0x180032839  jnz     loc_180032C3D
0x18003283f  mov     [r14], rdi
0x180032842  and     qword ptr [rdi+10h], 3
0x180032847  or      [rdi+10h], rbx
0x18003284b  test    byte ptr [rsi+8], 1
0x18003284f  mov     rcx, [rsp+78h+arg_8]
0x180032857  jnz     loc_180033199
0x18003285d  mov     rax, rsi
0x180032860  mov     [rax], rcx
0x180032863  and     byte ptr [r12], 0FEh
0x180032868  or      byte ptr [rdi+10h], 1
0x18003286c  mov     cl, [rsi+8]
0x18003286f  mov     rbx, [rdi+r13*8]
  ... truncated ...
```
