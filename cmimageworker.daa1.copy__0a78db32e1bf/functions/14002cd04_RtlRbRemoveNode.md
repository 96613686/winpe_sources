# RtlRbRemoveNode

- ea: `0x14002cd04`
- end: `0x14002d7ac`
- name: `RtlRbRemoveNode`
- size: `2728`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140024310`
- `0x140024f20`

## callees

- `0x14002cd04`
- `0x14002d7b4`

## pseudocode

```c
char __fastcall RtlRbRemoveNode(__int64 *a1, __int64 *a2)
{
  char v2; // al
  __int64 v4; // rbx
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  char v10; // al
  bool v11; // zf
  unsigned __int64 v12; // rax
  unsigned __int64 *v13; // r12
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  char v23; // r13
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // rcx
  __int64 v26; // rax
  char v27; // dl
  __int64 v28; // rax
  __int64 *v29; // rcx
  unsigned __int64 *v30; // r12
  __int64 *v31; // rcx
  unsigned __int64 v32; // r14
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // r14
  __int64 v35; // rdx
  __int64 *v36; // rcx
  __int64 *v37; // rcx
  __int64 v38; // rcx
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rcx
  unsigned int v41; // ebp
  unsigned __int64 v42; // rcx
  char v43; // cl
  __int64 v44; // r13
  __int64 v45; // r8
  unsigned __int64 v46; // rbx
  _QWORD *v47; // r12
  __int64 v48; // rax
  unsigned __int64 v49; // rax
  int v50; // r15d
  unsigned __int64 v51; // rcx
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // r14
  __int64 v54; // rcx
  unsigned __int64 v55; // rax
  unsigned __int64 v56; // rax
  unsigned __int64 v57; // rcx
  unsigned __int64 v58; // rax
  unsigned __int64 *v59; // r14
  unsigned __int64 v60; // rbp
  __int64 v61; // rdx
  unsigned __int64 v62; // rax
  unsigned __int64 v63; // rcx
  unsigned __int64 v64; // rax
  __int64 *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rax
  char v68; // dl
  char v69; // cl
  __int64 v70; // rax
  char v71; // al
  __int64 v72; // rdx
  __int64 v73; // rcx
  unsigned __int64 v74; // rcx
  char v75; // dl
  unsigned __int64 v76; // r14
  __int64 v77; // rbp
  unsigned __int64 v78; // rax
  int v79; // r15d
  unsigned __int64 v80; // rcx
  __int64 v81; // r13
  __int64 v82; // r12
  __int64 v83; // rcx
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // rcx
  unsigned __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // rbp
  __int64 v89; // rdx
  unsigned __int64 v90; // rax
  unsigned __int64 v91; // rcx
  unsigned __int64 v92; // rax
  unsigned __int64 v93; // rax
  __int64 v94; // rax
  char v95; // r15
  unsigned __int64 v96; // rcx
  int v97; // r15d
  unsigned __int64 v98; // rcx
  unsigned __int64 v99; // r14
  __int64 v100; // rcx
  unsigned __int64 v101; // rax
  unsigned __int64 v102; // rax
  unsigned __int64 v103; // rcx
  unsigned __int64 v104; // rax
  unsigned __int64 *v105; // r14
  unsigned __int64 v106; // rbp
  __int64 v107; // rax
  unsigned __int64 v108; // rcx
  unsigned __int64 v109; // r9
  unsigned __int64 v110; // rcx
  unsigned int v112; // [rsp+70h] [rbp+8h]
  __int64 v113; // [rsp+78h] [rbp+10h] BYREF
  __int64 v114; // [rsp+80h] [rbp+18h]
  __int64 v115; // [rsp+88h] [rbp+20h]

  v2 = *((_BYTE *)a1 + 8);
  v4 = *a2;
  v113 = 0;
  if ( (v2 & 1) != 0 && v4 )
    v4 ^= (unsigned __int64)a2;
  v6 = a2[1];
  if ( (v2 & 1) != 0 && v6 )
    v6 ^= (unsigned __int64)a2;
  if ( !v4 )
  {
    v4 = v6;
    goto LABEL_81;
  }
  if ( v6 )
  {
    v7 = v6;
    v112 = 1;
    v8 = v6;
    v9 = *(_QWORD *)v6;
    v10 = v2 & 1;
    while ( v9 )
    {
      v8 = v7;
      if ( v10 )
        v7 ^= v9;
      else
        v7 = v9;
      v112 = 0;
      v9 = *(_QWORD *)v7;
    }
    v11 = v10 == 0;
    v12 = v4;
    if ( !v11 )
      v12 = v7 ^ v4;
    *(_QWORD *)v7 = v12;
    v13 = (unsigned __int64 *)(v4 + 16);
    v14 = *(_QWORD *)(v4 + 16);
    v15 = v14 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v15 )
      v15 ^= v4;
    if ( (__int64 *)v15 != a2 )
      RtlpRbReportFatalError(v15, a2, v4);
    if ( (a1[1] & 1) != 0 )
      v16 = v7 ^ v4;
    else
      v16 = v7;
    *v13 = v16 | v14 & 3;
    v17 = *(_QWORD *)(v6 + 16);
    v18 = v17 & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v18 )
      v18 ^= v6;
    if ( (__int64 *)v18 != a2 )
      RtlpRbReportFatalError(v18, a2, v6);
    if ( (a1[1] & 1) != 0 )
      v19 = v7 ^ v6;
    else
      v19 = v7;
    v20 = v7 ^ v6;
    *(_QWORD *)(v6 + 16) = v19 | v17 & 3;
    v4 = *(_QWORD *)(v7 + 8);
    if ( (a1[1] & 1) != 0 && v4 )
    {
      v4 ^= v7;
    }
    else if ( (a1[1] & 1) == 0 )
    {
      v20 = v6;
    }
    *(_QWORD *)(v7 + 8) = v20;
    v21 = *(_QWORD *)(v7 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v21 )
      v21 ^= v7;
    if ( v21 != v8 && (v21 || v8 != v7) )
      RtlpRbReportFatalError(v21, v8, v7);
    v22 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
    v23 = *(_BYTE *)(v7 + 16);
    if ( (a1[1] & 1) != 0 && v22 )
    {
      v22 ^= (unsigned __int64)a2;
    }
    else if ( (a1[1] & 1) == 0 )
    {
      goto LABEL_52;
    }
    if ( v22 )
      v22 ^= v7;
