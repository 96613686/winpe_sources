# CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(IMFSourceResolver *,IMFByteStream *,ushort const *,IPropertyStore *,ulong,IMFMediaSource * *)

- ea: `0x18009a9a4`
- end: `0x18009ae20`
- name: `?CreateMediaSource@CMFSourceResolverOp@CMFVideoThumbnail@@QEAAJPEAUIMFSourceResolver@@PEAUIMFByteStream@@PEBGPEAUIPropertyStore@@KPEAPEAUIMFMediaSource@@@Z`
- size: `1148`
- prototype: `__int64 __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this, struct IMFSourceResolver *, struct IMFByteStream *, const unsigned __int16 *, struct IPropertyStore *, DWORD dwMilliseconds, struct IMFMediaSource **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800afff8`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180025548`
- `0x1800734a8`
- `0x180073b14`
- `0x18009a9a4`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009ac6a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009ac6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ac5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009addd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ac5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009addd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ab56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ac75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ab56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ac75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009aaae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009abb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009acb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ad4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009aaae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009abb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009acb5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ad4f`

## string_xrefs

- `0x18009a9e2`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18009ab05`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18009ac10`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18009ad0c`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x18009ada6`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`

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
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  HRESULT (__stdcall *BeginCreateObjectFromByteStream)(IMFSourceResolver *, IMFByteStream *, LPCWSTR, DWORD, IPropertyStore *, IUnknown **, IMFAsyncCallback *, IUnknown *); // rbx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  DWORD v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  struct IMFMediaSource *v39; // rax
  _BYTE v41[8]; // [rsp+50h] [rbp-51h] BYREF
  __int64 v42; // [rsp+58h] [rbp-49h] BYREF
  const unsigned __int16 *v43; // [rsp+60h] [rbp-41h]
  PROPVARIANT v44; // [rsp+68h] [rbp-39h] BYREF
  _BYTE v45[16]; // [rsp+80h] [rbp-21h] BYREF

  v43 = a4;
  *a7 = 0;
  v42 = 0;
  memset(&v44, 0, sizeof(v44));
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
  v44.hVal.QuadPart = 1;
  v44.vt = 19;
  v14 = ((__int64 (__fastcall *)(struct IPropertyStore *, void *, PROPVARIANT *))a5->lpVtbl->SetValue)(
          a5,
          &MFPKEY_MediaSource_ThumbnailMode,
          &v44);
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
      v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
  v17 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v15, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
  CMFPropVariant::Clear(&v44);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18009a9a4  push    rbp
0x18009a9a6  push    rbx
0x18009a9a7  push    rsi
0x18009a9a8  push    rdi
0x18009a9a9  push    r12
0x18009a9ab  push    r13
0x18009a9ad  push    r14
0x18009a9af  push    r15
0x18009a9b1  lea     rbp, [rsp-7]
0x18009a9b6  sub     rsp, 0A8h
0x18009a9bd  mov     rax, cs:__security_cookie
0x18009a9c4  xor     rax, rsp
0x18009a9c7  mov     [rbp+3Fh+var_50], rax
0x18009a9cb  mov     r12, [rbp+3Fh+arg_30]
0x18009a9cf  mov     r13, r8
0x18009a9d2  mov     r15, [rbp+3Fh+arg_20]
0x18009a9d6  mov     r14, rdx
0x18009a9d9  mov     rsi, rcx
0x18009a9dc  mov     [rbp+3Fh+var_80], r9
0x18009a9e0  xor     edi, edi
0x18009a9e2  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18009a9e9  xorps   xmm0, xmm0
0x18009a9ec  mov     [r12], rdi
0x18009a9f0  xor     eax, eax
0x18009a9f2  mov     [rbp+3Fh+var_88], rdi
0x18009a9f6  mov     r8d, 878h; int
0x18009a9fc  mov     [rbp+3Fh+var_68], rax
0x18009aa00  lea     rcx, [rbp+3Fh+var_90]; this
0x18009aa04  movups  [rbp+3Fh+var_78], xmm0
0x18009aa08  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009aa0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009aa14  cmp     [rcx+8], dil
0x18009aa18  jz      short loc_18009AA6D
0x18009aa1a  cmp     [rsi+58h], rdi
0x18009aa1e  jz      short loc_18009AA6D
0x18009aa20  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009aa25  mov     rdx, [rsi+58h]
0x18009aa29  mov     rdi, rax
0x18009aa2c  mov     rcx, [rdx]
0x18009aa2f  mov     rax, [rcx+128h]
0x18009aa36  mov     rcx, rdx
0x18009aa39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa3e  mov     r8, [rsi+58h]
0x18009aa42  lea     rdx, [rbp+3Fh+var_60]
0x18009aa46  mov     ebx, eax
0x18009aa48  mov     rcx, [r8]
0x18009aa4b  mov     rax, [rcx+118h]
0x18009aa52  mov     rcx, r8
0x18009aa55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa5a  movups  xmm0, xmmword ptr [rax]
0x18009aa5d  mov     [rdi+7E0h], ebx
0x18009aa63  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18009aa6b  xor     edi, edi
0x18009aa6d  mov     eax, 13h
0x18009aa72  mov     qword ptr [rbp+3Fh+var_78+8], 1
0x18009aa7a  mov     word ptr [rbp+3Fh+var_78], ax
0x18009aa7e  lea     r8, [rbp+3Fh+var_78]
0x18009aa82  mov     rax, [r15]
0x18009aa85  lea     rdx, MFPKEY_MediaSource_ThumbnailMode
0x18009aa8c  mov     rcx, r15
0x18009aa8f  mov     rax, [rax+30h]
0x18009aa93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aa98  mov     ebx, eax
0x18009aa9a  test    eax, eax
0x18009aa9c  jns     loc_18009AB4F
0x18009aaa2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009aaa9  test    rcx, rcx
0x18009aaac  jnz     short loc_18009AAEF
0x18009aaae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009aab4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009aabb  mov     rcx, rax
0x18009aabe  test    rax, rax
0x18009aac1  jz      short loc_18009AAE1
0x18009aac3  mov     rax, [rax]
0x18009aac6  mov     edx, 7F0h
0x18009aacb  mov     rax, [rax+8]
0x18009aacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aad4  test    eax, eax
0x18009aad6  jz      short loc_18009AAE1
0x18009aad8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009aadf  jmp     short loc_18009AAEF
0x18009aae1  lea     rcx, qword_1801B07E0; this
0x18009aae8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009aaef  cmp     [rcx+8], dil
0x18009aaf3  jz      short loc_18009AB1A
0x18009aaf5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009aafa  cmp     [rax+7CCh], ebx
0x18009ab00  jz      short loc_18009AB1A
0x18009ab02  mov     r9d, ebx; int
0x18009ab05  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18009ab0c  mov     r8d, 87Ah; int
0x18009ab12  mov     rcx, rax; this
0x18009ab15  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009ab1a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009ab21  jb      loc_18009ADE3
0x18009ab27  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ab2e  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18009ab35  mov     edx, 0D4h
0x18009ab3a  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18009ab3e  mov     r9, rsi
0x18009ab41  mov     rcx, [rcx+10h]
0x18009ab45  call    WPP_SF_qD
0x18009ab4a  jmp     loc_18009ADE3
0x18009ab4f  lea     rdi, [rsi+30h]
0x18009ab53  mov     rcx, rdi; lpCriticalSection
0x18009ab56  call    cs:__imp_EnterCriticalSection
0x18009ab5c  mov     rax, [r14]
0x18009ab5f  lea     rcx, [rbp+3Fh+var_88]
0x18009ab63  mov     rbx, [rax+38h]
0x18009ab67  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009ab6c  mov     r8, [rbp+3Fh+var_80]
0x18009ab70  lea     rcx, [rsi+10h]
0x18009ab74  mov     [rsp+0E0h+var_A8], r14
0x18009ab79  lea     rax, [rbp+3Fh+var_88]
0x18009ab7d  mov     [rsp+0E0h+var_B0], rcx
0x18009ab82  mov     r9d, 10401h
0x18009ab88  mov     [rsp+0E0h+var_B8], rax
0x18009ab8d  mov     rdx, r13
0x18009ab90  mov     rax, rbx
0x18009ab93  mov     [rsp+0E0h+var_C0], r15
0x18009ab98  mov     rcx, r14
0x18009ab9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aba0  xor     r15d, r15d
0x18009aba3  mov     ebx, eax
0x18009aba5  test    eax, eax
0x18009aba7  jns     loc_18009AC5A
0x18009abad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009abb4  test    rcx, rcx
0x18009abb7  jnz     short loc_18009ABFA
0x18009abb9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009abbf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009abc6  mov     rcx, rax
0x18009abc9  test    rax, rax
0x18009abcc  jz      short loc_18009ABEC
0x18009abce  mov     rax, [rax]
0x18009abd1  mov     edx, 7F0h
0x18009abd6  mov     rax, [rax+8]
0x18009abda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009abdf  test    eax, eax
0x18009abe1  jz      short loc_18009ABEC
0x18009abe3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009abea  jmp     short loc_18009ABFA
0x18009abec  lea     rcx, qword_1801B07E0; this
0x18009abf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009abfa  cmp     [rcx+8], r15b
0x18009abfe  jz      short loc_18009AC25
0x18009ac00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009ac05  cmp     [rax+7CCh], ebx
0x18009ac0b  jz      short loc_18009AC25
0x18009ac0d  mov     r9d, ebx; int
0x18009ac10  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18009ac17  mov     r8d, 882h; int
0x18009ac1d  mov     rcx, rax; this
0x18009ac20  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009ac25  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009ac2c  jb      loc_18009ADDA
0x18009ac32  mov     edx, 0D5h
0x18009ac37  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ac3e  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18009ac45  mov     r9, rsi
0x18009ac48  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18009ac4c  mov     rcx, [rcx+10h]
0x18009ac50  call    WPP_SF_qD
0x18009ac55  jmp     loc_18009ADDA
0x18009ac5a  mov     rcx, rdi; lpCriticalSection
0x18009ac5d  call    cs:__imp_LeaveCriticalSection
0x18009ac63  mov     edx, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x18009ac66  mov     rcx, [rsi+20h]; hHandle
0x18009ac6a  call    cs:__imp_WaitForSingleObject
0x18009ac70  mov     rcx, rdi; lpCriticalSection
0x18009ac73  mov     ebx, eax
0x18009ac75  call    cs:__imp_EnterCriticalSection
0x18009ac7b  cmp     ebx, 102h
0x18009ac81  jnz     short loc_18009AC9C
0x18009ac83  mov     rdx, [rbp+3Fh+var_88]
0x18009ac87  mov     rcx, r14
0x18009ac8a  mov     byte ptr [rsi+2Ch], 1
0x18009ac8e  mov     rax, [r14]
0x18009ac91  mov     rax, [rax+48h]
0x18009ac95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ac9a  jmp     short loc_18009ACA4
0x18009ac9c  test    ebx, ebx
0x18009ac9e  jz      loc_18009AD38
0x18009aca4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009acab  mov     ebx, 8000FFFFh
0x18009acb0  test    rcx, rcx
0x18009acb3  jnz     short loc_18009ACF6
0x18009acb5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009acbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009acc2  mov     rcx, rax
0x18009acc5  test    rax, rax
0x18009acc8  jz      short loc_18009ACE8
0x18009acca  mov     rax, [rax]
0x18009accd  mov     edx, 7F0h
0x18009acd2  mov     rax, [rax+8]
0x18009acd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009acdb  test    eax, eax
0x18009acdd  jz      short loc_18009ACE8
0x18009acdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ace6  jmp     short loc_18009ACF6
0x18009ace8  lea     rcx, qword_1801B07E0; this
0x18009acef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009acf6  cmp     [rcx+8], r15b
0x18009acfa  jz      short loc_18009AD21
0x18009acfc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009ad01  cmp     [rax+7CCh], ebx
0x18009ad07  jz      short loc_18009AD21
0x18009ad09  mov     r9d, ebx; int
0x18009ad0c  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18009ad13  mov     r8d, 892h; int
0x18009ad19  mov     rcx, rax; this
0x18009ad1c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009ad21  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009ad28  jb      loc_18009ADDA
0x18009ad2e  mov     edx, 0D6h
0x18009ad33  jmp     loc_18009AC37
0x18009ad38  mov     ebx, [rsi+28h]
0x18009ad3b  test    ebx, ebx
0x18009ad3d  jns     loc_18009ADCE
0x18009ad43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ad4a  test    rcx, rcx
0x18009ad4d  jnz     short loc_18009AD90
0x18009ad4f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009ad55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ad5c  mov     rcx, rax
0x18009ad5f  test    rax, rax
0x18009ad62  jz      short loc_18009AD82
0x18009ad64  mov     rax, [rax]
0x18009ad67  mov     edx, 7F0h
0x18009ad6c  mov     rax, [rax+8]
0x18009ad70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ad75  test    eax, eax
0x18009ad77  jz      short loc_18009AD82
0x18009ad79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ad80  jmp     short loc_18009AD90
0x18009ad82  lea     rcx, qword_1801B07E0; this
0x18009ad89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ad90  cmp     [rcx+8], r15b
0x18009ad94  jz      short loc_18009ADBB
0x18009ad96  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009ad9b  cmp     [rax+7CCh], ebx
0x18009ada1  jz      short loc_18009ADBB
0x18009ada3  mov     r9d, ebx; int
0x18009ada6  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18009adad  mov     r8d, 894h; int
0x18009adb3  mov     rcx, rax; this
0x18009adb6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009adbb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009adc2  jb      short loc_18009ADDA
0x18009adc4  mov     edx, 0D7h
0x18009adc9  jmp     loc_18009AC37
0x18009adce  mov     rax, [rsi+18h]
0x18009add2  mov     [rsi+18h], r15
0x18009add6  mov     [r12], rax
0x18009adda  mov     rcx, rdi; lpCriticalSection
0x18009addd  call    cs:__imp_LeaveCriticalSection
0x18009ade3  lea     rcx, [rbp+3Fh+var_90]; this
0x18009ade7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009adec  lea     rcx, [rbp+3Fh+var_78]; this
0x18009adf0  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x18009adf5  lea     rcx, [rbp+3Fh+var_88]
0x18009adf9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009adfe  mov     eax, ebx
0x18009ae00  mov     rcx, [rbp+3Fh+var_50]
0x18009ae04  xor     rcx, rsp; StackCookie
0x18009ae07  call    __security_check_cookie
0x18009ae0c  add     rsp, 0A8h
0x18009ae13  pop     r15
0x18009ae15  pop     r14
0x18009ae17  pop     r13
0x18009ae19  pop     r12
0x18009ae1b  pop     rdi
0x18009ae1c  pop     rsi
0x18009ae1d  pop     rbx
0x18009ae1e  pop     rbp
0x18009ae1f  retn
```
