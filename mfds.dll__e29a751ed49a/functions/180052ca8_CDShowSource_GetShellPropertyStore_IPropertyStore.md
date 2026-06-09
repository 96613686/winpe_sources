# CDShowSource::GetShellPropertyStore(IPropertyStore * *)

- ea: `0x180052ca8`
- end: `0x180053630`
- name: `?GetShellPropertyStore@CDShowSource@@IEAAJPEAPEAUIPropertyStore@@@Z`
- size: `2440`
- prototype: `__int64 __fastcall(CDShowSource *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006c450`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180023f20`
- `0x180032a50`
- `0x18004840c`
- `0x180051ce4`
- `0x180052ca8`
- `0x180053934`
- `0x180072c44`
- `0x180074160`
- `0x1800765a0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180052f38`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180053024`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180052f38`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180053024`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180052e4f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180052e4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535da`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180053104`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180053104`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052d93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052e9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052f84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053070`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005314e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053229`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800532f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800533e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005354e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052d93`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052e9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052f84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053070`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005314e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053229`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800532f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800533e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005354e`
- `MFPlat!MFCreatePathFromURL` at `0x180052e7a`
- `MFPlat!MFCreatePathFromURL` at `0x180052e7a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18005312c`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800533bf`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18005312c`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x1800533bf`

## pseudocode

