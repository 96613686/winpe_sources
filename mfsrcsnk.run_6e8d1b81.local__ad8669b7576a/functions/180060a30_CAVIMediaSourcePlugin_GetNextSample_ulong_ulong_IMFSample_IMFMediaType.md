# CAVIMediaSourcePlugin::GetNextSample(ulong *,ulong *,IMFSample * *,IMFMediaType * *)

- ea: `0x180060a30`
- end: `0x1800616c3`
- name: `?GetNextSample@CAVIMediaSourcePlugin@@UEAAJPEAK0PEAPEAUIMFSample@@PEAPEAUIMFMediaType@@@Z`
- size: `3219`
- prototype: `__int64 __fastcall(CAVIMediaSourcePlugin *__hidden this, unsigned int *, unsigned int *, struct IMFSample **, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007214`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18003fe50`
- `0x180060a30`
- `0x180073b14`
- `0x180074814`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060a9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060bbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060c5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060d00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060dd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061035`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800610ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006133e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800613ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800614bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006158a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061640`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060a9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060bbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060c5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060d00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180060dd1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061035`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800610ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006133e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800613ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800614bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006158a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061640`

## string_xrefs

- `0x180060a5a`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180060af5`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180060c15`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180060cb4`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180060d57`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180060e28`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x18006108c`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061141`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061395`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061445`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061512`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x1800615e1`: `CAVIMediaSourcePlugin::GetNextSample`
- `0x180061697`: `CAVIMediaSourcePlugin::GetNextSample`

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
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v18 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v24 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v82 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v29 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v67 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
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
        v71 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v53 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v48 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v75 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v79 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x180060a30  mov     [rsp-38h+arg_18], rbx
