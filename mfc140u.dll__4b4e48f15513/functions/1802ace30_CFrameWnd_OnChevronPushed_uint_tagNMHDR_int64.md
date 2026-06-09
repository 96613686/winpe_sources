# CFrameWnd::OnChevronPushed(uint,tagNMHDR *,__int64 *)

- ea: `0x1802ace30`
- end: `0x1802ad709`
- name: `?OnChevronPushed@CFrameWnd@@IEAAHIPEAUtagNMHDR@@PEA_J@Z`
- size: `2265`
- prototype: `int __fastcall(CFrameWnd *this, unsigned int __formal, tagNMHDR *pnm, __int64 *pResult)`
- caller_count: `0`
- callee_count: `34`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800027e0`
- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x18000ddc0`
- `0x18001cb54`
- `0x18001d090`
- `0x180062dbc`
- `0x1801dd100`
- `0x1801dd470`
- `0x1801e5770`
- `0x180231d70`
- `0x18023f820`
- `0x180296d50`
- `0x180298130`
- `0x18029a390`
- `0x1802a32c0`
- `0x1802ace30`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802aef40`
- `0x1802afdb0`
- `0x1802afe10`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b4d10`
- `0x1802b4da0`
- `0x1802b4ed0`
- `0x1802bafd0`
- `0x1802bbce0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!memset` at `0x1802ad19b`
- `VCRUNTIME140!memset` at `0x1802ad19b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802ad552`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1802ad552`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1802ace96`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1802ad046`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1802ace96`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1802ad046`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802acee2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802ad093`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802acee2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1802ad093`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1802acf20`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1802ad0cd`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1802acf20`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1802ad0cd`
- `USER32!CreatePopupMenu` at `0x1802ad1f3`
- `USER32!CreatePopupMenu` at `0x1802ad1f3`
- `USER32!IntersectRect` at `0x1802ad17e`
- `USER32!IntersectRect` at `0x1802ad17e`
- `USER32!GetSysColor` at `0x1802ad3b2`
- `USER32!GetSysColor` at `0x1802ad3b2`
- `USER32!InsertMenuItemW` at `0x1802ad4a6`
- `USER32!InsertMenuItemW` at `0x1802ad4a6`
- `USER32!SendMessageW` at `0x1802ad01e`
- `USER32!SendMessageW` at `0x1802ad039`
- `USER32!SendMessageW` at `0x1802ad13a`
- `USER32!SendMessageW` at `0x1802ad163`
- `USER32!SendMessageW` at `0x1802ad1b3`
- `USER32!SendMessageW` at `0x1802ad01e`
- `USER32!SendMessageW` at `0x1802ad039`
- `USER32!SendMessageW` at `0x1802ad13a`
- `USER32!SendMessageW` at `0x1802ad163`
- `USER32!SendMessageW` at `0x1802ad1b3`
- `USER32!CopyRect` at `0x1802ad31f`
- `USER32!CopyRect` at `0x1802ad4c4`
- `USER32!CopyRect` at `0x1802ad31f`
- `USER32!CopyRect` at `0x1802ad4c4`
- `USER32!GetClassNameW` at `0x1802aced5`
- `USER32!GetClassNameW` at `0x1802ad086`
- `USER32!GetClassNameW` at `0x1802aced5`
- `USER32!GetClassNameW` at `0x1802ad086`
- `USER32!OffsetRect` at `0x1802ad33e`
- `USER32!OffsetRect` at `0x1802ad33e`
- `GDI32!ExtTextOutW` at `0x1802ad3f8`
- `GDI32!ExtTextOutW` at `0x1802ad3f8`
- `GDI32!SetBkColor` at `0x1802ad3c8`
- `GDI32!SetBkColor` at `0x1802ad3c8`
- `GDI32!DeleteDC` at `0x1802ad618`
- `GDI32!DeleteDC` at `0x1802ad618`
- `GDI32!CreateCompatibleBitmap` at `0x1802ad362`
- `GDI32!CreateCompatibleBitmap` at `0x1802ad362`
- `GDI32!SelectObject` at `0x1802ad392`
- `GDI32!SelectObject` at `0x1802ad43d`
- `GDI32!SelectObject` at `0x1802ad392`
- `GDI32!SelectObject` at `0x1802ad43d`
- `GDI32!CreateCompatibleDC` at `0x1802ad209`
- `GDI32!CreateCompatibleDC` at `0x1802ad209`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CFrameWnd::OnChevronPushed(CFrameWnd *this, __int64 __formal, tagNMHDR *pnm, __int64 *pResult)
{
  wchar_t *m_pszData; // rbx
  unsigned int v7; // esi
  int v8; // edi
  int v9; // eax
  CWnd *v10; // r14
  CFrameWnd *ParentFrame; // rax
  wchar_t *v12; // rdi
  int v13; // r15d
  int v14; // eax
  CToolBar *v15; // r13
  LRESULT v16; // rax
  UINT v17; // r15d
  UINT v18; // r14d
  struct _IMAGELIST *v19; // rax
  HMENU PopupMenu; // rax
  HDC CompatibleDC; // rax
  unsigned int v22; // ebx
  __int64 m_nSize; // r12
  bool v24; // cf
  CObject **m_pData; // r15
  unsigned int v26; // edi
  HINSTANCE__ *StringResourceHandle; // rax
  CObject *v28; // rax
  __int64 v29; // rdi
  CGdiObject *v30; // rbx
  HBITMAP CompatibleBitmap; // rax
  CObject *v32; // rax
  CObject_vtbl *v33; // rdx
  HGDIOBJ v34; // rax
  CGdiObject *v35; // rax
  COLORREF SysColor; // eax
  CObject *v37; // rax
  CObject_vtbl *v38; // rdx
  HGDIOBJ v39; // rax
  CGdiObject *v40; // rax
  unsigned int v41; // r14d
  __int64 v42; // rbx
  CObject *v43; // rcx
  wchar_t *v44; // rdx
  HDC v45; // rax
  wchar_t *v46; // rdx
  unsigned int v48; // [rsp+40h] [rbp-C0h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strClassName; // [rsp+48h] [rbp-B8h] BYREF
  int iImage; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int nID; // [rsp+54h] [rbp-ACh] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strRes; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int nStyle; // [rsp+60h] [rbp-A0h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strMenu; // [rsp+68h] [rbp-98h] BYREF
  CDC dcDest; // [rsp+70h] [rbp-90h] BYREF
  CImageList *v56; // [rsp+90h] [rbp-70h]
  CChevronOwnerDrawMenu menu; // [rsp+98h] [rbp-68h] BYREF
  CTypedPtrArray<CObArray,CBitmap *> bmp; // [rsp+B8h] [rbp-48h] BYREF
  LRESULT v59; // [rsp+E0h] [rbp-20h]
  RECT *lprcSrc; // [rsp+E8h] [rbp-18h]
  CWnd *v61; // [rsp+F0h] [rbp-10h]
  CWnd *pWnd; // [rsp+F8h] [rbp-8h]
  __int64 *v63; // [rsp+100h] [rbp+0h]
  tagMENUITEMINFOW MenuInfo; // [rsp+110h] [rbp+10h] BYREF
  CObject *v65; // [rsp+160h] [rbp+60h]
  CClientDC dcClient; // [rsp+168h] [rbp+68h] BYREF
  tagREBARBANDINFOW BandInfo; // [rsp+190h] [rbp+90h] BYREF
  tagRECT rcDst; // [rsp+210h] [rbp+110h] BYREF
  CRect rcBand; // [rsp+220h] [rbp+120h] BYREF
  CRect rc; // [rsp+230h] [rbp+130h] BYREF
  CRect rcBtn; // [rsp+240h] [rbp+140h] BYREF
  CRect rcInt; // [rsp+250h] [rbp+150h] BYREF
  _IMAGEINFO ImageInfo; // [rsp+260h] [rbp+160h] BYREF

  v63 = pResult;
  pWnd = this;
  m_pszData = (wchar_t *)(((__int64 (__fastcall *)(CAfxStringMgr *, __int64))afxStringManager.GetNilString)(
                            &afxStringManager,
                            __formal)
                        + 24);
  strClassName.m_pszData = m_pszData;
  v7 = 1;
  v8 = wcslen(L"ReBarWindow32") + 1;
  if ( v8 < 0 )
    goto LABEL_72;
  if ( ((1 - *((_DWORD *)m_pszData - 2)) | (*((_DWORD *)m_pszData - 3) - v8)) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&strClassName, v8);
    m_pszData = strClassName.m_pszData;
  }
  GetClassNameW(pnm->hwndFrom, m_pszData, v8);
  v9 = wcsnlen(m_pszData, *((int *)m_pszData - 3));
  if ( v9 < 0 || v9 > *((_DWORD *)m_pszData - 3) )
LABEL_72:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)m_pszData - 4) = v9;
  m_pszData[v9] = 0;
  v10 = CWnd::FromHandlePermanent(pnm->hwndFrom);
  v61 = v10;
  if ( wcscmp(m_pszData, L"ReBarWindow32") )
    goto LABEL_67;
  if ( !v10 )
    goto LABEL_67;
  if ( !CObject::IsKindOf(v10, &CReBar::classCReBar) )
    goto LABEL_67;
  ParentFrame = CWnd::GetParentFrame(v10);
  if ( ParentFrame )
  {
    if ( this != ParentFrame )
      goto LABEL_67;
  }
  rcBand = 0;
  rcBtn = 0;
  rcInt = 0;
  CChevronOwnerDrawMenu::CChevronOwnerDrawMenu(&menu);
  strRes.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  v12 = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  strMenu.m_pszData = v12;
  dcDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcDest.m_hDC, 0, 20);
  CClientDC::CClientDC(&dcClient, this);
  BandInfo.cbSize = (unsigned int)v10[1].m_xAccessible.__vftable;
  BandInfo.fMask = 16;
  SendMessageW(v10->m_hWnd, 0x41Cu, LODWORD(pnm[1].hwndFrom), (LPARAM)&BandInfo);
  SendMessageW(v10->m_hWnd, 0x409u, LODWORD(pnm[1].hwndFrom), (LPARAM)&rcBand);
  v13 = wcslen(L"ToolbarWindow32") + 1;
  if ( v13 < 0 )
    goto LABEL_71;
  if ( ((1 - *((_DWORD *)m_pszData - 2)) | (*((_DWORD *)m_pszData - 3) - v13)) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&strClassName, v13);
    m_pszData = strClassName.m_pszData;
  }
  GetClassNameW(BandInfo.hwndChild, m_pszData, v13);
  v14 = wcsnlen(m_pszData, *((int *)m_pszData - 3));
  if ( v14 < 0 || v14 > *((_DWORD *)m_pszData - 3) )
LABEL_71:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)m_pszData - 4) = v14;
  m_pszData[v14] = 0;
  v15 = (CToolBar *)CWnd::FromHandlePermanent(BandInfo.hwndChild);
  if ( wcscmp(m_pszData, L"ToolbarWindow32")
    || !v15
    || !CObject::IsKindOf(v15, (const CRuntimeClass *)&CStatusBar::`vftable'[111]) )
  {
    CClientDC::~CClientDC(&dcClient);
    dcDest.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( dcDest.m_hDC )
    {
      v45 = CDC::Detach(&dcDest);
      DeleteDC(v45);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    v46 = strRes.m_pszData - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)strRes.m_pszData - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v46 + 8LL))(*(_QWORD *)v46);
    menu.m_MenuFont.__vftable = (CFont_vtbl *)CFont::`vftable';
    CGdiObject::~CGdiObject(&menu.m_MenuFont);
    menu.__vftable = (CChevronOwnerDrawMenu_vtbl *)CMenu::`vftable';
    CMenu::DestroyMenu(&menu);
    m_pszData = strClassName.m_pszData;
