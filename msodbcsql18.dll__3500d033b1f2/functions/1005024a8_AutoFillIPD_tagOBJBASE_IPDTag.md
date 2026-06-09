# AutoFillIPD(tagOBJBASE *,IPDTag *)

- ea: `0x1005024a8`
- end: `0x100505045`
- name: `?AutoFillIPD@@YAFPEAUtagOBJBASE@@PEAUIPDTag@@@Z`
- size: `11165`
- prototype: `__int16 __fastcall(struct tagOBJBASE *, struct IPDTag *)`
- caller_count: `5`
- callee_count: `50`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x100507acc`
- `0x10050f0c0`
- `0x10050fbf0`
- `0x100511d90`
- `0x100513310`

## callees

- `0x100405630`
- `0x1004056a8`
- `0x100405948`
- `0x100406ddc`
- `0x100456d5c`
- `0x10045839c`
- `0x100459968`
- `0x10045be64`
- `0x100493378`
- `0x10049ecd4`
- `0x1004a1520`
- `0x1004bb0c8`
- `0x1004bc288`
- `0x1004bf770`
- `0x1004ca97c`
- `0x1004cdc74`
- `0x1004f02dc`
- `0x1004fa5c0`
- `0x100502240`
- `0x1005024a8`
- `0x100505590`
- `0x10050562c`
- `0x10050a1bc`
- `0x10050b338`
- `0x10050b56c`
- `0x10050e2a0`
- `0x100510348`
- `0x100520370`
- `0x10052120c`
- `0x1005212b4`
- `0x100522bdc`
- `0x100522d90`
- `0x1005257d4`
- `0x100525dbc`
- `0x100526b90`
- `0x100526d38`
- `0x100529b4c`
- `0x10052ac8c`
- `0x100535e58`
- `0x100538aa8`
- `0x100538c74`
- `0x100538f74`
- `0x10053a0d0`
- `0x10053f52c`
- `0x10053f614`
- `0x100546a24`
- `0x100546a7c`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100504170`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100504170`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100504cd7`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100504cd7`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502dab`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502dc3`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502ddb`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502df3`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502e1f`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502eab`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502f5e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502f94`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100503568`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502dab`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502dc3`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502ddb`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502df3`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502e1f`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502eab`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502f5e`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100502f94`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x100503568`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x10050445d`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x10050445d`

## string_xrefs

