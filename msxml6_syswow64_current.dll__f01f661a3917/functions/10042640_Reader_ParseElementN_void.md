# Reader::ParseElementN(void)

- ea: `0x10042640`
- end: `0x10044318`
- name: `?ParseElementN@Reader@@AAEXXZ`
- size: `7384`
- prototype: `void __thiscall(Reader *this)`
- caller_count: `2`
- callee_count: `33`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1003c4e2`
- `0x10042640`

## callees

- `0x1003c2f2`
- `0x1003c330`
- `0x1003c60a`
- `0x1003c872`
- `0x1003d8f0`
- `0x1003e2d1`
- `0x1003ecd7`
- `0x10040dee`
- `0x10040e10`
- `0x1004118e`
- `0x10041340`
- `0x10041610`
- `0x10042640`
- `0x10044320`
- `0x1004d6c0`
- `0x1004d88d`
- `0x1004dee0`
- `0x100556dd`
- `0x1005902f`
- `0x10059742`
- `0x1005cd9c`
- `0x1005dcbe`
- `0x1005dce2`
- `0x10067a9f`
- `0x10067bc0`
- `0x1006b510`
- `0x1006c354`
- `0x10070469`
- `0x1010f5de`
- `0x1016ae1a`
- `0x1016aeb1`
- `0x101711a8`
- `0x101711b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1004340d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1004340d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x10043435`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x10043435`

## string_xrefs

- `0x10043415`: `SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\n`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __usercall Reader::ParseElementN(Reader *this@<ecx>, int a2@<ebp>, int a3@<edi>, HRESULT lSize@<esi>)
{
  Reader *endPrefixMapping; // edi
  unsigned int ulMaxElementDepth; // ecx
  unsigned int v6; // eax
  BlockAlloc *pBlock; // ecx
  CharacterSource *pCharacterSource; // edx
  SourceType sourceType; // eax
  unsigned int v10; // esi
  BlockAlloc::Header *v11; // eax
  BlockAlloc::Header *v12; // eax
  CharacterSource *v13; // edx
  unsigned int v14; // esi
  SourceType v15; // eax
  unsigned __int8 *v16; // ecx
  NamespaceSupport *v17; // edx
  NamespaceSupport *v18; // eax
  unsigned int v19; // eax
  size_t v20; // eax
  wchar_t *nNsPrefix; // eax
  BlockAlloc::Header *v22; // eax
  int v23; // eax
  NamespaceSupport *v24; // esi
  NamespaceSupport *v25; // eax
  int lCapacity; // ecx
  unsigned int nContext; // eax
  char *v28; // ecx
  wchar_t *v29; // eax
  int v30; // ecx
  BlockAlloc *j; // ecx
  size_t cHashAttributes; // ecx
  unsigned int k; // edx
  int v34; // ecx
  int v35; // eax
  char *v36; // edx
  int v37; // esi
  NamespaceSupport *v38; // ecx
  NamespaceSupport *v39; // ecx
  int v40; // eax
  StringPtr *v41; // edx
  wchar_t *v42; // edx
  unsigned int v43; // esi
  bool v44; // cf
  unsigned __int8 v45; // al
  unsigned __int8 v46; // al
  unsigned __int8 nContext_high; // al
  int v48; // eax
  int v49; // eax
  char *v50; // edx
  StringPtr *m; // eax
  unsigned __int8 *pbCurr; // ecx
  int v53; // eax
  unsigned __int8 *pbSeg; // edx
  size_t v55; // ecx
  StringPtr *v56; // eax
  BlockAlloc::Header *v57; // ecx
  unsigned int v58; // eax
  unsigned int nHashSize; // edx
  StringPtr *v60; // eax
  bool v61; // cf
  unsigned __int8 v62; // al
  unsigned __int8 v63; // al
  unsigned __int8 pPrev_high; // al
  int v65; // eax
  size_t v66; // eax
  unsigned __int8 *v67; // ecx
  NamespaceSupport *v68; // eax
  size_t v69; // eax
  StringPtr *v70; // eax
  wchar_t *v71; // ecx
  int v72; // eax
  BlockAlloc::Header *v73; // eax
  unsigned int v74; // ecx
  int nToken; // eax
  CharacterSource *v76; // ecx
  SourceType v77; // eax
  unsigned int v78; // esi
  BlockAlloc *v79; // ecx
  wchar_t *v80; // edx
  BlockAlloc::Header *v81; // eax
  CharacterSource *v82; // ecx
  unsigned int v83; // esi
  SourceType v84; // eax
  int v85; // ecx
  wchar_t *v86; // eax
  wchar_t *v87; // ecx
  unsigned int v88; // eax
  unsigned int v89; // eax
  wchar_t *v90; // edx
  unsigned int v91; // esi
  NamespaceSupport *v92; // eax
  unsigned int v93; // esi
  bool v94; // cf
  unsigned __int8 v95; // cl
  unsigned __int8 v96; // cl
  unsigned __int8 v97; // cl
  int v98; // eax
  BlockAlloc::Header *v99; // edx
  CharacterSource *v100; // ecx
  SourceType v101; // eax
  unsigned int v102; // esi
  unsigned int v103; // eax
  CharacterSource *v104; // ecx
  wchar_t *v105; // edx
  unsigned int v106; // esi
  SourceType v107; // eax
  unsigned __int16 *v108; // edx
  wchar_t *v109; // ecx
  wchar_t *v110; // eax
  unsigned int v111; // eax
  unsigned int v112; // eax
  size_t v113; // ecx
  int v114; // ecx
  __int128 v115; // xmm0
  int v116; // eax
  NamespaceSupport *v117; // ecx
  int v118; // eax
  __int128 v119; // xmm0
  int v120; // ecx
  wchar_t *v121; // eax
  wchar_t *v122; // ecx
  unsigned int v123; // eax
  HRESULT (__stdcall *endElement)(ISAXContentHandler *, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int); // ecx
  int v125; // eax
  char *v126; // edx
  int v127; // esi
  unsigned int v128; // ecx
  int v129; // eax
  unsigned int v130; // eax
  BlockAlloc::Header *v131; // ecx
  int v132; // eax
  __int128 v133; // xmm0
  NamespaceSupport *v134; // ecx
  __int128 v135; // xmm0
  HRESULT (__stdcall *characters)(ISAXContentHandler *, const wchar_t *, int); // ecx
  BlockAlloc::Header *v137; // eax
  BlockAlloc *v138; // ecx
  size_t v139; // ecx
  BlockAlloc::Header *pNext; // eax
  int v141; // ecx
  wchar_t *v142; // eax
  wchar_t *v143; // ecx
  unsigned int v144; // eax
  NamespaceSupport *v145; // ecx
  IMXRContentHandler *p; // edx
  int v147; // eax
  int v148; // ecx
  DWORD CurrentThreadId; // eax
  BlockAlloc::Header *v150; // ecx
  _WORD *v151; // edx
  int v152; // edi
  int v153; // eax
  Reader *v154; // edi
  void (__thiscall ***v155)(unsigned int, int); // eax
  _DWORD *v156; // eax
  CharacterSource *v157; // ecx
  SourceType v158; // eax
  unsigned int v159; // esi
  BlockAlloc::Header *v160; // ecx
  wchar_t *v161; // edx
  CharacterSource *v162; // ecx
  unsigned int v163; // esi
  SourceType v164; // eax
  int v165; // ecx
  wchar_t *v166; // eax
  wchar_t *v167; // ecx
  unsigned int v168; // eax
  unsigned int v169; // eax
  NamespaceSupport *v170; // eax
  StringPtr *pLastPrefix; // ecx
  int v172; // ecx
  int v173; // edx
  size_t v174; // ecx
  int v175; // eax
  StringPtr *i; // eax
  StringPtr *v177; // ecx
  int v178; // ecx
  NamespaceSupport *v179; // edi
  NamespaceSupport *v180; // eax
  StringPtr *v181; // ecx
  int v182; // eax
  int jj; // edi
  bool v184; // zf
  size_t v185; // ecx
  int v186; // ecx
  int v187; // ecx
  wchar_t *v188; // eax
  wchar_t *v189; // ecx
  unsigned int v190; // eax
  int v191; // edx
  StringPtr *pLastNsUri; // eax
  wchar_t *pwh; // ecx
  int *n; // eax
  NamespaceSupport *v195; // eax
  int v196; // edx
  int v197; // eax
  int v198; // eax
  int v199; // edx
  int ii; // edx
  StringPtr *v201; // ecx
  char *v202; // edx
  _stack<Attribute> *p_attributes; // eax
  unsigned int v204; // edi
  int v205; // esi
  Attribute *v206; // eax
  wchar_t *v207; // eax
  int *v208; // eax
  int v209; // esi
  char *v210; // eax
  int v211; // eax
  HRESULT v212; // eax
  int v213; // edi
  XSyntaxNode **v214; // esi
  Reader *v215; // eax
  StringPtr *v216; // esi
  const wchar_t *v217; // eax
  unsigned int nHashSeed; // edi
  unsigned int v219; // esi
  unsigned int v220; // eax
  int v221; // edx
  unsigned int *pHashAttributes; // eax
  IMXRContentHandler *v223; // [esp-C4h] [ebp-24Ch]
  IMXRContentHandler *v224; // [esp-B0h] [ebp-238h]
  int v225; // [esp-A4h] [ebp-22Ch]
  HRESULT v226; // [esp-A0h] [ebp-228h]
  __int128 v227; // [esp-64h] [ebp-1ECh]
  __int128 v228; // [esp-54h] [ebp-1DCh]
  __int128 v229; // [esp-44h] [ebp-1CCh]
  __int128 v230; // [esp-34h] [ebp-1BCh]
  int v231; // [esp-24h] [ebp-1ACh]
  const wchar_t *v232; // [esp-20h] [ebp-1A8h]
  size_t v233; // [esp-1Ch] [ebp-1A4h] BYREF
  wchar_t *v234; // [esp-18h] [ebp-1A0h]
  wchar_t *v235; // [esp-14h] [ebp-19Ch]
  NamespaceSupport *v236; // [esp-10h] [ebp-198h]
  StringPtr v237; // [esp-Ch] [ebp-194h] BYREF
  StringPtr v238; // [esp-4h] [ebp-18Ch] BYREF
  StringPtr v239; // [esp+4h] [ebp-184h] BYREF
  _BYTE v240[44]; // [esp+Ch] [ebp-17Ch] OVERLAPPED BYREF
  NamespaceSupport *pStack; // [esp+44h] [ebp-144h]
  Reader *v242; // [esp+48h] [ebp-140h]
  unsigned int v243; // [esp+4Ch] [ebp-13Ch]
  NamespaceSupport *p_nsSupport; // [esp+54h] [ebp-134h]
  StringPtr *v245; // [esp+5Ch] [ebp-12Ch]
  size_t v246; // [esp+60h] [ebp-128h]
  NamespaceSupport *pFirst; // [esp+64h] [ebp-124h]
  unsigned int pCurr; // [esp+68h] [ebp-120h]
  unsigned int p_pBlock; // [esp+6Ch] [ebp-11Ch]
  wchar_t *v250; // [esp+70h] [ebp-118h]
  wchar_t v251[132]; // [esp+74h] [ebp-114h] BYREF
  int v252; // [esp+17Ch] [ebp-Ch]
  void *v253; // [esp+180h] [ebp-8h]
  void *retaddr; // [esp+188h] [ebp+0h]

  v252 = a2;
  v253 = retaddr;
  v226 = lSize;
  v225 = a3;
  endPrefixMapping = this;
  v242 = this;
  memset(v240, 0, 32);
  while ( 1 )
  {
    ulMaxElementDepth = endPrefixMapping->_ulMaxElementDepth;
    v6 = endPrefixMapping->_ulCurrentElementDepth + 1;
    endPrefixMapping->_ulCurrentElementDepth = v6;
    if ( ulMaxElementDepth && v6 > ulMaxElementDepth )
    {
      MXRRaiseException(-1072894318);
LABEL_364:
      MXRRaiseException(v212);
LABEL_365:
      NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled = 0;
      NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled = 0;
      Registry::readMultipleSettings(NewParserCallbackFailureTrackingRegistry::s_rgSettings);
      NewParserCallbackFailureTrackingRegistry::s_fInitialized = 1;
LABEL_196:
      if ( !NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled )
        goto LABEL_170;
      goto LABEL_197;
    }
    pBlock = (BlockAlloc *)endPrefixMapping->_alloc._pBlock;
    pCharacterSource = endPrefixMapping->_scanner._pCharacterSource;
    pFirst = (NamespaceSupport *)pBlock[1]._pFirst;
    *(_DWORD *)&v240[32] = pFirst;
    sourceType = pCharacterSource->_sourceType;
    if ( sourceType )
    {
      if ( sourceType == Utf16 )
      {
LABEL_19:
        v10 = &pCharacterSource->_pbCurr[-2 * pCharacterSource->_lDelta] - pCharacterSource->_pbSeg;
      }
      else
      {
LABEL_336:
        switch ( sourceType )
        {
          case Utf16B:
          case Ucs2:
          case Ucs2B:
          case CodePage:
            goto LABEL_19;
          case Ucs4:
          case Ucs4B:
            v10 = &pCharacterSource->_pbCurr[-4 * pCharacterSource->_lDelta] - pCharacterSource->_pbSeg;
            break;
          default:
            goto LABEL_5;
        }
      }
    }
    else
    {
LABEL_5:
      v10 = 2 * (&pCharacterSource->_pbCurr[-pCharacterSource->_lDelta] - pCharacterSource->_pbSeg);
    }
    if ( (char *)pBlock[1]._pBlock - (char *)pFirst >= v10 )
    {
      v12 = (BlockAlloc::Header *)pFirst;
    }
    else
    {
      while ( 1 )
      {
        p_pBlock = (unsigned int)&pBlock->_pBlock;
        v11 = pBlock->_pBlock;
        if ( !v11 )
          break;
        pBlock = (BlockAlloc *)pBlock->_pBlock;
        if ( v11->pLast - (unsigned __int8 *)v11 - 16 >= v10 )
        {
          pBlock[1]._pFirst = (BlockAlloc::Header *)&pBlock[2];
          goto LABEL_10;
        }
      }
      pBlock = (BlockAlloc *)BlockAlloc::EnqueueBlock(pBlock, v10, (BlockAlloc::Header *)pBlock);
      *(_DWORD *)p_pBlock = pBlock;
LABEL_10:
      endPrefixMapping->_alloc._pBlock = (BlockAlloc::Header *)pBlock;
      v12 = pBlock[1]._pFirst;
      pFirst = (NamespaceSupport *)v12;
    }
    pBlock[1]._pFirst = (BlockAlloc::Header *)((char *)pBlock[1]._pFirst + v10);
    v13 = endPrefixMapping->_scanner._pCharacterSource;
    *(_DWORD *)v240 = v12;
    v14 = v10 >> 1;
    *(_DWORD *)&v240[4] = v14;
    v15 = v13->_sourceType;
    if ( v15 )
    {
      if ( v15 == Utf16 )
      {
        pbCurr = v13->_pbCurr;
        v53 = 2 * v13->_lDelta;
        pbSeg = v13->_pbSeg;
        v55 = &pbCurr[-v53] - pbSeg;
        if ( (v55 + 1) >> 1 > v14 )
          goto LABEL_369;
        *(_DWORD *)&v240[4] = v55 >> 1;
        memcpy(pFirst, pbSeg, v55);
        v17 = pFirst;
      }
      else
      {
        switch ( v15 )
        {
          case Utf16B:
            v16 = v13->_pbSeg;
            p_pBlock = (unsigned int)&v13->_pbCurr[-2 * v13->_lDelta];
            v17 = pFirst;
            v18 = pFirst;
            v246 = (size_t)pFirst;
            while ( 2 )
            {
              v250 = (wchar_t *)v16;
              v19 = ((char *)v18 - (char *)v17) >> 1;
              if ( (unsigned int)v16 >= p_pBlock )
                goto LABEL_22;
              if ( v19 < v14 )
              {
                v20 = v246;
                *(_WORD *)v246 = (*(unsigned __int8 *)v250 << 8) | v16[1];
                v18 = (NamespaceSupport *)(v20 + 2);
                v246 = (size_t)v18;
                v16 = (unsigned __int8 *)(v250 + 1);
                continue;
              }
              goto LABEL_369;
            }
          case Ucs2:
          case CodePage:
            Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v13, (StringPtr *)v240);
            goto LABEL_21;
          case Ucs2B:
            v67 = v13->_pbSeg;
            p_pBlock = (unsigned int)&v13->_pbCurr[-2 * v13->_lDelta];
            v17 = pFirst;
            v68 = pFirst;
            v246 = (size_t)pFirst;
            break;
          case Ucs4:
            Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v13, (StringPtr *)v240);
            goto LABEL_21;
          case Ucs4B:
            Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v13, (StringPtr *)v240);
            goto LABEL_21;
          default:
            goto LABEL_20;
        }
        while ( 1 )
        {
          v250 = (wchar_t *)v67;
          v19 = ((char *)v68 - (char *)v17) >> 1;
          if ( (unsigned int)v67 >= p_pBlock )
            break;
          if ( v19 >= v14 )
            goto LABEL_369;
          v69 = v246;
          *(_WORD *)v246 = (*(unsigned __int8 *)v250 << 8) | v67[1];
          v68 = (NamespaceSupport *)(v69 + 2);
          v246 = (size_t)v68;
          v67 = (unsigned __int8 *)(v250 + 1);
        }
LABEL_22:
        *(_DWORD *)&v240[4] = v19;
      }
    }
    else
    {
LABEL_20:
      Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v13, (StringPtr *)v240);
