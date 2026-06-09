# CreateCSE_EventSourceAssoc(IWbemServices *,ushort const *,ushort const *)

- ea: `0x1800abcf8`
- end: `0x1800ac738`
- name: `?CreateCSE_EventSourceAssoc@@YAJPEAUIWbemServices@@PEBG1@Z`
- size: `2624`
- prototype: `__int64 __fastcall(struct IWbemServices *, const unsigned __int16 *, wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800acbd8`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18004b210`
- `0x1800535a0`
- `0x1800585e8`
- `0x180075ec0`
- `0x18007d320`
- `0x1800abcf8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ac32c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ac348`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ac3c1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ac455`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ac32c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ac348`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ac3c1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ac455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac045`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800abfed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ac23b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800abfed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ac23b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800ac182`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800ac182`
- `OLEAUT32!__imp_SysFreeString` at `0x1800abdfa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800abf40`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac494`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac49e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac508`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac512`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac51c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac526`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac530`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac557`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac561`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac56b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac575`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac57f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac589`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac5e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac5f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac5fc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac606`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac610`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac61a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac643`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac64d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac657`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac661`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac66b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac675`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac6b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800abdfa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800abf40`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac494`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac49e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac4fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac508`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac512`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac51c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac526`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac530`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac557`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac561`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac56b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac575`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac57f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac589`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac5e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac5f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac5fc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac606`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac610`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac61a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac643`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac64d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac657`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac661`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac66b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac675`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ac6b3`

## string_xrefs

- `0x1800ac077`: `RSOP_ExtensionStatus.extensionGuid="%s"`
- `0x1800ac6d3`: `CreateCSE_EventSourceAssoc: invalid arguments`
- `0x1800ac6f8`: `CreateCSE_EventSourceAssoc: invalid arguments`
- `0x1800abd57`: `RSOP_ExtensionEventSource`
- `0x1800abdb4`: `CreateCSE_EventSourceAssoc: GetObject failed, 0x%x`
- `0x1800abddb`: `CreateCSE_EventSourceAssoc: GetObject failed, 0x%x`
- `0x1800abee4`: `CreateCSE_EventSourceAssoc: GetObject failed, 0x%x`
- `0x1800abf0c`: `CreateCSE_EventSourceAssoc: GetObject failed, 0x%x`
- `0x1800abe3f`: `CreateCSE_EventSourceAssoc: SpawnInstance failed, 0x%x`
- `0x1800abe67`: `CreateCSE_EventSourceAssoc: SpawnInstance failed, 0x%x`
- `0x1800abf89`: `CreateCSE_EventSourceAssoc: SpawnInstance failed, 0x%x`
- `0x1800abfbc`: `CreateCSE_EventSourceAssoc: SpawnInstance failed, 0x%x`
- `0x1800abe8b`: `RSOP_ExtensionEventSourceLink`
- `0x1800ac01e`: `CreateCSE_EventSourceAssoc: LocalAlloc failed, 0x%x`
- `0x1800ac04e`: `CreateCSE_EventSourceAssoc: LocalAlloc failed, 0x%x`
- `0x1800ac0d7`: `extensionStatus`
- `0x1800ac5ab`: `CreateCSE_EventSourceAssoc: CoCreateGuid failed, 0x%x`
- `0x1800ac5d3`: `CreateCSE_EventSourceAssoc: CoCreateGuid failed, 0x%x`
- `0x1800ac256`: `RSOP_ExtensionEventSource.id="%s"`

## pseudocode