- `0x100502da4`: `update`
- `0x100502dec`: `delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AutoFillIPD(struct tagOBJBASE *a1, struct IPDTag *a2)
{
  struct tagOBJBASE *v2; // r12
  int v3; // esi
  __int64 v4; // rbx
  __int64 v5; // rcx
  struct tagOBJBASE *v6; // r13
  _BYTE *v7; // r15
  __int64 v8; // rax
  int v9; // r14d
  unsigned int v10; // r9d
  unsigned __int16 BatchCtxOrRecover; // di
  __int64 v12; // rdx
  __int64 v13; // rax
  const void *v14; // r12
  __int64 v15; // r15
  struct IPDTag *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rbx
  unsigned __int64 v19; // r8
  struct tagDBC *v20; // r15
  struct tagSTMT *v21; // rbx
  int v22; // eax
  __int64 v23; // r9
  unsigned __int16 v24; // r8
  struct tagOBJBASE *v25; // rdi
  CRPCRequest *v26; // rcx
  _WORD *v27; // rdi
  __int16 v28; // bx
  __int64 v29; // rdx
  bool v30; // al
  __int64 v31; // rdi
  __int64 v32; // rdi
  __int64 *v33; // rax
  __int64 v34; // rbx
  int ServerMetadata; // eax
  __int64 v36; // r9
  unsigned __int16 v37; // r8
  struct tagOBJBASE *v38; // rdi
  CRPCRequest *v39; // rcx
  _WORD *v40; // rdi
  __int16 v41; // bx
  unsigned __int16 v42; // r8
  struct tagOBJBASE *v43; // rdi
  CRPCRequest *v44; // rcx
  _WORD *v45; // rdi
  __int16 v46; // bx
  __int64 v47; // rdx
  bool v48; // al
  __int64 v49; // rdi
  __int64 v50; // rdi
  __int64 *v51; // rax
  __int64 v52; // rbx
  int v53; // r13d
  int v54; // r12d
  char *v55; // rbx
  __int64 v56; // r14
  unsigned __int16 LexToken; // dx
  int v58; // r8d
  wchar_t *v59; // rbx
  wchar_t *v60; // r9
  const unsigned __int16 *v61; // rbx
  unsigned int v62; // eax
  int v63; // ecx
  int v64; // edx
  unsigned __int16 v65; // r15
  const unsigned __int16 *v66; // rbx
  unsigned int v67; // r14d
  const unsigned __int16 *v68; // r12
  unsigned __int16 v69; // r15
  int v70; // r8d
  int v71; // edx
  unsigned __int16 v72; // ax
  unsigned __int16 v73; // ax
  unsigned __int64 v74; // rdx
  __int64 v75; // rax
  unsigned __int16 v76; // ax
  unsigned int v77; // r8d
  int v78; // r9d
  unsigned int v79; // edx
  const unsigned __int16 *v80; // r15
  __int64 v81; // rax
  const unsigned __int16 *v82; // rbx
  unsigned int v83; // r14d
  __int64 v84; // rax
  unsigned __int16 *v85; // r10
  unsigned __int16 *v86; // rbx
  unsigned int v87; // r14d
  unsigned __int16 v88; // r12
  int v89; // edx
  unsigned __int16 *v90; // rdi
  int v91; // r8d
  int v92; // edx
  __int64 v93; // rax
  struct tagOBJBASE *v94; // r15
  __int64 v95; // rdx
  unsigned int v96; // r13d
  wchar_t *v97; // r15
  unsigned __int16 v98; // r15
  __int64 v99; // r9
  unsigned int v100; // r15d
  __int64 v101; // r12
  unsigned __int64 v102; // r8
  __int64 v103; // r9
  int v104; // eax
  __int64 v105; // rdx
  __int64 v106; // rdx
  unsigned int v107; // ecx
  __int64 v108; // rax
  const unsigned __int16 *v109; // rbx
  unsigned int v110; // r14d
  __int64 v111; // rax
  unsigned __int64 v112; // r15
  unsigned __int64 v113; // r12
  int v114; // r13d
  int v115; // edi
  struct tagDBC *v116; // r15
  unsigned __int16 v117; // cx
  struct tagOBJBASE *v118; // rbx
  int v119; // eax
  __int64 v120; // r9
  __int16 v121; // ax
  struct pl *v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rdx
  unsigned int v125; // r12d
  unsigned __int64 i; // rbx
  int v127; // esi
  unsigned __int16 *v128; // r10
  int v129; // ecx
  unsigned __int16 *v130; // rax
  const unsigned __int16 *v131; // r15
  struct tagDBC *v132; // r13
  unsigned __int64 v133; // r14
  __int64 v134; // rax
  unsigned __int64 v135; // rsi
  wchar_t *v136; // rax
  __int64 v137; // r9
  __int64 v138; // rdx
  unsigned __int16 *v139; // rsi
  wchar_t *v140; // rcx
  int v141; // r15d
  unsigned __int16 **v142; // r12
  _DWORD *v143; // r14
  __int64 v144; // rax
  const unsigned __int16 *v145; // r8
  int v146; // r14d
  __int64 v147; // r9
  CRPCRequest **v148; // r13
  struct tagSTMT *v149; // r15
  __int64 v150; // r8
  __int64 v151; // rsi
  __int64 v152; // rbx
  int v153; // ecx
  rsize_t DestinationSize; // rdx
  unsigned __int16 v155; // r8
  int v156; // ebx
  struct tagSTMT *v157; // rdx
  unsigned __int16 v158; // r8
  int v159; // esi
  unsigned __int16 *v160; // r14
  struct tagDBC *v161; // r15
  unsigned __int16 v162; // ax
  __int64 v163; // rdx
  unsigned __int16 v164; // cx
  unsigned __int64 v165; // rax
  __int64 v166; // r9
  struct IPDTag *v167; // rsi
  __int16 v168; // cx
  __int16 *v169; // r8
  __int16 v170; // ax
  __int64 v171; // rax
  struct tagSTMT *v172; // rdx
  unsigned __int16 v173; // bx
  struct ext_buffer **v174; // r14
  unsigned __int16 *v175; // rbx
  __int64 v176; // rsi
  struct IPDTag *v177; // rbx
  unsigned int v178; // r9d
  unsigned __int64 v179; // r15
  __int64 v180; // r12
  __int64 v181; // rcx
  unsigned __int16 v182; // r8
  __int64 v183; // r14
  __int64 v184; // rsi
  const wchar_t *NameFromPool; // rbx
  const wchar_t *v186; // rax
  int v187; // eax
  __int64 *v189; // [rsp+38h] [rbp-E0h]
  __int64 *v190; // [rsp+38h] [rbp-E0h]
  __int64 *v191; // [rsp+38h] [rbp-E0h]
  __int64 *v192; // [rsp+38h] [rbp-E0h]
  __int64 *v193; // [rsp+38h] [rbp-E0h]
  __int64 *v194; // [rsp+38h] [rbp-E0h]
  __int64 *v195; // [rsp+38h] [rbp-E0h]
  __int64 *v196; // [rsp+38h] [rbp-E0h]
  size_t v197; // [rsp+60h] [rbp-B8h]
  unsigned __int16 v198; // [rsp+68h] [rbp-B0h]
  size_t MaxCount; // [rsp+98h] [rbp-80h] BYREF
  unsigned __int16 v200[2]; // [rsp+A0h] [rbp-78h] BYREF
  unsigned __int16 v201; // [rsp+A4h] [rbp-74h] BYREF
  _BYTE *v202; // [rsp+A8h] [rbp-70h]
  struct tagOBJBASE *v203; // [rsp+B0h] [rbp-68h]
  int v204; // [rsp+B8h] [rbp-60h]
  __int64 v205; // [rsp+C0h] [rbp-58h] BYREF
  int v206; // [rsp+C8h] [rbp-50h]
  bool v207; // [rsp+CCh] [rbp-4Ch] BYREF
  unsigned int v208[2]; // [rsp+CEh] [rbp-4Ah] BYREF
  unsigned __int16 *v209; // [rsp+D8h] [rbp-40h] BYREF
  struct tagDBC *v210; // [rsp+E0h] [rbp-38h]
  unsigned int v211[2]; // [rsp+E8h] [rbp-30h] BYREF
  unsigned __int64 v212; // [rsp+F0h] [rbp-28h]
  struct tagSTMT *v213; // [rsp+F8h] [rbp-20h]
  struct ext_buffer *v214; // [rsp+100h] [rbp-18h] BYREF
  unsigned __int16 *v215; // [rsp+108h] [rbp-10h]
  unsigned int v216; // [rsp+110h] [rbp-8h] BYREF
  struct IPDTag *v217; // [rsp+118h] [rbp+0h]
  unsigned int v218; // [rsp+120h] [rbp+8h] BYREF
  int v219; // [rsp+124h] [rbp+Ch]
  struct ext_buffer *v220; // [rsp+128h] [rbp+10h] BYREF
  wchar_t *String2; // [rsp+130h] [rbp+18h] BYREF
  struct ext_buffer *v222[2]; // [rsp+138h] [rbp+20h] BYREF
  void **v223; // [rsp+148h] [rbp+30h] BYREF
  __int64 v224; // [rsp+150h] [rbp+38h]
  __int128 v225; // [rsp+158h] [rbp+40h]
  struct tagOBJBASE *v226; // [rsp+168h] [rbp+50h]
  __int16 v227; // [rsp+170h] [rbp+58h]
  int v228; // [rsp+178h] [rbp+60h]
  __int64 v229; // [rsp+180h] [rbp+68h]
  struct ext_buffer *v230[2]; // [rsp+188h] [rbp+70h] BYREF
  unsigned int v231; // [rsp+198h] [rbp+80h] BYREF
  struct tagOBJBASE *v232; // [rsp+1A0h] [rbp+88h]
  unsigned int v233[2]; // [rsp+1A8h] [rbp+90h] BYREF
  unsigned __int16 *v234; // [rsp+1B0h] [rbp+98h] BYREF
  unsigned __int64 v235; // [rsp+1B8h] [rbp+A0h] BYREF
  int v236; // [rsp+1C0h] [rbp+A8h] BYREF
  unsigned int v237; // [rsp+1C4h] [rbp+ACh] BYREF
  unsigned __int16 *v238; // [rsp+1C8h] [rbp+B0h]
  unsigned __int64 v239; // [rsp+1D0h] [rbp+B8h] BYREF
  __int64 v240; // [rsp+1D8h] [rbp+C0h]
  unsigned int v241; // [rsp+1E0h] [rbp+C8h] BYREF
  unsigned int v242[2]; // [rsp+1E8h] [rbp+D0h]
  unsigned __int16 *v243; // [rsp+1F0h] [rbp+D8h]
  struct BATCHCTX *v244; // [rsp+1F8h] [rbp+E0h]
  __int128 v245; // [rsp+200h] [rbp+E8h] BYREF
  _OWORD Destination[3]; // [rsp+210h] [rbp+F8h] BYREF
  __int64 v247; // [rsp+240h] [rbp+128h]
  __int64 v248; // [rsp+248h] [rbp+130h]
  _WORD *v249; // [rsp+250h] [rbp+138h]
  __int16 v250; // [rsp+258h] [rbp+140h]
  _WORD *v251; // [rsp+260h] [rbp+148h]
  __int16 v252; // [rsp+268h] [rbp+150h]
  _WORD *v253; // [rsp+270h] [rbp+158h]
  __int16 v254; // [rsp+278h] [rbp+160h]
  __int16 v255[8]; // [rsp+288h] [rbp+170h] BYREF
  __int16 v256[8]; // [rsp+298h] [rbp+180h] BYREF
  __int128 v257; // [rsp+2A8h] [rbp+190h] BYREF
  unsigned int v258[4]; // [rsp+2B8h] [rbp+1A0h] BYREF
  __int16 v259[8]; // [rsp+2C8h] [rbp+1B0h] BYREF
  __int128 v260; // [rsp+2D8h] [rbp+1C0h] BYREF
  unsigned int v261[4]; // [rsp+2E8h] [rbp+1D0h] BYREF
  __int128 v262; // [rsp+2F8h] [rbp+1E0h]
  _DWORD v263[4]; // [rsp+308h] [rbp+1F0h] BYREF
  unsigned __int16 *v264[2]; // [rsp+318h] [rbp+200h] BYREF
  __int128 v265; // [rsp+328h] [rbp+210h]
  unsigned __int16 v266[136]; // [rsp+338h] [rbp+220h] BYREF
  unsigned __int16 Source[2]; // [rsp+448h] [rbp+330h] BYREF
  char v268[268]; // [rsp+44Ch] [rbp+334h] BYREF
  wchar_t pszDest[544]; // [rsp+558h] [rbp+440h] BYREF

  v248 = -2;
  v217 = a2;
  v2 = a1;
  v203 = a1;
  v200[0] = 0;
  v3 = 0;
  v4 = *((_QWORD *)a2 + 8);
  v213 = (struct tagSTMT *)v4;
  v5 = *(_QWORD *)(v4 + 112);
  v210 = (struct tagDBC *)v5;
  v6 = *(struct tagOBJBASE **)(v5 + 96);
  v232 = v6;
  v222[0] = 0;
  v214 = 0;
  v238 = 0;
  v234 = 0;
  v7 = 0;
  v202 = 0;
  if ( !*(_QWORD *)(v5 + 64)
    || (v8 = *(_QWORD *)(v5 + 64), *(_BYTE *)(v8 + 3878) < 0xBu)
    || (*(_BYTE *)(v8 + 416) & 2) != 0
    || *(_DWORD *)(v4 + 4232)
    || (v9 = 1, *(_QWORD *)(v5 + 760)) )
  {
    v9 = 0;
  }
  v10 = *(_DWORD *)(v4 + 1508);
  v218 = v10;
  v220 = 0;
  v240 = 0;
  if ( v6 != (struct tagOBJBASE *)-320LL )
  {
    v240 = *((_QWORD *)v6 + 40);
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v240 + 32) + 8LL))(v240 + 32, 0, 2);
    v10 = v218;
  }
  v245 = 0;
  BatchCtxOrRecover = GetBatchCtxOrRecover(v6, (struct CAutoBatchCtx_ODBC *)&v245, 0, v10, &v218, 1u);
  v244 = (struct BATCHCTX *)*((_QWORD *)v6 + 141);
  if ( (BatchCtxOrRecover & 0xFFFE) != 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_519;
    v12 = 9508873;
    goto LABEL_12;
  }
  BatchCtxOrRecover = 0;
  if ( *(_QWORD *)(v4 + 1984) == 1 && (*(_DWORD *)(v4 + 1516) & 0x8000200) == 0x8000000 && *(_QWORD *)(v4 + 472) )
    BatchCtxOrRecover = Prepare((struct tagSTMT *)v4);
  if ( (bidGblFlags & 2) != 0 )
    BatchCtxOrRecover = _bidx_SNACOdbc_ErrCode(0, 0x31809u, BatchCtxOrRecover);
  if ( BatchCtxOrRecover == 0xFFFF )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_519;
    v12 = 9512969;
LABEL_12:
    bidTraceMark(0, v12);
    goto LABEL_519;
  }
  if ( (*(_DWORD *)(v4 + 1516) & 0xB00) != 0x200 || *(_DWORD *)(v4 + 2080) )
  {
    v72 = -25374;
    goto LABEL_518;
  }
  if ( (unsigned int)CheckBusy(v6, v200) || CheckOptions(v6) == -1 )
    goto LABEL_519;
  v13 = *(_QWORD *)(v4 + 472);
  v14 = (const void *)(v13 + 24);
  v243 = (unsigned __int16 *)(v13 + 24);
  v15 = *(_QWORD *)(v13 + 8) >> 1;
  *(_QWORD *)v242 = v15;
  v16 = v217;
  if ( !*((_QWORD *)v217 + 15) )
  {
    BatchCtxOrRecover = AllocPlex(
                          v217,
                          *((struct tagOBJBASE **)v217 + 8),
                          *(unsigned int *)(*((_QWORD *)v217 + 8) + 796LL));
    if ( (BatchCtxOrRecover & 0xFFFE) != 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_31:
        v2 = v203;
LABEL_32:
        v7 = v202;
        goto LABEL_519;
      }
      v17 = 9542665;
LABEL_30:
      bidTraceMark(0, v17);
      goto LABEL_31;
    }
    BatchCtxOrRecover = UnbindParam(v16, *(unsigned int *)(*((_QWORD *)v16 + 8) + 796LL));
    if ( (BatchCtxOrRecover & 0xFFFE) != 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_31;
      v17 = 9545737;
      goto LABEL_30;
    }
  }
  v18 = 2LL * (unsigned int)v15;
  v19 = v18 + 512;
  if ( (unsigned int)v15 <= 0x190 )
    v19 = 1000;
  v20 = v210;
  if ( CreateExtBufferEx(v210, v222, v19, 0x80u, 1) == -1
    || WriteToExtBufferEx(v20, v222, v14, v18, 1) == -1
    || DoSubstitutions(0, v20, v222) == -1 )
  {
    goto LABEL_31;
  }
  if ( v9 )
  {
    v224 = 0;
    v225 = 0;
    v226 = 0;
    v227 = 0;
    v223 = &CImpODBCIObtainParameterMetadata::`vftable';
    v228 = 0;
    v229 = 0;
    *(_OWORD *)v230 = 0;
    v21 = v213;
    v22 = CImpODBCIObtainParameterMetadata::Initialize(
            (CImpODBCIObtainParameterMetadata *)&v223,
            v213,
            *((_DWORD *)v213 + 199),
            v222[0],
            v217);
    if ( v22 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(0, 9563145, (unsigned int)v22, v23);
      }
      v223 = &CImpODBCIObtainParameterMetadata::`vftable';
      DestroyNamePool(v226, v230);
      v223 = &CImpODBCObtainMetadata::`vftable';
      v25 = v226;
      if ( v226 )
      {
        if ( *((_QWORD *)&v225 + 1) )
        {
          v26 = (CRPCRequest *)*((_QWORD *)v226 + 140);
          if ( v26 )
          {
            CRPCRequest::RemoveAllCommands(v26, v226);
            v25 = v226;
          }
        }
        v27 = (_WORD *)((char *)v25 + 24);
        v28 = *v27;
        v249 = v27;
        v250 = v28;
        *v27 = v28 | 4;
        ExportImp::SQLFreeStmt(v226, 0, v24);
        *v27 = v28;
        *((_WORD *)v226 + 406) = v227;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v226 + 40) + 32LL) + 24LL))(*((_QWORD *)v226 + 40) + 32LL);
      }
      goto LABEL_50;
    }
    *((_WORD *)v21 + 406) |= 0x403u;
    ServerMetadata = IObtainMetadata::GetServerMetadata((IObtainMetadata *)&v223, 0);
    v3 = ServerMetadata;
    if ( ServerMetadata < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(0, 9570313, (unsigned int)ServerMetadata, v36);
      }
      v223 = &CImpODBCIObtainParameterMetadata::`vftable';
      DestroyNamePool(v226, v230);
      v223 = &CImpODBCObtainMetadata::`vftable';
      v38 = v226;
      if ( v226 )
      {
        if ( *((_QWORD *)&v225 + 1) )
        {
          v39 = (CRPCRequest *)*((_QWORD *)v226 + 140);
          if ( v39 )
          {
            CRPCRequest::RemoveAllCommands(v39, v226);
            v38 = v226;
          }
        }
        v40 = (_WORD *)((char *)v38 + 24);
        v41 = *v40;
        v251 = v40;
        v252 = v41;
        *v40 = v41 | 4;
        ExportImp::SQLFreeStmt(v226, 0, v37);
        *v40 = v41;
        *((_WORD *)v226 + 406) = v227;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v226 + 40) + 32LL) + 24LL))(*((_QWORD *)v226 + 40) + 32LL);
      }