LABEL_21:
      v17 = *(NamespaceSupport **)v240;
      pFirst = *(NamespaceSupport **)v240;
    }
    nNsPrefix = (wchar_t *)endPrefixMapping->_scanner._nNsPrefix;
    ++endPrefixMapping->_nsSupport._nContext;
    v250 = nNsPrefix;
    *(_DWORD *)&v240[12] = nNsPrefix;
    p_nsSupport = &endPrefixMapping->_nsSupport;
    v22 = endPrefixMapping->_alloc._pBlock;
    *(_DWORD *)&v240[8] = v17;
    pCurr = (unsigned int)v22->pCurr;
    *(_DWORD *)&v240[36] = pCurr;
    Reader::ParseAttributesN(endPrefixMapping);
    lSize = endPrefixMapping->_attributes._lSize;
    p_pBlock = lSize;
    if ( !lSize )
    {
      if ( endPrefixMapping->_nsAttributes._lSize )
        goto LABEL_25;
      goto LABEL_37;
    }
    if ( lSize < 0 )
      goto LABEL_369;
    if ( lSize < 63 )
    {
LABEL_25:
      v23 = 17 * lSize;
      pStack = (NamespaceSupport *)endPrefixMapping->_attributes._pStack;
      v24 = pStack;
      v25 = (NamespaceSupport *)((char *)pStack + 4 * v23);
      v236 = v25;
      while ( 1 )
      {
        if ( v24 >= v25 )
          goto LABEL_36;
        lCapacity = v24->_maps._lCapacity;
        nContext = v24->_nContext;
        if ( lCapacity )
        {
          v24->_nHashSize = nContext + 2 * lCapacity + 2;
          v24->_pLastPrefix = (StringPtr *)&v24->_maps._pStack[-lCapacity - 1];
          v170 = p_nsSupport;
          pLastPrefix = p_nsSupport->_pLastPrefix;
          if ( pLastPrefix )
          {
            v191 = v24->_maps._lCapacity;
            if ( v191 == pLastPrefix->n )
            {
              if ( !memcmp((const void *)v24->_maps._lSize, pLastPrefix->pwh, 2 * v191) )
              {
                pLastNsUri = p_nsSupport->_pLastNsUri;
                pwh = pLastNsUri->pwh;
                n = (int *)pLastNsUri->n;
                v24->_maps._lInitialCapacity = (int)pwh;
                v24->_pHashTable = n;
                goto LABEL_30;
              }
              v170 = p_nsSupport;
            }
          }
          v172 = v170->_maps._lSize;
          if ( !v172 )
            goto LABEL_250;
          v173 = v24->_maps._lCapacity;
          if ( v172 < 10 )
          {
            p_pBlock = 2 * v173;
            v174 = (size_t)v170->_maps._pStack;
            v175 = v170->_maps._lSize;
            v246 = v174;
            for ( i = (StringPtr *)(v174 + 28 * v175 - 28); ; i = (StringPtr *)((char *)i - 28) )
            {
              v245 = i;
              if ( v173 == i->n )
              {
                if ( !memcmp(i->pwh, (const void *)v24->_maps._lSize, p_pBlock) )
                {
                  v177 = v245;
                  goto LABEL_266;
                }
                i = v245;
                v173 = v24->_maps._lCapacity;
                v174 = v246;
              }
              if ( i == (StringPtr *)v174 )
                goto LABEL_250;
            }
          }
          p_pBlock = hash((const wchar_t *)v24->_maps._lSize, v173, v170->_nHashSeed);
          v195 = p_nsSupport;
          v196 = p_nsSupport->_pHashTable[p_pBlock % p_nsSupport->_nHashSize] - 1;
          while ( 1 )
          {
            if ( v196 < 0 )
              goto LABEL_250;
            v177 = (StringPtr *)&v195->_maps._pStack[28 * v196];
            v245 = v177;
            if ( (wchar_t *)p_pBlock == v177[3].pwh )
            {
              v197 = v24->_maps._lCapacity;
              if ( v197 == v177->n )
              {
                v198 = memcmp((const void *)v24->_maps._lSize, v177->pwh, 2 * v197);
                v177 = v245;
                if ( !v198 )
                  break;
              }
            }
            v196 = v177[2].n;
            v195 = p_nsSupport;
          }
          if ( !v245 )
            goto LABEL_250;
LABEL_266:
          v180 = p_nsSupport;
          p_nsSupport->_pLastPrefix = v177;
          v181 = v177 + 1;
          v180->_pLastNsUri = v181;
          v29 = v181->pwh;
          v30 = v181->n;
        }
        else
        {
          v28 = v24->_maps._pStack;
          v24->_nHashSize = nContext;
          v24->_pLastPrefix = (StringPtr *)v28;
          v29 = CodeStringPtr::empty.pwh;
          v30 = CodeStringPtr::empty.n;
        }
        v24->_pHashTable = (int *)v30;
        v24->_maps._lInitialCapacity = (int)v29;
LABEL_30:
        for ( j = (BlockAlloc *)pStack; ; j = (BlockAlloc *)((char *)j + 68) )
        {
          v246 = (size_t)j;
          if ( j >= (BlockAlloc *)v24 )
            break;
          v56 = (StringPtr *)j[3]._pBlock;
          if ( v56 != v24->_pLastPrefix )
            continue;
          v57 = j[3]._pFirst;
          v58 = 2 * (_DWORD)v56;
          nHashSize = v24->_nHashSize;
          v44 = v58 < 4;
          v60 = (StringPtr *)(v58 - 4);
          v245 = v60;
          if ( v44 )
          {
LABEL_71:
            if ( v60 == (StringPtr *)-4 )
              goto LABEL_79;
          }
          else
          {
            while ( v57->pPrev == *(BlockAlloc::Header **)nHashSize )
            {
              v57 = (BlockAlloc::Header *)((char *)v57 + 4);
              nHashSize += 4;
              v44 = (unsigned int)v245 < 4;
              v60 = (StringPtr *)((char *)v245 - 4);
              v245 = CONTAINING_RECORD(v245, StringPtr, n);
              if ( v44 )
                goto LABEL_71;
            }
          }
          v61 = LOBYTE(v57->pPrev) < *(_BYTE *)nHashSize;
          if ( LOBYTE(v57->pPrev) != *(_BYTE *)nHashSize
            || v245 != (StringPtr *)-3
            && ((v62 = BYTE1(v57->pPrev), v61 = v62 < *(_BYTE *)(nHashSize + 1), v62 != *(_BYTE *)(nHashSize + 1))
             || v245 != (StringPtr *)-2
             && ((v63 = BYTE2(v57->pPrev), v61 = v63 < *(_BYTE *)(nHashSize + 2), v63 != *(_BYTE *)(nHashSize + 2))
              || v245 != (StringPtr *)-1
              && (pPrev_high = HIBYTE(v57->pPrev),
                  v61 = pPrev_high < *(_BYTE *)(nHashSize + 3),
                  pPrev_high != *(_BYTE *)(nHashSize + 3)))) )
          {
            v65 = v61 ? -1 : 1;
            goto LABEL_80;
          }
LABEL_79:
          v65 = 0;
LABEL_80:
          j = (BlockAlloc *)v246;
          if ( !v65 )
          {
            v208 = *(int **)(v246 + 20);
            if ( v208 == v24->_pHashTable )
            {
              if ( !memcmp(*(const void **)(v246 + 16), (const void *)v24->_maps._lInitialCapacity, 2 * (_DWORD)v208) )
                goto LABEL_335;
              j = (BlockAlloc *)v246;
            }
          }
        }
        v25 = v236;
        v24 = (NamespaceSupport *)((char *)v24 + 68);
      }
    }
    v66 = lSize + ((unsigned int)lSize >> 2);
    v246 = v66;
    if ( v66 < lSize )
    {
      if ( (unsigned int)lSize >= 0x7FFFFFFF )
        goto LABEL_368;
      v66 = 0x7FFFFFFF;
      v246 = 0x7FFFFFFF;
    }
    cHashAttributes = endPrefixMapping->_cHashAttributes;
    if ( v66 > cHashAttributes )
    {
      v212 = ULongLongToUInt(2LL * cHashAttributes, &v233);
      if ( v212 < 0 )
        goto LABEL_364;
      v213 = v233;
      if ( v233 < v246 )
        v213 = v246;
      v233 = v213;
      v214 = new_array<unsigned int>(v213);
      MemFree(v242->_pHashAttributes);
      v215 = v242;
      v242->_cHashAttributes = v213;
      endPrefixMapping = v215;
      v215->_pHashAttributes = (unsigned int *)v214;
      lSize = p_pBlock;
      v66 = v246;
    }
    memset(endPrefixMapping->_pHashAttributes, 0, 4 * v66);
    for ( k = 0; ; *(unsigned int *)((char *)endPrefixMapping->_pHashAttributes + v243) = k )
    {
      pStack = (NamespaceSupport *)k;
      if ( k >= lSize )
        break;
      v245 = (StringPtr *)&endPrefixMapping->_attributes._pStack[68 * k];
      v216 = v245 + 2;
      NamespaceSupport::ProcessAttribute(p_nsSupport, v245, v245 + 1, v245 + 2, v245 + 3);
      v217 = v216->pwh;
      nHashSeed = endPrefixMapping->_nHashSeed;
      v236 = (NamespaceSupport *)v216->n;
      v232 = v217;
      v219 = hash(v217, (int)v236, nHashSeed);
      v231 = v245[3].n;
      v235 = v245[3].pwh;
      v220 = hash(v235, v231, nHashSeed);
      endPrefixMapping = v242;
      v221 = (v219 ^ (unsigned __int64)v220) % v246;
      pHashAttributes = v242->_pHashAttributes;
      v243 = 4 * v221;
      v207 = (wchar_t *)pHashAttributes[v221];
      v234 = v207;
      while ( v207 )
      {
        v209 = (int)&endPrefixMapping->_attributes._pStack[68 * (_DWORD)v207];
        v210 = *(char **)(v209 - 48);
        if ( v210 == (char *)v236 && !memcmp(*(const void **)(v209 - 52), v232, 2 * (_DWORD)v210) )
        {
          v211 = *(_DWORD *)(v209 - 40);
          if ( v211 == v231 && !memcmp(*(const void **)(v209 - 44), v235, 2 * v211) )
          {
LABEL_335:
            MXRRaiseException(-1072894404);
            goto LABEL_336;
          }
        }
        v207 = *(wchar_t **)(v209 - 4);
      }
      lSize = p_pBlock;
      k = (unsigned int)&pStack->_nContext + 1;
      v245[8].pwh = v234;
    }
