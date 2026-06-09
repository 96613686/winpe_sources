# CWMArtistProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180076a70`
- end: `0x1800773fc`
- name: `?SetNativeValue@CWMArtistProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `2444`
- prototype: `int(CWMArtistProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x180013110`
- `0x1800153e4`
- `0x180015410`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180060ea0`
- `0x180076a70`
- `0x180077708`
- `0x180079680`
- `0x18008847c`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076c10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076d45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076dd5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076ef5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077037`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007710d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800771c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007722f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076c10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076d45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076dd5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076e65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076ef5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077037`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007710d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800771c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007722f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077328`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800771a2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180077306`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800771a2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180077306`

## pseudocode

```c
__int64 __fastcall CWMArtistProperty::SetNativeValue(PROPVARIANT *this, struct tagPROPVARIANT *a2)
{
  CallStackTracing *v4; // rcx
  HRESULT Element; // edi
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  int v8; // r15d
  unsigned int i; // r12d
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v18; // ecx
  __int64 v19; // rdx
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  PROPVARIANT *p_pvar; // rcx
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  PROPVARIANT pvar; // [rsp+30h] [rbp-29h] BYREF
  PROPVARIANT pvarSrc; // [rsp+48h] [rbp-11h] BYREF
  PROPVARIANT v59; // [rsp+60h] [rbp+7h] BYREF
  PROPVARIANT pvarDest; // [rsp+78h] [rbp+1Fh] BYREF
  char v61; // [rsp+D0h] [rbp+77h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v61, "CWMArtistProperty::SetNativeValue", 902);
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  memset(&pvarDest, 0, sizeof(pvarDest));
  CMFPropVariant::Clear(&pvarDest);
  CMFPropVariant::Copy(&pvarDest, a2);
  if ( (pvarDest.vt & 0xFFF) != 0x1F )
  {
    v4 = CallStackTracing::s_wpInstance;
    Element = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v4 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMArtistProperty::SetNativeValue", 912, -2147418113);
    }
    if ( g_wppLevels )
    {
      v7 = 91;
LABEL_145:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, Element);
      goto LABEL_146;
    }
    goto LABEL_146;
  }
  if ( (pvarDest.vt & 0x1000) != 0 )
  {
    v8 = 0;
    for ( i = 0; i < CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest); ++i )
    {
      memset(&pvar, 0, sizeof(pvar));
      memset(&v59, 0, sizeof(v59));
      Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, i, &pvar);
      if ( Element < 0 )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
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
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v33 + 499) != Element )
            CallStackContext::TraceFailure(v33, "CWMArtistProperty::SetNativeValue", 921, Element);
        }
        if ( g_wppLevels )
        {
          v21 = 92;
LABEL_80:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            Element);
        }
LABEL_81:
        CMFPropVariant::Clear(&v59);
        p_pvar = &pvar;
