# CMFPropVariantConvert::CreateFromData(CMFPropVariant *,ushort,void const *,ulong)

- ea: `0x180028340`
- end: `0x180028ff3`
- name: `?CreateFromData@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@GPEBXK@Z`
- size: `3251`
- prototype: `__int64 __fastcall(struct CMFPropVariant *this, unsigned __int16, const void *, unsigned int)`
- caller_count: `5`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024720`
- `0x180026690`
- `0x180080f80`
- `0x1800a8760`
- `0x1800d2140`

## callees

- `0x18000d7b4`
- `0x180010190`
- `0x18001303c`
- `0x180025548`
- `0x180028340`
- `0x180071a44`
- `0x180073b14`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002892d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002892d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180028be4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180028be4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180028541`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800285fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002864d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002868e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800286c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800286fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002873e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002877f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800287c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180028801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002883b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002887c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180028541`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800285fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002864d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002868e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800286c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800286fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002873e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002877f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800287c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180028801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002883b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002887c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028581`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028ce7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028581`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028bb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028ce7`

## string_xrefs

- `0x18002837e`: `CMFPropVariantConvert::CreateFromData`
- `0x180028913`: `CMFPropVariantConvert::CreateFromData`
- `0x18002896d`: `CMFPropVariantConvert::CreateFromData`
- `0x18002899e`: `CMFPropVariantConvert::CreateFromData`
- `0x1800289cf`: `CMFPropVariantConvert::CreateFromData`
- `0x180028a57`: `CMFPropVariantConvert::CreateFromData`
- `0x180028a85`: `CMFPropVariantConvert::CreateFromData`

## pseudocode

