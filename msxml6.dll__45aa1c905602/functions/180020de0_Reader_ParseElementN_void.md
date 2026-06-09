# Reader::ParseElementN(void)

- ea: `0x180020de0`
- end: `0x180023370`
- name: `?ParseElementN@Reader@@AEAAXXZ`
- size: `9616`
- prototype: `void __fastcall(Reader *this)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020de0`
- `0x18003b36c`

## callees

- `0x180017480`
- `0x18001d5d0`
- `0x18001e090`
- `0x18001e330`
- `0x18001e584`
- `0x18001e5ac`
- `0x18001e6f0`
- `0x18002086c`
- `0x1800208a0`
- `0x180020adc`
- `0x180020de0`
- `0x180023380`
- `0x18003b560`
- `0x18003b7b0`
- `0x180044b1c`
- `0x180044e64`
- `0x18004d294`
- `0x1800505e0`
- `0x1800506c0`
- `0x180050790`
- `0x180060f00`
- `0x18006f2d4`
- `0x180076cdc`
- `0x1800bde70`
- `0x1800be55c`
- `0x1800c090c`
- `0x1800c1bb4`
- `0x1800cc51c`
- `0x1800cc6c0`
- `0x1800cd3e4`
- `0x180178b5c`
- `0x18017c1cc`
- `0x18017c1d8`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800230d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023178`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800230d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023178`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180023106`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800231aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180023106`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800231aa`

## string_xrefs

- `0x1800230e3`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`
- `0x180023187`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`

## pseudocode

```c
void __fastcall Reader::ParseElementN(Reader *this)
{
  unsigned int ulMaxElementDepth; // eax
  BlockAlloc::Header *pBlock; // rsi
  CharacterSource *pCharacterSource; // rdx
  unsigned __int8 *pCurr; // r15
  SourceType sourceType; // eax
  unsigned int v7; // edi
  unsigned __int8 *v8; // r14
  unsigned int v9; // eax
  CharacterSource *v10; // r9
  unsigned int v11; // edi
  SourceType v12; // eax
  __int64 pwh_low; // rsi
  char *v14; // r8
  unsigned __int16 *pbSeg; // rdx
  unsigned __int64 v16; // r10
  __int64 v17; // rax
  int nNsPrefix; // edi
  BlockAlloc::Header *v19; // rax
  unsigned __int8 *v20; // r12
  __int64 lSize; // r14
  char *pStack; // r15
  char *v23; // rdi
  char *v24; // rsi
  __int64 v25; // rdx
  char *k; // r14
  __int64 v27; // rax
  __int64 v28; // rdx
  int v29; // r10d
  char *v30; // r9
  int nContext; // r8d
  __int64 v32; // rdx
  const wchar_t *v33; // r13
  __int64 v34; // r8
  StringPtr *v35; // rdx
  StringPtr *pLastNsUri; // rax
  bool v37; // zf
  unsigned int v38; // r14d
  const wchar_t *pwh; // rdi
  IMXRContentHandler *v40; // rcx
  int v41; // r15d
  HRESULT v42; // eax
  HRESULT v43; // esi
  BlockAlloc::Header *v44; // rax
  int v45; // r12d
  int nToken; // eax
  CharacterSource *v47; // rdx
  int v48; // r14d
  SourceType v49; // eax
  unsigned int v50; // edi
  BlockAlloc::Header *v51; // rsi
  wchar_t *v52; // r9
  CharacterSource *v53; // r10
  unsigned int v54; // edi
  SourceType v55; // eax
  __int64 v56; // rsi
  BlockAlloc::Header *pNext; // rax
  wchar_t *v58; // r8
  unsigned __int16 *v59; // rdx
  unsigned __int64 v60; // r11
  int v61; // edi
  __int64 v62; // rdx
  char *v63; // r9
  int v64; // r8d
  __int64 mm; // rdx
  NamespaceSupport *p_nsSupport; // rdi
  __int64 v67; // r8
  int v68; // edx
  BlockAlloc::Header *v69; // rax
  unsigned __int8 *v70; // rdx
  __int64 v71; // rcx
  BlockAlloc::Header *v72; // rax
  unsigned __int64 v73; // rcx
  __int64 v74; // r14
  char *v75; // rax
  __int64 v76; // rax
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int64 v79; // rcx
  char *v80; // rax
  __int128 v81; // xmm0
  __int128 v82; // xmm1
  __int128 v83; // xmm0
  bool v84; // al
  size_t v85; // r8
  unsigned int v86; // esi
  unsigned __int8 *v87; // rdx
  CharacterSource *v88; // rdx
  BlockAlloc::Header *v89; // rsi
  SourceType v90; // eax
  unsigned __int8 *v91; // r15
  unsigned int v92; // edi
  wchar_t *v93; // r10
  BlockAlloc::Header *v94; // rax
  unsigned __int64 v95; // rax
  __int64 v96; // r14
  char *v97; // rax
  size_t v98; // r8
  char *v99; // rax
  __int64 v100; // rcx
  __int128 v101; // xmm4
  __int128 v102; // xmm3
  __int128 v103; // xmm2
  __int128 v104; // xmm1
  unsigned __int64 v105; // rcx
  __int64 v106; // r14
  char *v107; // rax
  CharacterSource *v108; // r9
  unsigned int v109; // edi
  SourceType v110; // eax
  __int64 v111; // rsi
  BlockAlloc::Header *v112; // rax
  const wchar_t *v113; // r12
  bool v114; // al
  wchar_t *v115; // r8
  unsigned __int16 *v116; // rdx
  unsigned __int64 v117; // r11
  size_t v118; // r8
  char *v119; // r8
  unsigned __int16 *v120; // rdx
  unsigned __int64 v121; // r10
  wchar_t *v122; // r8
  unsigned __int16 *v123; // rdx
  unsigned __int64 v124; // r11
  BlockAlloc::Header *kk; // rcx
  BlockAlloc::Header *v126; // rdi
  unsigned __int8 *v127; // r14
  BlockAlloc::Header *v128; // rax
  unsigned __int64 v129; // rax
  __int64 v130; // rsi
  char *v131; // rax
  CharacterSource *v132; // rdx
  BlockAlloc::Header *v133; // rsi
  SourceType v134; // eax
  unsigned __int8 *v135; // r15
  unsigned int v136; // edi
  wchar_t *v137; // r10
  BlockAlloc::Header *v138; // rax
  CharacterSource *v139; // r9
  unsigned int v140; // edi
  SourceType v141; // eax
  __int64 v142; // rsi
  BlockAlloc::Header *v143; // rax
  BlockAlloc::Header *nn; // rcx
  char *v145; // r8
  unsigned __int8 *v146; // rdx
  unsigned __int64 v147; // r10
  __int64 v148; // rcx
  ISAXLexicalHandler *v149; // rcx
  unsigned __int8 *v150; // r14
  HRESULT v151; // esi
  __int64 v152; // rcx
  __int64 v153; // rax
  __int64 v154; // r15
  __int64 v155; // rcx
  void (__fastcall ***v156)(_QWORD, __int64); // rcx
  ISAXLexicalHandler *v157; // r14
  HRESULT (__fastcall *endEntity)(ISAXLexicalHandler *, const wchar_t *, int); // rsi
  int v159; // edi
  const wchar_t **v160; // rax
  HRESULT v161; // eax
  HRESULT v162; // edi
  CharacterSource *v163; // rdx
  BlockAlloc::Header *v164; // r14
  SourceType v165; // eax
  unsigned __int8 *v166; // r15
  unsigned int v167; // edi
  BlockAlloc::Header *v168; // rax
  unsigned __int64 v169; // rax
  __int64 v170; // rsi
  char *v171; // rax
  wchar_t *v172; // r8
  unsigned __int8 *v173; // rdx
  unsigned __int64 v174; // r11
  unsigned int v175; // ecx
  StringPtr *pLastPrefix; // rdx
  int v177; // eax
  int v178; // edx
  char *v179; // r8
  int v180; // r9d
  char *i; // r14
  unsigned int v182; // r15d
  __int64 cHashAttributes; // rax
  unsigned int m; // esi
  unsigned int v185; // r11d
  unsigned int v186; // eax
  unsigned int v187; // r10d
  unsigned __int64 v188; // rdx
  unsigned int *pHashAttributes; // rax
  unsigned int v190; // eax
  wchar_t *v191; // r8
  unsigned __int16 *v192; // rdx
  unsigned __int64 v193; // r11
  wchar_t *v194; // rdx
  BlockAlloc::Header *v195; // rax
  unsigned __int64 v196; // rax
  __int64 v197; // r14
  char *v198; // rax
  wchar_t *v199; // r8
  unsigned __int16 *v200; // rdx
  unsigned __int64 v201; // r11
  wchar_t *v202; // rsi
  CharacterSource *v203; // r9
  unsigned int v204; // edi
  SourceType v205; // eax
  wchar_t *v206; // r8
  unsigned __int16 *v207; // rdx
  unsigned __int64 v208; // r10
  __int64 v209; // rax
  HRESULT v210; // eax
  HRESULT v211; // eax
  HRESULT v212; // edi
  int v213; // eax
  char *v214; // r14
  char *jj; // rsi
  unsigned int v216; // eax
  int v217; // r10d
  const void *v218; // r11
  int *pHashTable; // rcx
  unsigned int v220; // r9d
  int j; // edx
  BlockAlloc::Header *i1; // rcx
  size_t v223; // r8
  size_t v224; // r8
  unsigned __int8 *v225; // rdx
  wchar_t *v226; // rdx
  unsigned __int8 *v227; // r8
  unsigned __int64 v228; // r11
  unsigned int v229; // ecx
  __int64 v230; // rax
  int v231; // r10d
  IMXRContentHandler *p; // rcx
  __int64 v233; // rax
  char *v234; // rdx
  int v235; // r8d
  const wchar_t *v236; // r9
  unsigned __int16 *v237; // r8
  unsigned __int64 v238; // rdx
  wchar_t *v239; // r9
  unsigned __int16 *v240; // r8
  unsigned __int64 v241; // rdx
  wchar_t *v242; // r9
  unsigned int v243; // r14d
  int ii; // edx
  char *v245; // rsi
  char *n; // r14
  StringPtr v247; // xmm6
  StringPtr v248; // xmm7
  StringPtr v249; // xmm8
  StringPtr v250; // xmm9
  StringPtr v251; // xmm10
  StringPtr v252; // xmm11
  __int128 v253; // xmm12
  __int64 v254; // xmm13_8
  Attribute *v255; // rax
  unsigned int v256; // ecx
  __int64 v257; // rax
  char *v258; // rax
  CharacterSource *v259; // rdx
  SourceType v260; // eax
  unsigned int v261; // esi
  wchar_t *v262; // rax
  int v263; // eax
  HRESULT v264; // eax
  unsigned int v265; // esi
  unsigned int *v266; // rdi
  int v267; // eax
  wchar_t *v268; // r9
  StringPtr *pLName; // [rsp+28h] [rbp-E0h]
  StringPtr *pLNamea; // [rsp+28h] [rbp-E0h]
  IMXRAttributes *v271; // [rsp+40h] [rbp-C8h]
  unsigned int puResult[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v273; // [rsp+60h] [rbp-A8h]
  StringPtr *v274; // [rsp+68h] [rbp-A0h]
  void *Buf1; // [rsp+70h] [rbp-98h]
  StringPtr *v276; // [rsp+78h] [rbp-90h]
  StringPtr v277; // [rsp+80h] [rbp-88h] BYREF
  void *pScope; // [rsp+90h] [rbp-78h]
  int *v279; // [rsp+98h] [rbp-70h]
  Reader::ParseElementNContext context; // [rsp+A0h] [rbp-68h] BYREF
  int pnContext[2]; // [rsp+F8h] [rbp-10h] BYREF
  StringPtr v282; // [rsp+108h] [rbp+0h] BYREF
  StringPtr pValue; // [rsp+118h] [rbp+10h] BYREF
  StringPtr v284; // [rsp+128h] [rbp+20h] BYREF
  StringPtr v285; // [rsp+138h] [rbp+30h] BYREF
  StringPtr *v286; // [rsp+148h] [rbp+40h]
  unsigned __int64 v287; // [rsp+150h] [rbp+48h]
  _OWORD v288[5]; // [rsp+158h] [rbp+50h] BYREF
  __int64 v289; // [rsp+1A8h] [rbp+A0h]
  wchar_t pszDest[128]; // [rsp+1B8h] [rbp+B0h] BYREF

  *(_QWORD *)&context.qname.n = 0;
  LODWORD(context.prefix.pwh) = 0;
  *(_QWORD *)&context.prefix.n = 0;
  LODWORD(context.uri.pwh) = 0;
  *(_QWORD *)&context.uri.n = 0;
  LODWORD(context.lname.pwh) = 0;
  *(_QWORD *)&context.lname.n = 0;
  LODWORD(context.pScope) = 0;
LABEL_2:
  ++this->_ulCurrentElementDepth;
  ulMaxElementDepth = this->_ulMaxElementDepth;
  if ( ulMaxElementDepth && this->_ulCurrentElementDepth > ulMaxElementDepth )
  {
    MXRRaiseException(-1072894318);
    __debugbreak();
  }
  pBlock = this->_alloc._pBlock;
  pCharacterSource = this->_scanner._pCharacterSource;
  pCurr = pBlock->pCurr;
  sourceType = pCharacterSource->_sourceType;
  pScope = pCurr;
  context.pAttributesScope = pCurr;
  if ( sourceType )
  {
    if ( sourceType == Utf16 )
    {
LABEL_12:
      v7 = LODWORD(pCharacterSource->_pbCurr) - 2 * pCharacterSource->_lDelta - LODWORD(pCharacterSource->_pbSeg);
    }
    else
    {
      switch ( sourceType )
      {
        case Utf16B:
        case Ucs2:
        case Ucs2B:
        case CodePage:
          goto LABEL_12;
        case Ucs4:
        case Ucs4B:
          v7 = LODWORD(pCharacterSource->_pbCurr) - 4 * pCharacterSource->_lDelta - LODWORD(pCharacterSource->_pbSeg);
          break;
        default:
          goto LABEL_5;
      }
    }
  }
  else
  {
LABEL_5:
    v7 = 2 * (LODWORD(pCharacterSource->_pbCurr) - pCharacterSource->_lDelta - LODWORD(pCharacterSource->_pbSeg));
  }
  v8 = pCurr;
  v9 = LODWORD(pBlock->pLast) - (_DWORD)pCurr;
  Buf1 = pCurr;
  if ( v9 < v7 )
  {
    while ( 1 )
    {
      pNext = pBlock->pNext;
      if ( !pNext )
        break;
      pBlock = pBlock->pNext;
      if ( LODWORD(pNext->pLast) - (int)pNext - 32 >= v7 )
      {
        pBlock->pCurr = (unsigned __int8 *)&pBlock[1];
        goto LABEL_121;
      }
    }
    if ( v7 + 32 < v7 || (v105 = pBlock->pLast - (unsigned __int8 *)pBlock, v105 > 0xFFFFFFFF) )
    {
LABEL_63:
      MXRRaiseException(-2147024362);
      __debugbreak();
    }
    while ( 1 )
    {
      v106 = (unsigned int)v105;
      if ( (unsigned int)v105 >= v7 + 32 )
        break;
      LODWORD(v105) = 2 * v105;
      if ( (unsigned __int64)(2 * v106) > 0xFFFFFFFF )
        goto LABEL_63;
    }
    v107 = new_array<unsigned char>((unsigned int)v105);
    *(_QWORD *)v107 = pBlock;
    *((_QWORD *)v107 + 2) = v107 + 32;
    *((_QWORD *)v107 + 3) = &v107[v106];
    *((_QWORD *)v107 + 1) = 0;
    pBlock->pNext = (BlockAlloc::Header *)v107;
    pBlock = (BlockAlloc::Header *)v107;
LABEL_121:
    this->_alloc._pBlock = pBlock;
    v8 = pBlock->pCurr;
    Buf1 = v8;
  }
  pBlock->pCurr += v7;
  v10 = this->_scanner._pCharacterSource;
  v11 = v7 >> 1;
  *(_QWORD *)&context.qname.n = v8;
  LODWORD(context.prefix.pwh) = v11;
  v12 = v10->_sourceType;
  if ( v12 == Utf16B )
  {
    v14 = (char *)v8;
    pbSeg = (unsigned __int16 *)v10->_pbSeg;
    v16 = (unsigned __int64)&v10->_pbCurr[-2 * v10->_lDelta];
    while ( 1 )
    {
      v17 = (v14 - (char *)v8) >> 1;
      if ( (unsigned __int64)pbSeg >= v16 )
        break;
      if ( (unsigned int)v17 >= v11 )
        goto LABEL_206;
      *(_WORD *)v14 = _byteswap_ushort(*pbSeg);
      v14 += 2;
      ++pbSeg;
    }
LABEL_17:
    pwh_low = (unsigned int)v17;
    LODWORD(context.prefix.pwh) = v17;
    goto LABEL_18;
  }
  if ( v12 == Utf8 )
  {
LABEL_9:
    Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v10, (StringPtr *)&context.qname.n);
LABEL_10:
    v8 = *(unsigned __int8 **)&context.qname.n;
    pScope = context.pAttributesScope;
    pwh_low = LODWORD(context.prefix.pwh);
    Buf1 = *(void **)&context.qname.n;
LABEL_18:
    v273 = pwh_low;
    goto LABEL_19;
  }
  switch ( v12 )
  {
    case Utf16:
      v85 = (unsigned int)(LODWORD(v10->_pbCurr) - 2 * v10->_lDelta - LODWORD(v10->_pbSeg));
      if ( (v85 + 1) >> 1 > v11 )
        goto LABEL_206;
      v86 = v85;
LABEL_109:
      v87 = v10->_pbSeg;
      v273 = v86 >> 1;
      LODWORD(context.prefix.pwh) = v86 >> 1;
      memcpy_0(v8, v87, v85);
      goto LABEL_19;
    case Ucs2:
      v86 = LODWORD(v10->_pbCurr) - 2 * v10->_lDelta - LODWORD(v10->_pbSeg);
      v85 = v86;
      if ( ((unsigned __int64)v86 + 1) >> 1 > v11 )
        goto LABEL_206;
      goto LABEL_109;
    case Ucs2B:
      v119 = (char *)v8;
      v120 = (unsigned __int16 *)v10->_pbSeg;
      v121 = (unsigned __int64)&v10->_pbCurr[-2 * v10->_lDelta];
      while ( 2 )
      {
        v17 = (v119 - (char *)v8) >> 1;
        if ( (unsigned __int64)v120 >= v121 )
          goto LABEL_17;
        if ( (unsigned int)v17 < v11 )
        {
          *(_WORD *)v119 = _byteswap_ushort(*v120);
          v119 += 2;
          ++v120;
          continue;
        }
        goto LABEL_206;
      }
    case Ucs4:
      v145 = (char *)v8;
      v146 = v10->_pbSeg;
      v147 = (unsigned __int64)&v10->_pbCurr[-4 * v10->_lDelta];
      break;
    case Ucs4B:
      Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v10, (StringPtr *)&context.qname.n);
      goto LABEL_10;
    case CodePage:
      Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v10, (StringPtr *)&context.qname.n);
      v8 = *(unsigned __int8 **)&context.qname.n;
      pwh_low = LODWORD(context.prefix.pwh);
      pScope = context.pAttributesScope;
      Buf1 = *(void **)&context.qname.n;
      goto LABEL_18;
    default:
      goto LABEL_9;
  }
  while ( 1 )
  {
    v148 = (v145 - (char *)v8) >> 1;
    if ( (unsigned __int64)(v146 + 3) >= v147 )
      break;
    if ( (unsigned int)v148 >= v11 )
      goto LABEL_206;
    v256 = *(_DWORD *)v146;
    if ( *(_DWORD *)v146 > 0xFFFFu )
    {
      *(_WORD *)v145 = (v256 >> 10) - 10304;
      if ( (unsigned int)((v145 + 2 - (char *)v8) >> 1) >= v11 )
        goto LABEL_206;
      *((_WORD *)v145 + 1) = v256 & 0x3FF | 0xDC00;
      v145 += 4;
      v146 += 4;
    }
    else
    {
      *(_WORD *)v145 = v256;
      v145 += 2;
      v146 += 4;
    }
  }
  LODWORD(context.prefix.pwh) = (v145 - (char *)v8) >> 1;
  v273 = (unsigned int)v148;
