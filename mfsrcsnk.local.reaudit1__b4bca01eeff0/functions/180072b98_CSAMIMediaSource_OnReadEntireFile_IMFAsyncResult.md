# CSAMIMediaSource::OnReadEntireFile(IMFAsyncResult *)

- ea: `0x180072b98`
- end: `0x180073955`
- name: `?OnReadEntireFile@CSAMIMediaSource@@AEAAJPEAUIMFAsyncResult@@@Z`
- size: `3517`
- prototype: `__int64 __fastcall(CSAMIMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18015b850`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800496c4`
- `0x180072b98`
- `0x180074194`
- `0x1800792a4`
- `0x180079680`
- `0x18007cb48`
- `0x1800f3848`
- `0x180110a94`
- `0x180110ed0`
- `0x18015c52c`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072cb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800738bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072cb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800738bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072bea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072bea`
- `MFPlat!MFPutWorkItemEx2` at `0x180073906`
- `MFPlat!MFPutWorkItemEx2` at `0x180073906`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072c10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072d94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072e52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072f06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072fbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073071`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073166`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800732b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800733ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007349c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800734ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007360b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800736c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007376f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073818`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072c10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072d94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072e52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072f06`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072fbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073071`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073166`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800732b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800733ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007349c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800734ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007360b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800736c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007376f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073818`

## string_xrefs

- `0x180072bc0`: `CSAMIMediaSource::OnReadEntireFile`
- `0x180072f64`: `CSAMIMediaSource::OnReadEntireFile`
- `0x1800730cf`: `CSAMIMediaSource::OnReadEntireFile`
- `0x1800731c4`: `CSAMIMediaSource::OnReadEntireFile`
- `0x18007330e`: `CSAMIMediaSource::OnReadEntireFile`
- `0x180073427`: `CSAMIMediaSource::OnReadEntireFile`
- `0x18007355d`: `CSAMIMediaSource::OnReadEntireFile`
- `0x1800735ad`: `CSAMIMediaSource::OnReadEntireFile`
- `0x180073669`: `CSAMIMediaSource::OnReadEntireFile`
- `0x180073724`: `CSAMIMediaSource::OnReadEntireFile`
- `0x1800737cd`: `CSAMIMediaSource::OnReadEntireFile`
- `0x180073876`: `CSAMIMediaSource::OnReadEntireFile`

## pseudocode

```c
__int64 __fastcall CSAMIMediaSource::OnReadEntireFile(CSAMIMediaSource *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  wchar_t *v5; // rcx
  int PresentationDescriptor; // edi
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  struct tagMFASYNCRESULT *v14; // r13
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  DWORD v23; // r14d
  __int64 v24; // rdx
  int v25; // r8d
  wchar_t *v26; // rcx
  int v27; // r15d
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  unsigned __int64 v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  unsigned __int64 v39; // r14
  void *v40; // rax
  __int64 v41; // rdx
  void *v42; // rdi
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  unsigned int v46; // r9d
  int v47; // r9d
  unsigned int v48; // eax
  unsigned int v49; // r15d
  void *v50; // rax
  __int64 v51; // rdx
  void *v52; // rdi
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  unsigned int v56; // r9d
  int v57; // r9d
  unsigned int v58; // ecx
  unsigned __int64 v59; // rdx
  const char *v60; // rcx
  __int64 v61; // rdx
  wchar_t *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  unsigned int v65; // ecx
  const char *v66; // rcx
  __int64 v67; // rdx
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  wchar_t *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  struct CallStackContext *v73; // rax
  unsigned int v74; // ecx
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
  wchar_t *v85; // rcx
  CallStackTracing *v86; // rax
  struct CallStackContext *v87; // rax
  IMFAsyncCallback *pCallback; // rcx
  _BYTE v90[8]; // [rsp+30h] [rbp-30h] BYREF
  void *i; // [rsp+38h] [rbp-28h] BYREF
  int v92; // [rsp+40h] [rbp-20h] BYREF
  IMFAsyncResult *pResult; // [rsp+48h] [rbp-18h] BYREF
  int v94; // [rsp+50h] [rbp-10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v90, "CSAMIMediaSource::OnReadEntireFile", 265);
  pResult = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( !a2 )
  {
    v5 = (wchar_t *)CallStackTracing::s_wpInstance;
    PresentationDescriptor = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSAMIMediaSource::OnReadEntireFile", 277, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v9 = 32;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
      this,
      PresentationDescriptor);
LABEL_13:
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
    goto LABEL_202;
  }
  PresentationDescriptor = ((__int64 (__fastcall *)(struct IMFAsyncResult *, IMFAsyncResult **))a2->lpVtbl->GetState)(
                             a2,
                             &pResult);
  if ( PresentationDescriptor < 0 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
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
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != PresentationDescriptor )
        CallStackContext::TraceFailure(v13, "CSAMIMediaSource::OnReadEntireFile", 283, PresentationDescriptor);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v9 = 33;
    goto LABEL_12;
  }
  v14 = (struct tagMFASYNCRESULT *)pResult;
  if ( !pResult )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    PresentationDescriptor = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      if ( *((_DWORD *)v17 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v17, "CSAMIMediaSource::OnReadEntireFile", 285, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v9 = 34;
    goto LABEL_12;
  }
  v18 = *((_QWORD *)this + 90);
  v94 = 0;
  PresentationDescriptor = (*(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *, int *))(*(_QWORD *)v18 + 88LL))(
                             v18,
                             a2,
                             &v94);
  if ( PresentationDescriptor < 0 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != PresentationDescriptor )
        CallStackContext::TraceFailure(v22, "CSAMIMediaSource::OnReadEntireFile", 293, PresentationDescriptor);
    }
    v23 = 1;
    if ( !g_wppLevels )
      goto LABEL_196;
    v24 = 35;
    goto LABEL_47;
  }
  v25 = *((_DWORD *)this + 188);
  if ( v94 != v25 )
  {
    v26 = (wchar_t *)CallStackTracing::s_wpInstance;
    v27 = -1072875845;
    PresentationDescriptor = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v26 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
      if ( *((_DWORD *)v29 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v29, "CSAMIMediaSource::OnReadEntireFile", 299, -1072875845);
    }
    v23 = 1;
    if ( !g_wppLevels )
      goto LABEL_196;
    v30 = 36;
    goto LABEL_195;
  }
  PresentationDescriptor = CSAMIInterpreter::ParseSAMI(
                             (CSAMIMediaSource *)((char *)this + 760),
                             *((const char **)this + 93),
                             v25);
  if ( PresentationDescriptor < 0 )
  {
    v32 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v34 + 499) != PresentationDescriptor )
        CallStackContext::TraceFailure(v34, "CSAMIMediaSource::OnReadEntireFile", 307, PresentationDescriptor);
    }
    v23 = 1;
    if ( !g_wppLevels )
      goto LABEL_196;
    v24 = 37;
    goto LABEL_47;
  }
  v35 = *((unsigned int *)this + 524);
  *((_DWORD *)this + 648) = v35;
  if ( !(_DWORD)v35 )
  {
    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
    v27 = -1072875845;
    PresentationDescriptor = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
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
      if ( *((_DWORD *)v38 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v38, "CSAMIMediaSource::OnReadEntireFile", 315, -1072875845);
    }
    v23 = 1;
    if ( !g_wppLevels )
      goto LABEL_196;
    v30 = 38;
    goto LABEL_195;
  }
  v39 = v35;
  v40 = operator new(saturated_mul(v35, 8u));
  v42 = v40;
  if ( v40 )
    `vector constructor iterator'(v40, 8u, v39, ComSmartPtr<IMFMediaType>::ComSmartPtr<IMFMediaType>);
  else
    v42 = 0;
  *((_QWORD *)this + 325) = v42;
  if ( !v42 )
  {
    v43 = (wchar_t *)CallStackTracing::s_wpInstance;
    v27 = -2147024882;
    PresentationDescriptor = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
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
      if ( *((_DWORD *)v45 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v45, "CSAMIMediaSource::OnReadEntireFile", 322, -2147024882);
    }
    v23 = 1;
    if ( !g_wppLevels )
      goto LABEL_196;
    v30 = 39;
    goto LABEL_195;
  }
  v46 = 0;
  v23 = 1;
  for ( i = (void *)*((_QWORD *)this + 260); v46 < *((_DWORD *)this + 648); v46 = v47 + 1 )
    CVPtrList::GetNext((CVPtrList *)v46, &i, (void **)(*((_QWORD *)this + 325) + 8LL * v46));
  v48 = *((_DWORD *)this + 636);
  *((_DWORD *)this + 652) = v48;
  if ( v48 )
  {
    v49 = v48;
    v50 = operator new(saturated_mul(v48, 8u));
    v52 = v50;
    if ( v50 )
      `vector constructor iterator'(v50, 8u, v49, ComSmartPtr<IMFMediaType>::ComSmartPtr<IMFMediaType>);
    else
      v52 = 0;
    *((_QWORD *)this + 327) = v52;
    if ( !v52 )
    {
      v53 = (wchar_t *)CallStackTracing::s_wpInstance;
      v27 = -2147024882;
      PresentationDescriptor = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
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
        if ( *((_DWORD *)v55 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v55, "CSAMIMediaSource::OnReadEntireFile", 342, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_196;
      v30 = 40;
      goto LABEL_195;
    }
    v56 = 0;
    for ( i = (void *)*((_QWORD *)this + 316); v56 < *((_DWORD *)this + 652); v56 = v57 + 1 )
      CVPtrList::GetNext((CVPtrList *)v56, &i, (void **)(*((_QWORD *)this + 327) + 8LL * v56));
    *((_DWORD *)this + 653) = 0;
  }
  v58 = *((_DWORD *)this + 640);
  v59 = v58 + *((_DWORD *)this + 641);
  i = 0;
  if ( (unsigned int)v59 < v58 )
  {
    *((_DWORD *)this + 649) = -1;
    v27 = -2147024362;
    v85 = (wchar_t *)CallStackTracing::s_wpInstance;
    PresentationDescriptor = -2147024362;
    if ( !CallStackTracing::s_wpInstance )
    {
      v86 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
      CallStackTracing::s_wpInstance = v86;
      if ( v86 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v86 + 8LL))(v86, 2032) )
      {
        v85 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v85 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v85 + 8) )
    {
      v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v85);
      if ( *((_DWORD *)v87 + 499) != -2147024362 )
        CallStackContext::TraceFailure(v87, "CSAMIMediaSource::OnReadEntireFile", 369, -2147024362);
    }
    if ( !g_wppLevels )
      goto LABEL_196;
    v30 = 41;
  }
  else
  {
    *((_DWORD *)this + 649) = v59;
    v60 = (const char *)*((_QWORD *)this + 323);
    if ( v60 )
    {
      PresentationDescriptor = StringCchLengthA(v60, v59, (unsigned __int64 *)&i);
      if ( PresentationDescriptor < 0 )
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
          if ( *((_DWORD *)v64 + 499) != PresentationDescriptor )
            CallStackContext::TraceFailure(v64, "CSAMIMediaSource::OnReadEntireFile", 373, PresentationDescriptor);
        }
        if ( !g_wppLevels )
          goto LABEL_196;
        v24 = 42;
        goto LABEL_47;
      }
      v65 = *((_DWORD *)this + 649);
      v59 = v65 + 2 * (_DWORD)i;
      if ( (unsigned int)v59 < v65 )
      {
        *((_DWORD *)this + 649) = -1;
        v27 = -2147024362;
        v70 = (wchar_t *)CallStackTracing::s_wpInstance;
        PresentationDescriptor = -2147024362;
        if ( !CallStackTracing::s_wpInstance )
        {
          v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
          CallStackTracing::s_wpInstance = v71;
          if ( v71 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
          {
            v70 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v70 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v70 + 8) )
        {
          v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
          if ( *((_DWORD *)v72 + 499) != -2147024362 )
            CallStackContext::TraceFailure(v72, "CSAMIMediaSource::OnReadEntireFile", 374, -2147024362);
        }
        if ( !g_wppLevels )
          goto LABEL_196;
        v30 = 43;
        goto LABEL_195;
      }
      *((_DWORD *)this + 649) = v59;
    }
    v66 = (const char *)*((_QWORD *)this + 322);
    if ( !v66 )
      goto LABEL_163;
    PresentationDescriptor = StringCchLengthA(v66, v59, (unsigned __int64 *)&i);
    if ( PresentationDescriptor < 0 )
    {
      v68 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67);
        CallStackTracing::s_wpInstance = v69;
        if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
        {
          v68 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v68 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v68 + 8) )
      {
        v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
        if ( *((_DWORD *)v73 + 499) != PresentationDescriptor )
          CallStackContext::TraceFailure(v73, "CSAMIMediaSource::OnReadEntireFile", 379, PresentationDescriptor);
      }
      if ( !g_wppLevels )
        goto LABEL_196;
      v24 = 44;
      goto LABEL_47;
    }
    v74 = *((_DWORD *)this + 649);
    v59 = v74 + (unsigned int)i;
    if ( (unsigned int)v59 < v74 )
    {
      *((_DWORD *)this + 649) = -1;
      v27 = -2147024362;
      v75 = (wchar_t *)CallStackTracing::s_wpInstance;
      PresentationDescriptor = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
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
        if ( *((_DWORD *)v77 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v77, "CSAMIMediaSource::OnReadEntireFile", 380, -2147024362);
      }
      if ( !g_wppLevels )
        goto LABEL_196;
      v30 = 45;
    }
    else
    {
LABEL_163:
      if ( (int)v59 + 300 >= (unsigned int)v59 )
      {
        *((_DWORD *)this + 649) = v59 + 300;
        PresentationDescriptor = CMediaSourceBase::CreatePresentationDescriptor(this);
        if ( PresentationDescriptor >= 0 )
          goto LABEL_196;
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
          if ( *((_DWORD *)v81 + 499) != PresentationDescriptor )
            CallStackContext::TraceFailure(v81, "CSAMIMediaSource::OnReadEntireFile", 389, PresentationDescriptor);
        }
        if ( !g_wppLevels )
          goto LABEL_196;
        v24 = 47;
LABEL_47:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids,
          this,
          PresentationDescriptor);
        goto LABEL_196;
      }
      *((_DWORD *)this + 649) = -1;
      v27 = -2147024362;
      v82 = (wchar_t *)CallStackTracing::s_wpInstance;
      PresentationDescriptor = -2147024362;
      if ( !CallStackTracing::s_wpInstance )
      {
        v83 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
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
        if ( *((_DWORD *)v84 + 499) != -2147024362 )
          CallStackContext::TraceFailure(v84, "CSAMIMediaSource::OnReadEntireFile", 383, -2147024362);
      }
      if ( !g_wppLevels )
        goto LABEL_196;
      v30 = 46;
    }
  }
