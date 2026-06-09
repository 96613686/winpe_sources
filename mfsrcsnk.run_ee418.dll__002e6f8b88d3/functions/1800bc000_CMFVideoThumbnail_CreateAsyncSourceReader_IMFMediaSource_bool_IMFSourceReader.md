# CMFVideoThumbnail::CreateAsyncSourceReader(IMFMediaSource *,bool,IMFSourceReader * *)

- ea: `0x1800bc000`
- end: `0x1800bc714`
- name: `?CreateAsyncSourceReader@CMFVideoThumbnail@@AEAAJPEAUIMFMediaSource@@_NPEAPEAUIMFSourceReader@@@Z`
- size: `1812`
- prototype: `__int64 __fastcall(CMFVideoThumbnail *__hidden this, struct IMFMediaSource *, bool, struct IMFSourceReader **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800afff8`
- `0x18015a8dc`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800734a8`
- `0x180073b14`
- `0x1800bc000`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc0dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc1c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc27d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc336`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc3eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc4a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc570`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc637`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc0dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc1c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc27d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc336`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc3eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc4a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc570`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc637`
- `MFPlat!MFCreateAttributes` at `0x1800bc0c1`
- `MFPlat!MFCreateAttributes` at `0x1800bc0c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc554`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800bc554`

## string_xrefs

