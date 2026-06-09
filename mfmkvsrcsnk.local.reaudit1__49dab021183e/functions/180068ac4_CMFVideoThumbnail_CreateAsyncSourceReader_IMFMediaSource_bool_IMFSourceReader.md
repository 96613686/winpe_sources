# CMFVideoThumbnail::CreateAsyncSourceReader(IMFMediaSource *,bool,IMFSourceReader * *)

- ea: `0x180068ac4`
- end: `0x18006912c`
- name: `?CreateAsyncSourceReader@CMFVideoThumbnail@@AEAAJPEAUIMFMediaSource@@_NPEAPEAUIMFSourceReader@@@Z`
- size: `1640`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaSource *, bool, struct IMFSourceReader **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180069134`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180068ac4`
- `0x18006c764`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068f6b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068f6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068ba4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068c89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068d48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068e03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068eba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068f8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069056`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068ba4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068c89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068d48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068e03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068eba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068f8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069056`
- `MFPlat!MFCreateAttributes` at `0x180068b82`
- `MFPlat!MFCreateAttributes` at `0x180068b82`

## string_xrefs

- `0x180068af2`: `CMFVideoThumbnail::CreateAsyncSourceReader`

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
        v14 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v27 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v33 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v39 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v52 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v45 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v21 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180068ac4  push    rbp
