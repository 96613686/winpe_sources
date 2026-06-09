# GarbageCollectNamespace(ushort *,IWbemServices *,ulong)

- ea: `0x1800206dc`
- end: `0x1800213a6`
- name: `?GarbageCollectNamespace@@YAJPEAGPEAUIWbemServices@@K@Z`
- size: `3274`
- prototype: `int(unsigned __int16 *, struct IWbemServices *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800589b8`

## callees

- `0x18000a504`
- `0x1800206dc`
- `0x180022bd4`
- `0x1800535a0`
- `0x1800585e8`
- `0x180063da4`
- `0x18006b5f0`
- `0x180072f8c`
- `0x180075ec0`
- `0x1800adfc8`
- `0x1800b8358`
- `0x1800b85e8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180020ab0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180020ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020ad9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020ad9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020951`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020b81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020951`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020b81`
- `OLEAUT32!__imp_SysAllocString` at `0x1800207b9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800208ce`
- `OLEAUT32!__imp_SysAllocString` at `0x180020a68`
- `OLEAUT32!__imp_SysAllocString` at `0x1800207b9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800208ce`
- `OLEAUT32!__imp_SysAllocString` at `0x180020a68`
- `OLEAUT32!__imp_SysFreeString` at `0x180020817`
- `OLEAUT32!__imp_SysFreeString` at `0x1800208b2`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d91`
- `OLEAUT32!__imp_SysFreeString` at `0x180020e69`
- `OLEAUT32!__imp_SysFreeString` at `0x180020ec8`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180021158`
- `OLEAUT32!__imp_SysFreeString` at `0x18002116c`
- `OLEAUT32!__imp_SysFreeString` at `0x180021176`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180021251`
- `OLEAUT32!__imp_SysFreeString` at `0x18002125b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212ba`
- `OLEAUT32!__imp_SysFreeString` at `0x180021347`
- `OLEAUT32!__imp_SysFreeString` at `0x180021351`
- `OLEAUT32!__imp_SysFreeString` at `0x180020817`
- `OLEAUT32!__imp_SysFreeString` at `0x1800208b2`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d91`
- `OLEAUT32!__imp_SysFreeString` at `0x180020e69`
- `OLEAUT32!__imp_SysFreeString` at `0x180020ec8`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f3f`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800210c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180021158`
- `OLEAUT32!__imp_SysFreeString` at `0x18002116c`
- `OLEAUT32!__imp_SysFreeString` at `0x180021176`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180021251`
- `OLEAUT32!__imp_SysFreeString` at `0x18002125b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212ba`
- `OLEAUT32!__imp_SysFreeString` at `0x180021347`
- `OLEAUT32!__imp_SysFreeString` at `0x180021351`
- `OLEAUT32!__imp_VariantInit` at `0x180020a08`
- `OLEAUT32!__imp_VariantInit` at `0x180020a08`
- `OLEAUT32!__imp_VariantClear` at `0x180020a79`
- `OLEAUT32!__imp_VariantClear` at `0x180020a79`

## string_xrefs

- `0x180020766`: `GarbageCollectNamespace: OpenNamespace failed. hr=0x%08X`
- `0x180020798`: `GarbageCollectNamespace: OpenNamespace failed. hr=0x%08X`
- `0x180020875`: `GarbageCollectNamespace: CreateInstanceEnum failed. hr=0x%08X`
- `0x18002089d`: `GarbageCollectNamespace: CreateInstanceEnum failed. hr=0x%08X`
- `0x180020974`: `GarbageCollectNamespace: Profile key open failed.`
- `0x1800209a4`: `GarbageCollectNamespace: Profile key open failed.`
- `0x180021063`: `GarbageCollectNamespace: ConvertWMINameToSid failed. hr=0x%x`
- `0x18002108b`: `GarbageCollectNamespace: ConvertWMINameToSid failed. hr=0x%x`
- `0x180020b29`: `GarbageCollectNamespace: Converted WMI namespace:%ws to SID %ws\n`
- `0x180020b53`: `GarbageCollectNamespace: Converted WMI namespace:%ws to SID %ws\n`
- `0x180020e18`: `GarbageCollectNamespace: Profile for SID %ws exists. Not garbage collecting.\n`
- `0x180020e40`: `GarbageCollectNamespace: Profile for SID %ws exists. Not garbage collecting.\n`
- `0x180020ba7`: `GarbageCollectNamespace: Profile for SID %ws does not exists. Consider for garbage collecting.\n`
- `0x180020bcf`: `GarbageCollectNamespace: Profile for SID %ws does not exists. Consider for garbage collecting.\n`
- `0x180020ff9`: `GarbageCollectNamespace: OpenNamespace returned 0x%x`
- `0x180021021`: `GarbageCollectNamespace: OpenNamespace returned 0x%x`
- `0x180020e8b`: `GarbageCollectNamespace: DeleteInstance returned 0x%x`
- `0x180020eb3`: `GarbageCollectNamespace: DeleteInstance returned 0x%x`
- `0x180020d52`: `GarbageCollectNamespace: Deleted namespace:%ws\%ws\n`
- `0x180020d7c`: `GarbageCollectNamespace: Deleted namespace:%ws\%ws\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall GarbageCollectNamespace(unsigned __int16 *a1, struct IWbemServices *a2, unsigned int a3)
{
  unsigned int v5; // ebx
  OLECHAR *v6; // rdi
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rsi
  OLECHAR *v9; // rcx
  unsigned int v10; // eax
  int v11; // ebx
  __int64 v12; // rcx
  OLECHAR *v13; // rbx
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r15
  const WCHAR *v17; // rax
  const WCHAR *v18; // r14
  void (*v19)(void *, unsigned int, const unsigned __int16 *, char **); // r10
  int v20; // r15d
  unsigned int v21; // r14d
  int v22; // r14d
  OLECHAR *v23; // r14
  signed int LastError; // eax
  __int64 v26; // [rsp+40h] [rbp-79h] BYREF
  struct IWbemServices *v27; // [rsp+48h] [rbp-71h] BYREF
  const WCHAR *v28; // [rsp+50h] [rbp-69h] BYREF
  __int64 v29; // [rsp+58h] [rbp-61h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v32; // [rsp+70h] [rbp-49h] BYREF
  char v33; // [rsp+7Ch] [rbp-3Dh]
  OLECHAR *v34; // [rsp+80h] [rbp-39h]
  BSTR bstrString; // [rsp+88h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v37[16]; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE v38[16]; // [rsp+B8h] [rbp-1h] BYREF
  OLECHAR *v39; // [rsp+C8h] [rbp+Fh]
  OLECHAR *v40; // [rsp+D0h] [rbp+17h]
  int v41; // [rsp+120h] [rbp+67h] BYREF
  __int64 v42; // [rsp+138h] [rbp+7Fh] BYREF

  hKey = 0;
  if ( !a1 || !a2 )
  {
    XKey::Free((XKey *)&hKey);
    return 2147500037LL;
  }
  v29 = 0;
  v5 = ((__int64 (__fastcall *)(struct IWbemServices *, unsigned __int16 *, _QWORD, _QWORD, __int64 *, _QWORD))a2->lpVtbl->OpenNamespace)(
         a2,
         a1,
         0,
         0,
         &v29,
         0);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GarbageCollectNamespace: OpenNamespace failed. hr=0x%08X", v5);
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"GarbageCollectNamespace: OpenNamespace failed. hr=0x%08X", v5);
      }
    }
    goto LABEL_182;
  }
  v42 = 0;
  v6 = SysAllocString(L"__namespace");
  v39 = v6;
  if ( !v6 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory");
      }
    }
    v7 = 0;
