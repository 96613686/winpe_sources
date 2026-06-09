# CMFVideoThumbnail::CreateSourceReaderFromMFSource(IMFByteStream *,IMFSourceReader * *)

- ea: `0x18004bec8`
- end: `0x18004c10b`
- name: `?CreateSourceReaderFromMFSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004c254`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180048710`
- `0x18004ab18`
- `0x18004bec8`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bf99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c045`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bf99`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004c045`
- `MFPlat!MFCreateSourceResolver` at `0x18004bf7d`
- `MFPlat!MFCreateSourceResolver` at `0x18004bf7d`

## string_xrefs

- `0x18004befa`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`
- `0x18004bff0`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`
- `0x18004c09c`: `CMFVideoThumbnail::CreateSourceReaderFromMFSource`

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
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-58h] BYREF
  IMFSourceResolver *ppISourceResolver; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v22[16]; // [rsp+40h] [rbp-48h] BYREF

  ppISourceResolver = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v20,
    "CMFVideoThumbnail::CreateSourceReaderFromMFSource",
    504);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v22);
    *((_DWORD *)ThreadRelativeContext + 504) = v7;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppISourceResolver);
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
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != AsyncSourceReaderUsingSourceResolver )
          CallStackContext::TraceFailure(
            v18,
            "CMFVideoThumbnail::CreateSourceReaderFromMFSource",
            508,
            AsyncSourceReaderUsingSourceResolver);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 47;
        goto LABEL_26;
      }
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != AsyncSourceReaderUsingSourceResolver )
        CallStackContext::TraceFailure(
          v13,
          "CMFVideoThumbnail::CreateSourceReaderFromMFSource",
          506,
          AsyncSourceReaderUsingSourceResolver);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 46;
LABEL_26:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        AsyncSourceReaderUsingSourceResolver);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppISourceResolver);
  return (unsigned int)AsyncSourceReaderUsingSourceResolver;
}