LABEL_195:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_0776a4c2c75433e71492a25261740b6d_Traceguids, this, v27);
LABEL_196:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  pCallback = v14->pCallback;
  v14->hrStatusResult = PresentationDescriptor;
  if ( pCallback )
  {
    LODWORD(i) = 0;
    v92 = 0;
    if ( ((int (__fastcall *)(IMFAsyncCallback *, void **, int *))pCallback->lpVtbl->GetParameters)(pCallback, &i, &v92) >= 0 )
      v23 = v92;
    else
      v92 = 1;
    MFPutWorkItemEx2(v23, 0, &v14->AsyncResult);
  }
  else
  {
    CAsyncResult::SignalEvent(v14);
  }
LABEL_202:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v90);
  return (unsigned int)PresentationDescriptor;
}

```

## disassembly

```asm
0x180072b98  mov     [rsp-38h+arg_10], rbx
0x180072b9d  push    rbp
0x180072b9e  push    rsi
0x180072b9f  push    rdi
0x180072ba0  push    r12
0x180072ba2  push    r13
0x180072ba4  push    r14
0x180072ba6  push    r15
0x180072ba8  mov     rbp, rsp
0x180072bab  sub     rsp, 60h
0x180072baf  mov     rax, cs:__security_cookie
0x180072bb6  xor     rax, rsp
0x180072bb9  mov     [rbp+var_8], rax
0x180072bbd  mov     r14, rdx
0x180072bc0  lea     r15, aCsamimediasour_8; "CSAMIMediaSource::OnReadEntireFile"
0x180072bc7  mov     rsi, rcx
0x180072bca  mov     rdx, r15; char *
0x180072bcd  mov     r8d, 109h; int
0x180072bd3  lea     rcx, [rbp+var_30]; this
0x180072bd7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180072bdc  lea     rbx, [rsi+28h]
0x180072be0  xor     r12d, r12d
0x180072be3  mov     rcx, rbx; lpCriticalSection
0x180072be6  mov     [rbp+pResult], r12
0x180072bea  call    cs:__imp_EnterCriticalSection
0x180072bf1  nop     dword ptr [rax+rax+00h]
0x180072bf6  test    r14, r14
0x180072bf9  jnz     loc_180072CC3
0x180072bff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072c06  mov     edi, 80004003h
0x180072c0b  test    rcx, rcx
0x180072c0e  jnz     short loc_180072C57
0x180072c10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072c17  nop     dword ptr [rax+rax+00h]
0x180072c1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072c23  mov     rcx, rax
0x180072c26  test    rax, rax
0x180072c29  jz      short loc_180072C49
0x180072c2b  mov     rax, [rax]
0x180072c2e  mov     edx, 7F0h
0x180072c33  mov     rax, [rax+8]
0x180072c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c3c  test    eax, eax
0x180072c3e  jz      short loc_180072C49
0x180072c40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072c47  jmp     short loc_180072C57
0x180072c49  lea     rcx, qword_1801B97E0; this
0x180072c50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072c57  cmp     [rcx+8], r12b
0x180072c5b  jz      short loc_180072C7E
0x180072c5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072c62  cmp     [rax+7CCh], edi
0x180072c68  jz      short loc_180072C7E
0x180072c6a  mov     r9d, edi; int
0x180072c6d  mov     r8d, 115h; int
0x180072c73  mov     rdx, r15; char *
0x180072c76  mov     rcx, rax; this
0x180072c79  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072c7e  mov     r14d, 1
0x180072c84  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180072c8b  jb      short loc_180072CAF
0x180072c8d  lea     edx, [r14+1Fh]
0x180072c91  mov     rcx, cs:WPP_GLOBAL_Control
0x180072c98  lea     r8, WPP_0776a4c2c75433e71492a25261740b6d_Traceguids
0x180072c9f  mov     r9, rsi
0x180072ca2  mov     [rsp+60h+var_40], edi
0x180072ca6  mov     rcx, [rcx+10h]
0x180072caa  call    WPP_SF_qD
0x180072caf  mov     rcx, rbx; lpCriticalSection
0x180072cb2  call    cs:__imp_LeaveCriticalSection
0x180072cb9  nop     dword ptr [rax+rax+00h]
0x180072cbe  jmp     loc_18007391C
0x180072cc3  mov     rax, [r14]
0x180072cc6  lea     rdx, [rbp+pResult]
0x180072cca  mov     rcx, r14
0x180072ccd  mov     rax, [rax+18h]
0x180072cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072cd6  mov     edi, eax
0x180072cd8  test    eax, eax
0x180072cda  jns     loc_180072D76
0x180072ce0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072ce7  test    rcx, rcx
0x180072cea  jnz     short loc_180072D33
0x180072cec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072cf3  nop     dword ptr [rax+rax+00h]
0x180072cf8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072cff  mov     rcx, rax
0x180072d02  test    rax, rax
0x180072d05  jz      short loc_180072D25
0x180072d07  mov     rax, [rax]
0x180072d0a  mov     edx, 7F0h
0x180072d0f  mov     rax, [rax+8]
0x180072d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d18  test    eax, eax
0x180072d1a  jz      short loc_180072D25
0x180072d1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072d23  jmp     short loc_180072D33
0x180072d25  lea     rcx, qword_1801B97E0; this
0x180072d2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072d33  cmp     [rcx+8], r12b
0x180072d37  jz      short loc_180072D5A
0x180072d39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072d3e  cmp     [rax+7CCh], edi
0x180072d44  jz      short loc_180072D5A
0x180072d46  mov     r9d, edi; int
0x180072d49  mov     r8d, 11Bh; int
0x180072d4f  mov     rdx, r15; char *
0x180072d52  mov     rcx, rax; this
0x180072d55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072d5a  mov     r14d, 1
0x180072d60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180072d67  jb      loc_180072CAF
0x180072d6d  lea     edx, [r14+20h]
0x180072d71  jmp     loc_180072C91
0x180072d76  mov     r13, [rbp+pResult]
0x180072d7a  test    r13, r13
0x180072d7d  jnz     loc_180072E1E
0x180072d83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072d8a  mov     edi, 80070057h
0x180072d8f  test    rcx, rcx
0x180072d92  jnz     short loc_180072DDB
0x180072d94  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072d9b  nop     dword ptr [rax+rax+00h]
0x180072da0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072da7  mov     rcx, rax
0x180072daa  test    rax, rax
0x180072dad  jz      short loc_180072DCD
0x180072daf  mov     rax, [rax]
0x180072db2  mov     edx, 7F0h
0x180072db7  mov     rax, [rax+8]
0x180072dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072dc0  test    eax, eax
0x180072dc2  jz      short loc_180072DCD
0x180072dc4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072dcb  jmp     short loc_180072DDB
0x180072dcd  lea     rcx, qword_1801B97E0; this
0x180072dd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072ddb  cmp     [rcx+8], r12b
0x180072ddf  jz      short loc_180072E02
0x180072de1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072de6  cmp     [rax+7CCh], edi
0x180072dec  jz      short loc_180072E02
0x180072dee  mov     r9d, edi; int
0x180072df1  mov     r8d, 11Dh; int
0x180072df7  mov     rdx, r15; char *
0x180072dfa  mov     rcx, rax; this
0x180072dfd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072e02  mov     r14d, 1
0x180072e08  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180072e0f  jb      loc_180072CAF
0x180072e15  lea     edx, [r14+21h]
0x180072e19  jmp     loc_180072C91
0x180072e1e  mov     rcx, [rsi+2D0h]
0x180072e25  lea     r8, [rbp+var_10]
0x180072e29  mov     [rbp+var_10], r12d
0x180072e2d  mov     rdx, r14
0x180072e30  mov     rax, [rcx]
0x180072e33  mov     rax, [rax+58h]
0x180072e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e3c  mov     edi, eax
0x180072e3e  test    eax, eax
0x180072e40  jns     loc_180072EE0
0x180072e46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072e4d  test    rcx, rcx
0x180072e50  jnz     short loc_180072E99
0x180072e52  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072e59  nop     dword ptr [rax+rax+00h]
0x180072e5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072e65  mov     rcx, rax
0x180072e68  test    rax, rax
0x180072e6b  jz      short loc_180072E8B
0x180072e6d  mov     rax, [rax]
0x180072e70  mov     edx, 7F0h
0x180072e75  mov     rax, [rax+8]
0x180072e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e7e  test    eax, eax
0x180072e80  jz      short loc_180072E8B
0x180072e82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072e89  jmp     short loc_180072E99
0x180072e8b  lea     rcx, qword_1801B97E0; this
0x180072e92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072e99  cmp     [rcx+8], r12b
0x180072e9d  jz      short loc_180072EC0
0x180072e9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072ea4  cmp     [rax+7CCh], edi
0x180072eaa  jz      short loc_180072EC0
0x180072eac  mov     r9d, edi; int
0x180072eaf  mov     r8d, 125h; int
0x180072eb5  mov     rdx, r15; char *
0x180072eb8  mov     rcx, rax; this
0x180072ebb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072ec0  mov     r14d, 1
0x180072ec6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180072ecd  jb      loc_1800738B8
0x180072ed3  lea     edx, [r14+22h]
0x180072ed7  mov     [rsp+60h+var_40], edi
0x180072edb  jmp     loc_18007389E
0x180072ee0  mov     r8d, [rsi+2F0h]; int
0x180072ee7  cmp     [rbp+var_10], r8d
0x180072eeb  jz      loc_180072F95
0x180072ef1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072ef8  mov     r15d, 0C00D36BBh
0x180072efe  mov     edi, r15d
0x180072f01  test    rcx, rcx
0x180072f04  jnz     short loc_180072F4D
0x180072f06  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072f0d  nop     dword ptr [rax+rax+00h]
0x180072f12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072f19  mov     rcx, rax
0x180072f1c  test    rax, rax
0x180072f1f  jz      short loc_180072F3F
0x180072f21  mov     rax, [rax]
0x180072f24  mov     edx, 7F0h
0x180072f29  mov     rax, [rax+8]
0x180072f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072f32  test    eax, eax
0x180072f34  jz      short loc_180072F3F
0x180072f36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072f3d  jmp     short loc_180072F4D
0x180072f3f  lea     rcx, qword_1801B97E0; this
0x180072f46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072f4d  cmp     [rcx+8], r12b
0x180072f51  jz      short loc_180072F79
0x180072f53  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072f58  cmp     [rax+7CCh], r15d
0x180072f5f  jz      short loc_180072F79
0x180072f61  mov     r9d, r15d; int
0x180072f64  lea     rdx, aCsamimediasour_8; "CSAMIMediaSource::OnReadEntireFile"
0x180072f6b  mov     r8d, 12Bh; int
0x180072f71  mov     rcx, rax; this
0x180072f74  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072f79  mov     r14d, 1
0x180072f7f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180072f86  jb      loc_1800738B8
0x180072f8c  lea     edx, [r14+23h]
0x180072f90  jmp     loc_180073899
0x180072f95  mov     rdx, [rsi+2E8h]; char *
0x180072f9c  lea     rcx, [rsi+2F8h]; this
0x180072fa3  call    ?ParseSAMI@CSAMIInterpreter@@QEAAJPEBDH@Z; CSAMIInterpreter::ParseSAMI(char const *,int)
0x180072fa8  mov     edi, eax
0x180072faa  test    eax, eax
0x180072fac  jns     loc_180073048
0x180072fb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072fb9  test    rcx, rcx
0x180072fbc  jnz     short loc_180073005
0x180072fbe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072fc5  nop     dword ptr [rax+rax+00h]
0x180072fca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072fd1  mov     rcx, rax
0x180072fd4  test    rax, rax
0x180072fd7  jz      short loc_180072FF7
0x180072fd9  mov     rax, [rax]
0x180072fdc  mov     edx, 7F0h
0x180072fe1  mov     rax, [rax+8]
0x180072fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072fea  test    eax, eax
0x180072fec  jz      short loc_180072FF7
0x180072fee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072ff5  jmp     short loc_180073005
0x180072ff7  lea     rcx, qword_1801B97E0; this
0x180072ffe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073005  cmp     [rcx+8], r12b
0x180073009  jz      short loc_18007302C
0x18007300b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073010  cmp     [rax+7CCh], edi
0x180073016  jz      short loc_18007302C
0x180073018  mov     r9d, edi; int
0x18007301b  mov     r8d, 133h; int
0x180073021  mov     rdx, r15; char *
0x180073024  mov     rcx, rax; this
0x180073027  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007302c  mov     r14d, 1
0x180073032  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180073039  jb      loc_1800738B8
0x18007303f  lea     edx, [r14+24h]
0x180073043  jmp     loc_180072ED7
0x180073048  mov     eax, [rsi+830h]
0x18007304e  mov     [rsi+0A20h], eax
0x180073054  test    eax, eax
0x180073056  jnz     loc_180073100
0x18007305c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073063  mov     r15d, 0C00D36BBh
0x180073069  mov     edi, r15d
0x18007306c  test    rcx, rcx
0x18007306f  jnz     short loc_1800730B8
0x180073071  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073078  nop     dword ptr [rax+rax+00h]
0x18007307d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073084  mov     rcx, rax
0x180073087  test    rax, rax
0x18007308a  jz      short loc_1800730AA
0x18007308c  mov     rax, [rax]
0x18007308f  mov     edx, 7F0h
0x180073094  mov     rax, [rax+8]
0x180073098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007309d  test    eax, eax
0x18007309f  jz      short loc_1800730AA
0x1800730a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800730a8  jmp     short loc_1800730B8
0x1800730aa  lea     rcx, qword_1801B97E0; this
  ... truncated ...
```