LABEL_19:
  nNsPrefix = this->_scanner._nNsPrefix;
  ++this->_nsSupport._nContext;
  v19 = this->_alloc._pBlock;
  *(_QWORD *)&context.prefix.n = v8;
  LODWORD(v274) = nNsPrefix;
  LODWORD(context.uri.pwh) = nNsPrefix;
  v20 = v19->pCurr;
  *(_QWORD *)&context.nContext = v20;
  Reader::ParseAttributesN(this);
  lSize = this->_attributes._lSize;
  if ( !(_DWORD)lSize )
  {
    if ( !this->_nsAttributes._lSize )
      goto LABEL_30;
    goto LABEL_21;
  }
  if ( (int)lSize < 0 )
  {
LABEL_206:
    MXRRaiseException(-2147418113);
    __debugbreak();
  }
  if ( (int)lSize < 63 )
  {
LABEL_21:
    pStack = this->_attributes._pStack;
    v23 = pStack;
    v24 = &pStack[120 * lSize];
    while ( v23 < v24 )
    {
      v25 = *((int *)v23 + 6);
      if ( (_DWORD)v25 )
      {
        *((_QWORD *)v23 + 6) = *(_QWORD *)v23 + 2 * (v25 + 1);
        *((_DWORD *)v23 + 14) = *((_DWORD *)v23 + 2) + ~(_DWORD)v25;
        pLastPrefix = this->_nsSupport._pLastPrefix;
        if ( pLastPrefix )
        {
          v230 = *((int *)v23 + 6);
          if ( (_DWORD)v230 == pLastPrefix->n && !memcmp_0(*((const void **)v23 + 2), pLastPrefix->pwh, 2 * v230) )
          {
            *((_OWORD *)v23 + 2) = *this->_nsSupport._pLastNsUri;
            goto LABEL_25;
          }
        }
        v177 = this->_nsSupport._maps._lSize;
        if ( v177 )
        {
          if ( v177 < 10 )
          {
            v178 = *((_DWORD *)v23 + 6);
            v179 = this->_nsSupport._maps._pStack;
            v180 = 2 * v178;
            puResult[0] = 2 * v178;
            for ( i = &v179[48 * v177 - 48]; ; i -= 48 )
            {
              if ( v178 == *((_DWORD *)i + 2) )
              {
                if ( !memcmp_0(*(const void **)i, *((const void **)v23 + 2), v180) )
                  goto LABEL_254;
                v178 = *((_DWORD *)v23 + 6);
                v179 = this->_nsSupport._maps._pStack;
                v180 = puResult[0];
              }
              if ( i == v179 )
                goto LABEL_310;
            }
          }
          v216 = hash(*((const wchar_t **)v23 + 2), *((_DWORD *)v23 + 6), this->_nsSupport._nHashSeed);
          pHashTable = this->_nsSupport._pHashTable;
          v220 = v216;
          puResult[0] = v216;
          for ( j = pHashTable[v216 % this->_nsSupport._nHashSize] - 1; ; j = *((_DWORD *)i + 9) )
          {
            if ( j < 0 )
              goto LABEL_310;
            i = &this->_nsSupport._maps._pStack[48 * j];
            if ( v220 == *((_DWORD *)i + 10) && v217 == *((_DWORD *)i + 2) )
            {
              if ( !memcmp_0(v218, *(const void **)i, 2LL * v217) )
              {
LABEL_254:
                this->_nsSupport._pLastPrefix = (StringPtr *)i;
                this->_nsSupport._pLastNsUri = (StringPtr *)(i + 16);
                *((_OWORD *)v23 + 2) = *((_OWORD *)i + 1);
                goto LABEL_25;
              }
              v217 = *((_DWORD *)v23 + 6);
              v220 = puResult[0];
              v218 = (const void *)*((_QWORD *)v23 + 2);
            }
          }
        }
        goto LABEL_310;
      }
      *((_OWORD *)v23 + 3) = *(_OWORD *)v23;
      *((StringPtr *)v23 + 2) = CodeStringPtr::empty;
LABEL_25:
      for ( k = pStack; k < v23; k += 120 )
      {
        v76 = *((int *)k + 14);
        if ( (_DWORD)v76 == *((_DWORD *)v23 + 14)
          && !memcmp_0(*((const void **)k + 6), *((const void **)v23 + 6), 2 * v76) )
        {
          v257 = *((int *)k + 10);
          if ( (_DWORD)v257 == *((_DWORD *)v23 + 10)
            && !memcmp_0(*((const void **)k + 4), *((const void **)v23 + 4), 2 * v257) )
          {
            goto LABEL_388;
          }
        }
      }
      v23 += 120;
    }
    nNsPrefix = (int)v274;
    goto LABEL_29;
  }
  v182 = lSize + ((unsigned int)lSize >> 2);
  if ( v182 < (unsigned int)lSize )
  {
    if ( (unsigned int)lSize >= 0x7FFFFFFF )
    {
      MXRRaiseException(-2147352566);
      __debugbreak();
    }
    v182 = 0x7FFFFFFF;
  }
  cHashAttributes = this->_cHashAttributes;
  if ( v182 > (unsigned int)cHashAttributes )
  {
    puResult[0] = 0;
    v264 = ULongLongToUInt(2 * cHashAttributes, puResult);
    if ( v264 < 0 )
    {
      MXRRaiseException(v264);
      __debugbreak();
    }
    v265 = puResult[0];
    if ( puResult[0] < v182 )
      v265 = v182;
    v266 = new_array<unsigned int>(v265);
    MemFree(this->_pHashAttributes);
    this->_pHashAttributes = v266;
    nNsPrefix = (int)v274;
    this->_cHashAttributes = v265;
  }
  memset_0(this->_pHashAttributes, 0, 4LL * v182);
  for ( m = 0; m < (unsigned int)lSize; this->_pHashAttributes[v287 / 4] = m )
  {
    v274 = (StringPtr *)&this->_attributes._pStack[120 * m];
    v286 = v274 + 3;
    v276 = v274 + 2;
    NamespaceSupport::ProcessAttribute(&this->_nsSupport, v274, v274 + 1, v274 + 2, v274 + 3);
    hash(v276->pwh, v274[2].n, this->_nHashSeed);
    v186 = hash(v286->pwh, v274[3].n, v185);
    v188 = (v187 ^ (unsigned __int64)v186) % v182;
    pHashAttributes = this->_pHashAttributes;
    v287 = 4 * v188;
    v190 = pHashAttributes[(unsigned int)v188];
    puResult[0] = v190;
    while ( v190 )
    {
      v258 = &this->_attributes._pStack[120 * (v190 - 1)];
      v279 = (int *)v258;
      if ( *((_DWORD *)v258 + 10) == v276->n )
      {
        v37 = memcmp_0(*((const void **)v258 + 4), v276->pwh, 2LL * *((int *)v258 + 10)) == 0;
        v258 = (char *)v279;
        if ( v37 && v279[14] == v286->n )
        {
          if ( !memcmp_0(*((const void **)v279 + 6), v286->pwh, 2LL * v279[14]) )
          {
LABEL_388:
            MXRRaiseException(-1072894404);
            __debugbreak();
          }
          v258 = (char *)v279;
        }
      }
      v190 = *((_DWORD *)v258 + 28);
    }
    ++m;
    LODWORD(v274[7].pwh) = puResult[0];
  }
