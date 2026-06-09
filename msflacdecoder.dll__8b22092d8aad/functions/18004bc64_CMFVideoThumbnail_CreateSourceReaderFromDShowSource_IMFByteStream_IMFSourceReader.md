# CMFVideoThumbnail::CreateSourceReaderFromDShowSource(IMFByteStream *,IMFSourceReader * *)

- ea: `0x18004bc64`
- end: `0x18004bec0`
- name: `?CreateSourceReaderFromDShowSource@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAPEAUIMFSourceReader@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFByteStream *, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

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
- `0x18004bc64`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004bd32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004bd32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bd4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bdfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bd4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004bdfa`

## string_xrefs

- `0x18004bc96`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`
- `0x18004bda5`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`
- `0x18004be51`: `CMFVideoThumbnail::CreateSourceReaderFromDShowSource`

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
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-58h] BYREF
  struct IMFSourceResolver *ppv; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v22[16]; // [rsp+40h] [rbp-48h] BYREF

  ppv = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v20,
    "CMFVideoThumbnail::CreateSourceReaderFromDShowSource",
    521);
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  Instance = CoCreateInstance(&CLSID_DShowSourceResolver, 0, 1u, &IID_IMFSourceResolver, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(this, a2, ppv, a3);
    if ( Instance < 0 )
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
        if ( *((_DWORD *)v18 + 499) != Instance )
          CallStackContext::TraceFailure(v18, "CMFVideoThumbnail::CreateSourceReaderFromDShowSource", 526, Instance);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 50;
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
      if ( *((_DWORD *)v13 + 499) != Instance )
        CallStackContext::TraceFailure(v13, "CMFVideoThumbnail::CreateSourceReaderFromDShowSource", 524, Instance);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 49;
LABEL_26:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids,
        this,
        Instance);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004bc64  push    rbx
