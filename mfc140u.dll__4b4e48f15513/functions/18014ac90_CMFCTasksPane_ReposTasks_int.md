# CMFCTasksPane::ReposTasks(int)

- ea: `0x18014ac90`
- end: `0x18014b7b1`
- name: `?ReposTasks@CMFCTasksPane@@MEAAHH@Z`
- size: `2849`
- prototype: `int __fastcall(CMFCTasksPane *this, int bCalcHeightOnly)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task`

## callees

- `0x180009844`
- `0x18006cab0`
- `0x18014ac90`
- `0x18014d620`
- `0x180231d70`
- `0x180296d00`
- `0x1802af110`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802b66c0`
- `0x1802b6730`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!SetRectEmpty` at `0x18014b03e`
- `USER32!SetRectEmpty` at `0x18014b300`
- `USER32!SetRectEmpty` at `0x18014b03e`
- `USER32!SetRectEmpty` at `0x18014b300`
- `USER32!IsRectEmpty` at `0x18014b425`
- `USER32!IsRectEmpty` at `0x18014b6a9`
- `USER32!IsRectEmpty` at `0x18014b425`
- `USER32!IsRectEmpty` at `0x18014b6a9`
- `USER32!InflateRect` at `0x18014ad99`
- `USER32!InflateRect` at `0x18014b125`
- `USER32!InflateRect` at `0x18014b3fa`
- `USER32!InflateRect` at `0x18014ad99`
- `USER32!InflateRect` at `0x18014b125`
- `USER32!InflateRect` at `0x18014b3fa`
- `USER32!OffsetRect` at `0x18014b5d0`
- `USER32!OffsetRect` at `0x18014b5e4`
- `USER32!OffsetRect` at `0x18014b5f3`
- `USER32!OffsetRect` at `0x18014b5d0`
- `USER32!OffsetRect` at `0x18014b5e4`
- `USER32!OffsetRect` at `0x18014b5f3`
- `GDI32!GetTextExtentPoint32W` at `0x18014aee6`
- `GDI32!GetTextExtentPoint32W` at `0x18014b24a`
- `GDI32!GetTextExtentPoint32W` at `0x18014aee6`
- `GDI32!GetTextExtentPoint32W` at `0x18014b24a`
- `GDI32!GetTextMetricsW` at `0x18014adce`
- `GDI32!GetTextMetricsW` at `0x18014adce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFCTasksPane::ReposTasks(CMFCTasksPane *this, int bCalcHeightOnly)
{
  int v2; // r15d
  CMFCTasksPane *v3; // rdi
  int top; // eax
  int left; // eax
  int m_nVertMargin; // ebx
  int m_nHorzMargin; // edx
  CFont *p_m_fontBold; // rbx
  int cy; // ecx
  int v10; // esi
  __int64 m_iActivePage; // rcx
  __int64 v12; // rcx
  CObList::CNode *i; // rax
  CObject *data; // rdx
  CObList::CNode *m_pNodeHead; // r12
  CObject *v16; // r13
  CFont *v17; // rbx
  int m_nGroupCaptionVertOffset; // r14d
  int m_nGroupCaptionHeight; // ebx
  int v20; // eax
  int v21; // esi
  int v22; // r14d
  CObject_vtbl *v23; // rbx
  void (__fastcall *Serialize)(CObject *, CArchive *); // rcx
  int v25; // ebx
  int v26; // r12d
  CObject_vtbl *v27; // rcx
  void (__fastcall *v28)(CObject *, CArchive *); // r14
  int v29; // eax
  int v30; // r15d
  int m_nTasksIconHorzOffset; // r12d
  int m_bWrapTasks; // eax
  CFont *v33; // rbx
  int v34; // r15d
  int v35; // ecx
  int v36; // ebx
  CFont *v37; // rbx
  int v38; // eax
  int v39; // ecx
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int m_nTasksIconVertOffset; // eax
  int v44; // eax
  int bottom; // edx
  int v46; // ecx
  unsigned int v47; // r15d
  int m_nTasksHorzOffset; // edx
  __int64 v49; // r8
  int v50; // ecx
  int v51; // r9d
  int v52; // esi
  int v53; // r8d
  int v54; // ecx
  int v55; // eax
  int m_nGroupVertOffset; // eax
  CObList::CNode *m_pNodeTail; // rcx
  CObject *v58; // rbx
  CObject_vtbl *v59; // rcx
  void (__fastcall *v60)(CObject *, CArchive *); // rax
  int v61; // r14d
  CObject_vtbl *v62; // r15
  void (__fastcall *v63)(CObject *, CArchive *); // rcx
  CObList::CNode *v64; // rbx
  CMFCTasksPaneTaskGroup *v65; // rcx
  __int64 v66; // rsi
  CObList::CNode *v67; // r14
  CObject *v68; // r15
  HWND__ *v69; // rcx
  CWnd *v70; // r12
  int v71; // r14d
  int v72; // eax
  unsigned int v73; // ebx
  int v76; // [rsp+44h] [rbp-BCh]
  int v77; // [rsp+48h] [rbp-B8h]
  int v78; // [rsp+48h] [rbp-B8h]
  CObList::CNode *v79; // [rsp+50h] [rbp-B0h]
  __int64 v80; // [rsp+50h] [rbp-B0h]
  tagSIZE v81; // [rsp+58h] [rbp-A8h] BYREF
  CSize sizeGroupBorders; // [rsp+60h] [rbp-A0h] BYREF
  CClientDC dc; // [rsp+68h] [rbp-98h] BYREF
  CMFCTasksPanePropertyPage *v84; // [rsp+90h] [rbp-70h]
  __int128 v85; // [rsp+98h] [rbp-68h]
  __int128 v86; // [rsp+A8h] [rbp-58h]
  __int128 v87; // [rsp+B8h] [rbp-48h]
  __int128 v88; // [rsp+C8h] [rbp-38h]
  tagSIZE psizl; // [rsp+D8h] [rbp-28h] BYREF
  CRuntimeClass *(__fastcall *GetRuntimeClass)(CObject *); // [rsp+E0h] [rbp-20h]
  CMFCTasksPane *v91; // [rsp+E8h] [rbp-18h]
  CFont *pFont; // [rsp+F0h] [rbp-10h]
  CRect rectTasks; // [rsp+100h] [rbp+0h] BYREF
  CRect rectChildWnd; // [rsp+110h] [rbp+10h] BYREF
  CRect rectText; // [rsp+120h] [rbp+20h] BYREF
  tagTEXTMETRICW tm; // [rsp+130h] [rbp+30h] BYREF

  v2 = bCalcHeightOnly;
  v3 = this;
  v91 = this;
  if ( !afxGlobalData.m_bInitialized )
  {
    AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
    afxGlobalData.m_bInitialized = 1;
  }
  if ( afxGlobalData.bIsRemoteSession )
    v3->m_bAnimationEnabled = 0;
  if ( !v3 )
    return 0;
  if ( !v3->m_hWnd )
    return 0;
  if ( !v3->m_lstTaskGroups.m_nCount )
    return 0;
  top = v3->m_rectTasks.top;
  if ( top < 0 )
    return 0;
  if ( v3->m_rectTasks.bottom <= top )
    return 0;
  left = v3->m_rectTasks.left;
  if ( left < 0 || v3->m_rectTasks.right <= left )
    return 0;
  rectTasks = v3->m_rectTasks;
  m_nVertMargin = v3->m_nVertMargin;
  if ( m_nVertMargin == -1 )
    m_nVertMargin = CMFCVisualManager::GetInstance()->m_nVertMargin;
  m_nHorzMargin = v3->m_nHorzMargin;
  if ( m_nHorzMargin == -1 )
    m_nHorzMargin = CMFCVisualManager::GetInstance()->m_nHorzMargin;
  InflateRect(&rectTasks, -m_nHorzMargin, -m_nVertMargin);
  CClientDC::CClientDC(&dc, v3);
  p_m_fontBold = &v3->m_fontBold;
  pFont = CDC::SelectObject(&dc, &v3->m_fontBold);
  GetTextMetricsW(dc.m_hAttribDC, &tm);
  cy = v3->m_sizeIcon.cy;
  if ( tm.tmHeight > cy )
    cy = tm.tmHeight;
  v3->m_nRowHeight = cy;
  v3->m_nAnimGroupExtraHeight = 0;
  v10 = rectTasks.top - v3->m_nVertScrollOffset * cy;
  v77 = v10;
  m_iActivePage = v3->m_iActivePage;
  if ( m_iActivePage < 0 )
    goto LABEL_205;
  if ( m_iActivePage >= v3->m_arrHistoryStack.m_nSize )
    goto LABEL_205;
  v12 = v3->m_arrHistoryStack.m_pData[m_iActivePage];
  if ( v12 >= v3->m_lstTasksPanes.m_nCount || v12 < 0 )
    goto LABEL_205;
  for ( i = v3->m_lstTasksPanes.m_pNodeHead; v12; i = i->pNext )
    --v12;
  if ( !i )
LABEL_205:
    AfxThrowInvalidArgException();
  data = i->data;
  v84 = (CMFCTasksPanePropertyPage *)data;
  m_pNodeHead = v3->m_lstTaskGroups.m_pNodeHead;
  if ( m_pNodeHead )
  {
    while ( 1 )
    {
      v16 = m_pNodeHead->data;
      m_pNodeHead = m_pNodeHead->pNext;
      v79 = m_pNodeHead;
      if ( (CObject *)v16[1].__vftable == data )
        break;
LABEL_157:
      if ( !m_pNodeHead )
      {
        v77 = v10;
        goto LABEL_159;
      }
    }
    CDC::SelectObject(&dc, p_m_fontBold);
    if ( LODWORD(v16[2].__vftable[-1].AssertValid) )
    {
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      v17 = CDC::SelectObject(&dc, &afxGlobalData.fontBold);
      GetTextExtentPoint32W(dc.m_hAttribDC, (LPCWSTR)v16[2].__vftable, (int)v16[2].__vftable[-1].AssertValid, &psizl);
      CDC::SelectObject(&dc, v17);
      m_nGroupCaptionVertOffset = v3->m_nGroupCaptionVertOffset;
      if ( m_nGroupCaptionVertOffset == -1 )
        m_nGroupCaptionVertOffset = CMFCVisualManager::GetInstance()->m_nGroupCaptionVertOffset;
      m_nGroupCaptionHeight = v3->m_nGroupCaptionHeight;
      if ( m_nGroupCaptionHeight == -1 )
        m_nGroupCaptionHeight = CMFCVisualManager::GetInstance()->m_nGroupCaptionHeight;
      if ( v3->IsToolBox(v3) )
      {
        if ( m_nGroupCaptionVertOffset < 5 )
          m_nGroupCaptionVertOffset = 5;
        if ( v3->m_nGroupCaptionHeight == -1 )
          m_nGroupCaptionHeight = 18;
      }
      if ( m_nGroupCaptionVertOffset + psizl.cy > m_nGroupCaptionHeight )
        m_nGroupCaptionHeight = m_nGroupCaptionVertOffset + psizl.cy;
    }
    else
    {
      m_nGroupCaptionHeight = 0;
    }
    if ( v16[17].__vftable )
    {
      if ( SHIDWORD(v16[15].__vftable) < rectTasks.right - rectTasks.left - m_nGroupCaptionHeight )
      {
        v20 = (int)v16[16].__vftable;
        if ( m_nGroupCaptionHeight < v20 )
          v10 += v20 - m_nGroupCaptionHeight;
      }
    }
    if ( !v2 )
    {
      *(_QWORD *)&v85 = __PAIR64__(v10, rectTasks.left);
      DWORD2(v85) = rectTasks.right;
      HIDWORD(v85) = m_nGroupCaptionHeight + v10;
      *(_OWORD *)((char *)&v16[11].__vftable + 4) = v85;
    }
    v21 = m_nGroupCaptionHeight + v10;
    v22 = v21;
    v78 = v21;
    CMFCTasksPane::SetFont(v3, &dc);
    if ( v3->m_bCanCollapse
      && LODWORD(v16[11].__vftable)
      && LODWORD(v16[2].__vftable[-1].AssertValid)
      && (!v3->m_bAnimationEnabled || v16 != v3->m_pAnimatedGroup || v3->m_sizeAnim.cy <= 0 || v2) )
    {
      if ( !v2 )
      {
        LODWORD(v86) = rectTasks.left;
        DWORD1(v86) = v21 - 1;
        DWORD2(v86) = rectTasks.right;
        HIDWORD(v86) = v21 - 1;
        *(_OWORD *)((char *)&v16[13].__vftable + 4) = v86;
        v23 = v16[4].__vftable;
        while ( v23 )
        {
          Serialize = v23->Serialize;
          v23 = (CObject_vtbl *)v23->GetRuntimeClass;
          if ( !*((_QWORD *)Serialize + 8) )
            SetRectEmpty((LPRECT)((char *)Serialize + 24));
        }
      }
LABEL_154:
      m_nGroupVertOffset = v3->m_nGroupVertOffset;
      if ( m_nGroupVertOffset == -1 )
        m_nGroupVertOffset = CMFCVisualManager::GetInstance()->m_nGroupVertOffset;
      v10 = m_nGroupVertOffset + v21;
      data = v84;
      p_m_fontBold = &v3->m_fontBold;
      goto LABEL_157;
    }
    v25 = 1;
    v26 = 1;
    v76 = 1;
    v3->GetTasksGroupBorders(v3, &sizeGroupBorders);
    v27 = v16[4].__vftable;
    if ( !v27 )
    {
LABEL_152:
      m_pNodeHead = v79;
      if ( !v2 )
      {
        *(_QWORD *)&v88 = __PAIR64__(v22, rectTasks.left);
        *((_QWORD *)&v88 + 1) = __PAIR64__(v21, rectTasks.right);
        *(_OWORD *)((char *)&v16[13].__vftable + 4) = v88;
      }
      goto LABEL_154;
    }
    while ( 1 )
    {
      v28 = v27->Serialize;
      GetRuntimeClass = v27->GetRuntimeClass;
      if ( *((_QWORD *)v28 + 8) )
      {
        if ( v26 && *((_DWORD *)v28 + 19) )
        {
          if ( v3->m_bOffsetCustomControls )
          {
            m_nTasksIconVertOffset = v3->m_nTasksIconVertOffset;
            if ( m_nTasksIconVertOffset == -1 )
              m_nTasksIconVertOffset = CMFCVisualManager::GetInstance()->m_nTasksIconVertOffset;
            v21 += m_nTasksIconVertOffset;
          }
          else
          {
            v21 += sizeGroupBorders.cy;
          }
        }
        CWnd::FromHandle(*((HWND__ **)v28 + 8));
        if ( !v2 )
        {
          rectChildWnd = rectTasks;
          if ( *((_DWORD *)v28 + 19) )
            v44 = *((_DWORD *)v28 + 11);
          else
            v44 = 0;
          bottom = v44 + v21;
          v46 = v21;
          if ( v3->m_rectTasks.top + 1 > v21 )
            v46 = v3->m_rectTasks.top + 1;
          rectChildWnd.top = v46;
          v47 = v46 + *((_DWORD *)v28 + 11) - bottom;
          if ( v3->m_rectTasks.bottom < bottom )
            bottom = v3->m_rectTasks.bottom;
          rectChildWnd.bottom = bottom;
          if ( v3->m_bOffsetCustomControls )
          {
            m_nTasksHorzOffset = v3->m_nTasksHorzOffset;
            if ( m_nTasksHorzOffset == -1 )
              m_nTasksHorzOffset = CMFCVisualManager::GetInstance()->m_nTasksHorzOffset;
          }
          else
          {
            m_nTasksHorzOffset = sizeGroupBorders.cx;
          }
          InflateRect(&rectChildWnd, -m_nTasksHorzOffset, 0);
          *(CRect *)((char *)v28 + 24) = rectChildWnd;
          if ( v3->IsToolBox(v3) )
          {
            if ( IsRectEmpty((const RECT *)((char *)v28 + 24)) )
              v49 = 0;
            else
              v49 = v47;
            v3->ScrollChild(v3, *((HWND__ **)v28 + 8), v49);
          }
          v25 = v76;
          v2 = bCalcHeightOnly;
        }
        if ( *((_DWORD *)v28 + 19) )
        {
          v21 += *((_DWORD *)v28 + 11);
          v25 = 1;
          v26 = 1;
          v76 = 1;
LABEL_106:
          if ( v3->m_bOffsetCustomControls )
          {
            v42 = v3->m_nTasksIconVertOffset;
            if ( v42 == -1 )
              v42 = CMFCVisualManager::GetInstance()->m_nTasksIconVertOffset;
            v21 += v42;
          }
          else
          {
            v21 += sizeGroupBorders.cy;
          }
          goto LABEL_138;
        }
      }
      else
      {
        if ( *((_DWORD *)v28 + 19) )
        {
          if ( v26 )
          {
            v29 = v3->m_nTasksIconVertOffset;
            if ( v29 == -1 )
              v29 = CMFCVisualManager::GetInstance()->m_nTasksIconVertOffset;
            v21 += v29;
          }
          v30 = v3->m_nTasksHorzOffset;
          if ( v30 == -1 )
            v30 = CMFCVisualManager::GetInstance()->m_nTasksHorzOffset;
          m_nTasksIconHorzOffset = v3->m_nTasksIconHorzOffset;
          if ( m_nTasksIconHorzOffset == -1 )
            m_nTasksIconHorzOffset = CMFCVisualManager::GetInstance()->m_nTasksIconHorzOffset;
          if ( *((_DWORD *)v28 + 12) )
            m_bWrapTasks = v3->m_bWrapTasks;
          else
            m_bWrapTasks = v3->m_bWrapLabels;
          if ( m_bWrapTasks )
          {
            rectChildWnd = rectTasks;
            InflateRect(&rectChildWnd, -v30, 0);
            rectChildWnd.top = v21;
            rectChildWnd.bottom = v21 + v3->m_sizeIcon.cy;
            rectText = rectChildWnd;
            rectText.left = m_nTasksIconHorzOffset + _mm_cvtsi128_si32((__m128i)rectChildWnd) + v3->m_sizeIcon.cx;
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            v33 = CDC::SelectObject(&dc, &afxGlobalData.fontUnderline);
            v34 = dc.DrawTextW(
                    &dc,
                    (const wchar_t *)*((_QWORD *)v28 + 2),
                    *(unsigned int *)(*((_QWORD *)v28 + 2) - 16LL),
                    &rectText,
                    1040u);
            CDC::SelectObject(&dc, v33);
            if ( *((_DWORD *)v28 + 21) )
            {
              v35 = 10;
              if ( v34 > 10 )
                v35 = v34;
              v34 = v35;
            }
            v36 = v3->m_sizeIcon.cy;
            if ( v34 > v36 )
              v36 = v34;
            rectChildWnd.bottom = v36 + rectChildWnd.top;
            if ( !bCalcHeightOnly )
              *(CRect *)((char *)v28 + 24) = rectChildWnd;
          }
          else
          {
            if ( !afxGlobalData.m_bInitialized )
            {
              AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
              afxGlobalData.m_bInitialized = 1;
            }
            v37 = CDC::SelectObject(&dc, &afxGlobalData.fontUnderline);
            GetTextExtentPoint32W(dc.m_hAttribDC, *((LPCWSTR *)v28 + 2), *(_DWORD *)(*((_QWORD *)v28 + 2) - 16LL), &v81);
            CDC::SelectObject(&dc, v37);
            v36 = v3->m_sizeIcon.cy;
            if ( v81.cy > v36 )
              v36 = v81.cy;
            if ( *((_DWORD *)v28 + 21) )
            {
              v38 = 10;
              if ( v36 > 10 )
                v38 = v36;
              v36 = v38;
            }
            if ( !bCalcHeightOnly )
            {
              v39 = rectTasks.left + v30 + m_nTasksIconHorzOffset + v81.cx + v3->m_sizeIcon.cx;
              LODWORD(v87) = v30 + rectTasks.left;
              *(_QWORD *)((char *)&v87 + 4) = __PAIR64__(v39, v21);
              HIDWORD(v87) = v36 + v21;
              *(_OWORD *)((char *)v28 + 24) = v87;
              v40 = *((_DWORD *)v28 + 6);
              if ( v40 <= rectTasks.right - v30 )
                v40 = rectTasks.right - v30;
              *((_DWORD *)v28 + 8) = v40;
            }
          }
          v41 = v3->m_nTasksIconVertOffset;
          if ( v41 == -1 )
            v41 = CMFCVisualManager::GetInstance()->m_nTasksIconVertOffset;
          v21 += v36 + v41;
          v26 = 0;
          v25 = 0;
          v76 = 0;
          v2 = bCalcHeightOnly;
          goto LABEL_138;
        }
        if ( !v2 )
          SetRectEmpty((LPRECT)((char *)v28 + 24));
      }
      if ( v25 && *((_DWORD *)v28 + 19) )
        goto LABEL_106;
LABEL_138:
      if ( !v2 )
      {
        if ( v3->m_bAnimationEnabled )
        {
          if ( v16 == v3->m_pAnimatedGroup )
          {
            v50 = v3->m_sizeAnim.cy;
            if ( v21 > v50 + v78 )
            {
              v51 = v21;
              v52 = 0;
              if ( v50 >= 0 )
                v52 = v3->m_sizeAnim.cy;
              v21 = v78 + v52;
              v53 = *((_DWORD *)v28 + 9);
              v54 = *((_DWORD *)v28 + 7);
              v55 = v53;
              if ( v53 >= v21 - 1 )
                v55 = v21 - 1;
              if ( v54 <= v55 )
              {
                v54 = v21 - 1;
                if ( v53 < v21 - 1 )
                  v54 = *((_DWORD *)v28 + 9);
              }
              *((_DWORD *)v28 + 9) = v54;
              v3->m_nAnimGroupExtraHeight += v51 - v21;
            }
          }
        }
      }
      v27 = (CObject_vtbl *)GetRuntimeClass;
      if ( !GetRuntimeClass )
      {
        v22 = v78;
        goto LABEL_152;
      }
    }
  }
LABEL_159:
  if ( !v2 )
  {
    m_pNodeTail = v3->m_lstTaskGroups.m_pNodeTail;
    while ( m_pNodeTail )
    {
      v58 = m_pNodeTail->data;
      m_pNodeTail = m_pNodeTail->pPrev;
      if ( (CObject *)v58[1].__vftable == data )
      {
        if ( LODWORD(v58[10].__vftable) && v58[6].__vftable && !v3->m_nVertScrollTotal )
        {
          v59 = v58[5].__vftable;
          while ( v59 )
          {
            v60 = v59->Serialize;
            v59 = (CObject_vtbl *)v59->~CObject;
            if ( *((_DWORD *)v60 + 19) )
            {
              v61 = rectTasks.bottom - LODWORD(v58[15].__vftable);
              if ( v61 > 0 )
              {
                v62 = v58[4].__vftable;
                while ( v62 )
                {
                  v63 = v62->Serialize;
                  v62 = (CObject_vtbl *)v62->GetRuntimeClass;
                  if ( *((_DWORD *)v63 + 19) )
                    OffsetRect((LPRECT)((char *)v63 + 24), 0, v61);
                }
                OffsetRect((LPRECT)((char *)&v58[11].__vftable + 4), 0, v61);
                OffsetRect((LPRECT)((char *)&v58[13].__vftable + 4), 0, v61);
              }
              goto LABEL_177;
            }
          }
        }
        break;
      }
    }
LABEL_177:
    v64 = v3->m_lstTaskGroups.m_pNodeHead;
    if ( v64 )
    {
      do
      {
        v65 = (CMFCTasksPaneTaskGroup *)v64->data;
        v64 = v64->pNext;
        if ( v65->m_pPage == v84 )
        {
          if ( !v3->m_bCanCollapse || !v65->m_bIsCollapsed || (v66 = 1, !*((_DWORD *)v65->m_strName.m_pszData - 4)) )
            v66 = 0;
          if ( !v3->m_bAnimationEnabled || v65 != v3->m_pAnimatedGroup || (v80 = 1, v3->m_sizeAnim.cy <= 0) )
            v80 = 0;
          v67 = v65->m_lstTasks.m_pNodeHead;
          if ( v67 )
          {
            do
            {
              v68 = v67->data;
              v67 = v67->pNext;
              v69 = (HWND__ *)v68[8].__vftable;
              if ( v69 )
              {
                v70 = CWnd::FromHandle(v69);
                if ( v66 && !v80 || !HIDWORD(v68[9].__vftable) || IsRectEmpty((const RECT *)&v68[3]) )
                {
                  CWnd::ShowWindow(v70, 0);
                }
                else
                {
                  CWnd::SetWindowPos(
                    v70,
                    0,
                    (int)v68[3].__vftable,
                    HIDWORD(v68[3].__vftable),
                    LODWORD(v68[4].__vftable) - LODWORD(v68[3].__vftable),
                    HIDWORD(v68[4].__vftable) - HIDWORD(v68[3].__vftable),
                    0x14u);
                  CWnd::ShowWindow(v70, 4);
                }
              }
            }
            while ( v67 );
            v3 = v91;
          }
        }
      }
      while ( v64 );
      v10 = v77;
    }
  }
  CDC::SelectObject(&dc, pFont);
  v71 = v3->m_nGroupVertOffset;
  if ( v71 == -1 )
    v71 = CMFCVisualManager::GetInstance()->m_nGroupVertOffset;
  v72 = v3->m_nVertMargin;
  if ( v72 == -1 )
    v72 = CMFCVisualManager::GetInstance()->m_nVertMargin;
  v73 = v10 + v72 + v3->m_nVertScrollOffset * v3->m_nRowHeight - v71;
  CClientDC::~CClientDC(&dc);
  return v73;
}

```

