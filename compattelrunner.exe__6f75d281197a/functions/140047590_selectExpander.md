# selectExpander

- ea: `0x140047590`
- end: `0x140048097`
- name: `selectExpander`
- size: `2823`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x14002b178`
- `0x140045f58`
- `0x140047590`
- `0x140051aec`
- `0x140053fec`
- `0x140054178`
- `0x1400560c4`
- `0x140056260`
- `0x140059c88`
- `0x14005fb28`
- `0x14005fbf8`
- `0x14006280c`
- `0x140062bfc`
- `0x140062e80`
- `0x140063d48`
- `0x14006a268`
- `0x14006ec20`
- `0x14006f654`
- `0x1400702ec`
- `0x140080048`
- `0x140097310`

## string_xrefs

- `0x140047812`: `access to view "%s" prohibited`

## pseudocode

```c
__int64 __fastcall selectExpander(__int64 **a1, __int64 a2)
{
  __int64 *v2; // r14
  unsigned __int16 v3; // ax
  __int64 v4; // r13
  __int64 v6; // rsi
  _DWORD *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // r12d
  _DWORD *v13; // rdi
  __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 TableItem; // rax
  const char **v22; // rsi
  unsigned int v23; // eax
  char v24; // al
  const char *v25; // rax
  __int16 v26; // bx
  int v27; // eax
  _DWORD *v28; // r12
  __int64 v29; // r8
  int v30; // ecx
  __int64 v31; // rdx
  const char *v32; // rdx
  int *v33; // r15
  int v34; // eax
  __int64 v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // r8
  const char *v38; // r11
  __int64 v39; // rax
  int *v40; // rax
  _DWORD *v41; // r10
  __int64 v42; // r9
  _DWORD *v43; // rdi
  const char *v44; // rax
  __int64 v45; // rbx
  int v46; // eax
  int v47; // ecx
  const char *v48; // r12
  int v49; // edi
  const char *v50; // rsi
  __int64 v51; // rax
  int *v52; // rax
  __int64 v53; // rbx
  __int64 v54; // rax
  int v55; // ecx
  const char *v56; // rdx
  __int64 v57; // rbx
  int matched; // eax
  __int64 v59; // rcx
  const char *v60; // r12
  int v61; // eax
  __int64 v62; // rsi
  int i; // ebx
  __int64 v64; // rcx
  __int64 v65; // rdi
  __int64 v66; // rbx
  __int64 v67; // rdx
  __int64 *j; // rcx
  __int64 v69; // rax
  int *v70; // rax
  __int64 v71; // rbx
  int v72; // esi
  __int64 v73; // rax
  int v74; // eax
  int v75; // eax
  __int64 v76; // rax
  _DWORD *v77; // rcx
  __int64 v78; // [rsp+30h] [rbp-C8h]
  unsigned int v79; // [rsp+38h] [rbp-C0h]
  _DWORD *v80; // [rsp+40h] [rbp-B8h]
  int v81; // [rsp+48h] [rbp-B0h]
  _DWORD *v82; // [rsp+50h] [rbp-A8h]
  int v83; // [rsp+58h] [rbp-A0h]
  int v84; // [rsp+5Ch] [rbp-9Ch]
  const char *v85; // [rsp+60h] [rbp-98h]
  const char *v86; // [rsp+68h] [rbp-90h]
  const char *v87; // [rsp+70h] [rbp-88h]
  __int64 v88; // [rsp+78h] [rbp-80h]
  int v89; // [rsp+80h] [rbp-78h]
  const char *v90; // [rsp+88h] [rbp-70h]
  _DWORD *v91; // [rsp+90h] [rbp-68h]
  const char *v92; // [rsp+98h] [rbp-60h]
  _DWORD *v93; // [rsp+A0h] [rbp-58h]
  __int64 v94; // [rsp+A8h] [rbp-50h]
  unsigned __int8 v95; // [rsp+100h] [rbp+8h]
  int v96; // [rsp+100h] [rbp+8h]
  unsigned __int16 v98; // [rsp+110h] [rbp+18h]
  int v99; // [rsp+118h] [rbp+20h]

  v2 = *a1;
  v3 = *(_WORD *)(a2 + 4);
  v4 = a2;
  v98 = v3;
  v6 = **a1;
  *(_DWORD *)(a2 + 4) |= 0x40u;
  v78 = v6;
  if ( *(_BYTE *)(v6 + 103) )
    return 2;
  if ( (v3 & 0x40) != 0 )
    return 1;
  if ( *((_WORD *)a1 + 18) )
    *(_DWORD *)(a2 + 16) = ++*((_DWORD *)v2 + 35);
  v8 = *(_DWORD **)(a2 + 40);
  v80 = v8;
  v91 = *(_DWORD **)(a2 + 32);
  if ( v2[50] && (*(_DWORD *)(a2 + 4) & 0x200000) != 0 )
  {
    v9 = *(_QWORD *)(a2 + 104);
    if ( !v9 )
    {
      v9 = sqlite3DbMallocZero(v6, 64);
      *(_QWORD *)(v4 + 104) = v9;
      if ( !v9 )
        return 2;
    }
    *(_DWORD *)(v9 + 4) = 1;
  }
  v10 = *(_QWORD *)(v4 + 104);
  if ( v10 && !*((_DWORD *)v2 + 12) )
  {
    *(_QWORD *)(v10 + 8) = v2[50];
    v2[50] = v10;
  }
  sqlite3SrcListAssignCursors(v2, v8);
  v12 = v11;
  v13 = v8 + 2;
  v93 = v8 + 2;
  if ( *v8 > (int)v11 )
  {
    while ( 1 )
    {
      if ( *((_QWORD *)v13 + 4) != v11 )
        goto LABEL_52;
      if ( *((_QWORD *)v13 + 2) == v11 )
        break;
      v20 = resolveFromTermToCte(v2, a1, v13);
      v11 = 0;
      if ( !v20 )
      {
        TableItem = sqlite3LocateTableItem(v2, 0, v13);
        v11 = 0;
        *((_QWORD *)v13 + 4) = TableItem;
        v22 = (const char **)TableItem;
        if ( !TableItem )
          return 2;
        v23 = *(_DWORD *)(TableItem + 44);
        if ( v23 >= 0xFFFF )
        {
          sqlite3ErrorMsg(v2, "too many references to \"%s\": max 65535", *v22);
          *((_QWORD *)v13 + 4) = 0;
          return 2;
        }
        *((_DWORD *)v22 + 11) = v23 + 1;
        v24 = *((_BYTE *)v22 + 63);
        if ( v24 != 1 && (v13[16] & 4) != 0 )
        {
          sqlite3ErrorMsg(v2, "'%s' is not a function", *((const char **)v13 + 2));
          return 2;
        }
        if ( !v24 )
          goto LABEL_50;
        v95 = *((_BYTE *)a1 + 36);
        if ( (v24 == 1 || *((__int16 *)v22 + 27) <= 0) && (unsigned int)viewGetColumnNames(v2, v22) )
          return 2;
        if ( *((_BYTE *)v22 + 63) == 2 )
        {
          if ( (*(_DWORD *)(v78 + 48) & 0x80000000) == 0 && v22[12] != *(const char **)(*(_QWORD *)(v78 + 32) + 56LL) )
            sqlite3ErrorMsg(v2, "access to view \"%s\" prohibited", *v22);
          *((_QWORD *)v13 + 5) = sqlite3SelectDup(v78, v22[8], 0);
        }
        else if ( *((_BYTE *)v22 + 63) == 1 && *((char *)v13 + 64) < 0 )
        {
          v25 = v22[10];
          if ( v25 )
          {
            if ( *((unsigned __int8 *)v25 + 30) > ((*(_DWORD *)(v78 + 48) >> 7) & 1u) )
              sqlite3ErrorMsg(v2, "unsafe use of virtual table \"%s\"", *v22);
          }
        }
        v26 = *((_WORD *)v22 + 27);
        *((_WORD *)v22 + 27) = -1;
        *((_WORD *)a1 + 18) = 1;
        sqlite3WalkSelect(a1, *((_QWORD *)v13 + 5));
        v11 = 0;
        *((_WORD *)a1 + 18) = v95;
        *((_WORD *)v22 + 27) = v26;
        goto LABEL_49;
      }
      if ( v20 > 1 )
        return 2;
LABEL_50:
      if ( (v13[16] & 2) != 0 )
      {
        v27 = sqlite3IndexedByLookup(v2, v13, 0);
        v11 = 0;
        if ( v27 )
          return 2;
      }
LABEL_52:
      if ( ++v12 >= *v8 )
      {
        v6 = v78;
        goto LABEL_57;
      }
      v13 += 26;
    }
    if ( (unsigned int)sqlite3WalkSelect(a1, *((_QWORD *)v13 + 5)) )
      return 2;
    v14 = *((_QWORD *)v13 + 5);
    v15 = sqlite3DbMallocZero(*v2, 104);
    *((_QWORD *)v13 + 4) = v15;
    v16 = v15;
    if ( !v15 )
      return 2;
    *(_DWORD *)(v15 + 44) = 1;
    v17 = *((_QWORD *)v13 + 3);
    v18 = *v2;
    v19 = v17 ? sqlite3DbStrDup(v18, v17) : sqlite3MPrintf(v18, "%!S", v13);
    *(_QWORD *)v16 = v19;
    while ( *(_QWORD *)(v14 + 80) )
      v14 = *(_QWORD *)(v14 + 80);
    sqlite3ColumnsFromExprList(v2, *(_QWORD *)(v14 + 32), v16 + 54, v16 + 8);
    *(_DWORD *)(v16 + 48) |= 0x4200u;
    v11 = 0;
    *(_WORD *)(v16 + 52) = -1;
    *(_WORD *)(v16 + 58) = 200;
    if ( *((_DWORD *)v2 + 12) )
      return 2;
LABEL_49:
    v8 = v80;
    goto LABEL_50;
  }
LABEL_57:
  if ( *((_DWORD *)v2 + 12) != (_DWORD)v11 || (unsigned int)sqlite3ProcessJoin(v2, v4) )
    return 2;
  v28 = v91;
  v29 = 0;
  v79 = 0;
  v30 = 0;
  if ( (int)*v91 <= 0 )
  {
LABEL_64:
    if ( v30 >= *v91 )
      goto LABEL_174;
  }
  else
  {
    while ( 1 )
    {
      v31 = *(_QWORD *)&v91[8 * v30 + 2];
      if ( *(_BYTE *)v31 == 0xB4 || *(_BYTE *)v31 == 0x8D && **(_BYTE **)(v31 + 24) == 0xB4 )
        break;
      v29 = *(_DWORD *)(v31 + 4) | (unsigned int)v29;
      ++v30;
      v79 = v29;
      if ( v30 >= *v91 )
        goto LABEL_64;
    }
  }
  v32 = 0;
  v33 = 0;
  v84 = 0;
  v89 = *(_DWORD *)(*v2 + 48) & 0x44;
  v34 = 0;
  if ( (int)*v91 > 0 )
  {
    do
    {
      v35 = 8LL * v34;
      v36 = *(_QWORD *)&v28[v35 + 2];
      v94 = v36;
      v37 = *(_DWORD *)(v36 + 4) | (unsigned int)v29;
      v79 = v37;
      if ( *(_BYTE *)v36 == 0xB4 )
      {
        v38 = v32;
        v39 = *(_QWORD *)&v28[v35 + 2];
      }
      else
      {
        if ( *(_BYTE *)v36 != 0x8D || **(_BYTE **)(v36 + 24) != 0xB4 )
        {
          v40 = (int *)sqlite3ExprListAppend(v2, v33, v36);
          v32 = 0;
          v33 = v40;
          if ( v40 )
          {
            *(_QWORD *)&v40[8 * *v40 - 4] = *(_QWORD *)&v28[v35 + 4];
            v40[8 * *v40 - 1] ^= (v28[v35 + 7] ^ v40[8 * *v40 - 1]) & 3;
            *(_QWORD *)&v28[v35 + 4] = 0;
          }
          *(_QWORD *)&v28[v35 + 2] = 0;
          goto LABEL_172;
        }
        v38 = *(const char **)(*(_QWORD *)(v36 + 16) + 8LL);
        v39 = *(_QWORD *)(v36 + 24);
      }
      v41 = v80;
      v42 = (unsigned int)v32;
      v43 = v93;
      v85 = v38;
      v81 = (int)v32;
      v83 = *(_DWORD *)(v39 + 52);
      v96 = (int)v32;
      v82 = v93;
      if ( *v80 <= (int)v32 )
        goto LABEL_167;
      do
      {
        v44 = (const char *)*((_QWORD *)v43 + 3);
        v45 = *((_QWORD *)v43 + 4);
        v88 = v45;
        v87 = v44;
        if ( !v44 )
        {
          v44 = *(const char **)v45;
          v87 = *(const char **)v45;
        }
        if ( *(_BYTE *)(v6 + 103) != (_BYTE)v32 )
          break;
        if ( (v43[16] & 0x2000) != 0 )
        {
          v86 = v32;
          v90 = *(const char **)(*((_QWORD *)v43 + 5) + 32LL);
          goto LABEL_90;
        }
        if ( v38 )
        {
          v46 = sqlite3StrICmp(v38, v44);
          LODWORD(v42) = v96;
          v32 = 0;
          v41 = v80;
          if ( v46 )
            goto LABEL_165;
        }
        v90 = v32;
        v32 = *(const char **)(v45 + 96);
        if ( v32 )
        {
          v37 = *(_QWORD *)(v6 + 32);
          v47 = 0;
          if ( *(const char **)(v37 + 24) == v32 )
          {
            v32 = 0;
LABEL_88:
            _mm_lfence();
            v86 = *(const char **)(32LL * v47 + *(_QWORD *)(v6 + 32));
            goto LABEL_90;
          }
          do
            ++v47;
          while ( *(const char **)(32LL * v47 + v37 + 24) != v32 );
          v32 = 0;
          if ( v47 >= 0 )
            goto LABEL_88;
        }
        v86 = "*";
LABEL_90:
        if ( (int)v42 + 1 < *v41 && (v43[42] & 0x400) != 0 && (v98 & 0x800) != 0 )
        {
          v48 = (const char *)*((_QWORD *)v43 + 22);
          v49 = (int)v32;
          v92 = v48;
          if ( *(_DWORD *)v48 > (int)v32 )
          {
            do
            {
              v50 = *(const char **)&v48[16 * v49 + 8];
              v51 = sqlite3Expr(v78, 59, v50);
              if ( v51 && (*(_BYTE *)(v51 + 4) & 3) == 0 )
                *(_DWORD *)(v51 + 52) = v83;
              v52 = (int *)sqlite3ExprListAppend(v2, v33, v51);
              v32 = 0;
              v33 = v52;
              if ( v52 )
              {
                v53 = 8 * (*v52 - 1LL);
                v54 = sqlite3MPrintf(v78, "..%s", v50);
                v33[v53 + 7] &= ~1u;
                v33[v53 + 7] |= 0x82u;
                v32 = 0;
                *(_QWORD *)&v33[v53 + 4] = v54;
              }
              ++v49;
            }
            while ( v49 < *(_DWORD *)v48 );
            v4 = a2;
            v6 = v78;
            v45 = v88;
            LODWORD(v42) = v96;
            v41 = v80;
          }
          v43 = v82;
        }
        else
        {
          v92 = v32;
        }
        v55 = (int)v32;
        v99 = (int)v32;
        if ( (__int16)v32 < *(__int16 *)(v45 + 54) )
        {
          while ( 1 )
          {
            v56 = v85;
            v57 = v55;
            if ( !v85 || !v90 )
              goto LABEL_107;
            matched = sqlite3MatchEName(&v90[32 * v55 + 8], 0, v85, 0);
            v32 = 0;
            if ( matched )
              break;
LABEL_162:
            v55 = v99 + 1;
            v43 = v82;
            v99 = v55;
            if ( v55 >= *(__int16 *)(v88 + 54) )
              goto LABEL_163;
          }
          v56 = v85;
LABEL_107:
          v59 = *(_QWORD *)(v88 + 8);
          if ( (*(_DWORD *)(v4 + 4) & 0x20000) == 0 && (*(_BYTE *)(v59 + 24 * v57 + 18) & 2) != 0 )
            goto LABEL_161;
          v37 = v98;
          if ( (*(_WORD *)(v59 + 24 * v57 + 18) & 0x400) != 0 && !v56 && (v98 & 0x800) == 0 )
            goto LABEL_161;
          v60 = *(const char **)(v59 + 24 * v57);
          v81 = 1;
          if ( v96 > 0 && !v56 && (v98 & 0x800) == 0 && (v43[16] & 0x400) != 0 )
          {
            v61 = sqlite3IdListIndex(*((_QWORD *)v43 + 9), v60);
            v32 = 0;
            if ( v61 >= 0 )
              goto LABEL_162;
          }
          v62 = sqlite3Expr(v6, 59, v60);
          if ( (int)*v80 <= 1 )
          {
LABEL_128:
            if ( *((_BYTE *)v2 + 300) >= 2u )
              goto LABEL_129;
            v65 = v78;
          }
          else
          {
            if ( (v43[15] & 0x40) != 0 && (v98 & 0x800) == 0 )
            {
              for ( i = *v80 + ~v96; i > 0; --i )
              {
                v43 += 26;
                if ( (v43[16] & 0x400) != 0 )
                {
                  v64 = *((_QWORD *)v43 + 9);
                  if ( v64 )
                  {
                    if ( (int)sqlite3IdListIndex(v64, v60) >= 0 )
                      goto LABEL_128;
                  }
                }
              }
            }
LABEL_129:
            v65 = v78;
            v66 = sqlite3Expr(v78, 59, v87);
            v62 = sqlite3PExpr(v2, 141, v66);
            if ( *((_BYTE *)v2 + 300) >= 2u )
            {
              v67 = *(_QWORD *)(v94 + 16);
              if ( v67 )
              {
                for ( j = (__int64 *)v2[51]; j; j = (__int64 *)j[3] )
                {
                  if ( *j == v67 )
                  {
                    *j = v66;
                    break;
                  }
                }
              }
            }
            if ( v86 )
            {
              v69 = sqlite3Expr(v78, 59, v86);
              v62 = sqlite3PExpr(v2, 141, v69);
            }
          }
          if ( v62 && (*(_BYTE *)(v62 + 4) & 3) == 0 )
            *(_DWORD *)(v62 + 52) = v83;
          v70 = (int *)sqlite3ExprListAppend(v2, v33, v62);
          v32 = 0;
          v33 = v70;
          if ( !v70 )
          {
LABEL_163:
            v43 = v82;
            LODWORD(v42) = v96;
            v41 = v80;
            goto LABEL_164;
          }
          v71 = 8LL * *v70;
          if ( (v98 & 0x800) == 0 || *((_BYTE *)v2 + 300) >= 2u )
          {
            v6 = v78;
            if ( v89 == 4 )
              v76 = sqlite3MPrintf(v78, "%s.%s", v87, v60);
            else
              v76 = sqlite3DbStrDup(v78, v60);
            v33[v71 - 1] &= 0xFFFFFFFC;
            *(_QWORD *)&v33[v71 - 4] = v76;
LABEL_161:
            v32 = 0;
            goto LABEL_162;
          }
          if ( v90 )
          {
            v72 = v99;
            v73 = sqlite3DbStrDup(v65, *(_QWORD *)&v90[32 * v99 + 16]);
          }
          else
          {
            v73 = sqlite3MPrintf(v65, "%s.%s.%s", v86, v87, v60);
            v72 = v99;
          }
          *(_QWORD *)&v33[v71 - 4] = v73;
          v33[v71 - 1] &= ~1u;
          v33[v71 - 1] |= 2u;
          if ( (v82[16] & 0x400) == 0 )
          {
            v32 = 0;
            goto LABEL_153;
          }
          v74 = sqlite3IdListIndex(*((_QWORD *)v82 + 9), v60);
          v32 = 0;
          if ( v74 >= 0 )
          {
LABEL_156:
            v33[v71 - 1] |= 0x100u;
          }
          else
          {
LABEL_153:
            if ( v92 )
            {
              v75 = sqlite3IdListIndex(v92, v60);
              v32 = 0;
              if ( v75 >= 0 )
                goto LABEL_156;
            }
            v37 = 1024;
            if ( (*(_WORD *)(*(_QWORD *)(v88 + 8) + 24LL * v72 + 18) & 0x400) != 0 )
              goto LABEL_156;
          }
          v6 = v78;
          goto LABEL_162;
        }
LABEL_164:
        v38 = v85;
LABEL_165:
        v6 = v78;
        v42 = (unsigned int)(v42 + 1);
        v43 += 26;
        v96 = v42;
        v82 = v43;
      }
      while ( (int)v42 < *v41 );
      v28 = v91;
      if ( !v81 )
      {
LABEL_167:
        if ( v38 )
          sqlite3ErrorMsg(v2, "no such table: %s", v38);
        else
          sqlite3ErrorMsg(v2, "no tables specified", v37, v42);
        v32 = 0;
      }
LABEL_172:
      LODWORD(v29) = v79;
      v34 = v84 + 1;
      v84 = v34;
    }
    while ( v34 < *v28 );
  }
  exprListDeleteNN(v6, v28);
  v29 = v79;
  *(_QWORD *)(v4 + 32) = v33;
LABEL_174:
  v77 = *(_DWORD **)(v4 + 32);
  if ( v77 )
  {
    if ( *v77 > *(_DWORD *)(v6 + 144) )
    {
      sqlite3ErrorMsg(v2, "too many columns in result set", v29);
      return 2;
    }
    if ( (v29 & 0x400008) != 0 )
      *(_DWORD *)(v4 + 4) |= 0x40000u;
  }
  return 0;
}