```c
__int64 __fastcall CDShowSource::GetShellPropertyStore(CDShowSource *this, struct IPropertyStore **a2)
{
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  __int128 *v7; // rax
  __int128 v8; // xmm0
  __int64 v9; // rax
  HRESULT FullPathNameW; // ebx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  CallStackTracing *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  wchar_t *v21; // rbx
  size_t v22; // rax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  const wchar_t *v26; // rax
  const wchar_t *v27; // rbx
  size_t v28; // rax
  CallStackTracing *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  const WCHAR *v32; // rbx
  CallStackTracing *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  const WCHAR *v44; // rax
  CallStackTracing *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  struct IPropertyStore *v51; // rax
  CallStackTracing *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  _BYTE v56[8]; // [rsp+30h] [rbp-29h] BYREF
  void *v57; // [rsp+38h] [rbp-21h] BYREF
  struct IPropertyStore *v58; // [rsp+40h] [rbp-19h] BYREF
  wchar_t *String; // [rsp+48h] [rbp-11h] BYREF
  int v60; // [rsp+50h] [rbp-9h] BYREF
  __int64 v61; // [rsp+54h] [rbp-5h]
  int v62; // [rsp+5Ch] [rbp+3h]
  __int64 v63; // [rsp+60h] [rbp+7h]
  _BYTE ppv[12]; // [rsp+68h] [rbp+Fh] BYREF
  int v65; // [rsp+74h] [rbp+1Bh]
  __int64 v66; // [rsp+78h] [rbp+1Fh]

  v60 &= 0xFFFFFFF8;
  *a2 = 0;
  v58 = 0;
  v61 = 0;
  v63 = 0;
  v62 = 0;
  String = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v56, "CDShowSource::GetShellPropertyStore", 470);
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 137) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 137) + 296LL))(*((_QWORD *)this + 137));
    v7 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 137) + 280LL))(
                       *((_QWORD *)this + 137),
                       ppv);
    v4 = CallStackTracing::s_wpInstance;
    v8 = *v7;
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  v9 = *((_QWORD *)this + 92);
  if ( !v9 )
  {
    FullPathNameW = -2147467261;
    if ( !v4 )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v4 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)v12 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v12, "CDShowSource::GetShellPropertyStore", 470, -2147467261);
    }
    if ( g_wppLevels )
    {
      v13 = 32;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
        this,
        FullPathNameW);
      goto LABEL_130;
    }
    goto LABEL_130;
  }
  v14 = CMFBaseStringT<unsigned short>::PContents(v9 + 16);
  v15 = _o__wcsnicmp(v14, L"file:", 5);
  v16 = *((_QWORD *)this + 92) + 16LL;
  if ( v15 )
  {
    v26 = (const wchar_t *)CMFBaseStringT<unsigned short>::PContents(v16);
    LODWORD(v57) = -1;
    v27 = v26;
    if ( !v26 )
      goto LABEL_56;
    v28 = wcslen(v26);
    if ( (int)UIntPtrToLong(v28, (int *)&v57) >= 0 )
    {
      FullPathNameW = CMFBaseStringT<unsigned short>::_Append(&v60, v27, (unsigned int)v57);
      if ( FullPathNameW >= 0 )
        goto LABEL_56;
    }
    else
    {
      FullPathNameW = -2147024785;
      LODWORD(v61) = -2147024785;
    }
    v29 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext(v29);
      if ( *((_DWORD *)v31 + 499) != FullPathNameW )
        CallStackContext::TraceFailure(v31, "CDShowSource::GetShellPropertyStore", 481, FullPathNameW);
    }
    if ( g_wppLevels )
    {
      v13 = 35;
      goto LABEL_15;
    }
    goto LABEL_130;
  }
  v17 = CMFBaseStringT<unsigned short>::PContents(v16);
  FullPathNameW = MFCreatePathFromURL(v17, &String);
  if ( FullPathNameW >= 0 )
  {
    v21 = String;
    LODWORD(v57) = -1;
    if ( String )
    {
      v22 = wcslen(String);
      if ( (int)UIntPtrToLong(v22, (int *)&v57) < 0 )
      {
        FullPathNameW = -2147024785;
        LODWORD(v61) = -2147024785;
        goto LABEL_32;
      }
      FullPathNameW = CMFBaseStringT<unsigned short>::_Append(&v60, v21, (unsigned int)v57);
      if ( FullPathNameW < 0 )
      {
LABEL_32:
        v23 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext(v23);
          if ( *((_DWORD *)v25 + 499) != FullPathNameW )
            CallStackContext::TraceFailure(v25, "CDShowSource::GetShellPropertyStore", 477, FullPathNameW);
        }
        if ( g_wppLevels )
        {
          v13 = 34;
          goto LABEL_15;
        }
        goto LABEL_130;
      }
    }
LABEL_56:
    v32 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(&v60);
    if ( !PathIsRelativeW(v32) )
    {
      *(_QWORD *)ppv = 0;
      FullPathNameW = SHCreateItemFromParsingName(v32, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)ppv);
      if ( FullPathNameW < 0 )
      {
        v33 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext(v33);
          if ( *((_DWORD *)v35 + 499) != FullPathNameW )
            CallStackContext::TraceFailure(v35, "CDShowSource::GetShellPropertyStore", 487, FullPathNameW);
        }
        if ( !g_wppLevels )
          goto LABEL_69;
        v36 = 36;
LABEL_68:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v36,
          &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
          this,
          FullPathNameW);
LABEL_69:
        ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(ppv);
        goto LABEL_130;
      }
      FullPathNameW = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, struct IPropertyStore **))(**(_QWORD **)ppv
                                                                                                  + 64LL))(
                        *(_QWORD *)ppv,
                        0,
                        &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                        &v58);
      if ( FullPathNameW < 0 )
      {
        v37 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext(v37);
          if ( *((_DWORD *)v39 + 499) != FullPathNameW )
            CallStackContext::TraceFailure(v39, "CDShowSource::GetShellPropertyStore", 489, FullPathNameW);
        }
        if ( !g_wppLevels )
          goto LABEL_69;
        v36 = 37;
        goto LABEL_68;
      }
      ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(ppv);
LABEL_118:
      v51 = v58;
      if ( v58 )
      {
        v58 = 0;
        *a2 = v51;
        goto LABEL_130;
      }
      v52 = CallStackTracing::s_wpInstance;
      FullPathNameW = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext(v52);
        if ( *((_DWORD *)v54 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v54, "CDShowSource::GetShellPropertyStore", 505, -2147418113);
      }
      if ( g_wppLevels )
      {
        v13 = 41;
        goto LABEL_15;
      }
      goto LABEL_130;
    }
    *(_DWORD *)ppv &= 0xFFFFFFF8;
    *(_QWORD *)&ppv[4] = 0;
    v66 = 0;
    v65 = 0;
    v57 = 0;
    FullPathNameW = CDShowSource::GetFullPathNameW(this, v32, ppv);
    if ( FullPathNameW >= 0 )
    {
      v44 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(ppv);
      FullPathNameW = SHCreateItemFromParsingName(v44, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v57);
      if ( FullPathNameW >= 0 )
      {
        FullPathNameW = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, struct IPropertyStore **))(*(_QWORD *)v57 + 64LL))(
                          v57,
                          0,
                          &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                          &v58);
        if ( FullPathNameW >= 0 )
        {
          ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v57);
          CMFBaseStringT<char>::~CMFBaseStringT<char>(ppv);
          goto LABEL_118;
        }
        v48 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v49;
          if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
          {
            v48 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v48 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v48 + 8) )
        {
          v50 = CallStackTracing::GetThreadRelativeContext(v48);
          if ( *((_DWORD *)v50 + 499) != FullPathNameW )
            CallStackContext::TraceFailure(v50, "CDShowSource::GetShellPropertyStore", 502, FullPathNameW);
        }
        if ( !g_wppLevels )
        {
LABEL_94:
          ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v57);
          CMFBaseStringT<char>::~CMFBaseStringT<char>(ppv);
          goto LABEL_130;
        }
        v43 = 40;
      }
      else
      {
        v45 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext(v45);
          if ( *((_DWORD *)v47 + 499) != FullPathNameW )
            CallStackContext::TraceFailure(v47, "CDShowSource::GetShellPropertyStore", 500, FullPathNameW);
        }
        if ( !g_wppLevels )
          goto LABEL_94;
        v43 = 39;
      }
    }
    else
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext(v40);
        if ( *((_DWORD *)v42 + 499) != FullPathNameW )
          CallStackContext::TraceFailure(v42, "CDShowSource::GetShellPropertyStore", 498, FullPathNameW);
      }
      if ( !g_wppLevels )
        goto LABEL_94;
      v43 = 38;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v43,
      &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
      this,
      FullPathNameW);
    goto LABEL_94;
  }
  v18 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext(v18);
    if ( *((_DWORD *)v20 + 499) != FullPathNameW )
      CallStackContext::TraceFailure(v20, "CDShowSource::GetShellPropertyStore", 475, FullPathNameW);
  }
  if ( g_wppLevels )
  {
    v13 = 33;
    goto LABEL_15;
  }
LABEL_130:
  CoTaskMemFree(String);
  String = 0;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
  CMFBaseStringT<char>::~CMFBaseStringT<char>(&v60);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v58);
  return (unsigned int)FullPathNameW;
}

```