LABEL_50:
      if ( !(_QWORD)v225 )
        goto LABEL_507;
      if ( --*(_DWORD *)(v224 + 1136) )
        goto LABEL_507;
      if ( (*(_BYTE *)(*(_QWORD *)(v225 + 72) + 416LL) & 1) != 0 )
      {
        v30 = *(_QWORD *)(v225 + 112) == 0;
      }
      else
      {
        if ( v224 != *(_QWORD *)(v225 + 112) )
        {
          v29 = *(_QWORD *)(*(_QWORD *)(v224 + 112) + 120LL);
          if ( !v29 || !*(_DWORD *)(v29 + 1848) )
          {
LABEL_59:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v224 + 328) + 32LL) + 8LL))(*(_QWORD *)(v224 + 328) + 32LL);
            BATCHCTX::Release(*(BATCHCTX **)(v224 + 1128));
            *(_QWORD *)(v224 + 1128) = 0;
            v31 = *(_QWORD *)(v224 + 112);
            if ( *(_DWORD *)(v31 + 3272) )
            {
              v32 = *(_QWORD *)(v31 + 3248);
              v33 = (__int64 *)(v32 + 24);
              v34 = 0;
              if ( v32 != -24 )
              {
                v34 = *v33;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(*v33 + 32) + 8LL))(*v33 + 32);
              }
              --*(_DWORD *)(v32 + 16);
              if ( v34 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(v34 + 32) + 24LL))(v34 + 32);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v224 + 328) + 32LL) + 24LL))(*(_QWORD *)(v224 + 328) + 32LL);
            goto LABEL_507;
          }
        }
        v30 = 0;
      }
      if ( !v30 )
        goto LABEL_507;
      goto LABEL_59;
    }
    v223 = &CImpODBCIObtainParameterMetadata::`vftable';
    DestroyNamePool(v226, v230);
    v223 = &CImpODBCObtainMetadata::`vftable';
    v43 = v226;
    if ( v226 )
    {
      if ( *((_QWORD *)&v225 + 1) )
      {
        v44 = (CRPCRequest *)*((_QWORD *)v226 + 140);
        if ( v44 )
        {
          CRPCRequest::RemoveAllCommands(v44, v226);
          v43 = v226;
        }
      }
      v45 = (_WORD *)((char *)v43 + 24);
      v46 = *v45;
      v253 = v45;
      v254 = v46;
      *v45 = v46 | 4;
      ExportImp::SQLFreeStmt(v226, 0, v42);
      *v45 = v46;
      *((_WORD *)v226 + 406) = v227;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v226 + 40) + 32LL) + 24LL))(*((_QWORD *)v226 + 40) + 32LL);
    }
    if ( (_QWORD)v225 )
    {
      if ( !--*(_DWORD *)(v224 + 1136) )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(v225 + 72) + 416LL) & 1) != 0 )
        {
          v48 = *(_QWORD *)(v225 + 112) == 0;
        }
        else
        {
          if ( v224 != *(_QWORD *)(v225 + 112) )
          {
            v47 = *(_QWORD *)(*(_QWORD *)(v224 + 112) + 120LL);
            if ( !v47 || !*(_DWORD *)(v47 + 1848) )
              goto LABEL_88;
          }
          v48 = 0;
        }
        if ( v48 )
        {
LABEL_88:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v224 + 328) + 32LL) + 8LL))(*(_QWORD *)(v224 + 328) + 32LL);
          BATCHCTX::Release(*(BATCHCTX **)(v224 + 1128));
          *(_QWORD *)(v224 + 1128) = 0;
          v49 = *(_QWORD *)(v224 + 112);
          if ( *(_DWORD *)(v49 + 3272) )
          {
            v50 = *(_QWORD *)(v49 + 3248);
            v51 = (__int64 *)(v50 + 24);
            v52 = 0;
            if ( v50 != -24 )
            {
              v52 = *v51;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(*v51 + 32) + 8LL))(*v51 + 32);
            }
            --*(_DWORD *)(v50 + 16);
            if ( v52 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)(v52 + 32) + 24LL))(v52 + 32);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v224 + 328) + 32LL) + 24LL))(*(_QWORD *)(v224 + 328) + 32LL);
        }
      }
    }
