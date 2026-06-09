# CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(IMFSourceResolver *,IMFByteStream *,ushort const *,IPropertyStore *,ulong,IMFMediaSource * *)

- ea: `0x180069df0`
- end: `0x18006a2a3`
- name: `?CreateMediaSource@CMFSourceResolverOp@CMFVideoThumbnail@@QEAAJPEAUIMFSourceResolver@@PEAUIMFByteStream@@PEBGPEAUIPropertyStore@@KPEAPEAUIMFMediaSource@@@Z`
- size: `1203`
- prototype: `__int64 __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this, struct IMFSourceResolver *, struct IMFByteStream *, const unsigned __int16 *, struct IPropertyStore *, DWORD dwMilliseconds, struct IMFMediaSource **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180069134`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180069df0`
- `0x1800744d8`
- `0x1800746f8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069fa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a0df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069fa8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a0df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a0bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a259`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a0bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a259`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006a0ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006a0ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069efa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a011`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a125`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a1c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069efa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a011`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a125`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a1c5`

## string_xrefs

- `0x180069e2e`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x180069f57`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18006a06e`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18006a182`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18006a222`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`

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
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  HRESULT (__stdcall *BeginCreateObjectFromByteStream)(IMFSourceResolver *, IMFByteStream *, LPCWSTR, DWORD, IPropertyStore *, IUnknown **, IMFAsyncCallback *, IUnknown *); // rbx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  DWORD v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  struct IMFMediaSource *v39; // rax
  _BYTE v41[8]; // [rsp+50h] [rbp-51h] BYREF
  __int64 v42; // [rsp+58h] [rbp-49h] BYREF
  const unsigned __int16 *v43; // [rsp+60h] [rbp-41h]
  PROPVARIANT pvar; // [rsp+68h] [rbp-39h] BYREF
  _BYTE v45[16]; // [rsp+80h] [rbp-21h] BYREF

  v43 = a4;
  *a7 = 0;
  v42 = 0;
  memset(&pvar, 0, sizeof(pvar));
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v41,
    "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource",
    2168);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 11) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 296LL))(*((_QWORD *)this + 11));
    v12 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 11) + 280LL))(
                       *((_QWORD *)this + 11),
                       v45);
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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
    v14 = ((__int64 (__fastcall *)(struct IMFSourceResolver *, struct IMFByteStream *, const unsigned __int16 *, __int64, struct IPropertyStore *, __int64 *, char *, struct IMFSourceResolver *))BeginCreateObjectFromByteStream)(
            a2,
            a3,
            v43,
            66561,
            a5,
            &v42,
            (char *)this + 16,
            a2);
    if ( v14 < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != v14 )
          CallStackContext::TraceFailure(v26, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2178, v14);
      }
      if ( !g_wppLevels )
        goto LABEL_52;
      v27 = 213;
      goto LABEL_26;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v28 = WaitForSingleObject(*((HANDLE *)this + 4), dwMilliseconds);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( v28 == 258 )
    {
      v32 = v42;
      *((_BYTE *)this + 44) = 1;
      ((void (__fastcall *)(struct IMFSourceResolver *, __int64))a2->lpVtbl->CancelObjectCreation)(a2, v32);
    }
    else if ( !v28 )
    {
      v14 = *((_DWORD *)this + 10);
      if ( v14 >= 0 )
      {
        v39 = (struct IMFMediaSource *)*((_QWORD *)this + 3);
        *((_QWORD *)this + 3) = 0;
        *a7 = v39;
        goto LABEL_52;
      }
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != v14 )
          CallStackContext::TraceFailure(v38, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2196, v14);
      }
      if ( !g_wppLevels )
        goto LABEL_52;
      v27 = 215;
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v14);
LABEL_52:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      goto LABEL_53;
    }
    v33 = (__int64 *)CallStackTracing::s_wpInstance;
    v14 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( *((_DWORD *)v35 + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          v35,
          "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource",
          2194,
          -2147418113);
    }
    if ( !g_wppLevels )
      goto LABEL_52;
    v27 = 214;
    goto LABEL_26;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v15, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != v14 )
      CallStackContext::TraceFailure(v19, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2170, v14);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v14);
