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
  __int64 v10; // r8
  __int64 v11; // r9
  char *v12; // rsi
  wchar_t *v13; // rcx
  int v14; // ebx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  struct IMFMediaType **v18; // rdi
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rax
  unsigned int v30; // r14d
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  CAVIIAVSStreamParser *v35; // rdi
  unsigned int NumberOfStreams; // r11d
  char *v37; // rax
  char *v38; // r10
  char *v39; // r9
  unsigned int v40; // edx
  char *v41; // r8
  int v42; // r14d
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // r13d
  unsigned int j; // edi
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 *v58; // rcx
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 i; // rdi
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 v67; // r13
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // rax
  struct IMFSample *v72; // rcx
  __int64 v73; // r8
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 k; // r8
  wchar_t *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  __int64 v80; // rdx
  wchar_t *v81; // rcx
  CallStackTracing *v82; // rax
  struct CallStackContext *v83; // rax
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // r9
  wchar_t *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r9
  wchar_t *v93; // rcx
  CallStackTracing *v94; // rax
  struct CallStackContext *v95; // rax
  wchar_t *v96; // rcx
  CallStackTracing *v97; // rax
  struct CallStackContext *v98; // rax
  __int64 v99; // [rsp+30h] [rbp-40h] BYREF
  int v100; // [rsp+38h] [rbp-38h] BYREF
  void *v101; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v102; // [rsp+48h] [rbp-28h]
  __int64 v103; // [rsp+50h] [rbp-20h] BYREF
  char *v104; // [rsp+58h] [rbp-18h]
  char *v105; // [rsp+60h] [rbp-10h]
  char *v106; // [rsp+68h] [rbp-8h]
  unsigned int v107; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int *v108; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int *v109; // [rsp+C0h] [rbp+50h]

  v109 = a3;
  v108 = a2;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v107, "CAVIMediaSourcePlugin::GetNextSample", 1772);
  v12 = (char *)this - 16;
  v100 = 0;
  v101 = 0;
  if ( !a2 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIMediaSourcePlugin::GetNextSample", 1780, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v17 = 180;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      (char *)this - 16,
      -2147467261);
LABEL_13:
    v18 = a5;