## disassembly

```asm
0x18014ac90  mov     [rsp-8+arg_8], rbx
0x18014ac95  mov     [rsp-8+arg_10], rsi
0x18014ac9a  mov     [rsp-8+arg_18], rdi
0x18014ac9f  push    rbp
0x18014aca0  push    r12
0x18014aca2  push    r13
0x18014aca4  push    r14
0x18014aca6  push    r15
0x18014aca8  lea     rbp, [rsp-80h]
0x18014acad  sub     rsp, 180h
0x18014acb4  mov     rax, cs:__security_cookie
0x18014acbb  xor     rax, rsp
0x18014acbe  mov     [rbp+0A0h+var_30], rax
0x18014acc2  mov     r15d, bCalcHeightOnly
0x18014acc5  mov     [rsp+1A0h+var_160], bCalcHeightOnly
0x18014acc9  mov     rdi, this
0x18014accc  mov     [rbp+0A0h+var_B8], this
0x18014acd0  xor     r13d, r13d
0x18014acd3  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r13d; AFX_GLOBAL_DATA afxGlobalData ...
0x18014acda  jnz     short loc_18014ACF2
0x18014acdc  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18014ace3  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18014ace8  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18014acf2  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.bIsRemoteSession, r13d; AFX_GLOBAL_DATA afxGlobalData ...
0x18014acf9  jz      short loc_18014AD02
0x18014acfb  mov     [rdi+4F0h], r13d
0x18014ad02  test    rdi, rdi
0x18014ad05  jz      loc_18014B77C
0x18014ad0b  cmp     [rdi+40h], r13
0x18014ad0f  jz      loc_18014B77C
0x18014ad15  cmp     [rdi+658h], r13
0x18014ad1c  jz      loc_18014B77C
0x18014ad22  mov     eax, [rdi+5DCh]
0x18014ad28  test    eax, eax
0x18014ad2a  js      loc_18014B77C
0x18014ad30  cmp     [rdi+5E4h], eax
0x18014ad36  jle     loc_18014B77C
0x18014ad3c  mov     eax, [rdi+5D8h]
0x18014ad42  test    eax, eax
0x18014ad44  js      loc_18014B77C
0x18014ad4a  cmp     [rdi+5E0h], eax
0x18014ad50  jle     loc_18014B77C
0x18014ad56  movups  xmm0, xmmword ptr [rdi+5D8h]
0x18014ad5d  movdqu  xmmword ptr [rbp+0A0h+rectTasks.left], xmm0
0x18014ad62  mov     ebx, [rdi+524h]
0x18014ad68  cmp     ebx, 0FFFFFFFFh
0x18014ad6b  jnz     short loc_18014AD78
0x18014ad6d  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18014ad72  mov     ebx, [rax+0D0h]
0x18014ad78  mov     bCalcHeightOnly, [rdi+528h]
0x18014ad7e  cmp     bCalcHeightOnly, 0FFFFFFFFh
0x18014ad81  jnz     short loc_18014AD8E
0x18014ad83  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18014ad88  mov     bCalcHeightOnly, [rax+0D4h]
0x18014ad8e  neg     ebx
0x18014ad90  neg     bCalcHeightOnly; dx
0x18014ad92  mov     r8d, ebx; dy
0x18014ad95  lea     this, [rbp+0A0h+rectTasks]; lprc
0x18014ad99  call    cs:__imp_InflateRect
0x18014ad9f  mov     rdx, rdi; pWnd
0x18014ada2  lea     this, [rsp+1A0h+dc]; this
0x18014ada7  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x18014adac  nop
0x18014adad  lea     rbx, [rdi+558h]
0x18014adb4  mov     rdx, rbx; pFont
0x18014adb7  lea     this, [rsp+1A0h+dc]; this
0x18014adbc  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18014adc1  mov     [rbp+0A0h+pFont], rax
0x18014adc5  lea     rdx, [rbp+0A0h+tm]; lptm
0x18014adc9  mov     this, [rsp+1A0h+dc.m_hAttribDC]; hdc
0x18014adce  call    cs:__imp_GetTextMetricsW
0x18014add4  mov     ecx, [rdi+58Ch]
0x18014adda  cmp     [rbp+0A0h+tm.tmHeight], ecx
0x18014addd  cmovg   ecx, [rbp+0A0h+tm.tmHeight]
0x18014ade1  mov     [rdi+51Ch], ecx
0x18014ade7  mov     [rdi+520h], r13d
0x18014adee  imul    ecx, [rdi+510h]
0x18014adf5  mov     esi, [rbp+0A0h+rectTasks.top]
0x18014adf8  sub     esi, ecx
0x18014adfa  mov     [rsp+1A0h+var_158], esi
0x18014adfe  movsxd  this, dword ptr [rdi+504h]
0x18014ae05  test    this, this
0x18014ae08  js      loc_18014B7AB
0x18014ae0e  cmp     this, [rdi+788h]
0x18014ae15  jge     loc_18014B7AB
0x18014ae1b  mov     rax, [rdi+780h]
0x18014ae22  movsxd  this, dword ptr [rax+this*4]
0x18014ae26  cmp     this, [rdi+620h]
0x18014ae2d  jge     loc_18014B7AB
0x18014ae33  test    this, this
0x18014ae36  js      loc_18014B7AB
0x18014ae3c  mov     rax, [rdi+610h]
0x18014ae43  jz      short loc_18014AE4E
0x18014ae45  sub     this, 1
0x18014ae49  mov     rax, [rax]
0x18014ae4c  jnz     short loc_18014AE45
0x18014ae4e  test    rax, rax
0x18014ae51  jz      loc_18014B7AB
0x18014ae57  mov     rdx, [rax+10h]
0x18014ae5b  mov     [rbp+0A0h+var_110], rdx
0x18014ae5f  mov     r12, [rdi+648h]
0x18014ae66  test    r12, r12
0x18014ae69  jz      loc_18014B54D
0x18014ae6f  mov     r13, [r12+10h]
0x18014ae74  mov     r12, [r12]
0x18014ae78  mov     [rsp+1A0h+var_150], r12
0x18014ae7d  cmp     [r13+8], rdx
0x18014ae81  jnz     loc_18014B53D
0x18014ae87  mov     rdx, rbx; pFont
0x18014ae8a  lea     this, [rsp+1A0h+dc]; this
0x18014ae8f  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18014ae94  mov     rax, [r13+10h]
0x18014ae98  cmp     dword ptr [rax-10h], 0
0x18014ae9c  jz      loc_18014AF67
0x18014aea2  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x18014aea9  jnz     short loc_18014AEC1
0x18014aeab  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18014aeb2  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18014aeb7  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18014aec1  lea     rdx, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.fontBold; pFont
0x18014aec8  lea     this, [rsp+1A0h+dc]; this
0x18014aecd  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18014aed2  mov     rbx, rax
0x18014aed5  mov     rdx, [r13+10h]; lpString
0x18014aed9  lea     r9, [rbp+0A0h+psizl]; psizl
0x18014aedd  mov     r8d, [rdx-10h]; c
0x18014aee1  mov     this, [rsp+1A0h+dc.m_hAttribDC]; hdc
0x18014aee6  call    cs:__imp_GetTextExtentPoint32W
0x18014aeec  mov     rdx, rbx; pFont
0x18014aeef  lea     this, [rsp+1A0h+dc]; this
0x18014aef4  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18014aef9  mov     r14d, [rdi+538h]
0x18014af00  cmp     r14d, 0FFFFFFFFh
0x18014af04  jnz     short loc_18014AF12
0x18014af06  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18014af0b  mov     r14d, [rax+0E4h]
0x18014af12  mov     ebx, [rdi+530h]
0x18014af18  cmp     ebx, 0FFFFFFFFh
0x18014af1b  jnz     short loc_18014AF28
0x18014af1d  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18014af22  mov     ebx, [rax+0DCh]
0x18014af28  mov     rax, [rdi]
0x18014af2b  mov     this, rdi
0x18014af2e  mov     rax, [rax+798h]
0x18014af35  call    cs:__guard_dispatch_icall_fptr
0x18014af3b  test    eax, eax
0x18014af3d  jz      short loc_18014AF5A
0x18014af3f  mov     eax, 5
0x18014af44  cmp     r14d, eax
0x18014af47  cmovl   r14d, eax
0x18014af4b  mov     eax, 12h
0x18014af50  cmp     dword ptr [rdi+530h], 0FFFFFFFFh
0x18014af57  cmovz   ebx, eax
0x18014af5a  mov     ecx, [rbp+0A0h+psizl.cy]
0x18014af5d  add     ecx, r14d
0x18014af60  cmp     ecx, ebx
0x18014af62  cmovg   ebx, ecx
0x18014af65  jmp     short loc_18014AF69
0x18014af67  xor     ebx, ebx
0x18014af69  mov     ecx, [rbp+0A0h+rectTasks.right]
0x18014af6c  mov     bCalcHeightOnly, [rbp+0A0h+rectTasks.left]
0x18014af6f  cmp     qword ptr [r13+88h], 0
0x18014af77  jz      short loc_18014AF94
0x18014af79  mov     eax, ecx
0x18014af7b  sub     eax, bCalcHeightOnly
0x18014af7d  sub     eax, ebx
0x18014af7f  cmp     [r13+7Ch], eax
0x18014af83  jge     short loc_18014AF94
0x18014af85  mov     eax, [r13+80h]
0x18014af8c  cmp     ebx, eax
0x18014af8e  jge     short loc_18014AF94
0x18014af90  sub     eax, ebx
0x18014af92  add     esi, eax
0x18014af94  test    r15d, r15d
0x18014af97  jnz     short loc_18014AFB2
0x18014af99  mov     dword ptr [rbp+0A0h+var_108], bCalcHeightOnly
0x18014af9c  mov     dword ptr [rbp+0A0h+var_108+4], esi
0x18014af9f  mov     dword ptr [rbp+0A0h+var_108+8], ecx
0x18014afa2  lea     eax, [rbx+rsi]
0x18014afa5  mov     dword ptr [rbp+0A0h+var_108+0Ch], eax
0x18014afa8  movups  xmm0, [rbp+0A0h+var_108]
0x18014afac  movdqu  xmmword ptr [r13+5Ch], xmm0
0x18014afb2  add     esi, ebx
0x18014afb4  mov     r14d, esi
0x18014afb7  mov     [rsp+1A0h+var_158], esi
0x18014afbb  lea     rdx, [rsp+1A0h+dc]; pDC
0x18014afc0  mov     this, rdi; this
0x18014afc3  call    ?SetFont@CMFCTasksPane@@IEAAPEAUHFONT__@@PEAVCDC@@@Z; CMFCTasksPane::SetFont(CDC *)
0x18014afc8  xor     bCalcHeightOnly, bCalcHeightOnly
0x18014afca  cmp     [rdi+4E0h], bCalcHeightOnly
0x18014afd0  jz      short loc_18014B050
0x18014afd2  cmp     [r13+58h], bCalcHeightOnly
0x18014afd6  jz      short loc_18014B050
0x18014afd8  mov     rax, [r13+10h]
0x18014afdc  cmp     [rax-10h], bCalcHeightOnly
0x18014afdf  jz      short loc_18014B050
0x18014afe1  cmp     [rdi+4F0h], bCalcHeightOnly
0x18014afe7  jz      short loc_18014AFFF
0x18014afe9  cmp     r13, [rdi+7B0h]
0x18014aff0  jnz     short loc_18014AFFF
0x18014aff2  cmp     [rdi+5A4h], bCalcHeightOnly
0x18014aff8  jle     short loc_18014AFFF
0x18014affa  test    r15d, r15d
0x18014affd  jz      short loc_18014B050
0x18014afff  test    r15d, r15d
0x18014b002  jnz     loc_18014B51A
0x18014b008  mov     eax, [rbp+0A0h+rectTasks.left]
0x18014b00b  mov     dword ptr [rbp+0A0h+var_F8], eax
0x18014b00e  lea     ecx, [rsi-1]
0x18014b011  mov     dword ptr [rbp+0A0h+var_F8+4], ecx
0x18014b014  mov     eax, [rbp+0A0h+rectTasks.right]
0x18014b017  mov     dword ptr [rbp+0A0h+var_F8+8], eax
0x18014b01a  mov     dword ptr [rbp+0A0h+var_F8+0Ch], ecx
0x18014b01d  movups  xmm0, [rbp+0A0h+var_F8]
0x18014b021  movdqu  xmmword ptr [r13+6Ch], xmm0
0x18014b027  mov     rbx, [r13+20h]
0x18014b02b  jmp     short loc_18014B046
0x18014b02d  mov     this, [rbx+10h]
0x18014b031  mov     rbx, [rbx]
0x18014b034  cmp     [this+40h], rdx
0x18014b038  jnz     short loc_18014B046
0x18014b03a  add     this, 18h; lprc
0x18014b03e  call    cs:__imp_SetRectEmpty
0x18014b044  xor     bCalcHeightOnly, bCalcHeightOnly
0x18014b046  test    rbx, rbx
0x18014b049  jnz     short loc_18014B02D
0x18014b04b  jmp     loc_18014B51A
0x18014b050  mov     ebx, 1
0x18014b055  mov     r12d, ebx
0x18014b058  mov     [rsp+1A0h+var_15C], ebx
0x18014b05c  mov     rax, [rdi]
0x18014b05f  lea     rdx, [rsp+1A0h+sizeGroupBorders]
0x18014b064  mov     this, rdi
0x18014b067  mov     rax, [rax+7C0h]
0x18014b06e  call    cs:__guard_dispatch_icall_fptr
0x18014b074  mov     this, [r13+20h]
0x18014b078  test    this, this
0x18014b07b  jz      loc_18014B4F3
0x18014b081  mov     r14, [this+10h]
0x18014b085  mov     this, [this]
0x18014b088  mov     [rbp+0A0h+var_C0], this
0x18014b08c  cmp     qword ptr [r14+40h], 0
0x18014b091  jnz     loc_18014B343
0x18014b097  cmp     dword ptr [r14+4Ch], 0
0x18014b09c  jz      loc_18014B2F7
0x18014b0a2  test    r12d, r12d
0x18014b0a5  jz      short loc_18014B0BF
0x18014b0a7  mov     eax, [rdi+544h]
0x18014b0ad  cmp     eax, 0FFFFFFFFh
0x18014b0b0  jnz     short loc_18014B0BD
0x18014b0b2  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18014b0b7  mov     eax, [rax+0F0h]
0x18014b0bd  add     esi, eax
0x18014b0bf  mov     r15d, [rdi+53Ch]
0x18014b0c6  cmp     r15d, 0FFFFFFFFh
0x18014b0ca  jnz     short loc_18014B0D8
0x18014b0cc  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18014b0d1  mov     r15d, [rax+0E8h]
0x18014b0d8  mov     r12d, [rdi+540h]
0x18014b0df  cmp     r12d, 0FFFFFFFFh
0x18014b0e3  jnz     short loc_18014B0F1
0x18014b0e5  call    ?GetInstance@CMFCVisualManager@@SAPEAV1@XZ; CMFCVisualManager::GetInstance(void)
0x18014b0ea  mov     r12d, [rax+0ECh]
0x18014b0f1  xor     ebx, ebx
0x18014b0f3  cmp     [r14+30h], ebx
0x18014b0f7  jnz     short loc_18014B101
0x18014b0f9  mov     eax, [rdi+500h]
0x18014b0ff  jmp     short loc_18014B107
0x18014b101  mov     eax, [rdi+4FCh]
0x18014b107  test    eax, eax
0x18014b109  jz      loc_18014B206
0x18014b10f  movaps  xmm0, xmmword ptr [rbp+0A0h+rectTasks.left]
0x18014b113  movdqa  xmmword ptr [rbp+0A0h+rectChildWnd.left], xmm0
0x18014b118  neg     r15d
0x18014b11b  xor     r8d, r8d; dy
0x18014b11e  mov     bCalcHeightOnly, r15d; dx
0x18014b121  lea     this, [rbp+0A0h+rectChildWnd]; lprc
0x18014b125  call    cs:__imp_InflateRect
0x18014b12b  mov     [rbp+0A0h+rectChildWnd.top], esi
0x18014b12e  mov     ecx, [rdi+58Ch]
0x18014b134  add     ecx, esi
0x18014b136  mov     [rbp+0A0h+rectChildWnd.bottom], ecx
0x18014b139  movaps  xmm0, xmmword ptr [rbp+0A0h+rectChildWnd.left]
0x18014b13d  movdqa  xmmword ptr [rbp+0A0h+rectText.left], xmm0
0x18014b142  mov     ecx, [rdi+588h]
0x18014b148  movd    eax, xmm0
0x18014b14c  add     ecx, eax
0x18014b14e  add     ecx, r12d
0x18014b151  mov     [rbp+0A0h+rectText.left], ecx
0x18014b154  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x18014b15a  jnz     short loc_18014B172
0x18014b15c  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18014b163  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18014b168  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18014b172  lea     rdx, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.fontUnderline; pFont
0x18014b179  lea     this, [rsp+1A0h+dc]; this
0x18014b17e  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x18014b183  mov     rbx, rax
0x18014b186  mov     this, [rsp+1A0h+dc.__vftable]
0x18014b18b  mov     rax, [this+0E0h]
  ... truncated ...
```
