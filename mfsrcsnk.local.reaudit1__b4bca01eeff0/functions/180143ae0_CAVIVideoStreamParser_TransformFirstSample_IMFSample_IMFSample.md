# CAVIVideoStreamParser::TransformFirstSample(IMFSample *,IMFSample * *)

- ea: `0x180143ae0`
- end: `0x180144822`
- name: `?TransformFirstSample@CAVIVideoStreamParser@@UEAAJPEAUIMFSample@@PEAPEAU2@@Z`
- size: `3394`
- prototype: `__int64 __fastcall(const void **this, struct IMFSample *, struct IMFSample **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800612cc`
- `0x18006e524`
- `0x180079680`
- `0x180140de0`
- `0x1801429b8`
- `0x180143ae0`
- `0x18016cba0`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143b61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143c95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143d5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143e1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143f0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143fba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144061`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144122`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144201`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014431e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801443e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014447f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801445d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144685`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144740`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143b61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143c95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143d5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143e1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143f0f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180143fba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144061`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144122`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144201`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014431e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801443e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014447f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801445d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144685`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180144740`
- `MFPlat!MFCreateMemoryBuffer` at `0x180143d3d`
- `MFPlat!MFCreateMemoryBuffer` at `0x180143d3d`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1801442f9`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1801443bd`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1801442f9`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1801443bd`
- `MFPlat!MFCreateSample` at `0x180143f98`
- `MFPlat!MFCreateSample` at `0x180143f98`

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
          v8 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      25,
      &WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids,
      *((unsigned int *)this + 166),
      *((_DWORD *)this + 170));
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
        v14 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v18 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v23 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v27 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v33 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v37 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v43 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v48 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v65 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v62 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v69 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v77 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v73 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v57 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x180143ae0  mov     [rsp-38h+arg_8], rbx