0x18004bc66  push    rbp
0x18004bc67  push    rsi
0x18004bc68  push    rdi
0x18004bc69  push    r14
0x18004bc6b  sub     rsp, 60h
0x18004bc6f  mov     rax, cs:__security_cookie
0x18004bc76  xor     rax, rsp
0x18004bc79  mov     [rsp+88h+var_38], rax
0x18004bc7e  mov     r14, r8
0x18004bc81  mov     [rsp+88h+var_50], 0
0x18004bc8a  mov     rbp, rdx
0x18004bc8d  mov     rsi, rcx
0x18004bc90  mov     r8d, 209h; int
0x18004bc96  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18004bc9d  lea     rcx, [rsp+88h+var_58]; this
0x18004bca2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004bca7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004bcae  cmp     byte ptr [rcx+8], 0
0x18004bcb2  jz      short loc_18004BD0A
0x18004bcb4  cmp     qword ptr [rsi+190h], 0
0x18004bcbc  jz      short loc_18004BD0A
0x18004bcbe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bcc3  mov     rcx, [rsi+190h]
0x18004bcca  mov     rdi, rax
0x18004bccd  mov     rdx, [rcx]
0x18004bcd0  mov     rax, [rdx+128h]
0x18004bcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcdc  mov     rcx, [rsi+190h]
0x18004bce3  mov     ebx, eax
0x18004bce5  mov     rdx, [rcx]
0x18004bce8  mov     rax, [rdx+118h]
0x18004bcef  lea     rdx, [rsp+88h+var_48]
0x18004bcf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcf9  movups  xmm0, xmmword ptr [rax]
0x18004bcfc  mov     [rdi+7E0h], ebx
0x18004bd02  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004bd0a  lea     rcx, [rsp+88h+var_50]
0x18004bd0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bd14  xor     edx, edx; pUnkOuter
0x18004bd16  lea     rax, [rsp+88h+var_50]
0x18004bd1b  lea     r9, IID_IMFSourceResolver; riid
0x18004bd22  mov     [rsp+88h+ppv], rax; ppv
0x18004bd27  lea     rcx, CLSID_DShowSourceResolver; rclsid
0x18004bd2e  lea     r8d, [rdx+1]; dwClsContext
0x18004bd32  call    cs:__imp_CoCreateInstance
0x18004bd38  mov     ebx, eax
0x18004bd3a  test    eax, eax
0x18004bd3c  jns     loc_18004BDD1
0x18004bd42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd49  test    rcx, rcx
0x18004bd4c  jnz     short loc_18004BD8F
0x18004bd4e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004bd54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd5b  mov     rcx, rax
0x18004bd5e  test    rax, rax
0x18004bd61  jz      short loc_18004BD81
0x18004bd63  mov     rax, [rax]
0x18004bd66  mov     edx, 7F0h
0x18004bd6b  mov     rax, [rax+8]
0x18004bd6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd74  test    eax, eax
0x18004bd76  jz      short loc_18004BD81
0x18004bd78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd7f  jmp     short loc_18004BD8F
0x18004bd81  lea     rcx, qword_18006EB20; this
0x18004bd88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bd8f  cmp     byte ptr [rcx+8], 0
0x18004bd93  jz      short loc_18004BDBA
0x18004bd95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004bd9a  cmp     [rax+7CCh], ebx
0x18004bda0  jz      short loc_18004BDBA
0x18004bda2  mov     r9d, ebx; int
0x18004bda5  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18004bdac  mov     r8d, 20Ch; int
0x18004bdb2  mov     rcx, rax; this
0x18004bdb5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004bdba  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004bdbf  cmp     al, 1
0x18004bdc1  jb      loc_18004BE92
0x18004bdc7  mov     edx, 31h ; '1'
0x18004bdcc  jmp     loc_18004BE74
0x18004bdd1  mov     r8, [rsp+88h+var_50]; struct IMFSourceResolver *
0x18004bdd6  mov     r9, r14; struct IMFSourceReader **
0x18004bdd9  mov     rdx, rbp; struct IMFByteStream *
0x18004bddc  mov     rcx, rsi; this
0x18004bddf  call    ?CreateAsyncSourceReaderUsingSourceResolver@CMFVideoThumbnail@@AEAAJPEAUIMFByteStream@@PEAUIMFSourceResolver@@PEAPEAUIMFSourceReader@@@Z; CMFVideoThumbnail::CreateAsyncSourceReaderUsingSourceResolver(IMFByteStream *,IMFSourceResolver *,IMFSourceReader * *)
0x18004bde4  mov     ebx, eax
0x18004bde6  test    eax, eax
0x18004bde8  jns     loc_18004BE92
0x18004bdee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004bdf5  test    rcx, rcx
0x18004bdf8  jnz     short loc_18004BE3B
0x18004bdfa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004be00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004be07  mov     rcx, rax
0x18004be0a  test    rax, rax
0x18004be0d  jz      short loc_18004BE2D
0x18004be0f  mov     rax, [rax]
0x18004be12  mov     edx, 7F0h
0x18004be17  mov     rax, [rax+8]
0x18004be1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be20  test    eax, eax
0x18004be22  jz      short loc_18004BE2D
0x18004be24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004be2b  jmp     short loc_18004BE3B
0x18004be2d  lea     rcx, qword_18006EB20; this
0x18004be34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004be3b  cmp     byte ptr [rcx+8], 0
0x18004be3f  jz      short loc_18004BE66
0x18004be41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004be46  cmp     [rax+7CCh], ebx
0x18004be4c  jz      short loc_18004BE66
0x18004be4e  mov     r9d, ebx; int
0x18004be51  lea     rdx, aCmfvideothumbn_18; "CMFVideoThumbnail::CreateSourceReaderFr"...
0x18004be58  mov     r8d, 20Eh; int
0x18004be5e  mov     rcx, rax; this
0x18004be61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004be66  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004be6b  cmp     al, 1
0x18004be6d  jb      short loc_18004BE92
0x18004be6f  mov     edx, 32h ; '2'
0x18004be74  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be7b  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004be82  mov     r9, rsi
0x18004be85  mov     dword ptr [rsp+88h+ppv], ebx
0x18004be89  mov     rcx, [rcx+10h]
0x18004be8d  call    WPP_SF_qd
0x18004be92  lea     rcx, [rsp+88h+var_58]; this
0x18004be97  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004be9c  lea     rcx, [rsp+88h+var_50]
0x18004bea1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bea6  mov     eax, ebx
0x18004bea8  mov     rcx, [rsp+88h+var_38]
0x18004bead  xor     rcx, rsp; StackCookie
0x18004beb0  call    __security_check_cookie
0x18004beb5  add     rsp, 60h
0x18004beb9  pop     r14
0x18004bebb  pop     rdi
0x18004bebc  pop     rsi
0x18004bebd  pop     rbp
0x18004bebe  pop     rbx
0x18004bebf  retn
```
