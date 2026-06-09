# CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(IMFSourceResolver *,IMFByteStream *,ushort const *,IPropertyStore *,ulong,IMFMediaSource * *)

- ea: `0x1800671c8`
- end: `0x180067644`
- name: `?CreateMediaSource@CMFSourceResolverOp@CMFVideoThumbnail@@QEAAJPEAUIMFSourceResolver@@PEAUIMFByteStream@@PEBGPEAUIPropertyStore@@KPEAPEAUIMFMediaSource@@@Z`
- size: `1148`
- prototype: `__int64 __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this, struct IMFSourceResolver *, struct IMFByteStream *, const unsigned __int16 *, struct IPropertyStore *, DWORD dwMilliseconds, struct IMFMediaSource **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180066500`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800671c8`
- `0x180071330`
- `0x180071524`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006737a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067499`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006737a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067499`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067481`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067601`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067481`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067601`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006748e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006748e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800672d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800673dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800674d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067573`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800672d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800673dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800674d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067573`

## string_xrefs

- `0x180067206`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x180067329`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x180067434`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x180067530`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x1800675ca`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`

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
          v24 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v36 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v33 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v17 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800671c8  push    rbp
0x1800671ca  push    rbx
0x1800671cb  push    rsi
0x1800671cc  push    rdi
0x1800671cd  push    r12
0x1800671cf  push    r13
0x1800671d1  push    r14
0x1800671d3  push    r15
0x1800671d5  lea     rbp, [rsp-7]
0x1800671da  sub     rsp, 0A8h
0x1800671e1  mov     rax, cs:__security_cookie
0x1800671e8  xor     rax, rsp
0x1800671eb  mov     [rbp+3Fh+var_50], rax
0x1800671ef  mov     r12, [rbp+3Fh+arg_30]
0x1800671f3  mov     r13, r8
0x1800671f6  mov     r15, [rbp+3Fh+arg_20]
0x1800671fa  mov     r14, rdx
0x1800671fd  mov     rsi, rcx
0x180067200  mov     [rbp+3Fh+var_80], r9
0x180067204  xor     edi, edi
0x180067206  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006720d  xorps   xmm0, xmm0
0x180067210  mov     [r12], rdi
0x180067214  xor     eax, eax
0x180067216  mov     [rbp+3Fh+var_88], rdi
0x18006721a  mov     r8d, 878h; int
0x180067220  mov     qword ptr [rbp+3Fh+pvar+10h], rax
0x180067224  lea     rcx, [rbp+3Fh+var_90]; this
0x180067228  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x18006722c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067231  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180067238  cmp     [rcx+8], dil
0x18006723c  jz      short loc_180067291
0x18006723e  cmp     [rsi+58h], rdi
0x180067242  jz      short loc_180067291
0x180067244  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067249  mov     rdx, [rsi+58h]
0x18006724d  mov     rdi, rax
0x180067250  mov     rcx, [rdx]
0x180067253  mov     rax, [rcx+128h]
0x18006725a  mov     rcx, rdx
0x18006725d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067262  mov     r8, [rsi+58h]
0x180067266  lea     rdx, [rbp+3Fh+var_60]
0x18006726a  mov     ebx, eax
0x18006726c  mov     rcx, [r8]
0x18006726f  mov     rax, [rcx+118h]
0x180067276  mov     rcx, r8
0x180067279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006727e  movups  xmm0, xmmword ptr [rax]
0x180067281  mov     [rdi+7E0h], ebx
0x180067287  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006728f  xor     edi, edi
0x180067291  mov     eax, 13h
0x180067296  mov     qword ptr [rbp+3Fh+pvar+8], 1
0x18006729e  mov     word ptr [rbp+3Fh+pvar], ax
0x1800672a2  lea     r8, [rbp+3Fh+pvar]
0x1800672a6  mov     rax, [r15]
0x1800672a9  lea     rdx, MFPKEY_MediaSource_ThumbnailMode
0x1800672b0  mov     rcx, r15
0x1800672b3  mov     rax, [rax+30h]
0x1800672b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672bc  mov     ebx, eax
0x1800672be  test    eax, eax
0x1800672c0  jns     loc_180067373
0x1800672c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800672cd  test    rcx, rcx
0x1800672d0  jnz     short loc_180067313
0x1800672d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800672d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800672df  mov     rcx, rax
0x1800672e2  test    rax, rax
0x1800672e5  jz      short loc_180067305
0x1800672e7  mov     rax, [rax]
0x1800672ea  mov     edx, 7F0h
0x1800672ef  mov     rax, [rax+8]
0x1800672f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672f8  test    eax, eax
0x1800672fa  jz      short loc_180067305
0x1800672fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067303  jmp     short loc_180067313
0x180067305  lea     rcx, qword_1800D6F70; this
0x18006730c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067313  cmp     [rcx+8], dil
0x180067317  jz      short loc_18006733E
0x180067319  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006731e  cmp     [rax+7CCh], ebx
0x180067324  jz      short loc_18006733E
0x180067326  mov     r9d, ebx; int
0x180067329  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180067330  mov     r8d, 87Ah; int
0x180067336  mov     rcx, rax; this
0x180067339  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006733e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067345  jb      loc_180067607
0x18006734b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067352  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180067359  mov     edx, 0D4h
0x18006735e  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180067362  mov     r9, rsi
0x180067365  mov     rcx, [rcx+10h]
0x180067369  call    WPP_SF_qD
0x18006736e  jmp     loc_180067607
0x180067373  lea     rdi, [rsi+30h]
0x180067377  mov     rcx, rdi; lpCriticalSection
0x18006737a  call    cs:__imp_EnterCriticalSection
0x180067380  mov     rax, [r14]
0x180067383  lea     rcx, [rbp+3Fh+var_88]
0x180067387  mov     rbx, [rax+38h]
0x18006738b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067390  mov     r8, [rbp+3Fh+var_80]
0x180067394  lea     rcx, [rsi+10h]
0x180067398  mov     [rsp+0E0h+var_A8], r14
0x18006739d  lea     rax, [rbp+3Fh+var_88]
0x1800673a1  mov     [rsp+0E0h+var_B0], rcx
0x1800673a6  mov     r9d, 10401h
0x1800673ac  mov     [rsp+0E0h+var_B8], rax
0x1800673b1  mov     rdx, r13
0x1800673b4  mov     rax, rbx
0x1800673b7  mov     [rsp+0E0h+var_C0], r15
0x1800673bc  mov     rcx, r14
0x1800673bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800673c4  xor     r15d, r15d
0x1800673c7  mov     ebx, eax
0x1800673c9  test    eax, eax
0x1800673cb  jns     loc_18006747E
0x1800673d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800673d8  test    rcx, rcx
0x1800673db  jnz     short loc_18006741E
0x1800673dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800673e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800673ea  mov     rcx, rax
0x1800673ed  test    rax, rax
0x1800673f0  jz      short loc_180067410
0x1800673f2  mov     rax, [rax]
0x1800673f5  mov     edx, 7F0h
0x1800673fa  mov     rax, [rax+8]
0x1800673fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067403  test    eax, eax
0x180067405  jz      short loc_180067410
0x180067407  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006740e  jmp     short loc_18006741E
0x180067410  lea     rcx, qword_1800D6F70; this
0x180067417  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006741e  cmp     [rcx+8], r15b
0x180067422  jz      short loc_180067449
0x180067424  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067429  cmp     [rax+7CCh], ebx
0x18006742f  jz      short loc_180067449
0x180067431  mov     r9d, ebx; int
0x180067434  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18006743b  mov     r8d, 882h; int
0x180067441  mov     rcx, rax; this
0x180067444  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067449  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067450  jb      loc_1800675FE
0x180067456  mov     edx, 0D5h
0x18006745b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067462  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180067469  mov     r9, rsi
0x18006746c  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180067470  mov     rcx, [rcx+10h]
0x180067474  call    WPP_SF_qD
0x180067479  jmp     loc_1800675FE
0x18006747e  mov     rcx, rdi; lpCriticalSection
0x180067481  call    cs:__imp_LeaveCriticalSection
0x180067487  mov     edx, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x18006748a  mov     rcx, [rsi+20h]; hHandle
0x18006748e  call    cs:__imp_WaitForSingleObject
0x180067494  mov     rcx, rdi; lpCriticalSection
0x180067497  mov     ebx, eax
0x180067499  call    cs:__imp_EnterCriticalSection
0x18006749f  cmp     ebx, 102h
0x1800674a5  jnz     short loc_1800674C0
0x1800674a7  mov     rdx, [rbp+3Fh+var_88]
0x1800674ab  mov     rcx, r14
0x1800674ae  mov     byte ptr [rsi+2Ch], 1
0x1800674b2  mov     rax, [r14]
0x1800674b5  mov     rax, [rax+48h]
0x1800674b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674be  jmp     short loc_1800674C8
0x1800674c0  test    ebx, ebx
0x1800674c2  jz      loc_18006755C
0x1800674c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800674cf  mov     ebx, 8000FFFFh
0x1800674d4  test    rcx, rcx
0x1800674d7  jnz     short loc_18006751A
0x1800674d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800674df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800674e6  mov     rcx, rax
0x1800674e9  test    rax, rax
0x1800674ec  jz      short loc_18006750C
0x1800674ee  mov     rax, [rax]
0x1800674f1  mov     edx, 7F0h
0x1800674f6  mov     rax, [rax+8]
0x1800674fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674ff  test    eax, eax
0x180067501  jz      short loc_18006750C
0x180067503  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006750a  jmp     short loc_18006751A
0x18006750c  lea     rcx, qword_1800D6F70; this
0x180067513  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006751a  cmp     [rcx+8], r15b
0x18006751e  jz      short loc_180067545
0x180067520  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067525  cmp     [rax+7CCh], ebx
0x18006752b  jz      short loc_180067545
0x18006752d  mov     r9d, ebx; int
0x180067530  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180067537  mov     r8d, 892h; int
0x18006753d  mov     rcx, rax; this
0x180067540  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067545  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006754c  jb      loc_1800675FE
0x180067552  mov     edx, 0D6h
0x180067557  jmp     loc_18006745B
0x18006755c  mov     ebx, [rsi+28h]
0x18006755f  test    ebx, ebx
0x180067561  jns     loc_1800675F2
0x180067567  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006756e  test    rcx, rcx
0x180067571  jnz     short loc_1800675B4
0x180067573  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067579  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067580  mov     rcx, rax
0x180067583  test    rax, rax
0x180067586  jz      short loc_1800675A6
0x180067588  mov     rax, [rax]
0x18006758b  mov     edx, 7F0h
0x180067590  mov     rax, [rax+8]
0x180067594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067599  test    eax, eax
0x18006759b  jz      short loc_1800675A6
0x18006759d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800675a4  jmp     short loc_1800675B4
0x1800675a6  lea     rcx, qword_1800D6F70; this
0x1800675ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800675b4  cmp     [rcx+8], r15b
0x1800675b8  jz      short loc_1800675DF
0x1800675ba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800675bf  cmp     [rax+7CCh], ebx
0x1800675c5  jz      short loc_1800675DF
0x1800675c7  mov     r9d, ebx; int
0x1800675ca  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x1800675d1  mov     r8d, 894h; int
0x1800675d7  mov     rcx, rax; this
0x1800675da  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800675df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800675e6  jb      short loc_1800675FE
0x1800675e8  mov     edx, 0D7h
0x1800675ed  jmp     loc_18006745B
0x1800675f2  mov     rax, [rsi+18h]
0x1800675f6  mov     [rsi+18h], r15
0x1800675fa  mov     [r12], rax
0x1800675fe  mov     rcx, rdi; lpCriticalSection
0x180067601  call    cs:__imp_LeaveCriticalSection
0x180067607  lea     rcx, [rbp+3Fh+var_90]; this
0x18006760b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067610  lea     rcx, [rbp+3Fh+pvar]; pvar
0x180067614  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180067619  lea     rcx, [rbp+3Fh+var_88]
0x18006761d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067622  mov     eax, ebx
0x180067624  mov     rcx, [rbp+3Fh+var_50]
0x180067628  xor     rcx, rsp; StackCookie
0x18006762b  call    __security_check_cookie
0x180067630  add     rsp, 0A8h
0x180067637  pop     r15
0x180067639  pop     r14
0x18006763b  pop     r13
0x18006763d  pop     r12
0x18006763f  pop     rdi
0x180067640  pop     rsi
0x180067641  pop     rbx
0x180067642  pop     rbp
0x180067643  retn
```
