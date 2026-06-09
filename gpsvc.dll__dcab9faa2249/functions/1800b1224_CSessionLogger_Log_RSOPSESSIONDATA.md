# CSessionLogger::Log(_RSOPSESSIONDATA *)

- ea: `0x1800b1224`
- end: `0x1800b1f63`
- name: `?Log@CSessionLogger@@QEAAHPEAU_RSOPSESSIONDATA@@@Z`
- size: `3391`
- prototype: `__int64 __fastcall(CSessionLogger *__hidden this, struct _RSOPSESSIONDATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800ad3cc`

## callees

- `0x18004b210`
- `0x1800535a0`
- `0x1800585e8`
- `0x18005ce04`
- `0x180062e10`
- `0x180075ec0`
- `0x180076054`
- `0x1800762fc`
- `0x18007d320`
- `0x1800b1224`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800b1dc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800b1dc3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1323`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1336`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1619`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b16a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1878`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1981`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1c36`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1e32`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1e3c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1e46`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1e50`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1ee3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1eed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1ef7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1f01`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1f1f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1f33`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1323`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1336`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1619`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b16a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1878`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1981`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1c36`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1e32`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1e3c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1e46`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1e50`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1ee3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1eed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1ef7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1f01`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1f1f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1f33`
- `OLEAUT32!__imp_VariantInit` at `0x1800b1391`
- `OLEAUT32!__imp_VariantInit` at `0x1800b1391`
- `OLEAUT32!__imp_VariantClear` at `0x1800b144e`
- `OLEAUT32!__imp_VariantClear` at `0x1800b144e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800b14f9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800b14f9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800b1492`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800b1492`

## string_xrefs

- `0x1800b14b8`: `CSessionLogger::Log: SafeArrayCopy failed. hr=0x%08X.`
- `0x1800b14e1`: `CSessionLogger::Log: SafeArrayCopy failed. hr=0x%08X.`
- `0x1800b1a85`: `CSessionLogger::Log: logging new security grps`
- `0x1800b1aa0`: `CSessionLogger::Log: logging new security grps`
- `0x1800b1abe`: `CSessionLogger::Log: logging new security grps because it wasn't defined before`
- `0x1800b1ae3`: `CSessionLogger::Log: logging new security grps because it wasn't defined before`
- `0x1800b1b10`: `CSessionLogger::Log: restoring old security grps`
- `0x1800b1b35`: `CSessionLogger::Log: restoring old security grps`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CSessionLogger::Log(unsigned __int16 **this, struct _RSOPSESSIONDATA *a2)
{
  OLECHAR *v5; // rbx
  OLECHAR *v6; // rdi
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rcx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HRESULT v12; // eax
  int v13; // eax
  OLECHAR *v14; // rsi
  OLECHAR *v15; // rcx
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax
  int v20; // eax
  OLECHAR *v21; // r15
  OLECHAR *v22; // rcx
  int v23; // eax
  OLECHAR *v24; // r12
  OLECHAR *v25; // rcx
  int v26; // eax
  __int64 v27; // r8
  int v28; // ecx
  void (*v29)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v30; // rdx
  int v31; // eax
  OLECHAR *v32; // r14
  OLECHAR *v33; // rcx
  CSessionLogger *v34; // r13
  int v35; // eax
  __int64 v36; // r8
  void (*v37)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v38; // rdx
  int v39; // eax
  int v40; // eax
  unsigned int v41; // r13d
  SAFEARRAY *ppsaOut; // [rsp+40h] [rbp-79h] BYREF
  __int64 v43; // [rsp+48h] [rbp-71h] BYREF
  VARIANTARG *p_pvarg; // [rsp+50h] [rbp-69h] BYREF
  struct IWbemClassObject *v45; // [rsp+58h] [rbp-61h] BYREF
  __int64 v46; // [rsp+60h] [rbp-59h] BYREF
  SAFEARRAY *v47; // [rsp+68h] [rbp-51h]
  __int64 v48; // [rsp+70h] [rbp-49h]
  CSessionLogger *v49; // [rsp+78h] [rbp-41h]
  BSTR v50; // [rsp+80h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-31h] BYREF
  BSTR v52; // [rsp+A0h] [rbp-19h] BYREF
  BSTR v53; // [rsp+A8h] [rbp-11h] BYREF
  BSTR v54; // [rsp+B0h] [rbp-9h] BYREF
  BSTR v55; // [rsp+B8h] [rbp-1h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+7h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp+Fh] BYREF

  v49 = (CSessionLogger *)this;
  if ( !*(_DWORD *)this )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CSessionLogger::Log: Failed to initialize.");
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"CSessionLogger::Log: Failed to initialize.");
      }
    }
    return 0;
  }
  v5 = 0;
  v50 = 0;
  ppsaOut = 0;
  XBStr::XBStr((XBStr *)&bstrString, L"RSOP_Session.id=\"Session1\"");
  v6 = bstrString;
  if ( !bstrString )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg((_DWORD)bstrString + 2, L"CSessionLogger::Log: Failed to allocate memory.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CSessionLogger::Log: Failed to allocate memory.");
      }
    }
    v7 = 0;
    goto LABEL_17;
  }
  v43 = 0;
  v9 = (*(__int64 (__fastcall **)(unsigned __int16 *, BSTR, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)this[12]
                                                                                              + 48LL))(
         this[12],
         bstrString,
         0,
         0,
         &v43,
         0);
  if ( v9 < 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CSessionLogger::Log: GetObject failed. hr=0x%08X", (unsigned int)v9);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CSessionLogger::Log: GetObject failed. hr=0x%08X", (unsigned int)v9);
      }
    }
  }
  else
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    p_pvarg = &pvarg;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v43 + 32LL))(
            v43,
            this[8],
            0,
            &pvarg,
            0,
            0);
    if ( v10 < 0 || pvarg.vt == 1 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CSessionLogger::Log: Get failed. hr=0x%08X.", (unsigned int)v10);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CSessionLogger::Log: Get failed. hr=0x%08X.", (unsigned int)v10);
        }
      }
    }
    else
    {
      XBStr::operator=(&v50, pvarg.bstrVal);
      v5 = v50;
      if ( !v50 )
      {
        XVariant::~XVariant(&p_pvarg);
LABEL_24:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        v7 = v6;
LABEL_17:
        SysFreeString(v7);
        XSafeArray::~XSafeArray((XSafeArray *)&ppsaOut);
        v8 = 0;
LABEL_18:
        SysFreeString(v8);
        return 0;
      }
    }
    VariantClear(&pvarg);
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v43 + 32LL))(
            v43,
            this[6],
            0,
            &pvarg,
            0,
            0);
    if ( v11 < 0 || pvarg.vt == 1 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CSessionLogger::Log: Get failed. hr=0x%08X.", (unsigned int)v11);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CSessionLogger::Log: Get failed. hr=0x%08X.", (unsigned int)v11);
        }
      }
    }
    else
    {
      v12 = SafeArrayCopy(pvarg.parray, &ppsaOut);
      if ( v12 < 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"CSessionLogger::Log: SafeArrayCopy failed. hr=0x%08X.", (unsigned int)v12);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"CSessionLogger::Log: SafeArrayCopy failed. hr=0x%08X.", (unsigned int)v12);
          }
        }
        if ( ppsaOut )
          SafeArrayDestroy(ppsaOut);
        ppsaOut = 0;
      }
    }
    XVariant::~XVariant(&p_pvarg);
  }
  v45 = 0;
  v13 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, struct IWbemClassObject **))(*(_QWORD *)this[11] + 120LL))(
          this[11],
          0,
          &v45);
  if ( v13 < 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CSessionLogger::Log: SpawnInstance failed with 0x%x", (unsigned int)v13);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CSessionLogger::Log: SpawnInstance failed with 0x%x", (unsigned int)v13);
      }
    }
    goto LABEL_63;
  }
  p_pvarg = (VARIANTARG *)v45;
  XBStr::XBStr((XBStr *)&v52, L"Session1");
  v14 = v52;
  if ( !v52 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg((_DWORD)v52 + 2, L"CSessionLogger::Log: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CSessionLogger::Log: Failed to allocate memory");
      }
    }
    v15 = 0;
    goto LABEL_72;
  }
  v46 = 8;
  v48 = 0;
  v47 = (SAFEARRAY *)v52;
  v16 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
          v45,
          this[1],
          0,
          &v46,
          0);
  v17 = (unsigned int)v16;
  if ( v16 < 0 )
    goto LABEL_74;
  LOWORD(v46) = 3;
  LODWORD(v47) = 2228228;
  v18 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
          v45,
          this[2],
          0,
          &v46,
          0);
  v17 = (unsigned int)v18;
  if ( v18 < 0 )
    goto LABEL_74;
  LOWORD(v46) = 3;
  LODWORD(v47) = *((_DWORD *)a2 + 12);
  v19 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
          v45,
          this[3],
          0,
          &v46,
          0);
  v17 = (unsigned int)v19;
  if ( v19 < 0 )
    goto LABEL_74;
  LOWORD(v46) = 11;
  LOWORD(v47) = *((_DWORD *)a2 + 11) ? -1 : 0;
  v20 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
          v45,
          this[9],
          0,
          &v46,
          0);
  v17 = (unsigned int)v20;
  if ( v20 < 0 )
  {
LABEL_74:
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CSessionLogger::Log: Put failed with 0x%x", v17);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CSessionLogger::Log: Put failed with 0x%x", v17);
      }
    }
    goto LABEL_80;
  }
  XBStr::XBStr((XBStr *)&v53, *(const unsigned __int16 **)a2);
  v21 = v53;
  if ( *(_QWORD *)a2 )
  {
    if ( !v53 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg((_DWORD)v53 + 2, L"CSessionLogger::Log: Failed to allocate memory");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CSessionLogger::Log: Failed to allocate memory");
        }
      }
      v22 = 0;
      goto LABEL_96;
    }
    LOWORD(v46) = 8;
    v47 = (SAFEARRAY *)v53;
    v23 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
            v45,
            this[4],
            0,
            &v46,
            0);
    if ( v23 < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CSessionLogger::Log: Put failed with 0x%x", (unsigned int)v23);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CSessionLogger::Log: Put failed with 0x%x", (unsigned int)v23);
        }
      }
      goto LABEL_104;
    }
  }
  XBStr::XBStr((XBStr *)&v54, *((const unsigned __int16 **)a2 + 1));
  v24 = v54;
  if ( *((_QWORD *)a2 + 1) )
  {
    if ( !v54 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg((_DWORD)v54 + 2, L"CSessionLogger::Log: Failed to allocate memory");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CSessionLogger::Log: Failed to allocate memory");
        }
      }
      v25 = 0;
      goto LABEL_114;
    }
    LOWORD(v46) = 8;
    v47 = (SAFEARRAY *)v54;
    v26 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
            v45,
            this[5],
            0,
            &v46,
            0);
    v27 = (unsigned int)v26;
    if ( v26 < 0 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
      {
LABEL_123:
        v25 = v24;
LABEL_114:
        SysFreeString(v25);
LABEL_104:
        v22 = v21;
LABEL_96:
        SysFreeString(v22);
LABEL_80:
        v15 = v14;
LABEL_72:
        SysFreeString(v15);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&p_pvarg);
LABEL_63:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        SysFreeString(v6);
        XSafeArray::~XSafeArray((XSafeArray *)&ppsaOut);
        v8 = v5;
        goto LABEL_18;
      }
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CSessionLogger::Log: Put failed with 0x%x", (unsigned int)v26);
        goto LABEL_123;
      }
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
        goto LABEL_123;
