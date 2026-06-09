# CSecurityBand::RecordPageActionBlocked(ulong,ulong,tagVARIANT *,int)

- ea: `0x1801a2f5c`
- end: `0x1801a391b`
- name: `?RecordPageActionBlocked@CSecurityBand@@QEAAHKKPEAUtagVARIANT@@H@Z`
- size: `2495`
- prototype: `__int64 __fastcall(CSecurityBand *__hidden this, unsigned int, unsigned int, struct tagVARIANT *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18014c27c`

## callees

- `0x180041590`
- `0x18005c660`
- `0x18007587c`
- `0x1800a130c`
- `0x1801a2f5c`
- `0x1801a67fc`
- `0x1803f6340`
- `0x1803f687c`
- `0x1803f68bc`
- `0x180591f80`
- `0x180592040`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x1801a310d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x1801a318a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x1801a310d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x1801a318a`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a335d`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a3503`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a3540`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a35d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a376a`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a37f2`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a3864`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a335d`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a3503`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a3540`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a35d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a376a`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a37f2`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a3864`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a375a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a37e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a3853`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a389f`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a38b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a38d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a375a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a37e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a3853`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a389f`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a38b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a38d0`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a30cf`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a3150`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a362f`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a3690`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a30cf`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a3150`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a362f`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a3690`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a3028`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801a3028`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a30ac`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3135`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a31b7`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a31ff`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3235`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3317`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a34a5`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a34e6`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a35b1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3614`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3675`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3737`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a37bc`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a382a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a30ac`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3135`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a31b7`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a31ff`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3235`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3317`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a34a5`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a34e6`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a35b1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3614`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3675`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a3737`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a37bc`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1801a382a`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a3345`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a378a`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a3345`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1801a378a`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1801a31d8`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x1801a31d8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a2fbf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a3253`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a340e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a3424`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a343e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a2fbf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a3253`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a340e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a3424`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801a343e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a30f3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a3170`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a326d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a3458`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a346e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a3484`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a3647`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a36a8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a30f3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a3170`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a326d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a3458`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a346e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a3484`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a3647`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1801a36a8`

## pseudocode

```c
_BOOL8 __fastcall CSecurityBand::RecordPageActionBlocked(
        CSecurityBand *this,
        int a2,
        LONG a3,
        struct tagVARIANT *a4,
        int a5)
{
  BOOL v8; // r14d
  unsigned __int16 **v9; // rbx
  CDocObjectHost *v10; // rcx
  LONG v11; // edx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // r13
  SAFEARRAY *parray; // rcx
  const WCHAR *v14; // rcx
  SAFEARRAY *v15; // rcx
  const WCHAR *v16; // rcx
  SAFEARRAY *v17; // rcx
  SAFEARRAY *v18; // rcx
  SAFEARRAY *v19; // rcx
  const WCHAR *v20; // rcx
  BSTR *v21; // rcx
  VARTYPE vt; // r8
  bool v23; // al
  bool v24; // di
  SAFEARRAY *llVal; // rcx
  BSTR v26; // rax
  unsigned __int64 v27; // r8
  int ModuleInfoFromSignature; // eax
  unsigned __int64 v29; // rdx
  SAFEARRAY *v30; // rcx
  SAFEARRAY *v31; // rcx
  LPCOLESTR *p_pv; // rcx
  unsigned __int16 *v33; // rax
  SAFEARRAY *v34; // rcx
  unsigned __int16 *v35; // rbx
  SAFEARRAY *v36; // rcx
  SAFEARRAY *v37; // rcx
  SAFEARRAY *v38; // rcx
  const WCHAR *v39; // rax
  SAFEARRAY *v40; // rcx
  BSTR v41; // rax
  SAFEARRAY *v42; // rcx
  BSTR v43; // rax
  OLECHAR *v44; // rcx
  OLECHAR *v45; // rcx
  unsigned __int64 v47; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v48; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v49; // [rsp+48h] [rbp-B8h]
  LONG rgIndices; // [rsp+60h] [rbp-A0h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h]
  __int128 pv; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+90h] [rbp-70h]
  LPCWSTR psz[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v56; // [rsp+A8h] [rbp-58h]
  LONG plUbound; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR *v58[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-38h]
  LPWSTR ppwsz; // [rsp+D0h] [rbp-30h] BYREF
  BSTR pbstr[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v62; // [rsp+E8h] [rbp-18h]
  WCHAR v63[128]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[264]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v65[128]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v66[264]; // [rsp+500h] [rbp+400h] BYREF
  WCHAR v67[2088]; // [rsp+710h] [rbp+610h] BYREF

  rgIndices = a3;
  v8 = a2 != *((_DWORD *)this + 2);
  if ( (a2 & 0x3000200) == 0 )
  {
    v9 = (unsigned __int16 **)((char *)this + 32);
    CoTaskMemFree(*((LPVOID *)this + 4));
    v10 = (CDocObjectHost *)*((_QWORD *)this + 2);
    *v9 = 0;
    CDocObjectHost::_GetCurrentPageW(v10, v9, 1);
  }
  if ( a5 && (a2 & 0x22000200) == 0 )
    CSecurityBand::ResetCachedPageActionDetails(this);
  if ( a4 )
  {
    v11 = 0;
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a4->llVal;
    plUbound = 0;
    if ( (a4->vt & 0x2000) != 0 )
    {
      SafeArrayGetUBound(p_llVal->parray, 1u, &plUbound);
      v11 = plUbound;
    }
    if ( (a2 & 0x202) != 0 && a4->vt == 8204 )
    {
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a4->llVal;
      parray = a4->parray;
      if ( parray )
      {
        if ( v11 == 4 )
        {
          v54 = 0;
          v62 = 0;
          v52 = 0;
          pv = 0;
          v59 = 0;
          *(_OWORD *)pbstr = 0;
          v56 = 0;
          *(_OWORD *)lpsz = 0;
          rgIndices = 0;
          *(_OWORD *)v58 = 0;
          *(_OWORD *)psz = 0;
          if ( SafeArrayGetElement(parray, &rgIndices, &pv) >= 0 && (_WORD)pv == 8 && SysStringLen(*((BSTR *)&pv + 1)) )
          {
            v14 = (const WCHAR *)*((_QWORD *)this + 6);
            if ( v14 )
            {
              if ( StrCmpW(v14, *((PCWSTR *)&pv + 1)) )
              {
                ++*((_DWORD *)this + 11);
                v8 = 1;
              }
            }
            else if ( SHStrDupW(*((LPCWSTR *)&pv + 1), (LPWSTR *)this + 6) >= 0 )
            {
              *((_DWORD *)this + 11) = 1;
            }
            v15 = a4->parray;
            rgIndices = 1;
            if ( SafeArrayGetElement(v15, &rgIndices, pbstr) >= 0 && LOWORD(pbstr[0]) == 8 && SysStringLen(pbstr[1]) )
            {
              v16 = (const WCHAR *)*((_QWORD *)this + 7);
              if ( v16 )
              {
                if ( StrCmpW(v16, pbstr[1]) )
                {
                  ++*((_DWORD *)this + 10);
                  v8 = 1;
                }
              }
              else if ( SHStrDupW(pbstr[1], (LPWSTR *)this + 7) >= 0 )
              {
                *((_DWORD *)this + 10) = 1;
              }
            }
          }
          v17 = a4->parray;
          rgIndices = 2;
          if ( SafeArrayGetElement(v17, &rgIndices, lpsz) >= 0
            && LOWORD(lpsz[0]) == 8
            && !CLSIDFromString(lpsz[1], (LPCLSID)this + 4) )
          {
            v8 = 1;
          }
          v18 = a4->parray;
          rgIndices = 3;
          if ( SafeArrayGetElement(v18, &rgIndices, v58) >= 0 && LOWORD(v58[0]) == 19 )
          {
            v8 = 1;
            *((_DWORD *)this + 20) = v58[1];
          }
          v19 = a4->parray;
          rgIndices = 4;
          if ( SafeArrayGetElement(v19, &rgIndices, psz) >= 0 && LOWORD(psz[0]) == 8 )
          {
            CoTaskMemFree(*((LPVOID *)this + 11));
            v20 = psz[1];
            *((_QWORD *)this + 11) = 0;
            if ( SHStrDupW(v20, (LPWSTR *)this + 11) >= 0 )
              v8 = 1;
          }
          ATL::CComVariant::Clear((ATL::CComVariant *)psz);
          ATL::CComVariant::Clear((ATL::CComVariant *)v58);
          ATL::CComVariant::Clear((ATL::CComVariant *)lpsz);
          v21 = pbstr;
LABEL_60:
          ATL::CComVariant::Clear((ATL::CComVariant *)v21);
          p_pv = (LPCOLESTR *)&pv;
LABEL_100:
          ATL::CComVariant::Clear((ATL::CComVariant *)p_pv);
          return v8;
        }
      }
    }
    vt = a4->vt;
    v23 = (a4->vt & 0x2000) != 0;
    v24 = 0;
    if ( (a2 & 0x2040000) != 0 && v23 && !*((_QWORD *)this + 13) && v11 == 2 )
    {
      llVal = (SAFEARRAY *)p_llVal->llVal;
      rgIndices = 0;
      v54 = 0;
      v59 = 0;
      v52 = 0;
      pv = 0;
      *(_OWORD *)v58 = 0;
      *(_OWORD *)lpsz = 0;
      if ( SafeArrayGetElement(llVal, &rgIndices, &pv) >= 0
        && (_WORD)pv == 8
        && (*(_OWORD *)pbstr = 0, SHCLSIDFromString(*((PCWSTR *)&pv + 1), (CLSID *)pbstr) >= 0)
        && (v26 = SysAllocString(*((const OLECHAR **)&pv + 1)), (*((_QWORD *)this + 13) = v26) != 0)
        && Ext_GetModulePath((const struct _GUID *)pbstr, v66, 0x104u, 3u, 0) >= 0
        && (ModuleInfoFromSignature = Ext_GetModuleInfoFromSignature(
                                        v66,
                                        v63,
                                        v27,
                                        0x8640u,
                                        Buffer,
                                        v47,
                                        v67,
                                        v48,
                                        v65,
                                        v49,
                                        1),
            ModuleInfoFromSignature >= 0) )
      {
        *((_DWORD *)this + 34) = ModuleInfoFromSignature == 0;
      }
      else
      {
        Ext_GetStaticPublisher(v63, 0x80u);
        Ext_GetStaticDisplayName(Buffer, v29);
        v67[0] = 0;
      }
      CoTaskMemFree(*((LPVOID *)this + 6));
      *((_QWORD *)this + 6) = 0;
      CoTaskMemFree(*((LPVOID *)this + 7));
      *((_QWORD *)this + 7) = 0;
      CoTaskMemFree(*((LPVOID *)this + 12));
      *((_QWORD *)this + 12) = 0;
      SHStrDupW(v63, (LPWSTR *)this + 6);
      SHStrDupW(Buffer, (LPWSTR *)this + 7);
      SHStrDupW(v67, (LPWSTR *)this + 12);
      v30 = (SAFEARRAY *)p_llVal->llVal;
      rgIndices = 1;
      if ( SafeArrayGetElement(v30, &rgIndices, v58) >= 0 && LOWORD(v58[0]) == 19 )
        *((_DWORD *)this + 38) = v58[1];
      if ( *((_DWORD *)this + 38) == 2 )
      {
        v31 = (SAFEARRAY *)p_llVal->llVal;
        rgIndices = 2;
        if ( SafeArrayGetElement(v31, &rgIndices, lpsz) >= 0 && LOWORD(lpsz[0]) == 8 )
          *((_QWORD *)this + 14) = SysAllocString(lpsz[1]);
      }
      ATL::CComVariant::Clear((ATL::CComVariant *)lpsz);
      v21 = v58;
      goto LABEL_60;
    }
    if ( (a2 & 0x10000000) != 0 && vt == 8 )
    {
      v33 = SysAllocString(p_llVal->bstrVal);
      if ( v33 )
        CSecurityBand::_SetDetailsForCompatNotifications(this, v33, 0, 0);
    }
    else
    {
      if ( (a2 & 0x1000000) != 0 && vt == 8204 )
      {
        v34 = (SAFEARRAY *)p_llVal->llVal;
        if ( p_llVal->llVal )
        {
          if ( v11 == 2 )
          {
            rgIndices = 2;
            v52 = 0;
            *(_OWORD *)lpsz = 0;
            if ( SafeArrayGetElement(v34, &rgIndices, lpsz) >= 0 && LOWORD(lpsz[0]) == 8 )
            {
              v35 = SysAllocString(lpsz[1]);
              if ( v35 )
              {
                v36 = (SAFEARRAY *)p_llVal->llVal;
                pbstr[0] = 0;
                ppwsz = 0;
                v56 = 0;
                *(_OWORD *)psz = 0;
                rgIndices = 0;
                if ( SafeArrayGetElement(v36, &rgIndices, psz) >= 0 && LOWORD(psz[0]) == 8 && SysStringLen((BSTR)psz[1]) )
                  SHStrDupW(psz[1], pbstr);
                v37 = (SAFEARRAY *)p_llVal->llVal;
                rgIndices = 1;
                pv = 0;
                v54 = 0;
                if ( SafeArrayGetElement(v37, &rgIndices, &pv) >= 0
                  && (_WORD)pv == 8
                  && SysStringLen(*((BSTR *)&pv + 1)) )
                {
                  SHStrDupW(*((LPCWSTR *)&pv + 1), &ppwsz);
                }
                CSecurityBand::_SetDetailsForCompatNotifications(this, v35, pbstr[0], ppwsz);
                ATL::CComVariant::Clear((ATL::CComVariant *)&pv);
                ATL::CComVariant::Clear((ATL::CComVariant *)psz);
              }
            }
            p_pv = lpsz;
            goto LABEL_100;
          }
        }
      }
      if ( (a2 & 0x40000000) != 0 && (rgIndices & 0x40) != 0 && vt == 8204 )
      {
        v38 = (SAFEARRAY *)p_llVal->llVal;
        if ( p_llVal->llVal )
        {
          if ( v11 == 3 )
          {
            rgIndices = 1;
            v56 = 0;
            *(_OWORD *)psz = 0;
            if ( SafeArrayGetElement(v38, &rgIndices, psz) < 0 )
              goto LABEL_98;
            if ( LOWORD(psz[0]) != 8 )
              goto LABEL_98;
            SysFreeString(*((BSTR *)this + 13));
            v39 = SysAllocString(psz[1]);
            *((_QWORD *)this + 13) = v39;
            if ( !v39 || SHCLSIDFromString(v39, (CLSID *)this + 4) < 0 )
              goto LABEL_98;
            v40 = (SAFEARRAY *)p_llVal->llVal;
            rgIndices = 2;
            *(_OWORD *)v58 = 0;
            v59 = 0;
            if ( SafeArrayGetElement(v40, &rgIndices, v58) >= 0 && LOWORD(v58[0]) == 8 )
            {
              SysFreeString(*((BSTR *)this + 20));
              v41 = SysAllocString(v58[1]);
              rgIndices = 3;
              *((_QWORD *)this + 20) = v41;
              v42 = (SAFEARRAY *)p_llVal->llVal;
              v52 = 0;
              *(_OWORD *)lpsz = 0;
              if ( SafeArrayGetElement(v42, &rgIndices, lpsz) >= 0 && LOWORD(lpsz[0]) == 8 && *((_QWORD *)this + 20) )
              {
                SysFreeString(*((BSTR *)this + 21));
                v43 = SysAllocString(lpsz[1]);
                *((_QWORD *)this + 21) = v43;
                v24 = v43 != 0;
              }
              ATL::CComVariant::Clear((ATL::CComVariant *)lpsz);
            }
            ATL::CComVariant::Clear((ATL::CComVariant *)v58);
            if ( !v24 )
            {
LABEL_98:
              SysFreeString(*((BSTR *)this + 13));
              v44 = (OLECHAR *)*((_QWORD *)this + 20);
              *((_QWORD *)this + 13) = 0;
              SysFreeString(v44);
              v45 = (OLECHAR *)*((_QWORD *)this + 21);
              *((_QWORD *)this + 20) = 0;
              SysFreeString(v45);
              *((_QWORD *)this + 21) = 0;
            }
            p_pv = psz;
            goto LABEL_100;
          }
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1801a2f5c  mov     [rsp-8+arg_8], rbx
0x1801a2f61  mov     [rsp-8+arg_10], rsi
0x1801a2f66  push    rbp
0x1801a2f67  push    rdi
0x1801a2f68  push    r13
0x1801a2f6a  push    r14
0x1801a2f6c  push    r15
0x1801a2f6e  lea     rbp, [rsp-1670h]
0x1801a2f76  mov     eax, 1770h
0x1801a2f7b  call    _alloca_probe
0x1801a2f80  sub     rsp, rax
0x1801a2f83  mov     rax, cs:__security_cookie
0x1801a2f8a  xor     rax, rsp
0x1801a2f8d  mov     [rbp+1690h+var_30], rax
0x1801a2f94  xor     r14d, r14d
0x1801a2f97  mov     [rsp+1790h+rgIndices], r8d
0x1801a2f9c  cmp     edx, [rcx+8]
0x1801a2f9f  mov     rdi, r9
0x1801a2fa2  mov     esi, edx
0x1801a2fa4  mov     r15, rcx
0x1801a2fa7  setnz   r14b
0x1801a2fab  mov     ebx, 1
0x1801a2fb0  test    edx, 3000200h
0x1801a2fb6  jnz     short loc_1801A2FE9
0x1801a2fb8  lea     rbx, [rcx+20h]
0x1801a2fbc  mov     rcx, [rbx]; pv
0x1801a2fbf  call    cs:__imp_CoTaskMemFree
0x1801a2fc6  nop     dword ptr [rax+rax+00h]
0x1801a2fcb  mov     rcx, [r15+10h]; this
0x1801a2fcf  mov     r8d, 1; int
0x1801a2fd5  mov     rdx, rbx; unsigned __int16 **
0x1801a2fd8  mov     qword ptr [rbx], 0
0x1801a2fdf  call    ?_GetCurrentPageW@CDocObjectHost@@IEAAJPEAPEAGH@Z; CDocObjectHost::_GetCurrentPageW(ushort * *,int)
0x1801a2fe4  mov     ebx, 1
0x1801a2fe9  cmp     [rbp+1690h+arg_20], 0
0x1801a2ff0  jz      short loc_1801A3002
0x1801a2ff2  test    esi, 22000200h
0x1801a2ff8  jnz     short loc_1801A3002
0x1801a2ffa  mov     rcx, r15; this
0x1801a2ffd  call    ?ResetCachedPageActionDetails@CSecurityBand@@QEAAXXZ; CSecurityBand::ResetCachedPageActionDetails(void)
0x1801a3002  test    rdi, rdi
0x1801a3005  jz      loc_1801A38EC
0x1801a300b  xor     edx, edx
0x1801a300d  lea     r13, [rdi+8]
0x1801a3011  mov     eax, 2000h
0x1801a3016  mov     [rbp+1690h+plUbound], edx
0x1801a3019  test    [rdi], ax
0x1801a301c  jz      short loc_1801A3037
0x1801a301e  mov     rcx, [r13+0]; psa
0x1801a3022  lea     r8, [rbp+1690h+plUbound]; plUbound
0x1801a3026  mov     edx, ebx; nDim
0x1801a3028  call    cs:__imp_SafeArrayGetUBound
0x1801a302f  nop     dword ptr [rax+rax+00h]
0x1801a3034  mov     edx, [rbp+1690h+plUbound]
0x1801a3037  mov     r9d, 200Ch
0x1801a303d  test    esi, 202h
0x1801a3043  jz      loc_1801A32A9
0x1801a3049  cmp     [rdi], r9w
0x1801a304d  jnz     loc_1801A32A9
0x1801a3053  lea     r13, [rdi+8]
0x1801a3057  mov     rcx, [r13+0]; psa
0x1801a305b  test    rcx, rcx
0x1801a305e  jz      loc_1801A32A9
0x1801a3064  cmp     edx, 4
0x1801a3067  jnz     loc_1801A32A9
0x1801a306d  xor     eax, eax
0x1801a306f  lea     r8, [rbp+1690h+pv]; pv
0x1801a3073  xorps   xmm0, xmm0
0x1801a3076  mov     [rbp+1690h+var_1700], rax
0x1801a307a  xorps   xmm1, xmm1
0x1801a307d  mov     [rbp+1690h+var_16A8], rax
0x1801a3081  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x1801a3086  mov     [rsp+1790h+var_1718], rax
0x1801a308b  movups  [rbp+1690h+pv], xmm0
0x1801a308f  mov     [rbp+1690h+var_16C8], rax
0x1801a3093  movups  xmmword ptr [rbp+1690h+pbstr], xmm1
0x1801a3097  mov     [rbp+1690h+var_16E8], rax
0x1801a309b  movups  xmmword ptr [rsp+1790h+lpsz], xmm0
0x1801a30a0  mov     [rsp+1790h+rgIndices], eax
0x1801a30a4  movups  xmmword ptr [rbp+1690h+var_16D8], xmm1
0x1801a30a8  movups  xmmword ptr [rbp+1690h+psz], xmm0
0x1801a30ac  call    cs:__imp_SafeArrayGetElement
0x1801a30b3  nop     dword ptr [rax+rax+00h]
0x1801a30b8  test    eax, eax
0x1801a30ba  js      loc_1801A31A1
0x1801a30c0  cmp     word ptr [rbp+1690h+pv], 8
0x1801a30c5  jnz     loc_1801A31A1
0x1801a30cb  mov     rcx, qword ptr [rbp+1690h+pv+8]; pbstr
0x1801a30cf  call    cs:__imp_SysStringLen
0x1801a30d6  nop     dword ptr [rax+rax+00h]
0x1801a30db  test    eax, eax
0x1801a30dd  jz      loc_1801A31A1
0x1801a30e3  lea     rdx, [r15+30h]; ppwsz
0x1801a30e7  mov     rcx, [rdx]; psz1
0x1801a30ea  test    rcx, rcx
0x1801a30ed  jnz     short loc_1801A3109
0x1801a30ef  mov     rcx, qword ptr [rbp+1690h+pv+8]; psz
0x1801a30f3  call    cs:__imp_SHStrDupW
0x1801a30fa  nop     dword ptr [rax+rax+00h]
0x1801a30ff  test    eax, eax
0x1801a3101  js      short loc_1801A3124
0x1801a3103  mov     [r15+2Ch], ebx
0x1801a3107  jmp     short loc_1801A3124
0x1801a3109  mov     rdx, qword ptr [rbp+1690h+pv+8]; psz2
0x1801a310d  call    cs:__imp_StrCmpW
0x1801a3114  nop     dword ptr [rax+rax+00h]
0x1801a3119  test    eax, eax
0x1801a311b  jz      short loc_1801A3124
0x1801a311d  add     [r15+2Ch], ebx
0x1801a3121  mov     r14d, ebx
0x1801a3124  mov     rcx, [rdi+8]; psa
0x1801a3128  lea     r8, [rbp+1690h+pbstr]; pv
0x1801a312c  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x1801a3131  mov     [rsp+1790h+rgIndices], ebx
0x1801a3135  call    cs:__imp_SafeArrayGetElement
0x1801a313c  nop     dword ptr [rax+rax+00h]
0x1801a3141  test    eax, eax
0x1801a3143  js      short loc_1801A31A1
0x1801a3145  cmp     word ptr [rbp+1690h+pbstr], 8
0x1801a314a  jnz     short loc_1801A31A1
0x1801a314c  mov     rcx, [rbp+1690h+pbstr+8]; pbstr
0x1801a3150  call    cs:__imp_SysStringLen
0x1801a3157  nop     dword ptr [rax+rax+00h]
0x1801a315c  test    eax, eax
0x1801a315e  jz      short loc_1801A31A1
0x1801a3160  lea     rdx, [r15+38h]; ppwsz
0x1801a3164  mov     rcx, [rdx]; psz1
0x1801a3167  test    rcx, rcx
0x1801a316a  jnz     short loc_1801A3186
0x1801a316c  mov     rcx, [rbp+1690h+pbstr+8]; psz
0x1801a3170  call    cs:__imp_SHStrDupW
0x1801a3177  nop     dword ptr [rax+rax+00h]
0x1801a317c  test    eax, eax
0x1801a317e  js      short loc_1801A31A1
0x1801a3180  mov     [r15+28h], ebx
0x1801a3184  jmp     short loc_1801A31A1
0x1801a3186  mov     rdx, [rbp+1690h+pbstr+8]; psz2
0x1801a318a  call    cs:__imp_StrCmpW
0x1801a3191  nop     dword ptr [rax+rax+00h]
0x1801a3196  test    eax, eax
0x1801a3198  jz      short loc_1801A31A1
0x1801a319a  add     [r15+28h], ebx
0x1801a319e  mov     r14d, ebx
0x1801a31a1  mov     rcx, [rdi+8]; psa
0x1801a31a5  lea     r8, [rsp+1790h+lpsz]; pv
0x1801a31aa  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x1801a31af  mov     [rsp+1790h+rgIndices], 2
0x1801a31b7  call    cs:__imp_SafeArrayGetElement
0x1801a31be  nop     dword ptr [rax+rax+00h]
0x1801a31c3  test    eax, eax
0x1801a31c5  js      short loc_1801A31EA
0x1801a31c7  cmp     word ptr [rsp+1790h+lpsz], 8
0x1801a31cd  jnz     short loc_1801A31EA
0x1801a31cf  mov     rcx, [rsp+1790h+lpsz+8]; lpsz
0x1801a31d4  lea     rdx, [r15+40h]; pclsid
0x1801a31d8  call    cs:__imp_CLSIDFromString
0x1801a31df  nop     dword ptr [rax+rax+00h]
0x1801a31e4  test    eax, eax
0x1801a31e6  cmovz   r14d, ebx
0x1801a31ea  mov     rcx, [rdi+8]; psa
0x1801a31ee  lea     r8, [rbp+1690h+var_16D8]; pv
0x1801a31f2  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x1801a31f7  mov     [rsp+1790h+rgIndices], 3
0x1801a31ff  call    cs:__imp_SafeArrayGetElement
0x1801a3206  nop     dword ptr [rax+rax+00h]
0x1801a320b  test    eax, eax
0x1801a320d  js      short loc_1801A3220
0x1801a320f  cmp     word ptr [rbp+1690h+var_16D8], 13h
0x1801a3214  jnz     short loc_1801A3220
0x1801a3216  mov     eax, dword ptr [rbp+1690h+var_16D8+8]
0x1801a3219  mov     r14d, ebx
0x1801a321c  mov     [r15+50h], eax
0x1801a3220  mov     rcx, [rdi+8]; psa
0x1801a3224  lea     r8, [rbp+1690h+psz]; pv
0x1801a3228  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x1801a322d  mov     [rsp+1790h+rgIndices], 4
0x1801a3235  call    cs:__imp_SafeArrayGetElement
0x1801a323c  nop     dword ptr [rax+rax+00h]
0x1801a3241  test    eax, eax
0x1801a3243  js      short loc_1801A3284
0x1801a3245  cmp     word ptr [rbp+1690h+psz], 8
0x1801a324a  jnz     short loc_1801A3284
0x1801a324c  lea     rbx, [r15+58h]
0x1801a3250  mov     rcx, [rbx]; pv
0x1801a3253  call    cs:__imp_CoTaskMemFree
0x1801a325a  nop     dword ptr [rax+rax+00h]
0x1801a325f  mov     rcx, [rbp+1690h+psz+8]; psz
0x1801a3263  mov     rdx, rbx; ppwsz
0x1801a3266  mov     qword ptr [rbx], 0
0x1801a326d  call    cs:__imp_SHStrDupW
0x1801a3274  nop     dword ptr [rax+rax+00h]
0x1801a3279  test    eax, eax
0x1801a327b  mov     eax, 1
0x1801a3280  cmovns  r14d, eax
0x1801a3284  lea     rcx, [rbp+1690h+psz]; this
0x1801a3288  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1801a328d  lea     rcx, [rbp+1690h+var_16D8]; this
0x1801a3291  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1801a3296  lea     rcx, [rsp+1790h+lpsz]; this
0x1801a329b  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x1801a32a0  lea     rcx, [rbp+1690h+pbstr]
0x1801a32a4  jmp     loc_1801A3521
0x1801a32a9  movzx   r8d, word ptr [rdi]
0x1801a32ad  test    esi, 2040000h
0x1801a32b3  mov     eax, 0Dh
0x1801a32b8  mov     ebx, 2
0x1801a32bd  setnz   cl
0x1801a32c0  bt      r8w, ax
0x1801a32c5  setb    al
0x1801a32c8  xor     edi, edi
0x1801a32ca  test    al, cl
0x1801a32cc  jz      loc_1801A352F
0x1801a32d2  cmp     [r15+68h], rdi
0x1801a32d6  jnz     loc_1801A352F
0x1801a32dc  cmp     edx, ebx
0x1801a32de  jnz     loc_1801A352F
0x1801a32e4  mov     rcx, [r13+0]; psa
0x1801a32e8  lea     r8, [rbp+1690h+pv]; pv
0x1801a32ec  xor     eax, eax
0x1801a32ee  mov     [rsp+1790h+rgIndices], edi
0x1801a32f2  xorps   xmm0, xmm0
0x1801a32f5  mov     [rbp+1690h+var_1700], rax
0x1801a32f9  xorps   xmm1, xmm1
0x1801a32fc  mov     [rbp+1690h+var_16C8], rax
0x1801a3300  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x1801a3305  mov     [rsp+1790h+var_1718], rax
0x1801a330a  movups  [rbp+1690h+pv], xmm0
0x1801a330e  movups  xmmword ptr [rbp+1690h+var_16D8], xmm1
0x1801a3312  movups  xmmword ptr [rsp+1790h+lpsz], xmm0
0x1801a3317  call    cs:__imp_SafeArrayGetElement
0x1801a331e  nop     dword ptr [rax+rax+00h]
0x1801a3323  test    eax, eax
0x1801a3325  js      loc_1801A33E6
0x1801a332b  cmp     word ptr [rbp+1690h+pv], 8
0x1801a3330  jnz     loc_1801A33E6
0x1801a3336  mov     rcx, qword ptr [rbp+1690h+pv+8]; psz
0x1801a333a  lea     rdx, [rbp+1690h+pbstr]; pclsid
0x1801a333e  xorps   xmm0, xmm0
0x1801a3341  movups  xmmword ptr [rbp+1690h+pbstr], xmm0
0x1801a3345  call    cs:__imp_SHCLSIDFromString
0x1801a334c  nop     dword ptr [rax+rax+00h]
0x1801a3351  test    eax, eax
0x1801a3353  js      loc_1801A33E6
0x1801a3359  mov     rcx, qword ptr [rbp+1690h+pv+8]; psz
0x1801a335d  call    cs:__imp_SysAllocString
0x1801a3364  nop     dword ptr [rax+rax+00h]
0x1801a3369  mov     [r15+68h], rax
0x1801a336d  test    rax, rax
0x1801a3370  jz      short loc_1801A33E6
0x1801a3372  lea     r9d, [rbx+1]; unsigned int
0x1801a3376  mov     [rsp+1790h+lpBuffer], rdi; enum _EXT_ARCHITECTURE *
0x1801a337b  mov     r8d, 104h; unsigned __int64
0x1801a3381  lea     rdx, [rbp+1690h+var_1290]; unsigned __int16 *
0x1801a3388  lea     rcx, [rbp+1690h+pbstr]; struct _GUID *
0x1801a338c  call    ?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)
0x1801a3391  test    eax, eax
0x1801a3393  js      short loc_1801A33E6
0x1801a3395  mov     [rsp+1790h+var_1740], 1; bool
0x1801a339a  lea     rax, [rbp+1690h+var_1390]
0x1801a33a1  mov     [rsp+1790h+var_1750], rax; unsigned __int16 *
0x1801a33a6  lea     rdx, [rbp+1690h+var_16A0]; unsigned __int16 *
0x1801a33aa  lea     rax, [rbp+1690h+var_1080]
0x1801a33b1  mov     r9d, 8640h; unsigned int
0x1801a33b7  mov     [rsp+1790h+var_1760], rax; unsigned __int16 *
0x1801a33bc  lea     rcx, [rbp+1690h+var_1290]; unsigned __int16 *
0x1801a33c3  lea     rax, [rbp+1690h+Buffer]
0x1801a33ca  mov     [rsp+1790h+lpBuffer], rax; lpBuffer
0x1801a33cf  call    ?Ext_GetModuleInfoFromSignature@@YAJPEBGPEAG_KI121212_N@Z; Ext_GetModuleInfoFromSignature(ushort const *,ushort *,unsigned __int64,uint,ushort *,unsigned __int64,ushort *,unsigned __int64,ushort *,unsigned __int64,bool)
0x1801a33d4  test    eax, eax
0x1801a33d6  js      short loc_1801A33E6
0x1801a33d8  mov     ecx, edi
0x1801a33da  setz    cl
0x1801a33dd  mov     [r15+88h], ecx
0x1801a33e4  jmp     short loc_1801A3407
0x1801a33e6  mov     edx, 80h; cchBufferMax
0x1801a33eb  lea     rcx, [rbp+1690h+var_16A0]; lpBuffer
0x1801a33ef  call    ?Ext_GetStaticPublisher@@YAXPEAG_K@Z; Ext_GetStaticPublisher(ushort *,unsigned __int64)
0x1801a33f4  lea     rcx, [rbp+1690h+Buffer]; lpBuffer
0x1801a33fb  call    ?Ext_GetStaticDisplayName@@YAXPEAG_K@Z; Ext_GetStaticDisplayName(ushort *,unsigned __int64)
0x1801a3400  mov     [rbp+1690h+var_1080], di
0x1801a3407  lea     rsi, [r15+30h]
0x1801a340b  mov     rcx, [rsi]; pv
0x1801a340e  call    cs:__imp_CoTaskMemFree
0x1801a3415  nop     dword ptr [rax+rax+00h]
0x1801a341a  mov     [rsi], rdi
0x1801a341d  lea     rdi, [r15+38h]
0x1801a3421  mov     rcx, [rdi]; pv
0x1801a3424  call    cs:__imp_CoTaskMemFree
0x1801a342b  nop     dword ptr [rax+rax+00h]
0x1801a3430  lea     rbx, [r15+60h]
0x1801a3434  mov     qword ptr [rdi], 0
0x1801a343b  mov     rcx, [rbx]; pv
0x1801a343e  call    cs:__imp_CoTaskMemFree
0x1801a3445  nop     dword ptr [rax+rax+00h]
0x1801a344a  mov     rdx, rsi; ppwsz
0x1801a344d  mov     qword ptr [rbx], 0
0x1801a3454  lea     rcx, [rbp+1690h+var_16A0]; psz
0x1801a3458  call    cs:__imp_SHStrDupW
0x1801a345f  nop     dword ptr [rax+rax+00h]
0x1801a3464  mov     rdx, rdi; ppwsz
  ... truncated ...
```