LABEL_36:
    v34 = endPrefixMapping->_nsAttributes._lSize;
    if ( v34 )
    {
      if ( endPrefixMapping->_fNamespacePrefixes )
      {
        v202 = endPrefixMapping->_nsAttributes._pStack;
        v243 = (unsigned int)v202;
        v234 = (wchar_t *)&v202[68 * v34];
        if ( v202 < (char *)v234 )
        {
          p_attributes = &endPrefixMapping->_attributes;
          v204 = (unsigned int)v202;
          v235 = (wchar_t *)p_attributes;
          do
          {
            v205 = *(_DWORD *)(v204 + 64);
            v230 = *(_OWORD *)v204;
            v229 = *(_OWORD *)(v204 + 16);
            v228 = *(_OWORD *)(v204 + 32);
            v227 = *(_OWORD *)(v204 + 48);
            v206 = _stack<Attribute>::push(p_attributes);
            v204 += 68;
            *(_OWORD *)&v206->qname.pwh = v230;
            *(_OWORD *)&v206->uri.pwh = v229;
            *(_OWORD *)&v206->type.pwh = v228;
            *(_OWORD *)&v206->nToken = v227;
            v206->nHashNext = v205;
            p_attributes = (_stack<Attribute> *)v235;
          }
          while ( v204 < (unsigned int)v234 );
          endPrefixMapping = v242;
        }
      }
    }
