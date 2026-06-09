# CMFCPopupMenuBar::OnKey(uint)

- ea: `0x1800c13f0`
- end: `0x1800c1a0a`
- name: `?OnKey@CMFCPopupMenuBar@@MEAAHI@Z`
- size: `1562`
- prototype: `int __fastcall(CMFCPopupMenuBar *this, unsigned int nChar)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800281b0`

## callees

- `0x180024200`
- `0x180076790`
- `0x180076860`
- `0x1800bf7e0`
- `0x1800c13f0`
- `0x1800c33d4`
- `0x180231d70`
- `0x18023f820`
- `0x180296d00`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!GetKeyState` at `0x1800c146c`
- `USER32!GetKeyState` at `0x1800c146c`
- `USER32!GetClientRect` at `0x1800c182c`
- `USER32!GetClientRect` at `0x1800c182c`
- `USER32!SendMessageW` at `0x1800c15bc`
- `USER32!SendMessageW` at `0x1800c19c1`
- `USER32!SendMessageW` at `0x1800c15bc`
- `USER32!SendMessageW` at `0x1800c19c1`
- `USER32!InvalidateRect` at `0x1800c186e`
- `USER32!InvalidateRect` at `0x1800c1882`
- `USER32!InvalidateRect` at `0x1800c186e`
- `USER32!InvalidateRect` at `0x1800c1882`
- `USER32!GetAsyncKeyState` at `0x1800c14e3`
- `USER32!GetAsyncKeyState` at `0x1800c14e3`
- `USER32!IsRectEmpty` at `0x1800c16cc`
- `USER32!IsRectEmpty` at `0x1800c1789`
- `USER32!IsRectEmpty` at `0x1800c16cc`
- `USER32!IsRectEmpty` at `0x1800c1789`
- `USER32!GetParent` at `0x1800c19a1`
- `USER32!GetParent` at `0x1800c19a1`
- `USER32!UpdateWindow` at `0x1800c188c`
- `USER32!UpdateWindow` at `0x1800c188c`

## pseudocode

```c
__int64 __fastcall CMFCPopupMenuBar::OnKey(CMFCPopupMenuBar *this, unsigned int nChar)
{
  __int64 m_iHighlighted; // r14
  unsigned int v3; // esi
  __int64 v5; // rax
  CObList::CNode *m_pNodeHead; // rdi
  CMFCToolBarButton *data; // r15
  int v8; // r12d
  char KeyState; // al
  CObList::CNode *v10; // rdx
  int v11; // ecx
  CMap<unsigned int,unsigned int &,CMFCToolBarButton *,CMFCToolBarButton * &>::CAssoc *v12; // rax
  CMFCToolBarButton *value; // rsi
  int v14; // edx
  CObList::CNode *v15; // rcx
  CObList::CNode *v16; // rax
  wchar_t *m_pszData; // rcx
  CMFCPopupMenuBar *v18; // rcx
  const CMFCToolBarButton *v19; // r8
  unsigned int v20; // edx
  CMap<int,int,unsigned int,unsigned int>::CAssoc *AssocAt; // rax
  CObList::CNode *pNext; // rsi
  CObList::CNode *v23; // rcx
  CObList::CNode *v24; // r12
  CObject *v25; // r13
  CObList::CNode *m_pNodeTail; // rsi
  CObject *v27; // r13
  HWND__ *m_hWnd; // rcx
  CRect m_rect; // xmm0
  __int64 v30; // rax
  unsigned int v31; // edi
  int v32; // r15d
  int v33; // r14d
  int v34; // edx
  HWND__ *m_hWndOwner; // rax
  CWnd *v37; // rax
  unsigned int v38; // [rsp+20h] [rbp-40h]
  unsigned int nUpperChar; // [rsp+28h] [rbp-38h] BYREF
  unsigned int nHashValue; // [rsp+30h] [rbp-30h] BYREF
  unsigned int nHashBucket; // [rsp+34h] [rbp-2Ch] BYREF
  CRect rectClient; // [rsp+38h] [rbp-28h] BYREF
  CRect rectNew; // [rsp+48h] [rbp-18h] BYREF

  m_iHighlighted = this->m_iHighlighted;
  v38 = 0;
  v3 = nChar;
  if ( (int)m_iHighlighted < 0 || (v5 = this->m_iHighlighted, m_iHighlighted >= this->m_Buttons.m_nCount) )
  {
    m_pNodeHead = 0;
  }
  else
  {
    m_pNodeHead = this->m_Buttons.m_pNodeHead;
    if ( (_DWORD)m_iHighlighted )
    {
      do
      {
        m_pNodeHead = m_pNodeHead->pNext;
        --v5;
      }
      while ( v5 );
    }
    if ( m_pNodeHead )
    {
      data = (CMFCToolBarButton *)m_pNodeHead->data;
      goto LABEL_9;
    }
  }
  data = 0;
LABEL_9:
  v8 = 0;
  if ( nChar == 9 )
  {
    KeyState = GetKeyState(16);
    v10 = m_pNodeHead;
    if ( KeyState < 0 )
    {
      v11 = 38;
LABEL_65:
      if ( !this->m_bDropDownListMode || v10 != this->m_Buttons.m_pNodeHead || v11 == 35 )
      {
        v38 = 1;
        if ( this->m_Buttons.m_nCount )
        {
          if ( !m_pNodeHead || (m_pNodeTail = m_pNodeHead->pPrev) == 0 )
          {
            m_pNodeTail = this->m_Buttons.m_pNodeTail;
            LODWORD(m_iHighlighted) = this->m_Buttons.m_nCount;
          }
          LODWORD(m_iHighlighted) = m_iHighlighted - 1;
          if ( m_pNodeTail != m_pNodeHead )
          {
            while ( 1 )
            {
              v24 = m_pNodeTail;
              if ( !m_pNodeTail )
                break;
              v27 = m_pNodeTail->data;
              m_pNodeTail = m_pNodeTail->pPrev;
              if ( ((__int64)v27[5].__vftable & 1) != 0
                || IsRectEmpty((const RECT *)&v27[13])
                || HIDWORD(v27[4].__vftable) == -2 )
              {
                LODWORD(m_iHighlighted) = m_iHighlighted - 1;
                if ( !m_pNodeTail )
                {
                  if ( this->m_bDropDownListMode )
                    return 1;
                  m_pNodeTail = this->m_Buttons.m_pNodeTail;
                  LODWORD(m_iHighlighted) = LODWORD(this->m_Buttons.m_nCount) - 1;
                }
                if ( m_pNodeTail != m_pNodeHead )
                  continue;
              }
              goto LABEL_81;
            }
LABEL_111:
            AfxThrowInvalidArgException();
          }
        }
        return v38;
      }
      return 1;
    }
    v11 = 40;
  }
  else
  {
    v10 = m_pNodeHead;
    v11 = v3;
    switch ( v3 )
    {
      case 0xDu:
        v38 = 1;
        if ( data
          && CObject::IsKindOf(data, &CMFCToolBarMenuButton::classCMFCToolBarMenuButton)
          && (((unsigned int (__fastcall *)(CMFCToolBarButton *))data->__vftable[1].OnCalculateSize)(data)
           || !((unsigned int (__fastcall *)(CMFCToolBarButton *, _QWORD))data->__vftable[1].GetRuntimeClass)(data, 0)) )
        {
          m_hWndOwner = this->m_hWndOwner;
          if ( !m_hWndOwner )
            m_hWndOwner = GetParent(this->m_hWnd);
          v37 = CWnd::FromHandle(m_hWndOwner);
          SendMessageW(v37->m_hWnd, 0x362u, 0xE001u, 0);
          this->OnSendCommand(this, data);
        }
        return v38;
      case 0x21u:
      case 0x22u:
        if ( this->m_bDropDownListMode && this->m_nDropDownPageSize > 0 )
        {
          v31 = 40;
          this->m_bInScrollMode = 1;
          v32 = m_iHighlighted;
          v33 = 0;
          if ( v3 == 33 )
            v31 = 38;
          do
          {
            this->OnKey(this, v31);
            ++v33;
          }
          while ( v33 < this->m_nDropDownPageSize );
          v34 = this->m_iHighlighted;
          this->m_bInScrollMode = 0;
          if ( v32 != v34 )
            ((void (__fastcall *)(CMFCPopupMenuBar *))this->AccNotifyObjectFocusEvent)(this);
          return 1;
        }
        return v38;
      case 0x23u:
        m_pNodeHead = 0;
        goto LABEL_65;
      case 0x24u:
        m_pNodeHead = 0;
        break;
      case 0x26u:
        goto LABEL_65;
      case 0x28u:
        break;
      default:
        if ( CMFCToolBar::m_bCustomizeMode || GetAsyncKeyState(17) < 0 )
          return v38;
        if ( CKeyboardManager::IsKeyPrintable(v3)
          && (nUpperChar = CKeyboardManager::TranslateCharToUpper(v3),
              v3 = nUpperChar,
              (v12 = CMap<unsigned int,unsigned int &,CMFCToolBarButton *,CMFCToolBarButton * &>::GetAssocAt(
                       &this->m_AccelKeys,
                       &nUpperChar,
                       &nHashBucket,
                       &nHashValue)) != 0) )
        {
          value = v12->value;
          v14 = 0;
          v15 = this->m_Buttons.m_pNodeHead;
          while ( v15 )
          {
            v16 = v15;
            v15 = v15->pNext;
            if ( !v16->data )
              goto LABEL_111;
            if ( v16->data == value )
            {
              LODWORD(m_iHighlighted) = v14;
              break;
            }
            ++v14;
          }
          if ( !value || !CObject::IsKindOf(value, &CMFCToolBarMenuButton::classCMFCToolBarMenuButton) )
            goto LABEL_82;
          if ( ((unsigned int (__fastcall *)(CMFCToolBarButton *, _QWORD))value->__vftable[1].GetRuntimeClass)(value, 0) )
          {
            m_pszData = value[1].m_strText.m_pszData;
            if ( m_pszData )
              SendMessageW(*((HWND *)m_pszData + 8), 0x100u, 0x24u, 0);
LABEL_82:
            if ( value != data )
            {
              if ( v8 && !this->m_bInScrollMode )
                this->AccNotifyObjectFocusEvent(this, m_iHighlighted);
              if ( CMFCToolBar::m_bCustomizeMode )
                this->m_iSelected = m_iHighlighted;
              m_hWnd = this->m_hWnd;
              this->m_iHighlighted = m_iHighlighted;
              rectClient = 0;
              GetClientRect(m_hWnd, &rectClient);
              m_rect = value->m_rect;
              v30 = HIDWORD(*(_QWORD *)&value->m_rect.left);
              rectNew = m_rect;
              if ( (int)v30 >= rectClient.top
                && _mm_srli_si128(*(__m128i *)&m_rect, 8).m128i_i32[1] <= rectClient.bottom )
              {
                if ( data )
                  InvalidateRect(this->m_hWnd, &data->m_rect, 1);
                InvalidateRect(this->m_hWnd, &rectNew, 1);
                UpdateWindow(this->m_hWnd);
              }
              if ( value->m_nID != -1 )
                ((void (__fastcall *)(CMFCPopupMenuBar *))this->ShowCommandMessageString)(this);
            }
            return v38;
          }
          v18 = this;
          if ( (value->m_nStyle & 0x40000) == 0 )
          {
            v38 = this->OnSendCommand(this, value);
            if ( v38 )
              return 1;
            goto LABEL_82;
          }
          v19 = value;
          v20 = 0;
        }
        else
        {
          if ( !CMFCMenuBar::m_bRecentlyUsedMenus )
            return v38;
          if ( this->m_bAreAllCommandsShown )
            return v38;
          AssocAt = CMap<unsigned int,unsigned int,unsigned long,unsigned long>::GetAssocAt(
                      (CMap<int,int,unsigned int,unsigned int> *)&this->m_HiddenItemsAccel,
                      v3,
                      &nHashValue,
                      &nHashBucket);
          if ( !AssocAt )
            return v38;
          v20 = AssocAt->value;
          v19 = 0;
          v18 = this;
        }
        CMFCPopupMenuBar::InvokeMenuCommand(v18, v20, v19);
        return 1;
    }
  }
  if ( this->m_bDropDownListMode && v10 == this->m_Buttons.m_pNodeTail && v11 != 36 )
    return 1;
  v38 = 1;
  if ( this->m_Buttons.m_nCount )
  {
    pNext = m_pNodeHead;
    if ( m_pNodeHead )
      pNext = m_pNodeHead->pNext;
    v23 = pNext;
    if ( !pNext )
      pNext = this->m_Buttons.m_pNodeHead;
    LODWORD(m_iHighlighted) = v23 != 0 ? m_iHighlighted + 1 : 0;
    if ( pNext != m_pNodeHead )
    {
      do
      {
        v24 = pNext;
        if ( !pNext )
          goto LABEL_111;
        v25 = pNext->data;
        pNext = pNext->pNext;
        if ( ((__int64)v25[5].__vftable & 1) == 0
          && !IsRectEmpty((const RECT *)&v25[13])
          && HIDWORD(v25[4].__vftable) != -2 )
        {
          break;
        }
        LODWORD(m_iHighlighted) = m_iHighlighted + 1;
        if ( !pNext )
        {
          if ( this->m_bDropDownListMode )
            return 1;
          pNext = this->m_Buttons.m_pNodeHead;
          LODWORD(m_iHighlighted) = 0;
        }
      }
      while ( pNext != m_pNodeHead );
LABEL_81:
      value = (CMFCToolBarButton *)v24->data;
      v8 = 1;
      goto LABEL_82;
    }
  }
  return v38;
}

