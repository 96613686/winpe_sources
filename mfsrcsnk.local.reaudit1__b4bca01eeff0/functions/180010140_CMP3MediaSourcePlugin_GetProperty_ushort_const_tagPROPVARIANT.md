# CMP3MediaSourcePlugin::GetProperty(ushort const *,tagPROPVARIANT *)

- ea: `0x180010140`
- end: `0x180010fbc`
- name: `?GetProperty@CMP3MediaSourcePlugin@@UEAAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `3708`
- prototype: `int(CMP3MediaSourcePlugin *__hidden this, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callees

- `0x180005cf4`
- `0x180010140`
- `0x180010fc4`
- `0x1800111d0`
- `0x180011940`
- `0x180013110`
- `0x180013f10`
- `0x180015410`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180077708`
- `0x180079680`
- `0x1800dc9ac`
- `0x180110a88`
- `0x180110ad4`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800104ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800104ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010450`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800105a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800105ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010631`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010673`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800106fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010740`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800107bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010803`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010845`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010887`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800108ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010450`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800105a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800105ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010631`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010673`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800106fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010740`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800107bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010803`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010845`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010887`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800108ce`

## string_xrefs

- `0x180010187`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010917`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010948`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010979`: `CMP3MediaSourcePlugin::GetProperty`
- `0x1800109a7`: `CMP3MediaSourcePlugin::GetProperty`
- `0x1800109d8`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010a06`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010a34`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010a62`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010a90`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010abe`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010aec`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010b1a`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010b48`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180010b76`: `CMP3MediaSourcePlugin::GetProperty`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::GetProperty(
        CMP3MediaSourcePlugin *this,
        const unsigned __int16 *a2,
        struct tagPROPVARIANT *a3)
{
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int IndexedAttributeIndices; // edi
  unsigned __int16 *v16; // r15
  __int64 v17; // rdx
  __int64 v18; // rcx
  void *v19; // r14
  unsigned __int16 i; // r12
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned __int16 v26; // dx
  CallStackTracing *v27; // rcx
  __int64 v28; // rdx
  CallStackTracing *v29; // rcx
  char *v30; // r13
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  BYTE *pData; // xmm1_8
  CallStackTracing *v35; // rcx
  wchar_t *v36; // rax
  CallStackTracing *v37; // rax
  wchar_t *v38; // rax
  CallStackTracing *v39; // rax
  wchar_t *v40; // rax
  CallStackTracing *v41; // rax
  wchar_t *v42; // rax
  CallStackTracing *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  CallStackTracing *v48; // rax
  CallStackTracing *v49; // rax
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  struct CallStackContext *v61; // rax
  struct CallStackContext *v62; // rax
  struct CallStackContext *v63; // rax
  struct CallStackContext *v64; // rax
  struct CallStackContext *v65; // rax
  struct CallStackContext *v66; // rax
  struct CallStackContext *v67; // rax
  struct CallStackContext *v68; // rax
  struct CallStackContext *v69; // rax
  struct CallStackContext *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // rdx
  int v75; // [rsp+30h] [rbp-69h]
  int v76; // [rsp+30h] [rbp-69h]
  int v77; // [rsp+48h] [rbp-51h]
  int v78; // [rsp+48h] [rbp-51h]
  const unsigned __int16 *v79; // [rsp+50h] [rbp-49h]
  const unsigned __int16 *v80; // [rsp+50h] [rbp-49h]
  unsigned __int16 v81; // [rsp+60h] [rbp-39h] BYREF
  char *v82; // [rsp+68h] [rbp-31h]
  unsigned __int16 v83[2]; // [rsp+70h] [rbp-29h] BYREF
  WMT_ATTR_DATATYPE v84; // [rsp+74h] [rbp-25h] BYREF
  unsigned __int16 *v85; // [rsp+78h] [rbp-21h]
  unsigned int v86[2]; // [rsp+80h] [rbp-19h] BYREF
  PROPVARIANT pvarSrc; // [rsp+88h] [rbp-11h] BYREF
  PROPVARIANT pvarDest; // [rsp+A0h] [rbp+7h] BYREF

  v5 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v5 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
    v8 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v8 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v9 = 2 * v8;
      *((_QWORD *)ThreadRelativeContext + v9) = "CMP3MediaSourcePlugin::GetProperty";
      *((_DWORD *)ThreadRelativeContext + 2 * v9 + 2) = 2955;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  v84 = WMT_TYPE_BINARY;
  v83[0] = 0;
  v81 = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v86[0] = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v82 = (char *)this - 40;
  if ( !a2 )
  {
    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
    IndexedAttributeIndices = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
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
      v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
      if ( *((_DWORD *)v58 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v58, "CMP3MediaSourcePlugin::GetProperty", 2974, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v72 = 289;
LABEL_119:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v72,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      (char *)this - 40,
      IndexedAttributeIndices);
    goto LABEL_39;
  }
  if ( !a3 )
  {
    v38 = (wchar_t *)CallStackTracing::s_wpInstance;
    IndexedAttributeIndices = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
      CallStackTracing::s_wpInstance = v39;
      if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
      {
        v38 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v38 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v38 + 8) )
    {
      v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
      if ( *((_DWORD *)v59 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v59, "CMP3MediaSourcePlugin::GetProperty", 2975, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v72 = 290;
    goto LABEL_119;
  }
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  IndexedAttributeIndices = CWMHeaderInfoIndexBase::GetIndexedAttributeIndices(
                              (CWMHeaderInfoIndexBase *)(*((_QWORD *)this + 46)
                                                       + 16LL
                                                       + *(int *)(*(_QWORD *)(*((_QWORD *)this + 46) + 16LL) + 8LL)),
                              (unsigned __int16)*((_QWORD *)this + 46) + 16,
                              a2,
                              v83,
                              0,
                              &v81,
                              v75);
  if ( IndexedAttributeIndices < 0 )
  {
    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, v13);
      CallStackTracing::s_wpInstance = v41;
      if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v40 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v40 + 8) )
    {
      v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
      if ( *((_DWORD *)v60 + 499) != IndexedAttributeIndices )
        CallStackContext::TraceFailure(v60, "CMP3MediaSourcePlugin::GetProperty", 2988, IndexedAttributeIndices);
    }
    if ( !g_wppLevels )
      goto LABEL_39;
    v72 = 291;
    goto LABEL_119;
  }
  if ( !v81 )
  {
    IndexedAttributeIndices = -1072873843;
LABEL_39:
    operator delete(0);
    operator delete(0);
    goto LABEL_37;
  }
  v16 = (unsigned __int16 *)operator new[](saturated_mul(v81, 2u));
  if ( !v16 )
  {
    v35 = CallStackTracing::s_wpInstance;
    IndexedAttributeIndices = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v35 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v35 + 8) )
    {
      v61 = CallStackTracing::GetThreadRelativeContext(v35);
      if ( *((_DWORD *)v61 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v61, "CMP3MediaSourcePlugin::GetProperty", 3003, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_44;
    v73 = 292;
    goto LABEL_131;
  }
  IndexedAttributeIndices = CWMHeaderInfoIndexBase::GetIndexedAttributeIndices(
                              (CWMHeaderInfoIndexBase *)(*((_QWORD *)this + 46)
                                                       + 16LL
                                                       + *(int *)(*(_QWORD *)(*((_QWORD *)this + 46) + 16LL) + 8LL)),
                              (unsigned __int16)*((_QWORD *)this + 46) + 16,
                              a2,
                              v83,
                              v16,
                              &v81,
                              v76);
  if ( IndexedAttributeIndices < 0 )
  {
    v42 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v18, v17);
      CallStackTracing::s_wpInstance = v43;
      if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
      {
        v42 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v42 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v42 + 8) )
    {
      v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
      if ( *((_DWORD *)v62 + 499) != IndexedAttributeIndices )
        CallStackContext::TraceFailure(v62, "CMP3MediaSourcePlugin::GetProperty", 3016, IndexedAttributeIndices);
    }
    if ( !g_wppLevels )
      goto LABEL_44;
    v73 = 293;
LABEL_131:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v73,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      (char *)this - 40,
      IndexedAttributeIndices);
LABEL_44:
    operator delete(v16);
    operator delete(0);
    goto LABEL_37;
  }
  v19 = 0;
  for ( i = 0; ; ++i )
  {
    if ( v81 <= i )
    {
      v30 = v82;
      goto LABEL_33;
    }
    v21 = *((_QWORD *)this + 46);
    memset(&pvarSrc, 0, sizeof(pvarSrc));
    v22 = *(_QWORD *)(v21 + 16);
    v85 = &v16[i];
    IndexedAttributeIndices = CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(
                                (CWMHeaderInfoIndexBase *)(v21 + *(int *)(v22 + 8) + 16LL),
                                0,
                                *v85,
                                0,
                                0,
                                &v84,
                                0,
                                0,
                                v86,
                                v77,
                                v79);
    if ( IndexedAttributeIndices < 0 )
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v29 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v70 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( *((_DWORD *)v70 + 499) != IndexedAttributeIndices )
          CallStackContext::TraceFailure(v70, "CMP3MediaSourcePlugin::GetProperty", 3037, IndexedAttributeIndices);
      }
      v30 = v82;
      if ( !g_wppLevels )
        goto LABEL_28;
      v74 = 294;
      goto LABEL_178;
    }
    operator delete(v19);
    v19 = operator new[](v86[0]);
    if ( !v19 )
    {
      v56 = (wchar_t *)CallStackTracing::s_wpInstance;
      IndexedAttributeIndices = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
        CallStackTracing::s_wpInstance = v57;
        if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        {
          v56 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v56 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
        if ( *((_DWORD *)v69 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v69, "CMP3MediaSourcePlugin::GetProperty", 3044, -2147024882);
      }
      v30 = v82;
      if ( !g_wppLevels )
        goto LABEL_28;
      v74 = 295;
      goto LABEL_178;
    }
    IndexedAttributeIndices = CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(
                                (CWMHeaderInfoIndexBase *)(*((_QWORD *)this + 46)
                                                         + 16LL
                                                         + *(int *)(*(_QWORD *)(*((_QWORD *)this + 46) + 16LL) + 8LL)),
                                0,
                                *v85,
                                0,
                                0,
                                0,
                                0,
                                (unsigned __int8 *)v19,
                                v86,
                                v78,
                                v80);
    if ( IndexedAttributeIndices < 0 )
    {
      v54 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
        CallStackTracing::s_wpInstance = v55;
        if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
        {
          v54 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v54 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v54 + 8) )
      {
        v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
        if ( *((_DWORD *)v68 + 499) != IndexedAttributeIndices )
          CallStackContext::TraceFailure(v68, "CMP3MediaSourcePlugin::GetProperty", 3056, IndexedAttributeIndices);
      }
      v30 = v82;
      if ( !g_wppLevels )
        goto LABEL_28;
      v74 = 296;
      goto LABEL_178;
    }
    if ( v84 != WMT_TYPE_STRING )
    {
      switch ( v84 )
      {
        case WMT_TYPE_DWORD:
          v26 = 19;
          goto LABEL_20;
        case WMT_TYPE_BINARY:
          v26 = 65;
          goto LABEL_20;
        case WMT_TYPE_BOOL:
          v26 = 11;
          goto LABEL_20;
        case WMT_TYPE_QWORD:
          v26 = 21;
          goto LABEL_20;
        case WMT_TYPE_WORD:
          v26 = 18;
          goto LABEL_20;
        case WMT_TYPE_GUID:
          v26 = 72;
          goto LABEL_20;
        default:
          IndexedAttributeIndices = -1072873844;
          if ( !CallStackTracing::s_wpInstance )
          {
            v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, v24);
            CallStackTracing::s_wpInstance = v48;
            if ( !v48
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          v27 = CallStackTracing::s_wpInstance;
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v63 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v63 + 499) != -1072873844 )
              CallStackContext::TraceFailure(v63, "CMP3MediaSourcePlugin::GetProperty", 3093, -1072873844);
          }
          v30 = v82;
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              297,
              &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
              v82,
              -1072873844);
          goto LABEL_70;
      }
    }
    v26 = 31;
