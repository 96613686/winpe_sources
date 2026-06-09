# CMFByteStreamMediaSource::GetMetadataPropertyStore(IPropertyStore * *)

- ea: `0x180071a8c`
- end: `0x180071ec6`
- name: `?GetMetadataPropertyStore@CMFByteStreamMediaSource@@IEAAJPEAPEAUIPropertyStore@@@Z`
- size: `1082`
- prototype: `__int64 __fastcall(CMFByteStreamMediaSource *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180071760`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18004f1d4`
- `0x180071a8c`
- `0x180073b14`
- `0x1800d0d40`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071b09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071bda`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071c9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071d46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071df4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071b09`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071bda`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071c9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071d46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071e8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071e8a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180071c66`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180071c7e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180071c66`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180071c7e`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::GetMetadataPropertyStore(
        CMFByteStreamMediaSource *this,
        struct IPropertyStore **a2)
{
  HRESULT ByteStreamOriginName; // ebx
  struct IPropertyStore **v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
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
  struct IPropertyStore *v37; // rcx
  IStream *ppstm; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppvObject; // [rsp+38h] [rbp-8h] BYREF
  char v41; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v42; // [rsp+80h] [rbp+40h] BYREF
  LPCWSTR pszFile; // [rsp+88h] [rbp+48h] BYREF

  ByteStreamOriginName = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v41,
    "CMFByteStreamMediaSource::GetMetadataPropertyStore",
    2843);
  v5 = (struct IPropertyStore **)((char *)this + 960);
  ppvObject = 0;
  ppstm = 0;
  pszFile = 0;
  v42 = 0;
  if ( *((_QWORD *)this + 120) )
    goto LABEL_59;
  ByteStreamOriginName = CMFByteStreamSourceReader::GetByteStreamOriginName(
                           (CMFByteStreamMediaSource *)((char *)this + 1120),
                           (unsigned __int16 **)&pszFile,
                           &v42);
  if ( ByteStreamOriginName < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ByteStreamOriginName )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFByteStreamMediaSource::GetMetadataPropertyStore",
          2861,
          ByteStreamOriginName);
    }
    if ( g_wppLevels )
    {
      v12 = 266;
LABEL_13:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
        this,
        ByteStreamOriginName);
      goto LABEL_61;
    }
    goto LABEL_61;
  }
  ByteStreamOriginName = MFGetService(
                           *((IUnknown **)this + 112),
                           &MF_PROPERTY_HANDLER_SERVICE,
                           &IID_IInitializeWithStream,
                           &ppvObject);
  if ( ByteStreamOriginName >= 0 )
  {
    if ( SHCreateStreamOnFileW(pszFile, 1u, &ppstm) < 0 )
    {
      ByteStreamOriginName = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
      if ( ByteStreamOriginName < 0 )
      {
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
          if ( *((_DWORD *)v24 + 499) != ByteStreamOriginName )
            CallStackContext::TraceFailure(
              v24,
              "CMFByteStreamMediaSource::GetMetadataPropertyStore",
              2877,
              ByteStreamOriginName);
        }
        if ( g_wppLevels )
        {
          v12 = 268;
          goto LABEL_13;
        }
        goto LABEL_61;
      }
    }
    ByteStreamOriginName = (*(__int64 (__fastcall **)(LPVOID, IStream *, _QWORD))(*(_QWORD *)ppvObject + 24LL))(
                             ppvObject,
                             ppstm,
                             0);
    if ( ByteStreamOriginName < 0 )
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
        if ( *((_DWORD *)v30 + 499) != ByteStreamOriginName )
          CallStackContext::TraceFailure(
            v30,
            "CMFByteStreamMediaSource::GetMetadataPropertyStore",
            2880,
            ByteStreamOriginName);
      }
      if ( g_wppLevels )
      {
        v12 = 269;
        goto LABEL_13;
      }
      goto LABEL_61;
    }
    ByteStreamOriginName = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))ppvObject)(
                             ppvObject,
                             &IID_IPropertyStore,
                             (char *)this + 960);
    if ( ByteStreamOriginName < 0 )
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
        if ( *((_DWORD *)v36 + 499) != ByteStreamOriginName )
          CallStackContext::TraceFailure(
            v36,
            "CMFByteStreamMediaSource::GetMetadataPropertyStore",
            2882,
            ByteStreamOriginName);
      }
      if ( g_wppLevels )
      {
        v12 = 270;
        goto LABEL_13;
      }
      goto LABEL_61;
    }
LABEL_59:
    v37 = *v5;
    *a2 = *v5;
    if ( v37 )
      ((void (__fastcall *)(struct IPropertyStore *))v37->lpVtbl->AddRef)(v37);
    goto LABEL_61;
  }
  v16 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)v18 + 499) != ByteStreamOriginName )
      CallStackContext::TraceFailure(
        v18,
        "CMFByteStreamMediaSource::GetMetadataPropertyStore",
        2869,
        ByteStreamOriginName);
  }
  if ( g_wppLevels )
  {
    v12 = 267;
    goto LABEL_13;
  }
LABEL_61:
  CoTaskMemFree((LPVOID)pszFile);
  pszFile = 0;
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppstm);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppvObject);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  return (unsigned int)ByteStreamOriginName;
}

```