LABEL_52:
    *(_QWORD *)(v7 + 16) &= 3uLL;
    *(_QWORD *)(v7 + 16) |= v22;
    *(_BYTE *)(v7 + 16) ^= (*((_BYTE *)a2 + 16) ^ *(_BYTE *)(v7 + 16)) & 1;
    v24 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v24 )
    {
      v27 = a1[1] & 1;
      if ( v27 )
        v24 ^= (unsigned __int64)a2;
      v28 = *(_QWORD *)(v24 + 8);
      if ( v27 && v28 )
        v29 = (__int64 *)(v28 ^ v24);
      else
        v29 = *(__int64 **)(v24 + 8);
      v26 = 0;
      if ( v29 == a2 )
        v26 = 8;
      v30 = (unsigned __int64 *)(v26 + v24);
      if ( v27 && *v30 )
        v31 = (__int64 *)(*v30 ^ v24);
      else
        v31 = (__int64 *)*v30;
      if ( v31 != a2 )
        RtlpRbReportFatalError(v31, a2, v24);
      if ( (a1[1] & 1) != 0 )
        v32 = v7 ^ v24;
      else
        v32 = v7;
      *v30 = v32;
      goto LABEL_125;
    }
    v25 = *a1;
    if ( (a1[1] & 1) != 0 )
    {
      if ( !v25 )
        goto LABEL_57;
      v25 ^= (unsigned __int64)a1;
    }
    if ( (__int64 *)v25 == a2 )
    {
      v26 = v7;
      if ( (a1[1] & 1) != 0 )
        v26 = (unsigned __int64)a1 ^ v7;
      *a1 = v26;
      goto LABEL_125;
    }
LABEL_57:
    RtlpRbReportFatalError(v25, a2, a1);
  }
  v6 = v4;
LABEL_81:
  v8 = a2[2] & 0xFFFFFFFFFFFFFFFCuLL;
  LOBYTE(v26) = v2 & 1;
  if ( (_BYTE)v26 )
  {
    if ( !v8 )
      goto LABEL_85;
    v8 ^= (unsigned __int64)a2;
  }
  if ( !v8 )
  {
LABEL_85:
    if ( v4 )
      *(_QWORD *)(v4 + 16) = 0;
    v33 = *a1;
    if ( (a1[1] & 1) != 0 )
    {
      if ( !v33 )
        goto LABEL_91;
      v33 ^= (unsigned __int64)a1;
    }
    if ( (__int64 *)v33 == a2 )
    {
      if ( (a1[1] & 1) != 0 )
      {
        v34 = (unsigned __int64)a1 ^ v4;
        v26 = -v4;
        a1[1] = ((unsigned __int64)a1 ^ v4) & -(__int64)(v4 != 0);
        *((_BYTE *)a1 + 8) |= 1u;
      }
      else
      {
        a1[1] = v4;
        v34 = (unsigned __int64)a1 ^ v6;
      }
      if ( (a1[1] & 1) != 0 )
        v4 = v34 & -(__int64)(v4 != 0);
      *a1 = v4;
      return v26;
    }
LABEL_91:
    RtlpRbReportFatalError(v33, a2, a1);
  }
  v35 = *(_QWORD *)(v8 + 8);
  v7 = (unsigned __int64)a2;
  if ( (_BYTE)v26 && v35 )
    v36 = (__int64 *)(v35 ^ v8);
  else
    v36 = *(__int64 **)(v8 + 8);
  if ( v36 == a2 )
  {
    v112 = 1;
  }
  else
  {
    if ( (_BYTE)v26 && *(_QWORD *)v8 )
      v37 = (__int64 *)(*(_QWORD *)v8 ^ v8);
    else
      v37 = *(__int64 **)v8;
    if ( v37 != a2 )
      RtlpRbReportFatalError(v37, a2, v8);
    v112 = 0;
    v38 = a1[1];
    if ( (v38 & 1) != 0 )
    {
      if ( v38 == 1 )
        goto LABEL_124;
      v26 = v38 ^ ((unsigned __int64)a1 | 1);
    }
    else
    {
      v26 = a1[1];
    }
    if ( (__int64 *)v26 == a2 )
    {
      LOBYTE(v26) = a1[1] & 1;
      if ( v4 )
      {
        if ( !(_BYTE)v26 )
        {
          a1[1] = v4;
          goto LABEL_124;
        }
        v39 = v4;
      }
      else
      {
        if ( !(_BYTE)v26 )
        {
          a1[1] = v8;
          goto LABEL_124;
        }
        v39 = v8;
      }
      v26 = (unsigned __int64)a1 ^ v39;
      a1[1] = v26;
      *((_BYTE *)a1 + 8) |= 1u;
    }
  }
