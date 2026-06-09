# CMFVideoThumbnail::CreateSourceReaderFromDShowSource(IMFByteStream *,IMFSourceReader * *)

- ea: `0x18006a2ac`
- end: `0x18006a51b`
- name: `?CreateSourceReaderFromDShowSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006a8cc`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180069134`
- `0x18006a2ac`
- `0x18006c764`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006a37a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006a37a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a39c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a44e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a39c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006a44e`

## string_xrefs

- `0x18006a2de`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`
- `0x18006a3f9`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`
- `0x18006a4ab`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`

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
          v20 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v13 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18006a2ac  push    rbx
0x18006a2ae  push    rbp
0x18006a2af  push    rsi
0x18006a2b0  push    rdi
0x18006a2b1  push    r14
0x18006a2b3  sub     rsp, 60h
0x18006a2b7  mov     rax, cs:__security_cookie
0x18006a2be  xor     rax, rsp
0x18006a2c1  mov     [rsp+88h+var_38], rax
0x18006a2c6  mov     r14, r8
0x18006a2c9  mov     [rsp+88h+var_50], 0
0x18006a2d2  mov     rbp, rdx
0x18006a2d5  mov     rsi, rcx
0x18006a2d8  mov     r8d, 209h; int
0x18006a2de  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18006a2e5  lea     rcx, [rsp+88h+var_58]; this
0x18006a2ea  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006a2ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006a2f6  cmp     byte ptr [rcx+8], 0
0x18006a2fa  jz      short loc_18006A352
0x18006a2fc  cmp     qword ptr [rsi+190h], 0
0x18006a304  jz      short loc_18006A352
0x18006a306  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a30b  mov     rcx, [rsi+190h]
0x18006a312  mov     rdi, rax
0x18006a315  mov     rdx, [rcx]
0x18006a318  mov     rax, [rdx+128h]
0x18006a31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a324  mov     rcx, [rsi+190h]
0x18006a32b  mov     ebx, eax
0x18006a32d  mov     rdx, [rcx]
0x18006a330  mov     rax, [rdx+118h]
0x18006a337  lea     rdx, [rsp+88h+var_48]
0x18006a33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a341  movups  xmm0, xmmword ptr [rax]
0x18006a344  mov     [rdi+7E0h], ebx
0x18006a34a  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006a352  lea     rcx, [rsp+88h+var_50]
0x18006a357  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18006a35c  xor     edx, edx; pUnkOuter
0x18006a35e  lea     rax, [rsp+88h+var_50]
0x18006a363  lea     r9, IID_IMFSourceResolver; riid
0x18006a36a  mov     [rsp+88h+ppv], rax; ppv
0x18006a36f  lea     rcx, CLSID_DShowSourceResolver; rclsid
0x18006a376  lea     r8d, [rdx+1]; dwClsContext
0x18006a37a  call    cs:__imp_CoCreateInstance
0x18006a381  nop     dword ptr [rax+rax+00h]
0x18006a386  mov     ebx, eax
0x18006a388  test    eax, eax
0x18006a38a  jns     loc_18006A425
0x18006a390  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a397  test    rcx, rcx
0x18006a39a  jnz     short loc_18006A3E3
0x18006a39c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a3a3  nop     dword ptr [rax+rax+00h]
0x18006a3a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a3af  mov     rcx, rax
0x18006a3b2  test    rax, rax
0x18006a3b5  jz      short loc_18006A3D5
0x18006a3b7  mov     rax, [rax]
0x18006a3ba  mov     edx, 7F0h
0x18006a3bf  mov     rax, [rax+8]
0x18006a3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3c8  test    eax, eax
0x18006a3ca  jz      short loc_18006A3D5
0x18006a3cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a3d3  jmp     short loc_18006A3E3
0x18006a3d5  lea     rcx, qword_1800DBF70; this
0x18006a3dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a3e3  cmp     byte ptr [rcx+8], 0
0x18006a3e7  jz      short loc_18006A40E
0x18006a3e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a3ee  cmp     [rax+7CCh], ebx
0x18006a3f4  jz      short loc_18006A40E
0x18006a3f6  mov     r9d, ebx; int
0x18006a3f9  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18006a400  mov     r8d, 20Ch; int
0x18006a406  mov     rcx, rax; this
0x18006a409  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a40e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a415  jb      loc_18006A4EC
0x18006a41b  mov     edx, 31h ; '1'
0x18006a420  jmp     loc_18006A4CE
0x18006a425  mov     r8, [rsp+88h+var_50]; struct IMFSourceResolver *
0x18006a42a  mov     r9, r14; struct IMFSourceReader **
0x18006a42d  mov     rdx, rbp; struct IMFByteStream *
0x18006a430  mov     rcx, rsi; this
0x18006a433  call    ?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)
0x18006a438  mov     ebx, eax
0x18006a43a  test    eax, eax
0x18006a43c  jns     loc_18006A4EC
0x18006a442  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a449  test    rcx, rcx
0x18006a44c  jnz     short loc_18006A495
0x18006a44e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006a455  nop     dword ptr [rax+rax+00h]
0x18006a45a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a461  mov     rcx, rax
0x18006a464  test    rax, rax
0x18006a467  jz      short loc_18006A487
0x18006a469  mov     rax, [rax]
0x18006a46c  mov     edx, 7F0h
0x18006a471  mov     rax, [rax+8]
0x18006a475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a47a  test    eax, eax
0x18006a47c  jz      short loc_18006A487
0x18006a47e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a485  jmp     short loc_18006A495
0x18006a487  lea     rcx, qword_1800DBF70; this
0x18006a48e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006a495  cmp     byte ptr [rcx+8], 0
0x18006a499  jz      short loc_18006A4C0
0x18006a49b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006a4a0  cmp     [rax+7CCh], ebx
0x18006a4a6  jz      short loc_18006A4C0
0x18006a4a8  mov     r9d, ebx; int
0x18006a4ab  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18006a4b2  mov     r8d, 20Eh; int
0x18006a4b8  mov     rcx, rax; this
0x18006a4bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006a4c0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006a4c7  jb      short loc_18006A4EC
0x18006a4c9  mov     edx, 32h ; '2'
0x18006a4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a4d5  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006a4dc  mov     r9, rsi
0x18006a4df  mov     dword ptr [rsp+88h+ppv], ebx
0x18006a4e3  mov     rcx, [rcx+10h]
0x18006a4e7  call    WPP_SF_qD
0x18006a4ec  lea     rcx, [rsp+88h+var_58]; this
0x18006a4f1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18006a4f6  lea     rcx, [rsp+88h+var_50]
0x18006a4fb  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18006a500  mov     eax, ebx
0x18006a502  mov     rcx, [rsp+88h+var_38]
0x18006a507  xor     rcx, rsp; StackCookie
0x18006a50a  call    __security_check_cookie
0x18006a50f  add     rsp, 60h
0x18006a513  pop     r14
0x18006a515  pop     rdi
0x18006a516  pop     rsi
0x18006a517  pop     rbp
0x18006a518  pop     rbx
0x18006a519  retn
```