0x180068ac6  push    rbx
0x180068ac7  push    rsi
0x180068ac8  push    rdi
0x180068ac9  push    r13
0x180068acb  push    r14
0x180068acd  push    r15
0x180068acf  mov     rbp, rsp
0x180068ad2  sub     rsp, 70h
0x180068ad6  mov     rax, cs:__security_cookie
0x180068add  xor     rax, rsp
0x180068ae0  mov     [rbp+var_8], rax
0x180068ae4  mov     r14, rdx
0x180068ae7  mov     [rbp+ppMFAttributes], 0
0x180068aef  mov     rsi, rcx
0x180068af2  lea     r13, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x180068af9  mov     rdx, r13; char *
0x180068afc  lea     rcx, [rbp+var_30]; this
0x180068b00  mov     r8d, 1D6h; int
0x180068b06  mov     r15, r9
0x180068b09  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180068b0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180068b15  cmp     byte ptr [rcx+8], 0
0x180068b19  jz      short loc_180068B70
0x180068b1b  cmp     qword ptr [rsi+190h], 0
0x180068b23  jz      short loc_180068B70
0x180068b25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068b2a  mov     rcx, [rsi+190h]
0x180068b31  mov     rdi, rax
0x180068b34  mov     rdx, [rcx]
0x180068b37  mov     rax, [rdx+128h]
0x180068b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b43  mov     rcx, [rsi+190h]
0x180068b4a  mov     ebx, eax
0x180068b4c  mov     rdx, [rcx]
0x180068b4f  mov     rax, [rdx+118h]
0x180068b56  lea     rdx, [rbp+var_18]
0x180068b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b5f  movups  xmm0, xmmword ptr [rax]
0x180068b62  mov     [rdi+7E0h], ebx
0x180068b68  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180068b70  lea     rcx, [rbp+ppMFAttributes]
0x180068b74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180068b79  mov     edx, 8; cInitialSize
0x180068b7e  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180068b82  call    cs:__imp_MFCreateAttributes
0x180068b89  nop     dword ptr [rax+rax+00h]
0x180068b8e  mov     edi, eax
0x180068b90  test    eax, eax
0x180068b92  jns     loc_180068C49
0x180068b98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068b9f  test    rcx, rcx
0x180068ba2  jnz     short loc_180068BEB
0x180068ba4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068bab  nop     dword ptr [rax+rax+00h]
0x180068bb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068bb7  mov     rcx, rax
0x180068bba  test    rax, rax
0x180068bbd  jz      short loc_180068BDD
0x180068bbf  mov     rax, [rax]
0x180068bc2  mov     edx, 7F0h
0x180068bc7  mov     rax, [rax+8]
0x180068bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068bd0  test    eax, eax
0x180068bd2  jz      short loc_180068BDD
0x180068bd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068bdb  jmp     short loc_180068BEB
0x180068bdd  lea     rcx, qword_1800DBF70; this
0x180068be4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068beb  cmp     byte ptr [rcx+8], 0
0x180068bef  jz      short loc_180068C12
0x180068bf1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068bf6  cmp     [rax+7CCh], edi
0x180068bfc  jz      short loc_180068C12
0x180068bfe  mov     r9d, edi; int
0x180068c01  mov     r8d, 1D6h; int
0x180068c07  mov     rdx, r13; char *
0x180068c0a  mov     rcx, rax; this
0x180068c0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068c12  mov     ebx, 1
0x180068c17  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180068c1d  jb      loc_1800690FC
0x180068c23  lea     edx, [rbx+24h]
0x180068c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c2d  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180068c34  mov     r9, rsi
0x180068c37  mov     dword ptr [rsp+70h+ppv], edi
0x180068c3b  mov     rcx, [rcx+10h]
0x180068c3f  call    WPP_SF_qD
0x180068c44  jmp     loc_1800690FC
0x180068c49  mov     rcx, [rbp+ppMFAttributes]
0x180068c4d  lea     rdx, [rsi+10h]
0x180068c51  mov     rax, rsi
0x180068c54  neg     rax
0x180068c57  mov     r9, [rcx]
0x180068c5a  sbb     r8, r8
0x180068c5d  and     r8, rdx
0x180068c60  lea     rdx, MF_SOURCE_READER_ASYNC_CALLBACK
0x180068c67  mov     rax, [r9+0D8h]
0x180068c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c73  mov     edi, eax
0x180068c75  test    eax, eax
0x180068c77  jns     loc_180068D10
0x180068c7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068c84  test    rcx, rcx
0x180068c87  jnz     short loc_180068CD0
0x180068c89  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068c90  nop     dword ptr [rax+rax+00h]
0x180068c95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068c9c  mov     rcx, rax
0x180068c9f  test    rax, rax
0x180068ca2  jz      short loc_180068CC2
0x180068ca4  mov     rax, [rax]
0x180068ca7  mov     edx, 7F0h
0x180068cac  mov     rax, [rax+8]
0x180068cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068cb5  test    eax, eax
0x180068cb7  jz      short loc_180068CC2
0x180068cb9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068cc0  jmp     short loc_180068CD0
0x180068cc2  lea     rcx, qword_1800DBF70; this
0x180068cc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068cd0  cmp     byte ptr [rcx+8], 0
0x180068cd4  jz      short loc_180068CF7
0x180068cd6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068cdb  cmp     [rax+7CCh], edi
0x180068ce1  jz      short loc_180068CF7
0x180068ce3  mov     r9d, edi; int
0x180068ce6  mov     r8d, 1D9h; int
0x180068cec  mov     rdx, r13; char *
0x180068cef  mov     rcx, rax; this
0x180068cf2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068cf7  mov     ebx, 1
0x180068cfc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180068d02  jb      loc_1800690FC
0x180068d08  lea     edx, [rbx+25h]
0x180068d0b  jmp     loc_180068C26
0x180068d10  mov     rcx, [rbp+ppMFAttributes]
0x180068d14  lea     rdx, MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING
0x180068d1b  mov     ebx, 1
0x180068d20  mov     r8d, ebx
0x180068d23  mov     rax, [rcx]
0x180068d26  mov     rax, [rax+0A8h]
0x180068d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d32  mov     edi, eax
0x180068d34  test    eax, eax
0x180068d36  jns     loc_180068DCC
0x180068d3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068d43  test    rcx, rcx
0x180068d46  jnz     short loc_180068D8F
0x180068d48  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068d4f  nop     dword ptr [rax+rax+00h]
0x180068d54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068d5b  mov     rcx, rax
0x180068d5e  test    rax, rax
0x180068d61  jz      short loc_180068D81
0x180068d63  mov     rax, [rax]
0x180068d66  mov     edx, 7F0h
0x180068d6b  mov     rax, [rax+8]
0x180068d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d74  test    eax, eax
0x180068d76  jz      short loc_180068D81
0x180068d78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068d7f  jmp     short loc_180068D8F
0x180068d81  lea     rcx, qword_1800DBF70; this
0x180068d88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068d8f  cmp     byte ptr [rcx+8], 0
0x180068d93  jz      short loc_180068DB6
0x180068d95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068d9a  cmp     [rax+7CCh], edi
0x180068da0  jz      short loc_180068DB6
0x180068da2  mov     r9d, edi; int
0x180068da5  mov     r8d, 1DCh; int
0x180068dab  mov     rdx, r13; char *
0x180068dae  mov     rcx, rax; this
0x180068db1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068db6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180068dbc  jb      loc_1800690FC
0x180068dc2  mov     edx, 27h ; '''
0x180068dc7  jmp     loc_180068C26
0x180068dcc  mov     rcx, [rbp+ppMFAttributes]
0x180068dd0  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x180068dd7  mov     r8, [rsi+190h]
0x180068dde  mov     rax, [rcx]
0x180068de1  mov     rax, [rax+0D8h]
0x180068de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ded  mov     edi, eax
0x180068def  test    eax, eax
0x180068df1  jns     loc_180068E87
0x180068df7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068dfe  test    rcx, rcx
0x180068e01  jnz     short loc_180068E4A
0x180068e03  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068e0a  nop     dword ptr [rax+rax+00h]
0x180068e0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068e16  mov     rcx, rax
0x180068e19  test    rax, rax
0x180068e1c  jz      short loc_180068E3C
0x180068e1e  mov     rax, [rax]
0x180068e21  mov     edx, 7F0h
0x180068e26  mov     rax, [rax+8]
0x180068e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068e2f  test    eax, eax
0x180068e31  jz      short loc_180068E3C
0x180068e33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068e3a  jmp     short loc_180068E4A
0x180068e3c  lea     rcx, qword_1800DBF70; this
0x180068e43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068e4a  cmp     byte ptr [rcx+8], 0
0x180068e4e  jz      short loc_180068E71
0x180068e50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068e55  cmp     [rax+7CCh], edi
0x180068e5b  jz      short loc_180068E71
0x180068e5d  mov     r9d, edi; int
0x180068e60  mov     r8d, 1DFh; int
0x180068e66  mov     rdx, r13; char *
0x180068e69  mov     rcx, rax; this
0x180068e6c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068e71  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180068e77  jb      loc_1800690FC
0x180068e7d  mov     edx, 28h ; '('
0x180068e82  jmp     loc_180068C26
0x180068e87  mov     rcx, [rbp+ppMFAttributes]
0x180068e8b  lea     rdx, MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS
0x180068e92  mov     r8d, ebx
0x180068e95  mov     rax, [rcx]
0x180068e98  mov     rax, [rax+0A8h]
0x180068e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ea4  mov     edi, eax
0x180068ea6  test    eax, eax
0x180068ea8  jns     loc_180068F3E
0x180068eae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068eb5  test    rcx, rcx
0x180068eb8  jnz     short loc_180068F01
0x180068eba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068ec1  nop     dword ptr [rax+rax+00h]
0x180068ec6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068ecd  mov     rcx, rax
0x180068ed0  test    rax, rax
0x180068ed3  jz      short loc_180068EF3
0x180068ed5  mov     rax, [rax]
0x180068ed8  mov     edx, 7F0h
0x180068edd  mov     rax, [rax+8]
0x180068ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ee6  test    eax, eax
0x180068ee8  jz      short loc_180068EF3
0x180068eea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068ef1  jmp     short loc_180068F01
0x180068ef3  lea     rcx, qword_1800DBF70; this
0x180068efa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068f01  cmp     byte ptr [rcx+8], 0
0x180068f05  jz      short loc_180068F28
0x180068f07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068f0c  cmp     [rax+7CCh], edi
0x180068f12  jz      short loc_180068F28
0x180068f14  mov     r9d, edi; int
0x180068f17  mov     r8d, 1E2h; int
0x180068f1d  mov     rdx, r13; char *
0x180068f20  mov     rcx, rax; this
0x180068f23  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068f28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180068f2e  jb      loc_1800690FC
0x180068f34  mov     edx, 29h ; ')'
0x180068f39  jmp     loc_180068C26
0x180068f3e  lea     rcx, [rbp+var_20]
0x180068f42  mov     [rbp+var_20], 0
0x180068f4a  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180068f4f  lea     rax, [rbp+var_20]
0x180068f53  mov     r8d, ebx; dwClsContext
0x180068f56  lea     r9, _GUID_e7fe2e12_661c_40da_92f9_4f002ab67627; riid
0x180068f5d  mov     [rsp+70h+ppv], rax; ppv
0x180068f62  xor     edx, edx; pUnkOuter
0x180068f64  lea     rcx, CLSID_MFReadWriteClassFactory; rclsid
0x180068f6b  call    cs:__imp_CoCreateInstance
0x180068f72  nop     dword ptr [rax+rax+00h]
0x180068f77  mov     edi, eax
0x180068f79  test    eax, eax
0x180068f7b  jns     loc_180069011
0x180068f81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068f88  test    rcx, rcx
0x180068f8b  jnz     short loc_180068FD4
0x180068f8d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068f94  nop     dword ptr [rax+rax+00h]
0x180068f99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068fa0  mov     rcx, rax
0x180068fa3  test    rax, rax
0x180068fa6  jz      short loc_180068FC6
0x180068fa8  mov     rax, [rax]
0x180068fab  mov     edx, 7F0h
0x180068fb0  mov     rax, [rax+8]
0x180068fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fb9  test    eax, eax
0x180068fbb  jz      short loc_180068FC6
0x180068fbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068fc4  jmp     short loc_180068FD4
0x180068fc6  lea     rcx, qword_1800DBF70; this
0x180068fcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068fd4  cmp     byte ptr [rcx+8], 0
0x180068fd8  jz      short loc_180068FFB
0x180068fda  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