LABEL_122:
      RedirectDebugMsg(2u, L"CSessionLogger::Log: Put failed with 0x%x", v27);
      goto LABEL_123;
    }
    goto LABEL_130;
  }
  v28 = *(_DWORD *)&g_dwDebugLevel;
  if ( !*(_DWORD *)&g_dwDebugLevel )
  {
LABEL_131:
    v29 = g_lpDebugMsg;
    goto LABEL_132;
  }
  v29 = g_lpDebugMsg;
  if ( g_lpDebugMsg )
  {
    g_lpDebugMsg(4u, L"CSessionLogger::Log: new SOM is NULL");
LABEL_130:
    v28 = *(_DWORD *)&g_dwDebugLevel;
    goto LABEL_131;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
  {
    RedirectDebugMsg(4u, L"CSessionLogger::Log: new SOM is NULL");
    goto LABEL_130;
  }
LABEL_132:
  if ( *((_DWORD *)a2 + 6) )
  {
    if ( v28 )
    {
      if ( !v29 )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(4u, L"CSessionLogger::Log: logging new security grps");
        goto LABEL_148;
      }
      v30 = L"CSessionLogger::Log: logging new security grps";
      goto LABEL_144;
    }
    goto LABEL_148;
  }
  if ( *((_QWORD *)a2 + 2) && !ppsaOut )
  {
    if ( v28 )
    {
      if ( !v29 )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(4u, L"CSessionLogger::Log: logging new security grps because it wasn't defined before");
        goto LABEL_148;
      }
      v30 = L"CSessionLogger::Log: logging new security grps because it wasn't defined before";
LABEL_144:
      v29(4u, v30);
    }
