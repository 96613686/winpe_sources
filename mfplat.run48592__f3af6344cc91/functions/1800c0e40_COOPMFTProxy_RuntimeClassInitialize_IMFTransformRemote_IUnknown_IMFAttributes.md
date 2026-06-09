# COOPMFTProxy::RuntimeClassInitialize(IMFTransformRemote *,IUnknown *,IMFAttributes *)

- ea: `0x1800c0e40`
- end: `0x1800c1ab4`
- name: `?RuntimeClassInitialize@COOPMFTProxy@@QEAAJPEAUIMFTransformRemote@@PEAUIUnknown@@PEAUIMFAttributes@@@Z`
- size: `3188`
- prototype: `__int64 __fastcall(COOPMFTProxy *__hidden this, struct IMFTransformRemote *, struct IUnknown *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180167174`

## callees

- `0x180004870`
- `0x1800143a0`
- `0x180014488`
- `0x1800144ac`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800916b8`
- `0x180096c0c`
- `0x1800c0e40`
- `0x1801200d0`
- `0x180121575`
- `0x180138518`
- `0x180154318`
- `0x180167078`
- `0x180167328`
- `0x180167a00`
- `0x1801685f0`
- `0x180169890`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c180b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c180b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c182a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c182a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c1594`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c1594`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c101c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c101c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c15b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c15b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c122b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1237`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1a7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c122b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1237`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1a7a`

## pseudocode

