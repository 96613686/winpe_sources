# CView::OnFilePrint(void)

- ea: `0x18028e0d0`
- end: `0x18028ed6c`
- name: `?OnFilePrint@CView@@IEAAXXZ`
- size: `3228`
- prototype: `void __fastcall(CView *this)`
- caller_count: `0`
- callee_count: `39`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800030d0`
- `0x180003230`
- `0x1800033dc`
- `0x18000ddc0`
- `0x18000df50`
- `0x18000e0e0`
- `0x180139860`
- `0x180139950`
- `0x180153990`
- `0x1801d62b0`
- `0x1801d7400`
- `0x180211ee0`
- `0x180211f40`
- `0x180212100`
- `0x180214260`
- `0x180214650`
- `0x1802160f0`
- `0x1802163c0`
- `0x1802235c0`
- `0x180223660`
- `0x180231d70`
- `0x1802334f0`
- `0x18028de70`
- `0x18028e0d0`
- `0x18028ed70`
- `0x18028ee30`
- `0x180296b90`
- `0x180297a80`
- `0x180297dd0`
- `0x18029a390`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802aef40`
- `0x1802b6170`
- `0x1802b6730`
- `0x1802b6790`
- `0x1802bbce0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18028ea9c`
- `KERNEL32!GetLastError` at `0x18028eb40`
- `KERNEL32!GetLastError` at `0x18028ea9c`
- `KERNEL32!GetLastError` at `0x18028eb40`
- `VCRUNTIME140!memset` at `0x18028e495`
- `VCRUNTIME140!memset` at `0x18028e495`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18028eb90`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18028eb90`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18028eb52`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18028eb52`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e937`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e93f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e96b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e976`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e9a7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e937`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e93f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e96b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e976`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18028e9a7`
- `USER32!SetRect` at `0x18028e9f9`
- `USER32!SetRect` at `0x18028e9f9`
- `USER32!UpdateWindow` at `0x18028e6e5`
- `USER32!UpdateWindow` at `0x18028e6e5`
- `GDI32!DeleteDC` at `0x18028e7b6`
- `GDI32!DeleteDC` at `0x18028e7b6`
- `GDI32!EndDoc` at `0x18028ec01`
- `GDI32!EndDoc` at `0x18028ec01`
- `GDI32!EndPage` at `0x18028ea8e`
- `GDI32!EndPage` at `0x18028ea8e`
- `GDI32!StartPage` at `0x18028ea1c`
- `GDI32!StartPage` at `0x18028ea1c`
- `GDI32!GetDeviceCaps` at `0x18028e9ce`
- `GDI32!GetDeviceCaps` at `0x18028e9e0`
- `GDI32!GetDeviceCaps` at `0x18028e9ce`
- `GDI32!GetDeviceCaps` at `0x18028e9e0`
- `GDI32!CreateDCW` at `0x18028e158`
- `GDI32!CreateDCW` at `0x18028e158`
- `GDI32!SetAbortProc` at `0x18028e5c1`
- `GDI32!SetAbortProc` at `0x18028e5c1`
- `GDI32!StartDocW` at `0x18028e701`
- `GDI32!StartDocW` at `0x18028e701`
- `GDI32!DPtoLP` at `0x18028ea11`
- `GDI32!DPtoLP` at `0x18028ea11`
- `GDI32!AbortDoc` at `0x18028ebf4`
- `GDI32!AbortDoc` at `0x18028ebf4`
- `WINSPOOL!OpenPrinterW` at `0x18028eae2`
- `WINSPOOL!OpenPrinterW` at `0x18028eae2`
- `WINSPOOL!GetJobW` at `0x18028eb36`
- `WINSPOOL!GetJobW` at `0x18028eb81`
- `WINSPOOL!GetJobW` at `0x18028eb36`
- `WINSPOOL!GetJobW` at `0x18028eb81`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
void __fastcall CView::OnFilePrint(CView *this)
{
  CCommandLineInfo *m_pCmdInfo; // rcx
  HDC DCW; // rax
  wchar_t *v4; // rbx
  _QWORD *v5; // rdx
  wchar_t *v6; // rdx
  wchar_t *v7; // rdx
  wchar_t *m_pszData; // rdx
  const ATL::CSimpleStringT<wchar_t,0> *PathName; // rax
  int (__fastcall **v10)(CDC *, wchar_t *, int, tagRECT *, unsigned int, tagDRAWTEXTPARAMS *); // rdx
  _QWORD *v11; // rdx
  wchar_t *v12; // rdx
  wchar_t *v13; // rdx
  wchar_t *v14; // rdx
  CDocument *m_pDocument; // rdx
  CFrameWnd *ParentFrame; // rax
  ATL::CStringData *v17; // rax
  wchar_t *v18; // rdx
  const ATL::CSimpleStringT<wchar_t,0> *PortName; // rax
  int (__fastcall **p_DrawTextExW)(CDC *, wchar_t *, int, tagRECT *, unsigned int, tagDRAWTEXTPARAMS *); // rdx
  CWinThread *m_pCurrentWinThread; // rcx
  wchar_t *v22; // rbx
  CNoTrackObject *Data; // rax
  wchar_t *v24; // rsi
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *DeviceName; // rax
  int (__fastcall **v26)(CDC *, wchar_t *, int, tagRECT *, unsigned int, tagDRAWTEXTPARAMS *); // rdx
  HDC v27; // rax
  _QWORD *v28; // rdx
  volatile signed __int32 *v29; // rdx
  unsigned __int16 *v30; // rdx
  unsigned int v31; // r8d
  unsigned int v32; // r9d
  unsigned int v33; // ecx
  unsigned int v34; // r13d
  unsigned int v35; // r12d
  int v36; // r15d
  unsigned int v37; // r14d
  HINSTANCE__ *StringResourceHandle; // rax
  int v39; // esi
  int v40; // ebx
  int *v41; // rax
  int DeviceCaps; // ebx
  int v43; // eax
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *v44; // rax
  LPWSTR *p_m_pszData; // rbx
  BOOL v46; // ebx
  _QWORD *v47; // rdx
  unsigned __int8 *v48; // r15
  BOOL JobW; // ebx
  int v50; // r12d
  wchar_t *v51; // rdx
  _QWORD *v52; // rdx
  wchar_t *v53; // rdx
  wchar_t *v54; // rdx
  unsigned int dwFlags[2]; // [rsp+28h] [rbp-E0h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strCaption; // [rsp+58h] [rbp-B0h] BYREF
  void *hPrinter; // [rsp+60h] [rbp-A8h] BYREF
  CDC dcPrint; // [rsp+68h] [rbp-A0h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strTitle; // [rsp+88h] [rbp-80h]
  ATL::CSimpleStringT<wchar_t,1> cBytesNeeded; // [rsp+90h] [rbp-78h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strDef; // [rsp+98h] [rbp-70h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strOutput; // [rsp+A0h] [rbp-68h] BYREF
  ATL::CSimpleStringT<wchar_t,1> cBytesUsed; // [rsp+A8h] [rbp-60h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > v64; // [rsp+B0h] [rbp-58h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strTemp; // [rsp+B8h] [rbp-50h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > v66; // [rsp+C0h] [rbp-48h] BYREF
  _DOCINFOW docInfo; // [rsp+C8h] [rbp-40h] BYREF
  CPrintingDialog dlgPrintStatus; // [rsp+F0h] [rbp-18h] BYREF
  CPrintInfo printInfo; // [rsp+220h] [rbp+118h] BYREF
  wchar_t szBuf[80]; // [rsp+270h] [rbp+168h] BYREF
  __int64 v71; // [rsp+3A8h] [rbp+2A0h]

  CPrintInfo::CPrintInfo((CPrintInfo *)&printInfo.m_bDocObject);
  if ( LOWORD(CWnd::GetCurrentMessage()->wParam) == 0xE108 )
  {
    m_pCmdInfo = AfxGetModuleState()->m_pCurrentWinApp->m_pCmdInfo;
    if ( m_pCmdInfo )
    {
      if ( m_pCmdInfo->m_nShellCommand == FilePrintTo )
      {
        DCW = CreateDCW(
                m_pCmdInfo->m_strDriverName.m_pszData,
                m_pCmdInfo->m_strPrinterName.m_pszData,
                m_pCmdInfo->m_strPortName.m_pszData,
                0);
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&printInfo.m_bDocObject + 304LL) + 32LL) = DCW;
        if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&printInfo.m_bDocObject + 304LL) + 32LL) )
        {
          AfxMessageBox(0xF106u, 0, 0xFFFFFFFF);
          goto LABEL_120;
        }
      }
    }
    printInfo.m_nCurPage = 1;
  }
  if ( !this->OnPreparePrinting(this, (CPrintInfo *)&printInfo.m_bDocObject) )
    goto LABEL_120;
  v4 = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  cBytesUsed.m_pszData = v4;
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)&printInfo.m_bDocObject + 304LL) + 40LL) & 0x20) == 0 || printInfo.m_bDirect )
  {
LABEL_29:
    cBytesNeeded.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    m_pDocument = this->m_pDocument;
    if ( m_pDocument )
    {
      ATL::CSimpleStringT<wchar_t,1>::operator=(
        &cBytesNeeded,
        (const ATL::CSimpleStringT<wchar_t,0> *)&m_pDocument->m_strTitle);
    }
    else
    {
      ParentFrame = CWnd::GetParentFrame(this);
      if ( !ParentFrame )
        AfxThrowInvalidArgException();
      CWnd::GetWindowTextW(
        ParentFrame,
        (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&cBytesNeeded);
    }
    memset(&docInfo.lpszDocName, 0, sizeof(_DOCINFOW));
    LODWORD(docInfo.lpszDocName) = 40;
    docInfo.lpszOutput = cBytesNeeded.m_pszData;
    v17 = afxStringManager.GetNilString(&afxStringManager);
    v18 = (wchar_t *)&v17[1];
    hPrinter = &v17[1];
    if ( *((_DWORD *)v4 - 4) )
    {
      docInfo.lpszDatatype = v4;
      if ( ((1 - v17->nRefs) | (v17->nAllocLength - 260)) < 0 )
      {
        ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2((ATL::CSimpleStringT<wchar_t,1> *)&hPrinter, 260);
        v18 = (wchar_t *)hPrinter;
      }
      AfxGetFileTitle(v4, v18, 0x104u);
    }
    else
    {
      docInfo.lpszDatatype = 0;
      PortName = (const ATL::CSimpleStringT<wchar_t,0> *)CPrintDialog::GetPortName(
                                                           *(CPrintDialog **)&printInfo.m_bDocObject,
                                                           (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&dcPrint);
      ATL::CSimpleStringT<wchar_t,1>::operator=((ATL::CSimpleStringT<wchar_t,1> *)&hPrinter, PortName);
      p_DrawTextExW = &dcPrint.__vftable[-1].DrawTextExW;
      if ( _InterlockedDecrement((volatile signed __int32 *)&dcPrint.__vftable[-1].Escape) <= 0 )
        (*(void (__fastcall **)(int (__fastcall *)(CDC *, wchar_t *, int, tagRECT *, unsigned int, tagDRAWTEXTPARAMS *)))(*(_QWORD *)*p_DrawTextExW + 8LL))(*p_DrawTextExW);
    }
    dcPrint.m_hDC = (HDC__ *)CDC::`vftable';
    *(_OWORD *)&dcPrint.m_hAttribDC = 0;
    LODWORD(strTitle.m_pszData) = 0;
    if ( !printInfo.m_bDirect )
    {
      CDC::Attach((CDC *)&dcPrint.m_hDC, *(HDC__ **)(*(_QWORD *)(*(_QWORD *)&printInfo.m_bDocObject + 304LL) + 32LL));
      LODWORD(strTitle.m_pszData) = 1;
    }
    this->OnBeginPrinting(this, (CDC *)&dcPrint.m_hDC, (CPrintInfo *)&printInfo.m_bDocObject);
    if ( !printInfo.m_bDirect )
      SetAbortProc(dcPrint.m_hAttribDC, _AfxAbortProc);
    m_pCurrentWinThread = AfxGetModuleThreadState()->m_pCurrentWinThread;
    if ( m_pCurrentWinThread )
      v22 = (wchar_t *)m_pCurrentWinThread->GetMainWnd(m_pCurrentWinThread);
    else
      v22 = 0;
    strCaption.m_pszData = v22;
    CWnd::EnableWindow((CWnd *)v22, 0);
    CDialog::CDialog((CDialog *)&dlgPrintStatus.m_dwRef);
    *(_QWORD *)&dlgPrintStatus.m_dwRef = CPrintingDialog::`vftable';
    CDialog::Create((CDialog *)&dlgPrintStatus.m_dwRef, (const wchar_t *)0x7802, this);
    Data = CProcessLocalObject::GetData(&_afxWinState, CProcessLocal<_AFX_WIN_STATE>::CreateObject);
    if ( !Data )
      AfxThrowInvalidArgException();
    LODWORD(Data[1].__vftable) = 0;
    v24 = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    v66.m_pszData = v24;
    CWnd::SetDlgItemTextW((CWnd *)&dlgPrintStatus.m_dwRef, 201, cBytesNeeded.m_pszData);
    DeviceName = CPrintDialog::GetDeviceName(
                   *(CPrintDialog **)&printInfo.m_bDocObject,
                   (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&dcPrint);
    CWnd::SetDlgItemTextW((CWnd *)&dlgPrintStatus.m_dwRef, 202, DeviceName->m_pszData);
    v26 = &dcPrint.__vftable[-1].DrawTextExW;
    if ( _InterlockedDecrement((volatile signed __int32 *)&dcPrint.__vftable[-1].Escape) <= 0 )
      (*(void (__fastcall **)(int (__fastcall *)(CDC *, wchar_t *, int, tagRECT *, unsigned int, tagDRAWTEXTPARAMS *)))(*(_QWORD *)*v26 + 8LL))(*v26);
    CWnd::SetDlgItemTextW((CWnd *)&dlgPrintStatus.m_dwRef, 203, (const wchar_t *)hPrinter);
    CWnd::ShowWindow((CWnd *)&dlgPrintStatus.m_dwRef, 5);
    UpdateWindow(*(HWND *)&dlgPrintStatus.m_bEnableActiveAccessibility);
    if ( !printInfo.m_bDirect )
    {
      printInfo.m_dwFlags = StartDocW(dcPrint.m_hAttribDC, (const DOCINFOW *)&docInfo.lpszDocName);
      if ( printInfo.m_dwFlags == -1 )
      {
        CWnd::EnableWindow((CWnd *)v22, 1);
        this->OnEndPrinting(this, (CDC *)&dcPrint.m_hDC, (CPrintInfo *)&printInfo.m_bDocObject);
        CWnd::DestroyWindow((CWnd *)&dlgPrintStatus.m_dwRef);
        CDC::Detach((CDC *)&dcPrint.m_hDC);
        AfxMessageBox(0xF106u, 0, 0xFFFFFFFF);
        if ( _InterlockedDecrement((volatile signed __int32 *)v24 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v24 - 3) + 8LL))(*((_QWORD *)v24 - 3));
        *(_QWORD *)&dlgPrintStatus.m_dwRef = CPrintingDialog::`vftable';
        CDialog::~CDialog((CDialog *)&dlgPrintStatus.m_dwRef);
        dcPrint.m_hDC = (HDC__ *)CDC::`vftable';
        if ( dcPrint.m_hAttribDC )
        {
          v27 = CDC::Detach((CDC *)&dcPrint.m_hDC);
          DeleteDC(v27);
        }
        v28 = (char *)hPrinter - 24;
        if ( _InterlockedDecrement((volatile signed __int32 *)hPrinter - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v28 + 8LL))(*v28);
        m_pszData = cBytesNeeded.m_pszData;
        goto LABEL_58;
      }
    }
    v30 = *(unsigned __int16 **)(*(_QWORD *)&printInfo.m_bDocObject + 304LL);
    v31 = v30[22];
    v32 = v30[24];
    v33 = v32;
    if ( v30[23] >= v32 )
      v33 = v30[23];
    v34 = v30[25];
    v35 = v34;
    if ( v33 <= v34 )
      v35 = v33;
    LODWORD(strOutput.m_pszData) = v35;
    if ( v31 >= v32 )
      v32 = v31;
    if ( v32 <= v34 )
      v34 = v32;
    v36 = v35 < v34 ? -1 : 1;
    LODWORD(strTemp.m_pszData) = v36;
    v37 = v35 + v36;
    if ( v35 == 0xFFFF )
      v37 = 0xFFFF;
    StringResourceHandle = AfxFindStringResourceHandle(0xF043u);
    if ( StringResourceHandle )
      ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
        &v66,
        StringResourceHandle,
        0xF043u);
    v39 = 0;
    if ( printInfo.m_bDirect )
    {
      this->OnPrepareDC(this, (CDC *)&dcPrint.m_hDC, (CPrintInfo *)&printInfo.m_bDocObject);
      this->OnPrint(this, (CDC *)&dcPrint.m_hDC, (CPrintInfo *)&printInfo.m_bDocObject);
    }
    else
    {
      LODWORD(printInfo.m_strPageDesc.m_pszData) = v34;
      if ( v34 == v37 )
        goto LABEL_111;
      do
      {
        this->OnPrepareDC(this, (CDC *)&dcPrint.m_hDC, (CPrintInfo *)&printInfo.m_bDocObject);
        if ( !printInfo.m_nNumPreviewPages )
          break;
        v40 = *_errno();
        *_errno() = 0;
        dwFlags[0] = (unsigned int)printInfo.m_strPageDesc.m_pszData;
        snwprintf_s(&szBuf[4], 0x50u, 0x4Fu, v66.m_pszData, *(_QWORD *)dwFlags);
        if ( *_errno() )
        {
          v41 = _errno();
          if ( *v41 )
          {
            if ( *v41 == 12 )
              ATL::AtlThrowImpl(-2147024882);
            if ( *v41 == 22 || *v41 == 34 )
              ATL::AtlThrowImpl(-2147024809);
            if ( *v41 != 80 )
              ATL::AtlThrowImpl(-2147467259);
          }
        }
        else
        {
          *_errno() = v40;
        }
        CWnd::SetDlgItemTextW((CWnd *)&dlgPrintStatus.m_dwRef, 204, &szBuf[4]);
        DeviceCaps = GetDeviceCaps(*(HDC *)&dcPrint.m_bPrinting, 10);
        v43 = GetDeviceCaps(*(HDC *)&dcPrint.m_bPrinting, 8);
        SetRect((LPRECT)&printInfo.m_rectDraw.right, 0, 0, v43, DeviceCaps);
        DPtoLP(*(HDC *)&dcPrint.m_bPrinting, (LPPOINT)&printInfo.m_rectDraw.right, 2);
        if ( StartPage(dcPrint.m_hAttribDC) < 0 )
          goto LABEL_106;
        this->OnPrepareDC(this, (CDC *)&dcPrint.m_hDC, (CPrintInfo *)&printInfo.m_bDocObject);
        this->OnPrint(this, (CDC *)&dcPrint.m_hDC, (CPrintInfo *)&printInfo.m_bDocObject);
        if ( v35 >= v34
          && v37 > v36
                 + (unsigned int)*(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)&printInfo.m_bDocObject + 304LL) + 50LL) )
        {
          v37 = v36 + *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)&printInfo.m_bDocObject + 304LL) + 50LL);
        }
        if ( EndPage(dcPrint.m_hAttribDC) < 0 && GetLastError() )
        {
          v44 = CPrintDialog::GetDeviceName(
                  *(CPrintDialog **)&printInfo.m_bDocObject,
                  (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&docInfo);
          p_m_pszData = &v44->m_pszData;
          if ( *((int *)v44->m_pszData - 2) > 1 )
            ATL::CSimpleStringT<wchar_t,1>::Fork(v44, *((_DWORD *)v44->m_pszData - 4));
          v46 = OpenPrinterW(*p_m_pszData, (LPHANDLE)&dcPrint.__vftable, 0);
          v47 = (_QWORD *)(*(_QWORD *)&docInfo.cbSize - 24LL);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&docInfo.cbSize - 24LL + 16), 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v47 + 8LL))(*v47);
          if ( !v46
            || !GetJobW(dcPrint.__vftable, printInfo.m_dwFlags, 1u, 0, 0, (LPDWORD)&strDef) && GetLastError() != 122
            || (v48 = (unsigned __int8 *)malloc(LODWORD(strDef.m_pszData))) == 0 )
          {
            v39 = 1;
            break;
          }
          JobW = GetJobW(dcPrint.__vftable, printInfo.m_dwFlags, 1u, v48, (DWORD)strDef.m_pszData, (LPDWORD)&v64);
          v50 = *((_DWORD *)v48 + 14);
          free(v48);
          if ( !JobW || (v50 & 0x800) == 0 )
          {
LABEL_106:
            v39 = 1;
            break;
          }
          v36 = (int)strTemp.m_pszData;
          v35 = (unsigned int)strOutput.m_pszData;
        }
        if ( !_AfxAbortProc(dcPrint.m_hAttribDC, 0) )
          goto LABEL_106;
        LODWORD(printInfo.m_strPageDesc.m_pszData) += v36;
      }
      while ( LODWORD(printInfo.m_strPageDesc.m_pszData) != v37 );
      v22 = strCaption.m_pszData;
    }
    if ( printInfo.m_bDirect )
    {
LABEL_112:
      CWnd::EnableWindow((CWnd *)v22, 1);
      this->OnEndPrinting(this, (CDC *)&dcPrint.m_hDC, (CPrintInfo *)&printInfo.m_bDocObject);
      CWnd::DestroyWindow((CWnd *)&dlgPrintStatus.m_dwRef);
      CDC::Detach((CDC *)&dcPrint.m_hDC);
      v51 = v66.m_pszData - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)v66.m_pszData - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v51 + 8LL))(*(_QWORD *)v51);
      *(_QWORD *)&dlgPrintStatus.m_dwRef = CPrintingDialog::`vftable';
      CDialog::~CDialog((CDialog *)&dlgPrintStatus.m_dwRef);
      CDC::~CDC((CDC *)&dcPrint.m_hDC);
      v52 = (char *)hPrinter - 24;
      if ( _InterlockedDecrement((volatile signed __int32 *)hPrinter - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v52 + 8LL))(*v52);
      v53 = cBytesNeeded.m_pszData - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)cBytesNeeded.m_pszData - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 8LL))(*(_QWORD *)v53);
      goto LABEL_118;
    }
    if ( v39 )
    {
      AbortDoc(dcPrint.m_hAttribDC);
      goto LABEL_112;
    }
