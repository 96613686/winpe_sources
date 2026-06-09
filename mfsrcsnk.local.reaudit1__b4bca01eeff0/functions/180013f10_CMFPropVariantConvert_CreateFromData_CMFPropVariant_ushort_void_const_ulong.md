# CMFPropVariantConvert::CreateFromData(CMFPropVariant *,ushort,void const *,ulong)

- ea: `0x180013f10`
- end: `0x180014be7`
- name: `?CreateFromData@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@GPEBXK@Z`
- size: `3287`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar, unsigned __int16, const void *, unsigned int)`
- caller_count: `5`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010140`
- `0x180012170`
- `0x180085990`
- `0x1800ad900`
- `0x1800d8150`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x180013f10`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180077708`
- `0x180079680`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001450c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001450c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800147df`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800147df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800140d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001419e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800141f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014239`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014274`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800142b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800142fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001433d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014384`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800143cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001440d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001444f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800140d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001419e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800141f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014239`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014274`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800142b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800142fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001433d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014384`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800143cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001440d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001444f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001411e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800147ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800148de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001411e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800147ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800148de`

## string_xrefs

- `0x180013f40`: `CMFPropVariantConvert::CreateFromData`
- `0x1800144f2`: `CMFPropVariantConvert::CreateFromData`
- `0x180014552`: `CMFPropVariantConvert::CreateFromData`
- `0x180014583`: `CMFPropVariantConvert::CreateFromData`
- `0x1800145b4`: `CMFPropVariantConvert::CreateFromData`
- `0x18001463f`: `CMFPropVariantConvert::CreateFromData`
- `0x180014670`: `CMFPropVariantConvert::CreateFromData`

## pseudocode