LABEL_148:
    v31 = LogSecurityGroups(v45, this[6], *((struct _TOKEN_GROUPS **)a2 + 2));
    goto LABEL_156;
  }
  if ( v28 )
  {
    if ( v29 )
    {
      v29(4u, L"CSessionLogger::Log: restoring old security grps");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CSessionLogger::Log: restoring old security grps");
    }
  }
  LOWORD(v46) = 8200;
  v47 = ppsaOut;
  v31 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
          v45,
          this[6],
          0,
          &v46,
          0);
LABEL_156:
  if ( v31 < 0 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_123;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"CSessionLogger::Log: Put failed with 0x%x", (unsigned int)v31);
      goto LABEL_123;
    }
    if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      goto LABEL_123;
    v27 = (unsigned int)v31;
    goto LABEL_122;
  }
  XBStr::XBStr((XBStr *)&v55, *((const unsigned __int16 **)a2 + 4));
  v32 = v55;
  if ( *((_QWORD *)a2 + 4) )
  {
    if ( !v55 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg((_DWORD)v55 + 2, L"CSessionLogger::Log: Failed to allocate memory");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CSessionLogger::Log: Failed to allocate memory");
        }
      }
      v33 = 0;
      goto LABEL_172;
    }
    LOWORD(v46) = 8;
    v47 = (SAFEARRAY *)v55;
    v34 = v49;
    v35 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
            v45,
            *((_QWORD *)v49 + 7),
            0,
            &v46,
            0);
    v36 = (unsigned int)v35;
    if ( v35 < 0 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
      {
LABEL_181:
        v33 = v32;
LABEL_172:
        SysFreeString(v33);
        goto LABEL_123;
      }
      v37 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"CSessionLogger::Log: Put failed with 0x%x", v36);
        goto LABEL_181;
      }
      v38 = L"CSessionLogger::Log: Put failed with 0x%x";
