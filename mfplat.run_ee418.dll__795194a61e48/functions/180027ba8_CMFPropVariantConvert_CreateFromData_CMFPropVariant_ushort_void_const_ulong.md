# CMFPropVariantConvert::CreateFromData(CMFPropVariant *,ushort,void const *,ulong)

- ea: `0x180027ba8`
- end: `0x180028873`
- name: `?CreateFromData@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@GPEBXK@Z`
- size: `3275`
- prototype: `__int64 __fastcall(struct CMFPropVariant *, unsigned __int16, _BYTE *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027b90`
- `0x180028880`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x180027ba8`
- `0x180029040`
- `0x18006fbbc`
- `0x180121581`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027c0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027d32`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027c0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027d32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027d8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027c2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027d46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027c2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028518`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180028843`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180028843`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002879a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800287d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002879a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800287d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028814`

## string_xrefs

- `0x180027bea`: `CMFPropVariantConvert::CreateFromData`
- `0x180027c3d`: `CMFPropVariantConvert::CreateFromData`
- `0x180028041`: `CMFPropVariantConvert::CreateFromData`
- `0x1800280e3`: `CMFPropVariantConvert::CreateFromData`
- `0x180028172`: `CMFPropVariantConvert::CreateFromData`
- `0x18002820a`: `CMFPropVariantConvert::CreateFromData`
- `0x1800282a2`: `CMFPropVariantConvert::CreateFromData`
- `0x18002833a`: `CMFPropVariantConvert::CreateFromData`
- `0x1800283cb`: `CMFPropVariantConvert::CreateFromData`
- `0x180028465`: `CMFPropVariantConvert::CreateFromData`
- `0x180028501`: `CMFPropVariantConvert::CreateFromData`
- `0x180028631`: `CMFPropVariantConvert::CreateFromData`
- `0x180028668`: `CMFPropVariantConvert::CreateFromData`
- `0x180028699`: `CMFPropVariantConvert::CreateFromData`

## pseudocode

