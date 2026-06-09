# CMP3MediaSourcePlugin::SetProperty(ushort const *,tagPROPVARIANT const *)

- ea: `0x1800b8d80`
- end: `0x1800b9664`
- name: `?SetProperty@CMP3MediaSourcePlugin@@UEAAJPEBGPEBUtagPROPVARIANT@@@Z`
- size: `2276`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *__hidden this, const unsigned __int16 *, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x180013110`
- `0x1800153e4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180060ea0`
- `0x18006a890`
- `0x180079680`
- `0x1800a71f0`
- `0x1800b8d80`
- `0x180110ed0`
- `0x180158dd0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9613`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b8df3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b8df3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8e29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8ef4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8fdd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b90a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b917b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9398`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b942d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b94c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9557`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8e29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8ef4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b8fdd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b90a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b917b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9398`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b942d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b94c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b9557`

## string_xrefs

- `0x1800b8dc1`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b903a`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b9100`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b91d8`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b93f5`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b948a`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b951f`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b95b4`: `CMP3MediaSourcePlugin::SetProperty`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::SetProperty(
        CMP3MediaSourcePlugin *this,
        unsigned __int16 *a2,
        PROPVARIANT *pvarSrc)
{
  int v6; // eax
  __int64 v7; // rdx
  int Element; // edi
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  char *v13; // r9
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned int ElementCount; // r13d
  __int64 v19; // rcx
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // r12d
  __int64 v35; // rdx
  __int64 v36; // rdx
  enum WMT_ATTR_DATATYPE v37; // r9d
  unsigned int ulVal; // r11d
  const unsigned __int8 *p_bVal; // r14
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  int v55; // [rsp+40h] [rbp-69h]
  _BYTE v56[4]; // [rsp+50h] [rbp-59h] BYREF
  int v57; // [rsp+54h] [rbp-55h]
  char *v58; // [rsp+58h] [rbp-51h]
  unsigned __int64 v59; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 *v60; // [rsp+68h] [rbp-41h]
  PROPVARIANT pvar; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int8 v62[4]; // [rsp+88h] [rbp-21h] BYREF
  PROPVARIANT pvarDest; // [rsp+90h] [rbp-19h] BYREF
  PROPVARIANT pvarSrca; // [rsp+A8h] [rbp-1h] BYREF

  v60 = a2;
  *(_DWORD *)v62 = 0;
  memset(&pvar, 0, sizeof(pvar));
  memset(&pvarDest, 0, sizeof(pvarDest));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v56, "CMP3MediaSourcePlugin::SetProperty", 2787);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v6 = CMP3MediaSourcePlugin::DeleteProperty(this, a2);
  Element = 0;
  if ( v6 != -1072873843 )
    Element = v6;
  if ( Element < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Element )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSourcePlugin::SetProperty", 2806, Element);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v12 = 279;
LABEL_14:
    v13 = (char *)this - 40;
    goto LABEL_15;
  }
  Element = CMFPropVariant::Copy(&pvarDest, pvarSrc);
  if ( Element < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != Element )
        CallStackContext::TraceFailure(v17, "CMP3MediaSourcePlugin::SetProperty", 2811, Element);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v12 = 280;
    goto LABEL_14;
  }
  v57 = 0;
  ElementCount = CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest);
  if ( ElementCount > 1 )
  {
    v19 = *((_QWORD *)this + 46) + 16LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 46) + 16LL) + 4LL);
    Element = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD))(*(_QWORD *)v19 + 112LL))(v19, a2, 0);
    if ( Element < 0 )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != Element )
          CallStackContext::TraceFailure(v23, "CMP3MediaSourcePlugin::SetProperty", 2821, Element);
      }
      if ( !g_wppLevels )
        goto LABEL_139;
      v12 = 281;
      v13 = (char *)this - 40;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
        v13,
        Element);
      goto LABEL_139;
    }
    if ( Element == 1 )
    {
      memset(&pvarSrca, 0, sizeof(pvarSrca));
      Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, 0, &pvarSrca);
      if ( Element < 0 )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
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
            CallStackContext::TraceFailure(v27, "CMP3MediaSourcePlugin::SetProperty", 2828, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_52;
        v28 = 282;
LABEL_51:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v28,
          &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
          (char *)this - 40,
          Element);
