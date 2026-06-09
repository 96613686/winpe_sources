# Reader::ParseElementN(void)

- ea: `0x180014550`
- end: `0x180016ab0`
- name: `?ParseElementN@Reader@@AEAAXXZ`
- size: `9568`
- prototype: `void __fastcall(Reader *this)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014550`
- `0x180026578`

## callees

- `0x18000ae54`
- `0x180010f20`
- `0x180011830`
- `0x180011ad0`
- `0x180011d24`
- `0x180011d4c`
- `0x180011e90`
- `0x180013fec`
- `0x180014020`
- `0x180014254`
- `0x180014550`
- `0x180016ac0`
- `0x180024fb4`
- `0x18002676c`
- `0x1800269c0`
- `0x180028a74`
- `0x180028c90`
- `0x180029870`
- `0x180029950`
- `0x180029a20`
- `0x18002dd48`
- `0x180071640`
- `0x18007797c`
- `0x1800bc810`
- `0x1800bce48`
- `0x1800bf3e0`
- `0x1800c0254`
- `0x1800cac00`
- `0x1800cada0`
- `0x1800cba94`
- `0x180174f4c`
- `0x18017851c`
- `0x180178528`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001682c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800168c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001682c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800168c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016858`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800168f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016858`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800168f0`

## string_xrefs

- `0x180016835`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`
- `0x1800168cd`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`

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
  char *v33; // r13
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
  unsigned int nHashSeed; // r14d
  unsigned __int16 *v244; // rcx
  unsigned __int16 *v245; // rdx
  int v246; // eax
  int ii; // edx
  char *v248; // rsi
  char *n; // r14
  StringPtr v250; // xmm6
  StringPtr v251; // xmm7
  StringPtr v252; // xmm8
  StringPtr v253; // xmm9
  StringPtr v254; // xmm10
  StringPtr v255; // xmm11
  __int128 v256; // xmm12
  __int64 v257; // xmm13_8
  Attribute *v258; // rax
  unsigned int v259; // ecx
  __int64 v260; // rax
  char *v261; // rax
  CharacterSource *v262; // rdx
  SourceType v263; // eax
  unsigned int v264; // esi
  wchar_t *v265; // rax
  int v266; // eax
  HRESULT v267; // eax
  unsigned int v268; // esi
  unsigned int *v269; // rdi
  int v270; // eax
  wchar_t *v271; // r9
  StringPtr *pLName; // [rsp+28h] [rbp-E0h]
  StringPtr *pLNamea; // [rsp+28h] [rbp-E0h]
  IMXRAttributes *v274; // [rsp+40h] [rbp-C8h]
  unsigned int puResult[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v276; // [rsp+60h] [rbp-A8h]
  StringPtr *v277; // [rsp+68h] [rbp-A0h]
  void *Buf1; // [rsp+70h] [rbp-98h]
  StringPtr *v279; // [rsp+78h] [rbp-90h]
  StringPtr v280; // [rsp+80h] [rbp-88h] BYREF
  void *pScope; // [rsp+90h] [rbp-78h]
  int *v282; // [rsp+98h] [rbp-70h]
  Reader::ParseElementNContext context; // [rsp+A0h] [rbp-68h] BYREF
  int pnContext[2]; // [rsp+F8h] [rbp-10h] BYREF
  StringPtr v285; // [rsp+108h] [rbp+0h] BYREF
  StringPtr pValue; // [rsp+118h] [rbp+10h] BYREF
  StringPtr v287; // [rsp+128h] [rbp+20h] BYREF
  StringPtr v288; // [rsp+138h] [rbp+30h] BYREF
  StringPtr *v289; // [rsp+148h] [rbp+40h]
  unsigned __int64 v290; // [rsp+150h] [rbp+48h]
  _OWORD v291[5]; // [rsp+158h] [rbp+50h] BYREF
  __int64 v292; // [rsp+1A8h] [rbp+A0h]
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
    v276 = pwh_low;
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
      v276 = v86 >> 1;
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
    v259 = *(_DWORD *)v146;
    if ( *(_DWORD *)v146 > 0xFFFFu )
    {
      *(_WORD *)v145 = (v259 >> 10) - 10304;
      if ( (unsigned int)((v145 + 2 - (char *)v8) >> 1) >= v11 )
        goto LABEL_206;
      *((_WORD *)v145 + 1) = v259 & 0x3FF | 0xDC00;
      v145 += 4;
      v146 += 4;
    }
    else
    {
      *(_WORD *)v145 = v259;
      v145 += 2;
      v146 += 4;
    }
  }
  LODWORD(context.prefix.pwh) = (v145 - (char *)v8) >> 1;
  v276 = (unsigned int)v148;
LABEL_19:
  nNsPrefix = this->_scanner._nNsPrefix;
  ++this->_nsSupport._nContext;
  v19 = this->_alloc._pBlock;
  *(_QWORD *)&context.prefix.n = v8;
  LODWORD(v277) = nNsPrefix;
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
          v260 = *((int *)k + 10);
          if ( (_DWORD)v260 == *((_DWORD *)v23 + 10)
            && !memcmp_0(*((const void **)k + 4), *((const void **)v23 + 4), 2 * v260) )
          {
            goto LABEL_390;
          }
        }
      }
      v23 += 120;
    }
    nNsPrefix = (int)v277;
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
    v267 = ULongLongToUInt(2 * cHashAttributes, puResult);
    if ( v267 < 0 )
    {
      MXRRaiseException(v267);
      __debugbreak();
    }
    v268 = puResult[0];
    if ( puResult[0] < v182 )
      v268 = v182;
    v269 = new_array<unsigned int>(v268);
    MemFree(this->_pHashAttributes);
    this->_pHashAttributes = v269;
    nNsPrefix = (int)v277;
    this->_cHashAttributes = v268;
  }
  memset_0(this->_pHashAttributes, 0, 4LL * v182);
  for ( m = 0; m < (unsigned int)lSize; this->_pHashAttributes[v290 / 4] = m )
  {
    v277 = (StringPtr *)&this->_attributes._pStack[120 * m];
    v289 = v277 + 3;
    v279 = v277 + 2;
    NamespaceSupport::ProcessAttribute(&this->_nsSupport, v277, v277 + 1, v277 + 2, v277 + 3);
    hash(v279->pwh, v277[2].n, this->_nHashSeed);
    v186 = hash(v289->pwh, v277[3].n, v185);
    v188 = (v187 ^ (unsigned __int64)v186) % v182;
    pHashAttributes = this->_pHashAttributes;
    v290 = 4 * v188;
    v190 = pHashAttributes[(unsigned int)v188];
    puResult[0] = v190;
    while ( v190 )
    {
      v261 = &this->_attributes._pStack[120 * (v190 - 1)];
      v282 = (int *)v261;
      if ( *((_DWORD *)v261 + 10) == v279->n )
      {
        v37 = memcmp_0(*((const void **)v261 + 4), v279->pwh, 2LL * *((int *)v261 + 10)) == 0;
        v261 = (char *)v282;
        if ( v37 && v282[14] == v289->n )
        {
          if ( !memcmp_0(*((const void **)v282 + 6), v289->pwh, 2LL * v282[14]) )
          {
LABEL_390:
            MXRRaiseException(-1072894404);
            __debugbreak();
          }
          v261 = (char *)v282;
        }
      }
      v190 = *((_DWORD *)v261 + 28);
    }
    ++m;
    LODWORD(v277[7].pwh) = puResult[0];
  }
LABEL_29:
  v27 = this->_nsAttributes._lSize;
  if ( (_DWORD)v27 )
  {
    if ( this->_fNamespacePrefixes )
    {
      v248 = this->_nsAttributes._pStack;
      for ( n = &v248[120 * v27]; v248 < n; *(_QWORD *)&v258->nHashNext = v257 )
      {
        v250 = *(StringPtr *)v248;
        v251 = (StringPtr)*((_OWORD *)v248 + 1);
        v252 = (StringPtr)*((_OWORD *)v248 + 2);
        v253 = (StringPtr)*((_OWORD *)v248 + 3);
        v254 = (StringPtr)*((_OWORD *)v248 + 4);
        v255 = (StringPtr)*((_OWORD *)v248 + 5);
        v256 = *((_OWORD *)v248 + 6);
        v257 = *((_QWORD *)v248 + 14);
        v258 = _stack<Attribute>::push(&this->_attributes);
        v248 += 120;
        v258->qname = v250;
        v258->prefix = v251;
        v258->uri = v252;
        v258->lname = v253;
        v258->type = v254;
        v258->value = v255;
        *(_OWORD *)&v258->nToken = v256;
      }
    }
  }
LABEL_30:
  v28 = this->_nsSupport._maps._lSize;
  v29 = 0;
  v30 = this->_nsSupport._maps._pStack;
  nContext = this->_nsSupport._nContext;
  LODWORD(v279) = 0;
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
      LODWORD(v279) = v29;
    }
  }
  pnContext[0] = v29;
  while ( v29 )
  {
    v231 = v29 - 1;
    p = this->_pContentHandler._p;
    v233 = this->_nsSupport._maps._lSize - v231;
    LODWORD(v279) = v231;
    pnContext[0] = v231;
    v234 = &this->_nsSupport._maps._pStack[48 * v233];
    v235 = *((_DWORD *)v234 - 6);
    v236 = (const wchar_t *)*((_QWORD *)v234 - 4);
    HIDWORD(context.lname.pwh) = *((_DWORD *)v234 - 5);
    v42 = p->startPrefixMapping(p, *((const wchar_t **)v234 - 6), *((_DWORD *)v234 - 10), v236, v235);
    v43 = v42;
    if ( v42 < 0 )
      goto LABEL_342;
    v29 = (int)v279;
  }
  v33 = (char *)Buf1;
  if ( nNsPrefix )
  {
    v34 = nNsPrefix;
    Buf1 = (char *)Buf1 + 2 * nNsPrefix + 2;
    *(_QWORD *)&context.lname.n = &v33[2 * nNsPrefix + 2];
    LODWORD(v277) = v276 - nNsPrefix - 1;
    LODWORD(context.pScope) = (_DWORD)v277;
  }
  else
  {
    v34 = 0;
    LODWORD(v277) = v276;
    context.pScope = (void *)__PAIR64__(HIDWORD(context.prefix.pwh), v276);
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
      nHashSeed = this->_nsSupport._nHashSeed;
      v244 = (unsigned __int16 *)v33;
      v245 = (unsigned __int16 *)&v33[2 * nNsPrefix];
      if ( v33 < (char *)v245 )
      {
        do
        {
          v246 = *v244++;
          nHashSeed = v246 ^ (33 * nHashSeed);
        }
        while ( v244 < v245 );
      }
      for ( ii = this->_nsSupport._pHashTable[nHashSeed % this->_nsSupport._nHashSize] - 1;
            ii >= 0;
            ii = *((_DWORD *)jj + 9) )
      {
        jj = &this->_nsSupport._maps._pStack[48 * ii];
        if ( nHashSeed == *((_DWORD *)jj + 10)
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
  v41 = (int)v277;
  HIDWORD(context.lname.pwh) = *(&pLastNsUri->n + 1);
  *(_QWORD *)&context.uri.n = pwh;
  v282 = (int *)pwh;
  v274 = &this->IMXRAttributes;
  LODWORD(context.lname.pwh) = v38;
  puResult[0] = v38;
  if ( v37 )
  {
    v42 = v40->startElement(v40, pwh, v38, (const wchar_t *)Buf1, (int)v277, (const wchar_t *)v33, v276, v274);
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
      v45 = (int)v279;
      goto $Continue;
    }
LABEL_342:
    Reader::OnCallbackFailure(v42);
    goto $CleanUp_2;
  }
  v113 = (const wchar_t *)Buf1;
  v43 = this->_pfnStartEmptyElement(v40, pwh, v38, (const wchar_t *)Buf1, (int)v277, (const wchar_t *)v33, v276, v274);
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
  v42 = this->_pfnEndEmptyElement(this->_pContentHandler._p, pwh, v38, v113, v41, (const wchar_t *)v33, v276);
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
    v33 = (char *)v101;
    *(_QWORD *)pnContext = *(_QWORD *)&v99[v100 - 8];
    v45 = _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)pnContext);
    LODWORD(v277) = _mm_cvtsi128_si32(_mm_loadl_epi64((const __m128i *)&v99[v100 - 32]));
    puResult[0] = _mm_cvtsi128_si32(_mm_loadl_epi64((const __m128i *)&v99[v100 - 48]));
    LODWORD(v276) = _mm_cvtsi128_si32(_mm_loadl_epi64((const __m128i *)&v99[v100 - 80]));
    *(_OWORD *)&context.qname.n = v101;
    *(_OWORD *)&context.uri.n = v102;
    *(_OWORD *)&context.lname.n = v103;
    *(_OWORD *)&context.pAttributesScope = v104;
    pScope = (void *)v104;
    Buf1 = (void *)v103;
    v282 = (int *)v102;
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
        memset_0(v291, 0, 0x58u);
        *(_OWORD *)&context.qname.n = v291[0];
        *(_OWORD *)&context.prefix.n = v291[1];
        *(_OWORD *)&context.uri.n = v291[2];
        *(_OWORD *)&context.lname.n = v291[3];
        *(_OWORD *)&context.pAttributesScope = v291[4];
        *(_QWORD *)pnContext = v292;
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
          v285.pwh = 0;
          v285.n = 0;
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
          v285.pwh = v137;
          v285.n = v140;
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
                Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v139, &v285);
                goto LABEL_193;
              case Ucs4B:
                Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v139, &v285);
                goto LABEL_193;
              case CodePage:
                Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v139, &v285);
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
            Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v139, &v285);
LABEL_193:
            LODWORD(v142) = v285.n;
          }
LABEL_194:
          v42 = this->_pfnWhitespace(this->_pContentHandler._p, v285.pwh, v142);
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
          v280.pwh = 0;
          v280.n = 0;
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
          v280.pwh = v202;
          v280.n = v204;
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
              Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v203, &v280);
              v202 = v280.pwh;
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
                v280.n = (unsigned int)v224 >> 1;
                memcpy_0(v202, v225, v224);
                goto LABEL_296;
              case Ucs2B:
                v240 = (unsigned __int16 *)v203->_pbSeg;
                v241 = (unsigned __int64)&v203->_pbCurr[-2 * v203->_lDelta];
                v242 = v202;
                break;
              case Ucs4:
                Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v203, &v280);
                v202 = v280.pwh;
                goto LABEL_296;
              case Ucs4B:
                Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v203, &v280);
                v202 = v280.pwh;
                goto LABEL_296;
              case CodePage:
                Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v203, &v280);
                v202 = v280.pwh;
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
          v280.n = v209;
LABEL_296:
          if ( v280.n >= 1 && *v202 == 120 )
          {
            v210 = HexCharEntity2Utf16(v202 + 1, v280.n - 1, v202, &v280.n);
            if ( v210 < 0 )
            {
LABEL_438:
              MXRRaiseException(v210);
              __debugbreak();
            }
          }
          else
          {
            v210 = CharEntity2Utf16(v202, v280.n, v202, &v280.n);
            if ( v210 < 0 )
              goto LABEL_438;
          }
          v211 = this->_pContentHandler._p->characters(this->_pContentHandler._p, v280.pwh, v280.n);
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
          v33 = *(char **)&context.qname.n;
          pScope = context.pAttributesScope;
          LODWORD(v277) = context.pScope;
          Buf1 = *(void **)&context.lname.n;
          puResult[0] = (unsigned int)context.lname.pwh;
          v282 = *(int **)&context.uri.n;
          v276 = LODWORD(context.prefix.pwh);
          continue;
        case 13:
          v149 = this->_pLexicalHandler._p;
          v288.pwh = 0;
          v288.n = 0;
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
            goto LABEL_371;
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
          v270 = this->_scanner._nToken;
          if ( v270 == 7 )
          {
            v262 = this->_scanner._pCharacterSource;
            v263 = v262->_sourceType;
            if ( v263 )
            {
              if ( v263 == Utf16 )
              {
LABEL_407:
                v264 = LODWORD(v262->_pbCurr) - 2 * v262->_lDelta - LODWORD(v262->_pbSeg);
              }
              else
              {
                switch ( v263 )
                {
                  case Utf16B:
                  case Ucs2:
                  case Ucs2B:
                  case CodePage:
                    goto LABEL_407;
                  case Ucs4:
                  case Ucs4B:
                    v264 = LODWORD(v262->_pbCurr) - 4 * v262->_lDelta - LODWORD(v262->_pbSeg);
                    break;
                  default:
                    goto LABEL_411;
                }
              }
            }
            else
            {
LABEL_411:
              v264 = 2 * (LODWORD(v262->_pbCurr) - v262->_lDelta - LODWORD(v262->_pbSeg));
            }
            v265 = (wchar_t *)BlockAlloc::AllocData(&this->_alloc, v264);
            v288.n = v264 >> 1;
            v288.pwh = v265;
            Scanner::GetSegmentValue(&this->_scanner, &v288);
            v266 = this->_pContentHandler._p->characters(this->_pContentHandler._p, v288.pwh, v288.n);
LABEL_409:
            v151 = v266;
            if ( v266 < 0 )
              goto LABEL_210;
            continue;
          }
          break;
        }
        if ( v270 == 9 )
        {
          v271 = (wchar_t *)BlockAlloc::AllocData(&this->_alloc, 2u);
          v288.n = 1;
          *v271 = 10;
          v266 = this->_pContentHandler._p->characters(this->_pContentHandler._p, v271, 1);
          goto LABEL_409;
        }
      }
      while ( v270 != 14 );
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
    v287.pwh = 0;
    v287.n = 0;
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
    v287.pwh = v52;
    v287.n = v54;
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
          Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v53, &v287);
          LODWORD(v56) = v287.n;
          goto LABEL_69;
        case CodePage:
          Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v53, &v287);
          LODWORD(v56) = v287.n;
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
      Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v53, &v287);
      LODWORD(v56) = v287.n;
    }
LABEL_69:
    v61 = v276;
    if ( (_DWORD)v56 != (_DWORD)v276 || memcmp_0(v287.pwh, v33, 2LL * (int)v56) )
    {
      MXRRaiseException(-1072894405);
      __debugbreak();
    }
    if ( v45 )
    {
LABEL_371:
      MXRRaiseException(-1072894394);
      __debugbreak();
    }
    v43 = this->_pContentHandler._p->endElement(
            this->_pContentHandler._p,
            (const wchar_t *)v282,
            puResult[0],
            (const wchar_t *)Buf1,
            (int)v277,
            (const wchar_t *)v33,
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
0x180014550  mov     rax, rsp
0x180014553  push    rbp
0x180014554  push    rbx
0x180014555  push    rsi
0x180014556  push    rdi
0x180014557  push    r12
0x180014559  push    r13
0x18001455b  push    r14
0x18001455d  push    r15
0x18001455f  lea     rbp, [rax-288h]
0x180014566  sub     rsp, 348h
0x18001456d  movaps  xmmword ptr [rax-58h], xmm6
0x180014571  movaps  xmmword ptr [rax-68h], xmm7
0x180014575  movaps  xmmword ptr [rax-78h], xmm8
0x18001457a  movaps  xmmword ptr [rax-88h], xmm9
0x180014582  movaps  xmmword ptr [rax-98h], xmm10
0x18001458a  movaps  xmmword ptr [rax-0A8h], xmm11
0x180014592  movaps  xmmword ptr [rax-0B8h], xmm12
0x18001459a  movaps  xmmword ptr [rax-0C8h], xmm13
0x1800145a2  mov     rax, cs:__security_cookie
0x1800145a9  xor     rax, rsp
0x1800145ac  mov     [rbp+280h+var_D0], rax
0x1800145b3  xor     r12d, r12d
0x1800145b6  mov     rbx, this
0x1800145b9  mov     qword ptr [rbp+280h+context.qname.n], r12
0x1800145bd  mov     dword ptr [rbp+280h+context.prefix.pwh], r12d
0x1800145c1  mov     qword ptr [rbp+280h+context.prefix.n], r12
0x1800145c5  mov     dword ptr [rbp+280h+context.uri.pwh], r12d
0x1800145c9  mov     qword ptr [rbp+280h+context.uri.n], r12
0x1800145cd  mov     dword ptr [rbp+280h+context.lname.pwh], r12d
0x1800145d1  mov     qword ptr [rbp+280h+context.lname.n], r12
0x1800145d5  mov     dword ptr [rbp+280h+context.pScope], r12d
0x1800145d9  mov     r13d, 0DC00h
0x1800145df  lea     r8, __ImageBase
0x1800145e6  mov     r11d, 3FFh
0x1800145ec  mov     r9d, 0FFFFFFFFh
0x1800145f2  nop     dword ptr [rax+00h]
0x1800145f6  nop     word ptr [rax+rax+00000000h]
0x180014600  inc     dword ptr [rbx+900h]
0x180014606  mov     eax, [rbx+8F8h]
0x18001460c  test    eax, eax
0x18001460e  jz      short loc_18001461C
0x180014610  cmp     [rbx+900h], eax
0x180014616  ja      loc_180015739
0x18001461c  mov     rsi, [rbx+98h]
0x180014623  mov     rdx, [rbx+30h]
0x180014627  mov     r15, [rsi+10h]
0x18001462b  mov     eax, [rdx+58h]
0x18001462e  mov     [rbp+280h+pScope], r15
0x180014632  mov     [rbp+280h+context.pAttributesScope], r15
0x180014636  test    eax, eax
0x180014638  jnz     short loc_1800146A1
0x18001463a  mov     edi, [rdx+20h]; jumptable 00000001800164C0 default case
0x18001463d  sub     edi, [rdx+38h]
0x180014640  sub     edi, [rdx+28h]
0x180014643  add     edi, edi
0x180014645  mov     eax, [rsi+18h]
0x180014648  mov     r14, r15
0x18001464b  sub     eax, r15d
0x18001464e  mov     [rsp+380h+Buf1], r15
0x180014653  cmp     eax, edi
0x180014655  jb      loc_1800149C0
0x18001465b  mov     eax, edi
0x18001465d  add     [rsi+10h], rax
0x180014661  mov     r9, [rbx+30h]
0x180014665  shr     edi, 1
0x180014667  mov     qword ptr [rbp+280h+context.qname.n], r14
0x18001466b  mov     dword ptr [rbp+280h+context.prefix.pwh], edi
0x18001466e  mov     eax, [r9+58h]
0x180014672  cmp     eax, 2
0x180014675  jz      short loc_1800146B9
0x180014677  test    eax, eax
0x180014679  jnz     loc_180014D14
0x18001467f  lea     rdx, [rbp+280h+context.qname.n]; jumptable 0000000180014D2C default case, case 2
0x180014683  mov     this, r9; this
0x180014686  call    ?GetSegmentValue@Utf8CharacterSource@@QEAAXPEAUStringPtr@@@Z; Utf8CharacterSource::GetSegmentValue(StringPtr *)
0x18001468b  mov     rsi, [rbp+280h+context.pAttributesScope]
0x18001468f  mov     r14, qword ptr [rbp+280h+context.qname.n]
0x180014693  mov     [rbp+280h+pScope], rsi
0x180014697  mov     esi, dword ptr [rbp+280h+context.prefix.pwh]
0x18001469a  mov     [rsp+380h+Buf1], r14
0x18001469f  jmp     short loc_180014705
0x1800146a1  cmp     eax, 1
0x1800146a4  jnz     loc_1800164A7
0x1800146aa  mov     eax, [rdx+38h]; jumptable 00000001800164C0 cases 2-4,7
0x1800146ad  mov     edi, [rdx+20h]
0x1800146b0  add     eax, eax
0x1800146b2  sub     edi, eax
0x1800146b4  sub     edi, [rdx+28h]
0x1800146b7  jmp     short loc_180014645
0x1800146b9  movsxd  rax, dword ptr [r9+38h]
0x1800146bd  mov     r8, r14
0x1800146c0  mov     r10, [r9+20h]
0x1800146c4  add     rax, rax
0x1800146c7  mov     rdx, [r9+28h]
0x1800146cb  sub     r10, rax
0x1800146ce  mov     rax, r8
0x1800146d1  sub     rax, r14
0x1800146d4  sar     rax, 1
0x1800146d7  cmp     rdx, r10
0x1800146da  jnb     short loc_180014700
0x1800146dc  cmp     eax, edi
0x1800146de  jnb     loc_180015494
0x1800146e4  movzx   eax, byte ptr [rdx]
0x1800146e7  movzx   ecx, byte ptr [rdx+1]
0x1800146eb  shl     ax, 8
0x1800146ef  or      cx, ax
0x1800146f2  mov     [r8], cx
0x1800146f6  add     r8, 2
0x1800146fa  add     rdx, 2
0x1800146fe  jmp     short loc_1800146CE
0x180014700  mov     esi, eax
0x180014702  mov     dword ptr [rbp+280h+context.prefix.pwh], eax
0x180014705  mov     [rsp+380h+var_328], rsi
0x18001470a  mov     edi, [rbx+7Ch]
0x18001470d  lea     r13, [rbx+128h]
0x180014714  inc     dword ptr [r13+0]
0x180014718  mov     this, rbx; this
0x18001471b  mov     rax, [rbx+98h]
0x180014722  mov     qword ptr [rbp+280h+context.prefix.n], r14
0x180014726  mov     dword ptr [rsp+380h+var_320], edi
0x18001472a  mov     dword ptr [rbp+280h+context.uri.pwh], edi
0x18001472d  mov     r12, [rax+10h]
0x180014731  mov     qword ptr [rbp+280h+context.nContext], r12
0x180014735  call    ?ParseAttributesN@Reader@@AEAAXXZ; Reader::ParseAttributesN(void)
0x18001473a  movsxd  r14, dword ptr [rbx+0C0h]
0x180014741  test    r14d, r14d
0x180014744  jnz     loc_1800157F2
0x18001474a  cmp     [rbx+0D8h], r14d
0x180014751  jz      short loc_1800147AC
0x180014753  mov     r15, [rbx+0B8h]
0x18001475a  imul    rsi, r14, 78h ; 'x'
0x18001475e  mov     rdi, r15
0x180014761  add     rsi, r15
0x180014764  cmp     rdi, rsi
0x180014767  jnb     short loc_180014799
0x180014769  movsxd  rdx, dword ptr [rdi+18h]
0x18001476d  test    edx, edx
0x18001476f  jnz     loc_180015744
0x180014775  movups  xmm0, xmmword ptr [rdi]
0x180014778  movups  xmmword ptr [rdi+30h], xmm0
0x18001477c  movups  xmm1, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::empty ...
0x180014783  movups  xmmword ptr [rdi+20h], xmm1
0x180014787  mov     r14, r15
0x18001478a  cmp     r14, rdi
0x18001478d  jb      loc_180014BFB
0x180014793  add     rdi, 78h ; 'x'
0x180014797  jmp     short loc_180014764
0x180014799  mov     edi, dword ptr [rsp+380h+var_320]
0x18001479d  movsxd  rax, dword ptr [rbx+0D8h]
0x1800147a4  test    eax, eax
0x1800147a6  jnz     loc_1800161AA
0x1800147ac  movsxd  rdx, dword ptr [rbx+138h]
0x1800147b3  xor     r10d, r10d
0x1800147b6  mov     r9, [rbx+130h]
0x1800147bd  mov     r8d, [rbx+128h]
0x1800147c4  mov     dword ptr [rsp+380h+var_310], r10d
0x1800147c9  lea     this, [rdx+rdx*2]
0x1800147cd  add     this, this
0x1800147d0  cmp     [r9+this*8-10h], r8d
0x1800147d5  jnz     short loc_1800147F7
0x1800147d7  sub     edx, 1
0x1800147da  js      short loc_1800147F7
0x1800147dc  lea     this, [rdx+rdx*2]
0x1800147e0  add     this, this
0x1800147e3  cmp     [r9+this*8+20h], r8d
0x1800147e8  jnz     short loc_1800147F2
0x1800147ea  inc     r10d
0x1800147ed  sub     edx, 1
0x1800147f0  jns     short loc_1800147DC
0x1800147f2  mov     dword ptr [rsp+380h+var_310], r10d
0x1800147f7  mov     [rbp+280h+pnContext], r10d
0x1800147fb  test    r10d, r10d
0x1800147fe  jnz     loc_180015EE0
0x180014804  mov     r13, [rsp+380h+Buf1]
0x180014809  test    edi, edi
0x18001480b  jnz     loc_1800160A3
0x180014811  mov     ecx, dword ptr [rsp+380h+var_328]
0x180014815  xor     r8d, r8d
0x180014818  mov     eax, dword ptr [rbp+280h+context.prefix.pwh+4]
0x18001481b  mov     dword ptr [rsp+380h+var_320], ecx
0x18001481f  mov     dword ptr [rbp+280h+context.pScope], ecx
0x180014822  mov     dword ptr [rbp+280h+context.pScope+4], eax
0x180014825  mov     [rsp+380h+Buf1], r13
0x18001482a  mov     qword ptr [rbp+280h+context.lname.n], r13
0x18001482e  mov     rdx, [rbx+158h]
0x180014835  test    rdx, rdx
0x180014838  jz      loc_180015C75
0x18001483e  cmp     edi, [rdx+8]
0x180014841  jnz     loc_180015C75
0x180014847  mov     rdx, [rdx]; Buf2
0x18001484a  add     r8, r8; Size
0x18001484d  mov     this, r13; Buf1
0x180014850  call    memcmp_0
0x180014855  test    eax, eax
0x180014857  jnz     loc_180015C75
0x18001485d  mov     rax, [rbx+160h]
0x180014864  cmp     dword ptr [rbx+38h], 5
0x180014868  lea     rdx, [rbx+8]
0x18001486c  mov     r14d, [rax+8]
0x180014870  mov     r8d, r14d
0x180014873  mov     rdi, [rax]
0x180014876  mov     eax, [rax+0Ch]
0x180014879  mov     this, [rbx+910h]
0x180014880  mov     r15d, dword ptr [rsp+380h+var_320]
0x180014885  mov     dword ptr [rbp+280h+context.lname.pwh+4], eax
0x180014888  mov     qword ptr [rbp+280h+context.uri.n], rdi
0x18001488c  mov     [rbp+280h+var_2F0], rdi
0x180014890  mov     [rsp+380h+var_348], rdx
0x180014895  mov     dword ptr [rbp+280h+context.lname.pwh], r14d
0x180014899  mov     [rsp+380h+puResult], r14d
0x18001489e  jnz     loc_18001509E
0x1800148a4  mov     rax, [this]
0x1800148a7  mov     rdx, [rsp+380h+var_328]
0x1800148ac  mov     r9, [rsp+380h+Buf1]
0x1800148b1  mov     dword ptr [rsp+380h+var_350], edx
0x1800148b5  mov     rdx, rdi
0x1800148b8  mov     rax, [rax+40h]
0x1800148bc  mov     qword ptr [rsp+380h+var_358], r13
0x1800148c1  mov     dword ptr [rsp+380h+pLName], r15d
0x1800148c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148cb  mov     esi, eax
0x1800148cd  test    eax, eax
0x1800148cf  js      loc_180015FCE
0x1800148d5  mov     rax, [rbx+98h]
0x1800148dc  cmp     rax, r12
0x1800148df  jnb     loc_1800152AC
0x1800148e5  cmp     r12, [rax+10h]
0x1800148e9  ja      loc_1800152AC
0x1800148ef  mov     [rax+10h], r12
0x1800148f3  mov     r12d, dword ptr [rsp+380h+var_310]
0x1800148f8  mov     edx, [rbx+58h]; jumptable 0000000180014D99 default case, cases 12,14,16,18-58
0x1800148fb  lea     this, [rbx+18h]; this
0x1800148ff  call    ?DoScan@Scanner@@AEAAXW4ScanOp@1@@Z; Scanner::DoScan(Scanner::ScanOp)
0x180014904  mov     eax, [rbx+38h]
0x180014907  cmp     eax, 4
0x18001490a  jz      short loc_18001492F
0x18001490c  cmp     eax, 3
0x18001490f  jnz     loc_180014D70
0x180014915  cmp     dword ptr [rbx+900h], 3E8h
0x18001491f  jnb     loc_180014C28
0x180014925  mov     this, rbx; this
0x180014928  call    ?ParseElementN@Reader@@AEAAXXZ; Reader::ParseElementN(void)
0x18001492d  jmp     short $Continue; jumptable 0000000180014D99 default case, cases 12,14,16,18-58
0x18001492f  mov     rdx, [rbx+30h]
0x180014933  xor     r14d, r14d
0x180014936  mov     [rbp+280h+var_260.pwh], r14
0x18001493a  mov     [rbp+280h+var_260.n], r14d
0x18001493e  mov     eax, [rdx+58h]
0x180014941  test    eax, eax
0x180014943  jnz     short loc_1800149A1
0x180014945  mov     edi, [rdx+20h]; jumptable 00000001800167A6 default case
0x180014948  sub     edi, [rdx+38h]
0x18001494b  sub     edi, [rdx+28h]
0x18001494e  add     edi, edi
0x180014950  mov     rsi, [rbx+98h]
0x180014957  mov     r9, [rsi+10h]
0x18001495b  mov     eax, [rsi+18h]
0x18001495e  sub     eax, r9d
0x180014961  cmp     eax, edi
0x180014963  jb      loc_180014B91
0x180014969  mov     eax, edi
0x18001496b  add     [rsi+10h], rax
0x18001496f  mov     r10, [rbx+30h]
0x180014973  shr     edi, 1
0x180014975  mov     [rbp+280h+var_260.pwh], r9
0x180014979  mov     [rbp+280h+var_260.n], edi
0x18001497c  mov     eax, [r10+58h]
0x180014980  cmp     eax, 2
0x180014983  jz      short loc_1800149E3
0x180014985  test    eax, eax
0x180014987  jnz     loc_180014E78
0x18001498d  lea     rdx, [rbp+280h+var_260]; jumptable 0000000180014E96 default case, case 2
0x180014991  mov     this, r10; this
0x180014994  call    ?GetSegmentValue@Utf8CharacterSource@@QEAAXPEAUStringPtr@@@Z; Utf8CharacterSource::GetSegmentValue(StringPtr *)
0x180014999  mov     esi, [rbp+280h+var_260.n]
0x18001499c  jmp     loc_180014A2C
0x1800149a1  cmp     eax, 1
0x1800149a4  jnz     loc_180016786
0x1800149aa  mov     eax, [rdx+38h]; jumptable 00000001800167A6 cases 2-4,7
0x1800149ad  mov     edi, [rdx+20h]
0x1800149b0  add     eax, eax
0x1800149b2  sub     edi, eax
0x1800149b4  sub     edi, [rdx+28h]
0x1800149b7  jmp     short loc_180014950
0x1800149c0  mov     rax, [rsi+8]
0x1800149c4  test    rax, rax
0x1800149c7  jnz     loc_180014E48
0x1800149cd  lea     eax, [rdi+20h]
0x1800149d0  cmp     eax, edi
0x1800149d2  jnb     loc_180014F8C
0x1800149d8  mov     ecx, 80070216h; hr
0x1800149dd  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1800149e2  int     3; Trap to Debugger
0x1800149e3  movsxd  rax, dword ptr [r10+38h]
0x1800149e7  mov     r8, r9
0x1800149ea  mov     r11, [r10+20h]
0x1800149ee  add     rax, rax
0x1800149f1  mov     rdx, [r10+28h]
0x1800149f5  sub     r11, rax
  ... truncated ...
```