LABEL_177:
      v37(2u, v38, v36);
      goto LABEL_181;
    }
  }
  else
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CSessionLogger::Log: new Site is NULL");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CSessionLogger::Log: new Site is NULL");
      }
    }
    v34 = v49;
  }
  SystemTime = 0;
  if ( v5 )
  {
    LOWORD(v46) = 8;
    v47 = (SAFEARRAY *)__PAIR64__(HIDWORD(v50), (unsigned int)v5);
    v39 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, _QWORD, __int64 *, _DWORD))v45->lpVtbl->Put)(
            v45,
            *((_QWORD *)v34 + 8),
            0,
            &v46,
            0);
    v36 = (unsigned int)v39;
    if ( v39 < 0 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_181;
      v37 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"CSessionLogger::Log: Put failed for creationtime with 0x%x", v36);
        goto LABEL_181;
      }
      v38 = L"CSessionLogger::Log: Put failed for creationtime with 0x%x";
      goto LABEL_177;
    }
  }
  else
  {
    GetSystemTime(&SystemTime);
    if ( !(unsigned int)LogTimeProperty(v45, *((unsigned __int16 **)v34 + 8), &SystemTime) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CSessionLogger::Log: LogTimeProperty failed");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CSessionLogger::Log: LogTimeProperty failed");
        }
      }
      SysFreeString(v32);
      SysFreeString(v24);
      SysFreeString(v21);
      SysFreeString(v14);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&p_pvarg);
      goto LABEL_24;
    }
  }
  v40 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v34 + 12)
                                                                                             + 112LL))(
          *((_QWORD *)v34 + 12),
          v45,
          0,
          0,
          0);
  v41 = 0;
  if ( v40 >= 0 )
  {
    v41 = 1;
  }
  else if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"CSessionLogger::Log: PutInstance failed with 0x%x", (unsigned int)v40);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"CSessionLogger::Log: PutInstance failed with 0x%x", (unsigned int)v40);
    }
  }
  SysFreeString(v32);
  SysFreeString(v24);
  SysFreeString(v21);
  SysFreeString(v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&p_pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
  SysFreeString(v6);
  XSafeArray::~XSafeArray((XSafeArray *)&ppsaOut);
  SysFreeString(v5);
  return v41;
}