```

## disassembly

```asm
0x18004bec8  push    rbx
0x18004beca  push    rbp
0x18004becb  push    rsi
0x18004becc  push    rdi
0x18004becd  push    r14
0x18004becf  sub     rsp, 60h
0x18004bed3  mov     rax, cs:__security_cookie
0x18004beda  xor     rax, rsp
0x18004bedd  mov     [rsp+88h+var_38], rax
0x18004bee2  mov     r14, r8
0x18004bee5  mov     [rsp+88h+ppISourceResolver], 0
0x18004beee  mov     rbp, rdx
0x18004bef1  mov     rsi, rcx
0x18004bef4  mov     r8d, 1F8h; int
0x18004befa  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18004bf01  lea     rcx, [rsp+88h+var_58]; this
0x18004bf06  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004bf0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004bf12  cmp     byte ptr [rcx+8], 0
0x18004bf16  jz      short loc_18004BF6E
0x18004bf18  cmp     qword ptr [rsi+190h], 0
0x18004bf20  jz      short loc_18004BF6E
0x18004bf22  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bf27  mov     rcx, [rsi+190h]
0x18004bf2e  mov     rdi, rax
0x18004bf31  mov     rdx, [rcx]
0x18004bf34  mov     rax, [rdx+128h]
0x18004bf3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf40  mov     rcx, [rsi+190h]
0x18004bf47  mov     ebx, eax
0x18004bf49  mov     rdx, [rcx]
0x18004bf4c  mov     rax, [rdx+118h]
0x18004bf53  lea     rdx, [rsp+88h+var_48]
0x18004bf58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf5d  movups  xmm0, xmmword ptr [rax]
0x18004bf60  mov     [rdi+7E0h], ebx
0x18004bf66  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004bf6e  lea     rcx, [rsp+88h+ppISourceResolver]
0x18004bf73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bf78  lea     rcx, [rsp+88h+ppISourceResolver]; ppISourceResolver
0x18004bf7d  call    cs:__imp_MFCreateSourceResolver
0x18004bf83  mov     ebx, eax
0x18004bf85  test    eax, eax
0x18004bf87  jns     loc_18004C01C
0x18004bf8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bf94  test    rcx, rcx
0x18004bf97  jnz     short loc_18004BFDA
0x18004bf99  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bf9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bfa6  mov     rcx, rax
0x18004bfa9  test    rax, rax
0x18004bfac  jz      short loc_18004BFCC
0x18004bfae  mov     rax, [rax]
0x18004bfb1  mov     edx, 7F0h
0x18004bfb6  mov     rax, [rax+8]
0x18004bfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfbf  test    eax, eax
0x18004bfc1  jz      short loc_18004BFCC
0x18004bfc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bfca  jmp     short loc_18004BFDA
0x18004bfcc  lea     rcx, qword_18006EB20; this
0x18004bfd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bfda  cmp     byte ptr [rcx+8], 0
0x18004bfde  jz      short loc_18004C005
0x18004bfe0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bfe5  cmp     [rax+7CCh], ebx
0x18004bfeb  jz      short loc_18004C005
0x18004bfed  mov     r9d, ebx; int
0x18004bff0  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18004bff7  mov     r8d, 1FAh; int
0x18004bffd  mov     rcx, rax; this
0x18004c000  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c005  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c00a  cmp     al, 1
0x18004c00c  jb      loc_18004C0DD
0x18004c012  mov     edx, 2Eh ; '.'
0x18004c017  jmp     loc_18004C0BF
0x18004c01c  mov     r8, [rsp+88h+ppISourceResolver]; struct IMFSourceResolver *
0x18004c021  mov     r9, r14; struct IMFSourceReader **
0x18004c024  mov     rdx, rbp; struct IMFByteStream *
0x18004c027  mov     rcx, rsi; this
0x18004c02a  call    ?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)
0x18004c02f  mov     ebx, eax
0x18004c031  test    eax, eax
0x18004c033  jns     loc_18004C0DD
0x18004c039  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c040  test    rcx, rcx
0x18004c043  jnz     short loc_18004C086
0x18004c045  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004c04b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c052  mov     rcx, rax
0x18004c055  test    rax, rax
0x18004c058  jz      short loc_18004C078
0x18004c05a  mov     rax, [rax]
0x18004c05d  mov     edx, 7F0h
0x18004c062  mov     rax, [rax+8]
0x18004c066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c06b  test    eax, eax
0x18004c06d  jz      short loc_18004C078
0x18004c06f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c076  jmp     short loc_18004C086
0x18004c078  lea     rcx, qword_18006EB20; this
0x18004c07f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004c086  cmp     byte ptr [rcx+8], 0
0x18004c08a  jz      short loc_18004C0B1
0x18004c08c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004c091  cmp     [rax+7CCh], ebx
0x18004c097  jz      short loc_18004C0B1
0x18004c099  mov     r9d, ebx; int
0x18004c09c  lea     rdx, aCmfvideothumbn_10; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18004c0a3  mov     r8d, 1FCh; int
0x18004c0a9  mov     rcx, rax; this
0x18004c0ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004c0b1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004c0b6  cmp     al, 1
0x18004c0b8  jb      short loc_18004C0DD
0x18004c0ba  mov     edx, 2Fh ; '/'
0x18004c0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0c6  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004c0cd  mov     r9, rsi
0x18004c0d0  mov     [rsp+88h+var_68], ebx
0x18004c0d4  mov     rcx, [rcx+10h]
0x18004c0d8  call    WPP_SF_qd
0x18004c0dd  lea     rcx, [rsp+88h+var_58]; this
0x18004c0e2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004c0e7  lea     rcx, [rsp+88h+ppISourceResolver]
0x18004c0ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c0f1  mov     eax, ebx
0x18004c0f3  mov     rcx, [rsp+88h+var_38]
0x18004c0f8  xor     rcx, rsp; StackCookie
0x18004c0fb  call    __security_check_cookie
0x18004c100  add     rsp, 60h
0x18004c104  pop     r14
0x18004c106  pop     rdi
0x18004c107  pop     rsi
0x18004c108  pop     rbp
0x18004c109  pop     rbx
0x18004c10a  retn
```
