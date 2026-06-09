# ConnectParameter::ParseConnectionString(wchar_t const *,bool)

- ea: `0x180153e00`
- end: `0x18015570b`
- name: `?ParseConnectionString@ConnectParameter@@QEAAKPEB_W_N@Z`
- size: `6411`
- prototype: `unsigned int(ConnectParameter *__hidden this, const wchar_t *, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180153680`
- `0x1801a93d0`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180007050`
- `0x1800993b0`
- `0x180153240`
- `0x180153280`
- `0x180153e00`
- `0x180156400`
- `0x180159da0`
- `0x18015a6f0`
- `0x18015a880`
- `0x1801a65b1`
- `0x1801a661c`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!LCMapStringW` at `0x180153f20`
- `KERNEL32!LCMapStringW` at `0x180153f20`
- `KERNEL32!CompareStringW` at `0x1801544fb`
- `KERNEL32!CompareStringW` at `0x1801546f9`
- `KERNEL32!CompareStringW` at `0x180154745`
- `KERNEL32!CompareStringW` at `0x1801547af`
- `KERNEL32!CompareStringW` at `0x1801544fb`
- `KERNEL32!CompareStringW` at `0x1801546f9`
- `KERNEL32!CompareStringW` at `0x180154745`
- `KERNEL32!CompareStringW` at `0x1801547af`
- `USER32!CharNextW` at `0x180153f83`
- `USER32!CharNextW` at `0x180153fa8`
- `USER32!CharNextW` at `0x180154033`
- `USER32!CharNextW` at `0x180154057`
- `USER32!CharNextW` at `0x180154173`
- `USER32!CharNextW` at `0x180154198`
- `USER32!CharNextW` at `0x180154223`
- `USER32!CharNextW` at `0x180154247`
- `USER32!CharNextW` at `0x180154393`
- `USER32!CharNextW` at `0x1801543b8`
- `USER32!CharNextW` at `0x180154443`
- `USER32!CharNextW` at `0x180154467`
- `USER32!CharNextW` at `0x1801548c3`
- `USER32!CharNextW` at `0x1801548e8`
- `USER32!CharNextW` at `0x180154963`
- `USER32!CharNextW` at `0x180154987`
- `USER32!CharNextW` at `0x180154af3`
- `USER32!CharNextW` at `0x180154b18`
- `USER32!CharNextW` at `0x180154b93`
- `USER32!CharNextW` at `0x180154bb7`
- `USER32!CharNextW` at `0x180154d63`
- `USER32!CharNextW` at `0x180154d88`
- `USER32!CharNextW` at `0x180154e13`
- `USER32!CharNextW` at `0x180154e37`
- `USER32!CharNextW` at `0x180154f73`
- `USER32!CharNextW` at `0x180154f98`
- `USER32!CharNextW` at `0x180155023`
- `USER32!CharNextW` at `0x180155047`
- `USER32!CharNextW` at `0x180153f83`
- `USER32!CharNextW` at `0x180153fa8`
- `USER32!CharNextW` at `0x180154033`
- `USER32!CharNextW` at `0x180154057`
- `USER32!CharNextW` at `0x180154173`
- `USER32!CharNextW` at `0x180154198`
- `USER32!CharNextW` at `0x180154223`
- `USER32!CharNextW` at `0x180154247`
- `USER32!CharNextW` at `0x180154393`
- `USER32!CharNextW` at `0x1801543b8`
- `USER32!CharNextW` at `0x180154443`
- `USER32!CharNextW` at `0x180154467`
- `USER32!CharNextW` at `0x1801548c3`
- `USER32!CharNextW` at `0x1801548e8`
- `USER32!CharNextW` at `0x180154963`
- `USER32!CharNextW` at `0x180154987`
- `USER32!CharNextW` at `0x180154af3`
- `USER32!CharNextW` at `0x180154b18`
- `USER32!CharNextW` at `0x180154b93`
- `USER32!CharNextW` at `0x180154bb7`
- `USER32!CharNextW` at `0x180154d63`
- `USER32!CharNextW` at `0x180154d88`
- `USER32!CharNextW` at `0x180154e13`
- `USER32!CharNextW` at `0x180154e37`
- `USER32!CharNextW` at `0x180154f73`
- `USER32!CharNextW` at `0x180154f98`
- `USER32!CharNextW` at `0x180155023`
- `USER32!CharNextW` at `0x180155047`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ConnectParameter::ParseConnectionString(wchar_t *this, const wchar_t *a2, char a3, __int64 a4)
{
  ConnectParameter *v6; // r14
  int v7; // r12d
  int v8; // r13d
  bool v9; // al
  __int64 v10; // rbx
  __int64 v11; // rsi
  unsigned __int64 v12; // r15
  __int64 v13; // rdx
  WCHAR *lpDestStr; // rax
  unsigned int cchDest; // ebx
  unsigned int v16; // eax
  const wchar_t *v17; // rcx
  WCHAR v18; // di
  const WCHAR *v19; // r14
  const WCHAR *v20; // rsi
  const WCHAR *v21; // rcx
  int v22; // ebx
  LPWSTR v23; // rax
  __int64 v24; // rax
  rsize_t v25; // rbp
  const WCHAR *v26; // rax
  const WCHAR *v27; // rsi
  WCHAR v28; // di
  const WCHAR *v29; // rcx
  int v30; // ebx
  LPWSTR v31; // rax
  __int64 v32; // rax
  unsigned __int64 v33; // rax
  rsize_t v34; // rbx
  wchar_t *v35; // rax
  WCHAR *v36; // r12
  __int64 v37; // rdi
  wchar_t *v38; // r15
  __int64 v39; // rax
  unsigned __int64 v40; // rbp
  WCHAR v41; // di
  const WCHAR *v42; // r14
  const WCHAR *v43; // rsi
  const WCHAR *v44; // rcx
  int v45; // ebx
  LPWSTR v46; // rax
  __int64 v47; // rax
  rsize_t v48; // r14
  const WCHAR *v49; // rax
  const WCHAR *v50; // rsi
  WCHAR v51; // di
  const WCHAR *v52; // rcx
  int v53; // ebx
  LPWSTR v54; // rax
  __int64 v55; // rax
  unsigned __int64 v56; // rax
  rsize_t v57; // rbx
  __int64 v58; // rcx
  wchar_t v59; // ax
  __int64 v60; // rcx
  wchar_t v61; // ax
  __int64 v62; // rcx
  wchar_t v63; // ax
  LPWSTR v64; // r14
  __int64 v65; // rbx
  __int64 v66; // rax
  unsigned __int64 v67; // rbp
  wchar_t v68; // di
  WCHAR *v69; // rsi
  const WCHAR *v70; // rcx
  int v71; // ebx
  LPWSTR v72; // rax
  __int64 v73; // rax
  unsigned __int64 v74; // r14
  LPWSTR v75; // rax
  const WCHAR *v76; // rsi
  WCHAR v77; // di
  const WCHAR *v78; // rcx
  int v79; // ebx
  LPWSTR v80; // rax
  __int64 v81; // rax
  unsigned __int64 v82; // rax
  unsigned __int64 v83; // rbx
  rsize_t v84; // r9
  rsize_t v85; // rdx
  ConnectParameter *v86; // r15
  char *v87; // rcx
  char *v88; // rdx
  __int16 v89; // ax
  char *v90; // rax
  __int64 v91; // rax
  __int64 v92; // rbp
  __int64 v93; // rdx
  _WORD *v94; // rax
  _WORD *v95; // rdi
  bool v96; // al
  __int64 v97; // rdx
  ConnectParameter *v98; // rcx
  __int16 v99; // ax
  ConnectParameter *v100; // rax
  _WORD *v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // rax
  const WCHAR *v104; // rbx
  __int64 v105; // r9
  int v106; // eax
  __int64 v107; // rdx
  __int64 v108; // rax
  _WORD *v109; // rdi
  const WCHAR *v110; // r8
  __int64 v111; // r9
  int v112; // eax
  __int64 v113; // rax
  wchar_t *v114; // rax
  wchar_t *v115; // r15
  __int64 v116; // rax
  unsigned __int64 v117; // rbp
  WCHAR v118; // di
  const WCHAR *v119; // r14
  const WCHAR *v120; // rsi
  const WCHAR *v121; // rcx
  int v122; // ebx
  LPWSTR v123; // rax
  __int64 v124; // rax
  rsize_t v125; // r14
  const WCHAR *v126; // rax
  const WCHAR *v127; // rsi
  WCHAR v128; // di
  const WCHAR *v129; // rcx
  int v130; // ebx
  LPWSTR v131; // rax
  __int64 v132; // rax
  unsigned __int64 v133; // rax
  rsize_t v134; // rbx
  ConnectParameter *v135; // rdi
  char *v136; // r9
  __int64 v137; // rdx
  _WORD *v138; // rcx
  __int16 v139; // ax
  _WORD *v140; // rax
  __int64 v141; // rcx
  wchar_t v142; // ax
  __int64 v143; // rcx
  wchar_t v144; // ax
  wchar_t *v145; // rax
  __int64 v146; // rax
  unsigned __int64 v147; // rbp
  WCHAR v148; // di
  const WCHAR *v149; // r14
  const WCHAR *v150; // rsi
  const WCHAR *v151; // rcx
  int v152; // ebx
  LPWSTR v153; // rax
  __int64 v154; // rax
  rsize_t v155; // r14
  const WCHAR *v156; // rax
  const WCHAR *v157; // rsi
  WCHAR v158; // di
  const WCHAR *v159; // rcx
  int v160; // ebx
  LPWSTR v161; // rax
  __int64 v162; // rax
  unsigned __int64 v163; // rax
  rsize_t v164; // rbx
  __int64 v165; // rax
  __int64 v166; // rdx
  _WORD *v167; // rax
  __int64 v168; // rdx
  _WORD *v169; // rax
  wchar_t *v170; // r15
  __int64 v171; // rax
  __int64 v172; // rax
  unsigned __int64 v173; // rbp
  WCHAR v174; // di
  const WCHAR *v175; // r14
  const WCHAR *v176; // rsi
  const WCHAR *v177; // rcx
  int v178; // ebx
  LPWSTR v179; // rax
  __int64 v180; // rax
  rsize_t v181; // r14
  const WCHAR *v182; // rax
  const WCHAR *v183; // rsi
  WCHAR v184; // di
  const WCHAR *v185; // rcx
  int v186; // ebx
  LPWSTR v187; // rax
  __int64 v188; // rax
  unsigned __int64 v189; // rax
  rsize_t v190; // rbx
  const wchar_t *v191; // r12
  __int64 v192; // rcx
  __int64 v193; // rax
  unsigned __int64 v194; // r15
  wchar_t v195; // di
  WCHAR *v196; // rsi
  const WCHAR *v197; // rcx
  int v198; // ebx
  LPWSTR v199; // rax
  __int64 v200; // rax
  rsize_t v201; // rbp
  LPWSTR v202; // rax
  const WCHAR *v203; // rsi
  WCHAR v204; // di
  const WCHAR *v205; // rcx
  int v206; // ebx
  LPWSTR v207; // rax
  __int64 v208; // rax
  unsigned __int64 v209; // rax
  rsize_t v210; // rbx
  __int64 v211; // rbx
  __int64 v212; // rcx
  wchar_t v213; // ax
  ConnectParameter *v214; // rcx
  __int16 v215; // ax
  __int16 v216; // ax
  ConnectParameter *v217; // rax
  char *v218; // rbx
  __int64 v219; // rcx
  wchar_t v220; // ax
  __int64 v221; // rcx
  wchar_t v222; // ax
  __int64 v223; // rcx
  wchar_t v224; // ax
  __int64 v225; // rcx
  wchar_t v226; // ax
  __int64 v227; // rcx
  wchar_t v228; // ax
  __int64 v229; // rcx
  wchar_t v230; // ax
  char *v231; // rdx
  __int64 v232; // rcx
  __int16 v233; // ax
  char *v234; // rax
  unsigned int v235; // r15d
  wchar_t *v236; // r8
  __int64 v237; // rdx
  char *v238; // rcx
  int v241; // [rsp+68h] [rbp-70h]
  wchar_t *v243; // [rsp+70h] [rbp-68h]
  int v244; // [rsp+78h] [rbp-60h]
  WCHAR *lpsz; // [rsp+80h] [rbp-58h]
  wchar_t *v246; // [rsp+88h] [rbp-50h]
  __int64 v247; // [rsp+90h] [rbp-48h] BYREF

  v6 = (ConnectParameter *)this;
  v247 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && `ConnectParameter::ParseConnectionString'::`7'::_bidPtrSA_040_118[0] )
    bidScopeEnterW(&v247, `ConnectParameter::ParseConnectionString'::`7'::_bidPtrSA_040_118[0], a2, a4);
  v7 = 0;
  v8 = 0;
  v244 = 0;
  *((_BYTE *)v6 + 3096) = a3;
  v9 = *((_BYTE *)v6 + 3094) && !a3;
  *((_BYTE *)v6 + 3094) = v9;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  if ( (_DWORD)v10 != -1 )
  {
    v11 = (unsigned int)v10;
    v12 = (unsigned int)v10 + 1LL;
    v13 = 2 * v12;
    if ( !is_mul_ok(v12, 2u) )
      v13 = -1;
    lpDestStr = (WCHAR *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 112LL))(
                           gpmo,
                           v13);
    lpsz = lpDestStr;
    if ( lpDestStr )
    {
      v241 = 87;
      cchDest = v10 + 1;
      v16 = LCMapStringW(0x800u, 0x100u, a2, -1, lpDestStr, cchDest);
      if ( !v16 || v16 > cchDest )
        goto LABEL_434;
      v17 = lpsz;
      lpsz[v11] = 0;
      v18 = *lpsz;
      if ( *lpsz )
      {
        if ( lpsz[v12 - 1] )
          goto LABEL_434;
        v19 = lpsz;
        v20 = 0;
        do
        {
          v21 = L" \t";
          v22 = 0;
          while ( 1 )
          {
            if ( !*v21 )
            {
LABEL_25:
              v20 = 0;
              goto LABEL_26;
            }
            if ( *v21 == v18 )
              break;
            v23 = CharNextW(v21);
            v21 = v23;
            if ( v23 )
            {
              v24 = v23 - L" \t";
              if ( (int)v24 > v22 )
              {
                v22 = v24;
                if ( (int)v24 < 3 )
                  continue;
              }
            }
            goto LABEL_25;
          }
          v26 = v19;
          if ( v20 )
            v26 = v20;
          v20 = v26;
LABEL_26:
          v19 = CharNextW(v19);
          v18 = *v19;
        }
        while ( *v19 );
        v17 = lpsz;
        if ( v20 )
        {
          v25 = v20 - lpsz + 1;
          if ( v25 >= v12 )
            goto LABEL_434;
          *v20 = 0;
        }
        else
        {
          v25 = v12;
        }
        v27 = lpsz;
        v28 = *lpsz;
        if ( *lpsz )
        {
          if ( lpsz[v25 - 1] )
            goto LABEL_434;
LABEL_36:
          v29 = L" \t";
          v30 = 0;
          while ( *v29 )
          {
            if ( *v29 == v28 )
            {
              v27 = CharNextW(v27);
              v28 = *v27;
              if ( *v27 )
                goto LABEL_36;
              break;
            }
            v31 = CharNextW(v29);
            v29 = v31;
            if ( v31 )
            {
              v32 = v31 - L" \t";
              if ( (int)v32 > v30 )
              {
                v30 = v32;
                if ( (int)v32 < 3 )
                  continue;
              }
            }
            break;
          }
          v17 = lpsz;
          if ( v27 != lpsz )
          {
            v33 = v27 - lpsz;
            if ( v33 >= v25 )
              goto LABEL_434;
            _mm_lfence();
            v34 = v25 - v33;
            wmemmove_s_0(lpsz, v25, v27, v25 - v33);
            v17 = lpsz;
            lpsz[v34] = 0;
          }
        }
        v6 = (ConnectParameter *)this;
      }
      _mm_lfence();
      v243 = (wchar_t *)v17;
      v35 = wcschr_0(v17, 0x3Au);
      v36 = v35;
      v246 = v35;
      v37 = 11;
      if ( !v35 )
      {
        v7 = 0;
        v65 = -1;
        v64 = v243;
LABEL_135:
        _mm_lfence();
        if ( CompareStringW(0x800u, 0, v64, 2, L"\\\\", 2) == 2 )
        {
          v86 = (ConnectParameter *)this;
          v87 = (char *)(this + 768);
          if ( this[768] )
          {
            if ( *(_WORD *)v87 != 110 || this[769] != 112 || this[770] )
              goto LABEL_435;
          }
          else
          {
            v88 = (char *)((char *)L"np" - v87);
            do
            {
              if ( v37 == -2147483635 )
                break;
              v89 = *(_WORD *)&v88[(_QWORD)v87];
              if ( !v89 )
                break;
              *(_WORD *)v87 = v89;
              v87 += 2;
              --v37;
            }
            while ( v37 );
            v90 = v87 - 2;
            if ( v37 )
              v90 = v87;
            *(_WORD *)v90 = 0;
          }
          _mm_lfence();
          v91 = -1;
          do
            ++v91;
          while ( v64[v91] );
          if ( (unsigned int)v91 <= 0xFF )
          {
            _mm_lfence();
            StringCchCopyW(this + 779, 0x100u, v64);
            v92 = -1;
            v93 = -1;
            do
              ++v93;
            while ( v64[v93 + 2] );
            v94 = (_WORD *)StrChrW_SYS(v64 + 2, v93, 92);
            v95 = v94;
            if ( v94 )
            {
              _mm_lfence();
              *v94 = 0;
              if ( !(unsigned int)IsBlank(v64 + 2) )
              {
                _mm_lfence();
                StringCchCopyW(this + 256, 0x100u, v64 + 2);
                v96 = IsLocalHost(v64 + 2);
                v97 = 256;
                v98 = (ConnectParameter *)this;
                if ( v96 )
                {
                  do
                  {
                    if ( v97 == -2147483390 )
                      break;
                    v99 = *(_WORD *)((char *)v98 + (char *)&gwszComputerName - (char *)this);
                    if ( !v99 )
                      break;
                    *(_WORD *)v98 = v99;
                    v98 = (ConnectParameter *)((char *)v98 + 2);
                    --v97;
                  }
                  while ( v97 );
                  v100 = (ConnectParameter *)((char *)v98 - 2);
                  if ( v97 )
                    v100 = v98;
                  *(_WORD *)v100 = 0;
                }
                else
                {
                  _mm_lfence();
                  if ( (int)StringCchCopyW(this, 0x100u, v64 + 2) < 0 )
                    goto LABEL_435;
                }
                _mm_lfence();
                v101 = v95 + 1;
                v102 = -1;
                do
                  ++v102;
                while ( v101[v102] );
                v103 = StrChrW_SYS(v101, v102, 92);
                if ( v103 )
                {
                  _mm_lfence();
                  v104 = (const WCHAR *)(v103 + 2);
                  v105 = -1;
                  do
                    ++v105;
                  while ( v104[v105] );
                  if ( CompareStringW(0x800u, 0, (PCNZWCH)(v103 + 2), v105, L"sql\\query", 9) == 2 )
                  {
                    this[512] = 0;
                    *((_BYTE *)this + 3094) = 0;
                    v241 = 0;
                    goto LABEL_435;
                  }
                  _mm_lfence();
                  v106 = CompareStringW(0x800u, 0, v104, 6, L"mssql$", 6);
                  _mm_lfence();
                  if ( v106 == 2 )
                  {
                    v107 = -1;
                    do
                      ++v107;
                    while ( v104[v107] );
                    v108 = StrChrW_SYS(v104, v107, 92);
                    v109 = (_WORD *)v108;
                    if ( !v108 )
                      goto LABEL_435;
                    _mm_lfence();
                    v110 = (const WCHAR *)(v108 + 2);
                    v111 = -1;
                    do
                      ++v111;
                    while ( v110[v111] );
                    v112 = CompareStringW(0x800u, 0, v110, v111, L"sql\\query", 9);
                    _mm_lfence();
                    if ( v112 == 2 )
                    {
                      do
                        ++v92;
                      while ( v104[v92] );
                      v113 = StrChrW_SYS(v104, (unsigned int)v92, 36);
                      *v109 = 0;
                      if ( (int)StringCchCopyW(this + 512, 0x100u, (const wchar_t *)(v113 + 2)) >= 0 )
                      {
                        *((_BYTE *)this + 3094) = 0;
                        v241 = 0;
                      }
                      goto LABEL_435;
                    }
                  }
                  if ( (int)StringCchPrintf_lW(this + 512, 0x100u, L"pipe%s", 0, v104) < 0 )
                    goto LABEL_435;
                  *((_BYTE *)this + 3095) = 0;
                  *((_BYTE *)this + 3094) = 0;
LABEL_182:
                  v241 = 0;
                }
              }
            }
          }
LABEL_435:
          (*(void (__fastcall **)(struct ISOSHost_MemObj *, WCHAR *))(*(_QWORD *)g_pMO + 128LL))(g_pMO, lpsz);
          if ( v241 )
          {
            if ( !v7 )
            {
              if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`248'::_bidPtrSA_030_604[0] )
              {
                v235 = v241;
                SniErrorIdFromStringId(0xC3CDu);
                bidTraceW(
                  `ConnectParameter::ParseConnectionString'::`248'::_bidSrcFileA[0],
                  618496,
                  `ConnectParameter::ParseConnectionString'::`248'::_bidPtrSA_030_604[0],
                  8);
              }
              else
              {
                v235 = v241;
              }
              SNISetLastError(8, v235, 50125);
LABEL_447:
              if ( (bidGblFlags & 0x20002) == 0x20002
                && `ConnectParameter::ParseConnectionString'::`264'::_bidPtrSA_030_629[0] )
              {
                v236 = `ConnectParameter::ParseConnectionString'::`264'::_bidPtrSA_030_629[0];
                v237 = 644096;
                v238 = `ConnectParameter::ParseConnectionString'::`264'::_bidSrcFileA[0];
LABEL_456:
                bidTraceW(v238, v237, v236, v235);
                goto LABEL_457;
              }
              goto LABEL_457;
            }
          }
          else if ( (bidGblFlags & 0x20002) == 0x20002
                 && `ConnectParameter::ParseConnectionString'::`257'::_bidPtrSA_030_626[0] )
          {
            bidTraceW(
              `ConnectParameter::ParseConnectionString'::`257'::_bidSrcFileA[0],
              641024,
              `ConnectParameter::ParseConnectionString'::`257'::_bidPtrSA_030_626[0],
              (char *)v86 + 1536);
          }
          v235 = v241;
          goto LABEL_447;
        }
        _mm_lfence();
        v114 = wcschr_0(v64, 0x2Cu);
        if ( v114 )
        {
          _mm_lfence();
          *v114 = 0;
          v115 = v114 + 1;
          v116 = -1;
          do
            ++v116;
          while ( v115[v116] );
          v117 = (unsigned int)v116 + 1LL;
          v118 = *v115;
          if ( *v115 )
          {
            if ( v115[v117 - 1] )
              goto LABEL_434;
            v119 = v115;
            v120 = 0;
            do
            {
              v121 = L" \t";
              v122 = 0;
              while ( 1 )
              {
                if ( !*v121 )
                {
LABEL_195:
                  v120 = 0;
                  goto LABEL_196;
                }
                if ( *v121 == v118 )
                  break;
                v123 = CharNextW(v121);
                v121 = v123;
                if ( v123 )
                {
                  v124 = v123 - L" \t";
                  if ( (int)v124 > v122 )
                  {
                    v122 = v124;
                    if ( (int)v124 < 3 )
                      continue;
                  }
                }
                goto LABEL_195;
              }
              v126 = v119;
              if ( v120 )
                v126 = v120;
              v120 = v126;
LABEL_196:
              v119 = CharNextW(v119);
              v118 = *v119;
            }
            while ( *v119 );
            if ( v120 )
            {
              v125 = v120 - v115 + 1;
              if ( v125 >= v117 )
                goto LABEL_434;
              *v120 = 0;
            }
            else
            {
              v125 = v117;
            }
            v127 = v115;
            v128 = *v115;
            if ( *v115 )
            {
              if ( v115[v125 - 1] )
                goto LABEL_434;
LABEL_206:
              v129 = L" \t";
              v130 = 0;
              while ( *v129 )
              {
                if ( *v129 == v128 )
                {
                  v127 = CharNextW(v127);
                  v128 = *v127;
                  if ( *v127 )
                    goto LABEL_206;
                  break;
                }
                v131 = CharNextW(v129);
                v129 = v131;
                if ( v131 )
                {
                  v132 = v131 - L" \t";
                  if ( (int)v132 > v130 )
                  {
                    v130 = v132;
                    if ( (int)v132 < 3 )
                      continue;
                  }
                }
                break;
              }
              if ( v127 != v115 )
              {
                v133 = v127 - v115;
                if ( v133 >= v125 )
                  goto LABEL_434;
                _mm_lfence();
                v134 = v125 - v133;
                wmemmove_s_0(v115, v125, v127, v125 - v133);
                v115[v134] = 0;
              }
            }
          }
          v135 = (ConnectParameter *)this;
          v136 = (char *)(this + 768);
          if ( !this[768] )
          {
            v137 = 11;
            v138 = this + 768;
            do
            {
              if ( v137 == -2147483635 )
                break;
              v139 = *(_WORD *)((char *)v138 + (char *)L"tcp" - v136);
              if ( !v139 )
                break;
              *v138++ = v139;
              --v137;
            }
            while ( v137 );
            v140 = v138 - 1;
            if ( v137 )
              v140 = v138;
            *v140 = 0;
          }
          v141 = 0;
          do
          {
            v142 = aTcp_1[v141++];
            if ( v142 != *(_WORD *)&v136[2 * v141 - 2] )
            {
              v86 = (ConnectParameter *)this;
              goto LABEL_435;
            }
          }
          while ( v141 != 4 );
          v143 = 0;
          while ( 1 )
          {
            v144 = aTcp_1[v143++];
            if ( v144 != *(_WORD *)&v136[2 * v143 - 2] )
              break;
            if ( v143 == 4 )
            {
              _mm_lfence();
              v145 = wcschr_0(v115, 0x2Cu);
              if ( v145 )
              {
                _mm_lfence();
                *v145 = 0;
                v146 = -1;
                do
                  ++v146;
                while ( v115[v146] );
                v147 = (unsigned int)v146 + 1LL;
                v148 = *v115;
                if ( *v115 )
                {
                  if ( v115[v147 - 1] )
                    goto LABEL_434;
                  v149 = v115;
                  v150 = 0;
                  do
                  {
                    v151 = L" \t";
                    v152 = 0;
                    while ( 1 )
                    {
                      if ( !*v151 )
                      {
LABEL_243:
                        v150 = 0;
                        goto LABEL_244;
                      }
                      if ( *v151 == v148 )
                        break;
                      v153 = CharNextW(v151);
                      v151 = v153;
                      if ( v153 )
                      {
                        v154 = v153 - L" \t";
                        if ( (int)v154 > v152 )
                        {
                          v152 = v154;
                          if ( (int)v154 < 3 )
                            continue;
                        }
                      }
                      goto LABEL_243;
                    }
                    v156 = v149;
                    if ( v150 )
                      v156 = v150;
                    v150 = v156;
LABEL_244:
                    v149 = CharNextW(v149);
                    v148 = *v149;
                  }
                  while ( *v149 );
                  if ( v150 )
                  {
                    v155 = v150 - v115 + 1;
                    if ( v155 >= v147 )
                      goto LABEL_434;
                    *v150 = 0;
                  }
                  else
                  {
                    v155 = v147;
                  }
                  v157 = v115;
                  v158 = *v115;
                  if ( *v115 )
                  {
                    if ( v115[v155 - 1] )
                      goto LABEL_434;
LABEL_254:
                    v159 = L" \t";
                    v160 = 0;
                    while ( *v159 )
                    {
                      if ( *v159 == v158 )
                      {
                        v157 = CharNextW(v157);
                        v158 = *v157;
                        if ( *v157 )
                          goto LABEL_254;
                        break;
                      }
                      v161 = CharNextW(v159);
                      v159 = v161;
                      if ( v161 )
                      {
                        v162 = v161 - L" \t";
                        if ( (int)v162 > v160 )
                        {
                          v160 = v162;
                          if ( (int)v162 < 3 )
                            continue;
                        }
                      }
                      break;
                    }
                    if ( v157 != v115 )
                    {
                      v163 = v157 - v115;
                      if ( v163 >= v155 )
                        goto LABEL_434;
                      _mm_lfence();
                      v164 = v155 - v163;
                      wmemmove_s_0(v115, v155, v157, v155 - v163);
                      v115[v164] = 0;
                    }
                  }
                }
                v135 = (ConnectParameter *)this;
              }
              break;
            }
          }
          if ( !*v115 )
            goto LABEL_434;
          if ( *v115 == 92 )
            goto LABEL_434;
          _mm_lfence();
          v65 = -1;
          v165 = -1;
          do
            ++v165;
          while ( v115[v165] );
          if ( (unsigned int)v165 > 0xFF )
            goto LABEL_434;
          _mm_lfence();
          v64 = v243;
          if ( (unsigned int)IsBlank(v243) )
            goto LABEL_434;
          _mm_lfence();
          v166 = -1;
          do
            ++v166;
          while ( v115[v166] );
          v167 = (_WORD *)StrChrW_SYS(v115, v166, 92);
          if ( v167 )
            *v167 = 0;
          StringCchCopyW((wchar_t *)v135 + 779, 0x100u, v115);
          v8 = 1;
          v244 = 1;
          *((_BYTE *)v135 + 3094) = 0;
        }
        _mm_lfence();
        v168 = -1;
        do
          ++v168;
        while ( v64[v168] );
        v169 = (_WORD *)StrChrW_SYS(v64, v168, 92);
        if ( !v169 )
          goto LABEL_322;
        _mm_lfence();
        *v169 = 0;
        v170 = v169 + 1;
        v171 = -1;
        do
          ++v171;
        while ( v170[v171] );
        if ( (unsigned int)v171 > 0xFF )
          goto LABEL_434;
        _mm_lfence();
        if ( (unsigned int)IsBlank(v64) )
          goto LABEL_434;
        _mm_lfence();
        v172 = -1;
        do
          ++v172;
        while ( v170[v172] );
        v173 = (unsigned int)v172 + 1LL;
        v174 = *v170;
        if ( *v170 )
        {
          if ( v170[v173 - 1] )
            goto LABEL_434;
          v175 = v170;
          v176 = 0;
          do
          {
            v177 = L" \t";
            v178 = 0;
            while ( 1 )
            {
              if ( !*v177 )
              {
LABEL_295:
                v176 = 0;
                goto LABEL_296;
              }
              if ( *v177 == v174 )
                break;
              v179 = CharNextW(v177);
              v177 = v179;
              if ( v179 )
              {
                v180 = v179 - L" \t";
                if ( (int)v180 > v178 )
                {
                  v178 = v180;
                  if ( (int)v180 < 3 )
                    continue;
                }
              }
              goto LABEL_295;
            }
            v182 = v175;
            if ( v176 )
              v182 = v176;
            v176 = v182;
LABEL_296:
            v175 = CharNextW(v175);
            v174 = *v175;
          }
          while ( *v175 );
          v8 = v244;
          if ( v176 )
          {
            v181 = v176 - v170 + 1;
            if ( v181 >= v173 )
              goto LABEL_434;
            *v176 = 0;
          }
          else
          {
            v181 = v173;
          }
          v183 = v170;
          v184 = *v170;
          if ( *v170 )
          {
            if ( v170[v181 - 1] )
              goto LABEL_434;
LABEL_306:
            v185 = L" \t";
            v186 = 0;
            while ( *v185 )
            {
              if ( *v185 == v184 )
              {
                v183 = CharNextW(v183);
                v184 = *v183;
                if ( *v183 )
                  goto LABEL_306;
                break;
              }
              v187 = CharNextW(v185);
              v185 = v187;
              if ( v187 )
              {
                v188 = v187 - L" \t";
                if ( (int)v188 > v186 )
                {
                  v186 = v188;
                  if ( (int)v188 < 3 )
                    continue;
                }
              }
              break;
            }
            if ( v183 != v170 )
            {
              v189 = v183 - v170;
              if ( v189 >= v181 )
                goto LABEL_434;
              _mm_lfence();
              v190 = v181 - v189;
              wmemmove_s_0(v170, v181, v183, v181 - v189);
              v170[v190] = 0;
            }
          }
          v65 = -1;
          v64 = v243;
        }
        if ( !*v170 )
        {
LABEL_322:
          v86 = (ConnectParameter *)this;
          v191 = this + 512;
          v192 = 0;
          while ( aMssqlserver_0[v192] == v191[v192] && aMssqlserver_0[v192 + 1] == v191[v192 + 1] )
          {
            v192 += 2;
            if ( v192 == 12 )
              goto LABEL_326;
          }
          _mm_lfence();
          v193 = -1;
          do
            ++v193;
          while ( v64[v193] );
          if ( (unsigned int)v193 > 0xFF )
          {
LABEL_326:
            v7 = 0;
            goto LABEL_435;
          }
          _mm_lfence();
          do
            ++v65;
          while ( v64[v65] );
          v194 = (unsigned int)v65 + 1LL;
          v195 = *v64;
          if ( !*v64 )
            goto LABEL_363;
          if ( !v64[v194 - 1] )
          {
            v196 = 0;
            do
            {
              v197 = L" \t";
              v198 = 0;
              while ( 1 )
              {
                if ( !*v197 )
                {
LABEL_341:
                  v196 = 0;
                  goto LABEL_342;
                }
                if ( *v197 == v195 )
                  break;
                v199 = CharNextW(v197);
                v197 = v199;
                if ( v199 )
                {
                  v200 = v199 - L" \t";
                  if ( (int)v200 > v198 )
                  {
                    v198 = v200;
                    if ( (int)v200 < 3 )
                      continue;
                  }
                }
                goto LABEL_341;
              }
              v202 = v64;
              if ( v196 )
                v202 = v196;
              v196 = v202;
LABEL_342:
              v64 = CharNextW(v64);
              v195 = *v64;
            }
            while ( *v64 );
            v64 = v243;
            if ( v196 )
            {
              v201 = v196 - v243 + 1;
              if ( v201 >= v194 )
                goto LABEL_433;
              *v196 = 0;
            }
            else
            {
              v201 = v194;
            }
            v203 = v243;
            v204 = *v243;
            if ( !*v243 )
              goto LABEL_363;
            if ( !v243[v201 - 1] )
            {
LABEL_352:
              v205 = L" \t";
              v206 = 0;
              while ( *v205 )
              {
                if ( *v205 == v204 )
                {
                  v203 = CharNextW(v203);
                  v204 = *v203;
                  if ( *v203 )
                    goto LABEL_352;
                  break;
                }
                v207 = CharNextW(v205);
                v205 = v207;
                if ( v207 )
                {
                  v208 = v207 - L" \t";
                  if ( (int)v208 > v206 )
                  {
                    v206 = v208;
                    if ( (int)v208 < 3 )
                      continue;
                  }
                }
                break;
              }
              if ( v203 != v243 )
              {
                v209 = v203 - v243;
                if ( v209 < v201 )
                {
                  _mm_lfence();
                  v210 = v201 - v209;
                  wmemmove_s_0(v243, v201, v203, v201 - v209);
                  v243[v210] = 0;
                  goto LABEL_363;
                }
                goto LABEL_433;
              }
LABEL_363:
              _mm_lfence();
              v86 = (ConnectParameter *)this;
              v211 = 256;
              StringCchCopyW(this + 256, 0x100u, v64);
              if ( (unsigned int)IsBlank(v64) || (_mm_lfence(), IsLocalHost(v64)) )
              {
                v212 = 0;
                while ( 1 )
                {
                  v213 = aAdmin[v212++];
                  if ( v213 != this[v212 + 767] )
                    break;
                  if ( v212 == 6 )
                  {
                    v214 = (ConnectParameter *)this;
                    do
                    {
                      if ( v211 == -2147483390 )
                        break;
                      v215 = *(_WORD *)((char *)v214 + (char *)L"localhost" - (char *)this);
                      if ( !v215 )
                        break;
                      *(_WORD *)v214 = v215;
                      v214 = (ConnectParameter *)((char *)v214 + 2);
                      --v211;
                    }
                    while ( v211 );
                    goto LABEL_378;
                  }
                }
                v214 = (ConnectParameter *)this;
                do
                {
                  if ( v211 == -2147483390 )
                    break;
                  v216 = *(_WORD *)((char *)v214 + (char *)&gwszComputerName - (char *)this);
                  if ( !v216 )
                    break;
                  *(_WORD *)v214 = v216;
                  v214 = (ConnectParameter *)((char *)v214 + 2);
                  --v211;
                }
                while ( v211 );
LABEL_378:
                v217 = (ConnectParameter *)((char *)v214 - 2);
                if ( v211 )
                  v217 = v214;
                *(_WORD *)v217 = 0;
              }
              else
              {
                _mm_lfence();
                StringCchCopyW(this, 0x100u, v64);
              }
              v218 = (char *)(this + 768);
              v219 = 0;
              while ( 1 )
              {
                v220 = aLpc[v219++];
                if ( v220 != *(_WORD *)&v218[2 * v219 - 2] )
                  break;
                if ( v219 == 4 )
                {
                  if ( !IsLocalHost(this) )
                  {
                    if ( (bidGblFlags & 2) != 0
                      && `ConnectParameter::ParseConnectionString'::`190'::_bidPtrSA_030_539[0] )
                    {
                      SniErrorIdFromStringId(0xC3DDu);
                      bidTraceW(
                        `ConnectParameter::ParseConnectionString'::`190'::_bidSrcFileA[0],
                        551936,
                        `ConnectParameter::ParseConnectionString'::`190'::_bidPtrSA_030_539[0],
                        8);
                    }
                    SNISetLastError(8, 87, 50141);
                    v7 = 1;
                    goto LABEL_435;
                  }
                  break;
                }
              }
              StringCchCopyW(this + 1035, 0x200u, this);
              if ( *v191 )
              {
                StringCchCatW(this + 1035, 0x200u, L"\\");
                StringCchCatW(this + 1035, 0x200u, v191);
                v7 = 0;
                v221 = 0;
                while ( 1 )
                {
                  v222 = aLpc[v221++];
                  if ( v222 != *(_WORD *)&v218[2 * v221 - 2] )
                    break;
                  if ( v221 == 4 )
                  {
                    *((_BYTE *)this + 3094) = 0;
                    goto LABEL_399;
                  }
                }
                v223 = 0;
                while ( 1 )
                {
                  v224 = aAdmin[v223++];
                  if ( v224 != *(_WORD *)&v218[2 * v223 - 2] )
                    break;
                  if ( v223 == 6 )
                  {
                    *((_BYTE *)this + 3094) = 0;
                    break;
                  }
                }
              }
              else
              {
                *((_BYTE *)this + 3094) = 0;
                v7 = 0;
              }
LABEL_399:
              if ( !a3 )
                goto LABEL_182;
              if ( *(_WORD *)v218 == 110 && this[769] == 112 && !this[770] )
              {
LABEL_414:
                v241 = 87;
                if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`212'::_bidPtrSA_030_571[0] )
                {
                  SniErrorIdFromStringId(0xC3E5u);
                  bidTraceW(
                    `ConnectParameter::ParseConnectionString'::`212'::_bidSrcFileA[0],
                    584704,
                    `ConnectParameter::ParseConnectionString'::`212'::_bidPtrSA_030_571[0],
                    8);
                }
                SNISetLastError(8, 87, 50149);
                v7 = 1;
              }
              else
              {
                v225 = 0;
                while ( 1 )
                {
                  v226 = aVia[v225++];
                  if ( v226 != *(_WORD *)&v218[2 * v225 - 2] )
                    break;
                  if ( v225 == 4 )
                    goto LABEL_414;
                }
                v227 = 0;
                while ( 1 )
                {
                  v228 = aLpc[v227++];
                  if ( v228 != *(_WORD *)&v218[2 * v227 - 2] )
                    break;
                  if ( v227 == 4 )
                    goto LABEL_414;
                }
                v229 = 0;
                while ( 1 )
                {
                  v230 = aAdmin[v229++];
                  if ( v230 != *(_WORD *)&v218[2 * v229 - 2] )
                    break;
                  if ( v229 == 6 )
                    goto LABEL_414;
                }
                if ( *(_WORD *)v218 )
                  goto LABEL_182;
                v231 = (char *)((char *)L"tcp" - v218);
                v232 = 11;
                do
                {
                  if ( v232 == -2147483635 )
                    break;
                  v233 = *(_WORD *)&v231[(_QWORD)v218];
                  if ( !v233 )
                    break;
                  *(_WORD *)v218 = v233;
                  v218 += 2;
                  --v232;
                }
                while ( v232 );
                v234 = v218 - 2;
                if ( v232 )
                  v234 = v218;
                *(_WORD *)v234 = 0;
                if ( v232 )
                  goto LABEL_182;
                if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`226'::_bidPtrSA_030_583[0] )
                {
                  _mm_lfence();
                  bidTraceW(
                    `ConnectParameter::ParseConnectionString'::`226'::_bidSrcFileA[0],
                    596992,
                    `ConnectParameter::ParseConnectionString'::`226'::_bidPtrSA_030_583[0],
                    2147942522LL);
                }
                v241 = 87;
                if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`234'::_bidPtrSA_030_586[0] )
                {
                  SniErrorIdFromStringId(0xC3B4u);
                  bidTraceW(
                    `ConnectParameter::ParseConnectionString'::`234'::_bidSrcFileA[0],
                    600064,
                    `ConnectParameter::ParseConnectionString'::`234'::_bidPtrSA_030_586[0],
                    8);
                }
                SNISetLastError(8, 87, 50100);
                v7 = 1;
              }
              goto LABEL_435;
            }
          }