LABEL_52:
        CMFPropVariant::Clear(&pvarSrca);
        goto LABEL_139;
      }
      CMFPropVariant::Clear(&pvarDest);
      Element = CMFPropVariant::Copy(&pvarDest, &pvarSrca);
      if ( Element < 0 )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != Element )
            CallStackContext::TraceFailure(v32, "CMP3MediaSourcePlugin::SetProperty", 2834, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_52;
        v28 = 283;
        goto LABEL_51;
      }
      v33 = CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest);
      v57 = 1;
      ElementCount = v33;
      CMFPropVariant::Clear(&pvarSrca);
    }
  }
  v34 = 0;
  v58 = (char *)this - 40;
  while ( 1 )
  {
    if ( ElementCount <= v34 )
    {
      *((_DWORD *)this + 340) = 1;
      goto LABEL_136;
    }
    Element = CMFPropVariant::Clear(&pvar);
    if ( Element < 0 )
    {
      v51 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
        CallStackTracing::s_wpInstance = v52;
        if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
        {
          v51 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v51 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v51 + 8) )
      {
        v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
        if ( *((_DWORD *)v53 + 499) != Element )
          CallStackContext::TraceFailure(v53, "CMP3MediaSourcePlugin::SetProperty", 2844, Element);
      }
      if ( g_wppLevels )
      {
        v44 = 284;
        goto LABEL_134;
      }
      goto LABEL_136;
    }
    Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, v34, &pvar);
    if ( Element < 0 )
    {
      v48 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
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
          CallStackContext::TraceFailure(v50, "CMP3MediaSourcePlugin::SetProperty", 2849, Element);
      }
      if ( g_wppLevels )
      {
        v44 = 285;
        goto LABEL_134;
      }
      goto LABEL_136;
    }
    if ( pvar.vt > 0x14u )
      break;
    switch ( pvar.vt )
    {
      case 0x14u:
        goto LABEL_89;
      case 2u:
        goto LABEL_79;
      case 3u:
        goto LABEL_77;
    }
    if ( pvar.vt != 8 )
    {
      switch ( pvar.vt )
      {
        case 0xBu:
          p_bVal = v62;
          v37 = WMT_TYPE_BOOL;
          *(_DWORD *)v62 = pvar.iVal == 0xFFFF;
          ulVal = 4;
          goto LABEL_91;
        case 0x12u:
LABEL_79:
          v37 = WMT_TYPE_WORD;
          ulVal = 2;
          break;
        case 0x13u:
LABEL_77:
          v37 = WMT_TYPE_DWORD;
          ulVal = 4;
          break;
        default:
          goto LABEL_93;
      }
LABEL_90:
      p_bVal = &pvar.bVal;
      goto LABEL_91;
    }
LABEL_87:
    p_bVal = pvar.pbVal;
    v59 = 0;
    Element = StringCbLengthW(pvar.bstrVal, 0xFFFFFFFE, &v59);
    if ( Element < 0 )
      goto LABEL_94;
    ulVal = v59;
    v37 = WMT_TYPE_STRING;
