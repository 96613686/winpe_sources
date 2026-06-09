# CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource(IMFSourceResolver *,IMFByteStream *,ushort const *,IPropertyStore *,ulong,IMFMediaSource * *)

- ea: `0x1800a0034`
- end: `0x1800a04e7`
- name: `?CreateMediaSource@CMFSourceResolverOp@CMFVideoThumbnail@@QEAAJPEAUIMFSourceResolver@@PEAUIMFByteStream@@PEBGPEAUIPropertyStore@@KPEAPEAUIMFMediaSource@@@Z`
- size: `1203`
- prototype: `__int64 __fastcall(CMFVideoThumbnail::CMFSourceResolverOp *__hidden this, struct IMFSourceResolver *, struct IMFByteStream *, const unsigned __int16 *, struct IPropertyStore *, DWORD dwMilliseconds, struct IMFMediaSource **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800b554c`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x1800790a8`
- `0x180079680`
- `0x1800a0034`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a0312`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a0312`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a02ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a049d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a02ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a049d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a01ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a0323`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a01ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a0323`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a013e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0255`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0369`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0409`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a013e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0255`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0369`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a0409`

## string_xrefs

- `0x1800a0072`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x1800a019b`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x1800a02b2`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x1800a03c6`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`
- `0x1800a0466`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource`

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
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  HRESULT (__stdcall *BeginCreateObjectFromByteStream)(IMFSourceResolver *, IMFByteStream *, LPCWSTR, DWORD, IPropertyStore *, IUnknown **, IMFAsyncCallback *, IUnknown *); // rbx
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  DWORD v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  wchar_t *v30; // rcx
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
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != v14 )
          CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2178, v14);
      }
      if ( !g_wppLevels )
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
      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v32 + 499) != v14 )
          CallStackContext::TraceFailure(v32, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2196, v14);
      }
      if ( !g_wppLevels )
        goto LABEL_52;
      v23 = 215;
LABEL_26:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v14);
LABEL_52:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      goto LABEL_53;
    }
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    v14 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
    if ( !g_wppLevels )
      goto LABEL_52;
    v23 = 214;
    goto LABEL_26;
  }
  v15 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != v14 )
      CallStackContext::TraceFailure(v17, "CMFVideoThumbnail::CMFSourceResolverOp::CreateMediaSource", 2170, v14);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v14);
