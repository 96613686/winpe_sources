# Reader::ParseAttributesN(void)

- ea: `0x10041610`
- end: `0x10042630`
- name: `?ParseAttributesN@Reader@@AAEXXZ`
- size: `4128`
- prototype: `void __usercall(Reader *this@<ecx>, int@<ebp>, int@<edi>)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1003da64`
- `0x10042640`

## callees

- `0x1003c2f2`
- `0x1003d666`
- `0x1003e210`
- `0x1003e2d1`
- `0x10040e10`
- `0x1004118e`
- `0x100411be`
- `0x10041200`
- `0x10041340`
- `0x10041610`
- `0x10044320`
- `0x1004cce0`
- `0x1004d6c0`
- `0x1004da15`
- `0x1005dcbe`
- `0x10064e1d`
- `0x10064eb7`
- `0x10065f14`
- `0x1006c354`
- `0x10164a26`
- `0x1016ae1a`
- `0x1016aeb1`
- `0x101711a8`
- `0x101711b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10041d40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10041e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10041d40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10041e28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10041c07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10041dba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10041c07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10041dba`

## pseudocode

```c
void __usercall Reader::ParseAttributesN(Reader *this@<ecx>, int a2@<ebp>, int a3@<edi>)
{
  Reader *v3; // esi
  int nToken; // eax
  int lCapacity; // eax
  int lSize; // edx
  CharacterSource *pCharacterSource; // ecx
  SourceType sourceType; // eax
  unsigned __int8 *v9; // edx
  BlockAlloc *pBlock; // ecx
  BlockAlloc::Header *v11; // eax
  _WORD *v12; // edx
  unsigned int v13; // eax
  CharacterSource *v14; // ecx
  SourceType v15; // eax
  char *v16; // ecx
  unsigned int v17; // eax
  Scanner *p_scanner; // edx
  int v19; // eax
  signed int v20; // ecx
  _DWORD *p_pStack; // eax
  int v22; // edx
  _DWORD *v23; // ecx
  CharacterSource *v24; // edx
  SourceType v25; // eax
  unsigned int v26; // ecx
  BlockAlloc::Header *v27; // edx
  StringPtr *v28; // eax
  StringPtr *v29; // edx
  int v30; // ecx
  unsigned int v31; // eax
  unsigned int v32; // ecx
  int v33; // eax
  int v34; // edx
  char *v35; // ecx
  int v36; // eax
  int v37; // ecx
  int v38; // eax
  int v39; // eax
  int v40; // ecx
  wchar_t *pwh; // eax
  __int128 v42; // xmm0
  Attribute *v43; // eax
  int v44; // ecx
  size_t v45; // edx
  BlockAlloc::Header *pNext; // eax
  int v47; // eax
  signed int v48; // eax
  unsigned int v49; // kr28_4
  char *v50; // eax
  unsigned __int8 *v51; // ecx
  unsigned int v52; // eax
  unsigned int v53; // kr30_4
  signed int lInitialCapacity; // edi
  char *v55; // eax
  int v56; // edx
  signed int v57; // eax
  void *v58; // edx
  CharacterSource *v59; // edx
  SourceType v60; // ecx
  unsigned int v61; // ecx
  BlockAlloc::Header *v62; // edx
  unsigned int v63; // eax
  StringPtr *v64; // edx
  CharacterSource *v65; // ecx
  SourceType v66; // eax
  int v67; // eax
  Reader *v68; // ecx
  unsigned int v69; // eax
  unsigned int v70; // eax
  char *v71; // eax
  Reader *v72; // ecx
  Reader *v73; // ecx
  AttValueToken *v74; // eax
  int v75; // ecx
  BlockAlloc::Header *v76; // eax
  unsigned __int8 *pCurr; // edx
  unsigned int v78; // eax
  wchar_t *v79; // eax
  __int128 v80; // xmm0
  Attribute *v81; // eax
  BlockAlloc::Header *v82; // eax
  CharacterSource *v83; // edx
  SourceType v84; // ecx
  unsigned int v85; // ecx
  BlockAlloc::Header *v86; // edx
  BlockAlloc::Header *v87; // eax
  int v88; // eax
  unsigned int v89; // eax
  BlockAlloc::Header *v90; // eax
  BlockAlloc::Header *v91; // eax
  char *v92; // edx
  HRESULT v93; // eax
  unsigned __int8 *v94; // eax
  int v95; // ecx
  _DWORD *v96; // edx
  unsigned int v97; // ecx
  StringPtr *v98; // edi
  char *v99; // edx
  BlockAlloc *v100; // ecx
  BlockAlloc *v101; // eax
  StringPtr *v102; // esi
  BlockAlloc *v103; // edx
  __int16 v104; // ax
  int n; // eax
  unsigned int v106; // eax
  int v107; // ecx
  unsigned int v108; // [esp-84h] [ebp-90h]
  size_t v109; // [esp-84h] [ebp-90h]
  size_t v110; // [esp-84h] [ebp-90h]
  unsigned int v111; // [esp-84h] [ebp-90h]
  StringPtr *v112; // [esp-84h] [ebp-90h]
  __int128 v113; // [esp-78h] [ebp-84h]
  __int128 v114; // [esp-68h] [ebp-74h]
  __int128 v115; // [esp-68h] [ebp-74h]
  __int128 v116; // [esp-58h] [ebp-64h]
  __int128 v117; // [esp-58h] [ebp-64h]
  __int128 v118; // [esp-48h] [ebp-54h]
  StringPtr v119; // [esp-38h] [ebp-44h] BYREF
  StringPtr v120; // [esp-30h] [ebp-3Ch] BYREF
  StringPtr v121; // [esp-28h] [ebp-34h] BYREF
  BlockAlloc *p_alloc; // [esp-20h] [ebp-2Ch]
  unsigned int p_pBlock; // [esp-1Ch] [ebp-28h]
  Reader *v124; // [esp-18h] [ebp-24h]
  unsigned int v125; // [esp-14h] [ebp-20h] BYREF
  unsigned int pFirst; // [esp-10h] [ebp-1Ch]
  int v127; // [esp-Ch] [ebp-18h]
  int v128; // [esp-8h] [ebp-14h]
  unsigned int v129; // [esp-4h] [ebp-10h]
  int v130; // [esp+0h] [ebp-Ch]
  void *v131; // [esp+4h] [ebp-8h]
  int v132; // [esp+8h] [ebp-4h] BYREF
  void *retaddr; // [esp+Ch] [ebp+0h]

  v130 = a2;
  v131 = retaddr;
  v3 = this;
  v124 = this;
  this->_attributes._lSize = 0;
  this->_nsAttributes._lSize = 0;
  this->_attValueTokens._lSize = 0;
  Scanner::DoScan(
    &this->_scanner,
    (Utf8CharacterSource *)&v132,
    (CharacterSource *)a3,
    *(_DWORD *)this->_scanner._scanOp);
LABEL_2:
  while ( 1 )
  {
    nToken = v3->_scanner._nToken;
    if ( nToken == 6 || nToken == 5 )
      break;
    if ( nToken == 12 )
    {
      lCapacity = v3->_attributes._lCapacity;
      if ( lCapacity != v3->_attributes._lSize )
        goto LABEL_7;
      while ( 2 )
      {
        if ( lCapacity )
        {
          if ( lCapacity >= 0 )
          {
            v53 = lCapacity;
            v52 = 2 * lCapacity;
            lInitialCapacity = v52;
            if ( is_mul_ok(2u, v53) && is_mul_ok(0x44u, v52) )
            {
              v55 = new_array<char>(68 * v52);
              v56 = 17 * v3->_attributes._lSize;
              pFirst = (unsigned int)v55;
              memcpy(v55, v3->_attributes._pStack, 4 * v56);
              memset(
                (void *)(pFirst + 68 * v3->_attributes._lSize),
                0,
                68 * (lInitialCapacity - v3->_attributes._lSize));
              if ( v3->_attributes._pStack )
                HeapFree(g_hMsxmlHeap, 0, v3->_attributes._pStack);
              v3->_attributes._pStack = (char *)pFirst;
              goto LABEL_113;
            }
          }
        }
        else
        {
          lInitialCapacity = v3->_attributes._lInitialCapacity;
          if ( lInitialCapacity >= 0 )
          {
            p_pBlock = 68 * lInitialCapacity;
            if ( is_mul_ok(0x44u, lInitialCapacity) )
            {
              v71 = new_array<char>(68 * lInitialCapacity);
              v110 = p_pBlock;
              v3->_attributes._pStack = v71;
              memset(v71, 0, v110);
LABEL_113:
              if ( (unsigned int)lInitialCapacity <= 0x7FFFFFFF )
              {
                v3->_attributes._lCapacity = lInitialCapacity;
LABEL_7:
                lSize = v3->_attributes._lSize;
                a3 = (int)&v3->_attributes._pStack[68 * lSize];
                v127 = a3;
                v3->_attributes._lSize = lSize + 1;
                pCharacterSource = v3->_scanner._pCharacterSource;
                sourceType = pCharacterSource->_sourceType;
                if ( sourceType == Utf8 )
                {
LABEL_8:
                  v9 = (unsigned __int8 *)(2
                                         * (&pCharacterSource->_pbCurr[-pCharacterSource->_lDelta]
                                          - pCharacterSource->_pbSeg));
                  goto LABEL_9;
                }
                if ( sourceType == Utf16 )
                {
LABEL_22:
                  v9 = (unsigned __int8 *)(&pCharacterSource->_pbCurr[-2 * pCharacterSource->_lDelta]
                                         - pCharacterSource->_pbSeg);
                  goto LABEL_9;
                }
LABEL_168:
                switch ( sourceType )
                {
                  case Utf16B:
                  case Ucs2:
                  case Ucs2B:
                  case CodePage:
                    goto LABEL_22;
                  case Ucs4:
                  case Ucs4B:
                    v9 = (unsigned __int8 *)(&pCharacterSource->_pbCurr[-4 * pCharacterSource->_lDelta]
                                           - pCharacterSource->_pbSeg);
                    break;
                  default:
                    goto LABEL_8;
                }
LABEL_9:
                pBlock = (BlockAlloc *)v3->_alloc._pBlock;
                p_alloc = &v3->_alloc;
                v129 = (unsigned int)v9;
                pFirst = (unsigned int)pBlock[1]._pFirst;
                if ( (char *)pBlock[1]._pBlock - pFirst >= (char *)v9 )
                {
                  v12 = (_WORD *)pFirst;
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
                    if ( (unsigned __int8 *)(v11->pLast - (unsigned __int8 *)v11 - 16) >= v9 )
                    {
                      pBlock[1]._pFirst = (BlockAlloc::Header *)&pBlock[2];
                      goto LABEL_13;
                    }
                  }
                  pBlock = (BlockAlloc *)BlockAlloc::EnqueueBlock(
                                           pBlock,
                                           (unsigned int)v9,
                                           (BlockAlloc::Header *)pBlock);
                  *(_DWORD *)p_pBlock = pBlock;
LABEL_13:
                  v3->_alloc._pBlock = (BlockAlloc::Header *)pBlock;
                  v12 = pBlock[1]._pFirst;
                  pFirst = (unsigned int)v12;
                }
                v13 = v129;
                pBlock[1]._pFirst = (BlockAlloc::Header *)((char *)pBlock[1]._pFirst + v129);
                v13 >>= 1;
                *(_DWORD *)a3 = v12;
                *(_DWORD *)(a3 + 4) = v13;
                v14 = v3->_scanner._pCharacterSource;
                v129 = v13;
                v15 = v14->_sourceType;
                if ( v15 )
                {
                  if ( v15 == Utf16 )
                  {
                    v45 = &v14->_pbCurr[-2 * v14->_lDelta] - v14->_pbSeg;
                    p_pBlock = v45;
                    if ( (v45 + 1) >> 1 > v129 )
                      goto LABEL_189;
                    *(_DWORD *)(a3 + 4) = v45 >> 1;
                    memcpy((void *)pFirst, v14->_pbSeg, v45);
                  }
                  else
                  {
                    switch ( v15 )
                    {
                      case Utf16B:
                        pFirst = (unsigned int)v14->_pbSeg;
                        p_pBlock = (unsigned int)&v14->_pbCurr[-2 * v14->_lDelta];
                        v16 = (char *)pFirst;
                        while ( 2 )
                        {
                          v17 = ((int)v12 - *(_DWORD *)a3) >> 1;
                          if ( (unsigned int)v16 >= p_pBlock )
                            goto LABEL_24;
                          if ( v17 < *(_DWORD *)(a3 + 4) )
                          {
                            *v12++ = (*(unsigned __int8 *)pFirst << 8) | (unsigned __int8)v16[1];
                            v16 = (char *)(pFirst + 2);
                            pFirst += 2;
                            continue;
                          }
                          goto LABEL_189;
                        }
                      case Ucs2:
                      case CodePage:
                        Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v14, (StringPtr *)a3);
                        goto LABEL_25;
                      case Ucs2B:
                        pFirst = (unsigned int)v14->_pbSeg;
                        p_pBlock = (unsigned int)&v14->_pbCurr[-2 * v14->_lDelta];
                        v51 = (unsigned __int8 *)pFirst;
                        break;
                      case Ucs4:
                        Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v14, (StringPtr *)a3);
                        goto LABEL_25;
                      case Ucs4B:
                        Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v14, (StringPtr *)a3);
                        goto LABEL_25;
                      default:
                        goto LABEL_23;
                    }
                    while ( 1 )
                    {
                      v17 = ((int)v12 - *(_DWORD *)a3) >> 1;
                      if ( (unsigned int)v51 >= p_pBlock )
                        break;
                      if ( v17 >= *(_DWORD *)(a3 + 4) )
                        goto LABEL_189;
                      *v12++ = *(unsigned __int8 *)(pFirst + 1) | (*v51 << 8);
                      v51 = (unsigned __int8 *)(pFirst + 2);
                      pFirst += 2;
                    }
LABEL_24:
                    *(_DWORD *)(a3 + 4) = v17;
                  }
                }
                else
                {
LABEL_23:
                  Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v14, (StringPtr *)a3);
                }
LABEL_25:
                p_scanner = &v3->_scanner;
                *(_DWORD *)(a3 + 8) = *(_DWORD *)a3;
                *(_DWORD *)(a3 + 12) = v3->_scanner._nNsPrefix;
                *(StringPtr *)(a3 + 32) = CodeStringPtr::CDATA;
                *(_DWORD *)(a3 + 48) = v3->_attValueTokens._lSize;
                *(_DWORD *)(a3 + 64) = 0;
                goto LABEL_26;
              }
            }
          }
        }
LABEL_81:
        MXRRaiseException(-2147024362);
        continue;
      }
    }
    if ( nToken == 59 )
      goto LABEL_190;
    MXRRaiseException(-1072896750);
LABEL_61:
    *(_DWORD *)(v31 + 8) = v32;
    p_scanner = &v3->_scanner;
LABEL_26:
    while ( 2 )
    {
      while ( 1 )
      {
        Scanner::DoScan(p_scanner, (Utf8CharacterSource *)&v132, (CharacterSource *)a3, *(_DWORD *)p_scanner->_scanOp);
        v19 = v3->_scanner._nToken;
        if ( v19 != 7 )
          break;
        v20 = v3->_attValueTokens._lCapacity;
        p_pStack = &v3->_attValueTokens._pStack;
        if ( v20 == v3->_attValueTokens._lSize )
        {
          if ( !v20 )
          {
            v47 = v3->_attValueTokens._lInitialCapacity;
            v128 = v47;
            if ( v47 < 0 )
              goto LABEL_81;
            v49 = v47;
            v48 = 12 * v47;
            p_pBlock = v48;
            if ( !is_mul_ok(0xCu, v49) )
              goto LABEL_81;
            if ( v48 >= 0
              && ((pFirst = 0, v48)
               && (v50 = (char *)HeapAlloc(g_hMsxmlHeap, 0, v48), (pFirst = (unsigned int)v50) != 0)
               || (failure_tracing::record(), (v50 = (char *)pFirst) != 0)) )
            {
              v109 = p_pBlock;
              v3->_attValueTokens._pStack = v50;
              memset(v50, 0, v109);
              p_pStack = &v3->_attValueTokens._pStack;
            }
            else
            {
              while ( 1 )
              {
                Exception::storeThis(&Exception::s_cexpOutOfMem);
                Exception::throwStored();
LABEL_90:
                v128 = 2 * v20;
                if ( is_mul_ok(2u, v20) )
                {
                  v57 = 24 * v20;
                  if ( is_mul_ok(0xCu, 2 * v20) )
                    continue;
                }
                goto LABEL_81;
                if ( v57 >= 0 )
                {
                  pFirst = 0;
                  if ( v57 )
                  {
                    v58 = HeapAlloc(g_hMsxmlHeap, 0, v57);
                    pFirst = (unsigned int)v58;
                    if ( v58 )
                      break;
                  }
                  failure_tracing::record();
                  v58 = (void *)pFirst;
                  if ( pFirst )
                    break;
                }
              }
              memcpy(v58, v3->_attValueTokens._pStack, 12 * v3->_attValueTokens._lSize);
              memset((void *)(pFirst + 12 * v3->_attValueTokens._lSize), 0, 12 * (v128 - v3->_attValueTokens._lSize));
              p_pStack = &v3->_attValueTokens._pStack;
              if ( v3->_attValueTokens._pStack )
              {
                HeapFree(g_hMsxmlHeap, 0, v3->_attValueTokens._pStack);
                p_pStack = &v3->_attValueTokens._pStack;
              }
              *p_pStack = pFirst;
            }
            if ( (unsigned int)v128 > 0x7FFFFFFF )
              goto LABEL_81;
            p_pStack[2] = v128;
            goto LABEL_28;
          }
          if ( v20 < 0 )
            goto LABEL_81;
          goto LABEL_90;
        }
LABEL_28:
        v22 = p_pStack[1];
        v129 = *p_pStack + 12 * v22;
        v23 = (_DWORD *)v129;
        v3->_attValueTokens._lSize = v22 + 1;
        *v23 = 7;
        v24 = v3->_scanner._pCharacterSource;
        v25 = v24->_sourceType;
        if ( v25 )
        {
          if ( v25 == Utf16 )
          {
LABEL_49:
            v26 = &v24->_pbCurr[-2 * v24->_lDelta] - v24->_pbSeg;
          }
          else
          {
            switch ( v25 )
            {
              case Utf16B:
              case Ucs2:
              case Ucs2B:
              case CodePage:
                goto LABEL_49;
              case Ucs4:
              case Ucs4B:
                v26 = &v24->_pbCurr[-4 * v24->_lDelta] - v24->_pbSeg;
                break;
              default:
                goto LABEL_29;
            }
          }
        }
        else
        {
LABEL_29:
          v26 = 2 * (&v24->_pbCurr[-v24->_lDelta] - v24->_pbSeg);
        }
        v27 = v3->_alloc._pBlock;
        v128 = v26;
        pFirst = (unsigned int)v27->pCurr;
        if ( &v27->pLast[-pFirst] < (unsigned __int8 *)v26 )
        {
          while ( 1 )
          {
            p_pBlock = (unsigned int)&v27->pNext;
            pNext = v27->pNext;
            if ( !pNext )
              break;
            v27 = v27->pNext;
            if ( pNext->pLast - (unsigned __int8 *)pNext - 16 >= v26 )
            {
              v27->pCurr = (unsigned __int8 *)&v27[1];
              goto LABEL_58;
            }
          }
          v90 = BlockAlloc::EnqueueBlock((BlockAlloc *)v26, v26, v27);
          v26 = v128;
          v27 = v90;
          *(_DWORD *)p_pBlock = v90;
LABEL_58:
          v3->_alloc._pBlock = v27;
          pFirst = (unsigned int)v27->pCurr;
        }
        v27->pCurr += v26;
        v28 = (StringPtr *)(v129 + 4);
        v29 = (StringPtr *)pFirst;
        *(_DWORD *)(v129 + 8) = v26 >> 1;
        a3 = v127;
        v28->pwh = (wchar_t *)v29;
        v128 = (int)v3->_scanner._pCharacterSource;
        v30 = *(_DWORD *)(v128 + 52);
        if ( v30 )
        {
          if ( v30 != 1 )
          {
            switch ( v30 )
            {
              case 2:
                pFirst = *(_DWORD *)(v128 + 24);
                p_pBlock = *(_DWORD *)(v128 + 20) - 2 * *(_DWORD *)(v128 + 32);
                while ( 2 )
                {
                  v31 = v129;
                  v128 = (int)v29;
                  v128 = (int)v29 - *(_DWORD *)(v129 + 4);
                  v32 = v128 >> 1;
                  a3 = v127;
                  if ( pFirst >= p_pBlock )
                    goto LABEL_61;
                  if ( v32 < *(_DWORD *)(v129 + 8) )
                  {
                    LOWORD(v29->pwh) = _byteswap_ushort(*(_WORD *)pFirst);
                    v29 = (StringPtr *)((char *)v29 + 2);
                    pFirst += 2;
                    continue;
                  }
                  goto LABEL_189;
                }
              case 3:
              case 7:
                Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v128, v28);
                p_scanner = &v3->_scanner;
                continue;
              case 4:
                pFirst = *(_DWORD *)(v128 + 24);
                p_pBlock = *(_DWORD *)(v128 + 20) - 2 * *(_DWORD *)(v128 + 32);
                break;
              case 5:
                Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v128, v28);
                p_scanner = &v3->_scanner;
                continue;
              case 6:
                Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v128, v28);
                p_scanner = &v3->_scanner;
                continue;
              default:
                goto LABEL_50;
            }
            while ( 1 )
            {
              v31 = v129;
              v128 = (int)v29;
              v128 = (int)v29 - *(_DWORD *)(v129 + 4);
              v32 = v128 >> 1;
              a3 = v127;
              if ( pFirst >= p_pBlock )
                goto LABEL_61;
              if ( v32 >= *(_DWORD *)(v129 + 8) )
                goto LABEL_189;
              LOWORD(v29->pwh) = _byteswap_ushort(*(_WORD *)pFirst);
              v29 = (StringPtr *)((char *)v29 + 2);
              pFirst += 2;
            }
          }
          v44 = v128;
          pFirst = *(_DWORD *)(v44 + 20) - 2 * *(_DWORD *)(v44 + 32) - *(_DWORD *)(v44 + 24);
          if ( (pFirst + 1) >> 1 > *(_DWORD *)(v129 + 8) )
            goto LABEL_189;
          v108 = pFirst;
          *(_DWORD *)(v129 + 8) = pFirst >> 1;
          memcpy(v29, *(const void **)(v44 + 24), v108);
          a3 = v127;
          p_scanner = &v3->_scanner;
        }
        else
        {
LABEL_50:
          Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v128, v28);
          p_scanner = &v3->_scanner;
        }
      }
      switch ( v19 )
      {
        case 8:
        case 9:
          v74 = _stack<AttValueToken>::push(&v3->_attValueTokens, (signed int)&v132);
          v75 = v3->_scanner._nToken;
          p_pBlock = (unsigned int)v74;
          v74->nType = v75;
          v76 = v3->_alloc._pBlock;
          pCurr = v76->pCurr;
          if ( (unsigned int)(v76->pLast - pCurr) < 2 )
          {
            v76 = BlockAlloc::RequeueBlock(&v3->_alloc, 2u);
            v3->_alloc._pBlock = v76;
            pCurr = v76->pCurr;
          }
          v76->pCurr += 2;
          v78 = p_pBlock;
          *(_DWORD *)(p_pBlock + 4) = pCurr;
          *(_WORD *)pCurr = 32;
          p_scanner = &v3->_scanner;
          *(_DWORD *)(v78 + 8) = 1;
          continue;
        case 10:
          pFirst = (unsigned int)_stack<AttValueToken>::push(&v3->_attValueTokens, (signed int)&v132);
          *(_DWORD *)pFirst = 10;
          v59 = v3->_scanner._pCharacterSource;
          v60 = v59->_sourceType;
          if ( v60 )
          {
            if ( v60 == Utf16 )
            {
LABEL_116:
              v61 = &v59->_pbCurr[-2 * v59->_lDelta] - v59->_pbSeg;
            }
            else
            {
              switch ( v60 )
              {
                case Utf16B:
                case Ucs2:
                case Ucs2B:
                case CodePage:
                  goto LABEL_116;
                case Ucs4:
                case Ucs4B:
                  v61 = &v59->_pbCurr[-4 * v59->_lDelta] - v59->_pbSeg;
                  break;
                default:
                  goto LABEL_100;
              }
            }
          }
          else
          {
LABEL_100:
            v61 = 2 * (&v59->_pbCurr[-v59->_lDelta] - v59->_pbSeg);
          }
          v62 = v3->_alloc._pBlock;
          v128 = v61;
          v129 = (unsigned int)v62->pCurr;
          if ( &v62->pLast[-v129] >= (unsigned __int8 *)v61 )
          {
            v63 = v129;
            goto LABEL_103;
          }
          while ( 1 )
          {
            p_pBlock = (unsigned int)&v62->pNext;
            v82 = v62->pNext;
            if ( !v82 )
              break;
            v62 = v62->pNext;
            if ( v82->pLast - (unsigned __int8 *)v82 - 16 >= v61 )
            {
              v62->pCurr = (unsigned __int8 *)&v62[1];
              goto LABEL_129;
            }
          }
          v91 = BlockAlloc::EnqueueBlock((BlockAlloc *)v61, v61, v62);
          v61 = v128;
          v62 = v91;
          *(_DWORD *)p_pBlock = v91;
LABEL_129:
          v3->_alloc._pBlock = v62;
          v63 = (unsigned int)v62->pCurr;
          v129 = v63;
LABEL_103:
          v62->pCurr += v61;
          v64 = (StringPtr *)(pFirst + 4);
          v128 = pFirst + 4;
          *(_DWORD *)(pFirst + 4) = v63;
          *(_DWORD *)(pFirst + 8) = v61 >> 1;
          v65 = v3->_scanner._pCharacterSource;
          v66 = v65->_sourceType;
          if ( v66 )
          {
            if ( v66 == Utf16 )
            {
              pFirst = (unsigned int)&v65->_pbCurr[-2 * v65->_lDelta];
              a3 = v127;
              pFirst -= (unsigned int)v65->_pbSeg;
              if ( (pFirst + 1) >> 1 > v64->n )
                goto LABEL_189;
              v111 = pFirst;
              v64->n = pFirst >> 1;
              memcpy((void *)v129, v65->_pbSeg, v111);
              Reader::CheckCharEntity(v73, (StringPtr *)v128);
              p_scanner = &v3->_scanner;
            }
            else
            {
              switch ( v66 )
              {
                case Utf16B:
                  pFirst = (unsigned int)v65->_pbSeg;
                  v67 = v129;
                  p_pBlock = (unsigned int)&v65->_pbCurr[-2 * v65->_lDelta];
                  v68 = (Reader *)pFirst;
                  while ( 2 )
                  {
                    v69 = (signed int)(v67 - (unsigned int)v64->pwh) >> 1;
                    if ( (unsigned int)v68 >= p_pBlock )
                      goto LABEL_136;
                    if ( v69 < v64->n )
                    {
                      v70 = v129;
                      *(_WORD *)v129 = *(unsigned __int8 *)(pFirst + 1)
                                     | (LOBYTE(v68->ISAXXMLReader::IUnknown::__vftable) << 8);
                      v67 = v70 + 2;
                      v68 = (Reader *)(pFirst + 2);
                      v129 = v67;
                      pFirst += 2;
                      continue;
                    }
                    goto LABEL_189;
                  }
                case Ucs2:
                case CodePage:
                  Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v65, v64);
                  goto LABEL_118;
                case Ucs2B:
                  pFirst = (unsigned int)v65->_pbSeg;
                  v88 = v129;
                  p_pBlock = (unsigned int)&v65->_pbCurr[-2 * v65->_lDelta];
                  v68 = (Reader *)pFirst;
                  break;
                case Ucs4:
                  Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v65, v64);
                  goto LABEL_118;
                case Ucs4B:
                  Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v65, v64);
                  goto LABEL_118;
                default:
                  goto LABEL_117;
              }
              while ( 1 )
              {
                v69 = (signed int)(v88 - (unsigned int)v64->pwh) >> 1;
                if ( (unsigned int)v68 >= p_pBlock )
                  break;
                if ( v69 >= v64->n )
                {
LABEL_189:
                  MXRRaiseException(-2147418113);
LABEL_190:
                  MXRRaiseException(-1072894463);
                  JUMPOUT(0x10042550);
                }
                v89 = v129;
                *(_WORD *)v129 = *(unsigned __int8 *)(pFirst + 1)
                               | (LOBYTE(v68->ISAXXMLReader::IUnknown::__vftable) << 8);
                v88 = v89 + 2;
                v68 = (Reader *)(pFirst + 2);
                v129 = v88;
                pFirst += 2;
              }
LABEL_136:
              v64->n = v69;
              Reader::CheckCharEntity(v68, v64);
              p_scanner = &v3->_scanner;
            }
          }
          else
          {
LABEL_117:
            Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v65, v64);
LABEL_118:
            Reader::CheckCharEntity(v72, (StringPtr *)v128);
            p_scanner = &v3->_scanner;
          }
          continue;
        case 11:
          v129 = (unsigned int)_stack<AttValueToken>::push(&v3->_attValueTokens, (signed int)&v132);
          *(_DWORD *)v129 = 11;
          v83 = v3->_scanner._pCharacterSource;
          v84 = v83->_sourceType;
          if ( v84 )
          {
            if ( v84 == Utf16 )
            {
LABEL_143:
              v85 = &v83->_pbCurr[-2 * v83->_lDelta] - v83->_pbSeg;
            }
            else
            {
              switch ( v84 )
              {
                case Utf16B:
                case Ucs2:
                case Ucs2B:
                case CodePage:
                  goto LABEL_143;
                case Ucs4:
                case Ucs4B:
                  v85 = &v83->_pbCurr[-4 * v83->_lDelta] - v83->_pbSeg;
                  break;
                default:
                  goto LABEL_132;
              }
            }
          }
          else
          {
LABEL_132:
            v85 = 2 * (&v83->_pbCurr[-v83->_lDelta] - v83->_pbSeg);
          }
          v86 = v3->_alloc._pBlock;
          v128 = v85;
          pFirst = (unsigned int)v86->pCurr;
          if ( &v86->pLast[-pFirst] < (unsigned __int8 *)v85 )
          {
            v87 = BlockAlloc::RequeueBlock(&v3->_alloc, v85);
            v85 = v128;
            v86 = v87;
            v3->_alloc._pBlock = v87;
            pFirst = (unsigned int)v87->pCurr;
          }
          v86->pCurr += v85;
          v112 = (StringPtr *)(v129 + 4);
          *(_DWORD *)(v129 + 4) = pFirst;
          *(_DWORD *)(v129 + 8) = v85 >> 1;
          Scanner::GetSegmentValue(&v3->_scanner, v112);
          p_scanner = &v3->_scanner;
          continue;
        default:
          v33 = *(_DWORD *)(a3 + 48);
          v34 = v3->_attValueTokens._lSize - v33;
          *(_DWORD *)(a3 + 56) = 0;
          *(_DWORD *)(a3 + 52) = v34;
          v35 = &v3->_attValueTokens._pStack[12 * v33];
          p_pBlock = (unsigned int)v35;
          if ( v34 == 1 )
          {
            if ( *(_DWORD *)v35 == 10 )
            {
LABEL_41:
              v36 = *((_DWORD *)v35 + 1);
              v37 = *((_DWORD *)v35 + 2);
              *(_DWORD *)(a3 + 40) = v36;
              *(_DWORD *)(a3 + 44) = v37;
              goto LABEL_42;
            }
            switch ( *(_DWORD *)v35 )
            {
              case 7:
              case 8:
              case 9:
                goto LABEL_41;
              case 0xB:
                v106 = *((_DWORD *)v35 + 2);
                *(_DWORD *)(a3 + 44) = v106;
                v93 = ULongLongToUInt(2LL * v106, &v125);
                if ( v93 < 0 )
                  goto LABEL_167;
                v120.pwh = (wchar_t *)BlockAlloc::AllocData(&v3->_alloc, v125);
                *(_DWORD *)(a3 + 40) = v120.pwh;
                v120.n = 0;
                Reader::ExpandAttributeValue(v3, (StringPtr *)(a3 + 40), (StringPtr *)(p_pBlock + 4), &v120);
                n = v120.n;
                break;
              default:
                goto LABEL_42;
            }
          }
          else
          {
            v92 = &v35[12 * v34];
            pFirst = (unsigned int)v92;
            if ( v35 < v92 )
            {
              v3 = *(Reader **)(a3 + 44);
              do
              {
                v3 = (Reader *)((char *)v3 + *((_DWORD *)v35 + 2));
                v35 += 12;
                *(_DWORD *)(a3 + 44) = v3;
              }
              while ( v35 < v92 );
            }
            v93 = ULongLongToUInt(2LL * *(unsigned int *)(a3 + 44), &v125);
            if ( v93 < 0 )
            {
LABEL_167:
              MXRRaiseException(v93);
              goto LABEL_168;
            }
            v94 = BlockAlloc::AllocData(p_alloc, v125);
            v95 = *(_DWORD *)(a3 + 52);
            v96 = (_DWORD *)(a3 + 40);
            v128 = (int)v94;
            p_pBlock = a3 + 40;
            v129 = pFirst - 12 * v95;
            v97 = pFirst;
            v3 = v124;
            *(_DWORD *)(a3 + 40) = v94;
            if ( v129 < v97 )
            {
              v98 = (StringPtr *)(a3 + 40);
              v99 = (char *)v129;
              do
              {
                if ( *(_DWORD *)v99 == 10 )
                {
LABEL_156:
                  v100 = (BlockAlloc *)*((_DWORD *)v99 + 1);
                  v101 = (BlockAlloc *)((char *)v100 + 2 * *((_DWORD *)v99 + 2));
                  p_alloc = v101;
                  if ( v100 < v101 )
                  {
                    v102 = (StringPtr *)v128;
                    v103 = v101;
                    do
                    {
                      v104 = (__int16)v100->_pFirst;
                      v100 = (BlockAlloc *)((char *)v100 + 2);
                      LOWORD(v102->pwh) = v104;
                      v102 = (StringPtr *)((char *)v102 + 2);
                    }
                    while ( v100 < v103 );
                    v99 = (char *)v129;
                    v128 = (int)v102;
                    v3 = v124;
                  }
                  v97 = pFirst;
LABEL_161:
                  v94 = (unsigned __int8 *)v128;
                }
                else
                {
                  switch ( *(_DWORD *)v99 )
                  {
                    case 7:
                    case 8:
                    case 9:
                      goto LABEL_156;
                    case 0xB:
                      v107 = v128 - (unsigned int)v98->pwh;
                      v121.pwh = v98->pwh;
                      v121.n = v107 >> 1;
                      Reader::ExpandAttributeValue(v3, v98, (StringPtr *)(v99 + 4), &v121);
                      v99 = (char *)v129;
                      v94 = (unsigned __int8 *)&v121.pwh[v121.n];
                      v97 = pFirst;
                      v128 = (int)v94;
                      break;
                    default:
                      goto LABEL_161;
                  }
                }
                v99 += 12;
                v129 = (unsigned int)v99;
              }
              while ( (unsigned int)v99 < v97 );
              a3 = v127;
              v96 = (_DWORD *)p_pBlock;
            }
            n = (int)&v94[-*v96] >> 1;
          }
          *(_DWORD *)(a3 + 44) = n;
LABEL_42:
          v38 = *(_DWORD *)(a3 + 12);
          if ( v38 )
          {
            if ( v38 != CodeStringPtr::xmlns.n || memcmp(*(const void **)(a3 + 8), CodeStringPtr::xmlns.pwh, 2 * v38) )
            {
LABEL_44:
              *(_DWORD *)(a3 + 60) = 0;
              goto LABEL_2;
            }
            v40 = *(_DWORD *)(a3 + 12);
            v119.pwh = (wchar_t *)(*(_DWORD *)a3 + 2 * v40 + 2);
            v119.n = *(_DWORD *)(a3 + 4) - v40 - 1;
            NamespaceSupport::PushPrefix(&v3->_nsSupport, &v119, (StringPtr *)(a3 + 40));
            *(StringPtr *)(a3 + 16) = CodeStringPtr::xmlnsUri;
            pwh = CodeStringPtr::empty.pwh;
            *(_DWORD *)(a3 + 28) = CodeStringPtr::empty.n;
            *(_DWORD *)(a3 + 24) = pwh;
            *(_DWORD *)(a3 + 60) = 1;
            v113 = *(_OWORD *)a3;
            v114 = *(_OWORD *)(a3 + 16);
            v116 = *(_OWORD *)(a3 + 32);
            v42 = *(_OWORD *)(a3 + 48);
            a3 = *(_DWORD *)(a3 + 64);
            v43 = _stack<Attribute>::push(&v3->_nsAttributes);
            *(_OWORD *)&v43->qname.pwh = v113;
            *(_OWORD *)&v43->uri.pwh = v114;
            *(_OWORD *)&v43->type.pwh = v116;
            *(_OWORD *)&v43->nToken = v42;
            v43->nHashNext = a3;
            --v3->_attributes._lSize;
          }
          else
          {
            v39 = *(_DWORD *)(a3 + 4);
            if ( v39 != CodeStringPtr::xmlns.n || memcmp(*(const void **)a3, CodeStringPtr::xmlns.pwh, 2 * v39) )
              goto LABEL_44;
            NamespaceSupport::PushPrefix(&v3->_nsSupport, &CodeStringPtr::empty, (StringPtr *)(a3 + 40));
            *(StringPtr *)(a3 + 16) = CodeStringPtr::xmlnsUri;
            v79 = CodeStringPtr::empty.pwh;
            *(_DWORD *)(a3 + 28) = CodeStringPtr::empty.n;
            *(_DWORD *)(a3 + 24) = v79;
            *(_DWORD *)(a3 + 60) = 1;
            v118 = *(_OWORD *)a3;
            v117 = *(_OWORD *)(a3 + 16);
            v115 = *(_OWORD *)(a3 + 32);
            v80 = *(_OWORD *)(a3 + 48);
            a3 = *(_DWORD *)(a3 + 64);
            v81 = _stack<Attribute>::push(&v3->_nsAttributes);
            *(_OWORD *)&v81->qname.pwh = v118;
            *(_OWORD *)&v81->uri.pwh = v117;
            *(_OWORD *)&v81->type.pwh = v115;
            *(_OWORD *)&v81->nToken = v80;
            v81->nHashNext = a3;
            --v3->_attributes._lSize;
          }
          break;
      }
      break;
    }
  }
}

```