```

## disassembly

```asm
0x1800b1224  mov     [rsp-8+arg_10], rbx
0x1800b1229  push    rbp
0x1800b122a  push    rsi
0x1800b122b  push    rdi
0x1800b122c  push    r12
0x1800b122e  push    r13
0x1800b1230  push    r14
0x1800b1232  push    r15
0x1800b1234  lea     rbp, [rsp-27h]
0x1800b1239  sub     rsp, 0E0h
0x1800b1240  mov     rax, cs:__security_cookie
0x1800b1247  xor     rax, rsp
0x1800b124a  mov     [rbp+57h+var_38], rax
0x1800b124e  mov     r13, rdx
0x1800b1251  mov     r14, rcx
0x1800b1254  mov     [rbp+57h+var_98], rcx
0x1800b1258  xor     r12d, r12d
0x1800b125b  cmp     [rcx], r12d
0x1800b125e  jnz     short loc_1800B12B2
0x1800b1260  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b1267  jz      short loc_1800B12AB
0x1800b1269  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b1270  test    rax, rax
0x1800b1273  jz      short loc_1800B1288
0x1800b1275  lea     rdx, aCsessionlogger_4; "CSessionLogger::Log: Failed to initiali"...
0x1800b127c  lea     ecx, [r12+2]
0x1800b1281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1286  jmp     short loc_1800B12AB
0x1800b1288  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b128f  jz      short loc_1800B12AB
0x1800b1291  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b1298  jz      short loc_1800B12AB
0x1800b129a  lea     rdx, aCsessionlogger_4; "CSessionLogger::Log: Failed to initiali"...
0x1800b12a1  mov     ecx, 2; unsigned int
0x1800b12a6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b12ab  xor     eax, eax
0x1800b12ad  jmp     loc_1800B1F3C
0x1800b12b2  mov     rbx, r12
0x1800b12b5  mov     [rbp+57h+var_90], rbx
0x1800b12b9  mov     [rbp+57h+ppsaOut], r12
0x1800b12bd  lea     rdx, aRsopSessionIdS; "RSOP_Session.id=\"Session1\""
0x1800b12c4  lea     rcx, [rbp+57h+bstrString]; this
0x1800b12c8  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800b12cd  nop
0x1800b12ce  mov     rdi, [rbp+57h+bstrString]
0x1800b12d2  test    rdi, rdi
0x1800b12d5  jnz     short loc_1800B1341
0x1800b12d7  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b12de  jz      short loc_1800B1321
0x1800b12e0  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b12e7  test    rax, rax
0x1800b12ea  jz      short loc_1800B12FD
0x1800b12ec  lea     rdx, aCsessionlogger; "CSessionLogger::Log: Failed to allocate"...
0x1800b12f3  lea     ecx, [rdi+2]
0x1800b12f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b12fb  jmp     short loc_1800B1321
0x1800b12fd  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b1304  jz      short loc_1800B1321
0x1800b1306  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b130d  jz      short loc_1800B1321
0x1800b130f  lea     rdx, aCsessionlogger; "CSessionLogger::Log: Failed to allocate"...
0x1800b1316  mov     ecx, 2; unsigned int
0x1800b131b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b1320  nop
0x1800b1321  xor     ecx, ecx; bstrString
0x1800b1323  call    cs:__imp_SysFreeString
0x1800b1329  nop
0x1800b132a  lea     rcx, [rbp+57h+ppsaOut]; this
0x1800b132e  call    ??1XSafeArray@@QEAA@XZ; XSafeArray::~XSafeArray(void)
0x1800b1333  nop
0x1800b1334  xor     ecx, ecx; bstrString
0x1800b1336  call    cs:__imp_SysFreeString
0x1800b133c  jmp     loc_1800B12AB
0x1800b1341  mov     [rbp+57h+var_C8], r12
0x1800b1345  mov     rcx, [r14+60h]
0x1800b1349  mov     rax, [rcx]
0x1800b134c  mov     [rsp+110h+var_E8], r12
0x1800b1351  lea     rdx, [rbp+57h+var_C8]
0x1800b1355  mov     [rsp+110h+var_F0], rdx
0x1800b135a  xor     r9d, r9d
0x1800b135d  xor     r8d, r8d
0x1800b1360  mov     rdx, rdi
0x1800b1363  mov     rax, [rax+30h]
0x1800b1367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b136c  mov     r8d, eax
0x1800b136f  mov     esi, 1
0x1800b1374  lea     r15d, [rsi+3]
0x1800b1378  test    eax, eax
0x1800b137a  js      loc_1800B1558
0x1800b1380  xorps   xmm0, xmm0
0x1800b1383  xor     eax, eax
0x1800b1385  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800b1389  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800b138d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800b1391  call    cs:__imp_VariantInit
0x1800b1397  lea     rax, [rbp+57h+pvarg]
0x1800b139b  mov     [rbp+57h+var_C0], rax
0x1800b139f  mov     rcx, [rbp+57h+var_C8]
0x1800b13a3  mov     rax, [rcx]
0x1800b13a6  mov     [rsp+110h+var_E8], r12
0x1800b13ab  mov     [rsp+110h+var_F0], r12
0x1800b13b0  lea     r9, [rbp+57h+pvarg]
0x1800b13b4  xor     r8d, r8d
0x1800b13b7  mov     rdx, [r14+40h]
0x1800b13bb  mov     rax, [rax+20h]
0x1800b13bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b13c4  mov     r8d, eax
0x1800b13c7  test    eax, eax
0x1800b13c9  js      short loc_1800B1403
0x1800b13cb  cmp     word ptr [rbp+57h+pvarg], si
0x1800b13cf  jz      short loc_1800B1403
0x1800b13d1  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x1800b13d5  lea     rcx, [rbp+57h+var_90]
0x1800b13d9  call    ??4XBStr@@QEAAXPEBG@Z; XBStr::operator=(ushort const *)
0x1800b13de  mov     rbx, [rbp+57h+var_90]
0x1800b13e2  test    rbx, rbx
0x1800b13e5  jnz     short loc_1800B144A
0x1800b13e7  lea     rcx, [rbp+57h+var_C0]; this
0x1800b13eb  call    ??1XVariant@@QEAA@XZ; XVariant::~XVariant(void)
0x1800b13f0  nop
0x1800b13f1  lea     rcx, [rbp+57h+var_C8]
0x1800b13f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b13fa  nop
0x1800b13fb  mov     rcx, rdi
0x1800b13fe  jmp     loc_1800B1323
0x1800b1403  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b140a  jz      short loc_1800B144A
0x1800b140c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b1413  test    rax, rax
0x1800b1416  jz      short loc_1800B1429
0x1800b1418  lea     rdx, aCsessionlogger_18; "CSessionLogger::Log: Get failed. hr=0x%"...
0x1800b141f  mov     ecx, r15d
0x1800b1422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1427  jmp     short loc_1800B144A
0x1800b1429  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b1430  jz      short loc_1800B144A
0x1800b1432  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b1439  jz      short loc_1800B144A
0x1800b143b  lea     rdx, aCsessionlogger_18; "CSessionLogger::Log: Get failed. hr=0x%"...
0x1800b1442  mov     ecx, r15d; unsigned int
0x1800b1445  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b144a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800b144e  call    cs:__imp_VariantClear
0x1800b1454  mov     rcx, [rbp+57h+var_C8]
0x1800b1458  mov     rax, [rcx]
0x1800b145b  mov     [rsp+110h+var_E8], r12
0x1800b1460  mov     [rsp+110h+var_F0], r12
0x1800b1465  lea     r9, [rbp+57h+pvarg]
0x1800b1469  xor     r8d, r8d
0x1800b146c  mov     rdx, [r14+30h]
0x1800b1470  mov     rax, [rax+20h]
0x1800b1474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1479  mov     r8d, eax
0x1800b147c  test    eax, eax
0x1800b147e  js      loc_1800B1505
0x1800b1484  cmp     word ptr [rbp+57h+pvarg], si
0x1800b1488  jz      short loc_1800B1505
0x1800b148a  lea     rdx, [rbp+57h+ppsaOut]; ppsaOut
0x1800b148e  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800b1492  call    cs:__imp_SafeArrayCopy
0x1800b1498  test    eax, eax
0x1800b149a  jns     loc_1800B154D
0x1800b14a0  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b14a7  jz      short loc_1800B14F0
0x1800b14a9  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b14b0  test    r9, r9
0x1800b14b3  jz      short loc_1800B14CC
0x1800b14b5  mov     r8d, eax
0x1800b14b8  lea     rdx, aCsessionlogger_7; "CSessionLogger::Log: SafeArrayCopy fail"...
0x1800b14bf  mov     ecx, r15d
0x1800b14c2  mov     rax, r9
0x1800b14c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b14ca  jmp     short loc_1800B14F0
0x1800b14cc  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b14d3  jz      short loc_1800B14F0
0x1800b14d5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b14dc  jz      short loc_1800B14F0
0x1800b14de  mov     r8d, eax
0x1800b14e1  lea     rdx, aCsessionlogger_7; "CSessionLogger::Log: SafeArrayCopy fail"...
0x1800b14e8  mov     ecx, r15d; unsigned int
0x1800b14eb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b14f0  mov     rcx, [rbp+57h+ppsaOut]; psa
0x1800b14f4  test    rcx, rcx
0x1800b14f7  jz      short loc_1800B14FF
0x1800b14f9  call    cs:__imp_SafeArrayDestroy
0x1800b14ff  mov     [rbp+57h+ppsaOut], r12
0x1800b1503  jmp     short loc_1800B154D
0x1800b1505  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b150c  jz      short loc_1800B154D
0x1800b150e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b1515  test    rax, rax
0x1800b1518  jz      short loc_1800B152B
0x1800b151a  lea     rdx, aCsessionlogger_18; "CSessionLogger::Log: Get failed. hr=0x%"...
0x1800b1521  mov     ecx, r15d
0x1800b1524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1529  jmp     short loc_1800B154D
0x1800b152b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b1532  jz      short loc_1800B154D
0x1800b1534  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b153b  jz      short loc_1800B154D
0x1800b153d  lea     rdx, aCsessionlogger_18; "CSessionLogger::Log: Get failed. hr=0x%"...
0x1800b1544  mov     ecx, r15d; unsigned int
0x1800b1547  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b154c  nop
0x1800b154d  lea     rcx, [rbp+57h+var_C0]; this
0x1800b1551  call    ??1XVariant@@QEAA@XZ; XVariant::~XVariant(void)
0x1800b1556  jmp     short loc_1800B159F
0x1800b1558  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b155f  jz      short loc_1800B159F
0x1800b1561  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b1568  test    rax, rax
0x1800b156b  jz      short loc_1800B157E
0x1800b156d  lea     rdx, aCsessionlogger_0; "CSessionLogger::Log: GetObject failed. "...
0x1800b1574  mov     ecx, r15d
0x1800b1577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b157c  jmp     short loc_1800B159F
0x1800b157e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b1585  jz      short loc_1800B159F
0x1800b1587  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b158e  jz      short loc_1800B159F
0x1800b1590  lea     rdx, aCsessionlogger_0; "CSessionLogger::Log: GetObject failed. "...
0x1800b1597  mov     ecx, r15d; unsigned int
0x1800b159a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b159f  mov     [rbp+57h+var_B8], r12
0x1800b15a3  mov     rcx, [r14+58h]
0x1800b15a7  mov     rax, [rcx]
0x1800b15aa  lea     r8, [rbp+57h+var_B8]
0x1800b15ae  xor     edx, edx
0x1800b15b0  mov     rax, [rax+78h]
0x1800b15b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b15b9  mov     r8d, eax
0x1800b15bc  test    eax, eax
0x1800b15be  jns     short loc_1800B1632
0x1800b15c0  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b15c7  jz      short loc_1800B160C
0x1800b15c9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b15d0  test    rax, rax
0x1800b15d3  jz      short loc_1800B15E8
0x1800b15d5  lea     rdx, aCsessionlogger_11; "CSessionLogger::Log: SpawnInstance fail"...
0x1800b15dc  mov     ecx, 2
0x1800b15e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b15e6  jmp     short loc_1800B160C
0x1800b15e8  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b15ef  jz      short loc_1800B160C
0x1800b15f1  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b15f8  jz      short loc_1800B160C
0x1800b15fa  lea     rdx, aCsessionlogger_11; "CSessionLogger::Log: SpawnInstance fail"...
0x1800b1601  mov     ecx, 2; unsigned int
0x1800b1606  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b160b  nop
0x1800b160c  lea     rcx, [rbp+57h+var_C8]
0x1800b1610  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b1615  nop
0x1800b1616  mov     rcx, rdi; bstrString
0x1800b1619  call    cs:__imp_SysFreeString
0x1800b161f  nop
0x1800b1620  lea     rcx, [rbp+57h+ppsaOut]; this
0x1800b1624  call    ??1XSafeArray@@QEAA@XZ; XSafeArray::~XSafeArray(void)
0x1800b1629  nop
0x1800b162a  mov     rcx, rbx
0x1800b162d  jmp     loc_1800B1336
0x1800b1632  mov     rax, [rbp+57h+var_B8]
0x1800b1636  mov     [rbp+57h+var_C0], rax
0x1800b163a  lea     rdx, aSession1; "Session1"
0x1800b1641  lea     rcx, [rbp+57h+var_70]; this
0x1800b1645  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800b164a  nop
0x1800b164b  mov     rsi, [rbp+57h+var_70]
0x1800b164f  test    rsi, rsi
0x1800b1652  jnz     short loc_1800B16B5
0x1800b1654  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800b165b  jz      short loc_1800B169E
0x1800b165d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b1664  test    rax, rax
0x1800b1667  jz      short loc_1800B167A
0x1800b1669  lea     rdx, aCsessionlogger_1; "CSessionLogger::Log: Failed to allocate"...
0x1800b1670  lea     ecx, [rsi+2]
0x1800b1673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1678  jmp     short loc_1800B169E
0x1800b167a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800b1681  jz      short loc_1800B169E
0x1800b1683  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b168a  jz      short loc_1800B169E
0x1800b168c  lea     rdx, aCsessionlogger_1; "CSessionLogger::Log: Failed to allocate"...
0x1800b1693  mov     ecx, 2; unsigned int
0x1800b1698  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b169d  nop
0x1800b169e  xor     ecx, ecx; bstrString
0x1800b16a0  call    cs:__imp_SysFreeString
0x1800b16a6  nop
0x1800b16a7  lea     rcx, [rbp+57h+var_C0]
0x1800b16ab  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b16b0  jmp     loc_1800B160C
0x1800b16b5  xorps   xmm0, xmm0
0x1800b16b8  xor     eax, eax
0x1800b16ba  movups  [rbp+57h+var_B0], xmm0
0x1800b16be  mov     [rbp+57h+var_A0], rax
0x1800b16c2  mov     eax, 8
0x1800b16c7  mov     word ptr [rbp+57h+var_B0], ax
0x1800b16cb  mov     dword ptr [rbp+57h+var_B0+8], esi
  ... truncated ...
```
