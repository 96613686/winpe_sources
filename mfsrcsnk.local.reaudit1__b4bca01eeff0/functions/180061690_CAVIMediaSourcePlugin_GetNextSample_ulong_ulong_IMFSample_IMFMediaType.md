# CAVIMediaSourcePlugin::GetNextSample(ulong *,ulong *,IMFSample * *,IMFMediaType * *)

- ea: `0x180061690`
- end: `0x18006236c`
- name: `?GetNextSample@CAVIMediaSourcePlugin@@UEAAJPEAK0PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z`
- size: `3292`
- prototype: `__int64 __fastcall(CAVIMediaSourcePlugin *__hidden this, unsigned int *, unsigned int *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18003cbec`
- `0x1800476a0`
- `0x180061690`
- `0x180079680`
- `0x18007a0e4`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800616fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061825`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800618ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061973`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061a4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061cb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061d6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061fc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006207f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062152`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062227`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800622e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800616fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061825`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800618ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061973`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061a4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061cb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061d6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061fc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006207f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062152`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180062227`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800622e3`

## string_xrefs

- `0x1800616ba`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x18006175b`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061882`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061927`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x1800619d0`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061aa7`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061d11`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061dcc`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180062026`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x1800620dc`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x1800621af`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180062284`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180062340`: `CAVIMediaSourcePlugin::GetNextSample`

## pseudocode

```c
__int64 __fastcall CAVIMediaSourcePlugin::GetNextSample(
        CAVIMediaSourcePlugin *this,
        unsigned int *a2,
        unsigned int *a3,
        struct IMFSample **a4,
        struct IMFMediaType **a5)
{
  __int64 v9; // rdx
  char *v10; // rsi
  wchar_t *v11; // rcx
  int v12; // ebx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  struct IMFMediaType **v16; // rdi
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rax
  unsigned int v28; // r14d
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  CAVIIAVSStreamParser *v33; // rdi
  unsigned int NumberOfStreams; // r11d
  char *v35; // rax
  char *v36; // r10
  char *v37; // r9
  unsigned int v38; // edx
  char *v39; // r8
  int v40; // r14d
  __int64 v41; // rcx
  __int64 v42; // rax
  int v43; // r13d
  unsigned int j; // edi
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 *v52; // rcx
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 i; // rdi
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // r13
  __int64 v60; // rdx
  __int64 v61; // rax
  struct IMFSample *v62; // rcx
  __int64 v63; // r8
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 k; // r8
  wchar_t *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // rdx
  wchar_t *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  __int64 v74; // rdx
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  struct CallStackContext *v77; // rax
  __int64 v78; // rdx
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  wchar_t *v82; // rcx
  CallStackTracing *v83; // rax
  struct CallStackContext *v84; // rax
  __int64 v85; // [rsp+30h] [rbp-40h] BYREF
  int v86; // [rsp+38h] [rbp-38h] BYREF
  void *v87; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v88; // [rsp+48h] [rbp-28h]
  __int64 v89; // [rsp+50h] [rbp-20h] BYREF
  char *v90; // [rsp+58h] [rbp-18h]
  char *v91; // [rsp+60h] [rbp-10h]
  char *v92; // [rsp+68h] [rbp-8h]
  unsigned int v93; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int *v94; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int *v95; // [rsp+C0h] [rbp+50h]

  v95 = a3;
  v94 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v93, "CAVIMediaSourcePlugin::GetNextSample", 1772);
  v10 = (char *)this - 16;
  v86 = 0;
  v87 = 0;
  if ( !a2 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIMediaSourcePlugin::GetNextSample", 1780, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v15 = 180;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      (char *)this - 16,
      -2147467261);
LABEL_13:
    v16 = a5;
