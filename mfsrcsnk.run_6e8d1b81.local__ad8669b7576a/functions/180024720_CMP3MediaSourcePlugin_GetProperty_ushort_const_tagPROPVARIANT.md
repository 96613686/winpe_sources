# CMP3MediaSourcePlugin::GetProperty(ushort const *,tagPROPVARIANT *)

- ea: `0x180024720`
- end: `0x180025540`
- name: `?GetProperty@CMP3MediaSourcePlugin@@UEAAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `3616`
- prototype: `int(CMP3MediaSourcePlugin *__hidden this, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180024720`
- `0x180025548`
- `0x180025740`
- `0x180025e90`
- `0x1800275f0`
- `0x180028340`
- `0x1800297c0`
- `0x180071a44`
- `0x180073b14`
- `0x1800d6770`
- `0x18010959c`
- `0x1801095e8`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024abd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024abd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024a2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024b72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024bb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024bef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024c2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024cad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024d62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024ddc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024e18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024e59`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024a2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024b72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024bb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024bef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024c2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024cad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024d62`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024ddc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024e18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024e59`

## string_xrefs

- `0x180024767`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180024e9c`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180024ecd`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180024efe`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180024f2c`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180024f5d`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180024f8b`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180024fb9`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180024fe7`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180025015`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180025043`: `CMP3MediaSourcePlugin::GetProperty`
- `0x180025071`: `CMP3MediaSourcePlugin::GetProperty`
- `0x18002509f`: `CMP3MediaSourcePlugin::GetProperty`
- `0x1800250cd`: `CMP3MediaSourcePlugin::GetProperty`
- `0x1800250fb`: `CMP3MediaSourcePlugin::GetProperty`

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
  __int64 v26; // rdx
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
        v36 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v38 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v40 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v42 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v56 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v54 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    IndexedAttributeIndices = CMFPropVariantConvert::CreateFromData(
                                (struct CMFPropVariant *)&pvarSrc,
                                v26,
                                (char *)v19,
                                v86[0]);
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
          v52 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        CMFPropVariant::Clear((CMFPropVariant *)&pvarSrc);
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
              v50 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v46 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    CMFPropVariant::Clear((CMFPropVariant *)&pvarSrc);
  }
  v30 = v82;
LABEL_70:
  if ( !CallStackTracing::s_wpInstance )
  {
    v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v27, v24);
    CallStackTracing::s_wpInstance = v49;
    if ( !v49 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
  CMFPropVariant::Clear((CMFPropVariant *)&pvarSrc);
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
      v31 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
  CMFPropVariant::Clear((CMFPropVariant *)&pvarDest);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
  return (unsigned int)IndexedAttributeIndices;
}