LABEL_29:
  v27 = this->_nsAttributes._lSize;
  if ( (_DWORD)v27 )
  {
    if ( this->_fNamespacePrefixes )
    {
      v245 = this->_nsAttributes._pStack;
      for ( n = &v245[120 * v27]; v245 < n; *(_QWORD *)&v255->nHashNext = v254 )
      {
        v247 = *(StringPtr *)v245;
        v248 = (StringPtr)*((_OWORD *)v245 + 1);
        v249 = (StringPtr)*((_OWORD *)v245 + 2);
        v250 = (StringPtr)*((_OWORD *)v245 + 3);
        v251 = (StringPtr)*((_OWORD *)v245 + 4);
        v252 = (StringPtr)*((_OWORD *)v245 + 5);
        v253 = *((_OWORD *)v245 + 6);
        v254 = *((_QWORD *)v245 + 14);
        v255 = _stack<Attribute>::push(&this->_attributes);
        v245 += 120;
        v255->qname = v247;
        v255->prefix = v248;
        v255->uri = v249;
        v255->lname = v250;
        v255->type = v251;
        v255->value = v252;
        *(_OWORD *)&v255->nToken = v253;
      }
    }
  }
LABEL_30:
  v28 = this->_nsSupport._maps._lSize;
  v29 = 0;
  v30 = this->_nsSupport._maps._pStack;
  nContext = this->_nsSupport._nContext;
  LODWORD(v276) = 0;
  if ( *(_DWORD *)&v30[48 * v28 - 16] == nContext )
  {
    v32 = (unsigned int)(v28 - 1);
    if ( (int)v32 >= 0 )
    {
      do
      {
        if ( *(_DWORD *)&v30[48 * v32 + 32] != nContext )
          break;
        ++v29;
        v32 = (unsigned int)(v32 - 1);
      }
      while ( (int)v32 >= 0 );
      LODWORD(v276) = v29;
    }
  }
  pnContext[0] = v29;
  while ( v29 )
  {
    v231 = v29 - 1;
    p = this->_pContentHandler._p;
    v233 = this->_nsSupport._maps._lSize - v231;
    LODWORD(v276) = v231;
    pnContext[0] = v231;
    v234 = &this->_nsSupport._maps._pStack[48 * v233];
    v235 = *((_DWORD *)v234 - 6);
    v236 = (const wchar_t *)*((_QWORD *)v234 - 4);
    HIDWORD(context.lname.pwh) = *((_DWORD *)v234 - 5);
    v42 = p->startPrefixMapping(p, *((const wchar_t **)v234 - 6), *((_DWORD *)v234 - 10), v236, v235);
    v43 = v42;
    if ( v42 < 0 )
      goto LABEL_342;
    v29 = (int)v276;
  }
  v33 = (const wchar_t *)Buf1;
  if ( nNsPrefix )
  {
    v34 = nNsPrefix;
    Buf1 = (char *)Buf1 + 2 * nNsPrefix + 2;
    *(_QWORD *)&context.lname.n = &v33[nNsPrefix + 1];
    LODWORD(v274) = v273 - nNsPrefix - 1;
    LODWORD(context.pScope) = (_DWORD)v274;
  }
  else
  {
    v34 = 0;
    LODWORD(v274) = v273;
    context.pScope = (void *)__PAIR64__(HIDWORD(context.prefix.pwh), v273);
    *(_QWORD *)&context.lname.n = Buf1;
  }
  v35 = this->_nsSupport._pLastPrefix;
  if ( v35 && nNsPrefix == v35->n && !memcmp_0(v33, v35->pwh, 2 * v34) )
  {
    pLastNsUri = this->_nsSupport._pLastNsUri;
  }
  else
  {
    v213 = this->_nsSupport._maps._lSize;
    if ( !v213 )
      goto LABEL_310;
    if ( v213 >= 10 )
    {
      v243 = hash(v33, nNsPrefix, this->_nsSupport._nHashSeed);
      for ( ii = this->_nsSupport._pHashTable[v243 % this->_nsSupport._nHashSize] - 1; ii >= 0; ii = *((_DWORD *)jj + 9) )
      {
        jj = &this->_nsSupport._maps._pStack[48 * ii];
        if ( v243 == *((_DWORD *)jj + 10)
          && nNsPrefix == *((_DWORD *)jj + 2)
          && !memcmp_0(v33, *(const void **)jj, 2LL * nNsPrefix) )
        {
          goto LABEL_307;
        }
      }
LABEL_310:
      MXRRaiseException(-1072894363);
      __debugbreak();
    }
    v214 = this->_nsSupport._maps._pStack;
    for ( jj = &v214[48 * v213 - 48];
          nNsPrefix != *((_DWORD *)jj + 2) || memcmp_0(*(const void **)jj, v33, 2 * nNsPrefix);
          jj -= 48 )
    {
      if ( jj == v214 )
        goto LABEL_310;
    }
LABEL_307:
    pLastNsUri = (StringPtr *)(jj + 16);
    this->_nsSupport._pLastPrefix = (StringPtr *)jj;
    this->_nsSupport._pLastNsUri = (StringPtr *)(jj + 16);
  }
  v37 = this->_scanner._nToken == 5;
  v38 = pLastNsUri->n;
  pwh = pLastNsUri->pwh;
  v40 = this->_pContentHandler._p;
  v41 = (int)v274;
  HIDWORD(context.lname.pwh) = *(&pLastNsUri->n + 1);
  *(_QWORD *)&context.uri.n = pwh;
  v279 = (int *)pwh;
  v271 = &this->IMXRAttributes;
  LODWORD(context.lname.pwh) = v38;
  puResult[0] = v38;
  if ( v37 )
  {
    v42 = v40->startElement(v40, pwh, v38, (const wchar_t *)Buf1, (int)v274, v33, v273, v271);
    v43 = v42;
    if ( v42 >= 0 )
    {
      v44 = this->_alloc._pBlock;
      if ( v44 >= (BlockAlloc::Header *)v20 || v20 > v44->pCurr )
      {
        for ( kk = v44->pPrev; ; kk = kk->pPrev )
        {
          this->_alloc._pBlock = kk;
          v44 = kk;
          if ( !kk )
            break;
          if ( kk < (BlockAlloc::Header *)v20 && v20 <= kk->pLast )
            goto LABEL_47;
        }
      }
      else
      {
LABEL_47:
        v44->pCurr = v20;
      }
      v45 = (int)v276;
      goto $Continue;
    }
LABEL_342:
    Reader::OnCallbackFailure(v42);
    goto $CleanUp_2;
  }
  v113 = (const wchar_t *)Buf1;
  v43 = this->_pfnStartEmptyElement(v40, pwh, v38, (const wchar_t *)Buf1, (int)v274, v33, v273, v271);
  if ( v43 < 0 )
  {
    v114 = NewParserCallbackFailureTrackingRegistry::s_fInitialized;
    if ( !NewParserCallbackFailureTrackingRegistry::s_fInitialized )
    {
      NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled = 0;
      NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled = 0;
      Registry::readMultipleSettings(NewParserCallbackFailureTrackingRegistry::s_rgSettings);
      v114 = 1;
      NewParserCallbackFailureTrackingRegistry::s_fInitialized = 1;
    }
    if ( NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled )
    {
      LODWORD(pLNamea) = GetCurrentThreadId();
      StringCchPrintfW(
        pszDest,
        0x80u,
        L"SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\r\n",
        (unsigned int)v43,
        pLNamea);
      OutputDebugStringW(pszDest);
      v114 = NewParserCallbackFailureTrackingRegistry::s_fInitialized;
    }
    if ( !v114 )
    {
      NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled = 0;
      NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled = 0;
      Registry::readMultipleSettings(NewParserCallbackFailureTrackingRegistry::s_rgSettings);
      NewParserCallbackFailureTrackingRegistry::s_fInitialized = 1;
    }
    if ( NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled )
      MEMORY[0] = 0;
$CleanUp_2:
    MXRRaiseException(v43);
    __debugbreak();
  }
  v42 = this->_pfnEndEmptyElement(this->_pContentHandler._p, pwh, v38, v113, v41, v33, v273);
  v43 = v42;
  if ( v42 < 0 )
    goto LABEL_342;
  v48 = 0;
  while ( 1 )
  {
    v62 = this->_nsSupport._maps._lSize;
    v63 = this->_nsSupport._maps._pStack;
    v64 = this->_nsSupport._nContext;
    if ( *(_DWORD *)&v63[48 * v62 - 16] == v64 )
    {
      for ( mm = (unsigned int)(v62 - 1); (int)mm >= 0; mm = (unsigned int)(mm - 1) )
      {
        if ( *(_DWORD *)&v63[48 * mm + 32] != v64 )
          break;
        ++v48;
      }
    }
    p_nsSupport = &this->_nsSupport;
    while ( v48 )
    {
      --v48;
      v42 = this->_pContentHandler._p->endPrefixMapping(
              this->_pContentHandler._p,
              *(const wchar_t **)&this->_nsSupport._maps._pStack[48 * (this->_nsSupport._maps._lSize - v48) - 48],
              *(unsigned int *)&this->_nsSupport._maps._pStack[48 * (this->_nsSupport._maps._lSize - v48) - 40]);
      v43 = v42;
      if ( v42 < 0 )
        goto LABEL_342;
    }
    v67 = this->_nsSupport._maps._lSize;
    v68 = p_nsSupport->_nContext;
    if ( *(_DWORD *)&this->_nsSupport._maps._pStack[48 * v67 - 16] == p_nsSupport->_nContext )
    {
      if ( v68 <= 0 )
        goto LABEL_206;
      if ( (_DWORD)v67 )
      {
        do
          NamespaceSupport::PopMap(&this->_nsSupport, 1);
        while ( *(_DWORD *)&this->_nsSupport._maps._pStack[48 * this->_nsSupport._maps._lSize - 16] >= p_nsSupport->_nContext );
        this->_nsSupport._pLastPrefix = 0;
        this->_nsSupport._pLastNsUri = 0;
      }
      --p_nsSupport->_nContext;
    }
    else
    {
      p_nsSupport->_nContext = v68 - 1;
    }
    v69 = this->_alloc._pBlock;
    v70 = (unsigned __int8 *)pScope;
    if ( v69 >= pScope || pScope > v69->pCurr )
    {
      for ( nn = v69->pPrev; ; nn = nn->pPrev )
      {
        this->_alloc._pBlock = nn;
        v69 = nn;
        if ( !nn )
          break;
        if ( nn < (BlockAlloc::Header *)v70 && v70 <= nn->pLast )
          goto LABEL_83;
      }
    }
    else
    {
LABEL_83:
      v69->pCurr = v70;
    }
    --this->_ulCurrentElementDepth;
    v71 = this->_parseElementNStack._lSize;
    if ( (int)v71 <= 0 )
      break;
    this->_parseElementNStack._lSize = v71 - 1;
    v99 = this->_parseElementNStack._pStack;
    v100 = 88 * v71;
    v101 = *(_OWORD *)&v99[v100 - 88];
    v102 = *(_OWORD *)&v99[v100 - 56];
    v103 = *(_OWORD *)&v99[v100 - 40];
    v104 = *(_OWORD *)&v99[v100 - 24];
    *(_OWORD *)&context.prefix.n = *(_OWORD *)&v99[v100 - 72];
    v33 = (const wchar_t *)v101;
    *(_QWORD *)pnContext = *(_QWORD *)&v99[v100 - 8];
    v45 = _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)pnContext);
    LODWORD(v274) = _mm_cvtsi128_si32(_mm_loadl_epi64((const __m128i *)&v99[v100 - 32]));
    puResult[0] = _mm_cvtsi128_si32(_mm_loadl_epi64((const __m128i *)&v99[v100 - 48]));
    LODWORD(v273) = _mm_cvtsi128_si32(_mm_loadl_epi64((const __m128i *)&v99[v100 - 80]));
    *(_OWORD *)&context.qname.n = v101;
    *(_OWORD *)&context.uri.n = v102;
    *(_OWORD *)&context.lname.n = v103;
    *(_OWORD *)&context.pAttributesScope = v104;
    pScope = (void *)v104;
    Buf1 = (void *)v103;
    v279 = (int *)v102;
