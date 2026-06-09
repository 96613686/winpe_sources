# CMFVideoThumbnail::CreateAsyncSourceReader(IMFMediaSource *,bool,IMFSourceReader * *)

- ea: `0x180065ec8`
- end: `0x1800664f9`
- name: `?CreateAsyncSourceReader@CMFVideoThumbnail@@AEAAJPEAUIMFMediaSource@@_NPEAPEAUIMFSourceReader@@@Z`
- size: `1585`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaSource *, bool, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180066500`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180065ec8`
- `0x180069a78`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006634b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006634b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065fa2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066081`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006613a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800661ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800662a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066367`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006642a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180065fa2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066081`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006613a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800661ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800662a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066367`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006642a`
- `MFPlat!MFCreateAttributes` at `0x180065f86`
- `MFPlat!MFCreateAttributes` at `0x180065f86`

## string_xrefs

- `0x180065ef6`: `CMFVideoThumbnail::CreateAsyncSourceReader`

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
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  _BYTE v56[8]; // [rsp+40h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v59[16]; // [rsp+58h] [rbp-18h] BYREF

  ppMFAttributes = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v56,
    "CMFVideoThumbnail::CreateAsyncSourceReader",
    470);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v9 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                      *((_QWORD *)this + 50),
                      v59);
    *((_DWORD *)ThreadRelativeContext + 504) = v8;
    *((_OWORD *)ThreadRelativeContext + 125) = v9;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  v11 = MFCreateAttributes(&ppMFAttributes, 8u);
  if ( v11 < 0 )
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12, v13);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != v11 )
        CallStackContext::TraceFailure(v16, "CMFVideoThumbnail::CreateAsyncSourceReader", 470, v11);
    }
    if ( g_wppLevels )
    {
      v17 = 37;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v11);
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
    v11 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING,
            1);
    if ( v11 < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != v11 )
          CallStackContext::TraceFailure(v29, "CMFVideoThumbnail::CreateAsyncSourceReader", 476, v11);
      }
      if ( g_wppLevels )
      {
        v17 = 39;
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    v11 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUnknown)(
            ppMFAttributes,
            MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE,
            *((_QWORD *)this + 50));
    if ( v11 < 0 )
    {
      v33 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)v35 + 499) != v11 )
          CallStackContext::TraceFailure(v35, "CMFVideoThumbnail::CreateAsyncSourceReader", 479, v11);
      }
      if ( g_wppLevels )
      {
        v17 = 40;
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    v11 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS,
            1);
    if ( v11 < 0 )
    {
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v41 + 499) != v11 )
          CallStackContext::TraceFailure(v41, "CMFVideoThumbnail::CreateAsyncSourceReader", 482, v11);
      }
      if ( g_wppLevels )
      {
        v17 = 41;
        goto LABEL_15;
      }
      goto LABEL_85;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&ppv);
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
      v52 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != v11 )
          CallStackContext::TraceFailure(v54, "CMFVideoThumbnail::CreateAsyncSourceReader", 493, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_84;
      v48 = 44;
    }
    else
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
        {
          v45 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != v11 )
          CallStackContext::TraceFailure(v47, "CMFVideoThumbnail::CreateAsyncSourceReader", 492, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_84;
      v48 = 43;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v48, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v11);
LABEL_84:
    Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&ppv);
    goto LABEL_85;
  }
  v21 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)v23 + 499) != v11 )
      CallStackContext::TraceFailure(v23, "CMFVideoThumbnail::CreateAsyncSourceReader", 473, v11);
  }
  if ( g_wppLevels )
  {
    v17 = 38;
    goto LABEL_15;
  }
LABEL_85:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFAttributes);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180065ec8  push    rbp
0x180065eca  push    rbx
0x180065ecb  push    rsi
0x180065ecc  push    rdi
0x180065ecd  push    r13
0x180065ecf  push    r14
0x180065ed1  push    r15
0x180065ed3  mov     rbp, rsp
0x180065ed6  sub     rsp, 70h
0x180065eda  mov     rax, cs:__security_cookie
0x180065ee1  xor     rax, rsp
0x180065ee4  mov     [rbp+var_8], rax
0x180065ee8  mov     r14, rdx
0x180065eeb  mov     [rbp+ppMFAttributes], 0
0x180065ef3  mov     rsi, rcx
0x180065ef6  lea     r13, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x180065efd  mov     rdx, r13; char *
0x180065f00  lea     rcx, [rbp+var_30]; this
0x180065f04  mov     r8d, 1D6h; int
0x180065f0a  mov     r15, r9
0x180065f0d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180065f12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180065f19  cmp     byte ptr [rcx+8], 0
0x180065f1d  jz      short loc_180065F74
0x180065f1f  cmp     qword ptr [rsi+190h], 0
0x180065f27  jz      short loc_180065F74
0x180065f29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065f2e  mov     rcx, [rsi+190h]
0x180065f35  mov     rdi, rax
0x180065f38  mov     rdx, [rcx]
0x180065f3b  mov     rax, [rdx+128h]
0x180065f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f47  mov     rcx, [rsi+190h]
0x180065f4e  mov     ebx, eax
0x180065f50  mov     rdx, [rcx]
0x180065f53  mov     rax, [rdx+118h]
0x180065f5a  lea     rdx, [rbp+var_18]
0x180065f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f63  movups  xmm0, xmmword ptr [rax]
0x180065f66  mov     [rdi+7E0h], ebx
0x180065f6c  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180065f74  lea     rcx, [rbp+ppMFAttributes]
0x180065f78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180065f7d  mov     edx, 8; cInitialSize
0x180065f82  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180065f86  call    cs:__imp_MFCreateAttributes
0x180065f8c  mov     edi, eax
0x180065f8e  test    eax, eax
0x180065f90  jns     loc_180066041
0x180065f96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065f9d  test    rcx, rcx
0x180065fa0  jnz     short loc_180065FE3
0x180065fa2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180065fa8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180065faf  mov     rcx, rax
0x180065fb2  test    rax, rax
0x180065fb5  jz      short loc_180065FD5
0x180065fb7  mov     rax, [rax]
0x180065fba  mov     edx, 7F0h
0x180065fbf  mov     rax, [rax+8]
0x180065fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fc8  test    eax, eax
0x180065fca  jz      short loc_180065FD5
0x180065fcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180065fd3  jmp     short loc_180065FE3
0x180065fd5  lea     rcx, qword_1800D6F70; this
0x180065fdc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180065fe3  cmp     byte ptr [rcx+8], 0
0x180065fe7  jz      short loc_18006600A
0x180065fe9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180065fee  cmp     [rax+7CCh], edi
0x180065ff4  jz      short loc_18006600A
0x180065ff6  mov     r9d, edi; int
0x180065ff9  mov     r8d, 1D6h; int
0x180065fff  mov     rdx, r13; char *
0x180066002  mov     rcx, rax; this
0x180066005  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006600a  mov     ebx, 1
0x18006600f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180066015  jb      loc_1800664CA
0x18006601b  lea     edx, [rbx+24h]
0x18006601e  mov     rcx, cs:WPP_GLOBAL_Control
0x180066025  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18006602c  mov     r9, rsi
0x18006602f  mov     dword ptr [rsp+70h+ppv], edi
0x180066033  mov     rcx, [rcx+10h]
0x180066037  call    WPP_SF_qD
0x18006603c  jmp     loc_1800664CA
0x180066041  mov     rcx, [rbp+ppMFAttributes]
0x180066045  lea     rdx, [rsi+10h]
0x180066049  mov     rax, rsi
0x18006604c  neg     rax
0x18006604f  mov     r9, [rcx]
0x180066052  sbb     r8, r8
0x180066055  and     r8, rdx
0x180066058  lea     rdx, MF_SOURCE_READER_ASYNC_CALLBACK
0x18006605f  mov     rax, [r9+0D8h]
0x180066066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006606b  mov     edi, eax
0x18006606d  test    eax, eax
0x18006606f  jns     loc_180066102
0x180066075  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006607c  test    rcx, rcx
0x18006607f  jnz     short loc_1800660C2
0x180066081  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180066087  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006608e  mov     rcx, rax
0x180066091  test    rax, rax
0x180066094  jz      short loc_1800660B4
0x180066096  mov     rax, [rax]
0x180066099  mov     edx, 7F0h
0x18006609e  mov     rax, [rax+8]
0x1800660a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660a7  test    eax, eax
0x1800660a9  jz      short loc_1800660B4
0x1800660ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800660b2  jmp     short loc_1800660C2
0x1800660b4  lea     rcx, qword_1800D6F70; this
0x1800660bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800660c2  cmp     byte ptr [rcx+8], 0
0x1800660c6  jz      short loc_1800660E9
0x1800660c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800660cd  cmp     [rax+7CCh], edi
0x1800660d3  jz      short loc_1800660E9
0x1800660d5  mov     r9d, edi; int
0x1800660d8  mov     r8d, 1D9h; int
0x1800660de  mov     rdx, r13; char *
0x1800660e1  mov     rcx, rax; this
0x1800660e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800660e9  mov     ebx, 1
0x1800660ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800660f4  jb      loc_1800664CA
0x1800660fa  lea     edx, [rbx+25h]
0x1800660fd  jmp     loc_18006601E
0x180066102  mov     rcx, [rbp+ppMFAttributes]
0x180066106  lea     rdx, MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING
0x18006610d  mov     ebx, 1
0x180066112  mov     r8d, ebx
0x180066115  mov     rax, [rcx]
0x180066118  mov     rax, [rax+0A8h]
0x18006611f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066124  mov     edi, eax
0x180066126  test    eax, eax
0x180066128  jns     loc_1800661B8
0x18006612e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066135  test    rcx, rcx
0x180066138  jnz     short loc_18006617B
0x18006613a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180066140  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180066147  mov     rcx, rax
0x18006614a  test    rax, rax
0x18006614d  jz      short loc_18006616D
0x18006614f  mov     rax, [rax]
0x180066152  mov     edx, 7F0h
0x180066157  mov     rax, [rax+8]
0x18006615b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066160  test    eax, eax
0x180066162  jz      short loc_18006616D
0x180066164  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006616b  jmp     short loc_18006617B
0x18006616d  lea     rcx, qword_1800D6F70; this
0x180066174  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006617b  cmp     byte ptr [rcx+8], 0
0x18006617f  jz      short loc_1800661A2
0x180066181  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180066186  cmp     [rax+7CCh], edi
0x18006618c  jz      short loc_1800661A2
0x18006618e  mov     r9d, edi; int
0x180066191  mov     r8d, 1DCh; int
0x180066197  mov     rdx, r13; char *
0x18006619a  mov     rcx, rax; this
0x18006619d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800661a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800661a8  jb      loc_1800664CA
0x1800661ae  mov     edx, 27h ; '''
0x1800661b3  jmp     loc_18006601E
0x1800661b8  mov     rcx, [rbp+ppMFAttributes]
0x1800661bc  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x1800661c3  mov     r8, [rsi+190h]
0x1800661ca  mov     rax, [rcx]
0x1800661cd  mov     rax, [rax+0D8h]
0x1800661d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661d9  mov     edi, eax
0x1800661db  test    eax, eax
0x1800661dd  jns     loc_18006626D
0x1800661e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800661ea  test    rcx, rcx
0x1800661ed  jnz     short loc_180066230
0x1800661ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800661f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800661fc  mov     rcx, rax
0x1800661ff  test    rax, rax
0x180066202  jz      short loc_180066222
0x180066204  mov     rax, [rax]
0x180066207  mov     edx, 7F0h
0x18006620c  mov     rax, [rax+8]
0x180066210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066215  test    eax, eax
0x180066217  jz      short loc_180066222
0x180066219  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066220  jmp     short loc_180066230
0x180066222  lea     rcx, qword_1800D6F70; this
0x180066229  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180066230  cmp     byte ptr [rcx+8], 0
0x180066234  jz      short loc_180066257
0x180066236  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006623b  cmp     [rax+7CCh], edi
0x180066241  jz      short loc_180066257
0x180066243  mov     r9d, edi; int
0x180066246  mov     r8d, 1DFh; int
0x18006624c  mov     rdx, r13; char *
0x18006624f  mov     rcx, rax; this
0x180066252  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180066257  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x18006625d  jb      loc_1800664CA
0x180066263  mov     edx, 28h ; '('
0x180066268  jmp     loc_18006601E
0x18006626d  mov     rcx, [rbp+ppMFAttributes]
0x180066271  lea     rdx, MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS
0x180066278  mov     r8d, ebx
0x18006627b  mov     rax, [rcx]
0x18006627e  mov     rax, [rax+0A8h]
0x180066285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006628a  mov     edi, eax
0x18006628c  test    eax, eax
0x18006628e  jns     loc_18006631E
0x180066294  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006629b  test    rcx, rcx
0x18006629e  jnz     short loc_1800662E1
0x1800662a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800662a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800662ad  mov     rcx, rax
0x1800662b0  test    rax, rax
0x1800662b3  jz      short loc_1800662D3
0x1800662b5  mov     rax, [rax]
0x1800662b8  mov     edx, 7F0h
0x1800662bd  mov     rax, [rax+8]
0x1800662c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662c6  test    eax, eax
0x1800662c8  jz      short loc_1800662D3
0x1800662ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800662d1  jmp     short loc_1800662E1
0x1800662d3  lea     rcx, qword_1800D6F70; this
0x1800662da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800662e1  cmp     byte ptr [rcx+8], 0
0x1800662e5  jz      short loc_180066308
0x1800662e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800662ec  cmp     [rax+7CCh], edi
0x1800662f2  jz      short loc_180066308
0x1800662f4  mov     r9d, edi; int
0x1800662f7  mov     r8d, 1E2h; int
0x1800662fd  mov     rdx, r13; char *
0x180066300  mov     rcx, rax; this
0x180066303  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180066308  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x18006630e  jb      loc_1800664CA
0x180066314  mov     edx, 29h ; ')'
0x180066319  jmp     loc_18006601E
0x18006631e  lea     rcx, [rbp+var_20]
0x180066322  mov     [rbp+var_20], 0
0x18006632a  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18006632f  lea     rax, [rbp+var_20]
0x180066333  mov     r8d, ebx; dwClsContext
0x180066336  lea     r9, _GUID_e7fe2e12_661c_40da_92f9_4f002ab67627; riid
0x18006633d  mov     [rsp+70h+ppv], rax; ppv
0x180066342  xor     edx, edx; pUnkOuter
0x180066344  lea     rcx, CLSID_MFReadWriteClassFactory; rclsid
0x18006634b  call    cs:__imp_CoCreateInstance
0x180066351  mov     edi, eax
0x180066353  test    eax, eax
0x180066355  jns     loc_1800663E5
0x18006635b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066362  test    rcx, rcx
0x180066365  jnz     short loc_1800663A8
0x180066367  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006636d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180066374  mov     rcx, rax
0x180066377  test    rax, rax
0x18006637a  jz      short loc_18006639A
0x18006637c  mov     rax, [rax]
0x18006637f  mov     edx, 7F0h
0x180066384  mov     rax, [rax+8]
0x180066388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006638d  test    eax, eax
0x18006638f  jz      short loc_18006639A
0x180066391  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066398  jmp     short loc_1800663A8
0x18006639a  lea     rcx, qword_1800D6F70; this
0x1800663a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800663a8  cmp     byte ptr [rcx+8], 0
0x1800663ac  jz      short loc_1800663CF
0x1800663ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800663b3  cmp     [rax+7CCh], edi
0x1800663b9  jz      short loc_1800663CF
0x1800663bb  mov     r9d, edi; int
0x1800663be  mov     r8d, 1ECh; int
0x1800663c4  mov     rdx, r13; char *
0x1800663c7  mov     rcx, rax; this
0x1800663ca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800663cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
  ... truncated ...
```
