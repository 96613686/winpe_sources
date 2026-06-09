# CSecurityBand::RecordPageActionBlocked(ulong,ulong,tagVARIANT *,int)

- ea: `0x18018f5ec`
- end: `0x18018fe7e`
- name: `?RecordPageActionBlocked@CSecurityBand@@QEAAHKKPEAUtagVARIANT@@H@Z`
- size: `2194`
- prototype: `__int64 __fastcall(CSecurityBand *__hidden this, unsigned int, unsigned int, struct tagVARIANT *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18013d35c`

## callees

- `0x18003f474`
- `0x18005908c`
- `0x18006ff5c`
- `0x18009a024`
- `0x18018f5ec`
- `0x180192bb4`
- `0x1803c33ec`
- `0x1803c38e8`
- `0x1803c3920`
- `0x18054e310`
- `0x18054e3d0`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18018f77f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18018f7e4`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18018f77f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18018f7e4`
- `OLEAUT32!__imp_SysAllocString` at `0x18018f981`
- `OLEAUT32!__imp_SysAllocString` at `0x18018faf1`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fb28`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fbb2`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fd10`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fd80`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fde0`
- `OLEAUT32!__imp_SysAllocString` at `0x18018f981`
- `OLEAUT32!__imp_SysAllocString` at `0x18018faf1`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fb28`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fbb2`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fd10`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fd80`
- `OLEAUT32!__imp_SysAllocString` at `0x18018fde0`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fd06`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fd76`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fdd5`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fe15`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fe26`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fe3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fd06`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fd76`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fdd5`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fe15`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fe26`
- `OLEAUT32!__imp_SysFreeString` at `0x18018fe3a`
- `OLEAUT32!__imp_SysStringLen` at `0x18018f74d`
- `OLEAUT32!__imp_SysStringLen` at `0x18018f7b6`
- `OLEAUT32!__imp_SysStringLen` at `0x18018fbff`
- `OLEAUT32!__imp_SysStringLen` at `0x18018fc4e`
- `OLEAUT32!__imp_SysStringLen` at `0x18018f74d`
- `OLEAUT32!__imp_SysStringLen` at `0x18018f7b6`
- `OLEAUT32!__imp_SysStringLen` at `0x18018fbff`
- `OLEAUT32!__imp_SysStringLen` at `0x18018fc4e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18018f6b2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18018f6b2`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f730`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f7a1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f80b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f847`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f877`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f947`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fa9f`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fada`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fb93`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fbea`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fc39`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fce9`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fd56`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fdb2`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f730`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f7a1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f80b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f847`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f877`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018f947`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fa9f`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fada`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fb93`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fbea`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fc39`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fce9`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fd56`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18018fdb2`
- `SHELL32!__imp_SHCLSIDFromString` at `0x18018f96f`
- `SHELL32!__imp_SHCLSIDFromString` at `0x18018fd2a`
- `SHELL32!__imp_SHCLSIDFromString` at `0x18018f96f`
- `SHELL32!__imp_SHCLSIDFromString` at `0x18018fd2a`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x18018f826`
- `api-ms-win-downlevel-ole32-l1-1-0!CLSIDFromString` at `0x18018f826`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018f64f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018f88f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018fa2c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018fa3c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018fa50`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018f64f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018f88f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018fa2c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018fa3c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18018fa50`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018f76b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018f7d0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018f8a3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fa64`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fa74`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fa84`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fc11`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fc60`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018f76b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018f7d0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018f8a3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fa64`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fa74`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fa84`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fc11`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18018fc60`

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
0x18018f5ec  mov     [rsp-8+arg_8], rbx
0x18018f5f1  mov     [rsp-8+arg_10], rsi
0x18018f5f6  push    rbp
0x18018f5f7  push    rdi
0x18018f5f8  push    r13
0x18018f5fa  push    r14
0x18018f5fc  push    r15
0x18018f5fe  lea     rbp, [rsp-1670h]
0x18018f606  mov     eax, 1770h
0x18018f60b  call    _alloca_probe
0x18018f610  sub     rsp, rax
0x18018f613  mov     rax, cs:__security_cookie
0x18018f61a  xor     rax, rsp
0x18018f61d  mov     [rbp+1690h+var_30], rax
0x18018f624  xor     r14d, r14d
0x18018f627  mov     [rsp+1790h+rgIndices], r8d
0x18018f62c  cmp     edx, [rcx+8]
0x18018f62f  mov     rdi, r9
0x18018f632  mov     esi, edx
0x18018f634  mov     r15, rcx
0x18018f637  setnz   r14b
0x18018f63b  mov     ebx, 1
0x18018f640  test    edx, 3000200h
0x18018f646  jnz     short loc_18018F673
0x18018f648  lea     rbx, [rcx+20h]
0x18018f64c  mov     rcx, [rbx]; pv
0x18018f64f  call    cs:__imp_CoTaskMemFree
0x18018f655  mov     rcx, [r15+10h]; this
0x18018f659  mov     r8d, 1; int
0x18018f65f  mov     rdx, rbx; unsigned __int16 **
0x18018f662  mov     qword ptr [rbx], 0
0x18018f669  call    ?_GetCurrentPageW@CDocObjectHost@@IEAAJPEAPEAGH@Z; CDocObjectHost::_GetCurrentPageW(ushort * *,int)
0x18018f66e  mov     ebx, 1
0x18018f673  cmp     [rbp+1690h+arg_20], 0
0x18018f67a  jz      short loc_18018F68C
0x18018f67c  test    esi, 22000200h
0x18018f682  jnz     short loc_18018F68C
0x18018f684  mov     rcx, r15; this
0x18018f687  call    ?ResetCachedPageActionDetails@CSecurityBand@@QEAAXXZ; CSecurityBand::ResetCachedPageActionDetails(void)
0x18018f68c  test    rdi, rdi
0x18018f68f  jz      loc_18018FE50
0x18018f695  xor     edx, edx
0x18018f697  lea     r13, [rdi+8]
0x18018f69b  mov     eax, 2000h
0x18018f6a0  mov     [rbp+1690h+plUbound], edx
0x18018f6a3  test    [rdi], ax
0x18018f6a6  jz      short loc_18018F6BB
0x18018f6a8  mov     rcx, [r13+0]; psa
0x18018f6ac  lea     r8, [rbp+1690h+plUbound]; plUbound
0x18018f6b0  mov     edx, ebx; nDim
0x18018f6b2  call    cs:__imp_SafeArrayGetUBound
0x18018f6b8  mov     edx, [rbp+1690h+plUbound]
0x18018f6bb  mov     r9d, 200Ch
0x18018f6c1  test    esi, 202h
0x18018f6c7  jz      loc_18018F8D9
0x18018f6cd  cmp     [rdi], r9w
0x18018f6d1  jnz     loc_18018F8D9
0x18018f6d7  lea     r13, [rdi+8]
0x18018f6db  mov     rcx, [r13+0]; psa
0x18018f6df  test    rcx, rcx
0x18018f6e2  jz      loc_18018F8D9
0x18018f6e8  cmp     edx, 4
0x18018f6eb  jnz     loc_18018F8D9
0x18018f6f1  xor     eax, eax
0x18018f6f3  lea     r8, [rbp+1690h+pv]; pv
0x18018f6f7  xorps   xmm0, xmm0
0x18018f6fa  mov     [rbp+1690h+var_1700], rax
0x18018f6fe  xorps   xmm1, xmm1
0x18018f701  mov     [rbp+1690h+var_16A8], rax
0x18018f705  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x18018f70a  mov     [rsp+1790h+var_1718], rax
0x18018f70f  movups  [rbp+1690h+pv], xmm0
0x18018f713  mov     [rbp+1690h+var_16C8], rax
0x18018f717  movups  xmmword ptr [rbp+1690h+pbstr], xmm1
0x18018f71b  mov     [rbp+1690h+var_16E8], rax
0x18018f71f  movups  xmmword ptr [rsp+1790h+lpsz], xmm0
0x18018f724  mov     [rsp+1790h+rgIndices], eax
0x18018f728  movups  xmmword ptr [rbp+1690h+var_16D8], xmm1
0x18018f72c  movups  xmmword ptr [rbp+1690h+psz], xmm0
0x18018f730  call    cs:__imp_SafeArrayGetElement
0x18018f736  test    eax, eax
0x18018f738  js      loc_18018F7F5
0x18018f73e  cmp     word ptr [rbp+1690h+pv], 8
0x18018f743  jnz     loc_18018F7F5
0x18018f749  mov     rcx, qword ptr [rbp+1690h+pv+8]; pbstr
0x18018f74d  call    cs:__imp_SysStringLen
0x18018f753  test    eax, eax
0x18018f755  jz      loc_18018F7F5
0x18018f75b  lea     rdx, [r15+30h]; ppwsz
0x18018f75f  mov     rcx, [rdx]; psz1
0x18018f762  test    rcx, rcx
0x18018f765  jnz     short loc_18018F77B
0x18018f767  mov     rcx, qword ptr [rbp+1690h+pv+8]; psz
0x18018f76b  call    cs:__imp_SHStrDupW
0x18018f771  test    eax, eax
0x18018f773  js      short loc_18018F790
0x18018f775  mov     [r15+2Ch], ebx
0x18018f779  jmp     short loc_18018F790
0x18018f77b  mov     rdx, qword ptr [rbp+1690h+pv+8]; psz2
0x18018f77f  call    cs:__imp_StrCmpW
0x18018f785  test    eax, eax
0x18018f787  jz      short loc_18018F790
0x18018f789  add     [r15+2Ch], ebx
0x18018f78d  mov     r14d, ebx
0x18018f790  mov     rcx, [rdi+8]; psa
0x18018f794  lea     r8, [rbp+1690h+pbstr]; pv
0x18018f798  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x18018f79d  mov     [rsp+1790h+rgIndices], ebx
0x18018f7a1  call    cs:__imp_SafeArrayGetElement
0x18018f7a7  test    eax, eax
0x18018f7a9  js      short loc_18018F7F5
0x18018f7ab  cmp     word ptr [rbp+1690h+pbstr], 8
0x18018f7b0  jnz     short loc_18018F7F5
0x18018f7b2  mov     rcx, [rbp+1690h+pbstr+8]; pbstr
0x18018f7b6  call    cs:__imp_SysStringLen
0x18018f7bc  test    eax, eax
0x18018f7be  jz      short loc_18018F7F5
0x18018f7c0  lea     rdx, [r15+38h]; ppwsz
0x18018f7c4  mov     rcx, [rdx]; psz1
0x18018f7c7  test    rcx, rcx
0x18018f7ca  jnz     short loc_18018F7E0
0x18018f7cc  mov     rcx, [rbp+1690h+pbstr+8]; psz
0x18018f7d0  call    cs:__imp_SHStrDupW
0x18018f7d6  test    eax, eax
0x18018f7d8  js      short loc_18018F7F5
0x18018f7da  mov     [r15+28h], ebx
0x18018f7de  jmp     short loc_18018F7F5
0x18018f7e0  mov     rdx, [rbp+1690h+pbstr+8]; psz2
0x18018f7e4  call    cs:__imp_StrCmpW
0x18018f7ea  test    eax, eax
0x18018f7ec  jz      short loc_18018F7F5
0x18018f7ee  add     [r15+28h], ebx
0x18018f7f2  mov     r14d, ebx
0x18018f7f5  mov     rcx, [rdi+8]; psa
0x18018f7f9  lea     r8, [rsp+1790h+lpsz]; pv
0x18018f7fe  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x18018f803  mov     [rsp+1790h+rgIndices], 2
0x18018f80b  call    cs:__imp_SafeArrayGetElement
0x18018f811  test    eax, eax
0x18018f813  js      short loc_18018F832
0x18018f815  cmp     word ptr [rsp+1790h+lpsz], 8
0x18018f81b  jnz     short loc_18018F832
0x18018f81d  mov     rcx, [rsp+1790h+lpsz+8]; lpsz
0x18018f822  lea     rdx, [r15+40h]; pclsid
0x18018f826  call    cs:__imp_CLSIDFromString
0x18018f82c  test    eax, eax
0x18018f82e  cmovz   r14d, ebx
0x18018f832  mov     rcx, [rdi+8]; psa
0x18018f836  lea     r8, [rbp+1690h+var_16D8]; pv
0x18018f83a  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x18018f83f  mov     [rsp+1790h+rgIndices], 3
0x18018f847  call    cs:__imp_SafeArrayGetElement
0x18018f84d  test    eax, eax
0x18018f84f  js      short loc_18018F862
0x18018f851  cmp     word ptr [rbp+1690h+var_16D8], 13h
0x18018f856  jnz     short loc_18018F862
0x18018f858  mov     eax, dword ptr [rbp+1690h+var_16D8+8]
0x18018f85b  mov     r14d, ebx
0x18018f85e  mov     [r15+50h], eax
0x18018f862  mov     rcx, [rdi+8]; psa
0x18018f866  lea     r8, [rbp+1690h+psz]; pv
0x18018f86a  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x18018f86f  mov     [rsp+1790h+rgIndices], 4
0x18018f877  call    cs:__imp_SafeArrayGetElement
0x18018f87d  test    eax, eax
0x18018f87f  js      short loc_18018F8B4
0x18018f881  cmp     word ptr [rbp+1690h+psz], 8
0x18018f886  jnz     short loc_18018F8B4
0x18018f888  lea     rbx, [r15+58h]
0x18018f88c  mov     rcx, [rbx]; pv
0x18018f88f  call    cs:__imp_CoTaskMemFree
0x18018f895  mov     rcx, [rbp+1690h+psz+8]; psz
0x18018f899  mov     rdx, rbx; ppwsz
0x18018f89c  mov     qword ptr [rbx], 0
0x18018f8a3  call    cs:__imp_SHStrDupW
0x18018f8a9  test    eax, eax
0x18018f8ab  mov     eax, 1
0x18018f8b0  cmovns  r14d, eax
0x18018f8b4  lea     rcx, [rbp+1690h+psz]; this
0x18018f8b8  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18018f8bd  lea     rcx, [rbp+1690h+var_16D8]; this
0x18018f8c1  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18018f8c6  lea     rcx, [rsp+1790h+lpsz]; this
0x18018f8cb  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18018f8d0  lea     rcx, [rbp+1690h+pbstr]
0x18018f8d4  jmp     loc_18018FB09
0x18018f8d9  movzx   r8d, word ptr [rdi]
0x18018f8dd  test    esi, 2040000h
0x18018f8e3  mov     eax, 0Dh
0x18018f8e8  mov     ebx, 2
0x18018f8ed  setnz   cl
0x18018f8f0  bt      r8w, ax
0x18018f8f5  setb    al
0x18018f8f8  xor     edi, edi
0x18018f8fa  test    al, cl
0x18018f8fc  jz      loc_18018FB17
0x18018f902  cmp     [r15+68h], rdi
0x18018f906  jnz     loc_18018FB17
0x18018f90c  cmp     edx, ebx
0x18018f90e  jnz     loc_18018FB17
0x18018f914  mov     rcx, [r13+0]; psa
0x18018f918  lea     r8, [rbp+1690h+pv]; pv
0x18018f91c  xor     eax, eax
0x18018f91e  mov     [rsp+1790h+rgIndices], edi
0x18018f922  xorps   xmm0, xmm0
0x18018f925  mov     [rbp+1690h+var_1700], rax
0x18018f929  xorps   xmm1, xmm1
0x18018f92c  mov     [rbp+1690h+var_16C8], rax
0x18018f930  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x18018f935  mov     [rsp+1790h+var_1718], rax
0x18018f93a  movups  [rbp+1690h+pv], xmm0
0x18018f93e  movups  xmmword ptr [rbp+1690h+var_16D8], xmm1
0x18018f942  movups  xmmword ptr [rsp+1790h+lpsz], xmm0
0x18018f947  call    cs:__imp_SafeArrayGetElement
0x18018f94d  test    eax, eax
0x18018f94f  js      loc_18018FA04
0x18018f955  cmp     word ptr [rbp+1690h+pv], 8
0x18018f95a  jnz     loc_18018FA04
0x18018f960  mov     rcx, qword ptr [rbp+1690h+pv+8]; psz
0x18018f964  lea     rdx, [rbp+1690h+pbstr]; pclsid
0x18018f968  xorps   xmm0, xmm0
0x18018f96b  movups  xmmword ptr [rbp+1690h+pbstr], xmm0
0x18018f96f  call    cs:__imp_SHCLSIDFromString
0x18018f975  test    eax, eax
0x18018f977  js      loc_18018FA04
0x18018f97d  mov     rcx, qword ptr [rbp+1690h+pv+8]; psz
0x18018f981  call    cs:__imp_SysAllocString
0x18018f987  mov     [r15+68h], rax
0x18018f98b  test    rax, rax
0x18018f98e  jz      short loc_18018FA04
0x18018f990  lea     r9d, [rbx+1]; unsigned int
0x18018f994  mov     [rsp+1790h+lpBuffer], rdi; enum _EXT_ARCHITECTURE *
0x18018f999  mov     r8d, 104h; unsigned __int64
0x18018f99f  lea     rdx, [rbp+1690h+var_1290]; unsigned __int16 *
0x18018f9a6  lea     rcx, [rbp+1690h+pbstr]; struct _GUID *
0x18018f9aa  call    ?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)
0x18018f9af  test    eax, eax
0x18018f9b1  js      short loc_18018FA04
0x18018f9b3  mov     [rsp+1790h+var_1740], 1; bool
0x18018f9b8  lea     rax, [rbp+1690h+var_1390]
0x18018f9bf  mov     [rsp+1790h+var_1750], rax; unsigned __int16 *
0x18018f9c4  lea     rdx, [rbp+1690h+var_16A0]; unsigned __int16 *
0x18018f9c8  lea     rax, [rbp+1690h+var_1080]
0x18018f9cf  mov     r9d, 8640h; unsigned int
0x18018f9d5  mov     [rsp+1790h+var_1760], rax; unsigned __int16 *
0x18018f9da  lea     rcx, [rbp+1690h+var_1290]; unsigned __int16 *
0x18018f9e1  lea     rax, [rbp+1690h+Buffer]
0x18018f9e8  mov     [rsp+1790h+lpBuffer], rax; lpBuffer
0x18018f9ed  call    ?Ext_GetModuleInfoFromSignature@@YAJPEBGPEAG_KI121212_N@Z; Ext_GetModuleInfoFromSignature(ushort const *,ushort *,unsigned __int64,uint,ushort *,unsigned __int64,ushort *,unsigned __int64,ushort *,unsigned __int64,bool)
0x18018f9f2  test    eax, eax
0x18018f9f4  js      short loc_18018FA04
0x18018f9f6  mov     ecx, edi
0x18018f9f8  setz    cl
0x18018f9fb  mov     [r15+88h], ecx
0x18018fa02  jmp     short loc_18018FA25
0x18018fa04  mov     edx, 80h; cchBufferMax
0x18018fa09  lea     rcx, [rbp+1690h+var_16A0]; lpBuffer
0x18018fa0d  call    ?Ext_GetStaticPublisher@@YAXPEAG_K@Z; Ext_GetStaticPublisher(ushort *,unsigned __int64)
0x18018fa12  lea     rcx, [rbp+1690h+Buffer]; lpBuffer
0x18018fa19  call    ?Ext_GetStaticDisplayName@@YAXPEAG_K@Z; Ext_GetStaticDisplayName(ushort *,unsigned __int64)
0x18018fa1e  mov     [rbp+1690h+var_1080], di
0x18018fa25  lea     rsi, [r15+30h]
0x18018fa29  mov     rcx, [rsi]; pv
0x18018fa2c  call    cs:__imp_CoTaskMemFree
0x18018fa32  mov     [rsi], rdi
0x18018fa35  lea     rdi, [r15+38h]
0x18018fa39  mov     rcx, [rdi]; pv
0x18018fa3c  call    cs:__imp_CoTaskMemFree
0x18018fa42  lea     rbx, [r15+60h]
0x18018fa46  mov     qword ptr [rdi], 0
0x18018fa4d  mov     rcx, [rbx]; pv
0x18018fa50  call    cs:__imp_CoTaskMemFree
0x18018fa56  mov     rdx, rsi; ppwsz
0x18018fa59  mov     qword ptr [rbx], 0
0x18018fa60  lea     rcx, [rbp+1690h+var_16A0]; psz
0x18018fa64  call    cs:__imp_SHStrDupW
0x18018fa6a  mov     rdx, rdi; ppwsz
0x18018fa6d  lea     rcx, [rbp+1690h+Buffer]; psz
0x18018fa74  call    cs:__imp_SHStrDupW
0x18018fa7a  mov     rdx, rbx; ppwsz
0x18018fa7d  lea     rcx, [rbp+1690h+var_1080]; psz
0x18018fa84  call    cs:__imp_SHStrDupW
0x18018fa8a  mov     rcx, [r13+0]; psa
0x18018fa8e  lea     r8, [rbp+1690h+var_16D8]; pv
0x18018fa92  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x18018fa97  mov     [rsp+1790h+rgIndices], 1
0x18018fa9f  call    cs:__imp_SafeArrayGetElement
0x18018faa5  test    eax, eax
0x18018faa7  js      short loc_18018FABA
0x18018faa9  cmp     word ptr [rbp+1690h+var_16D8], 13h
0x18018faae  jnz     short loc_18018FABA
0x18018fab0  mov     eax, dword ptr [rbp+1690h+var_16D8+8]
0x18018fab3  mov     [r15+98h], eax
0x18018faba  cmp     dword ptr [r15+98h], 2
0x18018fac2  jnz     short loc_18018FAFB
0x18018fac4  mov     rcx, [r13+0]; psa
0x18018fac8  lea     r8, [rsp+1790h+lpsz]; pv
0x18018facd  lea     rdx, [rsp+1790h+rgIndices]; rgIndices
0x18018fad2  mov     [rsp+1790h+rgIndices], 2
0x18018fada  call    cs:__imp_SafeArrayGetElement
  ... truncated ...
```