LABEL_14:
    if ( *a4 )
    {
      ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
      *a4 = 0;
    }
    if ( *v16 )
    {
      ((void (__fastcall *)(struct IMFMediaType *))(*v16)->lpVtbl->Release)(*v16);
      *v16 = 0;
    }
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v20, "CAVIMediaSourcePlugin::GetNextSample", 1781, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v15 = 181;
    goto LABEL_12;
  }
  if ( !a4 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
      if ( *((_DWORD *)v23 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v23, "CAVIMediaSourcePlugin::GetNextSample", 1782, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v15 = 182;
    goto LABEL_12;
  }
  v16 = a5;
  if ( !a5 )
  {
    v24 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v26 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v26, "CAVIMediaSourcePlugin::GetNextSample", 1783, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v15 = 183;
    goto LABEL_12;
  }
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *v16 = 0;
  if ( !*((_QWORD *)v10 + 9) || (v27 = *((_QWORD *)this + 8), *(_DWORD *)(v27 + 180) != 3) )
  {
    v82 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v83 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v83;
      if ( v83 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v83 + 8LL))(v83, 2032) )
      {
        v82 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v82 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v82 + 8) )
    {
      v84 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v82);
      if ( *((_DWORD *)v84 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v84, "CAVIMediaSourcePlugin::GetNextSample", 1792, -1072875854);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v32 = 184;
    goto LABEL_67;
  }
  v28 = *(_DWORD *)(v27 + 112);
  v93 = v28;
  if ( !v28 )
  {
    v29 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v31 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v31, "CAVIMediaSourcePlugin::GetNextSample", 1803, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v32 = 185;
    goto LABEL_67;
  }
  v12 = 0;
  v33 = **(CAVIIAVSStreamParser ***)(v27 + 104);
  if ( !(*(unsigned int (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)v33 + 8LL))(v33) )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v28 )
        goto LABEL_135;
      v57 = *((_QWORD *)this + 7);
      v85 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64 *))(*(_QWORD *)v57 + 272LL))(
              v57,
              (unsigned int)i,
              &v86,
              &v85);
      if ( v12 < 0 )
        break;
      if ( v86 )
      {
        v59 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 104LL) + 8 * i);
        v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v85 + 264LL))(v85, v95);
        if ( v12 < 0 )
        {
          v67 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60);
            CallStackTracing::s_wpInstance = v68;
            if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
            {
              v67 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v67 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v67 + 8) )
          {
            v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
            if ( *((_DWORD *)v69 + 499) != v12 )
              CallStackContext::TraceFailure(v69, "CAVIMediaSourcePlugin::GetNextSample", 1870, v12);
          }
          if ( g_wppLevels )
          {
            v70 = 189;
LABEL_151:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v70,
              &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
              (char *)this - 16,
              v12);
            goto LABEL_152;
          }
          goto LABEL_152;
        }
        if ( *((_DWORD *)v10 + 170) == 1 )
        {
          v61 = *((_QWORD *)this + 82);
          if ( v61 )
          {
            if ( *(_QWORD *)(v61 + 24 * i) && *(_DWORD *)(v61 + 24 * i + 16) )
            {
              _mm_lfence();
              v62 = *(struct IMFSample **)(*((_QWORD *)this + 82) + 24 * i);
              *a4 = v62;
              ((void (__fastcall *)(struct IMFSample *))v62->lpVtbl->AddRef)(v62);
              v63 = 0;
              if ( *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i + 8) - 500000LL >= 0 )
                v63 = *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i + 8) - 500000LL;
              ((void (__fastcall *)(_QWORD, __int64))(*a4)->lpVtbl->SetSampleTime)(*a4, v63);
              if ( *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i) )
              {
                _mm_lfence();
                v64 = *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
                *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i) = 0;
              }
              if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  190,
                  &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
                  (char *)this - 16,
                  i);
              goto LABEL_133;
            }
          }
        }
        if ( (unsigned int)CVPtrList::RemoveHead((CVPtrList *)(v59 + 88), &v87) )
        {
          *a4 = (struct IMFSample *)v87;
          v87 = 0;
LABEL_133:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v85);
          goto LABEL_134;
        }
        v28 = v93;
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v85);
    }
    v71 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58);
      CallStackTracing::s_wpInstance = v72;
      if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
      {
        v71 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v71 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v71 + 8) )
    {
      v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
      if ( *((_DWORD *)v73 + 499) != v12 )
        CallStackContext::TraceFailure(v73, "CAVIMediaSourcePlugin::GetNextSample", 1864, v12);
    }
    if ( g_wppLevels )
    {
      v70 = 188;
      goto LABEL_151;
    }
LABEL_152:
    v52 = &v85;
