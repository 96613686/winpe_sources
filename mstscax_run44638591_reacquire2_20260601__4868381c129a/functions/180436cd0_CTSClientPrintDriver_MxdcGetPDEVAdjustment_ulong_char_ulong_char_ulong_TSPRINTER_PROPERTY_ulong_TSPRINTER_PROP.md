# CTSClientPrintDriver::MxdcGetPDEVAdjustment(ulong,char *,ulong,char *,ulong,_TSPRINTER_PROPERTY *,ulong *,_TSPRINTER_PROPERTY * *)

- ea: `0x180436cd0`
- end: `0x18043777f`
- name: `?MxdcGetPDEVAdjustment@CTSClientPrintDriver@@UEAAJKPEADK0KPEAU_TSPRINTER_PROPERTY@@PEAKPEAPEAU2@@Z`
- size: `2735`
- prototype: `int(CTSClientPrintDriver *__hidden this, unsigned int, char *, unsigned int, char *, unsigned int, struct _TSPRINTER_PROPERTY *, unsigned int *, struct _TSPRINTER_PROPERTY **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001e0d8`
- `0x180039ce4`
- `0x180085e50`
- `0x1800e9b1c`
- `0x1800f7748`
- `0x18019e98c`
- `0x1804331b0`
- `0x1804356ac`
- `0x18043594c`
- `0x180436cd0`
- `0x180437b84`
- `0x180439648`
- `0x1804399f4`
- `0x18043a31c`
- `0x18043a758`
- `0x180688f86`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804371da`
- `KERNEL32!GetLastError` at `0x1804371da`
- `GDI32!GetDeviceCaps` at `0x180436fb4`
- `GDI32!GetDeviceCaps` at `0x180436fd1`
- `GDI32!GetDeviceCaps` at `0x180437055`
- `GDI32!GetDeviceCaps` at `0x18043707b`
- `GDI32!GetDeviceCaps` at `0x1804370a0`
- `GDI32!GetDeviceCaps` at `0x1804370d3`
- `GDI32!GetDeviceCaps` at `0x18043712c`
- `GDI32!GetDeviceCaps` at `0x180437150`
- `GDI32!GetDeviceCaps` at `0x180436fb4`
- `GDI32!GetDeviceCaps` at `0x180436fd1`
- `GDI32!GetDeviceCaps` at `0x180437055`
- `GDI32!GetDeviceCaps` at `0x18043707b`
- `GDI32!GetDeviceCaps` at `0x1804370a0`
- `GDI32!GetDeviceCaps` at `0x1804370d3`
- `GDI32!GetDeviceCaps` at `0x18043712c`
- `GDI32!GetDeviceCaps` at `0x180437150`
- `GDI32!DeleteDC` at `0x180436ffd`
- `GDI32!DeleteDC` at `0x1804371cf`
- `GDI32!DeleteDC` at `0x180436ffd`
- `GDI32!DeleteDC` at `0x1804371cf`
- `GDI32!CreateDCW` at `0x180436f9b`
- `GDI32!CreateDCW` at `0x180436f9b`
- `OLEAUT32!__imp_SysAllocString` at `0x18043730b`
- `OLEAUT32!__imp_SysAllocString` at `0x18043748c`
- `OLEAUT32!__imp_SysAllocString` at `0x18043730b`
- `OLEAUT32!__imp_SysAllocString` at `0x18043748c`
- `OLEAUT32!__imp_VariantInit` at `0x1804374b2`
- `OLEAUT32!__imp_VariantInit` at `0x1804374b2`
- `OLEAUT32!__imp_VariantClear` at `0x1804374fa`
- `OLEAUT32!__imp_VariantClear` at `0x1804374fa`
- `OLE32!CoTaskMemFree` at `0x180437752`
- `OLE32!CoTaskMemFree` at `0x180437752`

## string_xrefs

- `0x180437225`: `CreateDC`
- `0x18043727c`: `CTSClientPrintTicket::CreateInstance`
- `0x180437485`: `xmlns:psf='http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework'`

## pseudocode

```c
__int64 __fastcall CTSClientPrintDriver::MxdcGetPDEVAdjustment(
        CTSClientPrintDriver *this,
        unsigned int a2,
        DEVMODEW *a3,
        unsigned int a4,
        char *a5,
        unsigned int a6,
        struct _TSPRINTER_PROPERTY *a7,
        unsigned int *a8,
        struct _TSPRINTER_PROPERTY **a9)
{
  signed int PrintCapabilities; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct ITSVC_PrintTicketProvider *v15; // rcx
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  __int64 (__fastcall *v19)(_QWORD, _QWORD, DEVMODEW *, _QWORD, char *, unsigned int, LPVOID); // rax
  struct PrintPropertiesCollection *v20; // rdx
  unsigned int v21; // edi
  unsigned int v22; // esi
  __int64 v23; // rdx
  unsigned int *v24; // r8
  __int64 v25; // rbx
  int v26; // eax
  int v27; // eax
  CTSClientPrintDriver *v28; // rsi
  struct tagRECT *v29; // rbx
  HDC DCW; // rax
  HDC v31; // rdi
  double v32; // xmm7_8
  int DeviceCaps; // eax
  double v34; // xmm6_8
  unsigned int v35; // eax
  int v36; // eax
  DEVMODEW *v37; // rcx
  int v38; // esi
  unsigned int v39; // eax
  LONG v40; // eax
  LONG v41; // ecx
  LONG v42; // r8d
  signed int LastError; // eax
  int v44; // r8d
  struct IPrinterCollection *v45; // rdx
  CTSClientPrintTicket *v46; // rbx
  unsigned int v47; // eax
  __int64 v48; // rax
  struct ITSVC_PrintTicketProvider *v49; // rsi
  struct ITSVC_PrintTicketProvider *v50; // rdi
  BSTR v51; // rax
  unsigned int v52; // eax
  unsigned int v53; // eax
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  struct IXMLDOMDocument2 *v55; // r14
  unsigned int v56; // eax
  struct IXMLDOMDocument2Vtbl *v57; // rax
  BSTR v58; // rbx
  struct IXMLDOMDocument2 *v59; // rbx
  struct IXMLDOMDocument2Vtbl *v60; // rax
  unsigned int v61; // eax
  int v62; // edx
  const char *v63; // rcx
  int v64; // edi
  unsigned int v65; // eax
  struct tagRECT *v66; // r9
  LONG v67; // eax
  LONG top; // ecx
  LONG bottom; // r8d
  struct ITSVC_PrintTicketProvider *v71; // [rsp+48h] [rbp-89h] BYREF
  unsigned int v72[2]; // [rsp+50h] [rbp-81h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-79h] BYREF
  struct IXMLDOMDocument2 *v74; // [rsp+60h] [rbp-71h] BYREF
  struct ITSVC_PrintTicketProvider *v75; // [rsp+68h] [rbp-69h] BYREF
  struct IXMLDOMDocument2 *v76; // [rsp+70h] [rbp-61h] BYREF
  struct tagRECT *v77; // [rsp+78h] [rbp-59h]
  VARIANTARG pvarg; // [rsp+80h] [rbp-51h] BYREF
  VARIANTARG v79; // [rsp+98h] [rbp-39h] BYREF
  CTSClientPrintDriver *v80; // [rsp+118h] [rbp+47h] BYREF
  unsigned int v81; // [rsp+120h] [rbp+4Fh]
  DEVMODEW *pdm; // [rsp+128h] [rbp+57h]