LABEL_275:
    ExportImp::SQLFreeStmt(v6, 0, v42);
    BatchCtxOrRecover = 0;
    v2 = v203;
    v7 = v202;
    goto LABEL_506;
  }
  String2 = 0;
  v219 = 0;
  v53 = 0;
  LODWORD(v212) = 0;
  v54 = 0;
  v206 = 0;
  v211[1] = 0;
  v55 = (char *)v222[0] + 24;
  v56 = *((_QWORD *)v222[0] + 1) >> 1;
  LexToken = GetLexToken(
               v20,
               (const unsigned __int16 *)v222[0] + 12,
               (unsigned int)v56,
               (unsigned int *)&MaxCount + 1,
               (unsigned int *)&MaxCount);
  v58 = HIDWORD(MaxCount);
  v59 = (wchar_t *)&v55[2 * HIDWORD(MaxCount)];
  if ( LexToken == 3 )
  {
    v60 = v59;
    while ( *v59 == 40 )
    {
      v61 = &v60[(unsigned int)MaxCount];
      LODWORD(v56) = v56 - (v58 + MaxCount);
      LexToken = GetLexToken(v20, v61, (unsigned int)v56, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
      v58 = HIDWORD(MaxCount);
      v59 = (wchar_t *)&v61[HIDWORD(MaxCount)];
      v60 = v59;
      if ( LexToken != 3 )
        goto LABEL_98;
    }
    goto LABEL_516;
  }
LABEL_98:
  if ( LexToken != 1 )
    goto LABEL_516;
  v62 = MaxCount;
  if ( (_DWORD)MaxCount == 6 )
  {
    if ( !_wcsnicmp(L"update", v59, 6u)
      || !_wcsnicmp(L"select", v59, (unsigned int)MaxCount)
      || !_wcsnicmp(L"insert", v59, (unsigned int)MaxCount)
      || !_wcsnicmp(L"delete", v59, (unsigned int)MaxCount) )
    {
      goto LABEL_108;
    }
    v62 = MaxCount;
  }
  if ( v62 != 4 && v62 != 7 || _wcsnicmp(L"execute", v59, v62) )
  {
LABEL_516:
    v72 = -25368;
    v2 = v203;
    v7 = 0;
    goto LABEL_518;
  }
LABEL_108:
  v63 = MaxCount;
  v64 = HIDWORD(MaxCount);
LABEL_109:
  v65 = *v59 | 0x20;
  v201 = v65;
  v66 = &v59[v63];
  v67 = v56 - (v64 + v63);
  if ( v65 == 115 )
  {
    v68 = v66;
    while ( 1 )
    {
      if ( !v67 )
      {
LABEL_123:
        v54 = v206;
        v65 = v201;
        break;
      }
      v69 = GetLexToken(v210, v66, v67, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
      if ( v69 == 1 )
      {
        v70 = MaxCount;
        if ( (_DWORD)MaxCount != 4 )
          goto LABEL_119;
        if ( !_wcsnicmp(L"from", &v68[HIDWORD(MaxCount)], 4u) )
          goto LABEL_123;
      }
      if ( v69 == 3 )
      {
        v71 = HIDWORD(MaxCount);
        if ( v66[HIDWORD(MaxCount)] == 63 )
          goto LABEL_121;
        v70 = MaxCount;
        goto LABEL_120;
      }
      v70 = MaxCount;
LABEL_119:
      v71 = HIDWORD(MaxCount);
LABEL_120:
      v66 += (unsigned int)(v71 + v70);
      v68 = v66;
      v67 -= v71 + v70;
      if ( !v67 )
        goto LABEL_121;
    }
  }
  v73 = GetLexToken(v210, v66, v67, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
  v204 = 0;
  if ( v73 != 1 )
  {
    if ( v73 != 3 || v65 != 101 )
    {
LABEL_153:
      v77 = HIDWORD(MaxCount);
      v65 = v201;
LABEL_154:
      if ( !v53 )
        goto LABEL_121;
      goto LABEL_155;
    }
    v77 = HIDWORD(MaxCount);
    if ( v66[HIDWORD(MaxCount)] != 63 )
      goto LABEL_154;
    v204 = 1;
    v81 = (unsigned int)(HIDWORD(MaxCount) + MaxCount);
    v82 = &v66[v81];
    v83 = v67 - v81;
    GetLexToken(v210, v82, v83, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
    v84 = (unsigned int)(HIDWORD(MaxCount) + MaxCount);
    v66 = &v82[v84];
    v67 = v83 - v84;
    v76 = GetLexToken(v210, v66, v67, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
LABEL_151:
    if ( v76 == 1 )
    {
      v77 = HIDWORD(MaxCount);
      goto LABEL_155;
    }
    goto LABEL_153;
  }
  v74 = (unsigned int)MaxCount;
  if ( (_DWORD)MaxCount != 4 )
    goto LABEL_146;
  if ( v65 == 105 )
  {
    if ( !_wcsnicmp(L"into", &v66[HIDWORD(MaxCount)], 4u) )
      goto LABEL_132;
    v74 = (unsigned int)MaxCount;
  }
  if ( v65 != 115 && v65 != 100 )
  {
LABEL_146:
    v77 = HIDWORD(MaxCount);
    goto LABEL_156;
  }
  if ( _wcsnicmp(L"from", &v66[HIDWORD(MaxCount)], (unsigned int)v74) )
  {
    v77 = HIDWORD(MaxCount);
LABEL_155:
    v74 = (unsigned int)MaxCount;
    goto LABEL_156;
  }
LABEL_132:
  v75 = (unsigned int)(HIDWORD(MaxCount) + MaxCount);
  v66 += v75;
  v67 -= v75;
  v76 = GetLexToken(v210, v66, v67, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
  if ( v65 != 115 || v76 != 3 )
    goto LABEL_151;
  v77 = HIDWORD(MaxCount);
  v231 = HIDWORD(MaxCount);
  v78 = MaxCount;
  v216 = MaxCount;
  v79 = v67;
  *(unsigned int *)((char *)v208 + 2) = v67;
  if ( v66[HIDWORD(MaxCount)] != 123 )
  {
    v80 = v66;
    while ( 1 )
    {
      if ( v80[v77] != 40 )
        goto LABEL_153;
      v206 = ++v54;
      v80 += v78 + v77;
      *(unsigned int *)((char *)v208 + 2) = v79 - (v78 + v77);
      v76 = GetLexToken(v210, v80, *(unsigned int *)((char *)v208 + 2), &v231, &v216);
      if ( v76 != 3 )
        break;
      v77 = v231;
      v78 = v216;
      v79 = *(unsigned int *)((char *)v208 + 2);
    }
    v65 = v201;
    goto LABEL_151;
  }
  if ( v67 - HIDWORD(MaxCount) - (unsigned int)MaxCount < 3
    || ((v66[HIDWORD(MaxCount) + 1] - 79) & 0xFFDF) != 0
    || ((v66[HIDWORD(MaxCount) + 2] - 74) & 0xFFDF) != 0
    || v66[HIDWORD(MaxCount) + 3] != 32 )
  {
    goto LABEL_121;
  }
  v74 = 0;
  LODWORD(MaxCount) = 0;
  v53 = 1;
  LODWORD(v212) = 1;
LABEL_156:
  v85 = (unsigned __int16 *)&v66[v77];
  v215 = v85;
  if ( v65 == 101 )
  {
    *(_OWORD *)v264 = 0;
    v265 = 0;
    v263[0] = -1;
    *(_QWORD *)&v263[1] = 0;
    v263[3] = 0;
    LODWORD(v212) = 1;
    memset(Destination, 0, sizeof(Destination));
    v247 = 0;
    v125 = v67 - v77;
    v206 = v67 - v77;
    for ( i = 0; i <= 3; ++i )
    {
      if ( *v85 == 46 )
      {
        v263[i] = -1;
        *(unsigned int *)((char *)v208 + 2) = 0;
        v127 = 0;
      }
      else
      {
        if ( !(unsigned int)GetIdentifier(v85, v74, (unsigned int *)((char *)v208 + 2)) )
          goto LABEL_121;
        v128 = v215;
        if ( *v215 == 34 || *v215 == 91 )
        {
          v127 = 1;
          v129 = *(unsigned int *)((char *)v208 + 2);
          v263[i] = *(unsigned int *)((char *)v208 + 2) - 2;
          v130 = v128 + 1;
        }
        else
        {
          v129 = *(unsigned int *)((char *)v208 + 2);
          v263[i] = *(unsigned int *)((char *)v208 + 2);
          v130 = v128;
          v127 = 0;
        }
        v264[i] = v130;
        v85 = &v128[v129];
        v215 = v85;
        v74 = (unsigned int)(MaxCount - v129);
        LODWORD(MaxCount) = MaxCount - v129;
        v125 -= v129;
        v206 = v125;
      }
      if ( !(_DWORD)v74 )
        break;
      if ( *v85 == 46 )
      {
        v215 = ++v85;
        v74 = (unsigned int)(v74 - 1);
        LODWORD(MaxCount) = v74;
        v206 = --v125;
      }
      v127 = 0;
    }
    if ( i != 4 )
    {
      v131 = v85 - 1;
      v132 = v210;
      if ( *(v85 - 1) == 59
        && GetLexToken(v210, v85, v67, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount) == 2 )
      {
        if ( v127 )
        {
          v133 = (unsigned int)v263[i];
          v134 = (unsigned int)(v133 + MaxCount + 2 + HIDWORD(MaxCount));
          v135 = (unsigned int)v134;
          v239 = (unsigned int)v134;
          v136 = (wchar_t *)SQLAllocateMemoryEx(v203, 2 * v134, 1);
          v238 = v136;
          if ( !v136 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              v138 = 9852937;
LABEL_502:
              v104 = bidTraceHR(0, v138, 2147942414LL, v137);
              v7 = v202;
              v2 = v203;
              goto LABEL_503;
            }
            goto LABEL_504;
          }
          v119 = StringCchCopyNExW(v136, v135, v264[i], v133, 0, &v239, 0);
          if ( v119 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_507;
            v124 = 9856009;
            goto LABEL_305;
          }
          _mm_lfence();
          v139 = v238;
          v119 = StringCchCopyNW(&v238[v133], v239, v131, (unsigned int)(HIDWORD(MaxCount) + 1 + MaxCount));
          if ( v119 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_507;
            v124 = 9859081;
            goto LABEL_305;
          }
          v264[i] = v139;
        }
        v263[i] += HIDWORD(MaxCount) + MaxCount + 1;
      }
      v140 = pszDest;
      v209 = pszDest;
      if ( i == 2 )
      {
        if ( v263[0] != -1 )
        {
          v235 = 0;
          v119 = StringCchCopyNExW(pszDest, 0x21Cu, v264[0], v263[0], &v209, &v235, 0);
          if ( v119 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_507;
            v124 = 9885705;
            goto LABEL_305;
          }
          if ( v235 <= 1 )
          {
            BatchCtxOrRecover = -1;
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_323;
            v123 = 9895945;
            goto LABEL_322;
          }
          v119 = StringCchCopyExW(v209, v235, L".", &v209, 0, 0);
          if ( v119 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_507;
            v124 = 9891849;
            goto LABEL_305;
          }
        }
      }
      else if ( i == 3 )
      {
        v141 = 0;
        v142 = v264;
        v143 = v263;
        while ( 1 )
        {
          if ( *v143 != -1 )
          {
            v119 = StringCchCopyNExW(v140, 540 - (v140 - pszDest), *v142, (unsigned int)*v143, &v209, 0, 0);
            if ( v119 < 0 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_507;
              v124 = 9918473;
              goto LABEL_305;
            }
            v140 = v209;
          }
          v119 = StringCchCopyExW(v140, 540 - (v140 - pszDest), L".", &v209, 0, 0);
          if ( v119 < 0 )
            break;
          ++v141;
          ++v143;
          ++v142;
          if ( v141 >= 2 )
          {
            v125 = v206;
            goto LABEL_338;
          }
          v140 = v209;
        }
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_507;
        v124 = 9927689;
LABEL_305:
        _mm_lfence();
        bidTraceHR(0, v124, (unsigned int)v119, v120);
        goto LABEL_507;
      }
LABEL_338:
      if ( !*((_QWORD *)v132 + 8)
        || (v144 = *((_QWORD *)v132 + 8), *(_BYTE *)(v144 + 3878) < 0xAu)
        || (*(_BYTE *)(v144 + 416) & 2) != 0 )
      {
        if ( !*((_QWORD *)v132 + 8) || *(_BYTE *)(*((_QWORD *)v132 + 8) + 3878LL) < 9u )
        {
          v119 = StringCchPrintfW(v209, 540 - (v209 - pszDest), L".%s", off_1005D13D0);
          v146 = v204;
LABEL_347:
          if ( v119 < 0 )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_507;
            v124 = 9955337;
            goto LABEL_305;
          }
          v147 = -1;
          do
            ++v147;
          while ( pszDest[v147] );
          v148 = (CRPCRequest **)v232;
          if ( (int)AddRpcCmdFromStmt(v244, v232, pszDest, v147, 0, 0) < 0 )
            goto LABEL_499;
          _mm_lfence();
          v149 = v213;
          v150 = *((_QWORD *)v213 + 14);
          if ( *(_QWORD *)(v150 + 464) )
          {
            memcpy_s((char *)Destination + 8, 5u, (const void *const)(v150 + 1388), 5u);
          }
          else
          {
            DWORD2(Destination[0]) = 0;
            BYTE12(Destination[0]) = 0;
          }
          v151 = (int)i;
          if ( (i & 0x80000000) == 0LL )
          {
            v152 = 3;
            while ( v152 )
            {
              v153 = v263[v151];
              DestinationSize = (unsigned int)(2 * v153);
              if ( v153 == -1 )
                DestinationSize = 0;
              v155 = 0;
              if ( v153 == -1 )
                v155 = 256;
              if ( (int)CRPCRequest::AddParam(
                          v148[140],
                          0,
                          v155,
                          0xE7u,
                          DestinationSize,
                          0x1FEu,
                          v264[v151],
                          (const struct RPCPARAMEXINFO *)Destination,
                          0,
                          0,
                          0) < 0 )
                goto LABEL_31;
              --v152;
              if ( --v151 < 0 )
                break;
            }
          }
          v156 = 0;
          if ( (*(_BYTE *)(*((_QWORD *)v149 + 14) + 2488LL) & 4) == 0 )
          {
            LOBYTE(v208[0]) = 3;
            if ( (int)CRPCRequest::AddParam(v148[140], L"@ODBCVer", 0, 0x30u, 1u, 1u, v208, 0, 0, 0, 0) < 0 )
              goto LABEL_499;
          }
          BatchCtxOrRecover = ExecRPCImmediate((struct tagSTMT *)v148, 0, v218, 0, 0);
          if ( !BatchCtxOrRecover )
          {
            if ( !v146 )
            {
              BatchCtxOrRecover = ExportImp::SQLFetch((ExportImp *)v148, v157);
              if ( BatchCtxOrRecover )
                goto LABEL_484;
              v219 = 1;
            }
            BatchCtxOrRecover = ExportImp::SQLFetch((ExportImp *)v148, v157);
            v216 = BatchCtxOrRecover;
            if ( !BatchCtxOrRecover )
            {
              while ( 1 )
              {
                if ( !v125 )
                  goto LABEL_511;
                v159 = 0;
                if ( v204 )
                {
                  v156 = 0;
                  v204 = 0;
                  goto LABEL_391;
                }
                v160 = v215;
                v161 = v210;
                while ( 1 )
                {
                  v162 = GetLexToken(v161, v160, v125, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
                  v163 = HIDWORD(MaxCount);
                  if ( v162 == 3 )
                    break;
LABEL_385:
                  v160 += (unsigned int)(HIDWORD(MaxCount) + MaxCount);
                  v125 -= HIDWORD(MaxCount) + MaxCount;
                  if ( !v125 )
                    goto LABEL_386;
                }
                v164 = v160[HIDWORD(MaxCount)];
                if ( v164 == 40 )
                  break;
                if ( v164 == 41 )
                {
                  if ( !v156 )
                    goto LABEL_386;
                  --v156;
                  goto LABEL_385;
                }
                if ( v164 != 44 || v156 )
                {
                  if ( v164 == 63 )
                    v159 = 1;
                  goto LABEL_385;
                }
LABEL_386:
                v215 = v160;
                v206 = v125;
                v156 = 0;
                BatchCtxOrRecover = v216;
                v148 = (CRPCRequest **)v232;
                v149 = v213;
                if ( v125 )
                {
                  v215 = &v160[(unsigned int)(HIDWORD(MaxCount) + MaxCount)];
                  v206 = v125 - (HIDWORD(MaxCount) + MaxCount);
                }
                if ( !v159 )
                  goto LABEL_494;
LABEL_391:
                v219 = 1;
                memset_0(v255, 0, 0x80u);
                v259[4] = 1;
                WORD5(v260) = 1;
                Source[0] = 0;
                if ( (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)4,
                        0xFFF8u,
                        (__int16)Source,
                        (void *)0x102,
                        (__int64)&v205,
                        v189)
                    & 0xFFFE) != 0 )
                  goto LABEL_31;
                v165 = v205;
                if ( v205 == -1 )
                {
                  HIWORD(v260) = 0;
                  v261[0] = 0;
                  v167 = v217;
                }
                else
                {
                  if ( Source[0] != 64 )
                  {
                    v166 = -1;
                    do
                      ++v166;
                    while ( Source[v166] );
                    memmove_s(v268, 0x102u, Source, 2 * v166 + 2);
                    Source[0] = 64;
                    v165 = v205 + 2;
                    v205 += 2;
                  }
                  HIWORD(v260) = v165 >> 1;
                  v167 = v217;
                  if ( (int)AddToNamePool(v149, (struct ext_buffer **)v217 + 13, Source, HIWORD(v260), v261) < 0 )
                  {
                    HIWORD(v260) = 0;
                    v261[0] = 0;
                    BatchCtxOrRecover = -1;
                    if ( (bidGblFlags & 2) == 0 )
                      goto LABEL_323;
                    v123 = 10115081;
LABEL_322:
                    bidTraceMark(0, v123);
                    goto LABEL_323;
                  }
                }
                if ( (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)5,
                        0xFFF1u,
                        (__int16)&v259[4],
                        (void *)2,
                        (__int64)&v205,
                        v190)
                    & 0xFFFE) != 0 )
                  goto LABEL_323;
                v168 = v259[4];
                if ( !v259[4] )
                {
                  v168 = 1;
                  v259[4] = 1;
                  goto LABEL_408;
                }
                if ( v259[4] > 0x10u )
                  goto LABEL_494;
                v163 = 65846;
                if ( !_bittest((const int *)&v163, (unsigned __int16)v259[4]) )
                  goto LABEL_494;
                if ( v259[4] == 5 )
                {
                  v168 = 4;
                  v259[4] = 4;
                }
LABEL_408:
                if ( (v168 & 0xA) != 0 )
                {
                  v168 = 2;
                }
                else if ( (v168 & 0x14) != 0 )
                {
                  v168 = 4;
                }
                v256[3] |= v168;
                if ( (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)6,
                        0xFFF1u,
                        (__int16)v256,
                        0,
                        (__int64)&v205,
                        v189)
                    & 0xFFFE) != 0 )
                  goto LABEL_323;
                if ( ((v256[0] + 153) & 0xFFFD) == 0 )
                {
                  v211[1] = 0;
                  if ( (ExportImp::SQLGetData(
                          (ExportImp *)v148,
                          (struct tagSTMT *)7,
                          0xFFF8u,
                          (__int16)v266,
                          (void *)0x102,
                          (__int64)&v205,
                          v191)
                      & 0xFFFE) == 0
                    && v205 != -1
                    && (int)AddToNamePool(
                              (struct tagOBJBASE *)v148,
                              (struct ext_buffer **)v167 + 13,
                              v266,
                              (unsigned __int64)v205 >> 1,
                              &v211[1]) >= 0 )
                  {
                    if ( v256[0] == -151 )
                    {
                      v258[0] = v211[1];
                      BYTE3(v257) = (unsigned __int64)v205 >> 1;
                    }
                    else
                    {
                      *(_DWORD *)v259 = v211[1];
                      LOBYTE(v258[3]) = (unsigned __int64)v205 >> 1;
                    }
                    goto LABEL_420;
                  }
LABEL_323:
                  v2 = v203;
LABEL_324:
                  v7 = v202;
                  goto LABEL_519;
                }
LABEL_420:
                if ( (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)8,
                        0xFFEEu,
                        (__int16)v255,
                        0,
                        (__int64)&v205,
                        v191)
                    & 0xFFFE) != 0 )
                  goto LABEL_323;
                if ( ((unsigned __int16)(v256[0] + 10) <= 2u || v256[0] == 15) && *(_QWORD *)v255 )
                  *(_QWORD *)v255 *= 2LL;
                if ( (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)0xA,
                        0xFFF1u,
                        (__int16)&v256[1],
                        0,
                        (__int64)&v205,
                        v192)
                    & 0xFFFE) != 0
                  || (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)0xC,
                        0xFFF1u,
                        (__int16)&v260 + 10,
                        0,
                        0,
                        v193)
                    & 0xFFFE) != 0
                  || (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)0x11,
                        0xFFEEu,
                        (__int16)&v255[4],
                        0,
                        (__int64)&v205,
                        v194)
                    & 0xFFFE) != 0 )
                {
                  goto LABEL_323;
                }
                *(_QWORD *)&v255[4] &= -(__int64)(v205 != 0);
                if ( (unsigned __int16)(v256[0] - 91) <= 2u )
                {
                  v256[0] -= 82;
                  goto LABEL_476;
                }
                if ( v256[0] == 8 )
                {
                  v170 = 6;
                  goto LABEL_475;
                }
                if ( v256[0] == -150 )
                {
                  v256[0] = 13;
                  *(_DWORD *)&v259[2] = 1;
                  *(_QWORD *)&v255[4] = 8000;
                  *(_QWORD *)v255 = 8000;
                  goto LABEL_476;
                }
                if ( (unsigned __int16)(v256[0] + 153) > 2u )
                  goto LABEL_476;
                v201 = 0;
                if ( (ExportImp::SQLNumResultCols((ExportImp *)v148, (struct tagSTMT *)&v201, v169) & 0xFFFE) != 0 )
                  goto LABEL_323;
                if ( !*((_QWORD *)v210 + 8)
                  || (v171 = *((_QWORD *)v210 + 8), *(_BYTE *)(v171 + 3878) < 0xAu)
                  || (*(_BYTE *)(v171 + 416) & 2) != 0 )
                {
                  v172 = (struct tagSTMT *)((unsigned int)v201 - 6);
                  v173 = v201 - 5;
                }
                else
                {
                  v172 = (struct tagSTMT *)v201;
                  LOWORD(v172) = v201 - 8;
                  v173 = v201 - 7;
                }
                v266[0] = 0;
                if ( (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        v172,
                        0xFFF8u,
                        (__int16)v266,
                        (void *)0x102,
                        (__int64)&v205,
                        v189)
                    & 0xFFFE) != 0 )
                  goto LABEL_323;
                v174 = (struct ext_buffer **)((char *)v167 + 104);
                if ( v205 == -1 )
                {
                  BYTE1(v257) = 0;
                }
                else
                {
                  if ( (int)AddToNamePool(
                              (struct tagOBJBASE *)v148,
                              v174,
                              v266,
                              (unsigned __int64)v205 >> 1,
                              (unsigned int *)&v257 + 2) < 0 )
                    goto LABEL_323;
                  BYTE1(v257) = (unsigned __int64)v205 >> 1;
                }
                v266[0] = 0;
                if ( (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)v173,
                        0xFFF8u,
                        (__int16)v266,
                        (void *)0x102,
                        (__int64)&v205,
                        v195)
                    & 0xFFFE) != 0 )
                  goto LABEL_323;
                if ( v205 == -1 )
                {
                  BYTE2(v257) = 0;
                }
                else
                {
                  if ( (int)AddToNamePool(
                              (struct tagOBJBASE *)v148,
                              v174,
                              v266,
                              (unsigned __int64)v205 >> 1,
                              (unsigned int *)&v257 + 3) < 0 )
                    goto LABEL_323;
                  BYTE2(v257) = (unsigned __int64)v205 >> 1;
                }
                if ( v256[0] == -151 )
                {
                  if ( (ExportImp::SQLGetData(
                          (ExportImp *)v148,
                          (struct tagSTMT *)(unsigned __int16)(v201 - 4),
                          0xFFF8u,
                          0,
                          0,
                          (__int64)&v205,
                          v189)
                      & 0xFFFE) != 0
                    || v205 == -1
                    || v205 > 4130 )
                  {
                    goto LABEL_323;
                  }
                  if ( (v205 & 0xFFFFFFFFFFFFFFFEuLL) < 0x102 )
                  {
                    v175 = v266;
                    v176 = 258;
                    v266[0] = 0;
                    goto LABEL_458;
                  }
                  v176 = v205 + 2;
                  v175 = (unsigned __int16 *)SQLAllocateMemoryEx((struct tagOBJBASE *)v148, v205 + 2, 1);
                  if ( v175 )
                  {
LABEL_458:
                    if ( (ExportImp::SQLGetData(
                            (ExportImp *)v148,
                            (struct tagSTMT *)(unsigned __int16)(v201 - 4),
                            0xFFF8u,
                            (__int16)v175,
                            (void *)v176,
                            (__int64)&v205,
                            v196)
                        & 0xFFFE) != 0 )
                      goto LABEL_323;
                    if ( v205 == -1 )
                    {
                      WORD2(v257) = 0;
                      goto LABEL_463;
                    }
                    if ( (int)AddToNamePool(
                                (struct tagOBJBASE *)v148,
                                v174,
                                v175,
                                (unsigned __int64)v205 >> 1,
                                &v258[1]) >= 0 )
                    {
                      WORD2(v257) = (unsigned __int64)v205 >> 1;
LABEL_463:
                      if ( v175 != v266 && v175 )
                        ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl->Free)(g_pMO, v175);
                      v170 = 14;
LABEL_475:
                      v256[0] = v170;
                      goto LABEL_476;
                    }
                    if ( v175 == v266 || !v175 )
                      goto LABEL_323;
                    _mm_lfence();
                    ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl->Free)(g_pMO, v175);