LABEL_37:
    v35 = endPrefixMapping->_nsSupport._maps._lSize;
    v36 = endPrefixMapping->_nsSupport._maps._pStack;
    v37 = endPrefixMapping->_nsSupport._nContext;
    if ( *(_DWORD *)&v36[28 * v35 - 12] == v37 )
    {
      p_nsSupport = 0;
      v178 = v35 - 1;
      if ( v35 - 1 >= 0 )
      {
        v179 = p_nsSupport;
        do
        {
          if ( *(_DWORD *)&v36[28 * v178 + 16] != v37 )
            break;
          v179 = (NamespaceSupport *)((char *)v179 + 1);
          --v178;
        }
        while ( v178 >= 0 );
        p_nsSupport = v179;
        endPrefixMapping = v242;
      }
      v38 = p_nsSupport;
    }
    else
    {
      v38 = 0;
      p_nsSupport = 0;
    }
    *(_DWORD *)&v240[40] = v38;
    while ( v38 )
    {
      v145 = (NamespaceSupport *)((char *)v38 - 1);
      p = endPrefixMapping->_pContentHandler._p;
      v147 = endPrefixMapping->_nsSupport._maps._lSize - (_DWORD)v145 - 1;
      p_nsSupport = v145;
      *(_DWORD *)&v240[40] = v145;
      v148 = 7 * v147;
      lSize = ((int (__thiscall *)(HRESULT (__stdcall *)(ISAXContentHandler *, const wchar_t *, int, const wchar_t *, int), IMXRContentHandler *, _DWORD, _DWORD, _DWORD, _DWORD, int, HRESULT))p->startPrefixMapping)(
                p->startPrefixMapping,
                p,
                *(_DWORD *)&endPrefixMapping->_nsSupport._maps._pStack[4 * v148],
                *(_DWORD *)&endPrefixMapping->_nsSupport._maps._pStack[4 * v148 + 4],
                *(_DWORD *)&endPrefixMapping->_nsSupport._maps._pStack[4 * v148 + 8],
                *(_DWORD *)&endPrefixMapping->_nsSupport._maps._pStack[4 * v148 + 12],
                v225,
                v226);
      if ( lSize < 0 )
      {
        if ( NewParserCallbackFailureTrackingRegistry::s_fInitialized )
          goto LABEL_196;
        goto LABEL_365;
      }
      v38 = p_nsSupport;
    }
    v24 = (NamespaceSupport *)v250;
    v39 = pFirst;
    v246 = 2 * (_DWORD)v250;
    if ( v250 )
    {
      v246 = 2 * (_DWORD)v250;
      *(_DWORD *)&v240[24] = (char *)&pFirst->_nContext + 2 * (_DWORD)v250 + 2;
      v40 = *(_DWORD *)&v240[4] - (_DWORD)v250 - 1;
    }
    else
    {
      v40 = *(_DWORD *)&v240[4];
      *(_DWORD *)&v240[24] = pFirst;
    }
    v41 = endPrefixMapping->_nsSupport._pLastPrefix;
    *(_DWORD *)&v240[28] = v40;
    if ( !v41 || v250 != (wchar_t *)v41->n )
      goto LABEL_59;
    v42 = v41->pwh;
    v43 = v246 - 4;
    if ( v246 < 4 )
    {
LABEL_48:
      if ( v43 == -4 )
        goto LABEL_56;
    }
    else
    {
      while ( v39->_nContext == *(_DWORD *)v42 )
      {
        v39 = (NamespaceSupport *)((char *)v39 + 4);
        v42 += 2;
        v44 = v43 < 4;
        v43 -= 4;
        if ( v44 )
          goto LABEL_48;
      }
    }
    v44 = LOBYTE(v39->_nContext) < *(_BYTE *)v42;
    if ( LOBYTE(v39->_nContext) != *(_BYTE *)v42
      || v43 != -3
      && ((v45 = BYTE1(v39->_nContext), v44 = v45 < *((_BYTE *)v42 + 1), v45 != *((_BYTE *)v42 + 1))
       || v43 != -2
       && ((v46 = BYTE2(v39->_nContext), v44 = v46 < *((_BYTE *)v42 + 2), v46 != *((_BYTE *)v42 + 2))
        || v43 != -1
        && (nContext_high = HIBYTE(v39->_nContext),
            v44 = nContext_high < *((_BYTE *)v42 + 3),
            nContext_high != *((_BYTE *)v42 + 3)))) )
    {
      v48 = v44 ? -1 : 1;
      goto LABEL_57;
    }
LABEL_56:
    v48 = 0;
LABEL_57:
    if ( !v48 )
    {
      v70 = endPrefixMapping->_nsSupport._pLastNsUri;
      v71 = v70->pwh;
      v72 = v70->n;
      *(_DWORD *)&v240[16] = v71;
      *(_DWORD *)&v240[20] = v72;
      goto LABEL_93;
    }
    v24 = (NamespaceSupport *)v250;
LABEL_59:
    v49 = endPrefixMapping->_nsSupport._maps._lSize;
    if ( !v49 )
      break;
    if ( v49 < 10 )
    {
      v50 = endPrefixMapping->_nsSupport._maps._pStack;
      for ( m = (StringPtr *)&v50[28 * v49 - 28]; ; m = (StringPtr *)((char *)m - 28) )
      {
        v245 = m;
        if ( v24 == (NamespaceSupport *)m->n )
        {
          v184 = memcmp(m->pwh, pFirst, v246) == 0;
          m = v245;
          if ( v184 )
            goto LABEL_286;
          v24 = (NamespaceSupport *)v250;
          v50 = endPrefixMapping->_nsSupport._maps._pStack;
        }
        if ( m == (StringPtr *)v50 )
          goto LABEL_250;
      }
    }
    v199 = (int)v24;
    v24 = pFirst;
    v243 = hash((const wchar_t *)pFirst, v199, endPrefixMapping->_nsSupport._nHashSeed);
    for ( ii = endPrefixMapping->_nsSupport._pHashTable[v243 % endPrefixMapping->_nsSupport._nHashSize] - 1;
          ;
          ii = v201[2].n )
    {
      if ( ii < 0 )
        goto LABEL_250;
      v201 = (StringPtr *)&endPrefixMapping->_nsSupport._maps._pStack[28 * ii];
      v245 = v201;
      if ( (wchar_t *)v243 == v201[3].pwh && v250 == (wchar_t *)v201->n )
        break;
LABEL_317:
      ;
    }
    if ( memcmp(v24, v201->pwh, 2 * (_DWORD)v250) )
    {
      v201 = v245;
      goto LABEL_317;
    }
    m = v245;
    if ( !v245 )
      break;
LABEL_286:
    endPrefixMapping->_nsSupport._pLastPrefix = m;
    endPrefixMapping->_nsSupport._pLastNsUri = m + 1;
    v186 = m[1].n;
    *(_DWORD *)&v240[16] = m[1].pwh;
    *(_DWORD *)&v240[20] = v186;
LABEL_93:
    v223 = endPrefixMapping->_pContentHandler._p;
    if ( endPrefixMapping->_scanner._nToken != 5 )
    {
      lSize = ((int (__thiscall *)(HRESULT (__stdcall *)(IMXRContentHandler *, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int, ISAXAttributes *), IMXRContentHandler *, _DWORD, _DWORD, _DWORD, _DWORD))endPrefixMapping->_pfnStartEmptyElement)(
                endPrefixMapping->_pfnStartEmptyElement,
                v223,
                *(_DWORD *)&v240[16],
                *(_DWORD *)&v240[20],
                *(_DWORD *)&v240[24],
                *(_DWORD *)&v240[28]);
      if ( lSize >= 0 )
      {
        lSize = ((int (__thiscall *)(HRESULT (__stdcall *)(IMXRContentHandler *, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int), IMXRContentHandler *, _DWORD, _DWORD, _DWORD, _DWORD, NamespaceSupport *, _DWORD))endPrefixMapping->_pfnEndEmptyElement)(
                  endPrefixMapping->_pfnEndEmptyElement,
                  endPrefixMapping->_pContentHandler._p,
                  *(_DWORD *)&v240[16],
                  *(_DWORD *)&v240[20],
                  *(_DWORD *)&v240[24],
                  *(_DWORD *)&v240[28],
                  pFirst,
                  *(_DWORD *)&v240[4]);
        if ( lSize >= 0 )
          goto End_4;
      }
LABEL_258:
      Reader::OnCallbackFailure(lSize);
CleanUp_5:
      MXRRaiseException(lSize);
LABEL_173:
      --endPrefixMapping->_parseElementNStack._lSize;
      v132 = (int)&endPrefixMapping->_parseElementNStack._pStack[44 * endPrefixMapping->_parseElementNStack._lSize];
      v133 = *(_OWORD *)v132;
      p_nsSupport = *(NamespaceSupport **)(v132 + 40);
      *(_OWORD *)v240 = v133;
      v134 = (NamespaceSupport *)v133;
      v135 = *(_OWORD *)(v132 + 16);
      *(_DWORD *)&v240[40] = p_nsSupport;
      pFirst = v134;
      *(_OWORD *)&v240[16] = v135;
      *(_QWORD *)&v240[32] = *(_QWORD *)(v132 + 32);
      goto Continue_0;
    }
    lSize = ((int (__thiscall *)(HRESULT (__stdcall *)(ISAXContentHandler *, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int, ISAXAttributes *), IMXRContentHandler *, _DWORD, _DWORD, _DWORD, _DWORD))endPrefixMapping->_pContentHandler._p->startElement)(
              endPrefixMapping->_pContentHandler._p->startElement,
              v223,
              *(_DWORD *)&v240[16],
              *(_DWORD *)&v240[20],
              *(_DWORD *)&v240[24],
              *(_DWORD *)&v240[28]);
    if ( lSize < 0 )
    {
      if ( NewParserCallbackFailureTrackingRegistry::s_fInitialized )
        goto LABEL_169;
      goto LABEL_185;
    }
    v73 = endPrefixMapping->_alloc._pBlock;
    v74 = pCurr;
    if ( (unsigned int)v73 < pCurr && (unsigned __int8 *)pCurr <= v73->pCurr )
    {
      v73->pCurr = (unsigned __int8 *)pCurr;
      goto Continue_0;
    }
    do
    {
      v73 = v73->pPrev;
      endPrefixMapping->_alloc._pBlock = v73;
      if ( !v73 )
        goto Continue_0;
    }
    while ( (unsigned int)v73 >= v74 || (unsigned __int8 *)v74 > v73->pLast );
    v73->pCurr = (unsigned __int8 *)v74;
