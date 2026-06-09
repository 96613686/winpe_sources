# CAVIVideoStreamParser::TransformFirstSample(IMFSample *,IMFSample * *)

- ea: `0x18013c010`
- end: `0x18013ccdf`
- name: `?TransformFirstSample@CAVIVideoStreamParser@@UEAAJPEAUIMFSample@@PEAPEAU2@@Z`
- size: `3279`
- prototype: `__int64 __fastcall(const void **this, struct IMFSample *, struct IMFSample **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180060768`
- `0x18006cdb8`
- `0x180073b14`
- `0x180139490`
- `0x18013af88`
- `0x18013c010`
- `0x180163cac`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c091`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c1bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c27d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c421`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c4c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c61c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c6f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c806`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c8be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c955`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013caa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013cb4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013cc04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c091`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c1bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c27d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c332`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c421`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c4c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c61c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c6f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c806`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c8be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013c955`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013caa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013cb4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013cc04`
- `MFPlat!MFCreateMemoryBuffer` at `0x18013c261`
- `MFPlat!MFCreateMemoryBuffer` at `0x18013c261`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18013c7e7`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18013c89f`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18013c7e7`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x18013c89f`
- `MFPlat!MFCreateSample` at `0x18013c4a4`
- `MFPlat!MFCreateSample` at `0x18013c4a4`

## pseudocode