$Continue:
    while ( 1 )
    {
      Scanner::DoScan(&this->_scanner, (Scanner::ScanOp)*(_DWORD *)this->_scanner._scanOp);
      nToken = this->_scanner._nToken;
      if ( nToken == 4 )
        break;
      if ( nToken == 3 )
      {
        if ( this->_ulCurrentElementDepth < 0x3E8 )
        {
          Reader::ParseElementN(this);
          continue;
        }
        if ( this->_parseElementNStack._lCapacity == this->_parseElementNStack._lSize )
          _stack<Reader::ParseElementNContext>::grow(&this->_parseElementNStack);
        v77 = *(_OWORD *)&context.qname.n;
        v78 = *(_OWORD *)&context.prefix.n;
        v79 = 88LL * this->_parseElementNStack._lSize++;
        v80 = this->_parseElementNStack._pStack;
        *(_OWORD *)&v80[v79] = v77;
        v81 = *(_OWORD *)&context.uri.n;
        *(_OWORD *)&v80[v79 + 16] = v78;
        v82 = *(_OWORD *)&context.lname.n;
        *(_OWORD *)&v80[v79 + 32] = v81;
        v83 = *(_OWORD *)&context.pAttributesScope;
        *(_OWORD *)&v80[v79 + 48] = v82;
        *(_QWORD *)&v82 = *(_QWORD *)pnContext;
        *(_OWORD *)&v80[v79 + 64] = v83;
        *(_QWORD *)&v80[v79 + 80] = v82;
        memset_0(v288, 0, 0x58u);
        *(_OWORD *)&context.qname.n = v288[0];
        *(_OWORD *)&context.prefix.n = v288[1];
        *(_OWORD *)&context.uri.n = v288[2];
        *(_OWORD *)&context.lname.n = v288[3];
        *(_OWORD *)&context.pAttributesScope = v288[4];
        *(_QWORD *)pnContext = v289;
        goto LABEL_2;
      }
      switch ( nToken )
      {
        case 7:
          v88 = this->_scanner._pCharacterSource;
          v89 = this->_alloc._pBlock;
          pValue.pwh = 0;
          pValue.n = 0;
          v90 = v88->_sourceType;
          v91 = v89->pCurr;
          if ( v90 )
          {
            if ( v90 == Utf16 )
            {
LABEL_144:
              v92 = LODWORD(v88->_pbCurr) - 2 * v88->_lDelta - LODWORD(v88->_pbSeg);
            }
            else
            {
              switch ( v90 )
              {
                case Utf16B:
                case Ucs2:
                case Ucs2B:
                case CodePage:
                  goto LABEL_144;
                case Ucs4:
                case Ucs4B:
                  v92 = LODWORD(v88->_pbCurr) - 4 * v88->_lDelta - LODWORD(v88->_pbSeg);
                  break;
                default:
                  goto LABEL_112;
              }
            }
          }
          else
          {
LABEL_112:
            v92 = 2 * (LODWORD(v88->_pbCurr) - v88->_lDelta - LODWORD(v88->_pbSeg));
          }
          v93 = (wchar_t *)v89->pCurr;
          if ( LODWORD(v89->pLast) - (int)v91 >= v92 )
            goto LABEL_135;
          while ( 1 )
          {
            v94 = v89->pNext;
            if ( !v94 )
              break;
            v89 = v89->pNext;
            if ( LODWORD(v94->pLast) - (int)v94 - 32 >= v92 )
            {
              v89->pCurr = (unsigned __int8 *)&v89[1];
              goto LABEL_134;
            }
          }
          if ( v92 + 32 < v92 )
            goto LABEL_63;
          v95 = v89->pLast - (unsigned __int8 *)v89;
          if ( v95 > 0xFFFFFFFF )
            goto LABEL_63;
          while ( 1 )
          {
            v96 = (unsigned int)v95;
            if ( (unsigned int)v95 >= v92 + 32 )
              break;
            LODWORD(v95) = 2 * v95;
            if ( (unsigned __int64)(2 * v96) > 0xFFFFFFFF )
              goto LABEL_63;
          }
          v97 = new_array<unsigned char>((unsigned int)v95);
          *(_QWORD *)v97 = v89;
          *((_QWORD *)v97 + 2) = v97 + 32;
          *((_QWORD *)v97 + 3) = &v97[v96];
          *((_QWORD *)v97 + 1) = 0;
          v89->pNext = (BlockAlloc::Header *)v97;
          v89 = (BlockAlloc::Header *)v97;
LABEL_134:
          this->_alloc._pBlock = v89;
          v93 = (wchar_t *)v89->pCurr;
LABEL_135:
          v89->pCurr += v92;
          v108 = this->_scanner._pCharacterSource;
          v109 = v92 >> 1;
          pValue.pwh = v93;
          pValue.n = v109;
          v110 = v108->_sourceType;
          if ( v110 == Utf16B )
          {
            v115 = v93;
            v116 = (unsigned __int16 *)v108->_pbSeg;
            v117 = (unsigned __int64)&v108->_pbCurr[-2 * v108->_lDelta];
            while ( 1 )
            {
              v111 = v115 - v93;
              if ( (unsigned __int64)v116 >= v117 )
                break;
              if ( (unsigned int)v111 >= v109 )
                goto LABEL_206;
              *v115++ = _byteswap_ushort(*v116++);
            }
          }
          else if ( v110 )
          {
            switch ( v110 )
            {
              case Utf16:
                v118 = (unsigned int)(LODWORD(v108->_pbCurr) - 2 * v108->_lDelta - LODWORD(v108->_pbSeg));
                if ( (v118 + 1) >> 1 > v109 )
                  goto LABEL_206;
                LODWORD(v111) = (unsigned int)v118 >> 1;
                memcpy_0(v93, v108->_pbSeg, v118);
                goto LABEL_139;
              case Ucs2:
                if ( ((unsigned __int64)(unsigned int)(LODWORD(v108->_pbCurr) - 2 * v108->_lDelta - LODWORD(v108->_pbSeg))
                    + 1) >> 1 > v109 )
                  goto LABEL_206;
                LODWORD(v111) = (unsigned int)(LODWORD(v108->_pbCurr) - 2 * v108->_lDelta - LODWORD(v108->_pbSeg)) >> 1;
                memcpy_0(
                  v93,
                  v108->_pbSeg,
                  (unsigned int)(LODWORD(v108->_pbCurr) - 2 * v108->_lDelta - LODWORD(v108->_pbSeg)));
                goto LABEL_139;
              case Ucs2B:
                v191 = v93;
                v192 = (unsigned __int16 *)v108->_pbSeg;
                v193 = (unsigned __int64)&v108->_pbCurr[-2 * v108->_lDelta];
                while ( 2 )
                {
                  v111 = v191 - v93;
                  if ( (unsigned __int64)v192 >= v193 )
                    goto LABEL_139;
                  if ( (unsigned int)v111 < v109 )
                  {
                    *v191++ = _byteswap_ushort(*v192++);
                    continue;
                  }
                  goto LABEL_206;
                }
              case Ucs4:
                v226 = v93;
                v227 = v108->_pbSeg;
                v228 = (unsigned __int64)&v108->_pbCurr[-4 * v108->_lDelta];
                break;
              case Ucs4B:
                Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v108, &pValue);
                goto LABEL_138;
              case CodePage:
                Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v108, &pValue);
                goto LABEL_138;
              default:
                goto LABEL_137;
            }
            while ( 1 )
            {
              v111 = v226 - v93;
              if ( (unsigned __int64)(v227 + 3) >= v228 )
                break;
              if ( (unsigned int)v111 >= v109 )
                goto LABEL_206;
              v229 = *(_DWORD *)v227;
              if ( *(_DWORD *)v227 > 0xFFFFu )
              {
                *v226 = (v229 >> 10) - 10304;
                if ( (unsigned int)(v226 + 1 - v93) >= v109 )
                  goto LABEL_206;
                v226[1] = v229 & 0x3FF | 0xDC00;
                v226 += 2;
                v227 += 4;
              }
              else
              {
                *v226++ = v229;
                v227 += 4;
              }
            }
          }
          else
          {
LABEL_137:
            Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v108, &pValue);
