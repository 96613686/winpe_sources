# CMFSourceFilter::Load(ushort const *,_AMMediaType const *)

- ea: `0x180054830`
- end: `0x180054f4a`
- name: `?Load@CMFSourceFilter@@UEAAJPEBGPEBU_AMMediaType@@@Z`
- size: `1818`
- prototype: `int(CMFSourceFilter *__hidden this, const unsigned __int16 *, const struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `23`
- tags: `broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180023690`
- `0x180023738`
- `0x180023c88`
- `0x180023f3c`
- `0x180024964`
- `0x180024bcc`
- `0x180029550`
- `0x180032a50`
- `0x180036cb4`
- `0x1800381d8`
- `0x18004840c`
- `0x180051ce4`
- `0x180053934`
- `0x180054830`
- `0x180054f50`
- `0x180074160`
- `0x1800765a0`
- `0x1800928c8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x180054b53`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x180054b53`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800548bc`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800548bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800548fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054d89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800548fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054d89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054885`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054885`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800549a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054a9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054bb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054c77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800549a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054a9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054bb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054c77`
- `MFPlat!CreatePropertyStore` at `0x180054a78`
- `MFPlat!CreatePropertyStore` at `0x180054a78`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x180054e6f`
- `MFPlat!MFCreateAlignedMemoryBuffer` at `0x180054e6f`
- `MFPlat!MFCreateAsyncResult` at `0x180054c52`
- `MFPlat!MFCreateAsyncResult` at `0x180054c52`
- `MFPlat!MFCreateSourceResolver` at `0x18005497e`
- `MFPlat!MFCreateSourceResolver` at `0x18005497e`

## pseudocode

```c
__int64 __fastcall CMFSourceFilter::Load(CMFSourceFilter *this, const unsigned __int16 *a2, struct _AMMediaType *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  size_t v7; // rax
  HRESULT PropertyStore; // ebx
  int (__fastcall ***v9)(_QWORD, GUID *, char *); // rcx
  _QWORD *v10; // rbx
  CallStackTracing *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  _QWORD *v15; // r15
  CallStackTracing *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rax
  __int64 v26; // r11
  struct _GUID *v27; // r8
  char v28; // [rsp+40h] [rbp-29h] BYREF
  bool v29[3]; // [rsp+41h] [rbp-28h] BYREF
  int v30; // [rsp+44h] [rbp-25h] BYREF
  struct _AMMediaType *v31; // [rsp+48h] [rbp-21h]
  IMFMediaBuffer *ppBuffer; // [rsp+50h] [rbp-19h] BYREF
  __int128 v33; // [rsp+58h] [rbp-11h] BYREF
  __int64 v34; // [rsp+68h] [rbp-1h]
  IID v35; // [rsp+70h] [rbp+7h] BYREF
  int v36; // [rsp+80h] [rbp+17h]

  v31 = a3;
  if ( !a2 )
    return 2147500035LL;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 40);
  v29[0] = 0;
  v30 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this - 1);
  CBaseFilter::NotifyEvent((CMFSourceFilter *)((char *)this - 176), 16, 1, 0);
  LODWORD(ppBuffer) = -1;
  v7 = wcslen(a2);
  if ( (int)UIntPtrToLong(v7, (int *)&ppBuffer) < 0 )
  {
    PropertyStore = -2147024785;
    *((_DWORD *)this + 425) = -2147024785;
LABEL_6:
    LeaveCriticalSection(v6);
    goto LABEL_81;
  }
  PropertyStore = CMFBaseStringT<unsigned short>::_Append((char *)this + 1696, a2, (unsigned int)ppBuffer);
  if ( PropertyStore < 0 )
    goto LABEL_6;
  v9 = (int (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this - 10);
  v10 = (_QWORD *)((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  if ( v9 )
  {
    if ( (**v9)(v9, &IID_IGraphBuilder, (char *)this + 64) >= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 16LL))(*v10);
    else
      *v10 = 0;
  }
  CMFSourceFilter::_ReleaseByteStream((CMFSourceFilter *)((char *)this - 176));
  if ( !*((_QWORD *)this + 226) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CMFSourceFilter::Load", 5176);
    PropertyStore = MFCreateSourceResolver((IMFSourceResolver **)this + 226);
    if ( PropertyStore < 0 )
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != PropertyStore )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFSourceFilter::Load", 5176, PropertyStore);
      }
      if ( !g_wppLevels )
        goto LABEL_24;
      v14 = 87;
LABEL_23:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids,
        (char *)this - 176,
        PropertyStore);
