# CDocObjectHost::OnExec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x18003e130`
- end: `0x18003f749`
- name: `?OnExec@CDocObjectHost@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `5657`
- prototype: `__int64 __fastcall(CDocObjectHost *__hidden this, const struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `64`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005030`
- `0x1800144d0`
- `0x18001546c`
- `0x1800184f0`
- `0x18001d1a0`
- `0x180024b74`
- `0x18003b368`
- `0x18003e130`
- `0x18004d964`
- `0x18005a24c`
- `0x18006ff08`
- `0x180074f9c`
- `0x18007587c`
- `0x180078534`
- `0x18007af60`
- `0x18007b178`
- `0x18007c324`
- `0x18007ecc0`
- `0x180084250`
- `0x180085898`
- `0x180099fe8`
- `0x18009a074`
- `0x18009d0d0`
- `0x1800a7620`
- `0x1800c7650`
- `0x1800cd150`
- `0x1800cd2a4`
- `0x1800cd638`
- `0x1800cff60`
- `0x1800d3ea4`
- `0x1800dd040`
- `0x180104638`
- `0x180109710`
- `0x180123800`
- `0x180140a4c`
- `0x180141fbc`
- `0x180147fcc`
- `0x1801485c4`
- `0x180149778`
- `0x18014b984`
- `0x18014c27c`
- `0x18014e33c`
- `0x18014e7f4`
- `0x18014e884`
- `0x1801508cc`
- `0x180150bb4`
- `0x180150e74`
- `0x1801510fc`
- `0x1801512ac`
- `0x18015136c`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18003e932`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18003e932`
- `KERNEL32!DeactivateActCtx` at `0x18003e625`
- `KERNEL32!DeactivateActCtx` at `0x18003e625`
- `KERNEL32!LocalFree` at `0x18003ec75`
- `KERNEL32!LocalFree` at `0x18003ec75`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18003e4f9`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18003e4f9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18003ea46`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18003ec40`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18003ea46`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18003ec40`
- `USER32!PostMessageW` at `0x18003ec18`
- `USER32!PostMessageW` at `0x18003ec5e`
- `USER32!PostMessageW` at `0x18003ec18`
- `USER32!PostMessageW` at `0x18003ec5e`
- `USER32!GetSystemMetrics` at `0x18003f22b`
- `USER32!GetSystemMetrics` at `0x18003f22b`
- `USER32!EnableWindow` at `0x18003e554`
- `USER32!EnableWindow` at `0x18003e5b7`
- `USER32!EnableWindow` at `0x18003e554`
- `USER32!EnableWindow` at `0x18003e5b7`
- `USER32!GetAncestor` at `0x18003e53b`
- `USER32!GetAncestor` at `0x18003e53b`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003eaac`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003eb7a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003eaac`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003eb7a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003ead2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003eba5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003ead2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003eba5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003eaf9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003ebc6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003eaf9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003ebc6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003eb44`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003ebf6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003eb44`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003ebf6`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18003e4cf`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18003e4cf`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003edfd`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003edfd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003e70c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f118`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003e70c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003f118`
- `WININET!InternetSetOptionW` at `0x18003e5d9`
- `WININET!InternetSetOptionW` at `0x18003e5d9`

## pseudocode

```c
__int64 __fastcall CDocObjectHost::OnExec(
        CDocObjectHost *this,
        const struct _GUID *a2,
        unsigned int a3,
        __int64 a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6)
{
  unsigned int v6; // r13d
  unsigned int v7; // edi
  const struct _GUID *v8; // rbx
  CDocObjectHost *v10; // rcx
  __int64 v11; // rcx
  __int64 result; // rax
  LONG lVal; // eax
  int v14; // eax
  LONG v15; // edx
  __int64 v16; // rcx
  __int64 v17; // rax
  const unsigned __int16 *v18; // r8
  _lambda_ce15d259f53648a8c53bb735717135d9_ *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  HWND v23; // rsi
  int v24; // eax
  HWND v25; // r10
  int v26; // ebx
  HWND Ancestor; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  struct IUnknown *v33; // r8
  int v34; // esi
  __int64 v35; // rcx
  int v36; // esi
  LONG HookedTime; // esi
  IUnknown *v38; // rcx
  struct IUnknown *v39; // rbx
  int v40; // r9d
  PWSTR v41; // rax
  UINT v42; // edx
  SAFEARRAY *parray; // rcx
  unsigned int UBound; // ebx
  SAFEARRAY *v45; // rcx
  SAFEARRAY *v46; // rcx
  SAFEARRAY *v47; // rcx
  UINT v48; // edx
  PWSTR v49; // rbx
  __int64 v50; // rax
  CDocObjectHost *v51; // rcx
  unsigned int v52; // edx
  int v53; // eax
  __int64 v54; // rax
  __int64 (__fastcall ***v55)(_QWORD, GUID *, _OWORD *); // rcx
  int v56; // esi
  __int64 v57; // rcx
  struct _GUID *v58; // rax
  __int64 v59; // rcx
  unsigned int v60; // esi
  __int64 v61; // rdx
  const unsigned __int16 *v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rdx
  _WORD *v65; // rcx
  int UrlSchemeW; // eax
  __int64 v67; // rdx
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rcx
  BSTR bstrVal; // rbx
  int v73; // eax
  unsigned int v74; // edi
  unsigned int v75; // edi
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v79; // rcx
  struct tagVARIANT *v80; // [rsp+20h] [rbp-E0h]
  _OWORD *v81; // [rsp+20h] [rbp-E0h]
  struct tagVARIANT *v82; // [rsp+28h] [rbp-D8h]
  bool v83; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD ulCookie[2]; // [rsp+50h] [rbp-B0h] BYREF
  HWND hwnd; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID pPrivacyEnum; // [rsp+78h] [rbp-88h] BYREF
  __int16 v87; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v88; // [rsp+90h] [rbp-70h]
  char v89; // [rsp+98h] [rbp-68h]
  int v90; // [rsp+9Ch] [rbp-64h]
  __int128 v91; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v92; // [rsp+B0h] [rbp-50h]
  int v93; // [rsp+C0h] [rbp-40h]
  __int64 v94; // [rsp+C8h] [rbp-38h]
  WCHAR Buffer[2088]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v96[2088]; // [rsp+1130h] [rbp+1030h] BYREF

  v6 = a4;
  v7 = a3;
  v8 = a2;
  if ( !a2 )
  {
    v10 = (CDocObjectHost *)((char *)this - 72);
    if ( *((_QWORD *)v10 + 48) )
    {
      if ( a3 != 35 )
      {
        switch ( a3 )
        {
          case 1u:
            CDocObjectHost::_OnOpen(v10);
            return 0;
          case 2u:
            return 2147500033LL;
          case 3u:
            CDocObjectHost::_OnSave(v10);
            return 0;
          case 0x15u:
            CDocObjectHost::_InitToolbarButtons(v10);
            return 2147500037LL;
          case 0x16u:
            v11 = *((_QWORD *)this + 110);
            if ( v11 )
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)v11 + 32LL))(
                v11,
                0,
                a3,
                a4,
                a5,
                a6);
            return 0;
          case 0x19u:
            lVal = a5->lVal;
            if ( lVal )
            {
              v14 = 100 * lVal;
              if ( *((_DWORD *)this + 176) != v14 )
                *((_DWORD *)this + 176) = v14;
            }
            return 0;
          case 0x1Au:
            v15 = a5->lVal;
            if ( v15 )
              CDocObjectHost::_OnSetProgressPos(v10, v15, 4u);
            return 0;
          case 0x1Bu:
            CDocObjectHost::_OnSetStatusText(v10, a5);
            return 0;
          case 0x1Cu:
            if ( !a5 )
              goto LABEL_148;
            CDocObjectHost::_OnSetTitle(v10, a5);
            return 0;
          case 0x22u:
            break;
          case 0x27u:
            CDocObjectHost::_OnSetProgressPos(v10, 0, 1u);
            return 0;
          case 0x2Du:
            CDocObjectHost::_OnClose(v10);
            return 0;
          case 0x3Bu:
            return CDocObjectHost::_ShowPageActionMenu(v10, a4, a5);
          case 0x50u:
            return CDocObjectHost::_HandleFullScreenConsentCommand(v10, a5);
          default:
            return 2147746048LL;
        }
      }
      v16 = *((_QWORD *)this + 41);
      if ( v16 )
        (*(void (__fastcall **)(__int64, _QWORD, bool, struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)v16 + 240LL))(
          v16,
          *((_QWORD *)this + 36),
          a3 == 35,
          a5,
          a6);
      return 0;
    }
    return 2147500037LL;
  }
  v17 = *(_QWORD *)&CGID_ShellDocView.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&CGID_ShellDocView.Data1 == *(_QWORD *)&a2->Data1 )
    v17 = *(_QWORD *)CGID_ShellDocView.Data4 - *(_QWORD *)a2->Data4;
  if ( !v17 )
  {
    if ( a3 == 9 )
      return !*((_QWORD *)this + 101) || (*((_BYTE *)this + 576) & 8) == 0;
    switch ( a3 )
    {
      case 0x11u:
        v30 = *((_QWORD *)this + 111);
        if ( !v30 )
          return 2147500037LL;
        return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v30 + 40LL))(v30, a5->cyVal.Lo);
      case 0x1Cu:
        if ( *((_QWORD *)this + 242) )
        {
          v32 = *((_DWORD *)this + 517);
          if ( (v32 & 2) != 0 )
          {
            v33 = (struct IUnknown *)*((_QWORD *)this + 104);
            if ( v33 )
            {
              if ( !*((_QWORD *)this + 101) )
              {
                *((_DWORD *)this + 517) = v32 | 0x10;
                CDocObjectHost::CDOHBindStatusCallback::OnObjectAvailable(
                  (CDocObjectHost *)((char *)this + 1880),
                  &IID_IUnknown,
                  v33);
                CDocObjectHost::CDOHBindStatusCallback::AbortBinding((CDocObjectHost *)((char *)this + 1880));
              }
            }
          }
        }
        if ( *((_DWORD *)this + 155) )
          CDocObjectHost::_OnReadyState((CDocObjectHost *)((char *)this - 72), 4, 1);
        return 0;
      case 0x1Eu:
      case 0x3Cu:
        return 0;
      case 0x21u:
        if ( (int)CDocObjectHost::_GetCurrentPage((CDocObjectHost *)((char *)this - 72), Buffer, 0x824u, 1) < 0 )
          return 0;
        v18 = (const unsigned __int16 *)*((_QWORD *)this + 251);
        if ( v18 && *v18 )
          StringCchCopyW(Buffer, 0x824u, v18);
        *(_QWORD *)&ulCookie[0] = 0;
        SHActivateContext(ulCookie);
        v19 = _lambda_ce15d259f53648a8c53bb735717135d9_::_lambda_ce15d259f53648a8c53bb735717135d9_(
                (_lambda_ce15d259f53648a8c53bb735717135d9_ *)&pPrivacyEnum,
                (const struct DesktopEuppFirstRunUI *)Buffer,
                (const struct EuppFirstRunSettings **)this - 9);
        DpiContextWrapper__lambda_8abd0502c25a106ae885053b1c1b3f2d_(v20, v19);
        goto LABEL_60;
      case 0x23u:
        if ( (unsigned int)SHRestricted2W(1610612740, 0, 0) )
          return 0;
        hwnd = (HWND)*((_QWORD *)this + 7);
        if ( (int)SuppressDialog(&hwnd, 1u) < 0 )
          return 0;
        CDocObjectHost::_GetCurrentPage((CDocObjectHost *)((char *)this - 72), v96, 0x824u, 0);
        v22 = IsProtectedModeProcess();
        if ( v22 )
        {
          if ( v22 == 1 )
          {
            *(_QWORD *)&ulCookie[0] = 0;
            SHActivateContext(ulCookie);
            IEZoneConfigureW(hwnd, v96);
LABEL_60:
            if ( *(_QWORD *)&ulCookie[0] )
              DeactivateActCtx(0, *(ULONG_PTR *)&ulCookie[0]);
          }
        }
        else
        {
          LoadStringW(g_hinstMUI, 0x2003u, Buffer, 150);
          v23 = 0;
          v91 = 0;
          v93 = 0;
          v92 = 0;
          v94 = 0;
          v24 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(&v91);
          v25 = hwnd;
          v26 = v24;
          if ( hwnd )
          {
            Ancestor = GetAncestor(hwnd, 2u);
            v23 = Ancestor;
            if ( Ancestor )
              EnableWindow(Ancestor, 0);
            v25 = hwnd;
          }
          if ( v26 >= 0
            && (*(int (__fastcall **)(_QWORD, HWND, unsigned __int16 *, WCHAR *))(**((_QWORD **)&v92 + 1) + 104LL))(
                 *((_QWORD *)&v92 + 1),
                 v25,
                 v96,
                 Buffer) >= 0
            && (int)CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                      &v91,
                      0) >= 0 )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v92 + 1) + 112LL))(*((_QWORD *)&v92 + 1));
          }
          if ( v23 )
            EnableWindow(v23, 1);
          CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(&v91);
          InternetSetOptionW(0, 0x27u, 0, 0);
        }
        return 0;
      case 0x24u:
        CDocObjectHost::_OnCodePageChange((CDocObjectHost *)((char *)this - 72), a5);
        return 0;
      case 0x25u:
        *((_DWORD *)this + 144) |= 0x1000u;
        v35 = *((_QWORD *)this + 39);
        *((_DWORD *)this + 158) = a5->lVal;
        *(_QWORD *)&ulCookie[0] = 0;
        if ( v35 && (*(int (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v35 + 120LL))(v35, ulCookie) >= 0 )
        {
          if ( *(_QWORD *)&ulCookie[0] && (unsigned int)SHIsSameObject(*((_QWORD *)this + 36)) )
            CDocObjectHost::_ForwardSetSecureLock((CDocObjectHost *)((char *)this - 72), a5->lVal);
          ATL::CComPtr<IPrivacIEDatabase>::Release(ulCookie);
        }
        return 0;
      case 0x2Au:
      case 0x39u:
      case 0x81u:
        v31 = *((_QWORD *)this + 40);
        if ( !v31 )
          return 2147500037LL;
        return (*(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD))(*(_QWORD *)v31 + 32LL))(v31, a2, a3);
      case 0x2Bu:
        v82 = a6;
        v80 = a5;
        return IUnknown_Exec(*((_QWORD *)this + 101), (_DWORD)a2, a3, a4, (__int64)v80, (__int64)v82);
      case 0x37u:
        CDocObjectHost::_ResetStatusBar((CDocObjectHost *)((char *)this - 72));
        return 0;
      case 0x4Au:
        v28 = *((_QWORD *)this + 99);
        *(_QWORD *)&pPrivacyEnum.Data1 = 0;
        *(_QWORD *)&ulCookie[0] = 0;
        if ( v28
          && (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _OWORD *))(*(_QWORD *)v28 + 160LL))(
               v28,
               *((_QWORD *)this + 100),
               0,
               ulCookie) < 0 )
        {
          *(_QWORD *)&ulCookie[0] = 0;
        }
        v29 = *((_QWORD *)this + 42);
        if ( v29
          && (*(int (__fastcall **)(__int64, GUID *, GUID *, struct _GUID *))(*(_QWORD *)v29 + 24LL))(
               v29,
               &IID_IEnumPrivacyRecords,
               &GUID_3050f844_98b5_11cf_bb82_00aa00bdce0b,
               &pPrivacyEnum) >= 0 )
        {
          LODWORD(hwnd) = 0;
          if ( v6 == 1
            || (*(int (__fastcall **)(_QWORD, HWND *))(**(_QWORD **)&pPrivacyEnum.Data1 + 40LL))(
                 *(_QWORD *)&pPrivacyEnum.Data1,
                 &hwnd) >= 0
            && (_DWORD)hwnd )
          {
            DoPrivacyDlg(
              *((HWND *)this + 7),
              *(PCWSTR *)&ulCookie[0],
              *(IEnumPrivacyRecords **)&pPrivacyEnum.Data1,
              v6 == 1);
          }
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pPrivacyEnum.Data1 + 16LL))(*(_QWORD *)&pPrivacyEnum.Data1);
        }
        if ( *(_QWORD *)&ulCookie[0] )
          CoTaskMemFree(*(LPVOID *)&ulCookie[0]);
        return 0;
      case 0x4Bu:
        if ( (*((_DWORD *)this + 144) & 0x1000) != 0 )
          v36 = *((_DWORD *)this + 158);
        else
          v36 = 0;
        CDocObjectHost::_ForwardSetSecureLock((CDocObjectHost *)((char *)this - 72), v36);
        return 0;
      case 0x56u:
      case 0x59u:
        if ( !a6 )
          goto LABEL_148;
        *(_OWORD *)&a6->vt = 0;
        HookedTime = 0;
        a6->pRecInfo = 0;
        a6->vt = 19;
        v38 = (IUnknown *)*((_QWORD *)this + 101);
        *(_QWORD *)&ulCookie[0] = 0;
        if ( IUnknown_GetWindow(v38, (HWND *)ulCookie) >= 0 )
          HookedTime = TLSGetLastHookedTime(*(HWND *)&ulCookie[0]);
        a6->lVal = HookedTime;
        return 0;
      case 0x67u:
        if ( !a5 || a5->vt != 3 )
          goto LABEL_148;
        CDocObjectHost::_OnSetPhishingFilterStatus((char *)this - 72, a5->cyVal.Lo);
        return 0;
      case 0x68u:
        v21 = *((_QWORD *)this + 101);
        *(_QWORD *)&ulCookie[1] = 0;
        ulCookie[0] = 0xDu;
        IUnknown_Exec(v21, (unsigned int)&CGID_ShellDocView, 104, 0, (__int64)ulCookie, 0);
        return 0;
      case 0x71u:
        CDocObjectHost::_ShowAppCompatDialog((CDocObjectHost *)((char *)this - 72));
        return 0;
      case 0x72u:
        v34 = 0;
        if ( a5->iVal == -1 )
          v34 = 8;
        *((_DWORD *)this + 144) = *((_DWORD *)this + 144) & 0xFFFFFFF7 | v34;
        return 0;
      case 0x79u:
        IEHard_NavWarning(*((HWND *)this + 7), 1);
        return 0;
      case 0x7Au:
        v82 = a6;
        a3 = 122;
        v80 = a5;
        goto LABEL_41;
      case 0x7Bu:
        a3 = 123;
        v82 = 0;
        v80 = 0;
LABEL_41:
        LODWORD(a4) = 0;
        a2 = &CGID_ShellDocView;
        return IUnknown_Exec(*((_QWORD *)this + 101), (_DWORD)a2, a3, a4, (__int64)v80, (__int64)v82);
      case 0x88u:
        if ( !a6 || a6->vt != 3 )
          goto LABEL_148;
        a6->lVal = TLSGetTabId();
        return 0;
      case 0x93u:
        if ( !a5 || a5->vt != 8 )
          goto LABEL_148;
        v41 = StrDupW(a5->bstrVal);
        v42 = 33838;
        goto LABEL_146;
      case 0x96u:
        if ( !a5 || a5->vt != 8 )
          goto LABEL_148;
        v41 = StrDupW(a5->bstrVal);
        v42 = 33859;
LABEL_146:
        v49 = v41;
        if ( !PostMessageW(*((HWND *)this + 7), v42, 0, (LPARAM)v41) )
          LocalFree(v49);
        return 0;
      case 0x99u:
        v48 = 33869;
        goto LABEL_141;
      case 0x9Au:
        v48 = 33871;
LABEL_141:
        PostMessageW(*((HWND *)this + 7), v48, 0, 0);
        return 0;
      case 0x9Bu:
        *(_QWORD *)&ulCookie[0] = 0;
        if ( (int)CreateData(ulCookie) >= 0 )
        {
          v39 = *(struct IUnknown **)&ulCookie[0];
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&ulCookie[0] + 64LL))(*(_QWORD *)&ulCookie[0], 69771);
          ((void (__fastcall *)(struct IUnknown *, __int64))v39->lpVtbl[2].QueryInterface)(v39, 65660);
          ((void (__fastcall *)(struct IUnknown *, __int64))v39->lpVtbl[5].AddRef)(v39, 1);
          ((void (__fastcall *)(struct IUnknown *, _QWORD, __int64))v39->lpVtbl[1].AddRef)(v39, 0, 34392);
          CLayerParticipant::LayerSetInterface((CDocObjectHost *)((char *)this + 88), v39, 69771, v40);
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(ulCookie);
        return 0;
      case 0x9Fu:
        if ( !a5 || a5->vt != 8204 || SafeArrayGetDim(a5->parray) != 1 )
          return (unsigned int)-2147024809;
        parray = a5->parray;
        LODWORD(hwnd) = 0;
        UBound = SafeArrayGetUBound(parray, 1u, (LONG *)&hwnd);
        if ( (UBound & 0x80000000) == 0 )
        {
          if ( (_DWORD)hwnd == 2 )
          {
            v45 = a5->parray;
            *(_QWORD *)&ulCookie[0] = 0;
            UBound = SafeArrayAccessData(v45, (void **)ulCookie);
            if ( (UBound & 0x80000000) == 0 )
            {
              if ( **(_WORD **)&ulCookie[0] == 8
                && *(_WORD *)(*(_QWORD *)&ulCookie[0] + 24LL) == 3
                && *(_WORD *)(*(_QWORD *)&ulCookie[0] + 48LL) == 3 )
              {
                CDocObjectHost::_OnMediaCaptureGetConsent(
                  (CDocObjectHost *)((char *)this - 72),
                  *(const unsigned __int16 **)(*(_QWORD *)&ulCookie[0] + 8LL),
                  *(_DWORD *)(*(_QWORD *)&ulCookie[0] + 32LL),
                  *(_DWORD *)(*(_QWORD *)&ulCookie[0] + 56LL));
              }
              else
              {
                UBound = -2147024809;
              }
              SafeArrayUnaccessData(a5->parray);
            }
          }
          else
          {
            return (unsigned int)-2147024809;
          }
        }
        return UBound;
      case 0xA0u:
        if ( !a5 || a5->vt != 8204 || SafeArrayGetDim(a5->parray) != 1 )
          goto LABEL_148;
        v46 = a5->parray;
        LODWORD(hwnd) = 0;
        UBound = -2147024809;
        SafeArrayGetUBound(v46, 1u, (LONG *)&hwnd);
        if ( (_DWORD)hwnd != 1 )
          return UBound;
        v47 = a5->parray;
        *(_QWORD *)&ulCookie[0] = 0;
        UBound = SafeArrayAccessData(v47, (void **)ulCookie);
        if ( (UBound & 0x80000000) != 0 )
          return UBound;
        CDocObjectHost::_ShowMediaConsent(
          (CDocObjectHost *)((char *)this - 72),
          *(const unsigned __int16 **)(*(_QWORD *)&ulCookie[0] + 8LL),
          *(_DWORD *)(*(_QWORD *)&ulCookie[0] + 32LL));
        SafeArrayUnaccessData(a5->parray);
        return UBound;
      case 0xA6u:
        CDocObjectHost::CDOHBindStatusCallback::_HandleVTabSwitch(
          (CDocObjectHost *)((char *)this + 1880),
          (CDocObjectHost *)((char *)this - 72),
          1);
        return 0;
      case 0xB4u:
        if ( a5 && a5->vt == 11 )
        {
          CLayerParticipant::LayerSetBool((CDocObjectHost *)((char *)this + 88), a5->iVal != 0, 69697, 0);
          return 0;
        }
LABEL_148:
        result = 2147942487LL;
        break;
      default:
        return 2147746048LL;
    }
    return result;
  }
  v50 = *(_QWORD *)&CGID_Explorer.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&CGID_Explorer.Data1 == *(_QWORD *)&a2->Data1 )
    v50 = *(_QWORD *)CGID_Explorer.Data4 - *(_QWORD *)a2->Data4;
  if ( !v50 )
  {
    switch ( a3 )
    {
      case 3u:
        return CDocObjectHost::_OnMaySaveChanges((CDocObjectHost *)((char *)this - 72), a5);
      case 0x29u:
        if ( (_DWORD)a4 == 5 )
          a6->lVal = 0;
        else
          a6->lVal = -1;
        return 0;
      case 0x3Du:
        *((_DWORD *)this + 144) |= 0x400000u;
        return 0;
      case 0x43u:
        if ( !*((_QWORD *)this + 39) || !(unsigned int)IsPanToolSupported() )
          return 2147746048LL;
        return IUnknown_Exec(*((_QWORD *)this + 39), (unsigned int)&CGID_Explorer, 67, 0, (__int64)a5, (__int64)a6);
      case 0x44u:
        if ( !*((_QWORD *)this + 39) || !(unsigned int)IsPanToolSupported() )
          return 2147746048LL;
        return IUnknown_Exec(*((_QWORD *)this + 39), (unsigned int)&CGID_Explorer, 68, 0, (__int64)a5, (__int64)a6);
      case 0x4Eu:
        v51 = (CDocObjectHost *)((char *)this - 72);
        v52 = -1610612736;
        v53 = *((_DWORD *)this + 338);
        if ( (v53 & 0x2040202) == 0 )
          v52 = 0x80000000;
        CDocObjectHost::_HandlePageActionBlocked(v51, v53 | v52, a5);
        RefreshTabProtectedPolicies();
        return 0;
      case 0x88u:
        if ( !IsDualEngineProcess() )
          return 2147746048LL;
        CDocObjectHost::_DualEngineForceUpdateFavicon((CDocObjectHost *)((char *)this - 72));
        return 0;
      default:
        return 2147746048LL;
    }
  }
  v54 = *(_QWORD *)&CGID_DocHostCommandHandler.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&CGID_DocHostCommandHandler.Data1 == *(_QWORD *)&a2->Data1 )
    v54 = *(_QWORD *)CGID_DocHostCommandHandler.Data4 - *(_QWORD *)a2->Data4;
  if ( v54 )
  {
    v68 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_InternetButtons.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_InternetButtons.Data1 )
      v68 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_InternetButtons.Data4;
    if ( !v68 )
      goto LABEL_233;
    v69 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_MSOButtons.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_MSOButtons.Data1 )
      v69 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_MSOButtons.Data4;
    if ( !v69 )
    {
LABEL_233:
      if ( (_DWORD)a4 == 1 )
      {
        if ( *((_QWORD *)this + 40) && a5 && a5->vt == 37 )
        {
          bstrVal = a5->bstrVal;
          LOWORD(ulCookie[0]) = 3;
          memset((char *)ulCookie + 2, 0, 22);
          if ( GetSystemMetrics(40) )
            v73 = bstrVal[4];
          else
            v73 = *bstrVal;
          DWORD2(ulCookie[0]) = v73 | (bstrVal[6] << 16);
          v74 = v7 - 369;
          if ( v74 )
          {
            v75 = v74 - 1;
            if ( v75 )
            {
              if ( v75 == 3 )
                (*(void (__fastcall **)(_QWORD, const GUID *, __int64, _QWORD, _OWORD *, _QWORD))(**((_QWORD **)this + 40)
                                                                                                + 32LL))(
                  *((_QWORD *)this + 40),
                  &CGID_ShellDocView,
                  1,
                  0,
                  ulCookie,
                  0);
            }
            else
            {
              (*(void (__fastcall **)(_QWORD, const GUID *, __int64, _QWORD, _OWORD *, _QWORD))(**((_QWORD **)this + 40)
                                                                                              + 32LL))(
                *((_QWORD *)this + 40),
                &CGID_ShellDocView,
                50,
                0,
                ulCookie,
                0);
            }
          }
          else
          {
            v76 = *((_QWORD *)this + 40);
            v77 = 12;
            v78 = 0;
            v81 = ulCookie;
LABEL_251:
            (*(void (__fastcall **)(__int64, const GUID *, __int64, __int64, _OWORD *, _QWORD))(*(_QWORD *)v76 + 32LL))(
              v76,
              &CGID_Explorer,
              v77,
              v78,
              v81,
              0);
          }
        }
      }
      else if ( a3 - 0x2000 > 0x200 )
      {
        switch ( a3 )
        {
          case 0x104u:
          case 0x115u:
          case 0x170u:
            CDocObjectHost::_MappedBrowserExec((CDocObjectHost *)((char *)this - 72), a3, 2u);
            break;
          case 0x107u:
          case 0x108u:
          case 0x109u:
            CDocObjectHost::_MappedBrowserExec((CDocObjectHost *)((char *)this - 72), a3, 0);
            break;
          case 0x174u:
            v76 = *((_QWORD *)this + 40);
            if ( v76 )
            {
              v78 = 2;
              v77 = 47;
              v81 = 0;
              goto LABEL_251;
            }
            break;
          case 0x17Cu:
            CDocObjectHost::_OnPanningTool((CDocObjectHost *)((char *)this - 72));
            break;
          default:
            return 0;
        }
      }
      else
      {
        v79 = *((_QWORD *)this + 39);
        v88 = a3;
        v87 = 3;
        IUnknown_Exec(v79, (unsigned int)&CGID_Explorer, 79, 0, (__int64)&v87, 0);
        ATL::CComVariant::Clear((ATL::CComVariant *)&v87);
      }
      return 0;
    }
    v70 = *(_QWORD *)&CGID_InternetExplorer.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CGID_InternetExplorer.Data1 == *(_QWORD *)&a2->Data1 )
      v70 = *(_QWORD *)CGID_InternetExplorer.Data4 - *(_QWORD *)a2->Data4;
    if ( v70 )
      return 2147746052LL;
    if ( a3 == 2 || a3 == 3 || a3 == 4 || a3 - 5 < 2 )
    {
      v71 = *((_QWORD *)this + 40);
      if ( v71 )
        return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 32LL))(v71);
      return 2147500037LL;
    }
    return 2147746048LL;
  }
  if ( a3 > 0x8FC )
  {
    if ( a3 == 6041 || a3 == 6042 || a3 - 6043 <= 1 )
      goto LABEL_200;
    return 2147746048LL;
  }
  if ( a3 != 2300 )
  {
    switch ( a3 )
    {
      case 4u:
        CDocObjectHost::_OnSaveAs((CDocObjectHost *)((char *)this - 72));
        return 0;
      case 0xAu:
      case 0x29u:
      case 0x2Bu:
      case 0x44u:
      case 0x54u:
      case 0x55u:
        goto LABEL_192;
      case 0x28u:
        if ( (*((_DWORD *)this + 144) & 0x40000) != 0 )
        {
          v55 = (__int64 (__fastcall ***)(_QWORD, GUID *, _OWORD *))*((_QWORD *)this + 48);
          if ( v55 )
          {
            *(_QWORD *)&ulCookie[0] = 0;
            v56 = (**v55)(v55, &GUID_b722bccb_4e68_101b_a2bc_00aa00404770, ulCookie);
            if ( v56 >= 0 )
            {
              v56 = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, struct tagVARIANT *))(**(_QWORD **)&ulCookie[0] + 32LL))(
                      *(_QWORD *)&ulCookie[0],
                      v8,
                      v7,
                      v6,
                      a5,
                      a6);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&ulCookie[0] + 16LL))(*(_QWORD *)&ulCookie[0]);
            }
          }
          else
          {
            v57 = *((_QWORD *)this + 35);
            if ( v57 )
              return (unsigned int)(*(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD))(*(_QWORD *)(v57 + 24) + 32LL))(
                                     v57 + 24,
                                     a2,
                                     a3);
            else
              return (unsigned int)-2147467259;
          }
        }
        else
        {
          v56 = 0;
          a6->vt = 11;
          a6->iVal = -1;
        }
        return (unsigned int)v56;
      case 0x2Au:
        v83 = 0;
        CLayerParticipant::LayerGetBool((CDocObjectHost *)((char *)this + 88), &v83, 69722, 0);
        if ( v83 )
          return 0;
        goto LABEL_190;
      case 0x2Cu:
LABEL_190:
        if ( v7 == 44 )
        {
          v58 = CreateUserInputId(&pPrivacyEnum);
          v89 = 0;
          ulCookie[0] = *v58;
          ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)&v87, (struct _GUID *)ulCookie);
          BrowserTelemetry::IEPrintCommandInvoked();
          v90 = 3;
          ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&v87);
        }
LABEL_192:
        v59 = *((_QWORD *)this + 35);
        if ( v59 )
          v60 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)(v59 + 24) + 32LL))(
                  v59 + 24,
                  v8,
                  v7,
                  v6,
                  a5,
                  a6);
        else
          v60 = -2147467259;
        result = v60;
        break;
      case 0x39u:
        result = CDocObjectHost::FocusViewControls((CDocObjectHost *)((char *)this - 72), 0);
        break;
      default:
        return 2147746048LL;
    }
    return result;
  }
LABEL_200:
  v61 = 0;
  if ( a5 && a5->vt == 3 && (a5->lVal & 0x80000) != 0 )
    v61 = 4;
  (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 8) + 64LL))((char *)this + 64, v61);
  v62 = (const unsigned __int16 *)*((_QWORD *)this + 70);
  if ( v62 )
  {
    *((_DWORD *)this + 144) |= 0x800000u;
    CDocObjectHost::_DoAsyncNavigation((CDocObjectHost *)((char *)this - 72), v62);
    return 0;
  }
  v63 = *((_QWORD *)this + 99);
  UBound = -2147221248;
  if ( !v63 )
    return UBound;
  v64 = *((_QWORD *)this + 100);
  *(_QWORD *)&ulCookie[0] = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, _OWORD *))(*(_QWORD *)v63 + 160LL))(v63, v64, 0, ulCookie) < 0 )
    return UBound;
  if ( (unsigned int)IsErrorUrl(*(_QWORD *)&ulCookie[0]) )
  {
    v65 = (_WORD *)*((_QWORD *)this + 68);
    if ( v65 )
    {
      if ( *v65 )
      {
        UrlSchemeW = GetUrlSchemeW(v65 + 1);
        if ( (unsigned int)(UrlSchemeW - 1) <= 2 || UrlSchemeW == 11 )
        {
          v67 = *((_QWORD *)this + 68);
          *((_DWORD *)this + 144) |= 0x800000u;
          CDocObjectHost::_DoAsyncNavigation((CDocObjectHost *)((char *)this - 72), (const unsigned __int16 *)(v67 + 2));
        }
        UBound = 0;
      }
    }
  }
  CoTaskMemFree(*(LPVOID *)&ulCookie[0]);
  return UBound;
}

```

## disassembly

```asm
0x18003e130  push    rbp
0x18003e132  push    rbx
0x18003e133  push    rsi
0x18003e134  push    rdi
0x18003e135  push    r12
0x18003e137  push    r13
0x18003e139  push    r14
0x18003e13b  push    r15
0x18003e13d  lea     rbp, [rsp-2098h]
0x18003e145  mov     eax, 2198h
0x18003e14a  call    _alloca_probe
0x18003e14f  sub     rsp, rax
0x18003e152  mov     rax, cs:__security_cookie
0x18003e159  xor     rax, rsp
0x18003e15c  mov     [rbp+20D0h+var_50], rax
0x18003e163  mov     r12, [rbp+20D0h+arg_28]
0x18003e16a  mov     r13d, r9d
0x18003e16d  mov     r15, [rbp+20D0h+arg_20]
0x18003e174  mov     edi, r8d
0x18003e177  mov     rbx, rdx
0x18003e17a  mov     r14, rcx
0x18003e17d  test    rdx, rdx
0x18003e180  jnz     loc_18003E2FF
0x18003e186  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x18003e18a  cmp     [rcx+180h], rdx
0x18003e191  jz      loc_18003E232
0x18003e197  cmp     r8d, 23h ; '#'
0x18003e19b  jz      loc_18003E2C0; jumptable 000000018003E1C9 case 34
0x18003e1a1  lea     eax, [r8-1]; switch 80 cases
0x18003e1a5  cmp     eax, 4Fh
0x18003e1a8  ja      def_18003E1C9; jumptable 000000018003E1C9 default case, cases 4-20,23,24,29-33,35-38,40-44,46-58,60-79
0x18003e1ae  lea     r8, __ImageBase
0x18003e1b5  movzx   eax, ds:(byte_18003F434 - 180000000h)[r8+rax]
0x18003e1be  mov     edx, ds:(jpt_18003E1C9 - 180000000h)[r8+rax*4]
0x18003e1c6  add     rdx, r8
0x18003e1c9  jmp     rdx; switch jump
0x18003e1cf  xor     edx, edx; jumptable 000000018003E1C9 case 39
0x18003e1d1  mov     r8d, 1; unsigned int
0x18003e1d7  call    ?_OnSetProgressPos@CDocObjectHost@@IEAAXKK@Z; CDocObjectHost::_OnSetProgressPos(ulong,ulong)
0x18003e1dc  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e1e1  mov     rcx, [r14+370h]; jumptable 000000018003E1C9 case 22
0x18003e1e8  test    rcx, rcx
0x18003e1eb  jz      def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e1f1  mov     [rsp+21D0h+var_21A8], r12
0x18003e1f6  mov     r8d, edi
0x18003e1f9  mov     [rsp+21D0h+var_21B0], r15
0x18003e1fe  xor     edx, edx
0x18003e200  jmp     loc_18003F397
0x18003e205  mov     eax, 80004001h; jumptable 000000018003E1C9 case 2
0x18003e20a  jmp     loc_18003F3D3
0x18003e20f  call    ?_OnOpen@CDocObjectHost@@IEAAXXZ; jumptable 000000018003E1C9 case 1
0x18003e214  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e219  call    ?_OnSave@CDocObjectHost@@IEAAXXZ; jumptable 000000018003E1C9 case 3
0x18003e21e  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e223  call    ?_OnClose@CDocObjectHost@@IEBAXXZ; jumptable 000000018003E1C9 case 45
0x18003e228  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e22d  call    ?_InitToolbarButtons@CDocObjectHost@@IEAAXXZ; jumptable 000000018003E1C9 case 21
0x18003e232  mov     eax, 80004005h
0x18003e237  jmp     loc_18003F3D3
0x18003e23c  mov     eax, [r15+8]; jumptable 000000018003E1C9 case 25
0x18003e240  test    eax, eax
0x18003e242  jz      def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e248  imul    eax, 64h ; 'd'
0x18003e24b  cmp     [r14+2C0h], eax
0x18003e252  jz      def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e258  mov     [r14+2C0h], eax
0x18003e25f  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e264  mov     edx, [r15+8]; jumptable 000000018003E1C9 case 26
0x18003e268  test    edx, edx
0x18003e26a  jz      def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e270  mov     r8d, 4; unsigned int
0x18003e276  call    ?_OnSetProgressPos@CDocObjectHost@@IEAAXKK@Z; CDocObjectHost::_OnSetProgressPos(ulong,ulong)
0x18003e27b  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e280  mov     rdx, r15; jumptable 000000018003E1C9 case 27
0x18003e283  call    ?_OnSetStatusText@CDocObjectHost@@IEAAXPEBUtagVARIANT@@@Z; CDocObjectHost::_OnSetStatusText(tagVARIANT const *)
0x18003e288  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e28d  test    r15, r15; jumptable 000000018003E1C9 case 28
0x18003e290  jz      loc_18003EC86
0x18003e296  mov     rdx, r15; struct tagVARIANT *
0x18003e299  call    ?_OnSetTitle@CDocObjectHost@@IEAAXPEAUtagVARIANT@@@Z; CDocObjectHost::_OnSetTitle(tagVARIANT *)
0x18003e29e  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e2a3  mov     r8, r15; jumptable 000000018003E1C9 case 59
0x18003e2a6  mov     edx, r13d; unsigned int
0x18003e2a9  call    ?_ShowPageActionMenu@CDocObjectHost@@IEAAJKPEAUtagVARIANT@@@Z; CDocObjectHost::_ShowPageActionMenu(ulong,tagVARIANT *)
0x18003e2ae  jmp     loc_18003F3D3
0x18003e2b3  mov     rdx, r15; jumptable 000000018003E1C9 case 80
0x18003e2b6  call    ?_HandleFullScreenConsentCommand@CDocObjectHost@@IEAAJPEAUtagVARIANT@@@Z; CDocObjectHost::_HandleFullScreenConsentCommand(tagVARIANT *)
0x18003e2bb  jmp     loc_18003F3D3
0x18003e2c0  mov     rcx, [r14+148h]; jumptable 000000018003E1C9 case 34
0x18003e2c7  test    rcx, rcx
0x18003e2ca  jz      def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e2d0  mov     rax, [rcx]
0x18003e2d3  xor     esi, esi
0x18003e2d5  mov     rdx, [r14+120h]
0x18003e2dc  cmp     edi, 23h ; '#'
0x18003e2df  mov     r9, r15
0x18003e2e2  mov     [rsp+21D0h+var_21B0], r12
0x18003e2e7  setz    sil
0x18003e2eb  mov     rax, [rax+0F0h]
0x18003e2f2  mov     r8d, esi
0x18003e2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2fa  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e2ff  mov     rax, qword ptr cs:CGID_ShellDocView.Data1
0x18003e306  sub     rax, [rdx]
0x18003e309  jnz     short loc_18003E316
0x18003e30b  mov     rax, qword ptr cs:CGID_ShellDocView.Data4
0x18003e312  sub     rax, [rdx+8]
0x18003e316  test    rax, rax
0x18003e319  jnz     loc_18003ECB8
0x18003e31f  cmp     edi, 9
0x18003e322  jz      loc_18003EC90
0x18003e328  lea     eax, [r8-11h]; switch 164 cases
0x18003e32c  cmp     eax, 0A3h
0x18003e331  ja      def_18003E1C9; jumptable 000000018003E1C9 default case, cases 4-20,23,24,29-33,35-38,40-44,46-58,60-79
0x18003e337  lea     r8, __ImageBase
0x18003e33e  movzx   eax, ds:(byte_18003F500 - 180000000h)[r8+rax]
0x18003e347  mov     ecx, ds:(jpt_18003E352 - 180000000h)[r8+rax*4]
0x18003e34f  add     rcx, r8
0x18003e352  jmp     rcx; switch jump
0x18003e358  mov     r9d, 1; jumptable 000000018003E352 case 33
0x18003e35e  lea     rdx, [rbp+20D0h+Buffer]; unsigned __int16 *
0x18003e362  mov     r8d, 824h; unsigned int
0x18003e368  lea     rcx, [r14-48h]; this
0x18003e36c  call    ?_GetCurrentPage@CDocObjectHost@@IEAAJPEAGIH@Z; CDocObjectHost::_GetCurrentPage(ushort *,uint,int)
0x18003e371  test    eax, eax
0x18003e373  js      def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e379  mov     r8, [r14+7D8h]; unsigned __int16 *
0x18003e380  test    r8, r8
0x18003e383  jz      short loc_18003E39A
0x18003e385  cmp     word ptr [r8], 0
0x18003e38a  jz      short loc_18003E39A
0x18003e38c  mov     edx, 824h; unsigned __int64
0x18003e391  lea     rcx, [rbp+20D0h+Buffer]; unsigned __int16 *
0x18003e395  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003e39a  xor     esi, esi
0x18003e39c  lea     rcx, [rsp+21D0h+ulCookie]
0x18003e3a1  mov     [rsp+21D0h+ulCookie], rsi
0x18003e3a6  call    SHActivateContext
0x18003e3ab  lea     r8, [r14-48h]; struct EuppFirstRunSettings **
0x18003e3af  lea     rdx, [rbp+20D0h+Buffer]; struct DesktopEuppFirstRunUI *
0x18003e3b3  lea     rcx, [rsp+21D0h+pPrivacyEnum]; this
0x18003e3b8  call    ??0_lambda_ce15d259f53648a8c53bb735717135d9_@@QEAA@PEBVDesktopEuppFirstRunUI@@AEAPEBVEuppFirstRunSettings@@@Z; _lambda_ce15d259f53648a8c53bb735717135d9_::_lambda_ce15d259f53648a8c53bb735717135d9_(DesktopEuppFirstRunUI const *,EuppFirstRunSettings const * &)
0x18003e3bd  mov     rdx, rax
0x18003e3c0  call    DpiContextWrapper__lambda_8abd0502c25a106ae885053b1c1b3f2d___; DpiContextWrapper__lambda_8abd0502c25a106ae885053b1c1b3f2d_
0x18003e3c5  jmp     loc_18003E615
0x18003e3ca  mov     rcx, [r14+328h]; jumptable 000000018003E352 case 104
0x18003e3d1  lea     rdx, CGID_ShellDocView
0x18003e3d8  xor     eax, eax
0x18003e3da  xor     esi, esi
0x18003e3dc  mov     [rsp+21D0h+var_2170], rax
0x18003e3e1  xorps   xmm0, xmm0
0x18003e3e4  movups  xmmword ptr [rsp+21D0h+ulCookie], xmm0
0x18003e3e9  mov     eax, 0Dh
0x18003e3ee  mov     [rsp+21D0h+var_21A8], rsi
0x18003e3f3  mov     word ptr [rsp+21D0h+ulCookie], ax
0x18003e3f8  xor     r9d, r9d
0x18003e3fb  lea     rax, [rsp+21D0h+ulCookie]
0x18003e400  mov     [rsp+21D0h+ulCookie+8], rsi
0x18003e405  mov     r8d, 68h ; 'h'
0x18003e40b  mov     [rsp+21D0h+var_21B0], rax
0x18003e410  call    IUnknown_Exec
0x18003e415  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e41a  test    r15, r15; jumptable 000000018003E352 case 103
0x18003e41d  jz      loc_18003EC86
0x18003e423  cmp     word ptr [r15], 3
0x18003e428  jnz     loc_18003EC86
0x18003e42e  mov     edx, [r15+8]
0x18003e432  lea     rcx, [r14-48h]
0x18003e436  call    ?_OnSetPhishingFilterStatus@CDocObjectHost@@IEAAXW4tagNAVIGATION_BAND_PF_STATE@@@Z; CDocObjectHost::_OnSetPhishingFilterStatus(tagNAVIGATION_BAND_PF_STATE)
0x18003e43b  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e440  mov     [rsp+21D0h+var_21A8], r12; jumptable 000000018003E352 case 122
0x18003e445  mov     r8d, 7Ah ; 'z'
0x18003e44b  mov     [rsp+21D0h+var_21B0], r15
0x18003e450  xor     r9d, r9d
0x18003e453  lea     rdx, CGID_ShellDocView
0x18003e45a  mov     rcx, [r14+328h]
0x18003e461  call    IUnknown_Exec
0x18003e466  jmp     loc_18003F3D3
0x18003e46b  xor     esi, esi; jumptable 000000018003E352 case 123
0x18003e46d  mov     r8d, 7Bh ; '{'
0x18003e473  mov     [rsp+21D0h+var_21A8], rsi
0x18003e478  mov     [rsp+21D0h+var_21B0], rsi
0x18003e47d  jmp     short loc_18003E450
0x18003e47f  xor     r8d, r8d; jumptable 000000018003E352 case 35
0x18003e482  xor     edx, edx
0x18003e484  mov     ecx, 60000004h
0x18003e489  call    SHRestricted2W
0x18003e48e  test    eax, eax
0x18003e490  jnz     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e496  mov     rax, [r14+38h]
0x18003e49a  lea     rcx, [rsp+21D0h+hwnd]; HWND *
0x18003e49f  mov     edx, 1; unsigned int
0x18003e4a4  mov     [rsp+21D0h+hwnd], rax
0x18003e4a9  call    ?SuppressDialog@@YAJPEAPEAUHWND__@@K@Z; SuppressDialog(HWND__ * *,ulong)
0x18003e4ae  test    eax, eax
0x18003e4b0  js      def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e4b6  xor     r9d, r9d; int
0x18003e4b9  lea     rdx, [rbp+20D0h+var_10A0]; unsigned __int16 *
0x18003e4c0  mov     r8d, 824h; unsigned int
0x18003e4c6  lea     rcx, [r14-48h]; this
0x18003e4ca  call    ?_GetCurrentPage@CDocObjectHost@@IEAAJPEAGIH@Z; CDocObjectHost::_GetCurrentPage(ushort *,uint,int)
0x18003e4cf  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x18003e4d6  nop     dword ptr [rax+rax+00h]
0x18003e4db  test    eax, eax
0x18003e4dd  jnz     loc_18003E5EA
0x18003e4e3  mov     rcx, cs:g_hinstMUI; hInstance
0x18003e4ea  lea     r8, [rbp+20D0h+Buffer]; lpBuffer
0x18003e4ee  mov     r9d, 96h; cchBufferMax
0x18003e4f4  mov     edx, 2003h; uID
0x18003e4f9  call    cs:__imp_LoadStringW
0x18003e500  nop     dword ptr [rax+rax+00h]
0x18003e505  xorps   xmm0, xmm0
0x18003e508  lea     rcx, [rbp+20D0h+var_2130]
0x18003e50c  xorps   xmm1, xmm1
0x18003e50f  xor     esi, esi
0x18003e511  movdqu  [rbp+20D0h+var_2130], xmm0
0x18003e516  mov     [rbp+20D0h+var_2110], esi
0x18003e519  movdqu  [rbp+20D0h+var_2120], xmm1
0x18003e51e  mov     [rbp+20D0h+var_2108], rsi
0x18003e522  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x18003e527  mov     r10, [rsp+21D0h+hwnd]
0x18003e52c  mov     ebx, eax
0x18003e52e  test    r10, r10
0x18003e531  jz      short loc_18003E565
0x18003e533  mov     edx, 2; gaFlags
0x18003e538  mov     rcx, r10; hwnd
0x18003e53b  call    cs:__imp_GetAncestor
0x18003e542  nop     dword ptr [rax+rax+00h]
0x18003e547  mov     rsi, rax
0x18003e54a  test    rax, rax
0x18003e54d  jz      short loc_18003E560
0x18003e54f  xor     edx, edx; bEnable
0x18003e551  mov     rcx, rax; hWnd
0x18003e554  call    cs:__imp_EnableWindow
0x18003e55b  nop     dword ptr [rax+rax+00h]
0x18003e560  mov     r10, [rsp+21D0h+hwnd]
0x18003e565  test    ebx, ebx
0x18003e567  js      short loc_18003E5AA
0x18003e569  mov     rcx, qword ptr [rbp+20D0h+var_2120+8]
0x18003e56d  lea     r9, [rbp+20D0h+Buffer]
0x18003e571  lea     r8, [rbp+20D0h+var_10A0]
0x18003e578  mov     rdx, r10
0x18003e57b  mov     rax, [rcx]
0x18003e57e  mov     rax, [rax+68h]
0x18003e582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e587  test    eax, eax
0x18003e589  js      short loc_18003E5AA
0x18003e58b  xor     edx, edx
0x18003e58d  lea     rcx, [rbp+20D0h+var_2130]
0x18003e591  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x18003e596  test    eax, eax
0x18003e598  js      short loc_18003E5AA
0x18003e59a  mov     rcx, qword ptr [rbp+20D0h+var_2120+8]
0x18003e59e  mov     rax, [rcx]
0x18003e5a1  mov     rax, [rax+70h]
0x18003e5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5aa  test    rsi, rsi
0x18003e5ad  jz      short loc_18003E5C3
0x18003e5af  mov     edx, 1; bEnable
0x18003e5b4  mov     rcx, rsi; hWnd
0x18003e5b7  call    cs:__imp_EnableWindow
0x18003e5be  nop     dword ptr [rax+rax+00h]
0x18003e5c3  lea     rcx, [rbp+20D0h+var_2130]
0x18003e5c7  call    ??1?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAA@XZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(void)
0x18003e5cc  xor     r9d, r9d; dwBufferLength
0x18003e5cf  xor     r8d, r8d; lpBuffer
0x18003e5d2  mov     edx, 27h ; '''; dwOption
0x18003e5d7  xor     ecx, ecx; hInternet
0x18003e5d9  call    cs:__imp_InternetSetOptionW
0x18003e5e0  nop     dword ptr [rax+rax+00h]
0x18003e5e5  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e5ea  cmp     eax, 1
0x18003e5ed  jnz     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e5f3  xor     esi, esi
0x18003e5f5  lea     rcx, [rsp+21D0h+ulCookie]
0x18003e5fa  mov     [rsp+21D0h+ulCookie], rsi
0x18003e5ff  call    SHActivateContext
0x18003e604  mov     rcx, [rsp+21D0h+hwnd]
0x18003e609  lea     rdx, [rbp+20D0h+var_10A0]
0x18003e610  call    IEZoneConfigureW
0x18003e615  mov     rdx, [rsp+21D0h+ulCookie]; ulCookie
0x18003e61a  test    rdx, rdx
0x18003e61d  jz      def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e623  xor     ecx, ecx; dwFlags
0x18003e625  call    cs:__imp_DeactivateActCtx
0x18003e62c  nop     dword ptr [rax+rax+00h]
0x18003e631  jmp     def_18003F366; jumptable 000000018003E352 cases 30,60
0x18003e636  mov     rcx, [r14+318h]; jumptable 000000018003E352 case 74
0x18003e63d  xor     esi, esi
0x18003e63f  cmp     r13d, 1
0x18003e643  mov     qword ptr [rsp+21D0h+pPrivacyEnum], rsi
0x18003e648  mov     ebx, esi
0x18003e64a  mov     [rsp+21D0h+ulCookie], rsi
0x18003e64f  setz    bl
0x18003e652  test    rcx, rcx
0x18003e655  jz      short loc_18003E67E
0x18003e657  mov     rax, [rcx]
0x18003e65a  lea     r9, [rsp+21D0h+ulCookie]
0x18003e65f  mov     rdx, [r14+320h]
0x18003e666  xor     r8d, r8d
  ... truncated ...
```