LABEL_18:
    SysFreeString(v7);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
    v5 = -2147024882;
    goto LABEL_182;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64))(*(_QWORD *)v29 + 144LL))(v29, v6, 33);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GarbageCollectNamespace: CreateInstanceEnum failed. hr=0x%08X", v5);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GarbageCollectNamespace: CreateInstanceEnum failed. hr=0x%08X", v5);
      }
    }
    SysFreeString(v6);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
    goto LABEL_182;
  }
  v8 = SysAllocString(L"Name");
  v40 = v8;
  if ( !v8 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory");
      }
    }
    v9 = 0;
    goto LABEL_181;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\MicroSoft\\Windows NT\\CurrentVersion\\ProfileList\\",
         0,
         0x20019u,
         &hKey) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GarbageCollectNamespace: Profile key open failed.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GarbageCollectNamespace: Profile key open failed.");
      }
    }
    goto LABEL_180;
  }
  v26 = 0;
  v41 = 0;
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *, int *))(*(_QWORD *)v42 + 32LL))(
            v42,
            0,
            1,
            &v26,
            &v41);
    if ( v10 )
    {
      if ( v10 == 1 && !v41 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
        SysFreeString(v8);
        SysFreeString(v6);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
        XKey::Free((XKey *)&hKey);
        return 0;
      }
LABEL_173:
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GarbageCollectNamespace: Get failed. hr=0x%x", v10);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"GarbageCollectNamespace: Get failed. hr=0x%x", v10);
        }
      }
      goto LABEL_179;
    }
    if ( !v41 )
      goto LABEL_173;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v11 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v26 + 32LL))(
            v26,
            v8,
            0,
            &pvarg,
            0,
            0);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v12 = 0;
    v26 = 0;
    if ( v11 < 0 )
      break;
    v13 = 0;
    v34 = 0;
    if ( pvarg.llVal )
    {
      v13 = SysAllocString(pvarg.bstrVal);
      v34 = v13;
    }
    VariantClear(&pvarg);
    if ( !v13 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory");
        }
      }
      SysFreeString(0);