LABEL_14:
    if ( *a4 )
    {
      ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
      *a4 = 0;
    }
    if ( *v18 )
    {
      ((void (__fastcall *)(struct IMFMediaType *))(*v18)->lpVtbl->Release)(*v18);
      *v18 = 0;
    }
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v22, "CAVIMediaSourcePlugin::GetNextSample", 1781, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v17 = 181;
    goto LABEL_12;
  }
  if ( !a4 )
  {
    v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
      if ( *((_DWORD *)v25 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v25, "CAVIMediaSourcePlugin::GetNextSample", 1782, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v17 = 182;
    goto LABEL_12;
  }
  v18 = a5;
  if ( !a5 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v28 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v28, "CAVIMediaSourcePlugin::GetNextSample", 1783, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v17 = 183;
    goto LABEL_12;
  }
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *v18 = 0;
  if ( !*((_QWORD *)v12 + 9) || (v29 = *((_QWORD *)this + 8), *(_DWORD *)(v29 + 180) != 3) )
  {
    v96 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v97 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v97;
      if ( v97 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v97 + 8LL))(v97, 2032) )
      {
        v96 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v96 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v96 + 8) )
    {
      v98 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v96);
      if ( *((_DWORD *)v98 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v98, "CAVIMediaSourcePlugin::GetNextSample", 1792, -1072875854);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v34 = 184;
    goto LABEL_67;
  }
  v30 = *(_DWORD *)(v29 + 112);
  v107 = v30;
  if ( !v30 )
  {
    v31 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -1072875842;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
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
      v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)v33 + 499) != -1072875842 )
        CallStackContext::TraceFailure(v33, "CAVIMediaSourcePlugin::GetNextSample", 1803, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v34 = 185;
    goto LABEL_67;
  }
  v14 = 0;
  v35 = **(CAVIIAVSStreamParser ***)(v29 + 104);
  if ( !(*(unsigned int (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)v35 + 8LL))(v35) )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v30 )
        goto LABEL_135;
      v63 = *((_QWORD *)this + 7);
      v99 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64 *))(*(_QWORD *)v63 + 272LL))(
              v63,
              (unsigned int)i,
              &v100,
              &v99);
      if ( v14 < 0 )
        break;
      if ( v100 )
      {
        v67 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 104LL) + 8 * i);
        v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v99 + 264LL))(v99, v109);
        if ( v14 < 0 )
        {
          v77 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69, v70);
            CallStackTracing::s_wpInstance = v78;
            if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
            {
              v77 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v77 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v77 + 8) )
          {
            v79 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
            if ( *((_DWORD *)v79 + 499) != v14 )
              CallStackContext::TraceFailure(v79, "CAVIMediaSourcePlugin::GetNextSample", 1870, v14);
          }
          if ( g_wppLevels )
          {
            v80 = 189;
LABEL_151:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v80,
              &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
              (char *)this - 16,
              v14);
            goto LABEL_152;
          }
          goto LABEL_152;
        }
        if ( *((_DWORD *)v12 + 170) == 1 )
        {
          v71 = *((_QWORD *)this + 82);
          if ( v71 )
          {
            if ( *(_QWORD *)(v71 + 24 * i) && *(_DWORD *)(v71 + 24 * i + 16) )
            {
              _mm_lfence();
              v72 = *(struct IMFSample **)(*((_QWORD *)this + 82) + 24 * i);
              *a4 = v72;
              ((void (__fastcall *)(struct IMFSample *))v72->lpVtbl->AddRef)(v72);
              v73 = 0;
              if ( *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i + 8) - 500000LL >= 0 )
                v73 = *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i + 8) - 500000LL;
              ((void (__fastcall *)(_QWORD, __int64))(*a4)->lpVtbl->SetSampleTime)(*a4, v73);
              if ( *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i) )
              {
                _mm_lfence();
                v74 = *(_QWORD *)(*((_QWORD *)this + 82) + 24 * i);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
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
        if ( (unsigned int)CVPtrList::RemoveHead((CVPtrList *)(v67 + 88), &v101) )
        {
          *a4 = (struct IMFSample *)v101;
          v101 = 0;
LABEL_133:
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v99);
          goto LABEL_134;
        }
        v30 = v107;
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v99);
    }
    v81 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v82 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65, v66);
      CallStackTracing::s_wpInstance = v82;
      if ( v82 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v82 + 8LL))(v82, 2032) )
      {
        v81 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v81 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v81 + 8) )
    {
      v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v81);
      if ( *((_DWORD *)v83 + 499) != v14 )
        CallStackContext::TraceFailure(v83, "CAVIMediaSourcePlugin::GetNextSample", 1864, v14);
    }
    if ( g_wppLevels )
    {
      v80 = 188;
      goto LABEL_151;
    }
LABEL_152:
    v58 = &v99;
LABEL_104:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v58);
    goto LABEL_13;
  }
  NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v35);
  v102 = NumberOfStreams;
  v37 = (char *)v35 + 88;
  v38 = (char *)v35 + 688;
  v105 = (char *)v35 + 88;
  v39 = (char *)v35 + 1136;
  v106 = (char *)v35 + 688;
  v104 = (char *)v35 + 1136;
  while ( 1 )
  {
    v40 = *((_DWORD *)v37 + 110);
    v41 = v37;
    if ( v40 < *((_DWORD *)v38 + 110) )
      v41 = v38;
    v42 = (v40 < *((_DWORD *)v38 + 110)) + 1;
    if ( *((_DWORD *)v41 + 110) < *((_DWORD *)v39 + 110) )
    {
      v41 = v39;
      v42 = 3;
    }
    v43 = *((_QWORD *)v41 + 53);
    if ( !v43 )
      break;
    v101 = *(void **)v43;
    v44 = *(_QWORD *)(v43 + 8);
    *((_QWORD *)v41 + 53) = v44;
    if ( v44 )
      *(_QWORD *)(v44 + 16) = 0;
    else
      *((_QWORD *)v41 + 54) = 0;
    v45 = 0;
    *(_QWORD *)(v43 + 8) = *(_QWORD *)v41;
    *(_QWORD *)v41 = v43;
    --*((_DWORD *)v41 + 110);
    for ( j = 0; j < NumberOfStreams; ++j )
    {
      v47 = *((_QWORD *)this + 7);
      v103 = 0;
      LODWORD(v99) = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64 *))(*(_QWORD *)v47 + 272LL))(
              v47,
              j,
              &v100,
              &v103);
      if ( v14 < 0 )
      {
        v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49, v50);
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
          if ( *((_DWORD *)v61 + 499) != v14 )
            CallStackContext::TraceFailure(v61, "CAVIMediaSourcePlugin::GetNextSample", 1826, v14);
        }
        if ( g_wppLevels )
        {
          v57 = 186;
LABEL_102:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v57,
            &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
            (char *)this - 16,
            v14);
        }
