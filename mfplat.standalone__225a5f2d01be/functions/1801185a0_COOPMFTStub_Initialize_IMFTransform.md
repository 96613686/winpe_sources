# COOPMFTStub::Initialize(IMFTransform *)

- ea: `0x1801185a0`
- end: `0x180118d8f`
- name: `?Initialize@COOPMFTStub@@AEAAJPEAUIMFTransform@@@Z`
- size: `2031`
- prototype: `__int64 __fastcall(COOPMFTStub *__hidden this, struct IMFTransform *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c74d8`

## callees

- `0x180004870`
- `0x1800143a0`
- `0x1800144ac`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180040cb0`
- `0x1800916b8`
- `0x1801185a0`
- `0x180138518`
- `0x180167328`
- `0x180167a00`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180118bec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180118bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180118c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180118c0e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801186e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801187ff`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801186e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801187ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118a1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118a27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118d6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118a1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118a27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180118d6e`

## pseudocode

```c
__int64 __fastcall COOPMFTStub::Initialize(COOPMFTStub *this, struct IMFTransform *a2)
{
  struct IMFTransformVtbl *lpVtbl; // rax
  void *v5; // r12
  void *v6; // r15
  HRESULT (__stdcall *GetAttributes)(IMFTransform *, IMFAttributes **); // rbx
  CallStackTracing *v8; // rcx
  signed int v9; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  HRESULT (__stdcall *QueryInterface)(IMFTransform *, const IID *const, void **); // rbx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  struct IMFTransformVtbl *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  void *v19; // rcx
  void *v20; // rcx
  int v21; // eax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  unsigned int i; // esi
  unsigned int v25; // ecx
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  __int64 v38; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  void *v40; // [rsp+40h] [rbp-20h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v42; // [rsp+58h] [rbp-8h]
  unsigned __int64 v43; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int64 v44; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "COOPMFTStub::Initialize", 56);
  v40 = 0;
  v42 = 0;
  lpVtbl = a2->lpVtbl;
  v5 = 0;
  v6 = 0;
  pv = 0;
  v38 = 0;
  v43 = 0;
  GetAttributes = lpVtbl->GetAttributes;
  *(_OWORD *)pvar = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  if ( ((int (__fastcall *)(struct IMFTransform *, __int64 *))GetAttributes)(a2, &v38) >= 0
    && (unsigned int)MFGetAttributeUINT32(v38, &MF_TRANSFORM_ASYNC, 0) )
  {
    v8 = CallStackTracing::s_wpInstance;
    v9 = -1072861830;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v8->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
      if ( ThreadRelativeContext->m_result != -1072861830 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "COOPMFTStub::Initialize", 72, -1072861830);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_13;
    v11 = 15;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_1798d81f4e9332f4913729d6a2b23e3a_Traceguids, this, v9);
LABEL_13:
    PropVariantClear(pvar);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    goto LABEL_107;
  }
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  if ( ((int (__fastcall *)(struct IMFTransform *, GUID *, unsigned __int64 *))QueryInterface)(
         a2,
         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
         &v43) >= 0
    && (*(int (__fastcall **)(unsigned __int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v43 + 40LL))(
         v43,
         &MFPKEY_EXATTRIBUTE_SUPPORTED,
         pvar) >= 0
    && LOWORD(pvar[0]) == 11
    && LOWORD(pvar[1]) == 0xFFFF )
  {
    v13 = CallStackTracing::s_wpInstance;
    v9 = -1072861828;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v13 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v13->m_fEnabled )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( v14->m_result != -1072861828 )
        CallStackContext::TraceFailure(v14, "COOPMFTStub::Initialize", 80, -1072861828);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_13;
    v11 = 16;
    goto LABEL_12;
  }
  PropVariantClear(pvar);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  v15 = a2->lpVtbl;
  LODWORD(v44) = 0;
  LODWORD(v45) = 0;
  v9 = ((__int64 (__fastcall *)(struct IMFTransform *, unsigned __int64 *, unsigned __int64 *))v15->GetStreamCount)(
         a2,
         &v45,
         &v44);
  if ( v9 < 0 )
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
      if ( v17->m_result != v9 )
        CallStackContext::TraceFailure(v17, "COOPMFTStub::Initialize", 86, v9);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v18 = 17;