LABEL_138:
            LODWORD(v111) = pValue.n;
          }
LABEL_139:
          v42 = this->_pContentHandler._p->characters(this->_pContentHandler._p, pValue.pwh, v111);
          v43 = v42;
          if ( v42 < 0 )
            goto LABEL_342;
          v112 = this->_alloc._pBlock;
          if ( v112 >= (BlockAlloc::Header *)v91 || v91 > v112->pCurr )
          {
            for ( i1 = v112->pPrev; ; i1 = i1->pPrev )
            {
              this->_alloc._pBlock = i1;
              v112 = i1;
              if ( !i1 )
                break;
              if ( i1 < (BlockAlloc::Header *)v91 && v91 <= i1->pLast )
                goto LABEL_142;
            }
          }
          else
          {
LABEL_142:
            v112->pCurr = v91;
          }
          continue;
        case 8:
          v132 = this->_scanner._pCharacterSource;
          v133 = this->_alloc._pBlock;
          v282.pwh = 0;
          v282.n = 0;
          v134 = v132->_sourceType;
          v135 = v133->pCurr;
          if ( v134 )
          {
            if ( v134 == Utf16 )
            {
LABEL_274:
              v136 = LODWORD(v132->_pbCurr) - 2 * v132->_lDelta - LODWORD(v132->_pbSeg);
            }
            else
            {
              switch ( v134 )
              {
                case Utf16B:
                case Ucs2:
                case Ucs2B:
                case CodePage:
                  goto LABEL_274;
                case Ucs4:
                case Ucs4B:
                  v136 = LODWORD(v132->_pbCurr) - 4 * v132->_lDelta - LODWORD(v132->_pbSeg);
                  break;
                default:
                  goto LABEL_184;
              }
            }
          }
          else
          {
LABEL_184:
            v136 = 2 * (LODWORD(v132->_pbCurr) - v132->_lDelta - LODWORD(v132->_pbSeg));
          }
          v137 = (wchar_t *)v133->pCurr;
          if ( LODWORD(v133->pLast) - (int)v135 >= v136 )
            goto LABEL_190;
          while ( 1 )
          {
            v138 = v133->pNext;
            if ( !v138 )
              break;
            v133 = v133->pNext;
            if ( LODWORD(v138->pLast) - (int)v138 - 32 >= v136 )
            {
              v133->pCurr = (unsigned __int8 *)&v133[1];
              goto LABEL_189;
            }
          }
          if ( v136 + 32 < v136 )
            goto LABEL_63;
          v196 = v133->pLast - (unsigned __int8 *)v133;
          if ( v196 > 0xFFFFFFFF )
            goto LABEL_63;
          while ( 1 )
          {
            v197 = (unsigned int)v196;
            if ( (unsigned int)v196 >= v136 + 32 )
              break;
            LODWORD(v196) = 2 * v196;
            if ( (unsigned __int64)(2 * v197) > 0xFFFFFFFF )
              goto LABEL_63;
          }
          v198 = new_array<unsigned char>((unsigned int)v196);
          *(_QWORD *)v198 = v133;
          *((_QWORD *)v198 + 2) = v198 + 32;
          *((_QWORD *)v198 + 3) = &v198[v197];
          *((_QWORD *)v198 + 1) = 0;
          v133->pNext = (BlockAlloc::Header *)v198;
          v133 = (BlockAlloc::Header *)v198;
LABEL_189:
          this->_alloc._pBlock = v133;
          v137 = (wchar_t *)v133->pCurr;
LABEL_190:
          v133->pCurr += v136;
          v139 = this->_scanner._pCharacterSource;
          v140 = v136 >> 1;
          v282.pwh = v137;
          v282.n = v140;
          v141 = v139->_sourceType;
          if ( v141 == Utf16B )
          {
            v199 = v137;
            v200 = (unsigned __int16 *)v139->_pbSeg;
            v201 = (unsigned __int64)&v139->_pbCurr[-2 * v139->_lDelta];
            while ( 1 )
            {
              v142 = v199 - v137;
              if ( (unsigned __int64)v200 >= v201 )
                break;
              if ( (unsigned int)v142 >= v140 )
                goto LABEL_206;
              *v199++ = _byteswap_ushort(*v200++);
            }
          }
          else if ( v141 )
          {
            switch ( v141 )
            {
              case Utf16:
                v223 = (unsigned int)(LODWORD(v139->_pbCurr) - 2 * v139->_lDelta - LODWORD(v139->_pbSeg));
                if ( (v223 + 1) >> 1 > v140 )
                  goto LABEL_206;
                LODWORD(v142) = (unsigned int)v223 >> 1;
                memcpy_0(v137, v139->_pbSeg, v223);
                goto LABEL_194;
              case Ucs2:
                if ( ((unsigned __int64)(unsigned int)(LODWORD(v139->_pbCurr) - 2 * v139->_lDelta - LODWORD(v139->_pbSeg))
                    + 1) >> 1 > v140 )
                  goto LABEL_206;
                LODWORD(v142) = (unsigned int)(LODWORD(v139->_pbCurr) - 2 * v139->_lDelta - LODWORD(v139->_pbSeg)) >> 1;
                memcpy_0(
                  v137,
                  v139->_pbSeg,
                  (unsigned int)(LODWORD(v139->_pbCurr) - 2 * v139->_lDelta - LODWORD(v139->_pbSeg)));
                goto LABEL_194;
              case Ucs2B:
                v237 = (unsigned __int16 *)v139->_pbSeg;
                v238 = (unsigned __int64)&v139->_pbCurr[-2 * v139->_lDelta];
                v239 = v137;
                break;
              case Ucs4:
                Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v139, &v282);
                goto LABEL_193;
              case Ucs4B:
                Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v139, &v282);
                goto LABEL_193;
              case CodePage:
                Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v139, &v282);
                goto LABEL_193;
              default:
                goto LABEL_192;
            }
            while ( 1 )
            {
              v142 = v239 - v137;
              if ( (unsigned __int64)v237 >= v238 )
                break;
              if ( (unsigned int)v142 >= v140 )
                goto LABEL_206;
              *v239++ = _byteswap_ushort(*v237++);
            }
          }
          else
          {
LABEL_192:
            Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v139, &v282);
LABEL_193:
            LODWORD(v142) = v282.n;
          }