LABEL_111:
    EndDoc(dcPrint.m_hAttribDC);
    goto LABEL_112;
  }
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strOutput,
    (const wchar_t *)0xF045);
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v64,
    (const wchar_t *)0xF046);
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strCaption,
    (const wchar_t *)0xF047);
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&hPrinter,
    (const wchar_t *)0xF048);
  CFileDialog::CFileDialog(
    (CFileDialog *)&szBuf[4],
    0,
    strOutput.m_pszData,
    v64.m_pszData,
    6u,
    strCaption.m_pszData,
    0,
    0,
    1);
  *(_QWORD *)(v71 + 88) = hPrinter;
  if ( CFileDialog::DoModal((CFileDialog *)&szBuf[4]) == 1 )
  {
    PathName = (const ATL::CSimpleStringT<wchar_t,0> *)CFileDialog::GetPathName(
                                                         (CFileDialog *)&szBuf[4],
                                                         (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&dcPrint);
    ATL::CSimpleStringT<wchar_t,1>::operator=(&cBytesUsed, PathName);
    v10 = &dcPrint.__vftable[-1].DrawTextExW;
    if ( _InterlockedDecrement((volatile signed __int32 *)&dcPrint.__vftable[-1].Escape) <= 0 )
      (*(void (__fastcall **)(int (__fastcall *)(CDC *, wchar_t *, int, tagRECT *, unsigned int, tagDRAWTEXTPARAMS *)))(*(_QWORD *)*v10 + 8LL))(*v10);
    CFileDialog::~CFileDialog((CFileDialog *)&szBuf[4]);
    v11 = (char *)hPrinter - 24;
    if ( _InterlockedDecrement((volatile signed __int32 *)hPrinter - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
    v12 = strCaption.m_pszData - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)strCaption.m_pszData - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
    v13 = v64.m_pszData - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v64.m_pszData - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
    v14 = strOutput.m_pszData - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)strOutput.m_pszData - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
    v4 = cBytesUsed.m_pszData;
    goto LABEL_29;
  }
  CFileDialog::~CFileDialog((CFileDialog *)&szBuf[4]);
  v5 = (char *)hPrinter - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)hPrinter - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  v6 = strCaption.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)strCaption.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
  v7 = v64.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)v64.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  m_pszData = strOutput.m_pszData;