LABEL_67:
    v7 = 0;
    goto LABEL_68;
  }
  lprcSrc = (RECT *)&pnm[1].code;
  rcBand.right = pnm[1].code;
  CWnd::ClientToScreen(v10, &rcBand);
  CWnd::ScreenToClient(v15, &rcBand);
  v16 = SendMessageW(v15->m_hWnd, 0x418u, 0, 0);
  v17 = v16;
  v59 = v16;
  v18 = v16;
  do
    SendMessageW(v15->m_hWnd, 0x41Du, (int)--v18, (LPARAM)&rcBtn);
  while ( !IntersectRect(&rcInt, &rcBand, &rcBtn) && v18 );
  memset(&MenuInfo, 0, sizeof(MenuInfo));
  MenuInfo.cbSize = 80;
  v19 = (struct _IMAGELIST *)SendMessageW(v15->m_hWnd, 0x431u, 0, 0);
  v56 = CImageList::FromHandle(v19);
  memset(&bmp.m_pData, 0, 32);
  bmp.__vftable = (CTypedPtrArray<CObArray,CBitmap *>_vtbl *)CTypedPtrArray<CObArray,CBitmap *>::`vftable';
  CObArray::SetSize(&bmp, v17 - v18, -1);
  PopupMenu = CreatePopupMenu();
  CMenu::Attach(&menu, PopupMenu);
  CompatibleDC = CreateCompatibleDC(dcClient.m_hDC);
  CDC::Attach(&dcDest, CompatibleDC);
  v22 = 0;
  v48 = 0;
  m_nSize = bmp.m_nSize;
  v24 = v18 < v17;
  m_pData = bmp.m_pData;
  if ( v24 )
  {
    while ( 1 )
    {
      CToolBar::GetButtonInfo(v15, v18, &nID, &nStyle, &iImage);
      if ( (nStyle & 1) == 0 )
        break;
      if ( v22 )
      {
        MenuInfo.fMask = 256;
        MenuInfo.fType = 2048;
LABEL_46:
        InsertMenuItemW(menu.m_hMenu, v18, 1, &MenuInfo);
      }
      if ( ++v18 >= (unsigned int)v59 )
        goto LABEL_48;
    }
    MenuInfo.fMask = 354;
    v26 = nID;
    StringResourceHandle = AfxFindStringResourceHandle(nID);
    if ( StringResourceHandle
      && ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
           &strRes,
           StringResourceHandle,
           v26) )
    {
      AfxExtractSubString(&strMenu, strRes.m_pszData, 1, 0xAu);
    }
    else
    {
      ATL::CSimpleStringT<wchar_t,1>::Empty(&strMenu);
    }
    v28 = (CObject *)operator new(0x10u);
    v65 = v28;
    if ( v28 )
    {
      v28[1].__vftable = 0;
      v28->__vftable = (CObject_vtbl *)CBitmap::`vftable';
    }
    v29 = v22;
    CPtrArray::SetAtGrow(&bmp, v22, v28);
    m_nSize = bmp.m_nSize;
    m_pData = bmp.m_pData;
    if ( v56 && IsolationAwareImageList_GetImageInfo(v56->m_hImageList, iImage, &ImageInfo) )
    {
      CopyRect(&rcDst, &ImageInfo.rcImage);
      OffsetRect(&rcDst, -rcDst.left, -rcDst.top);
      if ( v22 >= m_nSize )
        goto LABEL_73;
      v30 = (CGdiObject *)m_pData[v22];
      CompatibleBitmap = CreateCompatibleBitmap(dcClient.m_hDC, rcDst.right, rcDst.bottom);
      CGdiObject::Attach(v30, CompatibleBitmap);
      v32 = m_pData[v29];
      v33 = 0;
      if ( v32 )
        v33 = v32[1].__vftable;
      v34 = SelectObject(dcDest.m_hDC, v33);
      v35 = CGdiObject::FromHandle(v34);
      if ( v29 >= m_nSize )
        goto LABEL_73;
      m_pData[v29] = v35;
      SysColor = GetSysColor(4);
      if ( !dcDest.m_hDC )
        goto LABEL_73;
      SetBkColor(dcDest.m_hDC, SysColor);
      ExtTextOutW(dcDest.m_hDC, 0, 0, 2u, &rcDst, 0, 0, 0);
      IsolationAwareImageList_Draw(v56->m_hImageList, iImage, dcDest.m_hDC, 0, 0, 1u);
      if ( v29 >= m_nSize )
        goto LABEL_73;
      v37 = m_pData[v29];
      v38 = 0;
      if ( v37 )
        v38 = v37[1].__vftable;
      v39 = SelectObject(dcDest.m_hDC, v38);
      v40 = CGdiObject::FromHandle(v39);
      if ( v29 >= m_nSize )
LABEL_73:
        AfxThrowInvalidArgException();
      m_pData[v29] = v40;
      MenuInfo.dwItemData = (unsigned __int64)v40;
      v22 = v48;
    }
    else
    {
      MenuInfo.dwItemData = 0;
    }
    v12 = strMenu.m_pszData;
    MenuInfo.dwTypeData = strMenu.m_pszData;
    MenuInfo.wID = nID;
    MenuInfo.fType = 256;
    v48 = ++v22;
    goto LABEL_46;
  }