LABEL_53:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v35);
  CMFPropVariant::Clear(&pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800a0034  push    rbp
0x1800a0036  push    rbx
0x1800a0037  push    rsi
0x1800a0038  push    rdi
0x1800a0039  push    r12
0x1800a003b  push    r13
0x1800a003d  push    r14
0x1800a003f  push    r15
0x1800a0041  lea     rbp, [rsp-7]
0x1800a0046  sub     rsp, 0A8h
0x1800a004d  mov     rax, cs:__security_cookie
0x1800a0054  xor     rax, rsp
0x1800a0057  mov     [rbp+3Fh+var_50], rax
0x1800a005b  mov     r12, [rbp+3Fh+arg_30]
0x1800a005f  mov     r13, r8
0x1800a0062  mov     r15, [rbp+3Fh+arg_20]
0x1800a0066  mov     r14, rdx
0x1800a0069  mov     rsi, rcx
0x1800a006c  mov     [rbp+3Fh+var_80], r9
0x1800a0070  xor     edi, edi
0x1800a0072  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x1800a0079  xorps   xmm0, xmm0
0x1800a007c  mov     [r12], rdi
0x1800a0080  xor     eax, eax
0x1800a0082  mov     [rbp+3Fh+var_88], rdi
0x1800a0086  mov     r8d, 878h; int
0x1800a008c  mov     qword ptr [rbp+3Fh+pvar+10h], rax
0x1800a0090  lea     rcx, [rbp+3Fh+var_90]; this
0x1800a0094  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x1800a0098  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a009d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a00a4  cmp     [rcx+8], dil
0x1800a00a8  jz      short loc_1800A00FD
0x1800a00aa  cmp     [rsi+58h], rdi
0x1800a00ae  jz      short loc_1800A00FD
0x1800a00b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a00b5  mov     rdx, [rsi+58h]
0x1800a00b9  mov     rdi, rax
0x1800a00bc  mov     rcx, [rdx]
0x1800a00bf  mov     rax, [rcx+128h]
0x1800a00c6  mov     rcx, rdx
0x1800a00c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a00ce  mov     r8, [rsi+58h]
0x1800a00d2  lea     rdx, [rbp+3Fh+var_60]
0x1800a00d6  mov     ebx, eax
0x1800a00d8  mov     rcx, [r8]
0x1800a00db  mov     rax, [rcx+118h]
0x1800a00e2  mov     rcx, r8
0x1800a00e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a00ea  movups  xmm0, xmmword ptr [rax]
0x1800a00ed  mov     [rdi+7E0h], ebx
0x1800a00f3  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a00fb  xor     edi, edi
0x1800a00fd  mov     eax, 13h
0x1800a0102  mov     qword ptr [rbp+3Fh+pvar+8], 1
0x1800a010a  mov     word ptr [rbp+3Fh+pvar], ax
0x1800a010e  lea     r8, [rbp+3Fh+pvar]
0x1800a0112  mov     rax, [r15]
0x1800a0115  lea     rdx, MFPKEY_MediaSource_ThumbnailMode
0x1800a011c  mov     rcx, r15
0x1800a011f  mov     rax, [rax+30h]
0x1800a0123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0128  mov     ebx, eax
0x1800a012a  test    eax, eax
0x1800a012c  jns     loc_1800A01E5
0x1800a0132  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0139  test    rcx, rcx
0x1800a013c  jnz     short loc_1800A0185
0x1800a013e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a0145  nop     dword ptr [rax+rax+00h]
0x1800a014a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0151  mov     rcx, rax
0x1800a0154  test    rax, rax
0x1800a0157  jz      short loc_1800A0177
0x1800a0159  mov     rax, [rax]
0x1800a015c  mov     edx, 7F0h
0x1800a0161  mov     rax, [rax+8]
0x1800a0165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a016a  test    eax, eax
0x1800a016c  jz      short loc_1800A0177
0x1800a016e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0175  jmp     short loc_1800A0185
0x1800a0177  lea     rcx, qword_1801B97E0; this
0x1800a017e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0185  cmp     [rcx+8], dil
0x1800a0189  jz      short loc_1800A01B0
0x1800a018b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a0190  cmp     [rax+7CCh], ebx
0x1800a0196  jz      short loc_1800A01B0
0x1800a0198  mov     r9d, ebx; int
0x1800a019b  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x1800a01a2  mov     r8d, 87Ah; int
0x1800a01a8  mov     rcx, rax; this
0x1800a01ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a01b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a01b7  jb      loc_1800A04A9
0x1800a01bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a01c4  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x1800a01cb  mov     edx, 0D4h
0x1800a01d0  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800a01d4  mov     r9, rsi
0x1800a01d7  mov     rcx, [rcx+10h]
0x1800a01db  call    WPP_SF_qD
0x1800a01e0  jmp     loc_1800A04A9
0x1800a01e5  lea     rdi, [rsi+30h]
0x1800a01e9  mov     rcx, rdi; lpCriticalSection
0x1800a01ec  call    cs:__imp_EnterCriticalSection
0x1800a01f3  nop     dword ptr [rax+rax+00h]
0x1800a01f8  mov     rax, [r14]
0x1800a01fb  lea     rcx, [rbp+3Fh+var_88]
0x1800a01ff  mov     rbx, [rax+38h]
0x1800a0203  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0208  mov     r8, [rbp+3Fh+var_80]
0x1800a020c  lea     rcx, [rsi+10h]
0x1800a0210  mov     [rsp+0E0h+var_A8], r14
0x1800a0215  lea     rax, [rbp+3Fh+var_88]
0x1800a0219  mov     [rsp+0E0h+var_B0], rcx
0x1800a021e  mov     r9d, 10401h
0x1800a0224  mov     [rsp+0E0h+var_B8], rax
0x1800a0229  mov     rdx, r13
0x1800a022c  mov     rax, rbx
0x1800a022f  mov     [rsp+0E0h+var_C0], r15
0x1800a0234  mov     rcx, r14
0x1800a0237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a023c  xor     r15d, r15d
0x1800a023f  mov     ebx, eax
0x1800a0241  test    eax, eax
0x1800a0243  jns     loc_1800A02FC
0x1800a0249  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0250  test    rcx, rcx
0x1800a0253  jnz     short loc_1800A029C
0x1800a0255  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a025c  nop     dword ptr [rax+rax+00h]
0x1800a0261  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0268  mov     rcx, rax
0x1800a026b  test    rax, rax
0x1800a026e  jz      short loc_1800A028E
0x1800a0270  mov     rax, [rax]
0x1800a0273  mov     edx, 7F0h
0x1800a0278  mov     rax, [rax+8]
0x1800a027c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0281  test    eax, eax
0x1800a0283  jz      short loc_1800A028E
0x1800a0285  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a028c  jmp     short loc_1800A029C
0x1800a028e  lea     rcx, qword_1801B97E0; this
0x1800a0295  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a029c  cmp     [rcx+8], r15b
0x1800a02a0  jz      short loc_1800A02C7
0x1800a02a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a02a7  cmp     [rax+7CCh], ebx
0x1800a02ad  jz      short loc_1800A02C7
0x1800a02af  mov     r9d, ebx; int
0x1800a02b2  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x1800a02b9  mov     r8d, 882h; int
0x1800a02bf  mov     rcx, rax; this
0x1800a02c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a02c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a02ce  jb      loc_1800A049A
0x1800a02d4  mov     edx, 0D5h
0x1800a02d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a02e0  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x1800a02e7  mov     r9, rsi
0x1800a02ea  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800a02ee  mov     rcx, [rcx+10h]
0x1800a02f2  call    WPP_SF_qD
0x1800a02f7  jmp     loc_1800A049A
0x1800a02fc  mov     rcx, rdi; lpCriticalSection
0x1800a02ff  call    cs:__imp_LeaveCriticalSection
0x1800a0306  nop     dword ptr [rax+rax+00h]
0x1800a030b  mov     edx, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x1800a030e  mov     rcx, [rsi+20h]; hHandle
0x1800a0312  call    cs:__imp_WaitForSingleObject
0x1800a0319  nop     dword ptr [rax+rax+00h]
0x1800a031e  mov     rcx, rdi; lpCriticalSection
0x1800a0321  mov     ebx, eax
0x1800a0323  call    cs:__imp_EnterCriticalSection
0x1800a032a  nop     dword ptr [rax+rax+00h]
0x1800a032f  cmp     ebx, 102h
0x1800a0335  jnz     short loc_1800A0350
0x1800a0337  mov     rdx, [rbp+3Fh+var_88]
0x1800a033b  mov     rcx, r14
0x1800a033e  mov     byte ptr [rsi+2Ch], 1
0x1800a0342  mov     rax, [r14]
0x1800a0345  mov     rax, [rax+48h]
0x1800a0349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a034e  jmp     short loc_1800A0358
0x1800a0350  test    ebx, ebx
0x1800a0352  jz      loc_1800A03F2
0x1800a0358  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a035f  mov     ebx, 8000FFFFh
0x1800a0364  test    rcx, rcx
0x1800a0367  jnz     short loc_1800A03B0
0x1800a0369  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a0370  nop     dword ptr [rax+rax+00h]
0x1800a0375  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a037c  mov     rcx, rax
0x1800a037f  test    rax, rax
0x1800a0382  jz      short loc_1800A03A2
0x1800a0384  mov     rax, [rax]
0x1800a0387  mov     edx, 7F0h
0x1800a038c  mov     rax, [rax+8]
0x1800a0390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0395  test    eax, eax
0x1800a0397  jz      short loc_1800A03A2
0x1800a0399  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a03a0  jmp     short loc_1800A03B0
0x1800a03a2  lea     rcx, qword_1801B97E0; this
0x1800a03a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a03b0  cmp     [rcx+8], r15b
0x1800a03b4  jz      short loc_1800A03DB
0x1800a03b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a03bb  cmp     [rax+7CCh], ebx
0x1800a03c1  jz      short loc_1800A03DB
0x1800a03c3  mov     r9d, ebx; int
0x1800a03c6  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x1800a03cd  mov     r8d, 892h; int
0x1800a03d3  mov     rcx, rax; this
0x1800a03d6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a03db  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a03e2  jb      loc_1800A049A
0x1800a03e8  mov     edx, 0D6h
0x1800a03ed  jmp     loc_1800A02D9
0x1800a03f2  mov     ebx, [rsi+28h]
0x1800a03f5  test    ebx, ebx
0x1800a03f7  jns     loc_1800A048E
0x1800a03fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0404  test    rcx, rcx
0x1800a0407  jnz     short loc_1800A0450
0x1800a0409  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a0410  nop     dword ptr [rax+rax+00h]
0x1800a0415  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a041c  mov     rcx, rax
0x1800a041f  test    rax, rax
0x1800a0422  jz      short loc_1800A0442
0x1800a0424  mov     rax, [rax]
0x1800a0427  mov     edx, 7F0h
0x1800a042c  mov     rax, [rax+8]
0x1800a0430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0435  test    eax, eax
0x1800a0437  jz      short loc_1800A0442
0x1800a0439  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0440  jmp     short loc_1800A0450
0x1800a0442  lea     rcx, qword_1801B97E0; this
0x1800a0449  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a0450  cmp     [rcx+8], r15b
0x1800a0454  jz      short loc_1800A047B
0x1800a0456  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a045b  cmp     [rax+7CCh], ebx
0x1800a0461  jz      short loc_1800A047B
0x1800a0463  mov     r9d, ebx; int
0x1800a0466  lea     rdx, aCmfvideothumbn_21; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x1800a046d  mov     r8d, 894h; int
0x1800a0473  mov     rcx, rax; this
0x1800a0476  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a047b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a0482  jb      short loc_1800A049A
0x1800a0484  mov     edx, 0D7h
0x1800a0489  jmp     loc_1800A02D9
0x1800a048e  mov     rax, [rsi+18h]
0x1800a0492  mov     [rsi+18h], r15
0x1800a0496  mov     [r12], rax
0x1800a049a  mov     rcx, rdi; lpCriticalSection
0x1800a049d  call    cs:__imp_LeaveCriticalSection
0x1800a04a4  nop     dword ptr [rax+rax+00h]
0x1800a04a9  lea     rcx, [rbp+3Fh+var_90]; this
0x1800a04ad  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a04b2  lea     rcx, [rbp+3Fh+pvar]; pvar
0x1800a04b6  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800a04bb  lea     rcx, [rbp+3Fh+var_88]
0x1800a04bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a04c4  mov     eax, ebx
0x1800a04c6  mov     rcx, [rbp+3Fh+var_50]
0x1800a04ca  xor     rcx, rsp; StackCookie
0x1800a04cd  call    __security_check_cookie
0x1800a04d2  add     rsp, 0A8h
0x1800a04d9  pop     r15
0x1800a04db  pop     r14
0x1800a04dd  pop     r13
0x1800a04df  pop     r12
0x1800a04e1  pop     rdi
0x1800a04e2  pop     rsi
0x1800a04e3  pop     rbx
0x1800a04e4  pop     rbp
0x1800a04e5  retn
```