LABEL_499:
                    v2 = v203;
                    v7 = v202;
                    goto LABEL_519;
                  }
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v138 = 10312713;
                    goto LABEL_502;
                  }
LABEL_504:
                  v7 = v202;
                  v2 = v203;
LABEL_505:
                  v3 = -2147024882;
                  goto LABEL_506;
                }
                if ( v256[0] != -152 )
                {
                  v170 = 16;
                  memset(v255, 0, sizeof(v255));
                  goto LABEL_475;
                }
                v266[0] = 0;
                if ( (ExportImp::SQLGetData(
                        (ExportImp *)v148,
                        (struct tagSTMT *)(unsigned __int16)(v201 - 1),
                        0xFFF8u,
                        (__int16)v266,
                        (void *)0x102,
                        (__int64)&v205,
                        v189)
                    & 0xFFFE) != 0 )
                  goto LABEL_323;
                if ( v205 == -1 )
                {
                  WORD3(v257) = 0;
                }
                else
                {
                  if ( (int)AddToNamePool((struct tagOBJBASE *)v148, v174, v266, (unsigned __int64)v205 >> 1, &v258[2]) < 0 )
                    goto LABEL_323;
                  WORD3(v257) = (unsigned __int8)((unsigned __int64)v205 >> 1);
                }
                v256[0] = 15;
                memset(v255, 0, sizeof(v255));
LABEL_476:
                v177 = v217;
                v163 = *((_QWORD *)v217 + 15);
                v158 = 0;
                if ( !v163 )
                {
                  v178 = v212;
LABEL_493:
                  LODWORD(v212) = v178 + 1;
                  *((_QWORD *)v177 + 15) = PlAddNewIEx(v217, (struct pl *)v163, v178, v255, 1);
                  v156 = 0;
                  goto LABEL_494;
                }
                v178 = v212;
                v179 = (unsigned int)v212;
                if ( (unsigned __int64)(unsigned int)v212 > *(_QWORD *)(v163 + 8) )
                  goto LABEL_493;
                v180 = (unsigned int)v212 - 1LL;
                v181 = v163 + *(_QWORD *)(v163 + 24) * v180 + 32;
                if ( !v181 || !*(_WORD *)(v181 + 94) )
                  goto LABEL_493;
                if ( (unsigned __int64)(unsigned int)v212 <= *(_QWORD *)(*((_QWORD *)v213 + 57) + 8LL) )
                {
                  while ( 1 )
                  {
                    v183 = *((_QWORD *)v177 + 15);
                    v184 = *(_QWORD *)(v183 + 24) * v180;
                    NameFromPool = GetNameFromPool(*((struct ext_buffer **)v177 + 13), v261[0]);
                    v186 = GetNameFromPool(*((struct ext_buffer **)v217 + 13), *(_DWORD *)(v184 + v183 + 128));
                    v187 = _wcsicmp(v186, NameFromPool);
                    v156 = 0;
                    if ( !v187 )
                      break;
                    ++v179;
                    ++v180;
                    if ( v179 > *(_QWORD *)(*((_QWORD *)v213 + 57) + 8LL) )
                      goto LABEL_482;
                    v177 = v217;
                  }
                  *(_OWORD *)(v184 + v183 + 32) = *(_OWORD *)v255;
                  *(_OWORD *)(v184 + v183 + 48) = *(_OWORD *)v256;
                  *(_OWORD *)(v184 + v183 + 64) = v257;
                  *(_OWORD *)(v184 + v183 + 80) = *(_OWORD *)v258;
                  *(_OWORD *)(v184 + v183 + 96) = *(_OWORD *)v259;
                  *(_OWORD *)(v184 + v183 + 112) = v260;
                  *(_OWORD *)(v184 + v183 + 128) = *(_OWORD *)v261;
                  *(_OWORD *)(v184 + v183 + 144) = v262;
                }
                else
                {
                  v156 = 0;
                }