LABEL_48:
  CopyRect(&rc, lprcSrc);
  CWnd::ClientToScreen(v61, &rc);
  CMenu::TrackPopupMenu(&menu, 0, rc.left, rc.bottom, pWnd, 0);
  *v63 = 0;
  v41 = 0;
  if ( v22 )
  {
    v42 = 0;
    do
    {
      if ( v42 < 0 || v42 >= m_nSize )
        AfxThrowInvalidArgException();
      v43 = m_pData[v42];
      if ( v43 )
        ((void (__fastcall *)(CObject *, __int64))v43->~CObject)(v43, 1);
      ++v41;
      ++v42;
    }
    while ( v41 < v48 );
  }
  free(m_pData);
  CClientDC::~CClientDC(&dcClient);
  CDC::~CDC(&dcDest);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
  v44 = strRes.m_pszData - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)strRes.m_pszData - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 8LL))(*(_QWORD *)v44);
  menu.m_MenuFont.__vftable = (CFont_vtbl *)CFont::`vftable';
  CGdiObject::~CGdiObject(&menu.m_MenuFont);
  menu.__vftable = (CChevronOwnerDrawMenu_vtbl *)CMenu::`vftable';
  CMenu::DestroyMenu(&menu);
  m_pszData = strClassName.m_pszData;