LABEL_124:
  v23 = *((_BYTE *)a2 + 16);
LABEL_125:
  if ( (a1[1] & 1) != 0 && v4 )
    v40 = v4 ^ v8;
  else
    v40 = v4;
  v41 = v112;
  *(_QWORD *)(v8 + 8LL * v112) = v40;
  if ( v4 )
  {
    v42 = *(_QWORD *)(v4 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v42 )
      v42 ^= v4;
    if ( v42 != v7 )
      RtlpRbReportFatalError(v42, v7, v4);
    if ( (a1[1] & 1) != 0 && v8 )
      v8 ^= v4;
    *(_QWORD *)(v4 + 16) = v8;
    return v26;
  }
  if ( (v23 & 1) != 0 )
    return v26;
  while ( 1 )
  {
    v43 = *((_BYTE *)a1 + 8);
    v44 = v41 ^ 1LL;
    v45 = v41;
    v114 = v41;
    v115 = v44;
    v46 = *(_QWORD *)(v8 + 8 * v44);
    if ( (v43 & 1) != 0 && v46 )
      v46 ^= v8;
    v47 = (_QWORD *)(v46 + 16);
    if ( (*(_BYTE *)(v46 + 16) & 1) != 0 )
    {
      v48 = *a1;
      if ( (a1[1] & 1) != 0 && v48 )
        v48 ^= (unsigned __int64)a1;
      v113 = v48;
      v49 = *v47 & 0xFFFFFFFFFFFFFFFCuLL;
      v50 = v43 & 1;
      if ( (v43 & 1) != 0 && v49 )
        v51 = v49 ^ v46;
      else
        v51 = *v47 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v51 != v8 )
        RtlpRbReportFatalError(v51, v8, v46);
      v52 = *(_QWORD *)(v8 + 8 * v44);
      if ( v50 && v52 )
        v52 ^= v8;
      if ( v52 != v46 )
        RtlpRbReportFatalError(v52, v46, v8);
      v53 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v50 )
      {
        if ( !v53 )
          goto LABEL_162;
        v53 ^= v8;
      }
      if ( v53 )
      {
        v54 = *(_QWORD *)(v53 + 8);
        if ( v50 && v54 )
          v55 = v54 ^ v53;
        else
          v55 = *(_QWORD *)(v53 + 8);
        if ( v55 == v8 )
        {
          if ( v50 )
            v56 = v46 ^ v53;
          else
            v56 = v46;
          *(_QWORD *)(v53 + 8) = v56;
        }
        else
        {
          if ( v50 && *(_QWORD *)v53 )
            v57 = *(_QWORD *)v53 ^ v53;
          else
            v57 = *(_QWORD *)v53;
          if ( v57 != v8 )
            RtlpRbReportFatalError(v57, v8, v53);
          if ( v50 )
            v58 = v46 ^ v53;
          else
            v58 = v46;
          *(_QWORD *)v53 = v58;
        }
        goto LABEL_184;
      }
LABEL_162:
      if ( v113 != v8 )
        RtlpRbReportFatalError(v113, v8, &v113);
      v113 = v46;