## disassembly

```asm
0x180052ca8  mov     [rsp-8+arg_10], rbx
0x180052cad  mov     [rsp-8+arg_18], rsi
0x180052cb2  push    rbp
0x180052cb3  push    rdi
0x180052cb4  push    r12
0x180052cb6  push    r14
0x180052cb8  push    r15
0x180052cba  lea     rbp, [rsp-37h]
0x180052cbf  sub     rsp, 90h
0x180052cc6  mov     rax, cs:__security_cookie
0x180052ccd  xor     rax, rsp
0x180052cd0  mov     [rbp+57h+var_30], rax
0x180052cd4  and     [rbp+57h+var_60], 0FFFFFFF8h
0x180052cd8  lea     r12, aCdshowsourceGe_0; "CDShowSource::GetShellPropertyStore"
0x180052cdf  xor     r15d, r15d
0x180052ce2  mov     r14, rdx
0x180052ce5  mov     [rdx], r15
0x180052ce8  mov     rsi, rcx
0x180052ceb  mov     rdx, r12; char *
0x180052cee  mov     [rbp+57h+var_70], r15
0x180052cf2  mov     r8d, 1D6h; int
0x180052cf8  mov     [rbp+57h+var_5C], r15
0x180052cfc  lea     rcx, [rbp+57h+var_80]; this
0x180052d00  mov     [rbp+57h+var_50], r15
0x180052d04  mov     [rbp+57h+var_54], r15d
0x180052d08  mov     [rbp+57h+String], r15
0x180052d0c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052d11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180052d18  cmp     [rcx+8], r15b
0x180052d1c  jz      short loc_180052D79
0x180052d1e  cmp     [rsi+448h], r15
0x180052d25  jz      short loc_180052D79
0x180052d27  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052d2c  mov     rcx, [rsi+448h]
0x180052d33  mov     rdi, rax
0x180052d36  mov     rdx, [rcx]
0x180052d39  mov     rax, [rdx+128h]
0x180052d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d45  mov     rcx, [rsi+448h]
0x180052d4c  mov     ebx, eax
0x180052d4e  mov     rdx, [rcx]
0x180052d51  mov     rax, [rdx+118h]
0x180052d58  lea     rdx, [rbp+57h+ppv]
0x180052d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052d68  movups  xmm0, xmmword ptr [rax]
0x180052d6b  mov     [rdi+7E0h], ebx
0x180052d71  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180052d79  mov     rax, [rsi+2E0h]
0x180052d80  test    rax, rax
0x180052d83  jnz     loc_180052E36
0x180052d89  mov     ebx, 80004003h
0x180052d8e  test    rcx, rcx
0x180052d91  jnz     short loc_180052DDA
0x180052d93  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052d9a  nop     dword ptr [rax+rax+00h]
0x180052d9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052da6  mov     rcx, rax
0x180052da9  test    rax, rax
0x180052dac  jz      short loc_180052DCC
0x180052dae  mov     rax, [rax]
0x180052db1  mov     edx, 7F0h
0x180052db6  mov     rax, [rax+8]
0x180052dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dbf  test    eax, eax
0x180052dc1  jz      short loc_180052DCC
0x180052dc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052dca  jmp     short loc_180052DDA
0x180052dcc  lea     rcx, qword_1800EB130; this
0x180052dd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052dda  cmp     [rcx+8], r15b
0x180052dde  jz      short loc_180052E01
0x180052de0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052de5  cmp     [rax+7CCh], ebx
0x180052deb  jz      short loc_180052E01
0x180052ded  mov     r9d, ebx; int
0x180052df0  mov     r8d, 1D6h; int
0x180052df6  mov     rdx, r12; char *
0x180052df9  mov     rcx, rax; this
0x180052dfc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052e01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180052e08  jb      loc_1800535D6
0x180052e0e  mov     edx, 20h ; ' '
0x180052e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180052e1a  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x180052e21  mov     r9, rsi
0x180052e24  mov     [rsp+0B0h+var_90], ebx
0x180052e28  mov     rcx, [rcx+10h]
0x180052e2c  call    WPP_SF_qD
0x180052e31  jmp     loc_1800535D6
0x180052e36  lea     rcx, [rax+10h]
0x180052e3a  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180052e3f  lea     rdx, aFile_0; "file:"
0x180052e46  mov     rcx, rax
0x180052e49  mov     r8d, 5
0x180052e4f  call    cs:__imp__o__wcsnicmp
0x180052e56  nop     dword ptr [rax+rax+00h]
0x180052e5b  mov     rcx, [rsi+2E0h]
0x180052e62  add     rcx, 10h
0x180052e66  test    eax, eax
0x180052e68  jnz     loc_180053009
0x180052e6e  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180052e73  lea     rdx, [rbp+57h+String]
0x180052e77  mov     rcx, rax
0x180052e7a  call    cs:__imp_MFCreatePathFromURL
0x180052e81  nop     dword ptr [rax+rax+00h]
0x180052e86  mov     ebx, eax
0x180052e88  test    eax, eax
0x180052e8a  jns     loc_180052F21
0x180052e90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052e97  test    rcx, rcx
0x180052e9a  jnz     short loc_180052EE3
0x180052e9c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052ea3  nop     dword ptr [rax+rax+00h]
0x180052ea8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052eaf  mov     rcx, rax
0x180052eb2  test    rax, rax
0x180052eb5  jz      short loc_180052ED5
0x180052eb7  mov     rax, [rax]
0x180052eba  mov     edx, 7F0h
0x180052ebf  mov     rax, [rax+8]
0x180052ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ec8  test    eax, eax
0x180052eca  jz      short loc_180052ED5
0x180052ecc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ed3  jmp     short loc_180052EE3
0x180052ed5  lea     rcx, qword_1800EB130; this
0x180052edc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ee3  cmp     [rcx+8], r15b
0x180052ee7  jz      short loc_180052F0A
0x180052ee9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052eee  cmp     [rax+7CCh], ebx
0x180052ef4  jz      short loc_180052F0A
0x180052ef6  mov     r9d, ebx; int
0x180052ef9  mov     r8d, 1DBh; int
0x180052eff  mov     rdx, r12; char *
0x180052f02  mov     rcx, rax; this
0x180052f05  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052f0a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180052f11  jb      loc_1800535D6
0x180052f17  mov     edx, 21h ; '!'
0x180052f1c  jmp     loc_180052E13
0x180052f21  mov     rbx, [rbp+57h+String]
0x180052f25  mov     dword ptr [rbp+57h+var_78], 0FFFFFFFFh
0x180052f2c  test    rbx, rbx
0x180052f2f  jz      loc_1800530F5
0x180052f35  mov     rcx, rbx; String
0x180052f38  call    cs:__imp_wcslen
0x180052f3f  nop     dword ptr [rax+rax+00h]
0x180052f44  mov     rcx, rax; unsigned __int64
0x180052f47  lea     rdx, [rbp+57h+var_78]; int *
0x180052f4b  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180052f50  test    eax, eax
0x180052f52  jns     short loc_180052F5E
0x180052f54  mov     ebx, 8007006Fh
0x180052f59  mov     dword ptr [rbp+57h+var_5C], ebx
0x180052f5c  jmp     short loc_180052F78
0x180052f5e  mov     r8d, dword ptr [rbp+57h+var_78]
0x180052f62  lea     rcx, [rbp+57h+var_60]
0x180052f66  mov     rdx, rbx
0x180052f69  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x180052f6e  mov     ebx, eax
0x180052f70  test    eax, eax
0x180052f72  jns     loc_1800530F5
0x180052f78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f7f  test    rcx, rcx
0x180052f82  jnz     short loc_180052FCB
0x180052f84  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052f8b  nop     dword ptr [rax+rax+00h]
0x180052f90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f97  mov     rcx, rax
0x180052f9a  test    rax, rax
0x180052f9d  jz      short loc_180052FBD
0x180052f9f  mov     rax, [rax]
0x180052fa2  mov     edx, 7F0h
0x180052fa7  mov     rax, [rax+8]
0x180052fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fb0  test    eax, eax
0x180052fb2  jz      short loc_180052FBD
0x180052fb4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052fbb  jmp     short loc_180052FCB
0x180052fbd  lea     rcx, qword_1800EB130; this
0x180052fc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052fcb  cmp     [rcx+8], r15b
0x180052fcf  jz      short loc_180052FF2
0x180052fd1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052fd6  cmp     [rax+7CCh], ebx
0x180052fdc  jz      short loc_180052FF2
0x180052fde  mov     r9d, ebx; int
0x180052fe1  mov     r8d, 1DDh; int
0x180052fe7  mov     rdx, r12; char *
0x180052fea  mov     rcx, rax; this
0x180052fed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052ff2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180052ff9  jb      loc_1800535D6
0x180052fff  mov     edx, 22h ; '"'
0x180053004  jmp     loc_180052E13
0x180053009  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18005300e  mov     dword ptr [rbp+57h+var_78], 0FFFFFFFFh
0x180053015  mov     rbx, rax
0x180053018  test    rax, rax
0x18005301b  jz      loc_1800530F5
0x180053021  mov     rcx, rax; String
0x180053024  call    cs:__imp_wcslen
0x18005302b  nop     dword ptr [rax+rax+00h]
0x180053030  mov     rcx, rax; unsigned __int64
0x180053033  lea     rdx, [rbp+57h+var_78]; int *
0x180053037  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18005303c  test    eax, eax
0x18005303e  jns     short loc_18005304A
0x180053040  mov     ebx, 8007006Fh
0x180053045  mov     dword ptr [rbp+57h+var_5C], ebx
0x180053048  jmp     short loc_180053064
0x18005304a  mov     r8d, dword ptr [rbp+57h+var_78]
0x18005304e  lea     rcx, [rbp+57h+var_60]
0x180053052  mov     rdx, rbx
0x180053055  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x18005305a  mov     ebx, eax
0x18005305c  test    eax, eax
0x18005305e  jns     loc_1800530F5
0x180053064  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005306b  test    rcx, rcx
0x18005306e  jnz     short loc_1800530B7
0x180053070  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053077  nop     dword ptr [rax+rax+00h]
0x18005307c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053083  mov     rcx, rax
0x180053086  test    rax, rax
0x180053089  jz      short loc_1800530A9
0x18005308b  mov     rax, [rax]
0x18005308e  mov     edx, 7F0h
0x180053093  mov     rax, [rax+8]
0x180053097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005309c  test    eax, eax
0x18005309e  jz      short loc_1800530A9
0x1800530a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800530a7  jmp     short loc_1800530B7
0x1800530a9  lea     rcx, qword_1800EB130; this
0x1800530b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800530b7  cmp     [rcx+8], r15b
0x1800530bb  jz      short loc_1800530DE
0x1800530bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800530c2  cmp     [rax+7CCh], ebx
0x1800530c8  jz      short loc_1800530DE
0x1800530ca  mov     r9d, ebx; int
0x1800530cd  mov     r8d, 1E1h; int
0x1800530d3  mov     rdx, r12; char *
0x1800530d6  mov     rcx, rax; this
0x1800530d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800530de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800530e5  jb      loc_1800535D6
0x1800530eb  mov     edx, 23h ; '#'
0x1800530f0  jmp     loc_180052E13
0x1800530f5  lea     rcx, [rbp+57h+var_60]
0x1800530f9  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x1800530fe  mov     rcx, rax; pszPath
0x180053101  mov     rbx, rax
0x180053104  call    cs:__imp_PathIsRelativeW
0x18005310b  nop     dword ptr [rax+rax+00h]
0x180053110  test    eax, eax
0x180053112  jnz     loc_1800532BC
0x180053118  lea     r9, [rbp+57h+ppv]; ppv
0x18005311c  mov     qword ptr [rbp+57h+ppv], r15
0x180053120  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180053127  xor     edx, edx; pbc
0x180053129  mov     rcx, rbx; pszPath
0x18005312c  call    cs:__imp_SHCreateItemFromParsingName
0x180053133  nop     dword ptr [rax+rax+00h]
0x180053138  mov     ebx, eax
0x18005313a  test    eax, eax
0x18005313c  jns     loc_1800531F6
0x180053142  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053149  test    rcx, rcx
0x18005314c  jnz     short loc_180053195
0x18005314e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053155  nop     dword ptr [rax+rax+00h]
0x18005315a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053161  mov     rcx, rax
0x180053164  test    rax, rax
0x180053167  jz      short loc_180053187
0x180053169  mov     rax, [rax]
0x18005316c  mov     edx, 7F0h
0x180053171  mov     rax, [rax+8]
0x180053175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005317a  test    eax, eax
0x18005317c  jz      short loc_180053187
0x18005317e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053185  jmp     short loc_180053195
0x180053187  lea     rcx, qword_1800EB130; this
0x18005318e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053195  cmp     [rcx+8], r15b
0x180053199  jz      short loc_1800531BC
0x18005319b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800531a0  cmp     [rax+7CCh], ebx
0x1800531a6  jz      short loc_1800531BC
0x1800531a8  mov     r9d, ebx; int
0x1800531ab  mov     r8d, 1E7h; int
0x1800531b1  mov     rdx, r12; char *
0x1800531b4  mov     rcx, rax; this
0x1800531b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
