# CMP3MediaSourcePlugin::SetProperty(ushort const *,tagPROPVARIANT const *)

- ea: `0x1800b3640`
- end: `0x1800b3ee1`
- name: `?SetProperty@CMP3MediaSourcePlugin@@UEAAJPEBGPEBUtagPROPVARIANT@@@Z`
- size: `2209`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *__hidden this, const unsigned __int16 *, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180025548`
- `0x1800275f0`
- `0x180029a00`
- `0x18006036c`
- `0x180069dec`
- `0x180073b14`
- `0x1800a236c`
- `0x1800b3640`
- `0x1801099f0`
- `0x180150800`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b3e97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b3e97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b36b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b36b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b36e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b37a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b388b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b394b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3a1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3c34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3cc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3d52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3de1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b36e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b37a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b388b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b394b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3a1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3c34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3cc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3d52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b3de1`

## string_xrefs

- `0x1800b3681`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b38e2`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b39a2`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b3a74`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b3c8b`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b3d1a`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b3da9`: `CMP3MediaSourcePlugin::SetProperty`
- `0x1800b3e38`: `CMP3MediaSourcePlugin::SetProperty`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::SetProperty(
        CMP3MediaSourcePlugin *this,
        unsigned __int16 *a2,
        PROPVARIANT *pvarSrc)
{
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  int Element; // edi
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  char *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned int ElementCount; // r13d
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  unsigned int v45; // eax
  unsigned int v46; // r12d
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  enum WMT_ATTR_DATATYPE v53; // r9d
  unsigned int ulVal; // r11d
  const unsigned __int8 *p_bVal; // r14
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  int v73; // [rsp+40h] [rbp-69h]
  _BYTE v74[4]; // [rsp+50h] [rbp-59h] BYREF
  int v75; // [rsp+54h] [rbp-55h]
  char *v76; // [rsp+58h] [rbp-51h]
  unsigned __int64 v77; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 *v78; // [rsp+68h] [rbp-41h]
  PROPVARIANT v79; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int8 v80[4]; // [rsp+88h] [rbp-21h] BYREF
  PROPVARIANT pvarDest; // [rsp+90h] [rbp-19h] BYREF
  PROPVARIANT pvarSrca; // [rsp+A8h] [rbp-1h] BYREF

  v78 = a2;
  *(_DWORD *)v80 = 0;
  memset(&v79, 0, sizeof(v79));
  memset(&pvarDest, 0, sizeof(pvarDest));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v74, "CMP3MediaSourcePlugin::SetProperty", 2787);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v6 = CMP3MediaSourcePlugin::DeleteProperty(this, a2);
  Element = 0;
  if ( v6 != -1072873843 )
    Element = v6;
  if ( Element < 0 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Element )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSourcePlugin::SetProperty", 2806, Element);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v14 = 279;
LABEL_14:
    v15 = (char *)this - 40;
    goto LABEL_15;
  }
  Element = CMFPropVariant::Copy(&pvarDest, pvarSrc, v8, v9);
  if ( Element < 0 )
  {
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != Element )
        CallStackContext::TraceFailure(v21, "CMP3MediaSourcePlugin::SetProperty", 2811, Element);
    }
    if ( !g_wppLevels )
      goto LABEL_139;
    v14 = 280;
    goto LABEL_14;
  }
  v75 = 0;
  ElementCount = CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest);
  if ( ElementCount > 1 )
  {
    v23 = *((_QWORD *)this + 46) + 16LL + *(int *)(*(_QWORD *)(*((_QWORD *)this + 46) + 16LL) + 4LL);
    Element = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD))(*(_QWORD *)v23 + 112LL))(v23, a2, 0);
    if ( Element < 0 )
    {
      v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != Element )
          CallStackContext::TraceFailure(v29, "CMP3MediaSourcePlugin::SetProperty", 2821, Element);
      }
      if ( !g_wppLevels )
        goto LABEL_139;
      v14 = 281;
      v15 = (char *)this - 40;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
        v15,
        Element);
      goto LABEL_139;
    }
    if ( Element == 1 )
    {
      memset(&pvarSrca, 0, sizeof(pvarSrca));
      Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, 0, &pvarSrca);
      if ( Element < 0 )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != Element )
            CallStackContext::TraceFailure(v35, "CMP3MediaSourcePlugin::SetProperty", 2828, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_52;
        v36 = 282;
LABEL_51:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v36,
          &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
          (char *)this - 40,
          Element);