```c
__int64 __fastcall CAVIVideoStreamParser::TransformFirstSample(
        const void **this,
        struct IMFSample *a2,
        struct IMFSample **a3)
{
  __int64 v6; // rdx
  HRESULT Sample; // ebx
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  DWORD v12; // ecx
  DWORD v13; // r12d
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  int v31; // r8d
  int v32; // r9d
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  HRESULT (__stdcall *ConvertToContiguousBuffer)(IMFSample *, IMFMediaBuffer **); // rax
  __int64 v42; // rdx
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 NextStartCode; // rax
  __int64 v52; // rax
  __int64 v53; // rdx
  int v54; // r12d
  DWORD v55; // r15d
  __int64 v56; // rdx
  wchar_t *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rdx
  wchar_t *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  wchar_t *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 v68; // rdx
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rdx
  wchar_t *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 v76; // rdx
  wchar_t *v77; // rcx
  CallStackTracing *v78; // rax
  struct CallStackContext *v79; // rax
  int v81; // [rsp+20h] [rbp-50h]
  int v82; // [rsp+30h] [rbp-40h] BYREF
  int v83; // [rsp+34h] [rbp-3Ch] BYREF
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-38h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+40h] [rbp-30h] BYREF
  IMFMediaBuffer *v86; // [rsp+48h] [rbp-28h] BYREF
  IMFMediaBuffer *v87; // [rsp+50h] [rbp-20h] BYREF
  IMFMediaBuffer *pBuffer; // [rsp+58h] [rbp-18h] BYREF
  void *v89[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v90; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v91; // [rsp+C8h] [rbp+58h] BYREF

  pBuffer = 0;
  if ( !this[84] && !this[82] )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v90,
      "CAVIVideoStreamParser::TransformFirstSample",
      219);
    Sample = CAVIStreamParser::TransformFirstSample((CAVIStreamParser *)this, a2, a3);
    if ( Sample < 0 )
    {
      v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Sample )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CAVIVideoStreamParser::TransformFirstSample",
            219,
            Sample);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids,
          this,
          Sample);
    }
    goto LABEL_186;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v90,
    "CAVIVideoStreamParser::TransformFirstSample",
    223);
  if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
  {
    v81 = *((_DWORD *)this + 170);
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      25,
      &WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids,
      *((unsigned int *)this + 166));
  }
  v12 = *((_DWORD *)this + 166);
  ppIMFSample = 0;
  ppBuffer = 0;
  v89[0] = 0;
  v83 = 0;
  v91 = 0;
  v13 = v12 + *((_DWORD *)this + 170);
  if ( v13 < v12 )
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    Sample = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v16, "CAVIVideoStreamParser::TransformFirstSample", 232, -2147024362);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids,
        this,
        -2147024362);
    goto LABEL_185;
  }
  Sample = MFCreateMemoryBuffer(v13, &ppBuffer);
  if ( Sample < 0 )
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
      if ( *((_DWORD *)v20 + 499) != Sample )
        CallStackContext::TraceFailure(v20, "CAVIVideoStreamParser::TransformFirstSample", 233, Sample);
    }
    if ( !g_wppLevels )
      goto LABEL_185;
    v21 = 27;
    goto LABEL_39;
  }
  Sample = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, int *, unsigned int *))ppBuffer->lpVtbl->Lock)(
             ppBuffer,
             v89,
             &v83,
             &v91);
  if ( Sample < 0 )
  {
    v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
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
      if ( *((_DWORD *)v25 + 499) != Sample )
        CallStackContext::TraceFailure(v25, "CAVIVideoStreamParser::TransformFirstSample", 235, Sample);
    }
    if ( !g_wppLevels )
      goto LABEL_185;
    v21 = 28;
    goto LABEL_39;
  }
  memcpy_0(v89[0], this[84], *((unsigned int *)this + 170));
  memcpy_0((char *)v89[0] + *((unsigned int *)this + 170), this[82], *((unsigned int *)this + 166));
  ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
  Sample = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer, v13);
  if ( Sample < 0 )
  {
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
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
      if ( *((_DWORD *)v29 + 499) != Sample )
        CallStackContext::TraceFailure(v29, "CAVIVideoStreamParser::TransformFirstSample", 242, Sample);
    }
    if ( !g_wppLevels )
      goto LABEL_185;
    v21 = 29;
    goto LABEL_39;
  }
  Sample = MFCreateSample(&ppIMFSample);
  if ( Sample < 0 )
  {
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
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
      if ( *((_DWORD *)v35 + 499) != Sample )
        CallStackContext::TraceFailure(v35, "CAVIVideoStreamParser::TransformFirstSample", 244, Sample);
    }
    if ( !g_wppLevels )
      goto LABEL_185;
    v21 = 30;
    goto LABEL_39;
  }
  Sample = MFCopySampleProperties(ppIMFSample, a2, v31, v32, v81);
  if ( Sample < 0 )
  {
    v37 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
      if ( *((_DWORD *)v39 + 499) != Sample )
        CallStackContext::TraceFailure(v39, "CAVIVideoStreamParser::TransformFirstSample", 251, Sample);
    }
    if ( !g_wppLevels )
      goto LABEL_185;
    v21 = 31;
LABEL_39:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids, this, Sample);
LABEL_185:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
LABEL_186:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v90);
    goto LABEL_187;
  }
  lpVtbl = a2->lpVtbl;
  v90 = 0;
  v82 = 0;
  v87 = 0;
  ConvertToContiguousBuffer = lpVtbl->ConvertToContiguousBuffer;
  v86 = 0;
  Sample = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer **))ConvertToContiguousBuffer)(a2, &pBuffer);
  if ( Sample < 0 )
  {
    v43 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
      CallStackTracing::s_wpInstance = v44;
      if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v43 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v43 + 8) )
    {
      v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
      if ( *((_DWORD *)v45 + 499) != Sample )
        CallStackContext::TraceFailure(v45, "CAVIVideoStreamParser::TransformFirstSample", 260, Sample);
    }
    if ( !g_wppLevels )
      goto LABEL_96;
    v46 = 32;
LABEL_95:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v46, &WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids, this, Sample);
LABEL_96:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v86);
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v87);
    goto LABEL_185;
  }
  Sample = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, int *, unsigned int *))pBuffer->lpVtbl->Lock)(
             pBuffer,
             v89,
             &v83,
             &v91);
  if ( Sample < 0 )
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
      if ( *((_DWORD *)v50 + 499) != Sample )
        CallStackContext::TraceFailure(v50, "CAVIVideoStreamParser::TransformFirstSample", 261, Sample);
    }
    if ( !g_wppLevels )
      goto LABEL_96;
    v46 = 33;
    goto LABEL_95;
  }
  NextStartCode = anonymous_namespace_::FindNextStartCode(v89[0], v91, &v90, &v82);
  if ( !NextStartCode || v82 != 9 )
  {
    ComSmartPtr<IMFMediaBuffer>::operator=(&v86, &pBuffer);
    goto LABEL_149;
  }
  v52 = anonymous_namespace_::FindNextStartCode(
          NextStartCode + v90,
          v91 + LODWORD(v89[0]) - (_DWORD)NextStartCode - v90,
          &v90,
          &v82);
  v54 = v52;
  if ( !v52 )
  {
    ComSmartPtr<IMFMediaBuffer>::operator=(&v87, &pBuffer);
    goto LABEL_149;
  }
  v55 = v52 - LODWORD(v89[0]);
  if ( v52 - (unsigned __int64)v89[0] > 0xFFFFFFFF )
  {
    v65 = (wchar_t *)CallStackTracing::s_wpInstance;
    Sample = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
      CallStackTracing::s_wpInstance = v66;
      if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
      {
        v65 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v65 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v65 + 8) )
    {
      v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
      if ( *((_DWORD *)v67 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v67, "CAVIVideoStreamParser::TransformFirstSample", 274, -2147024362);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids,
        this,
        -2147024362);
    goto LABEL_145;
  }
  Sample = MFCreateMediaBufferWrapper(pBuffer, 0, v55, &v87);
  if ( Sample >= 0 )
  {
    Sample = MFCreateMediaBufferWrapper(pBuffer, v54 - LODWORD(v89[0]), v91 - v55, &v86);
    if ( Sample < 0 )
    {
      v62 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61);
        CallStackTracing::s_wpInstance = v63;
        if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
        {
          v62 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v62 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v62 + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
        if ( *((_DWORD *)v64 + 499) != Sample )
          CallStackContext::TraceFailure(v64, "CAVIVideoStreamParser::TransformFirstSample", 276, Sample);
      }
      if ( !g_wppLevels )
        goto LABEL_145;
      v60 = 36;
      goto LABEL_123;
    }
LABEL_149:
    ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
    if ( v87
      && (Sample = ((__int64 (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample), Sample < 0) )
    {
      v69 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68);
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
        if ( *((_DWORD *)v71 + 499) != Sample )
          CallStackContext::TraceFailure(v71, "CAVIVideoStreamParser::TransformFirstSample", 295, Sample);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v46 = 37;
    }
    else
    {
      Sample = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                 ppIMFSample,
                 ppBuffer);
      if ( Sample >= 0 )
      {
        if ( !v86
          || (Sample = ((__int64 (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample), Sample >= 0) )
        {
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v86);
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v87);
          *a3 = ppIMFSample;
          ppIMFSample = 0;
          goto LABEL_185;
        }
        v77 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76);
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
          if ( *((_DWORD *)v79 + 499) != Sample )
            CallStackContext::TraceFailure(v79, "CAVIVideoStreamParser::TransformFirstSample", 300, Sample);
        }
        if ( !g_wppLevels )
          goto LABEL_96;
        v46 = 39;
      }
      else
      {
        v73 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v72);
          CallStackTracing::s_wpInstance = v74;
          if ( v74 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
          {
            v73 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v73 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v73 + 8) )
        {
          v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
          if ( *((_DWORD *)v75 + 499) != Sample )
            CallStackContext::TraceFailure(v75, "CAVIVideoStreamParser::TransformFirstSample", 297, Sample);
        }
        if ( !g_wppLevels )
          goto LABEL_96;
        v46 = 38;
      }
    }
    goto LABEL_95;
  }
  v57 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56);
    CallStackTracing::s_wpInstance = v58;
    if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
    {
      v57 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v57 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v57 + 8) )
  {
    v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
    if ( *((_DWORD *)v59 + 499) != Sample )
      CallStackContext::TraceFailure(v59, "CAVIVideoStreamParser::TransformFirstSample", 275, Sample);
  }
  if ( !g_wppLevels )
    goto LABEL_145;
  v60 = 35;
LABEL_123:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v60, &WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids, this, Sample);
LABEL_145:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v86);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v87);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v90);
  if ( pBuffer )
    ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
LABEL_187:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pBuffer);
  return (unsigned int)Sample;
}

```