Continue_0:
    while ( 2 )
    {
      while ( 2 )
      {
        Scanner::DoScan(&endPrefixMapping->_scanner, (Scanner::ScanOp)*(_DWORD *)endPrefixMapping->_scanner._scanOp);
        nToken = endPrefixMapping->_scanner._nToken;
        if ( nToken == 4 )
        {
          v76 = endPrefixMapping->_scanner._pCharacterSource;
          v77 = v76->_sourceType;
          if ( v77 )
          {
            if ( v77 == Utf16 )
            {
LABEL_145:
              v78 = &v76->_pbCurr[-2 * v76->_lDelta] - v76->_pbSeg;
            }
            else
            {
              switch ( v77 )
              {
                case Utf16B:
                case Ucs2:
                case Ucs2B:
                case CodePage:
                  goto LABEL_145;
                case Ucs4:
                case Ucs4B:
                  v78 = &v76->_pbCurr[-4 * v76->_lDelta] - v76->_pbSeg;
                  break;
                default:
                  goto LABEL_103;
              }
            }
          }
          else
          {
LABEL_103:
            v78 = 2 * (&v76->_pbCurr[-v76->_lDelta] - v76->_pbSeg);
          }
          v79 = (BlockAlloc *)endPrefixMapping->_alloc._pBlock;
          v80 = (wchar_t *)v79[1]._pFirst;
          if ( (char *)v79[1]._pBlock - (char *)v80 < v78 )
          {
            while ( 1 )
            {
              pCurr = (unsigned int)&v79->_pBlock;
              v81 = v79->_pBlock;
              if ( !v81 )
                break;
              v79 = (BlockAlloc *)v79->_pBlock;
              if ( v81->pLast - (unsigned __int8 *)v81 - 16 >= v78 )
              {
                v79[1]._pFirst = (BlockAlloc::Header *)&v79[2];
                goto LABEL_108;
              }
            }
            v79 = (BlockAlloc *)BlockAlloc::EnqueueBlock(v79, v78, (BlockAlloc::Header *)v79);
            *(_DWORD *)pCurr = v79;
LABEL_108:
            endPrefixMapping->_alloc._pBlock = (BlockAlloc::Header *)v79;
            v80 = (wchar_t *)v79[1]._pFirst;
          }
          v79[1]._pFirst = (BlockAlloc::Header *)((char *)v79[1]._pFirst + v78);
          v82 = endPrefixMapping->_scanner._pCharacterSource;
          v83 = v78 >> 1;
          v239.pwh = v80;
          v239.n = v83;
          v84 = v82->_sourceType;
          if ( v84 )
          {
            if ( v84 == Utf16 )
            {
              p_pBlock = (unsigned int)v82->_pbSeg;
              v113 = (size_t)&v82->_pbCurr[-p_pBlock + -2 * v82->_lDelta];
              if ( (v113 + 1) >> 1 > v83 )
                goto LABEL_369;
              pCurr = v113 >> 1;
              memcpy(v80, (const void *)p_pBlock, v113);
              v88 = pCurr;
            }
            else
            {
              switch ( v84 )
              {
                case Utf16B:
                  v250 = (wchar_t *)v82->_pbSeg;
                  v85 = (int)&v82->_pbCurr[-2 * v82->_lDelta];
                  p_pBlock = (unsigned int)v80;
                  pCurr = v85;
                  v86 = v80;
                  v87 = v250;
                  while ( 2 )
                  {
                    v88 = v86 - v80;
                    if ( (unsigned int)v87 >= pCurr )
                      goto LABEL_118;
                    if ( v88 < v83 )
                    {
                      v89 = p_pBlock;
                      *(_WORD *)p_pBlock = *((unsigned __int8 *)v250 + 1) | (*(unsigned __int8 *)v87 << 8);
                      v86 = (wchar_t *)(v89 + 2);
                      v87 = v250 + 1;
                      p_pBlock = (unsigned int)v86;
                      ++v250;
                      continue;
                    }
                    goto LABEL_369;
                  }
                case Ucs2:
                case CodePage:
                  Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v82, &v239);
                  goto LABEL_117;
                case Ucs2B:
                  v250 = (wchar_t *)v82->_pbSeg;
                  v120 = (int)&v82->_pbCurr[-2 * v82->_lDelta];
                  p_pBlock = (unsigned int)v80;
                  pCurr = v120;
                  v121 = v80;
                  v122 = v250;
                  break;
                case Ucs4:
                  Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v82, &v239);
                  goto LABEL_117;
                case Ucs4B:
                  Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v82, &v239);
                  goto LABEL_117;
                default:
                  goto LABEL_116;
              }
              while ( 1 )
              {
                v88 = v121 - v80;
                if ( (unsigned int)v122 >= pCurr )
                  break;
                if ( v88 >= v83 )
                  goto LABEL_369;
                v123 = p_pBlock;
                *(_WORD *)p_pBlock = *((unsigned __int8 *)v250 + 1) | (*(unsigned __int8 *)v122 << 8);
                v121 = (wchar_t *)(v123 + 2);
                v122 = v250 + 1;
                p_pBlock = (unsigned int)v121;
                ++v250;
              }
            }
          }
          else
          {
LABEL_116:
            Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v82, &v239);
LABEL_117:
            v88 = v239.n;
          }
LABEL_118:
          if ( v88 == *(_DWORD *)&v240[4] )
          {
            v90 = v239.pwh;
            v91 = 2 * v88;
            v92 = pFirst;
            v44 = v91 < 4;
            v93 = v91 - 4;
            if ( v44 )
            {
LABEL_122:
              if ( v93 != -4 )
                goto LABEL_123;
              goto LABEL_130;
            }
            while ( *(_DWORD *)v90 == v92->_nContext )
            {
              v90 += 2;
              v92 = (NamespaceSupport *)((char *)v92 + 4);
              v44 = v93 < 4;
              v93 -= 4;
              if ( v44 )
                goto LABEL_122;
            }
LABEL_123:
            v94 = *(_BYTE *)v90 < LOBYTE(v92->_nContext);
            if ( *(_BYTE *)v90 == LOBYTE(v92->_nContext)
              && (v93 == -3
               || (v95 = *((_BYTE *)v90 + 1), v94 = v95 < BYTE1(v92->_nContext), v95 == BYTE1(v92->_nContext))
               && (v93 == -2
                || (v96 = *((_BYTE *)v90 + 2), v94 = v96 < BYTE2(v92->_nContext), v96 == BYTE2(v92->_nContext))
                && (v93 == -1
                 || (v97 = *((_BYTE *)v90 + 3), v94 = v97 < HIBYTE(v92->_nContext), v97 == HIBYTE(v92->_nContext))))) )
            {
LABEL_130:
              v98 = 0;
            }
            else
            {
              v98 = v94 ? -1 : 1;
            }
            if ( !v98 )
            {
              if ( p_nsSupport )
                goto LABEL_367;
              endElement = endPrefixMapping->_pContentHandler._p->endElement;
              lSize = ((int (__thiscall *)(HRESULT (__stdcall *)(ISAXContentHandler *, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int), IMXRContentHandler *, _DWORD, _DWORD, _DWORD, _DWORD, NamespaceSupport *, _DWORD))endElement)(
                        endElement,
                        endPrefixMapping->_pContentHandler._p,
                        *(_DWORD *)&v240[16],
                        *(_DWORD *)&v240[20],
                        *(_DWORD *)&v240[24],
                        *(_DWORD *)&v240[28],
                        pFirst,
                        *(_DWORD *)&v240[4]);
              if ( lSize >= 0 )
              {
End_4:
                v125 = endPrefixMapping->_nsSupport._maps._lSize;
                v126 = endPrefixMapping->_nsSupport._maps._pStack;
                v127 = endPrefixMapping->_nsSupport._nContext;
                if ( *(_DWORD *)&v126[28 * v125 - 12] == v127 )
                {
                  v128 = 0;
                  v182 = v125 - 1;
                  pCurr = v182;
                  if ( v182 >= 0 )
                  {
                    for ( jj = v182; jj >= 0; --jj )
                    {
                      if ( *(_DWORD *)&v126[28 * jj + 16] != v127 )
                        break;
                      ++v128;
                    }
                    endPrefixMapping = v242;
                  }
                }
                else
                {
                  v128 = 0;
                }
                v24 = &endPrefixMapping->_nsSupport;
                pCurr = (unsigned int)&endPrefixMapping->_nsSupport;
                goto LABEL_160;
              }
              if ( NewParserCallbackFailureTrackingRegistry::s_fInitialized )
              {
LABEL_169:
                if ( !NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled )
                {
LABEL_170:
                  if ( IsNewParserCallbackFailureDebugBreakEnabled() )
                    MEMORY[0] = 0;
                  goto CleanUp_5;
                }
LABEL_197:
                CurrentThreadId = GetCurrentThreadId();
                StringCchPrintfW(
                  v251,
                  0x80u,
                  L"SAX callback failed with HRESULT = 0x%08X. (ThreadId = 0x%X)\r\n",
                  lSize,
                  CurrentThreadId);
                OutputDebugStringW(v251);
                goto LABEL_170;
              }
LABEL_185:
              NewParserCallbackFailureTrackingRegistry::s_fTracingEnabled = 0;
              NewParserCallbackFailureTrackingRegistry::s_fDebugBreakEnabled = 0;
              Registry::readMultipleSettings(NewParserCallbackFailureTrackingRegistry::s_rgSettings);
              NewParserCallbackFailureTrackingRegistry::s_fInitialized = 1;
              goto LABEL_169;
            }
          }
          MXRRaiseException(-1072894405);
LABEL_133:
          switch ( nToken )
          {
            case 7:
              v99 = endPrefixMapping->_alloc._pBlock;
              v100 = endPrefixMapping->_scanner._pCharacterSource;
              pStack = (NamespaceSupport *)v99->pCurr;
              v101 = v100->_sourceType;
              if ( v101 )
              {
                if ( v101 == Utf16 )
                {
LABEL_175:
                  v102 = &v100->_pbCurr[-2 * v100->_lDelta] - v100->_pbSeg;
                }
                else
                {
                  switch ( v101 )
                  {
                    case Utf16B:
                    case Ucs2:
                    case Ucs2B:
                    case CodePage:
                      goto LABEL_175;
                    case Ucs4:
                    case Ucs4B:
                      v102 = &v100->_pbCurr[-4 * v100->_lDelta] - v100->_pbSeg;
                      break;
                    default:
                      goto LABEL_135;
                  }
                }
              }
              else
              {
LABEL_135:
                v102 = 2 * (&v100->_pbCurr[-v100->_lDelta] - v100->_pbSeg);
              }
              v103 = v99->pLast - (unsigned __int8 *)pStack;
              v250 = (wchar_t *)pStack;
              if ( v103 >= v102 )
                goto LABEL_137;
              while ( 1 )
              {
                pCurr = (unsigned int)&v99->pNext;
                pNext = v99->pNext;
                if ( !pNext )
                  break;
                v99 = v99->pNext;
                if ( pNext->pLast - (unsigned __int8 *)pNext - 16 >= v102 )
                {
                  v99->pCurr = (unsigned __int8 *)&v99[1];
                  goto LABEL_189;
                }
              }
              v99 = BlockAlloc::EnqueueBlock((BlockAlloc *)pStack, v102, v99);
              *(_DWORD *)pCurr = v99;
LABEL_189:
              endPrefixMapping->_alloc._pBlock = v99;
              v250 = (wchar_t *)v99->pCurr;
LABEL_137:
              v99->pCurr += v102;
              v104 = endPrefixMapping->_scanner._pCharacterSource;
              v105 = v250;
              v106 = v102 >> 1;
              v238.pwh = v250;
              v107 = v104->_sourceType;
              v238.n = v106;
              if ( v107 )
              {
                if ( v107 == Utf16 )
                {
                  p_pBlock = (unsigned int)v104->_pbSeg;
                  v139 = (size_t)&v104->_pbCurr[-p_pBlock + -2 * v104->_lDelta];
                  if ( (v139 + 1) >> 1 > v106 )
                    goto LABEL_369;
                  v238.n = v139 >> 1;
                  memcpy(v250, (const void *)p_pBlock, v139);
                }
                else
                {
                  switch ( v107 )
                  {
                    case Utf16B:
                      v108 = (unsigned __int16 *)v104->_pbSeg;
                      pCurr = (unsigned int)&v104->_pbCurr[-2 * v104->_lDelta];
                      v109 = v250;
                      v110 = v250;
                      p_pBlock = (unsigned int)v250;
                      while ( 2 )
                      {
                        v111 = v110 - v109;
                        if ( (unsigned int)v108 >= pCurr )
                          goto LABEL_177;
                        if ( v111 < v106 )
                        {
                          v112 = p_pBlock;
                          *(_WORD *)p_pBlock = _byteswap_ushort(*v108);
                          v110 = (wchar_t *)(v112 + 2);
                          v109 = v250;
                          ++v108;
                          p_pBlock = (unsigned int)v110;
                          continue;
                        }
                        goto LABEL_369;
                      }
                    case Ucs2:
                    case CodePage:
                      Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v104, &v238);
                      goto LABEL_178;
                    case Ucs2B:
                      v250 = (wchar_t *)v104->_pbSeg;
                      v141 = (int)&v104->_pbCurr[-2 * v104->_lDelta];
                      p_pBlock = (unsigned int)v105;
                      pCurr = v141;
                      v142 = v105;
                      v143 = v250;
                      break;
                    case Ucs4:
                      Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v104, &v238);
                      goto LABEL_178;
                    case Ucs4B:
                      Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v104, &v238);
                      goto LABEL_178;
                    default:
                      goto LABEL_176;
                  }
                  while ( 1 )
                  {
                    v111 = v142 - v105;
                    if ( (unsigned int)v143 >= pCurr )
                      break;
                    if ( v111 >= v106 )
                      goto LABEL_369;
                    v144 = p_pBlock;
                    *(_WORD *)p_pBlock = *((unsigned __int8 *)v250 + 1) | (*(unsigned __int8 *)v143 << 8);
                    v142 = (wchar_t *)(v144 + 2);
                    v143 = v250 + 1;
                    p_pBlock = (unsigned int)v142;
                    ++v250;
                  }