```c
__int64 __fastcall COOPMFTProxy::RuntimeClassInitialize(
        COOPMFTProxy *this,
        __int64 (__fastcall ***a2)(struct IMFTransformRemote *, GUID *, __int64 **),
        struct IUnknown *a3,
        struct IMFAttributes *a4)
{
  void *v6; // r13
  __int64 (__fastcall *v7)(struct IMFTransformRemote *, GUID *, __int64 **); // rbx
  signed int v8; // ebx
  CallStackTracing *v9; // rcx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  CVPtrList *v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // r15
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // r12d
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rbx
  __int64 v29; // rax
  unsigned int v30; // ecx
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  CallStackTracing *v34; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v36; // rdx
  unsigned int i; // edi
  unsigned int v38; // ecx
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  CallStackTracing *v45; // rcx
  struct CallStackContext *v46; // rax
  __int64 *v47; // rdi
  void (__fastcall *v48)(__int64 *, LPVOID *); // rbx
  CallStackTracing *v49; // rcx
  struct CallStackContext *v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rbx
  struct _RTL_CRITICAL_SECTION *v53; // rdi
  void *v54; // rbx
  CallStackTracing *v55; // rcx
  struct CallStackContext *v56; // rax
  CallStackTracing *v57; // rcx
  struct CallStackContext *v58; // rax
  CallStackTracing *v59; // rcx
  struct CallStackContext *v60; // rax
  LPVOID pv; // [rsp+30h] [rbp-39h] BYREF
  CallStackScopeTrace v63; // [rsp+38h] [rbp-31h] BYREF
  LPVOID v64; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int64 v65; // [rsp+48h] [rbp-21h] BYREF
  __int64 *v66; // [rsp+50h] [rbp-19h] BYREF
  LPVOID v67; // [rsp+58h] [rbp-11h]
  struct IMFAttributes *v68; // [rsp+60h] [rbp-9h] BYREF
  GUID Buf1; // [rsp+68h] [rbp-1h] BYREF

  *(_QWORD *)&Buf1.Data1 = a3;
  v68 = a4;
  v67 = 0;
  v64 = 0;
  pv = 0;
  v66 = 0;
  v6 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v63, "COOPMFTProxy::RuntimeClassInitialize", 50);
  v7 = **a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  v8 = v7((struct IMFTransformRemote *)a2, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &v66);
  if ( v8 >= 0 )
  {
    v12 = (CVPtrList *)((char *)this + 72);
    *((_QWORD *)this + 61) = 0;
    if ( !*((_QWORD *)this + 10) )
    {
      *((_DWORD *)this + 22) = 1;
      *((_QWORD *)this + 10) = (char *)this + 96;
      v13 = 0;
      *((_QWORD *)this + 12) = 0;
      do
      {
        v14 = v13 + 2 * v13 + 1;
        ++v13;
        v15 = *((_QWORD *)this + 10) + 8 * v14;
        *(_QWORD *)(v15 + 8) = v12->m_NodePool.m_pFree;
        v12->m_NodePool.m_pFree = (CVPtrList::NODE *)v15;
      }
      while ( v13 != 16 );
    }
    v16 = (__int64 *)((char *)this + 520);
    *((_QWORD *)this + 117) = 0;
    if ( !*((_QWORD *)this + 66) )
    {
      *((_DWORD *)this + 134) = 1;
      *((_QWORD *)this + 66) = (char *)this + 544;
      v17 = 0;
      *((_QWORD *)this + 68) = 0;
      do
      {
        v18 = v17 + 2 * v17 + 1;
        ++v17;
        v19 = *((_QWORD *)this + 66) + 8 * v18;
        *(_QWORD *)(v19 + 8) = *v16;
        *v16 = v19;
      }
      while ( v17 != 16 );
    }
    Microsoft::WRL::ComPtr<IUnknown>::operator=((char *)this + 64, *(_QWORD *)&Buf1.Data1);
    Microsoft::WRL::ComPtr<IMFAttributes>::operator=((char *)this + 1096, v68);
    *((_QWORD *)this + 132) = GetCurrentProcess();
    v20 = COOPMFTProxy::SaveStubInfo(this, (struct IMFTransformRemote *)a2);
    v21 = 0;
    v8 = v20;
    if ( v20 >= 0 )
    {
      v65 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int64 *, char *))(*v66 + 32))(v66, &v65, (char *)&v65 + 4);
      if ( v8 >= 0 )
      {
        *(_QWORD *)&Buf1.Data1 = 0;
        v8 = ULongLongMult((unsigned int)v65, 4u, (unsigned __int64 *)&Buf1.Data1);
        if ( v8 >= 0 )
        {
          v8 = CTCoAllocPolicy::Alloc(v26, 1u, *(unsigned __int64 *)&Buf1.Data1, &pv);
          if ( v8 >= 0 )
          {
            *(_QWORD *)&Buf1.Data1 = 0;
            v8 = ULongLongMult(HIDWORD(v65), 4u, (unsigned __int64 *)&Buf1.Data1);
            if ( v8 >= 0 )
            {
              v8 = CTCoAllocPolicy::Alloc(v27, 1u, *(unsigned __int64 *)&Buf1.Data1, &v64);
              if ( v8 >= 0 )
              {
                v28 = v64;
                v6 = pv;
                v29 = *v66;
                v67 = v64;
                if ( (*(int (__fastcall **)(__int64 *, _QWORD, LPVOID, _QWORD, LPVOID))(v29 + 40))(
                       v66,
                       (unsigned int)v65,
                       pv,
                       HIDWORD(v65),
                       v64) < 0 )
                {
                  CoTaskMemFree(v6);
                  v6 = 0;
                  CoTaskMemFree(v28);
                  v67 = 0;
                }
                while ( v21 < (unsigned int)v65 )
                {
                  if ( v6 )
                    v30 = *((_DWORD *)v6 + v21);
                  else
                    v30 = v21;
                  LODWORD(v64) = v30;
                  pv = 0;
                  Buf1.Data1 = 0;
                  v8 = Microsoft::WRL::Details::MakeAndInitialize<CStream,CStream,unsigned long const &,enum StreamType>(
                         &pv,
                         &v64,
                         &Buf1);
                  if ( v8 < 0 )
                  {
                    v34 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::s_wpInstance = &stru_1801FC290;
                      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                      {
                        v34 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v34 = &stru_1801F8A30;
                        CallStackTracing::s_wpInstance = &stru_1801F8A30;
                      }
                    }
                    if ( v34->m_fEnabled )
                    {
                      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v34);
                      if ( ThreadRelativeContext->m_result != v8 )
                        CallStackContext::TraceFailure(
                          ThreadRelativeContext,
                          "COOPMFTProxy::RuntimeClassInitialize",
                          77,
                          v8);
                    }
                    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                    {
                      v36 = 19;
LABEL_69:
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v36,
                        WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids,
                        this,
                        v8);
                    }
                    goto LABEL_70;
                  }
                  if ( !CVPtrList::AddTail(v12, pv) )
                  {
                    v31 = CallStackTracing::s_wpInstance;
                    v8 = -2147024882;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::s_wpInstance = &stru_1801FC290;
                      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                      {
                        v31 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v31 = &stru_1801F8A30;
                        CallStackTracing::s_wpInstance = &stru_1801F8A30;
                      }
                    }
                    if ( v31->m_fEnabled )
                    {
                      v32 = CallStackTracing::GetThreadRelativeContext(v31);
                      if ( v32->m_result != -2147024882 )
                        CallStackContext::TraceFailure(v32, "COOPMFTProxy::RuntimeClassInitialize", 78, -2147024882);
                    }
                    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                    {
                      v33 = 20;
LABEL_59:
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v33,
                        WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids,
                        this,
                        -2147024882);
                    }
LABEL_70:
                    Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&pv);
                    goto LABEL_162;
                  }
                  pv = 0;
                  Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&pv);
                  ++v21;
                }
                for ( i = 0; i < HIDWORD(v65); ++i )
                {
                  if ( v67 )
                    v38 = *((_DWORD *)v67 + i);
                  else
                    v38 = i;
                  Buf1.Data1 = v38;
                  pv = 0;
                  LODWORD(v64) = 1;
                  v8 = Microsoft::WRL::Details::MakeAndInitialize<CStream,CStream,unsigned long const &,enum StreamType>(
                         &pv,
                         &Buf1,
                         &v64);
                  if ( v8 < 0 )
                  {
                    v41 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::s_wpInstance = &stru_1801FC290;
                      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                      {
                        v41 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v41 = &stru_1801F8A30;
                        CallStackTracing::s_wpInstance = &stru_1801F8A30;
                      }
                    }
                    if ( v41->m_fEnabled )
                    {
                      v42 = CallStackTracing::GetThreadRelativeContext(v41);
                      if ( v42->m_result != v8 )
                        CallStackContext::TraceFailure(v42, "COOPMFTProxy::RuntimeClassInitialize", 87, v8);
                    }
                    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                    {
                      v36 = 21;
                      goto LABEL_69;
                    }
                    goto LABEL_70;
                  }
                  if ( !CVPtrList::AddTail((CVPtrList *)((char *)this + 520), pv) )
                  {
                    v39 = CallStackTracing::s_wpInstance;
                    v8 = -2147024882;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::s_wpInstance = &stru_1801FC290;
                      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                      {
                        v39 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v39 = &stru_1801F8A30;
                        CallStackTracing::s_wpInstance = &stru_1801F8A30;
                      }
                    }
                    if ( v39->m_fEnabled )
                    {
                      v40 = CallStackTracing::GetThreadRelativeContext(v39);
                      if ( v40->m_result != -2147024882 )
                        CallStackContext::TraceFailure(v40, "COOPMFTProxy::RuntimeClassInitialize", 88, -2147024882);
                    }
                    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                    {
                      v33 = 22;
                      goto LABEL_59;
                    }
                    goto LABEL_70;
                  }
                  pv = 0;
                  Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&pv);
                }
                EventW = CreateEventW(0, 1, 0, 0);
                Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
                  (char *)this + 1072,
                  EventW);
                if ( *((_QWORD *)this + 135) )
                {
                  v47 = v66;
                  pv = 0;
                  v48 = *(void (__fastcall **)(__int64 *, LPVOID *))(*v66 + 64);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
                  v48(v47, &pv);
                  v68 = (struct IMFAttributes *)pv;
                  Microsoft::WRL::ComPtr<CMFOverridableAttributes>::InternalRelease((char *)this + 1088);
                  v8 = Microsoft::WRL::Details::MakeAndInitialize<CMFOverridableAttributes,CMFOverridableAttributes,IMFAttributes *>(
                         (char *)this + 1088,
                         &v68);
                  if ( v8 >= 0 )
                  {
                    v51 = *((_QWORD *)this + 137);
                    Buf1 = GUID_00000000_0000_0000_0000_000000000000;
                    (*(void (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v51 + 80LL))(
                      v51,
                      &MF_TRANSFORM_CATEGORY_Attribute,
                      &Buf1);
                    if ( !memcmp_0(&Buf1, &MFT_CATEGORY_VIDEO_DECODER, 0x10u)
                      || !memcmp_0(&Buf1, &MFT_CATEGORY_VIDEO_EFFECT, 0x10u)
                      || !memcmp_0(&Buf1, &MFT_CATEGORY_VIDEO_ENCODER, 0x10u)
                      || !memcmp_0(&Buf1, &MFT_CATEGORY_VIDEO_PROCESSOR, 0x10u) )
                    {
                      v52 = *((_QWORD *)this + 136);
                      v64 = 0;
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
                      v53 = (struct _RTL_CRITICAL_SECTION *)(v52 + 16);
                      EnterCriticalSection((LPCRITICAL_SECTION)(v52 + 16));
                      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v52 + 64);
                      v54 = *(void **)(v52 + 64);
                      v64 = v54;
                      if ( v53 )
                        LeaveCriticalSection(v53);
                      v8 = (*(__int64 (__fastcall **)(void *, __int64 *, __int64))(*(_QWORD *)v54 + 168LL))(
                             v54,
                             MF_SA_D3D11_AWARE,
                             1);
                      if ( v8 < 0 )
                      {
                        v55 = CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          CallStackTracing::s_wpInstance = &stru_1801FC290;
                          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                          {
                            v55 = CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v55 = &stru_1801F8A30;
                            CallStackTracing::s_wpInstance = &stru_1801F8A30;
                          }
                        }
                        if ( v55->m_fEnabled )
                        {
                          v56 = CallStackTracing::GetThreadRelativeContext(v55);
                          if ( v56->m_result != v8 )
                            CallStackContext::TraceFailure(v56, "COOPMFTProxy::RuntimeClassInitialize", 110, v8);
                        }
                        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                          WPP_SF_qD(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            26,
                            WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids,
                            this,
                            v8);
                      }
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
                    }
                  }
                  else
                  {
                    v49 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::s_wpInstance = &stru_1801FC290;
                      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                      {
                        v49 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v49 = &stru_1801F8A30;
                        CallStackTracing::s_wpInstance = &stru_1801F8A30;
                      }
                    }
                    if ( v49->m_fEnabled )
                    {
                      v50 = CallStackTracing::GetThreadRelativeContext(v49);
                      if ( v50->m_result != v8 )
                        CallStackContext::TraceFailure(v50, "COOPMFTProxy::RuntimeClassInitialize", 100, v8);
                    }
                    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        24,
                        WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids,
                        this,
                        v8);
                  }
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
                }
                else
                {
                  LastError = GetLastError();
                  v8 = LastError;
                  if ( LastError > 0 )
                    v8 = (unsigned __int16)LastError | 0x80070000;
                  v45 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v45 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v45 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v45->m_fEnabled )
                  {
                    v46 = CallStackTracing::GetThreadRelativeContext(v45);
                    if ( v8 < 0 && v46->m_result != v8 )
                      CallStackContext::TraceFailure(v46, "COOPMFTProxy::RuntimeClassInitialize", 93, v8);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v11 = 23;
                    goto LABEL_161;
                  }
                }
                goto LABEL_162;
              }
              v67 = v64;
            }
            v57 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v57 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v57 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v57->m_fEnabled )
            {
              v58 = CallStackTracing::GetThreadRelativeContext(v57);
              if ( v58->m_result != v8 )
                CallStackContext::TraceFailure(v58, "COOPMFTProxy::RuntimeClassInitialize", 65, v8);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids,
                this,
                v8);
            v6 = pv;
            goto LABEL_162;
          }
          v6 = pv;
        }
        v59 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v59 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v59 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v59->m_fEnabled )
        {
          v60 = CallStackTracing::GetThreadRelativeContext(v59);
          if ( v60->m_result != v8 )
            CallStackContext::TraceFailure(v60, "COOPMFTProxy::RuntimeClassInitialize", 64, v8);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v11 = 17;
          goto LABEL_161;
        }
      }
      else
      {
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
          if ( v25->m_result != v8 )
            CallStackContext::TraceFailure(v25, "COOPMFTProxy::RuntimeClassInitialize", 62, v8);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v11 = 16;
          goto LABEL_161;
        }
      }
    }
    else
    {
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v22 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v22->m_fEnabled )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( v23->m_result != v8 )
          CallStackContext::TraceFailure(v23, "COOPMFTProxy::RuntimeClassInitialize", 59, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v11 = 15;
        goto LABEL_161;
      }
    }
  }
  else
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v9->m_fEnabled )
    {
      v10 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( v10->m_result != v8 )
        CallStackContext::TraceFailure(v10, "COOPMFTProxy::RuntimeClassInitialize", 50, v8);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v11 = 12;
LABEL_161:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_8b72fb9e37393d18ba0dc45e576826c2_Traceguids, this, v8);
    }
  }
LABEL_162:
  CoTaskMemFree(v6);
  CoTaskMemFree(v67);
  CallStackScopeTrace::~CallStackScopeTrace(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c0e40  push    rbp
0x1800c0e42  push    rbx
0x1800c0e43  push    rsi
0x1800c0e44  push    rdi
0x1800c0e45  push    r12
0x1800c0e47  push    r13
0x1800c0e49  push    r14
0x1800c0e4b  push    r15
0x1800c0e4d  lea     rbp, [rsp-1Fh]
0x1800c0e52  sub     rsp, 88h
0x1800c0e59  mov     rax, cs:__security_cookie
0x1800c0e60  xor     rax, rsp
0x1800c0e63  mov     [rbp+57h+var_48], rax
0x1800c0e67  xor     r15d, r15d
0x1800c0e6a  mov     qword ptr [rbp+57h+Buf1], r8
0x1800c0e6e  mov     eax, r15d
0x1800c0e71  mov     [rbp+57h+var_60], r9
0x1800c0e75  mov     r12, rdx
0x1800c0e78  mov     [rbp+57h+var_68], rax
0x1800c0e7c  mov     r14, rcx
0x1800c0e7f  mov     [rbp+57h+var_80], rax
0x1800c0e83  lea     edi, [r15+32h]
0x1800c0e87  mov     [rbp+57h+pv], r15
0x1800c0e8b  mov     r8d, edi; int
0x1800c0e8e  mov     [rbp+57h+var_70], r15
0x1800c0e92  lea     rdx, aCoopmftproxyRu; "COOPMFTProxy::RuntimeClassInitialize"
0x1800c0e99  mov     r13d, r15d
0x1800c0e9c  lea     rcx, [rbp+57h+var_88]; this
0x1800c0ea0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c0ea5  mov     rax, [r12]
0x1800c0ea9  lea     rcx, [rbp+57h+var_70]
0x1800c0ead  mov     rbx, [rax]
0x1800c0eb0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c0eb5  lea     r8, [rbp+57h+var_70]
0x1800c0eb9  mov     rcx, r12
0x1800c0ebc  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x1800c0ec3  mov     rax, rbx
0x1800c0ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0ecb  mov     ebx, eax
0x1800c0ecd  test    eax, eax
0x1800c0ecf  jns     loc_1800C0F64
0x1800c0ed5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c0edc  test    rcx, rcx
0x1800c0edf  jnz     short loc_1800C0F22
0x1800c0ee1  mov     rcx, cs:stru_1801FC290.__vftable
0x1800c0ee8  lea     r8, stru_1801FC290
0x1800c0eef  mov     edx, 7F0h
0x1800c0ef4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c0efb  mov     rax, [rcx+8]
0x1800c0eff  mov     rcx, r8
0x1800c0f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0f07  test    eax, eax
0x1800c0f09  jnz     short loc_1800C0F1B
0x1800c0f0b  lea     rcx, stru_1801F8A30
0x1800c0f12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c0f19  jmp     short loc_1800C0F22
0x1800c0f1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800c0f22  cmp     [rcx+8], r15b
0x1800c0f26  jz      short loc_1800C0F4A
0x1800c0f28  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c0f2d  cmp     [rax+7CCh], ebx
0x1800c0f33  jz      short loc_1800C0F4A
0x1800c0f35  mov     r9d, ebx; int
0x1800c0f38  lea     rdx, aCoopmftproxyRu; "COOPMFTProxy::RuntimeClassInitialize"
0x1800c0f3f  mov     r8d, edi; int
0x1800c0f42  mov     rcx, rax; this
0x1800c0f45  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c0f4a  mov     esi, 1
0x1800c0f4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800c0f56  jb      loc_1800C1A6D
0x1800c0f5c  lea     edx, [rsi+0Bh]
0x1800c0f5f  jmp     loc_1800C1A4F
0x1800c0f64  lea     rdi, [r14+48h]
0x1800c0f68  mov     esi, 1
0x1800c0f6d  mov     [rdi+1A0h], r15
0x1800c0f74  cmp     [rdi+8], r15
0x1800c0f78  jnz     short loc_1800C0FB1
0x1800c0f7a  lea     rax, [rdi+18h]
0x1800c0f7e  mov     [rdi+10h], esi
0x1800c0f81  mov     [rdi+8], rax
0x1800c0f85  mov     r8, r15
0x1800c0f88  mov     [rax], r15
0x1800c0f8b  mov     rax, [rdi+8]
0x1800c0f8f  lea     rdx, ds:1[r8*2]
0x1800c0f97  add     rdx, r8
0x1800c0f9a  add     r8, rsi
0x1800c0f9d  lea     rdx, [rax+rdx*8]
0x1800c0fa1  mov     rax, [rdi]
0x1800c0fa4  mov     [rdx+8], rax
0x1800c0fa8  mov     [rdi], rdx
0x1800c0fab  cmp     r8, 10h
0x1800c0faf  jnz     short loc_1800C0F8B
0x1800c0fb1  lea     r15, [r14+208h]
0x1800c0fb8  xor     ecx, ecx
0x1800c0fba  mov     [r15+1A0h], rcx
0x1800c0fc1  cmp     [r15+8], rcx
0x1800c0fc5  jnz     short loc_1800C0FFF
0x1800c0fc7  lea     rax, [r15+18h]
0x1800c0fcb  mov     [r15+10h], esi
0x1800c0fcf  mov     [r15+8], rax
0x1800c0fd3  mov     r8d, ecx
0x1800c0fd6  mov     [rax], rcx
0x1800c0fd9  mov     rax, [r15+8]
0x1800c0fdd  lea     rdx, ds:1[r8*2]
0x1800c0fe5  add     rdx, r8
0x1800c0fe8  add     r8, rsi
0x1800c0feb  lea     rdx, [rax+rdx*8]
0x1800c0fef  mov     rax, [r15]
0x1800c0ff2  mov     [rdx+8], rax
0x1800c0ff6  mov     [r15], rdx
0x1800c0ff9  cmp     r8, 10h
0x1800c0ffd  jnz     short loc_1800C0FD9
0x1800c0fff  mov     rdx, qword ptr [rbp+57h+Buf1]
0x1800c1003  lea     rcx, [r14+40h]
0x1800c1007  call    ??4?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUnknown@@@Z; Microsoft::WRL::ComPtr<IUnknown>::operator=(IUnknown *)
0x1800c100c  mov     rdx, [rbp+57h+var_60]
0x1800c1010  lea     rcx, [r14+448h]
0x1800c1017  call    ??4?$ComPtr@UIMFAttributes@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFAttributes@@@Z; Microsoft::WRL::ComPtr<IMFAttributes>::operator=(IMFAttributes *)
0x1800c101c  call    cs:__imp_GetCurrentProcess
0x1800c1022  mov     rdx, r12; struct IMFTransformRemote *
0x1800c1025  mov     rcx, r14; this
0x1800c1028  mov     [r14+420h], rax
0x1800c102f  call    ?SaveStubInfo@COOPMFTProxy@@AEAAJPEAUIMFTransformRemote@@@Z; COOPMFTProxy::SaveStubInfo(IMFTransformRemote *)
0x1800c1034  xor     r12d, r12d
0x1800c1037  mov     ebx, eax
0x1800c1039  test    eax, eax
0x1800c103b  jns     loc_1800C10D0
0x1800c1041  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1048  test    rcx, rcx
0x1800c104b  jnz     short loc_1800C108E
0x1800c104d  mov     rax, cs:stru_1801FC290.__vftable
0x1800c1054  lea     r8, stru_1801FC290
0x1800c105b  mov     edx, 7F0h
0x1800c1060  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1067  mov     rcx, r8
0x1800c106a  mov     rax, [rax+8]
0x1800c106e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1073  test    eax, eax
0x1800c1075  jnz     short loc_1800C1087
0x1800c1077  lea     rcx, stru_1801F8A30
0x1800c107e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1085  jmp     short loc_1800C108E
0x1800c1087  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800c108e  cmp     [rcx+8], r12b
0x1800c1092  jz      short loc_1800C10B9
0x1800c1094  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1099  cmp     [rax+7CCh], ebx
0x1800c109f  jz      short loc_1800C10B9
0x1800c10a1  mov     r9d, ebx; int
0x1800c10a4  lea     rdx, aCoopmftproxyRu; "COOPMFTProxy::RuntimeClassInitialize"
0x1800c10ab  mov     r8d, 3Bh ; ';'; int
0x1800c10b1  mov     rcx, rax; this
0x1800c10b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c10b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800c10c0  jb      loc_1800C1A6D
0x1800c10c6  mov     edx, 0Fh
0x1800c10cb  jmp     loc_1800C1A4F
0x1800c10d0  mov     rcx, [rbp+57h+var_70]
0x1800c10d4  lea     r8, [rbp+57h+var_78+4]
0x1800c10d8  mov     dword ptr [rbp+57h+var_78+4], r12d
0x1800c10dc  lea     rdx, [rbp+57h+var_78]
0x1800c10e0  mov     dword ptr [rbp+57h+var_78], r12d
0x1800c10e4  mov     rax, [rcx]
0x1800c10e7  mov     rax, [rax+20h]
0x1800c10eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c10f0  mov     ebx, eax
0x1800c10f2  test    eax, eax
0x1800c10f4  jns     loc_1800C1189
0x1800c10fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1101  test    rcx, rcx
0x1800c1104  jnz     short loc_1800C1147
0x1800c1106  mov     rax, cs:stru_1801FC290.__vftable
0x1800c110d  lea     r8, stru_1801FC290
0x1800c1114  mov     edx, 7F0h
0x1800c1119  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1120  mov     rcx, r8
0x1800c1123  mov     rax, [rax+8]
0x1800c1127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c112c  test    eax, eax
0x1800c112e  jnz     short loc_1800C1140
0x1800c1130  lea     rcx, stru_1801F8A30
0x1800c1137  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c113e  jmp     short loc_1800C1147
0x1800c1140  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800c1147  cmp     [rcx+8], r12b
0x1800c114b  jz      short loc_1800C1172
0x1800c114d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1152  cmp     [rax+7CCh], ebx
0x1800c1158  jz      short loc_1800C1172
0x1800c115a  mov     r9d, ebx; int
0x1800c115d  lea     rdx, aCoopmftproxyRu; "COOPMFTProxy::RuntimeClassInitialize"
0x1800c1164  mov     r8d, 3Eh ; '>'; int
0x1800c116a  mov     rcx, rax; this
0x1800c116d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c1172  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800c1179  jb      loc_1800C1A6D
0x1800c117f  mov     edx, 10h
0x1800c1184  jmp     loc_1800C1A4F
0x1800c1189  mov     ecx, dword ptr [rbp+57h+var_78]; unsigned __int64
0x1800c118c  lea     r8, [rbp+57h+Buf1]; unsigned __int64 *
0x1800c1190  mov     edx, 4; unsigned __int64
0x1800c1195  mov     qword ptr [rbp+57h+Buf1], r12
0x1800c1199  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800c119e  mov     ebx, eax
0x1800c11a0  test    eax, eax
0x1800c11a2  js      loc_1800C19C5
0x1800c11a8  mov     r8, qword ptr [rbp+57h+Buf1]; unsigned __int64
0x1800c11ac  lea     r9, [rbp+57h+pv]; void **
0x1800c11b0  mov     edx, esi; unsigned int
0x1800c11b2  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800c11b7  mov     ebx, eax
0x1800c11b9  test    eax, eax
0x1800c11bb  js      loc_1800C19C1
0x1800c11c1  mov     ecx, dword ptr [rbp+57h+var_78+4]; unsigned __int64
0x1800c11c4  lea     r8, [rbp+57h+Buf1]; unsigned __int64 *
0x1800c11c8  mov     edx, 4; unsigned __int64
0x1800c11cd  mov     qword ptr [rbp+57h+Buf1], r12
0x1800c11d1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800c11d6  mov     ebx, eax
0x1800c11d8  test    eax, eax
0x1800c11da  js      loc_1800C1910
0x1800c11e0  mov     r8, qword ptr [rbp+57h+Buf1]; unsigned __int64
0x1800c11e4  lea     r9, [rbp+57h+var_80]; void **
0x1800c11e8  mov     edx, esi; unsigned int
0x1800c11ea  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800c11ef  mov     ebx, eax
0x1800c11f1  test    eax, eax
0x1800c11f3  js      loc_1800C1908
0x1800c11f9  mov     rcx, [rbp+57h+var_70]
0x1800c11fd  mov     rbx, [rbp+57h+var_80]
0x1800c1201  mov     r13, [rbp+57h+pv]
0x1800c1205  mov     r9d, dword ptr [rbp+57h+var_78+4]
0x1800c1209  mov     r8, r13
0x1800c120c  mov     rax, [rcx]
0x1800c120f  mov     edx, dword ptr [rbp+57h+var_78]
0x1800c1212  mov     [rbp+57h+var_68], rbx
0x1800c1216  mov     [rsp+0C0h+var_A0], rbx
0x1800c121b  mov     rax, [rax+28h]
0x1800c121f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1224  test    eax, eax
0x1800c1226  jns     short loc_1800C1241
0x1800c1228  mov     rcx, r13; pv
0x1800c122b  call    cs:__imp_CoTaskMemFree
0x1800c1231  mov     rcx, rbx; pv
0x1800c1234  mov     r13, r12
0x1800c1237  call    cs:__imp_CoTaskMemFree
0x1800c123d  mov     [rbp+57h+var_68], r12
0x1800c1241  cmp     r12d, dword ptr [rbp+57h+var_78]
0x1800c1245  jnb     loc_1800C13FD
0x1800c124b  test    r13, r13
0x1800c124e  jz      short loc_1800C125A
0x1800c1250  mov     eax, r12d
0x1800c1253  mov     ecx, [r13+rax*4+0]
0x1800c1258  jmp     short loc_1800C125D
0x1800c125a  mov     ecx, r12d
0x1800c125d  mov     dword ptr [rbp+57h+var_80], ecx
0x1800c1260  lea     r8, [rbp+57h+Buf1]
0x1800c1264  lea     rcx, [rbp+57h+pv]
0x1800c1268  mov     [rbp+57h+pv], 0
0x1800c1270  lea     rdx, [rbp+57h+var_80]
0x1800c1274  mov     dword ptr [rbp+57h+Buf1], 0
0x1800c127b  call    ??$MakeAndInitialize@VCStream@@V1@AEBKW4StreamType@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCStream@@@WRL@Microsoft@@@012@AEBK$$QEAW4StreamType@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CStream,CStream,ulong const &,StreamType>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CStream>>,ulong const &,StreamType &&)
0x1800c1280  mov     ebx, eax
0x1800c1282  test    eax, eax
0x1800c1284  js      loc_1800C134B
0x1800c128a  mov     rdx, [rbp+57h+pv]; void *
0x1800c128e  mov     rcx, rdi; this
0x1800c1291  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x1800c1296  test    rax, rax
0x1800c1299  jz      short loc_1800C12B1
0x1800c129b  lea     rcx, [rbp+57h+pv]
0x1800c129f  mov     [rbp+57h+pv], 0
0x1800c12a7  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x1800c12ac  add     r12d, esi
0x1800c12af  jmp     short loc_1800C1241
0x1800c12b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c12b8  mov     edi, 8007000Eh
0x1800c12bd  mov     ebx, edi
0x1800c12bf  test    rcx, rcx
0x1800c12c2  jnz     short loc_1800C1305
0x1800c12c4  mov     rax, cs:stru_1801FC290.__vftable
0x1800c12cb  lea     r8, stru_1801FC290
0x1800c12d2  mov     edx, 7F0h
0x1800c12d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c12de  mov     rcx, r8
0x1800c12e1  mov     rax, [rax+8]
0x1800c12e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c12ea  test    eax, eax
0x1800c12ec  jnz     short loc_1800C12FE
0x1800c12ee  lea     rcx, stru_1801F8A30
0x1800c12f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c12fc  jmp     short loc_1800C1305
0x1800c12fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800c1305  cmp     byte ptr [rcx+8], 0
0x1800c1309  jz      short loc_1800C1330
0x1800c130b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1310  cmp     [rax+7CCh], edi
0x1800c1316  jz      short loc_1800C1330
0x1800c1318  mov     r9d, edi; int
0x1800c131b  lea     rdx, aCoopmftproxyRu; "COOPMFTProxy::RuntimeClassInitialize"
  ... truncated ...
```