LABEL_106:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_1798d81f4e9332f4913729d6a2b23e3a_Traceguids, this, v9);
      goto LABEL_107;
    }
    goto LABEL_107;
  }
  v43 = 0;
  v9 = ULongLongMult((unsigned int)v45, 4u, &v43);
  if ( v9 < 0 )
  {
LABEL_96:
    v35 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v35 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v35 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v35->m_fEnabled )
    {
      v36 = CallStackTracing::GetThreadRelativeContext(v35);
      if ( v36->m_result != v9 )
        CallStackContext::TraceFailure(v36, "COOPMFTStub::Initialize", 88, v9);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v18 = 18;
      goto LABEL_106;
    }
    goto LABEL_107;
  }
  v9 = CTCoAllocPolicy::Alloc(v19, 1u, v43, &pv);
  if ( v9 < 0 )
  {
    v6 = pv;
    goto LABEL_96;
  }
  v43 = 0;
  v9 = ULongLongMult((unsigned int)v44, 4u, &v43);
  if ( v9 >= 0 )
  {
    v21 = CTCoAllocPolicy::Alloc(v20, 1u, v43, &v40);
    v5 = v40;
    v9 = v21;
  }
  if ( v9 >= 0 )
  {
    v6 = pv;
    if ( ((int (__fastcall *)(struct IMFTransform *, _QWORD, LPVOID, _QWORD, void *))a2->lpVtbl->GetStreamIDs)(
           a2,
           (unsigned int)v45,
           pv,
           (unsigned int)v44,
           v5) < 0 )
    {
      CoTaskMemFree(v6);
      v6 = 0;
      CoTaskMemFree(v5);
      v5 = 0;
    }
    for ( i = 0; i < (unsigned int)v44; ++i )
    {
      if ( v5 )
        v25 = *((_DWORD *)v5 + i);
      else
        v25 = i;
      LODWORD(v38) = v25;
      pv = 0;
      LODWORD(v43) = 1;
      v9 = Microsoft::WRL::Details::MakeAndInitialize<CStream,CStream,unsigned long const &,enum StreamType>(
             &pv,
             &v38,
             &v43);
      if ( v9 < 0 )
      {
        v29 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v29 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v29->m_fEnabled )
        {
          v30 = CallStackTracing::GetThreadRelativeContext(v29);
          if ( v30->m_result != v9 )
            CallStackContext::TraceFailure(v30, "COOPMFTStub::Initialize", 101, v9);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v28 = 20;
LABEL_80:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, WPP_1798d81f4e9332f4913729d6a2b23e3a_Traceguids, this, v9);
        }
LABEL_81:
        Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&pv);
        goto LABEL_107;
      }
      if ( !CVPtrList::AddTail((CVPtrList *)((char *)this + 128), pv) )
      {
        v26 = CallStackTracing::s_wpInstance;
        v9 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v26 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v26->m_fEnabled )
        {
          v27 = CallStackTracing::GetThreadRelativeContext(v26);
          if ( v27->m_result != -2147024882 )
            CallStackContext::TraceFailure(v27, "COOPMFTStub::Initialize", 102, -2147024882);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v28 = 21;
          goto LABEL_80;
        }
        goto LABEL_81;
      }
      pv = 0;
      Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(&pv);
    }
    EventW = CreateEventW(0, 1, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
      (char *)this + 576,
      EventW);
    if ( !*((_QWORD *)this + 73) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v33 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v33 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v33->m_fEnabled )
      {
        v34 = CallStackTracing::GetThreadRelativeContext(v33);
        if ( v9 < 0 && v34->m_result != v9 )
          CallStackContext::TraceFailure(v34, "COOPMFTStub::Initialize", 107, v9);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v18 = 22;
        goto LABEL_106;
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
      if ( v23->m_result != v9 )
        CallStackContext::TraceFailure(v23, "COOPMFTStub::Initialize", 89, v9);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1798d81f4e9332f4913729d6a2b23e3a_Traceguids, this, v9);
    v6 = pv;
  }
LABEL_107:
  CoTaskMemFree(v6);
  CoTaskMemFree(v5);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1801185a0  push    rbp