```c
__int64 __fastcall CMFPropVariantConvert::CreateFromData(
        struct CMFPropVariant *a1,
        unsigned __int16 a2,
        _BYTE *a3,
        unsigned int a4)
{
  size_t cchWideChar; // rsi
  CallStackTracing *v8; // rdi
  CallStackContext *p_m_context; // rbx
  DWORD LastError; // r14d
  CallStackContext *Value; // rax
  __int64 m_dwDepth; // rax
  __int64 v13; // rax
  __int16 v14; // dx
  unsigned int v15; // ecx
  signed int v16; // ebx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned __int16 **p_bstrVal; // rdi
  $4F14566F3E030B26BE335E185333FBC4 *v21; // rcx
  __int16 v22; // r14
  CallStackTracing *v23; // rdi
  CallStackContext *v24; // rsi
  DWORD v25; // ebp
  CallStackContext *v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v30; // rdx
  unsigned int v31; // ecx
  CallStackTracing *v32; // rcx
  __int64 v33; // rax
  CallStackTracing *v34; // rcx
  __int64 v35; // rax
  struct CallStackContext *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  __int64 v41; // rdx
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  CallStackTracing *v45; // rcx
  struct CallStackContext *v46; // rax
  CallStackTracing *v47; // rcx
  __int64 v48; // rdx
  struct CallStackContext *v49; // rax
  struct CallStackContext *v50; // rax
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  signed int v53; // eax
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v58; // rcx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  _OWORD *v70; // rax
  unsigned __int8 *v71; // rax
  _WORD *v72; // rax
  WCHAR *lpWideCharStr; // rax

  cchWideChar = a4;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
  }
  v8 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    p_m_context = &CallStackTracing::s_wpInstance->m_context;
    LastError = GetLastError();
    Value = (CallStackContext *)TlsGetValue(v8->m_dwTLSIndex);
    if ( Value )
    {
      p_m_context = Value;
    }
    else if ( !GetLastError() )
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v32 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v33 = v32->AllocateNewContext(v32);
      if ( v33 )
        p_m_context = (CallStackContext *)v33;
    }
    SetLastError(LastError);
    m_dwDepth = p_m_context->m_dwDepth;
    if ( (unsigned int)m_dwDepth < p_m_context->m_dwMaxDepth )
    {
      v13 = m_dwDepth;
      p_m_context->m_rgInfo[v13].m_pszFunction = "CMFPropVariantConvert::CreateFromData";
      p_m_context->m_rgInfo[v13].m_lineNumber = 799;
    }
    ++p_m_context->m_dwDepth;
  }
  if ( a1->vt )
  {
    v16 = -1072875798;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( ThreadRelativeContext->m_result != -1072875798 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariantConvert::CreateFromData", 812, -1072875798);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_24;
    v30 = 55;
LABEL_35:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v16);
    goto LABEL_24;
  }
  a1->vt = a2;
  if ( (a2 & 0x1000) != 0 )
  {
    v16 = -1072875797;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v36 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v36->m_result != -1072875797 )
        CallStackContext::TraceFailure(v36, "CMFPropVariantConvert::CreateFromData", 825, -1072875797);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_24;
    v30 = 56;
    goto LABEL_35;
  }
  if ( (_DWORD)cchWideChar )
  {
    v14 = 0;
    if ( a2 == 11 )
    {
      LODWORD(v58) = cchWideChar;
      while ( (_DWORD)v58 )
      {
        v58 = (unsigned int)(v58 - 1);
        if ( a3[v58] )
        {
          v14 = -1;
          break;
        }
      }
LABEL_14:
      v15 = a2 & 0xFFF;
      v16 = 0;
      if ( v15 <= 0x13 )
      {
        if ( v15 == 19 )
          goto LABEL_19;
        v17 = v15 - 2;
        if ( !v17 )
          goto LABEL_19;
        v18 = v17 - 1;
        if ( !v18 )
          goto LABEL_19;
        v19 = v18 - 6;
        if ( !v19 )
          goto LABEL_19;
        v31 = v19 - 2;
        if ( !v31 )
        {
          p_bstrVal = &a1->bstrVal;
          a1->iVal = v14;
          goto LABEL_22;
        }
        v59 = v31 - 2;
        if ( !v59 )
          goto LABEL_19;
        v60 = v59 - 1;
        if ( v60 )
        {
          v61 = v60 - 2;
          if ( !v61 || v61 - 1 < 2 )
            goto LABEL_19;
          goto LABEL_79;
        }
        if ( (_DWORD)cchWideChar == 16 )
        {
          p_bstrVal = &a1->bstrVal;
          *(_OWORD *)&a1->vt = *(_OWORD *)a3;
          goto LABEL_22;
        }
LABEL_200:
        v16 = -2147024809;
        goto LABEL_201;
      }
      v62 = v15 - 20;
      if ( !v62 || (v63 = v62 - 1) == 0 || (v64 = v63 - 1) == 0 || (v65 = v64 - 1) == 0 )
      {
LABEL_19:
        if ( (unsigned int)cchWideChar <= 8 )
        {
          p_bstrVal = &a1->bstrVal;
          v21 = &a1->decVal.8;
LABEL_21:
          memcpy_0(v21, a3, cchWideChar);
          goto LABEL_22;
        }
        goto LABEL_200;
      }
      v66 = v65 - 7;
      if ( v66 )
      {
        v67 = v66 - 1;
        if ( v67 )
        {
          v68 = v67 - 33;
          if ( !v68 )
            goto LABEL_19;
          v69 = v68 - 1;
          if ( v69 )
          {
            if ( v69 != 7 )
            {
LABEL_79:
              v16 = -2147024809;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
              if ( CallStackTracing::s_wpInstance->m_fEnabled )
              {
                v39 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                if ( v39->m_result != -2147024809 )
                  CallStackContext::TraceFailure(v39, "CMFPropVariantConvert::CreateFromData", 970, -2147024809);
              }
              if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                goto LABEL_201;
              v38 = 66;
              goto LABEL_129;
            }
            if ( (_DWORD)cchWideChar != 16 )
              goto LABEL_200;
            v70 = CoTaskMemAlloc(0x10u);
            p_bstrVal = &a1->bstrVal;
            a1->decVal.Lo64 = (unsigned __int64)v70;
            if ( v70 )
            {
              *v70 = *(_OWORD *)a3;
              goto LABEL_22;
            }
            v40 = CallStackTracing::s_wpInstance;
            v16 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v40 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v40 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v40->m_fEnabled )
            {
              v42 = CallStackTracing::GetThreadRelativeContext(v40);
              if ( v42->m_result != -2147024882 )
                CallStackContext::TraceFailure(v42, "CMFPropVariantConvert::CreateFromData", 927, -2147024882);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_201;
            v41 = 65;
          }
          else
          {
            v71 = (unsigned __int8 *)CoTaskMemAlloc(cchWideChar);
            a1->bstrblobVal.pData = v71;
            if ( v71 )
            {
              p_bstrVal = &a1->bstrVal;
              v21 = ($4F14566F3E030B26BE335E185333FBC4 *)v71;
              a1->decVal.Lo32 = cchWideChar;
              goto LABEL_21;
            }
            v43 = CallStackTracing::s_wpInstance;
            v16 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v43 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v43 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v43->m_fEnabled )
            {
              v44 = CallStackTracing::GetThreadRelativeContext(v43);
              if ( v44->m_result != -2147024882 )
                CallStackContext::TraceFailure(v44, "CMFPropVariantConvert::CreateFromData", 914, -2147024882);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
LABEL_201:
              CMFPropVariant::Clear((PROPVARIANT *)a1);
              goto LABEL_24;
            }
            v41 = 64;
          }
LABEL_138:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v41,
            &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
            0,
            -2147024882);
          goto LABEL_201;
        }
        if ( (cchWideChar & 1) != 0 || (unsigned int)cchWideChar < 2 )
        {
          v16 = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
          if ( CallStackTracing::s_wpInstance->m_fEnabled )
          {
            v50 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( v50->m_result != -2147024809 )
              CallStackContext::TraceFailure(v50, "CMFPropVariantConvert::CreateFromData", 901, -2147024809);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_201;
          v38 = 61;
LABEL_129:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v38,
            &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
            0,
            -2147024809);
          goto LABEL_201;
        }
        v72 = CoTaskMemAlloc(cchWideChar);
        p_bstrVal = &a1->bstrVal;
        a1->decVal.Lo64 = (unsigned __int64)v72;
        if ( !v72 )
        {
          v45 = CallStackTracing::s_wpInstance;
          v16 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v45 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v45 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v45->m_fEnabled )
          {
            v46 = CallStackTracing::GetThreadRelativeContext(v45);
            if ( v46->m_result != -2147024882 )
              CallStackContext::TraceFailure(v46, "CMFPropVariantConvert::CreateFromData", 905, -2147024882);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_201;
          v41 = 62;
          goto LABEL_138;
        }
        *v72 = 0;
        v16 = StringCchCopyW(*p_bstrVal, cchWideChar >> 1, (const unsigned __int16 *)a3);
        if ( v16 < 0 )
        {
          v47 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v47 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v47 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v47->m_fEnabled )
          {
            v49 = CallStackTracing::GetThreadRelativeContext(v47);
            if ( v49->m_result != v16 )
              CallStackContext::TraceFailure(v49, "CMFPropVariantConvert::CreateFromData", 909, v16);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_201;
          v48 = 63;
          goto LABEL_151;
        }
      }
      else
      {
        lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2 * cchWideChar);
        p_bstrVal = &a1->bstrVal;
        a1->decVal.Lo64 = (unsigned __int64)lpWideCharStr;
        if ( !lpWideCharStr )
        {
          v51 = CallStackTracing::s_wpInstance;
          v16 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v51 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v51 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v51->m_fEnabled )
          {
            v52 = CallStackTracing::GetThreadRelativeContext(v51);
            if ( v52->m_result != -2147024882 )
              CallStackContext::TraceFailure(v52, "CMFPropVariantConvert::CreateFromData", 876, -2147024882);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_201;
          v41 = 58;
          goto LABEL_138;
        }
        a1->vt = 31;
        if ( !MultiByteToWideChar(0, 0, a3, cchWideChar, lpWideCharStr, cchWideChar) )
        {
          v53 = GetLastError();
          v16 = v53;
          if ( v53 > 0 )
            v16 = (unsigned __int16)v53 | 0x80070000;
          v54 = CallStackTracing::s_wpInstance;
          if ( v16 < 0 )
          {
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v54 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v54 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v54->m_fEnabled )
            {
              v55 = CallStackTracing::GetThreadRelativeContext(v54);
              if ( v55->m_result != v16 )
                CallStackContext::TraceFailure(v55, "CMFPropVariantConvert::CreateFromData", 889, v16);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_201;
            v48 = 59;
          }
          else
          {
            v16 = -2147418113;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v54 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v54 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v54->m_fEnabled )
            {
              v56 = CallStackTracing::GetThreadRelativeContext(v54);
              if ( v56->m_result != -2147418113 )
                CallStackContext::TraceFailure(v56, "CMFPropVariantConvert::CreateFromData", 890, -2147418113);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_201;
            v48 = 60;
          }
LABEL_151:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v48, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v16);
          goto LABEL_201;
        }
        (*p_bstrVal)[(unsigned int)(cchWideChar - 1)] = 0;
      }
LABEL_22:
      v22 = a1->vt & 0xFFF;
      if ( (v22 == 13 || v22 == 9) && *p_bstrVal )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)*p_bstrVal + 8LL))(*p_bstrVal);
      goto LABEL_24;
    }
LABEL_12:
    if ( a2 == 8 )
    {
      a1->vt = 31;
      a2 = 31;
    }
    goto LABEL_14;
  }
  if ( !a2 || a2 == 65 )
  {
    v14 = 0;
    goto LABEL_12;
  }
  v16 = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( !((unsigned int (__fastcall *)(CallStackTracing *, __int64, __int64))stru_1801FC290.CheckVersionMatch)(
            &stru_1801FC290,
            2032,
            8) )
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
  }
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v37 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( v37->m_result != -2147024809 )
      CallStackContext::TraceFailure(v37, "CMFPropVariantConvert::CreateFromData", 834, -2147024809);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, -2147024809);
LABEL_24:
  v23 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v24 = &CallStackTracing::s_wpInstance->m_context;
    v25 = GetLastError();
    v26 = (CallStackContext *)TlsGetValue(v23->m_dwTLSIndex);
    if ( v26 )
    {
      v24 = v26;
    }
    else if ( !GetLastError() )
    {
      v34 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v34 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v35 = v34->AllocateNewContext(v34);
      if ( v35 )
        v24 = (CallStackContext *)v35;
    }
    SetLastError(v25);
    v27 = v24->m_dwDepth;
    if ( v27 )
    {
      v28 = v27 - 1;
      v24->m_dwDepth = v28;
      if ( !v28 )
      {
        v24->m_dwDepth = 0;
        *(_QWORD *)&v24->m_instanceId = 0;
        v24->m_result = 0;
        v24->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v24->m_dwErrorsInContext = 0;
        v24->m_dwThreadID = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180027ba8  push    rbx
0x180027baa  push    rbp
0x180027bab  push    rsi
0x180027bac  push    rdi
0x180027bad  push    r12
0x180027baf  push    r13
0x180027bb1  push    r14
0x180027bb3  push    r15
0x180027bb5  sub     rsp, 38h
0x180027bb9  xor     r13d, r13d
0x180027bbc  mov     esi, r9d
0x180027bbf  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180027bc6  lea     rbx, stru_1801F8A30
0x180027bcd  mov     r12, r8
0x180027bd0  lea     r14, stru_1801FC290
0x180027bd7  movzx   ebp, dx
0x180027bda  mov     r15, rcx
0x180027bdd  jz      loc_180027E41
0x180027be3  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027bea  lea     rcx, aCmfpropvariant_10; "CMFPropVariantConvert::CreateFromData"
0x180027bf1  cmp     [rdi+8], r13b
0x180027bf5  jz      loc_180027FD8
0x180027bfb  lea     rbx, [rdi+0D0h]
0x180027c02  call    cs:__imp_GetLastError
0x180027c08  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180027c0b  mov     r14d, eax
0x180027c0e  call    cs:__imp_TlsGetValue
0x180027c14  test    rax, rax
0x180027c17  jz      loc_180027EE8
0x180027c1d  mov     rbx, rax
0x180027c20  lea     rdi, stru_1801F8A30
0x180027c27  mov     ecx, r14d; dwErrCode
0x180027c2a  call    cs:__imp_SetLastError
0x180027c30  mov     eax, [rbx+7C4h]
0x180027c36  lea     r14, stru_1801FC290
0x180027c3d  lea     rcx, aCmfpropvariant_10; "CMFPropVariantConvert::CreateFromData"
0x180027c44  cmp     eax, [rbx+7C8h]
0x180027c4a  jnb     short loc_180027C5B
0x180027c4c  add     rax, rax
0x180027c4f  mov     [rbx+rax*8], rcx
0x180027c53  mov     dword ptr [rbx+rax*8+8], 31Fh
0x180027c5b  inc     dword ptr [rbx+7C4h]
0x180027c61  cmp     r13w, [r15]
0x180027c65  jnz     loc_180027DAB
0x180027c6b  movzx   ecx, bp
0x180027c6e  mov     [r15], bp
0x180027c72  mov     eax, 1000h
0x180027c77  and     cx, ax
0x180027c7a  cmp     r13w, cx
0x180027c7e  jnz     loc_180027EAE
0x180027c84  mov     ecx, 1Fh
0x180027c89  lea     edx, [rcx+22h]
0x180027c8c  lea     r8d, [rcx-17h]
0x180027c90  test    esi, esi
0x180027c92  jz      loc_18002805B
0x180027c98  lea     eax, [rcx-14h]
0x180027c9b  mov     edx, r13d
0x180027c9e  cmp     ax, bp
0x180027ca1  jz      loc_1800286BB
0x180027ca7  cmp     r8w, bp
0x180027cab  jz      loc_180027E35
0x180027cb1  movzx   ecx, bp
0x180027cb4  mov     r14d, 0FFFh
0x180027cba  and     ecx, r14d
0x180027cbd  mov     ebx, r13d
0x180027cc0  cmp     ecx, 13h
0x180027cc3  ja      loc_18002871F
0x180027cc9  jz      short loc_180027CDE
0x180027ccb  sub     ecx, 2
0x180027cce  jz      short loc_180027CDE
0x180027cd0  sub     ecx, 1
0x180027cd3  jz      short loc_180027CDE
0x180027cd5  sub     ecx, 6
0x180027cd8  jnz     loc_180027E20
0x180027cde  cmp     esi, r8d
0x180027ce1  ja      loc_180028861
0x180027ce7  lea     rdi, [r15+8]
0x180027ceb  mov     rcx, rdi; void *
0x180027cee  mov     r8, rsi; Size
0x180027cf1  mov     rdx, r12; Src
0x180027cf4  call    memcpy_0
0x180027cf9  and     r14w, [r15]
0x180027cfd  cmp     r14w, 0Dh
0x180027d02  jz      loc_180027E03
0x180027d08  cmp     r14w, 9
0x180027d0d  jz      loc_180027E03
0x180027d13  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027d1a  cmp     [rdi+8], r13b
0x180027d1e  jz      short loc_180027D98
0x180027d20  lea     rsi, [rdi+0D0h]
0x180027d27  call    cs:__imp_GetLastError
0x180027d2d  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180027d30  mov     ebp, eax
0x180027d32  call    cs:__imp_TlsGetValue
0x180027d38  test    rax, rax
0x180027d3b  jz      loc_180027F24
0x180027d41  mov     rsi, rax
0x180027d44  mov     ecx, ebp; dwErrCode
0x180027d46  call    cs:__imp_SetLastError
0x180027d4c  mov     eax, [rsi+7C4h]
0x180027d52  test    eax, eax
0x180027d54  jz      short loc_180027D98
0x180027d56  sub     eax, 1
0x180027d59  mov     [rsi+7C4h], eax
0x180027d5f  jnz     short loc_180027D98
0x180027d61  mov     [rsi+7C4h], r13d
0x180027d68  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180027d6f  mov     [rsi+7E0h], r13
0x180027d76  mov     [rsi+7CCh], r13d
0x180027d7d  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x180027d85  mov     [rsi+7E8h], r13d
0x180027d8c  call    cs:__imp_GetCurrentThreadId
0x180027d92  mov     [rsi+7C0h], eax
0x180027d98  mov     eax, ebx
0x180027d9a  add     rsp, 38h
0x180027d9e  pop     r15
0x180027da0  pop     r14
0x180027da2  pop     r13
0x180027da4  pop     r12
0x180027da6  pop     rdi
0x180027da7  pop     rsi
0x180027da8  pop     rbp
0x180027da9  pop     rbx
0x180027daa  retn
0x180027dab  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180027db2  mov     ebx, 0C00D36EAh
0x180027db7  jz      loc_180027E74
0x180027dbd  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027dc4  cmp     [rdi+8], r13b
0x180027dc8  jnz     loc_180028682
0x180027dce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027dd5  jb      loc_180027D13
0x180027ddb  mov     edx, 37h ; '7'
0x180027de0  mov     dword ptr [rsp+78h+lpWideCharStr], ebx
0x180027de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027deb  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180027df2  xor     r9d, r9d
0x180027df5  mov     rcx, [rcx+10h]
0x180027df9  call    WPP_SF_qD
0x180027dfe  jmp     loc_180027D13
0x180027e03  mov     rcx, [rdi]
0x180027e06  test    rcx, rcx
0x180027e09  jz      loc_180027D13
0x180027e0f  mov     rax, [rcx]
0x180027e12  mov     rax, [rax+8]
0x180027e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e1b  jmp     loc_180027D13
0x180027e20  sub     ecx, 2
0x180027e23  jnz     loc_1800286D5
0x180027e29  lea     rdi, [r15+8]
0x180027e2d  mov     [rdi], dx
0x180027e30  jmp     loc_180027CF9
0x180027e35  mov     [r15], cx
0x180027e39  movzx   ebp, cx
0x180027e3c  jmp     loc_180027CB1
0x180027e41  mov     rax, cs:stru_1801FC290.__vftable
0x180027e48  mov     edx, 7F0h
0x180027e4d  mov     rcx, r14
0x180027e50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x180027e57  mov     rax, [rax+8]
0x180027e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e60  test    eax, eax
0x180027e62  jnz     loc_180027BE3
0x180027e68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027e6f  jmp     loc_180027BE3
0x180027e74  mov     rax, cs:stru_1801FC290.__vftable
0x180027e7b  mov     edx, 7F0h
0x180027e80  mov     rcx, r14
0x180027e83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x180027e8a  mov     rax, [rax+8]
0x180027e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e93  test    eax, eax
0x180027e95  jnz     loc_180027DBD
0x180027e9b  lea     rax, stru_1801F8A30
0x180027ea2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ea9  jmp     loc_180027DBD
0x180027eae  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180027eb5  mov     ebx, 0C00D36EBh
0x180027eba  jz      loc_180027F59
0x180027ec0  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ec7  cmp     [rdi+8], r13b
0x180027ecb  jnz     loc_18002802A
0x180027ed1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027ed8  jb      loc_180027D13
0x180027ede  mov     edx, 38h ; '8'
0x180027ee3  jmp     loc_180027DE0
0x180027ee8  call    cs:__imp_GetLastError
0x180027eee  test    eax, eax
0x180027ef0  jnz     loc_180027C20
0x180027ef6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027efd  test    rcx, rcx
0x180027f00  jz      loc_180027F8C
0x180027f06  lea     rdi, stru_1801F8A30
0x180027f0d  mov     rax, [rcx]
0x180027f10  mov     rax, [rax]
0x180027f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f18  test    rax, rax
0x180027f1b  cmovnz  rbx, rax
0x180027f1f  jmp     loc_180027C27
0x180027f24  call    cs:__imp_GetLastError
0x180027f2a  test    eax, eax
0x180027f2c  jnz     loc_180027D44
0x180027f32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f39  test    rcx, rcx
0x180027f3c  jz      loc_180027FE4
0x180027f42  mov     rax, [rcx]
0x180027f45  mov     rax, [rax]
0x180027f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f4d  test    rax, rax
0x180027f50  cmovnz  rsi, rax
0x180027f54  jmp     loc_180027D44
0x180027f59  mov     rax, cs:stru_1801FC290.__vftable
0x180027f60  mov     edx, 7F0h
0x180027f65  mov     rcx, r14
0x180027f68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f6f  mov     rax, [rax+8]
0x180027f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f78  test    eax, eax
0x180027f7a  jnz     loc_180027EC0
0x180027f80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180027f87  jmp     loc_180027EC0
0x180027f8c  mov     rax, cs:stru_1801FC290.__vftable
0x180027f93  lea     r8, stru_1801FC290
0x180027f9a  mov     edx, 7F0h
0x180027f9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180027fa6  mov     rcx, r8
0x180027fa9  mov     rax, [rax+8]
0x180027fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fb2  lea     rdi, stru_1801F8A30
0x180027fb9  test    eax, eax
0x180027fbb  jnz     short loc_180027FCC
0x180027fbd  mov     rcx, rdi
0x180027fc0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027fc7  jmp     loc_180027F0D
0x180027fcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027fd3  jmp     loc_180027F0D
0x180027fd8  lea     rdi, stru_1801F8A30
0x180027fdf  jmp     loc_180027C61
0x180027fe4  mov     rax, cs:stru_1801FC290.__vftable
0x180027feb  lea     rcx, stru_1801FC290
0x180027ff2  mov     edx, 7F0h
0x180027ff7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ffe  mov     rax, [rax+8]
0x180028002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028007  test    eax, eax
0x180028009  jnz     short loc_18002801E
0x18002800b  lea     rcx, stru_1801F8A30
0x180028012  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180028019  jmp     loc_180027F42
0x18002801e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180028025  jmp     loc_180027F42
0x18002802a  mov     rcx, rdi; this
0x18002802d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180028032  cmp     [rax+7CCh], ebx
0x180028038  jz      loc_180027ED1
0x18002803e  mov     r9d, ebx; int
0x180028041  lea     rdx, aCmfpropvariant_10; "CMFPropVariantConvert::CreateFromData"
0x180028048  mov     r8d, 339h; int
0x18002804e  mov     rcx, rax; this
0x180028051  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180028056  jmp     loc_180027ED1
0x18002805b  cmp     r13w, bp
0x18002805f  jz      loc_1800286B3
0x180028065  cmp     dx, bp
0x180028068  jz      loc_1800286B3
0x18002806e  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180028075  mov     esi, 80070057h
0x18002807a  mov     ebx, esi
0x18002807c  jnz     short loc_1800280A8
0x18002807e  mov     rax, cs:stru_1801FC290.__vftable
0x180028085  mov     edx, 7F0h
0x18002808a  mov     rcx, r14
0x18002808d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r14; CallStackTracing * CallStackTracing::s_wpInstance
0x180028094  mov     rax, [rax+8]
0x180028098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002809d  test    eax, eax
0x18002809f  jnz     short loc_1800280A8
0x1800280a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800280a8  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800280af  cmp     [rdi+8], r13b
0x1800280b3  jnz     short loc_1800280D0
0x1800280b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800280bc  jb      loc_180027D13
0x1800280c2  mov     edx, 39h ; '9'
0x1800280c7  mov     dword ptr [rsp+78h+lpWideCharStr], esi
0x1800280cb  jmp     loc_180027DE4
0x1800280d0  mov     rcx, rdi; this
0x1800280d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800280d8  cmp     [rax+7CCh], esi
0x1800280de  jz      short loc_1800280B5
0x1800280e0  mov     r9d, esi; int
0x1800280e3  lea     rdx, aCmfpropvariant_10; "CMFPropVariantConvert::CreateFromData"
0x1800280ea  mov     r8d, 342h; int
0x1800280f0  mov     rcx, rax; this
0x1800280f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800280f8  jmp     short loc_1800280B5
0x1800280fa  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180028101  mov     esi, 80070057h
0x180028106  mov     ebx, esi
0x180028108  jnz     short loc_18002813B
  ... truncated ...
```
