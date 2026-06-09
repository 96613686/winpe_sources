# CCommand::DeriveFromStmt(_GUID const *,wchar_t const *,unsigned __int64,unsigned __int64,PARAMINFO *,int *,unsigned __int64,unsigned __int64 *)

- ea: `0x1800d6570`
- end: `0x1800d84a2`
- name: `?DeriveFromStmt@CCommand@@QEAAJPEBU_GUID@@PEB_W_K2PEAUPARAMINFO@@PEAH2PEA_K@Z`
- size: `7986`
- prototype: `int(CCommand *__hidden this, const struct _GUID *, const wchar_t *, unsigned __int64, unsigned __int64, struct PARAMINFO *, int *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800d84b0`

## callees

- `0x180003030`
- `0x180003d80`
- `0x180005910`
- `0x180009340`
- `0x180009700`
- `0x180009de0`
- `0x180010400`
- `0x1800290c0`
- `0x1800296c0`
- `0x18002a2a0`
- `0x18002ad90`
- `0x1800845d0`
- `0x180085120`
- `0x180089230`
- `0x1800d47a0`
- `0x1800d6570`
- `0x1800d8dc0`
- `0x1800dd210`
- `0x1800de280`
- `0x1800e01f0`
- `0x1800e07d0`
- `0x1800e09b0`
- `0x1801a6628`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800d7354`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800d7354`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d66ca`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d66eb`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d670c`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6729`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6752`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d677f`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d68ee`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d69bf`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6a33`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6d5f`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6dc2`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6e2e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d66ca`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d66eb`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d670c`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6729`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6752`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d677f`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d68ee`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d69bf`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6a33`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6d5f`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6dc2`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800d6e2e`
- `api-ms-win-crt-string-l1-1-0!towlower` at `0x1800d679a`
- `api-ms-win-crt-string-l1-1-0!towlower` at `0x1800d679a`

## string_xrefs

- `0x1800d6722`: `delete`
- `0x1800d66c3`: `update`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CCommand::DeriveFromStmt(
        CDBConnection **this,
        const struct _GUID *a2,
        wchar_t *a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        struct PARAMINFO *a6,
        int *a7,
        unsigned __int64 a8,
        unsigned __int64 *a9)
{
  CCommand *v9; // r13
  wchar_t *v10; // rbx
  unsigned __int64 v11; // r15
  _WORD *v12; // r12
  __int64 v13; // r14
  __int64 v14; // rdi
  size_t v15; // rax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // r14
  wint_t v18; // r13
  const wchar_t *v19; // rdi
  unsigned __int64 v20; // r15
  unsigned int LexToken; // eax
  unsigned __int64 v22; // rdx
  wchar_t v23; // cx
  int v24; // ebx
  unsigned int v25; // eax
  unsigned __int16 v26; // r14
  int v27; // r15d
  __int64 v28; // rdx
  int v29; // ebx
  size_t v30; // rcx
  unsigned int i; // eax
  size_t v32; // r9
  const wchar_t *v33; // r12
  wchar_t *v34; // rsi
  unsigned __int64 v35; // r15
  unsigned int v36; // edi
  unsigned __int64 v37; // rsi
  const wchar_t *v38; // rbx
  const wchar_t *v39; // rbx
  unsigned __int64 v40; // r15
  __int64 v41; // rbx
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // r13
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rbx
  __int64 v47; // rdx
  wchar_t *v48; // rax
  unsigned __int64 v49; // rdx
  wchar_t *v50; // rcx
  char *v51; // r9
  wchar_t v52; // ax
  unsigned __int64 v53; // rbx
  const wchar_t *v54; // r12
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // rsi
  size_t v57; // rcx
  size_t v58; // r14
  unsigned int v59; // eax
  int v60; // eax
  const wchar_t *v61; // rbx
  unsigned __int64 v62; // rbx
  int v63; // r14d
  int v64; // edi
  wchar_t *v65; // rsi
  CCommand *v66; // r12
  unsigned __int64 v67; // rax
  wchar_t v68; // ax
  unsigned __int64 v69; // rdx
  _WORD *v70; // rax
  unsigned __int64 v71; // rdx
  __int64 v72; // rsi
  unsigned __int64 v73; // rdx
  unsigned __int64 v74; // rdx
  wchar_t *v75; // rax
  unsigned __int64 v76; // rcx
  unsigned int v77; // ebx
  unsigned __int16 Expression; // ax
  unsigned __int64 v79; // r12
  wchar_t *v80; // rsi
  unsigned __int64 v81; // rax
  unsigned __int64 v82; // r10
  unsigned __int64 v83; // r11
  unsigned __int64 v84; // rdx
  wchar_t *v85; // r15
  wchar_t *v86; // rcx
  unsigned __int64 v87; // r8
  signed __int64 v88; // r9
  wchar_t v89; // ax
  wchar_t *v90; // rax
  unsigned __int64 v91; // rdx
  char *v92; // rcx
  unsigned __int64 v93; // r8
  signed __int64 v94; // r9
  __int16 v95; // ax
  char *v96; // rax
  const wchar_t *v97; // rcx
  unsigned __int64 v98; // r15
  unsigned __int64 j; // rbx
  int v100; // eax
  __int64 v101; // rcx
  __int64 v102; // r14
  unsigned __int64 v103; // rdi
  unsigned __int64 v104; // r14
  unsigned __int64 v105; // r14
  unsigned __int64 v106; // rbx
  wchar_t k; // ax
  unsigned __int64 v108; // rsi
  unsigned __int64 v109; // r11
  __int64 v110; // r10
  unsigned __int64 v111; // r8
  unsigned __int64 v112; // rdx
  wchar_t *v113; // rax
  char *v114; // rcx
  unsigned __int64 v115; // r8
  signed __int64 v116; // r9
  __int16 v117; // ax
  char *v118; // rax
  unsigned __int64 v119; // r8
  unsigned __int64 v120; // rcx
  wchar_t v121; // ax
  unsigned __int64 v122; // r10
  unsigned __int64 v123; // rbx
  unsigned __int64 v124; // r8
  _WORD *v125; // rcx
  unsigned __int64 v126; // rdx
  unsigned __int64 v127; // r8
  char *v128; // r9
  __int16 v129; // ax
  _WORD *v130; // rax
  unsigned __int64 v131; // rbx
  unsigned __int64 v132; // rdx
  wchar_t *v133; // r10
  wchar_t *v134; // rcx
  unsigned __int64 v135; // r8
  signed __int64 v136; // r9
  wchar_t v137; // ax
  wchar_t *v138; // rax
  __int64 v139; // rdx
  int v140; // eax
  const struct _GUID *v141; // r13
  int v142; // eax
  int v143; // eax
  int v144; // eax
  int v145; // eax
  __int64 v146; // rdx
  unsigned __int64 v147; // r14
  unsigned __int64 v148; // r10
  unsigned __int64 v149; // rdx
  wchar_t *v150; // rax
  wchar_t *v151; // rcx
  unsigned __int64 v152; // r8
  char *v153; // r9
  wchar_t v154; // ax
  wchar_t *v155; // rax
  unsigned __int64 v156; // r14
  unsigned __int64 v157; // r10
  wchar_t *v158; // rcx
  unsigned __int64 v159; // r9
  unsigned __int64 v160; // rdx
  signed __int64 v161; // r8
  wchar_t v162; // ax
  wchar_t *v163; // rax
  unsigned __int64 v164; // r14
  unsigned __int64 v165; // rdx
  signed __int64 v166; // r12
  wchar_t v167; // ax
  wchar_t *v168; // rax
  unsigned __int64 v169; // r8
  wchar_t *v170; // r14
  CCommand *v171; // r13
  int MetadataQuery; // eax
  int v173; // eax
  const struct COLINFO *v174; // r14
  unsigned __int64 v175; // rsi
  wchar_t *v176; // r12
  unsigned __int64 v177; // r13
  const wchar_t *v178; // rbx
  unsigned __int64 v179; // r15
  unsigned __int64 v180; // r15
  int v181; // edi
  int v182; // ebx
  unsigned __int64 v183; // r13
  wchar_t *v184; // r12
  wchar_t v185; // ax
  int *v186; // rdi
  struct PARAMINFO *v187; // rdx
  CDBConnection *v188; // rcx
  __int64 v189; // rax
  struct CExtByteBuffer *v190; // rax
  int v191; // eax
  __int64 v193; // r8
  __int64 v194; // rdx
  __int64 v195; // rdx
  int v196; // eax
  CCommand *v197; // rdi
  unsigned __int16 v198; // [rsp+80h] [rbp-80h]
  wchar_t *SubStr; // [rsp+88h] [rbp-78h]
  __int64 v200; // [rsp+90h] [rbp-70h]
  _WORD *v202; // [rsp+A0h] [rbp-60h]
  unsigned int v203; // [rsp+A8h] [rbp-58h]
  int v204; // [rsp+ACh] [rbp-54h]
  unsigned __int64 v205; // [rsp+B0h] [rbp-50h]
  wchar_t *Str; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v208; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v209; // [rsp+C8h] [rbp-38h]
  wchar_t *v210; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *Src; // [rsp+D8h] [rbp-28h]
  const wchar_t *v212; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v213; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t *v214; // [rsp+F0h] [rbp-10h]
  wchar_t v215; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v216; // [rsp+100h] [rbp+0h]
  unsigned __int64 v217; // [rsp+108h] [rbp+8h]
  unsigned __int64 v218; // [rsp+110h] [rbp+10h]
  unsigned __int64 v219; // [rsp+118h] [rbp+18h]
  unsigned __int64 v220; // [rsp+120h] [rbp+20h]
  unsigned __int64 v221; // [rsp+128h] [rbp+28h]
  int *v222; // [rsp+130h] [rbp+30h]
  unsigned __int64 *v223; // [rsp+138h] [rbp+38h]
  struct PARAMINFO *v224; // [rsp+140h] [rbp+40h]
  wchar_t *v225; // [rsp+148h] [rbp+48h]
  __int64 v226; // [rsp+150h] [rbp+50h]
  unsigned __int64 v227; // [rsp+158h] [rbp+58h] BYREF
  size_t MaxCount; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v229; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int64 v230; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int64 v231; // [rsp+178h] [rbp+78h] BYREF
  wchar_t *v232; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v233; // [rsp+188h] [rbp+88h] BYREF
  __int64 v234; // [rsp+190h] [rbp+90h]
  unsigned __int64 v235; // [rsp+198h] [rbp+98h] BYREF

  v217 = a4;
  v225 = a3;
  v9 = (CCommand *)this;
  v224 = a6;
  v222 = a7;
  v223 = a9;
  v227 = 0;
  MaxCount = 0;
  v198 = 0;
  v10 = a3;
  v11 = a4;
  v232 = 0;
  v235 = 0;
  Src = 0;
  v208 = 0;
  v216 = 0;
  v213 = 0;
  v210 = 0;
  v204 = 0;
  v12 = 0;
  v202 = 0;
  v218 = 0;
  v13 = *((_QWORD *)this[55] + 104);
  v226 = v13;
  v14 = 0;
  v200 = 0;
  SubStr = 0;
  Str = 0;
  v219 = 0;
  while ( 1 )
  {
    if ( GetLexToken(v10, v11, &v227, &MaxCount) != 1
      || (*(_BYTE *)(v13 + 9264) < 0xBu || *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 344) + 40LL) + 880LL) == 80)
      && !(unsigned int)FIsStmtKeyword(&v10[v227], MaxCount, *(struct CDataSource **)(*((_QWORD *)v9 + 55) + 832LL)) )
    {
      v26 = -25400;
      if ( (bidGblFlags & 2) != 0 )
      {
        v29 = bidTraceHR(off_1802604F8[0], 4402185, 2147500037LL);
        v27 = -2147467259;
        goto LABEL_447;
      }
      goto LABEL_446;
    }
    v15 = MaxCount;
    if ( MaxCount == 6 )
    {
      if ( !_wcsnicmp(L"update", &v10[v227], 6u)
        || !_wcsnicmp(L"select", &v10[v227], MaxCount)
        || !_wcsnicmp(L"insert", &v10[v227], MaxCount)
        || !_wcsnicmp(L"delete", &v10[v227], MaxCount) )
      {
        goto LABEL_17;
      }
      v15 = MaxCount;
    }
    if ( v15 != 4 )
      goto LABEL_15;
    if ( _wcsnicmp(L"exec", &v10[v227], 4u) )
    {
      v15 = MaxCount;
LABEL_15:
      if ( v15 == 7 && !_wcsnicmp(L"execute", &v10[v227], 7u) )
        goto LABEL_17;
      v26 = -25400;
      if ( (bidGblFlags & 2) != 0 )
      {
        v29 = bidTraceHR(off_1802604F8[0], 4417545, 2147500037LL);
        v27 = -2147467259;
        goto LABEL_447;
      }
LABEL_446:
      v29 = -2147467259;
      v27 = -2147467259;
      goto LABEL_447;
    }
LABEL_17:
    v16 = v227;
LABEL_18:
    v17 = 0;
    v18 = towlower(v10[v16]);
    v215 = v18;
    v19 = &v10[MaxCount + v227];
    v20 = v11 - (MaxCount + v227);
    if ( v18 != 115 || !v20 )
      goto LABEL_48;
LABEL_20:
    LexToken = GetLexToken(v19, v20, &v227, &MaxCount);
    if ( LexToken != 3 )
      goto LABEL_35;
    do
    {
      v22 = v227;
      v23 = v19[v227];
      if ( v23 != 40 )
      {
        if ( v23 == 41 )
        {
          v26 = -25400;
          v27 = -2147467259;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_263;
          v28 = 4501513;
LABEL_30:
          v29 = bidTraceHR(off_1802604F8[0], v28, 2147500037LL);
          v14 = v200;
          goto LABEL_447;
        }
        if ( v19[v227] == 63 )
        {
          v26 = -25400;
          v27 = -2147467259;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_263;
          v28 = 4517897;
          goto LABEL_30;
        }
LABEL_44:
        v30 = MaxCount;
LABEL_45:
        v19 += v30 + v22;
        v20 -= v30 + v22;
        if ( !v20 )
        {
          v26 = -25400;
          v27 = -2147467259;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_263;
          v28 = 4527113;
          goto LABEL_30;
        }
        goto LABEL_20;
      }
      v24 = 1;
      do
      {
        v19 += MaxCount + v22;
        v20 -= MaxCount + v22;
        if ( !v20 )
        {
          v26 = -25400;
          v27 = -2147467259;
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_263;
          v28 = 4453385;
          goto LABEL_30;
        }
        v25 = GetLexToken(v19, v20, &v227, &MaxCount);
        v22 = v227;
        if ( v25 == 3 )
        {
          switch ( v19[v227] )
          {
            case '(':
              ++v24;
              break;
            case ')':
              --v24;
              break;
            case '?':
              v26 = -25400;
              v27 = -2147467259;
              if ( (bidGblFlags & 2) == 0 )
              {
                v29 = -2147467259;
                v14 = v200;
                goto LABEL_447;
              }
              v28 = 4478985;
              goto LABEL_30;
          }
        }
      }
      while ( v24 );
      v19 += MaxCount + v227;
      v20 -= MaxCount + v227;
      LexToken = GetLexToken(v19, v20, &v227, &MaxCount);
    }
    while ( LexToken == 3 );
LABEL_35:
    v22 = v227;
    if ( LexToken != 1 )
      goto LABEL_44;
    v30 = MaxCount;
    if ( MaxCount != 4 )
      goto LABEL_45;
    if ( _wcsnicmp(L"from", &v19[v227], 4u) )
    {
      v22 = v227;
      goto LABEL_44;
    }
LABEL_48:
    i = GetLexToken(v19, v20, &v227, &MaxCount);
    if ( i != 1 )
    {
      if ( i != 3 )
        goto LABEL_66;
      if ( v18 != 101 || v19[v227] != 63 )
        goto LABEL_440;
      v17 = 1;
      v39 = &v19[MaxCount + v227];
      v40 = v20 - (MaxCount + v227);
      GetLexToken(v39, v40, &v227, &MaxCount);
      v19 = &v39[MaxCount + v227];
      v20 = v40 - (MaxCount + v227);
      goto LABEL_65;
    }
    v32 = MaxCount;
    if ( MaxCount != 4 )
      goto LABEL_68;
    if ( v18 == 105 )
    {
      if ( _wcsnicmp(L"into", &v19[v227], MaxCount) )
      {
        v33 = &v19[v227];
        v212 = v33;
        v34 = (wchar_t *)&v19[MaxCount + v227];
        v214 = v34;
        v35 = v20 - MaxCount - v227;
        v231 = v35;
        v36 = GetLexToken(v34, v35, &v227, &MaxCount);
        v203 = v36;
        goto LABEL_77;
      }
LABEL_56:
      v19 += MaxCount + v227;
      v20 -= MaxCount + v227;
      if ( v18 == 115 )
      {
        v230 = v227;
        v231 = MaxCount;
        v37 = v20;
        v227 = 0;
        MaxCount = 0;
        v38 = v19;
        for ( i = GetLexToken(v19, v20, &v230, &v231); i == 3; i = GetLexToken(v38, v37, &v230, &v231) )
        {
          if ( v38[v230] != 40 )
            break;
          v38 += v231 + v230;
          v37 -= v231 + v230;
        }
LABEL_66:
        if ( i == 1 )
        {
LABEL_67:
          v32 = MaxCount;
          goto LABEL_68;
        }
LABEL_440:
        v26 = -25400;
        v27 = -2147467259;
        if ( (bidGblFlags & 2) != 0 )
        {
          v28 = 4598793;
          goto LABEL_30;
        }
LABEL_263:
        v29 = -2147467259;
        v14 = v200;
        goto LABEL_447;
      }
LABEL_65:
      i = GetLexToken(v19, v20, &v227, &MaxCount);
      goto LABEL_66;
    }
    if ( v18 == 115 || v18 == 100 )
    {
      if ( !_wcsnicmp(L"from", &v19[v227], 4u) )
        goto LABEL_56;
      goto LABEL_67;
    }
LABEL_68:
    v33 = &v19[v227];
    v212 = v33;
    v34 = (wchar_t *)&v19[v32 + v227];
    v214 = v34;
    v35 = v20 - (v32 + v227);
    v231 = v35;
    if ( v18 == 101 )
      return CCommand::DeriveFromSProc(
               (CCommand *)this,
               a2,
               &v19[v227],
               v32,
               &v19[v32 + v227],
               v35,
               a5,
               v17,
               v224,
               v223);
    v36 = GetLexToken(v34, v35, &v227, &MaxCount);
    v203 = v36;
    if ( v18 == 115 )
    {
      v41 = 0;
      if ( v35 )
      {
        while ( 2 )
        {
          if ( v36 == 1 )
          {
            if ( !v41 && (unsigned int)FIsEndFromClause(&v34[v227], v35 - v227) )
            {
LABEL_76:
              v214 = v34;
              v203 = v36;
              v231 = v35;
              break;
            }
LABEL_74:
            v42 = v227;
          }
          else
          {
            if ( v36 != 3 )
              goto LABEL_74;
            v42 = v227;
            v68 = v34[v227];
            if ( v68 == 40 )
            {
              ++v41;
            }
            else if ( v68 == 41 )
            {
              --v41;
            }
          }
          v34 += MaxCount + v42;
          v35 -= MaxCount + v42;
          v36 = GetLexToken(v34, v35, &v227, &MaxCount);
          if ( !v35 )
            goto LABEL_76;
          continue;
        }
      }
    }
LABEL_77:
    v43 = v34 - v33;
    v220 = v43;
    if ( IndexWChar(0x3Fu, v33, v43) < v43 )
    {
      v26 = -25400;
      v27 = -2147467259;
      if ( (bidGblFlags & 2) == 0 )
      {
        v29 = -2147467259;
        v14 = v200;
        v12 = v202;
        goto LABEL_447;
      }
      v195 = 4662281;
      goto LABEL_424;
    }
    if ( Src )
      goto LABEL_95;
    v234 = 0;
    v44 = 130 * a5;
    if ( !is_mul_ok(0x82u, a5)
      || (v45 = v44 + v217, v44 + v217 < v44)
      || (v46 = v45 + 13, v216 = v45 + 13, v45 + 13 < v45) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_269;
      v139 = 4674569;
      goto LABEL_268;
    }
    v47 = 2 * v46;
    if ( !is_mul_ok(v46, 2u) )
      v47 = -1;
    v48 = (wchar_t *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(
                       g_pMO,
                       v47);
    Src = v48;
    if ( !v48 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_269;
      v139 = 4682761;
LABEL_268:
      v140 = bidTraceHR(off_1802604F8[0], v139, 2147942414LL);
LABEL_270:
      v141 = a2;
      v29 = CError::PostHResult(g_pCError, v140, a2);
      v14 = v200;
      v12 = v202;
      v26 = v198;
      v27 = -2147467259;
      goto LABEL_448;
    }
    if ( v46 )
    {
      if ( v46 <= 0x7FFFFFFF )
      {
        v49 = v46;
        v50 = v48;
        v51 = (char *)((char *)L"select " - (char *)v48);
        do
        {
          if ( !(v49 + 2147483646 - v46) )
            break;
          v52 = *(_WORD *)&v51[(_QWORD)v50];
          if ( !v52 )
            break;
          *v50++ = v52;
          --v49;
        }
        while ( v49 );
        v48 = v50 - 1;
        if ( v49 )
          v48 = v50;
      }
      *v48 = 0;
    }
    v208 = 7;
LABEL_95:
    v53 = v35;
    v205 = v35;
    v54 = v34;
    v230 = (unsigned __int64)v34;
    v55 = v227;
    v56 = v227;
    v57 = MaxCount;
    v58 = MaxCount;
    if ( !v35 )
    {
LABEL_110:
      LODWORD(v233) = 0;
      v62 = v35;
      v203 = v36;
      v227 = v56;
      MaxCount = v58;
      v63 = 0;
      goto LABEL_111;
    }
    v59 = v203;
    while ( 1 )
    {
      if ( v59 == 1 && v57 == 5 )
      {
        if ( !_wcsnicmp(L"union", &v54[v55], 5u) )
          goto LABEL_120;
        v55 = v227;
        v57 = MaxCount;
      }
      v54 += v57 + v55;
      v230 = (unsigned __int64)v54;
      v53 -= v57 + v55;
      v205 = v53;
      v59 = GetLexToken(v54, v53, &v227, &MaxCount);
      v203 = v59;
      v57 = MaxCount;
      if ( MaxCount != 5 )
      {
        v55 = v227;
        goto LABEL_109;
      }
      v60 = _wcsnicmp(L"union", &v54[v227], 5u);
      v57 = MaxCount;
      v55 = v227;
      if ( !v60 )
        break;
LABEL_108:
      v59 = v203;
LABEL_109:
      if ( !v53 )
        goto LABEL_110;
    }
    v61 = &v54[MaxCount + v227];
    v229 = 0;
    v233 = 0;
    if ( v205 - MaxCount == v227 )
      goto LABEL_107;
    GetLexToken(v61, v205 - MaxCount - v227, &v229, &v233);
    if ( v233 != 3 || _wcsnicmp(L"all", &v61[v229], 3u) )
    {
      v55 = v227;
      v57 = MaxCount;
LABEL_107:
      v53 = v205;
      goto LABEL_108;
    }
    MaxCount += v233 + v229;
    v53 = v205;
LABEL_120:
    if ( !v53 )
      goto LABEL_110;
    v63 = 1;
    LODWORD(v233) = 1;
    v204 = 1;
    v62 = v35 - v205;
    v12 = v202;
    if ( !v202 )
    {
      v218 = 0;
      v69 = 2 * v216;
      if ( !is_mul_ok(v216, 2u) )
        v69 = -1;
      v70 = (_WORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 112LL))(
                       g_pMO,
                       v69);
      v12 = v70;
      v202 = v70;
      if ( !v70 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v142 = bidTraceHR(off_1802604F8[0], 4766729, 2147942414LL);
        else
          v142 = -2147024882;
        v141 = a2;
        v29 = CError::PostHResult(g_pCError, v142, a2);
        v14 = v200;
        v26 = v198;
        v27 = -2147467259;
        goto LABEL_448;
      }
      *v70 = 0;
    }
    v14 = v200;
    if ( !v200 )
    {
      v71 = 2 * v217;
      if ( !is_mul_ok(v217, 2u) )
        v71 = -1;
      v14 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 112LL))(
              g_pMO,
              v71);
      v200 = v14;
      if ( !v14 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v143 = bidTraceHR(off_1802604F8[0], 4782089, 2147942414LL);
        else
          v143 = -2147024882;
        v141 = a2;
        v29 = CError::PostHResult(g_pCError, v143, a2);
        v26 = v198;
        v27 = -2147467259;
        goto LABEL_448;
      }
    }
    v72 = (__int64)SubStr;
    if ( !SubStr )
    {
      v73 = 2 * v217;
      if ( !is_mul_ok(v217, 2u) )
        v73 = -1;
      v72 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 112LL))(
              g_pMO,
              v73);
      SubStr = (wchar_t *)v72;
      if ( !v72 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v144 = bidTraceHR(off_1802604F8[0], 4793353, 2147942414LL);
        else
          v144 = -2147024882;
        v141 = a2;
        v29 = CError::PostHResult(g_pCError, v144, a2);
        v26 = v198;
        v27 = -2147467259;
        goto LABEL_449;
      }
    }
    if ( !Str )
    {
      v74 = 2 * v217;
      if ( !is_mul_ok(v217, 2u) )
        v74 = -1;
      v75 = (wchar_t *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, unsigned __int64))(*(_QWORD *)g_pMO + 112LL))(
                         g_pMO,
                         v74);
      Str = v75;
      if ( !v75 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v145 = bidTraceHR(off_1802604F8[0], 4806665, 2147942414LL);
        else
          v145 = -2147024882;
        v141 = a2;
        v29 = CError::PostHResult(g_pCError, v145, a2);
        v26 = v198;
        v27 = -2147467259;
        goto LABEL_451;
      }
      *v75 = 0;
      v63 = 1;
      LODWORD(v233) = 1;
      v64 = 1;
      LODWORD(v229) = 1;
LABEL_112:
      _mm_lfence();
      v65 = v214;
      v66 = (CCommand *)this;
      v67 = CCommand::CountParamMarkers((CCommand *)this, v214, v62);
      goto LABEL_140;
    }
LABEL_111:
    v64 = v204;
    LODWORD(v229) = v204;
    if ( v204 )
      goto LABEL_112;
    v67 = a5;
    v65 = v214;
    v66 = (CCommand *)this;
LABEL_140:
    v234 = v67;
    if ( v67 > a8 )
    {
      if ( (bidGblFlags & 2) != 0 )
        v140 = bidTraceHR(off_1802604F8[0], 4826121, 2147549183LL);
      else
        v140 = -2147418113;
      goto LABEL_270;
    }
    v76 = 1;
LABEL_142:
    v221 = v76;
    if ( v76 <= v67 )
      break;
    v105 = v208;
LABEL_258:
    if ( !(_DWORD)v233 )
    {
      v147 = v105 - 1;
      v148 = v216;
      if ( v216 < v147 )
      {
        v27 = -2147467259;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_295;
        v146 = 5067785;
        goto LABEL_291;
      }
      v149 = v216 - v147;
      v150 = Src;
      v151 = &Src[v147];
      if ( v216 != v147 )
      {
        if ( v149 <= 0x7FFFFFFF )
        {
          v152 = 2147483646 - v149;
          v153 = (char *)((char *)L" from " - (char *)v151);
          do
          {
            if ( !(v149 + v152) )
              break;
            v154 = *(_WORD *)&v153[(_QWORD)v151];
            if ( !v154 )
              break;
            *v151++ = v154;
            --v149;
          }
          while ( v149 );
          v155 = v151 - 1;
          if ( v149 )
            v155 = v151;
          *v155 = 0;
          v150 = Src;
        }
        else
        {
          *v151 = 0;
        }
      }
      v156 = v147 + 6;
      if ( v148 < v156 )
      {
        v27 = -2147467259;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_295;
        v146 = 5082121;
        goto LABEL_291;
      }
      v157 = v148 - v156;
      v158 = &v150[v156];
      if ( !v204 )
      {
        if ( v157 )
        {
          if ( v157 <= 0x7FFFFFFF )
          {
            if ( v43 <= 0x7FFFFFFE )
            {
              v165 = v43 - v157;
              v166 = (char *)v212 - (char *)v158;
              do
              {
                if ( !(v157 + v165) )
                  break;
                v167 = *(wchar_t *)((char *)v158 + v166);
                if ( !v167 )
                  break;
                *v158++ = v167;
                --v157;
              }
              while ( v157 );
              v168 = v158 - 1;
              if ( v157 )
                v168 = v158;
              *v168 = 0;
            }
            else
            {
              *v158 = 0;
            }
          }
          else
          {
            *v158 = 0;
          }
        }
        v164 = v43 + v156;
        v12 = v202;
        goto LABEL_354;
      }
      v159 = v218 - 1;
      if ( v157 )
      {
        if ( v157 <= 0x7FFFFFFF )
        {
          v12 = v202;
          if ( v159 <= 0x7FFFFFFE )
          {
            v160 = v159 - v157;
            v161 = (char *)v202 - (char *)v158;
            do
            {
              if ( !(v157 + v160) )
                break;
              v162 = *(wchar_t *)((char *)v158 + v161);
              if ( !v162 )
                break;
              *v158++ = v162;
              --v157;
            }
            while ( v157 );
            v163 = v158 - 1;
            if ( v157 )
              v163 = v158;
            *v163 = 0;
          }
          else
          {
            *v158 = 0;
          }
          goto LABEL_339;
        }
        *v158 = 0;
      }
      v12 = v202;
LABEL_339:
      v164 = v159 + v156;
      if ( v12 )
      {
        (*(void (__fastcall **)(struct ISOSHost_MemObj *, _WORD *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v12);
        v12 = 0;
        v202 = 0;
      }
LABEL_354:
      v169 = v164;
      v170 = Src;
      v171 = (CCommand *)this;
      MetadataQuery = CCommand::GetMetadataQuery((CCommand *)this, Src, v169, &v232, &v235);
      v29 = MetadataQuery;
      if ( MetadataQuery < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          _mm_lfence();
          bidTraceHR(off_1802604F8[0], 5112841, (unsigned int)MetadataQuery);
          v14 = v200;
          v26 = v198;
          v27 = -2147467259;
          goto LABEL_447;
        }
        goto LABEL_309;
      }
      _mm_lfence();
      if ( !v232 )
      {
        v26 = -25400;
        v27 = -2147467259;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_263;
        v28 = 5118985;
        goto LABEL_30;
      }
      _mm_lfence();
      v29 = CStmt::HandleFirehoseModeAtExecute(this[150], a2, 1, 0);
      if ( v29 < 0 )
      {
LABEL_309:
        v14 = v200;
        v26 = v198;
        v27 = -2147467259;
        goto LABEL_447;
      }
      if ( (unsigned int)CDBConnection::CheckOptions(this[149], this[150]) == -1 )
      {
        v27 = -2147467259;
        if ( (bidGblFlags & 2) != 0 )
          v29 = bidTraceHR(off_1802604F8[0], 5138441, 2147500037LL);
        else
          v29 = -2147467259;
        v14 = v200;
        v26 = v198;
        goto LABEL_447;
      }
      v173 = CStmt::SQLExecImmediate(this[150], v232, v235);
      if ( v173 == -1
        || v173 == 1 && !*(_WORD *)CStmt::GetRowMetadata(this[150]) && (CStmt::SQLMoreResults(this[150]) & 0xFFFE) != 0 )
      {
        _mm_lfence();
        CStmt::StmtXferErrors(this[150], (struct CErrorData *)(this + 142));
        CStmt::SQLExecImmediate(this[150], g_wszFmtOnlyOff, g_cwchFmtOnlyOff);
        v26 = v198;
      }
      else
      {
        if ( v232 )
        {
          (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
          v232 = 0;
        }
        if ( v170 )
        {
          (*(void (__fastcall **)(struct ISOSHost_MemObj *, wchar_t *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v170);
          Src = 0;
        }
        v174 = (const struct COLINFO *)(*((_QWORD *)CStmt::GetRowMetadata(this[150]) + 1) + 304LL);
        v175 = *(unsigned __int16 *)CStmt::GetRowMetadata(this[150]);
        if ( v175 >= a5 )
        {
          v176 = v210;
          v177 = v213;
          if ( v213 == 1 && *v210 == 42 )
          {
            v178 = &v214[MaxCount + v227];
            v179 = v35 - (MaxCount + v227);
            GetLexToken(v178, v179, &v227, &MaxCount);
            v214 = (wchar_t *)&v178[MaxCount + v227];
            v231 = v179 - (MaxCount + v227);
          }
          v180 = 1;
          v234 = 1;
          if ( !a5 )
          {
LABEL_410:
            _mm_lfence();
            if ( Str )
            {
              _mm_lfence();
              (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
            }
            if ( v200 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v200);
            }
            if ( SubStr )
            {
              _mm_lfence();
              (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
            }
            CStmt::SQLFreeStmt(this[150], 0, 0);
            return 0;
          }
          while ( v177 == 1 && *v176 == 42 )
          {
            v181 = 0;
            v182 = 0;
            v183 = v231;
            v184 = v214;
            do
            {
              if ( GetLexToken(v184, v183, &v227, &MaxCount) == 3 )
              {
                v185 = v184[v227];
                switch ( v185 )
                {
                  case '(':
                    ++v181;
                    break;
                  case ')':
                    if ( !v181 )
                      goto LABEL_396;
                    --v181;
                    break;
                  case ',':
                    if ( !v181 )
                    {
                      if ( v182 )
                        goto LABEL_396;
                      v174 = (const struct COLINFO *)((char *)v174 + 304);
                      LOWORD(v175) = v175 - 1;
                    }
                    break;
                  case '?':
                    ++v182;
                    break;
                }
              }
              v184 += MaxCount + v227;
              v183 -= MaxCount + v227;
            }
            while ( v183 );
LABEL_396:
            v214 = &v184[MaxCount + v227];
            v231 = v183 - (MaxCount + v227);
            v180 = v234;
            v176 = v210;
            v177 = v213;
            if ( v182 > 0 )
              goto LABEL_399;
LABEL_409:
            if ( v180 > a5 )
              goto LABEL_410;
          }
          v182 = 1;
LABEL_399:
          v186 = &v222[v180 - 1];
          while ( 1 )
          {
            if ( !(_WORD)v175 )
            {
              v26 = -24812;
              goto LABEL_421;
            }
            v187 = (struct PARAMINFO *)((char *)v224 + 64 * (*v223)++);
            if ( v180 > a8 )
              break;
            v188 = this[150];
            v189 = *((_QWORD *)v188 + 84);
            if ( !v189 || (v190 = *(struct CExtByteBuffer **)(v189 + 1952)) == 0 )
              v190 = (CDBConnection *)((char *)v188 + 352);
            v191 = CCommand::ParamInfoFromColInfo((CCommand *)this, v187, v174, *v186, v190);
            if ( v191 < 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_420;
              _mm_lfence();
              v193 = (unsigned int)v191;
              v194 = 5260297;
              goto LABEL_419;
            }
            --v182;
            LOWORD(v175) = v175 - 1;
            v174 = (const struct COLINFO *)((char *)v174 + 304);
            v234 = ++v180;
            ++v186;
            if ( v182 <= 0 )
              goto LABEL_409;
          }
          if ( (bidGblFlags & 2) != 0 )
          {
            v194 = 5252105;
            v193 = 2147549183LL;
LABEL_419:
            bidTraceHR(off_1802604F8[0], v194, v193);
          }
LABEL_420:
          v26 = v198;
LABEL_421:
          v171 = (CCommand *)this;
        }
        else
        {
          v26 = -24812;
        }
      }
      _mm_lfence();
      CStmt::SQLFreeStmt(*((CStmt **)v171 + 150), 0, 0);
      v27 = -2147467259;
      if ( (bidGblFlags & 2) == 0 )
      {
        v29 = -2147467259;
        v14 = v200;
        v12 = v202;
        goto LABEL_447;
      }
      v195 = 5299209;
LABEL_424:
      v29 = bidTraceHR(off_1802604F8[0], v195, 2147500037LL);
      v14 = v200;
      v12 = v202;
      goto LABEL_447;
    }
    v10 = (wchar_t *)(v230 + 2 * (MaxCount + v227));
    v11 = v205 - (MaxCount + v227);
    v14 = v200;
    v12 = v202;
    v9 = (CCommand *)this;
    v13 = v226;
  }
  _mm_lfence();
  v77 = v203;
  Expression = CCommand::FindExpression(
                 v66,
                 v35 + 1,
                 v65,
                 v35,
                 v65,
                 v215,
                 v76,
                 v227,
                 MaxCount,
                 v203,
                 v217,
                 v225,
                 &v213,
                 (const wchar_t **)&v210,
                 &v222[v76 - 1]);
  v198 = Expression;
  if ( Expression )
  {
    if ( Expression == 999 )
    {
      v10 = v210;
      v11 = v213;
      v16 = 0;
      v227 = 0;
      MaxCount = 0;
      v12 = v202;
      goto LABEL_18;
    }
    if ( Expression != 40157 )
    {
      if ( Expression != 40168 )
      {
        v27 = -2147467259;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_295;
        v146 = 4872201;
        goto LABEL_291;
      }
      if ( (bidGblFlags & 2) != 0 )
        v29 = bidTraceHR(off_1802604F8[0], 4868105, 2147749396LL);
      else
        v29 = -2147217900;
      v12 = v202;
      goto LABEL_309;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      v139 = 4864009;
      goto LABEL_268;
    }
LABEL_269:
    v140 = -2147024882;
    goto LABEL_270;
  }
  v79 = v213;
  v80 = v210;
  if ( !v64 )
  {
    if ( v213 )
    {
      do
      {
        if ( *v80 != 32 && (unsigned __int16)(*v80 - 9) > 4u )
          break;
        v213 = --v79;
        v210 = ++v80;
        v203 = v77;
        LODWORD(v233) = v63;
        LODWORD(v229) = 0;
      }
      while ( v79 );
    }
    if ( v216 < v208 )
    {
      v27 = -2147467259;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_295;
      v146 = 5035017;
      goto LABEL_291;
    }
    v132 = v216 - v208;
    v133 = Src;
    v134 = &Src[v208];
    if ( v216 != v208 )
    {
      if ( v132 > 0x7FFFFFFF )
      {
        *v134 = 0;
        v104 = v79 + v208;
        v133[v79 + v208] = 44;
        goto LABEL_190;
      }
      if ( v79 > 0x7FFFFFFE )
      {
        *v134 = 0;
        v104 = v79 + v208;
        v133[v79 + v208] = 44;
        goto LABEL_190;
      }
      v135 = v79 - v132;
      v136 = (char *)v80 - (char *)v134;
      do
      {
        if ( !(v132 + v135) )
          break;
        v137 = *(wchar_t *)((char *)v134 + v136);
        if ( !v137 )
          break;
        *v134++ = v137;
        --v132;
      }
      while ( v132 );
      v138 = v134 - 1;
      if ( v132 )
        v138 = v134;
      *v138 = 0;
    }
    v104 = v79 + v208;
    v133[v79 + v208] = 44;
LABEL_190:
    v105 = v104 + 1;
    v208 = v105;
    if ( v79 == 1 && *v80 == 42 )
      goto LABEL_258;
    v76 = v221 + 1;
    v208 = v105;
    v63 = v233;
    v67 = v234;
    v65 = v214;
    v66 = (CCommand *)this;
    goto LABEL_142;
  }
  v81 = IndexWChar(0x2Eu, v210, v213);
  v82 = v208;
  v83 = v216;
  if ( v79 == v81 )
  {
    if ( v216 < v208 )
    {
      v27 = -2147467259;
      if ( (bidGblFlags & 2) != 0 )
      {
        v146 = 4889609;
        goto LABEL_291;
      }
      v29 = -2147467259;
      v14 = v200;
      v12 = v202;
      v26 = v198;
      goto LABEL_447;
    }
    v84 = v216 - v208;
    v85 = Src;
    v86 = &Src[v208];
    if ( v216 != v208 )
    {
      if ( v84 <= 0x7FFFFFFF )
      {
        if ( v43 <= 0x7FFFFFFE )
        {
          v87 = v43 - v84;
          v88 = (char *)v212 - (char *)v86;
          do
          {
            if ( !(v84 + v87) )
              break;
            v89 = *(wchar_t *)((char *)v86 + v88);
            if ( !v89 )
              break;
            *v86++ = v89;
            --v84;
          }
          while ( v84 );
          v90 = v86 - 1;
          if ( v84 )
            v90 = v86;
          *v90 = 0;
        }
        else
        {
          *v86 = 0;
        }
      }
      else
      {
        *v86 = 0;
      }
    }
    v85[v43 + v208] = 46;
    v82 = v43 + v208 + 1;
    v208 = v82;
  }
  else
  {
    v85 = Src;
  }
  if ( v79 )
  {
    do
    {
      if ( *v80 != 32 && (unsigned __int16)(*v80 - 9) > 4u )
        break;
      ++v80;
      --v79;
    }
    while ( v79 );
    v213 = v79;
    v210 = v80;
    LODWORD(v233) = v63;
    LODWORD(v229) = v64;
    v43 = v220;
    v82 = v208;
  }
  if ( v83 < v82 )
  {
    v27 = -2147467259;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_295;
    v146 = 4909065;
    goto LABEL_291;
  }
  v91 = v83 - v82;
  v92 = (char *)&v85[v82];
  if ( v83 != v82 )
  {
    if ( v91 <= 0x7FFFFFFF )
    {
      if ( v79 <= 0x7FFFFFFE )
      {
        v93 = v79 - v91;
        v94 = (char *)v80 - v92;
        do
        {
          if ( !(v91 + v93) )
            break;
          v95 = *(_WORD *)&v92[v94];
          if ( !v95 )
            break;
          *(_WORD *)v92 = v95;
          v92 += 2;
          --v91;
        }
        while ( v91 );
        v96 = v92 - 2;
        if ( v91 )
          v96 = v92;
        *(_WORD *)v96 = 0;
      }
      else
      {
        *(_WORD *)v92 = 0;
      }
    }
    else
    {
      *(_WORD *)v92 = 0;
    }
  }
  v209 = v79 + v82;
  v85[v79 + v82] = 44;
  v97 = v212;
  if ( v43 )
  {
    do
    {
      if ( *v97 != 32 && (unsigned __int16)(*v97 - 9) > 4u )
        break;
      ++v97;
      --v43;
    }
    while ( v43 );
    v212 = v97;
    LODWORD(v233) = v63;
    LODWORD(v229) = v64;
    v220 = v43;
    v79 = v213;
    v80 = v210;
  }
  v98 = 0;
  for ( j = 0; j < v43; ++j )
  {
    v100 = iswspace(v97[j]);
    v97 = v212;
    if ( !v100 )
      *(_WORD *)(v200 + 2 * v98++) = v212[j];
  }
  v101 = v200;
  *(_WORD *)(v200 + 2 * v98) = 0;
  v102 = 0;
  v103 = 0;
  if ( !v98 )
  {
LABEL_189:
    v104 = v209;
    v64 = v229;
    v35 = v231;
    goto LABEL_190;
  }
  while ( 1 )
  {
    v106 = 0;
    for ( k = *(_WORD *)(v101 + 2 * v103); k != 44; k = *(_WORD *)(v101 + 2 * v103) )
    {
      if ( !k )
        break;
      SubStr[v106++] = k;
      ++v103;
    }
    ++v103;
    ++v102;
    SubStr[v106] = 0;
    if ( !wcsstr_0(Str, SubStr) )
      break;
LABEL_235:
    v101 = v200;
    if ( v103 >= v98 )
    {
      v80 = v210;
      goto LABEL_189;
    }
  }
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = v219;
  if ( v217 < v219 )
  {
    v27 = -2147467259;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_295;
    v146 = 4968457;
LABEL_291:
    v29 = bidTraceHR(off_1802604F8[0], v146, 2147500037LL);
    v12 = v202;
    v14 = v200;
    v26 = v198;
    goto LABEL_447;
  }
  v112 = v217 - v219;
  v113 = Str;
  v114 = (char *)&Str[v219];
  if ( v217 != v219 )
  {
    if ( v112 <= 0x7FFFFFFF )
    {
      if ( v106 <= 0x7FFFFFFE )
      {
        v115 = v106 - v112;
        v116 = (char *)SubStr - v114;
        do
        {
          if ( !(v112 + v115) )
            break;
          v117 = *(_WORD *)&v114[v116];
          if ( !v117 )
            break;
          *(_WORD *)v114 = v117;
          v114 += 2;
          --v112;
        }
        while ( v112 );
        v118 = v114 - 2;
        if ( v112 )
          v118 = v114;
        *(_WORD *)v118 = 0;
        v113 = Str;
        v111 = v219;
      }
      else
      {
        *(_WORD *)v114 = 0;
      }
    }
    else
    {
      *(_WORD *)v114 = 0;
    }
  }
  v119 = v106 + v111;
  v113[v119] = 44;
  v219 = v119 + 1;
  v113[v119 + 1] = 0;
  v120 = 0;
  while ( 2 )
  {
    v121 = v212[v120];
    if ( v121 != 44 && v121 )
      goto LABEL_216;
    if ( ++v110 == v102 - 1 )
    {
      v108 = v120 + 1;
      goto LABEL_216;
    }
    if ( v110 != v102 )
    {
LABEL_216:
      if ( ++v120 > v43 )
        goto LABEL_219;
      continue;
    }
    break;
  }
  v109 = v120;
LABEL_219:
  v122 = v120 - 1;
  if ( v120 <= v43 )
    v122 = v109;
  v123 = v218;
  if ( v216 >= v218 )
  {
    v124 = v122 - v108;
    v125 = &v202[v218];
    v126 = v216 - v218;
    if ( v216 != v218 )
    {
      if ( v126 <= 0x7FFFFFFF )
      {
        if ( v124 <= 0x7FFFFFFE )
        {
          v127 = v124 - v126;
          v128 = (char *)v212 + 2 * v108 - (_QWORD)v125;
          do
          {
            if ( !(v126 + v127) )
              break;
            v129 = *(_WORD *)&v128[(_QWORD)v125];
            if ( !v129 )
              break;
            *v125++ = v129;
            --v126;
          }
          while ( v126 );
          v130 = v125 - 1;
          if ( v126 )
            v130 = v125;
          *v130 = 0;
        }
        else
        {
          *v125 = 0;
        }
      }
      else
      {
        *v125 = 0;
      }
    }
    v131 = v122 - v108 + v123;
    v202[v131] = 44;
    v218 = v131 + 1;
    v202[v131 + 1] = 0;
    goto LABEL_235;
  }
  v27 = -2147467259;
  if ( (bidGblFlags & 2) != 0 )
  {
    v146 = 5010441;
    goto LABEL_291;
  }
LABEL_295:
  v29 = -2147467259;
  v12 = v202;
  v14 = v200;
  v26 = v198;
LABEL_447:
  v141 = a2;
LABEL_448:
  v72 = (__int64)SubStr;
LABEL_449:
  if ( Str )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
LABEL_451:
  if ( v14 )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v14);
  if ( v72 )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v72);
  if ( Src )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
  if ( v232 )
  {
    (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
    v232 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *, _WORD *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, v12);
  if ( v29 == -2147467259 )
  {
    if ( v26 )
    {
      if ( (bidGblFlags & 2) != 0 )
        v196 = bidTraceHR(off_1802604F8[0], 5314569, 2147500037LL);
      else
        v196 = -2147467259;
      v197 = (CCommand *)this;
      CErrorData::PostStandardError((CErrorData *)(this + 142), v26, v196, 0);
    }
    else
    {
      v197 = (CCommand *)this;
    }
    if ( *((_QWORD *)v197 + 142) )
    {
      if ( (bidGblFlags & 2) != 0 )
        v27 = bidTraceHR(off_1802604F8[0], 5317641, 2147500037LL);
      CError::PostSqlErrors(g_pCError, v27, v141, (CCommand *)((char *)v197 + 1136));
    }
  }
  return v29;
}

```