LABEL_58:
  v29 = (volatile signed __int32 *)(m_pszData - 12);
  if ( _InterlockedDecrement(v29 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
LABEL_118:
  v54 = cBytesUsed.m_pszData - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)cBytesUsed.m_pszData - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v54 + 8LL))(*(_QWORD *)v54);
LABEL_120:
  CPrintInfo::~CPrintInfo((CPrintInfo *)&printInfo.m_bDocObject);
}

```

## disassembly

```asm
0x18028e0d0  mov     rax, rsp
0x18028e0d3  mov     [rax+10h], rbx
0x18028e0d7  mov     [rax+18h], rsi
0x18028e0db  mov     [rax+20h], rdi
0x18028e0df  push    rbp
0x18028e0e0  push    r12
0x18028e0e2  push    r13
0x18028e0e4  push    r14
0x18028e0e6  push    r15
0x18028e0e8  lea     rbp, [rax-738h]
0x18028e0ef  sub     rsp, 810h
0x18028e0f6  mov     rax, cs:__security_cookie
0x18028e0fd  xor     rax, rsp
0x18028e100  mov     [rbp+730h+var_30], rax
0x18028e107  mov     rdi, this
0x18028e10a  lea     this, [rbp+730h+printInfo.m_bDocObject]; this
0x18028e111  call    ??0CPrintInfo@@QEAA@XZ; CPrintInfo::CPrintInfo(void)
0x18028e116  nop
0x18028e117  call    ?GetCurrentMessage@CWnd@@KAPEBUtagMSG@@XZ; CWnd::GetCurrentMessage(void)
0x18028e11c  mov     ecx, 0E108h
0x18028e121  xor     r14d, r14d
0x18028e124  lea     r12d, [r14+1]
0x18028e128  cmp     [rax+10h], cx
0x18028e12c  jnz     short loc_18028E1A0
0x18028e12e  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18028e133  mov     this, [rax+8]
0x18028e137  mov     this, [this+128h]
0x18028e13e  test    this, this
0x18028e141  jz      short loc_18028E199
0x18028e143  cmp     dword ptr [this+18h], 3
0x18028e147  jnz     short loc_18028E199
0x18028e149  xor     r9d, r9d; pdm
0x18028e14c  mov     r8, [this+38h]; pszPort
0x18028e150  mov     rdx, [this+28h]; pwszDevice
0x18028e154  mov     this, [this+30h]; pwszDriver
0x18028e158  call    cs:__imp_CreateDCW
0x18028e15e  mov     this, qword ptr [rbp+730h+printInfo.m_bDocObject]
0x18028e165  mov     rdx, [this+130h]
0x18028e16c  mov     [rdx+20h], rax
0x18028e170  mov     rax, qword ptr [rbp+730h+printInfo.m_bDocObject]
0x18028e177  mov     this, [rax+130h]
0x18028e17e  cmp     [this+20h], r14
0x18028e182  jnz     short loc_18028E199
0x18028e184  or      r8d, 0FFFFFFFFh; nIDHelp
0x18028e188  xor     edx, edx; nType
0x18028e18a  mov     ecx, 0F106h; nIDPrompt
0x18028e18f  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x18028e194  jmp     loc_18028ED03
0x18028e199  mov     [rbp+730h+printInfo.m_nCurPage], r12d
0x18028e1a0  mov     rax, [rdi]
0x18028e1a3  lea     rdx, [rbp+730h+printInfo.m_bDocObject]
0x18028e1aa  mov     this, rdi
0x18028e1ad  mov     rax, [rax+350h]
0x18028e1b4  call    cs:__guard_dispatch_icall_fptr
0x18028e1ba  test    eax, eax
0x18028e1bc  jz      loc_18028ED03
0x18028e1c2  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18028e1c9  lea     r13, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18028e1d0  mov     this, r13
0x18028e1d3  mov     rax, [rax+18h]
0x18028e1d7  call    cs:__guard_dispatch_icall_fptr
0x18028e1dd  lea     rbx, [rax+18h]
0x18028e1e1  mov     [rbp+730h+cBytesUsed], rbx
0x18028e1e5  mov     rax, qword ptr [rbp+730h+printInfo.m_bDocObject]
0x18028e1ec  mov     this, [rax+130h]
0x18028e1f3  or      r15d, 0FFFFFFFFh
0x18028e1f7  test    byte ptr [this+28h], 20h
0x18028e1fb  jz      loc_18028E433
0x18028e201  cmp     [rbp+730h+printInfo.m_bDirect], r14d
0x18028e208  jnz     loc_18028E433
0x18028e20e  mov     edx, 0F045h; pszSrc
0x18028e213  lea     this, [rbp+730h+strOutput]; this
0x18028e217  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18028e21c  nop
0x18028e21d  mov     edx, 0F046h; pszSrc
0x18028e222  lea     this, [rbp+730h+var_788]; this
0x18028e226  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18028e22b  nop
0x18028e22c  mov     edx, 0F047h; pszSrc
0x18028e231  lea     this, [rsp+830h+strCaption]; this
0x18028e236  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18028e23b  nop
0x18028e23c  mov     edx, 0F048h; pszSrc
0x18028e241  lea     this, [rsp+830h+hPrinter]; this
0x18028e246  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18028e24b  nop
0x18028e24c  mov     [rsp+830h+bVistaStyle], r12d; bVistaStyle
0x18028e251  mov     [rsp+830h+dwSize], r14d; dwSize
0x18028e256  mov     [rsp+830h+pParentWnd], r14; pParentWnd
0x18028e25b  mov     rax, [rsp+830h+strCaption.m_pszData]
0x18028e260  mov     [rsp+830h+lpszFilter], rax; lpszFilter
0x18028e265  mov     [rsp+830h+dwFlags], 6; dwFlags
0x18028e26d  mov     r9, [rbp+730h+var_788.m_pszData]; lpszFileName
0x18028e271  mov     r8, [rbp+730h+strOutput.m_pszData]; lpszDefExt
0x18028e275  xor     edx, edx; bOpenFileDialog
0x18028e277  lea     this, [rbp+730h+szBuf+8]; this
0x18028e27e  call    ??0CFileDialog@@QEAA@HPEB_W0K0PEAVCWnd@@KH@Z; CFileDialog::CFileDialog(int,wchar_t const *,wchar_t const *,ulong,wchar_t const *,CWnd *,ulong,int)
0x18028e283  nop
0x18028e284  mov     this, [rsp+830h+hPrinter]
0x18028e289  mov     rax, [rbp+730h+var_490]
0x18028e290  mov     [rax+58h], this
0x18028e294  lea     this, [rbp+730h+szBuf+8]; this
0x18028e29b  call    ?DoModal@CFileDialog@@UEAA_JXZ; CFileDialog::DoModal(void)
0x18028e2a0  cmp     rax, r12
0x18028e2a3  jz      loc_18028E339
0x18028e2a9  lea     this, [rbp+730h+szBuf+8]; this
0x18028e2b0  call    ??1CFileDialog@@UEAA@XZ; CFileDialog::~CFileDialog(void)
0x18028e2b5  nop
0x18028e2b6  mov     rdx, [rsp+830h+hPrinter]
0x18028e2bb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e2bf  mov     eax, r15d
0x18028e2c2  lock xadd [rdx+10h], eax
0x18028e2c7  add     eax, r15d
0x18028e2ca  test    eax, eax
0x18028e2cc  jg      short loc_18028E2DF
0x18028e2ce  mov     this, [rdx]
0x18028e2d1  mov     rax, [this]
0x18028e2d4  mov     rax, [rax+8]
0x18028e2d8  call    cs:__guard_dispatch_icall_fptr
0x18028e2de  nop
0x18028e2df  mov     rdx, [rsp+830h+strCaption.m_pszData]
0x18028e2e4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e2e8  mov     eax, r15d
0x18028e2eb  lock xadd [rdx+10h], eax
0x18028e2f0  add     eax, r15d
0x18028e2f3  test    eax, eax
0x18028e2f5  jg      short loc_18028E308
0x18028e2f7  mov     this, [rdx]
0x18028e2fa  mov     rax, [this]
0x18028e2fd  mov     rax, [rax+8]
0x18028e301  call    cs:__guard_dispatch_icall_fptr
0x18028e307  nop
0x18028e308  mov     rdx, [rbp+730h+var_788.m_pszData]
0x18028e30c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e310  mov     eax, r15d
0x18028e313  lock xadd [rdx+10h], eax
0x18028e318  add     eax, r15d
0x18028e31b  test    eax, eax
0x18028e31d  jg      short loc_18028E330
0x18028e31f  mov     this, [rdx]
0x18028e322  mov     rax, [this]
0x18028e325  mov     rax, [rax+8]
0x18028e329  call    cs:__guard_dispatch_icall_fptr
0x18028e32f  nop
0x18028e330  mov     rdx, [rbp+730h+strOutput.m_pszData]
0x18028e334  jmp     loc_18028E7EA
0x18028e339  lea     rdx, [rsp+830h+dcPrint]; result
0x18028e33e  lea     this, [rbp+730h+szBuf+8]; this
0x18028e345  call    ?GetPathName@CFileDialog@@QEBA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@XZ; CFileDialog::GetPathName(void)
0x18028e34a  nop
0x18028e34b  mov     rdx, rax; strSrc
0x18028e34e  lea     this, [rbp+730h+cBytesUsed]; this
0x18028e352  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x18028e357  nop
0x18028e358  mov     rdx, [rsp+830h+dcPrint.__vftable]
0x18028e35d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e361  mov     eax, r15d
0x18028e364  lock xadd [rdx+10h], eax
0x18028e369  add     eax, r15d
0x18028e36c  test    eax, eax
0x18028e36e  jg      short loc_18028E381
0x18028e370  mov     this, [rdx]
0x18028e373  mov     rax, [this]
0x18028e376  mov     rax, [rax+8]
0x18028e37a  call    cs:__guard_dispatch_icall_fptr
0x18028e380  nop
0x18028e381  lea     this, [rbp+730h+szBuf+8]; this
0x18028e388  call    ??1CFileDialog@@UEAA@XZ; CFileDialog::~CFileDialog(void)
0x18028e38d  nop
0x18028e38e  mov     rdx, [rsp+830h+hPrinter]
0x18028e393  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e397  mov     eax, r15d
0x18028e39a  lock xadd [rdx+10h], eax
0x18028e39f  add     eax, r15d
0x18028e3a2  test    eax, eax
0x18028e3a4  jg      short loc_18028E3B7
0x18028e3a6  mov     this, [rdx]
0x18028e3a9  mov     rax, [this]
0x18028e3ac  mov     rax, [rax+8]
0x18028e3b0  call    cs:__guard_dispatch_icall_fptr
0x18028e3b6  nop
0x18028e3b7  mov     rdx, [rsp+830h+strCaption.m_pszData]
0x18028e3bc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e3c0  mov     eax, r15d
0x18028e3c3  lock xadd [rdx+10h], eax
0x18028e3c8  add     eax, r15d
0x18028e3cb  test    eax, eax
0x18028e3cd  jg      short loc_18028E3E0
0x18028e3cf  mov     this, [rdx]
0x18028e3d2  mov     rax, [this]
0x18028e3d5  mov     rax, [rax+8]
0x18028e3d9  call    cs:__guard_dispatch_icall_fptr
0x18028e3df  nop
0x18028e3e0  mov     rdx, [rbp+730h+var_788.m_pszData]
0x18028e3e4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e3e8  mov     eax, r15d
0x18028e3eb  lock xadd [rdx+10h], eax
0x18028e3f0  add     eax, r15d
0x18028e3f3  test    eax, eax
0x18028e3f5  jg      short loc_18028E408
0x18028e3f7  mov     this, [rdx]
0x18028e3fa  mov     rax, [this]
0x18028e3fd  mov     rax, [rax+8]
0x18028e401  call    cs:__guard_dispatch_icall_fptr
0x18028e407  nop
0x18028e408  mov     rdx, [rbp+730h+strOutput.m_pszData]
0x18028e40c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e410  mov     eax, r15d
0x18028e413  lock xadd [rdx+10h], eax
0x18028e418  add     eax, r15d
0x18028e41b  test    eax, eax
0x18028e41d  jg      short loc_18028E42F
0x18028e41f  mov     this, [rdx]
0x18028e422  mov     rax, [this]
0x18028e425  mov     rax, [rax+8]
0x18028e429  call    cs:__guard_dispatch_icall_fptr
0x18028e42f  mov     rbx, [rbp+730h+cBytesUsed]
0x18028e433  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18028e43a  mov     this, r13
0x18028e43d  mov     rax, [rax+18h]
0x18028e441  call    cs:__guard_dispatch_icall_fptr
0x18028e447  add     rax, 18h
0x18028e44b  mov     [rbp+730h+cBytesNeeded], rax
0x18028e44f  mov     rdx, [rdi+0E8h]
0x18028e456  test    rdx, rdx
0x18028e459  jz      short loc_18028E46A
0x18028e45b  add     rdx, 40h ; '@'; strSrc
0x18028e45f  lea     this, [rbp+730h+cBytesNeeded]; this
0x18028e463  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x18028e468  jmp     short loc_18028E487
0x18028e46a  mov     this, rdi; this
0x18028e46d  call    ?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetParentFrame(void)
0x18028e472  test    rax, rax
0x18028e475  jz      loc_18028ED55
0x18028e47b  lea     rdx, [rbp+730h+cBytesNeeded]; rString
0x18028e47f  mov     this, rax; this
0x18028e482  call    ?GetWindowTextW@CWnd@@QEBAXAEAV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z; CWnd::GetWindowTextW(ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18028e487  mov     esi, 28h ; '('
0x18028e48c  mov     r8d, esi; Size
0x18028e48f  xor     edx, edx; Val
0x18028e491  lea     this, [rbp+730h+docInfo.lpszDocName]; void *
0x18028e495  call    cs:__imp_memset
0x18028e49b  mov     dword ptr [rbp+730h+docInfo.lpszDocName], esi
0x18028e49e  mov     rax, [rbp+730h+cBytesNeeded]
0x18028e4a2  mov     [rbp+730h+docInfo.lpszOutput], rax
0x18028e4a6  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18028e4ad  mov     this, r13
0x18028e4b0  mov     rax, [rax+18h]
0x18028e4b4  call    cs:__guard_dispatch_icall_fptr
0x18028e4ba  lea     rdx, [rax+18h]
0x18028e4be  mov     [rsp+830h+hPrinter], rdx
0x18028e4c3  cmp     [rbx-10h], r14d
0x18028e4c7  jnz     short loc_18028E517
0x18028e4c9  mov     [rbp+730h+docInfo.lpszDatatype], r14
0x18028e4cd  lea     rdx, [rsp+830h+dcPrint]; result
0x18028e4d2  mov     this, qword ptr [rbp+730h+printInfo.m_bDocObject]; this
0x18028e4d9  call    ?GetPortName@CPrintDialog@@QEBA?AV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@XZ; CPrintDialog::GetPortName(void)
0x18028e4de  nop
0x18028e4df  mov     rdx, rax; strSrc
0x18028e4e2  lea     this, [rsp+830h+hPrinter]; this
0x18028e4e7  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x18028e4ec  nop
0x18028e4ed  mov     rdx, [rsp+830h+dcPrint.__vftable]
0x18028e4f2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18028e4f6  mov     eax, r15d
0x18028e4f9  lock xadd [rdx+10h], eax
0x18028e4fe  add     eax, r15d
0x18028e501  test    eax, eax
0x18028e503  jg      short loc_18028E54B
0x18028e505  mov     this, [rdx]
0x18028e508  mov     rax, [this]
0x18028e50b  mov     rax, [rax+8]
0x18028e50f  call    cs:__guard_dispatch_icall_fptr
0x18028e515  jmp     short loc_18028E54B
0x18028e517  mov     [rbp+730h+docInfo.lpszDatatype], rbx
0x18028e51b  mov     ecx, r12d
0x18028e51e  sub     ecx, [rdx-8]
0x18028e521  mov     eax, [rdx-0Ch]
0x18028e524  mov     esi, 104h
0x18028e529  sub     eax, esi
0x18028e52b  or      eax, ecx
0x18028e52d  jge     short loc_18028E540
0x18028e52f  mov     edx, esi; nLength
0x18028e531  lea     this, [rsp+830h+hPrinter]; this
0x18028e536  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x18028e53b  mov     rdx, [rsp+830h+hPrinter]; lpszTitle
0x18028e540  mov     r8d, esi; nMax
0x18028e543  mov     this, rbx; lpszPathName
0x18028e546  call    ?AfxGetFileTitle@@YAIPEB_WPEA_WI@Z; AfxGetFileTitle(wchar_t const *,wchar_t *,uint)
0x18028e54b  lea     r13, ??_7CDC@@6B@; const CDC::`vftable'
0x18028e552  mov     [rsp+830h+dcPrint.m_hDC], r13
0x18028e557  xorps   xmm0, xmm0
0x18028e55a  movdqu  xmmword ptr [rsp+830h+dcPrint.m_hAttribDC], xmm0
0x18028e560  mov     dword ptr [rbp+730h+strTitle.m_pszData], r14d
0x18028e564  cmp     [rbp+730h+printInfo.m_bDirect], r14d
0x18028e56b  jnz     short loc_18028E58D
0x18028e56d  mov     rax, qword ptr [rbp+730h+printInfo.m_bDocObject]
0x18028e574  mov     rdx, [rax+130h]
0x18028e57b  mov     rdx, [rdx+20h]; hDC
0x18028e57f  lea     this, [rsp+830h+dcPrint.m_hDC]; this
  ... truncated ...
```