LABEL_53:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
  CMFPropVariant::Clear(&pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180069df0  push    rbp
0x180069df2  push    rbx
0x180069df3  push    rsi
0x180069df4  push    rdi
0x180069df5  push    r12
0x180069df7  push    r13
0x180069df9  push    r14
0x180069dfb  push    r15
0x180069dfd  lea     rbp, [rsp-7]
0x180069e02  sub     rsp, 0A8h
0x180069e09  mov     rax, cs:__security_cookie
0x180069e10  xor     rax, rsp
0x180069e13  mov     [rbp+3Fh+var_50], rax
0x180069e17  mov     r12, [rbp+3Fh+arg_30]
0x180069e1b  mov     r13, r8
0x180069e1e  mov     r15, [rbp+3Fh+arg_20]
0x180069e22  mov     r14, rdx
0x180069e25  mov     rsi, rcx
0x180069e28  mov     [rbp+3Fh+var_80], r9
0x180069e2c  xor     edi, edi
0x180069e2e  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180069e35  xorps   xmm0, xmm0
0x180069e38  mov     [r12], rdi
0x180069e3c  xor     eax, eax
0x180069e3e  mov     [rbp+3Fh+var_88], rdi
0x180069e42  mov     r8d, 878h; int
0x180069e48  mov     qword ptr [rbp+3Fh+pvar+10h], rax
0x180069e4c  lea     rcx, [rbp+3Fh+var_90]; this
0x180069e50  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x180069e54  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180069e59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180069e60  cmp     [rcx+8], dil
0x180069e64  jz      short loc_180069EB9
0x180069e66  cmp     [rsi+58h], rdi
0x180069e6a  jz      short loc_180069EB9
0x180069e6c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069e71  mov     rdx, [rsi+58h]
0x180069e75  mov     rdi, rax
0x180069e78  mov     rcx, [rdx]
0x180069e7b  mov     rax, [rcx+128h]
0x180069e82  mov     rcx, rdx
0x180069e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069e8a  mov     r8, [rsi+58h]
0x180069e8e  lea     rdx, [rbp+3Fh+var_60]
0x180069e92  mov     ebx, eax
0x180069e94  mov     rcx, [r8]
0x180069e97  mov     rax, [rcx+118h]
0x180069e9e  mov     rcx, r8
0x180069ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ea6  movups  xmm0, xmmword ptr [rax]
0x180069ea9  mov     [rdi+7E0h], ebx
0x180069eaf  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180069eb7  xor     edi, edi
0x180069eb9  mov     eax, 13h
0x180069ebe  mov     qword ptr [rbp+3Fh+pvar+8], 1
0x180069ec6  mov     word ptr [rbp+3Fh+pvar], ax
0x180069eca  lea     r8, [rbp+3Fh+pvar]
0x180069ece  mov     rax, [r15]
0x180069ed1  lea     rdx, MFPKEY_MediaSource_ThumbnailMode
0x180069ed8  mov     rcx, r15
0x180069edb  mov     rax, [rax+30h]
0x180069edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ee4  mov     ebx, eax
0x180069ee6  test    eax, eax
0x180069ee8  jns     loc_180069FA1
0x180069eee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069ef5  test    rcx, rcx
0x180069ef8  jnz     short loc_180069F41
0x180069efa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069f01  nop     dword ptr [rax+rax+00h]
0x180069f06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069f0d  mov     rcx, rax
0x180069f10  test    rax, rax
0x180069f13  jz      short loc_180069F33
0x180069f15  mov     rax, [rax]
0x180069f18  mov     edx, 7F0h
0x180069f1d  mov     rax, [rax+8]
0x180069f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f26  test    eax, eax
0x180069f28  jz      short loc_180069F33
0x180069f2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069f31  jmp     short loc_180069F41
0x180069f33  lea     rcx, qword_1800DBF70; this
0x180069f3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069f41  cmp     [rcx+8], dil
0x180069f45  jz      short loc_180069F6C
0x180069f47  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069f4c  cmp     [rax+7CCh], ebx
0x180069f52  jz      short loc_180069F6C
0x180069f54  mov     r9d, ebx; int
0x180069f57  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180069f5e  mov     r8d, 87Ah; int
0x180069f64  mov     rcx, rax; this
0x180069f67  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069f6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069f73  jb      loc_18006A265
0x180069f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180069f80  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180069f87  mov     edx, 0D4h
0x180069f8c  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180069f90  mov     r9, rsi
0x180069f93  mov     rcx, [rcx+10h]
0x180069f97  call    WPP_SF_qD
0x180069f9c  jmp     loc_18006A265
0x180069fa1  lea     rdi, [rsi+30h]
0x180069fa5  mov     rcx, rdi; lpCriticalSection
0x180069fa8  call    cs:__imp_EnterCriticalSection
0x180069faf  nop     dword ptr [rax+rax+00h]
0x180069fb4  mov     rax, [r14]
0x180069fb7  lea     rcx, [rbp+3Fh+var_88]
0x180069fbb  mov     rbx, [rax+38h]
0x180069fbf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180069fc4  mov     r8, [rbp+3Fh+var_80]
0x180069fc8  lea     rcx, [rsi+10h]
0x180069fcc  mov     [rsp+0E0h+var_A8], r14
0x180069fd1  lea     rax, [rbp+3Fh+var_88]
0x180069fd5  mov     [rsp+0E0h+var_B0], rcx
0x180069fda  mov     r9d, 10401h
0x180069fe0  mov     [rsp+0E0h+var_B8], rax
0x180069fe5  mov     rdx, r13
0x180069fe8  mov     rax, rbx
0x180069feb  mov     [rsp+0E0h+var_C0], r15
0x180069ff0  mov     rcx, r14
0x180069ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ff8  xor     r15d, r15d
0x180069ffb  mov     ebx, eax
0x180069ffd  test    eax, eax
0x180069fff  jns     loc_18006A0B8
0x18006a005  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a00c  test    rcx, rcx
0x18006a00f  jnz     short loc_18006A058
0x18006a011  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a018  nop     dword ptr [rax+rax+00h]
0x18006a01d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a024  mov     rcx, rax
0x18006a027  test    rax, rax
0x18006a02a  jz      short loc_18006A04A
0x18006a02c  mov     rax, [rax]
0x18006a02f  mov     edx, 7F0h
0x18006a034  mov     rax, [rax+8]
0x18006a038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a03d  test    eax, eax
0x18006a03f  jz      short loc_18006A04A
0x18006a041  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a048  jmp     short loc_18006A058
0x18006a04a  lea     rcx, qword_1800DBF70; this
0x18006a051  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a058  cmp     [rcx+8], r15b
0x18006a05c  jz      short loc_18006A083
0x18006a05e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a063  cmp     [rax+7CCh], ebx
0x18006a069  jz      short loc_18006A083
0x18006a06b  mov     r9d, ebx; int
0x18006a06e  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006a075  mov     r8d, 882h; int
0x18006a07b  mov     rcx, rax; this
0x18006a07e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a083  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a08a  jb      loc_18006A256
0x18006a090  mov     edx, 0D5h
0x18006a095  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a09c  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006a0a3  mov     r9, rsi
0x18006a0a6  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18006a0aa  mov     rcx, [rcx+10h]
0x18006a0ae  call    WPP_SF_qD
0x18006a0b3  jmp     loc_18006A256
0x18006a0b8  mov     rcx, rdi; lpCriticalSection
0x18006a0bb  call    cs:__imp_LeaveCriticalSection
0x18006a0c2  nop     dword ptr [rax+rax+00h]
0x18006a0c7  mov     edx, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x18006a0ca  mov     rcx, [rsi+20h]; hHandle
0x18006a0ce  call    cs:__imp_WaitForSingleObject
0x18006a0d5  nop     dword ptr [rax+rax+00h]
0x18006a0da  mov     rcx, rdi; lpCriticalSection
0x18006a0dd  mov     ebx, eax
0x18006a0df  call    cs:__imp_EnterCriticalSection
0x18006a0e6  nop     dword ptr [rax+rax+00h]
0x18006a0eb  cmp     ebx, 102h
0x18006a0f1  jnz     short loc_18006A10C
0x18006a0f3  mov     rdx, [rbp+3Fh+var_88]
0x18006a0f7  mov     rcx, r14
0x18006a0fa  mov     byte ptr [rsi+2Ch], 1
0x18006a0fe  mov     rax, [r14]
0x18006a101  mov     rax, [rax+48h]
0x18006a105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a10a  jmp     short loc_18006A114
0x18006a10c  test    ebx, ebx
0x18006a10e  jz      loc_18006A1AE
0x18006a114  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a11b  mov     ebx, 8000FFFFh
0x18006a120  test    rcx, rcx
0x18006a123  jnz     short loc_18006A16C
0x18006a125  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a12c  nop     dword ptr [rax+rax+00h]
0x18006a131  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a138  mov     rcx, rax
0x18006a13b  test    rax, rax
0x18006a13e  jz      short loc_18006A15E
0x18006a140  mov     rax, [rax]
0x18006a143  mov     edx, 7F0h
0x18006a148  mov     rax, [rax+8]
0x18006a14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a151  test    eax, eax
0x18006a153  jz      short loc_18006A15E
0x18006a155  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a15c  jmp     short loc_18006A16C
0x18006a15e  lea     rcx, qword_1800DBF70; this
0x18006a165  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a16c  cmp     [rcx+8], r15b
0x18006a170  jz      short loc_18006A197
0x18006a172  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a177  cmp     [rax+7CCh], ebx
0x18006a17d  jz      short loc_18006A197
0x18006a17f  mov     r9d, ebx; int
0x18006a182  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006a189  mov     r8d, 892h; int
0x18006a18f  mov     rcx, rax; this
0x18006a192  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a197  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a19e  jb      loc_18006A256
0x18006a1a4  mov     edx, 0D6h
0x18006a1a9  jmp     loc_18006A095
0x18006a1ae  mov     ebx, [rsi+28h]
0x18006a1b1  test    ebx, ebx
0x18006a1b3  jns     loc_18006A24A
0x18006a1b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a1c0  test    rcx, rcx
0x18006a1c3  jnz     short loc_18006A20C
0x18006a1c5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a1cc  nop     dword ptr [rax+rax+00h]
0x18006a1d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a1d8  mov     rcx, rax
0x18006a1db  test    rax, rax
0x18006a1de  jz      short loc_18006A1FE
0x18006a1e0  mov     rax, [rax]
0x18006a1e3  mov     edx, 7F0h
0x18006a1e8  mov     rax, [rax+8]
0x18006a1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1f1  test    eax, eax
0x18006a1f3  jz      short loc_18006A1FE
0x18006a1f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a1fc  jmp     short loc_18006A20C
0x18006a1fe  lea     rcx, qword_1800DBF70; this
0x18006a205  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a20c  cmp     [rcx+8], r15b
0x18006a210  jz      short loc_18006A237
0x18006a212  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a217  cmp     [rax+7CCh], ebx
0x18006a21d  jz      short loc_18006A237
0x18006a21f  mov     r9d, ebx; int
0x18006a222  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006a229  mov     r8d, 894h; int
0x18006a22f  mov     rcx, rax; this
0x18006a232  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a237  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a23e  jb      short loc_18006A256
0x18006a240  mov     edx, 0D7h
0x18006a245  jmp     loc_18006A095
0x18006a24a  mov     rax, [rsi+18h]
0x18006a24e  mov     [rsi+18h], r15
0x18006a252  mov     [r12], rax
0x18006a256  mov     rcx, rdi; lpCriticalSection
0x18006a259  call    cs:__imp_LeaveCriticalSection
0x18006a260  nop     dword ptr [rax+rax+00h]
0x18006a265  lea     rcx, [rbp+3Fh+var_90]; this
0x18006a269  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006a26e  lea     rcx, [rbp+3Fh+pvar]; pvar
0x18006a272  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18006a277  lea     rcx, [rbp+3Fh+var_88]
0x18006a27b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a280  mov     eax, ebx
0x18006a282  mov     rcx, [rbp+3Fh+var_50]
0x18006a286  xor     rcx, rsp; StackCookie
0x18006a289  call    __security_check_cookie
0x18006a28e  add     rsp, 0A8h
0x18006a295  pop     r15
0x18006a297  pop     r14
0x18006a299  pop     r13
0x18006a29b  pop     r12
0x18006a29d  pop     rdi
0x18006a29e  pop     rsi
0x18006a29f  pop     rbx
0x18006a2a0  pop     rbp
0x18006a2a1  retn
```