LABEL_177:
                  v238.n = v111;
                }
              }
              else
              {
LABEL_176:
                Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v104, &v238);
              }
LABEL_178:
              characters = endPrefixMapping->_pContentHandler._p->characters;
              lSize = ((int (__thiscall *)(HRESULT (__stdcall *)(ISAXContentHandler *, const wchar_t *, int), IMXRContentHandler *, wchar_t *, int))characters)(
                        characters,
                        endPrefixMapping->_pContentHandler._p,
                        v238.pwh,
                        v238.n);
              if ( lSize < 0 )
                goto LABEL_258;
              v137 = endPrefixMapping->_alloc._pBlock;
              v138 = (BlockAlloc *)pStack;
              if ( v137 >= (BlockAlloc::Header *)pStack || (unsigned __int8 *)pStack > v137->pCurr )
              {
                while ( 1 )
                {
                  v137 = v137->pPrev;
                  endPrefixMapping->_alloc._pBlock = v137;
                  if ( !v137 )
                    break;
                  if ( v137 < (BlockAlloc::Header *)v138 && (unsigned __int8 *)v138 <= v137->pLast )
                    goto LABEL_181;
                }
              }
              else
              {
LABEL_181:
                v137->pCurr = (unsigned __int8 *)v138;
              }
              continue;
            case 8:
              v157 = endPrefixMapping->_scanner._pCharacterSource;
              v243 = (unsigned int)endPrefixMapping->_alloc._pBlock->pCurr;
              v158 = v157->_sourceType;
              if ( v158 )
              {
                if ( v158 == Utf16 )
                {
LABEL_273:
                  v159 = &v157->_pbCurr[-2 * v157->_lDelta] - v157->_pbSeg;
                }
                else
                {
                  switch ( v158 )
                  {
                    case Utf16B:
                    case Ucs2:
                    case Ucs2B:
                    case CodePage:
                      goto LABEL_273;
                    case Ucs4:
                    case Ucs4B:
                      v159 = &v157->_pbCurr[-4 * v157->_lDelta] - v157->_pbSeg;
                      break;
                    default:
                      goto LABEL_229;
                  }
                }
              }
              else
              {
LABEL_229:
                v159 = 2 * (&v157->_pbCurr[-v157->_lDelta] - v157->_pbSeg);
              }
              v160 = endPrefixMapping->_alloc._pBlock;
              v161 = (wchar_t *)v160->pCurr;
              if ( v160->pLast - (unsigned __int8 *)v161 < v159 )
              {
                v160 = BlockAlloc::RequeueBlock(&endPrefixMapping->_alloc, v159);
                endPrefixMapping->_alloc._pBlock = v160;
                v161 = (wchar_t *)v160->pCurr;
              }
              v160->pCurr += v159;
              v162 = endPrefixMapping->_scanner._pCharacterSource;
              v163 = v159 >> 1;
              v237.pwh = v161;
              v237.n = v163;
              v164 = v162->_sourceType;
              if ( v164 )
              {
                if ( v164 == Utf16 )
                {
                  p_pBlock = (unsigned int)v162->_pbSeg;
                  v185 = (size_t)&v162->_pbCurr[-p_pBlock + -2 * v162->_lDelta];
                  if ( (v185 + 1) >> 1 > v163 )
                    goto LABEL_369;
                  v237.n = v185 >> 1;
                  memcpy(v161, (const void *)p_pBlock, v185);
                }
                else
                {
                  switch ( v164 )
                  {
                    case Utf16B:
                      v250 = (wchar_t *)v162->_pbSeg;
                      v165 = (int)&v162->_pbCurr[-2 * v162->_lDelta];
                      p_pBlock = (unsigned int)v161;
                      pCurr = v165;
                      v166 = v161;
                      v167 = v250;
                      while ( 2 )
                      {
                        v168 = v166 - v161;
                        if ( (unsigned int)v167 >= pCurr )
                          goto LABEL_277;
                        if ( v168 < v163 )
                        {
                          v169 = p_pBlock;
                          *(_WORD *)p_pBlock = (*(unsigned __int8 *)v250 << 8) | *((unsigned __int8 *)v167 + 1);
                          v166 = (wchar_t *)(v169 + 2);
                          v167 = v250 + 1;
                          p_pBlock = (unsigned int)v166;
                          ++v250;
                          continue;
                        }
                        goto LABEL_369;
                      }
                    case Ucs2:
                    case CodePage:
                      Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v162, &v237);
                      goto LABEL_278;
                    case Ucs2B:
                      v250 = (wchar_t *)v162->_pbSeg;
                      v187 = (int)&v162->_pbCurr[-2 * v162->_lDelta];
                      p_pBlock = (unsigned int)v161;
                      pCurr = v187;
                      v188 = v161;
                      v189 = v250;
                      break;
                    case Ucs4:
                      Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v162, &v237);
                      goto LABEL_278;
                    case Ucs4B:
                      Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v162, &v237);
                      goto LABEL_278;
                    default:
                      goto LABEL_276;
                  }
                  while ( 1 )
                  {
                    v168 = v188 - v161;
                    if ( (unsigned int)v189 >= pCurr )
                      break;
                    if ( v168 >= v163 )
                      goto LABEL_369;
                    v190 = p_pBlock;
                    *(_WORD *)p_pBlock = *((unsigned __int8 *)v250 + 1) | (*(unsigned __int8 *)v189 << 8);
                    v188 = (wchar_t *)(v190 + 2);
                    v189 = v250 + 1;
                    p_pBlock = (unsigned int)v188;
                    ++v250;
                  }
LABEL_277:
                  v237.n = v168;
                }
              }
              else
              {
LABEL_276:
                Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v162, &v237);
              }
