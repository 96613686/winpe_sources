# MFDSUtils::DShowSampleToMFSample(IMediaSample *,IMFSample * *,__int64,CMediaType *,int)

- ea: `0x180069934`
- end: `0x18006a475`
- name: `?DShowSampleToMFSample@MFDSUtils@@YAJPEAUIMediaSample@@PEAPEAUIMFSample@@_JPEAVCMediaType@@H@Z`
- size: `2881`
- prototype: `__int64 __usercall@<rax>(MFDSUtils *__hidden this@<rcx>, struct IMediaSample *@<rdx>, struct IMFSample **@<r8>, __int64@<r9>, struct CMediaType *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005bb20`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x180051ce4`
- `0x1800618d8`
- `0x180069934`
- `0x180074a06`
- `0x1800c9010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800699be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069a98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069b46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069bfd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069cdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069d9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069e54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069f3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069ff5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a0cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a1f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a2d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a35d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800699be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069a98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069b46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069bfd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069cdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069d9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069e54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069f3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069ff5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a0cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a1f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a2d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a35d`
- `MFPlat!MFCreateSample` at `0x18006999c`
- `MFPlat!MFCreateSample` at `0x18006999c`
- `MFPlat!MFCreateMemoryBuffer` at `0x180069a76`
- `MFPlat!MFCreateMemoryBuffer` at `0x180069a76`
- `MFPlat!MFCopyImage` at `0x180069caa`
- `MFPlat!MFCopyImage` at `0x180069caa`

## pseudocode

```c
__int64 __fastcall MFDSUtils::DShowSampleToMFSample(
        MFDSUtils *this,
        struct IMediaSample *a2,
        struct IMFSample **a3,
        struct IMFSample *a4,
        struct CMediaType *a5)
{
  HRESULT v9; // ebx
  CallStackTracing *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  DWORD v14; // eax
  CallStackTracing *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  DWORD dwWidthInBytes; // eax
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  IMFMediaBuffer *v28; // rdi
  HRESULT (__stdcall *SetCurrentLength)(IMFMediaBuffer *, DWORD); // rbx
  unsigned int v30; // eax
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  int v37; // eax
  CallStackTracing *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rbx
  CallStackTracing *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  struct CMediaType *v51; // r9
  CallStackTracing *v52; // rcx
  CallStackTracing *v53; // rax
  CallStackTracing *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *v57; // rax
  _BYTE v59[8]; // [rsp+30h] [rbp-81h] BYREF
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-79h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+40h] [rbp-71h] BYREF
  __int64 v62; // [rsp+48h] [rbp-69h] BYREF
  int v63; // [rsp+50h] [rbp-61h] BYREF
  int v64; // [rsp+54h] [rbp-5Dh] BYREF
  char *v65; // [rsp+58h] [rbp-59h] BYREF
  __int64 v66; // [rsp+60h] [rbp-51h] BYREF
  BYTE *pSrc; // [rsp+68h] [rbp-49h] BYREF
  BYTE *pDest; // [rsp+70h] [rbp-41h] BYREF
  __int64 v69; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v70[128]; // [rsp+80h] [rbp-31h] BYREF

  ppIMFSample = 0;
  ppBuffer = 0;
  v69 = 0;
  v66 = 0;
  v65 = 0;
  pSrc = 0;
  pDest = 0;
  v64 = 0;
  v63 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v59, "MFDSUtils::DShowSampleToMFSample", 40);
  v9 = MFCreateSample(&ppIMFSample);
  if ( v9 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(MFDSUtils *))(*(_QWORD *)this + 32LL))(this);
    v9 = MFCreateMemoryBuffer(v14, &ppBuffer);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(MFDSUtils *, BYTE **))(*(_QWORD *)this + 24LL))(this, &pSrc);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *, BYTE **, int *, int *))ppBuffer->lpVtbl->Lock)(
               ppBuffer,
               &pDest,
               &v64,
               &v63);
        if ( v9 >= 0 )
        {
          dwWidthInBytes = (*(__int64 (__fastcall **)(MFDSUtils *))(*(_QWORD *)this + 32LL))(this);
          MFCopyImage(pDest, dwWidthInBytes, pSrc, dwWidthInBytes, dwWidthInBytes, 1u);
          v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
          if ( v9 >= 0 )
          {
            v28 = ppBuffer;
            SetCurrentLength = ppBuffer->lpVtbl->SetCurrentLength;
            v30 = (*(__int64 (__fastcall **)(MFDSUtils *))(*(_QWORD *)this + 88LL))(this);
            v9 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))SetCurrentLength)(v28, v30);
            if ( v9 >= 0 )
            {
              v9 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                     ppIMFSample,
                     ppBuffer);
              if ( v9 >= 0 )
              {
                v37 = (*(__int64 (__fastcall **)(MFDSUtils *, __int64 *, char **))(*(_QWORD *)this + 40LL))(
                        this,
                        &v66,
                        &v65);
                if ( v37 != -2147220919 )
                {
                  if ( v37 == 262768 )
                    v65 = (char *)a3 + v66;
                  v9 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(
                         ppIMFSample,
                         v66);
                  if ( v9 < 0 )
                  {
                    v38 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                      CallStackTracing::s_wpInstance = v39;
                      if ( v39
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(
                             v39,
                             2032) )
                      {
                        v38 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v38 = (CallStackTracing *)&qword_1800EB130;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                      }
                    }
                    if ( *((_BYTE *)v38 + 8) )
                    {
                      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v38);
                      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
                        CallStackContext::TraceFailure(
                          ThreadRelativeContext,
                          "MFDSUtils::DShowSampleToMFSample",
                          80,
                          v9);
                    }
                    if ( g_wppLevels )
                    {
                      v13 = 17;
                      goto LABEL_12;
                    }
                    goto LABEL_157;
                  }
                  v9 = ((__int64 (__fastcall *)(IMFSample *, char *))ppIMFSample->lpVtbl->SetSampleDuration)(
                         ppIMFSample,
                         &v65[-v66]);
                  if ( v9 < 0 )
                  {
                    v41 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                      CallStackTracing::s_wpInstance = v42;
                      if ( v42
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(
                             v42,
                             2032) )
                      {
                        v41 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v41 = (CallStackTracing *)&qword_1800EB130;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                      }
                    }
                    if ( *((_BYTE *)v41 + 8) )
                    {
                      v43 = CallStackTracing::GetThreadRelativeContext(v41);
                      if ( *((_DWORD *)v43 + 499) != v9 )
                        CallStackContext::TraceFailure(v43, "MFDSUtils::DShowSampleToMFSample", 81, v9);
                    }
                    if ( g_wppLevels )
                    {
                      v13 = 18;
                      goto LABEL_12;
                    }
                    goto LABEL_157;
                  }
                }
                if ( (*(unsigned int (__fastcall **)(MFDSUtils *))(*(_QWORD *)this + 56LL))(this)
                  || (v9 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                             ppIMFSample,
                             &MFSampleExtension_CleanPoint,
                             1),
                      v9 >= 0) )
                {
                  v47 = *(_QWORD *)this;
                  if ( (_DWORD)a5 )
                  {
                    v62 = 0;
                    memset_0(v70, 0, 0x40u);
                    if ( (*(int (__fastcall **)(MFDSUtils *, GUID *, __int64 *))v47)(
                           this,
                           &GUID_36b73884_c2c8_11cf_8b46_00805f6cef60,
                           &v62) >= 0
                      && (*(int (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v62 + 152LL))(v62, 64, v70) >= 0
                      && (v70[8] & 0x40) != 0 )
                    {
                      v9 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                             ppIMFSample,
                             &MFSampleExtension_Discontinuity,
                             1);
                      if ( v9 < 0 )
                      {
                        v48 = CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                          CallStackTracing::s_wpInstance = v49;
                          if ( v49
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(
                                 v49,
                                 2032) )
                          {
                            v48 = CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v48 = (CallStackTracing *)&qword_1800EB130;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                          }
                        }
                        if ( *((_BYTE *)v48 + 8) )
                        {
                          v50 = CallStackTracing::GetThreadRelativeContext(v48);
                          if ( *((_DWORD *)v50 + 499) != v9 )
                            CallStackContext::TraceFailure(v50, "MFDSUtils::DShowSampleToMFSample", 103, v9);
                        }
                        if ( g_wppLevels )
                          WPP_SF_qD(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            20,
                            &WPP_c5bc35423be535bbd1b3448c3ea9d8bd_Traceguids,
                            0,
                            v9);
                        ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v62);
                        goto LABEL_157;
                      }
                    }
                    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v62);
                  }
                  else if ( !(*(unsigned int (__fastcall **)(MFDSUtils *))(v47 + 120))(this) )
                  {
                    v9 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
                           ppIMFSample,
                           &MFSampleExtension_Discontinuity,
                           1);
                    if ( v9 < 0 )
                    {
                      v54 = CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                        CallStackTracing::s_wpInstance = v55;
                        if ( v55
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(
                               v55,
                               2032) )
                        {
                          v54 = CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v54 = (CallStackTracing *)&qword_1800EB130;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                        }
                      }
                      if ( *((_BYTE *)v54 + 8) )
                      {
                        v56 = CallStackTracing::GetThreadRelativeContext(v54);
                        if ( *((_DWORD *)v56 + 499) != v9 )
                          CallStackContext::TraceFailure(v56, "MFDSUtils::DShowSampleToMFSample", 114, v9);
                      }
                      if ( g_wppLevels )
                      {
                        v13 = 21;
                        goto LABEL_12;
                      }
                      goto LABEL_157;
                    }
                  }
                  v9 = MFDSUtils::TransferSampleFlags(this, (struct IMediaSample *)ppIMFSample, a4, v51);
                  if ( v9 >= 0 )
                  {
                    a2->lpVtbl = (struct IMediaSampleVtbl *)ppIMFSample;
                    ppIMFSample = 0;
                    goto LABEL_157;
                  }
                  v52 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                    CallStackTracing::s_wpInstance = v53;
                    if ( v53
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                    {
                      v52 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v52 = (CallStackTracing *)&qword_1800EB130;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                    }
                  }
                  if ( *((_BYTE *)v52 + 8) )
                  {
                    v57 = CallStackTracing::GetThreadRelativeContext(v52);
                    if ( *((_DWORD *)v57 + 499) != v9 )
                      CallStackContext::TraceFailure(v57, "MFDSUtils::DShowSampleToMFSample", 121, v9);
                  }
                  if ( g_wppLevels )
                  {
                    v13 = 22;
                    goto LABEL_12;
                  }
                  goto LABEL_157;
                }
                v44 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                  CallStackTracing::s_wpInstance = v45;
                  if ( v45
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
                  {
                    v44 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v44 = (CallStackTracing *)&qword_1800EB130;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                  }
                }
                if ( *((_BYTE *)v44 + 8) )
                {
                  v46 = CallStackTracing::GetThreadRelativeContext(v44);
                  if ( *((_DWORD *)v46 + 499) != v9 )
                    CallStackContext::TraceFailure(v46, "MFDSUtils::DShowSampleToMFSample", 90, v9);
                }
                if ( g_wppLevels )
                {
                  v13 = 19;
                  goto LABEL_12;
                }
              }
              else
              {
                v34 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                  CallStackTracing::s_wpInstance = v35;
                  if ( v35
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
                  {
                    v34 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v34 = (CallStackTracing *)&qword_1800EB130;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                  }
                }
                if ( *((_BYTE *)v34 + 8) )
                {
                  v36 = CallStackTracing::GetThreadRelativeContext(v34);
                  if ( *((_DWORD *)v36 + 499) != v9 )
                    CallStackContext::TraceFailure(v36, "MFDSUtils::DShowSampleToMFSample", 58, v9);
                }
                if ( g_wppLevels )
                {
                  v13 = 16;
                  goto LABEL_12;
                }
              }
            }
            else
            {
              v31 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v32;
                if ( v32
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                {
                  v31 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v31 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v31 + 8) )
              {
                v33 = CallStackTracing::GetThreadRelativeContext(v31);
                if ( *((_DWORD *)v33 + 499) != v9 )
                  CallStackContext::TraceFailure(v33, "MFDSUtils::DShowSampleToMFSample", 56, v9);
              }
              if ( g_wppLevels )
              {
                v13 = 15;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v25 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
              {
                v25 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v25 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v25 + 8) )
            {
              v27 = CallStackTracing::GetThreadRelativeContext(v25);
              if ( *((_DWORD *)v27 + 499) != v9 )
                CallStackContext::TraceFailure(v27, "MFDSUtils::DShowSampleToMFSample", 54, v9);
            }
            if ( g_wppLevels )
            {
              v13 = 14;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v21 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v21 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            v23 = CallStackTracing::GetThreadRelativeContext(v21);
            if ( *((_DWORD *)v23 + 499) != v9 )
              CallStackContext::TraceFailure(v23, "MFDSUtils::DShowSampleToMFSample", 49, v9);
          }
          if ( g_wppLevels )
          {
            v13 = 13;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v18 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext(v18);
          if ( *((_DWORD *)v20 + 499) != v9 )
            CallStackContext::TraceFailure(v20, "MFDSUtils::DShowSampleToMFSample", 47, v9);
        }
        if ( g_wppLevels )
        {
          v13 = 12;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(v15);
        if ( *((_DWORD *)v17 + 499) != v9 )
          CallStackContext::TraceFailure(v17, "MFDSUtils::DShowSampleToMFSample", 45, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 11;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v12 + 499) != v9 )
        CallStackContext::TraceFailure(v12, "MFDSUtils::DShowSampleToMFSample", 40, v9);
    }
    if ( g_wppLevels )
    {
      v13 = 10;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_c5bc35423be535bbd1b3448c3ea9d8bd_Traceguids, 0, v9);
    }
  }