LABEL_103:
        v58 = &v103;
        goto LABEL_104;
      }
      v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v103 + 264LL))(v103, &v99);
      if ( v14 < 0 )
      {
        v54 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
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
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != v14 )
            CallStackContext::TraceFailure(v56, "CAVIMediaSourcePlugin::GetNextSample", 1827, v14);
        }
        if ( g_wppLevels )
        {
          v57 = 187;
          goto LABEL_102;
        }
        goto LABEL_103;
      }
      if ( (_DWORD)v99 == v42 )
      {
        if ( v100 )
        {
          *v109 = v99;
          *a4 = (struct IMFSample *)v101;
          v101 = 0;
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v103);
          goto LABEL_89;
        }
        v45 = 1;
        ComSmartPtr<IUnknown>::Release(&v101);
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v103);
      NumberOfStreams = v102;
    }
    if ( !v45 )
    {
      ComSmartPtr<IUnknown>::Release(&v101);
LABEL_89:
      NumberOfStreams = v102;
    }
    if ( *a4 )
      break;
    v39 = v104;
    v37 = v105;
    v38 = v106;
  }
LABEL_134:
  v30 = v107;
LABEL_135:
  v75 = (__int64)*a4;
  if ( *a4 )
  {
    LODWORD(v108) = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, unsigned int **))(*(_QWORD *)v75 + 312LL))(v75, &v108);
    if ( v14 < 0 )
    {
      v87 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v84, v85, v86);
        CallStackTracing::s_wpInstance = v88;
        if ( v88 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(v88, 2032) )
        {
          v87 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v87 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v87 + 8) )
      {
        v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v87);
        if ( *((_DWORD *)v89 + 499) != v14 )
          CallStackContext::TraceFailure(v89, "CAVIMediaSourcePlugin::GetNextSample", 1920, v14);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          191,
          &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
          (char *)this - 16,
          v14);
      goto LABEL_13;
    }
    if ( (_DWORD)v108 )
      goto LABEL_18;
    v18 = a5;
    v14 = ((__int64 (__fastcall *)(_QWORD, void *, GUID *, struct IMFMediaType **))(*a4)->lpVtbl->GetUnknown)(
            *a4,
            &AVI_SAMPLE_ATTRIBUTE_FORMATCHANGE_MEDIATYPE,
            &IID_IMFMediaType,
            a5);
    if ( v14 >= 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
      goto LABEL_18;
    }
    v93 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v94 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v90, v91, v92);
      CallStackTracing::s_wpInstance = v94;
      if ( v94 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v94 + 8LL))(v94, 2032) )
      {
        v93 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v93 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v93 + 8) )
    {
      v95 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v93);
      if ( *((_DWORD *)v95 + 499) != v14 )
        CallStackContext::TraceFailure(v95, "CAVIMediaSourcePlugin::GetNextSample", 1926, v14);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v34 = 192;
LABEL_67:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v34,
      &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
      (char *)this - 16,
      v14);
    goto LABEL_14;
  }
  for ( k = 0; (unsigned int)k < v30; k = (unsigned int)(k + 1) )
  {
    if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 104LL) + 8 * k) + 80LL) )
      goto LABEL_18;
  }
  *v108 = 1;
LABEL_18:
  if ( v101 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v101 + 16LL))(v101);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v107);
  return (unsigned int)v14;
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