LABEL_278:
              lSize = ((int (__thiscall *)(HRESULT (__stdcall *)(IMXRContentHandler *, const wchar_t *, int), IMXRContentHandler *, wchar_t *, int))endPrefixMapping->_pfnWhitespace)(
                        endPrefixMapping->_pfnWhitespace,
                        endPrefixMapping->_pContentHandler._p,
                        v237.pwh,
                        v237.n);
              if ( lSize < 0 )
                goto LABEL_258;
              v137 = endPrefixMapping->_alloc._pBlock;
              v138 = (BlockAlloc *)v243;
              if ( (unsigned int)v137 >= v243 || (unsigned __int8 *)v243 > v137->pCurr )
              {
                while ( 1 )
                {
                  v137 = v137->pPrev;
                  endPrefixMapping->_alloc._pBlock = v137;
                  if ( !v137 )
                    break;
                  if ( v137 < (BlockAlloc::Header *)v138 && (unsigned __int8 *)v138 <= v137->pLast )
                    goto LABEL_181;
                }
              }
              else
              {
                v137->pCurr = (unsigned __int8 *)v243;
              }
              continue;
            case 9:
              v150 = endPrefixMapping->_alloc._pBlock;
              pCurr = (unsigned int)v150->pCurr;
              v151 = (_WORD *)pCurr;
              if ( &v150->pLast[-pCurr] < (unsigned __int8 *)2 )
              {
                v150 = BlockAlloc::RequeueBlock(&endPrefixMapping->_alloc, 2u);
                endPrefixMapping->_alloc._pBlock = v150;
                v151 = v150->pCurr;
              }
              v150->pCurr += 2;
              *v151 = 10;
              lSize = ((int (__thiscall *)(HRESULT (__stdcall *)(IMXRContentHandler *, const wchar_t *, int), IMXRContentHandler *, _WORD *, int))endPrefixMapping->_pfnWhitespace)(
                        endPrefixMapping->_pfnWhitespace,
                        endPrefixMapping->_pContentHandler._p,
                        v151,
                        1);
              if ( lSize < 0 )
                goto LABEL_258;
              v137 = endPrefixMapping->_alloc._pBlock;
              v138 = (BlockAlloc *)pCurr;
              if ( (unsigned int)v137 < pCurr && (unsigned __int8 *)pCurr <= v137->pCurr )
              {
                v137->pCurr = (unsigned __int8 *)pCurr;
                continue;
              }
              while ( 1 )
              {
                v137 = v137->pPrev;
                endPrefixMapping->_alloc._pBlock = v137;
                if ( !v137 )
                  goto Continue_0;
                if ( v137 < (BlockAlloc::Header *)v138 && (unsigned __int8 *)v138 <= v137->pLast )
                  goto LABEL_181;
              }
            case 10:
              Reader::ParseCharRef(endPrefixMapping);
              continue;
            case 11:
              Reader::ParseEntityRef(endPrefixMapping, *(void **)&v240[32], (int *)&v240[40]);
              p_nsSupport = *(NamespaceSupport **)&v240[40];
              pFirst = *(NamespaceSupport **)v240;
              continue;
            case 13:
              Reader::ParseCdSect(endPrefixMapping);
              continue;
            case 15:
              Reader::ParseComment(endPrefixMapping);
              continue;
            case 17:
              Reader::ParsePi(endPrefixMapping);
              continue;
            case 59:
              --endPrefixMapping->_ulCurrentElementDepth;
              v152 = *(_DWORD *)&endPrefixMapping->_inputSources._pStack[4 * endPrefixMapping->_inputSources._lSize - 4];
              v153 = (*(int (__thiscall **)(int))(*(_DWORD *)v152 + 12))(v152);
              v154 = v242;
              v250 = (wchar_t *)v153;
              if ( v242->_inputSources._lSize == 1 )
              {
                MXRRaiseException(-1072894463);
LABEL_367:
                MXRRaiseException(-1072894394);
LABEL_368:
                MXRRaiseException(-2147352566);
LABEL_369:
                MXRRaiseException(-2147418113);
                JUMPOUT(0x100441F8);
              }
              if ( *(_BYTE *)(v153 + 40) )
                --v242->_nExternalMarkup;
              if ( *(_DWORD *)(v153 + 76) != *(_DWORD *)&v240[32] )
                goto LABEL_367;
              *(_DWORD *)(v153 + 76) = 0;
              Scanner::PopInputSource(&v154->_scanner);
              --v154->_inputSources._lSize;
              v155 = *(void (__thiscall ****)(unsigned int, int))&v154->_inputSources._pStack[4
                                                                                            * v154->_inputSources._lSize];
              pCurr = (unsigned int)v155;
              if ( v155 )
                (**v155)(pCurr, 1);
              p_nsSupport = (NamespaceSupport *)((char *)p_nsSupport - 1);
              *(_DWORD *)&v240[40] = p_nsSupport;
              pCurr = (unsigned int)v154->_pLexicalHandler._p;
              v243 = *(_DWORD *)(*(_DWORD *)pCurr + 24);
              endPrefixMapping = *(Reader **)((*(int (__thiscall **)(wchar_t *))(*(_DWORD *)v250 + 4))(v250) + 4);
              v156 = (_DWORD *)(*(int (__thiscall **)(wchar_t *))(*(_DWORD *)v250 + 4))(v250);
              lSize = ((int (__thiscall *)(unsigned int, unsigned int, _DWORD, Reader *))v243)(
                        v243,
                        pCurr,
                        *v156,
                        endPrefixMapping);
              if ( lSize < 0 )
                goto LABEL_258;
              endPrefixMapping = v242;
              break;
            default:
              continue;
          }
          continue;
        }
        break;
      }
      if ( nToken != 3 )
        goto LABEL_133;
      if ( endPrefixMapping->_ulCurrentElementDepth < 0x3E8 )
      {
        Reader::ParseElementN(endPrefixMapping);
        continue;
      }
      break;
    }
    lSize = (HRESULT)&endPrefixMapping->_parseElementNStack;
    if ( endPrefixMapping->_parseElementNStack._lCapacity == endPrefixMapping->_parseElementNStack._lSize )
      _stack<Reader::ParseElementNContext>::grow(&endPrefixMapping->_parseElementNStack);
    v114 = endPrefixMapping->_parseElementNStack._lSize;
    v115 = *(_OWORD *)v240;
    *(_DWORD *)&v240[40] = 0;
    endPrefixMapping->_parseElementNStack._lSize = v114 + 1;
    v116 = 44 * v114;
    v117 = p_nsSupport;
    v118 = *(_DWORD *)lSize + v116;
    *(_OWORD *)v118 = v115;
    v119 = *(_OWORD *)&v240[16];
    *(_OWORD *)&v240[16] = 0;
    *(_OWORD *)(v118 + 16) = v119;
    *(_QWORD *)(v118 + 32) = *(_QWORD *)&v240[32];
    *(_OWORD *)v240 = 0;
    *(_DWORD *)(v118 + 40) = v117;
    *(_QWORD *)&v240[32] = 0;
  }
LABEL_250:
  MXRRaiseException(-1072894363);
  do
  {
    v243 = v128 - 1;
    v224 = endPrefixMapping->_pContentHandler._p;
    endPrefixMapping = (Reader *)v224->endPrefixMapping;
    lSize = ((int (__thiscall *)(Reader *, IMXRContentHandler *, _DWORD, _DWORD))endPrefixMapping)(
              endPrefixMapping,
              v224,
              *(_DWORD *)&v24->_maps._pStack[28 * (v129 - v128)],
              *(_DWORD *)&v24->_maps._pStack[28 * (v129 - v128) + 4]);
    if ( lSize < 0 )
      goto LABEL_258;
    endPrefixMapping = v242;
    v24 = (NamespaceSupport *)pCurr;
    v128 = v243;
LABEL_160:
    v129 = v24->_maps._lSize;
  }
  while ( v128 );
  if ( *(_DWORD *)&v24->_maps._pStack[28 * v129 - 12] == v24->_nContext )
    NamespaceSupport::PopContextImpl(v24);
  else
    --v24->_nContext;
  v130 = *(_DWORD *)&v240[32];
  v131 = endPrefixMapping->_alloc._pBlock;
  if ( (unsigned int)v131 >= *(_DWORD *)&v240[32] || (unsigned __int8 *)*(_DWORD *)&v240[32] > v131->pCurr )
  {
    while ( 1 )
    {
      v131 = v131->pPrev;
      endPrefixMapping->_alloc._pBlock = v131;
      if ( !v131 )
        break;
      if ( (unsigned int)v131 < v130 && (unsigned __int8 *)v130 <= v131->pLast )
        goto LABEL_165;
    }
  }
  else
  {
LABEL_165:
    v131->pCurr = (unsigned __int8 *)v130;
  }
  --endPrefixMapping->_ulCurrentElementDepth;
  if ( endPrefixMapping->_parseElementNStack._lSize > 0 )
    goto LABEL_173;
}