LABEL_24:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
      goto LABEL_6;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  }
  v15 = (_QWORD *)((char *)this + 56);
  if ( !*((_QWORD *)this + 7) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CMFSourceFilter::Load", 5182);
    PropertyStore = CreatePropertyStore((IPropertyStore **)this + 7);
    if ( PropertyStore < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( *((_DWORD *)v18 + 499) != PropertyStore )
          CallStackContext::TraceFailure(v18, "CMFSourceFilter::Load", 5182, PropertyStore);
      }
      if ( !g_wppLevels )
        goto LABEL_24;
      v14 = 88;
      goto LABEL_23;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  }
  v36 = 0;
  v34 = 0;
  v33 = 0;
  v35 = MFNETSOURCE_ENABLE_STREAMING;
  memset(&v33, 0, 0x18u);
  WORD4(v33) = 0;
  LOWORD(v33) = 11;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "CMFSourceFilter::Load", 5196);
  PropertyStore = (*(__int64 (__fastcall **)(_QWORD, IID *, __int128 *))(*(_QWORD *)*v15 + 48LL))(*v15, &v35, &v33);
  if ( PropertyStore < 0 )
  {
    v19 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v19);
      if ( *((_DWORD *)v21 + 499) != PropertyStore )
        CallStackContext::TraceFailure(v21, "CMFSourceFilter::Load", 5196, PropertyStore);
    }
    if ( !g_wppLevels )
      goto LABEL_24;
    v14 = 89;
    goto LABEL_23;
  }
  ATL::CComPtrBase<IMFAsyncResult>::Release((char *)this + 1824);
  PropertyStore = MFCreateAsyncResult(0, 0, 0, (IMFAsyncResult **)this + 228);
  if ( PropertyStore < 0 )
  {
    v22 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext(v22);
      if ( *((_DWORD *)v24 + 499) != PropertyStore )
        CallStackContext::TraceFailure(v24, "CMFSourceFilter::Load", 5199, PropertyStore);
    }
    if ( !g_wppLevels )
      goto LABEL_24;
    v14 = 90;
    goto LABEL_23;
  }
  if ( *((_QWORD *)this + 227) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 227, 0);
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 460) = 0;
  v25 = CMFBaseStringT<unsigned short>::PContents((char *)this + 1696);
  PropertyStore = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, char *, char *, _QWORD))(*(_QWORD *)v26 + 40LL))(
                    v26,
                    v25,
                    65538,
                    *v15,
                    (char *)this + 1816,
                    (char *)this + 1880,
                    *((_QWORD *)this + 228));
  if ( PropertyStore < 0 )
    goto LABEL_24;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  LeaveCriticalSection(v6);
  CAMEvent::Wait((CMFSourceFilter *)((char *)this + 1832), 0xFFFFFFFF);
  if ( *((_DWORD *)this + 8) )
  {
    PropertyStore = -2147467260;
  }
  else
  {
    PropertyStore = *((_DWORD *)this + 460);
    if ( PropertyStore >= 0 )
    {
      if ( v31 )
      {
        CMediaType::Set((CMFSourceFilter *)((char *)this + 1720), v31);
      }
      else
      {
        PropertyStore = CMFSourceFilter::_GetMediaTypeStream(
                          (CMFSourceFilter *)((char *)this - 176),
                          (CMFSourceFilter *)((char *)this + 1720),
                          v27,
                          v29,
                          (enum Mpeg2_TS_Flavor *)&v30);
        if ( PropertyStore < 0 )
        {
          CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v29, "CMFSourceFilter::Load", 5249);
          if ( (unsigned __int8)byte_1800EACCB >= 8u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              91,
              &WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids,
              (unsigned int)PropertyStore);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v29);
          goto LABEL_81;
        }
      }
      if ( (unsigned int)CMFSourceFilter::_ShouldUsePushMode((CMFSourceFilter *)((char *)this - 176)) )
      {
        *((_DWORD *)this + 18) = 1;
        ppBuffer = 0;
        if ( MFCreateAlignedMemoryBuffer(0x20000u, 0x1FFu, &ppBuffer) >= 0 )
          CMFSourceMPEG2TSPin::SetUseCircularBuffer(*((CMFSourceMPEG2TSPin **)this + 211), ppBuffer);
        if ( v29[0] )
          *(_DWORD *)(*((_QWORD *)this + 211) + 456LL) = v30;
        PropertyStore = CBasePin::SetMediaType(
                          (CBasePin *)(*((_QWORD *)this + 211) + 120LL),
                          (CMFSourceFilter *)((char *)this + 1720));
        ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&ppBuffer);
      }
      else
      {
        PropertyStore = (*(__int64 (__fastcall **)(char *, char *))(*((_QWORD *)this + 11) + 72LL))(
                          (char *)this + 88,
                          (char *)this + 1720);
      }
      if ( PropertyStore >= 0 )
        goto LABEL_83;
    }
  }