LABEL_82:
        CMFPropVariant::Clear(p_pvar);
        goto LABEL_146;
      }
      v11 = *pvar.bstrVal;
      if ( v8 )
      {
        v12 = v11 - 68;
        if ( !v12 )
        {
          v12 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 2) - 67;
          if ( *(_WORD *)(pvar.hVal.QuadPart + 2) == 67 )
            v12 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 4);
        }
        if ( v12 )
        {
          Element = CMFPropVariant::CreateString((CMFPropVariant *)&v59, 0x1Fu, L"AC");
          if ( Element < 0 )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
              {
                v25 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v25 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v25 + 8) )
            {
              v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
              if ( *((_DWORD *)v27 + 499) != Element )
                CallStackContext::TraceFailure(v27, "CWMArtistProperty::SetNativeValue", 941, Element);
            }
            if ( g_wppLevels )
            {
              v21 = 94;
              goto LABEL_80;
            }
            goto LABEL_81;
          }
          CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &v59);
        }
        else
        {
          CMFPropVariant::Clear(&pvar);
          Element = CMFPropVariant::CreateString((CMFPropVariant *)&pvar, 0x1Fu, L"AC/DC");
          if ( Element < 0 )
          {
            v14 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
              CallStackTracing::s_wpInstance = v15;
              if ( v15
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
              {
                v14 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v14 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v14 + 8) )
            {
              v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
              if ( *((_DWORD *)v20 + 499) != Element )
                CallStackContext::TraceFailure(v20, "CWMArtistProperty::SetNativeValue", 934, Element);
            }
            if ( g_wppLevels )
            {
              v21 = 93;
              goto LABEL_80;
            }
            goto LABEL_81;
          }
        }
        Element = CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &pvar);
        if ( Element < 0 )
        {
          v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != Element )
              CallStackContext::TraceFailure(v24, "CWMArtistProperty::SetNativeValue", 944, Element);
          }
          if ( g_wppLevels )
          {
            v21 = 95;
            goto LABEL_80;
          }
          goto LABEL_81;
        }
        v8 = 0;
      }
      else
      {
        v18 = v11 - 65;
        if ( !v18 )
        {
          v18 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 2) - 67;
          if ( *(_WORD *)(pvar.hVal.QuadPart + 2) == 67 )
            v18 = *(unsigned __int16 *)(pvar.hVal.QuadPart + 4);
        }
        if ( v18 )
        {
          Element = CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &pvar);
          if ( Element < 0 )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
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
              v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)v30 + 499) != Element )
                CallStackContext::TraceFailure(v30, "CWMArtistProperty::SetNativeValue", 959, Element);
            }
            if ( g_wppLevels )
            {
              v21 = 96;
              goto LABEL_80;
            }
            goto LABEL_81;
          }
        }
        else
        {
          v8 = 1;
        }
      }
      CMFPropVariant::Clear(&v59);
      CMFPropVariant::Clear(&pvar);
    }
    if ( v8 )
    {
      memset(&v59, 0, sizeof(v59));
      CMFPropVariant::CreateString((CMFPropVariant *)&v59, 0x1Fu, L"AC");
      CMFPropVariant::AppendElement((CMFPropVariant *)&pvarSrc, &v59);
      CMFPropVariant::Clear(&v59);
    }
    if ( (pvarSrc.vt & 0x1000) != 0 && CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarSrc) == 1 )
    {
      memset(&v59, 0, sizeof(v59));
      Element = CMFPropVariant::Copy(&v59, &pvarSrc);
      if ( Element < 0 )
      {
        v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
          if ( *((_DWORD *)v38 + 499) != Element )
            CallStackContext::TraceFailure(v38, "CWMArtistProperty::SetNativeValue", 981, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_99;
        v39 = 97;
LABEL_98:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v39,
          WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
          this,
          Element);
LABEL_99:
        p_pvar = &v59;
        goto LABEL_82;
      }
      CMFPropVariant::Clear(&pvarSrc);
      Element = CMFPropVariant::CreateString((CMFPropVariant *)&pvarSrc, 0x1Fu, *(const void **)v59.bstrblobVal.pData);
      if ( Element < 0 )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
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
          v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v43 + 499) != Element )
            CallStackContext::TraceFailure(v43, "CWMArtistProperty::SetNativeValue", 984, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_99;
        v39 = 98;
        goto LABEL_98;
      }
      CMFPropVariant::Clear(&v59);
    }
LABEL_112:
    Element = PropVariantCopy(this + 5, &pvarSrc);
    if ( Element >= 0 )
    {
      Element = PropVariantCopy(this + 4, &pvarSrc);
      if ( Element < 0 )
      {
        v53 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
          CallStackTracing::s_wpInstance = v54;
          if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
          {
            v53 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v53 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
          if ( *((_DWORD *)v55 + 499) != Element )
            CallStackContext::TraceFailure(v55, "CWMArtistProperty::SetNativeValue", 996, Element);
        }
        if ( g_wppLevels )
        {
          v7 = 101;
          goto LABEL_145;
        }
      }
    }
    else
    {
      v45 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v51 + 499) != Element )
          CallStackContext::TraceFailure(v51, "CWMArtistProperty::SetNativeValue", 995, Element);
      }
      if ( g_wppLevels )
      {
        v7 = 100;
        goto LABEL_145;
      }
    }
    goto LABEL_146;
  }
  Element = CMFPropVariant::Copy(&pvarSrc, &pvarDest);
  if ( Element >= 0 )
    goto LABEL_112;
  v48 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
    CallStackTracing::s_wpInstance = v49;
    if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
    {
      v48 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v48 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v48 + 8) )
  {
    v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
    if ( *((_DWORD *)v50 + 499) != Element )
      CallStackContext::TraceFailure(v50, "CWMArtistProperty::SetNativeValue", 992, Element);
  }
  if ( g_wppLevels )
  {
    v7 = 99;
    goto LABEL_145;
  }
LABEL_146:
  CMFPropVariant::Clear(&pvarDest);
  CMFPropVariant::Clear(&pvarSrc);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v61);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180076a70  mov     [rsp-8+arg_0], rbx