LABEL_157:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v59);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v69);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppBuffer);
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppIMFSample);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180069934  push    rbp
0x180069936  push    rbx
0x180069937  push    rsi
0x180069938  push    rdi
0x180069939  push    r12
0x18006993b  push    r13
0x18006993d  push    r14
0x18006993f  push    r15
0x180069941  lea     rbp, [rsp-17h]
0x180069946  sub     rsp, 0C8h
0x18006994d  xor     r13d, r13d
0x180069950  lea     rdi, aMfdsutilsDshow; "MFDSUtils::DShowSampleToMFSample"
0x180069957  mov     r14, r8
0x18006995a  mov     [rbp+4Fh+ppIMFSample], r13
0x18006995e  mov     r15, rdx
0x180069961  mov     [rbp+4Fh+ppBuffer], r13
0x180069965  mov     rsi, rcx
0x180069968  mov     [rbp+4Fh+var_88], r13
0x18006996c  lea     r8d, [r13+28h]; int
0x180069970  mov     [rbp+4Fh+var_A0], r13
0x180069974  mov     rdx, rdi; char *
0x180069977  mov     [rbp+4Fh+var_A8], r13
0x18006997b  lea     rcx, [rsp+100h+var_D0]; this
0x180069980  mov     [rbp+4Fh+pSrc], r13
0x180069984  mov     r12, r9
0x180069987  mov     [rbp+4Fh+pDest], r13
0x18006998b  mov     [rbp+4Fh+var_AC], r13d
0x18006998f  mov     [rbp+4Fh+var_B0], r13d
0x180069993  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180069998  lea     rcx, [rbp+4Fh+ppIMFSample]; ppIMFSample
0x18006999c  call    cs:__imp_MFCreateSample
0x1800699a3  nop     dword ptr [rax+rax+00h]
0x1800699a8  mov     ebx, eax
0x1800699aa  test    eax, eax
0x1800699ac  jns     loc_180069A61
0x1800699b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800699b9  test    rcx, rcx
0x1800699bc  jnz     short loc_180069A05
0x1800699be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800699c5  nop     dword ptr [rax+rax+00h]
0x1800699ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800699d1  mov     rcx, rax
0x1800699d4  test    rax, rax
0x1800699d7  jz      short loc_1800699F7
0x1800699d9  mov     rax, [rax]
0x1800699dc  mov     edx, 7F0h
0x1800699e1  mov     rax, [rax+8]
0x1800699e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699ea  test    eax, eax
0x1800699ec  jz      short loc_1800699F7
0x1800699ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800699f5  jmp     short loc_180069A05
0x1800699f7  lea     rcx, qword_1800EB130; this
0x1800699fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069a05  cmp     [rcx+8], r13b
0x180069a09  jz      short loc_180069A2C
0x180069a0b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069a10  cmp     [rax+7CCh], ebx
0x180069a16  jz      short loc_180069A2C
0x180069a18  mov     r9d, ebx; int
0x180069a1b  mov     r8d, 28h ; '('; int
0x180069a21  mov     rdx, rdi; char *
0x180069a24  mov     rcx, rax; this
0x180069a27  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069a2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069a33  jb      loc_18006A439
0x180069a39  mov     edx, 0Ah
0x180069a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180069a45  lea     r8, WPP_c5bc35423be535bbd1b3448c3ea9d8bd_Traceguids
0x180069a4c  xor     r9d, r9d
0x180069a4f  mov     [rsp+100h+dwWidthInBytes], ebx
0x180069a53  mov     rcx, [rcx+10h]
0x180069a57  call    WPP_SF_qD
0x180069a5c  jmp     loc_18006A439
0x180069a61  mov     rax, [rsi]
0x180069a64  mov     rcx, rsi
0x180069a67  mov     rax, [rax+20h]
0x180069a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a70  lea     rdx, [rbp+4Fh+ppBuffer]; ppBuffer
0x180069a74  mov     ecx, eax; cbMaxLength
0x180069a76  call    cs:__imp_MFCreateMemoryBuffer
0x180069a7d  nop     dword ptr [rax+rax+00h]
0x180069a82  mov     ebx, eax
0x180069a84  test    eax, eax
0x180069a86  jns     loc_180069B1D
0x180069a8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069a93  test    rcx, rcx
0x180069a96  jnz     short loc_180069ADF
0x180069a98  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069a9f  nop     dword ptr [rax+rax+00h]
0x180069aa4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069aab  mov     rcx, rax
0x180069aae  test    rax, rax
0x180069ab1  jz      short loc_180069AD1
0x180069ab3  mov     rax, [rax]
0x180069ab6  mov     edx, 7F0h
0x180069abb  mov     rax, [rax+8]
0x180069abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ac4  test    eax, eax
0x180069ac6  jz      short loc_180069AD1
0x180069ac8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069acf  jmp     short loc_180069ADF
0x180069ad1  lea     rcx, qword_1800EB130; this
0x180069ad8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069adf  cmp     [rcx+8], r13b
0x180069ae3  jz      short loc_180069B06
0x180069ae5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069aea  cmp     [rax+7CCh], ebx
0x180069af0  jz      short loc_180069B06
0x180069af2  mov     r9d, ebx; int
0x180069af5  mov     r8d, 2Dh ; '-'; int
0x180069afb  mov     rdx, rdi; char *
0x180069afe  mov     rcx, rax; this
0x180069b01  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069b06  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069b0d  jb      loc_18006A439
0x180069b13  mov     edx, 0Bh
0x180069b18  jmp     loc_180069A3E
0x180069b1d  mov     rax, [rsi]
0x180069b20  lea     rdx, [rbp+4Fh+pSrc]
0x180069b24  mov     rcx, rsi
0x180069b27  mov     rax, [rax+18h]
0x180069b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b30  mov     ebx, eax
0x180069b32  test    eax, eax
0x180069b34  jns     loc_180069BCB
0x180069b3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069b41  test    rcx, rcx
0x180069b44  jnz     short loc_180069B8D
0x180069b46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069b4d  nop     dword ptr [rax+rax+00h]
0x180069b52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069b59  mov     rcx, rax
0x180069b5c  test    rax, rax
0x180069b5f  jz      short loc_180069B7F
0x180069b61  mov     rax, [rax]
0x180069b64  mov     edx, 7F0h
0x180069b69  mov     rax, [rax+8]
0x180069b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b72  test    eax, eax
0x180069b74  jz      short loc_180069B7F
0x180069b76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069b7d  jmp     short loc_180069B8D
0x180069b7f  lea     rcx, qword_1800EB130; this
0x180069b86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069b8d  cmp     [rcx+8], r13b
0x180069b91  jz      short loc_180069BB4
0x180069b93  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069b98  cmp     [rax+7CCh], ebx
0x180069b9e  jz      short loc_180069BB4
0x180069ba0  mov     r9d, ebx; int
0x180069ba3  mov     r8d, 2Fh ; '/'; int
0x180069ba9  mov     rdx, rdi; char *
0x180069bac  mov     rcx, rax; this
0x180069baf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069bb4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069bbb  jb      loc_18006A439
0x180069bc1  mov     edx, 0Ch
0x180069bc6  jmp     loc_180069A3E
0x180069bcb  mov     rcx, [rbp+4Fh+ppBuffer]
0x180069bcf  lea     r9, [rbp+4Fh+var_B0]
0x180069bd3  lea     r8, [rbp+4Fh+var_AC]
0x180069bd7  lea     rdx, [rbp+4Fh+pDest]
0x180069bdb  mov     rax, [rcx]
0x180069bde  mov     rax, [rax+18h]
0x180069be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069be7  mov     ebx, eax
0x180069be9  test    eax, eax
0x180069beb  jns     loc_180069C82
0x180069bf1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069bf8  test    rcx, rcx
0x180069bfb  jnz     short loc_180069C44
0x180069bfd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069c04  nop     dword ptr [rax+rax+00h]
0x180069c09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069c10  mov     rcx, rax
0x180069c13  test    rax, rax
0x180069c16  jz      short loc_180069C36
0x180069c18  mov     rax, [rax]
0x180069c1b  mov     edx, 7F0h
0x180069c20  mov     rax, [rax+8]
0x180069c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069c29  test    eax, eax
0x180069c2b  jz      short loc_180069C36
0x180069c2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069c34  jmp     short loc_180069C44
0x180069c36  lea     rcx, qword_1800EB130; this
0x180069c3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069c44  cmp     [rcx+8], r13b
0x180069c48  jz      short loc_180069C6B
0x180069c4a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069c4f  cmp     [rax+7CCh], ebx
0x180069c55  jz      short loc_180069C6B
0x180069c57  mov     r9d, ebx; int
0x180069c5a  mov     r8d, 31h ; '1'; int
0x180069c60  mov     rdx, rdi; char *
0x180069c63  mov     rcx, rax; this
0x180069c66  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069c6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069c72  jb      loc_18006A439
0x180069c78  mov     edx, 0Dh
0x180069c7d  jmp     loc_180069A3E
0x180069c82  mov     rax, [rsi]
0x180069c85  mov     rcx, rsi
0x180069c88  mov     rax, [rax+20h]
0x180069c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069c91  mov     r8, [rbp+4Fh+pSrc]; pSrc
0x180069c95  mov     r9d, eax; lSrcStride
0x180069c98  mov     rcx, [rbp+4Fh+pDest]; pDest
0x180069c9c  mov     edx, eax; lDestStride
0x180069c9e  mov     [rsp+100h+dwLines], 1; dwLines
0x180069ca6  mov     [rsp+100h+dwWidthInBytes], eax; dwWidthInBytes
0x180069caa  call    cs:__imp_MFCopyImage
0x180069cb1  nop     dword ptr [rax+rax+00h]
0x180069cb6  mov     rcx, [rbp+4Fh+ppBuffer]
0x180069cba  mov     rax, [rcx]
0x180069cbd  mov     rax, [rax+20h]
0x180069cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069cc6  mov     ebx, eax
0x180069cc8  test    eax, eax
0x180069cca  jns     loc_180069D61
0x180069cd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069cd7  test    rcx, rcx
0x180069cda  jnz     short loc_180069D23
0x180069cdc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069ce3  nop     dword ptr [rax+rax+00h]
0x180069ce8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069cef  mov     rcx, rax
0x180069cf2  test    rax, rax
0x180069cf5  jz      short loc_180069D15
0x180069cf7  mov     rax, [rax]
0x180069cfa  mov     edx, 7F0h
0x180069cff  mov     rax, [rax+8]
0x180069d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d08  test    eax, eax
0x180069d0a  jz      short loc_180069D15
0x180069d0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d13  jmp     short loc_180069D23
0x180069d15  lea     rcx, qword_1800EB130; this
0x180069d1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d23  cmp     [rcx+8], r13b
0x180069d27  jz      short loc_180069D4A
0x180069d29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069d2e  cmp     [rax+7CCh], ebx
0x180069d34  jz      short loc_180069D4A
0x180069d36  mov     r9d, ebx; int
0x180069d39  mov     r8d, 36h ; '6'; int
0x180069d3f  mov     rdx, rdi; char *
0x180069d42  mov     rcx, rax; this
0x180069d45  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069d4a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069d51  jb      loc_18006A439
0x180069d57  mov     edx, 0Eh
0x180069d5c  jmp     loc_180069A3E
0x180069d61  mov     rdi, [rbp+4Fh+ppBuffer]
0x180069d65  mov     rcx, rsi
0x180069d68  mov     rdx, [rsi]
0x180069d6b  mov     rax, [rdi]
0x180069d6e  mov     rbx, [rax+30h]
0x180069d72  mov     rax, [rdx+58h]
0x180069d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d7b  mov     edx, eax
0x180069d7d  mov     rcx, rdi
0x180069d80  mov     rax, rbx
0x180069d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d88  mov     ebx, eax
0x180069d8a  test    eax, eax
0x180069d8c  jns     loc_180069E27
0x180069d92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069d99  test    rcx, rcx
0x180069d9c  jnz     short loc_180069DE5
0x180069d9e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069da5  nop     dword ptr [rax+rax+00h]
0x180069daa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069db1  mov     rcx, rax
0x180069db4  test    rax, rax
0x180069db7  jz      short loc_180069DD7
0x180069db9  mov     rax, [rax]
0x180069dbc  mov     edx, 7F0h
0x180069dc1  mov     rax, [rax+8]
0x180069dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069dca  test    eax, eax
0x180069dcc  jz      short loc_180069DD7
0x180069dce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069dd5  jmp     short loc_180069DE5
0x180069dd7  lea     rcx, qword_1800EB130; this
0x180069dde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069de5  cmp     [rcx+8], r13b
0x180069de9  jz      short loc_180069E10
0x180069deb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069df0  cmp     [rax+7CCh], ebx
0x180069df6  jz      short loc_180069E10
0x180069df8  mov     r9d, ebx; int
0x180069dfb  lea     rdx, aMfdsutilsDshow; "MFDSUtils::DShowSampleToMFSample"
0x180069e02  mov     r8d, 38h ; '8'; int
0x180069e08  mov     rcx, rax; this
0x180069e0b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069e10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069e17  jb      loc_18006A439
0x180069e1d  mov     edx, 0Fh
  ... truncated ...
```