LABEL_179:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
LABEL_180:
      v9 = v8;
LABEL_181:
      SysFreeString(v9);
      SysFreeString(v6);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
      v5 = -2147467259;
      goto LABEL_182;
    }
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    if ( v14 > 1 && !(unsigned int)_o__wcsnicmp(v13, L"S_", 2) )
    {
      v15 = -1;
      do
        ++v15;
      while ( v13[v15] );
      v16 = v15 + 1;
      v17 = (const WCHAR *)LocalAlloc(0x40u, 2 * (v15 + 1));
      v18 = v17;
      v28 = v17;
      if ( v17 )
      {
        v20 = ConvertWMINameToSid(v13, v16, v17);
        if ( v20 < 0 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel != (_DWORD)v19 )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"GarbageCollectNamespace: ConvertWMINameToSid failed. hr=0x%x", (unsigned int)v20);
            }
            else if ( g_lpDebugMsgContextInstance != v19 && g_lpDebugMsgContext != v19 )
            {
              RedirectDebugMsg(4u, L"GarbageCollectNamespace: ConvertWMINameToSid failed. hr=0x%x", (unsigned int)v20);
            }
          }
LABEL_139:
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v28);
          SysFreeString(v13);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
          SysFreeString(v8);
          SysFreeString(v6);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
          v5 = v20;
LABEL_182:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
          goto LABEL_183;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              (_DWORD)v19 + 4,
              L"GarbageCollectNamespace: Converted WMI namespace:%ws to SID %ws\n",
              v13,
              v18);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"GarbageCollectNamespace: Converted WMI namespace:%ws to SID %ws\n", v13, v18);
          }
        }
        phkResult = 0;
        if ( !RegOpenKeyExW(hKey, v18, 0, 0x20019u, &phkResult) )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"GarbageCollectNamespace: Profile for SID %ws exists. Not garbage collecting.\n", v18);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                4u,
                L"GarbageCollectNamespace: Profile for SID %ws exists. Not garbage collecting.\n",
                v18);
            }
          }
          goto LABEL_103;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              4u,
              L"GarbageCollectNamespace: Profile for SID %ws does not exists. Consider for garbage collecting.\n",
              v18);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              4u,
              L"GarbageCollectNamespace: Profile for SID %ws does not exists. Consider for garbage collecting.\n",
              v18);
          }
        }
        v27 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, struct IWbemServices **, _QWORD))(*(_QWORD *)v29 + 24LL))(
                v29,
                v13,
                0,
                0,
                &v27,
                0);
        if ( (v21 & 0x80000000) == 0 )
        {
          v22 = IsNamespaceStale(v27, a3);
          XInterface<IWbemServices>::operator=((__int64 *)&v27);
          if ( !v22 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"GarbageCollectNamespace: WMI namespace %ws is not stale.\n", v13);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"GarbageCollectNamespace: WMI namespace %ws is not stale.\n", v13);
              }
            }
            goto LABEL_96;
          }
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"GarbageCollectNamespace: WMI namespace %ws is stale.\n", v13);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"GarbageCollectNamespace: WMI namespace %ws is stale.\n", v13);
            }
          }
          CWString::CWString((CWString *)&v32, L"__namespace.name=\"");
          CWString::CWString((CWString *)v37, v13);
          CWString::operator+=((CWString *)&v32);
          CWString::Reset((CWString *)v37);
          CWString::CWString((CWString *)v38, L"\"");
          CWString::operator+=((CWString *)&v32);
          CWString::Reset((CWString *)v38);
          if ( v33 )
          {
            XBStr::XBStr((XBStr *)&bstrString, v32);
            v23 = bstrString;
            if ( bstrString )
            {
              v20 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v29 + 128LL))(
                      v29,
                      bstrString,
                      0,
                      0,
                      0);
              if ( v20 >= 0 )
              {
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(4u, L"GarbageCollectNamespace: Deleted namespace:%ws\\%ws\n", a1, v13);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(4u, L"GarbageCollectNamespace: Deleted namespace:%ws\\%ws\n", a1, v13);
                  }
                }
                SysFreeString(v23);
                CWString::Reset((CWString *)&v32);