## disassembly

```asm
0x180071a8c  mov     [rsp-28h+arg_8], rbx
0x180071a91  push    rbp
0x180071a92  push    rsi
0x180071a93  push    rdi
0x180071a94  push    r12
0x180071a96  push    r14
0x180071a98  mov     rbp, rsp
0x180071a9b  sub     rsp, 40h
0x180071a9f  mov     r14, rdx
0x180071aa2  lea     r12, aCmfbytestreamm_62; "CMFByteStreamMediaSource::GetMetadataPr"...
0x180071aa9  mov     rdi, rcx
0x180071aac  mov     rdx, r12; char *
0x180071aaf  mov     r8d, 0B1Bh; int
0x180071ab5  lea     rcx, [rbp+arg_0]; this
0x180071ab9  xor     ebx, ebx
0x180071abb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071ac0  lea     rsi, [rdi+3C0h]
0x180071ac7  mov     [rbp+ppvObject], rbx
0x180071acb  mov     [rbp+ppstm], rbx
0x180071acf  mov     [rbp+pszFile], rbx
0x180071ad3  mov     [rbp+arg_10], ebx
0x180071ad6  cmp     [rsi], rbx
0x180071ad9  jnz     loc_180071E6F
0x180071adf  lea     rcx, [rdi+460h]; this
0x180071ae6  lea     r8, [rbp+arg_10]; unsigned int *
0x180071aea  lea     rdx, [rbp+pszFile]; unsigned __int16 **
0x180071aee  call    ?GetByteStreamOriginName@CMFByteStreamSourceReader@@QEAAJPEAPEAGPEAI@Z; CMFByteStreamSourceReader::GetByteStreamOriginName(ushort * *,uint *)
0x180071af3  mov     ebx, eax
0x180071af5  test    eax, eax
0x180071af7  jns     loc_180071BA6
0x180071afd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071b04  test    rcx, rcx
0x180071b07  jnz     short loc_180071B4A
0x180071b09  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071b0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071b16  mov     rcx, rax
0x180071b19  test    rax, rax
0x180071b1c  jz      short loc_180071B3C
0x180071b1e  mov     rax, [rax]
0x180071b21  mov     edx, 7F0h
0x180071b26  mov     rax, [rax+8]
0x180071b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b2f  test    eax, eax
0x180071b31  jz      short loc_180071B3C
0x180071b33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071b3a  jmp     short loc_180071B4A
0x180071b3c  lea     rcx, qword_1801B07E0; this
0x180071b43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071b4a  cmp     byte ptr [rcx+8], 0
0x180071b4e  jz      short loc_180071B71
0x180071b50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071b55  cmp     [rax+7CCh], ebx
0x180071b5b  jz      short loc_180071B71
0x180071b5d  mov     r9d, ebx; int
0x180071b60  mov     r8d, 0B2Dh; int
0x180071b66  mov     rdx, r12; char *
0x180071b69  mov     rcx, rax; this
0x180071b6c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071b71  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071b78  jb      loc_180071E86
0x180071b7e  mov     edx, 10Ah
0x180071b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180071b8a  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x180071b91  mov     r9, rdi
0x180071b94  mov     [rsp+40h+var_20], ebx
0x180071b98  mov     rcx, [rcx+10h]
0x180071b9c  call    WPP_SF_qD
0x180071ba1  jmp     loc_180071E86
0x180071ba6  mov     rcx, [rdi+380h]; punkObject
0x180071bad  lea     r9, [rbp+ppvObject]; ppvObject
0x180071bb1  lea     r8, IID_IInitializeWithStream; riid
0x180071bb8  lea     rdx, MF_PROPERTY_HANDLER_SERVICE; guidService
0x180071bbf  call    MFGetService
0x180071bc4  mov     ebx, eax
0x180071bc6  test    eax, eax
0x180071bc8  jns     loc_180071C59
0x180071bce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071bd5  test    rcx, rcx
0x180071bd8  jnz     short loc_180071C1B
0x180071bda  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071be0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071be7  mov     rcx, rax
0x180071bea  test    rax, rax
0x180071bed  jz      short loc_180071C0D
0x180071bef  mov     rax, [rax]
0x180071bf2  mov     edx, 7F0h
0x180071bf7  mov     rax, [rax+8]
0x180071bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071c00  test    eax, eax
0x180071c02  jz      short loc_180071C0D
0x180071c04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071c0b  jmp     short loc_180071C1B
0x180071c0d  lea     rcx, qword_1801B07E0; this
0x180071c14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071c1b  cmp     byte ptr [rcx+8], 0
0x180071c1f  jz      short loc_180071C42
0x180071c21  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071c26  cmp     [rax+7CCh], ebx
0x180071c2c  jz      short loc_180071C42
0x180071c2e  mov     r9d, ebx; int
0x180071c31  mov     r8d, 0B35h; int
0x180071c37  mov     rdx, r12; char *
0x180071c3a  mov     rcx, rax; this
0x180071c3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071c42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071c49  jb      loc_180071E86
0x180071c4f  mov     edx, 10Bh
0x180071c54  jmp     loc_180071B83
0x180071c59  mov     rcx, [rbp+pszFile]; pszFile
0x180071c5d  lea     r8, [rbp+ppstm]; ppstm
0x180071c61  mov     edx, 1; grfMode
0x180071c66  call    cs:__imp_SHCreateStreamOnFileW
0x180071c6c  test    eax, eax
0x180071c6e  jns     loc_180071D19
0x180071c74  mov     rcx, [rbp+pszFile]; pszFile
0x180071c78  lea     r8, [rbp+ppstm]; ppstm
0x180071c7c  xor     edx, edx; grfMode
0x180071c7e  call    cs:__imp_SHCreateStreamOnFileW
0x180071c84  mov     ebx, eax
0x180071c86  test    eax, eax
0x180071c88  jns     loc_180071D19
0x180071c8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071c95  test    rcx, rcx
0x180071c98  jnz     short loc_180071CDB
0x180071c9a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071ca0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071ca7  mov     rcx, rax
0x180071caa  test    rax, rax
0x180071cad  jz      short loc_180071CCD
0x180071caf  mov     rax, [rax]
0x180071cb2  mov     edx, 7F0h
0x180071cb7  mov     rax, [rax+8]
0x180071cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071cc0  test    eax, eax
0x180071cc2  jz      short loc_180071CCD
0x180071cc4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071ccb  jmp     short loc_180071CDB
0x180071ccd  lea     rcx, qword_1801B07E0; this
0x180071cd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071cdb  cmp     byte ptr [rcx+8], 0
0x180071cdf  jz      short loc_180071D02
0x180071ce1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071ce6  cmp     [rax+7CCh], ebx
0x180071cec  jz      short loc_180071D02
0x180071cee  mov     r9d, ebx; int
0x180071cf1  mov     r8d, 0B3Dh; int
0x180071cf7  mov     rdx, r12; char *
0x180071cfa  mov     rcx, rax; this
0x180071cfd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071d02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071d09  jb      loc_180071E86
0x180071d0f  mov     edx, 10Ch
0x180071d14  jmp     loc_180071B83
0x180071d19  mov     rcx, [rbp+ppvObject]
0x180071d1d  xor     r8d, r8d
0x180071d20  mov     rdx, [rbp+ppstm]
0x180071d24  mov     rax, [rcx]
0x180071d27  mov     rax, [rax+18h]
0x180071d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d30  mov     ebx, eax
0x180071d32  test    eax, eax
0x180071d34  jns     loc_180071DC5
0x180071d3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071d41  test    rcx, rcx
0x180071d44  jnz     short loc_180071D87
0x180071d46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071d4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071d53  mov     rcx, rax
0x180071d56  test    rax, rax
0x180071d59  jz      short loc_180071D79
0x180071d5b  mov     rax, [rax]
0x180071d5e  mov     edx, 7F0h
0x180071d63  mov     rax, [rax+8]
0x180071d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071d6c  test    eax, eax
0x180071d6e  jz      short loc_180071D79
0x180071d70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071d77  jmp     short loc_180071D87
0x180071d79  lea     rcx, qword_1801B07E0; this
0x180071d80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071d87  cmp     byte ptr [rcx+8], 0
0x180071d8b  jz      short loc_180071DAE
0x180071d8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071d92  cmp     [rax+7CCh], ebx
0x180071d98  jz      short loc_180071DAE
0x180071d9a  mov     r9d, ebx; int
0x180071d9d  mov     r8d, 0B40h; int
0x180071da3  mov     rdx, r12; char *
0x180071da6  mov     rcx, rax; this
0x180071da9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071dae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071db5  jb      loc_180071E86
0x180071dbb  mov     edx, 10Dh
0x180071dc0  jmp     loc_180071B83
0x180071dc5  mov     rcx, [rbp+ppvObject]
0x180071dc9  lea     rdx, IID_IPropertyStore
0x180071dd0  mov     r8, rsi
0x180071dd3  mov     rax, [rcx]
0x180071dd6  mov     rax, [rax]
0x180071dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071dde  mov     ebx, eax
0x180071de0  test    eax, eax
0x180071de2  jns     loc_180071E6F
0x180071de8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071def  test    rcx, rcx
0x180071df2  jnz     short loc_180071E35
0x180071df4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071dfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e01  mov     rcx, rax
0x180071e04  test    rax, rax
0x180071e07  jz      short loc_180071E27
0x180071e09  mov     rax, [rax]
0x180071e0c  mov     edx, 7F0h
0x180071e11  mov     rax, [rax+8]
0x180071e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e1a  test    eax, eax
0x180071e1c  jz      short loc_180071E27
0x180071e1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e25  jmp     short loc_180071E35
0x180071e27  lea     rcx, qword_1801B07E0; this
0x180071e2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071e35  cmp     byte ptr [rcx+8], 0
0x180071e39  jz      short loc_180071E5C
0x180071e3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071e40  cmp     [rax+7CCh], ebx
0x180071e46  jz      short loc_180071E5C
0x180071e48  mov     r9d, ebx; int
0x180071e4b  mov     r8d, 0B42h; int
0x180071e51  mov     rdx, r12; char *
0x180071e54  mov     rcx, rax; this
0x180071e57  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071e5c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071e63  jb      short loc_180071E86
0x180071e65  mov     edx, 10Eh
0x180071e6a  jmp     loc_180071B83
0x180071e6f  mov     rcx, [rsi]
0x180071e72  mov     [r14], rcx
0x180071e75  test    rcx, rcx
0x180071e78  jz      short loc_180071E86
0x180071e7a  mov     rax, [rcx]
0x180071e7d  mov     rax, [rax+8]
0x180071e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e86  mov     rcx, [rbp+pszFile]; pv
0x180071e8a  call    cs:__imp_CoTaskMemFree
0x180071e90  lea     rcx, [rbp+ppstm]; void *
0x180071e94  mov     [rbp+pszFile], 0
0x180071e9c  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180071ea1  lea     rcx, [rbp+ppvObject]; void *
0x180071ea5  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180071eaa  lea     rcx, [rbp+arg_0]; this
0x180071eae  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180071eb3  mov     eax, ebx
0x180071eb5  mov     rbx, [rsp+40h+arg_8]
0x180071eba  add     rsp, 40h
0x180071ebe  pop     r14
0x180071ec0  pop     r12
0x180071ec2  pop     rdi
0x180071ec3  pop     rsi
0x180071ec4  pop     rbp
0x180071ec5  retn
```