LABEL_20:
    IndexedAttributeIndices = CMFPropVariantConvert::CreateFromData((__int64)&pvarSrc, v26, (char *)v19, v86[0]);
    if ( IndexedAttributeIndices < 0 )
      break;
    if ( v81 <= 1u )
    {
      IndexedAttributeIndices = CMFPropVariant::Copy(&pvarDest, &pvarSrc);
      if ( IndexedAttributeIndices >= 0 )
        goto LABEL_23;
      v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v66 + 499) != IndexedAttributeIndices )
          CallStackContext::TraceFailure(v66, "CMP3MediaSourcePlugin::GetProperty", 3122, IndexedAttributeIndices);
      }
      v30 = v82;
      if ( !g_wppLevels )
      {
LABEL_28:
        CMFPropVariant::Clear(&pvarSrc);
        goto LABEL_29;
      }
      v74 = 301;
LABEL_178:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v74,
        &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
        v30,
        IndexedAttributeIndices);
      goto LABEL_28;
    }
    if ( pvarDest.vt )
    {
      if ( ((pvarDest.vt ^ pvarSrc.vt) & 0xFFF) != 0 )
      {
        IndexedAttributeIndices = CMFPropVariant::ConvertToVariantArray((CMFPropVariant *)&pvarDest);
        if ( IndexedAttributeIndices < 0 )
        {
          v50 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
            CallStackTracing::s_wpInstance = v51;
            if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
            {
              v50 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v50 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v50 + 8) )
          {
            v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
            if ( *((_DWORD *)v64 + 499) != IndexedAttributeIndices )
              CallStackContext::TraceFailure(v64, "CMP3MediaSourcePlugin::GetProperty", 3107, IndexedAttributeIndices);
          }
          v30 = v82;
          if ( !g_wppLevels )
            goto LABEL_28;
          v74 = 299;
          goto LABEL_178;
        }
      }
    }
    IndexedAttributeIndices = CMFPropVariant::AppendElement((CMFPropVariant *)&pvarDest, &pvarSrc);
    if ( IndexedAttributeIndices < 0 )
    {
      v46 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
        CallStackTracing::s_wpInstance = v47;
        if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
        {
          v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
        if ( *((_DWORD *)v65 + 499) != IndexedAttributeIndices )
          CallStackContext::TraceFailure(v65, "CMP3MediaSourcePlugin::GetProperty", 3114, IndexedAttributeIndices);
      }
      v30 = v82;
      if ( !g_wppLevels )
        goto LABEL_28;
      v74 = 300;
      goto LABEL_178;
    }