```

## disassembly

```asm
0x10042640  mov     edi, edi
0x10042642  push    ebx
0x10042643  mov     ebx, esp
0x10042645  sub     esp, 8
0x10042648  and     esp, 0FFFFFFF0h
0x1004264b  add     esp, 4
0x1004264e  push    ebp
0x1004264f  mov     ebp, [ebx+4]
0x10042652  mov     [esp+0Ch+var_8], ebp
0x10042656  mov     ebp, esp
0x10042658  sub     esp, 218h
0x1004265e  mov     eax, ___security_cookie
0x10042663  xor     eax, ebp
0x10042665  mov     [ebp-4], eax
0x10042668  push    esi
0x10042669  push    edi
0x1004266a  xorps   xmm0, xmm0
0x1004266d  mov     edi, this
0x1004266f  mov     [ebp-134h], edi
0x10042675  movaps  xmmword ptr [ebp-170h], xmm0
0x1004267c  movaps  xmmword ptr [ebp-160h], xmm0
0x10042683  mov     eax, [edi+4E4h]
0x10042689  mov     this, [edi+4DCh]
0x1004268f  inc     eax
0x10042690  mov     [edi+4E4h], eax
0x10042696  test    this, this
0x10042698  jz      short loc_100426A2
0x1004269a  cmp     eax, this
0x1004269c  ja      loc_1004418C
0x100426a2  mov     this, [edi+68h]; this
0x100426a5  mov     edx, [edi+1Ch]
0x100426a8  mov     eax, [this+8]
0x100426ab  mov     [ebp-118h], eax
0x100426b1  mov     [ebp-150h], eax
0x100426b7  mov     eax, [edx+34h]
0x100426ba  test    eax, eax
0x100426bc  jnz     loc_100427BA
0x100426c2  mov     esi, [edx+14h]; jumptable 10043EBC default case
0x100426c5  sub     esi, [edx+20h]
0x100426c8  sub     esi, [edx+18h]
0x100426cb  add     esi, esi
0x100426cd  mov     eax, [this+0Ch]
0x100426d0  sub     eax, [ebp-118h]
0x100426d6  cmp     eax, esi
0x100426d8  jnb     loc_10042B53
0x100426de  mov     edi, edi
0x100426e0  lea     eax, [this+4]
0x100426e3  mov     [ebp-110h], eax
0x100426e9  mov     eax, [eax]
0x100426eb  test    eax, eax
0x100426ed  jz      loc_10043485
0x100426f3  mov     this, eax
0x100426f5  mov     eax, [this+0Ch]
0x100426f8  sub     eax, this
0x100426fa  sub     eax, 10h
0x100426fd  cmp     eax, esi
0x100426ff  jb      short loc_100426E0
0x10042701  lea     eax, [this+10h]
0x10042704  mov     [this+8], eax
0x10042707  mov     [edi+68h], this
0x1004270a  mov     eax, [this+8]
0x1004270d  mov     [ebp-118h], eax
0x10042713  add     [this+8], esi
0x10042716  mov     edx, [edi+1Ch]
0x10042719  mov     [ebp-170h], eax
0x1004271f  shr     esi, 1
0x10042721  mov     [ebp-16Ch], esi
0x10042727  mov     eax, [edx+34h]
0x1004272a  test    eax, eax
0x1004272c  jz      def_10042747; jumptable 10042747 default case
0x10042732  cmp     eax, 1
0x10042735  jz      loc_10042A2E
0x1004273b  sub     eax, 2; switch 6 cases
0x1004273e  cmp     eax, 5
0x10042741  ja      def_10042747; jumptable 10042747 default case
0x10042747  jmp     ds:$LN921[eax*4]; switch jump
0x1004274e  mov     eax, [edx+20h]; jumptable 10042747 case 2
0x10042751  mov     this, [edx+18h]
0x10042754  add     eax, eax
0x10042756  mov     edx, [edx+14h]
0x10042759  sub     edx, eax
0x1004275b  mov     [ebp-110h], edx
0x10042761  mov     edx, [ebp-118h]
0x10042767  mov     eax, edx
0x10042769  mov     [ebp-11Ch], edx
0x1004276f  sub     eax, edx
0x10042771  mov     [ebp-10Ch], this
0x10042777  sar     eax, 1
0x10042779  cmp     this, [ebp-110h]
0x1004277f  jnb     short loc_100427F1
0x10042781  cmp     eax, esi
0x10042783  jnb     loc_100441EE
0x10042789  mov     eax, [ebp-10Ch]
0x1004278f  movzx   this, byte ptr [this+1]
0x10042793  movzx   eax, byte ptr [eax]
0x10042796  shl     ax, 8
0x1004279a  or      cx, ax
0x1004279d  mov     eax, [ebp-11Ch]
0x100427a3  mov     [eax], cx
0x100427a6  add     eax, 2
0x100427a9  mov     this, [ebp-10Ch]
0x100427af  mov     [ebp-11Ch], eax
0x100427b5  add     this, 2
0x100427b8  jmp     short loc_1004276F
0x100427ba  cmp     eax, 1
0x100427bd  jnz     loc_10043EB0
0x100427c3  mov     eax, [edx+20h]; jumptable 10043EBC cases 2-4,7
0x100427c6  mov     esi, [edx+14h]
0x100427c9  add     eax, eax
0x100427cb  sub     esi, eax
0x100427cd  sub     esi, [edx+18h]
0x100427d0  jmp     loc_100426CD
0x100427d5  lea     eax, [ebp-170h]; jumptable 10042747 default case
0x100427db  mov     this, edx; this
0x100427dd  push    eax; pValue
0x100427de  call    ?GetSegmentValue@Utf8CharacterSource@@QAEXPAUStringPtr@@@Z; Utf8CharacterSource::GetSegmentValue(StringPtr *)
0x100427e3  mov     edx, [ebp-170h]
0x100427e9  mov     [ebp-118h], edx
0x100427ef  jmp     short loc_100427F7
0x100427f1  mov     [ebp-16Ch], eax
0x100427f7  mov     eax, [edi+50h]
0x100427fa  mov     this, edi; this
0x100427fc  inc     dword ptr [edi+0C8h]
0x10042802  mov     [ebp-10Ch], eax
0x10042808  mov     [ebp-164h], eax
0x1004280e  lea     eax, [edi+0C8h]
0x10042814  mov     [ebp-128h], eax
0x1004281a  mov     eax, [edi+68h]
0x1004281d  mov     [ebp-168h], edx
0x10042823  mov     eax, [eax+8]
0x10042826  mov     [ebp-114h], eax
0x1004282c  mov     [ebp-14Ch], eax
0x10042832  call    ?ParseAttributesN@Reader@@AAEXXZ; Reader::ParseAttributesN(void)
0x10042837  mov     esi, [edi+80h]
0x1004283d  mov     [ebp-110h], esi
0x10042843  test    esi, esi
0x10042845  jnz     loc_10042B13
0x1004284b  cmp     [edi+90h], esi
0x10042851  jz      loc_100428FC
0x10042857  mov     this, [edi+7Ch]
0x1004285a  mov     eax, esi
0x1004285c  shl     eax, 4
0x1004285f  add     eax, esi
0x10042861  mov     [ebp-138h], this
0x10042867  mov     esi, this
0x10042869  lea     eax, [this+eax*4]
0x1004286c  mov     [ebp-18Ch], eax
0x10042872  cmp     esi, eax
0x10042874  jnb     short loc_100428EE
0x10042876  mov     this, [esi+0Ch]
0x10042879  mov     eax, [esi]
0x1004287b  test    this, this
0x1004287d  jnz     loc_10043774
0x10042883  mov     this, [esi+4]
0x10042886  mov     [esi+18h], eax
0x10042889  mov     [esi+1Ch], this
0x1004288c  mov     eax, ?empty@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::empty ...
0x10042891  mov     this, ?empty@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::empty ...
0x10042897  mov     [esi+14h], this
0x1004289a  mov     [esi+10h], eax
0x1004289d  mov     this, [ebp-138h]
0x100428a3  mov     [ebp-11Ch], this
0x100428a9  cmp     this, esi
0x100428ab  jb      loc_10042A6F
0x100428b1  mov     eax, [ebp-18Ch]
0x100428b7  add     esi, 44h ; 'D'
0x100428ba  jmp     short loc_10042872
0x100428bc  mov     this, [edi+0C0h]
0x100428c2  cmp     eax, this
0x100428c4  ja      loc_10043F0F
0x100428ca  shl     eax, 2
0x100428cd  push    eax; Size
0x100428ce  push    0; Val
0x100428d0  push    dword ptr [edi+0BCh]; void *
0x100428d6  call    _memset
0x100428db  add     esp, 0Ch
0x100428de  xor     edx, edx
0x100428e0  mov     [ebp-138h], edx
0x100428e6  cmp     edx, esi
0x100428e8  jb      loc_10043F85
0x100428ee  mov     this, [edi+90h]
0x100428f4  test    this, this
0x100428f6  jnz     loc_10043D3D
0x100428fc  mov     eax, [edi+0D0h]
0x10042902  mov     edx, [edi+0CCh]
0x10042908  mov     esi, [edi+0C8h]
0x1004290e  lea     this, ds:0[eax*8]
0x10042915  sub     this, eax
0x10042917  cmp     [edx+this*4-0Ch], esi
0x1004291b  jz      loc_1004390A
0x10042921  xor     this, this
0x10042923  mov     [ebp-128h], this
0x10042929  mov     [ebp-148h], this
0x1004292f  nop
0x10042930  test    this, this
0x10042932  jnz     loc_1004339F
0x10042938  mov     esi, [ebp-10Ch]
0x1004293e  mov     this, [ebp-118h]
0x10042944  lea     edx, [esi+esi]
0x10042947  mov     [ebp-11Ch], edx
0x1004294d  test    esi, esi
0x1004294f  jnz     loc_10043BC9
0x10042955  mov     eax, [ebp-16Ch]
0x1004295b  mov     [ebp-158h], this
0x10042961  mov     edx, [edi+0E4h]
0x10042967  mov     [ebp-154h], eax
0x1004296d  test    edx, edx
0x1004296f  jz      short loc_100429E6
0x10042971  cmp     esi, [edx+4]
0x10042974  jnz     short loc_100429E6
0x10042976  mov     esi, [ebp-11Ch]
0x1004297c  mov     edx, [edx]
0x1004297e  sub     esi, 4
0x10042981  jb      short loc_10042994
0x10042983  mov     eax, [this]
0x10042985  cmp     eax, [edx]
0x10042987  jnz     short loc_10042999
0x10042989  add     this, 4
0x1004298c  add     edx, 4
0x1004298f  sub     esi, 4
0x10042992  jnb     short loc_10042983
0x10042994  cmp     esi, 0FFFFFFFCh
0x10042997  jz      short loc_100429D6
0x10042999  mov     al, [this]
0x1004299b  cmp     al, [edx]
0x1004299d  jnz     loc_10043E09
0x100429a3  cmp     esi, 0FFFFFFFDh
0x100429a6  jz      short loc_100429D6
0x100429a8  mov     al, [this+1]
0x100429ab  cmp     al, [edx+1]
0x100429ae  jnz     loc_10043E09
0x100429b4  cmp     esi, 0FFFFFFFEh
0x100429b7  jz      short loc_100429D6
0x100429b9  mov     al, [this+2]
0x100429bc  cmp     al, [edx+2]
0x100429bf  jnz     loc_10043E09
0x100429c5  cmp     esi, 0FFFFFFFFh
0x100429c8  jz      short loc_100429D6
0x100429ca  mov     al, [this+3]
0x100429cd  cmp     al, [edx+3]
0x100429d0  jnz     loc_10043E09
0x100429d6  xor     eax, eax
0x100429d8  test    eax, eax
0x100429da  jz      loc_10042BCE
0x100429e0  mov     esi, [ebp-10Ch]
0x100429e6  mov     eax, [edi+0D0h]
0x100429ec  test    eax, eax
0x100429ee  jz      loc_10043812
0x100429f4  cmp     eax, 0Ah
0x100429f7  jge     loc_10043CB9
0x100429fd  mov     edx, [edi+0CCh]
0x10042a03  lea     this, ds:0[eax*8]
0x10042a0a  sub     this, eax
0x10042a0c  lea     eax, [this-7]
0x10042a0f  lea     eax, [edx+eax*4]
0x10042a12  mov     [ebp-120h], eax
0x10042a18  cmp     esi, [eax+4]
0x10042a1b  jz      loc_100439BC
0x10042a21  cmp     eax, edx
0x10042a23  jz      loc_10043812
0x10042a29  sub     eax, 1Ch
0x10042a2c  jmp     short loc_10042A12
0x10042a2e  mov     eax, [edx+20h]
0x10042a31  mov     this, [edx+14h]
0x10042a34  add     eax, eax
0x10042a36  mov     edx, [edx+18h]
0x10042a39  sub     this, eax
0x10042a3b  sub     this, edx
0x10042a3d  lea     eax, [this+1]
0x10042a40  shr     eax, 1
0x10042a42  cmp     eax, esi
0x10042a44  ja      loc_100441EE
0x10042a4a  push    this; Size
0x10042a4b  mov     eax, this
0x10042a4d  push    edx; Src
0x10042a4e  push    dword ptr [ebp-118h]; void *
0x10042a54  shr     eax, 1
0x10042a56  mov     [ebp-16Ch], eax
0x10042a5c  call    _memcpy
0x10042a61  mov     edx, [ebp-118h]
0x10042a67  add     esp, 0Ch
0x10042a6a  jmp     loc_100427F7
0x10042a6f  mov     eax, [this+1Ch]
0x10042a72  cmp     eax, [esi+1Ch]
0x10042a75  jnz     loc_10042B0B
0x10042a7b  mov     this, [this+18h]
0x10042a7e  add     eax, eax
0x10042a80  mov     edx, [esi+18h]
0x10042a83  sub     eax, 4
0x10042a86  mov     [ebp-120h], eax
0x10042a8c  jb      short loc_10042AAD
0x10042a8e  mov     edi, edi
0x10042a90  mov     eax, [this]
0x10042a92  cmp     eax, [edx]
0x10042a94  jnz     short loc_10042AB2
0x10042a96  mov     eax, [ebp-120h]
0x10042a9c  add     this, 4
0x10042a9f  add     edx, 4
0x10042aa2  sub     eax, 4
0x10042aa5  mov     [ebp-120h], eax
  ... truncated ...
```