LABEL_433:
          v7 = 0;
          goto LABEL_434;
        }
        _mm_lfence();
        if ( !(unsigned int)IsBlank(v170) )
        {
          if ( !v8 )
          {
            _mm_lfence();
            StringCchCopyW(this + 512, 0x100u, v170);
          }
          goto LABEL_322;
        }
LABEL_434:
        v86 = (ConnectParameter *)this;
        goto LABEL_435;
      }
      *v35 = 0;
      if ( (__int64)(((char *)v35 - (char *)lpsz) & 0xFFFFFFFFFFFFFFFEuLL) > 20 )
        goto LABEL_433;
      _mm_lfence();
      v38 = (wchar_t *)((char *)v6 + 1536);
      StringCchCopyW((wchar_t *)v6 + 768, 0xBu, lpsz);
      v39 = -1;
      do
        ++v39;
      while ( v38[v39] );
      v40 = (unsigned int)v39 + 1LL;
      v41 = *v38;
      if ( *v38 )
      {
        if ( v38[v40 - 1] )
          goto LABEL_433;
        v42 = (const WCHAR *)((char *)v6 + 1536);
        v43 = 0;
        do
        {
          v44 = L" \t";
          v45 = 0;
          while ( 1 )
          {
            if ( !*v44 )
            {
LABEL_61:
              v43 = 0;
              goto LABEL_62;
            }
            if ( *v44 == v41 )
              break;
            v46 = CharNextW(v44);
            v44 = v46;
            if ( v46 )
            {
              v47 = v46 - L" \t";
              if ( (int)v47 > v45 )
              {
                v45 = v47;
                if ( (int)v47 < 3 )
                  continue;
              }
            }
            goto LABEL_61;
          }
          v49 = v42;
          if ( v43 )
            v49 = v43;
          v43 = v49;
LABEL_62:
          v42 = CharNextW(v42);
          v41 = *v42;
        }
        while ( *v42 );
        v36 = v246;
        if ( v43 )
        {
          v48 = v43 - v38 + 1;
          if ( v48 >= v40 )
            goto LABEL_433;
          *v43 = 0;
        }
        else
        {
          v48 = v40;
        }
        v50 = v38;
        v51 = *v38;
        if ( *v38 )
        {
          if ( v38[v48 - 1] )
            goto LABEL_433;
LABEL_72:
          v52 = L" \t";
          v53 = 0;
          while ( *v52 )
          {
            if ( *v52 == v51 )
            {
              v50 = CharNextW(v50);
              v51 = *v50;
              if ( *v50 )
                goto LABEL_72;
              break;
            }
            v54 = CharNextW(v52);
            v52 = v54;
            if ( v54 )
            {
              v55 = v54 - L" \t";
              if ( (int)v55 > v53 )
              {
                v53 = v55;
                if ( (int)v55 < 3 )
                  continue;
              }
            }
            break;
          }
          if ( v50 != v38 )
          {
            v56 = v50 - v38;
            if ( v56 >= v48 )
              goto LABEL_433;
            _mm_lfence();
            v57 = v48 - v56;
            wmemmove_s_0(v38, v48, v50, v48 - v56);
            v38[v57] = 0;
          }
        }
      }
      if ( v36 == lpsz )
      {
LABEL_131:
        *v36 = 58;
        v7 = 0;
        *v38 = 0;
      }
      else
      {
        v58 = 0;
        while ( 1 )
        {
          v59 = aTcp_1[v58++];
          if ( v59 != v38[v58 - 1] )
            break;
          if ( v58 == 4 )
            goto LABEL_98;
        }
        if ( *v38 != 110 || v38[1] != 112 || v38[2] )
        {
          v60 = 0;
          while ( 1 )
          {
            v61 = aLpc[v60++];
            if ( v61 != v38[v60 - 1] )
              break;
            if ( v60 == 4 )
              goto LABEL_98;
          }
          v62 = 0;
          do
          {
            v63 = aAdmin[v62++];
            if ( v63 != v38[v62 - 1] )
              goto LABEL_131;
          }
          while ( v62 != 6 );
        }
LABEL_98:
        _mm_lfence();
        v64 = v36 + 1;
        v243 = v36 + 1;
        v65 = -1;
        v66 = -1;
        do
          ++v66;
        while ( v64[v66] );
        v67 = (unsigned int)v66 + 1LL;
        v68 = *v64;
        v7 = 0;
        if ( !*v64 )
          goto LABEL_134;
        if ( v64[v67 - 1] )
          goto LABEL_434;
        v69 = 0;
        do
        {
          v70 = L" \t";
          v71 = 0;
          while ( 1 )
          {
            if ( !*v70 )
            {
LABEL_109:
              v69 = 0;
              goto LABEL_110;
            }
            if ( *v70 == v68 )
              break;
            v72 = CharNextW(v70);
            v70 = v72;
            if ( v72 )
            {
              v73 = v72 - L" \t";
              if ( (int)v73 > v71 )
              {
                v71 = v73;
                if ( (int)v73 < 3 )
                  continue;
              }
            }
            goto LABEL_109;
          }
          v75 = v64;
          if ( v69 )
            v75 = v69;
          v69 = v75;
LABEL_110:
          v64 = CharNextW(v64);
          v68 = *v64;
        }
        while ( *v64 );
        if ( v69 )
        {
          v74 = v69 - v243 + 1;
          if ( v74 >= v67 )
            goto LABEL_434;
          *v69 = 0;
        }
        else
        {
          v74 = v67;
        }
        v76 = v243;
        v77 = *v243;
        if ( *v243 )
        {
          if ( v243[v74 - 1] )
            goto LABEL_434;
LABEL_120:
          v78 = L" \t";
          v79 = 0;
          while ( *v78 )
          {
            if ( *v78 == v77 )
            {
              v76 = CharNextW(v76);
              v77 = *v76;
              if ( *v76 )
                goto LABEL_120;
              break;
            }
            v80 = CharNextW(v78);
            v78 = v80;
            if ( v80 )
            {
              v81 = v80 - L" \t";
              if ( (int)v81 > v79 )
              {
                v79 = v81;
                if ( (int)v81 < 3 )
                  continue;
              }
            }
            break;
          }
          if ( v76 != v243 )
          {
            v82 = v76 - v243;
            if ( v82 >= v74 )
              goto LABEL_434;
            _mm_lfence();
            v83 = v74 - v82;
            v84 = v74 - v82;
            v85 = v74;
            v64 = v243;
            wmemmove_s_0(v243, v85, v76, v84);
            v243[v83] = 0;
LABEL_133:
            v65 = -1;
LABEL_134:
            v37 = 11;
            goto LABEL_135;
          }
        }
      }
      v64 = v243;
      goto LABEL_133;
    }
  }
  v235 = 14;
  if ( (bidGblFlags & 2) != 0 && `ConnectParameter::ParseConnectionString'::`20'::_bidPtrSA_030_139[0] )
  {
    SniErrorIdFromStringId(0xC3B4u);
    bidTraceW(
      `ConnectParameter::ParseConnectionString'::`20'::_bidSrcFileA[0],
      142336,
      `ConnectParameter::ParseConnectionString'::`20'::_bidPtrSA_030_139[0],
      8);
  }
  SNISetLastError(8, 14, 50100);
  if ( (bidGblFlags & 0x20002) == 0x20002 && `ConnectParameter::ParseConnectionString'::`27'::_bidPtrSA_030_140[0] )
  {
    v236 = `ConnectParameter::ParseConnectionString'::`27'::_bidPtrSA_030_140[0];
    v237 = 143360;
    v238 = `ConnectParameter::ParseConnectionString'::`27'::_bidSrcFileA[0];
    goto LABEL_456;
  }
LABEL_457:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v247);
  return v235;
}