```

## disassembly

```asm
0x1800c13f0  mov     [rsp-38h+arg_10], rbx
0x1800c13f5  push    rbp
0x1800c13f6  push    rsi
0x1800c13f7  push    rdi
0x1800c13f8  push    r12
0x1800c13fa  push    r13
0x1800c13fc  push    r14
0x1800c13fe  push    r15
0x1800c1400  mov     rbp, rsp
0x1800c1403  sub     rsp, 60h
0x1800c1407  mov     rax, cs:__security_cookie
0x1800c140e  xor     rax, rsp
0x1800c1411  mov     [rbp+var_8], rax
0x1800c1415  movsxd  r14, dword ptr [this+1138h]
0x1800c141c  xor     r13d, r13d
0x1800c141f  mov     [rbp+var_40], r13d
0x1800c1423  mov     esi, nChar
0x1800c1425  mov     rbx, this
0x1800c1428  test    r14d, r14d
0x1800c142b  js      short loc_1800C145B
0x1800c142d  mov     rax, r14
0x1800c1430  cmp     r14, [this+11A0h]
0x1800c1437  jge     short loc_1800C145B
0x1800c1439  test    r14d, r14d
0x1800c143c  js      short loc_1800C145B
0x1800c143e  mov     rdi, [this+1190h]
0x1800c1445  jz      short loc_1800C1450
0x1800c1447  mov     rdi, [rdi]
0x1800c144a  sub     rax, 1
0x1800c144e  jnz     short loc_1800C1447
0x1800c1450  test    rdi, rdi
0x1800c1453  jz      short loc_1800C145E
0x1800c1455  mov     r15, [rdi+10h]
0x1800c1459  jmp     short loc_1800C1461
0x1800c145b  mov     rdi, r13
0x1800c145e  mov     r15, r13
0x1800c1461  mov     r12d, r13d
0x1800c1464  cmp     esi, 9
0x1800c1467  jnz     short loc_1800C148B
0x1800c1469  lea     ecx, [rsi+7]; nVirtKey
0x1800c146c  call    cs:__imp_GetKeyState
0x1800c1472  mov     rdx, rdi
0x1800c1475  test    al, al
0x1800c1477  jns     short loc_1800C1481
0x1800c1479  lea     ecx, [rsi+1Dh]
0x1800c147c  jmp     loc_1800C1710
0x1800c1481  mov     ecx, 28h ; '('
0x1800c1486  jmp     loc_1800C164C
0x1800c148b  mov     eax, esi
0x1800c148d  mov     rdx, rdi
0x1800c1490  mov     ecx, esi
0x1800c1492  sub     eax, 0Dh
0x1800c1495  jz      loc_1800C193E
0x1800c149b  sub     eax, 14h
0x1800c149e  jz      loc_1800C18B6
0x1800c14a4  sub     eax, 1
0x1800c14a7  jz      loc_1800C18B6
0x1800c14ad  sub     eax, 1
0x1800c14b0  jz      loc_1800C170D
0x1800c14b6  sub     eax, 1
0x1800c14b9  jz      loc_1800C1649
0x1800c14bf  sub     eax, 2
0x1800c14c2  jz      loc_1800C1710
0x1800c14c8  cmp     eax, 2
0x1800c14cb  jz      loc_1800C164C
0x1800c14d1  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r13d; int CMFCToolBar::m_bCustomizeMode
0x1800c14d8  jnz     loc_1800C19DD
0x1800c14de  mov     ecx, 11h; vKey
0x1800c14e3  call    cs:__imp_GetAsyncKeyState
0x1800c14e9  test    ax, ax
0x1800c14ec  js      loc_1800C19DD
0x1800c14f2  mov     ecx, esi; nChar
0x1800c14f4  call    ?IsKeyPrintable@CKeyboardManager@@SAHI@Z; CKeyboardManager::IsKeyPrintable(uint)
0x1800c14f9  test    eax, eax
0x1800c14fb  jz      loc_1800C1605
0x1800c1501  mov     ecx, esi; nChar
0x1800c1503  call    ?TranslateCharToUpper@CKeyboardManager@@SAII@Z; CKeyboardManager::TranslateCharToUpper(uint)
0x1800c1508  lea     this, [rbx+1318h]; this
0x1800c150f  mov     [rbp+nUpperChar], eax
0x1800c1512  lea     r9, [rbp+nHashValue]; nHashValue
0x1800c1516  mov     esi, eax
0x1800c1518  lea     r8, [rbp+nHashBucket]; nHashBucket
0x1800c151c  lea     rdx, [rbp+nUpperChar]; key
0x1800c1520  call    ?GetAssocAt@?$CMap@IAEAIPEAVCMFCToolBarButton@@AEAPEAV1@@@IEBAPEAVCAssoc@1@AEAI00@Z; CMap<uint,uint &,CMFCToolBarButton *,CMFCToolBarButton * &>::GetAssocAt(uint &,uint &,uint &)
0x1800c1525  test    rax, rax
0x1800c1528  jz      loc_1800C1605
0x1800c152e  mov     rsi, [rax+8]
0x1800c1532  mov     nChar, r13d
0x1800c1535  mov     this, [rbx+1190h]
0x1800c153c  mov     rdi, rsi
0x1800c153f  jmp     short loc_1800C1559
0x1800c1541  lea     rax, [this]
0x1800c1544  mov     this, [this]
0x1800c1547  cmp     [rax+10h], r13
0x1800c154b  jz      loc_1800C1A04
0x1800c1551  cmp     [rax+10h], rsi
0x1800c1555  jz      short loc_1800C1560
0x1800c1557  inc     nChar
0x1800c1559  test    this, this
0x1800c155c  jnz     short loc_1800C1541
0x1800c155e  jmp     short loc_1800C1563
0x1800c1560  mov     r14d, nChar
0x1800c1563  test    rdi, rdi
0x1800c1566  jz      loc_1800C17D8
0x1800c156c  lea     rdx, ?classCMFCToolBarMenuButton@CMFCToolBarMenuButton@@2UCRuntimeClass@@A; pClass
0x1800c1573  mov     this, rdi; this
0x1800c1576  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1800c157b  test    eax, eax
0x1800c157d  jz      loc_1800C17D8
0x1800c1583  mov     rax, [rdi]
0x1800c1586  xor     nChar, nChar
0x1800c1588  mov     this, rdi
0x1800c158b  mov     rax, [rax+1A8h]
0x1800c1592  call    cs:__guard_dispatch_icall_fptr
0x1800c1598  test    eax, eax
0x1800c159a  jz      short loc_1800C15C7
0x1800c159c  mov     this, [rdi+0C0h]
0x1800c15a3  test    this, this
0x1800c15a6  jz      loc_1800C17D8
0x1800c15ac  mov     this, [this+40h]; hWnd
0x1800c15b0  xor     r9d, r9d; lParam
0x1800c15b3  mov     nChar, 100h; Msg
0x1800c15b8  lea     r8d, [r9+24h]; wParam
0x1800c15bc  call    cs:__imp_SendMessageW
0x1800c15c2  jmp     loc_1800C17D8
0x1800c15c7  test    dword ptr [rdi+28h], 40000h
0x1800c15ce  mov     this, rbx; this
0x1800c15d1  jz      short loc_1800C15E2
0x1800c15d3  mov     r8, rdi; pMenuItem
0x1800c15d6  xor     nChar, nChar; uiCmdId
0x1800c15d8  call    ?InvokeMenuCommand@CMFCPopupMenuBar@@IEAAXIPEBVCMFCToolBarButton@@@Z; CMFCPopupMenuBar::InvokeMenuCommand(uint,CMFCToolBarButton const *)
0x1800c15dd  jmp     loc_1800C1934
0x1800c15e2  mov     rax, [rbx]
0x1800c15e5  mov     rdx, rdi
0x1800c15e8  mov     rax, [rax+7E0h]
0x1800c15ef  call    cs:__guard_dispatch_icall_fptr
0x1800c15f5  mov     [rbp+var_40], eax
0x1800c15f8  test    eax, eax
0x1800c15fa  jnz     loc_1800C1934
0x1800c1600  jmp     loc_1800C17D8
0x1800c1605  cmp     cs:?m_bRecentlyUsedMenus@CMFCMenuBar@@1HA, r13d; int CMFCMenuBar::m_bRecentlyUsedMenus
0x1800c160c  jz      loc_1800C19DD
0x1800c1612  cmp     [rbx+1380h], r13d
0x1800c1619  jnz     loc_1800C19DD
0x1800c161f  lea     this, [rbx+13E8h]; this
0x1800c1626  mov     nChar, esi; key
0x1800c1628  lea     r9, [rbp+nHashBucket]; nHashValue
0x1800c162c  lea     r8, [rbp+nHashValue]; nHashBucket
0x1800c1630  call    ?GetAssocAt@?$CMap@IIKK@@IEBAPEAVCAssoc@1@IAEAI0@Z; CMap<uint,uint,ulong,ulong>::GetAssocAt(uint,uint &,uint &)
0x1800c1635  test    rax, rax
0x1800c1638  jz      loc_1800C19DD
0x1800c163e  mov     nChar, [rax+4]
0x1800c1641  xor     r8d, r8d
0x1800c1644  mov     this, rbx
0x1800c1647  jmp     short loc_1800C15D8
0x1800c1649  mov     rdi, r13
0x1800c164c  cmp     [rbx+1398h], r13d
0x1800c1653  jz      short loc_1800C1667
0x1800c1655  cmp     rdx, [rbx+1198h]
0x1800c165c  jnz     short loc_1800C1667
0x1800c165e  cmp     ecx, 24h ; '$'
0x1800c1661  jnz     loc_1800C1934
0x1800c1667  mov     [rbp+var_40], 1
0x1800c166e  cmp     [rbx+11A0h], r13
0x1800c1675  jz      loc_1800C19DD
0x1800c167b  mov     rsi, rdi
0x1800c167e  test    rdi, rdi
0x1800c1681  jz      short loc_1800C1686
0x1800c1683  mov     rsi, [rdi]
0x1800c1686  mov     this, rsi
0x1800c1689  test    rsi, rsi
0x1800c168c  jnz     short loc_1800C1695
0x1800c168e  mov     rsi, [rbx+1190h]
0x1800c1695  neg     this
0x1800c1698  lea     eax, [r14+1]
0x1800c169c  sbb     r14d, r14d
0x1800c169f  and     r14d, eax
0x1800c16a2  cmp     rsi, rdi
0x1800c16a5  jz      loc_1800C19DD
0x1800c16ab  mov     r12, rsi
0x1800c16ae  mov     r13, rsi
0x1800c16b1  test    rsi, rsi
0x1800c16b4  jz      loc_1800C1A04
0x1800c16ba  mov     r13, [r13+10h]
0x1800c16be  mov     rsi, [rsi]
0x1800c16c1  test    byte ptr [r13+28h], 1
0x1800c16c6  jnz     short loc_1800C16E1
0x1800c16c8  lea     this, [r13+68h]; lprc
0x1800c16cc  call    cs:__imp_IsRectEmpty
0x1800c16d2  test    eax, eax
0x1800c16d4  jnz     short loc_1800C16E1
0x1800c16d6  cmp     dword ptr [r13+24h], 0FFFFFFFEh
0x1800c16db  jnz     loc_1800C17CA
0x1800c16e1  inc     r14d
0x1800c16e4  xor     r13d, r13d
0x1800c16e7  test    rsi, rsi
0x1800c16ea  jnz     short loc_1800C1703
0x1800c16ec  cmp     [rbx+1398h], r13d
0x1800c16f3  jnz     loc_1800C1934
0x1800c16f9  mov     rsi, [rbx+1190h]
0x1800c1700  mov     r14d, r13d
0x1800c1703  cmp     rsi, rdi
0x1800c1706  jnz     short loc_1800C16AB
0x1800c1708  jmp     loc_1800C17CD
0x1800c170d  mov     rdi, r13
0x1800c1710  cmp     [rbx+1398h], r13d
0x1800c1717  jz      short loc_1800C172B
0x1800c1719  cmp     rdx, [rbx+1190h]
0x1800c1720  jnz     short loc_1800C172B
0x1800c1722  cmp     ecx, 23h ; '#'
0x1800c1725  jnz     loc_1800C1934
0x1800c172b  mov     [rbp+var_40], 1
0x1800c1732  cmp     [rbx+11A0h], r13
0x1800c1739  jz      loc_1800C19DD
0x1800c173f  test    rdi, rdi
0x1800c1742  jz      short loc_1800C174D
0x1800c1744  mov     rsi, [rdi+8]
0x1800c1748  test    rsi, rsi
0x1800c174b  jnz     short loc_1800C175B
0x1800c174d  mov     rsi, [rbx+1198h]
0x1800c1754  mov     r14d, [rbx+11A0h]
0x1800c175b  dec     r14d
0x1800c175e  cmp     rsi, rdi
0x1800c1761  jz      loc_1800C19DD
0x1800c1767  mov     r12, rsi
0x1800c176a  mov     r13, rsi
0x1800c176d  test    rsi, rsi
0x1800c1770  jz      loc_1800C1A04
0x1800c1776  mov     r13, [r13+10h]
0x1800c177a  mov     rsi, [rsi+8]
0x1800c177e  test    byte ptr [r13+28h], 1
0x1800c1783  jnz     short loc_1800C179A
0x1800c1785  lea     this, [r13+68h]; lprc
0x1800c1789  call    cs:__imp_IsRectEmpty
0x1800c178f  test    eax, eax
0x1800c1791  jnz     short loc_1800C179A
0x1800c1793  cmp     dword ptr [r13+24h], 0FFFFFFFEh
0x1800c1798  jnz     short loc_1800C17CA
0x1800c179a  dec     r14d
0x1800c179d  xor     r13d, r13d
0x1800c17a0  test    rsi, rsi
0x1800c17a3  jnz     short loc_1800C17C3
0x1800c17a5  cmp     [rbx+1398h], r13d
0x1800c17ac  jnz     loc_1800C1934
0x1800c17b2  mov     r14d, [rbx+11A0h]
0x1800c17b9  mov     rsi, [rbx+1198h]
0x1800c17c0  dec     r14d
0x1800c17c3  cmp     rsi, rdi
0x1800c17c6  jnz     short loc_1800C1767
0x1800c17c8  jmp     short loc_1800C17CD
0x1800c17ca  xor     r13d, r13d
0x1800c17cd  mov     rsi, [r12+10h]
0x1800c17d2  mov     r12d, 1
0x1800c17d8  cmp     rsi, r15
0x1800c17db  jz      loc_1800C19DD
0x1800c17e1  test    r12d, r12d
0x1800c17e4  jz      short loc_1800C1805
0x1800c17e6  cmp     [rbx+13A0h], r13d
0x1800c17ed  jnz     short loc_1800C1805
0x1800c17ef  mov     rax, [rbx]
0x1800c17f2  mov     nChar, r14d
0x1800c17f5  mov     this, rbx
0x1800c17f8  mov     rax, [rax+4C8h]
0x1800c17ff  call    cs:__guard_dispatch_icall_fptr
0x1800c1805  cmp     cs:?m_bCustomizeMode@CMFCToolBar@@1HA, r13d; int CMFCToolBar::m_bCustomizeMode
0x1800c180c  jz      short loc_1800C1815
0x1800c180e  mov     [rbx+113Ch], r14d
0x1800c1815  mov     this, [rbx+40h]; hWnd
0x1800c1819  lea     rdx, [rbp+rectClient]; lpRect
0x1800c181d  xorps   xmm0, xmm0
0x1800c1820  mov     [rbx+1138h], r14d
0x1800c1827  movdqu  xmmword ptr [rbp+rectClient.left], xmm0
0x1800c182c  call    cs:__imp_GetClientRect
0x1800c1832  movups  xmm0, xmmword ptr [rsi+68h]
0x1800c1836  movq    rax, xmm0
0x1800c183b  shr     rax, 20h
0x1800c183f  movups  xmmword ptr [rbp+rectNew.left], xmm0
0x1800c1843  cmp     eax, [rbp+rectClient.top]
0x1800c1846  jl      short loc_1800C1892
0x1800c1848  psrldq  xmm0, 8
0x1800c184d  movq    rax, xmm0
0x1800c1852  shr     rax, 20h
0x1800c1856  cmp     eax, [rbp+rectClient.bottom]
0x1800c1859  jg      short loc_1800C1892
0x1800c185b  test    r15, r15
0x1800c185e  jz      short loc_1800C1874
0x1800c1860  mov     this, [rbx+40h]; hWnd
0x1800c1864  lea     rdx, [r15+68h]; lpRect
0x1800c1868  mov     r8d, 1; bErase
0x1800c186e  call    cs:__imp_InvalidateRect
0x1800c1874  mov     this, [rbx+40h]; hWnd
0x1800c1878  lea     rdx, [rbp+rectNew]; lpRect
0x1800c187c  mov     r8d, 1; bErase
0x1800c1882  call    cs:__imp_InvalidateRect
0x1800c1888  mov     this, [rbx+40h]; hWnd
0x1800c188c  call    cs:__imp_UpdateWindow
0x1800c1892  mov     nChar, [rsi+24h]
0x1800c1895  cmp     nChar, 0FFFFFFFFh
0x1800c1898  jz      loc_1800C19DD
0x1800c189e  mov     rax, [rbx]
  ... truncated ...
```