LABEL_194:
          v42 = this->_pfnWhitespace(this->_pContentHandler._p, v282.pwh, v142);
          v43 = v42;
          if ( v42 < 0 )
            goto LABEL_342;
          v143 = this->_alloc._pBlock;
          if ( v143 >= (BlockAlloc::Header *)v135 || v135 > v143->pCurr )
          {
            while ( 1 )
            {
              v143 = v143->pPrev;
              this->_alloc._pBlock = v143;
              if ( !v143 )
                break;
              if ( v143 < (BlockAlloc::Header *)v135 && v135 <= v143->pLast )
              {
                v143->pCurr = v135;
                goto $Continue;
              }
            }
          }
          else
          {
            v143->pCurr = v135;
          }
          continue;
        case 9:
          v126 = this->_alloc._pBlock;
          v127 = v126->pCurr;
          if ( (unsigned int)(LODWORD(v126->pLast) - (_DWORD)v127) >= 2 )
          {
            v194 = (wchar_t *)v126->pCurr;
          }
          else
          {
            while ( 1 )
            {
              v128 = v126->pNext;
              if ( !v128 )
                break;
              v126 = v126->pNext;
              if ( (unsigned int)(LODWORD(v128->pLast) - (_DWORD)v128 - 32) >= 2 )
              {
                v126->pCurr = (unsigned __int8 *)&v126[1];
                goto LABEL_268;
              }
            }
            v129 = v126->pLast - (unsigned __int8 *)v126;
            if ( v129 > 0xFFFFFFFF )
              goto LABEL_63;
            while ( 1 )
            {
              v130 = (unsigned int)v129;
              if ( (unsigned int)v129 >= 0x22 )
                break;
              LODWORD(v129) = 2 * v129;
              if ( (unsigned __int64)(2 * v130) > 0xFFFFFFFF )
                goto LABEL_63;
            }
            v131 = new_array<unsigned char>((unsigned int)v129);
            *(_QWORD *)v131 = v126;
            *((_QWORD *)v131 + 2) = v131 + 32;
            *((_QWORD *)v131 + 3) = &v131[v130];
            *((_QWORD *)v131 + 1) = 0;
            v126->pNext = (BlockAlloc::Header *)v131;
            v126 = (BlockAlloc::Header *)v131;
LABEL_268:
            this->_alloc._pBlock = v126;
            v194 = (wchar_t *)v126->pCurr;
          }
          v126->pCurr += 2;
          *v194 = 10;
          v42 = this->_pfnWhitespace(this->_pContentHandler._p, v194, 1);
          v43 = v42;
          if ( v42 < 0 )
            goto LABEL_342;
          v195 = this->_alloc._pBlock;
          if ( v195 >= (BlockAlloc::Header *)v127 || v127 > v195->pCurr )
          {
            while ( 1 )
            {
              v195 = v195->pPrev;
              this->_alloc._pBlock = v195;
              if ( !v195 )
                break;
              if ( v195 < (BlockAlloc::Header *)v127 && v127 <= v195->pLast )
              {
                v195->pCurr = v127;
                goto $Continue;
              }
            }
          }
          else
          {
            v195->pCurr = v127;
          }
          continue;
        case 10:
          v163 = this->_scanner._pCharacterSource;
          v164 = this->_alloc._pBlock;
          v277.pwh = 0;
          v277.n = 0;
          v165 = v163->_sourceType;
          v166 = v164->pCurr;
          if ( v165 )
          {
            if ( v165 == Utf16 )
            {
LABEL_284:
              v167 = LODWORD(v163->_pbCurr) - 2 * v163->_lDelta - LODWORD(v163->_pbSeg);
            }
            else
            {
              switch ( v165 )
              {
                case Utf16B:
                case Ucs2:
                case Ucs2B:
                case CodePage:
                  goto LABEL_284;
                case Ucs4:
                case Ucs4B:
                  v167 = LODWORD(v163->_pbCurr) - 4 * v163->_lDelta - LODWORD(v163->_pbSeg);
                  break;
                default:
                  goto LABEL_222;
              }
            }
          }
          else
          {
LABEL_222:
            v167 = 2 * (LODWORD(v163->_pbCurr) - v163->_lDelta - LODWORD(v163->_pbSeg));
          }
          if ( LODWORD(v164->pLast) - (int)v166 >= v167 )
          {
            v202 = (wchar_t *)v164->pCurr;
          }
          else
          {
            while ( 1 )
            {
              v168 = v164->pNext;
              if ( !v168 )
                break;
              v164 = v164->pNext;
              if ( LODWORD(v168->pLast) - (int)v168 - 32 >= v167 )
              {
                v164->pCurr = (unsigned __int8 *)&v164[1];
                goto LABEL_287;
              }
            }
            if ( v167 + 32 < v167 )
              goto LABEL_63;
            v169 = v164->pLast - (unsigned __int8 *)v164;
            if ( v169 > 0xFFFFFFFF )
              goto LABEL_63;
            while ( 1 )
            {
              v170 = (unsigned int)v169;
              if ( (unsigned int)v169 >= v167 + 32 )
                break;
              LODWORD(v169) = 2 * v169;
              if ( (unsigned __int64)(2 * v170) > 0xFFFFFFFF )
                goto LABEL_63;
            }
            v171 = new_array<unsigned char>((unsigned int)v169);
            *(_QWORD *)v171 = v164;
            *((_QWORD *)v171 + 2) = v171 + 32;
            *((_QWORD *)v171 + 3) = &v171[v170];
            *((_QWORD *)v171 + 1) = 0;
            v164->pNext = (BlockAlloc::Header *)v171;
            v164 = (BlockAlloc::Header *)v171;
LABEL_287:
            this->_alloc._pBlock = v164;
            v202 = (wchar_t *)v164->pCurr;
          }
          v164->pCurr += v167;
          v203 = this->_scanner._pCharacterSource;
          v204 = v167 >> 1;
          v277.pwh = v202;
          v277.n = v204;
          v205 = v203->_sourceType;
          if ( v205 == Utf16B )
          {
            v206 = v202;
            v207 = (unsigned __int16 *)v203->_pbSeg;
            v208 = (unsigned __int64)&v203->_pbCurr[-2 * v203->_lDelta];
            while ( 1 )
            {
              v209 = v206 - v202;
              if ( (unsigned __int64)v207 >= v208 )
                break;
              if ( (unsigned int)v209 >= v204 )
                goto LABEL_206;
              *v206++ = _byteswap_ushort(*v207++);
            }
          }
          else
          {
            if ( v205 == Utf8 )
            {
LABEL_290:
              Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v203, &v277);
              v202 = v277.pwh;
              goto LABEL_296;
            }
            switch ( v205 )
            {
              case Utf16:
              case Ucs2:
                v224 = (unsigned int)(LODWORD(v203->_pbCurr) - 2 * v203->_lDelta - LODWORD(v203->_pbSeg));
                if ( (v224 + 1) >> 1 > v204 )
                  goto LABEL_206;
                v225 = v203->_pbSeg;
                v277.n = (unsigned int)v224 >> 1;
                memcpy_0(v202, v225, v224);
                goto LABEL_296;
              case Ucs2B:
                v240 = (unsigned __int16 *)v203->_pbSeg;
                v241 = (unsigned __int64)&v203->_pbCurr[-2 * v203->_lDelta];
                v242 = v202;
                break;
              case Ucs4:
                Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v203, &v277);
                v202 = v277.pwh;
                goto LABEL_296;
              case Ucs4B:
                Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v203, &v277);
                v202 = v277.pwh;
                goto LABEL_296;
              case CodePage:
                Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v203, &v277);
                v202 = v277.pwh;
                goto LABEL_296;
              default:
                goto LABEL_290;
            }
            while ( 1 )
            {
              v209 = v242 - v202;
              if ( (unsigned __int64)v240 >= v241 )
                break;
              if ( (unsigned int)v209 >= v204 )
                goto LABEL_206;
              *v242++ = _byteswap_ushort(*v240++);
            }
          }
          v277.n = v209;
LABEL_296:
          if ( v277.n >= 1 && *v202 == 120 )
          {
            v210 = HexCharEntity2Utf16(v202 + 1, v277.n - 1, v202, &v277.n);
            if ( v210 < 0 )
            {
LABEL_436:
              MXRRaiseException(v210);
              __debugbreak();
            }
          }
          else
          {
            v210 = CharEntity2Utf16(v202, v277.n, v202, &v277.n);
            if ( v210 < 0 )
              goto LABEL_436;
          }
          v211 = this->_pContentHandler._p->characters(this->_pContentHandler._p, v277.pwh, v277.n);
          v212 = v211;
          if ( v211 < 0 )
          {
            Reader::OnCallbackFailure(v211);
            MXRRaiseException(v212);
            __debugbreak();
          }
          BlockAlloc::PopScope(&this->_alloc, v166);
          continue;
        case 11:
          Reader::ParseEntityRef(this, pScope, pnContext);
          v45 = pnContext[0];
          v33 = *(const wchar_t **)&context.qname.n;
          pScope = context.pAttributesScope;
          LODWORD(v274) = context.pScope;
          Buf1 = *(void **)&context.lname.n;
          puResult[0] = (unsigned int)context.lname.pwh;
          v279 = *(int **)&context.uri.n;
          v273 = LODWORD(context.prefix.pwh);
          continue;
        case 13:
          v149 = this->_pLexicalHandler._p;
          v285.pwh = 0;
          v285.n = 0;
          v150 = this->_alloc._pBlock->pCurr;
          v151 = v149->startCDATA(v149);
          if ( v151 < 0 )
            goto LABEL_210;
          break;
        case 15:
          Reader::ParseComment(this);
          continue;
        case 17:
          Reader::ParsePi(this);
          continue;
        case 59:
          --this->_ulCurrentElementDepth;
          v152 = *(_QWORD *)&this->_inputSources._pStack[8 * this->_inputSources._lSize - 8];
          v153 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v152 + 24LL))(v152);
          v154 = v153;
          if ( this->_inputSources._lSize == 1 )
          {
            MXRRaiseException(-1072894463);
            __debugbreak();
          }
          if ( *(_BYTE *)(v153 + 80) )
            --this->_nExternalMarkup;
          if ( *(void **)(v153 + 152) != pScope )
            goto LABEL_369;
          *(_QWORD *)(v153 + 152) = 0;
          Scanner::PopInputSource(&this->_scanner);
          v155 = this->_inputSources._lSize;
          this->_inputSources._lSize = v155 - 1;
          v156 = *(void (__fastcall ****)(_QWORD, __int64))&this->_inputSources._pStack[8 * v155 - 8];
          if ( v156 )
            (**v156)(v156, 1);
          v157 = this->_pLexicalHandler._p;
          pnContext[0] = --v45;
          endEntity = v157->endEntity;
          v159 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v154 + 8LL))(v154) + 8);
          v160 = (const wchar_t **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v154 + 8LL))(v154);
          v161 = endEntity(v157, *v160, v159);
          v162 = v161;
          if ( v161 < 0 )
          {
            Reader::OnCallbackFailure(v161);
            MXRRaiseException(v162);
            __debugbreak();
          }
          continue;
        default:
          continue;
      }
      do
      {
        while ( 2 )
        {
          Scanner::DoScan(&this->_scanner, (Scanner::ScanOp)*(_DWORD *)this->_scanner._scanOp);
          v267 = this->_scanner._nToken;
          if ( v267 == 7 )
          {
            v259 = this->_scanner._pCharacterSource;
            v260 = v259->_sourceType;
            if ( v260 )
            {
              if ( v260 == Utf16 )
              {
LABEL_405:
                v261 = LODWORD(v259->_pbCurr) - 2 * v259->_lDelta - LODWORD(v259->_pbSeg);
              }
              else
              {
                switch ( v260 )
                {
                  case Utf16B:
                  case Ucs2:
                  case Ucs2B:
                  case CodePage:
                    goto LABEL_405;
                  case Ucs4:
                  case Ucs4B:
                    v261 = LODWORD(v259->_pbCurr) - 4 * v259->_lDelta - LODWORD(v259->_pbSeg);
                    break;
                  default:
                    goto LABEL_409;
                }
              }
            }
            else
            {
LABEL_409:
              v261 = 2 * (LODWORD(v259->_pbCurr) - v259->_lDelta - LODWORD(v259->_pbSeg));
            }
            v262 = (wchar_t *)BlockAlloc::AllocData(&this->_alloc, v261);
            v285.n = v261 >> 1;
            v285.pwh = v262;
            Scanner::GetSegmentValue(&this->_scanner, &v285);
            v263 = this->_pContentHandler._p->characters(this->_pContentHandler._p, v285.pwh, v285.n);
LABEL_407:
            v151 = v263;
            if ( v263 < 0 )
              goto LABEL_210;
            continue;
          }
          break;
        }
        if ( v267 == 9 )
        {
          v268 = (wchar_t *)BlockAlloc::AllocData(&this->_alloc, 2u);
          v285.n = 1;
          *v268 = 10;
          v263 = this->_pContentHandler._p->characters(this->_pContentHandler._p, v268, 1);
          goto LABEL_407;
        }
      }
      while ( v267 != 14 );
      v151 = this->_pLexicalHandler._p->endCDATA(this->_pLexicalHandler._p);
      if ( v151 < 0 )
      {
LABEL_210:
        Reader::OnCallbackFailure(v151);
        MXRRaiseException(v151);
        __debugbreak();
      }
      BlockAlloc::PopScope(&this->_alloc, v150);
    }
    v47 = this->_scanner._pCharacterSource;
    v48 = 0;
    v284.pwh = 0;
    v284.n = 0;
    v49 = v47->_sourceType;
    if ( v49 )
    {
      if ( v49 == Utf16 )
      {
LABEL_60:
        v50 = LODWORD(v47->_pbCurr) - 2 * v47->_lDelta - LODWORD(v47->_pbSeg);
      }
      else
      {
        switch ( v49 )
        {
          case Utf16B:
          case Ucs2:
          case Ucs2B:
          case CodePage:
            goto LABEL_60;
          case Ucs4:
          case Ucs4B:
            v50 = LODWORD(v47->_pbCurr) - 4 * v47->_lDelta - LODWORD(v47->_pbSeg);
            break;
          default:
            goto LABEL_54;
        }
      }
    }
    else
    {
LABEL_54:
      v50 = 2 * (LODWORD(v47->_pbCurr) - v47->_lDelta - LODWORD(v47->_pbSeg));
    }
    v51 = this->_alloc._pBlock;
    v52 = (wchar_t *)v51->pCurr;
    if ( LODWORD(v51->pLast) - (int)v52 < v50 )
    {
      while ( 1 )
      {
        v72 = v51->pNext;
        if ( !v72 )
          break;
        v51 = v51->pNext;
        if ( LODWORD(v72->pLast) - (int)v72 - 32 >= v50 )
        {
          v51->pCurr = (unsigned __int8 *)&v51[1];
          goto LABEL_127;
        }
      }
      if ( v50 + 32 < v50 )
        goto LABEL_63;
      v73 = v51->pLast - (unsigned __int8 *)v51;
      if ( v73 > 0xFFFFFFFF )
        goto LABEL_63;
      while ( 1 )
      {
        v74 = (unsigned int)v73;
        if ( (unsigned int)v73 >= v50 + 32 )
          break;
        LODWORD(v73) = 2 * v73;
        if ( (unsigned __int64)(2 * v74) > 0xFFFFFFFF )
          goto LABEL_63;
      }
      v75 = new_array<unsigned char>((unsigned int)v73);
      *(_QWORD *)v75 = v51;
      *((_QWORD *)v75 + 2) = v75 + 32;
      *((_QWORD *)v75 + 3) = &v75[v74];
      v48 = 0;
      *((_QWORD *)v75 + 1) = 0;
      v51->pNext = (BlockAlloc::Header *)v75;
      v51 = (BlockAlloc::Header *)v75;
LABEL_127:
      this->_alloc._pBlock = v51;
      v52 = (wchar_t *)v51->pCurr;
    }
    v51->pCurr += v50;
    v53 = this->_scanner._pCharacterSource;
    v54 = v50 >> 1;
    v284.pwh = v52;
    v284.n = v54;
    v55 = v53->_sourceType;
    if ( v55 == Utf16B )
    {
      v58 = v52;
      v59 = (unsigned __int16 *)v53->_pbSeg;
      v60 = (unsigned __int64)&v53->_pbCurr[-2 * v53->_lDelta];
      while ( (unsigned __int64)v59 < v60 )
      {
        if ( (unsigned int)(v58 - v52) >= v54 )
          goto LABEL_206;
        *v58++ = _byteswap_ushort(*v59++);
      }
      LODWORD(v56) = v58 - v52;
    }
    else if ( v55 )
    {
      switch ( v55 )
      {
        case Utf16:
          v98 = (unsigned int)(LODWORD(v53->_pbCurr) - 2 * v53->_lDelta - LODWORD(v53->_pbSeg));
          if ( (v98 + 1) >> 1 > v54 )
            goto LABEL_206;
          LODWORD(v56) = (unsigned int)v98 >> 1;
          memcpy_0(v52, v53->_pbSeg, v98);
          goto LABEL_69;
        case Ucs2:
          if ( ((unsigned __int64)(unsigned int)(LODWORD(v53->_pbCurr) - 2 * v53->_lDelta - LODWORD(v53->_pbSeg)) + 1) >> 1 > v54 )
            goto LABEL_206;
          LODWORD(v56) = (unsigned int)(LODWORD(v53->_pbCurr) - 2 * v53->_lDelta - LODWORD(v53->_pbSeg)) >> 1;
          memcpy_0(v52, v53->_pbSeg, (unsigned int)(LODWORD(v53->_pbCurr) - 2 * v53->_lDelta - LODWORD(v53->_pbSeg)));
          goto LABEL_69;
        case Ucs2B:
          v122 = v52;
          v123 = (unsigned __int16 *)v53->_pbSeg;
          v124 = (unsigned __int64)&v53->_pbCurr[-2 * v53->_lDelta];
          while ( 2 )
          {
            v56 = v122 - v52;
            if ( (unsigned __int64)v123 >= v124 )
              goto LABEL_69;
            if ( (unsigned int)v56 < v54 )
            {
              *v122++ = _byteswap_ushort(*v123++);
              continue;
            }
            goto LABEL_206;
          }
        case Ucs4:
          v172 = v52;
          v173 = v53->_pbSeg;
          v174 = (unsigned __int64)&v53->_pbCurr[-4 * v53->_lDelta];
          break;
        case Ucs4B:
          Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v53, &v284);
          LODWORD(v56) = v284.n;
          goto LABEL_69;
        case CodePage:
          Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v53, &v284);
          LODWORD(v56) = v284.n;
          goto LABEL_69;
        default:
          goto LABEL_58;
      }
      while ( 1 )
      {
        v56 = v172 - v52;
        if ( (unsigned __int64)(v173 + 3) >= v174 )
          break;
        if ( (unsigned int)v56 >= v54 )
          goto LABEL_206;
        v175 = *(_DWORD *)v173;
        if ( *(_DWORD *)v173 > 0xFFFFu )
        {
          *v172 = (v175 >> 10) - 10304;
          if ( (unsigned int)(v172 + 1 - v52) >= v54 )
            goto LABEL_206;
          v172[1] = v175 & 0x3FF | 0xDC00;
          v172 += 2;
          v173 += 4;
        }
        else
        {
          *v172++ = v175;
          v173 += 4;
        }
      }
    }
    else
    {
LABEL_58:
      Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v53, &v284);
      LODWORD(v56) = v284.n;
    }
