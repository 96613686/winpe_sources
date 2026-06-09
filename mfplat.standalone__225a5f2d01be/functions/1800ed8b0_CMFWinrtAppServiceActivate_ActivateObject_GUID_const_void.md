# CMFWinrtAppServiceActivate::ActivateObject(_GUID const &,void * *)

- ea: `0x1800ed8b0`
- end: `0x1800ee02c`
- name: `?ActivateObject@CMFWinrtAppServiceActivate@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1916`
- prototype: `__int64 __fastcall(struct IMFAttributes *this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004870`
- `0x180009af0`
- `0x180011454`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180057e90`
- `0x1800888e0`
- `0x1800b2bf8`
- `0x1800c2760`
- `0x1800ed8b0`
- `0x1801250c8`
- `0x18016697c`
- `0x180166c58`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed918`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ed918`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ee00c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ee00c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ed8e4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800edf9d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ed8e4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800edf9d`

## string_xrefs

- `0x1800ed924`: `CMFWinrtAppServiceActivate::ActivateObject`
- `0x1800ed9f6`: `CMFWinrtAppServiceActivate::ActivateObject`
- `0x1800edac0`: `CMFWinrtAppServiceActivate::ActivateObject`
- `0x1800edb92`: `CMFWinrtAppServiceActivate::ActivateObject`
- `0x1800edc7a`: `CMFWinrtAppServiceActivate::ActivateObject`
- `0x1800edd31`: `CMFWinrtAppServiceActivate::ActivateObject`
- `0x1800ede78`: `CMFWinrtAppServiceActivate::ActivateObject`
- `0x1800edf09`: `CMFWinrtAppServiceActivate::ActivateObject`
- `0x1800edf52`: `CMFWinrtAppServiceActivate::ActivateObject`

## pseudocode