LABEL_68:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)m_pszData - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)m_pszData - 3) + 8LL))(*((_QWORD *)m_pszData - 3));
  return v7;
}

```

## disassembly

```asm
0x1802ace30  mov     [rsp-8+arg_8], rbx
0x1802ace35  push    rbp
0x1802ace36  push    rsi
0x1802ace37  push    rdi
0x1802ace38  push    r12
0x1802ace3a  push    r13
0x1802ace3c  push    r14
0x1802ace3e  push    r15
0x1802ace40  lea     rbp, [rsp-190h]
0x1802ace48  sub     rsp, 290h
0x1802ace4f  mov     rax, cs:__security_cookie
0x1802ace56  xor     rax, rsp
0x1802ace59  mov     [rbp+1C0h+var_38], rax
0x1802ace60  mov     [rbp+1C0h+var_1C0], pResult
0x1802ace64  mov     r12, pnm
0x1802ace67  mov     r15, this
0x1802ace6a  mov     [rbp+1C0h+pWnd], this
0x1802ace6e  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1802ace75  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x1802ace7c  mov     rax, [rax+18h]
0x1802ace80  call    cs:__guard_dispatch_icall_fptr
0x1802ace86  lea     rbx, [rax+18h]
0x1802ace8a  mov     [rsp+2C0h+strClassName.m_pszData], rbx
0x1802ace8f  lea     this, aRebarwindow32; "ReBarWindow32"
0x1802ace96  call    cs:__imp_wcslen
0x1802ace9c  mov     rdi, rax
0x1802ace9f  mov     esi, 1
0x1802acea4  add     edi, esi
0x1802acea6  js      loc_1802AD6F2
0x1802aceac  mov     __formal, esi
0x1802aceae  sub     __formal, [rbx-8]
0x1802aceb1  mov     ecx, [rbx-0Ch]
0x1802aceb4  sub     ecx, edi
0x1802aceb6  or      ecx, __formal
0x1802aceb8  jge     short loc_1802ACECB
0x1802aceba  mov     __formal, edi; nLength
0x1802acebc  lea     this, [rsp+2C0h+strClassName]; this
0x1802acec1  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x1802acec6  mov     rbx, [rsp+2C0h+strClassName.m_pszData]
0x1802acecb  mov     r8d, edi; nMaxCount
0x1802acece  mov     rdx, rbx; lpClassName
0x1802aced1  mov     this, [r12]; hWnd
0x1802aced5  call    cs:__imp_GetClassNameW
0x1802acedb  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x1802acedf  mov     this, rbx; Source
0x1802acee2  call    cs:__imp_wcsnlen
0x1802acee8  xor     r13d, r13d
0x1802aceeb  test    eax, eax
0x1802aceed  js      loc_1802AD6F2
0x1802acef3  cmp     eax, [rbx-0Ch]
0x1802acef6  jg      loc_1802AD6F2
0x1802acefc  mov     [rbx-10h], eax
0x1802aceff  cdqe
0x1802acf01  mov     [rbx+rax*2], r13w
0x1802acf06  mov     this, [r12]; hWnd
0x1802acf0a  call    ?FromHandlePermanent@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandlePermanent(HWND__ *)
0x1802acf0f  mov     r14, rax
0x1802acf12  mov     [rbp+1C0h+var_1D0], rax
0x1802acf16  lea     rdx, aRebarwindow32; "ReBarWindow32"
0x1802acf1d  mov     this, rbx; String1
0x1802acf20  call    cs:__imp_wcscmp
0x1802acf26  nop
0x1802acf27  test    eax, eax
0x1802acf29  jnz     loc_1802AD697
0x1802acf2f  test    r14, r14
0x1802acf32  jz      loc_1802AD697
0x1802acf38  lea     rdx, ?classCReBar@CReBar@@2UCRuntimeClass@@B; pClass
0x1802acf3f  mov     this, r14; this
0x1802acf42  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1802acf47  test    eax, eax
0x1802acf49  jz      loc_1802AD697
0x1802acf4f  mov     this, r14; this
0x1802acf52  call    ?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetParentFrame(void)
0x1802acf57  test    rax, rax
0x1802acf5a  jz      short loc_1802ACF65
0x1802acf5c  cmp     r15, rax
0x1802acf5f  jnz     loc_1802AD697
0x1802acf65  xorps   xmm0, xmm0
0x1802acf68  movups  xmmword ptr [rbp+1C0h+rcBand.left], xmm0
0x1802acf6f  xorps   xmm1, xmm1
0x1802acf72  movups  xmmword ptr [rbp+1C0h+rcBtn.left], xmm1
0x1802acf79  movups  xmmword ptr [rbp+1C0h+rcInt.left], xmm0
0x1802acf80  lea     this, [rbp+1C0h+menu]; this
0x1802acf84  call    ??0CChevronOwnerDrawMenu@@QEAA@XZ; CChevronOwnerDrawMenu::CChevronOwnerDrawMenu(void)
0x1802acf89  nop
0x1802acf8a  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1802acf91  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x1802acf98  mov     rax, [rax+18h]
0x1802acf9c  call    cs:__guard_dispatch_icall_fptr
0x1802acfa2  add     rax, 18h
0x1802acfa6  mov     [rsp+2C0h+strRes.m_pszData], rax
0x1802acfab  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x1802acfb2  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x1802acfb9  mov     rax, [rax+18h]
0x1802acfbd  call    cs:__guard_dispatch_icall_fptr
0x1802acfc3  lea     rdi, [rax+18h]
0x1802acfc7  mov     [rsp+2C0h+strMenu.m_pszData], rdi
0x1802acfcc  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1802acfd3  mov     [rsp+2C0h+dcDest.__vftable], rax
0x1802acfd8  xorps   xmm0, xmm0
0x1802acfdb  movdqu  xmmword ptr [rsp+2C0h+dcDest.m_hDC], xmm0
0x1802acfe1  mov     [rbp+1C0h+dcDest.m_bPrinting], r13d
0x1802acfe5  mov     rdx, r15; pWnd
0x1802acfe8  lea     this, [rbp+1C0h+dcClient]; this
0x1802acfec  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x1802acff1  nop
0x1802acff2  mov     eax, [r14+148h]
0x1802acff9  mov     [rbp+1C0h+BandInfo.cbSize], eax
0x1802acfff  mov     [rbp+1C0h+BandInfo.fMask], 10h
0x1802ad009  mov     r8d, [r12+18h]; wParam
0x1802ad00e  lea     pResult, [rbp+1C0h+BandInfo]; lParam
0x1802ad015  mov     __formal, 41Ch; Msg
0x1802ad01a  mov     this, [r14+40h]; hWnd
0x1802ad01e  call    cs:__imp_SendMessageW
0x1802ad024  mov     r8d, [r12+18h]; wParam
0x1802ad029  lea     pResult, [rbp+1C0h+rcBand]; lParam
0x1802ad030  mov     __formal, 409h; Msg
0x1802ad035  mov     this, [r14+40h]; hWnd
0x1802ad039  call    cs:__imp_SendMessageW
0x1802ad03f  lea     this, aToolbarwindow3; "ToolbarWindow32"
0x1802ad046  call    cs:__imp_wcslen
0x1802ad04c  mov     r15, rax
0x1802ad04f  add     r15d, esi
0x1802ad052  js      loc_1802AD6E7
0x1802ad058  mov     __formal, esi
0x1802ad05a  sub     __formal, [rbx-8]
0x1802ad05d  mov     ecx, [rbx-0Ch]
0x1802ad060  sub     ecx, r15d
0x1802ad063  or      ecx, __formal
0x1802ad065  jge     short loc_1802AD079
0x1802ad067  mov     __formal, r15d; nLength
0x1802ad06a  lea     this, [rsp+2C0h+strClassName]; this
0x1802ad06f  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x1802ad074  mov     rbx, [rsp+2C0h+strClassName.m_pszData]
0x1802ad079  mov     r8d, r15d; nMaxCount
0x1802ad07c  mov     rdx, rbx; lpClassName
0x1802ad07f  mov     this, [rbp+1C0h+BandInfo.hwndChild]; hWnd
0x1802ad086  call    cs:__imp_GetClassNameW
0x1802ad08c  movsxd  rdx, dword ptr [rbx-0Ch]; MaxCount
0x1802ad090  mov     this, rbx; Source
0x1802ad093  call    cs:__imp_wcsnlen
0x1802ad099  test    eax, eax
0x1802ad09b  js      loc_1802AD6E7
0x1802ad0a1  cmp     eax, [rbx-0Ch]
0x1802ad0a4  jg      loc_1802AD6E7
0x1802ad0aa  mov     [rbx-10h], eax
0x1802ad0ad  cdqe
0x1802ad0af  mov     [rbx+rax*2], r13w
0x1802ad0b4  mov     this, [rbp+1C0h+BandInfo.hwndChild]; hWnd
0x1802ad0bb  call    ?FromHandlePermanent@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandlePermanent(HWND__ *)
0x1802ad0c0  mov     r13, rax
0x1802ad0c3  lea     rdx, aToolbarwindow3; "ToolbarWindow32"
0x1802ad0ca  mov     this, rbx; String1
0x1802ad0cd  call    cs:__imp_wcscmp
0x1802ad0d3  nop
0x1802ad0d4  test    eax, eax
0x1802ad0d6  jnz     loc_1802AD5EB
0x1802ad0dc  test    r13, r13
0x1802ad0df  jz      loc_1802AD5EB
0x1802ad0e5  lea     rdx, ??_7CStatusBar@@6B@+378h; pClass
0x1802ad0ec  mov     this, r13; this
0x1802ad0ef  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x1802ad0f4  test    eax, eax
0x1802ad0f6  jz      loc_1802AD5EB
0x1802ad0fc  lea     rax, [r12+28h]
0x1802ad101  mov     [rbp+1C0h+lprcSrc], rax
0x1802ad105  mov     eax, [rax]
0x1802ad107  mov     [rbp+1C0h+rcBand.right], eax
0x1802ad10d  lea     rdx, [rbp+1C0h+rcBand]; lpRect
0x1802ad114  mov     this, r14; this
0x1802ad117  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x1802ad11c  lea     rdx, [rbp+1C0h+rcBand]; lpRect
0x1802ad123  mov     this, r13; this
0x1802ad126  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1802ad12b  xor     r9d, r9d; lParam
0x1802ad12e  xor     r8d, r8d; wParam
0x1802ad131  mov     __formal, 418h; Msg
0x1802ad136  mov     this, [r13+40h]; hWnd
0x1802ad13a  call    cs:__imp_SendMessageW
0x1802ad140  mov     r15, rax
0x1802ad143  mov     [rbp+1C0h+var_1E0], rax
0x1802ad147  mov     r14d, eax
0x1802ad14a  xor     r12d, r12d
0x1802ad14d  dec     r14d
0x1802ad150  movsxd  pnm, r14d; wParam
0x1802ad153  lea     pResult, [rbp+1C0h+rcBtn]; lParam
0x1802ad15a  mov     __formal, 41Dh; Msg
0x1802ad15f  mov     this, [r13+40h]; hWnd
0x1802ad163  call    cs:__imp_SendMessageW
0x1802ad169  lea     pnm, [rbp+1C0h+rcBtn]; lprcSrc2
0x1802ad170  lea     rdx, [rbp+1C0h+rcBand]; lprcSrc1
0x1802ad177  lea     this, [rbp+1C0h+rcInt]; lprcDst
0x1802ad17e  call    cs:__imp_IntersectRect
0x1802ad184  test    eax, eax
0x1802ad186  jnz     short loc_1802AD18D
0x1802ad188  test    r14d, r14d
0x1802ad18b  jnz     short loc_1802AD14D
0x1802ad18d  mov     ebx, 50h ; 'P'
0x1802ad192  mov     r8d, ebx; Size
0x1802ad195  xor     __formal, __formal; Val
0x1802ad197  lea     this, [rbp+1C0h+MenuInfo]; void *
0x1802ad19b  call    cs:__imp_memset
0x1802ad1a1  mov     [rbp+1C0h+MenuInfo.cbSize], ebx
0x1802ad1a4  xor     r9d, r9d; lParam
0x1802ad1a7  xor     r8d, r8d; wParam
0x1802ad1aa  mov     __formal, 431h; Msg
0x1802ad1af  mov     this, [r13+40h]; hWnd
0x1802ad1b3  call    cs:__imp_SendMessageW
0x1802ad1b9  mov     this, rax; h
0x1802ad1bc  call    ?FromHandle@CImageList@@SAPEAV1@PEAU_IMAGELIST@@@Z; CImageList::FromHandle(_IMAGELIST *)
0x1802ad1c1  mov     [rbp+1C0h+var_230], rax
0x1802ad1c5  mov     [rbp+1C0h+bmp.m_pData], r12
0x1802ad1c9  mov     [rbp+1C0h+bmp.m_nGrowBy], r12
0x1802ad1cd  mov     [rbp+1C0h+bmp.m_nMaxSize], r12
0x1802ad1d1  mov     [rbp+1C0h+bmp.m_nSize], r12
0x1802ad1d5  lea     rax, ??_7?$CTypedPtrArray@VCObArray@@PEAVCBitmap@@@@6B@; const CTypedPtrArray<CObArray,CBitmap *>::`vftable'
0x1802ad1dc  mov     [rbp+1C0h+bmp.__vftable], rax
0x1802ad1e0  mov     __formal, r15d
0x1802ad1e3  sub     __formal, r14d; nNewSize
0x1802ad1e6  or      pnm, 0FFFFFFFFFFFFFFFFh; nGrowBy
0x1802ad1ea  lea     this, [rbp+1C0h+bmp]; this
0x1802ad1ee  call    ?SetSize@CObArray@@QEAAX_J0@Z; CObArray::SetSize(__int64,__int64)
0x1802ad1f3  call    cs:__imp_CreatePopupMenu
0x1802ad1f9  mov     rdx, rax; hMenu
0x1802ad1fc  lea     this, [rbp+1C0h+menu]; this
0x1802ad200  call    ?Attach@CMenu@@QEAAHPEAUHMENU__@@@Z; CMenu::Attach(HMENU__ *)
0x1802ad205  mov     this, [rbp+1C0h+dcClient.m_hDC]; hdc
0x1802ad209  call    cs:__imp_CreateCompatibleDC
0x1802ad20f  mov     rdx, rax; hDC
0x1802ad212  lea     this, [rsp+2C0h+dcDest]; this
0x1802ad217  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802ad21c  mov     ebx, r12d
0x1802ad21f  mov     [rsp+2C0h+var_280], ebx
0x1802ad223  mov     r12, [rbp+1C0h+bmp.m_nSize]
0x1802ad227  cmp     r14d, r15d
0x1802ad22a  mov     r15, [rbp+1C0h+bmp.m_pData]
0x1802ad22e  jnb     loc_1802AD4B9
0x1802ad234  lea     rax, [rsp+2C0h+iImage]
0x1802ad239  mov     [rsp+2C0h+lprect], rax; iImage
0x1802ad23e  lea     pResult, [rsp+2C0h+nStyle]; nStyle
0x1802ad243  lea     pnm, [rsp+2C0h+nID]; nID
0x1802ad248  mov     __formal, r14d; nIndex
0x1802ad24b  mov     this, r13; this
0x1802ad24e  call    ?GetButtonInfo@CToolBar@@QEBAXHAEAI0AEAH@Z; CToolBar::GetButtonInfo(int,uint &,uint &,int &)
0x1802ad253  test    byte ptr [rsp+2C0h+nStyle], sil
0x1802ad258  jnz     loc_1802AD486
0x1802ad25e  mov     [rbp+1C0h+MenuInfo.fMask], 162h
0x1802ad265  mov     edi, [rsp+2C0h+nID]
0x1802ad269  mov     ecx, edi; nID
0x1802ad26b  call    ?AfxFindStringResourceHandle@@YAPEAUHINSTANCE__@@I@Z; AfxFindStringResourceHandle(uint)
0x1802ad270  nop
0x1802ad271  test    rax, rax
0x1802ad274  jz      short loc_1802AD2A4
0x1802ad276  mov     r8d, edi; nID
0x1802ad279  mov     rdx, rax; hInstance
0x1802ad27c  lea     this, [rsp+2C0h+strRes]; this
0x1802ad281  call    ?LoadStringW@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x1802ad286  test    eax, eax
0x1802ad288  jz      short loc_1802AD2A4
0x1802ad28a  mov     r9d, 0Ah; chSep
0x1802ad290  mov     r8d, esi; iSubString
0x1802ad293  mov     rdx, [rsp+2C0h+strRes.m_pszData]; lpszFullString
0x1802ad298  lea     this, [rsp+2C0h+strMenu]; rString
0x1802ad29d  call    ?AfxExtractSubString@@YAHAEAV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@PEB_WH_W@Z; AfxExtractSubString(ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,wchar_t const *,int,wchar_t)
0x1802ad2a2  jmp     short loc_1802AD2AE
0x1802ad2a4  lea     this, [rsp+2C0h+strMenu]; this
0x1802ad2a9  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x1802ad2ae  mov     ecx, 10h; nSize
0x1802ad2b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802ad2b8  mov     [rbp+1C0h+var_160], rax
0x1802ad2bc  test    rax, rax
0x1802ad2bf  jz      short loc_1802AD2D0
0x1802ad2c1  and     qword ptr [rax+8], 0
0x1802ad2c6  lea     this, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802ad2cd  mov     [rax], this
0x1802ad2d0  mov     edi, ebx
0x1802ad2d2  mov     pnm, rax; newElement
0x1802ad2d5  mov     __formal, ebx; nIndex
0x1802ad2d7  lea     this, [rbp+1C0h+bmp]; this
0x1802ad2db  call    ?SetAtGrow@CPtrArray@@QEAAX_JPEAX@Z; CPtrArray::SetAtGrow(__int64,void *)
0x1802ad2e0  mov     r12, [rbp+1C0h+bmp.m_nSize]
0x1802ad2e4  mov     r15, [rbp+1C0h+bmp.m_pData]
0x1802ad2e8  mov     rax, [rbp+1C0h+var_230]
0x1802ad2ec  test    rax, rax
0x1802ad2ef  jz      loc_1802AD462
0x1802ad2f5  lea     pnm, [rbp+1C0h+ImageInfo]; pImageInfo
0x1802ad2fc  mov     __formal, [rsp+2C0h+iImage]; i
0x1802ad300  mov     this, [rax+8]; himl
0x1802ad304  call    IsolationAwareImageList_GetImageInfo
0x1802ad309  test    eax, eax
0x1802ad30b  jz      loc_1802AD462
0x1802ad311  lea     rdx, [rbp+1C0h+ImageInfo.rcImage]; lprcSrc
0x1802ad318  lea     this, [rbp+1C0h+rcDst]; lprcDst
0x1802ad31f  call    cs:__imp_CopyRect
0x1802ad325  mov     r8d, [rbp+1C0h+rcDst.top]
0x1802ad32c  neg     r8d; dy
0x1802ad32f  mov     __formal, [rbp+1C0h+rcDst.left]
0x1802ad335  neg     __formal; dx
0x1802ad337  lea     this, [rbp+1C0h+rcDst]; lprc
0x1802ad33e  call    cs:__imp_OffsetRect
  ... truncated ...
```