0x180143ae5  push    rbp
0x180143ae6  push    rsi
0x180143ae7  push    rdi
0x180143ae8  push    r12
0x180143aea  push    r13
0x180143aec  push    r14
0x180143aee  push    r15
0x180143af0  mov     rbp, rsp
0x180143af3  sub     rsp, 70h
0x180143af7  xor     r12d, r12d
0x180143afa  mov     r13, r8
0x180143afd  mov     r15, rdx
0x180143b00  mov     rdi, rcx
0x180143b03  mov     [rbp+pBuffer], r12
0x180143b07  cmp     [rcx+2A0h], r12
0x180143b0e  jnz     loc_180143C01
0x180143b14  cmp     [rcx+290h], r12
0x180143b1b  jnz     loc_180143C01
0x180143b21  mov     r14d, 0DBh
0x180143b27  lea     rsi, aCavivideostrea_5; "CAVIVideoStreamParser::TransformFirstSa"...
0x180143b2e  mov     r8d, r14d; int
0x180143b31  lea     rcx, [rbp+arg_0]; this
0x180143b35  mov     rdx, rsi; char *
0x180143b38  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180143b3d  mov     r8, r13; struct IMFSample **
0x180143b40  mov     rdx, r15; struct IMFSample *
0x180143b43  mov     rcx, rdi; this
0x180143b46  call    ?TransformFirstSample@CAVIStreamParser@@UEAAJPEAUIMFSample@@PEAPEAU2@@Z; CAVIStreamParser::TransformFirstSample(IMFSample *,IMFSample * *)
0x180143b4b  mov     ebx, eax
0x180143b4d  test    eax, eax
0x180143b4f  jns     loc_1801447F5
0x180143b55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143b5c  test    rcx, rcx
0x180143b5f  jnz     short loc_180143BA8
0x180143b61  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180143b68  nop     dword ptr [rax+rax+00h]
0x180143b6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180143b74  mov     rcx, rax
0x180143b77  test    rax, rax
0x180143b7a  jz      short loc_180143B9A
0x180143b7c  mov     rax, [rax]
0x180143b7f  mov     edx, 7F0h
0x180143b84  mov     rax, [rax+8]
0x180143b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143b8d  test    eax, eax
0x180143b8f  jz      short loc_180143B9A
0x180143b91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143b98  jmp     short loc_180143BA8
0x180143b9a  lea     rcx, qword_1801B97E0; this
0x180143ba1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180143ba8  cmp     [rcx+8], r12b
0x180143bac  jz      short loc_180143BCC
0x180143bae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180143bb3  cmp     [rax+7CCh], ebx
0x180143bb9  jz      short loc_180143BCC
0x180143bbb  mov     r9d, ebx; int
0x180143bbe  mov     r8d, r14d; int
0x180143bc1  mov     rdx, rsi; char *
0x180143bc4  mov     rcx, rax; this
0x180143bc7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180143bcc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180143bd3  jb      loc_1801447F5
0x180143bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180143be0  lea     r8, WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids
0x180143be7  mov     edx, 18h
0x180143bec  mov     [rsp+70h+var_50], ebx
0x180143bf0  mov     r9, rdi
0x180143bf3  mov     rcx, [rcx+10h]
0x180143bf7  call    WPP_SF_qD
0x180143bfc  jmp     loc_1801447F5
0x180143c01  lea     rsi, aCavivideostrea_5; "CAVIVideoStreamParser::TransformFirstSa"...
0x180143c08  mov     r8d, 0DFh; int
0x180143c0e  mov     rdx, rsi; char *
0x180143c11  lea     rcx, [rbp+arg_0]; this
0x180143c15  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180143c1a  cmp     cs:byte_1801BA109, 20h ; ' '
0x180143c21  lea     r14, WPP_a8a8c43195cf32946a196ad84950bda1_Traceguids
0x180143c28  jb      short loc_180143C53
0x180143c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180143c31  mov     edx, 19h
0x180143c36  mov     eax, [rdi+2A8h]
0x180143c3c  mov     r8, r14
0x180143c3f  mov     r9d, [rdi+298h]
0x180143c46  mov     [rsp+70h+var_50], eax; int
0x180143c4a  mov     rcx, [rcx+38h]
0x180143c4e  call    WPP_SF_dd
0x180143c53  mov     ecx, [rdi+298h]
0x180143c59  mov     [rbp+ppIMFSample], r12
0x180143c5d  mov     [rbp+ppBuffer], r12
0x180143c61  mov     [rbp+var_10], r12
0x180143c65  mov     [rbp+var_3C], r12d
0x180143c69  mov     [rbp+arg_18], r12d
0x180143c6d  mov     r12d, [rdi+2A8h]
0x180143c74  add     r12d, ecx
0x180143c77  cmp     r12d, ecx
0x180143c7a  jnb     loc_180143D36
0x180143c80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143c87  mov     r15d, 80070216h
0x180143c8d  mov     ebx, r15d
0x180143c90  test    rcx, rcx
0x180143c93  jnz     short loc_180143CDC
0x180143c95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180143c9c  nop     dword ptr [rax+rax+00h]
0x180143ca1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180143ca8  mov     rcx, rax
0x180143cab  test    rax, rax
0x180143cae  jz      short loc_180143CCE
0x180143cb0  mov     rax, [rax]
0x180143cb3  mov     edx, 7F0h
0x180143cb8  mov     rax, [rax+8]
0x180143cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143cc1  test    eax, eax
0x180143cc3  jz      short loc_180143CCE
0x180143cc5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143ccc  jmp     short loc_180143CDC
0x180143cce  lea     rcx, qword_1801B97E0; this
0x180143cd5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180143cdc  cmp     byte ptr [rcx+8], 0
0x180143ce0  jz      short loc_180143D04
0x180143ce2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180143ce7  cmp     [rax+7CCh], r15d
0x180143cee  jz      short loc_180143D04
0x180143cf0  mov     r9d, r15d; int
0x180143cf3  mov     r8d, 0E8h; int
0x180143cf9  mov     rdx, rsi; char *
0x180143cfc  mov     rcx, rax; this
0x180143cff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180143d04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180143d0b  jb      loc_1801447E3
0x180143d11  mov     edx, 1Ah
0x180143d16  mov     [rsp+70h+var_50], r15d
0x180143d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180143d22  mov     r9, rdi
0x180143d25  mov     r8, r14
0x180143d28  mov     rcx, [rcx+10h]
0x180143d2c  call    WPP_SF_qD
0x180143d31  jmp     loc_1801447E3
0x180143d36  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180143d3a  mov     ecx, r12d; cbMaxLength
0x180143d3d  call    cs:__imp_MFCreateMemoryBuffer
0x180143d44  nop     dword ptr [rax+rax+00h]
0x180143d49  mov     ebx, eax
0x180143d4b  test    eax, eax
0x180143d4d  jns     loc_180143DE8
0x180143d53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143d5a  test    rcx, rcx
0x180143d5d  jnz     short loc_180143DA6
0x180143d5f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180143d66  nop     dword ptr [rax+rax+00h]
0x180143d6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180143d72  mov     rcx, rax
0x180143d75  test    rax, rax
0x180143d78  jz      short loc_180143D98
0x180143d7a  mov     rax, [rax]
0x180143d7d  mov     edx, 7F0h
0x180143d82  mov     rax, [rax+8]
0x180143d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143d8b  test    eax, eax
0x180143d8d  jz      short loc_180143D98
0x180143d8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143d96  jmp     short loc_180143DA6
0x180143d98  lea     rcx, qword_1801B97E0; this
0x180143d9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180143da6  cmp     byte ptr [rcx+8], 0
0x180143daa  jz      short loc_180143DCD
0x180143dac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180143db1  cmp     [rax+7CCh], ebx
0x180143db7  jz      short loc_180143DCD
0x180143db9  mov     r9d, ebx; int
0x180143dbc  mov     r8d, 0E9h; int
0x180143dc2  mov     rdx, rsi; char *
0x180143dc5  mov     rcx, rax; this
0x180143dc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180143dcd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180143dd4  jb      loc_1801447E3
0x180143dda  mov     edx, 1Bh
0x180143ddf  mov     [rsp+70h+var_50], ebx
0x180143de3  jmp     loc_180143D1B
0x180143de8  mov     rcx, [rbp+ppBuffer]
0x180143dec  lea     r9, [rbp+arg_18]
0x180143df0  lea     r8, [rbp+var_3C]
0x180143df4  lea     rdx, [rbp+var_10]
0x180143df8  mov     rax, [rcx]
0x180143dfb  mov     rax, [rax+18h]
0x180143dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143e04  mov     ebx, eax
0x180143e06  test    eax, eax
0x180143e08  jns     loc_180143E9F
0x180143e0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143e15  test    rcx, rcx
0x180143e18  jnz     short loc_180143E61
0x180143e1a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180143e21  nop     dword ptr [rax+rax+00h]
0x180143e26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180143e2d  mov     rcx, rax
0x180143e30  test    rax, rax
0x180143e33  jz      short loc_180143E53
0x180143e35  mov     rax, [rax]
0x180143e38  mov     edx, 7F0h
0x180143e3d  mov     rax, [rax+8]
0x180143e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143e46  test    eax, eax
0x180143e48  jz      short loc_180143E53
0x180143e4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143e51  jmp     short loc_180143E61
0x180143e53  lea     rcx, qword_1801B97E0; this
0x180143e5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180143e61  cmp     byte ptr [rcx+8], 0
0x180143e65  jz      short loc_180143E88
0x180143e67  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180143e6c  cmp     [rax+7CCh], ebx
0x180143e72  jz      short loc_180143E88
0x180143e74  mov     r9d, ebx; int
0x180143e77  mov     r8d, 0EBh; int
0x180143e7d  mov     rdx, rsi; char *
0x180143e80  mov     rcx, rax; this
0x180143e83  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180143e88  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180143e8f  jb      loc_1801447E3
0x180143e95  mov     edx, 1Ch
0x180143e9a  jmp     loc_180143DDF
0x180143e9f  mov     r8d, [rdi+2A8h]; Size
0x180143ea6  mov     rdx, [rdi+2A0h]; Src
0x180143ead  mov     rcx, [rbp+var_10]; void *
0x180143eb1  call    memcpy_0
0x180143eb6  mov     ecx, [rdi+2A8h]
0x180143ebc  add     rcx, [rbp+var_10]; void *
0x180143ec0  mov     r8d, [rdi+298h]; Size
0x180143ec7  mov     rdx, [rdi+290h]; Src
0x180143ece  call    memcpy_0
0x180143ed3  mov     rcx, [rbp+ppBuffer]
0x180143ed7  mov     rax, [rcx]
0x180143eda  mov     rax, [rax+20h]
0x180143ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143ee3  mov     rcx, [rbp+ppBuffer]
0x180143ee7  mov     edx, r12d
0x180143eea  mov     rax, [rcx]
0x180143eed  mov     rax, [rax+30h]
0x180143ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143ef6  xor     r12d, r12d
0x180143ef9  mov     ebx, eax
0x180143efb  test    eax, eax
0x180143efd  jns     loc_180143F94
0x180143f03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143f0a  test    rcx, rcx
0x180143f0d  jnz     short loc_180143F56
0x180143f0f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180143f16  nop     dword ptr [rax+rax+00h]
0x180143f1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180143f22  mov     rcx, rax
0x180143f25  test    rax, rax
0x180143f28  jz      short loc_180143F48
0x180143f2a  mov     rax, [rax]
0x180143f2d  mov     edx, 7F0h
0x180143f32  mov     rax, [rax+8]
0x180143f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143f3b  test    eax, eax
0x180143f3d  jz      short loc_180143F48
0x180143f3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143f46  jmp     short loc_180143F56
0x180143f48  lea     rcx, qword_1801B97E0; this
0x180143f4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180143f56  cmp     [rcx+8], r12b
0x180143f5a  jz      short loc_180143F7D
0x180143f5c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180143f61  cmp     [rax+7CCh], ebx
0x180143f67  jz      short loc_180143F7D
0x180143f69  mov     r9d, ebx; int
0x180143f6c  mov     r8d, 0F2h; int
0x180143f72  mov     rdx, rsi; char *
0x180143f75  mov     rcx, rax; this
0x180143f78  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180143f7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180143f84  jb      loc_1801447E3
0x180143f8a  mov     edx, 1Dh
0x180143f8f  jmp     loc_180143DDF
0x180143f94  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180143f98  call    cs:__imp_MFCreateSample
0x180143f9f  nop     dword ptr [rax+rax+00h]
0x180143fa4  mov     ebx, eax
0x180143fa6  test    eax, eax
0x180143fa8  jns     loc_18014403F
0x180143fae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143fb5  test    rcx, rcx
0x180143fb8  jnz     short loc_180144001
0x180143fba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180143fc1  nop     dword ptr [rax+rax+00h]
0x180143fc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180143fcd  mov     rcx, rax
0x180143fd0  test    rax, rax
0x180143fd3  jz      short loc_180143FF3
0x180143fd5  mov     rax, [rax]
0x180143fd8  mov     edx, 7F0h
0x180143fdd  mov     rax, [rax+8]
0x180143fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143fe6  test    eax, eax
0x180143fe8  jz      short loc_180143FF3
0x180143fea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180143ff1  jmp     short loc_180144001
  ... truncated ...
```