LABEL_91:
    Element = CWMHeaderInfoIndexBase::AddIndexedAttribute(
                (CWMHeaderInfoIndexBase *)(*((_QWORD *)this + 46)
                                         + 16LL
                                         + *(int *)(*(_QWORD *)(*((_QWORD *)this + 46) + 16LL) + 8LL)),
                0,
                v60,
                v37,
                0,
                p_bVal,
                ulVal,
                0,
                v55);
    if ( Element < 0 )
    {
      v45 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
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
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != Element )
          CallStackContext::TraceFailure(v47, "CMP3MediaSourcePlugin::SetProperty", 2930, Element);
      }
      if ( g_wppLevels )
      {
        v44 = 287;
        goto LABEL_134;
      }
      goto LABEL_136;
    }
    ++v34;
  }
  switch ( pvar.vt )
  {
    case 0x15u:
      goto LABEL_89;
    case 0x1Fu:
      goto LABEL_87;
    case 0x40u:
LABEL_89:
      v37 = WMT_TYPE_QWORD;
      ulVal = 8;
      goto LABEL_90;
    case 0x41u:
      p_bVal = pvar.bstrblobVal.pData;
      v37 = WMT_TYPE_BINARY;
      ulVal = pvar.ulVal;
      goto LABEL_91;
    case 0x48u:
      p_bVal = pvar.pbVal;
      v37 = WMT_TYPE_GUID;
      ulVal = 16;
      goto LABEL_91;
  }
LABEL_93:
  Element = -1072875854;
LABEL_94:
  v41 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
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
      CallStackContext::TraceFailure(v43, "CMP3MediaSourcePlugin::SetProperty", 2915, Element);
  }
  if ( g_wppLevels )
  {
    v44 = 286;
LABEL_134:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v44, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, v58, Element);
  }
LABEL_136:
  if ( v57 && Element >= 0 )
    Element = 262560;
LABEL_139:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
  CMFPropVariant::Clear(&pvarDest);
  CMFPropVariant::Clear(&pvar);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x1800b8d80  mov     [rsp-8+arg_18], rbx