LABEL_96:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
LABEL_103:
                XKey::Free((XKey *)&phkResult);
                XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v28);
                goto LABEL_104;
              }
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(2u, L"GarbageCollectNamespace: DeleteInstance returned 0x%x", (unsigned int)v20);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"GarbageCollectNamespace: DeleteInstance returned 0x%x", (unsigned int)v20);
                }
              }
              SysFreeString(v23);
              CWString::Reset((CWString *)&v32);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
              XKey::Free((XKey *)&phkResult);
              goto LABEL_139;
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory.");
              }
            }
            SysFreeString(0);
          }
          else if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"GarbageCollectNamespace: Failed to allocate memory.");
            }
          }
          CWString::Reset((CWString *)&v32);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
          XKey::Free((XKey *)&phkResult);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v28);
          SysFreeString(v13);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
          SysFreeString(v8);
          v7 = v6;
          goto LABEL_18;
        }
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"GarbageCollectNamespace: OpenNamespace returned 0x%x", v21);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"GarbageCollectNamespace: OpenNamespace returned 0x%x", v21);
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
        XKey::Free((XKey *)&phkResult);
      }
      else
      {
        LastError = GetLastError();
        v21 = LastError;
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"GarbageCollectNamespace: AllocMem failed. hr=0x%x", v21);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"GarbageCollectNamespace: AllocMem failed. hr=0x%x", v21);
          }
        }
      }
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v28);
      SysFreeString(v13);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
      SysFreeString(v8);
      SysFreeString(v6);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
      v5 = v21;
      goto LABEL_182;
    }
LABEL_104:
    SysFreeString(v13);
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"GarbageCollectNamespace: Get failed. hr=0x%x", (unsigned int)v11);
      goto LABEL_162;
    }
    if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"GarbageCollectNamespace: Get failed. hr=0x%x", (unsigned int)v11);
LABEL_162:
      v12 = v26;
    }
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  SysFreeString(v8);
  SysFreeString(v6);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  v5 = -2147467259;
LABEL_183:
  XKey::Free((XKey *)&hKey);
  return v5;
}

