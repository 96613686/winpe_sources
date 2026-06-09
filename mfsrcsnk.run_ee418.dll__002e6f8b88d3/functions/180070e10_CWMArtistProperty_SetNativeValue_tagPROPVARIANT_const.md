# CWMArtistProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180070e10`
- end: `0x18007174b`
- name: `?SetNativeValue@CWMArtistProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `2363`
- prototype: `int(CWMArtistProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180025548`
- `0x1800275f0`
- `0x1800297c0`
- `0x180029a00`
- `0x18006036c`
- `0x180070e10`
- `0x180071a44`
- `0x180073b14`
- `0x180083944`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070fac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800710db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071165`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800711ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071279`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800713b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071534`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071591`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007167e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180070fac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800710db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071165`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800711ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071279`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800713b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071485`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071534`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071591`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007167e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180071514`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180071662`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180071514`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180071662`

## pseudocode

```c
__int64 __fastcall CWMArtistProperty::SetNativeValue(PROPVARIANT *this, struct tagPROPVARIANT *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // r9
  CallStackTracing *v7; // rcx
  int Element; // edi
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  int v11; // r15d
  unsigned int i; // r12d
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // ecx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  PROPVARIANT *v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  wchar_t *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r9
  wchar_t *v78; // rcx
  CallStackTracing *v79; // rax
  struct CallStackContext *v80; // rax
  PROPVARIANT v82; // [rsp+30h] [rbp-29h] BYREF
  PROPVARIANT pvarSrc; // [rsp+48h] [rbp-11h] BYREF
  PROPVARIANT v84; // [rsp+60h] [rbp+7h] BYREF
  PROPVARIANT pvarDest; // [rsp+78h] [rbp+1Fh] BYREF
  char v86; // [rsp+D0h] [rbp+77h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v86, "CWMArtistProperty::SetNativeValue", 902);
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  memset(&pvarDest, 0, sizeof(pvarDest));
  CMFPropVariant::Clear(&pvarDest);
  CMFPropVariant::Copy(&pvarDest, a2, v4, v5);
  if ( (pvarDest.vt & 0xFFF) != 0x1F )
  {
    v7 = CallStackTracing::s_wpInstance;
    Element = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMArtistProperty::SetNativeValue", 912, -2147418113);
    }
    if ( g_wppLevels )
    {
      v10 = 91;
LABEL_145:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        Element);
      goto LABEL_146;
    }
    goto LABEL_146;
  }
  if ( (pvarDest.vt & 0x1000) != 0 )
  {
    v11 = 0;
    for ( i = 0; i < CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest); ++i )
    {
      memset(&v82, 0, sizeof(v82));
      memset(&v84, 0, sizeof(v84));
      Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, i, &v82);
      if ( Element < 0 )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != Element )
            CallStackContext::TraceFailure(v46, "CWMArtistProperty::SetNativeValue", 921, Element);
        }
        if ( g_wppLevels )
        {
          v34 = 92;
LABEL_80:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v34,
            &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            Element);
        }
LABEL_81:
        CMFPropVariant::Clear(&v84);
        v47 = &v82;
LABEL_82:
        CMFPropVariant::Clear(v47);
        goto LABEL_146;
      }
      v16 = *v82.bstrVal;
      if ( v11 )
      {
        v17 = v16 - 68;
        if ( !v17 )
        {
          v17 = *(unsigned __int16 *)(v82.hVal.QuadPart + 2) - 67;
          if ( *(_WORD *)(v82.hVal.QuadPart + 2) == 67 )
            v17 = *(unsigned __int16 *)(v82.hVal.QuadPart + 4);
        }
        if ( v17 )
        {
          Element = CMFPropVariant::CreateString((CMFPropVariant *)&v84, 31, (const CHAR *)L"AC");
          if ( Element < 0 )
          {
            v38 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
              CallStackTracing::s_wpInstance = v39;
              if ( v39
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
              {
                v38 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v38 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v38 + 8) )
            {
              v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
              if ( *((_DWORD *)v40 + 499) != Element )
                CallStackContext::TraceFailure(v40, "CWMArtistProperty::SetNativeValue", 941, Element);
            }
            if ( g_wppLevels )
            {
              v34 = 94;
              goto LABEL_80;
            }
            goto LABEL_81;
          }
          CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &v84);
        }
        else
        {
          CMFPropVariant::Clear(&v82);
          Element = CMFPropVariant::CreateString((CMFPropVariant *)&v82, 31, (const CHAR *)L"AC/DC");
          if ( Element < 0 )
          {
            v21 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
              CallStackTracing::s_wpInstance = v22;
              if ( v22
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
              {
                v21 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v21 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
              if ( *((_DWORD *)v33 + 499) != Element )
                CallStackContext::TraceFailure(v33, "CWMArtistProperty::SetNativeValue", 934, Element);
            }
            if ( g_wppLevels )
            {
              v34 = 93;
              goto LABEL_80;
            }
            goto LABEL_81;
          }
        }
        Element = CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &v82);
        if ( Element < 0 )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != Element )
              CallStackContext::TraceFailure(v37, "CWMArtistProperty::SetNativeValue", 944, Element);
          }
          if ( g_wppLevels )
          {
            v34 = 95;
            goto LABEL_80;
          }
          goto LABEL_81;
        }
        v11 = 0;
      }
      else
      {
        v29 = v16 - 65;
        if ( !v29 )
        {
          v29 = *(unsigned __int16 *)(v82.hVal.QuadPart + 2) - 67;
          if ( *(_WORD *)(v82.hVal.QuadPart + 2) == 67 )
            v29 = *(unsigned __int16 *)(v82.hVal.QuadPart + 4);
        }
        if ( v29 )
        {
          Element = CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &v82);
          if ( Element < 0 )
          {
            v41 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
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
              v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
              if ( *((_DWORD *)v43 + 499) != Element )
                CallStackContext::TraceFailure(v43, "CWMArtistProperty::SetNativeValue", 959, Element);
            }
            if ( g_wppLevels )
            {
              v34 = 96;
              goto LABEL_80;
            }
            goto LABEL_81;
          }
        }
        else
        {
          v11 = 1;
        }
      }
      CMFPropVariant::Clear(&v84);
      CMFPropVariant::Clear(&v82);
    }
    if ( v11 )
    {
      memset(&v84, 0, sizeof(v84));
      CMFPropVariant::CreateString((CMFPropVariant *)&v84, 31, (const CHAR *)L"AC");
      CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &v84);
      CMFPropVariant::Clear(&v84);
    }
    if ( (pvarSrc.vt & 0x1000) != 0 && CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarSrc) == 1 )
    {
      memset(&v84, 0, sizeof(v84));
      Element = CMFPropVariant::Copy(&v84, &pvarSrc, v48, v49);
      if ( Element < 0 )
      {
        v53 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
          CallStackTracing::s_wpInstance = v54;
          if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          {
            v53 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v53 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
          if ( *((_DWORD *)v55 + 499) != Element )
            CallStackContext::TraceFailure(v55, "CWMArtistProperty::SetNativeValue", 981, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_99;
        v56 = 97;
LABEL_98:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v56,
          &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          Element);
LABEL_99:
        v47 = &v84;
        goto LABEL_82;
      }
      CMFPropVariant::Clear(&pvarSrc);
      Element = CMFPropVariant::CreateString((CMFPropVariant *)&pvarSrc, 31, *(const CHAR **)v84.bstrblobVal.pData);
      if ( Element < 0 )
      {
        v60 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58, v59);
          CallStackTracing::s_wpInstance = v61;
          if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
          {
            v60 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v60 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v60 + 8) )
        {
          v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
          if ( *((_DWORD *)v62 + 499) != Element )
            CallStackContext::TraceFailure(v62, "CWMArtistProperty::SetNativeValue", 984, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_99;
        v56 = 98;
        goto LABEL_98;
      }
      CMFPropVariant::Clear(&v84);
    }
LABEL_112:
    Element = PropVariantCopy(this + 5, &pvarSrc);
    if ( Element >= 0 )
    {
      Element = PropVariantCopy(this + 4, &pvarSrc);
      if ( Element < 0 )
      {
        v78 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v79 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v75, v76, v77);
          CallStackTracing::s_wpInstance = v79;
          if ( v79 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v79 + 8LL))(v79, 2032) )
          {
            v78 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v78 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v78 + 8) )
        {
          v80 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v78);
          if ( *((_DWORD *)v80 + 499) != Element )
            CallStackContext::TraceFailure(v80, "CWMArtistProperty::SetNativeValue", 996, Element);
        }
        if ( g_wppLevels )
        {
          v10 = 101;
          goto LABEL_145;
        }
      }
    }
    else
    {
      v66 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
        CallStackTracing::s_wpInstance = v67;
        if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
        {
          v66 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v66 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v66 + 8) )
      {
        v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
        if ( *((_DWORD *)v74 + 499) != Element )
          CallStackContext::TraceFailure(v74, "CWMArtistProperty::SetNativeValue", 995, Element);
      }
      if ( g_wppLevels )
      {
        v10 = 100;
        goto LABEL_145;
      }
    }
    goto LABEL_146;
  }
  Element = CMFPropVariant::Copy(&pvarSrc, &pvarDest, 31, v6);
  if ( Element >= 0 )
    goto LABEL_112;
  v71 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69, v70);
    CallStackTracing::s_wpInstance = v72;
    if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
    {
      v71 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v71 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v71 + 8) )
  {
    v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
    if ( *((_DWORD *)v73 + 499) != Element )
      CallStackContext::TraceFailure(v73, "CWMArtistProperty::SetNativeValue", 992, Element);
  }
  if ( g_wppLevels )
  {
    v10 = 99;
    goto LABEL_145;
  }
LABEL_146:
  CMFPropVariant::Clear(&pvarDest);
  CMFPropVariant::Clear(&pvarSrc);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v86);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180070e10  mov     [rsp-8+arg_0], rbx
0x180070e15  mov     [rsp-8+arg_8], rdi
0x180070e1a  push    rbp
0x180070e1b  push    r12
0x180070e1d  push    r13
0x180070e1f  push    r14
0x180070e21  push    r15
0x180070e23  lea     rbp, [rsp-37h]
0x180070e28  sub     rsp, 90h
0x180070e2f  mov     rbx, rdx
0x180070e32  lea     r13, aCwmartistprope; "CWMArtistProperty::SetNativeValue"
0x180070e39  mov     r14, rcx
0x180070e3c  mov     rdx, r13; char *
0x180070e3f  mov     r8d, 386h; int
0x180070e45  lea     rcx, [rbp+57h+arg_10]; this
0x180070e49  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180070e4e  xor     eax, eax
0x180070e50  lea     rcx, [rbp+57h+pvarDest]; this
0x180070e54  xorps   xmm0, xmm0
0x180070e57  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x180070e5b  xorps   xmm1, xmm1
0x180070e5e  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x180070e62  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x180070e66  movups  xmmword ptr [rbp+57h+pvarDest], xmm1
0x180070e6a  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180070e6f  mov     rdx, rbx; pvarSrc
0x180070e72  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x180070e76  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180070e7b  movzx   ecx, word ptr [rbp+57h+pvarDest]
0x180070e7f  mov     edx, 0FFFh
0x180070e84  movzx   eax, cx
0x180070e87  mov     r8d, 1Fh
0x180070e8d  and     ax, dx
0x180070e90  xor     ebx, ebx
0x180070e92  cmp     ax, r8w
0x180070e96  jz      short loc_180070EF2
0x180070e98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070e9f  mov     edi, 8000FFFFh
0x180070ea4  test    rcx, rcx
0x180070ea7  jnz     short loc_180070EB5
0x180070ea9  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180070eae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180070eb5  cmp     [rcx+8], bl
0x180070eb8  jz      short loc_180070EDB
0x180070eba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180070ebf  cmp     [rax+7CCh], edi
0x180070ec5  jz      short loc_180070EDB
0x180070ec7  mov     r9d, edi; int
0x180070eca  mov     r8d, 390h; int
0x180070ed0  mov     rdx, r13; char *
0x180070ed3  mov     rcx, rax; this
0x180070ed6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180070edb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180070ee2  jb      loc_180071711
0x180070ee8  mov     edx, 5Bh ; '['
0x180070eed  jmp     loc_1800716F3
0x180070ef2  mov     edi, 1000h
0x180070ef7  and     cx, di
0x180070efa  cmp     bx, cx
0x180070efd  jz      loc_180071572
0x180070f03  mov     r15d, ebx
0x180070f06  mov     r12d, ebx
0x180070f09  lea     rcx, [rbp+57h+pvarDest]; this
0x180070f0d  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x180070f12  cmp     r12d, eax
0x180070f15  jnb     loc_180071323
0x180070f1b  xor     eax, eax
0x180070f1d  lea     r8, [rbp+57h+var_80]; pvarDest
0x180070f21  xorps   xmm0, xmm0
0x180070f24  mov     qword ptr [rbp+57h+var_80+10h], rax
0x180070f28  xorps   xmm1, xmm1
0x180070f2b  mov     qword ptr [rbp+57h+var_50+10h], rax
0x180070f2f  mov     edx, r12d; unsigned int
0x180070f32  lea     rcx, [rbp+57h+pvarDest]; this
0x180070f36  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180070f3a  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x180070f3e  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x180070f43  mov     edi, eax
0x180070f45  test    eax, eax
0x180070f47  js      loc_18007126D
0x180070f4d  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x180070f51  movzx   ecx, word ptr [rdx]
0x180070f54  test    r15d, r15d
0x180070f57  jz      loc_180071032
0x180070f5d  sub     ecx, 44h ; 'D'
0x180070f60  jnz     short loc_180070F74
0x180070f62  movzx   ecx, word ptr [rdx+2]
0x180070f66  sub     ecx, 43h ; 'C'
0x180070f69  jnz     short loc_180070F74
0x180070f6b  movzx   ecx, word ptr [rdx+4]
0x180070f6f  movzx   eax, bx
0x180070f72  sub     ecx, eax
0x180070f74  test    ecx, ecx
0x180070f76  jnz     short loc_180070FEA
0x180070f78  lea     rcx, [rbp+57h+var_80]; this
0x180070f7c  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180070f81  mov     edx, 1Fh; unsigned __int16
0x180070f86  lea     r8, aAcDc; "AC/DC"
0x180070f8d  lea     rcx, [rbp+57h+var_80]; this
0x180070f91  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x180070f96  mov     edi, eax
0x180070f98  test    eax, eax
0x180070f9a  jns     short loc_180071016
0x180070f9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070fa3  test    rcx, rcx
0x180070fa6  jnz     loc_180071092
0x180070fac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180070fb2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180070fb9  mov     rcx, rax
0x180070fbc  test    rax, rax
0x180070fbf  jz      loc_180071084
0x180070fc5  mov     rax, [rax]
0x180070fc8  mov     edx, 7F0h
0x180070fcd  mov     rax, [rax+8]
0x180070fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070fd6  test    eax, eax
0x180070fd8  jz      loc_180071084
0x180070fde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180070fe5  jmp     loc_180071092
0x180070fea  mov     edx, 1Fh; unsigned __int16
0x180070fef  lea     r8, aAc; "AC"
0x180070ff6  lea     rcx, [rbp+57h+var_50]; this
0x180070ffa  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x180070fff  mov     edi, eax
0x180071001  test    eax, eax
0x180071003  js      loc_180071159
0x180071009  lea     rdx, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x18007100d  lea     rcx, [rbp+57h+pvarSrc]; this
0x180071011  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x180071016  lea     rdx, [rbp+57h+var_80]; struct tagPROPVARIANT *
0x18007101a  lea     rcx, [rbp+57h+pvarSrc]; this
0x18007101e  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x180071023  mov     edi, eax
0x180071025  test    eax, eax
0x180071027  js      loc_1800710CF
0x18007102d  mov     r15d, ebx
0x180071030  jmp     short loc_18007106A
0x180071032  sub     ecx, 41h ; 'A'
0x180071035  jnz     short loc_180071049
0x180071037  movzx   ecx, word ptr [rdx+2]
0x18007103b  sub     ecx, 43h ; 'C'
0x18007103e  jnz     short loc_180071049
0x180071040  movzx   ecx, word ptr [rdx+4]
0x180071044  movzx   eax, bx
0x180071047  sub     ecx, eax
0x180071049  test    ecx, ecx
0x18007104b  jnz     short loc_180071053
0x18007104d  lea     r15d, [rcx+1]
0x180071051  jmp     short loc_18007106A
0x180071053  lea     rdx, [rbp+57h+var_80]; struct tagPROPVARIANT *
0x180071057  lea     rcx, [rbp+57h+pvarSrc]; this
0x18007105b  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x180071060  mov     edi, eax
0x180071062  test    eax, eax
0x180071064  js      loc_1800711E3
0x18007106a  lea     rcx, [rbp+57h+var_50]; this
0x18007106e  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180071073  lea     rcx, [rbp+57h+var_80]; this
0x180071077  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18007107c  inc     r12d
0x18007107f  jmp     loc_180070F09
0x180071084  lea     rcx, qword_1801B07E0; this
0x18007108b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071092  cmp     [rcx+8], bl
0x180071095  jz      short loc_1800710B8
0x180071097  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007109c  cmp     [rax+7CCh], edi
0x1800710a2  jz      short loc_1800710B8
0x1800710a4  mov     r9d, edi; int
0x1800710a7  mov     r8d, 3A6h; int
0x1800710ad  mov     rdx, r13; char *
0x1800710b0  mov     rcx, rax; this
0x1800710b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800710b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800710bf  jb      loc_18007130C
0x1800710c5  mov     edx, 5Dh ; ']'
0x1800710ca  jmp     loc_1800712EE
0x1800710cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710d6  test    rcx, rcx
0x1800710d9  jnz     short loc_18007111C
0x1800710db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800710e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710e8  mov     rcx, rax
0x1800710eb  test    rax, rax
0x1800710ee  jz      short loc_18007110E
0x1800710f0  mov     rax, [rax]
0x1800710f3  mov     edx, 7F0h
0x1800710f8  mov     rax, [rax+8]
0x1800710fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071101  test    eax, eax
0x180071103  jz      short loc_18007110E
0x180071105  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007110c  jmp     short loc_18007111C
0x18007110e  lea     rcx, qword_1801B07E0; this
0x180071115  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007111c  cmp     [rcx+8], bl
0x18007111f  jz      short loc_180071142
0x180071121  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071126  cmp     [rax+7CCh], edi
0x18007112c  jz      short loc_180071142
0x18007112e  mov     r9d, edi; int
0x180071131  mov     r8d, 3B0h; int
0x180071137  mov     rdx, r13; char *
0x18007113a  mov     rcx, rax; this
0x18007113d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071142  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071149  jb      loc_18007130C
0x18007114f  mov     edx, 5Fh ; '_'
0x180071154  jmp     loc_1800712EE
0x180071159  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071160  test    rcx, rcx
0x180071163  jnz     short loc_1800711A6
0x180071165  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007116b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071172  mov     rcx, rax
0x180071175  test    rax, rax
0x180071178  jz      short loc_180071198
0x18007117a  mov     rax, [rax]
0x18007117d  mov     edx, 7F0h
0x180071182  mov     rax, [rax+8]
0x180071186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007118b  test    eax, eax
0x18007118d  jz      short loc_180071198
0x18007118f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071196  jmp     short loc_1800711A6
0x180071198  lea     rcx, qword_1801B07E0; this
0x18007119f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711a6  cmp     [rcx+8], bl
0x1800711a9  jz      short loc_1800711CC
0x1800711ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800711b0  cmp     [rax+7CCh], edi
0x1800711b6  jz      short loc_1800711CC
0x1800711b8  mov     r9d, edi; int
0x1800711bb  mov     r8d, 3ADh; int
0x1800711c1  mov     rdx, r13; char *
0x1800711c4  mov     rcx, rax; this
0x1800711c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800711cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800711d3  jb      loc_18007130C
0x1800711d9  mov     edx, 5Eh ; '^'
0x1800711de  jmp     loc_1800712EE
0x1800711e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711ea  test    rcx, rcx
0x1800711ed  jnz     short loc_180071230
0x1800711ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800711f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711fc  mov     rcx, rax
0x1800711ff  test    rax, rax
0x180071202  jz      short loc_180071222
0x180071204  mov     rax, [rax]
0x180071207  mov     edx, 7F0h
0x18007120c  mov     rax, [rax+8]
0x180071210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071215  test    eax, eax
0x180071217  jz      short loc_180071222
0x180071219  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071220  jmp     short loc_180071230
0x180071222  lea     rcx, qword_1801B07E0; this
0x180071229  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071230  cmp     [rcx+8], bl
0x180071233  jz      short loc_180071256
0x180071235  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007123a  cmp     [rax+7CCh], edi
0x180071240  jz      short loc_180071256
0x180071242  mov     r9d, edi; int
0x180071245  mov     r8d, 3BFh; int
0x18007124b  mov     rdx, r13; char *
0x18007124e  mov     rcx, rax; this
0x180071251  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071256  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007125d  jb      loc_18007130C
0x180071263  mov     edx, 60h ; '`'
0x180071268  jmp     loc_1800712EE
0x18007126d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071274  test    rcx, rcx
0x180071277  jnz     short loc_1800712BA
0x180071279  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007127f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071286  mov     rcx, rax
0x180071289  test    rax, rax
0x18007128c  jz      short loc_1800712AC
0x18007128e  mov     rax, [rax]
0x180071291  mov     edx, 7F0h
0x180071296  mov     rax, [rax+8]
0x18007129a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007129f  test    eax, eax
0x1800712a1  jz      short loc_1800712AC
0x1800712a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800712aa  jmp     short loc_1800712BA
0x1800712ac  lea     rcx, qword_1801B07E0; this
0x1800712b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800712ba  cmp     [rcx+8], bl
0x1800712bd  jz      short loc_1800712E0
0x1800712bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800712c4  cmp     [rax+7CCh], edi
0x1800712ca  jz      short loc_1800712E0
0x1800712cc  mov     r9d, edi; int
0x1800712cf  mov     r8d, 399h; int
0x1800712d5  mov     rdx, r13; char *
0x1800712d8  mov     rcx, rax; this
  ... truncated ...
```