LABEL_104:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v52);
    goto LABEL_13;
  }
  NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v33);
  v88 = NumberOfStreams;
  v35 = (char *)v33 + 88;
  v36 = (char *)v33 + 688;
  v91 = (char *)v33 + 88;
  v37 = (char *)v33 + 1136;
  v92 = (char *)v33 + 688;
  v90 = (char *)v33 + 1136;
  while ( 1 )
  {
    v38 = *((_DWORD *)v35 + 110);
    v39 = v35;
    if ( v38 < *((_DWORD *)v36 + 110) )
      v39 = v36;
    v40 = (v38 < *((_DWORD *)v36 + 110)) + 1;
    if ( *((_DWORD *)v39 + 110) < *((_DWORD *)v37 + 110) )
    {
      v39 = v37;
      v40 = 3;
    }
    v41 = *((_QWORD *)v39 + 53);
    if ( !v41 )
      break;
    v87 = *(void **)v41;
    v42 = *(_QWORD *)(v41 + 8);
    *((_QWORD *)v39 + 53) = v42;
    if ( v42 )
      *(_QWORD *)(v42 + 16) = 0;
    else
      *((_QWORD *)v39 + 54) = 0;
    v43 = 0;
    *(_QWORD *)(v41 + 8) = *(_QWORD *)v39;
    *(_QWORD *)v39 = v41;
    --*((_DWORD *)v39 + 110);
    for ( j = 0; j < NumberOfStreams; ++j )
    {
      v45 = *((_QWORD *)this + 7);
      v89 = 0;
      LODWORD(v85) = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64 *))(*(_QWORD *)v45 + 272LL))(v45, j, &v86, &v89);
      if ( v12 < 0 )
      {
        v53 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
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
          if ( *((_DWORD *)v55 + 499) != v12 )
            CallStackContext::TraceFailure(v55, "CAVIMediaSourcePlugin::GetNextSample", 1826, v12);
        }
        if ( g_wppLevels )
        {
          v51 = 186;
LABEL_102:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v51,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            (char *)this - 16,
            v12);
        }
LABEL_103:
        v52 = &v89;
        goto LABEL_104;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v89 + 264LL))(v89, &v85);
      if ( v12 < 0 )
      {
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
          if ( *((_DWORD *)v50 + 499) != v12 )
            CallStackContext::TraceFailure(v50, "CAVIMediaSourcePlugin::GetNextSample", 1827, v12);
        }
        if ( g_wppLevels )
        {
          v51 = 187;
          goto LABEL_102;
        }
        goto LABEL_103;
      }
      if ( (_DWORD)v85 == v40 )
      {
        if ( v86 )
        {
          *v95 = v85;
          *a4 = (struct IMFSample *)v87;
          v87 = 0;
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v89);
          goto LABEL_89;
        }
        v43 = 1;
        ComSmartPtr<IUnknown>::Release(&v87);
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v89);
      NumberOfStreams = v88;
    }
    if ( !v43 )
    {
      ComSmartPtr<IUnknown>::Release(&v87);
LABEL_89:
      NumberOfStreams = v88;
    }
    if ( *a4 )
      break;
    v37 = v90;
    v35 = v91;
    v36 = v92;
  }
LABEL_134:
  v28 = v93;
LABEL_135:
  v65 = (__int64)*a4;
  if ( *a4 )
  {
    LODWORD(v94) = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, unsigned int **))(*(_QWORD *)v65 + 312LL))(v65, &v94);
    if ( v12 < 0 )
    {
      v75 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v74);
        CallStackTracing::s_wpInstance = v76;
        if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v75 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v75 + 8) )
      {
        v77 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
        if ( *((_DWORD *)v77 + 499) != v12 )
          CallStackContext::TraceFailure(v77, "CAVIMediaSourcePlugin::GetNextSample", 1920, v12);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          191,
          &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
          (char *)this - 16,
          v12);
      goto LABEL_13;
    }
    if ( (_DWORD)v94 )
      goto LABEL_18;
    v16 = a5;
    v12 = ((__int64 (__fastcall *)(_QWORD, __int64 *, GUID *, struct IMFMediaType **))(*a4)->lpVtbl->GetUnknown)(
            *a4,
            AVI_SAMPLE_ATTRIBUTE_FORMATCHANGE_MEDIATYPE,
            &IID_IMFMediaType,
            a5);
    if ( v12 >= 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
      goto LABEL_18;
    }
    v79 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v78);
      CallStackTracing::s_wpInstance = v80;
      if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
      {
        v79 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v79 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v79 + 8) )
    {
      v81 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
      if ( *((_DWORD *)v81 + 499) != v12 )
        CallStackContext::TraceFailure(v81, "CAVIMediaSourcePlugin::GetNextSample", 1926, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v32 = 192;
LABEL_67:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v32,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      (char *)this - 16,
      v12);
    goto LABEL_14;
  }
  for ( k = 0; (unsigned int)k < v28; k = (unsigned int)(k + 1) )
  {
    if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 104LL) + 8 * k) + 80LL) )
      goto LABEL_18;
  }
  *v94 = 1;