LABEL_81:
  CMFSourceFilter::_ReleaseByteStream((CMFSourceFilter *)((char *)this - 176));
  if ( *((_QWORD *)this + 6) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 6, 0);
LABEL_83:
  ATL::CComPtrBase<IMFAsyncResult>::Release((char *)this + 1824);
  ATL::CComPtrBase<IMFAsyncResult>::Release((char *)this + 1816);
  CBaseFilter::NotifyEvent((CMFSourceFilter *)((char *)this - 176), 16, 0, 0);
  return (unsigned int)PropertyStore;
}

```

## disassembly

```asm
0x180054830  mov     [rsp-8+arg_18], rbx
0x180054835  push    rbp
0x180054836  push    rsi
0x180054837  push    rdi
0x180054838  push    r12
0x18005483a  push    r13
0x18005483c  push    r14
0x18005483e  push    r15
0x180054840  lea     rbp, [rsp-27h]
0x180054845  sub     rsp, 90h
0x18005484c  mov     rax, cs:__security_cookie
0x180054853  xor     rax, rsp
0x180054856  mov     [rbp+57h+var_38], rax
0x18005485a  xor     r13d, r13d
0x18005485d  mov     [rbp+57h+var_78], r8
0x180054861  mov     rbx, rdx
0x180054864  mov     rdi, rcx
0x180054867  test    rdx, rdx
0x18005486a  jnz     short loc_180054876
0x18005486c  mov     eax, 80004003h
0x180054871  jmp     loc_180054F22
0x180054876  lea     r14, [rcx-28h]
0x18005487a  mov     [rbp+57h+var_7F], r13b
0x18005487e  mov     rcx, r14; lpCriticalSection
0x180054881  mov     [rbp+57h+var_7C], r13d
0x180054885  call    cs:__imp_EnterCriticalSection
0x18005488c  nop     dword ptr [rax+rax+00h]
0x180054891  xor     r9d, r9d; __int64
0x180054894  lea     rsi, [rdi-0B0h]
0x18005489b  mov     rcx, rsi; this
0x18005489e  lea     edx, [r9+10h]; int
0x1800548a2  lea     r8d, [r9+1]; __int64
0x1800548a6  call    ?NotifyEvent@CBaseFilter@@QEAAJJ_J0@Z; CBaseFilter::NotifyEvent(long,__int64,__int64)
0x1800548ab  mov     rcx, rbx; String
0x1800548ae  mov     dword ptr [rbp+57h+ppBuffer], 0FFFFFFFFh
0x1800548b5  lea     r15, [rdi+6A0h]
0x1800548bc  call    cs:__imp_wcslen
0x1800548c3  nop     dword ptr [rax+rax+00h]
0x1800548c8  mov     rcx, rax; unsigned __int64
0x1800548cb  lea     rdx, [rbp+57h+ppBuffer]; int *
0x1800548cf  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x1800548d4  test    eax, eax
0x1800548d6  jns     short loc_1800548E3
0x1800548d8  mov     ebx, 8007006Fh
0x1800548dd  mov     [r15+4], ebx
0x1800548e1  jmp     short loc_1800548F8
0x1800548e3  mov     r8d, dword ptr [rbp+57h+ppBuffer]
0x1800548e7  mov     rdx, rbx
0x1800548ea  mov     rcx, r15
0x1800548ed  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x1800548f2  mov     ebx, eax
0x1800548f4  test    eax, eax
0x1800548f6  jns     short loc_18005490C
0x1800548f8  mov     rcx, r14; lpCriticalSection
0x1800548fb  call    cs:__imp_LeaveCriticalSection
0x180054902  nop     dword ptr [rax+rax+00h]
0x180054907  jmp     loc_180054EDE
0x18005490c  mov     rcx, [rdi-50h]
0x180054910  lea     rbx, [rdi+40h]
0x180054914  mov     [rbx], r13
0x180054917  test    rcx, rcx
0x18005491a  jz      short loc_180054949
0x18005491c  mov     rax, [rcx]
0x18005491f  lea     rdx, IID_IGraphBuilder
0x180054926  mov     r8, rbx
0x180054929  mov     rax, [rax]
0x18005492c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054931  test    eax, eax
0x180054933  jns     short loc_18005493A
0x180054935  mov     [rbx], r13
0x180054938  jmp     short loc_180054949
0x18005493a  mov     rcx, [rbx]
0x18005493d  mov     rax, [rcx]
0x180054940  mov     rax, [rax+10h]
0x180054944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054949  mov     rcx, rsi; this
0x18005494c  call    ?_ReleaseByteStream@CMFSourceFilter@@QEAAXXZ; CMFSourceFilter::_ReleaseByteStream(void)
0x180054951  lea     r12, [rdi+710h]
0x180054958  cmp     [r12], r13
0x18005495c  jnz     loc_180054A52
0x180054962  mov     r15d, 1438h
0x180054968  lea     rdx, aCmfsourcefilte_1; "CMFSourceFilter::Load"
0x18005496f  mov     r8d, r15d; int
0x180054972  lea     rcx, [rbp+57h+var_80]; this
0x180054976  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005497b  mov     rcx, r12; ppISourceResolver
0x18005497e  call    cs:__imp_MFCreateSourceResolver
0x180054985  nop     dword ptr [rax+rax+00h]
0x18005498a  mov     ebx, eax
0x18005498c  test    eax, eax
0x18005498e  jns     loc_180054A49
0x180054994  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005499b  test    rcx, rcx
0x18005499e  jnz     short loc_1800549E7
0x1800549a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800549a7  nop     dword ptr [rax+rax+00h]
0x1800549ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800549b3  mov     rcx, rax
0x1800549b6  test    rax, rax
0x1800549b9  jz      short loc_1800549D9
0x1800549bb  mov     rax, [rax]
0x1800549be  mov     edx, 7F0h
0x1800549c3  mov     rax, [rax+8]
0x1800549c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549cc  test    eax, eax
0x1800549ce  jz      short loc_1800549D9
0x1800549d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800549d7  jmp     short loc_1800549E7
0x1800549d9  lea     rcx, qword_1800EB130; this
0x1800549e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800549e7  cmp     [rcx+8], r13b
0x1800549eb  jz      short loc_180054A0F
0x1800549ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800549f2  cmp     [rax+7CCh], ebx
0x1800549f8  jz      short loc_180054A0F
0x1800549fa  mov     r9d, ebx; int
0x1800549fd  lea     rdx, aCmfsourcefilte_1; "CMFSourceFilter::Load"
0x180054a04  mov     r8d, r15d; int
0x180054a07  mov     rcx, rax; this
0x180054a0a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054a0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180054a16  jb      short loc_180054A3B
0x180054a18  mov     edx, 57h ; 'W'
0x180054a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054a24  lea     r8, WPP_a17c9a5307dc339d07bf8540fd97a1f5_Traceguids
0x180054a2b  mov     r9, rsi
0x180054a2e  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180054a32  mov     rcx, [rcx+10h]
0x180054a36  call    WPP_SF_qD
0x180054a3b  lea     rcx, [rbp+57h+var_80]; this
0x180054a3f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054a44  jmp     loc_1800548F8
0x180054a49  lea     rcx, [rbp+57h+var_80]; this
0x180054a4d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054a52  lea     r15, [rdi+38h]
0x180054a56  cmp     [r15], r13
0x180054a59  jnz     loc_180054B2C
0x180054a5f  mov     r8d, 143Eh; int
0x180054a65  lea     rdx, aCmfsourcefilte_1; "CMFSourceFilter::Load"
0x180054a6c  lea     rcx, [rbp+57h+var_80]; this
0x180054a70  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054a75  mov     rcx, r15; ppStore
0x180054a78  call    cs:__imp_CreatePropertyStore
0x180054a7f  nop     dword ptr [rax+rax+00h]
0x180054a84  mov     ebx, eax
0x180054a86  test    eax, eax
0x180054a88  jns     loc_180054B23
0x180054a8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054a95  test    rcx, rcx
0x180054a98  jnz     short loc_180054AE1
0x180054a9a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054aa1  nop     dword ptr [rax+rax+00h]
0x180054aa6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054aad  mov     rcx, rax
0x180054ab0  test    rax, rax
0x180054ab3  jz      short loc_180054AD3
0x180054ab5  mov     rax, [rax]
0x180054ab8  mov     edx, 7F0h
0x180054abd  mov     rax, [rax+8]
0x180054ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ac6  test    eax, eax
0x180054ac8  jz      short loc_180054AD3
0x180054aca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054ad1  jmp     short loc_180054AE1
0x180054ad3  lea     rcx, qword_1800EB130; this
0x180054ada  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054ae1  cmp     [rcx+8], r13b
0x180054ae5  jz      short loc_180054B0C
0x180054ae7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054aec  cmp     [rax+7CCh], ebx
0x180054af2  jz      short loc_180054B0C
0x180054af4  mov     r9d, ebx; int
0x180054af7  lea     rdx, aCmfsourcefilte_1; "CMFSourceFilter::Load"
0x180054afe  mov     r8d, 143Eh; int
0x180054b04  mov     rcx, rax; this
0x180054b07  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054b0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180054b13  jb      loc_180054A3B
0x180054b19  mov     edx, 58h ; 'X'
0x180054b1e  jmp     loc_180054A1D
0x180054b23  lea     rcx, [rbp+57h+var_80]; this
0x180054b27  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054b2c  movups  xmm1, xmmword ptr cs:MFNETSOURCE_ENABLE_STREAMING.Data1
0x180054b33  xor     eax, eax
0x180054b35  mov     [rbp+57h+var_40], r13d
0x180054b39  xorps   xmm0, xmm0
0x180054b3c  mov     [rbp+57h+var_58], rax
0x180054b40  xor     edx, edx; Val
0x180054b42  lea     rcx, [rbp+57h+var_68]; void *
0x180054b46  movups  [rbp+57h+var_68], xmm0
0x180054b4a  lea     r8d, [rax+18h]; Size
0x180054b4e  movdqu  [rbp+57h+var_50], xmm1
0x180054b53  call    cs:__imp_memset
0x180054b5a  nop     dword ptr [rax+rax+00h]
0x180054b5f  mov     eax, 0Bh
0x180054b64  mov     word ptr [rbp+57h+var_68+8], r13w
0x180054b69  mov     r8d, 144Ch; int
0x180054b6f  mov     word ptr [rbp+57h+var_68], ax
0x180054b73  lea     rdx, aCmfsourcefilte_1; "CMFSourceFilter::Load"
0x180054b7a  lea     rcx, [rbp+57h+var_80]; this
0x180054b7e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054b83  mov     rcx, [r15]
0x180054b86  lea     r8, [rbp+57h+var_68]
0x180054b8a  lea     rdx, [rbp+57h+var_50]
0x180054b8e  mov     rax, [rcx]
0x180054b91  mov     rax, [rax+30h]
0x180054b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b9a  mov     ebx, eax
0x180054b9c  test    eax, eax
0x180054b9e  jns     loc_180054C39
0x180054ba4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054bab  test    rcx, rcx
0x180054bae  jnz     short loc_180054BF7
0x180054bb0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054bb7  nop     dword ptr [rax+rax+00h]
0x180054bbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054bc3  mov     rcx, rax
0x180054bc6  test    rax, rax
0x180054bc9  jz      short loc_180054BE9
0x180054bcb  mov     rax, [rax]
0x180054bce  mov     edx, 7F0h
0x180054bd3  mov     rax, [rax+8]
0x180054bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bdc  test    eax, eax
0x180054bde  jz      short loc_180054BE9
0x180054be0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054be7  jmp     short loc_180054BF7
0x180054be9  lea     rcx, qword_1800EB130; this
0x180054bf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054bf7  cmp     [rcx+8], r13b
0x180054bfb  jz      short loc_180054C22
0x180054bfd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054c02  cmp     [rax+7CCh], ebx
0x180054c08  jz      short loc_180054C22
0x180054c0a  mov     r9d, ebx; int
0x180054c0d  lea     rdx, aCmfsourcefilte_1; "CMFSourceFilter::Load"
0x180054c14  mov     r8d, 144Ch; int
0x180054c1a  mov     rcx, rax; this
0x180054c1d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054c22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180054c29  jb      loc_180054A3B
0x180054c2f  mov     edx, 59h ; 'Y'
0x180054c34  jmp     loc_180054A1D
0x180054c39  lea     r13, [rdi+720h]
0x180054c40  mov     rcx, r13
0x180054c43  call    ?Release@?$CComPtrBase@UIMFAsyncResult@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IMFAsyncResult>::Release(void)
0x180054c48  mov     r9, r13; ppAsyncResult
0x180054c4b  xor     r8d, r8d; punkState
0x180054c4e  xor     edx, edx; pCallback
0x180054c50  xor     ecx, ecx; punkObject
0x180054c52  call    cs:__imp_MFCreateAsyncResult
0x180054c59  nop     dword ptr [rax+rax+00h]
0x180054c5e  mov     ebx, eax
0x180054c60  test    eax, eax
0x180054c62  jns     loc_180054D00
0x180054c68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c6f  xor     r13d, r13d
0x180054c72  test    rcx, rcx
0x180054c75  jnz     short loc_180054CBE
0x180054c77  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054c7e  nop     dword ptr [rax+rax+00h]
0x180054c83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c8a  mov     rcx, rax
0x180054c8d  test    rax, rax
0x180054c90  jz      short loc_180054CB0
0x180054c92  mov     rax, [rax]
0x180054c95  mov     edx, 7F0h
0x180054c9a  mov     rax, [rax+8]
0x180054c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ca3  test    eax, eax
0x180054ca5  jz      short loc_180054CB0
0x180054ca7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054cae  jmp     short loc_180054CBE
0x180054cb0  lea     rcx, qword_1800EB130; this
0x180054cb7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054cbe  cmp     [rcx+8], r13b
0x180054cc2  jz      short loc_180054CE9
0x180054cc4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054cc9  cmp     [rax+7CCh], ebx
0x180054ccf  jz      short loc_180054CE9
0x180054cd1  mov     r9d, ebx; int
0x180054cd4  lea     rdx, aCmfsourcefilte_1; "CMFSourceFilter::Load"
0x180054cdb  mov     r8d, 144Fh; int
0x180054ce1  mov     rcx, rax; this
0x180054ce4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054ce9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180054cf0  jb      loc_180054A3B
0x180054cf6  mov     edx, 5Ah ; 'Z'
0x180054cfb  jmp     loc_180054A1D
0x180054d00  lea     rbx, [rdi+718h]
0x180054d07  cmp     qword ptr [rbx], 0
0x180054d0b  jz      short loc_180054D17
0x180054d0d  xor     edx, edx; struct IUnknown *
0x180054d0f  mov     rcx, rbx; struct IUnknown **
0x180054d12  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180054d17  mov     r11, [r12]
0x180054d1b  lea     rcx, [rdi+6A0h]
0x180054d22  mov     dword ptr [rdi+20h], 0
0x180054d29  mov     dword ptr [rdi+730h], 0
0x180054d33  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
  ... truncated ...
```