LABEL_52:
        CMFPropVariant::Clear(&pvarSrca);
        goto LABEL_139;
      }
      CMFPropVariant::Clear(&pvarDest);
      Element = CMFPropVariant::Copy(&pvarDest, &pvarSrca, v37, v38);
      if ( Element < 0 )
      {
        v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != Element )
            CallStackContext::TraceFailure(v44, "CMP3MediaSourcePlugin::SetProperty", 2834, Element);
        }
        if ( !g_wppLevels )
          goto LABEL_52;
        v36 = 283;
        goto LABEL_51;
      }
      v45 = CMFPropVariant::GetElementCount((CMFPropVariant *)&pvarDest);
      v75 = 1;
      ElementCount = v45;
      CMFPropVariant::Clear(&pvarSrca);
    }
  }
  v46 = 0;
  v76 = (char *)this - 40;
  while ( 1 )
  {
    if ( ElementCount <= v46 )
    {
      *((_DWORD *)this + 340) = 1;
      goto LABEL_136;
    }
    Element = CMFPropVariant::Clear(&v79);
    if ( Element < 0 )
    {
      v69 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
        CallStackTracing::s_wpInstance = v70;
        if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
        {
          v69 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v69 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v69 + 8) )
      {
        v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
        if ( *((_DWORD *)v71 + 499) != Element )
          CallStackContext::TraceFailure(v71, "CMP3MediaSourcePlugin::SetProperty", 2844, Element);
      }
      if ( g_wppLevels )
      {
        v62 = 284;
        goto LABEL_134;
      }
      goto LABEL_136;
    }
    Element = CMFPropVariant::GetElement((CMFPropVariant *)&pvarDest, v46, &v79);
    if ( Element < 0 )
    {
      v66 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
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
        v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
        if ( *((_DWORD *)v68 + 499) != Element )
          CallStackContext::TraceFailure(v68, "CMP3MediaSourcePlugin::SetProperty", 2849, Element);
      }
      if ( g_wppLevels )
      {
        v62 = 285;
        goto LABEL_134;
      }
      goto LABEL_136;
    }
    if ( v79.vt > 0x14u )
      break;
    switch ( v79.vt )
    {
      case 0x14u:
        goto LABEL_89;
      case 2u:
        goto LABEL_79;
      case 3u:
        goto LABEL_77;
    }
    if ( v79.vt != 8 )
    {
      switch ( v79.vt )
      {
        case 0xBu:
          p_bVal = v80;
          v53 = WMT_TYPE_BOOL;
          *(_DWORD *)v80 = v79.iVal == 0xFFFF;
          ulVal = 4;
          goto LABEL_91;
        case 0x12u:
LABEL_79:
          v53 = WMT_TYPE_WORD;
          ulVal = 2;
          break;
        case 0x13u:
LABEL_77:
          v53 = WMT_TYPE_DWORD;
          ulVal = 4;
          break;
        default:
          goto LABEL_93;
      }
LABEL_90:
      p_bVal = &v79.bVal;
      goto LABEL_91;
    }
LABEL_87:
    p_bVal = v79.pbVal;
    v77 = 0;
    Element = StringCbLengthW(v79.bstrVal, 0xFFFFFFFE, &v77);
    if ( Element < 0 )
      goto LABEL_94;
    ulVal = v77;
    v53 = WMT_TYPE_STRING;