LABEL_23:
    CMFPropVariant::Clear(&pvarSrc);
  }
  v30 = v82;
LABEL_70:
  if ( !CallStackTracing::s_wpInstance )
  {
    v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v27, v24);
    CallStackTracing::s_wpInstance = v49;
    if ( !v49 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v67 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v67 + 499) != IndexedAttributeIndices )
      CallStackContext::TraceFailure(v67, "CMP3MediaSourcePlugin::GetProperty", 3096, IndexedAttributeIndices);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      298,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      v30,
      IndexedAttributeIndices);
  CMFPropVariant::Clear(&pvarSrc);
LABEL_33:
  if ( IndexedAttributeIndices >= 0 )
  {
    operator delete(v16);
    operator delete(v19);
    pData = pvarDest.bstrblobVal.pData;
    *(_OWORD *)&a3->vt = *(_OWORD *)&pvarDest.vt;
    pvarDest.vt = 0;
    a3->bstrblobVal.pData = pData;
    goto LABEL_37;
  }
LABEL_29:
  v31 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
    v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
    if ( *((_DWORD *)v71 + 499) != IndexedAttributeIndices )
      CallStackContext::TraceFailure(v71, "CMP3MediaSourcePlugin::GetProperty", 3126, IndexedAttributeIndices);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      303,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      v30,
      IndexedAttributeIndices);
  operator delete(v16);
  operator delete(v19);