0x180076a75  mov     [rsp-8+arg_8], rdi
0x180076a7a  push    rbp
0x180076a7b  push    r12
0x180076a7d  push    r13
0x180076a7f  push    r14
0x180076a81  push    r15
0x180076a83  lea     rbp, [rsp-37h]
0x180076a88  sub     rsp, 90h
0x180076a8f  mov     rbx, rdx
0x180076a92  lea     r13, aCwmartistprope; "CWMArtistProperty::SetNativeValue"
0x180076a99  mov     r14, rcx
0x180076a9c  mov     rdx, r13; char *
0x180076a9f  mov     r8d, 386h; int
0x180076aa5  lea     rcx, [rbp+57h+arg_10]; this
0x180076aa9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180076aae  xor     eax, eax
0x180076ab0  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180076ab4  xorps   xmm0, xmm0
0x180076ab7  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x180076abb  xorps   xmm1, xmm1
0x180076abe  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x180076ac2  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x180076ac6  movups  xmmword ptr [rbp+57h+pvarDest], xmm1
0x180076aca  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180076acf  mov     rdx, rbx; pvarSrc
0x180076ad2  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x180076ad6  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180076adb  movzx   ecx, word ptr [rbp+57h+pvarDest]
0x180076adf  mov     edx, 0FFFh
0x180076ae4  movzx   eax, cx
0x180076ae7  mov     r8d, 1Fh
0x180076aed  and     ax, dx
0x180076af0  xor     ebx, ebx
0x180076af2  cmp     ax, r8w
0x180076af6  jz      short loc_180076B52
0x180076af8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076aff  mov     edi, 8000FFFFh
0x180076b04  test    rcx, rcx
0x180076b07  jnz     short loc_180076B15
0x180076b09  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180076b0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180076b15  cmp     [rcx+8], bl
0x180076b18  jz      short loc_180076B3B
0x180076b1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076b1f  cmp     [rax+7CCh], edi
0x180076b25  jz      short loc_180076B3B
0x180076b27  mov     r9d, edi; int
0x180076b2a  mov     r8d, 390h; int
0x180076b30  mov     rdx, r13; char *
0x180076b33  mov     rcx, rax; this
0x180076b36  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076b3b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076b42  jb      loc_1800773C1
0x180076b48  mov     edx, 5Bh ; '['
0x180076b4d  jmp     loc_1800773A3
0x180076b52  mov     edi, 1000h
0x180076b57  and     cx, di
0x180076b5a  cmp     bx, cx
0x180076b5d  jz      loc_18007720C
0x180076b63  mov     r15d, ebx
0x180076b66  mov     r12d, ebx
0x180076b69  lea     rcx, [rbp+57h+pvarDest]; this
0x180076b6d  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x180076b72  cmp     r12d, eax
0x180076b75  jnb     loc_180076FA5
0x180076b7b  xor     eax, eax
0x180076b7d  lea     r8, [rbp+57h+pvar]; pvarDest
0x180076b81  xorps   xmm0, xmm0
0x180076b84  mov     qword ptr [rbp+57h+pvar+10h], rax
0x180076b88  xorps   xmm1, xmm1
0x180076b8b  mov     qword ptr [rbp+57h+var_50+10h], rax
0x180076b8f  mov     edx, r12d; unsigned int
0x180076b92  lea     rcx, [rbp+57h+pvarDest]; this
0x180076b96  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180076b9a  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x180076b9e  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x180076ba3  mov     edi, eax
0x180076ba5  test    eax, eax
0x180076ba7  js      loc_180076EE9
0x180076bad  mov     rdx, qword ptr [rbp+57h+pvar+8]
0x180076bb1  movzx   ecx, word ptr [rdx]
0x180076bb4  test    r15d, r15d
0x180076bb7  jz      loc_180076C9C
0x180076bbd  sub     ecx, 44h ; 'D'
0x180076bc0  jnz     short loc_180076BD4
0x180076bc2  movzx   ecx, word ptr [rdx+2]
0x180076bc6  sub     ecx, 43h ; 'C'
0x180076bc9  jnz     short loc_180076BD4
0x180076bcb  movzx   ecx, word ptr [rdx+4]
0x180076bcf  movzx   eax, bx
0x180076bd2  sub     ecx, eax
0x180076bd4  test    ecx, ecx
0x180076bd6  jnz     short loc_180076C54
0x180076bd8  lea     rcx, [rbp+57h+pvar]; pvar
0x180076bdc  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180076be1  mov     edx, 1Fh; unsigned __int16
0x180076be6  lea     r8, aAcDc; "AC/DC"
0x180076bed  lea     rcx, [rbp+57h+pvar]; this
0x180076bf1  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x180076bf6  mov     edi, eax
0x180076bf8  test    eax, eax
0x180076bfa  jns     loc_180076C80
0x180076c00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c07  test    rcx, rcx
0x180076c0a  jnz     loc_180076CFC
0x180076c10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076c17  nop     dword ptr [rax+rax+00h]
0x180076c1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c23  mov     rcx, rax
0x180076c26  test    rax, rax
0x180076c29  jz      loc_180076CEE
0x180076c2f  mov     rax, [rax]
0x180076c32  mov     edx, 7F0h
0x180076c37  mov     rax, [rax+8]
0x180076c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076c40  test    eax, eax
0x180076c42  jz      loc_180076CEE
0x180076c48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076c4f  jmp     loc_180076CFC
0x180076c54  mov     edx, 1Fh; unsigned __int16
0x180076c59  lea     r8, aAc; "AC"
0x180076c60  lea     rcx, [rbp+57h+var_50]; this
0x180076c64  call    ?CreateString@CMFPropVariant@@QEAAJGPEBX@Z; CMFPropVariant::CreateString(ushort,void const *)
0x180076c69  mov     edi, eax
0x180076c6b  test    eax, eax
0x180076c6d  js      loc_180076DC9
0x180076c73  lea     rdx, [rbp+57h+var_50]; struct tagPROPVARIANT *
0x180076c77  lea     rcx, [rbp+57h+pvarSrc]; this
0x180076c7b  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x180076c80  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180076c84  lea     rcx, [rbp+57h+pvarSrc]; this
0x180076c88  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x180076c8d  mov     edi, eax
0x180076c8f  test    eax, eax
0x180076c91  js      loc_180076D39
0x180076c97  mov     r15d, ebx
0x180076c9a  jmp     short loc_180076CD4
0x180076c9c  sub     ecx, 41h ; 'A'
0x180076c9f  jnz     short loc_180076CB3
0x180076ca1  movzx   ecx, word ptr [rdx+2]
0x180076ca5  sub     ecx, 43h ; 'C'
0x180076ca8  jnz     short loc_180076CB3
0x180076caa  movzx   ecx, word ptr [rdx+4]
0x180076cae  movzx   eax, bx
0x180076cb1  sub     ecx, eax
0x180076cb3  test    ecx, ecx
0x180076cb5  jnz     short loc_180076CBD
0x180076cb7  lea     r15d, [rcx+1]
0x180076cbb  jmp     short loc_180076CD4
0x180076cbd  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180076cc1  lea     rcx, [rbp+57h+pvarSrc]; this
0x180076cc5  call    ?AppendElement@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::AppendElement(tagPROPVARIANT const *)
0x180076cca  mov     edi, eax
0x180076ccc  test    eax, eax
0x180076cce  js      loc_180076E59
0x180076cd4  lea     rcx, [rbp+57h+var_50]; pvar
0x180076cd8  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180076cdd  lea     rcx, [rbp+57h+pvar]; pvar
0x180076ce1  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180076ce6  inc     r12d
0x180076ce9  jmp     loc_180076B69
0x180076cee  lea     rcx, qword_1801B97E0; this
0x180076cf5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076cfc  cmp     [rcx+8], bl
0x180076cff  jz      short loc_180076D22
0x180076d01  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076d06  cmp     [rax+7CCh], edi
0x180076d0c  jz      short loc_180076D22
0x180076d0e  mov     r9d, edi; int
0x180076d11  mov     r8d, 3A6h; int
0x180076d17  mov     rdx, r13; char *
0x180076d1a  mov     rcx, rax; this
0x180076d1d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076d22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076d29  jb      loc_180076F8E
0x180076d2f  mov     edx, 5Dh ; ']'
0x180076d34  jmp     loc_180076F70
0x180076d39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d40  test    rcx, rcx
0x180076d43  jnz     short loc_180076D8C
0x180076d45  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076d4c  nop     dword ptr [rax+rax+00h]
0x180076d51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d58  mov     rcx, rax
0x180076d5b  test    rax, rax
0x180076d5e  jz      short loc_180076D7E
0x180076d60  mov     rax, [rax]
0x180076d63  mov     edx, 7F0h
0x180076d68  mov     rax, [rax+8]
0x180076d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076d71  test    eax, eax
0x180076d73  jz      short loc_180076D7E
0x180076d75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d7c  jmp     short loc_180076D8C
0x180076d7e  lea     rcx, qword_1801B97E0; this
0x180076d85  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076d8c  cmp     [rcx+8], bl
0x180076d8f  jz      short loc_180076DB2
0x180076d91  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076d96  cmp     [rax+7CCh], edi
0x180076d9c  jz      short loc_180076DB2
0x180076d9e  mov     r9d, edi; int
0x180076da1  mov     r8d, 3B0h; int
0x180076da7  mov     rdx, r13; char *
0x180076daa  mov     rcx, rax; this
0x180076dad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076db2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076db9  jb      loc_180076F8E
0x180076dbf  mov     edx, 5Fh ; '_'
0x180076dc4  jmp     loc_180076F70
0x180076dc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076dd0  test    rcx, rcx
0x180076dd3  jnz     short loc_180076E1C
0x180076dd5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076ddc  nop     dword ptr [rax+rax+00h]
0x180076de1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076de8  mov     rcx, rax
0x180076deb  test    rax, rax
0x180076dee  jz      short loc_180076E0E
0x180076df0  mov     rax, [rax]
0x180076df3  mov     edx, 7F0h
0x180076df8  mov     rax, [rax+8]
0x180076dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e01  test    eax, eax
0x180076e03  jz      short loc_180076E0E
0x180076e05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e0c  jmp     short loc_180076E1C
0x180076e0e  lea     rcx, qword_1801B97E0; this
0x180076e15  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e1c  cmp     [rcx+8], bl
0x180076e1f  jz      short loc_180076E42
0x180076e21  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076e26  cmp     [rax+7CCh], edi
0x180076e2c  jz      short loc_180076E42
0x180076e2e  mov     r9d, edi; int
0x180076e31  mov     r8d, 3ADh; int
0x180076e37  mov     rdx, r13; char *
0x180076e3a  mov     rcx, rax; this
0x180076e3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076e42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076e49  jb      loc_180076F8E
0x180076e4f  mov     edx, 5Eh ; '^'
0x180076e54  jmp     loc_180076F70
0x180076e59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e60  test    rcx, rcx
0x180076e63  jnz     short loc_180076EAC
0x180076e65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076e6c  nop     dword ptr [rax+rax+00h]
0x180076e71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e78  mov     rcx, rax
0x180076e7b  test    rax, rax
0x180076e7e  jz      short loc_180076E9E
0x180076e80  mov     rax, [rax]
0x180076e83  mov     edx, 7F0h
0x180076e88  mov     rax, [rax+8]
0x180076e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076e91  test    eax, eax
0x180076e93  jz      short loc_180076E9E
0x180076e95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076e9c  jmp     short loc_180076EAC
0x180076e9e  lea     rcx, qword_1801B97E0; this
0x180076ea5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076eac  cmp     [rcx+8], bl
0x180076eaf  jz      short loc_180076ED2
0x180076eb1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076eb6  cmp     [rax+7CCh], edi
0x180076ebc  jz      short loc_180076ED2
0x180076ebe  mov     r9d, edi; int
0x180076ec1  mov     r8d, 3BFh; int
0x180076ec7  mov     rdx, r13; char *
0x180076eca  mov     rcx, rax; this
0x180076ecd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076ed2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076ed9  jb      loc_180076F8E
0x180076edf  mov     edx, 60h ; '`'
0x180076ee4  jmp     loc_180076F70
0x180076ee9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076ef0  test    rcx, rcx
0x180076ef3  jnz     short loc_180076F3C
0x180076ef5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076efc  nop     dword ptr [rax+rax+00h]
0x180076f01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076f08  mov     rcx, rax
0x180076f0b  test    rax, rax
0x180076f0e  jz      short loc_180076F2E
0x180076f10  mov     rax, [rax]
0x180076f13  mov     edx, 7F0h
0x180076f18  mov     rax, [rax+8]
0x180076f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f21  test    eax, eax
0x180076f23  jz      short loc_180076F2E
0x180076f25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076f2c  jmp     short loc_180076F3C
0x180076f2e  lea     rcx, qword_1801B97E0; this
0x180076f35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076f3c  cmp     [rcx+8], bl
0x180076f3f  jz      short loc_180076F62
0x180076f41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076f46  cmp     [rax+7CCh], edi
  ... truncated ...
```