LABEL_91:
    Element = CWMHeaderInfoIndexBase::AddIndexedAttribute(
                (CWMHeaderInfoIndexBase *)(*((_QWORD *)this + 46)
                                         + 16LL
                                         + *(int *)(*(_QWORD *)(*((_QWORD *)this + 46) + 16LL) + 8LL)),
                0,
                v78,
                v53,
                0,
                p_bVal,
                ulVal,
                0,
                v73);
    if ( Element < 0 )
    {
      v63 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57, v58);
        CallStackTracing::s_wpInstance = v64;
        if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
        {
          v63 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v63 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v63 + 8) )
      {
        v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
        if ( *((_DWORD *)v65 + 499) != Element )
          CallStackContext::TraceFailure(v65, "CMP3MediaSourcePlugin::SetProperty", 2930, Element);
      }
      if ( g_wppLevels )
      {
        v62 = 287;
        goto LABEL_134;
      }
      goto LABEL_136;
    }
    ++v46;
  }
  switch ( v79.vt )
  {
    case 0x15u:
      goto LABEL_89;
    case 0x1Fu:
      goto LABEL_87;
    case 0x40u:
LABEL_89:
      v53 = WMT_TYPE_QWORD;
      ulVal = 8;
      goto LABEL_90;
    case 0x41u:
      p_bVal = v79.bstrblobVal.pData;
      v53 = WMT_TYPE_BINARY;
      ulVal = v79.ulVal;
      goto LABEL_91;
    case 0x48u:
      p_bVal = v79.pbVal;
      v53 = WMT_TYPE_GUID;
      ulVal = 16;
      goto LABEL_91;
  }
LABEL_93:
  Element = -1072875854;
LABEL_94:
  v59 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51, v52);
    CallStackTracing::s_wpInstance = v60;
    if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
    {
      v59 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v59 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v59 + 8) )
  {
    v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
    if ( *((_DWORD *)v61 + 499) != Element )
      CallStackContext::TraceFailure(v61, "CMP3MediaSourcePlugin::SetProperty", 2915, Element);
  }
  if ( g_wppLevels )
  {
    v62 = 286;
LABEL_134:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v62, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, v76, Element);
  }
LABEL_136:
  if ( v75 && Element >= 0 )
    Element = 262560;
LABEL_139:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v74);
  CMFPropVariant::Clear(&pvarDest);
  CMFPropVariant::Clear(&v79);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x1800b3640  mov     [rsp-8+arg_18], rbx