LABEL_37:
  LeaveCriticalSection(v10);
  CMFPropVariant::Clear(&pvarDest);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
  return (unsigned int)IndexedAttributeIndices;
}

```

## disassembly

```asm
0x180010140  mov     [rsp-8+arg_18], rbx
0x180010145  push    rbp
0x180010146  push    rsi
0x180010147  push    rdi
0x180010148  push    r12
0x18001014a  push    r13
0x18001014c  push    r14
0x18001014e  push    r15
0x180010150  lea     rbp, [rsp-27h]
0x180010155  sub     rsp, 0C0h
0x18001015c  mov     rax, cs:__security_cookie
0x180010163  xor     rax, rsp
0x180010166  mov     [rbp+57h+var_38], rax
0x18001016a  mov     r13, rcx
0x18001016d  mov     rsi, r8
0x180010170  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180010177  mov     r14, rdx
0x18001017a  test    rcx, rcx
0x18001017d  jz      loc_180010482
0x180010183  cmp     byte ptr [rcx+8], 0
0x180010187  lea     rbx, aCmp3mediasourc_5; "CMP3MediaSourcePlugin::GetProperty"
0x18001018e  jz      short loc_1800101B8
0x180010190  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010195  mov     ecx, [rax+7C4h]
0x18001019b  cmp     ecx, [rax+7C8h]
0x1800101a1  jnb     short loc_1800101B2
0x1800101a3  add     rcx, rcx
0x1800101a6  mov     [rax+rcx*8], rbx
0x1800101aa  mov     dword ptr [rax+rcx*8+8], 0B8Bh
0x1800101b2  inc     dword ptr [rax+7C4h]
0x1800101b8  xor     r15d, r15d
0x1800101bb  mov     [rbp+57h+var_7C], 2
0x1800101c2  xorps   xmm0, xmm0
0x1800101c5  mov     [rbp+57h+var_80], r15w
0x1800101ca  xor     eax, eax
0x1800101cc  mov     [rbp+57h+var_90], r15w
0x1800101d1  lea     rbx, [r13+10h]
0x1800101d5  mov     [rbp+57h+var_70], r15d
0x1800101d9  mov     rcx, rbx; lpCriticalSection
0x1800101dc  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x1800101e0  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x1800101e4  call    cs:__imp_EnterCriticalSection
0x1800101eb  nop     dword ptr [rax+rax+00h]
0x1800101f0  lea     r12, [r13-28h]
0x1800101f4  mov     [rbp+57h+var_88], r12
0x1800101f8  test    r14, r14
0x1800101fb  jz      loc_180010593
0x180010201  test    rsi, rsi
0x180010204  jz      loc_1800105DA
0x18001020a  xor     eax, eax
0x18001020c  lea     r9, [rbp+57h+var_80]; unsigned __int16 *
0x180010210  xorps   xmm0, xmm0
0x180010213  mov     r8, r14; unsigned __int16 *
0x180010216  movups  xmmword ptr [rsi], xmm0
0x180010219  mov     [rsi+10h], rax
0x18001021d  mov     rdx, [r12+198h]
0x180010225  mov     rax, [rdx+10h]
0x180010229  add     rdx, 10h; unsigned __int16
0x18001022d  movsxd  rcx, dword ptr [rax+8]
0x180010231  lea     rax, [rbp+57h+var_90]
0x180010235  mov     [rsp+0F0h+var_C8], rax; unsigned __int16 *
0x18001023a  add     rcx, rdx; this
0x18001023d  mov     [rsp+0F0h+var_D0], r15; unsigned __int16 *
0x180010242  call    ?GetIndexedAttributeIndices@CWMHeaderInfoIndexBase@@QEAAJGPEBGPEAG11H@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeIndices(ushort,ushort const *,ushort *,ushort *,ushort *,int)
0x180010247  mov     edi, eax
0x180010249  test    eax, eax
0x18001024b  js      loc_180010621
0x180010251  movzx   ecx, [rbp+57h+var_90]
0x180010255  cmp     r15w, cx
0x180010259  jz      loc_180010534
0x18001025f  mov     eax, 2
0x180010264  mul     rcx
0x180010267  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001026e  cmovb   rax, rcx
0x180010272  mov     rcx, rax; unsigned __int64
0x180010275  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001027a  mov     r15, rax
0x18001027d  test    rax, rax
0x180010280  jz      loc_180010549
0x180010286  mov     rdx, [r13+170h]
0x18001028d  lea     r9, [rbp+57h+var_80]; unsigned __int16 *
0x180010291  mov     r8, r14; unsigned __int16 *
0x180010294  mov     rax, [rdx+10h]
0x180010298  add     rdx, 10h; unsigned __int16
0x18001029c  movsxd  rcx, dword ptr [rax+8]
0x1800102a0  lea     rax, [rbp+57h+var_90]
0x1800102a4  mov     [rsp+0F0h+var_C8], rax; unsigned __int16 *
0x1800102a9  add     rcx, rdx; this
0x1800102ac  mov     [rsp+0F0h+var_D0], r15; unsigned __int16 *
0x1800102b1  call    ?GetIndexedAttributeIndices@CWMHeaderInfoIndexBase@@QEAAJGPEBGPEAG11H@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeIndices(ushort,ushort const *,ushort *,ushort *,ushort *,int)
0x1800102b6  mov     edi, eax
0x1800102b8  test    eax, eax
0x1800102ba  js      loc_180010663
0x1800102c0  xor     r9d, r9d
0x1800102c3  mov     r14d, r9d
0x1800102c6  mov     r12d, r9d
0x1800102c9  cmp     [rbp+57h+var_90], r12w
0x1800102ce  jbe     loc_1800104A4
0x1800102d4  mov     r8, [r13+170h]
0x1800102db  xor     eax, eax
0x1800102dd  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x1800102e1  xorps   xmm0, xmm0
0x1800102e4  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x1800102e8  movzx   eax, r12w
0x1800102ec  xor     edx, edx; unsigned __int16
0x1800102ee  lea     r10, [r15+rax*2]
0x1800102f2  mov     rax, [r8+10h]
0x1800102f6  mov     [rbp+57h+var_78], r10
0x1800102fa  movsxd  rcx, dword ptr [rax+8]
0x1800102fe  lea     rax, [rbp+57h+var_70]
0x180010302  mov     [rsp+0F0h+var_B0], rax; unsigned int *
0x180010307  add     rcx, 10h
0x18001030b  mov     [rsp+0F0h+var_B8], r9; unsigned __int8 *
0x180010310  lea     rax, [rbp+57h+var_7C]
0x180010314  mov     [rsp+0F0h+var_C0], r9; unsigned __int16 *
0x180010319  add     rcx, r8; this
0x18001031c  movzx   r8d, word ptr [r10]; unsigned __int16
0x180010320  mov     [rsp+0F0h+var_C8], rax; enum WMT_ATTR_DATATYPE *
0x180010325  mov     [rsp+0F0h+var_D0], r9; unsigned __int16 *
0x18001032a  xor     r9d, r9d; unsigned __int16 *
0x18001032d  call    ?GetIndexedAttributeByIndexEx@CWMHeaderInfoIndexBase@@QEAAJGGPEAG0PEAW4WMT_ATTR_DATATYPE@@0PEAEPEAKHPEBG@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(ushort,ushort,ushort *,ushort *,WMT_ATTR_DATATYPE *,ushort *,uchar *,ulong *,int,ushort const *)
0x180010332  mov     edi, eax
0x180010334  test    eax, eax
0x180010336  js      loc_180010410
0x18001033c  mov     rcx, r14; Block
0x18001033f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010344  mov     ecx, [rbp+57h+var_70]; unsigned __int64
0x180010347  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001034c  mov     r14, rax
0x18001034f  test    rax, rax
0x180010352  jz      loc_1800108B9
0x180010358  mov     r9, [r13+170h]
0x18001035f  xor     edx, edx; unsigned __int16
0x180010361  mov     r8, [rbp+57h+var_78]
0x180010365  mov     rax, [r9+10h]
0x180010369  add     r9, 10h
0x18001036d  movzx   r8d, word ptr [r8]; unsigned __int16
0x180010371  movsxd  rcx, dword ptr [rax+8]
0x180010375  lea     rax, [rbp+57h+var_70]
0x180010379  mov     [rsp+0F0h+var_B0], rax; unsigned int *
0x18001037e  add     rcx, r9; this
0x180010381  xor     eax, eax
0x180010383  mov     [rsp+0F0h+var_B8], r14; unsigned __int8 *
0x180010388  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x18001038d  xor     r9d, r9d; unsigned __int16 *
0x180010390  mov     [rsp+0F0h+var_C8], rax; enum WMT_ATTR_DATATYPE *
0x180010395  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x18001039a  call    ?GetIndexedAttributeByIndexEx@CWMHeaderInfoIndexBase@@QEAAJGGPEAG0PEAW4WMT_ATTR_DATATYPE@@0PEAEPEAKHPEBG@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(ushort,ushort,ushort *,ushort *,WMT_ATTR_DATATYPE *,ushort *,uchar *,ulong *,int,ushort const *)
0x18001039f  mov     edi, eax
0x1800103a1  test    eax, eax
0x1800103a3  js      loc_180010877
0x1800103a9  movsxd  rax, [rbp+57h+var_7C]
0x1800103ad  cmp     eax, 1
0x1800103b0  jnz     loc_180010CD8
0x1800103b6  mov     edx, 1Fh; unsigned __int16
0x1800103bb  mov     r9d, [rbp+57h+var_70]; unsigned int
0x1800103bf  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x1800103c3  mov     r8, r14; void *
0x1800103c6  call    ?CreateFromData@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@GPEBXK@Z; CMFPropVariantConvert::CreateFromData(CMFPropVariant *,ushort,void const *,ulong)
0x1800103cb  mov     edi, eax
0x1800103cd  test    eax, eax
0x1800103cf  js      loc_180010E21
0x1800103d5  mov     eax, 1
0x1800103da  cmp     ax, [rbp+57h+var_90]
0x1800103de  jb      loc_1800106A5
0x1800103e4  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x1800103e8  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x1800103ec  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800103f1  mov     edi, eax
0x1800103f3  test    eax, eax
0x1800103f5  js      loc_180010835
0x1800103fb  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x1800103ff  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180010404  inc     r12w
0x180010408  xor     r9d, r9d
0x18001040b  jmp     loc_1800102C9
0x180010410  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180010417  test    rcx, rcx
0x18001041a  jz      short loc_180010493
0x18001041c  cmp     byte ptr [rcx+8], 0
0x180010420  jnz     loc_180010B34
0x180010426  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001042d  mov     r13, [rbp+57h+var_88]
0x180010431  jnb     loc_180010F19
0x180010437  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x18001043b  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180010440  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010447  test    rcx, rcx
0x18001044a  jnz     loc_180010F61
0x180010450  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010457  nop     dword ptr [rax+rax+00h]
0x18001045c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010463  mov     rcx, rax
0x180010466  test    rax, rax
0x180010469  jnz     loc_180010F41
0x18001046f  lea     rcx, qword_1801B97E0
0x180010476  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001047d  jmp     loc_180010F61
0x180010482  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180010487  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001048e  jmp     loc_180010183
0x180010493  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180010498  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001049f  jmp     loc_18001041C
0x1800104a4  mov     r13, [rbp+57h+var_88]
0x1800104a8  test    edi, edi
0x1800104aa  js      short loc_180010440
0x1800104ac  mov     rcx, r15; Block
0x1800104af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104b4  mov     rcx, r14; Block
0x1800104b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104bc  jmp     short loc_1800104D2
0x1800104be  mov     rcx, r15; Block
0x1800104c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104c6  mov     rcx, r14; Block
0x1800104c9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800104ce  test    edi, edi
0x1800104d0  js      short loc_1800104E9
0x1800104d2  movups  xmm0, xmmword ptr [rbp+57h+pvarDest]
0x1800104d6  xor     eax, eax
0x1800104d8  movsd   xmm1, qword ptr [rbp+57h+pvarDest+10h]
0x1800104dd  movups  xmmword ptr [rsi], xmm0
0x1800104e0  mov     word ptr [rbp+57h+pvarDest], ax
0x1800104e4  movsd   qword ptr [rsi+10h], xmm1
0x1800104e9  mov     rcx, rbx; lpCriticalSection
0x1800104ec  call    cs:__imp_LeaveCriticalSection
0x1800104f3  nop     dword ptr [rax+rax+00h]
0x1800104f8  lea     rcx, [rbp+57h+pvarDest]; pvar
0x1800104fc  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180010501  lea     rcx, [rbp+57h+var_90]; this
0x180010505  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001050a  mov     eax, edi
0x18001050c  mov     rcx, [rbp+57h+var_38]
0x180010510  xor     rcx, rsp; StackCookie
0x180010513  call    __security_check_cookie
0x180010518  mov     rbx, [rsp+0F0h+arg_18]
0x180010520  add     rsp, 0C0h
0x180010527  pop     r15
0x180010529  pop     r14
0x18001052b  pop     r13
0x18001052d  pop     r12
0x18001052f  pop     rdi
0x180010530  pop     rsi
0x180010531  pop     rbp
0x180010532  retn
0x180010534  mov     edi, 0C00D3E8Dh
0x180010539  xor     ecx, ecx; Block
0x18001053b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010540  xor     ecx, ecx; Block
0x180010542  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010547  jmp     short loc_1800104E9
0x180010549  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180010550  mov     edi, 8007000Eh
0x180010555  test    rcx, rcx
0x180010558  jz      short loc_180010585
0x18001055a  cmp     byte ptr [rcx+8], 0
0x18001055e  jnz     loc_180010993
0x180010564  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001056b  jnb     loc_180010C70
0x180010571  mov     rcx, r15; Block
0x180010574  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010579  xor     ecx, ecx; Block
0x18001057b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010580  jmp     loc_1800104E9
0x180010585  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001058a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010591  jmp     short loc_18001055A
0x180010593  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001059a  mov     edi, 80004003h
0x18001059f  test    rax, rax
0x1800105a2  jnz     loc_180010BB0
0x1800105a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800105af  nop     dword ptr [rax+rax+00h]
0x1800105b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800105bb  mov     rcx, rax
0x1800105be  test    rax, rax
0x1800105c1  jnz     loc_180010B90
0x1800105c7  lea     rax, qword_1801B97E0
0x1800105ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800105d5  jmp     loc_180010BB0
0x1800105da  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800105e1  mov     edi, 80004003h
0x1800105e6  test    rax, rax
0x1800105e9  jnz     loc_180010C16
0x1800105ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800105f6  nop     dword ptr [rax+rax+00h]
0x1800105fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010602  mov     rcx, rax
0x180010605  test    rax, rax
0x180010608  jnz     loc_180010BF6
0x18001060e  lea     rax, qword_1801B97E0
0x180010615  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001061c  jmp     loc_180010C16
0x180010621  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010628  test    rax, rax
0x18001062b  jnz     loc_180010C54
0x180010631  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010638  nop     dword ptr [rax+rax+00h]
0x18001063d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010644  mov     rcx, rax
  ... truncated ...
```
