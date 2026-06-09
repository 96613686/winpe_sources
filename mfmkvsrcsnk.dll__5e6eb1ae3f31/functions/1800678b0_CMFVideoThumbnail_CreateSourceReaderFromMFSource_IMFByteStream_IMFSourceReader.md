# CMFVideoThumbnail::CreateSourceReaderFromMFSource(IMFByteStream *,IMFSourceReader * *)

- ea: `0x1800678b0`
- end: `0x180067af3`
- name: `?CreateSourceReaderFromMFSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180067c44`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180066500`
- `0x1800678b0`
- `0x180069a78`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067981`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067a2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067981`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067a2d`
- `MFPlat!MFCreateSourceResolver` at `0x180067965`
- `MFPlat!MFCreateSourceResolver` at `0x180067965`

## string_xrefs

- `0x1800678e2`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`
- `0x1800679d8`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`
- `0x180067a84`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CreateSourceReaderFromMFSource(
        CMFVideoThumbnail *this,
        struct IMFByteStream *a2,
        struct IMFSourceReader **a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  HRESULT AsyncSourceReaderUsingSourceResolver; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  _BYTE v24[8]; // [rsp+30h] [rbp-58h] BYREF
  IMFSourceResolver *ppISourceResolver; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v26[16]; // [rsp+40h] [rbp-48h] BYREF

  ppISourceResolver = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v24,
    "CMFVideoThumbnail::CreateSourceReaderFromMFSource",
    504);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v26);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&ppISourceResolver);
  AsyncSourceReaderUsingSourceResolver = MFCreateSourceResolver(&ppISourceResolver);
  if ( AsyncSourceReaderUsingSourceResolver >= 0 )
  {
    AsyncSourceReaderUsingSourceResolver = CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(
                                             this,
                                             a2,
                                             ppISourceResolver,
                                             a3);
    if ( AsyncSourceReaderUsingSourceResolver < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != AsyncSourceReaderUsingSourceResolver )
          CallStackContext::TraceFailure(
            v22,
            "CMFVideoThumbnail::CreateSourceReaderFromMFSource",
            508,
            AsyncSourceReaderUsingSourceResolver);
      }
      if ( g_wppLevels )
      {
        v16 = 47;
        goto LABEL_26;
      }
    }
  }
  else
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v11, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != AsyncSourceReaderUsingSourceResolver )
        CallStackContext::TraceFailure(
          v15,
          "CMFVideoThumbnail::CreateSourceReaderFromMFSource",
          506,
          AsyncSourceReaderUsingSourceResolver);
    }
    if ( g_wppLevels )
    {
      v16 = 46;
LABEL_26:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        AsyncSourceReaderUsingSourceResolver);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&ppISourceResolver);
  return (unsigned int)AsyncSourceReaderUsingSourceResolver;
}

