# CMFCFontComboBox::DrawItem(tagDRAWITEMSTRUCT *)

- ea: `0x180063300`
- end: `0x18006366c`
- name: `?DrawItem@CMFCFontComboBox@@UEAAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `876`
- prototype: `void __fastcall(CMFCFontComboBox *this, tagDRAWITEMSTRUCT *lpDIS)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001d090`
- `0x180062dbc`
- `0x180063300`
- `0x18006cab0`
- `0x1802a06d0`
- `0x1802a3370`
- `0x1802aee30`
- `0x1802af260`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!lstrcpyW` at `0x18006351e`
- `KERNEL32!lstrcpyW` at `0x18006351e`
- `USER32!DrawFocusRect` at `0x180063383`
- `USER32!DrawFocusRect` at `0x180063383`
- `USER32!FillRect` at `0x180063458`
- `USER32!FillRect` at `0x180063458`
- `USER32!CopyRect` at `0x18006336f`
- `USER32!CopyRect` at `0x18006336f`
- `GDI32!CreateFontIndirectW` at `0x18006354b`
- `GDI32!CreateFontIndirectW` at `0x18006354b`
- `GDI32!GetBkColor` at `0x180063427`
- `GDI32!GetBkColor` at `0x180063427`
- `GDI32!GetObjectW` at `0x180063510`
- `GDI32!GetObjectW` at `0x180063510`
- `GDI32!CreateSolidBrush` at `0x1800633da`
- `GDI32!CreateSolidBrush` at `0x18006342f`
- `GDI32!CreateSolidBrush` at `0x1800633da`
- `GDI32!CreateSolidBrush` at `0x18006342f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMFCFontComboBox::DrawItem(CMFCFontComboBox *this, tagDRAWITEMSTRUCT *lpDIS)
{
  CImageList *p_m_Images; // rcx
  CDC *v5; // rdi
  int v6; // r12d
  HBRUSH SolidBrush; // rax
  unsigned int (__fastcall *SetTextColor)(CDC *, unsigned int); // rsi
  COLORREF BkColor; // eax
  HBRUSH v10; // rax
  signed int itemID; // r15d
  __int64 v12; // rsi
  unsigned __int64 itemData; // rbx
  unsigned __int8 lfCharSet; // al
  int v15; // eax
  HFONT v16; // rax
  wchar_t *m_pszData; // rbx
  CBrush brushFill; // [rsp+30h] [rbp-79h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strText; // [rsp+40h] [rbp-69h] BYREF
  CFont fontSelected; // [rsp+48h] [rbp-61h] BYREF
  CRect rc; // [rsp+58h] [rbp-51h] BYREF
  tagLOGFONTW lf; // [rsp+70h] [rbp-39h] BYREF

  p_m_Images = &this->m_Images;
  if ( !p_m_Images || !p_m_Images->m_hImageList )
    CImageList::Create(p_m_Images, 0x4268u, 16, 0, 0xFFFFFFu);
  v5 = CDC::FromHandle(lpDIS->hDC);
  CopyRect(&rc, &lpDIS->rcItem);
  if ( (lpDIS->itemState & 0x10) != 0 )
    DrawFocusRect(v5->m_hDC, &rc);
  v6 = v5->SaveDC(v5);
  brushFill.m_hObject = 0;
  brushFill.__vftable = (CBrush_vtbl *)CBrush::`vftable';
  if ( (lpDIS->itemState & 1) != 0 )
  {
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    SolidBrush = CreateSolidBrush(afxGlobalData.clrHilite);
    CGdiObject::Attach(&brushFill, SolidBrush);
    SetTextColor = v5->SetTextColor;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    SetTextColor(v5, afxGlobalData.clrTextHilite);
  }
  else
  {
    BkColor = GetBkColor(v5->m_hAttribDC);
    v10 = CreateSolidBrush(BkColor);
    CGdiObject::Attach(&brushFill, v10);
  }
  CDC::SetBkMode(v5, 1);
  FillRect(v5->m_hDC, &rc, (HBRUSH)brushFill.m_hObject);
  itemID = lpDIS->itemID;
  if ( itemID >= 0 )
  {
    fontSelected.m_hObject = 0;
    fontSelected.__vftable = (CFont_vtbl *)CFont::`vftable';
    v12 = 0;
    itemData = lpDIS->itemData;
    if ( itemData )
    {
      if ( (*(_DWORD *)(itemData + 28) & 6) != 0 )
        IsolationAwareImageList_Draw(
          this->m_Images.m_hImageList,
          (*(_DWORD *)(itemData + 28) & 2) == 0,
          v5->m_hDC,
          rc.left,
          rc.top + (rc.bottom - rc.top - 16) / 2,
          0);
      rc.left += 22;
      if ( CMFCFontComboBox::m_bDrawUsingFont && *(_BYTE *)(itemData + 24) != 2 )
      {
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        GetObjectW(afxGlobalData.fontRegular.m_hObject, 92, &lf);
        lstrcpyW(lf.lfFaceName, *(LPCWSTR *)(itemData + 8));
        lfCharSet = lf.lfCharSet;
        if ( *(_BYTE *)(itemData + 24) != 1 )
          lfCharSet = *(_BYTE *)(itemData + 24);
        lf.lfCharSet = lfCharSet;
        if ( lf.lfHeight >= 0 )
          v15 = lf.lfHeight + 4;
        else
          v15 = lf.lfHeight - 4;
        lf.lfHeight = v15;
        v16 = CreateFontIndirectW(&lf);
        CGdiObject::Attach(&fontSelected, v16);
        v12 = (__int64)v5->SelectObject(v5, &fontSelected);
      }
    }
    strText.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    CComboBox::GetLBText(this, itemID, &strText);
    m_pszData = strText.m_pszData;
    v5->DrawTextW(v5, strText.m_pszData, *((_DWORD *)strText.m_pszData - 4), &rc, 36u);
    if ( v12 )
      v5->SelectObject(v5, (CFont *)v12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)m_pszData - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)m_pszData - 3) + 8LL))(*((_QWORD *)m_pszData - 3));
    fontSelected.__vftable = (CFont_vtbl *)CFont::`vftable';
    CGdiObject::~CGdiObject(&fontSelected);
  }
  v5->RestoreDC(v5, v6);
  brushFill.__vftable = (CBrush_vtbl *)CBrush::`vftable';
  CGdiObject::~CGdiObject(&brushFill);
}

```