LABEL_482:
                if ( v179 > *(_QWORD *)(*((_QWORD *)v213 + 57) + 8LL) )
                {
                  v219 = 0;
                  goto LABEL_484;
                }
LABEL_494:
                BatchCtxOrRecover = ExportImp::SQLFetch((ExportImp *)v148, (struct tagSTMT *)v163);
                v216 = BatchCtxOrRecover;
                if ( BatchCtxOrRecover )
                  goto LABEL_484;
                v125 = v206;
                v149 = v213;
              }
              ++v156;
              goto LABEL_385;
            }
          }
LABEL_484:
          if ( BatchCtxOrRecover == 0xFFFF )
          {
            _mm_lfence();
            v2 = v203;
            XferErrors(v203, (struct tagOBJBASE *)v148);
            ExportImp::SQLFreeStmt((ExportImp *)v148, 0, v182);
            BatchCtxOrRecover = -1;
            if ( (bidGblFlags & 2) != 0 )
              bidTraceMark(0, 10436617);
            goto LABEL_324;
          }
LABEL_511:
          _mm_lfence();
          if ( !v219 )
          {
            v200[0] = -25368;
            ExportImp::SQLFreeStmt((ExportImp *)v148, 0, v158);
            BatchCtxOrRecover = -1;
            if ( (bidGblFlags & 2) != 0 )
            {
              v123 = 10443785;
              goto LABEL_322;
            }
            goto LABEL_323;
          }
          ExportImp::SQLFreeStmt((ExportImp *)v148, 0, v158);
          BatchCtxOrRecover = 0;
          goto LABEL_499;
        }
        v145 = off_1005D1490;
      }
      else
      {
        v145 = off_1005D1598;
      }
      v119 = StringCchCopyW(v209, 540 - (v209 - pszDest), v145);
      v146 = v204;
      goto LABEL_347;
    }
LABEL_121:
    v2 = v203;
    goto LABEL_122;
  }
  v86 = (unsigned __int16 *)&v66[v77 + (unsigned int)v74];
  v209 = v86;
  v87 = v67 - (v77 + v74);
  v88 = GetLexToken(v210, v86, v87, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
  LOWORD(v208[0]) = v88;
  v89 = v206;
  v204 = v206;
  if ( v65 == 115 )
  {
    v90 = v86;
    while ( v87 )
    {
      if ( v53 )
      {
        v91 = HIDWORD(MaxCount);
        if ( v86[HIDWORD(MaxCount)] == 125 )
        {
          v86 = &v90[(unsigned int)(HIDWORD(MaxCount) + MaxCount)];
          v209 = v86;
          v87 -= HIDWORD(MaxCount) + MaxCount;
          break;
        }
      }
      else
      {
        if ( v88 == 1 )
        {
          if ( !v89 && (unsigned int)IsEndFromClause(&v86[HIDWORD(MaxCount)], v87 - HIDWORD(MaxCount)) )
            break;
LABEL_164:
          v91 = HIDWORD(MaxCount);
          goto LABEL_172;
        }
        if ( v88 != 3 )
          goto LABEL_164;
        v91 = HIDWORD(MaxCount);
        if ( v86[HIDWORD(MaxCount)] == 40 )
        {
          v92 = v89 + 1;
        }
        else
        {
          if ( v86[HIDWORD(MaxCount)] != 41 )
            goto LABEL_172;
          v92 = v89 - 1;
        }
        v204 = v92;
      }
LABEL_172:
      v93 = (unsigned int)(v91 + MaxCount);
      v86 += v93;
      v209 = v86;
      v90 = v86;
      v87 -= v93;
      v88 = GetLexToken(v210, v86, v87, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
      LOWORD(v208[0]) = v88;
      v89 = v204;
    }
  }
  v235 = v86 - v215;
  *(unsigned int *)((char *)v208 + 2) = v87 + 1;
  v94 = v203;
  if ( v214 )
  {
    *((_QWORD *)v214 + 1) = 0;
    *((_QWORD *)v220 + 1) = 0;
  }
  else
  {
    BatchCtxOrRecover = CreateExtBufferEx(v203, &v214, 0x3E8u, 0x200u, 1);
    if ( BatchCtxOrRecover )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_180;
      v95 = 10502153;
      goto LABEL_179;
    }
    BatchCtxOrRecover = CreateExtBufferEx(v94, &v220, 0x3E8u, 0x200u, 1);
    if ( BatchCtxOrRecover )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_180:
        v2 = v94;
LABEL_181:
        v7 = v202;
        goto LABEL_519;
      }
      v95 = 10505225;
LABEL_179:
      bidTraceMark(0, v95);
      goto LABEL_180;
    }
  }
  BatchCtxOrRecover = WriteToExtBufferEx(v94, &v220, L"group by ", 18, 1);
  if ( BatchCtxOrRecover )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_219;
    v106 = 10515465;
    goto LABEL_218;
  }
  BatchCtxOrRecover = WriteToExtBufferEx(v94, &v214, L"select ", 14, 1);
  if ( BatchCtxOrRecover )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_219;
    v106 = 10518537;
    goto LABEL_218;
  }
  v96 = 1;
  v97 = String2;
  while ( 1 )
  {
    if ( v96 > *((_DWORD *)v213 + 199) )
    {
      v2 = v203;
LABEL_223:
      *((_QWORD *)v214 + 1) -= 2LL;
      BatchCtxOrRecover = WriteToExtBufferEx(v2, &v214, L" from ", 12, 1);
      if ( BatchCtxOrRecover )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_181;
        v105 = 10599433;
        goto LABEL_211;
      }
      BatchCtxOrRecover = WriteToExtBufferEx(v2, &v214, v215, 2LL * (unsigned int)v235, 1);
      if ( BatchCtxOrRecover )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_181;
        v105 = 10602505;
        goto LABEL_211;
      }
      if ( v211[1] )
      {
        *((_QWORD *)v220 + 1) -= 2LL;
        BatchCtxOrRecover = WriteToExtBufferEx(v2, &v214, (char *)v220 + 24, *((_QWORD *)v220 + 1), 1);
        if ( BatchCtxOrRecover )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_181;
          v105 = 10611721;
          goto LABEL_211;
        }
      }
      BatchCtxOrRecover = GetMetadataQuery(
                            v2,
                            v213,
                            (unsigned __int16 *)v214 + 12,
                            *((_DWORD *)v214 + 2) >> 1,
                            &v234,
                            v233);
      if ( BatchCtxOrRecover )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_181;
        v105 = 10615817;
        goto LABEL_211;
      }
      if ( v234 )
      {
        v6 = v232;
        BatchCtxOrRecover = ExecImmediate(v232, v234, v233[0], v218, 1);
        if ( BatchCtxOrRecover == 0xFFFF )
        {
          XferErrors(v2, v6);
          Cancel(v6, 0);
          DisableFmtOnlyMode(v210, 0);
          goto LABEL_32;
        }
        v107 = v211[0];
        v42 = 1;
        if ( v211[0] == 1 && *v97 == 42 )
        {
          v108 = (unsigned int)(HIDWORD(MaxCount) + MaxCount);
          v109 = &v86[v108];
          v110 = v87 - v108;
          GetLexToken(v210, v109, v110, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount);
          v111 = (unsigned int)(HIDWORD(MaxCount) + MaxCount);
          v86 = (unsigned __int16 *)&v109[v111];
          v209 = v86;
          v87 = v110 - v111;
          v107 = v211[0];
          v42 = 1;
        }
        v112 = 1;
        *(_QWORD *)v233 = 1;
        v113 = 1;
        v215 = (unsigned __int16 *)1;
        if ( *(_QWORD *)(*((_QWORD *)v6 + 39) + 8LL) )
        {
          v114 = v204;
          while ( 1 )
          {
            v115 = 0;
            if ( v107 == 1 && *String2 == 42 )
            {
              v116 = v210;
              while ( 1 )
              {
                if ( GetLexToken(v116, v86, v87, (unsigned int *)&MaxCount + 1, (unsigned int *)&MaxCount) == 3 )
                {
                  v117 = v86[HIDWORD(MaxCount)];
                  if ( v117 != 40 )
                  {
                    if ( v117 == 41 )
                    {
                      if ( !v114 )
                        goto LABEL_257;
                    }
                    else
                    {
                      if ( v117 == 44 && !v114 )
                      {
LABEL_257:
                        v209 = &v86[(unsigned int)(HIDWORD(MaxCount) + MaxCount)];
                        v87 -= HIDWORD(MaxCount) + MaxCount;
                        v112 = *(_QWORD *)v233;
                        v113 = (unsigned __int64)v215;
                        goto LABEL_259;
                      }
                      if ( v117 == 63 )
                        ++v115;
                    }
                  }
                }
                v86 += (unsigned int)(HIDWORD(MaxCount) + MaxCount);
                v87 -= HIDWORD(MaxCount) + MaxCount;
                if ( !v87 )
                  goto LABEL_257;
              }
            }
            v115 = 1;
LABEL_259:
            v118 = v232;
            v119 = ParamInfoFromColInfo(
                     (struct paraminfoTag *)v255,
                     (struct tagCOLUMN_INFO *)(*(_QWORD *)(*((_QWORD *)v232 + 39) + 24LL) * (v112 - 1)
                                             + *((_QWORD *)v232 + 39)
                                             + 32LL),
                     v213,
                     v217,
                     *((struct ext_buffer **)v232 + 180));
            v3 = v119;
            if ( v119 < 0 )
              break;
            _mm_lfence();
            if ( v202 && v202[v113 - 1] && (v256[0] == -1 || v256[0] == -10) )
            {
              v121 = -9;
              if ( v256[0] == -1 )
                v121 = 12;
              v256[0] = v121;
              *(_QWORD *)v255 = 8000;
            }
            v42 = 1;
            if ( v115 )
            {
              while ( 1 )
              {
                v122 = PlAddNewIEx(v217, *((struct pl **)v217 + 15), v113, v255, 1);
                v42 = 1;
                v215 = (unsigned __int16 *)++v113;
                *((_QWORD *)v217 + 15) = v122;
                if ( !v122 )
                  break;
                if ( !--v115 )
                  goto LABEL_270;
              }
              BatchCtxOrRecover = -1;
              if ( (bidGblFlags & 2) != 0 )
              {
                v123 = 10706953;
                goto LABEL_322;
              }
              goto LABEL_323;
            }
LABEL_270:
            *(_QWORD *)v233 = ++v112;
            if ( v112 > *(_QWORD *)(*((_QWORD *)v118 + 39) + 8LL) )
            {
              v6 = v118;
              goto LABEL_275;
            }
            v86 = v209;
            v107 = v211[0];
          }
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_507;
          v124 = 10692617;
          goto LABEL_305;
        }
        goto LABEL_275;
      }
LABEL_122:
      v72 = -25400;
      v7 = v202;