LABEL_18:
  if ( v87 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v87 + 16LL))(v87);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v93);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180061690  mov     [rsp-38h+arg_18], rbx
0x180061695  mov     [rsp-38h+arg_10], r8
0x18006169a  mov     [rsp-38h+arg_8], rdx
0x18006169f  push    rbp
0x1800616a0  push    rsi
0x1800616a1  push    rdi
0x1800616a2  push    r12
0x1800616a4  push    r13
0x1800616a6  push    r14
0x1800616a8  push    r15
0x1800616aa  mov     rbp, rsp
0x1800616ad  sub     rsp, 70h
0x1800616b1  mov     rbx, r8
0x1800616b4  mov     r13, rdx
0x1800616b7  mov     r15, rcx
0x1800616ba  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x1800616c1  mov     r8d, 6ECh; int
0x1800616c7  lea     rcx, [rbp+arg_0]; this
0x1800616cb  mov     r12, r9
0x1800616ce  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800616d3  xor     r14d, r14d
0x1800616d6  lea     rsi, [r15-10h]
0x1800616da  mov     [rbp+var_38], r14d
0x1800616de  mov     [rbp+var_30], r14
0x1800616e2  test    r13, r13
0x1800616e5  jnz     loc_180061809
0x1800616eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800616f2  mov     edi, 80004003h
0x1800616f7  mov     ebx, edi
0x1800616f9  test    rcx, rcx
0x1800616fc  jnz     short loc_180061745
0x1800616fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061705  nop     dword ptr [rax+rax+00h]
0x18006170a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061711  mov     rcx, rax
0x180061714  test    rax, rax
0x180061717  jz      short loc_180061737
0x180061719  mov     rax, [rax]
0x18006171c  mov     edx, 7F0h
0x180061721  mov     rax, [rax+8]
0x180061725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006172a  test    eax, eax
0x18006172c  jz      short loc_180061737
0x18006172e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061735  jmp     short loc_180061745
0x180061737  lea     rcx, qword_1801B97E0; this
0x18006173e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061745  cmp     [rcx+8], r14b
0x180061749  jz      short loc_180061770
0x18006174b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061750  cmp     [rax+7CCh], edi
0x180061756  jz      short loc_180061770
0x180061758  mov     r9d, edi; int
0x18006175b  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180061762  mov     r8d, 6F4h; int
0x180061768  mov     rcx, rax; this
0x18006176b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061770  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061777  jb      short loc_18006179C
0x180061779  mov     edx, 0B4h
0x18006177e  mov     [rsp+70h+var_50], edi
0x180061782  mov     rcx, cs:WPP_GLOBAL_Control
0x180061789  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x180061790  mov     r9, rsi
0x180061793  mov     rcx, [rcx+10h]
0x180061797  call    WPP_SF_qD
0x18006179c  mov     rdi, [rbp+arg_20]
0x1800617a0  mov     rcx, [r12]
0x1800617a4  test    rcx, rcx
0x1800617a7  jz      short loc_1800617B9
0x1800617a9  mov     rax, [rcx]
0x1800617ac  mov     rax, [rax+10h]
0x1800617b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617b5  mov     [r12], r14
0x1800617b9  mov     rcx, [rdi]
0x1800617bc  test    rcx, rcx
0x1800617bf  jz      short loc_1800617D0
0x1800617c1  mov     rax, [rcx]
0x1800617c4  mov     rax, [rax+10h]
0x1800617c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617cd  mov     [rdi], r14
0x1800617d0  mov     rcx, [rbp+var_30]
0x1800617d4  test    rcx, rcx
0x1800617d7  jz      short loc_1800617E5
0x1800617d9  mov     rdx, [rcx]
0x1800617dc  mov     rax, [rdx+10h]
0x1800617e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617e5  lea     rcx, [rbp+arg_0]; this
0x1800617e9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800617ee  mov     eax, ebx
0x1800617f0  mov     rbx, [rsp+70h+arg_18]
0x1800617f8  add     rsp, 70h
0x1800617fc  pop     r15
0x1800617fe  pop     r14
0x180061800  pop     r13
0x180061802  pop     r12
0x180061804  pop     rdi
0x180061805  pop     rsi
0x180061806  pop     rbp
0x180061807  retn
0x180061809  test    rbx, rbx
0x18006180c  jnz     loc_1800618AE
0x180061812  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061819  mov     edi, 80004003h
0x18006181e  mov     ebx, edi
0x180061820  test    rcx, rcx
0x180061823  jnz     short loc_18006186C
0x180061825  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006182c  nop     dword ptr [rax+rax+00h]
0x180061831  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061838  mov     rcx, rax
0x18006183b  test    rax, rax
0x18006183e  jz      short loc_18006185E
0x180061840  mov     rax, [rax]
0x180061843  mov     edx, 7F0h
0x180061848  mov     rax, [rax+8]
0x18006184c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061851  test    eax, eax
0x180061853  jz      short loc_18006185E
0x180061855  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006185c  jmp     short loc_18006186C
0x18006185e  lea     rcx, qword_1801B97E0; this
0x180061865  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006186c  cmp     [rcx+8], r14b
0x180061870  jz      short loc_180061897
0x180061872  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061877  cmp     [rax+7CCh], edi
0x18006187d  jz      short loc_180061897
0x18006187f  mov     r9d, edi; int
0x180061882  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180061889  mov     r8d, 6F5h; int
0x18006188f  mov     rcx, rax; this
0x180061892  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061897  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006189e  jb      loc_18006179C
0x1800618a4  mov     edx, 0B5h
0x1800618a9  jmp     loc_18006177E
0x1800618ae  test    r12, r12
0x1800618b1  jnz     loc_180061953
0x1800618b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618be  mov     edi, 80004003h
0x1800618c3  mov     ebx, edi
0x1800618c5  test    rcx, rcx
0x1800618c8  jnz     short loc_180061911
0x1800618ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800618d1  nop     dword ptr [rax+rax+00h]
0x1800618d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618dd  mov     rcx, rax
0x1800618e0  test    rax, rax
0x1800618e3  jz      short loc_180061903
0x1800618e5  mov     rax, [rax]
0x1800618e8  mov     edx, 7F0h
0x1800618ed  mov     rax, [rax+8]
0x1800618f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618f6  test    eax, eax
0x1800618f8  jz      short loc_180061903
0x1800618fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061901  jmp     short loc_180061911
0x180061903  lea     rcx, qword_1801B97E0; this
0x18006190a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061911  cmp     [rcx+8], r14b
0x180061915  jz      short loc_18006193C
0x180061917  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006191c  cmp     [rax+7CCh], edi
0x180061922  jz      short loc_18006193C
0x180061924  mov     r9d, edi; int
0x180061927  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x18006192e  mov     r8d, 6F6h; int
0x180061934  mov     rcx, rax; this
0x180061937  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006193c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061943  jb      loc_18006179C
0x180061949  mov     edx, 0B6h
0x18006194e  jmp     loc_18006177E
0x180061953  mov     rdi, [rbp+arg_20]
0x180061957  test    rdi, rdi
0x18006195a  jnz     loc_1800619FC
0x180061960  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061967  mov     edi, 80004003h
0x18006196c  mov     ebx, edi
0x18006196e  test    rcx, rcx
0x180061971  jnz     short loc_1800619BA
0x180061973  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006197a  nop     dword ptr [rax+rax+00h]
0x18006197f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061986  mov     rcx, rax
0x180061989  test    rax, rax
0x18006198c  jz      short loc_1800619AC
0x18006198e  mov     rax, [rax]
0x180061991  mov     edx, 7F0h
0x180061996  mov     rax, [rax+8]
0x18006199a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006199f  test    eax, eax
0x1800619a1  jz      short loc_1800619AC
0x1800619a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800619aa  jmp     short loc_1800619BA
0x1800619ac  lea     rcx, qword_1801B97E0; this
0x1800619b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800619ba  cmp     [rcx+8], r14b
0x1800619be  jz      short loc_1800619E5
0x1800619c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800619c5  cmp     [rax+7CCh], edi
0x1800619cb  jz      short loc_1800619E5
0x1800619cd  mov     r9d, edi; int
0x1800619d0  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x1800619d7  mov     r8d, 6F7h; int
0x1800619dd  mov     rcx, rax; this
0x1800619e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800619e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800619ec  jb      loc_18006179C
0x1800619f2  mov     edx, 0B7h
0x1800619f7  jmp     loc_18006177E
0x1800619fc  mov     [r13+0], r14d
0x180061a00  mov     [rbx], r14d
0x180061a03  mov     [r12], r14
0x180061a07  mov     [rdi], r14
0x180061a0a  cmp     [rsi+48h], r14
0x180061a0e  jz      loc_1800622D2
0x180061a14  mov     rax, [r15+40h]
0x180061a18  cmp     dword ptr [rax+0B4h], 3
0x180061a1f  jnz     loc_1800622D2
0x180061a25  mov     r14d, [rax+70h]
0x180061a29  mov     [rbp+arg_0], r14d
0x180061a2d  test    r14d, r14d
0x180061a30  jnz     loc_180061AF1
0x180061a36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a3d  xor     r14d, r14d
0x180061a40  mov     ebx, 0C00D36BEh
0x180061a45  test    rcx, rcx
0x180061a48  jnz     short loc_180061A91
0x180061a4a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061a51  nop     dword ptr [rax+rax+00h]
0x180061a56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a5d  mov     rcx, rax
0x180061a60  test    rax, rax
0x180061a63  jz      short loc_180061A83
0x180061a65  mov     rax, [rax]
0x180061a68  mov     edx, 7F0h
0x180061a6d  mov     rax, [rax+8]
0x180061a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a76  test    eax, eax
0x180061a78  jz      short loc_180061A83
0x180061a7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a81  jmp     short loc_180061A91
0x180061a83  lea     rcx, qword_1801B97E0; this
0x180061a8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a91  cmp     [rcx+8], r14b
0x180061a95  jz      short loc_180061ABC
0x180061a97  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061a9c  cmp     [rax+7CCh], ebx
0x180061aa2  jz      short loc_180061ABC
0x180061aa4  mov     r9d, ebx; int
0x180061aa7  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180061aae  mov     r8d, 70Bh; int
0x180061ab4  mov     rcx, rax; this
0x180061ab7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061abc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180061ac3  jb      loc_1800617A0
0x180061ac9  mov     edx, 0B9h
0x180061ace  mov     rcx, cs:WPP_GLOBAL_Control
0x180061ad5  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x180061adc  mov     r9, rsi
0x180061adf  mov     [rsp+70h+var_50], ebx
0x180061ae3  mov     rcx, [rcx+10h]
0x180061ae7  call    WPP_SF_qD
0x180061aec  jmp     loc_1800617A0
0x180061af1  mov     rax, [rax+68h]
0x180061af5  xor     ebx, ebx
0x180061af7  mov     rdi, [rax]
0x180061afa  mov     rcx, rdi
0x180061afd  mov     rax, [rdi]
0x180061b00  mov     rax, [rax+8]
0x180061b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b09  test    eax, eax
0x180061b0b  jz      loc_180061DF8
0x180061b11  mov     rcx, rdi; this
0x180061b14  call    ?GetNumberOfStreams@CAVIIAVSStreamParser@@QEAAKXZ; CAVIIAVSStreamParser::GetNumberOfStreams(void)
0x180061b19  mov     r11d, eax
0x180061b1c  mov     [rbp+var_28], eax
0x180061b1f  lea     rax, [rdi+58h]
0x180061b23  lea     r10, [rdi+2B0h]
0x180061b2a  mov     [rbp+var_10], rax
0x180061b2e  lea     r9, [rdi+470h]
0x180061b35  mov     [rbp+var_8], r10
0x180061b39  mov     [rbp+var_18], r9
0x180061b3d  mov     edx, [rax+1B8h]
0x180061b43  mov     r8, rax
0x180061b46  cmp     edx, [r10+1B8h]
0x180061b4d  mov     eax, [r9+1B8h]
0x180061b54  cmovb   r8, r10
0x180061b58  sbb     r14d, r14d
0x180061b5b  neg     r14d
0x180061b5e  inc     r14d
0x180061b61  cmp     [r8+1B8h], eax
0x180061b68  jnb     short loc_180061B73
0x180061b6a  mov     r8, r9
0x180061b6d  mov     r14d, 3
0x180061b73  mov     rcx, [r8+1A8h]
0x180061b7a  test    rcx, rcx
0x180061b7d  jz      loc_180061F70
  ... truncated ...
```