0x1800b3645  push    rbp
0x1800b3646  push    rsi
0x1800b3647  push    rdi
0x1800b3648  push    r12
0x1800b364a  push    r13
0x1800b364c  push    r14
0x1800b364e  push    r15
0x1800b3650  lea     rbp, [rsp-27h]
0x1800b3655  sub     rsp, 0D0h
0x1800b365c  mov     rax, cs:__security_cookie
0x1800b3663  xor     rax, rsp
0x1800b3666  mov     [rbp+57h+var_40], rax
0x1800b366a  xor     eax, eax
0x1800b366c  mov     [rbp+57h+var_98], rdx
0x1800b3670  mov     rsi, r8
0x1800b3673  mov     qword ptr [rbp+57h+var_90+10h], rax
0x1800b3677  mov     r12, rdx
0x1800b367a  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x1800b367e  mov     r15, rcx
0x1800b3681  lea     r13, aCmp3mediasourc_57; "CMP3MediaSourcePlugin::SetProperty"
0x1800b3688  xorps   xmm0, xmm0
0x1800b368b  lea     rcx, [rbp+57h+var_B0]; this
0x1800b368f  xorps   xmm1, xmm1
0x1800b3692  xor     r14d, r14d
0x1800b3695  mov     rdx, r13; char *
0x1800b3698  mov     dword ptr [rbp+57h+var_78], r14d
0x1800b369c  mov     r8d, 0AE3h; int
0x1800b36a2  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1800b36a6  movups  xmmword ptr [rbp+57h+pvarDest], xmm1
0x1800b36aa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b36af  lea     rcx, [r15+10h]; lpCriticalSection
0x1800b36b3  call    cs:__imp_EnterCriticalSection
0x1800b36b9  mov     rdx, r12; unsigned __int16 *
0x1800b36bc  mov     rcx, r15; this
0x1800b36bf  call    ?DeleteProperty@CMP3MediaSourcePlugin@@UEAAJPEBG@Z; CMP3MediaSourcePlugin::DeleteProperty(ushort const *)
0x1800b36c4  cmp     eax, 0C00D3E8Dh
0x1800b36c9  mov     edi, r14d
0x1800b36cc  cmovnz  edi, eax
0x1800b36cf  test    edi, edi
0x1800b36d1  jns     loc_1800B3786
0x1800b36d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b36de  test    rcx, rcx
0x1800b36e1  jnz     short loc_1800B3724
0x1800b36e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b36e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b36f0  mov     rcx, rax
0x1800b36f3  test    rax, rax
0x1800b36f6  jz      short loc_1800B3716
0x1800b36f8  mov     rax, [rax]
0x1800b36fb  mov     edx, 7F0h
0x1800b3700  mov     rax, [rax+8]
0x1800b3704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3709  test    eax, eax
0x1800b370b  jz      short loc_1800B3716
0x1800b370d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3714  jmp     short loc_1800B3724
0x1800b3716  lea     rcx, qword_1801B07E0; this
0x1800b371d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3724  cmp     [rcx+8], r14b
0x1800b3728  jz      short loc_1800B374B
0x1800b372a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b372f  cmp     [rax+7CCh], edi
0x1800b3735  jz      short loc_1800B374B
0x1800b3737  mov     r9d, edi; int
0x1800b373a  mov     r8d, 0AF6h; int
0x1800b3740  mov     rdx, r13; char *
0x1800b3743  mov     rcx, rax; this
0x1800b3746  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b374b  mov     esi, 1
0x1800b3750  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b3757  jb      loc_1800B3E93
0x1800b375d  mov     edx, 117h
0x1800b3762  lea     r9, [r15-28h]
0x1800b3766  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b376d  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800b3774  mov     dword ptr [rsp+100h+var_E0], edi
0x1800b3778  mov     rcx, [rcx+10h]
0x1800b377c  call    WPP_SF_qD
0x1800b3781  jmp     loc_1800B3E93
0x1800b3786  mov     rdx, rsi; pvarSrc
0x1800b3789  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x1800b378d  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800b3792  mov     edi, eax
0x1800b3794  test    eax, eax
0x1800b3796  jns     loc_1800B382C
0x1800b379c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b37a3  test    rcx, rcx
0x1800b37a6  jnz     short loc_1800B37E9
0x1800b37a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b37ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b37b5  mov     rcx, rax
0x1800b37b8  test    rax, rax
0x1800b37bb  jz      short loc_1800B37DB
0x1800b37bd  mov     rax, [rax]
0x1800b37c0  mov     edx, 7F0h
0x1800b37c5  mov     rax, [rax+8]
0x1800b37c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b37ce  test    eax, eax
0x1800b37d0  jz      short loc_1800B37DB
0x1800b37d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b37d9  jmp     short loc_1800B37E9
0x1800b37db  lea     rcx, qword_1801B07E0; this
0x1800b37e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b37e9  cmp     [rcx+8], r14b
0x1800b37ed  jz      short loc_1800B3810
0x1800b37ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b37f4  cmp     [rax+7CCh], edi
0x1800b37fa  jz      short loc_1800B3810
0x1800b37fc  mov     r9d, edi; int
0x1800b37ff  mov     r8d, 0AFBh; int
0x1800b3805  mov     rdx, r13; char *
0x1800b3808  mov     rcx, rax; this
0x1800b380b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3810  mov     esi, 1
0x1800b3815  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b381c  jb      loc_1800B3E93
0x1800b3822  mov     edx, 118h
0x1800b3827  jmp     loc_1800B3762
0x1800b382c  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b3830  mov     [rbp+57h+var_AC], r14d
0x1800b3834  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1800b3839  mov     esi, 1
0x1800b383e  mov     r13d, eax
0x1800b3841  cmp     eax, esi
0x1800b3843  jbe     loc_1800B3AB8
0x1800b3849  lea     r14, [r15-28h]
0x1800b384d  xor     r8d, r8d
0x1800b3850  mov     rdx, [r14+198h]
0x1800b3857  mov     rax, [rdx+10h]
0x1800b385b  add     rdx, 10h
0x1800b385f  movsxd  rcx, dword ptr [rax+4]
0x1800b3863  add     rcx, rdx
0x1800b3866  mov     rdx, r12
0x1800b3869  mov     rax, [rcx]
0x1800b386c  mov     rax, [rax+70h]
0x1800b3870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3875  mov     edi, eax
0x1800b3877  test    eax, eax
0x1800b3879  jns     loc_1800B3911
0x1800b387f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3886  test    rcx, rcx
0x1800b3889  jnz     short loc_1800B38CC
0x1800b388b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3891  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3898  mov     rcx, rax
0x1800b389b  test    rax, rax
0x1800b389e  jz      short loc_1800B38BE
0x1800b38a0  mov     rax, [rax]
0x1800b38a3  mov     edx, 7F0h
0x1800b38a8  mov     rax, [rax+8]
0x1800b38ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b38b1  test    eax, eax
0x1800b38b3  jz      short loc_1800B38BE
0x1800b38b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b38bc  jmp     short loc_1800B38CC
0x1800b38be  lea     rcx, qword_1801B07E0; this
0x1800b38c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b38cc  cmp     byte ptr [rcx+8], 0
0x1800b38d0  jz      short loc_1800B38F7
0x1800b38d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b38d7  cmp     [rax+7CCh], edi
0x1800b38dd  jz      short loc_1800B38F7
0x1800b38df  mov     r9d, edi; int
0x1800b38e2  lea     rdx, aCmp3mediasourc_57; "CMP3MediaSourcePlugin::SetProperty"
0x1800b38e9  mov     r8d, 0B05h; int
0x1800b38ef  mov     rcx, rax; this
0x1800b38f2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b38f7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b38fe  jb      loc_1800B3E93
0x1800b3904  mov     edx, 119h
0x1800b3909  mov     r9, r14
0x1800b390c  jmp     loc_1800B3766
0x1800b3911  cmp     edi, esi
0x1800b3913  jnz     loc_1800B3AB8
0x1800b3919  xorps   xmm0, xmm0
0x1800b391c  lea     r8, [rbp+57h+pvarSrc]; pvarDest
0x1800b3920  xor     eax, eax
0x1800b3922  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b3926  xor     edx, edx; unsigned int
0x1800b3928  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x1800b392c  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x1800b3930  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x1800b3935  mov     edi, eax
0x1800b3937  test    eax, eax
0x1800b3939  jns     loc_1800B39F1
0x1800b393f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3946  test    rcx, rcx
0x1800b3949  jnz     short loc_1800B398C
0x1800b394b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3951  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3958  mov     rcx, rax
0x1800b395b  test    rax, rax
0x1800b395e  jz      short loc_1800B397E
0x1800b3960  mov     rax, [rax]
0x1800b3963  mov     edx, 7F0h
0x1800b3968  mov     rax, [rax+8]
0x1800b396c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3971  test    eax, eax
0x1800b3973  jz      short loc_1800B397E
0x1800b3975  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b397c  jmp     short loc_1800B398C
0x1800b397e  lea     rcx, qword_1801B07E0; this
0x1800b3985  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b398c  cmp     byte ptr [rcx+8], 0
0x1800b3990  jz      short loc_1800B39B7
0x1800b3992  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3997  cmp     [rax+7CCh], edi
0x1800b399d  jz      short loc_1800B39B7
0x1800b399f  mov     r9d, edi; int
0x1800b39a2  lea     rdx, aCmp3mediasourc_57; "CMP3MediaSourcePlugin::SetProperty"
0x1800b39a9  mov     r8d, 0B0Ch; int
0x1800b39af  mov     rcx, rax; this
0x1800b39b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b39b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b39be  jb      short loc_1800B39E3
0x1800b39c0  mov     edx, 11Ah
0x1800b39c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b39cc  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800b39d3  mov     r9, r14
0x1800b39d6  mov     dword ptr [rsp+100h+var_E0], edi
0x1800b39da  mov     rcx, [rcx+10h]
0x1800b39de  call    WPP_SF_qD
0x1800b39e3  lea     rcx, [rbp+57h+pvarSrc]; this
0x1800b39e7  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800b39ec  jmp     loc_1800B3E93
0x1800b39f1  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b39f5  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800b39fa  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x1800b39fe  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x1800b3a02  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800b3a07  mov     edi, eax
0x1800b3a09  test    eax, eax
0x1800b3a0b  jns     loc_1800B3AA0
0x1800b3a11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3a18  test    rcx, rcx
0x1800b3a1b  jnz     short loc_1800B3A5E
0x1800b3a1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b3a23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3a2a  mov     rcx, rax
0x1800b3a2d  test    rax, rax
0x1800b3a30  jz      short loc_1800B3A50
0x1800b3a32  mov     rax, [rax]
0x1800b3a35  mov     edx, 7F0h
0x1800b3a3a  mov     rax, [rax+8]
0x1800b3a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3a43  test    eax, eax
0x1800b3a45  jz      short loc_1800B3A50
0x1800b3a47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3a4e  jmp     short loc_1800B3A5E
0x1800b3a50  lea     rcx, qword_1801B07E0; this
0x1800b3a57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b3a5e  cmp     byte ptr [rcx+8], 0
0x1800b3a62  jz      short loc_1800B3A89
0x1800b3a64  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b3a69  cmp     [rax+7CCh], edi
0x1800b3a6f  jz      short loc_1800B3A89
0x1800b3a71  mov     r9d, edi; int
0x1800b3a74  lea     rdx, aCmp3mediasourc_57; "CMP3MediaSourcePlugin::SetProperty"
0x1800b3a7b  mov     r8d, 0B12h; int
0x1800b3a81  mov     rcx, rax; this
0x1800b3a84  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b3a89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800b3a90  jb      loc_1800B39E3
0x1800b3a96  mov     edx, 11Bh
0x1800b3a9b  jmp     loc_1800B39C5
0x1800b3aa0  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b3aa4  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x1800b3aa9  lea     rcx, [rbp+57h+pvarSrc]; this
0x1800b3aad  mov     [rbp+57h+var_AC], esi
0x1800b3ab0  mov     r13d, eax
0x1800b3ab3  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800b3ab8  lea     r14, [r15-28h]
0x1800b3abc  xor     r12d, r12d
0x1800b3abf  mov     [rbp+57h+var_A8], r14
0x1800b3ac3  cmp     r13d, r12d
0x1800b3ac6  jbe     loc_1800B3E7C
0x1800b3acc  lea     rcx, [rbp+57h+var_90]; this
0x1800b3ad0  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800b3ad5  mov     edi, eax
0x1800b3ad7  test    eax, eax
0x1800b3ad9  js      loc_1800B3DD5
0x1800b3adf  lea     r8, [rbp+57h+var_90]; pvarDest
0x1800b3ae3  mov     edx, r12d; unsigned int
0x1800b3ae6  lea     rcx, [rbp+57h+pvarDest]; this
0x1800b3aea  call    ?GetElement@CMFPropVariant@@QEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElement(ulong,tagPROPVARIANT *)
0x1800b3aef  mov     edi, eax
0x1800b3af1  test    eax, eax
0x1800b3af3  js      loc_1800B3D46
0x1800b3af9  movzx   ecx, word ptr [rbp+57h+var_90]
0x1800b3afd  cmp     ecx, 14h
0x1800b3b00  ja      short loc_1800B3B64
0x1800b3b02  jz      loc_1800B3BCA
0x1800b3b08  sub     ecx, 2
0x1800b3b0b  jz      short loc_1800B3B58
0x1800b3b0d  sub     ecx, esi
0x1800b3b0f  jz      short loc_1800B3B2C
0x1800b3b11  sub     ecx, 5
0x1800b3b14  jz      loc_1800B3B9E
0x1800b3b1a  sub     ecx, 3
  ... truncated ...
```