```

## disassembly

```asm
0x1800206dc  mov     [rsp-8+arg_8], rbx
0x1800206e1  push    rbp
0x1800206e2  push    rsi
0x1800206e3  push    rdi
0x1800206e4  push    r12
0x1800206e6  push    r13
0x1800206e8  push    r14
0x1800206ea  push    r15
0x1800206ec  lea     rbp, [rsp-27h]
0x1800206f1  sub     rsp, 0E0h
0x1800206f8  mov     r13d, r8d
0x1800206fb  mov     r10, rdx
0x1800206fe  mov     r12, rcx
0x180020701  xor     r15d, r15d
0x180020704  mov     [rbp+57h+hKey], r15
0x180020708  test    rcx, rcx
0x18002070b  jz      loc_18002137D
0x180020711  test    rdx, rdx
0x180020714  jz      loc_18002137D
0x18002071a  mov     [rbp+57h+var_B8], r15
0x18002071e  mov     rax, [rdx]
0x180020721  mov     [rsp+110h+var_E8], r15
0x180020726  lea     rcx, [rbp+57h+var_B8]
0x18002072a  mov     [rsp+110h+phkResult], rcx
0x18002072f  xor     r9d, r9d
0x180020732  xor     r8d, r8d
0x180020735  mov     rdx, r12
0x180020738  mov     rcx, r10
0x18002073b  mov     rax, [rax+18h]
0x18002073f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020744  mov     ebx, eax
0x180020746  test    eax, eax
0x180020748  jns     short loc_1800207AE
0x18002074a  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180020751  jz      loc_180021366
0x180020757  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002075e  test    rax, rax
0x180020761  jz      short loc_18002077B
0x180020763  mov     r8d, ebx
0x180020766  lea     rdx, aGarbagecollect_3; "GarbageCollectNamespace: OpenNamespace "...
0x18002076d  lea     ecx, [r15+2]
0x180020771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020776  jmp     loc_180021366
0x18002077b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180020782  jz      loc_180021366
0x180020788  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002078f  jz      loc_180021366
0x180020795  mov     r8d, ebx
0x180020798  lea     rdx, aGarbagecollect_3; "GarbageCollectNamespace: OpenNamespace "...
0x18002079f  mov     ecx, 2; unsigned int
0x1800207a4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800207a9  jmp     loc_180021366
0x1800207ae  mov     [rbp+57h+arg_18], r15
0x1800207b2  lea     rcx, aNamespace_0; "__namespace"
0x1800207b9  call    cs:__imp_SysAllocString
0x1800207bf  mov     rdi, rax
0x1800207c2  mov     [rbp+57h+var_48], rax
0x1800207c6  test    rax, rax
0x1800207c9  jnz     short loc_180020831
0x1800207cb  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800207d2  jz      short loc_180020815
0x1800207d4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800207db  test    rax, rax
0x1800207de  jz      short loc_1800207F1
0x1800207e0  lea     rdx, aGarbagecollect_2; "GarbageCollectNamespace: Failed to allo"...
0x1800207e7  lea     ecx, [rdi+2]
0x1800207ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207ef  jmp     short loc_180020815
0x1800207f1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800207f8  jz      short loc_180020815
0x1800207fa  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180020801  jz      short loc_180020815
0x180020803  lea     rdx, aGarbagecollect_2; "GarbageCollectNamespace: Failed to allo"...
0x18002080a  mov     ecx, 2; unsigned int
0x18002080f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180020814  nop
0x180020815  xor     ecx, ecx; bstrString
0x180020817  call    cs:__imp_SysFreeString
0x18002081d  nop
0x18002081e  lea     rcx, [rbp+57h+arg_18]
0x180020822  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020827  mov     ebx, 8007000Eh
0x18002082c  jmp     loc_180021366
0x180020831  mov     rcx, [rbp+57h+var_B8]
0x180020835  mov     rax, [rcx]
0x180020838  lea     rdx, [rbp+57h+arg_18]
0x18002083c  mov     [rsp+110h+phkResult], rdx
0x180020841  xor     r9d, r9d
0x180020844  lea     r8d, [r9+21h]
0x180020848  mov     rdx, rdi
0x18002084b  mov     rax, [rax+90h]
0x180020852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020857  mov     ebx, eax
0x180020859  test    eax, eax
0x18002085b  jns     short loc_1800208C7
0x18002085d  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180020864  jz      short loc_1800208AF
0x180020866  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002086d  test    rax, rax
0x180020870  jz      short loc_180020888
0x180020872  mov     r8d, ebx
0x180020875  lea     rdx, aGarbagecollect_9; "GarbageCollectNamespace: CreateInstance"...
0x18002087c  mov     ecx, 2
0x180020881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020886  jmp     short loc_1800208AF
0x180020888  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18002088f  jz      short loc_1800208AF
0x180020891  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180020898  jz      short loc_1800208AF
0x18002089a  mov     r8d, ebx
0x18002089d  lea     rdx, aGarbagecollect_9; "GarbageCollectNamespace: CreateInstance"...
0x1800208a4  mov     ecx, 2; unsigned int
0x1800208a9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800208ae  nop
0x1800208af  mov     rcx, rdi; bstrString
0x1800208b2  call    cs:__imp_SysFreeString
0x1800208b8  nop
0x1800208b9  lea     rcx, [rbp+57h+arg_18]
0x1800208bd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800208c2  jmp     loc_180021366
0x1800208c7  lea     rcx, aName; "Name"
0x1800208ce  call    cs:__imp_SysAllocString
0x1800208d4  mov     rsi, rax
0x1800208d7  mov     [rbp+57h+var_40], rax
0x1800208db  test    rax, rax
0x1800208de  jnz     short loc_180020931
0x1800208e0  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800208e7  jz      short loc_18002092A
0x1800208e9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800208f0  test    rax, rax
0x1800208f3  jz      short loc_180020906
0x1800208f5  lea     rdx, aGarbagecollect_2; "GarbageCollectNamespace: Failed to allo"...
0x1800208fc  lea     ecx, [rsi+2]
0x1800208ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020904  jmp     short loc_18002092A
0x180020906  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18002090d  jz      short loc_18002092A
0x18002090f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180020916  jz      short loc_18002092A
0x180020918  lea     rdx, aGarbagecollect_2; "GarbageCollectNamespace: Failed to allo"...
0x18002091f  mov     ecx, 2; unsigned int
0x180020924  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180020929  nop
0x18002092a  xor     ecx, ecx
0x18002092c  jmp     loc_180021347
0x180020931  lea     rax, [rbp+57h+hKey]
0x180020935  mov     [rsp+110h+phkResult], rax; phkResult
0x18002093a  mov     r9d, 20019h; samDesired
0x180020940  xor     r8d, r8d; ulOptions
0x180020943  lea     rdx, aSoftwareMicros_40; "SOFTWARE\\MicroSoft\\Windows NT\\Curren"...
0x18002094a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020951  call    cs:__imp_RegOpenKeyExW
0x180020957  test    eax, eax
0x180020959  jz      short loc_1800209BA
0x18002095b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180020962  jz      loc_180021344
0x180020968  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002096f  test    rax, rax
0x180020972  jz      short loc_18002098A
0x180020974  lea     rdx, aGarbagecollect_11; "GarbageCollectNamespace: Profile key op"...
0x18002097b  mov     ecx, 2
0x180020980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020985  jmp     loc_180021344
0x18002098a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180020991  jz      loc_180021344
0x180020997  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002099e  jz      loc_180021344
0x1800209a4  lea     rdx, aGarbagecollect_11; "GarbageCollectNamespace: Profile key op"...
0x1800209ab  mov     ecx, 2; unsigned int
0x1800209b0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800209b5  jmp     loc_180021344
0x1800209ba  mov     [rbp+57h+var_D0], r15
0x1800209be  mov     [rbp+57h+arg_0], r15d
0x1800209c2  mov     rcx, [rbp+57h+arg_18]
0x1800209c6  mov     rax, [rcx]
0x1800209c9  lea     rdx, [rbp+57h+arg_0]
0x1800209cd  mov     [rsp+110h+phkResult], rdx
0x1800209d2  lea     r9, [rbp+57h+var_D0]
0x1800209d6  xor     edx, edx
0x1800209d8  lea     r8d, [rdx+1]
0x1800209dc  mov     rax, [rax+20h]
0x1800209e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209e5  test    eax, eax
0x1800209e7  jnz     loc_180021298
0x1800209ed  cmp     [rbp+57h+arg_0], r15d
0x1800209f1  jz      loc_1800212E5
0x1800209f7  xorps   xmm0, xmm0
0x1800209fa  xor     eax, eax
0x1800209fc  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180020a00  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180020a04  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180020a08  call    cs:__imp_VariantInit
0x180020a0e  mov     rcx, [rbp+57h+var_D0]
0x180020a12  mov     rax, [rcx]
0x180020a15  mov     [rsp+110h+var_E8], r15
0x180020a1a  mov     [rsp+110h+phkResult], r15
0x180020a1f  lea     r9, [rbp+57h+pvarg]
0x180020a23  xor     r8d, r8d
0x180020a26  mov     rdx, rsi
0x180020a29  mov     rax, [rax+20h]
0x180020a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a32  mov     ebx, eax
0x180020a34  mov     rcx, [rbp+57h+var_D0]
0x180020a38  test    rcx, rcx
0x180020a3b  jz      short loc_180020A49
0x180020a3d  mov     rdx, [rcx]
0x180020a40  mov     rax, [rdx+10h]
0x180020a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a49  mov     rcx, r15
0x180020a4c  mov     [rbp+57h+var_D0], rcx
0x180020a50  test    ebx, ebx
0x180020a52  js      loc_1800211E7
0x180020a58  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psz
0x180020a5c  mov     rbx, r15
0x180020a5f  mov     [rbp+57h+var_90], rbx
0x180020a63  test    rcx, rcx
0x180020a66  jz      short loc_180020A75
0x180020a68  call    cs:__imp_SysAllocString
0x180020a6e  mov     rbx, rax
0x180020a71  mov     [rbp+57h+var_90], rax
0x180020a75  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180020a79  call    cs:__imp_VariantClear
0x180020a7f  test    rbx, rbx
0x180020a82  jz      loc_18002118E
0x180020a88  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020a8c  inc     rax
0x180020a8f  cmp     [rbx+rax*2], r15w
0x180020a94  jnz     short loc_180020A8C
0x180020a96  cmp     rax, 1
0x180020a9a  jbe     loc_180020E66
0x180020aa0  mov     r8d, 2
0x180020aa6  lea     rdx, aS_0; "S_"
0x180020aad  mov     rcx, rbx
0x180020ab0  call    cs:__imp__o__wcsnicmp
0x180020ab6  test    eax, eax
0x180020ab8  jnz     loc_180020E66
0x180020abe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020ac2  inc     rax
0x180020ac5  cmp     [rbx+rax*2], r15w
0x180020aca  jnz     short loc_180020AC2
0x180020acc  lea     r15, [rax+1]
0x180020ad0  lea     rdx, [r15+r15]; uBytes
0x180020ad4  mov     ecx, 40h ; '@'; uFlags
0x180020ad9  call    cs:__imp_LocalAlloc
0x180020adf  mov     r14, rax
0x180020ae2  mov     [rbp+57h+var_C0], rax
0x180020ae6  xor     r10d, r10d
0x180020ae9  test    rax, rax
0x180020aec  jz      loc_1800210E0
0x180020af2  mov     r8, rax
0x180020af5  mov     rdx, r15
0x180020af8  mov     rcx, rbx
0x180020afb  call    ConvertWMINameToSid
0x180020b00  mov     r15d, eax
0x180020b03  test    eax, eax
0x180020b05  js      loc_18002104B
0x180020b0b  xor     r15d, r15d
0x180020b0e  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180020b15  jz      short loc_180020B64
0x180020b17  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180020b1e  test    rax, rax
0x180020b21  jz      short loc_180020B3B
0x180020b23  mov     r9, r14
0x180020b26  mov     r8, rbx
0x180020b29  lea     rdx, aGarbagecollect_10; "GarbageCollectNamespace: Converted WMI "...
0x180020b30  lea     ecx, [r10+4]
0x180020b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b39  jmp     short loc_180020B64
0x180020b3b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180020b42  jz      short loc_180020B64
0x180020b44  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180020b4b  jz      short loc_180020B64
0x180020b4d  mov     r9, r14
0x180020b50  mov     r8, rbx
0x180020b53  lea     rdx, aGarbagecollect_10; "GarbageCollectNamespace: Converted WMI "...
0x180020b5a  mov     ecx, 4; unsigned int
0x180020b5f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180020b64  mov     [rbp+57h+var_B0], r15
0x180020b68  lea     rax, [rbp+57h+var_B0]
0x180020b6c  mov     [rsp+110h+phkResult], rax; phkResult
0x180020b71  mov     r9d, 20019h; samDesired
0x180020b77  xor     r8d, r8d; ulOptions
0x180020b7a  mov     rdx, r14; lpSubKey
0x180020b7d  mov     rcx, [rbp+57h+hKey]; hKey
0x180020b81  call    cs:__imp_RegOpenKeyExW
0x180020b87  test    eax, eax
0x180020b89  jz      loc_180020E00
0x180020b8f  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180020b96  jz      short loc_180020BE0
0x180020b98  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180020b9f  test    rax, rax
0x180020ba2  jz      short loc_180020BBA
0x180020ba4  mov     r8, r14
0x180020ba7  lea     rdx, aGarbagecollect_4; "GarbageCollectNamespace: Profile for SI"...
0x180020bae  mov     ecx, 4
0x180020bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bb8  jmp     short loc_180020BE0
0x180020bba  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180020bc1  jz      short loc_180020BE0
0x180020bc3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
  ... truncated ...
```