- `0x1800bc02e`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800bc134`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800bc217`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800bc2d4`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800bc38d`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800bc442`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800bc500`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800bc5c7`: `CMFVideoThumbnail::CreateAsyncSourceReader`
- `0x1800bc68e`: `CMFVideoThumbnail::CreateAsyncSourceReader`

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
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  wchar_t *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  _BYTE v63[8]; // [rsp+40h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v66[16]; // [rsp+58h] [rbp-18h] BYREF

  ppMFAttributes = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v63,
    "CMFVideoThumbnail::CreateAsyncSourceReader",
    470);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 50) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 296LL))(*((_QWORD *)this + 50));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 50) + 280LL))(
                       *((_QWORD *)this + 50),
                       v66);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppMFAttributes);
  v12 = MFCreateAttributes(&ppMFAttributes, 8u);
  if ( v12 < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != v12 )
        CallStackContext::TraceFailure(v17, "CMFVideoThumbnail::CreateAsyncSourceReader", 470, v12);
    }
    if ( g_wppLevels )
    {
      v18 = 37;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v12);
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
    v12 = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING,
            1);
    if ( v12 < 0 )
    {
      v28 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
        CallStackTracing::s_wpInstance = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
        if ( *((_DWORD *)v30 + 499) != v12 )
          CallStackContext::TraceFailure(v30, "CMFVideoThumbnail::CreateAsyncSourceReader", 476, v12);
      }
      if ( g_wppLevels )
      {
        v18 = 39;
        goto LABEL_15;
      }
      goto LABEL_97;
    }
    v12 = ((__int64 (__fastcall *)(IMFAttributes *, void *, _QWORD))ppMFAttributes->lpVtbl->SetUnknown)(
            ppMFAttributes,
            &MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE,
            *((_QWORD *)this + 50));
    if ( v12 < 0 )
    {
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != v12 )
          CallStackContext::TraceFailure(v36, "CMFVideoThumbnail::CreateAsyncSourceReader", 479, v12);
      }
      if ( g_wppLevels )
      {
        v18 = 40;
        goto LABEL_15;
      }
      goto LABEL_97;
    }
    v12 = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            &MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS,
            1);
    if ( v12 < 0 )
    {
      v40 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != v12 )
          CallStackContext::TraceFailure(v42, "CMFVideoThumbnail::CreateAsyncSourceReader", 482, v12);
      }
      if ( g_wppLevels )
      {
        v18 = 41;
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
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != v12 )
            CallStackContext::TraceFailure(v48, "CMFVideoThumbnail::CreateAsyncSourceReader", 487, v12);
        }
        if ( g_wppLevels )
        {
          v18 = 42;
          goto LABEL_15;
        }
        goto LABEL_97;
      }
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppv);
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
      v59 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57, v58);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        {
          v59 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v59 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
        if ( *((_DWORD *)v61 + 499) != v12 )
          CallStackContext::TraceFailure(v61, "CMFVideoThumbnail::CreateAsyncSourceReader", 493, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v55 = 44;
    }
    else
    {
      v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50, v51);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != v12 )
          CallStackContext::TraceFailure(v54, "CMFVideoThumbnail::CreateAsyncSourceReader", 492, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v55 = 43;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, this, v12);
LABEL_96:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppv);
    goto LABEL_97;
  }
  v22 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
    CallStackTracing::s_wpInstance = v23;
    if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
    {
      v22 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v22 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
    if ( *((_DWORD *)v24 + 499) != v12 )
      CallStackContext::TraceFailure(v24, "CMFVideoThumbnail::CreateAsyncSourceReader", 473, v12);
  }
  if ( g_wppLevels )
  {
    v18 = 38;
    goto LABEL_15;
  }
LABEL_97:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&ppMFAttributes);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800bc000  mov     [rsp-38h+arg_10], rbx
0x1800bc005  push    rbp
0x1800bc006  push    rsi
0x1800bc007  push    rdi
0x1800bc008  push    r12
0x1800bc00a  push    r13
0x1800bc00c  push    r14
0x1800bc00e  push    r15
0x1800bc010  mov     rbp, rsp
0x1800bc013  sub     rsp, 70h
0x1800bc017  mov     rax, cs:__security_cookie
0x1800bc01e  xor     rax, rsp
0x1800bc021  mov     [rbp+var_8], rax
0x1800bc025  mov     r14b, r8b
0x1800bc028  mov     r15, rdx
0x1800bc02b  mov     rsi, rcx
0x1800bc02e  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800bc035  xor     r13d, r13d
0x1800bc038  lea     rcx, [rbp+var_30]; this
0x1800bc03c  mov     r8d, 1D6h; int
0x1800bc042  mov     [rbp+ppMFAttributes], r13
0x1800bc046  mov     r12, r9
0x1800bc049  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bc04e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800bc055  cmp     [rcx+8], r13b
0x1800bc059  jz      short loc_1800BC0AF
0x1800bc05b  cmp     [rsi+190h], r13
0x1800bc062  jz      short loc_1800BC0AF
0x1800bc064  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc069  mov     rcx, [rsi+190h]
0x1800bc070  mov     rdi, rax
0x1800bc073  mov     rdx, [rcx]
0x1800bc076  mov     rax, [rdx+128h]
0x1800bc07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc082  mov     rcx, [rsi+190h]
0x1800bc089  mov     ebx, eax
0x1800bc08b  mov     rdx, [rcx]
0x1800bc08e  mov     rax, [rdx+118h]
0x1800bc095  lea     rdx, [rbp+var_18]
0x1800bc099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc09e  movups  xmm0, xmmword ptr [rax]
0x1800bc0a1  mov     [rdi+7E0h], ebx
0x1800bc0a7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800bc0af  lea     rcx, [rbp+ppMFAttributes]
0x1800bc0b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bc0b8  mov     edx, 8; cInitialSize
0x1800bc0bd  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800bc0c1  call    cs:__imp_MFCreateAttributes
0x1800bc0c7  mov     edi, eax
0x1800bc0c9  test    eax, eax
0x1800bc0cb  jns     loc_1800BC180
0x1800bc0d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc0d8  test    rcx, rcx
0x1800bc0db  jnz     short loc_1800BC11E
0x1800bc0dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bc0e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc0ea  mov     rcx, rax
0x1800bc0ed  test    rax, rax
0x1800bc0f0  jz      short loc_1800BC110
0x1800bc0f2  mov     rax, [rax]
0x1800bc0f5  mov     edx, 7F0h
0x1800bc0fa  mov     rax, [rax+8]
0x1800bc0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc103  test    eax, eax
0x1800bc105  jz      short loc_1800BC110
0x1800bc107  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc10e  jmp     short loc_1800BC11E
0x1800bc110  lea     rcx, qword_1801B07E0; this
0x1800bc117  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc11e  cmp     [rcx+8], r13b
0x1800bc122  jz      short loc_1800BC149
0x1800bc124  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc129  cmp     [rax+7CCh], edi
0x1800bc12f  jz      short loc_1800BC149
0x1800bc131  mov     r9d, edi; int
0x1800bc134  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800bc13b  mov     r8d, 1D6h; int
0x1800bc141  mov     rcx, rax; this
0x1800bc144  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bc149  mov     ebx, 1
0x1800bc14e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800bc154  jb      loc_1800BC6DC
0x1800bc15a  lea     edx, [rbx+24h]
0x1800bc15d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc164  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x1800bc16b  mov     r9, rsi
0x1800bc16e  mov     dword ptr [rsp+70h+ppv], edi
0x1800bc172  mov     rcx, [rcx+10h]
0x1800bc176  call    WPP_SF_qD
0x1800bc17b  jmp     loc_1800BC6DC
0x1800bc180  mov     rcx, [rbp+ppMFAttributes]
0x1800bc184  lea     rdx, [rsi+10h]
0x1800bc188  mov     rax, rsi
0x1800bc18b  neg     rax
0x1800bc18e  mov     r9, [rcx]
0x1800bc191  sbb     r8, r8
0x1800bc194  and     r8, rdx
0x1800bc197  lea     rdx, MF_SOURCE_READER_ASYNC_CALLBACK
0x1800bc19e  mov     rax, [r9+0D8h]
0x1800bc1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc1aa  mov     edi, eax
0x1800bc1ac  test    eax, eax
0x1800bc1ae  jns     loc_1800BC245
0x1800bc1b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc1bb  test    rcx, rcx
0x1800bc1be  jnz     short loc_1800BC201
0x1800bc1c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bc1c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc1cd  mov     rcx, rax
0x1800bc1d0  test    rax, rax
0x1800bc1d3  jz      short loc_1800BC1F3
0x1800bc1d5  mov     rax, [rax]
0x1800bc1d8  mov     edx, 7F0h
0x1800bc1dd  mov     rax, [rax+8]
0x1800bc1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc1e6  test    eax, eax
0x1800bc1e8  jz      short loc_1800BC1F3
0x1800bc1ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc1f1  jmp     short loc_1800BC201
0x1800bc1f3  lea     rcx, qword_1801B07E0; this
0x1800bc1fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc201  cmp     [rcx+8], r13b
0x1800bc205  jz      short loc_1800BC22C
0x1800bc207  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc20c  cmp     [rax+7CCh], edi
0x1800bc212  jz      short loc_1800BC22C
0x1800bc214  mov     r9d, edi; int
0x1800bc217  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800bc21e  mov     r8d, 1D9h; int
0x1800bc224  mov     rcx, rax; this
0x1800bc227  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bc22c  mov     ebx, 1
0x1800bc231  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800bc237  jb      loc_1800BC6DC
0x1800bc23d  lea     edx, [rbx+25h]
0x1800bc240  jmp     loc_1800BC15D
0x1800bc245  mov     rcx, [rbp+ppMFAttributes]
0x1800bc249  lea     rdx, MF_SOURCE_READER_ENABLE_ADVANCED_VIDEO_PROCESSING
0x1800bc250  mov     ebx, 1
0x1800bc255  mov     r8d, ebx
0x1800bc258  mov     rax, [rcx]
0x1800bc25b  mov     rax, [rax+0A8h]
0x1800bc262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc267  mov     edi, eax
0x1800bc269  test    eax, eax
0x1800bc26b  jns     loc_1800BC2FF
0x1800bc271  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc278  test    rcx, rcx
0x1800bc27b  jnz     short loc_1800BC2BE
0x1800bc27d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bc283  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc28a  mov     rcx, rax
0x1800bc28d  test    rax, rax
0x1800bc290  jz      short loc_1800BC2B0
0x1800bc292  mov     rax, [rax]
0x1800bc295  mov     edx, 7F0h
0x1800bc29a  mov     rax, [rax+8]
0x1800bc29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc2a3  test    eax, eax
0x1800bc2a5  jz      short loc_1800BC2B0
0x1800bc2a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc2ae  jmp     short loc_1800BC2BE
0x1800bc2b0  lea     rcx, qword_1801B07E0; this
0x1800bc2b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc2be  cmp     [rcx+8], r13b
0x1800bc2c2  jz      short loc_1800BC2E9
0x1800bc2c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc2c9  cmp     [rax+7CCh], edi
0x1800bc2cf  jz      short loc_1800BC2E9
0x1800bc2d1  mov     r9d, edi; int
0x1800bc2d4  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800bc2db  mov     r8d, 1DCh; int
0x1800bc2e1  mov     rcx, rax; this
0x1800bc2e4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bc2e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800bc2ef  jb      loc_1800BC6DC
0x1800bc2f5  mov     edx, 27h ; '''
0x1800bc2fa  jmp     loc_1800BC15D
0x1800bc2ff  mov     rcx, [rbp+ppMFAttributes]
0x1800bc303  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x1800bc30a  mov     r8, [rsi+190h]
0x1800bc311  mov     rax, [rcx]
0x1800bc314  mov     rax, [rax+0D8h]
0x1800bc31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc320  mov     edi, eax
0x1800bc322  test    eax, eax
0x1800bc324  jns     loc_1800BC3B8
0x1800bc32a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc331  test    rcx, rcx
0x1800bc334  jnz     short loc_1800BC377
0x1800bc336  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bc33c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc343  mov     rcx, rax
0x1800bc346  test    rax, rax
0x1800bc349  jz      short loc_1800BC369
0x1800bc34b  mov     rax, [rax]
0x1800bc34e  mov     edx, 7F0h
0x1800bc353  mov     rax, [rax+8]
0x1800bc357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc35c  test    eax, eax
0x1800bc35e  jz      short loc_1800BC369
0x1800bc360  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc367  jmp     short loc_1800BC377
0x1800bc369  lea     rcx, qword_1801B07E0; this
0x1800bc370  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc377  cmp     [rcx+8], r13b
0x1800bc37b  jz      short loc_1800BC3A2
0x1800bc37d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc382  cmp     [rax+7CCh], edi
0x1800bc388  jz      short loc_1800BC3A2
0x1800bc38a  mov     r9d, edi; int
0x1800bc38d  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800bc394  mov     r8d, 1DFh; int
0x1800bc39a  mov     rcx, rax; this
0x1800bc39d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bc3a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800bc3a8  jb      loc_1800BC6DC
0x1800bc3ae  mov     edx, 28h ; '('
0x1800bc3b3  jmp     loc_1800BC15D
0x1800bc3b8  mov     rcx, [rbp+ppMFAttributes]
0x1800bc3bc  lea     rdx, MF_SOURCE_READER_ENABLE_UNTRUSTED_STORE_EXTENSIONS
0x1800bc3c3  mov     r8d, ebx
0x1800bc3c6  mov     rax, [rcx]
0x1800bc3c9  mov     rax, [rax+0A8h]
0x1800bc3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc3d5  mov     edi, eax
0x1800bc3d7  test    eax, eax
0x1800bc3d9  jns     loc_1800BC46D
0x1800bc3df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc3e6  test    rcx, rcx
0x1800bc3e9  jnz     short loc_1800BC42C
0x1800bc3eb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bc3f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc3f8  mov     rcx, rax
0x1800bc3fb  test    rax, rax
0x1800bc3fe  jz      short loc_1800BC41E
0x1800bc400  mov     rax, [rax]
0x1800bc403  mov     edx, 7F0h
0x1800bc408  mov     rax, [rax+8]
0x1800bc40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc411  test    eax, eax
0x1800bc413  jz      short loc_1800BC41E
0x1800bc415  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc41c  jmp     short loc_1800BC42C
0x1800bc41e  lea     rcx, qword_1801B07E0; this
0x1800bc425  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc42c  cmp     [rcx+8], r13b
0x1800bc430  jz      short loc_1800BC457
0x1800bc432  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc437  cmp     [rax+7CCh], edi
0x1800bc43d  jz      short loc_1800BC457
0x1800bc43f  mov     r9d, edi; int
0x1800bc442  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800bc449  mov     r8d, 1E2h; int
0x1800bc44f  mov     rcx, rax; this
0x1800bc452  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bc457  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800bc45d  jb      loc_1800BC6DC
0x1800bc463  mov     edx, 29h ; ')'
0x1800bc468  jmp     loc_1800BC15D
0x1800bc46d  test    r14b, r14b
0x1800bc470  jz      loc_1800BC52B
0x1800bc476  mov     rcx, [rbp+ppMFAttributes]
0x1800bc47a  lea     rdx, MF_SOURCE_READER_DISCONNECT_MEDIASOURCE_ON_SHUTDOWN
0x1800bc481  mov     r8d, ebx
0x1800bc484  mov     rax, [rcx]
0x1800bc487  mov     rax, [rax+0A8h]
0x1800bc48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc493  mov     edi, eax
0x1800bc495  test    eax, eax
0x1800bc497  jns     loc_1800BC52B
0x1800bc49d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc4a4  test    rcx, rcx
0x1800bc4a7  jnz     short loc_1800BC4EA
0x1800bc4a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bc4af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc4b6  mov     rcx, rax
0x1800bc4b9  test    rax, rax
0x1800bc4bc  jz      short loc_1800BC4DC
0x1800bc4be  mov     rax, [rax]
0x1800bc4c1  mov     edx, 7F0h
0x1800bc4c6  mov     rax, [rax+8]
0x1800bc4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc4cf  test    eax, eax
0x1800bc4d1  jz      short loc_1800BC4DC
0x1800bc4d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc4da  jmp     short loc_1800BC4EA
0x1800bc4dc  lea     rcx, qword_1801B07E0; this
0x1800bc4e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bc4ea  cmp     [rcx+8], r13b
0x1800bc4ee  jz      short loc_1800BC515
0x1800bc4f0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bc4f5  cmp     [rax+7CCh], edi
0x1800bc4fb  jz      short loc_1800BC515
0x1800bc4fd  mov     r9d, edi; int
0x1800bc500  lea     rdx, aCmfvideothumbn_8; "CMFVideoThumbnail::CreateAsyncSourceRea"...
0x1800bc507  mov     r8d, 1E7h; int
0x1800bc50d  mov     rcx, rax; this
0x1800bc510  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bc515  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
  ... truncated ...
```
