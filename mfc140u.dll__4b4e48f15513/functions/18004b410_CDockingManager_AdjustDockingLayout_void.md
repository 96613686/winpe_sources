# CDockingManager::AdjustDockingLayout(void *)

- ea: `0x18004b410`
- end: `0x18004ba3c`
- name: `?AdjustDockingLayout@CDockingManager@@UEAAXPEAX@Z`
- size: `1580`
- prototype: `void __fastcall(CDockingManager *this, void *hdwp)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180047690`
- `0x18004a260`
- `0x18004b410`
- `0x18004ba40`
- `0x18004bc80`
- `0x18023f820`
- `0x180296d00`
- `0x18029a620`
- `0x1802afdb0`
- `0x1802afe10`
- `0x1802b62e0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!IsIconic` at `0x18004b4eb`
- `USER32!IsIconic` at `0x18004b4eb`
- `USER32!BeginDeferWindowPos` at `0x18004b52b`
- `USER32!BeginDeferWindowPos` at `0x18004b52b`
- `USER32!EndDeferWindowPos` at `0x18004b9de`
- `USER32!EndDeferWindowPos` at `0x18004b9de`
- `USER32!GetClientRect` at `0x18004b481`
- `USER32!GetClientRect` at `0x18004b553`
- `USER32!GetClientRect` at `0x18004b481`
- `USER32!GetClientRect` at `0x18004b553`
- `USER32!GetWindowRect` at `0x18004b674`
- `USER32!GetWindowRect` at `0x18004b674`
- `USER32!IsWindow` at `0x18004b4dd`
- `USER32!IsWindow` at `0x18004b4dd`
- `USER32!IsRectEmpty` at `0x18004b48e`
- `USER32!IsRectEmpty` at `0x18004b55c`
- `USER32!IsRectEmpty` at `0x18004b930`
- `USER32!IsRectEmpty` at `0x18004b48e`
- `USER32!IsRectEmpty` at `0x18004b55c`
- `USER32!IsRectEmpty` at `0x18004b930`
- `USER32!EqualRect` at `0x18004b984`
- `USER32!EqualRect` at `0x18004b984`
- `USER32!GetParent` at `0x18004b825`
- `USER32!GetParent` at `0x18004b825`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __fastcall CDockingManager::AdjustDockingLayout(CDockingManager *this, void *hdwp)
{
  CFrameWnd *m_pParentWnd; // rcx
  CRect *p_m_rectClientAreaBounds; // r14
  CRect *p_m_rectInPlace; // rsi
  CFrameWnd *TopLevelFrame; // rdi
  HWND m_hWnd; // rcx
  CRect *p_m_rectOuterEdgeBounds; // r12
  CRect m_rectOuterEdgeBounds; // xmm0
  CFrameWnd *v10; // rcx
  CObList::CNode *m_pNodeTail; // rsi
  CObList::CNode *v12; // rdi
  CObject *data; // rdi
  CObList::CNode *m_pNodeHead; // r15
  CWnd *v15; // rdi
  CFrameWnd *v16; // rax
  unsigned int v17; // r14d
  unsigned int bHorizontal; // r13d
  int IsKindOf; // eax
  __m128i v20; // xmm6
  HWND Parent; // rax
  CWnd *v22; // rax
  CFrameWnd *v23; // rax
  CObList::CNode *v24; // rdi
  CObject *v25; // rsi
  CFrameWnd *v26; // rcx
  HDWP hWinPosInfo; // [rsp+58h] [rbp-49h] BYREF
  CSize sizeRequered; // [rsp+60h] [rbp-41h]
  int v29; // [rsp+68h] [rbp-39h] BYREF
  int v30; // [rsp+6Ch] [rbp-35h]
  _BYTE rectControlBar[56]; // [rsp+70h] [rbp-31h] OVERLAPPED BYREF

  hWinPosInfo = hdwp;
  if ( !CDockingManager::m_bDisableRecalcLayout && !this->m_bAdjustingBarLayout )
  {
    m_pParentWnd = this->m_pParentWnd;
    if ( m_pParentWnd )
    {
      p_m_rectClientAreaBounds = &this->m_rectClientAreaBounds;
      GetClientRect(m_pParentWnd->m_hWnd, &this->m_rectClientAreaBounds);
      p_m_rectInPlace = &this->m_rectInPlace;
      if ( !IsRectEmpty(&this->m_rectInPlace) )
        *p_m_rectClientAreaBounds = *p_m_rectInPlace;
      if ( this->m_bEnableAdjustLayout
        && this->m_lstControlBars.m_nCount
        && ((TopLevelFrame = g_pTopLevelFrame) == 0 && (TopLevelFrame = CWnd::GetTopLevelFrame(this->m_pParentWnd)) == 0
         || (m_hWnd = TopLevelFrame->m_hWnd) == 0
         || !IsWindow(m_hWnd)
         || !IsIconic(TopLevelFrame->m_hWnd)) )
      {
        p_m_rectOuterEdgeBounds = &this->m_rectOuterEdgeBounds;
        m_rectOuterEdgeBounds = this->m_rectOuterEdgeBounds;
        this->m_bAdjustingBarLayout = 1;
        sizeRequered.cx = 0;
        *(CRect *)&rectControlBar[40] = m_rectOuterEdgeBounds;
        if ( !hWinPosInfo && !this->m_bIsPrintPreviewMode )
        {
          hWinPosInfo = BeginDeferWindowPos(this->m_lstControlBars.m_nCount);
          sizeRequered.cx = 1;
        }
        v10 = this->m_pParentWnd;
        *(CRect *)&rectControlBar[24] = this->m_rectDockBarBounds;
        GetClientRect(v10->m_hWnd, (LPRECT)&rectControlBar[24]);
        if ( !IsRectEmpty(&this->m_rectInPlace) )
          *(CRect *)&rectControlBar[24] = *p_m_rectInPlace;
        CWnd::ClientToScreen(this->m_pParentWnd, (tagRECT *)&rectControlBar[24]);
        m_pNodeTail = this->m_lstControlBars.m_pNodeTail;
        *(_OWORD *)&rectControlBar[8] = 0;
        if ( m_pNodeTail )
        {
          while ( 1 )
          {
            v12 = m_pNodeTail;
            m_pNodeTail = m_pNodeTail->pPrev;
            if ( !m_pNodeTail )
              break;
            data = v12->data;
            if ( CObject::IsKindOf(data, &CDockSite::classCDockSite)
              || CObject::IsKindOf(data, &CAutoHideDockSite::classCAutoHideDockSite) )
            {
              m_pNodeTail = m_pNodeTail->pNext;
              if ( m_pNodeTail )
                m_pNodeTail = m_pNodeTail->pNext;
              break;
            }
          }
        }
        m_pNodeHead = this->m_lstControlBars.m_pNodeHead;
        if ( m_pNodeHead )
        {
          do
          {
            v15 = (CWnd *)m_pNodeHead->data;
            m_pNodeHead = m_pNodeHead->pNext;
            if ( (CWnd::GetStyle(v15) & 0x10000000) == 0 )
            {
              if ( CObject::IsKindOf(v15, &CPane::classCPane)
                || CObject::IsKindOf(v15, &CPaneDivider::classCPaneDivider) )
              {
                continue;
              }
              if ( CObject::IsKindOf(v15, &CDockSite::classCDockSite) )
              {
                if ( this->m_bIsPrintPreviewMode )
                  continue;
                v16 = this->m_pParentWnd;
                if ( v16 )
                {
                  if ( v16->m_hWnd && v16->m_pNotifyHook )
                    continue;
                }
                if ( this->m_bHiddenForOLE )
                  continue;
              }
            }
            GetWindowRect(v15->m_hWnd, (LPRECT)&rectControlBar[8]);
            v17 = (unsigned int)v15->__vftable[1].GetMessageMap(v15);
            bHorizontal = (unsigned int)v15->__vftable[1].GetRuntimeClass(v15);
            *(_DWORD *)rectControlBar = ((__int64 (__fastcall *)(CWnd *))v15->__vftable[1].OnCmdMsg)(v15);
            if ( CObject::IsKindOf(v15, &CDockablePane::classCDockablePane) )
            {
              IsKindOf = CObject::IsKindOf(v15, &CDockablePane::classCDockablePane);
              if ( CDockablePane::GetDefaultPaneDivider((CDockablePane *)((unsigned __int64)v15
                                                                        & -(__int64)(IsKindOf != 0))) )
                continue;
            }
            ((void (__fastcall *)(CWnd *, int *, _QWORD, _QWORD))v15->__vftable[1].OnCommand)(v15, &v29, 0, bHorizontal);
            if ( bHorizontal )
            {
              if ( (v17 & 0x2000) != 0 )
                *(_DWORD *)&rectControlBar[20] = v30 + *(_DWORD *)&rectControlBar[12];
              else
                *(_DWORD *)&rectControlBar[12] = *(_DWORD *)&rectControlBar[20] - v30;
            }
            else if ( (v17 & 0x1000) != 0 )
            {
              *(_DWORD *)&rectControlBar[16] = *(_DWORD *)&rectControlBar[8] + v29;
            }
            else
            {
              *(_DWORD *)&rectControlBar[8] = *(_DWORD *)&rectControlBar[16] - v29;
            }
            CDockingManager::AlignByRect(
              this,
              (const CRect *)&rectControlBar[24],
              (CRect *)&rectControlBar[8],
              v17,
              bHorizontal,
              *(int *)rectControlBar);
            v20 = *(__m128i *)&rectControlBar[8];
            if ( CObject::IsKindOf(v15, &CDockSite::classCDockSite) )
            {
              CWnd::ScreenToClient(v15, (tagRECT *)&rectControlBar[8]);
              if ( v15->__vftable[1].GetRuntimeClass(v15)
                && *(_DWORD *)&rectControlBar[16] - *(_DWORD *)&rectControlBar[8] > 0
                || !v15->__vftable[1].GetRuntimeClass(v15)
                && *(_DWORD *)&rectControlBar[20] - *(_DWORD *)&rectControlBar[12] > 0 )
              {
                ((void (__fastcall *)(CWnd *, _BYTE *))v15->__vftable[1].OnTouchInput)(v15, &rectControlBar[8]);
              }
              *(__m128i *)&rectControlBar[8] = v20;
            }
            if ( CObject::IsKindOf(v15, &CPaneDivider::classCPaneDivider) )
            {
              ((void (__fastcall *)(CWnd *, _BYTE *, HDWP *))v15->__vftable[1].OnWndMsg)(
                v15,
                &rectControlBar[8],
                &hWinPosInfo);
            }
            else
            {
              Parent = GetParent(v15->m_hWnd);
              v22 = CWnd::FromHandle(Parent);
              CWnd::ScreenToClient(v22, (tagRECT *)&rectControlBar[8]);
              hWinPosInfo = (HDWP)((__int64 (__fastcall *)(CWnd *, _QWORD))v15->__vftable[1].get_accDefaultAction)(
                                    v15,
                                    0);
            }
            if ( (v17 & 0x2000) != 0 )
            {
              *(_DWORD *)&rectControlBar[28] += _mm_cvtsi128_si32(_mm_srli_si128(v20, 12))
                                              - _mm_cvtsi128_si32(_mm_srli_si128(v20, 4));
            }
            else if ( (v17 & 0x8000) != 0 )
            {
              *(_DWORD *)&rectControlBar[36] += _mm_cvtsi128_si32(_mm_srli_si128(v20, 4))
                                              - _mm_cvtsi128_si32(_mm_srli_si128(v20, 12));
            }
            else if ( (v17 & 0x1000) != 0 )
            {
              *(_DWORD *)&rectControlBar[24] += _mm_cvtsi128_si32(_mm_srli_si128(v20, 8)) - _mm_cvtsi128_si32(v20);
            }
            else
            {
              *(_DWORD *)&rectControlBar[32] += _mm_cvtsi128_si32(v20) - _mm_cvtsi128_si32(_mm_srli_si128(v20, 8));
            }
            if ( m_pNodeTail == m_pNodeHead )
              *p_m_rectOuterEdgeBounds = *(CRect *)&rectControlBar[24];
          }
          while ( m_pNodeHead );
          p_m_rectClientAreaBounds = &this->m_rectClientAreaBounds;
        }
        *p_m_rectClientAreaBounds = *(CRect *)&rectControlBar[24];
        if ( IsRectEmpty(&this->m_rectOuterEdgeBounds)
          || (v23 = this->m_pParentWnd) != 0 && v23->m_hWnd && v23->m_pNotifyHook )
        {
          *p_m_rectOuterEdgeBounds = *(CRect *)&rectControlBar[24];
        }
        CWnd::ScreenToClient(this->m_pParentWnd, p_m_rectClientAreaBounds);
        CWnd::ScreenToClient(this->m_pParentWnd, &this->m_rectOuterEdgeBounds);
        if ( !EqualRect(&this->m_rectOuterEdgeBounds, (const RECT *)&rectControlBar[40]) )
          CDockingManager::HideAutoHidePanes(this, 0, 1);
        v24 = this->m_lstControlBars.m_pNodeHead;
        while ( v24 )
        {
          v25 = v24->data;
          v24 = v24->pNext;
          if ( CObject::IsKindOf(v25, &CAutoHideDockSite::classCAutoHideDockSite) )
          {
            v25[68].__vftable = 0;
            CDockingManager::CalcPaneOffset(this, (CAutoHideDockSite *)v25);
          }
        }
        if ( sizeRequered.cx )
          EndDeferWindowPos(hWinPosInfo);
        v26 = this->m_pParentWnd;
        if ( v26->m_pNotifyHook )
          v26->RecalcLayout(v26, 1);
        this->m_bAdjustingBarLayout = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x18004b410  mov     rax, rsp
0x18004b413  mov     [rax+18h], rbx
0x18004b417  push    rbp
0x18004b418  push    rsi
0x18004b419  push    rdi
0x18004b41a  push    r12
0x18004b41c  push    r13
0x18004b41e  push    r14
0x18004b420  push    r15
0x18004b422  lea     rbp, [rax-5Fh]
0x18004b426  sub     rsp, 0C0h
0x18004b42d  movaps  xmmword ptr [rax-48h], xmm6
0x18004b431  mov     rax, cs:__security_cookie
0x18004b438  xor     rax, rsp
0x18004b43b  mov     [rbp+57h+var_50], rax
0x18004b43f  xor     r13d, r13d
0x18004b442  mov     [rbp+57h+hWinPosInfo], hdwp
0x18004b446  cmp     cs:?m_bDisableRecalcLayout@CDockingManager@@2HA, r13d; int CDockingManager::m_bDisableRecalcLayout
0x18004b44d  mov     rbx, this
0x18004b450  jnz     loc_18004BA10
0x18004b456  cmp     [this+250h], r13d
0x18004b45d  jnz     loc_18004BA10
0x18004b463  mov     this, [this+1B0h]
0x18004b46a  test    this, this
0x18004b46d  jz      loc_18004BA10
0x18004b473  mov     this, [this+40h]; hWnd
0x18004b477  lea     r14, [rbx+1C8h]
0x18004b47e  mov     hdwp, r14; lpRect
0x18004b481  call    cs:__imp_GetClientRect
0x18004b487  lea     rsi, [rbx+14h]
0x18004b48b  mov     this, rsi; lprc
0x18004b48e  call    cs:__imp_IsRectEmpty
0x18004b494  test    eax, eax
0x18004b496  jnz     short loc_18004B4A0
0x18004b498  movups  xmm0, xmmword ptr [rsi]
0x18004b49b  movdqu  xmmword ptr [r14], xmm0
0x18004b4a0  cmp     [rbx+8], r13d
0x18004b4a4  jz      loc_18004BA10
0x18004b4aa  cmp     [rbx+40h], r13
0x18004b4ae  jz      loc_18004BA10
0x18004b4b4  mov     rdi, cs:?g_pTopLevelFrame@@3PEAVCFrameWnd@@EA; CFrameWnd * g_pTopLevelFrame
0x18004b4bb  test    rdi, rdi
0x18004b4be  jnz     short loc_18004B4D4
0x18004b4c0  mov     this, [rbx+1B0h]; this
0x18004b4c7  call    ?GetTopLevelFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetTopLevelFrame(void)
0x18004b4cc  mov     rdi, rax
0x18004b4cf  test    rax, rax
0x18004b4d2  jz      short loc_18004B4F9
0x18004b4d4  mov     this, [rdi+40h]; hWnd
0x18004b4d8  test    this, this
0x18004b4db  jz      short loc_18004B4F9
0x18004b4dd  call    cs:__imp_IsWindow
0x18004b4e3  test    eax, eax
0x18004b4e5  jz      short loc_18004B4F9
0x18004b4e7  mov     this, [rdi+40h]; hWnd
0x18004b4eb  call    cs:__imp_IsIconic
0x18004b4f1  test    eax, eax
0x18004b4f3  jnz     loc_18004BA10
0x18004b4f9  lea     r12, [rbx+1D8h]
0x18004b500  mov     edi, 1
0x18004b505  movups  xmm0, xmmword ptr [r12]
0x18004b50a  mov     [rbx+250h], edi
0x18004b510  mov     [rbp+57h+sizeRequered.cx], r13d
0x18004b514  movdqu  xmmword ptr [rbp+57h+rectSaveOuterEdgeBounds.right], xmm0
0x18004b519  cmp     [rbp+57h+hWinPosInfo], r13
0x18004b51d  jnz     short loc_18004B538
0x18004b51f  cmp     [rbx+208h], r13d
0x18004b526  jnz     short loc_18004B538
0x18004b528  mov     ecx, [rbx+40h]; nNumWindows
0x18004b52b  call    cs:__imp_BeginDeferWindowPos
0x18004b531  mov     [rbp+57h+hWinPosInfo], rax
0x18004b535  mov     [rbp+57h+sizeRequered.cx], edi
0x18004b538  movups  xmm0, xmmword ptr [rbx+1B8h]
0x18004b53f  mov     this, [rbx+1B0h]
0x18004b546  lea     hdwp, [rbp+57h+rectCurrBounds.right]; lpRect
0x18004b54a  movdqu  xmmword ptr [rbp+57h+rectCurrBounds.right], xmm0
0x18004b54f  mov     this, [this+40h]; hWnd
0x18004b553  call    cs:__imp_GetClientRect
0x18004b559  mov     this, rsi; lprc
0x18004b55c  call    cs:__imp_IsRectEmpty
0x18004b562  test    eax, eax
0x18004b564  jnz     short loc_18004B56E
0x18004b566  movups  xmm0, xmmword ptr [rsi]
0x18004b569  movdqu  xmmword ptr [rbp+57h+rectCurrBounds.right], xmm0
0x18004b56e  mov     this, [rbx+1B0h]; this
0x18004b575  lea     hdwp, [rbp+57h+rectCurrBounds.right]; lpRect
0x18004b579  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x18004b57e  mov     rsi, [rbx+38h]
0x18004b582  xorps   xmm0, xmm0
0x18004b585  movdqa  xmmword ptr [rbp+57h+rectControlBar.right], xmm0
0x18004b58a  test    rsi, rsi
0x18004b58d  jz      short loc_18004B5D0
0x18004b58f  lea     rdi, [rsi]
0x18004b592  mov     rsi, [rsi+8]
0x18004b596  test    rsi, rsi
0x18004b599  jz      short loc_18004B5D0
0x18004b59b  mov     rdi, [rdi+10h]
0x18004b59f  lea     hdwp, ?classCDockSite@CDockSite@@2UCRuntimeClass@@B; pClass
0x18004b5a6  mov     this, rdi; this
0x18004b5a9  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b5ae  test    eax, eax
0x18004b5b0  jnz     short loc_18004B5C5
0x18004b5b2  lea     hdwp, ?classCAutoHideDockSite@CAutoHideDockSite@@2UCRuntimeClass@@B; pClass
0x18004b5b9  mov     this, rdi; this
0x18004b5bc  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b5c1  test    eax, eax
0x18004b5c3  jz      short loc_18004B58F
0x18004b5c5  mov     rsi, [rsi]
0x18004b5c8  test    rsi, rsi
0x18004b5cb  jz      short loc_18004B5D0
0x18004b5cd  mov     rsi, [rsi]
0x18004b5d0  mov     r15, [rbx+30h]
0x18004b5d4  test    r15, r15
0x18004b5d7  jz      loc_18004B924
0x18004b5dd  mov     rdi, [r15+10h]
0x18004b5e1  mov     r15, [r15]
0x18004b5e4  mov     this, rdi; this
0x18004b5e7  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x18004b5ec  bt      eax, 1Ch
0x18004b5f0  jb      short loc_18004B66C
0x18004b5f2  lea     hdwp, ?classCPane@CPane@@2UCRuntimeClass@@B; pClass
0x18004b5f9  mov     this, rdi; this
0x18004b5fc  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b601  test    eax, eax
0x18004b603  jnz     loc_18004B914
0x18004b609  lea     hdwp, ?classCPaneDivider@CPaneDivider@@2UCRuntimeClass@@B; pClass
0x18004b610  mov     this, rdi; this
0x18004b613  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b618  test    eax, eax
0x18004b61a  jnz     loc_18004B914
0x18004b620  lea     hdwp, ?classCDockSite@CDockSite@@2UCRuntimeClass@@B; pClass
0x18004b627  mov     this, rdi; this
0x18004b62a  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b62f  test    eax, eax
0x18004b631  jz      short loc_18004B66C
0x18004b633  cmp     [rbx+208h], r13d
0x18004b63a  jnz     loc_18004B914
0x18004b640  mov     rax, [rbx+1B0h]
0x18004b647  test    rax, rax
0x18004b64a  jz      short loc_18004B65F
0x18004b64c  cmp     [rax+40h], r13
0x18004b650  jz      short loc_18004B65F
0x18004b652  cmp     [rax+120h], r13
0x18004b659  jnz     loc_18004B914
0x18004b65f  cmp     [rbx+354h], r13d
0x18004b666  jnz     loc_18004B914
0x18004b66c  mov     this, [rdi+40h]; hWnd
0x18004b670  lea     hdwp, [rbp+57h+rectControlBar.right]; lpRect
0x18004b674  call    cs:__imp_GetWindowRect
0x18004b67a  mov     rax, [rdi]
0x18004b67d  mov     this, rdi
0x18004b680  mov     rax, [rax+338h]
0x18004b687  call    cs:__guard_dispatch_icall_fptr
0x18004b68d  mov     this, [rdi]
0x18004b690  mov     r14d, eax
0x18004b693  mov     rax, [this+2D8h]
0x18004b69a  mov     this, rdi
0x18004b69d  call    cs:__guard_dispatch_icall_fptr
0x18004b6a3  mov     this, [rdi]
0x18004b6a6  mov     r13d, eax
0x18004b6a9  mov     rax, [this+300h]
0x18004b6b0  mov     this, rdi
0x18004b6b3  call    cs:__guard_dispatch_icall_fptr
0x18004b6b9  lea     hdwp, ?classCDockablePane@CDockablePane@@2UCRuntimeClass@@A; pClass
0x18004b6c0  mov     this, rdi; this
0x18004b6c3  mov     [rbp+57h+rectControlBar.left], eax
0x18004b6c6  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b6cb  test    eax, eax
0x18004b6cd  jz      short loc_18004B6F4
0x18004b6cf  lea     hdwp, ?classCDockablePane@CDockablePane@@2UCRuntimeClass@@A; pClass
0x18004b6d6  mov     this, rdi; this
0x18004b6d9  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b6de  neg     eax
0x18004b6e0  sbb     this, this
0x18004b6e3  and     this, rdi; this
0x18004b6e6  call    ?GetDefaultPaneDivider@CDockablePane@@QEBAPEAVCPaneDivider@@XZ; CDockablePane::GetDefaultPaneDivider(void)
0x18004b6eb  test    rax, rax
0x18004b6ee  jnz     loc_18004B911
0x18004b6f4  mov     rax, [rdi]
0x18004b6f7  lea     hdwp, [rbp+57h+var_90]
0x18004b6fb  mov     r9d, r13d
0x18004b6fe  xor     r8d, r8d
0x18004b701  mov     this, rdi
0x18004b704  mov     rax, [rax+4D0h]
0x18004b70b  call    cs:__guard_dispatch_icall_fptr
0x18004b711  test    r13d, r13d
0x18004b714  jz      short loc_18004B733
0x18004b716  bt      r14d, 0Dh
0x18004b71b  jnb     short loc_18004B728
0x18004b71d  mov     ecx, [rbp+57h+rectControlBar.bottom]
0x18004b720  add     ecx, [rbp+57h+var_8C]
0x18004b723  mov     [rbp+57h+rectCurrBounds.top], ecx
0x18004b726  jmp     short loc_18004B74E
0x18004b728  mov     eax, [rbp+57h+rectCurrBounds.top]
0x18004b72b  sub     eax, [rbp+57h+var_8C]
0x18004b72e  mov     [rbp+57h+rectControlBar.bottom], eax
0x18004b731  jmp     short loc_18004B74E
0x18004b733  bt      r14d, 0Ch
0x18004b738  jnb     short loc_18004B745
0x18004b73a  mov     ecx, [rbp+57h+var_90]
0x18004b73d  add     ecx, [rbp+57h+rectControlBar.right]
0x18004b740  mov     [rbp+57h+rectCurrBounds.left], ecx
0x18004b743  jmp     short loc_18004B74E
0x18004b745  mov     eax, [rbp+57h+rectCurrBounds.left]
0x18004b748  sub     eax, [rbp+57h+var_90]
0x18004b74b  mov     [rbp+57h+rectControlBar.right], eax
0x18004b74e  mov     eax, [rbp+57h+rectControlBar.left]
0x18004b751  lea     r8, [rbp+57h+rectControlBar.right]; rectResult
0x18004b755  mov     [rsp+0F0h+bResizable], eax; bResizable
0x18004b759  lea     hdwp, [rbp+57h+rectCurrBounds.right]; rectToAlignBy
0x18004b75d  mov     r9d, r14d; dwAlignment
0x18004b760  mov     [rsp+0F0h+bHorizontal], r13d; bHorizontal
0x18004b765  mov     this, rbx; this
0x18004b768  call    ?AlignByRect@CDockingManager@@IEAAXAEBVCRect@@AEAV2@KHH@Z; CDockingManager::AlignByRect(CRect const &,CRect &,ulong,int,int)
0x18004b76d  movaps  xmm6, xmmword ptr [rbp+57h+rectControlBar.right]
0x18004b771  lea     hdwp, ?classCDockSite@CDockSite@@2UCRuntimeClass@@B; pClass
0x18004b778  mov     this, rdi; this
0x18004b77b  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b780  xor     r13d, r13d
0x18004b783  test    eax, eax
0x18004b785  jz      short loc_18004B7F1
0x18004b787  lea     hdwp, [rbp+57h+rectControlBar.right]; lpRect
0x18004b78b  mov     this, rdi; this
0x18004b78e  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x18004b793  mov     rax, [rdi]
0x18004b796  mov     this, rdi
0x18004b799  mov     rax, [rax+2D8h]
0x18004b7a0  call    cs:__guard_dispatch_icall_fptr
0x18004b7a6  test    eax, eax
0x18004b7a8  jz      short loc_18004B7B4
0x18004b7aa  mov     eax, [rbp+57h+rectCurrBounds.left]
0x18004b7ad  sub     eax, [rbp+57h+rectControlBar.right]
0x18004b7b0  test    eax, eax
0x18004b7b2  jg      short loc_18004B7D5
0x18004b7b4  mov     rax, [rdi]
0x18004b7b7  mov     this, rdi
0x18004b7ba  mov     rax, [rax+2D8h]
0x18004b7c1  call    cs:__guard_dispatch_icall_fptr
0x18004b7c7  test    eax, eax
0x18004b7c9  jnz     short loc_18004B7EC
0x18004b7cb  mov     eax, [rbp+57h+rectCurrBounds.top]
0x18004b7ce  sub     eax, [rbp+57h+rectControlBar.bottom]
0x18004b7d1  test    eax, eax
0x18004b7d3  jle     short loc_18004B7EC
0x18004b7d5  mov     rax, [rdi]
0x18004b7d8  lea     hdwp, [rbp+57h+rectControlBar.right]
0x18004b7dc  mov     this, rdi
0x18004b7df  mov     rax, [rax+540h]
0x18004b7e6  call    cs:__guard_dispatch_icall_fptr
0x18004b7ec  movdqa  xmmword ptr [rbp+57h+rectControlBar.right], xmm6
0x18004b7f1  lea     hdwp, ?classCPaneDivider@CPaneDivider@@2UCRuntimeClass@@B; pClass
0x18004b7f8  mov     this, rdi; this
0x18004b7fb  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x18004b800  test    eax, eax
0x18004b802  jz      short loc_18004B821
0x18004b804  mov     rax, [rdi]
0x18004b807  lea     r8, [rbp+57h+hWinPosInfo]
0x18004b80b  lea     hdwp, [rbp+57h+rectControlBar.right]
0x18004b80f  mov     this, rdi
0x18004b812  mov     rax, [rax+518h]
0x18004b819  call    cs:__guard_dispatch_icall_fptr
0x18004b81f  jmp     short loc_18004B887
0x18004b821  mov     this, [rdi+40h]; hWnd
0x18004b825  call    cs:__imp_GetParent
0x18004b82b  mov     this, rax; hWnd
0x18004b82e  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18004b833  lea     hdwp, [rbp+57h+rectControlBar.right]; lpRect
0x18004b837  mov     this, rax; this
0x18004b83a  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x18004b83f  mov     this, [rbp+57h+hWinPosInfo]
0x18004b843  mov     edx, [rbp+57h+rectCurrBounds.left]
0x18004b846  mov     r10d, [rbp+57h+rectCurrBounds.top]
0x18004b84a  mov     rax, [rdi]
0x18004b84d  mov     r9d, [rbp+57h+rectControlBar.bottom]
0x18004b851  sub     r10d, r9d
0x18004b854  mov     r8d, [rbp+57h+rectControlBar.right]
0x18004b858  sub     edx, r8d
0x18004b85b  mov     [rsp+0F0h+var_B8], this
0x18004b860  mov     this, rdi
0x18004b863  mov     rax, [rax+480h]
0x18004b86a  mov     dword ptr [rsp+0F0h+var_C0], 14h
0x18004b872  mov     [rsp+0F0h+bResizable], r10d
0x18004b877  mov     [rsp+0F0h+bHorizontal], edx
0x18004b87b  xor     edx, edx
0x18004b87d  call    cs:__guard_dispatch_icall_fptr
0x18004b883  mov     [rbp+57h+hWinPosInfo], rax
0x18004b887  bt      r14d, 0Dh
0x18004b88c  jnb     short loc_18004B8AB
0x18004b88e  movdqa  xmm0, xmm6
0x18004b892  psrldq  xmm6, 4
0x18004b897  psrldq  xmm0, 0Ch
0x18004b89c  movd    ecx, xmm0
0x18004b8a0  movd    eax, xmm6
0x18004b8a4  sub     ecx, eax
0x18004b8a6  add     [rbp+57h+rectCurrBounds.bottom], ecx
0x18004b8a9  jmp     short loc_18004B900
0x18004b8ab  bt      r14d, 0Fh
0x18004b8b0  jnb     short loc_18004B8CF
0x18004b8b2  movdqa  xmm0, xmm6
0x18004b8b6  psrldq  xmm6, 0Ch
  ... truncated ...
```