## disassembly

```asm
0x10041610  mov     edi, edi
0x10041612  push    ebx
0x10041613  mov     ebx, esp
0x10041615  sub     esp, 8
0x10041618  and     esp, 0FFFFFFF8h
0x1004161b  add     esp, 4
0x1004161e  push    ebp
0x1004161f  mov     ebp, [ebx+4]
0x10041622  mov     [esp+0Ch+var_8], ebp
0x10041626  mov     ebp, esp
0x10041628  sub     esp, 78h
0x1004162b  push    esi
0x1004162c  mov     esi, this
0x1004162e  push    edi
0x1004162f  mov     [ebp-18h], esi
0x10041632  mov     dword ptr [esi+80h], 0
0x1004163c  lea     this, [esi+0Ch]; this
0x1004163f  mov     dword ptr [esi+90h], 0
0x10041649  mov     dword ptr [esi+0A0h], 0
0x10041653  push    dword ptr [esi+34h]; op
0x10041656  call    ?DoScan@Scanner@@AAEXW4ScanOp@1@@Z; Scanner::DoScan(Scanner::ScanOp)
0x1004165b  nop     dword ptr [eax+eax+00h]
0x10041660  mov     eax, [esi+20h]
0x10041663  cmp     eax, 6
0x10041666  jnz     short loc_10041671
0x10041668  pop     edi
0x10041669  pop     esi
0x1004166a  mov     esp, ebp
0x1004166c  pop     ebp
0x1004166d  mov     esp, ebx
0x1004166f  pop     ebx
0x10041670  retn
0x10041671  cmp     eax, 5
0x10041674  jz      short loc_10041668
0x10041676  cmp     eax, 0Ch
0x10041679  jnz     loc_10041B2A
0x1004167f  mov     eax, [esi+84h]
0x10041685  cmp     eax, [esi+80h]
0x1004168b  jz      loc_10041CAA
0x10041691  mov     edx, [esi+80h]
0x10041697  mov     this, edx
0x10041699  mov     eax, [esi+7Ch]
0x1004169c  shl     this, 4
0x1004169f  add     this, edx
0x100416a1  lea     edi, [eax+this*4]
0x100416a4  lea     eax, [edx+1]
0x100416a7  mov     [ebp-0Ch], edi
0x100416aa  mov     [esi+80h], eax
0x100416b0  mov     this, [esi+1Ch]
0x100416b3  mov     eax, [this+34h]
0x100416b6  test    eax, eax
0x100416b8  jnz     loc_1004179B
0x100416be  mov     edx, [this+14h]; jumptable 1004239D default case
0x100416c1  sub     edx, [this+20h]
0x100416c4  sub     edx, [this+18h]
0x100416c7  add     edx, edx
0x100416c9  mov     this, [esi+68h]; this
0x100416cc  lea     eax, [esi+64h]
0x100416cf  mov     [ebp-20h], eax
0x100416d2  mov     [ebp-4], edx
0x100416d5  mov     eax, [this+8]
0x100416d8  mov     [ebp-10h], eax
0x100416db  mov     eax, [this+0Ch]
0x100416de  sub     eax, [ebp-10h]
0x100416e1  cmp     eax, edx
0x100416e3  jnb     loc_10041BA3
0x100416e9  nop     dword ptr [eax+00000000h]
0x100416f0  lea     eax, [this+4]
0x100416f3  mov     [ebp-1Ch], eax
0x100416f6  mov     eax, [eax]
0x100416f8  test    eax, eax
0x100416fa  jz      loc_10042132
0x10041700  mov     this, eax
0x10041702  mov     eax, [this+0Ch]
0x10041705  sub     eax, this
0x10041707  sub     eax, 10h
0x1004170a  cmp     eax, edx
0x1004170c  jb      short loc_100416F0
0x1004170e  lea     eax, [this+10h]
0x10041711  mov     [this+8], eax
0x10041714  mov     [esi+68h], this
0x10041717  mov     edx, [this+8]
0x1004171a  mov     [ebp-10h], edx
0x1004171d  mov     eax, [ebp-4]
0x10041720  add     [this+8], eax
0x10041723  shr     eax, 1
0x10041725  mov     [edi], edx
0x10041727  mov     [edi+4], eax
0x1004172a  mov     this, [esi+1Ch]; this
0x1004172d  mov     [ebp-4], eax
0x10041730  mov     eax, [this+34h]
0x10041733  test    eax, eax
0x10041735  jz      short def_10041748; jumptable 10041748 default case
0x10041737  cmp     eax, 1
0x1004173a  jz      loc_10041ABF
0x10041740  sub     eax, 2; switch 6 cases
0x10041743  cmp     eax, 5
0x10041746  ja      short def_10041748; jumptable 10041748 default case
0x10041748  jmp     ds:jpt_10041748[eax*4]; switch jump
0x1004174f  mov     eax, [this+18h]; jumptable 10041748 case 2
0x10041752  mov     [ebp-10h], eax
0x10041755  mov     eax, [this+20h]
0x10041758  mov     this, [this+14h]
0x1004175b  add     eax, eax
0x1004175d  sub     this, eax
0x1004175f  mov     [ebp-1Ch], this
0x10041762  mov     this, [ebp-10h]
0x10041765  mov     eax, edx
0x10041767  sub     eax, [edi]
0x10041769  sar     eax, 1
0x1004176b  cmp     this, [ebp-1Ch]
0x1004176e  jnb     short loc_100417BE
0x10041770  cmp     eax, [edi+4]
0x10041773  jnb     loc_1004253B
0x10041779  mov     eax, [ebp-10h]
0x1004177c  movzx   this, byte ptr [this+1]
0x10041780  movzx   eax, byte ptr [eax]
0x10041783  shl     ax, 8
0x10041787  or      cx, ax
0x1004178a  mov     [edx], cx
0x1004178d  add     edx, 2
0x10041790  mov     this, [ebp-10h]
0x10041793  add     this, 2
0x10041796  mov     [ebp-10h], this
0x10041799  jmp     short loc_10041765
0x1004179b  cmp     eax, 1
0x1004179e  jnz     loc_10042391
0x100417a4  mov     eax, [this+20h]; jumptable 1004239D cases 2-4,7
0x100417a7  mov     edx, [this+14h]
0x100417aa  add     eax, eax
0x100417ac  sub     edx, eax
0x100417ae  sub     edx, [this+18h]
0x100417b1  jmp     loc_100416C9
0x100417b6  push    edi; jumptable 10041748 default case
0x100417b7  call    ?GetSegmentValue@Utf8CharacterSource@@QAEXPAUStringPtr@@@Z; Utf8CharacterSource::GetSegmentValue(StringPtr *)
0x100417bc  jmp     short loc_100417C1
0x100417be  mov     [edi+4], eax
0x100417c1  mov     eax, [edi]
0x100417c3  lea     edx, [esi+0Ch]
0x100417c6  mov     [edi+8], eax
0x100417c9  mov     eax, [edx+44h]
0x100417cc  mov     [edi+0Ch], eax
0x100417cf  mov     eax, ds:?CDATA@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::CDATA ...
0x100417d4  mov     this, ds:?CDATA@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::CDATA ...
0x100417da  mov     [edi+20h], eax
0x100417dd  mov     [edi+24h], this
0x100417e0  mov     eax, [esi+0A0h]
0x100417e6  mov     [edi+30h], eax
0x100417e9  mov     dword ptr [edi+40h], 0
0x100417f0  push    dword ptr [edx+28h]; op
0x100417f3  mov     this, edx; this
0x100417f5  call    ?DoScan@Scanner@@AAEXW4ScanOp@1@@Z; Scanner::DoScan(Scanner::ScanOp)
0x100417fa  mov     eax, [esi+20h]
0x100417fd  cmp     eax, 7
0x10041800  jnz     loc_1004190E
0x10041806  mov     this, [esi+0A4h]
0x1004180c  lea     eax, [esi+9Ch]
0x10041812  cmp     this, [eax+4]
0x10041815  jz      loc_10041BAB
0x1004181b  mov     edx, [eax+4]
0x1004181e  mov     eax, [eax]
0x10041820  lea     this, [edx+edx*2]
0x10041823  lea     this, [eax+this*4]
0x10041826  lea     eax, [edx+1]
0x10041829  mov     [ebp-4], this
0x1004182c  mov     [esi+0A0h], eax
0x10041832  mov     dword ptr [this], 7
0x10041838  mov     edx, [esi+1Ch]
0x1004183b  mov     eax, [edx+34h]
0x1004183e  test    eax, eax
0x10041840  jnz     loc_10041A4D
0x10041846  mov     this, [edx+14h]; jumptable 10042451 default case
0x10041849  sub     this, [edx+20h]
0x1004184c  sub     this, [edx+18h]
0x1004184f  add     this, this; this
0x10041851  mov     edx, [esi+68h]
0x10041854  mov     [ebp-8], this
0x10041857  mov     eax, [edx+8]
0x1004185a  mov     [ebp-10h], eax
0x1004185d  mov     eax, [edx+0Ch]
0x10041860  sub     eax, [ebp-10h]
0x10041863  cmp     eax, this
0x10041865  jb      loc_10041AF8
0x1004186b  add     [edx+8], this
0x1004186e  mov     eax, [ebp-4]
0x10041871  mov     edi, [ebp-4]
0x10041874  add     eax, 4
0x10041877  mov     edx, [ebp-10h]
0x1004187a  shr     this, 1
0x1004187c  mov     [edi+8], this
0x1004187f  mov     edi, [ebp-0Ch]
0x10041882  mov     [eax], edx
0x10041884  mov     this, [esi+1Ch]
0x10041887  mov     [ebp-8], this
0x1004188a  mov     this, [this+34h]
0x1004188d  test    this, this
0x1004188f  jz      def_100418AA; jumptable 100418AA default case
0x10041895  cmp     this, 1
0x10041898  jz      loc_10041A79
0x1004189e  sub     this, 2; switch 6 cases
0x100418a1  cmp     this, 5
0x100418a4  ja      def_100418AA; jumptable 100418AA default case
0x100418aa  jmp     ds:jpt_100418AA[this*4]; switch jump
0x100418b1  mov     this, [ebp-8]; jumptable 100418AA case 2
0x100418b4  mov     eax, [this+18h]
0x100418b7  mov     [ebp-10h], eax
0x100418ba  mov     eax, [this+20h]
0x100418bd  mov     this, [this+14h]
0x100418c0  add     eax, eax
0x100418c2  sub     this, eax
0x100418c4  mov     [ebp-1Ch], this
0x100418c7  mov     eax, [ebp-4]
0x100418ca  mov     edi, edx
0x100418cc  mov     [ebp-8], edx
0x100418cf  sub     edi, [eax+4]
0x100418d2  mov     this, edi
0x100418d4  mov     [ebp-8], edi
0x100418d7  mov     edi, [ebp-1Ch]
0x100418da  sar     this, 1
0x100418dc  cmp     [ebp-10h], edi
0x100418df  mov     edi, [ebp-0Ch]
0x100418e2  jnb     loc_10041B3D
0x100418e8  cmp     this, [eax+8]
0x100418eb  jnb     loc_1004253B
0x100418f1  mov     eax, [ebp-10h]
0x100418f4  movzx   this, byte ptr [eax+1]
0x100418f8  movzx   eax, byte ptr [eax]
0x100418fb  shl     ax, 8
0x100418ff  or      cx, ax
0x10041902  mov     [edx], cx
0x10041905  add     edx, 2
0x10041908  add     dword ptr [ebp-10h], 2
0x1004190c  jmp     short loc_100418C7
0x1004190e  sub     eax, 8; switch 4 cases
0x10041911  cmp     eax, 3
0x10041914  jbe     loc_10041E3E
0x1004191a  mov     eax, [edi+30h]; jumptable 10041E3E default case
0x1004191d  mov     edx, [esi+0A0h]
0x10041923  sub     edx, eax
0x10041925  mov     dword ptr [edi+38h], 0
0x1004192c  mov     [edi+34h], edx
0x1004192f  lea     this, [eax+eax*2]
0x10041932  mov     eax, [esi+9Ch]
0x10041938  lea     this, [eax+this*4]
0x1004193b  mov     [ebp-1Ch], this
0x1004193e  cmp     edx, 1
0x10041941  jnz     loc_100422B0
0x10041947  mov     eax, [this]
0x10041949  cmp     eax, 0Ah
0x1004194c  jnz     loc_1004249E
0x10041952  mov     eax, [this+4]; jumptable 100424AA cases 7-9
0x10041955  mov     this, [this+8]
0x10041958  mov     [edi+28h], eax
0x1004195b  mov     [edi+2Ch], this
0x1004195e  mov     eax, [edi+0Ch]; jumptable 100424AA default case, case 10
0x10041961  test    eax, eax
0x10041963  jnz     short loc_10041980
0x10041965  mov     eax, [edi+4]
0x10041968  cmp     eax, ?xmlns@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::xmlns ...
0x1004196e  jz      loc_1004204A
0x10041974  mov     dword ptr [edi+3Ch], 0
0x1004197b  jmp     loc_10041660
0x10041980  cmp     eax, ?xmlns@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::xmlns ...
0x10041986  jnz     short loc_10041974
0x10041988  add     eax, eax
0x1004198a  push    eax; Size
0x1004198b  push    ?xmlns@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x10041991  push    dword ptr [edi+8]; Buf1
0x10041994  call    _memcmp
0x10041999  add     esp, 0Ch
0x1004199c  test    eax, eax
0x1004199e  jnz     short loc_10041974
0x100419a0  mov     this, [edi+0Ch]
0x100419a3  mov     eax, [edi]
0x100419a5  lea     eax, [eax+this*2]
0x100419a8  add     eax, 2
0x100419ab  mov     [ebp-38h], eax
0x100419ae  mov     eax, [edi+4]
0x100419b1  sub     eax, this
0x100419b3  lea     this, [esi+0C8h]; this
0x100419b9  dec     eax
0x100419ba  mov     [ebp-34h], eax
0x100419bd  lea     eax, [edi+28h]
0x100419c0  push    eax; pUri
0x100419c1  lea     eax, [ebp-38h]
0x100419c4  push    eax; pPrefix
0x100419c5  call    ?PushPrefix@NamespaceSupport@@QAEXPAUStringPtr@@0@Z; NamespaceSupport::PushPrefix(StringPtr *,StringPtr *)
0x100419ca  mov     eax, ds:?xmlnsUri@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::xmlnsUri ...
0x100419cf  mov     this, ds:?xmlnsUri@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::xmlnsUri ...
0x100419d5  mov     [edi+14h], this
0x100419d8  mov     [edi+10h], eax
0x100419db  mov     this, ?empty@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::empty ...
0x100419e1  mov     eax, ?empty@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::empty ...
0x100419e6  mov     [edi+1Ch], this
0x100419e9  lea     this, [esi+8Ch]; this
0x100419ef  mov     [edi+18h], eax
0x100419f2  mov     dword ptr [edi+3Ch], 1
0x100419f9  movups  xmm0, xmmword ptr [edi]
0x100419fc  movups  xmmword ptr [ebp-78h], xmm0
0x10041a00  movups  xmm0, xmmword ptr [edi+10h]
  ... truncated ...
```