LABEL_518:
      v200[0] = v72;
      goto LABEL_519;
    }
    v207 = 0;
    v198 = v88;
    LODWORD(v197) = MaxCount;
    v98 = v201;
    v2 = v203;
    BatchCtxOrRecover = FindExp(
                          v203,
                          v217,
                          v86,
                          *(unsigned int *)((char *)v208 + 2),
                          v86,
                          v87,
                          v243,
                          v242[0],
                          v201,
                          v96,
                          HIDWORD(MaxCount),
                          v197,
                          v198,
                          &String2,
                          v211,
                          &v236,
                          &v207);
    v63 = 0;
    if ( BatchCtxOrRecover )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_181;
      v105 = 10546185;
      goto LABEL_211;
    }
    if ( v207 )
    {
      v59 = String2;
      LODWORD(v56) = v211[0];
      v64 = 0;
      MaxCount = 0;
      v53 = v212;
      v54 = v206;
      goto LABEL_109;
    }
    if ( v236 && v98 != 105 )
      break;
LABEL_194:
    v100 = v211[0];
    v101 = 2LL * v211[0];
    BatchCtxOrRecover = WriteToExtBufferEx(v203, &v214, String2, v101, 1);
    if ( BatchCtxOrRecover )
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_219:
        v2 = v203;
        goto LABEL_181;
      }
      v106 = 10568713;
LABEL_218:
      bidTraceMark(0, v106);
      goto LABEL_219;
    }
    v102 = v100;
    v97 = String2;
    GetLexToken(v210, String2, v102, &v241, &v237);
    if ( !_wcsnicmp(L"case", v97, 4u) && v237 == 4 )
    {
      v211[1] = 1;
      v2 = v203;
      goto LABEL_200;
    }
    v103 = v101;
    v2 = v203;
    BatchCtxOrRecover = WriteToExtBufferEx(v203, &v220, v97, v103, 1);
    if ( BatchCtxOrRecover )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_181;
      v105 = 10582025;
      goto LABEL_211;
    }
    BatchCtxOrRecover = WriteCharToExtBufferEx(v2, &v220, 0x2Cu, 1u, 1);
    if ( BatchCtxOrRecover )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_181;
      v105 = 10586121;
LABEL_211:
      bidTraceMark(0, v105);
      goto LABEL_181;
    }