```c
__int64 __fastcall CMFPropVariantConvert::CreateFromData(
        struct CMFPropVariant *this,
        __int64 a2,
        _WORD *a3,
        __int64 a4)
{
  unsigned __int16 v4; // bx
  _WORD *v5; // rdi
  SIZE_T cchWideChar; // rsi
  __int64 v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // ebx
  _WORD *v14; // rax
  _WORD *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  _QWORD *v18; // r12
  _WORD *v19; // rcx
  SIZE_T v20; // rbx
  __int64 v21; // rax
  signed int v22; // ebp
  __int16 v23; // r14
  struct CallStackContext *v24; // rax
  int v25; // ecx
  int v26; // ecx
  CallStackTracing *v28; // rax
  void *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  CallStackTracing *v34; // rax
  CallStackTracing *v35; // rax
  wchar_t *v36; // rax
  CallStackTracing *v37; // rax
  CallStackTracing *v38; // rax
  wchar_t *v39; // rax
  CallStackTracing *v40; // rax
  wchar_t *v41; // rax
  CallStackTracing *v42; // rax
  int v43; // ebx
  CallStackTracing *v44; // rax
  wchar_t *v45; // rax
  CallStackTracing *v46; // rax
  wchar_t *v47; // rax
  CallStackTracing *v48; // rax
  CallStackTracing *v49; // rax
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  struct CallStackContext *v52; // rax
  struct CallStackContext *v53; // rax
  signed int LastError; // eax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  struct CallStackContext *v61; // rax
  struct CallStackContext *v62; // rax
  struct CallStackContext *v63; // rax
  struct CallStackContext *v64; // rax
  struct CallStackContext *v65; // rax
  struct CallStackContext *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 v68; // rdx
  WCHAR *lpWideCharStr; // rax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  _OWORD *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v79; // rdx

  v4 = a2;
  v5 = a3;
  cchWideChar = (unsigned int)a4;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v8 = (__int64)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v8 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v8 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v8 *= 2;
      *((_QWORD *)ThreadRelativeContext + v8) = "CMFPropVariantConvert::CreateFromData";
      *((_DWORD *)ThreadRelativeContext + 2 * v8 + 2) = 799;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  if ( *(_WORD *)this )
  {
    v22 = -1072875798;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v8, a2, a3, a4);
      CallStackTracing::s_wpInstance = v28;
      if ( !v28 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v67 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v67 + 499) != -1072875798 )
        CallStackContext::TraceFailure(v67, "CMFPropVariantConvert::CreateFromData", 812, -1072875798);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v68 = 55;
LABEL_183:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v68, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v22);
    goto LABEL_27;
  }
  *(_WORD *)this = v4;
  v10 = v4;
  if ( (v4 & 0x1000) != 0 )
  {
    v22 = -1072875797;
    if ( !CallStackTracing::s_wpInstance )
    {
      LOWORD(v10) = v4 & 0x1000;
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v10, a2, a3, a4);
      CallStackTracing::s_wpInstance = v34;
      if ( !v34 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v51 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v51 + 499) != -1072875797 )
        CallStackContext::TraceFailure(v51, "CMFPropVariantConvert::CreateFromData", 825, -1072875797);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v68 = 56;
    goto LABEL_183;
  }
  v11 = 65;
  if ( (_DWORD)cchWideChar )
  {
    v12 = 0;
    if ( v4 == 11 )
    {
      v11 = (unsigned int)cchWideChar;
      while ( (_DWORD)v11 )
      {
        v11 = (unsigned int)(v11 - 1);
        if ( *((_BYTE *)v5 + v11) )
        {
          v12 = 0xFFFFFFFFLL;
          break;
        }
      }
LABEL_13:
      v13 = v4 & 0xFFF;
      if ( v13 == 31 )
      {
        if ( (cchWideChar & 1) != 0 || (unsigned int)cchWideChar < 2 )
        {
          v43 = -2147024809;
          v22 = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v12, a3, a4);
            CallStackTracing::s_wpInstance = v50;
            if ( !v50
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v66 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v66 + 499) != -2147024809 )
              CallStackContext::TraceFailure(v66, "CMFPropVariantConvert::CreateFromData", 901, -2147024809);
          }
          if ( !g_wppLevels )
            goto LABEL_178;
          v79 = 61;
          goto LABEL_177;
        }
        v14 = CoTaskMemAlloc(cchWideChar);
        *((_QWORD *)this + 1) = v14;
        v18 = (_QWORD *)((char *)this + 8);
        v19 = v14;
        if ( !v14 )
        {
          v47 = (wchar_t *)CallStackTracing::s_wpInstance;
          v22 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
            CallStackTracing::s_wpInstance = v48;
            if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
            {
              v47 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v47 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v47 + 8) )
          {
            v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
            if ( *((_DWORD *)v64 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v64, "CMFPropVariantConvert::CreateFromData", 905, -2147024882);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              62,
              &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
              0,
              -2147024882);
          goto LABEL_178;
        }
        v20 = cchWideChar >> 1;
        *v14 = 0;
        if ( cchWideChar >> 1 )
        {
          v15 = (_WORD *)*v18;
          v21 = 2147483646;
          do
          {
            if ( !v21 )
              break;
            if ( !*v5 )
              break;
            *v15++ = *v5++;
            --v21;
            --v20;
          }
          while ( v20 );
          v19 = v15 - 1;
          v22 = -2147024774;
          if ( v20 )
          {
            v19 = v15;
            v22 = 0;
          }
          *v19 = 0;
          if ( v22 >= 0 )
            goto LABEL_25;
          v43 = v22;
        }
        else
        {
          v43 = -2147024809;
          v22 = -2147024809;
        }
        if ( !CallStackTracing::s_wpInstance )
        {
          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v15, v16, v17);
          CallStackTracing::s_wpInstance = v49;
          if ( !v49 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v65 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v65 + 499) != v43 )
            CallStackContext::TraceFailure(v65, "CMFPropVariantConvert::CreateFromData", 909, v43);
        }
        if ( g_wppLevels )
        {
          v79 = 63;
LABEL_177:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v79, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v43);
        }
      }
      else
      {
        v22 = 0;
        if ( v13 == 65 )
        {
          v29 = CoTaskMemAlloc(cchWideChar);
          *((_QWORD *)this + 2) = v29;
          if ( v29 )
          {
            v18 = (_QWORD *)((char *)this + 8);
            *((_DWORD *)this + 2) = cchWideChar;
            memcpy_0(v29, v5, cchWideChar);
LABEL_25:
            v23 = *(_WORD *)this & 0xFFF;
            if ( (v23 == 9 || v23 == 13) && *v18 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
            goto LABEL_27;
          }
          v45 = (wchar_t *)CallStackTracing::s_wpInstance;
          v22 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v31, v30, v32, v33);
            CallStackTracing::s_wpInstance = v46;
            if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
            {
              v45 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v45 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v45 + 8) )
          {
            v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
            if ( *((_DWORD *)v63 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v63, "CMFPropVariantConvert::CreateFromData", 914, -2147024882);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
              0,
              -2147024882);
        }
        else
        {
          switch ( v13 )
          {
            case 2:
            case 3:
            case 9:
            case 13:
            case 16:
            case 17:
            case 18:
            case 19:
            case 20:
            case 21:
            case 22:
            case 23:
            case 64:
              if ( (unsigned int)cchWideChar > 8 )
              {
                v22 = -2147024809;
                break;
              }
              v18 = (_QWORD *)((char *)this + 8);
              memcpy_0((char *)this + 8, v5, cchWideChar);
              goto LABEL_25;
            case 11:
              v18 = (_QWORD *)((char *)this + 8);
              *((_WORD *)this + 4) = v12;
              goto LABEL_25;
            case 14:
              if ( (_DWORD)cchWideChar != 16 )
              {
                v22 = -2147024809;
                break;
              }
              v18 = (_QWORD *)((char *)this + 8);
              *(_OWORD *)this = *(_OWORD *)v5;
              goto LABEL_25;
            case 30:
              lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2 * cchWideChar);
              *((_QWORD *)this + 1) = lpWideCharStr;
              v18 = (_QWORD *)((char *)this + 8);
              if ( lpWideCharStr )
              {
                *(_WORD *)this = 31;
                if ( MultiByteToWideChar(0, 0, (LPCCH)v5, cchWideChar, lpWideCharStr, cchWideChar) )
                {
                  *(_WORD *)(*v18 + 2LL * (unsigned int)(cchWideChar - 1)) = 0;
                  goto LABEL_25;
                }
                LastError = GetLastError();
                v22 = LastError;
                if ( LastError > 0 )
                  v22 = (unsigned __int16)LastError | 0x80070000;
                v39 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( v22 >= 0 )
                {
                  v22 = -2147418113;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v56, v55, v57, v58);
                    CallStackTracing::s_wpInstance = v40;
                    if ( v40
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                    {
                      v39 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v39 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v39 + 8) )
                  {
                    v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
                    if ( *((_DWORD *)v60 + 499) != -2147418113 )
                      CallStackContext::TraceFailure(v60, "CMFPropVariantConvert::CreateFromData", 890, -2147418113);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      60,
                      &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                      0,
                      -2147418113);
                }
                else
                {
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v56, v55, v57, v58);
                    CallStackTracing::s_wpInstance = v38;
                    if ( v38
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                    {
                      v39 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v39 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v39 + 8) )
                  {
                    v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
                    if ( *((_DWORD *)v59 + 499) != v22 )
                      CallStackContext::TraceFailure(v59, "CMFPropVariantConvert::CreateFromData", 889, v22);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      59,
                      &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                      0,
                      v22);
                }
              }
              else
              {
                v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                v22 = -2147024882;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v71, v70, v72, v73);
                  CallStackTracing::s_wpInstance = v37;
                  if ( v37
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                  {
                    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v36 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v36 + 8) )
                {
                  v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                  if ( *((_DWORD *)v53 + 499) != -2147024882 )
                    CallStackContext::TraceFailure(v53, "CMFPropVariantConvert::CreateFromData", 876, -2147024882);
                }
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    58,
                    &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                    0,
                    -2147024882);
              }
              break;
            case 72:
              if ( (_DWORD)cchWideChar != 16 )
              {
                v22 = -2147024809;
                break;
              }
              v74 = CoTaskMemAlloc(0x10u);
              *((_QWORD *)this + 1) = v74;
              v18 = (_QWORD *)((char *)this + 8);
              if ( v74 )
              {
                *v74 = *(_OWORD *)v5;
                goto LABEL_25;
              }
              v41 = (wchar_t *)CallStackTracing::s_wpInstance;
              v22 = -2147024882;
              if ( !CallStackTracing::s_wpInstance )
              {
                v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v76, v75, v77, v78);
                CallStackTracing::s_wpInstance = v42;
                if ( v42
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                {
                  v41 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v41 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v41 + 8) )
              {
                v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                if ( *((_DWORD *)v61 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(v61, "CMFPropVariantConvert::CreateFromData", 927, -2147024882);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  65,
                  &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                  0,
                  -2147024882);
              break;
            default:
              v43 = -2147024809;
              v22 = -2147024809;
              if ( !CallStackTracing::s_wpInstance )
              {
                v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v12, a3, a4);
                CallStackTracing::s_wpInstance = v44;
                if ( !v44
                  || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                {
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
              {
                v62 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                if ( *((_DWORD *)v62 + 499) != -2147024809 )
                  CallStackContext::TraceFailure(v62, "CMFPropVariantConvert::CreateFromData", 970, -2147024809);
              }
              if ( !g_wppLevels )
                break;
              v79 = 66;
              goto LABEL_177;
          }
        }
      }
LABEL_178:
      CMFPropVariant::Clear(this);
      goto LABEL_27;
    }
LABEL_11:
    if ( v4 == 8 )
    {
      *(_WORD *)this = 31;
      v4 = 31;
    }
    goto LABEL_13;
  }
  if ( !v4 )
  {
    v12 = 0;
    goto LABEL_11;
  }
  if ( v4 == 65 )
  {
    v12 = 0;
    goto LABEL_11;
  }
  v22 = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(65, a2, a3, a4);
    CallStackTracing::s_wpInstance = v35;
    if ( !v35 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v52 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v52 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v52, "CMFPropVariantConvert::CreateFromData", 834, -2147024809);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, -2147024809);
LABEL_27:
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v24 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v25 = *((_DWORD *)v24 + 497);
    if ( v25 )
    {
      v26 = v25 - 1;
      *((_DWORD *)v24 + 497) = v26;
      if ( !v26 )
        CallStackContext::ClearState(v24);
    }
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180028340  sub     rsp, 58h
0x180028344  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002834c  mov     [rsp+58h+arg_0], rbx
0x180028351  movzx   ebx, dx
0x180028354  mov     [rsp+58h+arg_10], rsi
0x180028359  mov     [rsp+58h+var_8], rdi
0x18002835e  mov     rdi, r8
0x180028361  mov     [rsp+58h+var_10], r12
0x180028366  mov     [rsp+58h+var_28], r15
0x18002836b  mov     r15, rcx
0x18002836e  mov     esi, r9d
0x180028371  jz      loc_18002856D
0x180028377  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002837e  lea     r12, aCmfpropvariant_14; "CMFPropVariantConvert::CreateFromData"
0x180028385  cmp     byte ptr [rcx+8], 0
0x180028389  jz      short loc_1800283B3
0x18002838b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180028390  mov     ecx, [rax+7C4h]
0x180028396  cmp     ecx, [rax+7C8h]
0x18002839c  jnb     short loc_1800283AD
0x18002839e  add     rcx, rcx
0x1800283a1  mov     [rax+rcx*8], r12
0x1800283a5  mov     dword ptr [rax+rcx*8+8], 31Fh
0x1800283ad  inc     dword ptr [rax+7C4h]
0x1800283b3  mov     [rsp+58h+arg_8], rbp
0x1800283b8  xor     eax, eax
0x1800283ba  mov     [rsp+58h+var_18], r13
0x1800283bf  mov     [rsp+58h+var_20], r14
0x1800283c4  cmp     ax, [r15]
0x1800283c8  jnz     loc_18002852F
0x1800283ce  mov     eax, 1000h
0x1800283d3  mov     [r15], bx
0x1800283d7  movzx   ecx, bx
0x1800283da  and     cx, ax
0x1800283dd  xor     eax, eax
0x1800283df  cmp     ax, cx
0x1800283e2  jnz     loc_1800285E9
0x1800283e8  mov     ecx, 41h ; 'A'
0x1800283ed  mov     r13d, 1Fh
0x1800283f3  test    esi, esi
0x1800283f5  jz      loc_180028627
0x1800283fb  movzx   edx, ax
0x1800283fe  mov     eax, 0Bh
0x180028403  cmp     ax, bx
0x180028406  jz      loc_180028B88
0x18002840c  mov     eax, 8
0x180028411  cmp     ax, bx
0x180028414  jz      loc_180028BA3
0x18002841a  mov     r14d, 0FFFh
0x180028420  and     ebx, r14d
0x180028423  cmp     ebx, r13d
0x180028426  jnz     loc_180028577
0x18002842c  test    sil, 1
0x180028430  jnz     loc_180028867
0x180028436  cmp     esi, 2
0x180028439  jb      loc_180028867
0x18002843f  mov     rcx, rsi; cb
0x180028442  mov     rbx, rsi
0x180028445  call    cs:__imp_CoTaskMemAlloc
0x18002844b  mov     [r15+8], rax
0x18002844f  lea     r12, [r15+8]
0x180028453  mov     rcx, rax
0x180028456  test    rax, rax
0x180028459  jz      loc_1800287EC
0x18002845f  xor     eax, eax
0x180028461  shr     rbx, 1
0x180028464  mov     [rcx], ax
0x180028467  jz      loc_180028E65
0x18002846d  mov     rdx, [r12]
0x180028471  mov     eax, 7FFFFFFEh
0x180028476  test    rax, rax
0x180028479  jz      short loc_180028497
0x18002847b  movzx   ecx, word ptr [rdi]
0x18002847e  test    cx, cx
0x180028481  jz      short loc_180028497
0x180028483  mov     [rdx], cx
0x180028486  add     rdi, 2
0x18002848a  add     rdx, 2
0x18002848e  dec     rax
0x180028491  sub     rbx, 1
0x180028495  jnz     short loc_180028476
0x180028497  xor     eax, eax
0x180028499  lea     rcx, [rdx-2]
0x18002849d  test    rbx, rbx
0x1800284a0  mov     ebp, 8007007Ah
0x1800284a5  cmovnz  rcx, rdx
0x1800284a9  cmovnz  ebp, eax
0x1800284ac  mov     [rcx], ax
0x1800284af  test    ebp, ebp
0x1800284b1  js      loc_180028E5E
0x1800284b7  and     r14w, [r15]
0x1800284bb  cmp     r14w, 9
0x1800284c0  jz      loc_180028EB4
0x1800284c6  cmp     r14w, 0Dh
0x1800284cb  jz      loc_180028EB4
0x1800284d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800284d8  mov     r15, [rsp+58h+var_28]
0x1800284dd  mov     r14, [rsp+58h+var_20]
0x1800284e2  mov     r13, [rsp+58h+var_18]
0x1800284e7  cmp     byte ptr [rcx+8], 0
0x1800284eb  mov     r12, [rsp+58h+var_10]
0x1800284f0  mov     rdi, [rsp+58h+var_8]
0x1800284f5  mov     rsi, [rsp+58h+arg_10]
0x1800284fa  mov     rbx, [rsp+58h+arg_0]
0x1800284ff  jz      short loc_180028523
0x180028501  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180028506  mov     ecx, [rax+7C4h]
0x18002850c  test    ecx, ecx
0x18002850e  jz      short loc_180028523
0x180028510  sub     ecx, 1
0x180028513  mov     [rax+7C4h], ecx
0x180028519  jnz     short loc_180028523
0x18002851b  mov     rcx, rax; this
0x18002851e  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180028523  mov     eax, ebp
0x180028525  mov     rbp, [rsp+58h+arg_8]
0x18002852a  add     rsp, 58h
0x18002852e  retn
0x18002852f  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028536  mov     ebp, 0C00D36EAh
0x18002853b  jnz     loc_180028F4E
0x180028541  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028547  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002854e  mov     rcx, rax
0x180028551  test    rax, rax
0x180028554  jnz     loc_180028F35
0x18002855a  lea     rax, qword_1801B07E0
0x180028561  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028568  jmp     loc_180028F4E
0x18002856d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180028572  jmp     loc_180028377
0x180028577  xor     ebp, ebp
0x180028579  cmp     ebx, 41h ; 'A'
0x18002857c  jnz     short loc_1800285AF
0x18002857e  mov     rcx, rsi; cb
0x180028581  call    cs:__imp_CoTaskMemAlloc
0x180028587  mov     [r15+10h], rax
0x18002858b  test    rax, rax
0x18002858e  jz      loc_1800287AB
0x180028594  lea     r12, [r15+8]
0x180028598  mov     r8, rsi; Size
0x18002859b  mov     rdx, rdi; Src
0x18002859e  mov     [r12], esi
0x1800285a2  mov     rcx, rax; void *
0x1800285a5  call    memcpy_0
0x1800285aa  jmp     loc_1800284B7
0x1800285af  add     ebx, 0FFFFFFFEh; switch 71 cases
0x1800285b2  cmp     ebx, 46h
0x1800285b5  ja      def_1800285D9; jumptable 00000001800285D9 default case, cases 4-8,10,12,15,24-29,31-63,65-71
0x1800285bb  lea     r8, __ImageBase
0x1800285c2  movsxd  rax, ebx
0x1800285c5  movzx   eax, ds:(byte_180028FAC - 180000000h)[r8+rax]
0x1800285ce  mov     ecx, ds:(jpt_1800285D9 - 180000000h)[r8+rax*4]
0x1800285d6  add     rcx, r8
0x1800285d9  jmp     rcx; switch jump
0x1800285db  lea     r12, [r15+8]; jumptable 00000001800285D9 case 11
0x1800285df  mov     [r12], dx
0x1800285e4  jmp     loc_1800284B7
0x1800285e9  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800285f0  mov     ebp, 0C00D36EBh
0x1800285f5  jnz     loc_180028B0C
0x1800285fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028601  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028608  mov     rcx, rax
0x18002860b  test    rax, rax
0x18002860e  jnz     loc_180028AF3
0x180028614  lea     rax, qword_1801B07E0
0x18002861b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028622  jmp     loc_180028B0C
0x180028627  cmp     ax, bx
0x18002862a  jz      loc_180028B34
0x180028630  cmp     cx, bx
0x180028633  jz      loc_180028B3B
0x180028639  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028640  mov     ebx, 80070057h
0x180028645  mov     ebp, ebx
0x180028647  jnz     loc_180028B5C
0x18002864d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028653  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002865a  mov     rcx, rax
0x18002865d  test    rax, rax
0x180028660  jnz     loc_180028B43
0x180028666  lea     rax, qword_1801B07E0
0x18002866d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028674  jmp     loc_180028B5C
0x180028679  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180028680  mov     ebp, 8007000Eh
0x180028685  test    rax, rax
0x180028688  jnz     loc_180028C24
0x18002868e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028694  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002869b  mov     rcx, rax
0x18002869e  test    rax, rax
0x1800286a1  jnz     loc_180028C04
0x1800286a7  lea     rax, qword_1801B07E0
0x1800286ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800286b5  jmp     loc_180028C24
0x1800286ba  test    rax, rax
0x1800286bd  jnz     loc_180028C69
0x1800286c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800286c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800286d0  mov     rcx, rax
0x1800286d3  test    rax, rax
0x1800286d6  jnz     loc_180028C49
0x1800286dc  lea     rax, qword_1801B07E0
0x1800286e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800286ea  jmp     loc_180028C69
0x1800286ef  mov     ebp, 8000FFFFh
0x1800286f4  test    rax, rax
0x1800286f7  jnz     loc_180028CAE
0x1800286fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028703  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002870a  mov     rcx, rax
0x18002870d  test    rax, rax
0x180028710  jnz     loc_180028C8E
0x180028716  lea     rax, qword_1801B07E0
0x18002871d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028724  jmp     loc_180028CAE
0x180028729  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180028730  mov     ebp, 8007000Eh
0x180028735  test    rax, rax
0x180028738  jnz     loc_180028D29
0x18002873e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028744  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002874b  mov     rcx, rax
0x18002874e  test    rax, rax
0x180028751  jnz     loc_180028D09
0x180028757  lea     rax, qword_1801B07E0
0x18002875e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028765  jmp     loc_180028D29
0x18002876a  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; jumptable 00000001800285D9 default case, cases 4-8,10,12,15,24-29,31-63,65-71
0x180028772  mov     ebx, 80070057h
0x180028777  mov     ebp, ebx
0x180028779  jnz     loc_180028DAC
0x18002877f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028785  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002878c  mov     rcx, rax
0x18002878f  test    rax, rax
0x180028792  jnz     loc_180028D93
0x180028798  lea     rax, qword_1801B07E0
0x18002879f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800287a6  jmp     loc_180028DAC
0x1800287ab  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800287b2  mov     ebp, 8007000Eh
0x1800287b7  test    rax, rax
0x1800287ba  jnz     loc_180028DF4
0x1800287c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800287c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800287cd  mov     rcx, rax
0x1800287d0  test    rax, rax
0x1800287d3  jnz     loc_180028DD4
0x1800287d9  lea     rax, qword_1801B07E0
0x1800287e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800287e7  jmp     loc_180028DF4
0x1800287ec  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800287f3  mov     ebp, 8007000Eh
0x1800287f8  test    rax, rax
0x1800287fb  jnz     loc_180028E39
0x180028801  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028807  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002880e  mov     rcx, rax
0x180028811  test    rax, rax
0x180028814  jnz     loc_180028E19
0x18002881a  lea     rax, qword_1801B07E0
0x180028821  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028828  jmp     loc_180028E39
0x18002882d  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180028835  jnz     loc_180028E8A
0x18002883b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028841  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028848  mov     rcx, rax
0x18002884b  test    rax, rax
0x18002884e  jnz     loc_180028E71
0x180028854  lea     rax, qword_1801B07E0
0x18002885b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028862  jmp     loc_180028E8A
0x180028867  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002886f  mov     ebx, 80070057h
0x180028874  mov     ebp, ebx
0x180028876  jnz     loc_180028EEB
0x18002887c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180028882  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180028889  mov     rcx, rax
0x18002888c  test    rax, rax
0x18002888f  jnz     loc_180028ED2
0x180028895  lea     rax, qword_1801B07E0
0x18002889c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800288a3  jmp     loc_180028EEB
0x1800288a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800288ad  cmp     [rax+7CCh], ebp
0x1800288b3  jz      loc_180028B1D
0x1800288b9  mov     r9d, ebp; int
0x1800288bc  mov     r8d, 339h; int
0x1800288c2  mov     rdx, r12; char *
0x1800288c5  mov     rcx, rax; this
0x1800288c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800288cd  jmp     loc_180028B1D
0x1800288d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800288d7  cmp     [rax+7CCh], ebx
0x1800288dd  jz      loc_180028B6D
  ... truncated ...
```
