# COOPMFTProxy::ProcessOutput(ulong,ulong,_MFT_OUTPUT_DATA_BUFFER *,ulong *)

- ea: `0x1800d0ba0`
- end: `0x1800d1763`
- name: `?ProcessOutput@COOPMFTProxy@@UEAAJKKPEAU_MFT_OUTPUT_DATA_BUFFER@@PEAK@Z`
- size: `3011`
- prototype: `__int64 __fastcall(COOPMFTProxy *this, unsigned int, unsigned int, struct _MFT_OUTPUT_DATA_BUFFER *, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004870`
- `0x180011454`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800916b8`
- `0x1800b4b10`
- `0x1800b9a34`
- `0x1800d0ba0`
- `0x1800e68b8`
- `0x1801250c8`
- `0x180138518`
- `0x180166fd0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d0bdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d0bdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1743`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1743`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d15c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d15c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d15ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1641`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1653`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d166f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d15ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1610`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1641`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1653`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d166f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1722`

## pseudocode

```c
__int64 __fastcall COOPMFTProxy::ProcessOutput(
        COOPMFTProxy *this,
        unsigned int a2,
        unsigned int a3,
        struct _MFT_OUTPUT_DATA_BUFFER *a4,
        unsigned int *a5)
{
  unsigned __int64 v5; // r13
  struct _MFT_OUTPUT_DATA_BUFFER *v7; // r12
  __int64 v9; // rdi
  CallStackTracing *v10; // rcx
  int MFSample; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  void *v18; // rcx
  __int64 v19; // r8
  _DWORD *v20; // rcx
  _QWORD *v21; // rsi
  void *v22; // rcx
  int v23; // eax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // r12d
  struct _MFT_OUTPUT_DATA_BUFFER *v28; // rdi
  __int64 v29; // r15
  int OutputCurrentType; // eax
  __int64 (__fastcall ***v31)(_QWORD, GUID *, unsigned __int64 *); // rdi
  __int64 (__fastcall *v32)(_QWORD, GUID *, unsigned __int64 *); // rbx
  int v33; // eax
  IMFSample *v34; // rax
  IMFCollection **v35; // rax
  __int64 v36; // rax
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  CallStackTracing *v50; // rcx
  struct CallStackContext *v51; // rax
  unsigned int i; // r14d
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rcx
  void *v56; // rcx
  __int64 *v57; // rcx
  __int64 v58; // rcx
  DWORD *v59; // rax
  CallStackTracing *v60; // rcx
  struct CallStackContext *v61; // rax
  struct IMFMediaType *v63; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v64; // [rsp+48h] [rbp-28h] BYREF
  LPVOID v65; // [rsp+50h] [rbp-20h] BYREF
  __int64 v66; // [rsp+58h] [rbp-18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-10h]
  LPVOID pv; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v69; // [rsp+C0h] [rbp+50h]
  struct _MFT_OUTPUT_DATA_BUFFER *v70; // [rsp+C8h] [rbp+58h]

  v70 = a4;
  v69 = a3;
  v5 = a3;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 1000);
  v7 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 25);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&pv, "COOPMFTProxy::ProcessOutput", 545);
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 127, WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids, this);
  v9 = 0;
  v65 = 0;
  v66 = 0;
  if ( *((_BYTE *)this + 1040) )
  {
    v10 = CallStackTracing::s_wpInstance;
    MFSample = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v10->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
      if ( ThreadRelativeContext->m_result != -1072873851 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "COOPMFTProxy::ProcessOutput", 551, -1072873851);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v13 = 128;
LABEL_159:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids,
        this,
        MFSample);
      goto LABEL_160;
    }
    goto LABEL_160;
  }
  if ( *((_QWORD *)this + 133) )
  {
    MFSample = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyTo<IMFTransformRemote>(
                 (char *)this + 968,
                 &v66);
    if ( MFSample < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v16 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v16->m_fEnabled )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( v17->m_result != MFSample )
          CallStackContext::TraceFailure(v17, "COOPMFTProxy::ProcessOutput", 561, MFSample);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 130;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
    pv = 0;
    MFSample = ULongLongMult(v5, 4u, (unsigned __int64 *)&pv);
    if ( MFSample < 0 || (MFSample = CTCoAllocPolicy::Alloc(v18, 1u, (unsigned __int64)pv, &v65), MFSample < 0) )
    {
      v60 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v60 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v60 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v60->m_fEnabled )
      {
        v61 = CallStackTracing::GetThreadRelativeContext(v60);
        if ( v61->m_result != MFSample )
          CallStackContext::TraceFailure(v61, "COOPMFTProxy::ProcessOutput", 562, MFSample);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v13 = 131;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
    v19 = 0;
    if ( (_DWORD)v5 )
    {
      v20 = v65;
      do
      {
        v20[v19] = v7[(unsigned int)v19].dwStreamID;
        v19 = (unsigned int)(v19 + 1);
      }
      while ( (unsigned int)v19 < (unsigned int)v5 );
    }
    v21 = 0;
    pv = 0;
    v64 = 0;
    MFSample = ULongLongMult(v5, 8u, &v64);
    if ( MFSample < 0 || (v23 = CTCoAllocPolicy::Alloc(v22, 1u, v64, &pv), v21 = pv, MFSample = v23, v23 < 0) )
    {
      v50 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v50 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v50->m_fEnabled )
      {
        v51 = CallStackTracing::GetThreadRelativeContext(v50);
        if ( MFSample < 0 && v51->m_result != MFSample )
          CallStackContext::TraceFailure(v51, "COOPMFTProxy::ProcessOutput", 568, MFSample);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_131;
      v26 = 132;
    }
    else
    {
      MFSample = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, LPVOID, LPVOID, unsigned int *))(*(_QWORD *)v66 + 56LL))(
                   v66,
                   *((_QWORD *)this + 132),
                   a2,
                   (unsigned int)v5,
                   v65,
                   pv,
                   a5);
      if ( MFSample >= 0 )
      {
        v27 = 0;
        v28 = v70;
        while ( v27 < (unsigned int)v5 )
        {
          v5 = (unsigned __int64)&v21[v27];
          if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 8LL) + 32LL) )
          {
            v48 = CallStackTracing::s_wpInstance;
            v9 = 0;
            MFSample = -1072875845;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v48 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v48 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v48->m_fEnabled )
            {
              v49 = CallStackTracing::GetThreadRelativeContext(v48);
              if ( v49->m_result != -1072875845 )
                CallStackContext::TraceFailure(v49, "COOPMFTProxy::ProcessOutput", 589, -1072875845);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                139,
                WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids,
                this,
                -1072875845);
            goto LABEL_73;
          }
          v64 = 0;
          pv = 0;
          v63 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
          v29 = v27;
          OutputCurrentType = COOPMFTProxy::GetOutputCurrentType(this, v28[v29].dwStreamID, &v63);
          v9 = 0;
          MFSample = OutputCurrentType;
          if ( OutputCurrentType < 0 )
          {
            v46 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v46 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v46 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v46->m_fEnabled )
            {
              v47 = CallStackTracing::GetThreadRelativeContext(v46);
              if ( v47->m_result != MFSample )
                CallStackContext::TraceFailure(v47, "COOPMFTProxy::ProcessOutput", 579, MFSample);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_72;
            v39 = 134;
LABEL_71:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v39,
              WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids,
              this,
              MFSample);
            goto LABEL_72;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
          MFSample = GetMFSample(
                       (struct IMFAsyncCallback *)(((unsigned __int64)this + 56)
                                                 & -(__int64)(*((_QWORD *)this + 131) != 0)),
                       (struct IMFSample **)&pv);
          if ( MFSample < 0 )
          {
            v44 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v44 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v44 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v44->m_fEnabled )
            {
              v45 = CallStackTracing::GetThreadRelativeContext(v44);
              if ( v45->m_result != MFSample )
                CallStackContext::TraceFailure(v45, "COOPMFTProxy::ProcessOutput", 581, MFSample);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_72;
            v39 = 135;
            goto LABEL_71;
          }
          MFSample = UnMarshalMFSample(
                       *(struct _MFMEDIASAMPLE_REMOTE **)(*(_QWORD *)v5 + 8LL),
                       *((struct IMFDXGIDeviceManager **)this + 131),
                       v63,
                       (struct IMFSample **)&pv);
          if ( MFSample < 0 )
          {
            v42 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v42 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v42 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v42->m_fEnabled )
            {
              v43 = CallStackTracing::GetThreadRelativeContext(v42);
              if ( v43->m_result != MFSample )
                CallStackContext::TraceFailure(v43, "COOPMFTProxy::ProcessOutput", 582, MFSample);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_72;
            v39 = 136;
            goto LABEL_71;
          }
          v31 = *(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned __int64 *))(*(_QWORD *)(*(_QWORD *)v5 + 8LL) + 32LL);
          v32 = **v31;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
          v33 = v32(v31, &GUID_00000000_0000_0000_c000_000000000046, &v64);
          v9 = 0;
          MFSample = v33;
          if ( v33 < 0 )
          {
            v40 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v40 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v40 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v40->m_fEnabled )
            {
              v41 = CallStackTracing::GetThreadRelativeContext(v40);
              if ( v41->m_result != MFSample )
                CallStackContext::TraceFailure(v41, "COOPMFTProxy::ProcessOutput", 583, MFSample);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_72;
            v39 = 137;
            goto LABEL_71;
          }
          MFSample = (*(__int64 (__fastcall **)(LPVOID, __int64 *, unsigned __int64))(*(_QWORD *)pv + 216LL))(
                       pv,
                       MFSampleExtension_RemoteSample,
                       v64);
          if ( MFSample < 0 )
          {
            v37 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v37 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v37 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v37->m_fEnabled )
            {
              v38 = CallStackTracing::GetThreadRelativeContext(v37);
              if ( v38->m_result != MFSample )
                CallStackContext::TraceFailure(v38, "COOPMFTProxy::ProcessOutput", 584, MFSample);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v39 = 138;
              goto LABEL_71;
            }
LABEL_72:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
LABEL_73:
            LODWORD(v5) = v69;
            goto LABEL_130;
          }
          v34 = (IMFSample *)pv;
          pv = 0;
          v28 = v70;
          v70[v29].pSample = v34;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
          v35 = *(IMFCollection ***)(*(_QWORD *)v5 + 24LL);
          if ( v35 )
            v28[v29].pEvents = *v35;
          v36 = *(_QWORD *)v5;
          ++v27;
          LODWORD(v5) = v69;
          v28[v29].dwStatus = **(_DWORD **)(v36 + 16);
        }
        v9 = 0;
LABEL_130:
        v7 = v70;
        goto LABEL_131;
      }
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v24->m_fEnabled )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( v25->m_result != MFSample )
          CallStackContext::TraceFailure(v25, "COOPMFTProxy::ProcessOutput", 569, MFSample);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
LABEL_131:
        if ( v21 )
        {
          for ( i = 0; i < (unsigned int)v5; ++v9 )
          {
            v53 = v21[v9];
            if ( v53 )
            {
              v54 = *(_QWORD *)(v53 + 8);
              if ( v54 )
              {
                v55 = *(_QWORD *)(v54 + 32);
                if ( v55 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                  *(_QWORD *)(*(_QWORD *)(v21[v9] + 8LL) + 32LL) = 0;
                }
                v56 = *(void **)(*(_QWORD *)(v21[v9] + 8LL) + 8LL);
                if ( v56 )
                  CloseHandle(v56);
                CoTaskMemFree(*(LPVOID *)(v21[v9] + 8LL));
                *(_QWORD *)(v21[v9] + 8LL) = 0;
              }
              v57 = *(__int64 **)(v21[v9] + 24LL);
              if ( v57 )
              {
                v58 = *v57;
                if ( v58 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
                  **(_QWORD **)(v21[v9] + 24LL) = 0;
                }
                CoTaskMemFree(*(LPVOID *)(v21[v9] + 24LL));
                *(_QWORD *)(v21[v9] + 24LL) = 0;
              }
              v59 = *(DWORD **)(v21[v9] + 16LL);
              if ( v59 )
              {
                v7[v9].dwStatus = *v59;
                CoTaskMemFree(*(LPVOID *)(v21[v9] + 16LL));
                *(_QWORD *)(v21[v9] + 16LL) = 0;
              }
              CoTaskMemFree((LPVOID)v21[v9]);
              v21[v9] = 0;
            }
            ++i;
          }
          CoTaskMemFree(v21);
        }
        goto LABEL_160;
      }
      v26 = 133;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids, this, MFSample);
    goto LABEL_131;
  }
  v14 = CallStackTracing::s_wpInstance;
  MFSample = -1072861838;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v14 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v14 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v14->m_fEnabled )
  {
    v15 = CallStackTracing::GetThreadRelativeContext(v14);
    if ( v15->m_result != -1072861838 )
      CallStackContext::TraceFailure(v15, "COOPMFTProxy::ProcessOutput", 558, -1072861838);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v13 = 129;
    goto LABEL_159;
  }
LABEL_160:
  CoTaskMemFree(v65);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&pv);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)MFSample;
}

```