LABEL_184:
      if ( v50 && v53 )
        v53 ^= v46;
      *v47 &= 3uLL;
      *v47 |= v53;
      v45 = v114;
      v59 = (unsigned __int64 *)(v46 + 8 * v114);
      if ( v50 && *v59 )
        v60 = *v59 ^ v46;
      else
        v60 = *v59;
      if ( v60 )
      {
        v61 = *(_QWORD *)(v60 + 16);
        v62 = v61 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v50 && v62 )
          v63 = v62 ^ v60;
        else
          v63 = *(_QWORD *)(v60 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
        if ( v63 != v46 )
          RtlpRbReportFatalError(v63, v46, v60);
        if ( v50 )
          v64 = v8 ^ v60;
        else
          v64 = v8;
        *(_QWORD *)(v60 + 16) = v64 | v61 & 3;
      }
      if ( v50 && v60 )
        v60 ^= v8;
      *(_QWORD *)(v8 + 8 * v44) = v60;
      if ( v50 )
      {
        v46 ^= v8;
        *v59 = v46;
      }
      else
      {
        *v59 = v8;
      }
      *(_QWORD *)(v8 + 16) &= 3uLL;
      v65 = a1;
      *(_QWORD *)(v8 + 16) |= v46;
      v66 = v113;
      if ( (a1[1] & 1) != 0 )
      {
        v66 = (v113 ^ (unsigned __int64)a1) & -(__int64)(v113 != 0);
        v65 = a1;
      }
      *v65 = v66;
      *(_BYTE *)v47 &= ~1u;
      *(_BYTE *)(v8 + 16) |= 1u;
      v43 = *((_BYTE *)a1 + 8);
      v46 = *(_QWORD *)(v8 + 8 * v44);
      if ( (v43 & 1) != 0 && v46 )
        v46 ^= v8;
      v41 = v112;
    }
    v67 = *(_QWORD *)v46;
    v68 = v43;
    v69 = v43 & 1;
    if ( *(_QWORD *)v46 )
    {
      if ( v69 )
        v67 ^= v46;
      if ( (*(_BYTE *)(v67 + 16) & 1) != 0 )
        break;
    }
    v70 = *(_QWORD *)(v46 + 8);
    if ( v70 )
    {
      if ( v69 )
        v70 ^= v46;
      if ( (*(_BYTE *)(v70 + 16) & 1) != 0 )
        break;
    }
    v71 = *(_BYTE *)(v8 + 16);
    if ( (v71 & 1) != 0 )
    {
      LOBYTE(v26) = v71 & 0xFE;
      *(_BYTE *)(v8 + 16) = v26;
      *(_BYTE *)(v46 + 16) |= 1u;
      return v26;
    }
    *(_BYTE *)(v46 + 16) |= 1u;
    v26 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 )
    {
      if ( !v26 )
        return v26;
      v26 ^= v8;
    }
    if ( !v26 )
      return v26;
    v72 = *(_QWORD *)(v26 + 8);
    if ( (a1[1] & 1) != 0 && v72 )
      v73 = v72 ^ v26;
    else
      v73 = *(_QWORD *)(v26 + 8);
    v11 = v73 == v8;
    v8 = v26;
    v41 = v11;
    v112 = v11;
  }
  v74 = *(_QWORD *)(v46 + 8 * v44);
  v75 = v68 & 1;
  if ( v75 )
  {
    if ( v74 )
    {
      v74 ^= v46;
      goto LABEL_235;
    }
LABEL_237:
    v76 = *(_QWORD *)(v46 + 8 * v45);
    if ( v75 && v76 )
      v76 ^= v46;
    *(_BYTE *)(v76 + 16) &= ~1u;
    v77 = v41 ^ 1;
    v78 = *(_QWORD *)(v76 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    v79 = a1[1] & 1;
    if ( (a1[1] & 1) != 0 && v78 )
      v80 = v78 ^ v76;
    else
      v80 = *(_QWORD *)(v76 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( v80 != v46 )
      RtlpRbReportFatalError(v80, v46, v76);
    v81 = (unsigned int)v77 ^ 1LL;
    v82 = (unsigned int)v77;
    v83 = *(_QWORD *)(v46 + 8 * v81);
    if ( (a1[1] & 1) != 0 && v83 )
      v83 ^= v46;
    if ( v83 != v76 )
      RtlpRbReportFatalError(v83, v76, v46);
    v84 = *(_QWORD *)(v8 + 8 * v77);
    if ( (a1[1] & 1) != 0 && v84 )
      v84 ^= v8;
    if ( v84 != v46 )
      RtlpRbReportFatalError(v84, v46, v8);
    v85 = *(_QWORD *)(v46 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
    if ( (a1[1] & 1) != 0 && v85 )
      v85 ^= v46;
    if ( v85 != v8 )
      RtlpRbReportFatalError(v85, v8, v46);
    if ( (a1[1] & 1) != 0 )
    {
      v86 = v8 ^ v76;
      *(_QWORD *)(v8 + 8 * v77) = v8 ^ v76;
      if ( v8 )
        goto LABEL_266;
    }
    else
    {
      *(_QWORD *)(v8 + 8 * v77) = v76;
    }
    v86 = v8;
LABEL_266:
    *(_QWORD *)(v76 + 16) &= 3uLL;
    *(_QWORD *)(v76 + 16) |= v86;
    v87 = *(_QWORD *)(v76 + 8 * v77);
    if ( v79 && v87 )
      v88 = v87 ^ v76;
    else
      v88 = *(_QWORD *)(v76 + 8 * v77);
    if ( v88 )
    {
      v89 = *(_QWORD *)(v88 + 16);
      v90 = v89 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v79 && v90 )
        v91 = v90 ^ v88;
      else
        v91 = *(_QWORD *)(v88 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v91 != v76 )
        RtlpRbReportFatalError(v91, v76, v88);
      if ( v79 )
        v92 = v46 ^ v88;
      else
        v92 = v46;
      *(_QWORD *)(v88 + 16) = v92 | v89 & 3;
    }
    if ( v79 && v88 )
      v88 ^= v46;
    *(_QWORD *)(v46 + 8 * v81) = v88;
    v93 = v76;
    if ( v79 )
    {
      v93 = v46 ^ v76;
      *(_QWORD *)(v76 + 8 * v82) = v46 ^ v76;
    }
    else
    {
      *(_QWORD *)(v76 + 8 * v82) = v46;
    }
    *(_QWORD *)(v46 + 16) &= 3uLL;
    v74 = v46;
    *(_QWORD *)(v46 + 16) |= v93;
    v46 = v76;
    v44 = v115;
  }
  else
  {
LABEL_235:
    if ( !v74 || (*(_BYTE *)(v74 + 16) & 1) == 0 )
      goto LABEL_237;
  }
  *(_BYTE *)(v46 + 16) ^= (*(_BYTE *)(v8 + 16) ^ *(_BYTE *)(v46 + 16)) & 1;
  *(_BYTE *)(v8 + 16) &= ~1u;
  *(_BYTE *)(v74 + 16) &= ~1u;
  v94 = *a1;
  if ( (a1[1] & 1) != 0 && v94 )
    v94 ^= (unsigned __int64)a1;
  v95 = *((_BYTE *)a1 + 8);
  v113 = v94;
  v96 = *(_QWORD *)(v46 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
  v97 = v95 & 1;
  if ( v97 && v96 )
    v96 ^= v46;
  if ( v96 != v8 )
    RtlpRbReportFatalError(v96, v8, v46);
  v98 = *(_QWORD *)(v8 + 8 * v44);
  if ( v97 && v98 )
    v98 ^= v8;
  if ( v98 != v46 )
    RtlpRbReportFatalError(v98, v46, v8);
  v99 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v97 )
  {
    if ( v99 )
    {
      v99 ^= v8;
      goto LABEL_304;
    }
LABEL_305:
    if ( v113 != v8 )
      RtlpRbReportFatalError(v113, v8, &v113);
    v113 = v46;
  }
  else
  {
LABEL_304:
    if ( !v99 )
      goto LABEL_305;
    v100 = *(_QWORD *)(v99 + 8);
    if ( v97 && v100 )
      v101 = v100 ^ v99;
    else
      v101 = *(_QWORD *)(v99 + 8);
    if ( v101 == v8 )
    {
      if ( v97 )
        v102 = v46 ^ v99;
      else
        v102 = v46;
      *(_QWORD *)(v99 + 8) = v102;
    }
    else
    {
      if ( v97 && *(_QWORD *)v99 )
        v103 = *(_QWORD *)v99 ^ v99;
      else
        v103 = *(_QWORD *)v99;
      if ( v103 != v8 )
        RtlpRbReportFatalError(v103, v8, v99);
      if ( v97 )
        v104 = v46 ^ v99;
      else
        v104 = v46;
      *(_QWORD *)v99 = v104;
    }
  }
  if ( v97 && v99 )
    v99 ^= v46;
  *(_QWORD *)(v46 + 16) &= 3uLL;
  *(_QWORD *)(v46 + 16) |= v99;
  v105 = (unsigned __int64 *)(v46 + 8 * v114);
  v106 = *v105;
  if ( v97 )
  {
    if ( v106 )
    {
      v106 ^= v46;
      goto LABEL_333;
    }
  }
  else
  {
LABEL_333:
    if ( v106 )
    {
      v107 = *(_QWORD *)(v106 + 16);
      v108 = v107 & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v97 && v108 )
        v109 = v108 ^ v106;
      else
        v109 = *(_QWORD *)(v106 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v109 != v46 )
        RtlpRbReportFatalError(v109, v46, v106);
      if ( v97 )
        v110 = v8 ^ v106;
      else
        v110 = v8;
      *(_QWORD *)(v106 + 16) = v110 | v107 & 3;
    }
  }
  if ( v97 && v106 )
    v106 ^= v8;
  *(_QWORD *)(v8 + 8 * v44) = v106;
  if ( v97 )
  {
    v46 ^= v8;
    *v105 = v46;
  }
  else
  {
    *v105 = v8;
  }
  *(_QWORD *)(v8 + 16) &= 3uLL;
  *(_QWORD *)(v8 + 16) |= v46;
  v26 = v113;
  if ( (a1[1] & 1) != 0 )
    v26 = (v113 ^ (unsigned __int64)a1) & -(__int64)(v113 != 0);
  *a1 = v26;
  return v26;
}