```c
__int64 __fastcall CMFWinrtAppServiceActivate::ActivateObject(
        struct IMFAttributes *this,
        const struct _GUID *a2,
        void **a3)
{
  HRESULT v6; // edi
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  struct IUnknown *QuadPart; // rbx
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  int v13; // eax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  struct CallStackContext *v26; // rax
  LONGLONG v27; // rbx
  unsigned __int64 v28; // rdx
  __int64 (__fastcall ***v30)(_QWORD, GUID *, struct IMFAttributes *); // [rsp+30h] [rbp-20h] BYREF
  struct IMFTransformRemote *v31; // [rsp+38h] [rbp-18h] BYREF
  LONGLONG v32; // [rsp+40h] [rbp-10h]
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+40h] BYREF
  struct IUnknown *v34; // [rsp+A8h] [rbp+58h] BYREF

  v32 = 0;
  PerformanceCount.QuadPart = 0;
  if ( QueryPerformanceCounter(&PerformanceCount) )
    v32 = MFllMulDiv(PerformanceCount.QuadPart - qword_1801FCD08, 10000000, c, 0);
  EnterCriticalSection((LPCRITICAL_SECTION)&this[11]);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&PerformanceCount,
    "CMFWinrtAppServiceActivate::ActivateObject",
    77);
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_a83c74d4f8b13487b138c9e59fc11a60_Traceguids, this);
  if ( this[16].__vftable )
    goto LABEL_63;
  PerformanceCount.QuadPart = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&PerformanceCount);
  v6 = MFCreateAttributes((IMFAttributes **)&PerformanceCount, 5u);
  if ( v6 < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( ThreadRelativeContext->m_result != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFWinrtAppServiceActivate::ActivateObject", 82, v6);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_17;
    v9 = 14;
    goto LABEL_16;
  }
  QuadPart = (struct IUnknown *)PerformanceCount.QuadPart;
  v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::CopyAllItems)(
         this,
         (LARGE_INTEGER)PerformanceCount.QuadPart);
  if ( v6 < 0 )
  {
    v11 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v11 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v11->m_fEnabled )
    {
      v12 = CallStackTracing::GetThreadRelativeContext(v11);
      if ( v12->m_result != v6 )
        CallStackContext::TraceFailure(v12, "CMFWinrtAppServiceActivate::ActivateObject", 83, v6);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_17;
    v9 = 15;
    goto LABEL_16;
  }
  v13 = (int)this[17].__vftable;
  if ( !v13 )
  {
    v31 = 0;
    v30 = 0;
    v34 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v6 = MFCreateTransformAppServiceConnector(this, &v34, &v31);
    if ( v6 < 0 )
    {
      v14 = CallStackTracing::s_wpInstance;
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
        if ( v15->m_result != v6 )
          CallStackContext::TraceFailure(v15, "CMFWinrtAppServiceActivate::ActivateObject", 91, v6);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_40;
      v16 = 16;
LABEL_39:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_a83c74d4f8b13487b138c9e59fc11a60_Traceguids, this, v6);
LABEL_40:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      goto LABEL_17;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    v6 = MFCreateOOPMFTProxy(v31, v34, QuadPart, &v30);
    if ( v6 < 0 )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v17 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v17->m_fEnabled )
      {
        v18 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( v18->m_result != v6 )
          CallStackContext::TraceFailure(v18, "CMFWinrtAppServiceActivate::ActivateObject", 95, v6);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_40;
      v16 = 17;
      goto LABEL_39;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&this[16]);
    v6 = (**v30)(v30, &GUID_00000000_0000_0000_c000_000000000046, this + 16);
    if ( v6 < 0 )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v19 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v19->m_fEnabled )
      {
        v20 = CallStackTracing::GetThreadRelativeContext(v19);
        if ( v20->m_result != v6 )
          CallStackContext::TraceFailure(v20, "CMFWinrtAppServiceActivate::ActivateObject", 96, v6);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_40;
      v16 = 18;
      goto LABEL_39;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    goto LABEL_62;
  }
  if ( v13 != 1 )
  {
    v24 = CallStackTracing::s_wpInstance;
    v6 = -1072875845;
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
      if ( v25->m_result != -1072875845 )
        CallStackContext::TraceFailure(v25, "CMFWinrtAppServiceActivate::ActivateObject", 104, -1072875845);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_17;
    v9 = 20;
LABEL_16:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_a83c74d4f8b13487b138c9e59fc11a60_Traceguids, this, v6);
LABEL_17:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&PerformanceCount);
    goto LABEL_93;
  }
  v34 = QuadPart;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&this[16]);
  v6 = Microsoft::WRL::Details::MakeAndInitialize<CMFMediaSourceAppServiceByteStreamHandler,IUnknown,IMFAttributes *>(
         &this[16],
         &v34);
  if ( v6 < 0 )
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
      if ( v23->m_result != v6 )
        CallStackContext::TraceFailure(v23, "CMFWinrtAppServiceActivate::ActivateObject", 100, v6);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_17;
    v9 = 19;
    goto LABEL_16;
  }
LABEL_62:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&PerformanceCount);
LABEL_63:
  v6 = (*(__int64 (__fastcall **)(IMFAttributes_vtbl *, const struct _GUID *, void **))this[16].QueryInterface)(
         this[16].__vftable,
         a2,
         a3);
  if ( v6 < 0 )
  {
    v21 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v21 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v21->m_fEnabled )
    {
      v26 = CallStackTracing::GetThreadRelativeContext(v21);
      if ( v26->m_result != v6 )
        CallStackContext::TraceFailure(v26, "CMFWinrtAppServiceActivate::ActivateObject", 108, v6);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_a83c74d4f8b13487b138c9e59fc11a60_Traceguids, this, v6);
  }
LABEL_93:
  v27 = 0;
  PerformanceCount.QuadPart = 0;
  if ( QueryPerformanceCounter(&PerformanceCount) )
    v27 = MFllMulDiv(PerformanceCount.QuadPart - qword_1801FCD08, 10000000, c, 0);
  if ( !LODWORD(this[17].__vftable) )
  {
    v28 = (__int64)((unsigned __int128)((v27 - v32) * (__int128)0x346DC5D63886594BLL) >> 64) >> 11;
    CMFWinrtAppServiceActivate::LogTransformAppSvcTelemetry((CMFWinrtAppServiceActivate *)this, v6, v28 + (v28 >> 63));
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&PerformanceCount);
  if ( this != (struct IMFAttributes *)-88LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)&this[11]);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ed8b0  mov     [rsp-38h+arg_8], rbx
0x1800ed8b5  push    rbp
0x1800ed8b6  push    rsi
0x1800ed8b7  push    rdi
0x1800ed8b8  push    r12
0x1800ed8ba  push    r13
0x1800ed8bc  push    r14
0x1800ed8be  push    r15
0x1800ed8c0  mov     rbp, rsp
0x1800ed8c3  sub     rsp, 50h
0x1800ed8c7  mov     rsi, rcx
0x1800ed8ca  mov     [rbp+var_10], 0
0x1800ed8d2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800ed8d6  mov     qword ptr [rbp+PerformanceCount], 0
0x1800ed8de  mov     r15, r8
0x1800ed8e1  mov     r12, rdx
0x1800ed8e4  call    cs:__imp_QueryPerformanceCounter
0x1800ed8ea  test    eax, eax
0x1800ed8ec  jz      short loc_1800ED911
0x1800ed8ee  mov     rcx, qword ptr [rbp+PerformanceCount]
0x1800ed8f2  xor     r9d, r9d; d
0x1800ed8f5  sub     rcx, cs:qword_1801FCD08; a
0x1800ed8fc  mov     edx, 989680h; b
0x1800ed901  mov     r8, cs:c; c
0x1800ed908  call    MFllMulDiv
0x1800ed90d  mov     [rbp+var_10], rax
0x1800ed911  lea     r13, [rsi+58h]
0x1800ed915  mov     rcx, r13; lpCriticalSection
0x1800ed918  call    cs:__imp_EnterCriticalSection
0x1800ed91e  mov     r8d, 4Dh ; 'M'; int
0x1800ed924  lea     rdx, aCmfwinrtappser_1; "CMFWinrtAppServiceActivate::ActivateObj"...
0x1800ed92b  lea     rcx, [rbp+PerformanceCount]; this
0x1800ed92f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ed934  cmp     cs:byte_1801FD289, 10h
0x1800ed93b  jb      short loc_1800ED95C
0x1800ed93d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed944  lea     r8, WPP_a83c74d4f8b13487b138c9e59fc11a60_Traceguids
0x1800ed94b  mov     edx, 0Dh
0x1800ed950  mov     r9, rsi
0x1800ed953  mov     rcx, [rcx+38h]
0x1800ed957  call    WPP_SF_q
0x1800ed95c  lea     r14, [rsi+80h]
0x1800ed963  cmp     qword ptr [r14], 0
0x1800ed967  jnz     loc_1800EDD81
0x1800ed96d  lea     rcx, [rbp+PerformanceCount]
0x1800ed971  mov     qword ptr [rbp+PerformanceCount], 0
0x1800ed979  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ed97e  mov     edx, 5; cInitialSize
0x1800ed983  lea     rcx, [rbp+PerformanceCount]; ppMFAttributes
0x1800ed987  call    MFCreateAttributes
0x1800ed98c  mov     edi, eax
0x1800ed98e  test    eax, eax
0x1800ed990  jns     loc_1800EDA45
0x1800ed996  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed99d  test    rcx, rcx
0x1800ed9a0  jnz     short loc_1800ED9E0
0x1800ed9a2  mov     rdx, cs:stru_1801FC290.__vftable
0x1800ed9a9  lea     rcx, stru_1801FC290
0x1800ed9b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed9b7  mov     rax, [rdx+8]
0x1800ed9bb  mov     edx, 7F0h
0x1800ed9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed9c5  test    eax, eax
0x1800ed9c7  jnz     short loc_1800ED9D9
0x1800ed9c9  lea     rcx, stru_1801F8A30
0x1800ed9d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ed9d7  jmp     short loc_1800ED9E0
0x1800ed9d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ed9e0  cmp     byte ptr [rcx+8], 0
0x1800ed9e4  jz      short loc_1800EDA0B
0x1800ed9e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ed9eb  cmp     [rax+7CCh], edi
0x1800ed9f1  jz      short loc_1800EDA0B
0x1800ed9f3  mov     r9d, edi; int
0x1800ed9f6  lea     rdx, aCmfwinrtappser_1; "CMFWinrtAppServiceActivate::ActivateObj"...
0x1800ed9fd  mov     r8d, 52h ; 'R'; int
0x1800eda03  mov     rcx, rax; this
0x1800eda06  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800eda0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800eda12  jb      short loc_1800EDA37
0x1800eda14  mov     edx, 0Eh
0x1800eda19  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eda20  lea     r8, WPP_a83c74d4f8b13487b138c9e59fc11a60_Traceguids
0x1800eda27  mov     r9, rsi
0x1800eda2a  mov     [rsp+50h+var_30], edi
0x1800eda2e  mov     rcx, [rcx+10h]
0x1800eda32  call    WPP_SF_qD
0x1800eda37  lea     rcx, [rbp+PerformanceCount]
0x1800eda3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800eda40  jmp     loc_1800EDF93
0x1800eda45  mov     rbx, qword ptr [rbp+PerformanceCount]
0x1800eda49  mov     rcx, rsi
0x1800eda4c  mov     rdx, rbx
0x1800eda4f  call    ?CopyAllItems@?$CMFAttributesImpl@UIMFActivate@@VCWin32AttributeLock@@@@UEAAJPEAUIMFAttributes@@@Z; CMFAttributesImpl<IMFActivate,CWin32AttributeLock>::CopyAllItems(IMFAttributes *)
0x1800eda54  xor     ecx, ecx
0x1800eda56  mov     edi, eax
0x1800eda58  test    eax, eax
0x1800eda5a  jns     loc_1800EDAEC
0x1800eda60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eda67  test    rcx, rcx
0x1800eda6a  jnz     short loc_1800EDAAA
0x1800eda6c  mov     rax, cs:stru_1801FC290.__vftable
0x1800eda73  lea     rcx, stru_1801FC290
0x1800eda7a  mov     edx, 7F0h
0x1800eda7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eda86  mov     rax, [rax+8]
0x1800eda8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eda8f  test    eax, eax
0x1800eda91  jnz     short loc_1800EDAA3
0x1800eda93  lea     rcx, stru_1801F8A30
0x1800eda9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edaa1  jmp     short loc_1800EDAAA
0x1800edaa3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800edaaa  cmp     byte ptr [rcx+8], 0
0x1800edaae  jz      short loc_1800EDAD5
0x1800edab0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800edab5  cmp     [rax+7CCh], edi
0x1800edabb  jz      short loc_1800EDAD5
0x1800edabd  mov     r9d, edi; int
0x1800edac0  lea     rdx, aCmfwinrtappser_1; "CMFWinrtAppServiceActivate::ActivateObj"...
0x1800edac7  mov     r8d, 53h ; 'S'; int
0x1800edacd  mov     rcx, rax; this
0x1800edad0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800edad5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800edadc  jb      loc_1800EDA37
0x1800edae2  mov     edx, 0Fh
0x1800edae7  jmp     loc_1800EDA19
0x1800edaec  mov     eax, [rsi+88h]
0x1800edaf2  test    eax, eax
0x1800edaf4  jnz     loc_1800EDDED
0x1800edafa  mov     [rbp+var_18], rcx
0x1800edafe  mov     [rbp+var_20], rcx
0x1800edb02  mov     [rbp+arg_18], rcx
0x1800edb06  lea     rcx, [rbp+var_18]
0x1800edb0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edb0f  lea     rcx, [rbp+arg_18]
0x1800edb13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800edb18  lea     r8, [rbp+var_18]; struct IMFTransformRemote **
0x1800edb1c  mov     rcx, rsi; struct IMFAttributes *
0x1800edb1f  lea     rdx, [rbp+arg_18]; struct IUnknown **
0x1800edb23  call    ?MFCreateTransformAppServiceConnector@@YAJPEAUIMFAttributes@@PEAPEAUIUnknown@@PEAPEAUIMFTransformRemote@@@Z; MFCreateTransformAppServiceConnector(IMFAttributes *,IUnknown * *,IMFTransformRemote * *)
0x1800edb28  mov     edi, eax
0x1800edb2a  test    eax, eax
0x1800edb2c  jns     loc_1800EDBF3
0x1800edb32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edb39  test    rcx, rcx
0x1800edb3c  jnz     short loc_1800EDB7C
0x1800edb3e  mov     rax, cs:stru_1801FC290.__vftable
0x1800edb45  lea     rcx, stru_1801FC290
0x1800edb4c  mov     edx, 7F0h
0x1800edb51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edb58  mov     rax, [rax+8]
0x1800edb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edb61  test    eax, eax
0x1800edb63  jnz     short loc_1800EDB75
0x1800edb65  lea     rcx, stru_1801F8A30
0x1800edb6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edb73  jmp     short loc_1800EDB7C
0x1800edb75  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800edb7c  cmp     byte ptr [rcx+8], 0
0x1800edb80  jz      short loc_1800EDBA7
0x1800edb82  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800edb87  cmp     [rax+7CCh], edi
0x1800edb8d  jz      short loc_1800EDBA7
0x1800edb8f  mov     r9d, edi; int
0x1800edb92  lea     rdx, aCmfwinrtappser_1; "CMFWinrtAppServiceActivate::ActivateObj"...
0x1800edb99  mov     r8d, 5Bh ; '['; int
0x1800edb9f  mov     rcx, rax; this
0x1800edba2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800edba7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800edbae  jb      short loc_1800EDBD3
0x1800edbb0  mov     edx, 10h
0x1800edbb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800edbbc  lea     r8, WPP_a83c74d4f8b13487b138c9e59fc11a60_Traceguids
0x1800edbc3  mov     r9, rsi
0x1800edbc6  mov     [rsp+50h+var_30], edi
0x1800edbca  mov     rcx, [rcx+10h]
0x1800edbce  call    WPP_SF_qD
0x1800edbd3  lea     rcx, [rbp+arg_18]
0x1800edbd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800edbdc  lea     rcx, [rbp+var_20]
0x1800edbe0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edbe5  lea     rcx, [rbp+var_18]
0x1800edbe9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edbee  jmp     loc_1800EDA37
0x1800edbf3  lea     rcx, [rbp+var_20]
0x1800edbf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edbfc  mov     rdx, [rbp+arg_18]
0x1800edc00  lea     r9, [rbp+var_20]
0x1800edc04  mov     rcx, [rbp+var_18]
0x1800edc08  mov     r8, rbx
0x1800edc0b  call    MFCreateOOPMFTProxy
0x1800edc10  mov     edi, eax
0x1800edc12  test    eax, eax
0x1800edc14  jns     loc_1800EDCA6
0x1800edc1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edc21  test    rcx, rcx
0x1800edc24  jnz     short loc_1800EDC64
0x1800edc26  mov     rax, cs:stru_1801FC290.__vftable
0x1800edc2d  lea     rcx, stru_1801FC290
0x1800edc34  mov     edx, 7F0h
0x1800edc39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edc40  mov     rax, [rax+8]
0x1800edc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc49  test    eax, eax
0x1800edc4b  jnz     short loc_1800EDC5D
0x1800edc4d  lea     rcx, stru_1801F8A30
0x1800edc54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edc5b  jmp     short loc_1800EDC64
0x1800edc5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800edc64  cmp     byte ptr [rcx+8], 0
0x1800edc68  jz      short loc_1800EDC8F
0x1800edc6a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800edc6f  cmp     [rax+7CCh], edi
0x1800edc75  jz      short loc_1800EDC8F
0x1800edc77  mov     r9d, edi; int
0x1800edc7a  lea     rdx, aCmfwinrtappser_1; "CMFWinrtAppServiceActivate::ActivateObj"...
0x1800edc81  mov     r8d, 5Fh ; '_'; int
0x1800edc87  mov     rcx, rax; this
0x1800edc8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800edc8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800edc96  jb      loc_1800EDBD3
0x1800edc9c  mov     edx, 11h
0x1800edca1  jmp     loc_1800EDBB5
0x1800edca6  mov     rcx, r14
0x1800edca9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800edcae  mov     rcx, [rbp+var_20]
0x1800edcb2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800edcb9  mov     r8, r14
0x1800edcbc  mov     rax, [rcx]
0x1800edcbf  mov     rax, [rax]
0x1800edcc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edcc7  mov     edi, eax
0x1800edcc9  test    eax, eax
0x1800edccb  jns     loc_1800EDD5D
0x1800edcd1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edcd8  test    rcx, rcx
0x1800edcdb  jnz     short loc_1800EDD1B
0x1800edcdd  mov     rax, cs:stru_1801FC290.__vftable
0x1800edce4  lea     rcx, stru_1801FC290
0x1800edceb  mov     edx, 7F0h
0x1800edcf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edcf7  mov     rax, [rax+8]
0x1800edcfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edd00  test    eax, eax
0x1800edd02  jnz     short loc_1800EDD14
0x1800edd04  lea     rcx, stru_1801F8A30
0x1800edd0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edd12  jmp     short loc_1800EDD1B
0x1800edd14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800edd1b  cmp     byte ptr [rcx+8], 0
0x1800edd1f  jz      short loc_1800EDD46
0x1800edd21  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800edd26  cmp     [rax+7CCh], edi
0x1800edd2c  jz      short loc_1800EDD46
0x1800edd2e  mov     r9d, edi; int
0x1800edd31  lea     rdx, aCmfwinrtappser_1; "CMFWinrtAppServiceActivate::ActivateObj"...
0x1800edd38  mov     r8d, 60h ; '`'; int
0x1800edd3e  mov     rcx, rax; this
0x1800edd41  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800edd46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800edd4d  jb      loc_1800EDBD3
0x1800edd53  mov     edx, 12h
0x1800edd58  jmp     loc_1800EDBB5
0x1800edd5d  lea     rcx, [rbp+arg_18]
0x1800edd61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800edd66  lea     rcx, [rbp+var_20]
0x1800edd6a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edd6f  lea     rcx, [rbp+var_18]
0x1800edd73  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edd78  lea     rcx, [rbp+PerformanceCount]
0x1800edd7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800edd81  mov     rcx, [r14]
0x1800edd84  mov     r8, r15
0x1800edd87  mov     rdx, r12
0x1800edd8a  mov     rax, [rcx]
0x1800edd8d  mov     rax, [rax]
0x1800edd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edd95  mov     edi, eax
0x1800edd97  test    eax, eax
0x1800edd99  jns     loc_1800EDF93
0x1800edd9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edda6  test    rcx, rcx
0x1800edda9  jnz     loc_1800EDF3C
0x1800eddaf  mov     rax, cs:stru_1801FC290.__vftable
0x1800eddb6  lea     rcx, stru_1801FC290
0x1800eddbd  mov     edx, 7F0h
0x1800eddc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800eddc9  mov     rax, [rax+8]
0x1800eddcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eddd2  test    eax, eax
0x1800eddd4  jnz     loc_1800EDF35
0x1800eddda  lea     rcx, stru_1801F8A30
0x1800edde1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800edde8  jmp     loc_1800EDF3C
0x1800edded  cmp     eax, 1
0x1800eddf0  jnz     loc_1800EDEA4
0x1800eddf6  mov     rcx, r14
0x1800eddf9  mov     [rbp+arg_18], rbx
0x1800eddfd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
  ... truncated ...
```
