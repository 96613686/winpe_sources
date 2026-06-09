# CMFVideoThumbnail::CreateAsyncSourceReader(IMFMediaSource *,bool,IMFSourceReader * *)

- ea: `0x18004a4d8`
- end: `0x18004ab10`
- name: `?CreateAsyncSourceReader@CMFVideoThumbnail@@AEAAJPEAUIMFMediaSource@@_NPEAPEAUIMFSourceReader@@@Z`
- size: `1592`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaSource *, bool, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ab18`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180048710`
- `0x18004a4d8`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a960`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004a960`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a5b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a692`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a74c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a802`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a8b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a97c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004aa40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a5b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a692`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a74c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a802`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a8b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a97c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004aa40`
- `MFPlat!MFCreateAttributes` at `0x18004a596`
- `MFPlat!MFCreateAttributes` at `0x18004a596`

## string_xrefs

- `0x18004a506`: `CMFVideoThumbnail::CreateAsyncSourceReader`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CreateAsyncSourceReader(
        CMFVideoThumbnail *this,
        struct IMFMediaSource *a2,
        __int64 a3,
        struct IMFSourceReader **a4)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v8; // ebx
  __int128 v9; // xmm0
  __int64 v10; // rdx
  HRESULT v11; // edi
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  _BYTE v42[8]; // [rsp+40h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v45[16]; // [rsp+58h] [rbp-18h] BYREF

  ppMFAttributes = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v42,
    "CMFVideoThumbnail::CreateAsyncSourceReader",
    470);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v9 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v45);
    *((_DWORD *)ThreadRelativeContext + 504) = v8;
    *((_OWORD *)ThreadRelativeContext + 125) = v9;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  v11 = MFCreateAttributes(&ppMFAttributes, 8u);
  if ( v11 < 0 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v11 )
        CallStackContext::TraceFailure(v14, "CMFVideoThumbnail::CreateAsyncSourceReader", 470, v11);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v15 = 37;
LABEL_15:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v11);
      goto LABEL_85;
    }
    goto LABEL_85;
  }
  v11 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, unsigned __int64))ppMFAttributes->lpVtbl->SetUnknown)(
          ppMFAttributes,
          &MF_SOURCE_READER_ASYNC_CALLBACK,
          ((unsigned __int64)this + 16) & -(__int64)(this != 0));
  if ( v11 >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING,
            1);
    if ( v11 < 0 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != v11 )
          CallStackContext::TraceFailure(v23, "CMFVideoThumbnail::CreateAsyncSourceReader", 476, v11);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v15 = 39;
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    v11 = ((__int64 (__fastcall *)(IMFAttributes *, void *, _QWORD))ppMFAttributes->lpVtbl->SetUnknown)(
            ppMFAttributes,
            &MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE,
            *((_QWORD *)this + 50));
    if ( v11 < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != v11 )
          CallStackContext::TraceFailure(v27, "CMFVideoThumbnail::CreateAsyncSourceReader", 479, v11);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v15 = 40;
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    v11 = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS,
            1);
    if ( v11 < 0 )
    {
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != v11 )
          CallStackContext::TraceFailure(v31, "CMFVideoThumbnail::CreateAsyncSourceReader", 482, v11);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v15 = 41;
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v11 = CoCreateInstance(&CLSID_MFReadWriteClassFactory, 0, 1u, &GUID_e7fe2e12_661c_40da_92f9_4f002ab67627, &ppv);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, GUID *, struct IMFMediaSource *, IMFAttributes *, GUID *, struct IMFSourceReader **))(*(_QWORD *)ppv + 32LL))(
              ppv,
              &CLSID_MFSourceReader,
              a2,
              ppMFAttributes,
              &GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993,
              a4);
      if ( v11 >= 0 )
      {
        v11 = 0;
        goto LABEL_84;
      }
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != v11 )
          CallStackContext::TraceFailure(v40, "CMFVideoThumbnail::CreateAsyncSourceReader", 493, v11);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_84;
      v36 = 44;
    }
    else
    {
      v33 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)v35 + 499) != v11 )
          CallStackContext::TraceFailure(v35, "CMFVideoThumbnail::CreateAsyncSourceReader", 492, v11);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_84;
      v36 = 43;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v11);
LABEL_84:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    goto LABEL_85;
  }
  v17 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
    CallStackTracing::s_wpInstance = v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v17 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
    if ( *((_DWORD *)v19 + 499) != v11 )
      CallStackContext::TraceFailure(v19, "CMFVideoThumbnail::CreateAsyncSourceReader", 473, v11);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v15 = 38;
    goto LABEL_15;
  }
LABEL_85:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v42);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004a4d8  push    rbp
0x18004a4da  push    rbx
0x18004a4db  push    rsi
0x18004a4dc  push    rdi
0x18004a4dd  push    r13
0x18004a4df  push    r14
0x18004a4e1  push    r15
0x18004a4e3  mov     rbp, rsp
0x18004a4e6  sub     rsp, 70h
0x18004a4ea  mov     rax, cs:__security_cookie
0x18004a4f1  xor     rax, rsp
0x18004a4f4  mov     [rbp+var_8], rax
0x18004a4f8  mov     r14, rdx
0x18004a4fb  mov     [rbp+ppMFAttributes], 0
0x18004a503  mov     rsi, rcx
0x18004a506  lea     r13, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x18004a50d  mov     rdx, r13; char *
0x18004a510  lea     rcx, [rbp+var_30]; this
0x18004a514  mov     r8d, 1D6h; int
0x18004a51a  mov     r15, r9
0x18004a51d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004a522  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004a529  cmp     byte ptr [rcx+8], 0
0x18004a52d  jz      short loc_18004A584
0x18004a52f  cmp     qword ptr [rsi+190h], 0
0x18004a537  jz      short loc_18004A584
0x18004a539  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a53e  mov     rcx, [rsi+190h]
0x18004a545  mov     rdi, rax
0x18004a548  mov     rdx, [rcx]
0x18004a54b  mov     rax, [rdx+128h]
0x18004a552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a557  mov     rcx, [rsi+190h]
0x18004a55e  mov     ebx, eax
0x18004a560  mov     rdx, [rcx]
0x18004a563  mov     rax, [rdx+118h]
0x18004a56a  lea     rdx, [rbp+var_18]
0x18004a56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a573  movups  xmm0, xmmword ptr [rax]
0x18004a576  mov     [rdi+7E0h], ebx
0x18004a57c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004a584  lea     rcx, [rbp+ppMFAttributes]
0x18004a588  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a58d  mov     edx, 8; cInitialSize
0x18004a592  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18004a596  call    cs:__imp_MFCreateAttributes
0x18004a59c  mov     edi, eax
0x18004a59e  test    eax, eax
0x18004a5a0  jns     loc_18004A652
0x18004a5a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5ad  test    rcx, rcx
0x18004a5b0  jnz     short loc_18004A5F3
0x18004a5b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a5b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5bf  mov     rcx, rax
0x18004a5c2  test    rax, rax
0x18004a5c5  jz      short loc_18004A5E5
0x18004a5c7  mov     rax, [rax]
0x18004a5ca  mov     edx, 7F0h
0x18004a5cf  mov     rax, [rax+8]
0x18004a5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5d8  test    eax, eax
0x18004a5da  jz      short loc_18004A5E5
0x18004a5dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5e3  jmp     short loc_18004A5F3
0x18004a5e5  lea     rcx, qword_18006EB20; this
0x18004a5ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5f3  cmp     byte ptr [rcx+8], 0
0x18004a5f7  jz      short loc_18004A61A
0x18004a5f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a5fe  cmp     [rax+7CCh], edi
0x18004a604  jz      short loc_18004A61A
0x18004a606  mov     r9d, edi; int
0x18004a609  mov     r8d, 1D6h; int
0x18004a60f  mov     rdx, r13; char *
0x18004a612  mov     rcx, rax; this
0x18004a615  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a61a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a61f  mov     ebx, 1
0x18004a624  cmp     al, bl
0x18004a626  jb      loc_18004AAE1
0x18004a62c  lea     edx, [rbx+24h]
0x18004a62f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a636  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004a63d  mov     r9, rsi
0x18004a640  mov     dword ptr [rsp+70h+ppv], edi
0x18004a644  mov     rcx, [rcx+10h]
0x18004a648  call    WPP_SF_qd
0x18004a64d  jmp     loc_18004AAE1
0x18004a652  mov     rcx, [rbp+ppMFAttributes]
0x18004a656  lea     rdx, [rsi+10h]
0x18004a65a  mov     rax, rsi
0x18004a65d  neg     rax
0x18004a660  mov     r9, [rcx]
0x18004a663  sbb     r8, r8
0x18004a666  and     r8, rdx
0x18004a669  lea     rdx, MF_SOURCE_READER_ASYNC_CALLBACK
0x18004a670  mov     rax, [r9+0D8h]
0x18004a677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a67c  mov     edi, eax
0x18004a67e  test    eax, eax
0x18004a680  jns     loc_18004A714
0x18004a686  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a68d  test    rcx, rcx
0x18004a690  jnz     short loc_18004A6D3
0x18004a692  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a698  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a69f  mov     rcx, rax
0x18004a6a2  test    rax, rax
0x18004a6a5  jz      short loc_18004A6C5
0x18004a6a7  mov     rax, [rax]
0x18004a6aa  mov     edx, 7F0h
0x18004a6af  mov     rax, [rax+8]
0x18004a6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6b8  test    eax, eax
0x18004a6ba  jz      short loc_18004A6C5
0x18004a6bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a6c3  jmp     short loc_18004A6D3
0x18004a6c5  lea     rcx, qword_18006EB20; this
0x18004a6cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a6d3  cmp     byte ptr [rcx+8], 0
0x18004a6d7  jz      short loc_18004A6FA
0x18004a6d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a6de  cmp     [rax+7CCh], edi
0x18004a6e4  jz      short loc_18004A6FA
0x18004a6e6  mov     r9d, edi; int
0x18004a6e9  mov     r8d, 1D9h; int
0x18004a6ef  mov     rdx, r13; char *
0x18004a6f2  mov     rcx, rax; this
0x18004a6f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a6fa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a6ff  mov     ebx, 1
0x18004a704  cmp     al, bl
0x18004a706  jb      loc_18004AAE1
0x18004a70c  lea     edx, [rbx+25h]
0x18004a70f  jmp     loc_18004A62F
0x18004a714  mov     rcx, [rbp+ppMFAttributes]
0x18004a718  lea     rdx, MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING
0x18004a71f  mov     ebx, 1
0x18004a724  mov     r8d, ebx
0x18004a727  mov     rax, [rcx]
0x18004a72a  mov     rax, [rax+0A8h]
0x18004a731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a736  mov     edi, eax
0x18004a738  test    eax, eax
0x18004a73a  jns     loc_18004A7CB
0x18004a740  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a747  test    rcx, rcx
0x18004a74a  jnz     short loc_18004A78D
0x18004a74c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a752  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a759  mov     rcx, rax
0x18004a75c  test    rax, rax
0x18004a75f  jz      short loc_18004A77F
0x18004a761  mov     rax, [rax]
0x18004a764  mov     edx, 7F0h
0x18004a769  mov     rax, [rax+8]
0x18004a76d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a772  test    eax, eax
0x18004a774  jz      short loc_18004A77F
0x18004a776  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a77d  jmp     short loc_18004A78D
0x18004a77f  lea     rcx, qword_18006EB20; this
0x18004a786  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a78d  cmp     byte ptr [rcx+8], 0
0x18004a791  jz      short loc_18004A7B4
0x18004a793  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a798  cmp     [rax+7CCh], edi
0x18004a79e  jz      short loc_18004A7B4
0x18004a7a0  mov     r9d, edi; int
0x18004a7a3  mov     r8d, 1DCh; int
0x18004a7a9  mov     rdx, r13; char *
0x18004a7ac  mov     rcx, rax; this
0x18004a7af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a7b4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a7b9  cmp     al, bl
0x18004a7bb  jb      loc_18004AAE1
0x18004a7c1  mov     edx, 27h ; '''
0x18004a7c6  jmp     loc_18004A62F
0x18004a7cb  mov     rcx, [rbp+ppMFAttributes]
0x18004a7cf  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x18004a7d6  mov     r8, [rsi+190h]
0x18004a7dd  mov     rax, [rcx]
0x18004a7e0  mov     rax, [rax+0D8h]
0x18004a7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7ec  mov     edi, eax
0x18004a7ee  test    eax, eax
0x18004a7f0  jns     loc_18004A881
0x18004a7f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a7fd  test    rcx, rcx
0x18004a800  jnz     short loc_18004A843
0x18004a802  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a808  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a80f  mov     rcx, rax
0x18004a812  test    rax, rax
0x18004a815  jz      short loc_18004A835
0x18004a817  mov     rax, [rax]
0x18004a81a  mov     edx, 7F0h
0x18004a81f  mov     rax, [rax+8]
0x18004a823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a828  test    eax, eax
0x18004a82a  jz      short loc_18004A835
0x18004a82c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a833  jmp     short loc_18004A843
0x18004a835  lea     rcx, qword_18006EB20; this
0x18004a83c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a843  cmp     byte ptr [rcx+8], 0
0x18004a847  jz      short loc_18004A86A
0x18004a849  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a84e  cmp     [rax+7CCh], edi
0x18004a854  jz      short loc_18004A86A
0x18004a856  mov     r9d, edi; int
0x18004a859  mov     r8d, 1DFh; int
0x18004a85f  mov     rdx, r13; char *
0x18004a862  mov     rcx, rax; this
0x18004a865  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a86a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a86f  cmp     al, bl
0x18004a871  jb      loc_18004AAE1
0x18004a877  mov     edx, 28h ; '('
0x18004a87c  jmp     loc_18004A62F
0x18004a881  mov     rcx, [rbp+ppMFAttributes]
0x18004a885  lea     rdx, MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS
0x18004a88c  mov     r8d, ebx
0x18004a88f  mov     rax, [rcx]
0x18004a892  mov     rax, [rax+0A8h]
0x18004a899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a89e  mov     edi, eax
0x18004a8a0  test    eax, eax
0x18004a8a2  jns     loc_18004A933
0x18004a8a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a8af  test    rcx, rcx
0x18004a8b2  jnz     short loc_18004A8F5
0x18004a8b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a8ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a8c1  mov     rcx, rax
0x18004a8c4  test    rax, rax
0x18004a8c7  jz      short loc_18004A8E7
0x18004a8c9  mov     rax, [rax]
0x18004a8cc  mov     edx, 7F0h
0x18004a8d1  mov     rax, [rax+8]
0x18004a8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8da  test    eax, eax
0x18004a8dc  jz      short loc_18004A8E7
0x18004a8de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a8e5  jmp     short loc_18004A8F5
0x18004a8e7  lea     rcx, qword_18006EB20; this
0x18004a8ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a8f5  cmp     byte ptr [rcx+8], 0
0x18004a8f9  jz      short loc_18004A91C
0x18004a8fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a900  cmp     [rax+7CCh], edi
0x18004a906  jz      short loc_18004A91C
0x18004a908  mov     r9d, edi; int
0x18004a90b  mov     r8d, 1E2h; int
0x18004a911  mov     rdx, r13; char *
0x18004a914  mov     rcx, rax; this
0x18004a917  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a91c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004a921  cmp     al, bl
0x18004a923  jb      loc_18004AAE1
0x18004a929  mov     edx, 29h ; ')'
0x18004a92e  jmp     loc_18004A62F
0x18004a933  lea     rcx, [rbp+var_20]
0x18004a937  mov     [rbp+var_20], 0
0x18004a93f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a944  lea     rax, [rbp+var_20]
0x18004a948  mov     r8d, ebx; dwClsContext
0x18004a94b  lea     r9, _GUID_e7fe2e12_661c_40da_92f9_4f002ab67627; riid
0x18004a952  mov     [rsp+70h+ppv], rax; ppv
0x18004a957  xor     edx, edx; pUnkOuter
0x18004a959  lea     rcx, CLSID_MFReadWriteClassFactory; rclsid
0x18004a960  call    cs:__imp_CoCreateInstance
0x18004a966  mov     edi, eax
0x18004a968  test    eax, eax
0x18004a96a  jns     loc_18004A9FB
0x18004a970  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a977  test    rcx, rcx
0x18004a97a  jnz     short loc_18004A9BD
0x18004a97c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a982  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a989  mov     rcx, rax
0x18004a98c  test    rax, rax
0x18004a98f  jz      short loc_18004A9AF
0x18004a991  mov     rax, [rax]
0x18004a994  mov     edx, 7F0h
0x18004a999  mov     rax, [rax+8]
0x18004a99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9a2  test    eax, eax
0x18004a9a4  jz      short loc_18004A9AF
0x18004a9a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a9ad  jmp     short loc_18004A9BD
0x18004a9af  lea     rcx, qword_18006EB20; this
0x18004a9b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a9bd  cmp     byte ptr [rcx+8], 0
0x18004a9c1  jz      short loc_18004A9E4
0x18004a9c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a9c8  cmp     [rax+7CCh], edi
0x18004a9ce  jz      short loc_18004A9E4
0x18004a9d0  mov     r9d, edi; int
  ... truncated ...
```
