# CMFVideoThumbnail::CreateAsyncSourceReader(IMFMediaSource *,bool,IMFSourceReader * *)

- ea: `0x1800c1b20`
- end: `0x1800c2271`
- name: `?CreateAsyncSourceReader@CMFVideoThumbnail@@AEAAJPEAUIMFMediaSource@@_NPEAPEAUIMFSourceReader@@@Z`
- size: `1873`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaSource *, bool, struct IMFSourceReader **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b554c`
- `0x18016339c`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x1800790a8`
- `0x180079680`
- `0x1800c1b20`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1c03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1daf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1e6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1f29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1fed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c20c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c218d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1c03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1daf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1e6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1f29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c1fed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c20c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800c218d`
- `MFPlat!MFCreateAttributes` at `0x1800c1be1`
- `MFPlat!MFCreateAttributes` at `0x1800c1be1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c209e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c209e`

## string_xrefs

- `0x1800c1b4e`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800c1c60`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800c1d49`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800c1e0c`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800c1ecb`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800c1f86`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800c204a`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800c211d`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800c21ea`: `CMFVideoThumbnail::CreateAsyncSourceReader`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CreateAsyncSourceReader(
        CMFVideoThumbnail *this,
        struct IMFMediaSource *a2,
        char a3,
        struct IMFSourceReader **a4)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  __int128 v10; // xmm0
  __int64 v11; // rdx
  HRESULT v12; // edi
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rdx
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  _BYTE v47[8]; // [rsp+40h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v50[16]; // [rsp+58h] [rbp-18h] BYREF

  ppMFAttributes = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v47,
    "CMFVideoThumbnail::CreateAsyncSourceReader",
    470);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v50);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  v12 = MFCreateAttributes(&ppMFAttributes, 8u);
  if ( v12 < 0 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != v12 )
        CallStackContext::TraceFailure(v15, "CMFVideoThumbnail::CreateAsyncSourceReader", 470, v12);
    }
    if ( g_wppLevels )
    {
      v16 = 37;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v12);
      goto LABEL_97;
    }
    goto LABEL_97;
  }
  v12 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, unsigned __int64))ppMFAttributes->lpVtbl->SetUnknown)(
          ppMFAttributes,
          &MF_SOURCE_READER_ASYNC_CALLBACK,
          ((unsigned __int64)this + 16) & -(__int64)(this != 0));
  if ( v12 >= 0 )
  {
    v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING,
            1);
    if ( v12 < 0 )
    {
      v22 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != v12 )
          CallStackContext::TraceFailure(v24, "CMFVideoThumbnail::CreateAsyncSourceReader", 476, v12);
      }
      if ( g_wppLevels )
      {
        v16 = 39;
        goto LABEL_15;
      }
      goto LABEL_97;
    }
    v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUnknown)(
            ppMFAttributes,
            MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE,
            *((_QWORD *)this + 50));
    if ( v12 < 0 )
    {
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != v12 )
          CallStackContext::TraceFailure(v28, "CMFVideoThumbnail::CreateAsyncSourceReader", 479, v12);
      }
      if ( g_wppLevels )
      {
        v16 = 40;
        goto LABEL_15;
      }
      goto LABEL_97;
    }
    v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS,
            1);
    if ( v12 < 0 )
    {
      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
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
        if ( *((_DWORD *)v32 + 499) != v12 )
          CallStackContext::TraceFailure(v32, "CMFVideoThumbnail::CreateAsyncSourceReader", 482, v12);
      }
      if ( g_wppLevels )
      {
        v16 = 41;
        goto LABEL_15;
      }
      goto LABEL_97;
    }
    if ( a3 )
    {
      v12 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
              ppMFAttributes,
              &MF_SOURCE_READER_DISCONNECT_MEDIASOURCE_ON_SHUTDOWN,
              1);
      if ( v12 < 0 )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != v12 )
            CallStackContext::TraceFailure(v36, "CMFVideoThumbnail::CreateAsyncSourceReader", 487, v12);
        }
        if ( g_wppLevels )
        {
          v16 = 42;
          goto LABEL_15;
        }
        goto LABEL_97;
      }
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v12 = CoCreateInstance(&CLSID_MFReadWriteClassFactory, 0, 1u, &GUID_e7fe2e12_661c_40da_92f9_4f002ab67627, &ppv);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, GUID *, struct IMFMediaSource *, IMFAttributes *, GUID *, struct IMFSourceReader **))(*(_QWORD *)ppv + 32LL))(
              ppv,
              &CLSID_MFSourceReader,
              a2,
              ppMFAttributes,
              &GUID_70ae66f2_c809_4e4f_8915_bdcb406b7993,
              a4);
      if ( v12 >= 0 )
      {
        v12 = 0;
        goto LABEL_96;
      }
      v43 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v43 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v43 + 8) )
      {
        v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
        if ( *((_DWORD *)v45 + 499) != v12 )
          CallStackContext::TraceFailure(v45, "CMFVideoThumbnail::CreateAsyncSourceReader", 493, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v41 = 44;
    }
    else
    {
      v38 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != v12 )
          CallStackContext::TraceFailure(v40, "CMFVideoThumbnail::CreateAsyncSourceReader", 492, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v41 = 43;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v41, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v12);
LABEL_96:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    goto LABEL_97;
  }
  v18 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != v12 )
      CallStackContext::TraceFailure(v20, "CMFVideoThumbnail::CreateAsyncSourceReader", 473, v12);
  }
  if ( g_wppLevels )
  {
    v16 = 38;
    goto LABEL_15;
  }
LABEL_97:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v47);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800c1b20  mov     [rsp-38h+arg_10], rbx
0x1800c1b25  push    rbp
0x1800c1b26  push    rsi
0x1800c1b27  push    rdi
0x1800c1b28  push    r12
0x1800c1b2a  push    r13
0x1800c1b2c  push    r14
0x1800c1b2e  push    r15
0x1800c1b30  mov     rbp, rsp
0x1800c1b33  sub     rsp, 70h
0x1800c1b37  mov     rax, cs:__security_cookie
0x1800c1b3e  xor     rax, rsp
0x1800c1b41  mov     [rbp+var_8], rax
0x1800c1b45  mov     r14b, r8b
0x1800c1b48  mov     r15, rdx
0x1800c1b4b  mov     rsi, rcx
0x1800c1b4e  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800c1b55  xor     r13d, r13d
0x1800c1b58  lea     rcx, [rbp+var_30]; this
0x1800c1b5c  mov     r8d, 1D6h; int
0x1800c1b62  mov     [rbp+ppMFAttributes], r13
0x1800c1b66  mov     r12, r9
0x1800c1b69  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800c1b6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800c1b75  cmp     [rcx+8], r13b
0x1800c1b79  jz      short loc_1800C1BCF
0x1800c1b7b  cmp     [rsi+190h], r13
0x1800c1b82  jz      short loc_1800C1BCF
0x1800c1b84  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1b89  mov     rcx, [rsi+190h]
0x1800c1b90  mov     rdi, rax
0x1800c1b93  mov     rdx, [rcx]
0x1800c1b96  mov     rax, [rdx+128h]
0x1800c1b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1ba2  mov     rcx, [rsi+190h]
0x1800c1ba9  mov     ebx, eax
0x1800c1bab  mov     rdx, [rcx]
0x1800c1bae  mov     rax, [rdx+118h]
0x1800c1bb5  lea     rdx, [rbp+var_18]
0x1800c1bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1bbe  movups  xmm0, xmmword ptr [rax]
0x1800c1bc1  mov     [rdi+7E0h], ebx
0x1800c1bc7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800c1bcf  lea     rcx, [rbp+ppMFAttributes]
0x1800c1bd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c1bd8  mov     edx, 8; cInitialSize
0x1800c1bdd  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800c1be1  call    cs:__imp_MFCreateAttributes
0x1800c1be8  nop     dword ptr [rax+rax+00h]
0x1800c1bed  mov     edi, eax
0x1800c1bef  test    eax, eax
0x1800c1bf1  jns     loc_1800C1CAC
0x1800c1bf7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1bfe  test    rcx, rcx
0x1800c1c01  jnz     short loc_1800C1C4A
0x1800c1c03  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c1c0a  nop     dword ptr [rax+rax+00h]
0x1800c1c0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1c16  mov     rcx, rax
0x1800c1c19  test    rax, rax
0x1800c1c1c  jz      short loc_1800C1C3C
0x1800c1c1e  mov     rax, [rax]
0x1800c1c21  mov     edx, 7F0h
0x1800c1c26  mov     rax, [rax+8]
0x1800c1c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1c2f  test    eax, eax
0x1800c1c31  jz      short loc_1800C1C3C
0x1800c1c33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1c3a  jmp     short loc_1800C1C4A
0x1800c1c3c  lea     rcx, qword_1801B97E0; this
0x1800c1c43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1c4a  cmp     [rcx+8], r13b
0x1800c1c4e  jz      short loc_1800C1C75
0x1800c1c50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1c55  cmp     [rax+7CCh], edi
0x1800c1c5b  jz      short loc_1800C1C75
0x1800c1c5d  mov     r9d, edi; int
0x1800c1c60  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800c1c67  mov     r8d, 1D6h; int
0x1800c1c6d  mov     rcx, rax; this
0x1800c1c70  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c1c75  mov     ebx, 1
0x1800c1c7a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800c1c80  jb      loc_1800C2238
0x1800c1c86  lea     edx, [rbx+24h]
0x1800c1c89  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1c90  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x1800c1c97  mov     r9, rsi
0x1800c1c9a  mov     dword ptr [rsp+70h+ppv], edi
0x1800c1c9e  mov     rcx, [rcx+10h]
0x1800c1ca2  call    WPP_SF_qD
0x1800c1ca7  jmp     loc_1800C2238
0x1800c1cac  mov     rcx, [rbp+ppMFAttributes]
0x1800c1cb0  lea     rdx, [rsi+10h]
0x1800c1cb4  mov     rax, rsi
0x1800c1cb7  neg     rax
0x1800c1cba  mov     r9, [rcx]
0x1800c1cbd  sbb     r8, r8
0x1800c1cc0  and     r8, rdx
0x1800c1cc3  lea     rdx, MF_SOURCE_READER_ASYNC_CALLBACK
0x1800c1cca  mov     rax, [r9+0D8h]
0x1800c1cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1cd6  mov     edi, eax
0x1800c1cd8  test    eax, eax
0x1800c1cda  jns     loc_1800C1D77
0x1800c1ce0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1ce7  test    rcx, rcx
0x1800c1cea  jnz     short loc_1800C1D33
0x1800c1cec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c1cf3  nop     dword ptr [rax+rax+00h]
0x1800c1cf8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1cff  mov     rcx, rax
0x1800c1d02  test    rax, rax
0x1800c1d05  jz      short loc_1800C1D25
0x1800c1d07  mov     rax, [rax]
0x1800c1d0a  mov     edx, 7F0h
0x1800c1d0f  mov     rax, [rax+8]
0x1800c1d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d18  test    eax, eax
0x1800c1d1a  jz      short loc_1800C1D25
0x1800c1d1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1d23  jmp     short loc_1800C1D33
0x1800c1d25  lea     rcx, qword_1801B97E0; this
0x1800c1d2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1d33  cmp     [rcx+8], r13b
0x1800c1d37  jz      short loc_1800C1D5E
0x1800c1d39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1d3e  cmp     [rax+7CCh], edi
0x1800c1d44  jz      short loc_1800C1D5E
0x1800c1d46  mov     r9d, edi; int
0x1800c1d49  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800c1d50  mov     r8d, 1D9h; int
0x1800c1d56  mov     rcx, rax; this
0x1800c1d59  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c1d5e  mov     ebx, 1
0x1800c1d63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800c1d69  jb      loc_1800C2238
0x1800c1d6f  lea     edx, [rbx+25h]
0x1800c1d72  jmp     loc_1800C1C89
0x1800c1d77  mov     rcx, [rbp+ppMFAttributes]
0x1800c1d7b  lea     rdx, MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING
0x1800c1d82  mov     ebx, 1
0x1800c1d87  mov     r8d, ebx
0x1800c1d8a  mov     rax, [rcx]
0x1800c1d8d  mov     rax, [rax+0A8h]
0x1800c1d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d99  mov     edi, eax
0x1800c1d9b  test    eax, eax
0x1800c1d9d  jns     loc_1800C1E37
0x1800c1da3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1daa  test    rcx, rcx
0x1800c1dad  jnz     short loc_1800C1DF6
0x1800c1daf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c1db6  nop     dword ptr [rax+rax+00h]
0x1800c1dbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1dc2  mov     rcx, rax
0x1800c1dc5  test    rax, rax
0x1800c1dc8  jz      short loc_1800C1DE8
0x1800c1dca  mov     rax, [rax]
0x1800c1dcd  mov     edx, 7F0h
0x1800c1dd2  mov     rax, [rax+8]
0x1800c1dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1ddb  test    eax, eax
0x1800c1ddd  jz      short loc_1800C1DE8
0x1800c1ddf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1de6  jmp     short loc_1800C1DF6
0x1800c1de8  lea     rcx, qword_1801B97E0; this
0x1800c1def  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1df6  cmp     [rcx+8], r13b
0x1800c1dfa  jz      short loc_1800C1E21
0x1800c1dfc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1e01  cmp     [rax+7CCh], edi
0x1800c1e07  jz      short loc_1800C1E21
0x1800c1e09  mov     r9d, edi; int
0x1800c1e0c  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800c1e13  mov     r8d, 1DCh; int
0x1800c1e19  mov     rcx, rax; this
0x1800c1e1c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c1e21  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800c1e27  jb      loc_1800C2238
0x1800c1e2d  mov     edx, 27h ; '''
0x1800c1e32  jmp     loc_1800C1C89
0x1800c1e37  mov     rcx, [rbp+ppMFAttributes]
0x1800c1e3b  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x1800c1e42  mov     r8, [rsi+190h]
0x1800c1e49  mov     rax, [rcx]
0x1800c1e4c  mov     rax, [rax+0D8h]
0x1800c1e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1e58  mov     edi, eax
0x1800c1e5a  test    eax, eax
0x1800c1e5c  jns     loc_1800C1EF6
0x1800c1e62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1e69  test    rcx, rcx
0x1800c1e6c  jnz     short loc_1800C1EB5
0x1800c1e6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c1e75  nop     dword ptr [rax+rax+00h]
0x1800c1e7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1e81  mov     rcx, rax
0x1800c1e84  test    rax, rax
0x1800c1e87  jz      short loc_1800C1EA7
0x1800c1e89  mov     rax, [rax]
0x1800c1e8c  mov     edx, 7F0h
0x1800c1e91  mov     rax, [rax+8]
0x1800c1e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1e9a  test    eax, eax
0x1800c1e9c  jz      short loc_1800C1EA7
0x1800c1e9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1ea5  jmp     short loc_1800C1EB5
0x1800c1ea7  lea     rcx, qword_1801B97E0; this
0x1800c1eae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1eb5  cmp     [rcx+8], r13b
0x1800c1eb9  jz      short loc_1800C1EE0
0x1800c1ebb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1ec0  cmp     [rax+7CCh], edi
0x1800c1ec6  jz      short loc_1800C1EE0
0x1800c1ec8  mov     r9d, edi; int
0x1800c1ecb  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800c1ed2  mov     r8d, 1DFh; int
0x1800c1ed8  mov     rcx, rax; this
0x1800c1edb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c1ee0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800c1ee6  jb      loc_1800C2238
0x1800c1eec  mov     edx, 28h ; '('
0x1800c1ef1  jmp     loc_1800C1C89
0x1800c1ef6  mov     rcx, [rbp+ppMFAttributes]
0x1800c1efa  lea     rdx, MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS
0x1800c1f01  mov     r8d, ebx
0x1800c1f04  mov     rax, [rcx]
0x1800c1f07  mov     rax, [rax+0A8h]
0x1800c1f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1f13  mov     edi, eax
0x1800c1f15  test    eax, eax
0x1800c1f17  jns     loc_1800C1FB1
0x1800c1f1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1f24  test    rcx, rcx
0x1800c1f27  jnz     short loc_1800C1F70
0x1800c1f29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c1f30  nop     dword ptr [rax+rax+00h]
0x1800c1f35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1f3c  mov     rcx, rax
0x1800c1f3f  test    rax, rax
0x1800c1f42  jz      short loc_1800C1F62
0x1800c1f44  mov     rax, [rax]
0x1800c1f47  mov     edx, 7F0h
0x1800c1f4c  mov     rax, [rax+8]
0x1800c1f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1f55  test    eax, eax
0x1800c1f57  jz      short loc_1800C1F62
0x1800c1f59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1f60  jmp     short loc_1800C1F70
0x1800c1f62  lea     rcx, qword_1801B97E0; this
0x1800c1f69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1f70  cmp     [rcx+8], r13b
0x1800c1f74  jz      short loc_1800C1F9B
0x1800c1f76  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c1f7b  cmp     [rax+7CCh], edi
0x1800c1f81  jz      short loc_1800C1F9B
0x1800c1f83  mov     r9d, edi; int
0x1800c1f86  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800c1f8d  mov     r8d, 1E2h; int
0x1800c1f93  mov     rcx, rax; this
0x1800c1f96  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800c1f9b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800c1fa1  jb      loc_1800C2238
0x1800c1fa7  mov     edx, 29h ; ')'
0x1800c1fac  jmp     loc_1800C1C89
0x1800c1fb1  test    r14b, r14b
0x1800c1fb4  jz      loc_1800C2075
0x1800c1fba  mov     rcx, [rbp+ppMFAttributes]
0x1800c1fbe  lea     rdx, MF_SOURCE_READER_DISCONNECT_MEDIASOURCE_ON_SHUTDOWN
0x1800c1fc5  mov     r8d, ebx
0x1800c1fc8  mov     rax, [rcx]
0x1800c1fcb  mov     rax, [rax+0A8h]
0x1800c1fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1fd7  mov     edi, eax
0x1800c1fd9  test    eax, eax
0x1800c1fdb  jns     loc_1800C2075
0x1800c1fe1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c1fe8  test    rcx, rcx
0x1800c1feb  jnz     short loc_1800C2034
0x1800c1fed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800c1ff4  nop     dword ptr [rax+rax+00h]
0x1800c1ff9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2000  mov     rcx, rax
0x1800c2003  test    rax, rax
0x1800c2006  jz      short loc_1800C2026
0x1800c2008  mov     rax, [rax]
0x1800c200b  mov     edx, 7F0h
0x1800c2010  mov     rax, [rax+8]
0x1800c2014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2019  test    eax, eax
0x1800c201b  jz      short loc_1800C2026
0x1800c201d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2024  jmp     short loc_1800C2034
0x1800c2026  lea     rcx, qword_1801B97E0; this
0x1800c202d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800c2034  cmp     [rcx+8], r13b
0x1800c2038  jz      short loc_1800C205F
0x1800c203a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800c203f  cmp     [rax+7CCh], edi
  ... truncated ...
```