## disassembly

```asm
0x1800d6570  push    rbp
0x1800d6572  push    rbx
0x1800d6573  push    rsi
0x1800d6574  push    rdi
0x1800d6575  push    r12
0x1800d6577  push    r13
0x1800d6579  push    r14
0x1800d657b  push    r15
0x1800d657d  lea     rbp, [rsp-0B8h]
0x1800d6585  sub     rsp, 1B8h
0x1800d658c  mov     rax, cs:__security_cookie
0x1800d6593  xor     rax, rsp
0x1800d6596  mov     [rbp+0F0h+var_50], rax
0x1800d659d  mov     [rbp+0F0h+var_E8], r9
0x1800d65a1  mov     [rbp+0F0h+var_A8], r8
0x1800d65a5  mov     [rbp+0F0h+var_158], rdx
0x1800d65a9  mov     r13, rcx
0x1800d65ac  mov     [rbp+0F0h+var_130], rcx
0x1800d65b0  mov     rcx, [rbp+0F0h+arg_28]
0x1800d65b7  mov     [rbp+0F0h+var_B0], rcx
0x1800d65bb  mov     rcx, [rbp+0F0h+arg_30]
0x1800d65c2  mov     [rbp+0F0h+var_C0], rcx
0x1800d65c6  mov     rcx, [rbp+0F0h+arg_40]
0x1800d65cd  mov     [rbp+0F0h+var_B8], rcx
0x1800d65d1  xor     ecx, ecx
0x1800d65d3  mov     [rbp+0F0h+var_98], rcx
0x1800d65d7  mov     [rbp+0F0h+MaxCount], rcx
0x1800d65db  movzx   r14d, cx
0x1800d65df  mov     dword ptr [rbp+0F0h+var_170], r14d
0x1800d65e3  mov     rbx, r8
0x1800d65e6  mov     r15, r9
0x1800d65e9  mov     [rbp+0F0h+var_70], rcx
0x1800d65f0  mov     [rbp+0F0h+var_58], rcx
0x1800d65f7  mov     [rbp+0F0h+Src], rcx
0x1800d65fb  mov     [rbp+0F0h+var_128], rcx
0x1800d65ff  mov     [rbp+0F0h+var_F0], rcx
0x1800d6603  mov     [rbp+0F0h+var_108], rcx
0x1800d6607  mov     [rbp+0F0h+var_120], rcx
0x1800d660b  mov     [rbp+0F0h+var_144], ecx
0x1800d660e  mov     r12d, ecx
0x1800d6611  mov     [rbp+0F0h+var_150], rcx
0x1800d6615  mov     [rbp+0F0h+var_E0], rcx
0x1800d6619  mov     rax, [r13+1B8h]
0x1800d6620  mov     r14, [rax+340h]
0x1800d6627  mov     [rbp+0F0h+var_A0], r14
0x1800d662b  mov     edi, ecx
0x1800d662d  mov     [rbp+0F0h+var_160], rcx
0x1800d6631  mov     [rbp+0F0h+SubStr], rcx
0x1800d6635  mov     [rbp+0F0h+Str], rcx
0x1800d6639  mov     [rbp+0F0h+var_D8], rcx
0x1800d663d  nop     dword ptr [rax]
0x1800d6640  lea     r9, [rbp+0F0h+MaxCount]; unsigned __int64 *
0x1800d6644  lea     r8, [rbp+0F0h+var_98]; unsigned __int64 *
0x1800d6648  mov     rdx, r15; unsigned __int64
0x1800d664b  mov     rcx, rbx; wchar_t *
0x1800d664e  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1800d6653  mov     esi, 80004005h
0x1800d6658  cmp     eax, 1
0x1800d665b  jnz     loc_1800D82E0
0x1800d6661  cmp     byte ptr [r14+2430h], 0Bh
0x1800d6669  jb      short loc_1800D6680
0x1800d666b  mov     rax, [r14+158h]
0x1800d6672  mov     rcx, [rax+28h]
0x1800d6676  cmp     word ptr [rcx+370h], 50h ; 'P'
0x1800d667e  jnz     short loc_1800D66A7
0x1800d6680  mov     rax, [r13+1B8h]
0x1800d6687  mov     r8, [rax+340h]; struct CDataSource *
0x1800d668e  mov     rax, [rbp+0F0h+var_98]
0x1800d6692  lea     rcx, [rbx+rax*2]; String1
0x1800d6696  mov     rdx, [rbp+0F0h+MaxCount]; MaxCount
0x1800d669a  call    ?FIsStmtKeyword@@YAHPEB_W_KPEAVCDataSource@@@Z; FIsStmtKeyword(wchar_t const *,unsigned __int64,CDataSource *)
0x1800d669f  test    eax, eax
0x1800d66a1  jz      loc_1800D82E0
0x1800d66a7  mov     rax, [rbp+0F0h+MaxCount]
0x1800d66ab  cmp     rax, 6
0x1800d66af  jnz     loc_1800D6737
0x1800d66b5  mov     rax, [rbp+0F0h+var_98]
0x1800d66b9  lea     rdx, [rbx+rax*2]; String2
0x1800d66bd  mov     r8d, 6; MaxCount
0x1800d66c3  lea     rcx, aUpdate; "update"
0x1800d66ca  call    cs:__imp__wcsnicmp
0x1800d66d0  test    eax, eax
0x1800d66d2  jz      loc_1800D678D
0x1800d66d8  mov     rax, [rbp+0F0h+var_98]
0x1800d66dc  lea     rdx, [rbx+rax*2]; String2
0x1800d66e0  mov     r8, [rbp+0F0h+MaxCount]; MaxCount
0x1800d66e4  lea     rcx, aSelect_0; "select"
0x1800d66eb  call    cs:__imp__wcsnicmp
0x1800d66f1  test    eax, eax
0x1800d66f3  jz      loc_1800D678D
0x1800d66f9  mov     rax, [rbp+0F0h+var_98]
0x1800d66fd  lea     rdx, [rbx+rax*2]; String2
0x1800d6701  mov     r8, [rbp+0F0h+MaxCount]; MaxCount
0x1800d6705  lea     rcx, aInsert; "insert"
0x1800d670c  call    cs:__imp__wcsnicmp
0x1800d6712  test    eax, eax
0x1800d6714  jz      short loc_1800D678D
0x1800d6716  mov     rax, [rbp+0F0h+var_98]
0x1800d671a  lea     rdx, [rbx+rax*2]; String2
0x1800d671e  mov     r8, [rbp+0F0h+MaxCount]; MaxCount
0x1800d6722  lea     rcx, aDelete; "delete"
0x1800d6729  call    cs:__imp__wcsnicmp
0x1800d672f  test    eax, eax
0x1800d6731  jz      short loc_1800D678D
0x1800d6733  mov     rax, [rbp+0F0h+MaxCount]
0x1800d6737  cmp     rax, 4
0x1800d673b  jnz     short loc_1800D6760
0x1800d673d  mov     rax, [rbp+0F0h+var_98]
0x1800d6741  lea     rdx, [rbx+rax*2]; String2
0x1800d6745  mov     r8d, 4; MaxCount
0x1800d674b  lea     rcx, aExec; "exec"
0x1800d6752  call    cs:__imp__wcsnicmp
0x1800d6758  test    eax, eax
0x1800d675a  jz      short loc_1800D678D
0x1800d675c  mov     rax, [rbp+0F0h+MaxCount]
0x1800d6760  cmp     rax, 7
0x1800d6764  jnz     loc_1800D82B3
0x1800d676a  mov     rax, [rbp+0F0h+var_98]
0x1800d676e  lea     rdx, [rbx+rax*2]; String2
0x1800d6772  mov     r8d, 7; MaxCount
0x1800d6778  lea     rcx, aExecute; "execute"
0x1800d677f  call    cs:__imp__wcsnicmp
0x1800d6785  test    eax, eax
0x1800d6787  jnz     loc_1800D82B3
0x1800d678d  mov     rax, [rbp+0F0h+var_98]
0x1800d6791  xor     ecx, ecx
0x1800d6793  mov     r14, rcx
0x1800d6796  movzx   ecx, word ptr [rbx+rax*2]; C
0x1800d679a  call    cs:__imp_towlower
0x1800d67a0  movzx   r13d, ax
0x1800d67a4  mov     [rbp+0F0h+var_F8], ax
0x1800d67a8  mov     r8, [rbp+0F0h+MaxCount]
0x1800d67ac  mov     rdx, [rbp+0F0h+var_98]
0x1800d67b0  lea     rcx, [r8+rdx]
0x1800d67b4  lea     rdi, [rbx+rcx*2]
0x1800d67b8  lea     rcx, [r8+rdx]
0x1800d67bc  sub     r15, rcx
0x1800d67bf  cmp     ax, 73h ; 's'
0x1800d67c3  jnz     loc_1800D697C
0x1800d67c9  test    r15, r15
0x1800d67cc  jz      loc_1800D697C
0x1800d67d2  lea     r9, [rbp+0F0h+MaxCount]; unsigned __int64 *
0x1800d67d6  lea     r8, [rbp+0F0h+var_98]; unsigned __int64 *
0x1800d67da  mov     rdx, r15; unsigned __int64
0x1800d67dd  mov     rcx, rdi; wchar_t *
0x1800d67e0  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1800d67e5  cmp     eax, 3
0x1800d67e8  jnz     loc_1800D68CD
0x1800d67ee  xchg    ax, ax
0x1800d67f0  mov     rdx, [rbp+0F0h+var_98]
0x1800d67f4  movzx   ecx, word ptr [rdi+rdx*2]
0x1800d67f8  cmp     cx, 28h ; '('
0x1800d67fc  jnz     loc_1800D6902
0x1800d6802  mov     ebx, 1
0x1800d6807  nop     word ptr [rax+rax+00000000h]
0x1800d6810  mov     rcx, [rbp+0F0h+MaxCount]
0x1800d6814  lea     rax, [rcx+rdx]
0x1800d6818  lea     rdi, [rdi+rax*2]
0x1800d681c  lea     rax, [rcx+rdx]
0x1800d6820  sub     r15, rax
0x1800d6823  jz      loc_1800D777A
0x1800d6829  lea     r9, [rbp+0F0h+MaxCount]; unsigned __int64 *
0x1800d682d  lea     r8, [rbp+0F0h+var_98]; unsigned __int64 *
0x1800d6831  mov     rdx, r15; unsigned __int64
0x1800d6834  mov     rcx, rdi; wchar_t *
0x1800d6837  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1800d683c  mov     rdx, [rbp+0F0h+var_98]
0x1800d6840  cmp     eax, 3
0x1800d6843  jnz     short loc_1800D6896
0x1800d6845  movzx   eax, word ptr [rdi+rdx*2]
0x1800d6849  sub     eax, 28h ; '('
0x1800d684c  jz      short loc_1800D6894
0x1800d684e  sub     eax, 1
0x1800d6851  jz      short loc_1800D6890
0x1800d6853  cmp     eax, 16h
0x1800d6856  jnz     short loc_1800D6896
0x1800d6858  mov     r14d, 9CC8h
0x1800d685e  mov     r15d, 80004005h
0x1800d6864  test    byte ptr cs:_bidGblFlags, 2
0x1800d686b  jz      loc_1800D776E
0x1800d6871  mov     edx, 445809h
0x1800d6876  mov     r8d, r15d
0x1800d6879  mov     rcx, cs:off_1802604F8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800d6880  call    _bidTraceHR
0x1800d6885  mov     ebx, eax
0x1800d6887  mov     rdi, [rbp+0F0h+var_160]
0x1800d688b  jmp     loc_1800D8312
0x1800d6890  dec     ebx
0x1800d6892  jmp     short loc_1800D6896
0x1800d6894  inc     ebx
0x1800d6896  test    ebx, ebx
0x1800d6898  jnz     loc_1800D6810
0x1800d689e  mov     rcx, [rbp+0F0h+MaxCount]
0x1800d68a2  lea     rax, [rcx+rdx]
0x1800d68a6  lea     rdi, [rdi+rax*2]
0x1800d68aa  lea     rax, [rcx+rdx]
0x1800d68ae  sub     r15, rax
0x1800d68b1  lea     r9, [rbp+0F0h+MaxCount]; unsigned __int64 *
0x1800d68b5  lea     r8, [rbp+0F0h+var_98]; unsigned __int64 *
0x1800d68b9  mov     rdx, r15; unsigned __int64
0x1800d68bc  mov     rcx, rdi; wchar_t *
0x1800d68bf  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1800d68c4  cmp     eax, 3
0x1800d68c7  jz      loc_1800D67F0
0x1800d68cd  mov     rdx, [rbp+0F0h+var_98]
0x1800d68d1  cmp     eax, 1
0x1800d68d4  jnz     short loc_1800D6930
0x1800d68d6  mov     rcx, [rbp+0F0h+MaxCount]
0x1800d68da  cmp     rcx, 4
0x1800d68de  jnz     short loc_1800D6944
0x1800d68e0  lea     rdx, [rdi+rdx*2]; String2
0x1800d68e4  mov     r8, rcx; MaxCount
0x1800d68e7  lea     rcx, aFrom_0; "from"
0x1800d68ee  call    cs:__imp__wcsnicmp
0x1800d68f4  test    eax, eax
0x1800d68f6  jz      loc_1800D697C
0x1800d68fc  mov     rdx, [rbp+0F0h+var_98]
0x1800d6900  jmp     short loc_1800D6940
0x1800d6902  cmp     eax, 3
0x1800d6905  jnz     short loc_1800D68D1
0x1800d6907  cmp     cx, 29h ; ')'
0x1800d690b  jnz     short loc_1800D6935
0x1800d690d  mov     r14d, 9CC8h
0x1800d6913  mov     r15d, 80004005h
0x1800d6919  test    byte ptr cs:_bidGblFlags, 2
0x1800d6920  jz      loc_1800D7799
0x1800d6926  mov     edx, 44B009h
0x1800d692b  jmp     loc_1800D6876
0x1800d6930  cmp     eax, 3
0x1800d6933  jnz     short loc_1800D6940
0x1800d6935  cmp     word ptr [rdi+rdx*2], 3Fh ; '?'
0x1800d693a  jz      loc_1800D77A5
0x1800d6940  mov     rcx, [rbp+0F0h+MaxCount]
0x1800d6944  lea     rax, [rcx+rdx]
0x1800d6948  lea     rdi, [rdi+rax*2]
0x1800d694c  lea     rax, [rcx+rdx]
0x1800d6950  sub     r15, rax
0x1800d6953  jnz     loc_1800D67D2
0x1800d6959  mov     r14d, 9CC8h
0x1800d695f  mov     r15d, 80004005h
0x1800d6965  test    byte ptr cs:_bidGblFlags, 2
0x1800d696c  jz      loc_1800D7799
0x1800d6972  mov     edx, 451409h
0x1800d6977  jmp     loc_1800D6876
0x1800d697c  lea     r9, [rbp+0F0h+MaxCount]; unsigned __int64 *
0x1800d6980  lea     r8, [rbp+0F0h+var_98]; unsigned __int64 *
0x1800d6984  mov     rdx, r15; unsigned __int64
0x1800d6987  mov     rcx, rdi; wchar_t *
0x1800d698a  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1800d698f  cmp     eax, 1
0x1800d6992  jnz     loc_1800D6ADC
0x1800d6998  mov     r9, [rbp+0F0h+MaxCount]
0x1800d699c  cmp     r9, 4
0x1800d69a0  jnz     loc_1800D6B5E
0x1800d69a6  cmp     r13w, 69h ; 'i'
0x1800d69ab  jnz     short loc_1800D6A0C
0x1800d69ad  mov     rax, [rbp+0F0h+var_98]
0x1800d69b1  lea     rdx, [rdi+rax*2]; String2
0x1800d69b5  mov     r8, r9; MaxCount
0x1800d69b8  lea     rcx, aInto; "into"
0x1800d69bf  call    cs:__imp__wcsnicmp
0x1800d69c5  test    eax, eax
0x1800d69c7  jz      short loc_1800D6A41
0x1800d69c9  mov     rdx, [rbp+0F0h+var_98]
0x1800d69cd  lea     r12, [rdi+rdx*2]
0x1800d69d1  mov     [rbp+0F0h+var_110], r12
0x1800d69d5  mov     rcx, [rbp+0F0h+MaxCount]
0x1800d69d9  lea     rax, [rcx+rdx]
0x1800d69dd  lea     rsi, [rdi+rax*2]
0x1800d69e1  mov     [rbp+0F0h+var_100], rsi
0x1800d69e5  sub     r15, rcx
0x1800d69e8  sub     r15, rdx
0x1800d69eb  mov     [rbp+0F0h+var_78], r15
0x1800d69ef  lea     r9, [rbp+0F0h+MaxCount]; unsigned __int64 *
0x1800d69f3  lea     r8, [rbp+0F0h+var_98]; unsigned __int64 *
0x1800d69f7  mov     rdx, r15; unsigned __int64
0x1800d69fa  mov     rcx, rsi; wchar_t *
0x1800d69fd  call    ?GetLexToken@@YAKPEB_W_KPEA_K2@Z; GetLexToken(wchar_t const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x1800d6a02  mov     edi, eax
0x1800d6a04  mov     [rbp+0F0h+var_148], eax
0x1800d6a07  jmp     loc_1800D6C15
0x1800d6a0c  cmp     r13w, 73h ; 's'
0x1800d6a11  jz      short loc_1800D6A1E
0x1800d6a13  cmp     r13w, 64h ; 'd'
0x1800d6a18  jnz     loc_1800D6B5E
0x1800d6a1e  mov     rax, [rbp+0F0h+var_98]
0x1800d6a22  lea     rdx, [rdi+rax*2]; String2
0x1800d6a26  mov     r8d, 4; MaxCount
0x1800d6a2c  lea     rcx, aFrom_0; "from"
0x1800d6a33  call    cs:__imp__wcsnicmp
0x1800d6a39  test    eax, eax
0x1800d6a3b  jnz     loc_1800D6B5A
0x1800d6a41  mov     rcx, [rbp+0F0h+MaxCount]
0x1800d6a45  mov     rdx, [rbp+0F0h+var_98]
0x1800d6a49  lea     rax, [rcx+rdx]
0x1800d6a4d  lea     rdi, [rdi+rax*2]
0x1800d6a51  lea     rax, [rcx+rdx]
0x1800d6a55  sub     r15, rax
0x1800d6a58  cmp     r13w, 73h ; 's'
0x1800d6a5d  jnz     loc_1800D6B3E
  ... truncated ...
```