LABEL_200:
    BatchCtxOrRecover = WriteCharToExtBufferEx(v2, &v214, 0x2Cu, 1u, 1);
    if ( BatchCtxOrRecover )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_181;
      v105 = 10590217;
      goto LABEL_211;
    }
    if ( v211[0] == 1 && *v97 == 42 )
      goto LABEL_223;
    ++v96;
    v88 = v208[0];
  }
  v7 = v202;
  if ( v202 || (v7 = SQLAllocateMemoryEx(v2, *((unsigned int *)v213 + 199), 1), (v202 = v7) != 0) )
  {
    v7[v96 - 1] = 1;
    goto LABEL_194;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_505;
  v104 = bidTraceHR(0, 10562569, 2147942414LL, v99);
LABEL_503:
  v3 = v104;
LABEL_506:
  if ( v3 < 0 )
  {
LABEL_507:
    BatchCtxOrRecover = -1;
    goto LABEL_323;
  }
LABEL_519:
  if ( v222[0] )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  if ( v214 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  if ( v220 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  if ( v238 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  if ( v234 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  if ( v7 )
    ((void (__fastcall *)(struct IMalloc *, _BYTE *))g_pMO->lpVtbl->Free)(g_pMO, v7);
  if ( v200[0] )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceMark(0, 10740745);
    PostSQLErrorEx(v2, v200[0], 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
  }
  CAutoBatchCtx_ODBC::Reset((CAutoBatchCtx_ODBC *)&v245);
  if ( (bidGblFlags & 2) != 0 )
    BatchCtxOrRecover = _bidx_SNACOdbc_ErrCode(0, 0xA3F009u, BatchCtxOrRecover);
  if ( v240 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v240 + 32) + 24LL))(v240 + 32);
  return BatchCtxOrRecover;
}

```

## disassembly

```asm
0x1005024a8  mov     rax, rsp
0x1005024ab  push    rbp
0x1005024ac  push    rsi
0x1005024ad  push    rdi
0x1005024ae  push    r12
0x1005024b0  push    r13
0x1005024b2  push    r14
0x1005024b4  push    r15
0x1005024b6  lea     rbp, [rax-8C8h]
0x1005024bd  sub     rsp, 9A0h
0x1005024c4  mov     [rbp+8C0h+var_790], 0FFFFFFFFFFFFFFFEh
0x1005024cf  mov     [rax+18h], rbx
0x1005024d3  mov     rax, cs:__security_cookie
0x1005024da  xor     rax, rsp
0x1005024dd  mov     [rbp+8C0h+var_40], rax
0x1005024e4  mov     rax, rdx
0x1005024e7  mov     [rbp+8C0h+var_8C0], rdx
0x1005024eb  mov     r12, rcx
0x1005024ee  mov     [rbp+8C0h+var_928], rcx
0x1005024f2  xor     edx, edx
0x1005024f4  mov     [rbp+8C0h+var_938], dx
0x1005024f8  mov     esi, edx
0x1005024fa  mov     rbx, [rax+40h]
0x1005024fe  mov     [rbp+8C0h+var_8E0], rbx
0x100502502  mov     rcx, [rbx+70h]
0x100502506  mov     [rbp+8C0h+var_8F8], rcx
0x10050250a  mov     r13, [rcx+60h]
0x10050250e  mov     [rbp+8C0h+var_838], r13
0x100502515  mov     [rbp+8C0h+var_8A0], rdx
0x100502519  mov     [rbp+8C0h+var_8D8], rdx
0x10050251d  mov     [rbp+8C0h+var_810], rdx
0x100502524  mov     [rbp+8C0h+var_828], rdx
0x10050252b  mov     r15d, edx
0x10050252e  mov     [rbp+8C0h+var_930], rdx
0x100502532  mov     rax, [rcx+40h]
0x100502536  lea     edi, [rdx+1]
0x100502539  lea     r8d, [rdx+2]
0x10050253d  test    rax, rax
0x100502540  jz      short loc_10050256C
0x100502542  mov     rax, [rcx+40h]
0x100502546  cmp     byte ptr [rax+0F26h], 0Bh
0x10050254d  jb      short loc_10050256C
0x10050254f  test    [rax+1A0h], r8b
0x100502556  jnz     short loc_10050256C
0x100502558  cmp     [rbx+1088h], edx
0x10050255e  jnz     short loc_10050256C
0x100502560  cmp     [rcx+2F8h], rdx
0x100502567  mov     r14d, edi
0x10050256a  jz      short loc_10050256F
0x10050256c  mov     r14d, edx
0x10050256f  mov     r9d, [rbx+5E4h]
0x100502576  mov     [rbp+8C0h+var_8B8], r9d
0x10050257a  mov     [rbp+8C0h+var_8B0], rdx
0x10050257e  lea     rax, [r13+140h]
0x100502585  mov     [rbp+8C0h+var_800], rdx
0x10050258c  test    rax, rax
0x10050258f  jz      short loc_1005025B0
0x100502591  mov     rax, [rax]
0x100502594  mov     [rbp+8C0h+var_800], rax
0x10050259b  lea     rcx, [rax+20h]
0x10050259f  mov     rax, [rcx]
0x1005025a2  mov     rax, [rax+8]
0x1005025a6  call    cs:__guard_dispatch_icall_fptr
0x1005025ac  mov     r9d, [rbp+8C0h+var_8B8]; unsigned int
0x1005025b0  xorps   xmm0, xmm0
0x1005025b3  movdqu  [rbp+8C0h+var_7D8], xmm0
0x1005025bb  mov     dword ptr [rsp+9D0h+var_9A8], edi; unsigned int
0x1005025bf  lea     rax, [rbp+8C0h+var_8B8]
0x1005025c3  mov     [rsp+9D0h+DestinationSize], rax; unsigned int
0x1005025c8  xor     r8d, r8d; unsigned __int8
0x1005025cb  lea     rdx, [rbp+8C0h+var_7D8]; struct CAutoBatchCtx_ODBC *
0x1005025d2  mov     rcx, r13; struct tagSTMT *
0x1005025d5  call    ?GetBatchCtxOrRecover@@YAFPEAUtagSTMT@@PEAVCAutoBatchCtx_ODBC@@EKPEAKK@Z; GetBatchCtxOrRecover(tagSTMT *,CAutoBatchCtx_ODBC *,uchar,ulong,ulong *,ulong)
0x1005025da  movzx   edi, ax
0x1005025dd  mov     rax, [r13+468h]
0x1005025e4  mov     [rbp+8C0h+var_7E0], rax
0x1005025eb  mov     ecx, 0FFFEh
0x1005025f0  test    cx, di
0x1005025f3  jz      short loc_100502617
0x1005025f5  mov     ecx, 2
0x1005025fa  test    byte ptr cs:_bidGblFlags, cl
0x100502600  jz      loc_100504EE1
0x100502606  mov     edx, 911809h
0x10050260b  xor     ecx, ecx
0x10050260d  call    _bidTraceMark
0x100502612  jmp     loc_100504EE1
0x100502617  xor     ecx, ecx
0x100502619  mov     edi, ecx
0x10050261b  lea     r9d, [rcx+1]
0x10050261f  cmp     [rbx+7C0h], r9
0x100502626  jnz     short loc_10050264E
0x100502628  mov     eax, [rbx+5ECh]
0x10050262e  and     eax, 8000200h
0x100502633  cmp     eax, 8000000h
0x100502638  jnz     short loc_10050264E
0x10050263a  cmp     [rbx+1D8h], rcx
0x100502641  jz      short loc_10050264E
0x100502643  mov     rcx, rbx; struct tagSTMT *
0x100502646  call    ?Prepare@@YAFPEAUtagSTMT@@@Z; Prepare(tagSTMT *)
0x10050264b  movzx   edi, ax
0x10050264e  mov     eax, 2
0x100502653  test    byte ptr cs:_bidGblFlags, al
0x100502659  jz      short loc_100502673
0x10050265b  movzx   r8d, di; __int16
0x10050265f  mov     edx, 31809h; unsigned __int64
0x100502664  xor     ecx, ecx; unsigned __int64
0x100502666  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x10050266b  movzx   edi, ax
0x10050266e  mov     eax, 2
0x100502673  or      rcx, 0FFFFFFFFFFFFFFFFh
0x100502677  cmp     di, cx
0x10050267a  jnz     short loc_100502692
0x10050267c  test    byte ptr cs:_bidGblFlags, al
0x100502682  jz      loc_100504EE1
0x100502688  mov     edx, 912809h
0x10050268d  jmp     loc_10050260B
0x100502692  mov     eax, [rbx+5ECh]
0x100502698  and     eax, 0B00h
0x10050269d  cmp     eax, 200h
0x1005026a2  jnz     loc_100504ED8
0x1005026a8  xor     eax, eax
0x1005026aa  cmp     [rbx+820h], eax
0x1005026b0  jnz     loc_100504ED8
0x1005026b6  lea     rdx, [rbp+8C0h+var_938]; unsigned __int16 *
0x1005026ba  mov     rcx, r13; struct tagSTMT *
0x1005026bd  call    ?CheckBusy@@YAHPEAUtagSTMT@@PEAG@Z; CheckBusy(tagSTMT *,ushort *)
0x1005026c2  test    eax, eax
0x1005026c4  jnz     loc_100504EE1
0x1005026ca  mov     rcx, r13; struct tagSTMT *
0x1005026cd  call    ?CheckOptions@@YAFPEAUtagSTMT@@@Z; CheckOptions(tagSTMT *)
0x1005026d2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1005026d6  cmp     ax, cx
0x1005026d9  jz      loc_100504EE1
0x1005026df  mov     rax, [rbx+1D8h]
0x1005026e6  lea     r12, [rax+18h]
0x1005026ea  mov     [rbp+8C0h+var_7E8], r12
0x1005026f1  mov     r15, [rax+8]
0x1005026f5  shr     r15, 1
0x1005026f8  mov     qword ptr [rbp+8C0h+var_7F0], r15
0x1005026ff  mov     rbx, [rbp+8C0h+var_8C0]
0x100502703  xor     eax, eax
0x100502705  cmp     [rbx+78h], rax
0x100502709  jnz     short loc_100502784
0x10050270b  mov     rdx, [rbx+40h]; struct tagOBJBASE *
0x10050270f  mov     r8d, [rdx+31Ch]; unsigned __int64
0x100502716  mov     rcx, rbx; struct IPDTag *
0x100502719  call    ?AllocPlex@@YAFPEAUIPDTag@@PEAUtagOBJBASE@@_K@Z; AllocPlex(IPDTag *,tagOBJBASE *,unsigned __int64)
0x10050271e  movzx   edi, ax
0x100502721  mov     eax, 0FFFEh
0x100502726  test    ax, di
0x100502729  jz      short loc_100502751
0x10050272b  mov     ecx, 2
0x100502730  test    byte ptr cs:_bidGblFlags, cl
0x100502736  jz      short loc_100502744
0x100502738  mov     edx, 919C09h
0x10050273d  xor     ecx, ecx
0x10050273f  call    _bidTraceMark
0x100502744  mov     r12, [rbp+8C0h+var_928]
0x100502748  mov     r15, [rbp+8C0h+var_930]
0x10050274c  jmp     loc_100504EE1
0x100502751  mov     rax, [rbx+40h]
0x100502755  mov     edx, [rax+31Ch]; unsigned __int64
0x10050275b  mov     rcx, rbx; struct IPDTag *
0x10050275e  call    ?UnbindParam@@YAFPEAUIPDTag@@_K@Z; UnbindParam(IPDTag *,unsigned __int64)
0x100502763  movzx   edi, ax
0x100502766  mov     eax, 0FFFEh
0x10050276b  test    ax, di
0x10050276e  jz      short loc_100502784
0x100502770  mov     ecx, 2
0x100502775  test    byte ptr cs:_bidGblFlags, cl
0x10050277b  jz      short loc_100502744
0x10050277d  mov     edx, 91A809h
0x100502782  jmp     short loc_10050273D
0x100502784  mov     eax, r15d
0x100502787  lea     rbx, [rax+rax]
0x10050278b  lea     r8, [rbx+200h]
0x100502792  mov     eax, 3E8h
0x100502797  cmp     r15d, 190h
0x10050279e  cmovbe  r8, rax; unsigned __int64
0x1005027a2  mov     eax, 1
0x1005027a7  mov     dword ptr [rsp+9D0h+DestinationSize], eax; int
0x1005027ab  lea     r9d, [rax+7Fh]; unsigned __int64
0x1005027af  lea     rdx, [rbp+8C0h+var_8A0]; struct ext_buffer **
0x1005027b3  mov     r15, [rbp+8C0h+var_8F8]
0x1005027b7  mov     rcx, r15; struct tagOBJBASE *
0x1005027ba  call    ?CreateExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@_K2H@Z; CreateExtBufferEx(tagOBJBASE *,ext_buffer * *,unsigned __int64,unsigned __int64,int)
0x1005027bf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1005027c3  cmp     ax, cx
0x1005027c6  jz      loc_100502744
0x1005027cc  lea     eax, [rcx+2]
0x1005027cf  mov     dword ptr [rsp+9D0h+DestinationSize], eax; int
0x1005027d3  mov     r9, rbx; __int64
0x1005027d6  mov     r8, r12; void *
0x1005027d9  lea     rdx, [rbp+8C0h+var_8A0]; struct ext_buffer **
0x1005027dd  mov     rcx, r15; struct tagOBJBASE *
0x1005027e0  call    ?WriteToExtBufferEx@@YAFPEAUtagOBJBASE@@PEAPEAUext_buffer@@PEBX_JH@Z; WriteToExtBufferEx(tagOBJBASE *,ext_buffer * *,void const *,__int64,int)
0x1005027e5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1005027e9  cmp     ax, r12w
0x1005027ed  jz      loc_100502744
0x1005027f3  lea     r8, [rbp+8C0h+var_8A0]; struct ext_buffer **
0x1005027f7  mov     rdx, r15; struct tagDBC *
0x1005027fa  xor     ecx, ecx; struct tagSTMT *
0x1005027fc  call    ?DoSubstitutions@@YAFPEAUtagSTMT@@PEAUtagDBC@@PEAPEAUext_buffer@@@Z; DoSubstitutions(tagSTMT *,tagDBC *,ext_buffer * *)
0x100502801  cmp     ax, r12w
0x100502805  jz      loc_100502744
0x10050280b  xor     ecx, ecx
0x10050280d  test    r14d, r14d
0x100502810  jz      loc_100502CE0
0x100502816  xor     r15d, r15d
0x100502819  mov     [rbp+8C0h+var_888], r15
0x10050281d  xorps   xmm0, xmm0
0x100502820  movdqa  [rbp+8C0h+var_880], xmm0
0x100502825  mov     [rbp+8C0h+var_870], r15
0x100502829  mov     [rbp+8C0h+var_868], r15w
0x10050282e  lea     rdi, ??_7CImpODBCIObtainParameterMetadata@@6B@; const CImpODBCIObtainParameterMetadata::`vftable'
0x100502835  mov     [rbp+8C0h+var_890], rdi
0x100502839  mov     [rbp+8C0h+var_860], r15d
0x10050283d  mov     [rbp+8C0h+var_858], r15
0x100502841  movdqa  xmmword ptr [rbp+8C0h+var_850], xmm0
0x100502846  mov     rcx, [rbp+8C0h+var_8C0]
0x10050284a  mov     [rsp+9D0h+DestinationSize], rcx; struct IPDTag *
0x10050284f  mov     r9, [rbp+8C0h+var_8A0]; struct ext_buffer *
0x100502853  mov     rbx, [rbp+8C0h+var_8E0]
0x100502857  mov     r8d, [rbx+31Ch]; unsigned int
0x10050285e  mov     rdx, rbx; struct tagSTMT *
0x100502861  lea     rcx, [rbp+8C0h+var_890]; this
0x100502865  call    ?Initialize@CImpODBCIObtainParameterMetadata@@QEAAJPEAUtagSTMT@@KPEAUext_buffer@@PEAUIPDTag@@@Z; CImpODBCIObtainParameterMetadata::Initialize(tagSTMT *,ulong,ext_buffer *,IPDTag *)
0x10050286a  test    eax, eax
0x10050286c  jns     loc_100502A46
0x100502872  lea     ecx, [r12+3]
0x100502877  test    byte ptr cs:_bidGblFlags, cl
0x10050287d  jz      short loc_100502892
0x10050287f  lfence
0x100502882  mov     r8d, eax
0x100502885  mov     edx, 91EC09h
0x10050288a  xor     ecx, ecx
0x10050288c  call    _bidTraceHR
0x100502891  nop
0x100502892  mov     [rbp+8C0h+var_890], rdi
0x100502896  lea     rdx, [rbp+8C0h+var_850]; struct ext_buffer **
0x10050289a  mov     rcx, [rbp+8C0h+var_870]; struct tagOBJBASE *
0x10050289e  call    ?DestroyNamePool@@YAXPEAUtagOBJBASE@@PEAPEAUext_buffer@@@Z; DestroyNamePool(tagOBJBASE *,ext_buffer * *)
0x1005028a3  nop
0x1005028a4  lea     rax, ??_7CImpODBCObtainMetadata@@6B@; const CImpODBCObtainMetadata::`vftable'
0x1005028ab  mov     [rbp+8C0h+var_890], rax
0x1005028af  mov     rdi, [rbp+8C0h+var_870]
0x1005028b3  test    rdi, rdi
0x1005028b6  jz      short loc_100502930
0x1005028b8  cmp     qword ptr [rbp+8C0h+var_880+8], r15
0x1005028bc  jz      short loc_1005028D6
0x1005028be  mov     rcx, [rdi+460h]; this
0x1005028c5  test    rcx, rcx
0x1005028c8  jz      short loc_1005028D6
0x1005028ca  mov     rdx, rdi; void *
0x1005028cd  call    ?RemoveAllCommands@CRPCRequest@@QEAAJPEAX@Z; CRPCRequest::RemoveAllCommands(void *)
0x1005028d2  mov     rdi, [rbp+8C0h+var_870]
0x1005028d6  add     rdi, 18h
0x1005028da  movzx   ebx, word ptr [rdi]
0x1005028dd  movzx   eax, bx
0x1005028e0  or      ax, 4
0x1005028e4  mov     [rbp+8C0h+var_788], rdi
0x1005028eb  mov     [rbp+8C0h+var_780], bx
0x1005028f2  mov     [rdi], ax
0x1005028f5  xor     edx, edx; struct tagSTMT *
0x1005028f7  mov     rcx, [rbp+8C0h+var_870]; this
0x1005028fb  call    ?SQLFreeStmt@ExportImp@@YAFPEAUtagSTMT@@G@Z; ExportImp::SQLFreeStmt(tagSTMT *,ushort)
0x100502900  nop
0x100502901  mov     [rdi], bx
0x100502904  mov     rcx, [rbp+8C0h+var_870]
0x100502908  movzx   eax, [rbp+8C0h+var_868]
0x10050290c  mov     [rcx+32Ch], ax
0x100502913  mov     rax, [rbp+8C0h+var_870]
0x100502917  mov     rcx, [rax+140h]
0x10050291e  add     rcx, 20h ; ' '
0x100502922  mov     rax, [rcx]
0x100502925  mov     rax, [rax+18h]
0x100502929  call    cs:__guard_dispatch_icall_fptr
0x10050292f  nop
0x100502930  cmp     qword ptr [rbp+8C0h+var_880], r15
0x100502934  jz      loc_100504E44
0x10050293a  mov     rax, [rbp+8C0h+var_888]
0x10050293e  add     [rax+470h], r12d
0x100502945  mov     rcx, [rbp+8C0h+var_888]
0x100502949  cmp     [rcx+470h], r15d
0x100502950  jnz     loc_100504E44
0x100502956  mov     rdx, qword ptr [rbp+8C0h+var_880]
0x10050295a  mov     rax, [rdx+48h]
0x10050295e  mov     esi, 1
0x100502963  test    [rax+1A0h], sil
0x10050296a  jnz     short loc_10050298D
0x10050296c  cmp     rcx, [rdx+70h]
0x100502970  jz      short loc_100502988
0x100502972  mov     rax, [rcx+70h]
0x100502976  mov     rdx, [rax+78h]
0x10050297a  test    rdx, rdx
0x10050297d  jz      short loc_10050299C
0x10050297f  cmp     [rdx+738h], r15d
0x100502986  jz      short loc_10050299C
0x100502988  mov     al, r15b
0x10050298b  jmp     short loc_100502994
  ... truncated ...
```