## disassembly

```asm
0x180063300  mov     [rsp-8+arg_10], rbx
0x180063305  mov     [rsp-8+arg_18], rsi
0x18006330a  push    rbp
0x18006330b  push    rdi
0x18006330c  push    r12
0x18006330e  push    r14
0x180063310  push    r15
0x180063312  lea     rbp, [rsp-37h]
0x180063317  sub     rsp, 0E0h
0x18006331e  mov     rax, cs:__security_cookie
0x180063325  xor     rax, rsp
0x180063328  mov     [rbp+57h+var_30], rax
0x18006332c  mov     rbx, lpDIS
0x18006332f  mov     r14, this
0x180063332  add     this, 0E8h; this
0x180063339  jz      short loc_180063342
0x18006333b  cmp     qword ptr [this+8], 0
0x180063340  jnz     short loc_18006335B
0x180063342  mov     [rsp+100h+crMask], 0FFFFFFh; crMask
0x18006334a  xor     r9d, r9d; nGrow
0x18006334d  mov     edx, 4268h; nBitmapID
0x180063352  lea     r8d, [r9+10h]; cx
0x180063356  call    ?Create@CImageList@@QEAAHIHHK@Z; CImageList::Create(uint,int,int,ulong)
0x18006335b  mov     this, [rbx+20h]; hDC
0x18006335f  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x180063364  mov     rdi, rax
0x180063367  lea     lpDIS, [rbx+28h]; lprcSrc
0x18006336b  lea     this, [rbp+57h+rc]; lprcDst
0x18006336f  call    cs:__imp_CopyRect
0x180063375  test    byte ptr [rbx+10h], 10h
0x180063379  jz      short loc_180063389
0x18006337b  lea     lpDIS, [rbp+57h+rc]; lprc
0x18006337f  mov     this, [rdi+8]; hDC
0x180063383  call    cs:__imp_DrawFocusRect
0x180063389  mov     rax, [rdi]
0x18006338c  mov     this, rdi
0x18006338f  mov     rax, [rax+48h]
0x180063393  call    cs:__guard_dispatch_icall_fptr
0x180063399  mov     r12d, eax
0x18006339c  and     [rbp+57h+brushFill.m_hObject], 0
0x1800633a1  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1800633a8  mov     [rbp+57h+brushFill.__vftable], rax
0x1800633ac  mov     r15d, 1
0x1800633b2  test    [rbx+10h], r15b
0x1800633b6  jz      short loc_180063423
0x1800633b8  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1800633bf  jnz     short loc_1800633D4
0x1800633c1  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800633c8  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800633cd  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x1800633d4  mov     ecx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrHilite; color
0x1800633da  call    cs:__imp_CreateSolidBrush
0x1800633e0  mov     lpDIS, rax; hObject
0x1800633e3  lea     this, [rbp+57h+brushFill]; this
0x1800633e7  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1800633ec  mov     rax, [rdi]
0x1800633ef  mov     rsi, [rax+70h]
0x1800633f3  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x1800633fa  jnz     short loc_18006340F
0x1800633fc  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180063403  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180063408  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r15d; AFX_GLOBAL_DATA afxGlobalData ...
0x18006340f  mov     edx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrTextHilite; AFX_GLOBAL_DATA afxGlobalData ...
0x180063415  mov     this, rdi
0x180063418  mov     rax, rsi
0x18006341b  call    cs:__guard_dispatch_icall_fptr
0x180063421  jmp     short loc_180063441
0x180063423  mov     this, [rdi+10h]; hdc
0x180063427  call    cs:__imp_GetBkColor
0x18006342d  mov     ecx, eax; color
0x18006342f  call    cs:__imp_CreateSolidBrush
0x180063435  mov     lpDIS, rax; hObject
0x180063438  lea     this, [rbp+57h+brushFill]; this
0x18006343c  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180063441  mov     edx, r15d; nBkMode
0x180063444  mov     this, rdi; this
0x180063447  call    ?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x18006344c  mov     r8, [rbp+57h+brushFill.m_hObject]; hbr
0x180063450  lea     lpDIS, [rbp+57h+rc]; lprc
0x180063454  mov     this, [rdi+8]; hDC
0x180063458  call    cs:__imp_FillRect
0x18006345e  mov     r15d, [rbx+8]
0x180063462  test    r15d, r15d
0x180063465  js      loc_18006361C
0x18006346b  and     [rbp+57h+fontSelected.m_hObject], 0
0x180063470  lea     rax, ??_7CFont@@6B@; const CFont::`vftable'
0x180063477  mov     [rbp+57h+fontSelected.__vftable], rax
0x18006347b  xor     esi, esi
0x18006347d  mov     rbx, [rbx+38h]
0x180063481  test    rbx, rbx
0x180063484  jz      loc_180063574
0x18006348a  mov     ecx, [rbx+1Ch]
0x18006348d  test    cl, 6
0x180063490  jz      short loc_1800634C8
0x180063492  mov     eax, [rbp+57h+rc.bottom]
0x180063495  sub     eax, [rbp+57h+rc.top]
0x180063498  sub     eax, 10h
0x18006349b  cdq
0x18006349c  sub     eax, edx
0x18006349e  sar     eax, 1
0x1800634a0  add     eax, [rbp+57h+rc.top]
0x1800634a3  shr     ecx, 1
0x1800634a5  not     ecx
0x1800634a7  and     ecx, 1
0x1800634aa  and     [rsp+100h+var_D8], esi
0x1800634ae  mov     [rsp+100h+crMask], eax; y
0x1800634b2  mov     r9d, [rbp+57h+rc.left]; x
0x1800634b6  mov     r8, [rdi+8]; hdcDst
0x1800634ba  mov     edx, ecx; i
0x1800634bc  mov     this, [r14+0F0h]; himl
0x1800634c3  call    IsolationAwareImageList_Draw
0x1800634c8  add     [rbp+57h+rc.left], 16h
0x1800634cc  cmp     cs:?m_bDrawUsingFont@CMFCFontComboBox@@2HA, esi; int CMFCFontComboBox::m_bDrawUsingFont
0x1800634d2  jz      loc_180063574
0x1800634d8  cmp     byte ptr [rbx+18h], 2
0x1800634dc  jz      loc_180063574
0x1800634e2  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, esi; AFX_GLOBAL_DATA afxGlobalData ...
0x1800634e8  jnz     short loc_180063500
0x1800634ea  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x1800634f1  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x1800634f6  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x180063500  lea     r8, [rbp+57h+lf]; pv
0x180063504  mov     edx, 5Ch ; '\'; c
0x180063509  mov     this, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.fontRegular.m_hObject; h
0x180063510  call    cs:__imp_GetObjectW
0x180063516  mov     lpDIS, [rbx+8]; lpString2
0x18006351a  lea     this, [rbp+57h+lf.lfFaceName]; lpString1
0x18006351e  call    cs:__imp_lstrcpyW
0x180063524  movzx   ecx, byte ptr [rbx+18h]
0x180063528  movzx   eax, [rbp+57h+lf.lfCharSet]
0x18006352c  cmp     cl, 1
0x18006352f  cmovnz  eax, ecx
0x180063532  mov     [rbp+57h+lf.lfCharSet], al
0x180063535  mov     eax, [rbp+57h+lf.lfHeight]
0x180063538  test    eax, eax
0x18006353a  jns     short loc_180063541
0x18006353c  sub     eax, 4
0x18006353f  jmp     short loc_180063544
0x180063541  add     eax, 4
0x180063544  mov     [rbp+57h+lf.lfHeight], eax
0x180063547  lea     this, [rbp+57h+lf]; lplf
0x18006354b  call    cs:__imp_CreateFontIndirectW
0x180063551  mov     lpDIS, rax; hObject
0x180063554  lea     this, [rbp+57h+fontSelected]; this
0x180063558  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18006355d  mov     rax, [rdi]
0x180063560  lea     lpDIS, [rbp+57h+fontSelected]
0x180063564  mov     this, rdi
0x180063567  mov     rax, [rax+60h]
0x18006356b  call    cs:__guard_dispatch_icall_fptr
0x180063571  mov     rsi, rax
0x180063574  mov     r8, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18006357b  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x180063582  mov     rax, [r8+18h]
0x180063586  call    cs:__guard_dispatch_icall_fptr
0x18006358c  add     rax, 18h
0x180063590  mov     [rbp+57h+strText.m_pszData], rax
0x180063594  lea     r8, [rbp+57h+strText]; rString
0x180063598  mov     edx, r15d; nIndex
0x18006359b  mov     this, r14; this
0x18006359e  call    ?GetLBText@CComboBox@@QEBAXHAEAV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z; CComboBox::GetLBText(int,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800635a3  mov     rax, [rdi]
0x1800635a6  mov     rbx, [rbp+57h+strText.m_pszData]
0x1800635aa  mov     [rsp+100h+crMask], 24h ; '$'
0x1800635b2  lea     r9, [rbp+57h+rc]
0x1800635b6  mov     r8d, [rbx-10h]
0x1800635ba  mov     lpDIS, rbx
0x1800635bd  mov     this, rdi
0x1800635c0  mov     rax, [rax+0E0h]
0x1800635c7  call    cs:__guard_dispatch_icall_fptr
0x1800635cd  test    rsi, rsi
0x1800635d0  jz      short loc_1800635E6
0x1800635d2  mov     rax, [rdi]
0x1800635d5  mov     lpDIS, rsi
0x1800635d8  mov     this, rdi
0x1800635db  mov     rax, [rax+60h]
0x1800635df  call    cs:__guard_dispatch_icall_fptr
0x1800635e5  nop
0x1800635e6  lea     lpDIS, [rbx-18h]
0x1800635ea  or      eax, 0FFFFFFFFh
0x1800635ed  lock xadd [lpDIS+10h], eax
0x1800635f2  sub     eax, 1
0x1800635f5  jg      short loc_180063608
0x1800635f7  mov     this, [lpDIS]
0x1800635fa  mov     rax, [this]
0x1800635fd  mov     rax, [rax+8]
0x180063601  call    cs:__guard_dispatch_icall_fptr
0x180063607  nop
0x180063608  lea     rax, ??_7CFont@@6B@; const CFont::`vftable'
0x18006360f  mov     [rbp+57h+fontSelected.__vftable], rax
0x180063613  lea     this, [rbp+57h+fontSelected]; this
0x180063617  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18006361c  mov     rax, [rdi]
0x18006361f  mov     edx, r12d
0x180063622  mov     this, rdi
0x180063625  mov     rax, [rax+50h]
0x180063629  call    cs:__guard_dispatch_icall_fptr
0x18006362f  nop
0x180063630  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x180063637  mov     [rbp+57h+brushFill.__vftable], rax
0x18006363b  lea     this, [rbp+57h+brushFill]; this
0x18006363f  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x180063644  mov     this, [rbp+57h+var_30]
0x180063648  xor     this, rsp; StackCookie
0x18006364b  call    __security_check_cookie
0x180063650  lea     r11, [rsp+100h+var_20]
0x180063658  mov     rbx, [r11+40h]
0x18006365c  mov     rsi, [r11+48h]
0x180063660  mov     rsp, r11
0x180063663  pop     r15
0x180063665  pop     r14
0x180063667  pop     r12
0x180063669  pop     rdi
0x18006366a  pop     rbp
0x18006366b  retn
```
