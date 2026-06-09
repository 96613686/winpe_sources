# CDocObjectHost::OnExec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x18003c150`
- end: `0x18003d6c9`
- name: `?OnExec@CDocObjectHost@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `5497`
- prototype: `__int64 __fastcall(CDocObjectHost *this, const struct _GUID *, unsigned int, __int64, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `64`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x180011230`
- `0x180012140`
- `0x180015150`
- `0x18001ba58`
- `0x1800231c4`
- `0x1800396ec`
- `0x18003c150`
- `0x18004a080`
- `0x1800567e4`
- `0x18006ac58`
- `0x18006f6d4`
- `0x18006ff5c`
- `0x180073354`
- `0x180075598`
- `0x180075640`
- `0x1800766c8`
- `0x180078fc0`
- `0x18007ded4`
- `0x1800800e0`
- `0x180092e68`
- `0x180092ee8`
- `0x180095b40`
- `0x1800a14b0`
- `0x1800c06ac`
- `0x1800c5d04`
- `0x1800c5df0`
- `0x1800c6168`
- `0x1800c87e8`
- `0x1800cbef4`
- `0x1800d4ac4`
- `0x1800f9670`
- `0x1800fe1f0`
- `0x180116f00`
- `0x180132898`
- `0x180133c9c`
- `0x1801393a4`
- `0x18013995c`
- `0x18013a9c4`
- `0x18013ca9c`
- `0x18013d35c`
- `0x18013f1fc`
- `0x18013f684`
- `0x18013f710`
- `0x180141680`
- `0x180141934`
- `0x180141be8`
- `0x180141e40`
- `0x180141ff0`
- `0x1801420a8`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18003c91a`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18003c91a`
- `KERNEL32!DeactivateActCtx` at `0x18003c619`
- `KERNEL32!DeactivateActCtx` at `0x18003c619`
- `KERNEL32!LocalFree` at `0x18003cc1a`
- `KERNEL32!LocalFree` at `0x18003cc1a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18003c50b`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18003c50b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18003ca28`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18003cbf1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18003ca28`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18003cbf1`
- `USER32!PostMessageW` at `0x18003cbbc`
- `USER32!PostMessageW` at `0x18003cbd6`
- `USER32!PostMessageW` at `0x18003cc09`
- `USER32!PostMessageW` at `0x18003cbbc`
- `USER32!PostMessageW` at `0x18003cbd6`
- `USER32!PostMessageW` at `0x18003cc09`
- `USER32!GetSystemMetrics` at `0x18003d1b6`
- `USER32!GetSystemMetrics` at `0x18003d1b6`
- `USER32!EnableWindow` at `0x18003c55a`
- `USER32!EnableWindow` at `0x18003c5b7`
- `USER32!EnableWindow` at `0x18003c55a`
- `USER32!EnableWindow` at `0x18003c5b7`
- `USER32!GetAncestor` at `0x18003c547`
- `USER32!GetAncestor` at `0x18003c547`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003ca88`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003cb3a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003ca88`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003cb3a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003caa4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003cb5f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003caa4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003cb5f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003cac5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003cb7a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003cac5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003cb7a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003cb0a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003cba0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003cb0a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003cba0`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18003c4e7`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18003c4e7`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003cd98`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18003cd98`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003c6fa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003d0a9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003c6fa`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18003d0a9`
- `WININET!InternetSetOptionW` at `0x18003c5d3`
- `WININET!InternetSetOptionW` at `0x18003c5d3`

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
  PWSTR v48; // rbx
  __int64 v49; // rax
  CDocObjectHost *v50; // rcx
  unsigned int v51; // edx
  int v52; // eax
  __int64 v53; // rax
  __int64 (__fastcall ***v54)(_QWORD, GUID *, _OWORD *); // rcx
  int v55; // esi
  __int64 v56; // rcx
  struct _GUID *v57; // rax
  __int64 v58; // rcx
  unsigned int v59; // esi
  __int64 v60; // rdx
  const unsigned __int16 *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rdx
  _WORD *v64; // rcx
  int UrlSchemeW; // eax
  __int64 v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rcx
  BSTR bstrVal; // rbx
  int v72; // eax
  unsigned int v73; // edi
  unsigned int v74; // edi
  __int64 v75; // rcx
  __int64 v76; // r8
  __int64 v77; // r9
  __int64 v78; // rcx
  struct tagVARIANT *v79; // [rsp+20h] [rbp-E0h]
  _OWORD *v80; // [rsp+20h] [rbp-E0h]
  struct tagVARIANT *v81; // [rsp+28h] [rbp-D8h]
  bool v82; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD ulCookie[2]; // [rsp+50h] [rbp-B0h] BYREF
  HWND hwnd; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID pPrivacyEnum; // [rsp+78h] [rbp-88h] BYREF
  __int16 v86; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v87; // [rsp+90h] [rbp-70h]
  char v88; // [rsp+98h] [rbp-68h]
  int v89; // [rsp+9Ch] [rbp-64h]
  __int128 v90; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v91; // [rsp+B0h] [rbp-50h]
  int v92; // [rsp+C0h] [rbp-40h]
  __int64 v93; // [rsp+C8h] [rbp-38h]
  WCHAR Buffer[2088]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v95[2088]; // [rsp+1130h] [rbp+1030h] BYREF

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
              goto LABEL_147;
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
        CDocObjectHost::_GetCurrentPage((CDocObjectHost *)((char *)this - 72), v95, 0x824u, 0);
        v22 = IsProtectedModeProcess();
        if ( v22 )
        {
          if ( v22 == 1 )
          {
            *(_QWORD *)&ulCookie[0] = 0;
            SHActivateContext(ulCookie);
            IEZoneConfigureW(hwnd, v95);
LABEL_60:
            if ( *(_QWORD *)&ulCookie[0] )
              DeactivateActCtx(0, *(ULONG_PTR *)&ulCookie[0]);
          }
        }
        else
        {
          LoadStringW(g_hinstMUI, 0x2003u, Buffer, 150);
          v23 = 0;
          v90 = 0;
          v92 = 0;
          v91 = 0;
          v93 = 0;
          v24 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(&v90);
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
            && (*(int (__fastcall **)(_QWORD, HWND, unsigned __int16 *, WCHAR *))(**((_QWORD **)&v91 + 1) + 104LL))(
                 *((_QWORD *)&v91 + 1),
                 v25,
                 v95,
                 Buffer) >= 0
            && (int)CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                      &v90,
                      0) >= 0 )
          {
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v91 + 1) + 112LL))(*((_QWORD *)&v91 + 1));
          }
          if ( v23 )
            EnableWindow(v23, 1);
          CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(&v90);
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
        v81 = a6;
        v79 = a5;
        return IUnknown_Exec(*((_QWORD *)this + 101), (_DWORD)a2, a3, a4, (__int64)v79, (__int64)v81);
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
          goto LABEL_147;
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
          goto LABEL_147;
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
        v81 = a6;
        a3 = 122;
        v79 = a5;
        goto LABEL_41;
      case 0x7Bu:
        a3 = 123;
        v81 = 0;
        v79 = 0;
LABEL_41:
        LODWORD(a4) = 0;
        a2 = &CGID_ShellDocView;
        return IUnknown_Exec(*((_QWORD *)this + 101), (_DWORD)a2, a3, a4, (__int64)v79, (__int64)v81);
      case 0x88u:
        if ( !a6 || a6->vt != 3 )
          goto LABEL_147;
        a6->lVal = TLSGetTabId();
        return 0;
      case 0x93u:
        if ( !a5 || a5->vt != 8 )
          goto LABEL_147;
        v41 = StrDupW(a5->bstrVal);
        v42 = 33838;
        goto LABEL_145;
      case 0x96u:
        if ( !a5 || a5->vt != 8 )
          goto LABEL_147;
        v41 = StrDupW(a5->bstrVal);
        v42 = 33859;
LABEL_145:
        v48 = v41;
        if ( !PostMessageW(*((HWND *)this + 7), v42, 0, (LPARAM)v41) )
          LocalFree(v48);
        return 0;
      case 0x99u:
        PostMessageW(*((HWND *)this + 7), 0x844Du, 0, 0);
        return 0;
      case 0x9Au:
        PostMessageW(*((HWND *)this + 7), 0x844Fu, 0, 0);
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
          goto LABEL_147;
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
LABEL_147:
        result = 2147942487LL;
        break;
      default:
        return 2147746048LL;
    }
    return result;
  }
  v49 = *(_QWORD *)&CGID_Explorer.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&CGID_Explorer.Data1 == *(_QWORD *)&a2->Data1 )
    v49 = *(_QWORD *)CGID_Explorer.Data4 - *(_QWORD *)a2->Data4;
  if ( !v49 )
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
        v50 = (CDocObjectHost *)((char *)this - 72);
        v51 = -1610612736;
        v52 = *((_DWORD *)this + 338);
        if ( (v52 & 0x2040202) == 0 )
          v51 = 0x80000000;
        CDocObjectHost::_HandlePageActionBlocked(v50, v52 | v51, a5);
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
  v53 = *(_QWORD *)&CGID_DocHostCommandHandler.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&CGID_DocHostCommandHandler.Data1 == *(_QWORD *)&a2->Data1 )
    v53 = *(_QWORD *)CGID_DocHostCommandHandler.Data4 - *(_QWORD *)a2->Data4;
  if ( v53 )
  {
    v67 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_InternetButtons.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_InternetButtons.Data1 )
      v67 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_InternetButtons.Data4;
    if ( !v67 )
      goto LABEL_232;
    v68 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_MSOButtons.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_MSOButtons.Data1 )
      v68 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_MSOButtons.Data4;
    if ( !v68 )
    {
LABEL_232:
      if ( (_DWORD)a4 == 1 )
      {
        if ( *((_QWORD *)this + 40) && a5 && a5->vt == 37 )
        {
          bstrVal = a5->bstrVal;
          LOWORD(ulCookie[0]) = 3;
          memset((char *)ulCookie + 2, 0, 22);
          if ( GetSystemMetrics(40) )
            v72 = bstrVal[4];
          else
            v72 = *bstrVal;
          DWORD2(ulCookie[0]) = v72 | (bstrVal[6] << 16);
          v73 = v7 - 369;
          if ( v73 )
          {
            v74 = v73 - 1;
            if ( v74 )
            {
              if ( v74 == 3 )
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
            v75 = *((_QWORD *)this + 40);
            v76 = 12;
            v77 = 0;
            v80 = ulCookie;
LABEL_250:
            (*(void (__fastcall **)(__int64, const GUID *, __int64, __int64, _OWORD *, _QWORD))(*(_QWORD *)v75 + 32LL))(
              v75,
              &CGID_Explorer,
              v76,
              v77,
              v80,
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
            v75 = *((_QWORD *)this + 40);
            if ( v75 )
            {
              v77 = 2;
              v76 = 47;
              v80 = 0;
              goto LABEL_250;
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
        v78 = *((_QWORD *)this + 39);
        v87 = a3;
        v86 = 3;
        IUnknown_Exec(v78, (unsigned int)&CGID_Explorer, 79, 0, (__int64)&v86, 0);
        ATL::CComVariant::Clear((ATL::CComVariant *)&v86);
      }
      return 0;
    }
    v69 = *(_QWORD *)&CGID_InternetExplorer.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CGID_InternetExplorer.Data1 == *(_QWORD *)&a2->Data1 )
      v69 = *(_QWORD *)CGID_InternetExplorer.Data4 - *(_QWORD *)a2->Data4;
    if ( v69 )
      return 2147746052LL;
    if ( a3 == 2 || a3 == 3 || a3 == 4 || a3 - 5 < 2 )
    {
      v70 = *((_QWORD *)this + 40);
      if ( v70 )
        return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v70 + 32LL))(v70);
      return 2147500037LL;
    }
    return 2147746048LL;
  }
  if ( a3 > 0x8FC )
  {
    if ( a3 == 6041 || a3 == 6042 || a3 - 6043 <= 1 )
      goto LABEL_199;
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
        goto LABEL_191;
      case 0x28u:
        if ( (*((_DWORD *)this + 144) & 0x40000) != 0 )
        {
          v54 = (__int64 (__fastcall ***)(_QWORD, GUID *, _OWORD *))*((_QWORD *)this + 48);
          if ( v54 )
          {
            *(_QWORD *)&ulCookie[0] = 0;
            v55 = (**v54)(v54, &GUID_b722bccb_4e68_101b_a2bc_00aa00404770, ulCookie);
            if ( v55 >= 0 )
            {
              v55 = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, struct tagVARIANT *))(**(_QWORD **)&ulCookie[0] + 32LL))(
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
            v56 = *((_QWORD *)this + 35);
            if ( v56 )
              return (unsigned int)(*(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD))(*(_QWORD *)(v56 + 24) + 32LL))(
                                     v56 + 24,
                                     a2,
                                     a3);
            else
              return (unsigned int)-2147467259;
          }
        }
        else
        {
          v55 = 0;
          a6->vt = 11;
          a6->iVal = -1;
        }
        return (unsigned int)v55;
      case 0x2Au:
        v82 = 0;
        CLayerParticipant::LayerGetBool((CDocObjectHost *)((char *)this + 88), &v82, 69722, 0);
        if ( v82 )
          return 0;
        goto LABEL_189;
      case 0x2Cu:
LABEL_189:
        if ( v7 == 44 )
        {
          v57 = CreateUserInputId(&pPrivacyEnum);
          v88 = 0;
          ulCookie[0] = *v57;
          ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)&v86, (struct _GUID *)ulCookie);
          BrowserTelemetry::IEPrintCommandInvoked();
          v89 = 3;
          ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&v86);
        }
LABEL_191:
        v58 = *((_QWORD *)this + 35);
        if ( v58 )
          v59 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, _QWORD, _QWORD, struct tagVARIANT *, struct tagVARIANT *))(*(_QWORD *)(v58 + 24) + 32LL))(
                  v58 + 24,
                  v8,
                  v7,
                  v6,
                  a5,
                  a6);
        else
          v59 = -2147467259;
        result = v59;
        break;
      case 0x39u:
        result = CDocObjectHost::FocusViewControls((CDocObjectHost *)((char *)this - 72), 0);
        break;
      default:
        return 2147746048LL;
    }
    return result;
  }
LABEL_199:
  v60 = 0;
  if ( a5 && a5->vt == 3 && (a5->lVal & 0x80000) != 0 )
    v60 = 4;
  (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 8) + 64LL))((char *)this + 64, v60);
  v61 = (const unsigned __int16 *)*((_QWORD *)this + 70);
  if ( v61 )
  {
    *((_DWORD *)this + 144) |= 0x800000u;
    CDocObjectHost::_DoAsyncNavigation((CDocObjectHost *)((char *)this - 72), v61);
    return 0;
  }
  v62 = *((_QWORD *)this + 99);
  UBound = -2147221248;
  if ( !v62 )
    return UBound;
  v63 = *((_QWORD *)this + 100);
  *(_QWORD *)&ulCookie[0] = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, _OWORD *))(*(_QWORD *)v62 + 160LL))(v62, v63, 0, ulCookie) < 0 )
    return UBound;
  if ( (unsigned int)IsErrorUrl(*(_QWORD *)&ulCookie[0]) )
  {
    v64 = (_WORD *)*((_QWORD *)this + 68);
    if ( v64 )
    {
      if ( *v64 )
      {
        UrlSchemeW = GetUrlSchemeW(v64 + 1);
        if ( (unsigned int)(UrlSchemeW - 1) <= 2 || UrlSchemeW == 11 )
        {
          v66 = *((_QWORD *)this + 68);
          *((_DWORD *)this + 144) |= 0x800000u;
          CDocObjectHost::_DoAsyncNavigation((CDocObjectHost *)((char *)this - 72), (const unsigned __int16 *)(v66 + 2));
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
0x18003c150  push    rbp
0x18003c152  push    rbx
0x18003c153  push    rsi
0x18003c154  push    rdi
0x18003c155  push    r12
0x18003c157  push    r13
0x18003c159  push    r14
0x18003c15b  push    r15
0x18003c15d  lea     rbp, [rsp-2098h]
0x18003c165  mov     eax, 2198h
0x18003c16a  call    _alloca_probe
0x18003c16f  sub     rsp, rax
0x18003c172  mov     rax, cs:__security_cookie
0x18003c179  xor     rax, rsp
0x18003c17c  mov     [rbp+20D0h+var_50], rax
0x18003c183  mov     r12, [rbp+20D0h+arg_28]
0x18003c18a  mov     r13d, r9d
0x18003c18d  mov     r15, [rbp+20D0h+arg_20]
0x18003c194  mov     edi, r8d
0x18003c197  mov     rbx, rdx
0x18003c19a  mov     r14, rcx
0x18003c19d  test    rdx, rdx
0x18003c1a0  jnz     loc_18003C31B
0x18003c1a6  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x18003c1aa  cmp     [rcx+180h], rdx
0x18003c1b1  jz      loc_18003C24E
0x18003c1b7  cmp     r8d, 23h ; '#'
0x18003c1bb  jz      loc_18003C2DC; jumptable 000000018003C1E9 case 34
0x18003c1c1  lea     eax, [r8-1]; switch 80 cases
0x18003c1c5  cmp     eax, 4Fh
0x18003c1c8  ja      def_18003C1E9; jumptable 000000018003C1E9 default case, cases 4-20,23,24,29-33,35-38,40-44,46-58,60-79
0x18003c1ce  lea     r8, __ImageBase
0x18003c1d5  movzx   eax, ds:(byte_18003D3B4 - 180000000h)[r8+rax]
0x18003c1de  mov     edx, ds:(jpt_18003C1E9 - 180000000h)[r8+rax*4]
0x18003c1e6  add     rdx, r8
0x18003c1e9  jmp     rdx; switch jump
0x18003c1eb  xor     edx, edx; jumptable 000000018003C1E9 case 39
0x18003c1ed  mov     r8d, 1; unsigned int
0x18003c1f3  call    ?_OnSetProgressPos@CDocObjectHost@@IEAAXKK@Z; CDocObjectHost::_OnSetProgressPos(ulong,ulong)
0x18003c1f8  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c1fd  mov     rcx, [r14+370h]; jumptable 000000018003C1E9 case 22
0x18003c204  test    rcx, rcx
0x18003c207  jz      def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c20d  mov     [rsp+21D0h+var_21A8], r12
0x18003c212  mov     r8d, edi
0x18003c215  mov     [rsp+21D0h+var_21B0], r15
0x18003c21a  xor     edx, edx
0x18003c21c  jmp     loc_18003D318
0x18003c221  mov     eax, 80004001h; jumptable 000000018003C1E9 case 2
0x18003c226  jmp     loc_18003D354
0x18003c22b  call    ?_OnOpen@CDocObjectHost@@IEAAXXZ; jumptable 000000018003C1E9 case 1
0x18003c230  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c235  call    ?_OnSave@CDocObjectHost@@IEAAXXZ; jumptable 000000018003C1E9 case 3
0x18003c23a  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c23f  call    ?_OnClose@CDocObjectHost@@IEBAXXZ; jumptable 000000018003C1E9 case 45
0x18003c244  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c249  call    ?_InitToolbarButtons@CDocObjectHost@@IEAAXXZ; jumptable 000000018003C1E9 case 21
0x18003c24e  mov     eax, 80004005h
0x18003c253  jmp     loc_18003D354
0x18003c258  mov     eax, [r15+8]; jumptable 000000018003C1E9 case 25
0x18003c25c  test    eax, eax
0x18003c25e  jz      def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c264  imul    eax, 64h ; 'd'
0x18003c267  cmp     [r14+2C0h], eax
0x18003c26e  jz      def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c274  mov     [r14+2C0h], eax
0x18003c27b  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c280  mov     edx, [r15+8]; jumptable 000000018003C1E9 case 26
0x18003c284  test    edx, edx
0x18003c286  jz      def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c28c  mov     r8d, 4; unsigned int
0x18003c292  call    ?_OnSetProgressPos@CDocObjectHost@@IEAAXKK@Z; CDocObjectHost::_OnSetProgressPos(ulong,ulong)
0x18003c297  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c29c  mov     rdx, r15; jumptable 000000018003C1E9 case 27
0x18003c29f  call    ?_OnSetStatusText@CDocObjectHost@@IEAAXPEBUtagVARIANT@@@Z; CDocObjectHost::_OnSetStatusText(tagVARIANT const *)
0x18003c2a4  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c2a9  test    r15, r15; jumptable 000000018003C1E9 case 28
0x18003c2ac  jz      loc_18003CC25
0x18003c2b2  mov     rdx, r15; struct tagVARIANT *
0x18003c2b5  call    ?_OnSetTitle@CDocObjectHost@@IEAAXPEAUtagVARIANT@@@Z; CDocObjectHost::_OnSetTitle(tagVARIANT *)
0x18003c2ba  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c2bf  mov     r8, r15; jumptable 000000018003C1E9 case 59
0x18003c2c2  mov     edx, r13d; unsigned int
0x18003c2c5  call    ?_ShowPageActionMenu@CDocObjectHost@@IEAAJKPEAUtagVARIANT@@@Z; CDocObjectHost::_ShowPageActionMenu(ulong,tagVARIANT *)
0x18003c2ca  jmp     loc_18003D354
0x18003c2cf  mov     rdx, r15; jumptable 000000018003C1E9 case 80
0x18003c2d2  call    ?_HandleFullScreenConsentCommand@CDocObjectHost@@IEAAJPEAUtagVARIANT@@@Z; CDocObjectHost::_HandleFullScreenConsentCommand(tagVARIANT *)
0x18003c2d7  jmp     loc_18003D354
0x18003c2dc  mov     rcx, [r14+148h]; jumptable 000000018003C1E9 case 34
0x18003c2e3  test    rcx, rcx
0x18003c2e6  jz      def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c2ec  mov     rax, [rcx]
0x18003c2ef  xor     esi, esi
0x18003c2f1  mov     rdx, [r14+120h]
0x18003c2f8  cmp     edi, 23h ; '#'
0x18003c2fb  mov     r9, r15
0x18003c2fe  mov     [rsp+21D0h+var_21B0], r12
0x18003c303  setz    sil
0x18003c307  mov     rax, [rax+0F0h]
0x18003c30e  mov     r8d, esi
0x18003c311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c316  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c31b  mov     rax, qword ptr cs:CGID_ShellDocView.Data1
0x18003c322  sub     rax, [rdx]
0x18003c325  jnz     short loc_18003C332
0x18003c327  mov     rax, qword ptr cs:CGID_ShellDocView.Data4
0x18003c32e  sub     rax, [rdx+8]
0x18003c332  test    rax, rax
0x18003c335  jnz     loc_18003CC57
0x18003c33b  cmp     edi, 9
0x18003c33e  jz      loc_18003CC2F
0x18003c344  lea     eax, [r8-11h]; switch 164 cases
0x18003c348  cmp     eax, 0A3h
0x18003c34d  ja      def_18003C1E9; jumptable 000000018003C1E9 default case, cases 4-20,23,24,29-33,35-38,40-44,46-58,60-79
0x18003c353  lea     r8, __ImageBase
0x18003c35a  movzx   eax, ds:(byte_18003D480 - 180000000h)[r8+rax]
0x18003c363  mov     ecx, ds:(jpt_18003C36E - 180000000h)[r8+rax*4]
0x18003c36b  add     rcx, r8
0x18003c36e  jmp     rcx; switch jump
0x18003c370  mov     r9d, 1; jumptable 000000018003C36E case 33
0x18003c376  lea     rdx, [rbp+20D0h+Buffer]; unsigned __int16 *
0x18003c37a  mov     r8d, 824h; unsigned int
0x18003c380  lea     rcx, [r14-48h]; this
0x18003c384  call    ?_GetCurrentPage@CDocObjectHost@@IEAAJPEAGIH@Z; CDocObjectHost::_GetCurrentPage(ushort *,uint,int)
0x18003c389  test    eax, eax
0x18003c38b  js      def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c391  mov     r8, [r14+7D8h]; unsigned __int16 *
0x18003c398  test    r8, r8
0x18003c39b  jz      short loc_18003C3B2
0x18003c39d  cmp     word ptr [r8], 0
0x18003c3a2  jz      short loc_18003C3B2
0x18003c3a4  mov     edx, 824h; unsigned __int64
0x18003c3a9  lea     rcx, [rbp+20D0h+Buffer]; unsigned __int16 *
0x18003c3ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003c3b2  xor     esi, esi
0x18003c3b4  lea     rcx, [rsp+21D0h+ulCookie]
0x18003c3b9  mov     [rsp+21D0h+ulCookie], rsi
0x18003c3be  call    SHActivateContext
0x18003c3c3  lea     r8, [r14-48h]; struct EuppFirstRunSettings **
0x18003c3c7  lea     rdx, [rbp+20D0h+Buffer]; struct DesktopEuppFirstRunUI *
0x18003c3cb  lea     rcx, [rsp+21D0h+pPrivacyEnum]; this
0x18003c3d0  call    ??0_lambda_ce15d259f53648a8c53bb735717135d9_@@QEAA@PEBVDesktopEuppFirstRunUI@@AEAPEBVEuppFirstRunSettings@@@Z; _lambda_ce15d259f53648a8c53bb735717135d9_::_lambda_ce15d259f53648a8c53bb735717135d9_(DesktopEuppFirstRunUI const *,EuppFirstRunSettings const * &)
0x18003c3d5  mov     rdx, rax
0x18003c3d8  call    DpiContextWrapper__lambda_8abd0502c25a106ae885053b1c1b3f2d___; DpiContextWrapper__lambda_8abd0502c25a106ae885053b1c1b3f2d_
0x18003c3dd  jmp     loc_18003C609
0x18003c3e2  mov     rcx, [r14+328h]; jumptable 000000018003C36E case 104
0x18003c3e9  lea     rdx, CGID_ShellDocView
0x18003c3f0  xor     eax, eax
0x18003c3f2  xor     esi, esi
0x18003c3f4  mov     [rsp+21D0h+var_2170], rax
0x18003c3f9  xorps   xmm0, xmm0
0x18003c3fc  movups  xmmword ptr [rsp+21D0h+ulCookie], xmm0
0x18003c401  mov     eax, 0Dh
0x18003c406  mov     [rsp+21D0h+var_21A8], rsi
0x18003c40b  mov     word ptr [rsp+21D0h+ulCookie], ax
0x18003c410  xor     r9d, r9d
0x18003c413  lea     rax, [rsp+21D0h+ulCookie]
0x18003c418  mov     [rsp+21D0h+ulCookie+8], rsi
0x18003c41d  mov     r8d, 68h ; 'h'
0x18003c423  mov     [rsp+21D0h+var_21B0], rax
0x18003c428  call    IUnknown_Exec
0x18003c42d  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c432  test    r15, r15; jumptable 000000018003C36E case 103
0x18003c435  jz      loc_18003CC25
0x18003c43b  cmp     word ptr [r15], 3
0x18003c440  jnz     loc_18003CC25
0x18003c446  mov     edx, [r15+8]
0x18003c44a  lea     rcx, [r14-48h]
0x18003c44e  call    ?_OnSetPhishingFilterStatus@CDocObjectHost@@IEAAXW4tagNAVIGATION_BAND_PF_STATE@@@Z; CDocObjectHost::_OnSetPhishingFilterStatus(tagNAVIGATION_BAND_PF_STATE)
0x18003c453  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c458  mov     [rsp+21D0h+var_21A8], r12; jumptable 000000018003C36E case 122
0x18003c45d  mov     r8d, 7Ah ; 'z'
0x18003c463  mov     [rsp+21D0h+var_21B0], r15
0x18003c468  xor     r9d, r9d
0x18003c46b  lea     rdx, CGID_ShellDocView
0x18003c472  mov     rcx, [r14+328h]
0x18003c479  call    IUnknown_Exec
0x18003c47e  jmp     loc_18003D354
0x18003c483  xor     esi, esi; jumptable 000000018003C36E case 123
0x18003c485  mov     r8d, 7Bh ; '{'
0x18003c48b  mov     [rsp+21D0h+var_21A8], rsi
0x18003c490  mov     [rsp+21D0h+var_21B0], rsi
0x18003c495  jmp     short loc_18003C468
0x18003c497  xor     r8d, r8d; jumptable 000000018003C36E case 35
0x18003c49a  xor     edx, edx
0x18003c49c  mov     ecx, 60000004h
0x18003c4a1  call    SHRestricted2W
0x18003c4a6  test    eax, eax
0x18003c4a8  jnz     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c4ae  mov     rax, [r14+38h]
0x18003c4b2  lea     rcx, [rsp+21D0h+hwnd]; HWND *
0x18003c4b7  mov     edx, 1; unsigned int
0x18003c4bc  mov     [rsp+21D0h+hwnd], rax
0x18003c4c1  call    ?SuppressDialog@@YAJPEAPEAUHWND__@@K@Z; SuppressDialog(HWND__ * *,ulong)
0x18003c4c6  test    eax, eax
0x18003c4c8  js      def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c4ce  xor     r9d, r9d; int
0x18003c4d1  lea     rdx, [rbp+20D0h+var_10A0]; unsigned __int16 *
0x18003c4d8  mov     r8d, 824h; unsigned int
0x18003c4de  lea     rcx, [r14-48h]; this
0x18003c4e2  call    ?_GetCurrentPage@CDocObjectHost@@IEAAJPEAGIH@Z; CDocObjectHost::_GetCurrentPage(ushort *,uint,int)
0x18003c4e7  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x18003c4ed  test    eax, eax
0x18003c4ef  jnz     loc_18003C5DE
0x18003c4f5  mov     rcx, cs:g_hinstMUI; hInstance
0x18003c4fc  lea     r8, [rbp+20D0h+Buffer]; lpBuffer
0x18003c500  mov     r9d, 96h; cchBufferMax
0x18003c506  mov     edx, 2003h; uID
0x18003c50b  call    cs:__imp_LoadStringW
0x18003c511  xorps   xmm0, xmm0
0x18003c514  lea     rcx, [rbp+20D0h+var_2130]
0x18003c518  xorps   xmm1, xmm1
0x18003c51b  xor     esi, esi
0x18003c51d  movdqu  [rbp+20D0h+var_2130], xmm0
0x18003c522  mov     [rbp+20D0h+var_2110], esi
0x18003c525  movdqu  [rbp+20D0h+var_2120], xmm1
0x18003c52a  mov     [rbp+20D0h+var_2108], rsi
0x18003c52e  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x18003c533  mov     r10, [rsp+21D0h+hwnd]
0x18003c538  mov     ebx, eax
0x18003c53a  test    r10, r10
0x18003c53d  jz      short loc_18003C565
0x18003c53f  mov     edx, 2; gaFlags
0x18003c544  mov     rcx, r10; hwnd
0x18003c547  call    cs:__imp_GetAncestor
0x18003c54d  mov     rsi, rax
0x18003c550  test    rax, rax
0x18003c553  jz      short loc_18003C560
0x18003c555  xor     edx, edx; bEnable
0x18003c557  mov     rcx, rax; hWnd
0x18003c55a  call    cs:__imp_EnableWindow
0x18003c560  mov     r10, [rsp+21D0h+hwnd]
0x18003c565  test    ebx, ebx
0x18003c567  js      short loc_18003C5AA
0x18003c569  mov     rcx, qword ptr [rbp+20D0h+var_2120+8]
0x18003c56d  lea     r9, [rbp+20D0h+Buffer]
0x18003c571  lea     r8, [rbp+20D0h+var_10A0]
0x18003c578  mov     rdx, r10
0x18003c57b  mov     rax, [rcx]
0x18003c57e  mov     rax, [rax+68h]
0x18003c582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c587  test    eax, eax
0x18003c589  js      short loc_18003C5AA
0x18003c58b  xor     edx, edx
0x18003c58d  lea     rcx, [rbp+20D0h+var_2130]
0x18003c591  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x18003c596  test    eax, eax
0x18003c598  js      short loc_18003C5AA
0x18003c59a  mov     rcx, qword ptr [rbp+20D0h+var_2120+8]
0x18003c59e  mov     rax, [rcx]
0x18003c5a1  mov     rax, [rax+70h]
0x18003c5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5aa  test    rsi, rsi
0x18003c5ad  jz      short loc_18003C5BD
0x18003c5af  mov     edx, 1; bEnable
0x18003c5b4  mov     rcx, rsi; hWnd
0x18003c5b7  call    cs:__imp_EnableWindow
0x18003c5bd  lea     rcx, [rbp+20D0h+var_2130]
0x18003c5c1  call    ??1?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAA@XZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(void)
0x18003c5c6  xor     r9d, r9d; dwBufferLength
0x18003c5c9  xor     r8d, r8d; lpBuffer
0x18003c5cc  mov     edx, 27h ; '''; dwOption
0x18003c5d1  xor     ecx, ecx; hInternet
0x18003c5d3  call    cs:__imp_InternetSetOptionW
0x18003c5d9  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c5de  cmp     eax, 1
0x18003c5e1  jnz     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c5e7  xor     esi, esi
0x18003c5e9  lea     rcx, [rsp+21D0h+ulCookie]
0x18003c5ee  mov     [rsp+21D0h+ulCookie], rsi
0x18003c5f3  call    SHActivateContext
0x18003c5f8  mov     rcx, [rsp+21D0h+hwnd]
0x18003c5fd  lea     rdx, [rbp+20D0h+var_10A0]
0x18003c604  call    IEZoneConfigureW
0x18003c609  mov     rdx, [rsp+21D0h+ulCookie]; ulCookie
0x18003c60e  test    rdx, rdx
0x18003c611  jz      def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c617  xor     ecx, ecx; dwFlags
0x18003c619  call    cs:__imp_DeactivateActCtx
0x18003c61f  jmp     def_18003D2EB; jumptable 000000018003C36E cases 30,60
0x18003c624  mov     rcx, [r14+318h]; jumptable 000000018003C36E case 74
0x18003c62b  xor     esi, esi
0x18003c62d  cmp     r13d, 1
0x18003c631  mov     qword ptr [rsp+21D0h+pPrivacyEnum], rsi
0x18003c636  mov     ebx, esi
0x18003c638  mov     [rsp+21D0h+ulCookie], rsi
0x18003c63d  setz    bl
0x18003c640  test    rcx, rcx
0x18003c643  jz      short loc_18003C66C
0x18003c645  mov     rax, [rcx]
0x18003c648  lea     r9, [rsp+21D0h+ulCookie]
0x18003c64d  mov     rdx, [r14+320h]
0x18003c654  xor     r8d, r8d
0x18003c657  mov     rax, [rax+0A0h]
0x18003c65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c663  test    eax, eax
0x18003c665  jns     short loc_18003C66C
0x18003c667  mov     [rsp+21D0h+ulCookie], rsi
0x18003c66c  mov     rcx, [r14+150h]
0x18003c673  test    rcx, rcx
  ... truncated ...
```