```

## disassembly

```asm
0x14002cd04  push    rbx
0x14002cd06  push    rbp
0x14002cd07  push    rsi
0x14002cd08  push    rdi
0x14002cd09  push    r12
0x14002cd0b  push    r13
0x14002cd0d  push    r14
0x14002cd0f  push    r15
0x14002cd11  sub     rsp, 28h
0x14002cd15  movzx   eax, byte ptr [rcx+8]
0x14002cd19  mov     rsi, rcx
0x14002cd1c  mov     rbx, [rdx]
0x14002cd1f  mov     ecx, eax
0x14002cd21  mov     [rsp+68h+arg_8], 0
0x14002cd2a  mov     rbp, rdx
0x14002cd2d  and     ecx, 1
0x14002cd30  jz      short loc_14002CD3A
0x14002cd32  test    rbx, rbx
0x14002cd35  jz      short loc_14002CD3A
0x14002cd37  xor     rbx, rdx
0x14002cd3a  mov     r14, [rdx+8]
0x14002cd3e  test    ecx, ecx
0x14002cd40  jz      short loc_14002CD4A
0x14002cd42  test    r14, r14
0x14002cd45  jz      short loc_14002CD4A
0x14002cd47  xor     r14, rbp
0x14002cd4a  test    rbx, rbx
0x14002cd4d  jnz     short loc_14002CD57
0x14002cd4f  mov     rbx, r14
0x14002cd52  jmp     loc_14002CF83
0x14002cd57  test    r14, r14
0x14002cd5a  jz      loc_14002CF80
0x14002cd60  mov     ecx, 1
0x14002cd65  mov     r15, r14
0x14002cd68  mov     [rsp+68h+arg_0], ecx
0x14002cd6c  mov     rdi, r14
0x14002cd6f  mov     rcx, [r14]
0x14002cd72  and     al, 1
0x14002cd74  test    rcx, rcx
0x14002cd77  jz      short loc_14002CD98
0x14002cd79  mov     rdi, r15
0x14002cd7c  test    al, al
0x14002cd7e  jz      short loc_14002CD8A
0x14002cd80  test    rcx, rcx
0x14002cd83  jz      short loc_14002CD8A
0x14002cd85  xor     r15, rcx
0x14002cd88  jmp     short loc_14002CD8D
0x14002cd8a  mov     r15, rcx
0x14002cd8d  xor     ecx, ecx
0x14002cd8f  mov     [rsp+68h+arg_0], ecx
0x14002cd93  mov     rcx, [r15]
0x14002cd96  jmp     short loc_14002CD74
0x14002cd98  test    al, al
0x14002cd9a  mov     rax, rbx
0x14002cd9d  jz      short loc_14002CDA2
0x14002cd9f  xor     rax, r15
0x14002cda2  mov     [r15], rax
0x14002cda5  lea     r12, [rbx+10h]
0x14002cda9  mov     rax, [r12]
0x14002cdad  mov     rcx, rax
0x14002cdb0  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14002cdb4  test    byte ptr [rsi+8], 1
0x14002cdb8  jz      short loc_14002CDC2
0x14002cdba  test    rcx, rcx
0x14002cdbd  jz      short loc_14002CDC2
0x14002cdbf  xor     rcx, rbx
0x14002cdc2  cmp     rcx, rbp
0x14002cdc5  jz      short loc_14002CDD3
0x14002cdc7  mov     r8, rbx
0x14002cdca  call    RtlpRbReportFatalError
0x14002cdcf  mov     rax, [r12]
0x14002cdd3  test    byte ptr [rsi+8], 1
0x14002cdd7  jz      short loc_14002CDDE
0x14002cdd9  xor     rbx, r15
0x14002cddc  jmp     short loc_14002CDE1
0x14002cdde  mov     rbx, r15
0x14002cde1  and     eax, 3
0x14002cde4  or      rax, rbx
0x14002cde7  mov     [r12], rax
0x14002cdeb  mov     rdx, [r14+10h]
0x14002cdef  mov     rcx, rdx
0x14002cdf2  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14002cdf6  test    byte ptr [rsi+8], 1
0x14002cdfa  jz      short loc_14002CE04
0x14002cdfc  test    rcx, rcx
0x14002cdff  jz      short loc_14002CE04
0x14002ce01  xor     rcx, r14
0x14002ce04  cmp     rcx, rbp
0x14002ce07  jz      short loc_14002CE18
0x14002ce09  mov     r8, r14
0x14002ce0c  mov     rdx, rbp
0x14002ce0f  call    RtlpRbReportFatalError
0x14002ce14  mov     rdx, [r14+10h]
0x14002ce18  test    byte ptr [rsi+8], 1
0x14002ce1c  jz      short loc_14002CE29
0x14002ce1e  mov     rax, r14
0x14002ce21  xor     rax, r15
0x14002ce24  mov     rcx, rax
0x14002ce27  jmp     short loc_14002CE32
0x14002ce29  mov     rcx, r14
0x14002ce2c  mov     rax, r15
0x14002ce2f  xor     rcx, r15
0x14002ce32  and     edx, 3
0x14002ce35  or      rdx, rax
0x14002ce38  mov     [r14+10h], rdx
0x14002ce3c  mov     al, [rsi+8]
0x14002ce3f  mov     rbx, [r15+8]
0x14002ce43  and     al, 1
0x14002ce45  jz      short loc_14002CE51
0x14002ce47  test    rbx, rbx
0x14002ce4a  jz      short loc_14002CE51
0x14002ce4c  xor     rbx, r15
0x14002ce4f  jmp     short loc_14002CE58
0x14002ce51  test    al, al
0x14002ce53  jnz     short loc_14002CE58
0x14002ce55  mov     rcx, r14
0x14002ce58  mov     [r15+8], rcx
0x14002ce5c  mov     rcx, [r15+10h]
0x14002ce60  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14002ce64  test    byte ptr [rsi+8], 1
0x14002ce68  jz      short loc_14002CE72
0x14002ce6a  test    rcx, rcx
0x14002ce6d  jz      short loc_14002CE72
0x14002ce6f  xor     rcx, r15
0x14002ce72  cmp     rcx, rdi
0x14002ce75  jz      short loc_14002CE8C
0x14002ce77  test    rcx, rcx
0x14002ce7a  jnz     short loc_14002CE81
0x14002ce7c  cmp     rdi, r15
0x14002ce7f  jz      short loc_14002CE8C
0x14002ce81  mov     r8, r15
0x14002ce84  mov     rdx, rdi
0x14002ce87  call    RtlpRbReportFatalError
0x14002ce8c  mov     rax, [rbp+10h]
0x14002ce90  mov     cl, [rsi+8]
0x14002ce93  and     rax, 0FFFFFFFFFFFFFFFCh
0x14002ce97  mov     r13b, [r15+10h]
0x14002ce9b  and     cl, 1
0x14002ce9e  jz      short loc_14002CEAA
0x14002cea0  test    rax, rax
0x14002cea3  jz      short loc_14002CEAA
0x14002cea5  xor     rax, rbp
0x14002cea8  jmp     short loc_14002CEAE
0x14002ceaa  test    cl, cl
0x14002ceac  jz      short loc_14002CEB6
0x14002ceae  test    rax, rax
0x14002ceb1  jz      short loc_14002CEB6
0x14002ceb3  xor     rax, r15
0x14002ceb6  and     qword ptr [r15+10h], 3
0x14002cebb  or      [r15+10h], rax
0x14002cebf  mov     al, [r15+10h]
0x14002cec3  xor     al, [rbp+10h]
0x14002cec6  and     al, 1
0x14002cec8  xor     [r15+10h], al
0x14002cecc  mov     r14, [rbp+10h]
0x14002ced0  and     r14, 0FFFFFFFFFFFFFFFCh
0x14002ced4  jnz     short loc_14002CF0D
0x14002ced6  test    byte ptr [rsi+8], 1
0x14002ceda  mov     rcx, [rsi]
0x14002cedd  jz      short loc_14002CEE7
0x14002cedf  test    rcx, rcx
0x14002cee2  jz      short loc_14002CF0B
0x14002cee4  xor     rcx, rsi
0x14002cee7  cmp     rcx, rbp
0x14002ceea  jz      short loc_14002CEF7
0x14002ceec  mov     r8, rsi
0x14002ceef  mov     rdx, rbp
0x14002cef2  call    RtlpRbReportFatalError
0x14002cef7  test    byte ptr [rsi+8], 1
0x14002cefb  mov     rax, r15
0x14002cefe  jz      short loc_14002CF03
0x14002cf00  xor     rax, rsi
0x14002cf03  mov     [rsi], rax
0x14002cf06  jmp     loc_14002D0B7
0x14002cf0b  jmp     short loc_14002CEEC
0x14002cf0d  mov     dl, [rsi+8]
0x14002cf10  and     dl, 1
0x14002cf13  jz      short loc_14002CF18
0x14002cf15  xor     r14, rbp
0x14002cf18  mov     rax, [r14+8]
0x14002cf1c  test    dl, dl
0x14002cf1e  jz      short loc_14002CF2D
0x14002cf20  test    rax, rax
0x14002cf23  jz      short loc_14002CF2D
0x14002cf25  mov     rcx, r14
0x14002cf28  xor     rcx, rax
0x14002cf2b  jmp     short loc_14002CF30
0x14002cf2d  mov     rcx, rax
0x14002cf30  xor     eax, eax
0x14002cf32  cmp     rcx, rbp
0x14002cf35  lea     r8d, [rax+8]
0x14002cf39  cmovz   eax, r8d
0x14002cf3d  lea     r12, [rax+r14]
0x14002cf41  test    dl, dl
0x14002cf43  jz      short loc_14002CF55
0x14002cf45  cmp     qword ptr [r12], 0
0x14002cf4a  jz      short loc_14002CF55
0x14002cf4c  mov     rcx, r14
0x14002cf4f  xor     rcx, [r12]
0x14002cf53  jmp     short loc_14002CF59
0x14002cf55  mov     rcx, [r12]
0x14002cf59  cmp     rcx, rbp
0x14002cf5c  jz      short loc_14002CF69
0x14002cf5e  mov     r8, r14
0x14002cf61  mov     rdx, rbp
0x14002cf64  call    RtlpRbReportFatalError
0x14002cf69  test    byte ptr [rsi+8], 1
0x14002cf6d  jz      short loc_14002CF74
0x14002cf6f  xor     r14, r15
0x14002cf72  jmp     short loc_14002CF77
0x14002cf74  mov     r14, r15
0x14002cf77  mov     [r12], r14
0x14002cf7b  jmp     loc_14002D0B7
0x14002cf80  mov     r14, rbx
0x14002cf83  mov     rdi, [rdx+10h]
0x14002cf87  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14002cf8b  and     al, 1
0x14002cf8d  jz      short loc_14002CF97
0x14002cf8f  test    rdi, rdi
0x14002cf92  jz      short loc_14002CF9C
0x14002cf94  xor     rdi, rbp
0x14002cf97  test    rdi, rdi
0x14002cf9a  jnz     short loc_14002D009
0x14002cf9c  test    rbx, rbx
0x14002cf9f  jz      short loc_14002CFA9
0x14002cfa1  mov     qword ptr [rbx+10h], 0
0x14002cfa9  test    byte ptr [rsi+8], 1
0x14002cfad  mov     rcx, [rsi]
0x14002cfb0  jz      short loc_14002CFBA
0x14002cfb2  test    rcx, rcx
0x14002cfb5  jz      short loc_14002CFE9
0x14002cfb7  xor     rcx, rsi
0x14002cfba  cmp     rcx, rbp
0x14002cfbd  jz      short loc_14002CFC7
0x14002cfbf  mov     r8, rsi
0x14002cfc2  call    RtlpRbReportFatalError
0x14002cfc7  test    byte ptr [rsi+8], 1
0x14002cfcb  jz      short loc_14002CFEB
0x14002cfcd  mov     r14, rbx
0x14002cfd0  mov     rax, rbx
0x14002cfd3  xor     r14, rsi
0x14002cfd6  neg     rax
0x14002cfd9  sbb     rcx, rcx
0x14002cfdc  and     rcx, r14
0x14002cfdf  mov     [rsi+8], rcx
0x14002cfe3  or      byte ptr [rsi+8], 1
0x14002cfe7  jmp     short loc_14002CFF2
0x14002cfe9  jmp     short loc_14002CFBF
0x14002cfeb  mov     [rsi+8], rbx
0x14002cfef  xor     r14, rsi
0x14002cff2  test    byte ptr [rsi+8], 1
0x14002cff6  jz      short loc_14002D001
0x14002cff8  neg     rbx
0x14002cffb  sbb     rbx, rbx
0x14002cffe  and     rbx, r14
0x14002d001  mov     [rsi], rbx
0x14002d004  jmp     loc_14002D79A
0x14002d009  mov     rdx, [rdi+8]
0x14002d00d  mov     r15, rbp
0x14002d010  test    al, al
0x14002d012  jz      short loc_14002D021
0x14002d014  test    rdx, rdx
0x14002d017  jz      short loc_14002D021
0x14002d019  mov     rcx, rdi
0x14002d01c  xor     rcx, rdx
0x14002d01f  jmp     short loc_14002D024
0x14002d021  mov     rcx, rdx
0x14002d024  cmp     rcx, rbp
0x14002d027  jnz     short loc_14002D034
0x14002d029  mov     ecx, 1
0x14002d02e  mov     [rsp+68h+arg_0], ecx
0x14002d032  jmp     short loc_14002D0B3
0x14002d034  test    al, al
0x14002d036  jz      short loc_14002D046
0x14002d038  cmp     qword ptr [rdi], 0
0x14002d03c  jz      short loc_14002D046
0x14002d03e  mov     rcx, rdi
0x14002d041  xor     rcx, [rdi]
0x14002d044  jmp     short loc_14002D049
0x14002d046  mov     rcx, [rdi]
0x14002d049  cmp     rcx, rbp
0x14002d04c  jz      short loc_14002D059
0x14002d04e  mov     r8, rdi
0x14002d051  mov     rdx, rbp
0x14002d054  call    RtlpRbReportFatalError
0x14002d059  xor     ecx, ecx
0x14002d05b  mov     [rsp+68h+arg_0], ecx
0x14002d05f  mov     rcx, [rsi+8]
0x14002d063  test    cl, 1
0x14002d066  jz      short loc_14002D07A
0x14002d068  cmp     rcx, 1
0x14002d06c  jz      short loc_14002D0B3
0x14002d06e  mov     rax, rsi
0x14002d071  or      rax, 1
0x14002d075  xor     rax, rcx
0x14002d078  jmp     short loc_14002D07D
0x14002d07a  mov     rax, rcx
0x14002d07d  cmp     rax, rbp
0x14002d080  jnz     short loc_14002D0B3
0x14002d082  mov     al, [rsi+8]
  ... truncated ...
```