  pdm = a3;
  v81 = a2;
  v80 = this;
  pv = 0;
  v72[0] = 0;
  *a8 = 0;
  *a9 = 0;
  PrintCapabilities = CTSClientPrintDriver::VerifyDevMode(this, (char *)a3, a2);
  if ( PrintCapabilities < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        100,
        (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"VerifyDevMode(pDevmodeIn, cbDevmodeIn)",
        PrintCapabilities);
    }
    return (unsigned int)PrintCapabilities;
  }
  PrintCapabilities = UnMarshalPrinterPropertiesCollection(a6, a7, v72, (struct PrintPropertiesCollection **)&pv);
  if ( PrintCapabilities < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_137;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 101;
    v18 = "UnMarshalPrinterPropertiesCollection";
    goto LABEL_136;
  }
  v19 = (__int64 (__fastcall *)(_QWORD, _QWORD, DEVMODEW *, _QWORD, char *, unsigned int, LPVOID))*((_QWORD *)this + 20);
  if ( v19 )
  {
    PrintCapabilities = v19(*((_QWORD *)this + 12), a2, a3, a4, a5, v72[0], pv);
    if ( PrintCapabilities < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_137;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 102;
      v18 = "_pfnMxdcGetPDEVAdjustment";
      goto LABEL_136;
    }
  }
  v20 = (struct PrintPropertiesCollection *)pv;
  if ( !*(_DWORD *)pv )
    goto LABEL_131;
  v71 = 0;
  v21 = 0;
  v22 = 0;
  v23 = *((_QWORD *)pv + 1);
  v24 = (unsigned int *)pv;
  *(_QWORD *)v72 = v23;
  do
  {
    v25 = v23 + 32LL * v22;
    if ( *(_DWORD *)(v25 + 8) == 10 )
    {
      v26 = wcscmp_0(L"MxdcImageableArea", *(const wchar_t **)v25);
      v24 = (unsigned int *)pv;
      v23 = *(_QWORD *)v72;
      if ( !v26 && *(_DWORD *)(v25 + 16) >= 0x10u )
      {
        v15 = (struct ITSVC_PrintTicketProvider *)v25;
        v71 = (struct ITSVC_PrintTicketProvider *)v25;
        goto LABEL_29;
      }
LABEL_28:
      v15 = v71;
      goto LABEL_29;
    }
    if ( *(_DWORD *)(v25 + 8) != 2 )
      goto LABEL_28;
    v27 = wcscmp_0(L"MxdcLandscapeRotation", *(const wchar_t **)v25);
    v15 = v71;
    v24 = (unsigned int *)pv;
    v23 = *(_QWORD *)v72;
    if ( !v27 && !*(_DWORD *)(v25 + 16) )
      v21 = 1;
LABEL_29:
    ++v22;
  }
  while ( v22 < *v24 );
  v28 = v80;
  v72[0] = v21;
  if ( !v15 )
  {
LABEL_130:
    v20 = (struct PrintPropertiesCollection *)pv;
LABEL_131:
    PrintCapabilities = MarshalPrinterPropertiesCollection((unsigned int)v15, v20, a8, a9);
    if ( PrintCapabilities >= 0
      || WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_137;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 114;
    v18 = "MarshalPrinterPropertiesCollection";
    goto LABEL_136;
  }
  v29 = (struct tagRECT *)*((_QWORD *)v15 + 3);
  v77 = v29;
  if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() || *((_DWORD *)v28 + 50) )
  {
    v44 = *((_DWORD *)v28 + 50);
    v45 = (struct IPrinterCollection *)*((_QWORD *)v28 + 8);
    v46 = 0;
    v71 = 0;
    v75 = 0;
    v76 = 0;
    v74 = 0;
    PrintCapabilities = CTSClientPrintTicket::CreateInstance(&v75, v45, v44);
    if ( PrintCapabilities < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v47 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
          v47,
          (__int64)"CTSClientPrintTicket::CreateInstance",
          PrintCapabilities);
      }
      if ( !v75 )
        goto LABEL_64;
      v48 = *(_QWORD *)v75;
      goto LABEL_63;
    }
    v49 = v75;
    v50 = 0;
    if ( v75 )
    {
      TCntPtr<CTSClientPrintTicket>::SafeRelease(&v71);
      v46 = v49;
      v71 = v49;
      TCntPtr<CPlayer>::SafeAddRef(&v71);
      v50 = v49;
    }
    if ( *((_QWORD *)v50 + 13) )
    {
      PrintCapabilities = -2147418113;
LABEL_71:
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v52 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
          v52,
          (__int64)"SetPrinterName",
          PrintCapabilities);
      }
      goto LABEL_75;
    }
    v51 = SysAllocString(*((const OLECHAR **)v80 + 11));
    *((_QWORD *)v50 + 13) = v51;
    if ( !v51 )
    {
      PrintCapabilities = -2147024882;
      goto LABEL_71;
    }
    PrintCapabilities = CTSClientPrintTicket::NoPT_ConvertDevModeToPrintTicket(v46, (unsigned __int8 *)pdm, v81, &v76);
    if ( PrintCapabilities < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v53 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          108,
          (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
          v53,
          (__int64)"ConvertDevModeToPrintTicket",
          PrintCapabilities);
      }
      if ( !v76 )
        goto LABEL_75;
      lpVtbl = v76->lpVtbl;
      goto LABEL_84;
    }
    v55 = v76;
    PrintCapabilities = CTSClientPrintTicket::NoPT_GetPrintCapabilities(v46, v76, &v74);
    if ( PrintCapabilities < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v56 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
          v56,
          (__int64)"NoPT_GetPrintCapabilities",
          PrintCapabilities);
      }
      goto LABEL_90;
    }
    v58 = SysAllocString(L"xmlns:psf='http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework'");
    if ( !v58 )
    {
      PrintCapabilities = -2147024882;
LABEL_90:
      if ( !v74 )
      {
LABEL_93:
        if ( !v55 )
          goto LABEL_75;
        lpVtbl = v55->lpVtbl;
LABEL_84:
        ((void (*)(void))lpVtbl->Release)();
LABEL_75:
        if ( !v49 )
          goto LABEL_64;
        v48 = *(_QWORD *)v49;
LABEL_63:
        (*(void (**)(void))(v48 + 16))();
LABEL_64:
        TCntPtr<CTSClientPrintTicket>::SafeRelease(&v71);
        goto LABEL_137;
      }
      v57 = v74->lpVtbl;
LABEL_92:
      ((void (*)(void))v57->Release)();
      goto LABEL_93;
    }
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.llVal = (LONGLONG)v58;
    v59 = v74;
    pvarg.vt = 8;
    v60 = v74->lpVtbl;
    v79 = pvarg;
    PrintCapabilities = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, VARIANTARG *))v60->setProperty)(
                          v74,
                          L"SelectionNamespaces",
                          &v79);
    VariantClear(&pvarg);
    if ( PrintCapabilities < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      v61 = RdpWppGetCurrentThreadActivityIdPrefix();
      v62 = 110;
      v63 = "setProperty";
LABEL_102:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v62,
        (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
        v61,
        (__int64)v63,
        PrintCapabilities);
LABEL_103:
      if ( !v59 )
        goto LABEL_93;
      v57 = v59->lpVtbl;
      goto LABEL_92;
    }
    PrintCapabilities = GetImgArea(v59, v77);
    if ( PrintCapabilities < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_103;
      }
      v61 = RdpWppGetCurrentThreadActivityIdPrefix();
      v62 = 111;
      v63 = "GetImgArea";
      goto LABEL_102;
    }
    if ( (pdm->dmFields & 1) != 0 && pdm->dmOrientation == 2 && !v72[0] )
    {
      LODWORD(v80) = 0;
      v72[0] = 0;
      PrintCapabilities = GetPageImageableSize(v59, (int *)&v80, (int *)v72);
      if ( PrintCapabilities < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_103;
        }
        v61 = RdpWppGetCurrentThreadActivityIdPrefix();
        v62 = 112;
        v63 = "GetPageImageableSize";
        goto LABEL_102;
      }
      v64 = (int)v80;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v65 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          113,
          WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
          v65,
          v64,
          v72[0]);
      }
      v66 = v77;
      v67 = v64 - v77->right;
      top = v77->top;
      bottom = v77->bottom;
      v77->bottom = v64 - v77->left;
      v66->top = v67;
      v66->left = top;
      v66->right = bottom;
    }
    if ( v59 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v59->lpVtbl->Release)(v59);
    if ( v55 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v55->lpVtbl->Release)(v55);
    if ( v49 )
      (*(void (__fastcall **)(struct ITSVC_PrintTicketProvider *))(*(_QWORD *)v49 + 16LL))(v49);
    TCntPtr<CTSClientPrintTicket>::SafeRelease(&v71);
    goto LABEL_130;
  }
  DCW = CreateDCW(0, *((LPCWSTR *)v28 + 11), 0, pdm);
  v31 = DCW;
  if ( !DCW )
  {
    LastError = GetLastError();
    PrintCapabilities = LastError;
    if ( LastError > 0 )
      PrintCapabilities = (unsigned __int16)LastError | 0x80070000;
    if ( PrintCapabilities < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_137;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 105;
      v18 = "CreateDC";
LABEL_136:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
        v16,
        (__int64)v18,
        PrintCapabilities);
      goto LABEL_137;
    }
    goto LABEL_130;
  }
  v32 = (double)GetDeviceCaps(DCW, 88) / 2.54;
  DeviceCaps = GetDeviceCaps(v31, 90);
  if ( v32 != 0.0 )
  {
    v34 = (double)DeviceCaps / 2.54;
    if ( v34 != 0.0 )
    {
      v29->left = (int)((double)(10000 * GetDeviceCaps(v31, 112)) / v32);
      v29->top = (int)((double)(10000 * GetDeviceCaps(v31, 113)) / v34);
      v29->right = (int)((double)v29->left + (double)(10000 * GetDeviceCaps(v31, 8)) / v32);
      v36 = GetDeviceCaps(v31, 10);
      v37 = pdm;
      v29->bottom = (int)((double)v29->top + (double)(10000 * v36) / v34);
      if ( (v37->dmFields & 1) != 0 && v37->dmOrientation == 2 && !v72[0] )
      {
        v38 = (int)((double)(10000 * GetDeviceCaps(v31, 110)) / v32);
        LODWORD(v80) = GetDeviceCaps(v31, 111);
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v39 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DLD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            103,
            WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
            v39,
            v38,
            (int)((double)(10000 * (int)v80) / v34));
        }
        v40 = v38 - v29->right;
        v41 = v29->top;
        v42 = v29->bottom;
        v29->bottom = v38 - v29->left;
        v29->top = v40;
        v29->left = v41;
        v29->right = v42;
      }
      DeleteDC(v31);
      goto LABEL_130;
    }
  }
  DeleteDC(v31);
  PrintCapabilities = -2147418113;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v35 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      104,
      (unsigned int)WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids,
      v35,
      (__int64)"GetDeviceCaps",
      255);
  }