```c
__int64 __fastcall CreateCSE_EventSourceAssoc(struct IWbemServices *a1, const unsigned __int16 *a2, wchar_t *a3)
{
  OLECHAR *v5; // rbx
  unsigned int v6; // edi
  int v8; // ebx
  __int64 v9; // rax
  unsigned __int64 v10; // rbx
  OLECHAR *v11; // rax
  const OLECHAR *v12; // r13
  void (*v13)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v15; // eax
  OLECHAR *v16; // r12
  OLECHAR *v17; // r14
  OLECHAR *v18; // r15
  OLECHAR *v19; // rbx
  OLECHAR *v20; // rsi
  OLECHAR *v21; // rdi
  int v22; // r13d
  __int64 v23; // rax
  OLECHAR *v24; // rax
  const OLECHAR *v25; // r13
  wchar_t *v26; // rax
  wchar_t *v27; // rax
  wchar_t *v28; // r13
  const OLECHAR *v29; // rdx
  const wchar_t *v30; // r13
  wchar_t *v31; // rax
  wchar_t *v32; // rcx
  __int64 v33; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+28h] [rbp-D8h]
  __int64 v35; // [rsp+30h] [rbp-D0h]
  __int64 v36; // [rsp+38h] [rbp-C8h]
  __int64 v37; // [rsp+40h] [rbp-C0h]
  __int64 v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+50h] [rbp-B0h]
  __int64 v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h]
  __int64 v42; // [rsp+68h] [rbp-98h]
  const OLECHAR *v43; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *v44; // [rsp+78h] [rbp-88h] BYREF
  BSTR v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *Str; // [rsp+A0h] [rbp-60h]
  __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v53; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-30h]
  BSTR v55; // [rsp+D8h] [rbp-28h] BYREF
  struct IWbemServices *v56; // [rsp+E0h] [rbp-20h]
  BSTR v57; // [rsp+E8h] [rbp-18h] BYREF
  BSTR v58; // [rsp+F0h] [rbp-10h] BYREF
  BSTR v59; // [rsp+F8h] [rbp-8h] BYREF
  BSTR v60; // [rsp+100h] [rbp+0h] BYREF
  GUID pguid; // [rsp+108h] [rbp+8h] BYREF
  OLECHAR v62[64]; // [rsp+120h] [rbp+20h] BYREF

  Str = a3;
  v56 = a1;
  if ( a1 && a2 && a3 )
  {
    XBStr::XBStr((XBStr *)&bstrString, L"RSOP_ExtensionEventSource");
    v48 = 0;
    v5 = bstrString;
    v6 = ((__int64 (__fastcall *)(struct IWbemServices *, BSTR, _QWORD, _QWORD, __int64 *, _QWORD))a1->lpVtbl->GetObjectA)(
           a1,
           bstrString,
           0,
           0,
           &v48,
           0);
    if ( (v6 & 0x80000000) != 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CreateCSE_EventSourceAssoc: GetObject failed, 0x%x", v6);
        }
        else if ( g_lpDebugMsgContextInstance )
        {
          if ( g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"CreateCSE_EventSourceAssoc: GetObject failed, 0x%x", v6);
        }
      }
LABEL_11:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
      SysFreeString(v5);
      return v6;
    }
    v46 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 120LL))(v48, 0, &v46);
    if ( (v6 & 0x80000000) != 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CreateCSE_EventSourceAssoc: SpawnInstance failed, 0x%x", v6);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CreateCSE_EventSourceAssoc: SpawnInstance failed, 0x%x", v6);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
      goto LABEL_11;
    }
    v52 = 0;
    XBStr::operator=(&bstrString, L"RSOP_ExtensionEventSourceLink");
    v8 = ((__int64 (__fastcall *)(struct IWbemServices *, BSTR, _QWORD, _QWORD, __int64 *, _QWORD))a1->lpVtbl->GetObjectA)(
           a1,
           bstrString,
           0,
           0,
           &v52,
           0);
    if ( v8 < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CreateCSE_EventSourceAssoc: GetObject failed, 0x%x", (unsigned int)v8);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CreateCSE_EventSourceAssoc: GetObject failed, 0x%x", (unsigned int)v8);
        }
      }
      goto LABEL_27;
    }
    v50 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 120LL))(v52, 0, &v50);
    if ( v8 < 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CreateCSE_EventSourceAssoc: SpawnInstance failed, 0x%x", (unsigned int)v8);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CreateCSE_EventSourceAssoc: SpawnInstance failed, 0x%x", (unsigned int)v8);
        }
      }
      goto LABEL_80;
    }
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v10 = v9 + 48;
    v11 = (OLECHAR *)LocalAlloc(0x40u, 2 * (v9 + 48));
    v12 = v11;
    v43 = v11;
    if ( !v11 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v13 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          LastError = GetLastError();
          v13(2u, L"CreateCSE_EventSourceAssoc: LocalAlloc failed, 0x%x", LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v15 = GetLastError();
          RedirectDebugMsg(2u, L"CreateCSE_EventSourceAssoc: LocalAlloc failed, 0x%x", v15);
        }
      }
LABEL_44:
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v43);
      v8 = -2147024882;
      goto LABEL_80;
    }
    v8 = StringCchPrintfW(v11, v10, L"RSOP_ExtensionStatus.extensionGuid=\"%s\"", a2);
    LODWORD(v47) = v8;
    if ( v8 < 0 )
    {
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v43);
LABEL_80:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
LABEL_27:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
      SysFreeString(bstrString);
      return (unsigned int)v8;
    }
    v53 = 0;
    v54 = 0;
    v16 = 0;
    v45 = 0;
    XBStr::XBStr((XBStr *)&v57, L"eventLogSource");
    XBStr::XBStr((XBStr *)&v58, L"eventLogName");
    XBStr::XBStr((XBStr *)&v55, L"extensionStatus");
    XBStr::XBStr((XBStr *)&v59, L"eventSource");
    XBStr::XBStr((XBStr *)&v60, L"id");
    LOWORD(v53) = 8;
    v17 = v57;
    v18 = v58;
    v19 = v55;
    v20 = v59;
    v21 = v60;
    while ( *Str )
    {
      XBStr::operator=(&v45, v12);
      v16 = v45;
      *((_QWORD *)&v53 + 1) = v45;
      v22 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, __int128 *, _DWORD))(*(_QWORD *)v50 + 40LL))(
              v50,
              v19,
              0,
              &v53,
              0);
      if ( v22 < 0 )
        goto LABEL_79;
      pguid = 0;
      v22 = CoCreateGuid(&pguid);
      if ( v22 < 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"CreateCSE_EventSourceAssoc: CoCreateGuid failed, 0x%x", (unsigned int)v22);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"CreateCSE_EventSourceAssoc: CoCreateGuid failed, 0x%x", (unsigned int)v22);
          }
        }
        goto LABEL_79;
      }
      LODWORD(v42) = pguid.Data4[7];
      LODWORD(v41) = pguid.Data4[6];
      LODWORD(v40) = pguid.Data4[5];
      LODWORD(v39) = pguid.Data4[4];
      LODWORD(v38) = pguid.Data4[3];
      LODWORD(v37) = pguid.Data4[2];
      LODWORD(v36) = pguid.Data4[1];
      LODWORD(v35) = pguid.Data4[0];
      LODWORD(v34) = pguid.Data3;
      LODWORD(v33) = pguid.Data2;
      v22 = StringCchPrintfW(
              v62,
              0x40u,
              L"{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
              pguid.Data1,
              v33,
              v34,
              v35,
              v36,
              v37,
              v38,
              v39,
              v40,
              v41,
              v42);
      v19 = v55;
      if ( v22 < 0 )
        goto LABEL_79;
      v23 = -1;
      do
        ++v23;
      while ( v62[v23] );
      v47 = v23 + 34;
      v24 = (OLECHAR *)LocalAlloc(0x40u, 2 * (v23 + 34));
      v25 = v24;
      v44 = v24;
      if ( !v24 )
      {
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v44);
        SysFreeString(v21);
        SysFreeString(v20);
        SysFreeString(v19);
        SysFreeString(v18);
        SysFreeString(v17);
        SysFreeString(v16);
        goto LABEL_44;
      }
      LODWORD(v47) = StringCchPrintfW(v24, v47, L"RSOP_ExtensionEventSource.id=\"%s\"", v62);
      if ( (v47 & 0x80000000) != 0LL )
        goto LABEL_71;
      XBStr::operator=(&v45, v25);
      v16 = v45;
      *((_QWORD *)&v53 + 1) = v45;
      v22 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, __int128 *, _DWORD))(*(_QWORD *)v50 + 40LL))(
              v50,
              v20,
              0,
              &v53,
              0);
      if ( v22 < 0
        || (v22 = ((__int64 (__fastcall *)(struct IWbemServices *, __int64, _QWORD, _QWORD, _QWORD))v56->lpVtbl->PutInstance)(
                    v56,
                    v50,
                    0,
                    0,
                    0),
            v22 < 0)
        || (XBStr::operator=(&v45, v62),
            v16 = v45,
            *((_QWORD *)&v53 + 1) = v45,
            v22 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, __int128 *, _DWORD))(*(_QWORD *)v46 + 40LL))(
                    v46,
                    v21,
                    0,
                    &v53,
                    0),
            v22 < 0) )
      {
LABEL_68:
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v44);
LABEL_79:
        SysFreeString(v21);
        SysFreeString(v20);
        SysFreeString(v19);
        SysFreeString(v18);
        SysFreeString(v17);
        SysFreeString(v16);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v43);
        v8 = v22;
        goto LABEL_80;
      }
      v26 = wcschr(Str, 0x28u);
      Str = v26;
      if ( !v26 )
      {
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v44);
        goto LABEL_82;
      }
      v27 = wcschr(v26 + 1, 0x2Cu);
      v28 = v27;
      if ( !v27 || (v29 = Str + 1, Str + 1 == v27) )
      {
LABEL_69:
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v44);
        SysFreeString(v21);
        SysFreeString(v20);
        SysFreeString(v19);
        SysFreeString(v18);
        SysFreeString(v17);
        SysFreeString(v16);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v43);
        v8 = -2147024809;
        goto LABEL_80;
      }
      *v27 = 0;
      XBStr::operator=(&v45, v29);
      v16 = v45;
      *((_QWORD *)&v53 + 1) = v45;
      LODWORD(v47) = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, __int128 *, _DWORD))(*(_QWORD *)v46 + 40LL))(
                       v46,
                       v17,
                       0,
                       &v53,
                       0);
      if ( (v47 & 0x80000000) != 0LL )
      {
LABEL_71:
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v44);
        SysFreeString(v21);
        SysFreeString(v20);
        SysFreeString(v19);
        SysFreeString(v18);
        SysFreeString(v17);
        SysFreeString(v16);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v43);
        v8 = v47;
        goto LABEL_80;
      }
      *v28 = 44;
      v30 = v28 + 1;
      v31 = wcschr(v30, 0x29u);
      Str = v31;
      if ( !v31 || v30 == v31 )
        goto LABEL_69;
      *v31 = 0;
      XBStr::operator=(&v45, v30);
      v16 = v45;
      *((_QWORD *)&v53 + 1) = v45;
      v22 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, __int128 *, _DWORD))(*(_QWORD *)v46 + 40LL))(
              v46,
              v18,
              0,
              &v53,
              0);
      if ( v22 < 0 )
        goto LABEL_68;
      v22 = ((__int64 (__fastcall *)(struct IWbemServices *, __int64, _QWORD, _QWORD, _QWORD))v56->lpVtbl->PutInstance)(
              v56,
              v46,
              0,
              0,
              0);
      LODWORD(v47) = v22;
      if ( v22 < 0 )
        goto LABEL_68;
      v32 = Str;
      *Str = 41;
      Str = wcschr(v32, 0) + 1;
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v44);
      v12 = v43;
    }
    v22 = v47;
LABEL_82:
    SysFreeString(v21);
    SysFreeString(v20);
    SysFreeString(v19);
    SysFreeString(v18);
    SysFreeString(v17);
    SysFreeString(v16);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v43);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    SysFreeString(bstrString);
    return (unsigned int)v22;
  }
  else
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CreateCSE_EventSourceAssoc: invalid arguments");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CreateCSE_EventSourceAssoc: invalid arguments");
      }
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800abcf8  mov     [rsp-8+arg_18], rbx
0x1800abcfd  push    rbp
0x1800abcfe  push    rsi
0x1800abcff  push    rdi
0x1800abd00  push    r12
0x1800abd02  push    r13
0x1800abd04  push    r14
0x1800abd06  push    r15
0x1800abd08  lea     rbp, [rsp-0B0h]
0x1800abd10  sub     rsp, 1B0h
0x1800abd17  mov     rax, cs:__security_cookie
0x1800abd1e  xor     rax, rsp
0x1800abd21  mov     [rbp+0E0h+var_40], rax
0x1800abd28  mov     rax, r8
0x1800abd2b  mov     [rbp+0E0h+Str], rax
0x1800abd2f  mov     rsi, rdx
0x1800abd32  mov     r14, rcx
0x1800abd35  mov     [rbp+0E0h+var_100], rcx
0x1800abd39  xor     r15d, r15d
0x1800abd3c  test    rcx, rcx
0x1800abd3f  jz      loc_1800AC6BE
0x1800abd45  test    rdx, rdx
0x1800abd48  jz      loc_1800AC6BE
0x1800abd4e  test    rax, rax
0x1800abd51  jz      loc_1800AC6BE
0x1800abd57  lea     rdx, aRsopExtensione_0; "RSOP_ExtensionEventSource"
0x1800abd5e  lea     rcx, [rbp+0E0h+bstrString]; this
0x1800abd62  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800abd67  nop
0x1800abd68  mov     [rbp+0E0h+var_148], r15
0x1800abd6c  mov     rax, [r14]
0x1800abd6f  mov     [rsp+1E0h+var_1B8], r15
0x1800abd74  lea     rcx, [rbp+0E0h+var_148]
0x1800abd78  mov     [rsp+1E0h+var_1C0], rcx
0x1800abd7d  xor     r9d, r9d
0x1800abd80  xor     r8d, r8d
0x1800abd83  mov     rbx, [rbp+0E0h+bstrString]
0x1800abd87  mov     rdx, rbx
0x1800abd8a  mov     rcx, r14
0x1800abd8d  mov     rax, [rax+30h]
0x1800abd91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abd96  mov     edi, eax
0x1800abd98  test    eax, eax
0x1800abd9a  jns     short loc_1800ABE07
0x1800abd9c  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800abda3  jz      short loc_1800ABDED
0x1800abda5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800abdac  test    rax, rax
0x1800abdaf  jz      short loc_1800ABDC6
0x1800abdb1  mov     r8d, edi
0x1800abdb4  lea     rdx, aCreatecseEvent_2; "CreateCSE_EventSourceAssoc: GetObject f"...
0x1800abdbb  lea     ecx, [r15+2]
0x1800abdbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abdc4  jmp     short loc_1800ABDED
0x1800abdc6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800abdcd  jz      short loc_1800ABDED
0x1800abdcf  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800abdd6  jz      short loc_1800ABDED
0x1800abdd8  mov     r8d, edi
0x1800abddb  lea     rdx, aCreatecseEvent_2; "CreateCSE_EventSourceAssoc: GetObject f"...
0x1800abde2  mov     ecx, 2; unsigned int
0x1800abde7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800abdec  nop
0x1800abded  lea     rcx, [rbp+0E0h+var_148]
0x1800abdf1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800abdf6  nop
0x1800abdf7  mov     rcx, rbx; bstrString
0x1800abdfa  call    cs:__imp_SysFreeString
0x1800abe00  mov     eax, edi
0x1800abe02  jmp     loc_1800AC70E
0x1800abe07  mov     [rbp+0E0h+var_158], r15
0x1800abe0b  mov     rcx, [rbp+0E0h+var_148]
0x1800abe0f  mov     rax, [rcx]
0x1800abe12  lea     r8, [rbp+0E0h+var_158]
0x1800abe16  xor     edx, edx
0x1800abe18  mov     rax, [rax+78h]
0x1800abe1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe21  mov     edi, eax
0x1800abe23  test    eax, eax
0x1800abe25  jns     short loc_1800ABE87
0x1800abe27  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800abe2e  jz      short loc_1800ABE79
0x1800abe30  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800abe37  test    rax, rax
0x1800abe3a  jz      short loc_1800ABE52
0x1800abe3c  mov     r8d, edi
0x1800abe3f  lea     rdx, aCreatecseEvent_0; "CreateCSE_EventSourceAssoc: SpawnInstan"...
0x1800abe46  mov     ecx, 2
0x1800abe4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe50  jmp     short loc_1800ABE79
0x1800abe52  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800abe59  jz      short loc_1800ABE79
0x1800abe5b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800abe62  jz      short loc_1800ABE79
0x1800abe64  mov     r8d, edi
0x1800abe67  lea     rdx, aCreatecseEvent_0; "CreateCSE_EventSourceAssoc: SpawnInstan"...
0x1800abe6e  mov     ecx, 2; unsigned int
0x1800abe73  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800abe78  nop
0x1800abe79  lea     rcx, [rbp+0E0h+var_158]
0x1800abe7d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800abe82  jmp     loc_1800ABDED
0x1800abe87  mov     [rbp+0E0h+var_128], r15
0x1800abe8b  lea     rdx, aRsopExtensione_1; "RSOP_ExtensionEventSourceLink"
0x1800abe92  lea     rcx, [rbp+0E0h+bstrString]
0x1800abe96  call    ??4XBStr@@QEAAXPEBG@Z; XBStr::operator=(ushort const *)
0x1800abe9b  mov     rax, [r14]
0x1800abe9e  mov     [rsp+1E0h+var_1B8], r15
0x1800abea3  lea     rcx, [rbp+0E0h+var_128]
0x1800abea7  mov     [rsp+1E0h+var_1C0], rcx
0x1800abeac  xor     r9d, r9d
0x1800abeaf  xor     r8d, r8d
0x1800abeb2  mov     rdx, [rbp+0E0h+bstrString]
0x1800abeb6  mov     rcx, r14
0x1800abeb9  mov     rax, [rax+30h]
0x1800abebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abec2  mov     ebx, eax
0x1800abec4  test    eax, eax
0x1800abec6  jns     loc_1800ABF4D
0x1800abecc  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800abed3  jz      short loc_1800ABF1E
0x1800abed5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800abedc  test    rax, rax
0x1800abedf  jz      short loc_1800ABEF7
0x1800abee1  mov     r8d, ebx
0x1800abee4  lea     rdx, aCreatecseEvent_2; "CreateCSE_EventSourceAssoc: GetObject f"...
0x1800abeeb  mov     ecx, 2
0x1800abef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abef5  jmp     short loc_1800ABF1E
0x1800abef7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800abefe  jz      short loc_1800ABF1E
0x1800abf00  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800abf07  jz      short loc_1800ABF1E
0x1800abf09  mov     r8d, ebx
0x1800abf0c  lea     rdx, aCreatecseEvent_2; "CreateCSE_EventSourceAssoc: GetObject f"...
0x1800abf13  mov     ecx, 2; unsigned int
0x1800abf18  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800abf1d  nop
0x1800abf1e  lea     rcx, [rbp+0E0h+var_128]
0x1800abf22  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800abf27  nop
0x1800abf28  lea     rcx, [rbp+0E0h+var_158]
0x1800abf2c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800abf31  nop
0x1800abf32  lea     rcx, [rbp+0E0h+var_148]
0x1800abf36  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800abf3b  nop
0x1800abf3c  mov     rcx, [rbp+0E0h+bstrString]; bstrString
0x1800abf40  call    cs:__imp_SysFreeString
0x1800abf46  mov     eax, ebx
0x1800abf48  jmp     loc_1800AC70E
0x1800abf4d  mov     [rbp+0E0h+var_138], r15
0x1800abf51  mov     rcx, [rbp+0E0h+var_128]
0x1800abf55  mov     rax, [rcx]
0x1800abf58  lea     r8, [rbp+0E0h+var_138]
0x1800abf5c  xor     edx, edx
0x1800abf5e  mov     rax, [rax+78h]
0x1800abf62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf67  mov     ebx, eax
0x1800abf69  test    eax, eax
0x1800abf6b  jns     short loc_1800ABFD2
0x1800abf6d  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800abf74  jz      loc_1800AC62E
0x1800abf7a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800abf81  test    rax, rax
0x1800abf84  jz      short loc_1800ABF9F
0x1800abf86  mov     r8d, ebx
0x1800abf89  lea     rdx, aCreatecseEvent_0; "CreateCSE_EventSourceAssoc: SpawnInstan"...
0x1800abf90  mov     ecx, 2
0x1800abf95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abf9a  jmp     loc_1800AC62E
0x1800abf9f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800abfa6  jz      loc_1800AC62E
0x1800abfac  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800abfb3  jz      loc_1800AC62E
0x1800abfb9  mov     r8d, ebx
0x1800abfbc  lea     rdx, aCreatecseEvent_0; "CreateCSE_EventSourceAssoc: SpawnInstan"...
0x1800abfc3  mov     ecx, 2; unsigned int
0x1800abfc8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800abfcd  jmp     loc_1800AC62E
0x1800abfd2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800abfd6  inc     rax
0x1800abfd9  cmp     [rsi+rax*2], r15w
0x1800abfde  jnz     short loc_1800ABFD6
0x1800abfe0  lea     rbx, [rax+30h]
0x1800abfe4  lea     rdx, [rbx+rbx]; uBytes
0x1800abfe8  mov     ecx, 40h ; '@'; uFlags
0x1800abfed  call    cs:__imp_LocalAlloc
0x1800abff3  mov     r13, rax
0x1800abff6  mov     [rsp+1E0h+var_170], rax
0x1800abffb  test    rax, rax
0x1800abffe  jnz     short loc_1800AC074
0x1800ac000  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800ac007  jz      short loc_1800AC060
0x1800ac009  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800ac010  test    rbx, rbx
0x1800ac013  jz      short loc_1800AC033
0x1800ac015  call    cs:__imp_GetLastError
0x1800ac01b  mov     r8d, eax
0x1800ac01e  lea     rdx, aCreatecseEvent; "CreateCSE_EventSourceAssoc: LocalAlloc "...
0x1800ac025  lea     ecx, [r13+2]
0x1800ac029  mov     rax, rbx
0x1800ac02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac031  jmp     short loc_1800AC060
0x1800ac033  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800ac03a  jz      short loc_1800AC060
0x1800ac03c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800ac043  jz      short loc_1800AC060
0x1800ac045  call    cs:__imp_GetLastError
0x1800ac04b  mov     r8d, eax
0x1800ac04e  lea     rdx, aCreatecseEvent; "CreateCSE_EventSourceAssoc: LocalAlloc "...
0x1800ac055  mov     ecx, 2; unsigned int
0x1800ac05a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800ac05f  nop
0x1800ac060  lea     rcx, [rsp+1E0h+var_170]
0x1800ac065  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800ac06a  mov     ebx, 8007000Eh
0x1800ac06f  jmp     loc_1800AC62E
0x1800ac074  mov     r9, rsi
0x1800ac077  lea     r8, aRsopExtensions_0; "RSOP_ExtensionStatus.extensionGuid=\"%s"...
0x1800ac07e  mov     rdx, rbx; unsigned __int64
0x1800ac081  mov     rcx, rax; unsigned __int16 *
0x1800ac084  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ac089  mov     ebx, eax
0x1800ac08b  mov     dword ptr [rbp+0E0h+var_150], eax
0x1800ac08e  test    eax, eax
0x1800ac090  jns     short loc_1800AC0A1
0x1800ac092  lea     rcx, [rsp+1E0h+var_170]
0x1800ac097  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800ac09c  jmp     loc_1800AC62E
0x1800ac0a1  xorps   xmm0, xmm0
0x1800ac0a4  xor     eax, eax
0x1800ac0a6  movups  [rbp+0E0h+var_120], xmm0
0x1800ac0aa  mov     [rbp+0E0h+var_110], rax
0x1800ac0ae  mov     r12, r15
0x1800ac0b1  mov     [rbp+0E0h+var_160], r15
0x1800ac0b5  lea     rdx, aEventlogsource; "eventLogSource"
0x1800ac0bc  lea     rcx, [rbp+0E0h+var_F8]; this
0x1800ac0c0  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800ac0c5  nop
0x1800ac0c6  lea     rdx, aEventlogname; "eventLogName"
0x1800ac0cd  lea     rcx, [rbp+0E0h+var_F0]; this
0x1800ac0d1  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800ac0d6  nop
0x1800ac0d7  lea     rdx, aExtensionstatu; "extensionStatus"
0x1800ac0de  lea     rcx, [rbp+0E0h+var_108]; this
0x1800ac0e2  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800ac0e7  nop
0x1800ac0e8  lea     rdx, aEventsource; "eventSource"
0x1800ac0ef  lea     rcx, [rbp+0E0h+var_E8]; this
0x1800ac0f3  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800ac0f8  nop
0x1800ac0f9  lea     rdx, aId; "id"
0x1800ac100  lea     rcx, [rbp+0E0h+var_E0]; this
0x1800ac104  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800ac109  nop
0x1800ac10a  mov     eax, 8
0x1800ac10f  mov     word ptr [rbp+0E0h+var_120], ax
0x1800ac113  mov     r14, [rbp+0E0h+var_F8]
0x1800ac117  mov     r15, [rbp+0E0h+var_F0]
0x1800ac11b  mov     rbx, [rbp+0E0h+var_108]
0x1800ac11f  mov     rsi, [rbp+0E0h+var_E8]
0x1800ac123  mov     rdi, [rbp+0E0h+var_E0]
0x1800ac127  mov     rax, [rbp+0E0h+Str]
0x1800ac12b  xor     ecx, ecx
0x1800ac12d  cmp     [rax], cx
0x1800ac130  jz      loc_1800AC63C
0x1800ac136  mov     rdx, r13
0x1800ac139  lea     rcx, [rbp+0E0h+var_160]
0x1800ac13d  call    ??4XBStr@@QEAAXPEBG@Z; XBStr::operator=(ushort const *)
0x1800ac142  mov     r12, [rbp+0E0h+var_160]
0x1800ac146  mov     qword ptr [rbp+0E0h+var_120+8], r12
0x1800ac14a  mov     rcx, [rbp+0E0h+var_138]
0x1800ac14e  mov     rax, [rcx]
0x1800ac151  mov     dword ptr [rsp+1E0h+var_1C0], 0
0x1800ac159  lea     r9, [rbp+0E0h+var_120]
0x1800ac15d  xor     r8d, r8d
0x1800ac160  mov     rdx, rbx
0x1800ac163  mov     rax, [rax+28h]
0x1800ac167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac16c  mov     r13d, eax
0x1800ac16f  test    eax, eax
0x1800ac171  js      loc_1800AC5E5
0x1800ac177  xorps   xmm0, xmm0
0x1800ac17a  movups  xmmword ptr [rbp+0E0h+pguid.Data1], xmm0
0x1800ac17e  lea     rcx, [rbp+0E0h+pguid]; pguid
0x1800ac182  call    cs:__imp_CoCreateGuid
0x1800ac188  mov     r13d, eax
0x1800ac18b  xor     ecx, ecx
0x1800ac18d  test    eax, eax
0x1800ac18f  js      loc_1800AC594
0x1800ac195  movzx   eax, [rbp+0E0h+pguid.Data4+7]
0x1800ac199  movzx   ecx, [rbp+0E0h+pguid.Data4+6]
0x1800ac19d  movzx   edx, [rbp+0E0h+pguid.Data4+5]
0x1800ac1a1  movzx   r8d, [rbp+0E0h+pguid.Data4+4]
0x1800ac1a6  movzx   r9d, [rbp+0E0h+pguid.Data4+3]
0x1800ac1ab  movzx   r10d, [rbp+0E0h+pguid.Data4+2]
0x1800ac1b0  movzx   r11d, [rbp+0E0h+pguid.Data4+1]
0x1800ac1b5  movzx   r13d, [rbp+0E0h+pguid.Data4]
0x1800ac1ba  movzx   ebx, [rbp+0E0h+pguid.Data2]
  ... truncated ...
```