0x180060a35  mov     [rsp-38h+arg_10], r8
0x180060a3a  mov     [rsp-38h+arg_8], rdx
0x180060a3f  push    rbp
0x180060a40  push    rsi
0x180060a41  push    rdi
0x180060a42  push    r12
0x180060a44  push    r13
0x180060a46  push    r14
0x180060a48  push    r15
0x180060a4a  mov     rbp, rsp
0x180060a4d  sub     rsp, 70h
0x180060a51  mov     rbx, r8
0x180060a54  mov     r13, rdx
0x180060a57  mov     r15, rcx
0x180060a5a  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180060a61  mov     r8d, 6ECh; int
0x180060a67  lea     rcx, [rbp+arg_0]; this
0x180060a6b  mov     r12, r9
0x180060a6e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180060a73  xor     r14d, r14d
0x180060a76  lea     rsi, [r15-10h]
0x180060a7a  mov     [rbp+var_38], r14d
0x180060a7e  mov     [rbp+var_30], r14
0x180060a82  test    r13, r13
0x180060a85  jnz     loc_180060BA2
0x180060a8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060a92  mov     edi, 80004003h
0x180060a97  mov     ebx, edi
0x180060a99  test    rcx, rcx
0x180060a9c  jnz     short loc_180060ADF
0x180060a9e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060aa4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060aab  mov     rcx, rax
0x180060aae  test    rax, rax
0x180060ab1  jz      short loc_180060AD1
0x180060ab3  mov     rax, [rax]
0x180060ab6  mov     edx, 7F0h
0x180060abb  mov     rax, [rax+8]
0x180060abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060ac4  test    eax, eax
0x180060ac6  jz      short loc_180060AD1
0x180060ac8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060acf  jmp     short loc_180060ADF
0x180060ad1  lea     rcx, qword_1801B07E0; this
0x180060ad8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060adf  cmp     [rcx+8], r14b
0x180060ae3  jz      short loc_180060B0A
0x180060ae5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060aea  cmp     [rax+7CCh], edi
0x180060af0  jz      short loc_180060B0A
0x180060af2  mov     r9d, edi; int
0x180060af5  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180060afc  mov     r8d, 6F4h; int
0x180060b02  mov     rcx, rax; this
0x180060b05  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060b0a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060b11  jb      short loc_180060B36
0x180060b13  mov     edx, 0B4h
0x180060b18  mov     [rsp+70h+var_50], edi
0x180060b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060b23  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x180060b2a  mov     r9, rsi
0x180060b2d  mov     rcx, [rcx+10h]
0x180060b31  call    WPP_SF_qD
0x180060b36  mov     rdi, [rbp+arg_20]
0x180060b3a  mov     rcx, [r12]
0x180060b3e  test    rcx, rcx
0x180060b41  jz      short loc_180060B53
0x180060b43  mov     rax, [rcx]
0x180060b46  mov     rax, [rax+10h]
0x180060b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b4f  mov     [r12], r14
0x180060b53  mov     rcx, [rdi]
0x180060b56  test    rcx, rcx
0x180060b59  jz      short loc_180060B6A
0x180060b5b  mov     rax, [rcx]
0x180060b5e  mov     rax, [rax+10h]
0x180060b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b67  mov     [rdi], r14
0x180060b6a  mov     rcx, [rbp+var_30]
0x180060b6e  test    rcx, rcx
0x180060b71  jz      short loc_180060B7F
0x180060b73  mov     rdx, [rcx]
0x180060b76  mov     rax, [rdx+10h]
0x180060b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b7f  lea     rcx, [rbp+arg_0]; this
0x180060b83  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180060b88  mov     eax, ebx
0x180060b8a  mov     rbx, [rsp+70h+arg_18]
0x180060b92  add     rsp, 70h
0x180060b96  pop     r15
0x180060b98  pop     r14
0x180060b9a  pop     r13
0x180060b9c  pop     r12
0x180060b9e  pop     rdi
0x180060b9f  pop     rsi
0x180060ba0  pop     rbp
0x180060ba1  retn
0x180060ba2  test    rbx, rbx
0x180060ba5  jnz     loc_180060C41
0x180060bab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060bb2  mov     edi, 80004003h
0x180060bb7  mov     ebx, edi
0x180060bb9  test    rcx, rcx
0x180060bbc  jnz     short loc_180060BFF
0x180060bbe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060bc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060bcb  mov     rcx, rax
0x180060bce  test    rax, rax
0x180060bd1  jz      short loc_180060BF1
0x180060bd3  mov     rax, [rax]
0x180060bd6  mov     edx, 7F0h
0x180060bdb  mov     rax, [rax+8]
0x180060bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060be4  test    eax, eax
0x180060be6  jz      short loc_180060BF1
0x180060be8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060bef  jmp     short loc_180060BFF
0x180060bf1  lea     rcx, qword_1801B07E0; this
0x180060bf8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060bff  cmp     [rcx+8], r14b
0x180060c03  jz      short loc_180060C2A
0x180060c05  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060c0a  cmp     [rax+7CCh], edi
0x180060c10  jz      short loc_180060C2A
0x180060c12  mov     r9d, edi; int
0x180060c15  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180060c1c  mov     r8d, 6F5h; int
0x180060c22  mov     rcx, rax; this
0x180060c25  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060c2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060c31  jb      loc_180060B36
0x180060c37  mov     edx, 0B5h
0x180060c3c  jmp     loc_180060B18
0x180060c41  test    r12, r12
0x180060c44  jnz     loc_180060CE0
0x180060c4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060c51  mov     edi, 80004003h
0x180060c56  mov     ebx, edi
0x180060c58  test    rcx, rcx
0x180060c5b  jnz     short loc_180060C9E
0x180060c5d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060c63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060c6a  mov     rcx, rax
0x180060c6d  test    rax, rax
0x180060c70  jz      short loc_180060C90
0x180060c72  mov     rax, [rax]
0x180060c75  mov     edx, 7F0h
0x180060c7a  mov     rax, [rax+8]
0x180060c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c83  test    eax, eax
0x180060c85  jz      short loc_180060C90
0x180060c87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060c8e  jmp     short loc_180060C9E
0x180060c90  lea     rcx, qword_1801B07E0; this
0x180060c97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060c9e  cmp     [rcx+8], r14b
0x180060ca2  jz      short loc_180060CC9
0x180060ca4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060ca9  cmp     [rax+7CCh], edi
0x180060caf  jz      short loc_180060CC9
0x180060cb1  mov     r9d, edi; int
0x180060cb4  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180060cbb  mov     r8d, 6F6h; int
0x180060cc1  mov     rcx, rax; this
0x180060cc4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060cc9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060cd0  jb      loc_180060B36
0x180060cd6  mov     edx, 0B6h
0x180060cdb  jmp     loc_180060B18
0x180060ce0  mov     rdi, [rbp+arg_20]
0x180060ce4  test    rdi, rdi
0x180060ce7  jnz     loc_180060D83
0x180060ced  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060cf4  mov     edi, 80004003h
0x180060cf9  mov     ebx, edi
0x180060cfb  test    rcx, rcx
0x180060cfe  jnz     short loc_180060D41
0x180060d00  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060d06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d0d  mov     rcx, rax
0x180060d10  test    rax, rax
0x180060d13  jz      short loc_180060D33
0x180060d15  mov     rax, [rax]
0x180060d18  mov     edx, 7F0h
0x180060d1d  mov     rax, [rax+8]
0x180060d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d26  test    eax, eax
0x180060d28  jz      short loc_180060D33
0x180060d2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d31  jmp     short loc_180060D41
0x180060d33  lea     rcx, qword_1801B07E0; this
0x180060d3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060d41  cmp     [rcx+8], r14b
0x180060d45  jz      short loc_180060D6C
0x180060d47  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060d4c  cmp     [rax+7CCh], edi
0x180060d52  jz      short loc_180060D6C
0x180060d54  mov     r9d, edi; int
0x180060d57  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180060d5e  mov     r8d, 6F7h; int
0x180060d64  mov     rcx, rax; this
0x180060d67  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060d6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060d73  jb      loc_180060B36
0x180060d79  mov     edx, 0B7h
0x180060d7e  jmp     loc_180060B18
0x180060d83  mov     [r13+0], r14d
0x180060d87  mov     [rbx], r14d
0x180060d8a  mov     [r12], r14
0x180060d8e  mov     [rdi], r14
0x180060d91  cmp     [rsi+48h], r14
0x180060d95  jz      loc_18006162F
0x180060d9b  mov     rax, [r15+40h]
0x180060d9f  cmp     dword ptr [rax+0B4h], 3
0x180060da6  jnz     loc_18006162F
0x180060dac  mov     r14d, [rax+70h]
0x180060db0  mov     [rbp+arg_0], r14d
0x180060db4  test    r14d, r14d
0x180060db7  jnz     loc_180060E72
0x180060dbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060dc4  xor     r14d, r14d
0x180060dc7  mov     ebx, 0C00D36BEh
0x180060dcc  test    rcx, rcx
0x180060dcf  jnz     short loc_180060E12
0x180060dd1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180060dd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180060dde  mov     rcx, rax
0x180060de1  test    rax, rax
0x180060de4  jz      short loc_180060E04
0x180060de6  mov     rax, [rax]
0x180060de9  mov     edx, 7F0h
0x180060dee  mov     rax, [rax+8]
0x180060df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060df7  test    eax, eax
0x180060df9  jz      short loc_180060E04
0x180060dfb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180060e02  jmp     short loc_180060E12
0x180060e04  lea     rcx, qword_1801B07E0; this
0x180060e0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180060e12  cmp     [rcx+8], r14b
0x180060e16  jz      short loc_180060E3D
0x180060e18  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180060e1d  cmp     [rax+7CCh], ebx
0x180060e23  jz      short loc_180060E3D
0x180060e25  mov     r9d, ebx; int
0x180060e28  lea     rdx, aCavimediasourc_17; "CAVIMediaSourcePlugin::GetNextSample"
0x180060e2f  mov     r8d, 70Bh; int
0x180060e35  mov     rcx, rax; this
0x180060e38  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180060e3d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180060e44  jb      loc_180060B3A
0x180060e4a  mov     edx, 0B9h
0x180060e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180060e56  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x180060e5d  mov     r9, rsi
0x180060e60  mov     [rsp+70h+var_50], ebx
0x180060e64  mov     rcx, [rcx+10h]
0x180060e68  call    WPP_SF_qD
0x180060e6d  jmp     loc_180060B3A
0x180060e72  mov     rax, [rax+68h]
0x180060e76  xor     ebx, ebx
0x180060e78  mov     rdi, [rax]
0x180060e7b  mov     rcx, rdi
0x180060e7e  mov     rax, [rdi]
0x180060e81  mov     rax, [rax+8]
0x180060e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060e8a  test    eax, eax
0x180060e8c  jz      loc_18006116D
0x180060e92  mov     rcx, rdi; this
0x180060e95  call    ?GetNumberOfStreams@CAVIIAVSStreamParser@@QEAAKXZ; CAVIIAVSStreamParser::GetNumberOfStreams(void)
0x180060e9a  mov     r11d, eax
0x180060e9d  mov     [rbp+var_28], eax
0x180060ea0  lea     rax, [rdi+58h]
0x180060ea4  lea     r10, [rdi+2B0h]
0x180060eab  mov     [rbp+var_10], rax
0x180060eaf  lea     r9, [rdi+470h]
0x180060eb6  mov     [rbp+var_8], r10
0x180060eba  mov     [rbp+var_18], r9
0x180060ebe  mov     edx, [rax+1B8h]
0x180060ec4  mov     r8, rax
0x180060ec7  cmp     edx, [r10+1B8h]
0x180060ece  mov     eax, [r9+1B8h]
0x180060ed5  cmovb   r8, r10
0x180060ed9  sbb     r14d, r14d
0x180060edc  neg     r14d
0x180060edf  inc     r14d
0x180060ee2  cmp     [r8+1B8h], eax
0x180060ee9  jnb     short loc_180060EF4
0x180060eeb  mov     r8, r9
0x180060eee  mov     r14d, 3
0x180060ef4  mov     rcx, [r8+1A8h]
0x180060efb  test    rcx, rcx
0x180060efe  jz      loc_1800612E5
0x180060f04  mov     rax, [rcx]
0x180060f07  mov     [rbp+var_30], rax
0x180060f0b  mov     rax, [rcx+8]
0x180060f0f  mov     [r8+1A8h], rax
0x180060f16  test    rax, rax
  ... truncated ...
```