## disassembly

```asm
0x1800d0ba0  mov     [rsp-38h+arg_8], rbx
0x1800d0ba5  mov     [rsp-38h+arg_18], r9
0x1800d0baa  mov     [rsp-38h+arg_10], r8d
0x1800d0baf  push    rbp
0x1800d0bb0  push    rsi
0x1800d0bb1  push    rdi
0x1800d0bb2  push    r12
0x1800d0bb4  push    r13
0x1800d0bb6  push    r14
0x1800d0bb8  push    r15
0x1800d0bba  mov     rbp, rsp
0x1800d0bbd  sub     rsp, 70h
0x1800d0bc1  lea     rax, [rcx+3E8h]
0x1800d0bc8  mov     r13d, r8d
0x1800d0bcb  mov     r14, rcx
0x1800d0bce  mov     [rbp+lpCriticalSection], rax
0x1800d0bd2  mov     rcx, rax; lpCriticalSection
0x1800d0bd5  mov     r12, r9
0x1800d0bd8  mov     r15d, edx
0x1800d0bdb  call    cs:__imp_EnterCriticalSection
0x1800d0be1  lea     rsi, aCoopmftproxyPr_2; "COOPMFTProxy::ProcessOutput"
0x1800d0be8  mov     r8d, 221h; int
0x1800d0bee  mov     rdx, rsi; char *
0x1800d0bf1  lea     rcx, [rbp+pv]; this
0x1800d0bf5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d0bfa  cmp     cs:byte_1801FD289, 10h
0x1800d0c01  jb      short loc_1800D0C22
0x1800d0c03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0c0a  lea     r8, WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids
0x1800d0c11  mov     edx, 7Fh
0x1800d0c16  mov     r9, r14
0x1800d0c19  mov     rcx, [rcx+38h]
0x1800d0c1d  call    WPP_SF_q
0x1800d0c22  xor     edi, edi
0x1800d0c24  mov     [rbp+var_20], rdi
0x1800d0c28  mov     [rbp+var_18], rdi
0x1800d0c2c  cmp     [r14+410h], dil
0x1800d0c33  jz      loc_1800D0CC9
0x1800d0c39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0c40  mov     ebx, 0C00D3E85h
0x1800d0c45  test    rcx, rcx
0x1800d0c48  jnz     short loc_1800D0C8B
0x1800d0c4a  mov     rax, cs:stru_1801FC290.__vftable
0x1800d0c51  lea     r8, stru_1801FC290
0x1800d0c58  mov     edx, 7F0h
0x1800d0c5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0c64  mov     rcx, r8
0x1800d0c67  mov     rax, [rax+8]
0x1800d0c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0c70  test    eax, eax
0x1800d0c72  jnz     short loc_1800D0C84
0x1800d0c74  lea     rcx, stru_1801F8A30
0x1800d0c7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0c82  jmp     short loc_1800D0C8B
0x1800d0c84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d0c8b  cmp     [rcx+8], dil
0x1800d0c8f  jz      short loc_1800D0CB2
0x1800d0c91  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d0c96  cmp     [rax+7CCh], ebx
0x1800d0c9c  jz      short loc_1800D0CB2
0x1800d0c9e  mov     r9d, ebx; int
0x1800d0ca1  mov     r8d, 227h; int
0x1800d0ca7  mov     rdx, rsi; char *
0x1800d0caa  mov     rcx, rax; this
0x1800d0cad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d0cb2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d0cb9  jb      loc_1800D171E
0x1800d0cbf  mov     edx, 80h
0x1800d0cc4  jmp     loc_1800D1700
0x1800d0cc9  cmp     [r14+428h], rdi
0x1800d0cd0  jnz     loc_1800D0D66
0x1800d0cd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0cdd  mov     ebx, 0C00D6D72h
0x1800d0ce2  test    rcx, rcx
0x1800d0ce5  jnz     short loc_1800D0D28
0x1800d0ce7  mov     rax, cs:stru_1801FC290.__vftable
0x1800d0cee  lea     r8, stru_1801FC290
0x1800d0cf5  mov     edx, 7F0h
0x1800d0cfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0d01  mov     rcx, r8
0x1800d0d04  mov     rax, [rax+8]
0x1800d0d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0d0d  test    eax, eax
0x1800d0d0f  jnz     short loc_1800D0D21
0x1800d0d11  lea     rcx, stru_1801F8A30
0x1800d0d18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0d1f  jmp     short loc_1800D0D28
0x1800d0d21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d0d28  cmp     [rcx+8], dil
0x1800d0d2c  jz      short loc_1800D0D4F
0x1800d0d2e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d0d33  cmp     [rax+7CCh], ebx
0x1800d0d39  jz      short loc_1800D0D4F
0x1800d0d3b  mov     r9d, ebx; int
0x1800d0d3e  mov     r8d, 22Eh; int
0x1800d0d44  mov     rdx, rsi; char *
0x1800d0d47  mov     rcx, rax; this
0x1800d0d4a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d0d4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d0d56  jb      loc_1800D171E
0x1800d0d5c  mov     edx, 81h
0x1800d0d61  jmp     loc_1800D1700
0x1800d0d66  lea     rcx, [r14+3C8h]
0x1800d0d6d  lea     rdx, [rbp+var_18]
0x1800d0d71  call    ??$CopyTo@UIMFTransformRemote@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJPEAPEAUIMFTransformRemote@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyTo<IMFTransformRemote>(IMFTransformRemote * *)
0x1800d0d76  mov     ebx, eax
0x1800d0d78  test    eax, eax
0x1800d0d7a  jns     loc_1800D0E0B
0x1800d0d80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0d87  test    rcx, rcx
0x1800d0d8a  jnz     short loc_1800D0DCD
0x1800d0d8c  mov     rcx, cs:stru_1801FC290.__vftable
0x1800d0d93  lea     r8, stru_1801FC290
0x1800d0d9a  mov     edx, 7F0h
0x1800d0d9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0da6  mov     rax, [rcx+8]
0x1800d0daa  mov     rcx, r8
0x1800d0dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0db2  test    eax, eax
0x1800d0db4  jnz     short loc_1800D0DC6
0x1800d0db6  lea     rcx, stru_1801F8A30
0x1800d0dbd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0dc4  jmp     short loc_1800D0DCD
0x1800d0dc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d0dcd  cmp     [rcx+8], dil
0x1800d0dd1  jz      short loc_1800D0DF4
0x1800d0dd3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d0dd8  cmp     [rax+7CCh], ebx
0x1800d0dde  jz      short loc_1800D0DF4
0x1800d0de0  mov     r9d, ebx; int
0x1800d0de3  mov     r8d, 231h; int
0x1800d0de9  mov     rdx, rsi; char *
0x1800d0dec  mov     rcx, rax; this
0x1800d0def  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d0df4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d0dfb  jb      loc_1800D171E
0x1800d0e01  mov     edx, 82h
0x1800d0e06  jmp     loc_1800D1700
0x1800d0e0b  lea     r8, [rbp+pv]; unsigned __int64 *
0x1800d0e0f  mov     [rbp+pv], rdi
0x1800d0e13  mov     edx, 4; unsigned __int64
0x1800d0e18  mov     rcx, r13; unsigned __int64
0x1800d0e1b  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800d0e20  mov     ebx, eax
0x1800d0e22  test    eax, eax
0x1800d0e24  js      loc_1800D167A
0x1800d0e2a  mov     r8, [rbp+pv]; unsigned __int64
0x1800d0e2e  lea     r9, [rbp+var_20]; void **
0x1800d0e32  mov     edx, 1; unsigned int
0x1800d0e37  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800d0e3c  mov     ebx, eax
0x1800d0e3e  test    eax, eax
0x1800d0e40  js      loc_1800D167A
0x1800d0e46  xor     r8d, r8d
0x1800d0e49  test    r13d, r13d
0x1800d0e4c  jz      short loc_1800D0E69
0x1800d0e4e  mov     rcx, [rbp+var_20]
0x1800d0e52  mov     eax, r8d
0x1800d0e55  shl     rax, 5
0x1800d0e59  mov     eax, [rax+r12]
0x1800d0e5d  mov     [rcx+r8*4], eax
0x1800d0e61  inc     r8d
0x1800d0e64  cmp     r8d, r13d
0x1800d0e67  jb      short loc_1800D0E52
0x1800d0e69  xor     esi, esi
0x1800d0e6b  lea     r8, [rbp+var_28]; unsigned __int64 *
0x1800d0e6f  mov     rcx, r13; unsigned __int64
0x1800d0e72  mov     [rbp+pv], rsi
0x1800d0e76  mov     [rbp+var_28], rsi
0x1800d0e7a  lea     edx, [rsi+8]; unsigned __int64
0x1800d0e7d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800d0e82  mov     ebx, eax
0x1800d0e84  test    eax, eax
0x1800d0e86  js      loc_1800D14CB
0x1800d0e8c  mov     r8, [rbp+var_28]; unsigned __int64
0x1800d0e90  lea     r9, [rbp+pv]; void **
0x1800d0e94  lea     edx, [rsi+1]; unsigned int
0x1800d0e97  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800d0e9c  mov     rsi, [rbp+pv]
0x1800d0ea0  mov     ebx, eax
0x1800d0ea2  test    eax, eax
0x1800d0ea4  js      loc_1800D14CB
0x1800d0eaa  mov     rcx, [rbp+var_18]
0x1800d0eae  mov     r9d, r13d
0x1800d0eb1  mov     rdx, [rbp+arg_20]
0x1800d0eb5  mov     r8d, r15d
0x1800d0eb8  mov     [rsp+70h+var_40], rdx
0x1800d0ebd  mov     rdx, [rbp+var_20]
0x1800d0ec1  mov     rax, [rcx]
0x1800d0ec4  mov     [rsp+70h+var_48], rsi
0x1800d0ec9  mov     [rsp+70h+var_50], rdx
0x1800d0ece  mov     rdx, [r14+420h]
0x1800d0ed5  mov     rax, [rax+38h]
0x1800d0ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0ede  mov     ebx, eax
0x1800d0ee0  test    eax, eax
0x1800d0ee2  jns     loc_1800D0F95
0x1800d0ee8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0eef  test    rcx, rcx
0x1800d0ef2  jnz     short loc_1800D0F35
0x1800d0ef4  mov     rax, cs:stru_1801FC290.__vftable
0x1800d0efb  lea     r8, stru_1801FC290
0x1800d0f02  mov     edx, 7F0h
0x1800d0f07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0f0e  mov     rcx, r8
0x1800d0f11  mov     rax, [rax+8]
0x1800d0f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0f1a  test    eax, eax
0x1800d0f1c  jnz     short loc_1800D0F2E
0x1800d0f1e  lea     rcx, stru_1801F8A30
0x1800d0f25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d0f2c  jmp     short loc_1800D0F35
0x1800d0f2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d0f35  cmp     [rcx+8], dil
0x1800d0f39  jz      short loc_1800D0F60
0x1800d0f3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d0f40  cmp     [rax+7CCh], ebx
0x1800d0f46  jz      short loc_1800D0F60
0x1800d0f48  mov     r9d, ebx; int
0x1800d0f4b  lea     rdx, aCoopmftproxyPr_2; "COOPMFTProxy::ProcessOutput"
0x1800d0f52  mov     r8d, 239h; int
0x1800d0f58  mov     rcx, rax; this
0x1800d0f5b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d0f60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d0f67  jb      loc_1800D1560
0x1800d0f6d  mov     edx, 85h
0x1800d0f72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0f79  lea     r8, WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids
0x1800d0f80  mov     r9, r14
0x1800d0f83  mov     dword ptr [rsp+70h+var_50], ebx
0x1800d0f87  mov     rcx, [rcx+10h]
0x1800d0f8b  call    WPP_SF_qD
0x1800d0f90  jmp     loc_1800D1560
0x1800d0f95  mov     r12d, edi
0x1800d0f98  mov     rdi, [rbp+arg_18]
0x1800d0f9c  cmp     r12d, r13d
0x1800d0f9f  jnb     loc_1800D155A
0x1800d0fa5  mov     r15d, r12d
0x1800d0fa8  lea     r13, [rsi+r15*8]
0x1800d0fac  mov     rax, [r13+0]
0x1800d0fb0  mov     rcx, [rax+8]
0x1800d0fb4  cmp     qword ptr [rcx+20h], 0
0x1800d0fb9  jz      loc_1800D1417
0x1800d0fbf  lea     rcx, [rbp+var_30]
0x1800d0fc3  mov     [rbp+var_28], 0
0x1800d0fcb  mov     [rbp+pv], 0
0x1800d0fd3  mov     [rbp+var_30], 0
0x1800d0fdb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d0fe0  shl     r15, 5
0x1800d0fe4  lea     r8, [rbp+var_30]; struct IMFMediaType **
0x1800d0fe8  mov     rcx, r14; this
0x1800d0feb  mov     edx, [r15+rdi]; unsigned int
0x1800d0fef  call    ?GetOutputCurrentType@COOPMFTProxy@@UEAAJKPEAPEAUIMFMediaType@@@Z; COOPMFTProxy::GetOutputCurrentType(ulong,IMFMediaType * *)
0x1800d0ff4  xor     edi, edi
0x1800d0ff6  mov     ebx, eax
0x1800d0ff8  test    eax, eax
0x1800d0ffa  js      loc_1800D1388
0x1800d1000  lea     rcx, [rbp+pv]
0x1800d1004  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d1009  mov     rax, [r14+418h]
0x1800d1010  lea     rdx, [r14+38h]
0x1800d1014  neg     rax
0x1800d1017  sbb     rcx, rcx
0x1800d101a  and     rcx, rdx; struct IMFAsyncCallback *
0x1800d101d  lea     rdx, [rbp+pv]; struct IMFSample **
0x1800d1021  call    ?GetMFSample@@YAJPEAUIMFAsyncCallback@@PEAPEAUIMFSample@@@Z; GetMFSample(IMFAsyncCallback *,IMFSample * *)
0x1800d1026  mov     ebx, eax
0x1800d1028  test    eax, eax
0x1800d102a  js      loc_1800D12F9
0x1800d1030  mov     rcx, [r13+0]
0x1800d1034  lea     r9, [rbp+pv]; struct IMFSample **
0x1800d1038  mov     r8, [rbp+var_30]; struct IMFMediaType *
0x1800d103c  mov     rdx, [r14+418h]; struct IMFDXGIDeviceManager *
0x1800d1043  mov     rcx, [rcx+8]; struct _MFMEDIASAMPLE_REMOTE *
0x1800d1047  call    ?UnMarshalMFSample@@YAJPEAU_MFMEDIASAMPLE_REMOTE@@PEAUIMFDXGIDeviceManager@@PEAUIMFMediaType@@PEAPEAUIMFSample@@@Z; UnMarshalMFSample(_MFMEDIASAMPLE_REMOTE *,IMFDXGIDeviceManager *,IMFMediaType *,IMFSample * *)
0x1800d104c  mov     ebx, eax
0x1800d104e  test    eax, eax
0x1800d1050  js      loc_1800D126A
0x1800d1056  mov     rax, [r13+0]
0x1800d105a  mov     rcx, [rax+8]
0x1800d105e  mov     rdi, [rcx+20h]
0x1800d1062  lea     rcx, [rbp+var_28]
0x1800d1066  mov     rax, [rdi]
0x1800d1069  mov     rbx, [rax]
0x1800d106c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d1071  lea     r8, [rbp+var_28]
0x1800d1075  mov     rcx, rdi
0x1800d1078  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800d107f  mov     rax, rbx
0x1800d1082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1087  xor     edi, edi
0x1800d1089  mov     ebx, eax
0x1800d108b  test    eax, eax
0x1800d108d  js      loc_1800D11DB
0x1800d1093  mov     rcx, [rbp+pv]
0x1800d1097  lea     rdx, MFSampleExtension_RemoteSample
0x1800d109e  mov     r8, [rbp+var_28]
0x1800d10a2  mov     rax, [rcx]
0x1800d10a5  mov     rax, [rax+0D8h]
0x1800d10ac  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