LABEL_137:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)PrintCapabilities;
}

```

## disassembly

```asm
0x180436cd0  mov     rax, rsp
0x180436cd3  mov     [rax+20h], rbx
0x180436cd7  mov     [rax+18h], r8
0x180436cdb  mov     [rax+10h], edx
0x180436cde  mov     [rax+8], rcx
0x180436ce2  push    rbp
0x180436ce3  push    rsi
0x180436ce4  push    rdi
0x180436ce5  push    r12
0x180436ce7  push    r13
0x180436ce9  push    r14
0x180436ceb  push    r15
0x180436ced  lea     rbp, [rax-3Fh]
0x180436cf1  sub     rsp, 0D0h
0x180436cf8  movaps  xmmword ptr [rax-48h], xmm6
0x180436cfc  xor     r12d, r12d
0x180436cff  movaps  xmmword ptr [rax-58h], xmm7
0x180436d03  mov     rbx, r8
0x180436d06  mov     rax, [rbp+37h+arg_38]
0x180436d0a  mov     r14d, edx
0x180436d0d  mov     r8d, edx; unsigned int
0x180436d10  mov     [rbp+37h+pv], r12
0x180436d14  mov     rdx, rbx; char *
0x180436d17  mov     [rsp+100h+var_B8], r12d
0x180436d1c  mov     r15d, r9d
0x180436d1f  mov     rsi, rcx
0x180436d22  mov     [rax], r12d
0x180436d25  mov     rax, [rbp+37h+arg_40]
0x180436d2c  mov     [rax], r12
0x180436d2f  call    ?VerifyDevMode@CTSClientPrintDriver@@IEAAJPEADK@Z; CTSClientPrintDriver::VerifyDevMode(char *,ulong)
0x180436d34  mov     edi, eax
0x180436d36  test    eax, eax
0x180436d38  jns     short loc_180436DA7
0x180436d3a  mov     rax, cs:WPP_GLOBAL_Control
0x180436d41  lea     r12, WPP_GLOBAL_Control
0x180436d48  cmp     rax, r12
0x180436d4b  jz      loc_180437758
0x180436d51  mov     r13d, 8
0x180436d57  test    [rax+1Ch], r13b
0x180436d5b  jz      loc_180437758
0x180436d61  lea     r15d, [r13-6]
0x180436d65  cmp     [rax+19h], r15b
0x180436d69  jb      loc_180437758
0x180436d6f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180436d74  lea     rcx, aVerifydevmodeP; "VerifyDevMode(pDevmodeIn, cbDevmodeIn)"
0x180436d7b  mov     dword ptr [rsp+100h+var_D8], edi
0x180436d7f  mov     qword ptr [rsp+100h+var_E0], rcx
0x180436d84  lea     edx, [r13+5Ch]
0x180436d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180436d8f  lea     r8, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180436d96  mov     r9d, eax
0x180436d99  mov     rcx, [rcx+10h]
0x180436d9d  call    WPP_SF_DsD
0x180436da2  jmp     loc_180437758
0x180436da7  mov     rdx, [rbp+37h+arg_30]; struct _TSPRINTER_PROPERTY *
0x180436dab  lea     r9, [rbp+37h+pv]; struct PrintPropertiesCollection **
0x180436daf  mov     ecx, [rbp+37h+arg_28]; unsigned int
0x180436db2  lea     r8, [rsp+100h+var_B8]; unsigned int *
0x180436db7  call    ?UnMarshalPrinterPropertiesCollection@@YAJKPEAU_TSPRINTER_PROPERTY@@PEAKPEAPEAUPrintPropertiesCollection@@@Z; UnMarshalPrinterPropertiesCollection(ulong,_TSPRINTER_PROPERTY *,ulong *,PrintPropertiesCollection * *)
0x180436dbc  mov     edi, eax
0x180436dbe  test    eax, eax
0x180436dc0  jns     short loc_180436E13
0x180436dc2  mov     rax, cs:WPP_GLOBAL_Control
0x180436dc9  lea     r12, WPP_GLOBAL_Control
0x180436dd0  cmp     rax, r12
0x180436dd3  jz      loc_180437746
0x180436dd9  mov     r13d, 8
0x180436ddf  test    [rax+1Ch], r13b
0x180436de3  jz      loc_180437746
0x180436de9  lea     r15d, [r13-6]
0x180436ded  cmp     [rax+19h], r15b
0x180436df1  jb      loc_180437746
0x180436df7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180436dfc  lea     edx, [r13+5Dh]
0x180436e00  lea     rcx, aUnmarshalprint; "UnMarshalPrinterPropertiesCollection"
0x180436e07  lea     r8, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180436e0e  jmp     loc_18043772A
0x180436e13  mov     rax, [rsi+0A0h]
0x180436e1a  test    rax, rax
0x180436e1d  jz      short loc_180436E9B
0x180436e1f  mov     rcx, [rbp+37h+pv]
0x180436e23  mov     r9d, r15d
0x180436e26  mov     [rsp+100h+var_D0], rcx
0x180436e2b  mov     r8, rbx
0x180436e2e  mov     ecx, [rsp+100h+var_B8]
0x180436e32  mov     edx, r14d
0x180436e35  mov     dword ptr [rsp+100h+var_D8], ecx
0x180436e39  mov     rcx, [rbp+37h+arg_20]
0x180436e3d  mov     qword ptr [rsp+100h+var_E0], rcx
0x180436e42  mov     rcx, [rsi+60h]
0x180436e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180436e4b  mov     edi, eax
0x180436e4d  test    eax, eax
0x180436e4f  jns     short loc_180436E9B
0x180436e51  mov     rax, cs:WPP_GLOBAL_Control
0x180436e58  lea     r12, WPP_GLOBAL_Control
0x180436e5f  cmp     rax, r12
0x180436e62  jz      loc_180437746
0x180436e68  mov     r13d, 8
0x180436e6e  test    [rax+1Ch], r13b
0x180436e72  jz      loc_180437746
0x180436e78  lea     r15d, [r13-6]
0x180436e7c  cmp     [rax+19h], r15b
0x180436e80  jb      loc_180437746
0x180436e86  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180436e8b  lea     edx, [r13+5Eh]
0x180436e8f  lea     rcx, aPfnmxdcgetpdev; "_pfnMxdcGetPDEVAdjustment"
0x180436e96  jmp     loc_180436E07
0x180436e9b  mov     rdx, [rbp+37h+pv]
0x180436e9f  lea     r12, WPP_GLOBAL_Control
0x180436ea6  mov     r13d, 8
0x180436eac  lea     r14, WPP_3d18931231a1393eec0ea8a725aabe5e_Traceguids
0x180436eb3  cmp     dword ptr [rdx], 0
0x180436eb6  lea     r15d, [r13-6]
0x180436eba  jbe     loc_1804376E8
0x180436ec0  xor     ecx, ecx
0x180436ec2  lea     r13d, [r15-1]
0x180436ec6  mov     [rsp+100h+var_C0], rcx
0x180436ecb  xor     edi, edi
0x180436ecd  mov     rcx, rdx
0x180436ed0  xor     esi, esi
0x180436ed2  mov     rdx, [rdx+8]
0x180436ed6  mov     r8, rcx
0x180436ed9  mov     qword ptr [rsp+100h+var_B8], rdx
0x180436ede  mov     ebx, esi
0x180436ee0  shl     rbx, 5
0x180436ee4  add     rbx, rdx
0x180436ee7  cmp     dword ptr [rbx+8], 0Ah
0x180436eeb  jnz     short loc_180436F19
0x180436eed  mov     rdx, [rbx]; String2
0x180436ef0  lea     rcx, aMxdcimageablea; "MxdcImageableArea"
0x180436ef7  call    wcscmp_0
0x180436efc  mov     r8, [rbp+37h+pv]
0x180436f00  mov     rdx, qword ptr [rsp+100h+var_B8]
0x180436f05  test    eax, eax
0x180436f07  jnz     short loc_180436F49
0x180436f09  cmp     dword ptr [rbx+10h], 10h
0x180436f0d  jb      short loc_180436F49
0x180436f0f  mov     rcx, rbx
0x180436f12  mov     [rsp+100h+var_C0], rbx
0x180436f17  jmp     short loc_180436F4E
0x180436f19  cmp     [rbx+8], r15d
0x180436f1d  jnz     short loc_180436F49
0x180436f1f  mov     rdx, [rbx]; String2
0x180436f22  lea     rcx, aMxdclandscaper; "MxdcLandscapeRotation"
0x180436f29  call    wcscmp_0
0x180436f2e  mov     rcx, [rsp+100h+var_C0]
0x180436f33  mov     r8, [rbp+37h+pv]
0x180436f37  mov     rdx, qword ptr [rsp+100h+var_B8]
0x180436f3c  test    eax, eax
0x180436f3e  jnz     short loc_180436F4E
0x180436f40  cmp     [rbx+10h], eax
0x180436f43  cmovz   edi, r13d
0x180436f47  jmp     short loc_180436F4E
0x180436f49  mov     rcx, [rsp+100h+var_C0]
0x180436f4e  add     esi, r13d
0x180436f51  cmp     esi, [r8]
0x180436f54  jb      short loc_180436EDE
0x180436f56  mov     rsi, [rbp+37h+arg_0]
0x180436f5a  mov     [rsp+100h+var_B8], edi
0x180436f5e  xor     edi, edi
0x180436f60  lea     r13d, [rdi+8]
0x180436f64  test    rcx, rcx
0x180436f67  jz      loc_1804376E4
0x180436f6d  mov     rbx, [rcx+18h]
0x180436f71  mov     [rbp+37h+var_90], rbx
0x180436f75  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x180436f7a  test    eax, eax
0x180436f7c  jnz     loc_180437231
0x180436f82  cmp     [rsi+0C8h], edi
0x180436f88  jnz     loc_180437231
0x180436f8e  mov     r9, [rbp+37h+pdm]; pdm
0x180436f92  xor     r8d, r8d; pszPort
0x180436f95  mov     rdx, [rsi+58h]; pwszDevice
0x180436f99  xor     ecx, ecx; pwszDriver
0x180436f9b  call    cs:__imp_CreateDCW
0x180436fa1  mov     rdi, rax
0x180436fa4  test    rax, rax
0x180436fa7  jz      loc_1804371DA
0x180436fad  lea     edx, [r13+50h]; index
0x180436fb1  mov     rcx, rax; hdc
0x180436fb4  call    cs:__imp_GetDeviceCaps
0x180436fba  lea     edx, [r13+52h]; index
0x180436fbe  mov     rcx, rdi; hdc
0x180436fc1  movd    xmm7, eax
0x180436fc5  cvtdq2pd xmm7, xmm7
0x180436fc9  divsd   xmm7, cs:__real@400451eb851eb852
0x180436fd1  call    cs:__imp_GetDeviceCaps
0x180436fd7  xorps   xmm0, xmm0
0x180436fda  ucomisd xmm7, xmm0
0x180436fde  jp      short loc_180436FE2
0x180436fe0  jz      short loc_180436FFA
0x180436fe2  movd    xmm6, eax
0x180436fe6  cvtdq2pd xmm6, xmm6
0x180436fea  divsd   xmm6, cs:__real@400451eb851eb852
0x180436ff2  ucomisd xmm6, xmm0
0x180436ff6  jp      short loc_18043704D
0x180436ff8  jnz     short loc_18043704D
0x180436ffa  mov     rcx, rdi; hdc
0x180436ffd  call    cs:__imp_DeleteDC
0x180437003  mov     edi, 8000FFFFh
0x180437008  mov     rax, cs:WPP_GLOBAL_Control
0x18043700f  cmp     rax, r12
0x180437012  jz      loc_180437746
0x180437018  test    [rax+1Ch], r13b
0x18043701c  jz      loc_180437746
0x180437022  cmp     [rax+19h], r15b
0x180437026  jb      loc_180437746
0x18043702c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180437031  mov     edx, 68h ; 'h'
0x180437036  mov     dword ptr [rsp+100h+var_D8], 8000FFFFh
0x18043703e  lea     rcx, aGetdevicecaps; "GetDeviceCaps"
0x180437045  mov     r8, r14
0x180437048  jmp     loc_18043772E
0x18043704d  mov     edx, 70h ; 'p'; index
0x180437052  mov     rcx, rdi; hdc
0x180437055  call    cs:__imp_GetDeviceCaps
0x18043705b  imul    ecx, eax, 2710h
0x180437061  mov     edx, 71h ; 'q'; index
0x180437066  movd    xmm0, ecx
0x18043706a  mov     rcx, rdi; hdc
0x18043706d  cvtdq2pd xmm0, xmm0
0x180437071  divsd   xmm0, xmm7
0x180437075  cvttsd2si eax, xmm0
0x180437079  mov     [rbx], eax
0x18043707b  call    cs:__imp_GetDeviceCaps
0x180437081  imul    ecx, eax, 2710h
0x180437087  mov     edx, r13d; index
0x18043708a  movd    xmm0, ecx
0x18043708e  mov     rcx, rdi; hdc
0x180437091  cvtdq2pd xmm0, xmm0
0x180437095  divsd   xmm0, xmm6
0x180437099  cvttsd2si eax, xmm0
0x18043709d  mov     [rbx+4], eax
0x1804370a0  call    cs:__imp_GetDeviceCaps
0x1804370a6  movd    xmm0, dword ptr [rbx]
0x1804370aa  mov     edx, 0Ah; index
0x1804370af  imul    ecx, eax, 2710h
0x1804370b5  cvtdq2pd xmm0, xmm0
0x1804370b9  movd    xmm1, ecx
0x1804370bd  mov     rcx, rdi; hdc
0x1804370c0  cvtdq2pd xmm1, xmm1
0x1804370c4  divsd   xmm1, xmm7
0x1804370c8  addsd   xmm0, xmm1
0x1804370cc  cvttsd2si eax, xmm0
0x1804370d0  mov     [rbx+8], eax
0x1804370d3  call    cs:__imp_GetDeviceCaps
0x1804370d9  movd    xmm0, dword ptr [rbx+4]
0x1804370de  imul    ecx, eax, 2710h
0x1804370e4  cvtdq2pd xmm0, xmm0
0x1804370e8  movd    xmm1, ecx
0x1804370ec  mov     rcx, [rbp+37h+pdm]
0x1804370f0  cvtdq2pd xmm1, xmm1
0x1804370f4  divsd   xmm1, xmm6
0x1804370f8  addsd   xmm0, xmm1
0x1804370fc  cvttsd2si eax, xmm0
0x180437100  mov     [rbx+0Ch], eax
0x180437103  mov     eax, [rcx+48h]
0x180437106  test    al, 1
0x180437108  jz      loc_1804371CC
0x18043710e  cmp     [rcx+4Ch], r15w
0x180437113  jnz     loc_1804371CC
0x180437119  cmp     [rsp+100h+var_B8], 0
0x18043711e  jnz     loc_1804371CC
0x180437124  mov     edx, 6Eh ; 'n'; index
0x180437129  mov     rcx, rdi; hdc
0x18043712c  call    cs:__imp_GetDeviceCaps
0x180437132  imul    ecx, eax, 2710h
0x180437138  mov     edx, 6Fh ; 'o'; index
0x18043713d  movd    xmm0, ecx
0x180437141  mov     rcx, rdi; hdc
0x180437144  cvtdq2pd xmm0, xmm0
0x180437148  divsd   xmm0, xmm7
0x18043714c  cvttsd2si esi, xmm0
0x180437150  call    cs:__imp_GetDeviceCaps
0x180437156  mov     dword ptr [rbp+37h+arg_0], eax
0x180437159  mov     rcx, cs:WPP_GLOBAL_Control
0x180437160  cmp     rcx, r12
0x180437163  jz      short loc_1804371B0
0x180437165  test    byte ptr [rcx+1Ch], 1
0x180437169  jz      short loc_1804371B0
0x18043716b  cmp     [rcx+19h], r15b
0x18043716f  jb      short loc_1804371B0
0x180437171  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180437176  imul    ecx, dword ptr [rbp+37h+arg_0], 2710h
0x18043717d  mov     edx, 67h ; 'g'
0x180437182  mov     r9d, eax
0x180437185  mov     r8, r14
0x180437188  movd    xmm0, ecx
0x18043718c  cvtdq2pd xmm0, xmm0
0x180437190  divsd   xmm0, xmm6
0x180437194  cvttsd2si ecx, xmm0
0x180437198  mov     dword ptr [rsp+100h+var_D8], ecx
0x18043719c  mov     rcx, cs:WPP_GLOBAL_Control
0x1804371a3  mov     [rsp+100h+var_E0], esi
0x1804371a7  mov     rcx, [rcx+10h]
0x1804371ab  call    WPP_SF_DLD
0x1804371b0  mov     edx, [rbx]
0x1804371b2  mov     eax, esi
0x1804371b4  sub     eax, [rbx+8]
  ... truncated ...
```