0x1800b8d85  push    rbp
0x1800b8d86  push    rsi
0x1800b8d87  push    rdi
0x1800b8d88  push    r12
0x1800b8d8a  push    r13
0x1800b8d8c  push    r14
0x1800b8d8e  push    r15
0x1800b8d90  lea     rbp, [rsp-27h]
0x1800b8d95  sub     rsp, 0D0h
0x1800b8d9c  mov     rax, cs:__security_cookie
0x1800b8da3  xor     rax, rsp
0x1800b8da6  mov     [rbp+57h+var_40], rax
0x1800b8daa  xor     eax, eax
0x1800b8dac  mov     [rbp+57h+var_98], rdx
0x1800b8db0  mov     rsi, r8
0x1800b8db3  mov     qword ptr [rbp+57h+pvar+10h], rax
0x1800b8db7  mov     r12, rdx
0x1800b8dba  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x1800b8dbe  mov     r15, rcx
0x1800b8dc1  lea     r13, aCmp3mediasourc_57; "CMP3MediaSourcePlugin::SetProperty"
0x1800b8dc8  xorps   xmm0, xmm0
0x1800b8dcb  lea     rcx, [rbp+57h+var_B0]; this
0x1800b8dcf  xorps   xmm1, xmm1
0x1800b8dd2  xor     r14d, r14d
0x1800b8dd5  mov     rdx, r13; char *
0x1800b8dd8  mov     dword ptr [rbp+57h+var_78], r14d
0x1800b8ddc  mov     r8d, 0AE3h; int
0x1800b8de2  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800b8de6  movups  xmmword ptr [rbp+57h+pvarDest], xmm1
0x1800b8dea  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b8def  lea     rcx, [r15+10h]; lpCriticalSection
0x1800b8df3  call    cs:__imp_EnterCriticalSection
0x1800b8dfa  nop     dword ptr [rax+rax+00h]
0x1800b8dff  mov     rdx, r12; unsigned __int16 *
0x1800b8e02  mov     rcx, r15; this
0x1800b8e05  call    ?DeleteProperty@CMP3MediaSourcePlugin@@UEAAJPEBG@Z; CMP3MediaSourcePlugin::DeleteProperty(ushort const *)
0x1800b8e0a  cmp     eax, 0C00D3E8Dh
0x1800b8e0f  mov     edi, r14d
0x1800b8e12  cmovnz  edi, eax
0x1800b8e15  test    edi, edi
0x1800b8e17  jns     loc_1800B8ED2
0x1800b8e1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8e24  test    rcx, rcx
0x1800b8e27  jnz     short loc_1800B8E70
0x1800b8e29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b8e30  nop     dword ptr [rax+rax+00h]
0x1800b8e35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8e3c  mov     rcx, rax
0x1800b8e3f  test    rax, rax
0x1800b8e42  jz      short loc_1800B8E62
0x1800b8e44  mov     rax, [rax]
0x1800b8e47  mov     edx, 7F0h
0x1800b8e4c  mov     rax, [rax+8]
0x1800b8e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8e55  test    eax, eax
0x1800b8e57  jz      short loc_1800B8E62
0x1800b8e59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8e60  jmp     short loc_1800B8E70
0x1800b8e62  lea     rcx, qword_1801B97E0; this
0x1800b8e69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8e70  cmp     [rcx+8], r14b
0x1800b8e74  jz      short loc_1800B8E97
0x1800b8e76  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b8e7b  cmp     [rax+7CCh], edi
0x1800b8e81  jz      short loc_1800B8E97
0x1800b8e83  mov     r9d, edi; int
0x1800b8e86  mov     r8d, 0AF6h; int
0x1800b8e8c  mov     rdx, r13; char *
0x1800b8e8f  mov     rcx, rax; this
0x1800b8e92  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b8e97  mov     esi, 1
0x1800b8e9c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b8ea3  jb      loc_1800B960F
0x1800b8ea9  mov     edx, 117h
0x1800b8eae  lea     r9, [r15-28h]
0x1800b8eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8eb9  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800b8ec0  mov     dword ptr [rsp+100h+var_E0], edi
0x1800b8ec4  mov     rcx, [rcx+10h]
0x1800b8ec8  call    WPP_SF_qD
0x1800b8ecd  jmp     loc_1800B960F
0x1800b8ed2  mov     rdx, rsi; pvarSrc
0x1800b8ed5  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x1800b8ed9  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800b8ede  mov     edi, eax
0x1800b8ee0  test    eax, eax
0x1800b8ee2  jns     loc_1800B8F7E
0x1800b8ee8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8eef  test    rcx, rcx
0x1800b8ef2  jnz     short loc_1800B8F3B
0x1800b8ef4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b8efb  nop     dword ptr [rax+rax+00h]
0x1800b8f00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8f07  mov     rcx, rax
0x1800b8f0a  test    rax, rax
0x1800b8f0d  jz      short loc_1800B8F2D
0x1800b8f0f  mov     rax, [rax]
0x1800b8f12  mov     edx, 7F0h
0x1800b8f17  mov     rax, [rax+8]
0x1800b8f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8f20  test    eax, eax
0x1800b8f22  jz      short loc_1800B8F2D
0x1800b8f24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8f2b  jmp     short loc_1800B8F3B
0x1800b8f2d  lea     rcx, qword_1801B97E0; this
0x1800b8f34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8f3b  cmp     [rcx+8], r14b
0x1800b8f3f  jz      short loc_1800B8F62
0x1800b8f41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b8f46  cmp     [rax+7CCh], edi
0x1800b8f4c  jz      short loc_1800B8F62
0x1800b8f4e  mov     r9d, edi; int
0x1800b8f51  mov     r8d, 0AFBh; int
0x1800b8f57  mov     rdx, r13; char *
0x1800b8f5a  mov     rcx, rax; this
0x1800b8f5d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b8f62  mov     esi, 1
0x1800b8f67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b8f6e  jb      loc_1800B960F
0x1800b8f74  mov     edx, 118h
0x1800b8f79  jmp     loc_1800B8EAE
0x1800b8f7e  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b8f82  mov     [rbp+57h+var_AC], r14d
0x1800b8f86  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1800b8f8b  mov     esi, 1
0x1800b8f90  mov     r13d, eax
0x1800b8f93  cmp     eax, esi
0x1800b8f95  jbe     loc_1800B921C
0x1800b8f9b  lea     r14, [r15-28h]
0x1800b8f9f  xor     r8d, r8d
0x1800b8fa2  mov     rdx, [r14+198h]
0x1800b8fa9  mov     rax, [rdx+10h]
0x1800b8fad  add     rdx, 10h
0x1800b8fb1  movsxd  rcx, dword ptr [rax+4]
0x1800b8fb5  add     rcx, rdx
0x1800b8fb8  mov     rdx, r12
0x1800b8fbb  mov     rax, [rcx]
0x1800b8fbe  mov     rax, [rax+70h]
0x1800b8fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8fc7  mov     edi, eax
0x1800b8fc9  test    eax, eax
0x1800b8fcb  jns     loc_1800B9069
0x1800b8fd1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8fd8  test    rcx, rcx
0x1800b8fdb  jnz     short loc_1800B9024
0x1800b8fdd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b8fe4  nop     dword ptr [rax+rax+00h]
0x1800b8fe9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b8ff0  mov     rcx, rax
0x1800b8ff3  test    rax, rax
0x1800b8ff6  jz      short loc_1800B9016
0x1800b8ff8  mov     rax, [rax]
0x1800b8ffb  mov     edx, 7F0h
0x1800b9000  mov     rax, [rax+8]
0x1800b9004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9009  test    eax, eax
0x1800b900b  jz      short loc_1800B9016
0x1800b900d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9014  jmp     short loc_1800B9024
0x1800b9016  lea     rcx, qword_1801B97E0; this
0x1800b901d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9024  cmp     byte ptr [rcx+8], 0
0x1800b9028  jz      short loc_1800B904F
0x1800b902a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b902f  cmp     [rax+7CCh], edi
0x1800b9035  jz      short loc_1800B904F
0x1800b9037  mov     r9d, edi; int
0x1800b903a  lea     rdx, aCmp3mediasourc_57; "CMP3MediaSourcePlugin::SetProperty"
0x1800b9041  mov     r8d, 0B05h; int
0x1800b9047  mov     rcx, rax; this
0x1800b904a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b904f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b9056  jb      loc_1800B960F
0x1800b905c  mov     edx, 119h
0x1800b9061  mov     r9, r14
0x1800b9064  jmp     loc_1800B8EB2
0x1800b9069  cmp     edi, esi
0x1800b906b  jnz     loc_1800B921C
0x1800b9071  xorps   xmm0, xmm0
0x1800b9074  lea     r8, [rbp+57h+pvarSrc]; pvarDest
0x1800b9078  xor     eax, eax
0x1800b907a  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b907e  xor     edx, edx; unsigned int
0x1800b9080  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x1800b9084  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x1800b9088  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x1800b908d  mov     edi, eax
0x1800b908f  test    eax, eax
0x1800b9091  jns     loc_1800B914F
0x1800b9097  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b909e  test    rcx, rcx
0x1800b90a1  jnz     short loc_1800B90EA
0x1800b90a3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b90aa  nop     dword ptr [rax+rax+00h]
0x1800b90af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b90b6  mov     rcx, rax
0x1800b90b9  test    rax, rax
0x1800b90bc  jz      short loc_1800B90DC
0x1800b90be  mov     rax, [rax]
0x1800b90c1  mov     edx, 7F0h
0x1800b90c6  mov     rax, [rax+8]
0x1800b90ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b90cf  test    eax, eax
0x1800b90d1  jz      short loc_1800B90DC
0x1800b90d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b90da  jmp     short loc_1800B90EA
0x1800b90dc  lea     rcx, qword_1801B97E0; this
0x1800b90e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b90ea  cmp     byte ptr [rcx+8], 0
0x1800b90ee  jz      short loc_1800B9115
0x1800b90f0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b90f5  cmp     [rax+7CCh], edi
0x1800b90fb  jz      short loc_1800B9115
0x1800b90fd  mov     r9d, edi; int
0x1800b9100  lea     rdx, aCmp3mediasourc_57; "CMP3MediaSourcePlugin::SetProperty"
0x1800b9107  mov     r8d, 0B0Ch; int
0x1800b910d  mov     rcx, rax; this
0x1800b9110  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b9115  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b911c  jb      short loc_1800B9141
0x1800b911e  mov     edx, 11Ah
0x1800b9123  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b912a  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800b9131  mov     r9, r14
0x1800b9134  mov     dword ptr [rsp+100h+var_E0], edi
0x1800b9138  mov     rcx, [rcx+10h]
0x1800b913c  call    WPP_SF_qD
0x1800b9141  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x1800b9145  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800b914a  jmp     loc_1800B960F
0x1800b914f  lea     rcx, [rbp+57h+pvarDest]; pvar
0x1800b9153  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800b9158  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x1800b915c  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x1800b9160  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800b9165  mov     edi, eax
0x1800b9167  test    eax, eax
0x1800b9169  jns     loc_1800B9204
0x1800b916f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b9176  test    rcx, rcx
0x1800b9179  jnz     short loc_1800B91C2
0x1800b917b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b9182  nop     dword ptr [rax+rax+00h]
0x1800b9187  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b918e  mov     rcx, rax
0x1800b9191  test    rax, rax
0x1800b9194  jz      short loc_1800B91B4
0x1800b9196  mov     rax, [rax]
0x1800b9199  mov     edx, 7F0h
0x1800b919e  mov     rax, [rax+8]
0x1800b91a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b91a7  test    eax, eax
0x1800b91a9  jz      short loc_1800B91B4
0x1800b91ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b91b2  jmp     short loc_1800B91C2
0x1800b91b4  lea     rcx, qword_1801B97E0; this
0x1800b91bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b91c2  cmp     byte ptr [rcx+8], 0
0x1800b91c6  jz      short loc_1800B91ED
0x1800b91c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b91cd  cmp     [rax+7CCh], edi
0x1800b91d3  jz      short loc_1800B91ED
0x1800b91d5  mov     r9d, edi; int
0x1800b91d8  lea     rdx, aCmp3mediasourc_57; "CMP3MediaSourcePlugin::SetProperty"
0x1800b91df  mov     r8d, 0B12h; int
0x1800b91e5  mov     rcx, rax; this
0x1800b91e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b91ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b91f4  jb      loc_1800B9141
0x1800b91fa  mov     edx, 11Bh
0x1800b91ff  jmp     loc_1800B9123
0x1800b9204  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b9208  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1800b920d  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x1800b9211  mov     [rbp+57h+var_AC], esi
0x1800b9214  mov     r13d, eax
0x1800b9217  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800b921c  lea     r14, [r15-28h]
0x1800b9220  xor     r12d, r12d
0x1800b9223  mov     [rbp+57h+var_A8], r14
0x1800b9227  cmp     r13d, r12d
0x1800b922a  jbe     loc_1800B95F8
0x1800b9230  lea     rcx, [rbp+57h+pvar]; pvar
0x1800b9234  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800b9239  mov     edi, eax
0x1800b923b  test    eax, eax
0x1800b923d  js      loc_1800B954B
0x1800b9243  lea     r8, [rbp+57h+pvar]; pvarDest
0x1800b9247  mov     edx, r12d; unsigned int
0x1800b924a  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b924e  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x1800b9253  mov     edi, eax
0x1800b9255  test    eax, eax
0x1800b9257  js      loc_1800B94B6
0x1800b925d  movzx   ecx, word ptr [rbp+57h+pvar]
0x1800b9261  cmp     ecx, 14h
0x1800b9264  ja      short loc_1800B92C8
0x1800b9266  jz      loc_1800B932E
0x1800b926c  sub     ecx, 2
  ... truncated ...
```
