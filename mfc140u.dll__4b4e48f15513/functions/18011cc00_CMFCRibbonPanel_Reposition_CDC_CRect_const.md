# CMFCRibbonPanel::Reposition(CDC *,CRect const &)

- ea: `0x18011cc00`
- end: `0x18011e370`
- name: `?Reposition@CMFCRibbonPanel@@MEAAXPEAVCDC@@AEBVCRect@@@Z`
- size: `6000`
- prototype: `void __fastcall(CMFCRibbonPanel *this, CDC *pDC, const CRect *rect)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800154f8`
- `0x1800155c4`
- `0x18001c080`
- `0x180023ffc`
- `0x180030880`
- `0x18011cc00`
- `0x18011f510`
- `0x18011f5c0`
- `0x18011f670`
- `0x18011f700`
- `0x18011f7f0`
- `0x180231d70`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d41d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d440`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d5f2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d615`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d68d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d6b0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d6ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d700`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d41d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d440`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d5f2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d615`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d68d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d6b0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d6ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18011d700`
- `USER32!SetRectEmpty` at `0x18011cc48`
- `USER32!SetRectEmpty` at `0x18011cc55`
- `USER32!SetRectEmpty` at `0x18011cc62`
- `USER32!SetRectEmpty` at `0x18011cc48`
- `USER32!SetRectEmpty` at `0x18011cc55`
- `USER32!SetRectEmpty` at `0x18011cc62`
- `USER32!IsRectEmpty` at `0x18011d122`
- `USER32!IsRectEmpty` at `0x18011d1d3`
- `USER32!IsRectEmpty` at `0x18011d273`
- `USER32!IsRectEmpty` at `0x18011d329`
- `USER32!IsRectEmpty` at `0x18011d3bf`
- `USER32!IsRectEmpty` at `0x18011d4ac`
- `USER32!IsRectEmpty` at `0x18011d588`
- `USER32!IsRectEmpty` at `0x18011db29`
- `USER32!IsRectEmpty` at `0x18011de3e`
- `USER32!IsRectEmpty` at `0x18011df70`
- `USER32!IsRectEmpty` at `0x18011d122`
- `USER32!IsRectEmpty` at `0x18011d1d3`
- `USER32!IsRectEmpty` at `0x18011d273`
- `USER32!IsRectEmpty` at `0x18011d329`
- `USER32!IsRectEmpty` at `0x18011d3bf`
- `USER32!IsRectEmpty` at `0x18011d4ac`
- `USER32!IsRectEmpty` at `0x18011d588`
- `USER32!IsRectEmpty` at `0x18011db29`
- `USER32!IsRectEmpty` at `0x18011de3e`
- `USER32!IsRectEmpty` at `0x18011df70`
- `USER32!InflateRect` at `0x18011e2c8`
- `USER32!InflateRect` at `0x18011e2c8`
- `USER32!OffsetRect` at `0x18011de59`
- `USER32!OffsetRect` at `0x18011e0fd`
- `USER32!OffsetRect` at `0x18011e225`
- `USER32!OffsetRect` at `0x18011de59`
- `USER32!OffsetRect` at `0x18011e0fd`
- `USER32!OffsetRect` at `0x18011e225`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=2
void __fastcall CMFCRibbonPanel::Reposition(CMFCRibbonPanel *this, CDC *pDC, const CRect *rect)
{
  CDC *v4; // r14
  int v6; // r15d
  CMFCRibbonCategory *m_pParent; // rax
  __int64 v8; // r8
  int v9; // ebx
  int v10; // ecx
  int v11; // eax
  int v12; // edx
  int v13; // eax
  __int64 m_nSize; // rcx
  __int64 v15; // r14
  CDC *v16; // r12
  CMFCRibbonBaseElement *v17; // rdi
  CMFCRibbonBaseElement_vtbl *v18; // rax
  int v19; // r13d
  int left; // r12d
  __m128i si128; // xmm6
  __int64 v22; // r9
  int v23; // r14d
  int v24; // r15d
  int v25; // r12d
  void *v26; // r13
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rdx
  CMFCRibbonBaseElement *v30; // rdi
  CDC *v31; // r13
  int v32; // r15d
  int v33; // r8d
  int v34; // edx
  int v35; // ecx
  int v36; // eax
  int v37; // ecx
  int v38; // r13d
  int v39; // edx
  int v40; // ecx
  unsigned __int64 v41; // rax
  int v42; // eax
  unsigned int v43; // r8d
  int v44; // eax
  int v45; // r14d
  int v46; // r12d
  __int64 v47; // rdi
  CMFCRibbonBaseElement *v48; // r15
  int v49; // eax
  int v50; // r12d
  __int64 v51; // r15
  CMFCRibbonBaseElement *v52; // rdi
  int v53; // ecx
  __int64 v54; // r12
  __int64 v55; // rdi
  int v56; // r12d
  __int64 i; // rdi
  CMFCRibbonBaseElement *v58; // r15
  __int64 j; // r14
  CMFCRibbonBaseElement *v60; // r15
  _QWORD *v61; // rcx
  _QWORD *v62; // rdi
  __int64 v63; // rcx
  __int64 v64; // r12
  __int64 v65; // r15
  CMFCRibbonBaseElement *v66; // rdi
  __int64 v67; // rdx
  CMFCRibbonBaseElement **m_pData; // r9
  __int64 v69; // rcx
  __int64 v70; // r15
  CMFCRibbonBaseElement *v71; // rdi
  _QWORD *v72; // rcx
  _QWORD *v73; // rdi
  __int64 v74; // rax
  _QWORD *v75; // rcx
  _QWORD *v76; // rdi
  _QWORD *v77; // rcx
  _QWORD *v78; // rbx
  int v79; // edi
  int v80; // eax
  int v81; // ecx
  __int64 v82; // r15
  __int64 v83; // rcx
  __int64 v84; // r12
  CMFCRibbonBaseElement *v85; // rdi
  bool v86; // zf
  BOOL v87; // r14d
  int v88; // eax
  int v89; // r9d
  int v90; // edx
  int v91; // ecx
  __int64 v92; // rcx
  __int64 v93; // r14
  CMFCRibbonBaseElement *v94; // rdi
  __int64 v95; // r8
  int v96; // edx
  int v97; // r14d
  int m_nYMargin; // ecx
  int v99; // eax
  __int64 v100; // r12
  int v101; // r9d
  int v102; // r11d
  __int64 v103; // r13
  int v104; // edx
  __int64 v105; // rcx
  int v106; // r9d
  CMFCRibbonBaseElement *v107; // r10
  int v108; // r15d
  __int64 v109; // rdi
  __int64 v110; // rcx
  CMFCRibbonBaseElement *v111; // r14
  BOOL v112; // eax
  __int64 v113; // rax
  int v114; // r10d
  int v115; // edx
  int v116; // r9d
  int top; // eax
  int m_nFullWidth; // eax
  int v119; // r15d
  __int64 v120; // rdi
  int v121; // r10d
  __int64 v122; // r8
  int right; // ecx
  __int64 v124; // rdx
  int m_nRows; // edx
  int v126; // r8d
  int v127; // r12d
  int v128; // r14d
  __int64 v129; // rcx
  __int64 v130; // rdi
  CMFCRibbonBaseElement *v131; // r15
  int v132; // r13d
  __int64 v133; // rax
  __int64 v134; // rcx
  CMFCRibbonBaseElement *v135; // rcx
  int v136; // r15d
  int v137; // r14d
  int v138; // r13d
  int v139; // edi
  __int64 v140; // rcx
  __int64 v141; // r12
  int v142; // eax
  int v143; // ecx
  int v144; // r11d
  __int64 v145; // r14
  int cx; // r8d
  __int64 v147; // r13
  __int64 v148; // rcx
  CMFCRibbonBaseElement *v149; // r14
  int m_nRow; // eax
  int m_nXMargin; // edx
  int v152; // r8d
  int v153; // ecx
  int v154; // r12d
  int v155; // r15d
  __int64 v156; // rcx
  __int64 v157; // r14
  CMFCRibbonBaseElement *v158; // rdi
  int v159; // eax
  int v160; // r8d
  int v161; // eax
  int v162; // eax
  int v163; // edx
  int v164; // eax
  int v165; // r8d
  int nColumnElements; // [rsp+28h] [rbp-B9h]
  int nColumnElementsa; // [rsp+28h] [rbp-B9h]
  int nColumnElementsb; // [rsp+28h] [rbp-B9h]
  int rValue; // [rsp+2Ch] [rbp-B5h] BYREF
  int v170; // [rsp+30h] [rbp-B1h] BYREF
  int key; // [rsp+34h] [rbp-ADh]
  CSize sizeElem; // [rsp+38h] [rbp-A9h]
  unsigned __int64 v173; // [rsp+40h] [rbp-A1h] BYREF
  int cxFull; // [rsp+48h] [rbp-99h]
  int v175; // [rsp+4Ch] [rbp-95h]
  int nCaptionHeight[2]; // [rsp+50h] [rbp-91h] BYREF
  CDC *v177; // [rsp+58h] [rbp-89h]
  int v178; // [rsp+60h] [rbp-81h]
  int v179; // [rsp+64h] [rbp-7Dh]
  _BYTE mapColumnElements[96]; // [rsp+68h] [rbp-79h] OVERLAPPED BYREF
  RECT m_rect; // [rsp+C8h] [rbp-19h] BYREF
  RECT rc; // [rsp+D8h] [rbp-9h] BYREF

  *(_QWORD *)&mapColumnElements[80] = rect;
  v4 = pDC;
  v177 = pDC;
  SetRectEmpty(&this->m_rectCaption);
  SetRectEmpty(&this->m_rectMenuAreaTop);
  SetRectEmpty(&this->m_rectMenuAreaBottom);
  v6 = 0;
  if ( this->m_pPaletteButton )
  {
    this->ReposPalette(this, v4, rect);
    return;
  }
  if ( this->m_bMenuMode )
  {
    this->RepositionMenu(this, v4, rect);
    return;
  }
  m_pParent = this->m_pParent;
  this->m_btnDefault.m_pParent = m_pParent;
  this->m_btnLaunch.m_pParent = m_pParent;
  this->m_btnLaunch.m_pParentPanel = this;
  this->m_btnDefault.OnCalcTextSize(&this->m_btnDefault, v4);
  *(_DWORD *)&mapColumnElements[4] = this->m_btnDefault.GetRegularSize(&this->m_btnDefault, &mapColumnElements[64], v4)->cx;
  this->m_rect = *rect;
  this->m_btnLaunch.m_rect = 0;
  if ( this->m_bForceCollpapse )
  {
    CMFCRibbonPanel::ShowDefaultButton(this, v4);
    return;
  }
  this->m_btnDefault.m_rect = 0;
  *(_QWORD *)&this->m_nFullWidth = 0;
  this->m_bShowCaption = 1;
  CMFCRibbonPanel::GetCaptionSize(this, (CSize *)&mapColumnElements[64], v4);
  v9 = *(_DWORD *)&mapColumnElements[64];
  if ( !this->m_bTruncateCaption )
  {
    v10 = *(_DWORD *)&mapColumnElements[64];
    if ( rect->right - rect->left > *(int *)&mapColumnElements[64] )
      v10 = rect->right - rect->left;
    this->m_rect.right = this->m_rect.left + v10;
  }
  v11 = rect->bottom - rect->top;
  v12 = rect->right - this->m_nXMargin - rect->left;
  key = v12;
  v13 = v11 - this->m_nYMargin;
  nCaptionHeight[1] = *(_DWORD *)&mapColumnElements[68];
  v175 = v13 - *(_DWORD *)&mapColumnElements[68];
  m_nSize = this->m_arElements.m_nSize;
  if ( m_nSize > 0 )
  {
    v15 = 0;
    v16 = v177;
    do
    {
      if ( v15 < 0 || v15 >= m_nSize )
        AfxThrowInvalidArgException();
      v17 = this->m_arElements.m_pData[v15];
      v17->OnCalcTextSize(v17, v16);
      v18 = v17->__vftable;
      if ( this->m_bFloatyMode )
        v18->SetCompactMode(v17, 1);
      else
        v18->SetInitialMode(v17, 0);
      v17->m_bFloatyMode = this->m_bFloatyMode;
      v17->m_nRow = -1;
      ++v6;
      ++v15;
      m_nSize = this->m_arElements.m_nSize;
    }
    while ( v6 < m_nSize );
    v4 = v16;
    v12 = key;
  }
  v19 = 0;
  left = 0;
  if ( this->m_bAlignByColumn && !this->m_bFloatyMode )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
LABEL_24:
    v22 = 3;
    while ( 1 )
    {
LABEL_25:
      v23 = 0;
      v24 = 0;
      v25 = 0;
      *(_QWORD *)&mapColumnElements[8] = CMap<int,int,int,int>::`vftable';
      v26 = 0;
      *(_QWORD *)&mapColumnElements[16] = 0;
      *(_DWORD *)&mapColumnElements[24] = 17;
      *(_OWORD *)&mapColumnElements[32] = 0;
      *(__m128i *)&mapColumnElements[48] = si128;
      v170 = 0;
      v27 = 0;
      *(_QWORD *)&rc.left = 0;
      v28 = this->m_arElements.m_nSize;
      v29 = v28;
      if ( v28 > 0 )
      {
        while ( 1 )
        {
          if ( v27 < 0 || v27 >= v29 )
            AfxThrowInvalidArgException();
          v30 = this->m_arElements.m_pData[v27];
          v31 = v177;
          ((void (__fastcall *)(CMFCRibbonBaseElement *, unsigned __int64 *, CDC *, __int64))v30->GetSize)(
            v30,
            &v173,
            v177,
            v22);
          if ( v173 )
          {
            if ( v30->IsSeparator(v30) )
            {
              v32 = v23 + v24;
              v33 = this->m_nYMargin + *(_DWORD *)(*(_QWORD *)&mapColumnElements[80] + 4LL);
              v34 = v32 + **(_DWORD **)&mapColumnElements[80] + this->m_nXMargin;
              v35 = v34 + v173;
              v30->m_rect.left = v34;
              v30->m_rect.top = v33;
              v30->m_rect.right = v35;
              v30->m_rect.bottom = v33 + v175;
              v24 = v173 + this->m_nXMargin + v32;
              v25 = 0;
              v23 = 0;
            }
            else
            {
              v36 = v30->IsWholeRowHeight(v30);
              v37 = HIDWORD(v173);
              if ( v36 )
                v37 = v175;
              HIDWORD(v173) = v37;
              if ( v37 + v25 > v175 )
              {
                if ( !v25 )
                {
                  CMFCRibbonPanel::ShowDefaultButton(this, v31);
                  v26 = *(void **)&mapColumnElements[16];
                  goto LABEL_140;
                }
                v24 += v23;
                v25 = 0;
                v23 = 0;
              }
              v38 = v24 + **(_DWORD **)&mapColumnElements[80] + this->m_nXMargin;
              v39 = v25 + this->m_nYMargin + *(_DWORD *)(*(_QWORD *)&mapColumnElements[80] + 4LL);
              v40 = v38 + v173;
              v41 = HIDWORD(v173);
              v30->m_rect.left = v38;
              v30->m_rect.top = v39;
              v30->m_rect.right = v40;
              v30->m_rect.bottom = v39 + v41;
              rValue = 1;
              v42 = CMap<unsigned int,unsigned int,int,int>::Lookup(
                      (CMap<int,int,int,int> *)&mapColumnElements[8],
                      v38,
                      &rValue);
              v43 = rValue;
              if ( v42 )
                v43 = rValue + 1;
              CMap<int,int,int,int>::SetAt((CMap<int,int,unsigned int,unsigned int> *)&mapColumnElements[8], v38, v43);
              v44 = v173;
              if ( v23 > (int)v173 )
                v44 = v23;
              v23 = v44;
              v25 += HIDWORD(v173);
            }
          }
          else
          {
            v30->m_rect = 0;
          }
          v22 = (unsigned int)(v170 + 1);
          v170 = v22;
          v27 = ++*(_QWORD *)&rc.left;
          v28 = this->m_arElements.m_nSize;
          v29 = v28;
          if ( (int)v22 >= v28 )
          {
            v26 = *(void **)&mapColumnElements[16];
            break;
          }
        }
      }
      if ( v23 + v24 <= key )
      {
        this->m_nFullWidth = v23 + v24;
        *(_QWORD *)&mapColumnElements[8] = CMap<int,int,int,int>::`vftable';
        CMapWordToOb::RemoveAll((CMapWordToPtr *)&mapColumnElements[8]);
        goto LABEL_259;
      }
      if ( !v23 )
        break;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      if ( v28 > 0 )
      {
        while ( !v45 )
        {
          if ( v47 < 0 || v47 >= v29 )
            goto LABEL_326;
          v48 = this->m_arElements.m_pData[v47];
          *(CRect *)&mapColumnElements[64] = v48->m_rect;
          if ( !IsRectEmpty((const RECT *)&mapColumnElements[64]) && v48->CanBeStretchedHorizontally(v48) )
          {
            v48->StretchHorizontally(v48);
            v45 = 1;
          }
          ++v46;
          ++v47;
          v29 = this->m_arElements.m_nSize;
          if ( v46 >= v29 )
          {
            if ( v45 )
              break;
            goto LABEL_55;
          }
        }
LABEL_76:
        *(_QWORD *)&mapColumnElements[8] = CMap<int,int,int,int>::`vftable';
        CMapWordToOb::RemoveAll((CMapWordToPtr *)&mapColumnElements[8]);
        goto LABEL_24;
      }
LABEL_55:
      rValue = 0;
      v49 = this->m_arElements.m_nSize;
      v50 = v49;
      if ( v49 > 3 )
        v50 = 3;
      v170 = v50;
      v51 = v49 - 1;
      while ( v51 >= 0 )
      {
        if ( v51 >= this->m_arElements.m_nSize )
          goto LABEL_326;
        v52 = this->m_arElements.m_pData[v51];
        *(CRect *)&mapColumnElements[64] = v52->m_rect;
        if ( !IsRectEmpty((const RECT *)&mapColumnElements[64]) )
        {
          if ( v52->m_bCompactMode || v52->m_bIntermediateMode || !v52->CanBeCompacted(v52) )
          {
            rValue = 0;
          }
          else
          {
            v53 = rValue + 1;
            rValue = v53;
            if ( v53 == v50 )
            {
              v45 = 1;
              v54 = 0;
              *(_QWORD *)&m_rect.left = v53;
              if ( v53 > 0 )
              {
                v55 = v51;
                while ( v55 >= 0 && v55 < this->m_arElements.m_nSize )
                {
                  *(_QWORD *)&mapColumnElements[64] = this->m_arElements.m_pData[v55];
                  rc = *(RECT *)(*(_QWORD *)&mapColumnElements[64] + 200LL);
                  if ( IsRectEmpty(&rc) )
                  {
                    ++v54;
                    ++v55;
                  }
                  else
                  {
                    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&mapColumnElements[64] + 488LL))(
                      *(_QWORD *)&mapColumnElements[64],
                      1);
                  }
                  ++v54;
                  ++v55;
                  if ( v54 >= *(__int64 *)&m_rect.left )
                    goto LABEL_73;
                }
LABEL_326:
                AfxThrowInvalidArgException();
              }
LABEL_73:
              v50 = v170;
            }
          }
        }
        --v51;
        if ( v45 )
          break;
      }
      if ( v45 )
        goto LABEL_76;
      v56 = 0;
      nColumnElements = -1;
      for ( i = LODWORD(this->m_arElements.m_nSize) - 1; i >= 0; --i )
      {
        if ( i >= this->m_arElements.m_nSize )
          goto LABEL_326;
        v58 = this->m_arElements.m_pData[i];
        *(CRect *)&mapColumnElements[64] = v58->m_rect;
        if ( !IsRectEmpty((const RECT *)&mapColumnElements[64]) )
        {
          if ( (nColumnElements == -1 || v58->m_rect.left == nColumnElements)
            && (nColumnElements = _mm_cvtsi128_si32((__m128i)v58->m_rect), v58->m_bIntermediateMode)
            && v58->HasCompactMode(v58) )
          {
            if ( ++v56 == 3 )
            {
              for ( j = 0; j < 3; ++j )
              {
                if ( i < 0 || i >= this->m_arElements.m_nSize )
                  goto LABEL_326;
                v60 = this->m_arElements.m_pData[i];
                *(CRect *)&mapColumnElements[64] = v60->m_rect;
                if ( IsRectEmpty((const RECT *)&mapColumnElements[64]) )
                {
                  ++j;
                  ++i;
                }
                else
                {
                  v60->SetCompactMode(v60, 1);
                }
                ++i;
              }
              if ( v26 )
                free(v26);
              v61 = *(_QWORD **)&mapColumnElements[48];
              v22 = 3;
              if ( *(_QWORD *)&mapColumnElements[48] )
              {
                do
                {
                  v62 = (_QWORD *)*v61;
                  free(v61);
                  v61 = v62;
                }
                while ( v62 );
                goto LABEL_24;
              }
              goto LABEL_25;
            }
          }
          else
          {
            v56 = 0;
            nColumnElements = -1;
          }
        }
      }
      v63 = this->m_arElements.m_nSize;
      v64 = v63 >= 3;
      rValue = v63 >= 3;
      if ( v64 >= v63 )
        goto LABEL_114;
      v65 = v63 >= 3;
      *(_QWORD *)&mapColumnElements[64] = v64 + 1;
      while ( 1 )
      {
        if ( v65 < 0 || v65 >= v63 )
          goto LABEL_326;
        v66 = this->m_arElements.m_pData[v65];
        m_rect = (RECT)v66->m_rect;
        if ( !IsRectEmpty(&m_rect) && !v66->m_bCompactMode && !v66->m_bIntermediateMode )
        {
          if ( v66->CanBeCompacted(v66) )
          {
            v67 = this->m_arElements.m_nSize;
            if ( rValue < v67 - 1 )
            {
              if ( *(__int64 *)&mapColumnElements[64] < 0 || *(__int64 *)&mapColumnElements[64] >= v67 )
                goto LABEL_326;
              m_pData = this->m_arElements.m_pData;
              if ( m_pData[v65 + 1]->m_bIntermediateMode )
                break;
            }
          }
        }
        ++rValue;
        ++v65;
        ++*(_QWORD *)&mapColumnElements[64];
        v63 = this->m_arElements.m_nSize;
        if ( rValue >= v63 )
          goto LABEL_114;
      }
      v170 = 0;
      v74 = rValue + 1LL;
      if ( v74 < 0 || v74 >= v67 )
        goto LABEL_326;
      if ( CMap<unsigned int,unsigned int,int,int>::Lookup(
             (CMap<int,int,int,int> *)&mapColumnElements[8],
             m_pData[v74]->m_rect.left,
             &v170)
        && (v22 = 3, v170 < 3) )
      {
        v66->m_bIntermediateMode = 1;
        v66->m_bCompactMode = 0;
        if ( v26 )
        {
          free(v26);
          v22 = 3;
        }
        v75 = *(_QWORD **)&mapColumnElements[48];
        if ( *(_QWORD *)&mapColumnElements[48] )
        {
          do
          {
            v76 = (_QWORD *)*v75;
            free(v75);
            v75 = v76;
          }
          while ( v76 );
          goto LABEL_24;
        }
      }
      else
      {
LABEL_114:
        v69 = this->m_arElements.m_nSize;
        if ( v64 >= v69 )
          break;
        v70 = v64;
        do
        {
          if ( v70 < 0 || v70 >= v69 )
            goto LABEL_326;
          v71 = this->m_arElements.m_pData[v70];
          *(CRect *)&mapColumnElements[64] = v71->m_rect;
          if ( !IsRectEmpty((const RECT *)&mapColumnElements[64])
            && v71->m_bIntermediateMode
            && v71->HasCompactMode(v71) )
          {
            v71->m_bIntermediateMode = 0;
            v71->m_bCompactMode = 1;
            v45 = 1;
          }
          LODWORD(v64) = v64 + 1;
          ++v70;
          v69 = this->m_arElements.m_nSize;
        }
        while ( (int)v64 < v69 );
        if ( !v45 )
          break;
        if ( v26 )
          free(v26);
        v72 = *(_QWORD **)&mapColumnElements[48];
        v22 = 3;
        if ( *(_QWORD *)&mapColumnElements[48] )
        {
          do
          {
            v73 = (_QWORD *)*v72;
            free(v72);
            v72 = v73;
          }
          while ( v73 );
          goto LABEL_24;
        }
      }
    }
    CMFCRibbonPanel::ShowDefaultButton(this, v177);
LABEL_140:
    if ( v26 )
      free(v26);
    v77 = *(_QWORD **)&mapColumnElements[48];
    if ( *(_QWORD *)&mapColumnElements[48] )
    {
      do
      {
        v78 = (_QWORD *)*v77;
        free(v77);
        v77 = v78;
      }
      while ( v78 );
    }
    return;
  }
  cxFull = 0;
  v79 = 0;
  nColumnElementsa = 0;
  v170 = 0;
  rValue = this->m_rect.bottom;
  nCaptionHeight[0] = 0;
  if ( !this->m_bIsCalcWidth )
  {
    v80 = CMap<unsigned int,unsigned int,int,int>::Lookup(&this->m_mapNonOptWidths, v12, nCaptionHeight);
    v81 = key;
    if ( v80 )
      v81 = nCaptionHeight[0];
    key = v81;
  }
  *(_QWORD *)&mapColumnElements[8] = CArray<int,int>::`vftable';
  memset(&mapColumnElements[16], 0, 32);
  v82 = 0;
  if ( !this->m_bFloatyMode )
  {
    *(_DWORD *)mapColumnElements = 0;
    LODWORD(v173) = 0;
    v179 = 0;
    v178 = 0;
    sizeElem.cx = 0;
    v83 = this->m_arElements.m_nSize;
    if ( v83 > 0 )
    {
      v84 = 0;
      rc.left = 0;
      do
      {
        if ( v84 < 0 || v84 >= v83 )
          AfxThrowInvalidArgException();
        v85 = this->m_arElements.m_pData[v84];
        v85->GetSize(v85, (CSize *)&mapColumnElements[64], v4);
        if ( !v85->HasLargeMode(v85)
          || v85->m_bCompactMode
          || (v86 = v85->m_bIntermediateMode == 0, nCaptionHeight[0] = 1, !v86) )
        {
          nCaptionHeight[0] = 0;
        }
        v87 = 0;
        if ( v85->IsSeparator(v85) && *(_DWORD *)mapColumnElements )
          v87 = v173 == 0;
        v88 = nCaptionHeight[0];
        if ( nCaptionHeight[0] || v87 )
        {
          if ( v85->IsSeparator(v85) )
          {
            if ( v179 || v178 )
              *(_DWORD *)&mapColumnElements[68] = v178;
          }
          else
          {
            v173 = *(_QWORD *)&mapColumnElements[64];
            v178 = *(_DWORD *)&mapColumnElements[68];
            v179 = *(_DWORD *)&mapColumnElements[64];
          }
          v89 = v175;
          if ( rValue == 0x7FFF )
            v89 = *(_DWORD *)&mapColumnElements[68];
          v8 = *(unsigned int *)(*(_QWORD *)&mapColumnElements[80] + 4LL);
          v90 = v19 + **(_DWORD **)&mapColumnElements[80] + this->m_nXMargin;
          v91 = v90 + *(_DWORD *)&mapColumnElements[64];
          v85->m_rect.left = v90;
          v85->m_rect.top = v8;
          v85->m_rect.right = v91;
          v85->m_rect.bottom = v8 + v89;
          v85->m_nRow = 999;
          v19 += *(_DWORD *)&mapColumnElements[64] + this->m_nXMargin;
          v170 = v19;
          v88 = nCaptionHeight[0];
        }
        *(_DWORD *)mapColumnElements = v88;
        LODWORD(v173) = v87;
        ++sizeElem.cx;
        ++v84;
        v83 = this->m_arElements.m_nSize;
        v4 = v177;
      }
      while ( sizeElem.cx < v83 );
      left = rc.left;
      v79 = 0;
    }
  }
  sizeElem.cx = 0;
  v92 = this->m_arElements.m_nSize;
  if ( v92 > 0 )
  {
    v93 = 0;
    while ( 1 )
    {
      if ( v93 < 0 || v93 >= v92 )
LABEL_328:
        AfxThrowInvalidArgException();
      v94 = this->m_arElements.m_pData[v93];
      v94->GetSize(v94, (CSize *)&m_rect, v177);
      if ( !m_rect.left && !m_rect.top )
        break;
      if ( v94->m_nRow != -1 )
        goto LABEL_181;
      if ( v94->IsSeparator(v94) )
        break;
      v113 = *(_QWORD *)&m_rect.left;
      if ( v19 + m_rect.left + this->m_nXMargin - 1 <= key )
      {
        v114 = cxFull;
      }
      else
      {
        if ( v19 == v170 )
          goto LABEL_220;
        left += cxFull;
        if ( this->m_bFloatyMode )
          left += this->m_nYMargin;
        if ( v82 < 0 )
          goto LABEL_328;
        CArray<int,int const &>::SetSize((CArray<int,int const &> *)&mapColumnElements[8], v82 + 1, v8);
        *(_DWORD *)(*(_QWORD *)&mapColumnElements[16] + 4 * v82) = v19;
        ++this->m_nRows;
        v19 = v170;
        v114 = 0;
        v82 = *(_QWORD *)&mapColumnElements[24];
        v113 = *(_QWORD *)&m_rect.left;
      }
      if ( left + m_rect.top > v175 )
      {
LABEL_220:
        CMFCRibbonPanel::ShowDefaultButton(this, v177);
        CArray<int,int>::~CArray<int,int>((CArray<int,int> *)&mapColumnElements[8]);
        return;
      }
      v8 = (unsigned int)(left + this->m_nYMargin + *(_DWORD *)(*(_QWORD *)&mapColumnElements[80] + 4LL));
      v115 = v19 + **(_DWORD **)&mapColumnElements[80] + this->m_nXMargin;
      v116 = HIDWORD(v113) + v8;
      v94->m_rect.left = v115;
      v94->m_rect.top = v8;
      v94->m_rect.right = v115 + v113;
      v94->m_rect.bottom = HIDWORD(v113) + v8;
      v94->m_nRow = this->m_nRows;
      top = m_rect.top;
      if ( v114 > m_rect.top )
        top = v114;
      cxFull = top;
      v19 += m_rect.left + this->m_nXMargin - 1;
      m_nFullWidth = this->m_nFullWidth;
      if ( m_nFullWidth <= v19 - 1 )
        m_nFullWidth = v19 - 1;
      this->m_nFullWidth = m_nFullWidth;
      if ( nColumnElementsa > v116 )
        v116 = nColumnElementsa;
      v79 = v116;
      nColumnElementsa = v116;
LABEL_182:
      ++sizeElem.cx;
      ++v93;
      v92 = this->m_arElements.m_nSize;
      if ( sizeElem.cx >= v92 )
        goto LABEL_183;
    }
    v94->m_rect = 0;
LABEL_181:
    v79 = nColumnElementsa;
    goto LABEL_182;
  }
LABEL_183:
  if ( v82 < 0 )
    goto LABEL_323;
  CArray<int,int const &>::SetSize((CArray<int,int const &> *)&mapColumnElements[8], v82 + 1, v8);
  v95 = *(_QWORD *)&mapColumnElements[16];
  *(_DWORD *)(*(_QWORD *)&mapColumnElements[16] + 4 * v82) = v19;
  v96 = this->m_nRows + 1;
  this->m_nRows = v96;
  v97 = rValue;
  if ( rValue == 0x7FFF )
  {
    m_nYMargin = this->m_nYMargin;
    v99 = nCaptionHeight[1] + m_nYMargin + v79;
    this->m_rect.bottom = v99;
    v175 = v99 - this->m_rect.top - m_nYMargin - nCaptionHeight[1];
  }
  if ( !this->m_bIsQATPopup && v96 > 1 )
  {
    LODWORD(v173) = 0;
    v100 = *(_QWORD *)&mapColumnElements[24];
    while ( 1 )
    {
      v101 = 0;
      sizeElem.cx = 0;
      v102 = -1;
      key = -1;
      v103 = -1;
      v177 = (CDC *)-1LL;
      v104 = 0;
      v105 = 0;
      if ( v100 <= 0 )
        break;
      do
      {
        if ( v105 < 0 || v105 >= v100 )
          goto LABEL_323;
        if ( *(_DWORD *)(v95 + 4 * v105) > v101 )
        {
          v101 = *(_DWORD *)(v95 + 4 * v105);
          sizeElem.cx = v101;
          v102 = v104;
          key = v104;
          v103 = v105;
          v177 = (CDC *)v105;
        }
        ++v104;
        ++v105;
      }
      while ( v104 < v100 );
      if ( v103 < 0 )
        break;
      v106 = 9999;
      nColumnElementsb = 9999;
      v107 = 0;
      *(_QWORD *)&mapColumnElements[80] = 0;
      v108 = 0;
      v109 = 0;
      v110 = this->m_arElements.m_nSize;
      if ( v110 <= 0 )
        break;
      do
      {
        if ( v109 < 0 || v109 >= v110 )
          goto LABEL_323;
        v111 = this->m_arElements.m_pData[v109];
        if ( v111->m_nRow == v102 )
        {
          *(CRect *)&mapColumnElements[64] = v111->m_rect;
          v112 = IsRectEmpty((const RECT *)&mapColumnElements[64]);
          v106 = nColumnElementsb;
          v102 = key;
          if ( v112 || *(_DWORD *)&mapColumnElements[72] - *(_DWORD *)&mapColumnElements[64] >= nColumnElementsb )
          {
            v107 = *(CMFCRibbonBaseElement **)&mapColumnElements[80];
          }
          else
          {
            v106 = *(_DWORD *)&mapColumnElements[72] - *(_DWORD *)&mapColumnElements[64];
            nColumnElementsb = *(_DWORD *)&mapColumnElements[72] - *(_DWORD *)&mapColumnElements[64];
            v107 = v111;
            *(_QWORD *)&mapColumnElements[80] = v111;
          }
        }
        ++v108;
        ++v109;
        v110 = this->m_arElements.m_nSize;
      }
      while ( v108 < v110 );
      if ( !v107 )
        break;
      v119 = v102 + 1;
      v120 = v103 + 1;
      if ( v102 + 1 >= v100 )
        break;
      while ( 1 )
      {
        if ( v120 < 0 || v120 >= v100 )
          goto LABEL_323;
        if ( v106 + *(_DWORD *)(*(_QWORD *)&mapColumnElements[16] + 4 * v120) < sizeElem.cx )
          break;
        ++v119;
        ++v120;
        if ( v119 >= v100 )
          goto LABEL_229;
      }
      v144 = 0;
      LODWORD(v173) = 0;
      LODWORD(v145) = 0;
      *(_QWORD *)&mapColumnElements[64] = 0;
      cx = 0;
      sizeElem.cx = 0;
      v147 = 0;
      v148 = this->m_arElements.m_nSize;
      if ( v148 > 0 )
      {
        while ( v147 >= 0 && v147 < v148 )
        {
          v149 = this->m_arElements.m_pData[v147];
          m_nRow = v149->m_nRow;
          if ( m_nRow == v119 )
          {
            m_nXMargin = this->m_nXMargin;
            if ( m_nXMargin + v149->m_rect.right > v144 )
              LODWORD(v173) = m_nXMargin + v149->m_rect.right;
            v145 = HIDWORD(*(_QWORD *)&v149->m_rect.left);
            *(_QWORD *)&mapColumnElements[64] = v145;
          }
          else
          {
            if ( m_nRow == key )
            {
              rc = (RECT)v149->m_rect;
              if ( _mm_cvtsi128_si32((__m128i)rc) > v107->m_rect.left )
              {
                OffsetRect(&rc, -(v106 + this->m_nXMargin), 0);
                v149->m_rect = (CRect)rc;
                v106 = nColumnElementsb;
                v107 = *(CMFCRibbonBaseElement **)&mapColumnElements[80];
                cx = sizeElem.cx;
              }
            }
            LODWORD(v145) = *(_DWORD *)&mapColumnElements[64];
          }
          sizeElem.cx = ++cx;
          ++v147;
          v148 = this->m_arElements.m_nSize;
          v144 = v173;
          if ( cx >= v148 )
            goto LABEL_297;
        }
LABEL_323:
        AfxThrowInvalidArgException();
      }
LABEL_297:
      v152 = HIDWORD(*(_QWORD *)&v107->m_rect.right) - HIDWORD(*(_QWORD *)&v107->m_rect.left);
      v153 = *(_QWORD *)&v107->m_rect.right - *(_QWORD *)&v107->m_rect.left;
      m_rect.left = v144;
      m_rect.right = v144 + v153;
      m_rect.top = v145;
      m_rect.bottom = v152 + v145;
      v107->m_rect = (CRect)m_rect;
      v107->m_nRow = v119;
      v95 = *(_QWORD *)&mapColumnElements[16];
      *(_DWORD *)(*(_QWORD *)&mapColumnElements[16] + 4 * v120) += v106;
      if ( (__int64)v177 >= v100 )
        goto LABEL_323;
      *(_DWORD *)(v95 + 4LL * (_QWORD)v177) -= v106;
      LODWORD(v173) = 1;
    }
LABEL_229:
    if ( (_DWORD)v173 )
    {
      this->m_nFullWidth = 0;
      v121 = 0;
      v122 = this->m_arElements.m_nSize;
      right = 0;
      if ( v122 > 0 )
      {
        v124 = 0;
        while ( v124 >= 0 && v124 < v122 )
        {
          if ( right <= this->m_arElements.m_pData[v124]->m_rect.right )
            right = this->m_arElements.m_pData[v124]->m_rect.right;
          this->m_nFullWidth = right;
          ++v121;
          ++v124;
          if ( v121 >= v122 )
            goto LABEL_237;
        }
        goto LABEL_323;
      }
LABEL_237:
      this->m_nFullWidth = right - this->m_rect.left - this->m_nXMargin;
    }
    v97 = rValue;
  }
  if ( v97 != 0x7FFF && !this->m_bFloatyMode )
  {
    m_nRows = this->m_nRows;
    v126 = cxFull;
    if ( m_nRows <= 1 )
      goto LABEL_252;
    v127 = (v175 - cxFull * m_nRows) / (m_nRows + 1);
    if ( v127 <= 0 )
      goto LABEL_252;
    v128 = 0;
    v129 = this->m_arElements.m_nSize;
    if ( v129 <= 0 )
      goto LABEL_252;
    v130 = 0;
    do
    {
      if ( v130 < 0 || v130 >= v129 )
        AfxThrowInvalidArgException();
      v131 = this->m_arElements.m_pData[v130];
      v132 = v131->m_nRow;
      *(CRect *)&mapColumnElements[80] = v131->m_rect;
      if ( v132 != 999 && !IsRectEmpty((const RECT *)&mapColumnElements[80]) )
      {
        OffsetRect((LPRECT)&mapColumnElements[80], 0, v127 * (v132 + 1) - v132);
        v131->m_rect = *(CRect *)&mapColumnElements[80];
      }
      ++v128;
      ++v130;
      v129 = this->m_arElements.m_nSize;
    }
    while ( v128 < v129 );
  }
  v126 = cxFull;
LABEL_252:
  if ( this->m_bIsQATPopup )
  {
    if ( v126 > 0 )
    {
      v133 = this->m_arElements.m_nSize;
      if ( v133 > 0 )
      {
        v134 = v133 - 1;
        if ( v133 - 1 < 0 || v134 >= v133 )
          goto LABEL_323;
        v135 = this->m_arElements.m_pData[v134];
        *(CRect *)&mapColumnElements[80] = v135->m_rect;
        *(_DWORD *)&mapColumnElements[92] = v126 + *(_DWORD *)&mapColumnElements[84];
        v135->m_rect = *(CRect *)&mapColumnElements[80];
      }
    }
  }
  CArray<int,int>::~CArray<int,int>((CArray<int,int> *)&mapColumnElements[8]);
LABEL_259:
  if ( !this->m_bFloatyMode )
  {
    if ( !this->m_bAlignByColumn )
      goto LABEL_299;
    if ( this->m_bCenterColumnVert || this->m_bJustifyColumns )
    {
      v136 = -1;
      v137 = -1;
      v138 = -1;
      v139 = 0;
      v140 = this->m_arElements.m_nSize;
      if ( v140 > 0 )
      {
        v141 = 0;
        do
        {
          if ( v141 < 0 || v141 >= v140 )
            AfxThrowInvalidArgException();
          *(CRect *)&mapColumnElements[80] = this->m_arElements.m_pData[v141]->m_rect;
          if ( !IsRectEmpty((const RECT *)&mapColumnElements[80]) )
          {
            v142 = *(_DWORD *)&mapColumnElements[80];
            if ( v136 == -1 )
            {
              v136 = v139;
              v137 = v139;
              v138 = *(_DWORD *)&mapColumnElements[80];
            }
            if ( v138 != *(_DWORD *)&mapColumnElements[80] )
            {
              if ( this->m_bCenterColumnVert )
              {
                CMFCRibbonPanel::CenterElementsInColumn(this, v136, v137, nCaptionHeight[1]);
                v142 = *(_DWORD *)&mapColumnElements[80];
              }
              if ( this->m_bJustifyColumns )
              {
                CMFCRibbonPanel::JustifyElementsInColumn(this, v136, v137);
                v142 = *(_DWORD *)&mapColumnElements[80];
              }
              v136 = v139;
              v138 = v142;
            }
            v137 = v139;
          }
          ++v139;
          ++v141;
          v140 = this->m_arElements.m_nSize;
        }
        while ( v139 < v140 );
      }
      if ( this->m_bCenterColumnVert )
        CMFCRibbonPanel::CenterElementsInColumn(this, v136, v137, nCaptionHeight[1]);
      if ( this->m_bJustifyColumns )
        CMFCRibbonPanel::JustifyElementsInColumn(this, v136, v137);
    }
    if ( this->m_bAlignByColumn && !this->m_bFloatyMode )
      v143 = CMFCRibbonPanel::CalcTotalWidth(this);
    else
LABEL_299:
      v143 = this->m_nFullWidth - 1;
    if ( v143 < v9 && !this->m_bTruncateCaption )
    {
      v154 = (v9 - v143) / 2;
      v155 = 0;
      v156 = this->m_arElements.m_nSize;
      if ( v156 > 0 )
      {
        v157 = 0;
        do
        {
          if ( v157 < 0 || v157 >= v156 )
            AfxThrowInvalidArgException();
          v158 = this->m_arElements.m_pData[v157];
          *(CRect *)&mapColumnElements[80] = v158->m_rect;
          OffsetRect((LPRECT)&mapColumnElements[80], v154, 0);
          v158->m_rect = *(CRect *)&mapColumnElements[80];
          ++v155;
          ++v157;
          v156 = this->m_arElements.m_nSize;
        }
        while ( v155 < v156 );
      }
      v143 = v9;
      v159 = this->m_nFullWidth;
      if ( v159 <= v9 )
        v159 = v9;
      this->m_nFullWidth = v159;
    }
    v160 = *(_DWORD *)&mapColumnElements[4];
    if ( !this->m_arElements.m_nSize )
    {
      v161 = *(_DWORD *)&mapColumnElements[4];
      if ( v9 > *(int *)&mapColumnElements[4] )
        v161 = v9;
      this->m_nFullWidth = this->m_nXMargin + v161;
    }
    v162 = this->m_nXMargin;
    v163 = this->m_rect.left;
    if ( v143 >= v160 )
      v164 = v163 + v143 + 2 * v162;
    else
      v164 = v160 + v163 + v162;
    this->m_rect.right = v164;
    if ( this->m_btnLaunch.m_nID )
    {
      *(CRect *)&mapColumnElements[80] = this->m_rect;
      InflateRect((LPRECT)&mapColumnElements[80], -1, -1);
      v165 = nCaptionHeight[1];
      *(_DWORD *)&mapColumnElements[84] = *(_DWORD *)&mapColumnElements[92] - nCaptionHeight[1] + 1;
      *(_DWORD *)&mapColumnElements[80] = *(_DWORD *)&mapColumnElements[88] - nCaptionHeight[1];
      --*(_DWORD *)&mapColumnElements[92];
      --*(_DWORD *)&mapColumnElements[88];
      this->m_btnLaunch.m_rect = *(CRect *)&mapColumnElements[80];
    }
    else
    {
      v165 = nCaptionHeight[1];
    }
    if ( this->m_bShowCaption )
    {
      this->m_rectCaption = this->m_rect;
      this->m_rectCaption.top = this->m_rectCaption.bottom - v165 - 1;
    }
  }
}

```

## disassembly

```asm
0x18011cc00  mov     rax, rsp
0x18011cc03  mov     [rax+20h], rbx
0x18011cc07  push    rbp
0x18011cc08  push    rsi
0x18011cc09  push    rdi
0x18011cc0a  push    r12
0x18011cc0c  push    r13
0x18011cc0e  push    r14
0x18011cc10  push    r15
0x18011cc12  lea     rbp, [rax-5Fh]
0x18011cc16  sub     rsp, 100h
0x18011cc1d  movaps  xmmword ptr [rax-48h], xmm6
0x18011cc21  mov     rax, cs:__security_cookie
0x18011cc28  xor     rax, rsp
0x18011cc2b  mov     [rbp+57h+var_50], rax
0x18011cc2f  mov     rdi, rect
0x18011cc32  mov     qword ptr [rbp+57h+rectLaunch.right], rect
0x18011cc36  mov     r14, pDC
0x18011cc39  mov     [rsp+130h+var_E0], pDC
0x18011cc3e  mov     rsi, this
0x18011cc41  add     this, 0FCh; lprc
0x18011cc48  call    cs:__imp_SetRectEmpty
0x18011cc4e  lea     this, [rsi+11Ch]; lprc
0x18011cc55  call    cs:__imp_SetRectEmpty
0x18011cc5b  lea     this, [rsi+12Ch]; lprc
0x18011cc62  call    cs:__imp_SetRectEmpty
0x18011cc68  xor     r15d, r15d
0x18011cc6b  mov     pDC, r14
0x18011cc6e  cmp     [rsi+168h], r15
0x18011cc75  jz      short loc_18011CCB9
0x18011cc77  mov     rax, [rsi]
0x18011cc7a  mov     rax, [rax+1F8h]
0x18011cc81  mov     this, rsi
0x18011cc84  mov     rect, rdi
0x18011cc87  call    cs:__guard_dispatch_icall_fptr
0x18011cc8d  mov     this, [rbp+57h+var_50]
0x18011cc91  xor     this, rsp; StackCookie
0x18011cc94  call    __security_check_cookie
0x18011cc99  lea     r11, [rsp+130h+var_30]
0x18011cca1  mov     rbx, [r11+58h]
0x18011cca5  movaps  xmm6, xmmword ptr [r11-10h]
0x18011ccaa  mov     rsp, r11
0x18011ccad  pop     r15
0x18011ccaf  pop     r14
0x18011ccb1  pop     r13
0x18011ccb3  pop     r12
0x18011ccb5  pop     rdi
0x18011ccb6  pop     rsi
0x18011ccb7  pop     rbp
0x18011ccb8  retn
0x18011ccb9  cmp     [rsi+0B8h], r15d
0x18011ccc0  jz      short loc_18011CCCE
0x18011ccc2  mov     rax, [rsi]
0x18011ccc5  mov     rax, [rax+1F0h]
0x18011cccc  jmp     short loc_18011CC81
0x18011ccce  mov     rax, [rsi+158h]
0x18011ccd5  mov     [rsi+4D0h], rax
0x18011ccdc  mov     [rsi+250h], rax
0x18011cce3  mov     [rsi+3E0h], rsi
0x18011ccea  lea     rbx, [rsi+3F0h]
0x18011ccf1  mov     rax, [rbx]
0x18011ccf4  mov     this, rbx
0x18011ccf7  mov     rax, [rax+310h]
0x18011ccfe  call    cs:__guard_dispatch_icall_fptr
0x18011cd04  mov     rax, [rbx]
0x18011cd07  mov     rect, r14
0x18011cd0a  lea     pDC, [rbp+57h+rectElem.right]
0x18011cd0e  mov     this, rbx
0x18011cd11  mov     rax, [rax+200h]
0x18011cd18  call    cs:__guard_dispatch_icall_fptr
0x18011cd1e  mov     ecx, [rax]
0x18011cd20  mov     dword ptr [rbp+57h+mapColumnElements.__vftable+4], ecx
0x18011cd23  movups  xmm0, xmmword ptr [rdi]
0x18011cd26  movdqu  xmmword ptr [rsi+10Ch], xmm0
0x18011cd2e  xorps   xmm1, xmm1
0x18011cd31  movdqu  xmmword ptr [rsi+238h], xmm1
0x18011cd39  mov     this, rsi; this
0x18011cd3c  cmp     [rsi+0A4h], r15d
0x18011cd43  jz      short loc_18011CD52
0x18011cd45  mov     pDC, r14; pDC
0x18011cd48  call    ?ShowDefaultButton@CMFCRibbonPanel@@IEAAXPEAVCDC@@@Z; CMFCRibbonPanel::ShowDefaultButton(CDC *)
0x18011cd4d  jmp     loc_18011CC8D
0x18011cd52  xorps   xmm0, xmm0
0x18011cd55  movdqu  xmmword ptr [rsi+4B8h], xmm0
0x18011cd5d  mov     [rsi+0E8h], r15
0x18011cd64  mov     dword ptr [rsi+0A0h], 1
0x18011cd6e  mov     rect, r14; pDC
0x18011cd71  lea     pDC, [rbp+57h+rectElem.right]; result
0x18011cd75  call    ?GetCaptionSize@CMFCRibbonPanel@@IEBA?AVCSize@@PEAVCDC@@@Z; CMFCRibbonPanel::GetCaptionSize(CDC *)
0x18011cd7a  mov     rbx, qword ptr [rbp+57h+rectElem.right]
0x18011cd7e  cmp     [rsi+0DCh], r15d
0x18011cd85  jnz     short loc_18011CD9F
0x18011cd87  mov     eax, [rdi+8]
0x18011cd8a  sub     eax, [rdi]
0x18011cd8c  mov     ecx, ebx
0x18011cd8e  cmp     eax, ebx
0x18011cd90  cmovg   ecx, eax
0x18011cd93  add     ecx, [rsi+10Ch]
0x18011cd99  mov     [rsi+114h], ecx
0x18011cd9f  mov     eax, [rdi+0Ch]
0x18011cda2  sub     eax, [rdi+4]
0x18011cda5  mov     edx, [rdi+8]
0x18011cda8  sub     edx, [rsi+0F0h]
0x18011cdae  sub     edx, [rdi]
0x18011cdb0  mov     [rsp+130h+key], edx
0x18011cdb4  sub     eax, [rsi+0F4h]
0x18011cdba  mov     ecx, [rbp+57h+rectElem.bottom]
0x18011cdbd  mov     [rsp+130h+nCaptionHeight+4], ecx
0x18011cdc1  sub     eax, ecx
0x18011cdc3  mov     [rsp+130h+var_EC], eax
0x18011cdc7  mov     this, [rsi+6E0h]
0x18011cdce  test    this, this
0x18011cdd1  jle     loc_18011CE71
0x18011cdd7  xor     r14d, r14d
0x18011cdda  mov     r12, [rsp+130h+var_E0]
0x18011cddf  test    r14, r14
0x18011cde2  js      loc_18011E346
0x18011cde8  cmp     r14, this
0x18011cdeb  jge     loc_18011E346
0x18011cdf1  mov     rax, [rsi+6D8h]
0x18011cdf8  mov     rdi, [rax+r14*8]
0x18011cdfc  mov     rax, [rdi]
0x18011cdff  mov     pDC, r12
0x18011ce02  mov     this, rdi
0x18011ce05  mov     rax, [rax+310h]
0x18011ce0c  call    cs:__guard_dispatch_icall_fptr
0x18011ce12  mov     rax, [rdi]
0x18011ce15  mov     this, rdi
0x18011ce18  cmp     dword ptr [rsi+0C0h], 0
0x18011ce1f  jnz     short loc_18011CE2C
0x18011ce21  xor     edx, edx
0x18011ce23  mov     rax, [rax+230h]
0x18011ce2a  jmp     short loc_18011CE38
0x18011ce2c  mov     edx, 1
0x18011ce31  mov     rax, [rax+1E8h]
0x18011ce38  call    cs:__guard_dispatch_icall_fptr
0x18011ce3e  mov     eax, [rsi+0C0h]
0x18011ce44  mov     [rdi+134h], eax
0x18011ce4a  or      dword ptr [rdi+11Ch], 0FFFFFFFFh
0x18011ce51  inc     r15d
0x18011ce54  inc     r14
0x18011ce57  mov     this, [rsi+6E0h]
0x18011ce5e  movsxd  rax, r15d
0x18011ce61  cmp     rax, this
0x18011ce64  jl      loc_18011CDDF
0x18011ce6a  mov     r14, r12
0x18011ce6d  mov     edx, [rsp+130h+key]; key
0x18011ce71  xor     r13d, r13d
0x18011ce74  xor     r12d, r12d
0x18011ce77  cmp     [rsi+0B0h], r12d
0x18011ce7e  jz      loc_18011D72B
0x18011ce84  cmp     [rsi+0C0h], r12d
0x18011ce8b  jnz     loc_18011D72B
0x18011ce91  movdqa  xmm6, cs:__xmm@000000000000000a0000000000000000
0x18011ce99  mov     r9d, 3
0x18011ce9f  lea     r10, ??_7?$CMap@HHHH@@6B@; const CMap<int,int,int,int>::`vftable'
0x18011cea6  xor     r14d, r14d
0x18011cea9  xor     r15d, r15d
0x18011ceac  xor     r12d, r12d
0x18011ceaf  mov     [rbp+57h+mapColumnElements.m_pHashTable], r10
0x18011ceb3  xor     r13d, r13d
0x18011ceb6  mov     qword ptr [rbp+57h+mapColumnElements.m_nHashTableSize], r13
0x18011ceba  mov     dword ptr [rbp+57h+mapColumnElements.m_nCount], 11h
0x18011cec1  xorps   xmm0, xmm0
0x18011cec4  movdqu  xmmword ptr [rbp+57h+mapColumnElements.m_pFreeList], xmm0
0x18011cec9  movdqu  xmmword ptr [rbp+57h+mapColumnElements.m_nBlockSize], xmm6
0x18011cece  and     [rsp+130h+var_108], r13d
0x18011ced3  xor     r8d, r8d
0x18011ced6  mov     qword ptr [rbp+57h+rc.left], rect
0x18011ceda  mov     this, [rsi+6E0h]
0x18011cee1  mov     pDC, this
0x18011cee4  test    this, this
0x18011cee7  jle     loc_18011D0C3
0x18011ceed  test    rect, rect
0x18011cef0  js      loc_18011E34C
0x18011cef6  cmp     rect, pDC
0x18011cef9  jge     loc_18011E34C
0x18011ceff  mov     rax, [rsi+6D8h]
0x18011cf06  mov     rdi, [rax+rect*8]
0x18011cf0a  mov     rax, [rdi]
0x18011cf0d  mov     r13, [rsp+130h+var_E0]
0x18011cf12  mov     rect, r13
0x18011cf15  lea     pDC, [rsp+130h+var_F8]
0x18011cf1a  mov     this, rdi
0x18011cf1d  mov     rax, [rax+1F8h]
0x18011cf24  call    cs:__guard_dispatch_icall_fptr
0x18011cf2a  cmp     [rsp+130h+var_F8], 0
0x18011cf2f  jnz     short loc_18011CF48
0x18011cf31  cmp     [rsp+130h+var_F4], 0
0x18011cf36  jnz     short loc_18011CF48
0x18011cf38  xorps   xmm0, xmm0
0x18011cf3b  movdqu  xmmword ptr [rdi+0C8h], xmm0
0x18011cf43  jmp     loc_18011D084
0x18011cf48  mov     rax, [rdi]
0x18011cf4b  mov     this, rdi
0x18011cf4e  mov     rax, [rax+240h]
0x18011cf55  call    cs:__guard_dispatch_icall_fptr
0x18011cf5b  test    eax, eax
0x18011cf5d  jz      short loc_18011CFBA
0x18011cf5f  add     r15d, r14d
0x18011cf62  mov     rax, qword ptr [rbp+57h+rectLaunch.right]
0x18011cf66  mov     r8d, [rax+4]
0x18011cf6a  add     r8d, [rsi+0F4h]
0x18011cf71  mov     edx, [rsi+0F0h]
0x18011cf77  add     edx, [rax]
0x18011cf79  add     edx, r15d
0x18011cf7c  mov     ecx, [rsp+130h+var_F8]
0x18011cf80  add     ecx, edx
0x18011cf82  mov     [rdi+0C8h], edx
0x18011cf88  mov     [rdi+0CCh], r8d
0x18011cf8f  mov     [rdi+0D0h], ecx
0x18011cf95  mov     eax, [rsp+130h+var_EC]
0x18011cf99  add     eax, r8d
0x18011cf9c  mov     [rdi+0D4h], eax
0x18011cfa2  mov     ecx, [rsi+0F0h]
0x18011cfa8  add     ecx, [rsp+130h+var_F8]
0x18011cfac  add     r15d, ecx
0x18011cfaf  xor     r12d, r12d
0x18011cfb2  xor     r14d, r14d
0x18011cfb5  jmp     loc_18011D084
0x18011cfba  mov     rax, [rdi]
0x18011cfbd  mov     this, rdi
0x18011cfc0  mov     rax, [rax+298h]
0x18011cfc7  call    cs:__guard_dispatch_icall_fptr
0x18011cfcd  mov     ecx, [rsp+130h+var_F4]
0x18011cfd1  test    eax, eax
0x18011cfd3  cmovnz  ecx, [rsp+130h+var_EC]
0x18011cfd8  mov     [rsp+130h+var_F4], ecx
0x18011cfdc  lea     eax, [this+r12]
0x18011cfe0  cmp     eax, [rsp+130h+var_EC]
0x18011cfe4  jle     short loc_18011CFF8
0x18011cfe6  test    r12d, r12d
0x18011cfe9  jz      loc_18011D6C3
0x18011cfef  add     r15d, r14d
0x18011cff2  xor     r12d, r12d
0x18011cff5  xor     r14d, r14d
0x18011cff8  mov     r13d, [rsi+0F0h]
0x18011cfff  mov     rax, qword ptr [rbp+57h+rectLaunch.right]
0x18011d003  add     r13d, [rax]
0x18011d006  add     r13d, r15d
0x18011d009  mov     edx, [rax+4]
0x18011d00c  add     edx, [rsi+0F4h]
0x18011d012  add     edx, r12d
0x18011d015  mov     ecx, [rsp+130h+var_F8]
0x18011d019  add     ecx, r13d
0x18011d01c  mov     rax, qword ptr [rsp+130h+var_F8]
0x18011d021  shr     rax, 20h
0x18011d025  mov     [rdi+0C8h], r13d
0x18011d02c  mov     [rdi+0CCh], edx
0x18011d032  mov     [rdi+0D0h], ecx
0x18011d038  add     eax, edx
0x18011d03a  mov     [rdi+0D4h], eax
0x18011d040  mov     [rsp+130h+rValue], 1
0x18011d048  lea     rect, [rsp+130h+rValue]; rValue
0x18011d04d  mov     edx, r13d; key
0x18011d050  lea     this, [rbp+57h+mapColumnElements.m_pHashTable]; this
0x18011d054  call    ?Lookup@?$CMap@IIHH@@QEBAHIAEAH@Z; CMap<uint,uint,int,int>::Lookup(uint,int &)
0x18011d059  mov     r8d, [rsp+130h+rValue]
0x18011d05e  test    eax, eax
0x18011d060  jz      short loc_18011D065
0x18011d062  inc     r8d; newValue
0x18011d065  mov     edx, r13d; key
0x18011d068  lea     this, [rbp+57h+mapColumnElements.m_pHashTable]; this
0x18011d06c  call    ?SetAt@?$CMap@HHHH@@QEAAXHH@Z; CMap<int,int,int,int>::SetAt(int,int)
0x18011d071  mov     eax, [rsp+130h+var_F8]
0x18011d075  cmp     r14d, eax
0x18011d078  cmovg   eax, r14d
0x18011d07c  mov     r14d, eax
0x18011d07f  add     r12d, [rsp+130h+var_F4]
0x18011d084  mov     r9d, [rsp+130h+var_108]
0x18011d089  inc     r9d
0x18011d08c  mov     [rsp+130h+var_108], r9d
0x18011d091  mov     rect, qword ptr [rbp+57h+rc.left]
0x18011d095  inc     rect
0x18011d098  mov     qword ptr [rbp+57h+rc.left], rect
0x18011d09c  mov     this, [rsi+6E0h]
0x18011d0a3  mov     pDC, this
0x18011d0a6  movsxd  rax, r9d
0x18011d0a9  cmp     rax, this
0x18011d0ac  jl      loc_18011CEED
0x18011d0b2  mov     r13, qword ptr [rbp+57h+mapColumnElements.m_nHashTableSize]
0x18011d0b6  mov     r9d, 3
0x18011d0bc  lea     r10, ??_7?$CMap@HHHH@@6B@; const CMap<int,int,int,int>::`vftable'
0x18011d0c3  lea     eax, [r14+r15]
0x18011d0c7  cmp     eax, [rsp+130h+key]
0x18011d0cb  jle     loc_18011D713
0x18011d0d1  test    r14d, r14d
0x18011d0d4  jz      loc_18011D6D4
0x18011d0da  xor     r14d, r14d
0x18011d0dd  xor     r12d, r12d
0x18011d0e0  xor     edi, edi
0x18011d0e2  test    this, this
0x18011d0e5  jle     loc_18011D182
0x18011d0eb  test    r14d, r14d
0x18011d0ee  jnz     loc_18011D2BE
0x18011d0f4  test    rdi, rdi
0x18011d0f7  js      loc_18011E352
0x18011d0fd  cmp     rdi, pDC
0x18011d100  jge     loc_18011E352
0x18011d106  mov     rax, [rsi+6D8h]
  ... truncated ...
```
