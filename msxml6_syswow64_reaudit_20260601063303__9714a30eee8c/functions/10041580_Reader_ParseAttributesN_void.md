# Reader::ParseAttributesN(void)

- ea: `0x10041580`
- end: `0x100425a0`
- name: `?ParseAttributesN@Reader@@AAEXXZ`
- size: `4128`
- prototype: `void __usercall(Reader *this@<ecx>, int@<ebp>, StringPtr *@<edi>)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1003d9d4`
- `0x100425b0`

## callees

- `0x1003c262`
- `0x1003d5d6`
- `0x1003e180`
- `0x1003e241`
- `0x10040d80`
- `0x100410fe`
- `0x1004112e`
- `0x10041170`
- `0x100412b0`
- `0x10041580`
- `0x10044290`
- `0x1004cc50`
- `0x1004d630`
- `0x1004d985`
- `0x1005dc2e`
- `0x10064d7d`
- `0x10064e17`
- `0x10065e74`
- `0x1006c2c4`
- `0x10164b26`
- `0x1016af0a`
- `0x1016afa1`
- `0x10171298`
- `0x101712a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10041cb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10041d98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10041cb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x10041d98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10041b77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10041d2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10041b77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x10041d2a`

## pseudocode

```c
void __usercall Reader::ParseAttributesN(Reader *this@<ecx>, int a2@<ebp>, StringPtr *a3@<edi>)
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
  wchar_t *v12; // edx
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
  wchar_t *pwh; // eax
  int v34; // edx
  char *v35; // ecx
  wchar_t *v36; // eax
  int v37; // ecx
  int v38; // eax
  int v39; // eax
  int v40; // ecx
  wchar_t *v41; // eax
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
  StringPtr *v94; // eax
  int v95; // ecx
  StringPtr *v96; // edx
  unsigned int v97; // ecx
  StringPtr *v98; // edi
  char *v99; // edx
  BlockAlloc *v100; // ecx
  BlockAlloc *v101; // eax
  StringPtr *v102; // esi
  BlockAlloc *v103; // edx
  __int16 v104; // ax
  int n; // eax
  int v106; // eax
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
  StringPtr *v127; // [esp-Ch] [ebp-18h]
  int v128; // [esp-8h] [ebp-14h]
  unsigned int v129; // [esp-4h] [ebp-10h]
  int v130; // [esp+0h] [ebp-Ch]
  void *v131; // [esp+4h] [ebp-8h]
  void *retaddr; // [esp+Ch] [ebp+0h]

  v130 = a2;
  v131 = retaddr;
  v3 = this;
  v124 = this;
  this->_attributes._lSize = 0;
  this->_nsAttributes._lSize = 0;
  this->_attValueTokens._lSize = 0;
  Scanner::DoScan(&this->_scanner, (Scanner::ScanOp)*(_DWORD *)this->_scanner._scanOp);
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
                a3 = (StringPtr *)&v3->_attributes._pStack[68 * lSize];
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
                  v12 = (wchar_t *)pFirst;
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
                  v12 = (wchar_t *)pBlock[1]._pFirst;
                  pFirst = (unsigned int)v12;
                }
                v13 = v129;
                pBlock[1]._pFirst = (BlockAlloc::Header *)((char *)pBlock[1]._pFirst + v129);
                v13 >>= 1;
                a3->pwh = v12;
                a3->n = v13;
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
                    a3->n = v45 >> 1;
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
                          v17 = v12 - a3->pwh;
                          if ( (unsigned int)v16 >= p_pBlock )
                            goto LABEL_24;
                          if ( v17 < a3->n )
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
                        Utf16CharacterSource::GetSegmentValue((Utf16CharacterSource *)v14, a3);
                        goto LABEL_25;
                      case Ucs2B:
                        pFirst = (unsigned int)v14->_pbSeg;
                        p_pBlock = (unsigned int)&v14->_pbCurr[-2 * v14->_lDelta];
                        v51 = (unsigned __int8 *)pFirst;
                        break;
                      case Ucs4:
                        Ucs4CharacterSource::GetSegmentValue((Ucs4CharacterSource *)v14, a3);
                        goto LABEL_25;
                      case Ucs4B:
                        Ucs4BCharacterSource::GetSegmentValue((Ucs4BCharacterSource *)v14, a3);
                        goto LABEL_25;
                      default:
                        goto LABEL_23;
                    }
                    while ( 1 )
                    {
                      v17 = v12 - a3->pwh;
                      if ( (unsigned int)v51 >= p_pBlock )
                        break;
                      if ( v17 >= a3->n )
                        goto LABEL_189;
                      *v12++ = *(unsigned __int8 *)(pFirst + 1) | (*v51 << 8);
                      v51 = (unsigned __int8 *)(pFirst + 2);
                      pFirst += 2;
                    }
LABEL_24:
                    a3->n = v17;
                  }
                }
                else
                {
LABEL_23:
                  Utf8CharacterSource::GetSegmentValue((Utf8CharacterSource *)v14, a3);
                }
LABEL_25:
                p_scanner = &v3->_scanner;
                a3[1].pwh = a3->pwh;
                a3[1].n = v3->_scanner._nNsPrefix;
                a3[4] = CodeStringPtr::CDATA;
                a3[6].pwh = (wchar_t *)v3->_attValueTokens._lSize;
                a3[8].pwh = 0;
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
        Scanner::DoScan(p_scanner, (Scanner::ScanOp)*(_DWORD *)p_scanner->_scanOp);
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
          v74 = _stack<AttValueToken>::push(&v3->_attValueTokens);
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
          pFirst = (unsigned int)_stack<AttValueToken>::push(&v3->_attValueTokens);
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
                  JUMPOUT(0x100424C0);
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
          v129 = (unsigned int)_stack<AttValueToken>::push(&v3->_attValueTokens);
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
          pwh = a3[6].pwh;
          v34 = v3->_attValueTokens._lSize - (_DWORD)pwh;
          a3[7].pwh = 0;
          a3[6].n = v34;
          v35 = &v3->_attValueTokens._pStack[12 * (_DWORD)pwh];
          p_pBlock = (unsigned int)v35;
          if ( v34 == 1 )
          {
            if ( *(_DWORD *)v35 == 10 )
            {
LABEL_41:
              v36 = (wchar_t *)*((_DWORD *)v35 + 1);
              v37 = *((_DWORD *)v35 + 2);
              a3[5].pwh = v36;
              a3[5].n = v37;
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
                a3[5].n = v106;
                v93 = ULongLongToUInt(2LL * (unsigned int)v106, &v125);
                if ( v93 < 0 )
                  goto LABEL_167;
                v120.pwh = (wchar_t *)BlockAlloc::AllocData(&v3->_alloc, v125);
                a3[5].pwh = v120.pwh;
                v120.n = 0;
                Reader::ExpandAttributeValue(v3, a3 + 5, (StringPtr *)(p_pBlock + 4), &v120);
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
              v3 = (Reader *)a3[5].n;
              do
              {
                v3 = (Reader *)((char *)v3 + *((_DWORD *)v35 + 2));
                v35 += 12;
                a3[5].n = (int)v3;
              }
              while ( v35 < v92 );
            }
            v93 = ULongLongToUInt(2LL * (unsigned int)a3[5].n, &v125);
            if ( v93 < 0 )
            {
LABEL_167:
              MXRRaiseException(v93);
              goto LABEL_168;
            }
            v94 = (StringPtr *)BlockAlloc::AllocData(p_alloc, v125);
            v95 = a3[6].n;
            v96 = a3 + 5;
            v128 = (int)v94;
            p_pBlock = (unsigned int)&a3[5];
            v129 = pFirst - 12 * v95;
            v97 = pFirst;
            v3 = v124;
            a3[5].pwh = (wchar_t *)v94;
            if ( v129 < v97 )
            {
              v98 = a3 + 5;
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
                  v94 = (StringPtr *)v128;
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
                      v94 = (StringPtr *)&v121.pwh[v121.n];
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
              v96 = (StringPtr *)p_pBlock;
            }
            n = ((char *)v94 - (char *)v96->pwh) >> 1;
          }
          a3[5].n = n;
LABEL_42:
          v38 = a3[1].n;
          if ( v38 )
          {
            if ( v38 != CodeStringPtr::xmlns.n || memcmp(a3[1].pwh, CodeStringPtr::xmlns.pwh, 2 * v38) )
            {
LABEL_44:
              a3[7].n = 0;
              goto LABEL_2;
            }
            v40 = a3[1].n;
            v119.pwh = &a3->pwh[v40 + 1];
            v119.n = a3->n - v40 - 1;
            NamespaceSupport::PushPrefix(&v3->_nsSupport, &v119, a3 + 5);
            a3[2] = CodeStringPtr::xmlnsUri;
            v41 = CodeStringPtr::empty.pwh;
            a3[3].n = CodeStringPtr::empty.n;
            a3[3].pwh = v41;
            a3[7].n = 1;
            v113 = *(_OWORD *)&a3->pwh;
            v114 = *(_OWORD *)&a3[2].pwh;
            v116 = *(_OWORD *)&a3[4].pwh;
            v42 = *(_OWORD *)&a3[6].pwh;
            a3 = (StringPtr *)a3[8].pwh;
            v43 = _stack<Attribute>::push(&v3->_nsAttributes);
            *(_OWORD *)&v43->qname.pwh = v113;
            *(_OWORD *)&v43->uri.pwh = v114;
            *(_OWORD *)&v43->type.pwh = v116;
            *(_OWORD *)&v43->nToken = v42;
            v43->nHashNext = (int)a3;
            --v3->_attributes._lSize;
          }
          else
          {
            v39 = a3->n;
            if ( v39 != CodeStringPtr::xmlns.n || memcmp(a3->pwh, CodeStringPtr::xmlns.pwh, 2 * v39) )
              goto LABEL_44;
            NamespaceSupport::PushPrefix(&v3->_nsSupport, &CodeStringPtr::empty, a3 + 5);
            a3[2] = CodeStringPtr::xmlnsUri;
            v79 = CodeStringPtr::empty.pwh;
            a3[3].n = CodeStringPtr::empty.n;
            a3[3].pwh = v79;
            a3[7].n = 1;
            v118 = *(_OWORD *)&a3->pwh;
            v117 = *(_OWORD *)&a3[2].pwh;
            v115 = *(_OWORD *)&a3[4].pwh;
            v80 = *(_OWORD *)&a3[6].pwh;
            a3 = (StringPtr *)a3[8].pwh;
            v81 = _stack<Attribute>::push(&v3->_nsAttributes);
            *(_OWORD *)&v81->qname.pwh = v118;
            *(_OWORD *)&v81->uri.pwh = v117;
            *(_OWORD *)&v81->type.pwh = v115;
            *(_OWORD *)&v81->nToken = v80;
            v81->nHashNext = (int)a3;
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
0x10041580  mov     edi, edi
0x10041582  push    ebx
0x10041583  mov     ebx, esp
0x10041585  sub     esp, 8
0x10041588  and     esp, 0FFFFFFF8h
0x1004158b  add     esp, 4
0x1004158e  push    ebp
0x1004158f  mov     ebp, [ebx+4]
0x10041592  mov     [esp+0Ch+var_8], ebp
0x10041596  mov     ebp, esp
0x10041598  sub     esp, 78h
0x1004159b  push    esi
0x1004159c  mov     esi, this
0x1004159e  push    edi
0x1004159f  mov     [ebp-18h], esi
0x100415a2  mov     dword ptr [esi+80h], 0
0x100415ac  lea     this, [esi+0Ch]; this
0x100415af  mov     dword ptr [esi+90h], 0
0x100415b9  mov     dword ptr [esi+0A0h], 0
0x100415c3  push    dword ptr [esi+34h]; op
0x100415c6  call    ?DoScan@Scanner@@AAEXW4ScanOp@1@@Z; Scanner::DoScan(Scanner::ScanOp)
0x100415cb  nop     dword ptr [eax+eax+00h]
0x100415d0  mov     eax, [esi+20h]
0x100415d3  cmp     eax, 6
0x100415d6  jnz     short loc_100415E1
0x100415d8  pop     edi
0x100415d9  pop     esi
0x100415da  mov     esp, ebp
0x100415dc  pop     ebp
0x100415dd  mov     esp, ebx
0x100415df  pop     ebx
0x100415e0  retn
0x100415e1  cmp     eax, 5
0x100415e4  jz      short loc_100415D8
0x100415e6  cmp     eax, 0Ch
0x100415e9  jnz     loc_10041A9A
0x100415ef  mov     eax, [esi+84h]
0x100415f5  cmp     eax, [esi+80h]
0x100415fb  jz      loc_10041C1A
0x10041601  mov     edx, [esi+80h]
0x10041607  mov     this, edx
0x10041609  mov     eax, [esi+7Ch]
0x1004160c  shl     this, 4
0x1004160f  add     this, edx
0x10041611  lea     edi, [eax+this*4]
0x10041614  lea     eax, [edx+1]
0x10041617  mov     [ebp-0Ch], edi
0x1004161a  mov     [esi+80h], eax
0x10041620  mov     this, [esi+1Ch]
0x10041623  mov     eax, [this+34h]
0x10041626  test    eax, eax
0x10041628  jnz     loc_1004170B
0x1004162e  mov     edx, [this+14h]; jumptable 1004230D default case
0x10041631  sub     edx, [this+20h]
0x10041634  sub     edx, [this+18h]
0x10041637  add     edx, edx
0x10041639  mov     this, [esi+68h]; this
0x1004163c  lea     eax, [esi+64h]
0x1004163f  mov     [ebp-20h], eax
0x10041642  mov     [ebp-4], edx
0x10041645  mov     eax, [this+8]
0x10041648  mov     [ebp-10h], eax
0x1004164b  mov     eax, [this+0Ch]
0x1004164e  sub     eax, [ebp-10h]
0x10041651  cmp     eax, edx
0x10041653  jnb     loc_10041B13
0x10041659  nop     dword ptr [eax+00000000h]
0x10041660  lea     eax, [this+4]
0x10041663  mov     [ebp-1Ch], eax
0x10041666  mov     eax, [eax]
0x10041668  test    eax, eax
0x1004166a  jz      loc_100420A2
0x10041670  mov     this, eax
0x10041672  mov     eax, [this+0Ch]
0x10041675  sub     eax, this
0x10041677  sub     eax, 10h
0x1004167a  cmp     eax, edx
0x1004167c  jb      short loc_10041660
0x1004167e  lea     eax, [this+10h]
0x10041681  mov     [this+8], eax
0x10041684  mov     [esi+68h], this
0x10041687  mov     edx, [this+8]
0x1004168a  mov     [ebp-10h], edx
0x1004168d  mov     eax, [ebp-4]
0x10041690  add     [this+8], eax
0x10041693  shr     eax, 1
0x10041695  mov     [edi], edx
0x10041697  mov     [edi+4], eax
0x1004169a  mov     this, [esi+1Ch]; this
0x1004169d  mov     [ebp-4], eax
0x100416a0  mov     eax, [this+34h]
0x100416a3  test    eax, eax
0x100416a5  jz      short def_100416B8; jumptable 100416B8 default case
0x100416a7  cmp     eax, 1
0x100416aa  jz      loc_10041A2F
0x100416b0  sub     eax, 2; switch 6 cases
0x100416b3  cmp     eax, 5
0x100416b6  ja      short def_100416B8; jumptable 100416B8 default case
0x100416b8  jmp     ds:jpt_100416B8[eax*4]; switch jump
0x100416bf  mov     eax, [this+18h]; jumptable 100416B8 case 2
0x100416c2  mov     [ebp-10h], eax
0x100416c5  mov     eax, [this+20h]
0x100416c8  mov     this, [this+14h]
0x100416cb  add     eax, eax
0x100416cd  sub     this, eax
0x100416cf  mov     [ebp-1Ch], this
0x100416d2  mov     this, [ebp-10h]
0x100416d5  mov     eax, edx
0x100416d7  sub     eax, [edi]
0x100416d9  sar     eax, 1
0x100416db  cmp     this, [ebp-1Ch]
0x100416de  jnb     short loc_1004172E
0x100416e0  cmp     eax, [edi+4]
0x100416e3  jnb     loc_100424AB
0x100416e9  mov     eax, [ebp-10h]
0x100416ec  movzx   this, byte ptr [this+1]
0x100416f0  movzx   eax, byte ptr [eax]
0x100416f3  shl     ax, 8
0x100416f7  or      cx, ax
0x100416fa  mov     [edx], cx
0x100416fd  add     edx, 2
0x10041700  mov     this, [ebp-10h]
0x10041703  add     this, 2
0x10041706  mov     [ebp-10h], this
0x10041709  jmp     short loc_100416D5
0x1004170b  cmp     eax, 1
0x1004170e  jnz     loc_10042301
0x10041714  mov     eax, [this+20h]; jumptable 1004230D cases 2-4,7
0x10041717  mov     edx, [this+14h]
0x1004171a  add     eax, eax
0x1004171c  sub     edx, eax
0x1004171e  sub     edx, [this+18h]
0x10041721  jmp     loc_10041639
0x10041726  push    edi; jumptable 100416B8 default case
0x10041727  call    ?GetSegmentValue@Utf8CharacterSource@@QAEXPAUStringPtr@@@Z; Utf8CharacterSource::GetSegmentValue(StringPtr *)
0x1004172c  jmp     short loc_10041731
0x1004172e  mov     [edi+4], eax
0x10041731  mov     eax, [edi]
0x10041733  lea     edx, [esi+0Ch]
0x10041736  mov     [edi+8], eax
0x10041739  mov     eax, [edx+44h]
0x1004173c  mov     [edi+0Ch], eax
0x1004173f  mov     eax, ds:?CDATA@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::CDATA ...
0x10041744  mov     this, ds:?CDATA@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::CDATA ...
0x1004174a  mov     [edi+20h], eax
0x1004174d  mov     [edi+24h], this
0x10041750  mov     eax, [esi+0A0h]
0x10041756  mov     [edi+30h], eax
0x10041759  mov     dword ptr [edi+40h], 0
0x10041760  push    dword ptr [edx+28h]; op
0x10041763  mov     this, edx; this
0x10041765  call    ?DoScan@Scanner@@AAEXW4ScanOp@1@@Z; Scanner::DoScan(Scanner::ScanOp)
0x1004176a  mov     eax, [esi+20h]
0x1004176d  cmp     eax, 7
0x10041770  jnz     loc_1004187E
0x10041776  mov     this, [esi+0A4h]
0x1004177c  lea     eax, [esi+9Ch]
0x10041782  cmp     this, [eax+4]
0x10041785  jz      loc_10041B1B
0x1004178b  mov     edx, [eax+4]
0x1004178e  mov     eax, [eax]
0x10041790  lea     this, [edx+edx*2]
0x10041793  lea     this, [eax+this*4]
0x10041796  lea     eax, [edx+1]
0x10041799  mov     [ebp-4], this
0x1004179c  mov     [esi+0A0h], eax
0x100417a2  mov     dword ptr [this], 7
0x100417a8  mov     edx, [esi+1Ch]
0x100417ab  mov     eax, [edx+34h]
0x100417ae  test    eax, eax
0x100417b0  jnz     loc_100419BD
0x100417b6  mov     this, [edx+14h]; jumptable 100423C1 default case
0x100417b9  sub     this, [edx+20h]
0x100417bc  sub     this, [edx+18h]
0x100417bf  add     this, this; this
0x100417c1  mov     edx, [esi+68h]
0x100417c4  mov     [ebp-8], this
0x100417c7  mov     eax, [edx+8]
0x100417ca  mov     [ebp-10h], eax
0x100417cd  mov     eax, [edx+0Ch]
0x100417d0  sub     eax, [ebp-10h]
0x100417d3  cmp     eax, this
0x100417d5  jb      loc_10041A68
0x100417db  add     [edx+8], this
0x100417de  mov     eax, [ebp-4]
0x100417e1  mov     edi, [ebp-4]
0x100417e4  add     eax, 4
0x100417e7  mov     edx, [ebp-10h]
0x100417ea  shr     this, 1
0x100417ec  mov     [edi+8], this
0x100417ef  mov     edi, [ebp-0Ch]
0x100417f2  mov     [eax], edx
0x100417f4  mov     this, [esi+1Ch]
0x100417f7  mov     [ebp-8], this
0x100417fa  mov     this, [this+34h]
0x100417fd  test    this, this
0x100417ff  jz      def_1004181A; jumptable 1004181A default case
0x10041805  cmp     this, 1
0x10041808  jz      loc_100419E9
0x1004180e  sub     this, 2; switch 6 cases
0x10041811  cmp     this, 5
0x10041814  ja      def_1004181A; jumptable 1004181A default case
0x1004181a  jmp     ds:jpt_1004181A[this*4]; switch jump
0x10041821  mov     this, [ebp-8]; jumptable 1004181A case 2
0x10041824  mov     eax, [this+18h]
0x10041827  mov     [ebp-10h], eax
0x1004182a  mov     eax, [this+20h]
0x1004182d  mov     this, [this+14h]
0x10041830  add     eax, eax
0x10041832  sub     this, eax
0x10041834  mov     [ebp-1Ch], this
0x10041837  mov     eax, [ebp-4]
0x1004183a  mov     edi, edx
0x1004183c  mov     [ebp-8], edx
0x1004183f  sub     edi, [eax+4]
0x10041842  mov     this, edi
0x10041844  mov     [ebp-8], edi
0x10041847  mov     edi, [ebp-1Ch]
0x1004184a  sar     this, 1
0x1004184c  cmp     [ebp-10h], edi
0x1004184f  mov     edi, [ebp-0Ch]
0x10041852  jnb     loc_10041AAD
0x10041858  cmp     this, [eax+8]
0x1004185b  jnb     loc_100424AB
0x10041861  mov     eax, [ebp-10h]
0x10041864  movzx   this, byte ptr [eax+1]
0x10041868  movzx   eax, byte ptr [eax]
0x1004186b  shl     ax, 8
0x1004186f  or      cx, ax
0x10041872  mov     [edx], cx
0x10041875  add     edx, 2
0x10041878  add     dword ptr [ebp-10h], 2
0x1004187c  jmp     short loc_10041837
0x1004187e  sub     eax, 8; switch 4 cases
0x10041881  cmp     eax, 3
0x10041884  jbe     loc_10041DAE
0x1004188a  mov     eax, [edi+30h]; jumptable 10041DAE default case
0x1004188d  mov     edx, [esi+0A0h]
0x10041893  sub     edx, eax
0x10041895  mov     dword ptr [edi+38h], 0
0x1004189c  mov     [edi+34h], edx
0x1004189f  lea     this, [eax+eax*2]
0x100418a2  mov     eax, [esi+9Ch]
0x100418a8  lea     this, [eax+this*4]
0x100418ab  mov     [ebp-1Ch], this
0x100418ae  cmp     edx, 1
0x100418b1  jnz     loc_10042220
0x100418b7  mov     eax, [this]
0x100418b9  cmp     eax, 0Ah
0x100418bc  jnz     loc_1004240E
0x100418c2  mov     eax, [this+4]; jumptable 1004241A cases 7-9
0x100418c5  mov     this, [this+8]
0x100418c8  mov     [edi+28h], eax
0x100418cb  mov     [edi+2Ch], this
0x100418ce  mov     eax, [edi+0Ch]; jumptable 1004241A default case, case 10
0x100418d1  test    eax, eax
0x100418d3  jnz     short loc_100418F0
0x100418d5  mov     eax, [edi+4]
0x100418d8  cmp     eax, ?xmlns@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::xmlns ...
0x100418de  jz      loc_10041FBA
0x100418e4  mov     dword ptr [edi+3Ch], 0
0x100418eb  jmp     loc_100415D0
0x100418f0  cmp     eax, ?xmlns@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::xmlns ...
0x100418f6  jnz     short loc_100418E4
0x100418f8  add     eax, eax
0x100418fa  push    eax; Size
0x100418fb  push    ?xmlns@CodeStringPtr@@2UStringPtr@@A.pwh; Buf2
0x10041901  push    dword ptr [edi+8]; Buf1
0x10041904  call    _memcmp
0x10041909  add     esp, 0Ch
0x1004190c  test    eax, eax
0x1004190e  jnz     short loc_100418E4
0x10041910  mov     this, [edi+0Ch]
0x10041913  mov     eax, [edi]
0x10041915  lea     eax, [eax+this*2]
0x10041918  add     eax, 2
0x1004191b  mov     [ebp-38h], eax
0x1004191e  mov     eax, [edi+4]
0x10041921  sub     eax, this
0x10041923  lea     this, [esi+0C8h]; this
0x10041929  dec     eax
0x1004192a  mov     [ebp-34h], eax
0x1004192d  lea     eax, [edi+28h]
0x10041930  push    eax; pUri
0x10041931  lea     eax, [ebp-38h]
0x10041934  push    eax; pPrefix
0x10041935  call    ?PushPrefix@NamespaceSupport@@QAEXPAUStringPtr@@0@Z; NamespaceSupport::PushPrefix(StringPtr *,StringPtr *)
0x1004193a  mov     eax, ds:?xmlnsUri@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::xmlnsUri ...
0x1004193f  mov     this, ds:?xmlnsUri@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::xmlnsUri ...
0x10041945  mov     [edi+14h], this
0x10041948  mov     [edi+10h], eax
0x1004194b  mov     this, ?empty@CodeStringPtr@@2UStringPtr@@A.n; StringPtr CodeStringPtr::empty ...
0x10041951  mov     eax, ?empty@CodeStringPtr@@2UStringPtr@@A.pwh; StringPtr CodeStringPtr::empty ...
0x10041956  mov     [edi+1Ch], this
0x10041959  lea     this, [esi+8Ch]; this
0x1004195f  mov     [edi+18h], eax
0x10041962  mov     dword ptr [edi+3Ch], 1
0x10041969  movups  xmm0, xmmword ptr [edi]
0x1004196c  movups  xmmword ptr [ebp-78h], xmm0
0x10041970  movups  xmm0, xmmword ptr [edi+10h]
  ... truncated ...
```