## disassembly

```asm
0x18013c010  mov     [rsp-38h+arg_8], rbx
0x18013c015  push    rbp
0x18013c016  push    rsi
0x18013c017  push    rdi
0x18013c018  push    r12
0x18013c01a  push    r13
0x18013c01c  push    r14
0x18013c01e  push    r15
0x18013c020  mov     rbp, rsp
0x18013c023  sub     rsp, 70h
0x18013c027  xor     r12d, r12d
0x18013c02a  mov     r13, r8
0x18013c02d  mov     r15, rdx
0x18013c030  mov     rdi, rcx
0x18013c033  mov     [rbp+pBuffer], r12
0x18013c037  cmp     [rcx+2A0h], r12
0x18013c03e  jnz     loc_18013C12B
0x18013c044  cmp     [rcx+290h], r12
0x18013c04b  jnz     loc_18013C12B
0x18013c051  mov     r14d, 0DBh
0x18013c057  lea     rsi, aCavivideostrea_5; "CAVIVideoStreamParser::TransformFirstSa"...
0x18013c05e  mov     r8d, r14d; int
0x18013c061  lea     rcx, [rbp+arg_0]; this
0x18013c065  mov     rdx, rsi; char *
0x18013c068  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18013c06d  mov     r8, r13; struct IMFSample **
0x18013c070  mov     rdx, r15; struct IMFSample *
0x18013c073  mov     rcx, rdi; this
0x18013c076  call    ?TransformFirstSample@CAVIStreamParser@@UEAAJPEAUIMFSample@@PEAPEAU2@@Z; CAVIStreamParser::TransformFirstSample(IMFSample *,IMFSample * *)
0x18013c07b  mov     ebx, eax
0x18013c07d  test    eax, eax
0x18013c07f  jns     loc_18013CCB3
0x18013c085  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c08c  test    rcx, rcx
0x18013c08f  jnz     short loc_18013C0D2
0x18013c091  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013c097  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c09e  mov     rcx, rax
0x18013c0a1  test    rax, rax
0x18013c0a4  jz      short loc_18013C0C4
0x18013c0a6  mov     rax, [rax]
0x18013c0a9  mov     edx, 7F0h
0x18013c0ae  mov     rax, [rax+8]
0x18013c0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c0b7  test    eax, eax
0x18013c0b9  jz      short loc_18013C0C4
0x18013c0bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c0c2  jmp     short loc_18013C0D2
0x18013c0c4  lea     rcx, qword_1801B07E0; this
0x18013c0cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c0d2  cmp     [rcx+8], r12b
0x18013c0d6  jz      short loc_18013C0F6
0x18013c0d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013c0dd  cmp     [rax+7CCh], ebx
0x18013c0e3  jz      short loc_18013C0F6
0x18013c0e5  mov     r9d, ebx; int
0x18013c0e8  mov     r8d, r14d; int
0x18013c0eb  mov     rdx, rsi; char *
0x18013c0ee  mov     rcx, rax; this
0x18013c0f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013c0f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013c0fd  jb      loc_18013CCB3
0x18013c103  mov     rcx, cs:WPP_GLOBAL_Control
0x18013c10a  lea     r8, WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids
0x18013c111  mov     edx, 18h
0x18013c116  mov     [rsp+70h+var_50], ebx
0x18013c11a  mov     r9, rdi
0x18013c11d  mov     rcx, [rcx+10h]
0x18013c121  call    WPP_SF_qD
0x18013c126  jmp     loc_18013CCB3
0x18013c12b  lea     rsi, aCavivideostrea_5; "CAVIVideoStreamParser::TransformFirstSa"...
0x18013c132  mov     r8d, 0DFh; int
0x18013c138  mov     rdx, rsi; char *
0x18013c13b  lea     rcx, [rbp+arg_0]; this
0x18013c13f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18013c144  cmp     cs:byte_1801B1109, 20h ; ' '
0x18013c14b  lea     r14, WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids
0x18013c152  jb      short loc_18013C17D
0x18013c154  mov     rcx, cs:WPP_GLOBAL_Control
0x18013c15b  mov     edx, 19h
0x18013c160  mov     eax, [rdi+2A8h]
0x18013c166  mov     r8, r14
0x18013c169  mov     r9d, [rdi+298h]
0x18013c170  mov     [rsp+70h+var_50], eax; int
0x18013c174  mov     rcx, [rcx+38h]
0x18013c178  call    WPP_SF_dd
0x18013c17d  mov     ecx, [rdi+298h]
0x18013c183  mov     [rbp+ppIMFSample], r12
0x18013c187  mov     [rbp+ppBuffer], r12
0x18013c18b  mov     [rbp+var_10], r12
0x18013c18f  mov     [rbp+var_3C], r12d
0x18013c193  mov     [rbp+arg_18], r12d
0x18013c197  mov     r12d, [rdi+2A8h]
0x18013c19e  add     r12d, ecx
0x18013c1a1  cmp     r12d, ecx
0x18013c1a4  jnb     loc_18013C25A
0x18013c1aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c1b1  mov     r15d, 80070216h
0x18013c1b7  mov     ebx, r15d
0x18013c1ba  test    rcx, rcx
0x18013c1bd  jnz     short loc_18013C200
0x18013c1bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013c1c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c1cc  mov     rcx, rax
0x18013c1cf  test    rax, rax
0x18013c1d2  jz      short loc_18013C1F2
0x18013c1d4  mov     rax, [rax]
0x18013c1d7  mov     edx, 7F0h
0x18013c1dc  mov     rax, [rax+8]
0x18013c1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c1e5  test    eax, eax
0x18013c1e7  jz      short loc_18013C1F2
0x18013c1e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c1f0  jmp     short loc_18013C200
0x18013c1f2  lea     rcx, qword_1801B07E0; this
0x18013c1f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c200  cmp     byte ptr [rcx+8], 0
0x18013c204  jz      short loc_18013C228
0x18013c206  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013c20b  cmp     [rax+7CCh], r15d
0x18013c212  jz      short loc_18013C228
0x18013c214  mov     r9d, r15d; int
0x18013c217  mov     r8d, 0E8h; int
0x18013c21d  mov     rdx, rsi; char *
0x18013c220  mov     rcx, rax; this
0x18013c223  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013c228  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013c22f  jb      loc_18013CCA1
0x18013c235  mov     edx, 1Ah
0x18013c23a  mov     [rsp+70h+var_50], r15d
0x18013c23f  mov     rcx, cs:WPP_GLOBAL_Control
0x18013c246  mov     r9, rdi
0x18013c249  mov     r8, r14
0x18013c24c  mov     rcx, [rcx+10h]
0x18013c250  call    WPP_SF_qD
0x18013c255  jmp     loc_18013CCA1
0x18013c25a  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18013c25e  mov     ecx, r12d; cbMaxLength
0x18013c261  call    cs:__imp_MFCreateMemoryBuffer
0x18013c267  mov     ebx, eax
0x18013c269  test    eax, eax
0x18013c26b  jns     loc_18013C300
0x18013c271  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c278  test    rcx, rcx
0x18013c27b  jnz     short loc_18013C2BE
0x18013c27d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013c283  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c28a  mov     rcx, rax
0x18013c28d  test    rax, rax
0x18013c290  jz      short loc_18013C2B0
0x18013c292  mov     rax, [rax]
0x18013c295  mov     edx, 7F0h
0x18013c29a  mov     rax, [rax+8]
0x18013c29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c2a3  test    eax, eax
0x18013c2a5  jz      short loc_18013C2B0
0x18013c2a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c2ae  jmp     short loc_18013C2BE
0x18013c2b0  lea     rcx, qword_1801B07E0; this
0x18013c2b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c2be  cmp     byte ptr [rcx+8], 0
0x18013c2c2  jz      short loc_18013C2E5
0x18013c2c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013c2c9  cmp     [rax+7CCh], ebx
0x18013c2cf  jz      short loc_18013C2E5
0x18013c2d1  mov     r9d, ebx; int
0x18013c2d4  mov     r8d, 0E9h; int
0x18013c2da  mov     rdx, rsi; char *
0x18013c2dd  mov     rcx, rax; this
0x18013c2e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013c2e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013c2ec  jb      loc_18013CCA1
0x18013c2f2  mov     edx, 1Bh
0x18013c2f7  mov     [rsp+70h+var_50], ebx
0x18013c2fb  jmp     loc_18013C23F
0x18013c300  mov     rcx, [rbp+ppBuffer]
0x18013c304  lea     r9, [rbp+arg_18]
0x18013c308  lea     r8, [rbp+var_3C]
0x18013c30c  lea     rdx, [rbp+var_10]
0x18013c310  mov     rax, [rcx]
0x18013c313  mov     rax, [rax+18h]
0x18013c317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c31c  mov     ebx, eax
0x18013c31e  test    eax, eax
0x18013c320  jns     loc_18013C3B1
0x18013c326  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c32d  test    rcx, rcx
0x18013c330  jnz     short loc_18013C373
0x18013c332  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013c338  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c33f  mov     rcx, rax
0x18013c342  test    rax, rax
0x18013c345  jz      short loc_18013C365
0x18013c347  mov     rax, [rax]
0x18013c34a  mov     edx, 7F0h
0x18013c34f  mov     rax, [rax+8]
0x18013c353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c358  test    eax, eax
0x18013c35a  jz      short loc_18013C365
0x18013c35c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c363  jmp     short loc_18013C373
0x18013c365  lea     rcx, qword_1801B07E0; this
0x18013c36c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c373  cmp     byte ptr [rcx+8], 0
0x18013c377  jz      short loc_18013C39A
0x18013c379  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013c37e  cmp     [rax+7CCh], ebx
0x18013c384  jz      short loc_18013C39A
0x18013c386  mov     r9d, ebx; int
0x18013c389  mov     r8d, 0EBh; int
0x18013c38f  mov     rdx, rsi; char *
0x18013c392  mov     rcx, rax; this
0x18013c395  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013c39a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013c3a1  jb      loc_18013CCA1
0x18013c3a7  mov     edx, 1Ch
0x18013c3ac  jmp     loc_18013C2F7
0x18013c3b1  mov     r8d, [rdi+2A8h]; Size
0x18013c3b8  mov     rdx, [rdi+2A0h]; Src
0x18013c3bf  mov     rcx, [rbp+var_10]; void *
0x18013c3c3  call    memcpy_0
0x18013c3c8  mov     ecx, [rdi+2A8h]
0x18013c3ce  add     rcx, [rbp+var_10]; void *
0x18013c3d2  mov     r8d, [rdi+298h]; Size
0x18013c3d9  mov     rdx, [rdi+290h]; Src
0x18013c3e0  call    memcpy_0
0x18013c3e5  mov     rcx, [rbp+ppBuffer]
0x18013c3e9  mov     rax, [rcx]
0x18013c3ec  mov     rax, [rax+20h]
0x18013c3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c3f5  mov     rcx, [rbp+ppBuffer]
0x18013c3f9  mov     edx, r12d
0x18013c3fc  mov     rax, [rcx]
0x18013c3ff  mov     rax, [rax+30h]
0x18013c403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c408  xor     r12d, r12d
0x18013c40b  mov     ebx, eax
0x18013c40d  test    eax, eax
0x18013c40f  jns     loc_18013C4A0
0x18013c415  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c41c  test    rcx, rcx
0x18013c41f  jnz     short loc_18013C462
0x18013c421  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013c427  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c42e  mov     rcx, rax
0x18013c431  test    rax, rax
0x18013c434  jz      short loc_18013C454
0x18013c436  mov     rax, [rax]
0x18013c439  mov     edx, 7F0h
0x18013c43e  mov     rax, [rax+8]
0x18013c442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c447  test    eax, eax
0x18013c449  jz      short loc_18013C454
0x18013c44b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c452  jmp     short loc_18013C462
0x18013c454  lea     rcx, qword_1801B07E0; this
0x18013c45b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c462  cmp     [rcx+8], r12b
0x18013c466  jz      short loc_18013C489
0x18013c468  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013c46d  cmp     [rax+7CCh], ebx
0x18013c473  jz      short loc_18013C489
0x18013c475  mov     r9d, ebx; int
0x18013c478  mov     r8d, 0F2h; int
0x18013c47e  mov     rdx, rsi; char *
0x18013c481  mov     rcx, rax; this
0x18013c484  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013c489  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013c490  jb      loc_18013CCA1
0x18013c496  mov     edx, 1Dh
0x18013c49b  jmp     loc_18013C2F7
0x18013c4a0  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x18013c4a4  call    cs:__imp_MFCreateSample
0x18013c4aa  mov     ebx, eax
0x18013c4ac  test    eax, eax
0x18013c4ae  jns     loc_18013C53F
0x18013c4b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c4bb  test    rcx, rcx
0x18013c4be  jnz     short loc_18013C501
0x18013c4c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013c4c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c4cd  mov     rcx, rax
0x18013c4d0  test    rax, rax
0x18013c4d3  jz      short loc_18013C4F3
0x18013c4d5  mov     rax, [rax]
0x18013c4d8  mov     edx, 7F0h
0x18013c4dd  mov     rax, [rax+8]
0x18013c4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c4e6  test    eax, eax
0x18013c4e8  jz      short loc_18013C4F3
0x18013c4ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c4f1  jmp     short loc_18013C501
0x18013c4f3  lea     rcx, qword_1801B07E0; this
0x18013c4fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013c501  cmp     [rcx+8], r12b
0x18013c505  jz      short loc_18013C528
0x18013c507  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013c50c  cmp     [rax+7CCh], ebx
0x18013c512  jz      short loc_18013C528
0x18013c514  mov     r9d, ebx; int
  ... truncated ...
```