```c
__int64 __fastcall CMFPropVariantConvert::CreateFromData(__int64 pvar, unsigned __int16 a2, char *a3, unsigned int a4)
{
  SIZE_T cchWideChar; // rsi
  wchar_t *v6; // rdx
  PROPVARIANT *v8; // r15
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int16 v12; // r8
  int v13; // ebx
  _WORD *v14; // rax
  LARGE_INTEGER *p_hVal; // r12
  _WORD *v16; // rcx
  SIZE_T v17; // rbx
  _WORD *QuadPart; // rdx
  __int64 v19; // rax
  signed int v20; // ebp
  __int16 v21; // r14
  CallStackTracing *v23; // rax
  BYTE *v24; // rax
  __int64 v25; // rcx
  CallStackTracing *v26; // rax
  CallStackTracing *v27; // rax
  wchar_t *v28; // rdx
  CallStackTracing *v29; // rax
  CallStackTracing *v30; // rax
  wchar_t *v31; // rdx
  CallStackTracing *v32; // rax
  wchar_t *v33; // rdx
  CallStackTracing *v34; // rax
  int v35; // ebx
  CallStackTracing *v36; // rax
  wchar_t *v37; // rdx
  CallStackTracing *v38; // rax
  wchar_t *v39; // rdx
  CallStackTracing *v40; // rax
  wchar_t *v41; // rdx
  CallStackTracing *v42; // rax
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  signed int LastError; // eax
  __int64 v48; // rcx
  struct CallStackContext *v49; // rax
  struct CallStackContext *v50; // rax
  struct CallStackContext *v51; // rax
  struct CallStackContext *v52; // rax
  struct CallStackContext *v53; // rax
  struct CallStackContext *v54; // rax
  struct CallStackContext *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  WCHAR *lpWideCharStr; // rax
  __int64 v60; // rcx
  _OWORD *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rdx
  char v64; // [rsp+60h] [rbp+8h] BYREF

  cchWideChar = a4;
  v6 = (wchar_t *)CallStackTracing::s_wpInstance;
  v8 = (PROPVARIANT *)pvar;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v6 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
    pvar = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)pvar < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      pvar *= 2;
      *((_QWORD *)ThreadRelativeContext + pvar) = "CMFPropVariantConvert::CreateFromData";
      *((_DWORD *)ThreadRelativeContext + 2 * pvar + 2) = 799;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( v8->vt )
  {
    v20 = -1072875798;
    if ( !v6 )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(pvar, 0);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v57 + 499) != -1072875798 )
        CallStackContext::TraceFailure(v57, "CMFPropVariantConvert::CreateFromData", 812, -1072875798);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v58 = 55;
LABEL_183:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v58, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v20);
    goto LABEL_27;
  }
  v8->vt = a2;
  v10 = a2;
  if ( (a2 & 0x1000) != 0 )
  {
    v20 = -1072875797;
    if ( !v6 )
    {
      LOWORD(v10) = a2 & 0x1000;
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v10, 0);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v44 + 499) != -1072875797 )
        CallStackContext::TraceFailure(v44, "CMFPropVariantConvert::CreateFromData", 825, -1072875797);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v58 = 56;
    goto LABEL_183;
  }
  v11 = 65;
  if ( (_DWORD)cchWideChar )
  {
    v12 = 0;
    if ( a2 == 11 )
    {
      v11 = (unsigned int)cchWideChar;
      while ( (_DWORD)v11 )
      {
        v11 = (unsigned int)(v11 - 1);
        if ( a3[v11] )
        {
          v12 = -1;
          break;
        }
      }
LABEL_13:
      v13 = a2 & 0xFFF;
      if ( v13 == 31 )
      {
        if ( (cchWideChar & 1) != 0 || (unsigned int)cchWideChar < 2 )
        {
          v35 = -2147024809;
          v20 = -2147024809;
          if ( !v6 )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, 0);
            CallStackTracing::s_wpInstance = v43;
            if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
            {
              v6 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v6 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v6 + 8) )
          {
            v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
            if ( *((_DWORD *)v56 + 499) != -2147024809 )
              CallStackContext::TraceFailure(v56, "CMFPropVariantConvert::CreateFromData", 901, -2147024809);
          }
          if ( !g_wppLevels )
            goto LABEL_177;
          v63 = 61;
          goto LABEL_176;
        }
        v14 = CoTaskMemAlloc(cchWideChar);
        v8->hVal.QuadPart = (LONGLONG)v14;
        p_hVal = &v8->hVal;
        v16 = v14;
        if ( !v14 )
        {
          v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          v20 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0);
            CallStackTracing::s_wpInstance = v40;
            if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              v39 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v39 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v39 + 8) )
          {
            v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
            if ( *((_DWORD *)v54 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v54, "CMFPropVariantConvert::CreateFromData", 905, -2147024882);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              62,
              WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
              0,
              -2147024882);
          goto LABEL_177;
        }
        v17 = cchWideChar >> 1;
        *v14 = 0;
        if ( cchWideChar >> 1 )
        {
          QuadPart = (_WORD *)p_hVal->QuadPart;
          v19 = 2147483646;
          do
          {
            if ( !v19 )
              break;
            if ( !*(_WORD *)a3 )
              break;
            *QuadPart = *(_WORD *)a3;
            a3 += 2;
            ++QuadPart;
            --v19;
            --v17;
          }
          while ( v17 );
          v16 = QuadPart - 1;
          v20 = -2147024774;
          if ( v17 )
          {
            v16 = QuadPart;
            v20 = 0;
          }
          *v16 = 0;
          if ( v20 >= 0 )
            goto LABEL_25;
          v35 = v20;
        }
        else
        {
          v35 = -2147024809;
          v20 = -2147024809;
        }
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, 0);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v55 + 499) != v35 )
            CallStackContext::TraceFailure(v55, "CMFPropVariantConvert::CreateFromData", 909, v35);
        }
        if ( g_wppLevels )
        {
          v63 = 63;
LABEL_176:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v63, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v35);
        }
      }
      else
      {
        v20 = 0;
        if ( v13 == 65 )
        {
          v24 = (BYTE *)CoTaskMemAlloc(cchWideChar);
          v8->bstrblobVal.pData = v24;
          if ( v24 )
          {
            p_hVal = &v8->hVal;
            v8->lVal = cchWideChar;
            memcpy_0(v24, a3, cchWideChar);
LABEL_25:
            v21 = v8->vt & 0xFFF;
            if ( v21 == 9 || v21 == 13 )
            {
              if ( p_hVal->QuadPart )
                (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)p_hVal->QuadPart + 8LL))(p_hVal->QuadPart);
            }
            goto LABEL_27;
          }
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
          v20 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, 0);
            CallStackTracing::s_wpInstance = v38;
            if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
            {
              v37 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v37 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v37 + 8) )
          {
            v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
            if ( *((_DWORD *)v53 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v53, "CMFPropVariantConvert::CreateFromData", 914, -2147024882);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
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
                goto LABEL_136;
              p_hVal = &v8->hVal;
              memcpy_0(&v8->decVal.8, a3, cchWideChar);
              goto LABEL_25;
            case 11:
              p_hVal = &v8->hVal;
              v8->iVal = v12;
              goto LABEL_25;
            case 14:
              if ( (_DWORD)cchWideChar != 16 )
                goto LABEL_136;
              p_hVal = &v8->hVal;
              *(_OWORD *)&v8->vt = *(_OWORD *)a3;
              goto LABEL_25;
            case 30:
              lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2 * cchWideChar);
              v8->hVal.QuadPart = (LONGLONG)lpWideCharStr;
              p_hVal = &v8->hVal;
              if ( lpWideCharStr )
              {
                v8->vt = 31;
                if ( MultiByteToWideChar(0, 0, a3, cchWideChar, lpWideCharStr, cchWideChar) )
                {
                  *(_WORD *)(p_hVal->QuadPart + 2LL * (unsigned int)(cchWideChar - 1)) = 0;
                  goto LABEL_25;
                }
                LastError = GetLastError();
                v20 = LastError;
                if ( LastError > 0 )
                  v20 = (unsigned __int16)LastError | 0x80070000;
                v31 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( v20 >= 0 )
                {
                  v20 = -2147418113;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v48, 0);
                    CallStackTracing::s_wpInstance = v32;
                    if ( v32
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                    {
                      v31 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v31 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v31 + 8) )
                  {
                    v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                    if ( *((_DWORD *)v50 + 499) != -2147418113 )
                      CallStackContext::TraceFailure(v50, "CMFPropVariantConvert::CreateFromData", 890, -2147418113);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      60,
                      WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                      0,
                      -2147418113);
                }
                else
                {
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v48, 0);
                    CallStackTracing::s_wpInstance = v30;
                    if ( v30
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
                    {
                      v31 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v31 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v31 + 8) )
                  {
                    v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                    if ( *((_DWORD *)v49 + 499) != v20 )
                      CallStackContext::TraceFailure(v49, "CMFPropVariantConvert::CreateFromData", 889, v20);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      59,
                      WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                      0,
                      v20);
                }
              }
              else
              {
                v28 = (wchar_t *)CallStackTracing::s_wpInstance;
                v20 = -2147024882;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v60, 0);
                  CallStackTracing::s_wpInstance = v29;
                  if ( v29
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
                  {
                    v28 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v28 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v28 + 8) )
                {
                  v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                  if ( *((_DWORD *)v46 + 499) != -2147024882 )
                    CallStackContext::TraceFailure(v46, "CMFPropVariantConvert::CreateFromData", 876, -2147024882);
                }
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    58,
                    WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                    0,
                    -2147024882);
              }
              break;
            case 72:
              if ( (_DWORD)cchWideChar == 16 )
              {
                v61 = CoTaskMemAlloc(0x10u);
                v8->hVal.QuadPart = (LONGLONG)v61;
                p_hVal = &v8->hVal;
                if ( v61 )
                {
                  *v61 = *(_OWORD *)a3;
                  goto LABEL_25;
                }
                v33 = (wchar_t *)CallStackTracing::s_wpInstance;
                v20 = -2147024882;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v62, 0);
                  CallStackTracing::s_wpInstance = v34;
                  if ( v34
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                  {
                    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v33 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v33 + 8) )
                {
                  v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                  if ( *((_DWORD *)v51 + 499) != -2147024882 )
                    CallStackContext::TraceFailure(v51, "CMFPropVariantConvert::CreateFromData", 927, -2147024882);
                }
                if ( g_wppLevels )
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    65,
                    WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                    0,
                    -2147024882);
              }
              else
              {
LABEL_136:
                v20 = -2147024809;
              }
              break;
            default:
              v35 = -2147024809;
              v20 = -2147024809;
              if ( !v6 )
              {
                v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, 0);
                CallStackTracing::s_wpInstance = v36;
                if ( v36
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
                {
                  v6 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v6 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v6 + 8) )
              {
                v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
                if ( *((_DWORD *)v52 + 499) != -2147024809 )
                  CallStackContext::TraceFailure(v52, "CMFPropVariantConvert::CreateFromData", 970, -2147024809);
              }
              if ( !g_wppLevels )
                break;
              v63 = 66;
              goto LABEL_176;
          }
        }
      }
LABEL_177:
      CMFPropVariant::Clear(v8);
      goto LABEL_27;
    }
LABEL_11:
    if ( a2 == 8 )
    {
      v8->vt = 31;
      a2 = 31;
    }
    goto LABEL_13;
  }
  if ( !a2 )
  {
    v12 = 0;
    goto LABEL_11;
  }
  if ( a2 == 65 )
  {
    v12 = 0;
    goto LABEL_11;
  }
  v20 = -2147024809;
  if ( !v6 )
  {
    v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(65, 0);
    CallStackTracing::s_wpInstance = v27;
    if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
    {
      v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v6 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v6 + 8) )
  {
    v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
    if ( *((_DWORD *)v45 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v45, "CMFPropVariantConvert::CreateFromData", 834, -2147024809);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, -2147024809);
LABEL_27:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v64);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180013f10  mov     [rsp+arg_18], rbx
0x180013f15  push    rbp
0x180013f16  push    rsi
0x180013f17  push    rdi
0x180013f18  push    r12
0x180013f1a  push    r15
0x180013f1c  sub     rsp, 30h
0x180013f20  movzx   ebx, dx
0x180013f23  mov     esi, r9d
0x180013f26  mov     rdx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013f2d  mov     rdi, r8
0x180013f30  mov     r15, rcx
0x180013f33  test    rdx, rdx
0x180013f36  jz      loc_180014103
0x180013f3c  cmp     byte ptr [rdx+8], 0
0x180013f40  lea     r12, aCmfpropvariant_14; "CMFPropVariantConvert::CreateFromData"
0x180013f47  jz      short loc_180013F7B
0x180013f49  mov     rcx, rdx; this
0x180013f4c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013f51  mov     ecx, [rax+7C4h]
0x180013f57  cmp     ecx, [rax+7C8h]
0x180013f5d  jnb     short loc_180013F6E
0x180013f5f  add     rcx, rcx
0x180013f62  mov     [rax+rcx*8], r12
0x180013f66  mov     dword ptr [rax+rcx*8+8], 31Fh
0x180013f6e  inc     dword ptr [rax+7C4h]
0x180013f74  mov     rdx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013f7b  xor     eax, eax
0x180013f7d  mov     [rsp+58h+arg_8], r13
0x180013f82  mov     [rsp+58h+arg_10], r14
0x180013f87  cmp     ax, [r15]
0x180013f8b  jnz     loc_1800140C3
0x180013f91  mov     eax, 1000h
0x180013f96  mov     [r15], bx
0x180013f9a  movzx   ecx, bx
0x180013f9d  and     cx, ax
0x180013fa0  xor     eax, eax
0x180013fa2  cmp     ax, cx
0x180013fa5  jnz     loc_180014190
0x180013fab  mov     ecx, 41h ; 'A'
0x180013fb0  mov     r13d, 1Fh
0x180013fb6  test    esi, esi
0x180013fb8  jz      loc_1800141D0
0x180013fbe  movzx   r8d, ax
0x180013fc2  mov     eax, 0Bh
0x180013fc7  cmp     ax, bx
0x180013fca  jz      loc_18001477B
0x180013fd0  mov     eax, 8
0x180013fd5  cmp     ax, bx
0x180013fd8  jz      loc_180014798
0x180013fde  mov     r14d, 0FFFh
0x180013fe4  and     ebx, r14d
0x180013fe7  cmp     ebx, r13d
0x180013fea  jnz     loc_180014114
0x180013ff0  test    sil, 1
0x180013ff4  jnz     loc_18001443F
0x180013ffa  cmp     esi, 2
0x180013ffd  jb      loc_18001443F
0x180014003  mov     rcx, rsi; cb
0x180014006  mov     rbx, rsi
0x180014009  call    cs:__imp_CoTaskMemAlloc
0x180014010  nop     dword ptr [rax+rax+00h]
0x180014015  mov     [r15+8], rax
0x180014019  lea     r12, [r15+8]
0x18001401d  mov     rcx, rax
0x180014020  test    rax, rax
0x180014023  jz      loc_1800143B6
0x180014029  xor     eax, eax
0x18001402b  shr     rbx, 1
0x18001402e  mov     [rcx], ax
0x180014031  jz      loc_180014A58
0x180014037  mov     rdx, [r12]
0x18001403b  mov     eax, 7FFFFFFEh
0x180014040  test    rax, rax
0x180014043  jz      short loc_180014061
0x180014045  movzx   ecx, word ptr [rdi]
0x180014048  test    cx, cx
0x18001404b  jz      short loc_180014061
0x18001404d  mov     [rdx], cx
0x180014050  add     rdi, 2
0x180014054  add     rdx, 2
0x180014058  dec     rax
0x18001405b  sub     rbx, 1
0x18001405f  jnz     short loc_180014040
0x180014061  xor     eax, eax
0x180014063  lea     rcx, [rdx-2]
0x180014067  test    rbx, rbx
0x18001406a  mov     ebp, 8007007Ah
0x18001406f  cmovnz  rcx, rdx
0x180014073  cmovnz  ebp, eax
0x180014076  mov     [rcx], ax
0x180014079  test    ebp, ebp
0x18001407b  js      loc_180014A51
0x180014081  and     r14w, [r15]
0x180014085  cmp     r14w, 9
0x18001408a  jz      loc_180014AA7
0x180014090  cmp     r14w, 0Dh
0x180014095  jz      loc_180014AA7
0x18001409b  lea     rcx, [rsp+58h+arg_0]; this
0x1800140a0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800140a5  mov     r14, [rsp+58h+arg_10]
0x1800140aa  mov     eax, ebp
0x1800140ac  mov     r13, [rsp+58h+arg_8]
0x1800140b1  mov     rbx, [rsp+58h+arg_18]
0x1800140b6  add     rsp, 30h
0x1800140ba  pop     r15
0x1800140bc  pop     r12
0x1800140be  pop     rdi
0x1800140bf  pop     rsi
0x1800140c0  pop     rbp
0x1800140c1  retn
0x1800140c3  mov     ebp, 0C00D36EAh
0x1800140c8  test    rdx, rdx
0x1800140cb  jnz     loc_180014B48
0x1800140d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800140d8  nop     dword ptr [rax+rax+00h]
0x1800140dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800140e4  mov     rcx, rax
0x1800140e7  test    rax, rax
0x1800140ea  jnz     loc_180014B28
0x1800140f0  lea     rdx, qword_1801B97E0
0x1800140f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800140fe  jmp     loc_180014B48
0x180014103  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180014108  mov     rdx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001410f  jmp     loc_180013F3C
0x180014114  xor     ebp, ebp
0x180014116  cmp     ebx, 41h ; 'A'
0x180014119  jnz     short loc_180014152
0x18001411b  mov     rcx, rsi; cb
0x18001411e  call    cs:__imp_CoTaskMemAlloc
0x180014125  nop     dword ptr [rax+rax+00h]
0x18001412a  mov     [r15+10h], rax
0x18001412e  test    rax, rax
0x180014131  jz      loc_18001436F
0x180014137  lea     r12, [r15+8]
0x18001413b  mov     r8, rsi; Size
0x18001413e  mov     rdx, rdi; Src
0x180014141  mov     [r12], esi
0x180014145  mov     rcx, rax; void *
0x180014148  call    memcpy_0
0x18001414d  jmp     loc_180014081
0x180014152  add     ebx, 0FFFFFFFEh; switch 71 cases
0x180014155  cmp     ebx, 46h
0x180014158  ja      def_18001417C; jumptable 000000018001417C default case, cases 4-8,10,12,15,24-29,31-63,65-71
0x18001415e  lea     r9, __ImageBase
0x180014165  movsxd  rax, ebx
0x180014168  movzx   eax, ds:(byte_180014BA0 - 180000000h)[r9+rax]
0x180014171  mov     ecx, ds:(jpt_18001417C - 180000000h)[r9+rax*4]
0x180014179  add     rcx, r9
0x18001417c  jmp     rcx; switch jump
0x180014182  lea     r12, [r15+8]; jumptable 000000018001417C case 11
0x180014186  mov     [r12], r8w
0x18001418b  jmp     loc_180014081
0x180014190  mov     ebp, 0C00D36EBh
0x180014195  test    rdx, rdx
0x180014198  jnz     loc_180014704
0x18001419e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800141a5  nop     dword ptr [rax+rax+00h]
0x1800141aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800141b1  mov     rcx, rax
0x1800141b4  test    rax, rax
0x1800141b7  jnz     loc_1800146E4
0x1800141bd  lea     rdx, qword_1801B97E0
0x1800141c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800141cb  jmp     loc_180014704
0x1800141d0  cmp     ax, bx
0x1800141d3  jz      loc_180014725
0x1800141d9  cmp     cx, bx
0x1800141dc  jz      loc_18001472D
0x1800141e2  mov     ebx, 80070057h
0x1800141e7  mov     ebp, ebx
0x1800141e9  test    rdx, rdx
0x1800141ec  jnz     loc_180014756
0x1800141f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800141f9  nop     dword ptr [rax+rax+00h]
0x1800141fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014205  mov     rcx, rax
0x180014208  test    rax, rax
0x18001420b  jnz     loc_180014736
0x180014211  lea     rdx, qword_1801B97E0
0x180014218  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001421f  jmp     loc_180014756
0x180014224  mov     rdx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001422b  mov     ebp, 8007000Eh
0x180014230  test    rdx, rdx
0x180014233  jnz     loc_180014825
0x180014239  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014240  nop     dword ptr [rax+rax+00h]
0x180014245  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001424c  mov     rcx, rax
0x18001424f  test    rax, rax
0x180014252  jnz     loc_180014805
0x180014258  lea     rdx, qword_1801B97E0
0x18001425f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x180014266  jmp     loc_180014825
0x18001426b  test    rdx, rdx
0x18001426e  jnz     loc_18001486A
0x180014274  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001427b  nop     dword ptr [rax+rax+00h]
0x180014280  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014287  mov     rcx, rax
0x18001428a  test    rax, rax
0x18001428d  jnz     loc_18001484A
0x180014293  lea     rdx, qword_1801B97E0
0x18001429a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800142a1  jmp     loc_18001486A
0x1800142a6  mov     ebp, 8000FFFFh
0x1800142ab  test    rdx, rdx
0x1800142ae  jnz     loc_1800148AF
0x1800142b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800142bb  nop     dword ptr [rax+rax+00h]
0x1800142c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800142c7  mov     rcx, rax
0x1800142ca  test    rax, rax
0x1800142cd  jnz     loc_18001488F
0x1800142d3  lea     rdx, qword_1801B97E0
0x1800142da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800142e1  jmp     loc_1800148AF
0x1800142e6  mov     rdx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800142ed  mov     ebp, 8007000Eh
0x1800142f2  test    rdx, rdx
0x1800142f5  jnz     loc_180014930
0x1800142fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014302  nop     dword ptr [rax+rax+00h]
0x180014307  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001430e  mov     rcx, rax
0x180014311  test    rax, rax
0x180014314  jnz     loc_180014910
0x18001431a  lea     rdx, qword_1801B97E0
0x180014321  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x180014328  jmp     loc_180014930
0x18001432d  mov     ebx, 80070057h; jumptable 000000018001417C default case, cases 4-8,10,12,15,24-29,31-63,65-71
0x180014332  mov     ebp, ebx
0x180014334  test    rdx, rdx
0x180014337  jnz     loc_1800149A6
0x18001433d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014344  nop     dword ptr [rax+rax+00h]
0x180014349  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014350  mov     rcx, rax
0x180014353  test    rax, rax
0x180014356  jnz     loc_180014986
0x18001435c  lea     rdx, qword_1801B97E0
0x180014363  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001436a  jmp     loc_1800149A6
0x18001436f  mov     rdx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014376  mov     ebp, 8007000Eh
0x18001437b  test    rdx, rdx
0x18001437e  jnz     loc_1800149E7
0x180014384  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001438b  nop     dword ptr [rax+rax+00h]
0x180014390  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014397  mov     rcx, rax
0x18001439a  test    rax, rax
0x18001439d  jnz     loc_1800149C7
0x1800143a3  lea     rdx, qword_1801B97E0
0x1800143aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800143b1  jmp     loc_1800149E7
0x1800143b6  mov     rdx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800143bd  mov     ebp, 8007000Eh
0x1800143c2  test    rdx, rdx
0x1800143c5  jnz     loc_180014A2C
0x1800143cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800143d2  nop     dword ptr [rax+rax+00h]
0x1800143d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800143de  mov     rcx, rax
0x1800143e1  test    rax, rax
0x1800143e4  jnz     loc_180014A0C
0x1800143ea  lea     rdx, qword_1801B97E0
0x1800143f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800143f8  jmp     loc_180014A2C
0x1800143fd  mov     rdx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014404  test    rdx, rdx
0x180014407  jnz     loc_180014A84
0x18001440d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014414  nop     dword ptr [rax+rax+00h]
0x180014419  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014420  mov     rcx, rax
0x180014423  test    rax, rax
0x180014426  jnz     loc_180014A64
0x18001442c  lea     rdx, qword_1801B97E0
0x180014433  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001443a  jmp     loc_180014A84
0x18001443f  mov     ebx, 80070057h
0x180014444  mov     ebp, ebx
0x180014446  test    rdx, rdx
0x180014449  jnz     loc_180014AE5
0x18001444f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014456  nop     dword ptr [rax+rax+00h]
0x18001445b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014462  mov     rcx, rax
0x180014465  test    rax, rax
0x180014468  jnz     loc_180014AC5
0x18001446e  lea     rdx, qword_1801B97E0
0x180014475  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001447c  jmp     loc_180014AE5
0x180014481  mov     rcx, rdx; this
0x180014484  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180014489  cmp     [rax+7CCh], ebp
0x18001448f  jz      loc_18001470E
  ... truncated ...
```