0x1801185a2  push    rbx
0x1801185a3  push    rsi
0x1801185a4  push    r12
0x1801185a6  push    r13
0x1801185a8  push    r14
0x1801185aa  push    r15
0x1801185ac  mov     rbp, rsp
0x1801185af  sub     rsp, 60h
0x1801185b3  mov     rsi, rdx
0x1801185b6  mov     r14, rcx
0x1801185b9  lea     rdx, aCoopmftstubIni; "COOPMFTStub::Initialize"
0x1801185c0  mov     r8d, 38h ; '8'; int
0x1801185c6  lea     rcx, [rbp+arg_8]; this
0x1801185ca  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801185cf  xor     r13d, r13d
0x1801185d2  lea     rcx, [rbp+var_30]
0x1801185d6  xor     eax, eax
0x1801185d8  mov     [rbp+var_20], r13
0x1801185dc  mov     [rbp+var_8], rax
0x1801185e0  xorps   xmm0, xmm0
0x1801185e3  mov     rax, [rsi]
0x1801185e6  mov     r12d, r13d
0x1801185e9  mov     r15d, r13d
0x1801185ec  mov     [rbp+pv], r13
0x1801185f0  mov     [rbp+var_30], r13
0x1801185f4  mov     [rbp+arg_8], r13
0x1801185f8  mov     rbx, [rax+40h]
0x1801185fc  movups  xmmword ptr [rbp+pvar], xmm0
0x180118600  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180118605  lea     rdx, [rbp+var_30]
0x180118609  mov     rcx, rsi
0x18011860c  mov     rax, rbx
0x18011860f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118614  test    eax, eax
0x180118616  js      loc_180118701
0x18011861c  mov     rcx, [rbp+var_30]
0x180118620  lea     rdx, MF_TRANSFORM_ASYNC
0x180118627  xor     r8d, r8d
0x18011862a  call    MFGetAttributeUINT32
0x18011862f  test    eax, eax
0x180118631  jz      loc_180118701
0x180118637  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011863e  mov     ebx, 0C00D6D7Ah
0x180118643  test    rcx, rcx
0x180118646  jnz     short loc_180118689
0x180118648  mov     rax, cs:stru_1801FC290.__vftable
0x18011864f  lea     r8, stru_1801FC290
0x180118656  mov     edx, 7F0h
0x18011865b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180118662  mov     rcx, r8
0x180118665  mov     rax, [rax+8]
0x180118669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011866e  test    eax, eax
0x180118670  jnz     short loc_180118682
0x180118672  lea     rcx, stru_1801F8A30
0x180118679  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180118680  jmp     short loc_180118689
0x180118682  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180118689  cmp     [rcx+8], r13b
0x18011868d  jz      short loc_1801186B4
0x18011868f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180118694  cmp     [rax+7CCh], ebx
0x18011869a  jz      short loc_1801186B4
0x18011869c  mov     r9d, ebx; int
0x18011869f  lea     rdx, aCoopmftstubIni; "COOPMFTStub::Initialize"
0x1801186a6  mov     r8d, 48h ; 'H'; int
0x1801186ac  mov     rcx, rax; this
0x1801186af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801186b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801186bb  jb      short loc_1801186E0
0x1801186bd  mov     edx, 0Fh
0x1801186c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801186c9  lea     r8, WPP_1798d81f4e9332f4913729d6a2b23e3a_Traceguids
0x1801186d0  mov     r9, r14
0x1801186d3  mov     dword ptr [rsp+60h+var_40], ebx
0x1801186d7  mov     rcx, [rcx+10h]
0x1801186db  call    WPP_SF_qD
0x1801186e0  lea     rcx, [rbp+pvar]; pvar
0x1801186e4  call    cs:__imp_PropVariantClear
0x1801186ea  lea     rcx, [rbp+arg_8]
0x1801186ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801186f3  lea     rcx, [rbp+var_30]
0x1801186f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801186fc  jmp     loc_180118D62
0x180118701  mov     rax, [rsi]
0x180118704  lea     rcx, [rbp+arg_8]
0x180118708  mov     rbx, [rax]
0x18011870b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180118710  lea     r8, [rbp+arg_8]
0x180118714  mov     rcx, rsi
0x180118717  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18011871e  mov     rax, rbx
0x180118721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118726  test    eax, eax
0x180118728  js      loc_1801187FB
0x18011872e  mov     rcx, [rbp+arg_8]
0x180118732  lea     r8, [rbp+pvar]
0x180118736  lea     rdx, MFPKEY_EXATTRIBUTE_SUPPORTED
0x18011873d  mov     rax, [rcx]
0x180118740  mov     rax, [rax+28h]
0x180118744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118749  test    eax, eax
0x18011874b  js      loc_1801187FB
0x180118751  cmp     word ptr [rbp+pvar], 0Bh
0x180118756  jnz     loc_1801187FB
0x18011875c  cmp     word ptr [rbp+pvar+8], 0FFFFh
0x180118761  jnz     loc_1801187FB
0x180118767  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011876e  mov     ebx, 0C00D6D7Ch
0x180118773  test    rcx, rcx
0x180118776  jnz     short loc_1801187B9
0x180118778  mov     rax, cs:stru_1801FC290.__vftable
0x18011877f  lea     r8, stru_1801FC290
0x180118786  mov     edx, 7F0h
0x18011878b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180118792  mov     rcx, r8
0x180118795  mov     rax, [rax+8]
0x180118799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011879e  test    eax, eax
0x1801187a0  jnz     short loc_1801187B2
0x1801187a2  lea     rcx, stru_1801F8A30
0x1801187a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801187b0  jmp     short loc_1801187B9
0x1801187b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801187b9  cmp     [rcx+8], r13b
0x1801187bd  jz      short loc_1801187E4
0x1801187bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801187c4  cmp     [rax+7CCh], ebx
0x1801187ca  jz      short loc_1801187E4
0x1801187cc  mov     r9d, ebx; int
0x1801187cf  lea     rdx, aCoopmftstubIni; "COOPMFTStub::Initialize"
0x1801187d6  mov     r8d, 50h ; 'P'; int
0x1801187dc  mov     rcx, rax; this
0x1801187df  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801187e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801187eb  jb      loc_1801186E0
0x1801187f1  mov     edx, 10h
0x1801187f6  jmp     loc_1801186C2
0x1801187fb  lea     rcx, [rbp+pvar]; pvar
0x1801187ff  call    cs:__imp_PropVariantClear
0x180118805  lea     rcx, [rbp+arg_8]
0x180118809  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011880e  lea     rcx, [rbp+var_30]
0x180118812  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180118817  mov     rax, [rsi]
0x18011881a  lea     r8, [rbp+arg_10]
0x18011881e  lea     rdx, [rbp+arg_18]
0x180118822  mov     dword ptr [rbp+arg_10], r13d
0x180118826  mov     rcx, rsi
0x180118829  mov     dword ptr [rbp+arg_18], r13d
0x18011882d  mov     rax, [rax+20h]
0x180118831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118836  mov     ebx, eax
0x180118838  test    eax, eax
0x18011883a  jns     loc_1801188CF
0x180118840  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118847  test    rcx, rcx
0x18011884a  jnz     short loc_18011888D
0x18011884c  mov     rcx, cs:stru_1801FC290.__vftable
0x180118853  lea     r8, stru_1801FC290
0x18011885a  mov     edx, 7F0h
0x18011885f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180118866  mov     rax, [rcx+8]
0x18011886a  mov     rcx, r8
0x18011886d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118872  test    eax, eax
0x180118874  jnz     short loc_180118886
0x180118876  lea     rcx, stru_1801F8A30
0x18011887d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180118884  jmp     short loc_18011888D
0x180118886  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18011888d  cmp     [rcx+8], r13b
0x180118891  jz      short loc_1801188B8
0x180118893  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180118898  cmp     [rax+7CCh], ebx
0x18011889e  jz      short loc_1801188B8
0x1801188a0  mov     r9d, ebx; int
0x1801188a3  lea     rdx, aCoopmftstubIni; "COOPMFTStub::Initialize"
0x1801188aa  mov     r8d, 56h ; 'V'; int
0x1801188b0  mov     rcx, rax; this
0x1801188b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801188b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801188bf  jb      loc_180118D62
0x1801188c5  mov     edx, 11h
0x1801188ca  jmp     loc_180118D44
0x1801188cf  mov     ecx, dword ptr [rbp+arg_18]; unsigned __int64
0x1801188d2  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x1801188d6  mov     edx, 4; unsigned __int64
0x1801188db  mov     [rbp+arg_8], r13
0x1801188df  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801188e4  mov     ebx, eax
0x1801188e6  test    eax, eax
0x1801188e8  js      loc_180118CBA
0x1801188ee  mov     r8, [rbp+arg_8]; unsigned __int64
0x1801188f2  lea     r9, [rbp+pv]; void **
0x1801188f6  mov     edx, 1; unsigned int
0x1801188fb  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180118900  mov     ebx, eax
0x180118902  test    eax, eax
0x180118904  js      loc_180118CB6
0x18011890a  mov     ecx, dword ptr [rbp+arg_10]; unsigned __int64
0x18011890d  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x180118911  mov     edx, 4; unsigned __int64
0x180118916  mov     [rbp+arg_8], r13
0x18011891a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18011891f  mov     ebx, eax
0x180118921  test    eax, eax
0x180118923  js      short loc_18011893D
0x180118925  mov     r8, [rbp+arg_8]; unsigned __int64
0x180118929  lea     r9, [rbp+var_20]; void **
0x18011892d  mov     edx, 1; unsigned int
0x180118932  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180118937  mov     r12, [rbp+var_20]
0x18011893b  mov     ebx, eax
0x18011893d  test    ebx, ebx
0x18011893f  jns     loc_1801189F2
0x180118945  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011894c  test    rcx, rcx
0x18011894f  jnz     short loc_180118992
0x180118951  mov     rax, cs:stru_1801FC290.__vftable
0x180118958  lea     r8, stru_1801FC290
0x18011895f  mov     edx, 7F0h
0x180118964  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18011896b  mov     rcx, r8
0x18011896e  mov     rax, [rax+8]
0x180118972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118977  test    eax, eax
0x180118979  jnz     short loc_18011898B
0x18011897b  lea     rcx, stru_1801F8A30
0x180118982  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180118989  jmp     short loc_180118992
0x18011898b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180118992  cmp     [rcx+8], r13b
0x180118996  jz      short loc_1801189BD
0x180118998  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011899d  cmp     [rax+7CCh], ebx
0x1801189a3  jz      short loc_1801189BD
0x1801189a5  mov     r9d, ebx; int
0x1801189a8  lea     rdx, aCoopmftstubIni; "COOPMFTStub::Initialize"
0x1801189af  mov     r8d, 59h ; 'Y'; int
0x1801189b5  mov     rcx, rax; this
0x1801189b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801189bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801189c4  jb      short loc_1801189E9
0x1801189c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801189cd  lea     r8, WPP_1798d81f4e9332f4913729d6a2b23e3a_Traceguids
0x1801189d4  mov     edx, 13h
0x1801189d9  mov     dword ptr [rsp+60h+var_40], ebx
0x1801189dd  mov     r9, r14
0x1801189e0  mov     rcx, [rcx+10h]
0x1801189e4  call    WPP_SF_qD
0x1801189e9  mov     r15, [rbp+pv]
0x1801189ed  jmp     loc_180118D62
0x1801189f2  mov     rax, [rsi]
0x1801189f5  mov     rcx, rsi
0x1801189f8  mov     r15, [rbp+pv]
0x1801189fc  mov     r9d, dword ptr [rbp+arg_10]
0x180118a00  mov     r8, r15
0x180118a03  mov     edx, dword ptr [rbp+arg_18]
0x180118a06  mov     rax, [rax+28h]
0x180118a0a  mov     [rsp+60h+var_40], r12
0x180118a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118a14  test    eax, eax
0x180118a16  jns     short loc_180118A30
0x180118a18  mov     rcx, r15; pv
0x180118a1b  call    cs:__imp_CoTaskMemFree
0x180118a21  mov     rcx, r12; pv
0x180118a24  mov     r15, r13
0x180118a27  call    cs:__imp_CoTaskMemFree
0x180118a2d  mov     r12, r13
0x180118a30  mov     esi, r13d
0x180118a33  cmp     esi, dword ptr [rbp+arg_10]
0x180118a36  jnb     loc_180118BE0
0x180118a3c  test    r12, r12
0x180118a3f  jz      short loc_180118A49
0x180118a41  mov     eax, esi
0x180118a43  mov     ecx, [r12+rax*4]
0x180118a47  jmp     short loc_180118A4B
0x180118a49  mov     ecx, esi
0x180118a4b  mov     dword ptr [rbp+var_30], ecx
0x180118a4e  lea     r8, [rbp+arg_8]
0x180118a52  lea     rcx, [rbp+pv]
0x180118a56  mov     [rbp+pv], r13
0x180118a5a  lea     rdx, [rbp+var_30]
0x180118a5e  mov     dword ptr [rbp+arg_8], 1
0x180118a65  call    ??$MakeAndInitialize@VCStream@@V1@AEBKW4StreamType@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCStream@@@WRL@Microsoft@@@012@AEBK$$QEAW4StreamType@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CStream,CStream,ulong const &,StreamType>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CStream>>,ulong const &,StreamType &&)
0x180118a6a  mov     ebx, eax
0x180118a6c  test    eax, eax
0x180118a6e  js      loc_180118B2E
0x180118a74  mov     rdx, [rbp+pv]; void *
0x180118a78  lea     rcx, [r14+80h]; this
0x180118a7f  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x180118a84  test    rax, rax
0x180118a87  jz      short loc_180118A9A
0x180118a89  lea     rcx, [rbp+pv]
0x180118a8d  mov     [rbp+pv], r13
0x180118a91  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x180118a96  inc     esi
0x180118a98  jmp     short loc_180118A33
  ... truncated ...
```