LABEL_69:
    v61 = v273;
    if ( (_DWORD)v56 != (_DWORD)v273 || memcmp_0(v284.pwh, v33, 2LL * (int)v56) )
    {
      MXRRaiseException(-1072894405);
      __debugbreak();
    }
    if ( v45 )
    {
LABEL_369:
      MXRRaiseException(-1072894394);
      __debugbreak();
    }
    v43 = this->_pContentHandler._p->endElement(
            this->_pContentHandler._p,
            (const wchar_t *)v279,
            puResult[0],
            (const wchar_t *)Buf1,
            (int)v274,
            v33,
            v61);
    if ( v43 < 0 )
    {
      v84 = NewParserCallbackFailureTrackingRegistry::s_fInitialized;
      if ( !NewParserCallbackFailureTrackingRegistry::s_fInitialized )
      {
        NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled = 0;
        NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled = 0;
        Registry::readMultipleSettings(NewParserCallbackFailureTrackingRegistry::s_rgSettings);
        v84 = 1;
        NewParserCallbackFailureTrackingRegistry::s_fInitialized = 1;
      }
      if ( NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled )
      {
        LODWORD(pLName) = GetCurrentThreadId();
        StringCchPrintfW(
          pszDest,
          0x80u,
          L"SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\r\n",
          (unsigned int)v43,
          pLName);
        OutputDebugStringW(pszDest);
        v84 = NewParserCallbackFailureTrackingRegistry::s_fInitialized;
      }
      if ( !v84 )
      {
        NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled = 0;
        NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled = 0;
        Registry::readMultipleSettings(NewParserCallbackFailureTrackingRegistry::s_rgSettings);
        NewParserCallbackFailureTrackingRegistry::s_fInitialized = 1;
      }
      if ( NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled )
        MEMORY[0] = 0;
      goto $CleanUp_2;
    }
  }
}

