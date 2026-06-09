# CMFVideoThumbnail::CreateSourceReaderFromDShowSource(IMFByteStream *,IMFSourceReader * *)

- ea: `0x18006764c`
- end: `0x1800678a8`
- name: `?CreateSourceReaderFromDShowSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180067c44`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180066500`
- `0x18006764c`
- `0x180069a78`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006771a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006771a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067736`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800677e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067736`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800677e2`

## string_xrefs

- `0x18006767e`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`
- `0x18006778d`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`
- `0x180067839`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CreateSourceReaderFromDShowSource(
        CMFVideoThumbnail *this,
        struct IMFByteStream *a2,
        struct IMFSourceReader **a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  HRESULT Instance; // ebx
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
  struct IMFSourceResolver *ppv; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v26[16]; // [rsp+40h] [rbp-48h] BYREF

  ppv = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v24,
    "CMFVideoThumbnail::CreateSourceReaderFromDShowSource",
    521);
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
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&ppv);
  Instance = CoCreateInstance(&CLSID_DShowSourceResolver, 0, 1u, &IID_IMFSourceResolver, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(this, a2, ppv, a3);
    if ( Instance < 0 )
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
        if ( *((_DWORD *)v22 + 499) != Instance )
          CallStackContext::TraceFailure(v22, "CMFVideoThumbnail::CreateSourceReaderFromDShowSource", 526, Instance);
      }
      if ( g_wppLevels )
      {
        v16 = 50;
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
      if ( *((_DWORD *)v15 + 499) != Instance )
        CallStackContext::TraceFailure(v15, "CMFVideoThumbnail::CreateSourceReaderFromDShowSource", 524, Instance);
    }
    if ( g_wppLevels )
    {
      v16 = 49;
LABEL_26:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        Instance);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18006764c  push    rbx
0x18006764e  push    rbp
0x18006764f  push    rsi
0x180067650  push    rdi
0x180067651  push    r14
0x180067653  sub     rsp, 60h
0x180067657  mov     rax, cs:__security_cookie
0x18006765e  xor     rax, rsp
0x180067661  mov     [rsp+88h+var_38], rax
0x180067666  mov     r14, r8
0x180067669  mov     [rsp+88h+var_50], 0
0x180067672  mov     rbp, rdx
0x180067675  mov     rsi, rcx
0x180067678  mov     r8d, 209h; int
0x18006767e  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x180067685  lea     rcx, [rsp+88h+var_58]; this
0x18006768a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006768f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180067696  cmp     byte ptr [rcx+8], 0
0x18006769a  jz      short loc_1800676F2
0x18006769c  cmp     qword ptr [rsi+190h], 0
0x1800676a4  jz      short loc_1800676F2
0x1800676a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800676ab  mov     rcx, [rsi+190h]
0x1800676b2  mov     rdi, rax
0x1800676b5  mov     rdx, [rcx]
0x1800676b8  mov     rax, [rdx+128h]
0x1800676bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676c4  mov     rcx, [rsi+190h]
0x1800676cb  mov     ebx, eax
0x1800676cd  mov     rdx, [rcx]
0x1800676d0  mov     rax, [rdx+118h]
0x1800676d7  lea     rdx, [rsp+88h+var_48]
0x1800676dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676e1  movups  xmm0, xmmword ptr [rax]
0x1800676e4  mov     [rdi+7E0h], ebx
0x1800676ea  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800676f2  lea     rcx, [rsp+88h+var_50]
0x1800676f7  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x1800676fc  xor     edx, edx; pUnkOuter
0x1800676fe  lea     rax, [rsp+88h+var_50]
0x180067703  lea     r9, IID_IMFSourceResolver; riid
0x18006770a  mov     [rsp+88h+ppv], rax; ppv
0x18006770f  lea     rcx, CLSID_DShowSourceResolver; rclsid
0x180067716  lea     r8d, [rdx+1]; dwClsContext
0x18006771a  call    cs:__imp_CoCreateInstance
0x180067720  mov     ebx, eax
0x180067722  test    eax, eax
0x180067724  jns     loc_1800677B9
0x18006772a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067731  test    rcx, rcx
0x180067734  jnz     short loc_180067777
0x180067736  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006773c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067743  mov     rcx, rax
0x180067746  test    rax, rax
0x180067749  jz      short loc_180067769
0x18006774b  mov     rax, [rax]
0x18006774e  mov     edx, 7F0h
0x180067753  mov     rax, [rax+8]
0x180067757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006775c  test    eax, eax
0x18006775e  jz      short loc_180067769
0x180067760  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067767  jmp     short loc_180067777
0x180067769  lea     rcx, qword_1800D6F70; this
0x180067770  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067777  cmp     byte ptr [rcx+8], 0
0x18006777b  jz      short loc_1800677A2
0x18006777d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067782  cmp     [rax+7CCh], ebx
0x180067788  jz      short loc_1800677A2
0x18006778a  mov     r9d, ebx; int
0x18006778d  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x180067794  mov     r8d, 20Ch; int
0x18006779a  mov     rcx, rax; this
0x18006779d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800677a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800677a9  jb      loc_18006787A
0x1800677af  mov     edx, 31h ; '1'
0x1800677b4  jmp     loc_18006785C
0x1800677b9  mov     r8, [rsp+88h+var_50]; struct IMFSourceResolver *
0x1800677be  mov     r9, r14; struct IMFSourceReader **
0x1800677c1  mov     rdx, rbp; struct IMFByteStream *
0x1800677c4  mov     rcx, rsi; this
0x1800677c7  call    ?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)
0x1800677cc  mov     ebx, eax
0x1800677ce  test    eax, eax
0x1800677d0  jns     loc_18006787A
0x1800677d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800677dd  test    rcx, rcx
0x1800677e0  jnz     short loc_180067823
0x1800677e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800677e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800677ef  mov     rcx, rax
0x1800677f2  test    rax, rax
0x1800677f5  jz      short loc_180067815
0x1800677f7  mov     rax, [rax]
0x1800677fa  mov     edx, 7F0h
0x1800677ff  mov     rax, [rax+8]
0x180067803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067808  test    eax, eax
0x18006780a  jz      short loc_180067815
0x18006780c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067813  jmp     short loc_180067823
0x180067815  lea     rcx, qword_1800D6F70; this
0x18006781c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067823  cmp     byte ptr [rcx+8], 0
0x180067827  jz      short loc_18006784E
0x180067829  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006782e  cmp     [rax+7CCh], ebx
0x180067834  jz      short loc_18006784E
0x180067836  mov     r9d, ebx; int
0x180067839  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x180067840  mov     r8d, 20Eh; int
0x180067846  mov     rcx, rax; this
0x180067849  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006784e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067855  jb      short loc_18006787A
0x180067857  mov     edx, 32h ; '2'
0x18006785c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067863  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006786a  mov     r9, rsi
0x18006786d  mov     dword ptr [rsp+88h+ppv], ebx
0x180067871  mov     rcx, [rcx+10h]
0x180067875  call    WPP_SF_qD
0x18006787a  lea     rcx, [rsp+88h+var_58]; this
0x18006787f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067884  lea     rcx, [rsp+88h+var_50]
0x180067889  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18006788e  mov     eax, ebx
0x180067890  mov     rcx, [rsp+88h+var_38]
0x180067895  xor     rcx, rsp; StackCookie
0x180067898  call    __security_check_cookie
0x18006789d  add     rsp, 60h
0x1800678a1  pop     r14
0x1800678a3  pop     rdi
0x1800678a4  pop     rsi
0x1800678a5  pop     rbp
0x1800678a6  pop     rbx
0x1800678a7  retn
```