```

## disassembly

```asm
0x140047590  mov     [rsp+arg_8], rdx
0x140047595  push    rbx
0x140047596  push    rbp
0x140047597  push    rsi
0x140047598  push    rdi
0x140047599  push    r12
0x14004759b  push    r13
0x14004759d  push    r14
0x14004759f  push    r15
0x1400475a1  sub     rsp, 0B8h
0x1400475a8  mov     r14, [rcx]
0x1400475ab  xor     r8d, r8d
0x1400475ae  movzx   eax, word ptr [rdx+4]
0x1400475b2  mov     r13, rdx
0x1400475b5  mov     r15, rcx
0x1400475b8  mov     [rsp+0F8h+arg_10], ax
0x1400475c0  mov     rsi, [r14]
0x1400475c3  or      dword ptr [rdx+4], 40h
0x1400475c7  mov     [rsp+0F8h+var_C8], rsi
0x1400475cc  cmp     [rsi+67h], r8b
0x1400475d0  jnz     loc_140047742
0x1400475d6  test    al, 40h
0x1400475d8  jz      short loc_1400475E3
0x1400475da  lea     eax, [r8+1]
0x1400475de  jmp     loc_140047747
0x1400475e3  mov     ebp, 1
0x1400475e8  cmp     [rcx+24h], r8w
0x1400475ed  jz      short loc_140047600
0x1400475ef  add     [r14+8Ch], ebp
0x1400475f6  mov     eax, [r14+8Ch]
0x1400475fd  mov     [rdx+10h], eax
0x140047600  mov     rbx, [rdx+28h]
0x140047604  mov     rax, [rdx+20h]
0x140047608  mov     [rsp+0F8h+var_B8], rbx
0x14004760d  mov     [rsp+0F8h+var_68], rax
0x140047615  cmp     [r14+190h], r8
0x14004761c  jz      short loc_14004764E
0x14004761e  test    dword ptr [rdx+4], 200000h
0x140047625  jz      short loc_14004764E
0x140047627  mov     rax, [rdx+68h]
0x14004762b  test    rax, rax
0x14004762e  jnz     short loc_14004764B
0x140047630  lea     edx, [rax+40h]
0x140047633  mov     rcx, rsi
0x140047636  call    sqlite3DbMallocZero
0x14004763b  xor     r8d, r8d
0x14004763e  mov     [r13+68h], rax
0x140047642  test    rax, rax
0x140047645  jz      loc_140047742
0x14004764b  mov     [rax+4], ebp
0x14004764e  mov     rcx, [r13+68h]
0x140047652  test    rcx, rcx
0x140047655  jz      short loc_14004766F
0x140047657  cmp     [r14+30h], r8d
0x14004765b  jnz     short loc_14004766F
0x14004765d  mov     rax, [r14+190h]
0x140047664  mov     [rcx+8], rax
0x140047668  mov     [r14+190h], rcx
0x14004766f  mov     rdx, rbx
0x140047672  mov     rcx, r14
0x140047675  call    sqlite3SrcListAssignCursors
0x14004767a  lea     rax, [rbx+8]
0x14004767e  mov     r12d, r8d
0x140047681  mov     rdi, rax
0x140047684  mov     [rsp+0F8h+var_58], rax
0x14004768c  cmp     [rbx], r8d
0x14004768f  jle     loc_140047910
0x140047695  cmp     [rdi+20h], r8
0x140047699  jnz     loc_1400478C3
0x14004769f  cmp     [rdi+10h], r8
0x1400476a3  jnz     loc_14004775B
0x1400476a9  mov     rdx, [rdi+28h]
0x1400476ad  mov     rcx, r15
0x1400476b0  call    sqlite3WalkSelect
0x1400476b5  test    eax, eax
0x1400476b7  jnz     loc_140047742
0x1400476bd  mov     rcx, [r14]
0x1400476c0  lea     edx, [rax+68h]
0x1400476c3  mov     rsi, [rdi+28h]
0x1400476c7  call    sqlite3DbMallocZero
0x1400476cc  mov     [rdi+20h], rax
0x1400476d0  mov     rbx, rax
0x1400476d3  test    rax, rax
0x1400476d6  jz      short loc_140047742
0x1400476d8  mov     [rax+2Ch], ebp
0x1400476db  mov     rdx, [rdi+18h]
0x1400476df  mov     rcx, [r14]
0x1400476e2  test    rdx, rdx
0x1400476e5  jz      short loc_1400476EE
0x1400476e7  call    sqlite3DbStrDup
0x1400476ec  jmp     short loc_1400476FD
0x1400476ee  mov     r8, rdi
0x1400476f1  lea     rdx, aS_3; "%!S"
0x1400476f8  call    sqlite3MPrintf
0x1400476fd  mov     [rbx], rax
0x140047700  xor     eax, eax
0x140047702  jmp     short loc_140047708
0x140047704  mov     rsi, [rsi+50h]
0x140047708  cmp     [rsi+50h], rax
0x14004770c  jnz     short loc_140047704
0x14004770e  mov     rdx, [rsi+20h]
0x140047712  lea     r9, [rbx+8]
0x140047716  lea     r8, [rbx+36h]
0x14004771a  mov     rcx, r14
0x14004771d  call    sqlite3ColumnsFromExprList
0x140047722  or      dword ptr [rbx+30h], 4200h
0x140047729  xor     r8d, r8d
0x14004772c  mov     word ptr [rbx+34h], 0FFFFh
0x140047732  mov     word ptr [rbx+3Ah], 0C8h
0x140047738  cmp     [r14+30h], r8d
0x14004773c  jz      loc_1400478A2
0x140047742  mov     eax, 2
0x140047747  add     rsp, 0B8h
0x14004774e  pop     r15
0x140047750  pop     r14
0x140047752  pop     r13
0x140047754  pop     r12
0x140047756  pop     rdi
0x140047757  pop     rsi
0x140047758  pop     rbp
0x140047759  pop     rbx
0x14004775a  retn
0x14004775b  mov     r8, rdi
0x14004775e  mov     rdx, r15
0x140047761  mov     rcx, r14
0x140047764  call    resolveFromTermToCte
0x140047769  xor     r8d, r8d
0x14004776c  test    eax, eax
0x14004776e  jz      short loc_140047779
0x140047770  cmp     eax, ebp
0x140047772  jg      short loc_140047742
0x140047774  jmp     loc_1400478A7
0x140047779  mov     r8, rdi
0x14004777c  xor     edx, edx
0x14004777e  mov     rcx, r14
0x140047781  call    sqlite3LocateTableItem
0x140047786  xor     r8d, r8d
0x140047789  mov     [rdi+20h], rax
0x14004778d  mov     rsi, rax
0x140047790  test    rax, rax
0x140047793  jz      short loc_140047742
0x140047795  mov     eax, [rax+2Ch]
0x140047798  cmp     eax, 0FFFFh
0x14004779d  jnb     loc_1400478EC
0x1400477a3  inc     eax
0x1400477a5  mov     [rsi+2Ch], eax
0x1400477a8  mov     al, [rsi+3Fh]
0x1400477ab  cmp     al, bpl
0x1400477ae  jz      short loc_1400477BA
0x1400477b0  test    byte ptr [rdi+40h], 4
0x1400477b4  jnz     loc_1400478D4
0x1400477ba  test    al, al
0x1400477bc  jz      loc_1400478A7
0x1400477c2  mov     cl, [r15+24h]
0x1400477c6  mov     byte ptr [rsp+0F8h+arg_0], cl
0x1400477cd  cmp     al, bpl
0x1400477d0  jz      short loc_1400477D9
0x1400477d2  cmp     [rsi+36h], r8w
0x1400477d7  jg      short loc_1400477EC
0x1400477d9  mov     rdx, rsi
0x1400477dc  mov     rcx, r14
0x1400477df  call    viewGetColumnNames
0x1400477e4  test    eax, eax
0x1400477e6  jnz     loc_140047742
0x1400477ec  cmp     byte ptr [rsi+3Fh], 2
0x1400477f0  jnz     short loc_140047836
0x1400477f2  mov     rbx, [rsp+0F8h+var_C8]
0x1400477f7  mov     eax, [rbx+30h]
0x1400477fa  bt      rax, 1Fh
0x1400477ff  jb      short loc_140047821
0x140047801  mov     rax, [rbx+20h]
0x140047805  mov     rcx, [rax+38h]
0x140047809  cmp     [rsi+60h], rcx
0x14004780d  jz      short loc_140047821
0x14004780f  mov     r8, [rsi]
0x140047812  lea     rdx, aAccessToViewSP; "access to view \"%s\" prohibited"
0x140047819  mov     rcx, r14
0x14004781c  call    sqlite3ErrorMsg
0x140047821  mov     rdx, [rsi+40h]
0x140047825  xor     r8d, r8d
0x140047828  mov     rcx, rbx
0x14004782b  call    sqlite3SelectDup
0x140047830  mov     [rdi+28h], rax
0x140047834  jmp     short loc_140047873
0x140047836  cmp     [rsi+3Fh], bpl
0x14004783a  jnz     short loc_140047873
0x14004783c  test    byte ptr [rdi+40h], 80h
0x140047840  jz      short loc_140047873
0x140047842  mov     rax, [rsi+50h]
0x140047846  test    rax, rax
0x140047849  jz      short loc_140047873
0x14004784b  mov     rcx, [rsp+0F8h+var_C8]
0x140047850  movzx   eax, byte ptr [rax+1Eh]
0x140047854  mov     ecx, [rcx+30h]
0x140047857  shr     rcx, 7
0x14004785b  and     ecx, ebp
0x14004785d  cmp     eax, ecx
0x14004785f  jbe     short loc_140047873
0x140047861  mov     r8, [rsi]
0x140047864  lea     rdx, aUnsafeUseOfVir; "unsafe use of virtual table \"%s\""
0x14004786b  mov     rcx, r14
0x14004786e  call    sqlite3ErrorMsg
0x140047873  movzx   ebx, word ptr [rsi+36h]
0x140047877  mov     rcx, r15
0x14004787a  mov     word ptr [rsi+36h], 0FFFFh
0x140047880  mov     [r15+24h], bp
0x140047885  mov     rdx, [rdi+28h]
0x140047889  call    sqlite3WalkSelect
0x14004788e  movzx   eax, byte ptr [rsp+0F8h+arg_0]
0x140047896  xor     r8d, r8d
0x140047899  mov     [r15+24h], ax
0x14004789e  mov     [rsi+36h], bx
0x1400478a2  mov     rbx, [rsp+0F8h+var_B8]
0x1400478a7  test    byte ptr [rdi+40h], 2
0x1400478ab  jz      short loc_1400478C3
0x1400478ad  mov     rdx, rdi
0x1400478b0  mov     rcx, r14
0x1400478b3  call    sqlite3IndexedByLookup
0x1400478b8  xor     r8d, r8d
0x1400478bb  test    eax, eax
0x1400478bd  jnz     loc_140047742
0x1400478c3  add     r12d, ebp
0x1400478c6  cmp     r12d, [rbx]
0x1400478c9  jge     short loc_14004790B
0x1400478cb  add     rdi, 68h ; 'h'
0x1400478cf  jmp     loc_140047695
0x1400478d4  mov     r8, [rdi+10h]
0x1400478d8  lea     rdx, aSIsNotAFunctio; "'%s' is not a function"
0x1400478df  mov     rcx, r14
0x1400478e2  call    sqlite3ErrorMsg
0x1400478e7  jmp     loc_140047742
0x1400478ec  mov     r8, [rsi]
0x1400478ef  lea     rdx, aTooManyReferen; "too many references to \"%s\": max 6553"...
0x1400478f6  mov     rcx, r14
0x1400478f9  call    sqlite3ErrorMsg
0x1400478fe  mov     qword ptr [rdi+20h], 0
0x140047906  jmp     loc_140047742
0x14004790b  mov     rsi, [rsp+0F8h+var_C8]
0x140047910  cmp     [r14+30h], r8d
0x140047914  jnz     loc_140047742
0x14004791a  mov     rdx, r13
0x14004791d  mov     rcx, r14
0x140047920  call    sqlite3ProcessJoin
0x140047925  xor     edx, edx
0x140047927  test    eax, eax
0x140047929  jnz     loc_140047742
0x14004792f  mov     r12, [rsp+0F8h+var_68]
0x140047937  mov     r8d, edx
0x14004793a  mov     [rsp+0F8h+var_C0], edx
0x14004793e  mov     ecx, edx
0x140047940  cmp     [r12], edx
0x140047944  jle     short loc_140047975
0x140047946  mov     eax, ecx
0x140047948  shl     rax, 5
0x14004794c  mov     rdx, [rax+r12+8]
0x140047951  cmp     byte ptr [rdx], 0B4h
0x140047954  jz      short loc_14004797F
0x140047956  cmp     byte ptr [rdx], 8Dh
0x140047959  jnz     short loc_140047964
0x14004795b  mov     rax, [rdx+18h]
0x14004795f  cmp     byte ptr [rax], 0B4h
0x140047962  jz      short loc_14004797F
0x140047964  or      r8d, [rdx+4]
0x140047968  add     ecx, ebp
0x14004796a  mov     [rsp+0F8h+var_C0], r8d
0x14004796f  cmp     ecx, [r12]
0x140047973  jl      short loc_140047946
0x140047975  cmp     ecx, [r12]
0x140047979  jge     loc_14004805A
0x14004797f  mov     rax, [r14]
0x140047982  xor     edx, edx
0x140047984  mov     r15d, edx
0x140047987  mov     [rsp+0F8h+var_9C], edx
0x14004798b  mov     eax, [rax+30h]
0x14004798e  and     eax, 44h
0x140047991  mov     [rsp+0F8h+var_78], eax
0x140047998  mov     eax, edx
0x14004799a  cmp     [r12], edx
0x14004799e  jle     loc_140048046
0x1400479a4  movsxd  rbx, eax
0x1400479a7  shl     rbx, 5
0x1400479ab  mov     rcx, [rbx+r12+8]
0x1400479b0  mov     [rsp+0F8h+var_50], rcx
0x1400479b8  or      r8d, [rcx+4]
0x1400479bc  cmp     byte ptr [rcx], 0B4h
0x1400479bf  mov     [rsp+0F8h+var_C0], r8d
0x1400479c4  jz      short loc_140047A33
0x1400479c6  cmp     byte ptr [rcx], 8Dh
0x1400479c9  jnz     short loc_1400479E2
0x1400479cb  mov     rax, [rcx+18h]
0x1400479cf  cmp     byte ptr [rax], 0B4h
0x1400479d2  jnz     short loc_1400479E2
0x1400479d4  mov     rax, [rcx+10h]
0x1400479d8  mov     r11, [rax+8]
0x1400479dc  mov     rax, [rcx+18h]
0x1400479e0  jmp     short loc_140047A39
0x1400479e2  mov     r8, rcx
0x1400479e5  mov     rdx, r15
0x1400479e8  mov     rcx, r14
0x1400479eb  call    sqlite3ExprListAppend
  ... truncated ...
```
