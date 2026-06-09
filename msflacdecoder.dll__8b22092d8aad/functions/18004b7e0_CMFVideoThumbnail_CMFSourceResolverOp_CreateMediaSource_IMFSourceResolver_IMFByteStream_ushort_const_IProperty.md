# CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(IMFSourceResolver *,IMFByteStream *,ushort const *,IPropertyStore *,ulong,IMFMediaSource * *)

- ea: `0x18004b7e0`
- end: `0x18004bc5c`
- name: `?CreateMediaSource@CMFSourceResolverOp@CMFVideoThumbnail@@QEAAJPEAUIMFSourceResolver@@PEAUIMFByteStream@@PEBGPEAUIPropertyStore@@KPEAPEAUIMFMediaSource@@@Z`
- size: `1148`
- prototype: `__int64 __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this, struct IMFSourceResolver *, struct IMFByteStream *, const unsigned __int16 *, struct IPropertyStore *, DWORD dwMilliseconds, struct IMFMediaSource **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004ab18`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180034a04`
- `0x180039e60`
- `0x180048710`
- `0x18004b7e0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004baa6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004baa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ba99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bc19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ba99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bc19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b992`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bab1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b992`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bab1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b8ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b9f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004baf1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bb8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b8ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b9f5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004baf1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bb8b`

## string_xrefs

- `0x18004b81e`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18004b941`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18004ba4c`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18004bb48`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18004bbe2`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(
        CMFVideoThumbnail::CMFSourceResolverOp *this,
        struct IMFSourceResolver *a2,
        struct IMFByteStream *a3,
        const unsigned __int16 *a4,
        struct IPropertyStore *a5,
        DWORD dwMilliseconds,
        struct IMFMediaSource **a7)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v11; // ebx
  __int128 v12; // xmm0
  __int64 v13; // rdx
  int v14; // ebx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  HRESULT (__stdcall *BeginCreateObjectFromByteStream)(IMFSourceResolver *, IMFByteStream *, LPCWSTR, DWORD, IPropertyStore *, IUnknown **, IMFAsyncCallback *, IUnknown *); // rbx
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  DWORD v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  struct IMFMediaSource *v33; // rax
  _BYTE v35[8]; // [rsp+50h] [rbp-51h] BYREF
  __int64 v36; // [rsp+58h] [rbp-49h] BYREF
  const unsigned __int16 *v37; // [rsp+60h] [rbp-41h]
  PROPVARIANT pvar; // [rsp+68h] [rbp-39h] BYREF
  _BYTE v39[16]; // [rsp+80h] [rbp-21h] BYREF

  v37 = a4;
  *a7 = 0;
  v36 = 0;
  memset(&pvar, 0, sizeof(pvar));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v35,
    "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource",
    2168);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 11) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 296LL))(*((_QWORD *)this + 11));
    v12 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 11) + 280LL))(
                       *((_QWORD *)this + 11),
                       v39);
    *((_DWORD *)ThreadRelativeContext + 504) = v11;
    *((_OWORD *)ThreadRelativeContext + 125) = v12;
  }
  pvar.hVal.QuadPart = 1;
  pvar.vt = 19;
  v14 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a5->lpVtbl->SetValue)(
          a5,
          MFPKEY_MediaSource_ThumbnailMode,
          &pvar);
  if ( v14 >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    BeginCreateObjectFromByteStream = a2->lpVtbl->BeginCreateObjectFromByteStream;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v14 = ((__int64 (__fastcall *)(struct IMFSourceResolver *, struct IMFByteStream *, const unsigned __int16 *, __int64, struct IPropertyStore *, __int64 *, char *, struct IMFSourceResolver *))BeginCreateObjectFromByteStream)(
            a2,
            a3,
            v37,
            66561,
            a5,
            &v36,
            (char *)this + 16,
            a2);
    if ( v14 < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != v14 )
          CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2178, v14);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_52;
      v23 = 213;
      goto LABEL_26;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v24 = WaitForSingleObject(*((HANDLE *)this + 4), dwMilliseconds);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( v24 == 258 )
    {
      v26 = v36;
      *((_BYTE *)this + 44) = 1;
      ((void (__fastcall *)(struct IMFSourceResolver *, __int64))a2->lpVtbl->CancelObjectCreation)(a2, v26);
    }
    else if ( !v24 )
    {
      v14 = *((_DWORD *)this + 10);
      if ( v14 >= 0 )
      {
        v33 = (struct IMFMediaSource *)*((_QWORD *)this + 3);
        *((_QWORD *)this + 3) = 0;
        *a7 = v33;
        goto LABEL_52;
      }
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v32 + 499) != v14 )
          CallStackContext::TraceFailure(v32, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2196, v14);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_52;
      v23 = 215;
LABEL_26:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v14);
LABEL_52:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      goto LABEL_53;
    }
    v27 = (__int64 *)CallStackTracing::s_wpInstance;
    v14 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)v29 + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          v29,
          "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource",
          2194,
          -2147418113);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_52;
    v23 = 214;
    goto LABEL_26;
  }
  v15 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != v14 )
      CallStackContext::TraceFailure(v17, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2170, v14);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v14);
LABEL_53:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v35);
  CMFPropVariant::Clear(&pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18004b7e0  push    rbp
0x18004b7e2  push    rbx
0x18004b7e3  push    rsi
0x18004b7e4  push    rdi
0x18004b7e5  push    r12
0x18004b7e7  push    r13
0x18004b7e9  push    r14
0x18004b7eb  push    r15
0x18004b7ed  lea     rbp, [rsp-7]
0x18004b7f2  sub     rsp, 0A8h
0x18004b7f9  mov     rax, cs:__security_cookie
0x18004b800  xor     rax, rsp
0x18004b803  mov     [rbp+3Fh+var_50], rax
0x18004b807  mov     r12, [rbp+3Fh+arg_30]
0x18004b80b  mov     r13, r8
0x18004b80e  mov     r15, [rbp+3Fh+arg_20]
0x18004b812  mov     r14, rdx
0x18004b815  mov     rsi, rcx
0x18004b818  mov     [rbp+3Fh+var_80], r9
0x18004b81c  xor     edi, edi
0x18004b81e  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18004b825  xorps   xmm0, xmm0
0x18004b828  mov     [r12], rdi
0x18004b82c  xor     eax, eax
0x18004b82e  mov     [rbp+3Fh+var_88], rdi
0x18004b832  mov     r8d, 878h; int
0x18004b838  mov     qword ptr [rbp+3Fh+pvar+10h], rax
0x18004b83c  lea     rcx, [rbp+3Fh+var_90]; this
0x18004b840  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x18004b844  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004b849  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b850  cmp     [rcx+8], dil
0x18004b854  jz      short loc_18004B8A9
0x18004b856  cmp     [rsi+58h], rdi
0x18004b85a  jz      short loc_18004B8A9
0x18004b85c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b861  mov     rdx, [rsi+58h]
0x18004b865  mov     rdi, rax
0x18004b868  mov     rcx, [rdx]
0x18004b86b  mov     rax, [rcx+128h]
0x18004b872  mov     rcx, rdx
0x18004b875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b87a  mov     r8, [rsi+58h]
0x18004b87e  lea     rdx, [rbp+3Fh+var_60]
0x18004b882  mov     ebx, eax
0x18004b884  mov     rcx, [r8]
0x18004b887  mov     rax, [rcx+118h]
0x18004b88e  mov     rcx, r8
0x18004b891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b896  movups  xmm0, xmmword ptr [rax]
0x18004b899  mov     [rdi+7E0h], ebx
0x18004b89f  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004b8a7  xor     edi, edi
0x18004b8a9  mov     eax, 13h
0x18004b8ae  mov     qword ptr [rbp+3Fh+pvar+8], 1
0x18004b8b6  mov     word ptr [rbp+3Fh+pvar], ax
0x18004b8ba  lea     r8, [rbp+3Fh+pvar]
0x18004b8be  mov     rax, [r15]
0x18004b8c1  lea     rdx, MFPKEY_MediaSource_ThumbnailMode
0x18004b8c8  mov     rcx, r15
0x18004b8cb  mov     rax, [rax+30h]
0x18004b8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8d4  mov     ebx, eax
0x18004b8d6  test    eax, eax
0x18004b8d8  jns     loc_18004B98B
0x18004b8de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b8e5  test    rcx, rcx
0x18004b8e8  jnz     short loc_18004B92B
0x18004b8ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b8f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b8f7  mov     rcx, rax
0x18004b8fa  test    rax, rax
0x18004b8fd  jz      short loc_18004B91D
0x18004b8ff  mov     rax, [rax]
0x18004b902  mov     edx, 7F0h
0x18004b907  mov     rax, [rax+8]
0x18004b90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b910  test    eax, eax
0x18004b912  jz      short loc_18004B91D
0x18004b914  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b91b  jmp     short loc_18004B92B
0x18004b91d  lea     rcx, qword_18006EB20; this
0x18004b924  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b92b  cmp     [rcx+8], dil
0x18004b92f  jz      short loc_18004B956
0x18004b931  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b936  cmp     [rax+7CCh], ebx
0x18004b93c  jz      short loc_18004B956
0x18004b93e  mov     r9d, ebx; int
0x18004b941  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18004b948  mov     r8d, 87Ah; int
0x18004b94e  mov     rcx, rax; this
0x18004b951  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b956  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004b95b  cmp     al, 1
0x18004b95d  jb      loc_18004BC1F
0x18004b963  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b96a  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004b971  mov     edx, 0D4h
0x18004b976  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18004b97a  mov     r9, rsi
0x18004b97d  mov     rcx, [rcx+10h]
0x18004b981  call    WPP_SF_qd
0x18004b986  jmp     loc_18004BC1F
0x18004b98b  lea     rdi, [rsi+30h]
0x18004b98f  mov     rcx, rdi; lpCriticalSection
0x18004b992  call    cs:__imp_EnterCriticalSection
0x18004b998  mov     rax, [r14]
0x18004b99b  lea     rcx, [rbp+3Fh+var_88]
0x18004b99f  mov     rbx, [rax+38h]
0x18004b9a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b9a8  mov     r8, [rbp+3Fh+var_80]
0x18004b9ac  lea     rcx, [rsi+10h]
0x18004b9b0  mov     [rsp+0E0h+var_A8], r14
0x18004b9b5  lea     rax, [rbp+3Fh+var_88]
0x18004b9b9  mov     [rsp+0E0h+var_B0], rcx
0x18004b9be  mov     r9d, 10401h
0x18004b9c4  mov     [rsp+0E0h+var_B8], rax
0x18004b9c9  mov     rdx, r13
0x18004b9cc  mov     rax, rbx
0x18004b9cf  mov     [rsp+0E0h+var_C0], r15
0x18004b9d4  mov     rcx, r14
0x18004b9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9dc  xor     r15d, r15d
0x18004b9df  mov     ebx, eax
0x18004b9e1  test    eax, eax
0x18004b9e3  jns     loc_18004BA96
0x18004b9e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b9f0  test    rcx, rcx
0x18004b9f3  jnz     short loc_18004BA36
0x18004b9f5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b9fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ba02  mov     rcx, rax
0x18004ba05  test    rax, rax
0x18004ba08  jz      short loc_18004BA28
0x18004ba0a  mov     rax, [rax]
0x18004ba0d  mov     edx, 7F0h
0x18004ba12  mov     rax, [rax+8]
0x18004ba16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba1b  test    eax, eax
0x18004ba1d  jz      short loc_18004BA28
0x18004ba1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ba26  jmp     short loc_18004BA36
0x18004ba28  lea     rcx, qword_18006EB20; this
0x18004ba2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ba36  cmp     [rcx+8], r15b
0x18004ba3a  jz      short loc_18004BA61
0x18004ba3c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ba41  cmp     [rax+7CCh], ebx
0x18004ba47  jz      short loc_18004BA61
0x18004ba49  mov     r9d, ebx; int
0x18004ba4c  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18004ba53  mov     r8d, 882h; int
0x18004ba59  mov     rcx, rax; this
0x18004ba5c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ba61  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004ba66  cmp     al, 1
0x18004ba68  jb      loc_18004BC16
0x18004ba6e  mov     edx, 0D5h
0x18004ba73  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba7a  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004ba81  mov     r9, rsi
0x18004ba84  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18004ba88  mov     rcx, [rcx+10h]
0x18004ba8c  call    WPP_SF_qd
0x18004ba91  jmp     loc_18004BC16
0x18004ba96  mov     rcx, rdi; lpCriticalSection
0x18004ba99  call    cs:__imp_LeaveCriticalSection
0x18004ba9f  mov     edx, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x18004baa2  mov     rcx, [rsi+20h]; hHandle
0x18004baa6  call    cs:__imp_WaitForSingleObject
0x18004baac  mov     rcx, rdi; lpCriticalSection
0x18004baaf  mov     ebx, eax
0x18004bab1  call    cs:__imp_EnterCriticalSection
0x18004bab7  cmp     ebx, 102h
0x18004babd  jnz     short loc_18004BAD8
0x18004babf  mov     rdx, [rbp+3Fh+var_88]
0x18004bac3  mov     rcx, r14
0x18004bac6  mov     byte ptr [rsi+2Ch], 1
0x18004baca  mov     rax, [r14]
0x18004bacd  mov     rax, [rax+48h]
0x18004bad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bad6  jmp     short loc_18004BAE0
0x18004bad8  test    ebx, ebx
0x18004bada  jz      loc_18004BB74
0x18004bae0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bae7  mov     ebx, 8000FFFFh
0x18004baec  test    rcx, rcx
0x18004baef  jnz     short loc_18004BB32
0x18004baf1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004baf7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bafe  mov     rcx, rax
0x18004bb01  test    rax, rax
0x18004bb04  jz      short loc_18004BB24
0x18004bb06  mov     rax, [rax]
0x18004bb09  mov     edx, 7F0h
0x18004bb0e  mov     rax, [rax+8]
0x18004bb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb17  test    eax, eax
0x18004bb19  jz      short loc_18004BB24
0x18004bb1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bb22  jmp     short loc_18004BB32
0x18004bb24  lea     rcx, qword_18006EB20; this
0x18004bb2b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bb32  cmp     [rcx+8], r15b
0x18004bb36  jz      short loc_18004BB5D
0x18004bb38  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bb3d  cmp     [rax+7CCh], ebx
0x18004bb43  jz      short loc_18004BB5D
0x18004bb45  mov     r9d, ebx; int
0x18004bb48  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18004bb4f  mov     r8d, 892h; int
0x18004bb55  mov     rcx, rax; this
0x18004bb58  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bb5d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004bb62  cmp     al, 1
0x18004bb64  jb      loc_18004BC16
0x18004bb6a  mov     edx, 0D6h
0x18004bb6f  jmp     loc_18004BA73
0x18004bb74  mov     ebx, [rsi+28h]
0x18004bb77  test    ebx, ebx
0x18004bb79  jns     loc_18004BC0A
0x18004bb7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bb86  test    rcx, rcx
0x18004bb89  jnz     short loc_18004BBCC
0x18004bb8b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bb91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bb98  mov     rcx, rax
0x18004bb9b  test    rax, rax
0x18004bb9e  jz      short loc_18004BBBE
0x18004bba0  mov     rax, [rax]
0x18004bba3  mov     edx, 7F0h
0x18004bba8  mov     rax, [rax+8]
0x18004bbac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbb1  test    eax, eax
0x18004bbb3  jz      short loc_18004BBBE
0x18004bbb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bbbc  jmp     short loc_18004BBCC
0x18004bbbe  lea     rcx, qword_18006EB20; this
0x18004bbc5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bbcc  cmp     [rcx+8], r15b
0x18004bbd0  jz      short loc_18004BBF7
0x18004bbd2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bbd7  cmp     [rax+7CCh], ebx
0x18004bbdd  jz      short loc_18004BBF7
0x18004bbdf  mov     r9d, ebx; int
0x18004bbe2  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18004bbe9  mov     r8d, 894h; int
0x18004bbef  mov     rcx, rax; this
0x18004bbf2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bbf7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004bbfc  cmp     al, 1
0x18004bbfe  jb      short loc_18004BC16
0x18004bc00  mov     edx, 0D7h
0x18004bc05  jmp     loc_18004BA73
0x18004bc0a  mov     rax, [rsi+18h]
0x18004bc0e  mov     [rsi+18h], r15
0x18004bc12  mov     [r12], rax
0x18004bc16  mov     rcx, rdi; lpCriticalSection
0x18004bc19  call    cs:__imp_LeaveCriticalSection
0x18004bc1f  lea     rcx, [rbp+3Fh+var_90]; this
0x18004bc23  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004bc28  lea     rcx, [rbp+3Fh+pvar]; pvar
0x18004bc2c  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18004bc31  lea     rcx, [rbp+3Fh+var_88]
0x18004bc35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bc3a  mov     eax, ebx
0x18004bc3c  mov     rcx, [rbp+3Fh+var_50]
0x18004bc40  xor     rcx, rsp; StackCookie
0x18004bc43  call    __security_check_cookie
0x18004bc48  add     rsp, 0A8h
0x18004bc4f  pop     r15
0x18004bc51  pop     r14
0x18004bc53  pop     r13
0x18004bc55  pop     r12
0x18004bc57  pop     rdi
0x18004bc58  pop     rsi
0x18004bc59  pop     rbx
0x18004bc5a  pop     rbp
0x18004bc5b  retn
```