```

## disassembly

```asm
0x1800678b0  push    rbx
0x1800678b2  push    rbp
0x1800678b3  push    rsi
0x1800678b4  push    rdi
0x1800678b5  push    r14
0x1800678b7  sub     rsp, 60h
0x1800678bb  mov     rax, cs:__security_cookie
0x1800678c2  xor     rax, rsp
0x1800678c5  mov     [rsp+88h+var_38], rax
0x1800678ca  mov     r14, r8
0x1800678cd  mov     [rsp+88h+ppISourceResolver], 0
0x1800678d6  mov     rbp, rdx
0x1800678d9  mov     rsi, rcx
0x1800678dc  mov     r8d, 1F8h; int
0x1800678e2  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x1800678e9  lea     rcx, [rsp+88h+var_58]; this
0x1800678ee  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800678f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800678fa  cmp     byte ptr [rcx+8], 0
0x1800678fe  jz      short loc_180067956
0x180067900  cmp     qword ptr [rsi+190h], 0
0x180067908  jz      short loc_180067956
0x18006790a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006790f  mov     rcx, [rsi+190h]
0x180067916  mov     rdi, rax
0x180067919  mov     rdx, [rcx]
0x18006791c  mov     rax, [rdx+128h]
0x180067923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067928  mov     rcx, [rsi+190h]
0x18006792f  mov     ebx, eax
0x180067931  mov     rdx, [rcx]
0x180067934  mov     rax, [rdx+118h]
0x18006793b  lea     rdx, [rsp+88h+var_48]
0x180067940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067945  movups  xmm0, xmmword ptr [rax]
0x180067948  mov     [rdi+7E0h], ebx
0x18006794e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180067956  lea     rcx, [rsp+88h+ppISourceResolver]
0x18006795b  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180067960  lea     rcx, [rsp+88h+ppISourceResolver]; ppISourceResolver
0x180067965  call    cs:__imp_MFCreateSourceResolver
0x18006796b  mov     ebx, eax
0x18006796d  test    eax, eax
0x18006796f  jns     loc_180067A04
0x180067975  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006797c  test    rcx, rcx
0x18006797f  jnz     short loc_1800679C2
0x180067981  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067987  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006798e  mov     rcx, rax
0x180067991  test    rax, rax
0x180067994  jz      short loc_1800679B4
0x180067996  mov     rax, [rax]
0x180067999  mov     edx, 7F0h
0x18006799e  mov     rax, [rax+8]
0x1800679a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679a7  test    eax, eax
0x1800679a9  jz      short loc_1800679B4
0x1800679ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800679b2  jmp     short loc_1800679C2
0x1800679b4  lea     rcx, qword_1800D6F70; this
0x1800679bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800679c2  cmp     byte ptr [rcx+8], 0
0x1800679c6  jz      short loc_1800679ED
0x1800679c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800679cd  cmp     [rax+7CCh], ebx
0x1800679d3  jz      short loc_1800679ED
0x1800679d5  mov     r9d, ebx; int
0x1800679d8  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x1800679df  mov     r8d, 1FAh; int
0x1800679e5  mov     rcx, rax; this
0x1800679e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800679ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800679f4  jb      loc_180067AC5
0x1800679fa  mov     edx, 2Eh ; '.'
0x1800679ff  jmp     loc_180067AA7
0x180067a04  mov     r8, [rsp+88h+ppISourceResolver]; struct IMFSourceResolver *
0x180067a09  mov     r9, r14; struct IMFSourceReader **
0x180067a0c  mov     rdx, rbp; struct IMFByteStream *
0x180067a0f  mov     rcx, rsi; this
0x180067a12  call    ?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)
0x180067a17  mov     ebx, eax
0x180067a19  test    eax, eax
0x180067a1b  jns     loc_180067AC5
0x180067a21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a28  test    rcx, rcx
0x180067a2b  jnz     short loc_180067A6E
0x180067a2d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067a33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a3a  mov     rcx, rax
0x180067a3d  test    rax, rax
0x180067a40  jz      short loc_180067A60
0x180067a42  mov     rax, [rax]
0x180067a45  mov     edx, 7F0h
0x180067a4a  mov     rax, [rax+8]
0x180067a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a53  test    eax, eax
0x180067a55  jz      short loc_180067A60
0x180067a57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a5e  jmp     short loc_180067A6E
0x180067a60  lea     rcx, qword_1800D6F70; this
0x180067a67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a6e  cmp     byte ptr [rcx+8], 0
0x180067a72  jz      short loc_180067A99
0x180067a74  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067a79  cmp     [rax+7CCh], ebx
0x180067a7f  jz      short loc_180067A99
0x180067a81  mov     r9d, ebx; int
0x180067a84  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x180067a8b  mov     r8d, 1FCh; int
0x180067a91  mov     rcx, rax; this
0x180067a94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067a99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067aa0  jb      short loc_180067AC5
0x180067aa2  mov     edx, 2Fh ; '/'
0x180067aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180067aae  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180067ab5  mov     r9, rsi
0x180067ab8  mov     [rsp+88h+var_68], ebx
0x180067abc  mov     rcx, [rcx+10h]
0x180067ac0  call    WPP_SF_qD
0x180067ac5  lea     rcx, [rsp+88h+var_58]; this
0x180067aca  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067acf  lea     rcx, [rsp+88h+ppISourceResolver]
0x180067ad4  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180067ad9  mov     eax, ebx
0x180067adb  mov     rcx, [rsp+88h+var_38]
0x180067ae0  xor     rcx, rsp; StackCookie
0x180067ae3  call    __security_check_cookie
0x180067ae8  add     rsp, 60h
0x180067aec  pop     r14
0x180067aee  pop     rdi
0x180067aef  pop     rsi
0x180067af0  pop     rbp
0x180067af1  pop     rbx
0x180067af2  retn
```