```

## disassembly

```asm
0x180020de0  mov     rax, rsp
0x180020de3  push    rbp
0x180020de4  push    rbx
0x180020de5  push    rsi
0x180020de6  push    rdi
0x180020de7  push    r12
0x180020de9  push    r13
0x180020deb  push    r14
0x180020ded  push    r15
0x180020def  lea     rbp, [rax-288h]
0x180020df6  sub     rsp, 348h
0x180020dfd  movaps  xmmword ptr [rax-58h], xmm6
0x180020e01  movaps  xmmword ptr [rax-68h], xmm7
0x180020e05  movaps  xmmword ptr [rax-78h], xmm8
0x180020e0a  movaps  xmmword ptr [rax-88h], xmm9
0x180020e12  movaps  xmmword ptr [rax-98h], xmm10
0x180020e1a  movaps  xmmword ptr [rax-0A8h], xmm11
0x180020e22  movaps  xmmword ptr [rax-0B8h], xmm12
0x180020e2a  movaps  xmmword ptr [rax-0C8h], xmm13
0x180020e32  mov     rax, cs:__security_cookie
0x180020e39  xor     rax, rsp
0x180020e3c  mov     [rbp+280h+var_D0], rax
0x180020e43  xor     r12d, r12d
0x180020e46  mov     rbx, this
0x180020e49  mov     qword ptr [rbp+280h+context.qname.n], r12
0x180020e4d  mov     dword ptr [rbp+280h+context.prefix.pwh], r12d
0x180020e51  mov     qword ptr [rbp+280h+context.prefix.n], r12
0x180020e55  mov     dword ptr [rbp+280h+context.uri.pwh], r12d
0x180020e59  mov     qword ptr [rbp+280h+context.uri.n], r12
0x180020e5d  mov     dword ptr [rbp+280h+context.lname.pwh], r12d
0x180020e61  mov     qword ptr [rbp+280h+context.lname.n], r12
0x180020e65  mov     dword ptr [rbp+280h+context.pScope], r12d
0x180020e69  mov     r13d, 0DC00h
0x180020e6f  lea     r8, __ImageBase
0x180020e76  mov     r11d, 3FFh
0x180020e7c  mov     r9d, 0FFFFFFFFh
0x180020e82  nop     dword ptr [rax+00h]
0x180020e86  nop     word ptr [rax+rax+00000000h]
0x180020e90  inc     dword ptr [rbx+900h]
0x180020e96  mov     eax, [rbx+8F8h]
0x180020e9c  test    eax, eax
0x180020e9e  jz      short loc_180020EAC
0x180020ea0  cmp     [rbx+900h], eax
0x180020ea6  ja      loc_180021FDA
0x180020eac  mov     rsi, [rbx+98h]
0x180020eb3  mov     rdx, [rbx+30h]
0x180020eb7  mov     r15, [rsi+10h]
0x180020ebb  mov     eax, [rdx+58h]
0x180020ebe  mov     [rbp+280h+pScope], r15
0x180020ec2  mov     [rbp+280h+context.pAttributesScope], r15
0x180020ec6  test    eax, eax
0x180020ec8  jnz     short loc_180020F31
0x180020eca  mov     edi, [rdx+20h]; jumptable 0000000180022D50 default case
0x180020ecd  sub     edi, [rdx+38h]
0x180020ed0  sub     edi, [rdx+28h]
0x180020ed3  add     edi, edi
0x180020ed5  mov     eax, [rsi+18h]
0x180020ed8  mov     r14, r15
0x180020edb  sub     eax, r15d
0x180020ede  mov     [rsp+380h+Buf1], r15
0x180020ee3  cmp     eax, edi
0x180020ee5  jb      loc_180021250
0x180020eeb  mov     eax, edi
0x180020eed  add     [rsi+10h], rax
0x180020ef1  mov     r9, [rbx+30h]
0x180020ef5  shr     edi, 1
0x180020ef7  mov     qword ptr [rbp+280h+context.qname.n], r14
0x180020efb  mov     dword ptr [rbp+280h+context.prefix.pwh], edi
0x180020efe  mov     eax, [r9+58h]
0x180020f02  cmp     eax, 2
0x180020f05  jz      short loc_180020F49
0x180020f07  test    eax, eax
0x180020f09  jnz     loc_1800215A5
0x180020f0f  lea     rdx, [rbp+280h+context.qname.n]; jumptable 00000001800215BD default case, case 2
0x180020f13  mov     this, r9; this
0x180020f16  call    ?GetSegmentValue@Utf8CharacterSource@@QEAAXPEAUStringPtr@@@Z; Utf8CharacterSource::GetSegmentValue(StringPtr *)
0x180020f1b  mov     rsi, [rbp+280h+context.pAttributesScope]
0x180020f1f  mov     r14, qword ptr [rbp+280h+context.qname.n]
0x180020f23  mov     [rbp+280h+pScope], rsi
0x180020f27  mov     esi, dword ptr [rbp+280h+context.prefix.pwh]
0x180020f2a  mov     [rsp+380h+Buf1], r14
0x180020f2f  jmp     short loc_180020F95
0x180020f31  cmp     eax, 1
0x180020f34  jnz     loc_180022D37
0x180020f3a  mov     eax, [rdx+38h]; jumptable 0000000180022D50 cases 2-4,7
0x180020f3d  mov     edi, [rdx+20h]
0x180020f40  add     eax, eax
0x180020f42  sub     edi, eax
0x180020f44  sub     edi, [rdx+28h]
0x180020f47  jmp     short loc_180020ED5
0x180020f49  movsxd  rax, dword ptr [r9+38h]
0x180020f4d  mov     r8, r14
0x180020f50  mov     r10, [r9+20h]
0x180020f54  add     rax, rax
0x180020f57  mov     rdx, [r9+28h]
0x180020f5b  sub     r10, rax
0x180020f5e  mov     rax, r8
0x180020f61  sub     rax, r14
0x180020f64  sar     rax, 1
0x180020f67  cmp     rdx, r10
0x180020f6a  jnb     short loc_180020F90
0x180020f6c  cmp     eax, edi
0x180020f6e  jnb     loc_180021D35
0x180020f74  movzx   eax, byte ptr [rdx]
0x180020f77  movzx   ecx, byte ptr [rdx+1]
0x180020f7b  shl     ax, 8
0x180020f7f  or      cx, ax
0x180020f82  mov     [r8], cx
0x180020f86  add     r8, 2
0x180020f8a  add     rdx, 2
0x180020f8e  jmp     short loc_180020F5E
0x180020f90  mov     esi, eax
0x180020f92  mov     dword ptr [rbp+280h+context.prefix.pwh], eax
0x180020f95  mov     [rsp+380h+var_328], rsi
0x180020f9a  mov     edi, [rbx+7Ch]
0x180020f9d  lea     r13, [rbx+128h]
0x180020fa4  inc     dword ptr [r13+0]
0x180020fa8  mov     this, rbx; this
0x180020fab  mov     rax, [rbx+98h]
0x180020fb2  mov     qword ptr [rbp+280h+context.prefix.n], r14
0x180020fb6  mov     dword ptr [rsp+380h+var_320], edi
0x180020fba  mov     dword ptr [rbp+280h+context.uri.pwh], edi
0x180020fbd  mov     r12, [rax+10h]
0x180020fc1  mov     qword ptr [rbp+280h+context.nContext], r12
0x180020fc5  call    ?ParseAttributesN@Reader@@AEAAXXZ; Reader::ParseAttributesN(void)
0x180020fca  movsxd  r14, dword ptr [rbx+0C0h]
0x180020fd1  test    r14d, r14d
0x180020fd4  jnz     loc_180022092
0x180020fda  cmp     [rbx+0D8h], r14d
0x180020fe1  jz      short loc_18002103C
0x180020fe3  mov     r15, [rbx+0B8h]
0x180020fea  imul    rsi, r14, 78h ; 'x'
0x180020fee  mov     rdi, r15
0x180020ff1  add     rsi, r15
0x180020ff4  cmp     rdi, rsi
0x180020ff7  jnb     short loc_180021029
0x180020ff9  movsxd  rdx, dword ptr [rdi+18h]
0x180020ffd  test    edx, edx
0x180020fff  jnz     loc_180021FE5
0x180021005  movups  xmm0, xmmword ptr [rdi]
0x180021008  movups  xmmword ptr [rdi+30h], xmm0
0x18002100c  movups  xmm1, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::empty ...
0x180021013  movups  xmmword ptr [rdi+20h], xmm1
0x180021017  mov     r14, r15
0x18002101a  cmp     r14, rdi
0x18002101d  jb      loc_18002148C
0x180021023  add     rdi, 78h ; 'x'
0x180021027  jmp     short loc_180020FF4
0x180021029  mov     edi, dword ptr [rsp+380h+var_320]
0x18002102d  movsxd  rax, dword ptr [rbx+0D8h]
0x180021034  test    eax, eax
0x180021036  jnz     loc_180022A33
0x18002103c  movsxd  rdx, dword ptr [rbx+138h]
0x180021043  xor     r10d, r10d
0x180021046  mov     r9, [rbx+130h]
0x18002104d  mov     r8d, [rbx+128h]
0x180021054  mov     dword ptr [rsp+380h+var_310], r10d
0x180021059  lea     this, [rdx+rdx*2]
0x18002105d  add     this, this
0x180021060  cmp     [r9+this*8-10h], r8d
0x180021065  jnz     short loc_180021087
0x180021067  sub     edx, 1
0x18002106a  js      short loc_180021087
0x18002106c  lea     this, [rdx+rdx*2]
0x180021070  add     this, this
0x180021073  cmp     [r9+this*8+20h], r8d
0x180021078  jnz     short loc_180021082
0x18002107a  inc     r10d
0x18002107d  sub     edx, 1
0x180021080  jns     short loc_18002106C
0x180021082  mov     dword ptr [rsp+380h+var_310], r10d
0x180021087  mov     [rbp+280h+pnContext], r10d
0x18002108b  test    r10d, r10d
0x18002108e  jnz     loc_180022788
0x180021094  mov     r13, [rsp+380h+Buf1]
0x180021099  test    edi, edi
0x18002109b  jnz     loc_18002294B
0x1800210a1  mov     ecx, dword ptr [rsp+380h+var_328]
0x1800210a5  xor     r8d, r8d
0x1800210a8  mov     eax, dword ptr [rbp+280h+context.prefix.pwh+4]
0x1800210ab  mov     dword ptr [rsp+380h+var_320], ecx
0x1800210af  mov     dword ptr [rbp+280h+context.pScope], ecx
0x1800210b2  mov     dword ptr [rbp+280h+context.pScope+4], eax
0x1800210b5  mov     [rsp+380h+Buf1], r13
0x1800210ba  mov     qword ptr [rbp+280h+context.lname.n], r13
0x1800210be  mov     rdx, [rbx+158h]
0x1800210c5  test    rdx, rdx
0x1800210c8  jz      loc_180022515
0x1800210ce  cmp     edi, [rdx+8]
0x1800210d1  jnz     loc_180022515
0x1800210d7  mov     rdx, [rdx]; Buf2
0x1800210da  add     r8, r8; Size
0x1800210dd  mov     this, r13; Buf1
0x1800210e0  call    memcmp_0
0x1800210e5  test    eax, eax
0x1800210e7  jnz     loc_180022515
0x1800210ed  mov     rax, [rbx+160h]
0x1800210f4  cmp     dword ptr [rbx+38h], 5
0x1800210f8  lea     rdx, [rbx+8]
0x1800210fc  mov     r14d, [rax+8]
0x180021100  mov     r8d, r14d
0x180021103  mov     rdi, [rax]
0x180021106  mov     eax, [rax+0Ch]
0x180021109  mov     this, [rbx+910h]
0x180021110  mov     r15d, dword ptr [rsp+380h+var_320]
0x180021115  mov     dword ptr [rbp+280h+context.lname.pwh+4], eax
0x180021118  mov     qword ptr [rbp+280h+context.uri.n], rdi
0x18002111c  mov     [rbp+280h+var_2F0], rdi
0x180021120  mov     [rsp+380h+var_348], rdx
0x180021125  mov     dword ptr [rbp+280h+context.lname.pwh], r14d
0x180021129  mov     [rsp+380h+puResult], r14d
0x18002112e  jnz     loc_18002193B
0x180021134  mov     rax, [this]
0x180021137  mov     rdx, [rsp+380h+var_328]
0x18002113c  mov     r9, [rsp+380h+Buf1]
0x180021141  mov     dword ptr [rsp+380h+var_350], edx
0x180021145  mov     rdx, rdi
0x180021148  mov     rax, [rax+40h]
0x18002114c  mov     qword ptr [rsp+380h+var_358], r13
0x180021151  mov     dword ptr [rsp+380h+pLName], r15d
0x180021156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002115b  mov     esi, eax
0x18002115d  test    eax, eax
0x18002115f  js      loc_180022876
0x180021165  mov     rax, [rbx+98h]
0x18002116c  cmp     rax, r12
0x18002116f  jnb     loc_180021B4D
0x180021175  cmp     r12, [rax+10h]
0x180021179  ja      loc_180021B4D
0x18002117f  mov     [rax+10h], r12
0x180021183  mov     r12d, dword ptr [rsp+380h+var_310]
0x180021188  mov     edx, [rbx+58h]; jumptable 000000018002162E default case, cases 12,14,16,18-58
0x18002118b  lea     this, [rbx+18h]; this
0x18002118f  call    ?DoScan@Scanner@@AEAAXW4ScanOp@1@@Z; Scanner::DoScan(Scanner::ScanOp)
0x180021194  mov     eax, [rbx+38h]
0x180021197  cmp     eax, 4
0x18002119a  jz      short loc_1800211BF
0x18002119c  cmp     eax, 3
0x18002119f  jnz     loc_180021605
0x1800211a5  cmp     dword ptr [rbx+900h], 3E8h
0x1800211af  jnb     loc_1800214B9
0x1800211b5  mov     this, rbx; this
0x1800211b8  call    ?ParseElementN@Reader@@AEAAXXZ; Reader::ParseElementN(void)
0x1800211bd  jmp     short $Continue; jumptable 000000018002162E default case, cases 12,14,16,18-58
0x1800211bf  mov     rdx, [rbx+30h]
0x1800211c3  xor     r14d, r14d
0x1800211c6  mov     [rbp+280h+var_260.pwh], r14
0x1800211ca  mov     [rbp+280h+var_260.n], r14d
0x1800211ce  mov     eax, [rdx+58h]
0x1800211d1  test    eax, eax
0x1800211d3  jnz     short loc_180021231
0x1800211d5  mov     edi, [rdx+20h]; jumptable 000000018002304A default case
0x1800211d8  sub     edi, [rdx+38h]
0x1800211db  sub     edi, [rdx+28h]
0x1800211de  add     edi, edi
0x1800211e0  mov     rsi, [rbx+98h]
0x1800211e7  mov     r9, [rsi+10h]
0x1800211eb  mov     eax, [rsi+18h]
0x1800211ee  sub     eax, r9d
0x1800211f1  cmp     eax, edi
0x1800211f3  jb      loc_180021422
0x1800211f9  mov     eax, edi
0x1800211fb  add     [rsi+10h], rax
0x1800211ff  mov     r10, [rbx+30h]
0x180021203  shr     edi, 1
0x180021205  mov     [rbp+280h+var_260.pwh], r9
0x180021209  mov     [rbp+280h+var_260.n], edi
0x18002120c  mov     eax, [r10+58h]
0x180021210  cmp     eax, 2
0x180021213  jz      short loc_180021273
0x180021215  test    eax, eax
0x180021217  jnz     loc_180021711
0x18002121d  lea     rdx, [rbp+280h+var_260]; jumptable 000000018002172F default case, case 2
0x180021221  mov     this, r10; this
0x180021224  call    ?GetSegmentValue@Utf8CharacterSource@@QEAAXPEAUStringPtr@@@Z; Utf8CharacterSource::GetSegmentValue(StringPtr *)
0x180021229  mov     esi, [rbp+280h+var_260.n]
0x18002122c  jmp     loc_1800212BC
0x180021231  cmp     eax, 1
0x180021234  jnz     loc_18002302A
0x18002123a  mov     eax, [rdx+38h]; jumptable 000000018002304A cases 2-4,7
0x18002123d  mov     edi, [rdx+20h]
0x180021240  add     eax, eax
0x180021242  sub     edi, eax
0x180021244  sub     edi, [rdx+28h]
0x180021247  jmp     short loc_1800211E0
0x180021250  mov     rax, [rsi+8]
0x180021254  test    rax, rax
0x180021257  jnz     loc_1800216E1
0x18002125d  lea     eax, [rdi+20h]
0x180021260  cmp     eax, edi
0x180021262  jnb     loc_180021829
0x180021268  mov     ecx, 80070216h; hr
0x18002126d  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x180021272  int     3; Trap to Debugger
0x180021273  movsxd  rax, dword ptr [r10+38h]
0x180021277  mov     r8, r9
0x18002127a  mov     r11, [r10+20h]
0x18002127e  add     rax, rax
0x180021281  mov     rdx, [r10+28h]
0x180021285  sub     r11, rax
  ... truncated ...
```
