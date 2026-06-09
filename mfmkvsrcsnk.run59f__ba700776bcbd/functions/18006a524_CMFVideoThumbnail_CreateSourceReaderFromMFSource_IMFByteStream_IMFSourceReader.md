# CMFVideoThumbnail::CreateSourceReaderFromMFSource(IMFByteStream *,IMFSourceReader * *)

- ea: `0x18006a524`
- end: `0x18006a77a`
- name: `?CreateSourceReaderFromMFSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18006a8cc`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180069134`
- `0x18006a524`
- `0x18006c764`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a5fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a6ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a5fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a6ad`
- `MFPlat!MFCreateSourceResolver` at `0x18006a5d9`
- `MFPlat!MFCreateSourceResolver` at `0x18006a5d9`

## string_xrefs

- `0x18006a556`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`
- `0x18006a658`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`
- `0x18006a70a`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`

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
          v20 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v13 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18006a524  push    rbx
0x18006a526  push    rbp
0x18006a527  push    rsi
0x18006a528  push    rdi
0x18006a529  push    r14
0x18006a52b  sub     rsp, 60h
0x18006a52f  mov     rax, cs:__security_cookie
0x18006a536  xor     rax, rsp
0x18006a539  mov     [rsp+88h+var_38], rax
0x18006a53e  mov     r14, r8
0x18006a541  mov     [rsp+88h+ppISourceResolver], 0
0x18006a54a  mov     rbp, rdx
0x18006a54d  mov     rsi, rcx
0x18006a550  mov     r8d, 1F8h; int
0x18006a556  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18006a55d  lea     rcx, [rsp+88h+var_58]; this
0x18006a562  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006a567  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006a56e  cmp     byte ptr [rcx+8], 0
0x18006a572  jz      short loc_18006A5CA
0x18006a574  cmp     qword ptr [rsi+190h], 0
0x18006a57c  jz      short loc_18006A5CA
0x18006a57e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a583  mov     rcx, [rsi+190h]
0x18006a58a  mov     rdi, rax
0x18006a58d  mov     rdx, [rcx]
0x18006a590  mov     rax, [rdx+128h]
0x18006a597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a59c  mov     rcx, [rsi+190h]
0x18006a5a3  mov     ebx, eax
0x18006a5a5  mov     rdx, [rcx]
0x18006a5a8  mov     rax, [rdx+118h]
0x18006a5af  lea     rdx, [rsp+88h+var_48]
0x18006a5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a5b9  movups  xmm0, xmmword ptr [rax]
0x18006a5bc  mov     [rdi+7E0h], ebx
0x18006a5c2  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006a5ca  lea     rcx, [rsp+88h+ppISourceResolver]
0x18006a5cf  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18006a5d4  lea     rcx, [rsp+88h+ppISourceResolver]; ppISourceResolver
0x18006a5d9  call    cs:__imp_MFCreateSourceResolver
0x18006a5e0  nop     dword ptr [rax+rax+00h]
0x18006a5e5  mov     ebx, eax
0x18006a5e7  test    eax, eax
0x18006a5e9  jns     loc_18006A684
0x18006a5ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a5f6  test    rcx, rcx
0x18006a5f9  jnz     short loc_18006A642
0x18006a5fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a602  nop     dword ptr [rax+rax+00h]
0x18006a607  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a60e  mov     rcx, rax
0x18006a611  test    rax, rax
0x18006a614  jz      short loc_18006A634
0x18006a616  mov     rax, [rax]
0x18006a619  mov     edx, 7F0h
0x18006a61e  mov     rax, [rax+8]
0x18006a622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a627  test    eax, eax
0x18006a629  jz      short loc_18006A634
0x18006a62b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a632  jmp     short loc_18006A642
0x18006a634  lea     rcx, qword_1800DBF70; this
0x18006a63b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a642  cmp     byte ptr [rcx+8], 0
0x18006a646  jz      short loc_18006A66D
0x18006a648  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a64d  cmp     [rax+7CCh], ebx
0x18006a653  jz      short loc_18006A66D
0x18006a655  mov     r9d, ebx; int
0x18006a658  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18006a65f  mov     r8d, 1FAh; int
0x18006a665  mov     rcx, rax; this
0x18006a668  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a66d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a674  jb      loc_18006A74B
0x18006a67a  mov     edx, 2Eh ; '.'
0x18006a67f  jmp     loc_18006A72D
0x18006a684  mov     r8, [rsp+88h+ppISourceResolver]; struct IMFSourceResolver *
0x18006a689  mov     r9, r14; struct IMFSourceReader **
0x18006a68c  mov     rdx, rbp; struct IMFByteStream *
0x18006a68f  mov     rcx, rsi; this
0x18006a692  call    ?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)
0x18006a697  mov     ebx, eax
0x18006a699  test    eax, eax
0x18006a69b  jns     loc_18006A74B
0x18006a6a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a6a8  test    rcx, rcx
0x18006a6ab  jnz     short loc_18006A6F4
0x18006a6ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a6b4  nop     dword ptr [rax+rax+00h]
0x18006a6b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a6c0  mov     rcx, rax
0x18006a6c3  test    rax, rax
0x18006a6c6  jz      short loc_18006A6E6
0x18006a6c8  mov     rax, [rax]
0x18006a6cb  mov     edx, 7F0h
0x18006a6d0  mov     rax, [rax+8]
0x18006a6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a6d9  test    eax, eax
0x18006a6db  jz      short loc_18006A6E6
0x18006a6dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a6e4  jmp     short loc_18006A6F4
0x18006a6e6  lea     rcx, qword_1800DBF70; this
0x18006a6ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a6f4  cmp     byte ptr [rcx+8], 0
0x18006a6f8  jz      short loc_18006A71F
0x18006a6fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a6ff  cmp     [rax+7CCh], ebx
0x18006a705  jz      short loc_18006A71F
0x18006a707  mov     r9d, ebx; int
0x18006a70a  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18006a711  mov     r8d, 1FCh; int
0x18006a717  mov     rcx, rax; this
0x18006a71a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a71f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a726  jb      short loc_18006A74B
0x18006a728  mov     edx, 2Fh ; '/'
0x18006a72d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a734  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006a73b  mov     r9, rsi
0x18006a73e  mov     [rsp+88h+var_68], ebx
0x18006a742  mov     rcx, [rcx+10h]
0x18006a746  call    WPP_SF_qD
0x18006a74b  lea     rcx, [rsp+88h+var_58]; this
0x18006a750  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006a755  lea     rcx, [rsp+88h+ppISourceResolver]
0x18006a75a  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18006a75f  mov     eax, ebx
0x18006a761  mov     rcx, [rsp+88h+var_38]
0x18006a766  xor     rcx, rsp; StackCookie
0x18006a769  call    __security_check_cookie
0x18006a76e  add     rsp, 60h
0x18006a772  pop     r14
0x18006a774  pop     rdi
0x18006a775  pop     rsi
0x18006a776  pop     rbp
0x18006a777  pop     rbx
0x18006a778  retn
```