```

## disassembly

```asm
0x180024720  mov     [rsp-8+arg_18], rbx
0x180024725  push    rbp
0x180024726  push    rsi
0x180024727  push    rdi
0x180024728  push    r12
0x18002472a  push    r13
0x18002472c  push    r14
0x18002472e  push    r15
0x180024730  lea     rbp, [rsp-27h]
0x180024735  sub     rsp, 0C0h
0x18002473c  mov     rax, cs:__security_cookie
0x180024743  xor     rax, rsp
0x180024746  mov     [rbp+57h+var_38], rax
0x18002474a  mov     r13, rcx
0x18002474d  mov     rsi, r8
0x180024750  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180024757  mov     r14, rdx
0x18002475a  test    rcx, rcx
0x18002475d  jz      loc_180024A56
0x180024763  cmp     byte ptr [rcx+8], 0
0x180024767  lea     rbx, aCmp3mediasourc_5; "CMP3MediaSourcePlugin::GetProperty"
0x18002476e  jz      short loc_180024798
0x180024770  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180024775  mov     ecx, [rax+7C4h]
0x18002477b  cmp     ecx, [rax+7C8h]
0x180024781  jnb     short loc_180024792
0x180024783  add     rcx, rcx
0x180024786  mov     [rax+rcx*8], rbx
0x18002478a  mov     dword ptr [rax+rcx*8+8], 0B8Bh
0x180024792  inc     dword ptr [rax+7C4h]
0x180024798  xor     r15d, r15d
0x18002479b  mov     [rbp+57h+var_7C], 2
0x1800247a2  xorps   xmm0, xmm0
0x1800247a5  mov     [rbp+57h+var_80], r15w
0x1800247aa  xor     eax, eax
0x1800247ac  mov     [rbp+57h+var_90], r15w
0x1800247b1  lea     rbx, [r13+10h]
0x1800247b5  mov     [rbp+57h+var_70], r15d
0x1800247b9  mov     rcx, rbx; lpCriticalSection
0x1800247bc  mov     qword ptr [rbp+57h+pvarDest+10h], rax
0x1800247c0  movups  xmmword ptr [rbp+57h+pvarDest], xmm0
0x1800247c4  call    cs:__imp_EnterCriticalSection
0x1800247ca  lea     r12, [r13-28h]
0x1800247ce  mov     [rbp+57h+var_88], r12
0x1800247d2  test    r14, r14
0x1800247d5  jz      loc_180024B5D
0x1800247db  test    rsi, rsi
0x1800247de  jz      loc_180024B9E
0x1800247e4  xor     eax, eax
0x1800247e6  lea     r9, [rbp+57h+var_80]; unsigned __int16 *
0x1800247ea  xorps   xmm0, xmm0
0x1800247ed  mov     r8, r14; unsigned __int16 *
0x1800247f0  movups  xmmword ptr [rsi], xmm0
0x1800247f3  mov     [rsi+10h], rax
0x1800247f7  mov     rdx, [r12+198h]
0x1800247ff  mov     rax, [rdx+10h]
0x180024803  add     rdx, 10h; unsigned __int16
0x180024807  movsxd  rcx, dword ptr [rax+8]
0x18002480b  lea     rax, [rbp+57h+var_90]
0x18002480f  mov     [rsp+0F0h+var_C8], rax; unsigned __int16 *
0x180024814  add     rcx, rdx; this
0x180024817  mov     [rsp+0F0h+var_D0], r15; unsigned __int16 *
0x18002481c  call    ?GetIndexedAttributeIndices@CWMHeaderInfoIndexBase@@QEAAJGPEBGPEAG11H@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeIndices(ushort,ushort const *,ushort *,ushort *,ushort *,int)
0x180024821  mov     edi, eax
0x180024823  test    eax, eax
0x180024825  js      loc_180024BDF
0x18002482b  movzx   ecx, [rbp+57h+var_90]
0x18002482f  cmp     r15w, cx
0x180024833  jz      loc_180024AFE
0x180024839  mov     eax, 2
0x18002483e  mul     rcx
0x180024841  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024848  cmovb   rax, rcx
0x18002484c  mov     rcx, rax; unsigned __int64
0x18002484f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180024854  mov     r15, rax
0x180024857  test    rax, rax
0x18002485a  jz      loc_180024B13
0x180024860  mov     rdx, [r13+170h]
0x180024867  lea     r9, [rbp+57h+var_80]; unsigned __int16 *
0x18002486b  mov     r8, r14; unsigned __int16 *
0x18002486e  mov     rax, [rdx+10h]
0x180024872  add     rdx, 10h; unsigned __int16
0x180024876  movsxd  rcx, dword ptr [rax+8]
0x18002487a  lea     rax, [rbp+57h+var_90]
0x18002487e  mov     [rsp+0F0h+var_C8], rax; unsigned __int16 *
0x180024883  add     rcx, rdx; this
0x180024886  mov     [rsp+0F0h+var_D0], r15; unsigned __int16 *
0x18002488b  call    ?GetIndexedAttributeIndices@CWMHeaderInfoIndexBase@@QEAAJGPEBGPEAG11H@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeIndices(ushort,ushort const *,ushort *,ushort *,ushort *,int)
0x180024890  mov     edi, eax
0x180024892  test    eax, eax
0x180024894  js      loc_180024C1B
0x18002489a  xor     r9d, r9d
0x18002489d  mov     r14d, r9d
0x1800248a0  mov     r12d, r9d
0x1800248a3  cmp     [rbp+57h+var_90], r12w
0x1800248a8  jbe     loc_180024A75
0x1800248ae  mov     r8, [r13+170h]
0x1800248b5  xor     eax, eax
0x1800248b7  mov     qword ptr [rbp+57h+pvarSrc+10h], rax
0x1800248bb  xorps   xmm0, xmm0
0x1800248be  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x1800248c2  movzx   eax, r12w
0x1800248c6  xor     edx, edx; unsigned __int16
0x1800248c8  lea     r10, [r15+rax*2]
0x1800248cc  mov     rax, [r8+10h]
0x1800248d0  mov     [rbp+57h+var_78], r10
0x1800248d4  movsxd  rcx, dword ptr [rax+8]
0x1800248d8  lea     rax, [rbp+57h+var_70]
0x1800248dc  mov     [rsp+0F0h+var_B0], rax; unsigned int *
0x1800248e1  add     rcx, 10h
0x1800248e5  mov     [rsp+0F0h+var_B8], r9; unsigned __int8 *
0x1800248ea  lea     rax, [rbp+57h+var_7C]
0x1800248ee  mov     [rsp+0F0h+var_C0], r9; unsigned __int16 *
0x1800248f3  add     rcx, r8; this
0x1800248f6  movzx   r8d, word ptr [r10]; unsigned __int16
0x1800248fa  mov     [rsp+0F0h+var_C8], rax; enum WMT_ATTR_DATATYPE *
0x1800248ff  mov     [rsp+0F0h+var_D0], r9; unsigned __int16 *
0x180024904  xor     r9d, r9d; unsigned __int16 *
0x180024907  call    ?GetIndexedAttributeByIndexEx@CWMHeaderInfoIndexBase@@QEAAJGGPEAG0PEAW4WMT_ATTR_DATATYPE@@0PEAEPEAKHPEBG@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(ushort,ushort,ushort *,ushort *,WMT_ATTR_DATATYPE *,ushort *,uchar *,ulong *,int,ushort const *)
0x18002490c  mov     edi, eax
0x18002490e  test    eax, eax
0x180024910  js      loc_1800249EA
0x180024916  mov     rcx, r14; Block
0x180024919  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002491e  mov     ecx, [rbp+57h+var_70]; unsigned __int64
0x180024921  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180024926  mov     r14, rax
0x180024929  test    rax, rax
0x18002492c  jz      loc_180024E44
0x180024932  mov     r9, [r13+170h]
0x180024939  xor     edx, edx; unsigned __int16
0x18002493b  mov     r8, [rbp+57h+var_78]
0x18002493f  mov     rax, [r9+10h]
0x180024943  add     r9, 10h
0x180024947  movzx   r8d, word ptr [r8]; unsigned __int16
0x18002494b  movsxd  rcx, dword ptr [rax+8]
0x18002494f  lea     rax, [rbp+57h+var_70]
0x180024953  mov     [rsp+0F0h+var_B0], rax; unsigned int *
0x180024958  add     rcx, r9; this
0x18002495b  xor     eax, eax
0x18002495d  mov     [rsp+0F0h+var_B8], r14; unsigned __int8 *
0x180024962  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x180024967  xor     r9d, r9d; unsigned __int16 *
0x18002496a  mov     [rsp+0F0h+var_C8], rax; enum WMT_ATTR_DATATYPE *
0x18002496f  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x180024974  call    ?GetIndexedAttributeByIndexEx@CWMHeaderInfoIndexBase@@QEAAJGGPEAG0PEAW4WMT_ATTR_DATATYPE@@0PEAEPEAKHPEBG@Z; CWMHeaderInfoIndexBase::GetIndexedAttributeByIndexEx(ushort,ushort,ushort *,ushort *,WMT_ATTR_DATATYPE *,ushort *,uchar *,ulong *,int,ushort const *)
0x180024979  mov     edi, eax
0x18002497b  test    eax, eax
0x18002497d  js      loc_180024E08
0x180024983  movsxd  rax, [rbp+57h+var_7C]
0x180024987  cmp     eax, 1
0x18002498a  jnz     loc_18002525D
0x180024990  mov     edx, 1Fh; unsigned __int16
0x180024995  mov     r9d, [rbp+57h+var_70]; unsigned int
0x180024999  lea     rcx, [rbp+57h+pvarSrc]; this
0x18002499d  mov     r8, r14; void *
0x1800249a0  call    ?CreateFromData@CMFPropVariantConvert@@SAJPEAVCMFPropVariant@@GPEBXK@Z; CMFPropVariantConvert::CreateFromData(CMFPropVariant *,ushort,void const *,ulong)
0x1800249a5  mov     edi, eax
0x1800249a7  test    eax, eax
0x1800249a9  js      loc_1800253A2
0x1800249af  mov     eax, 1
0x1800249b4  cmp     ax, [rbp+57h+var_90]
0x1800249b8  jb      loc_180024C57
0x1800249be  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x1800249c2  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x1800249c6  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800249cb  mov     edi, eax
0x1800249cd  test    eax, eax
0x1800249cf  js      loc_180024DCC
0x1800249d5  lea     rcx, [rbp+57h+pvarSrc]; this
0x1800249d9  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800249de  inc     r12w
0x1800249e2  xor     r9d, r9d
0x1800249e5  jmp     loc_1800248A3
0x1800249ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800249f1  test    rcx, rcx
0x1800249f4  jz      short loc_180024A67
0x1800249f6  cmp     byte ptr [rcx+8], 0
0x1800249fa  jnz     loc_1800250B9
0x180024a00  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024a07  mov     r13, [rbp+57h+var_88]
0x180024a0b  jnb     loc_18002549A
0x180024a11  lea     rcx, [rbp+57h+pvarSrc]; this
0x180024a15  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180024a1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024a21  test    rcx, rcx
0x180024a24  jnz     loc_1800254E2
0x180024a2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180024a30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024a37  mov     rcx, rax
0x180024a3a  test    rax, rax
0x180024a3d  jnz     loc_1800254C2
0x180024a43  lea     rcx, qword_1801B07E0
0x180024a4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180024a51  jmp     loc_1800254E2
0x180024a56  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180024a5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024a62  jmp     loc_180024763
0x180024a67  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180024a6c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024a73  jmp     short loc_1800249F6
0x180024a75  mov     r13, [rbp+57h+var_88]
0x180024a79  test    edi, edi
0x180024a7b  js      short loc_180024A1A
0x180024a7d  mov     rcx, r15; Block
0x180024a80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024a85  mov     rcx, r14; Block
0x180024a88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024a8d  jmp     short loc_180024AA3
0x180024a8f  mov     rcx, r15; Block
0x180024a92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024a97  mov     rcx, r14; Block
0x180024a9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024a9f  test    edi, edi
0x180024aa1  js      short loc_180024ABA
0x180024aa3  movups  xmm0, xmmword ptr [rbp+57h+pvarDest]
0x180024aa7  xor     eax, eax
0x180024aa9  movsd   xmm1, qword ptr [rbp+57h+pvarDest+10h]
0x180024aae  movups  xmmword ptr [rsi], xmm0
0x180024ab1  mov     word ptr [rbp+57h+pvarDest], ax
0x180024ab5  movsd   qword ptr [rsi+10h], xmm1
0x180024aba  mov     rcx, rbx; lpCriticalSection
0x180024abd  call    cs:__imp_LeaveCriticalSection
0x180024ac3  lea     rcx, [rbp+57h+pvarDest]; this
0x180024ac7  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180024acc  lea     rcx, [rbp+57h+var_90]; this
0x180024ad0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180024ad5  mov     eax, edi
0x180024ad7  mov     rcx, [rbp+57h+var_38]
0x180024adb  xor     rcx, rsp; StackCookie
0x180024ade  call    __security_check_cookie
0x180024ae3  mov     rbx, [rsp+0F0h+arg_18]
0x180024aeb  add     rsp, 0C0h
0x180024af2  pop     r15
0x180024af4  pop     r14
0x180024af6  pop     r13
0x180024af8  pop     r12
0x180024afa  pop     rdi
0x180024afb  pop     rsi
0x180024afc  pop     rbp
0x180024afd  retn
0x180024afe  mov     edi, 0C00D3E8Dh
0x180024b03  xor     ecx, ecx; Block
0x180024b05  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024b0a  xor     ecx, ecx; Block
0x180024b0c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024b11  jmp     short loc_180024ABA
0x180024b13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180024b1a  mov     edi, 8007000Eh
0x180024b1f  test    rcx, rcx
0x180024b22  jz      short loc_180024B4F
0x180024b24  cmp     byte ptr [rcx+8], 0
0x180024b28  jnz     loc_180024F18
0x180024b2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024b35  jnb     loc_1800251F5
0x180024b3b  mov     rcx, r15; Block
0x180024b3e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024b43  xor     ecx, ecx; Block
0x180024b45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024b4a  jmp     loc_180024ABA
0x180024b4f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180024b54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024b5b  jmp     short loc_180024B24
0x180024b5d  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024b64  mov     edi, 80004003h
0x180024b69  test    rax, rax
0x180024b6c  jnz     loc_180025135
0x180024b72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180024b78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024b7f  mov     rcx, rax
0x180024b82  test    rax, rax
0x180024b85  jnz     loc_180025115
0x180024b8b  lea     rax, qword_1801B07E0
0x180024b92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024b99  jmp     loc_180025135
0x180024b9e  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024ba5  mov     edi, 80004003h
0x180024baa  test    rax, rax
0x180024bad  jnz     loc_18002519B
0x180024bb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180024bb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024bc0  mov     rcx, rax
0x180024bc3  test    rax, rax
0x180024bc6  jnz     loc_18002517B
0x180024bcc  lea     rax, qword_1801B07E0
0x180024bd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024bda  jmp     loc_18002519B
0x180024bdf  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024be6  test    rax, rax
0x180024be9  jnz     loc_1800251D9
0x180024bef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180024bf5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024bfc  mov     rcx, rax
0x180024bff  test    rax, rax
0x180024c02  jnz     loc_1800251B9
0x180024c08  lea     rax, qword_1801B07E0
0x180024c0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024c16  jmp     loc_1800251D9
0x180024c1b  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