```

## disassembly

```asm
0x180153e00  mov     r11, rsp
0x180153e03  mov     [r11+18h], rbx
0x180153e07  push    rbp
0x180153e08  push    rsi
0x180153e09  push    rdi
0x180153e0a  push    r12
0x180153e0c  push    r13
0x180153e0e  push    r14
0x180153e10  push    r15
0x180153e12  sub     rsp, 0A0h
0x180153e19  mov     rax, cs:__security_cookie
0x180153e20  xor     rax, rsp
0x180153e23  mov     [rsp+0D8h+var_40], rax
0x180153e2b  movzx   ebx, r8b
0x180153e2f  mov     [rsp+0D8h+var_6C], bl
0x180153e33  mov     rdi, rdx
0x180153e36  mov     r14, rcx
0x180153e39  mov     [rsp+0D8h+lpString2], rcx
0x180153e3e  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180153e45  mov     [r11-48h], rbp
0x180153e49  mov     eax, cs:_bidGblFlags
0x180153e4f  and     eax, 20004h
0x180153e54  cmp     eax, 20004h
0x180153e59  jnz     short loc_180153E7A
0x180153e5b  mov     rax, cs:?_bidPtrSA_040_118@?6??ParseConnectionString@ConnectParameter@@QEAAKPEB_W_N@Z@4REB_WEB; wchar_t const * const `ConnectParameter::ParseConnectionString(wchar_t const *,bool)'::`7'::_bidPtrSA_040_118
0x180153e62  test    rax, rax
0x180153e65  jz      short loc_180153E7A
0x180153e67  mov     r8, rdx
0x180153e6a  mov     rdx, cs:?_bidPtrSA_040_118@?6??ParseConnectionString@ConnectParameter@@QEAAKPEB_W_N@Z@4REB_WEB; wchar_t const * const `ConnectParameter::ParseConnectionString(wchar_t const *,bool)'::`7'::_bidPtrSA_040_118
0x180153e71  lea     rcx, [r11-48h]
0x180153e75  call    _bidScopeEnterW
0x180153e7a  xor     r12d, r12d
0x180153e7d  mov     r13d, r12d
0x180153e80  mov     [rsp+0D8h+var_60], r12d
0x180153e85  mov     [r14+0C18h], bl
0x180153e8c  cmp     [r14+0C16h], r12b
0x180153e93  jz      short loc_180153E9D
0x180153e95  test    bl, bl
0x180153e97  jnz     short loc_180153E9D
0x180153e99  mov     al, 1
0x180153e9b  jmp     short loc_180153E9F
0x180153e9d  xor     al, al
0x180153e9f  mov     [r14+0C16h], al
0x180153ea6  mov     rbx, rbp
0x180153ea9  nop     dword ptr [rax+00000000h]
0x180153eb0  inc     rbx
0x180153eb3  cmp     [rdi+rbx*2], r12w
0x180153eb8  jnz     short loc_180153EB0
0x180153eba  cmp     ebx, 0FFFFFFFFh
0x180153ebd  jz      loc_180155636
0x180153ec3  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x180153eca  mov     esi, ebx
0x180153ecc  lea     r15, [rsi+1]
0x180153ed0  mov     eax, 2
0x180153ed5  mul     r15
0x180153ed8  mov     rdx, rax
0x180153edb  cmovb   rdx, rbp
0x180153edf  mov     rax, [rcx]
0x180153ee2  mov     rax, [rax+70h]
0x180153ee6  call    cs:__guard_dispatch_icall_fptr
0x180153eec  mov     [rsp+0D8h+lpsz], rax
0x180153ef4  test    rax, rax
0x180153ef7  jz      loc_180155636
0x180153efd  mov     [rsp+0D8h+var_70], 57h ; 'W'
0x180153f05  inc     ebx
0x180153f07  mov     [rsp+0D8h+cchDest], ebx; cchDest
0x180153f0b  mov     [rsp+0D8h+lpDestStr], rax; lpDestStr
0x180153f10  mov     r9d, ebp; cchSrc
0x180153f13  mov     r8, rdi; lpSrcStr
0x180153f16  mov     edx, 100h; dwMapFlags
0x180153f1b  mov     ecx, 800h; Locale
0x180153f20  call    cs:__imp_LCMapStringW
0x180153f26  test    eax, eax
0x180153f28  jz      loc_1801554C2
0x180153f2e  cmp     eax, ebx
0x180153f30  ja      loc_1801554C2
0x180153f36  mov     rcx, [rsp+0D8h+lpsz]
0x180153f3e  mov     [rcx+rsi*2], r12w
0x180153f43  movzx   edi, word ptr [rcx]
0x180153f46  test    di, di
0x180153f49  jz      loc_1801540B7
0x180153f4f  cmp     r12w, [rcx+r15*2-2]
0x180153f55  jnz     loc_1801554C2
0x180153f5b  mov     r14, rcx
0x180153f5e  mov     rsi, r12
0x180153f61  lea     rbp, sz; " \t"
0x180153f68  nop     dword ptr [rax+rax+00000000h]
0x180153f70  mov     rcx, rbp; lpsz
0x180153f73  mov     ebx, r12d
0x180153f76  movzx   eax, word ptr [rcx]
0x180153f79  test    ax, ax
0x180153f7c  jz      short loc_180153FA2
0x180153f7e  cmp     ax, di
0x180153f81  jz      short loc_180153FE1
0x180153f83  call    cs:__imp_CharNextW
0x180153f89  mov     rcx, rax
0x180153f8c  test    rax, rax
0x180153f8f  jz      short loc_180153FA2
0x180153f91  sub     rax, rbp
0x180153f94  sar     rax, 1
0x180153f97  cmp     eax, ebx
0x180153f99  jle     short loc_180153FA2
0x180153f9b  mov     ebx, eax
0x180153f9d  cmp     eax, 3
0x180153fa0  jl      short loc_180153F76
0x180153fa2  mov     rsi, r12
0x180153fa5  mov     rcx, r14; lpsz
0x180153fa8  call    cs:__imp_CharNextW
0x180153fae  mov     r14, rax
0x180153fb1  movzx   edi, word ptr [rax]
0x180153fb4  test    di, di
0x180153fb7  jnz     short loc_180153F70
0x180153fb9  mov     rcx, [rsp+0D8h+lpsz]
0x180153fc1  test    rsi, rsi
0x180153fc4  jz      short loc_180153FF0
0x180153fc6  mov     rbp, rsi
0x180153fc9  sub     rbp, rcx
0x180153fcc  sar     rbp, 1
0x180153fcf  inc     rbp
0x180153fd2  cmp     rbp, r15
0x180153fd5  jnb     loc_1801554C2
0x180153fdb  mov     [rsi], r12w
0x180153fdf  jmp     short loc_180153FF3
0x180153fe1  mov     rax, r14
0x180153fe4  test    rsi, rsi
0x180153fe7  cmovnz  rax, rsi
0x180153feb  mov     rsi, rax
0x180153fee  jmp     short loc_180153FA5
0x180153ff0  mov     rbp, r15
0x180153ff3  mov     rsi, rcx
0x180153ff6  movzx   edi, word ptr [rcx]
0x180153ff9  test    di, di
0x180153ffc  jz      loc_1801540AB
0x180154002  cmp     r12w, [rcx+rbp*2-2]
0x180154008  jnz     loc_1801554C2
0x18015400e  lea     r14, sz; " \t"
0x180154015  nop     word ptr [rax+rax+00000000h]
0x180154020  mov     rcx, r14; lpsz
0x180154023  mov     ebx, r12d
0x180154026  movzx   eax, word ptr [rcx]
0x180154029  test    ax, ax
0x18015402c  jz      short loc_180154068
0x18015402e  cmp     ax, di
0x180154031  jz      short loc_180154054
0x180154033  call    cs:__imp_CharNextW
0x180154039  mov     rcx, rax
0x18015403c  test    rax, rax
0x18015403f  jz      short loc_180154068
0x180154041  sub     rax, r14
0x180154044  sar     rax, 1
0x180154047  cmp     eax, ebx
0x180154049  jle     short loc_180154068
0x18015404b  mov     ebx, eax
0x18015404d  cmp     eax, 3
0x180154050  jl      short loc_180154026
0x180154052  jmp     short loc_180154068
0x180154054  mov     rcx, rsi; lpsz
0x180154057  call    cs:__imp_CharNextW
0x18015405d  mov     rsi, rax
0x180154060  movzx   edi, word ptr [rax]
0x180154063  test    di, di
0x180154066  jnz     short loc_180154020
0x180154068  mov     rcx, [rsp+0D8h+lpsz]; S1
0x180154070  cmp     rsi, rcx
0x180154073  jz      short loc_1801540AB
0x180154075  mov     rax, rsi
0x180154078  sub     rax, rcx
0x18015407b  sar     rax, 1
0x18015407e  cmp     rax, rbp
0x180154081  jnb     loc_1801554C2
0x180154087  lfence
0x18015408a  mov     rbx, rbp
0x18015408d  sub     rbx, rax
0x180154090  mov     r9, rbx; N
0x180154093  mov     r8, rsi; S2
0x180154096  mov     rdx, rbp; N1
0x180154099  call    wmemmove_s_0
0x18015409e  mov     rcx, [rsp+0D8h+lpsz]; Str
0x1801540a6  mov     [rcx+rbx*2], r12w
0x1801540ab  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1801540b2  mov     r14, [rsp+0D8h+lpString2]
0x1801540b7  lfence
0x1801540ba  mov     [rsp+0D8h+var_68], rcx
0x1801540bf  mov     edx, 3Ah ; ':'; Ch
0x1801540c4  call    wcschr_0
0x1801540c9  mov     r12, rax
0x1801540cc  mov     [rsp+0D8h+var_50], rax
0x1801540d4  mov     edi, 0Bh
0x1801540d9  lea     rsi, aTcp_1; "tcp"
0x1801540e0  test    rax, rax
0x1801540e3  jz      loc_180154563
0x1801540e9  xor     ebx, ebx
0x1801540eb  mov     [rax], bx
0x1801540ee  mov     rcx, rax
0x1801540f1  mov     rax, [rsp+0D8h+lpsz]
0x1801540f9  sub     rcx, rax
0x1801540fc  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180154100  cmp     rcx, 14h
0x180154104  jg      loc_1801554BF
0x18015410a  lfence
0x18015410d  lea     r15, [r14+600h]
0x180154114  mov     r8, rax; wchar_t *
0x180154117  mov     edx, edi; unsigned __int64
0x180154119  mov     rcx, r15; wchar_t *
0x18015411c  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180154121  mov     rax, rbp
0x180154124  inc     rax
0x180154127  cmp     [r15+rax*2], bx
0x18015412c  jnz     short loc_180154124
0x18015412e  mov     ebp, eax
0x180154130  inc     rbp
0x180154133  movzx   edi, word ptr [r15]
0x180154137  test    di, di
0x18015413a  jz      loc_180154299
0x180154140  cmp     bx, [r15+rbp*2-2]
0x180154146  jnz     loc_1801554BF
0x18015414c  mov     r14, r15
0x18015414f  mov     rsi, r13
0x180154152  lea     r12, sz; " \t"
0x180154159  nop     dword ptr [rax+00000000h]
0x180154160  mov     rcx, r12; lpsz
0x180154163  mov     ebx, r13d
0x180154166  movzx   eax, word ptr [rcx]
0x180154169  test    ax, ax
0x18015416c  jz      short loc_180154192
0x18015416e  cmp     ax, di
0x180154171  jz      short loc_1801541D2
0x180154173  call    cs:__imp_CharNextW
0x180154179  mov     rcx, rax
0x18015417c  test    rax, rax
0x18015417f  jz      short loc_180154192
0x180154181  sub     rax, r12
0x180154184  sar     rax, 1
0x180154187  cmp     eax, ebx
0x180154189  jle     short loc_180154192
0x18015418b  mov     ebx, eax
0x18015418d  cmp     eax, 3
0x180154190  jl      short loc_180154166
0x180154192  mov     rsi, r13
0x180154195  mov     rcx, r14; lpsz
0x180154198  call    cs:__imp_CharNextW
0x18015419e  mov     r14, rax
0x1801541a1  movzx   edi, word ptr [rax]
0x1801541a4  test    di, di
0x1801541a7  jnz     short loc_180154160
0x1801541a9  test    rsi, rsi
0x1801541ac  mov     r12, [rsp+0D8h+var_50]
0x1801541b4  jz      short loc_1801541E1
0x1801541b6  mov     r14, rsi
0x1801541b9  sub     r14, r15
0x1801541bc  sar     r14, 1
0x1801541bf  inc     r14
0x1801541c2  cmp     r14, rbp
0x1801541c5  jnb     loc_1801554BF
0x1801541cb  xor     ebx, ebx
0x1801541cd  mov     [rsi], bx
0x1801541d0  jmp     short loc_1801541E6
0x1801541d2  mov     rax, r14
0x1801541d5  test    rsi, rsi
0x1801541d8  cmovnz  rax, rsi
0x1801541dc  mov     rsi, rax
0x1801541df  jmp     short loc_180154195
0x1801541e1  mov     r14, rbp
0x1801541e4  xor     ebx, ebx
0x1801541e6  mov     rsi, r15
0x1801541e9  movzx   edi, word ptr [r15]
0x1801541ed  test    di, di
0x1801541f0  jz      loc_180154292
0x1801541f6  cmp     bx, [r15+r14*2-2]
0x1801541fc  jnz     loc_1801554BF
0x180154202  lea     rbp, sz; " \t"
0x180154209  nop     dword ptr [rax+00000000h]
0x180154210  mov     rcx, rbp; lpsz
0x180154213  mov     ebx, r13d
0x180154216  movzx   eax, word ptr [rcx]
0x180154219  test    ax, ax
0x18015421c  jz      short loc_180154258
0x18015421e  cmp     ax, di
0x180154221  jz      short loc_180154244
0x180154223  call    cs:__imp_CharNextW
0x180154229  mov     rcx, rax
0x18015422c  test    rax, rax
0x18015422f  jz      short loc_180154258
0x180154231  sub     rax, rbp
0x180154234  sar     rax, 1
0x180154237  cmp     eax, ebx
0x180154239  jle     short loc_180154258
0x18015423b  mov     ebx, eax
0x18015423d  cmp     eax, 3
0x180154240  jl      short loc_180154216
0x180154242  jmp     short loc_180154258
0x180154244  mov     rcx, rsi; lpsz
0x180154247  call    cs:__imp_CharNextW
0x18015424d  mov     rsi, rax
0x180154250  movzx   edi, word ptr [rax]
0x180154253  test    di, di
0x180154256  jnz     short loc_180154210
0x180154258  cmp     rsi, r15
0x18015425b  jz      short loc_180154290
0x18015425d  mov     rax, rsi
  ... truncated ...
```
