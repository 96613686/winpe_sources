# CMFByteStreamMediaSource::GetMetadataPropertyStore(IPropertyStore * *)

- ea: `0x180077758`
- end: `0x180077bc3`
- name: `?GetMetadataPropertyStore@CMFByteStreamMediaSource@@IEAAJPEAPEAUIPropertyStore@@@Z`
- size: `1131`
- prototype: `__int64 __fastcall(CMFByteStreamMediaSource *__hidden this, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180077410`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180053fb8`
- `0x180077758`
- `0x180079680`
- `0x1800d6c9c`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800777d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800778ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007797e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077a30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077ae4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800777d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800778ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007797e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077a30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077ae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077b80`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18007793e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18007795c`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18007793e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18007795c`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::GetMetadataPropertyStore(
        CMFByteStreamMediaSource *this,
        struct IPropertyStore **a2)
{
  HRESULT ByteStreamOriginName; // ebx
  struct IPropertyStore **v5; // rsi
  __int64 v6; // rdx
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  struct IPropertyStore *v27; // rcx
  IStream *ppstm; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppvObject; // [rsp+38h] [rbp-8h] BYREF
  char v31; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v32; // [rsp+80h] [rbp+40h] BYREF
  LPCWSTR pszFile; // [rsp+88h] [rbp+48h] BYREF

  ByteStreamOriginName = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v31,
    "CMFByteStreamMediaSource::GetMetadataPropertyStore",
    2843);
  v5 = (struct IPropertyStore **)((char *)this + 960);
  ppvObject = 0;
  ppstm = 0;
  pszFile = 0;
  v32 = 0;
  if ( *((_QWORD *)this + 120) )
    goto LABEL_59;
  ByteStreamOriginName = CMFByteStreamSourceReader::GetByteStreamOriginName(
                           (CMFByteStreamMediaSource *)((char *)this + 1120),
                           (unsigned __int16 **)&pszFile,
                           &v32);
  if ( ByteStreamOriginName < 0 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ByteStreamOriginName )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFByteStreamMediaSource::GetMetadataPropertyStore",
          2861,
          ByteStreamOriginName);
    }
    if ( g_wppLevels )
    {
      v10 = 266;
LABEL_13:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
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
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != ByteStreamOriginName )
            CallStackContext::TraceFailure(
              v18,
              "CMFByteStreamMediaSource::GetMetadataPropertyStore",
              2877,
              ByteStreamOriginName);
        }
        if ( g_wppLevels )
        {
          v10 = 268;
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
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != ByteStreamOriginName )
          CallStackContext::TraceFailure(
            v22,
            "CMFByteStreamMediaSource::GetMetadataPropertyStore",
            2880,
            ByteStreamOriginName);
      }
      if ( g_wppLevels )
      {
        v10 = 269;
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
      v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != ByteStreamOriginName )
          CallStackContext::TraceFailure(
            v26,
            "CMFByteStreamMediaSource::GetMetadataPropertyStore",
            2882,
            ByteStreamOriginName);
      }
      if ( g_wppLevels )
      {
        v10 = 270;
        goto LABEL_13;
      }
      goto LABEL_61;
    }
LABEL_59:
    v27 = *v5;
    *a2 = *v5;
    if ( v27 )
      ((void (__fastcall *)(struct IPropertyStore *))v27->lpVtbl->AddRef)(v27);
    goto LABEL_61;
  }
  v12 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
    CallStackTracing::s_wpInstance = v13;
    if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
    {
      v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
    if ( *((_DWORD *)v14 + 499) != ByteStreamOriginName )
      CallStackContext::TraceFailure(
        v14,
        "CMFByteStreamMediaSource::GetMetadataPropertyStore",
        2869,
        ByteStreamOriginName);
  }
  if ( g_wppLevels )
  {
    v10 = 267;
    goto LABEL_13;
  }
LABEL_61:
  CoTaskMemFree((LPVOID)pszFile);
  pszFile = 0;
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppstm);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppvObject);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v31);
  return (unsigned int)ByteStreamOriginName;
}

```

## disassembly

```asm
0x180077758  mov     [rsp-28h+arg_8], rbx
0x18007775d  push    rbp
0x18007775e  push    rsi
0x18007775f  push    rdi
0x180077760  push    r12
0x180077762  push    r14
0x180077764  mov     rbp, rsp
0x180077767  sub     rsp, 40h
0x18007776b  mov     r14, rdx
0x18007776e  lea     r12, aCmfbytestreamm_62; "CMFByteStreamMediaSource::GetMetadataPr"...
0x180077775  mov     rdi, rcx
0x180077778  mov     rdx, r12; char *
0x18007777b  mov     r8d, 0B1Bh; int
0x180077781  lea     rcx, [rbp+arg_0]; this
0x180077785  xor     ebx, ebx
0x180077787  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007778c  lea     rsi, [rdi+3C0h]
0x180077793  mov     [rbp+ppvObject], rbx
0x180077797  mov     [rbp+ppstm], rbx
0x18007779b  mov     [rbp+pszFile], rbx
0x18007779f  mov     [rbp+arg_10], ebx
0x1800777a2  cmp     [rsi], rbx
0x1800777a5  jnz     loc_180077B65
0x1800777ab  lea     rcx, [rdi+460h]; this
0x1800777b2  lea     r8, [rbp+arg_10]; unsigned int *
0x1800777b6  lea     rdx, [rbp+pszFile]; unsigned __int16 **
0x1800777ba  call    ?GetByteStreamOriginName@CMFByteStreamSourceReader@@QEAAJPEAPEAGPEAI@Z; CMFByteStreamSourceReader::GetByteStreamOriginName(ushort * *,uint *)
0x1800777bf  mov     ebx, eax
0x1800777c1  test    eax, eax
0x1800777c3  jns     loc_180077878
0x1800777c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800777d0  test    rcx, rcx
0x1800777d3  jnz     short loc_18007781C
0x1800777d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800777dc  nop     dword ptr [rax+rax+00h]
0x1800777e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800777e8  mov     rcx, rax
0x1800777eb  test    rax, rax
0x1800777ee  jz      short loc_18007780E
0x1800777f0  mov     rax, [rax]
0x1800777f3  mov     edx, 7F0h
0x1800777f8  mov     rax, [rax+8]
0x1800777fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077801  test    eax, eax
0x180077803  jz      short loc_18007780E
0x180077805  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007780c  jmp     short loc_18007781C
0x18007780e  lea     rcx, qword_1801B97E0; this
0x180077815  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007781c  cmp     byte ptr [rcx+8], 0
0x180077820  jz      short loc_180077843
0x180077822  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077827  cmp     [rax+7CCh], ebx
0x18007782d  jz      short loc_180077843
0x18007782f  mov     r9d, ebx; int
0x180077832  mov     r8d, 0B2Dh; int
0x180077838  mov     rdx, r12; char *
0x18007783b  mov     rcx, rax; this
0x18007783e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077843  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007784a  jb      loc_180077B7C
0x180077850  mov     edx, 10Ah
0x180077855  mov     rcx, cs:WPP_GLOBAL_Control
0x18007785c  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x180077863  mov     r9, rdi
0x180077866  mov     [rsp+40h+var_20], ebx
0x18007786a  mov     rcx, [rcx+10h]
0x18007786e  call    WPP_SF_qD
0x180077873  jmp     loc_180077B7C
0x180077878  mov     rcx, [rdi+380h]; punkObject
0x18007787f  lea     r9, [rbp+ppvObject]; ppvObject
0x180077883  lea     r8, IID_IInitializeWithStream; riid
0x18007788a  lea     rdx, MF_PROPERTY_HANDLER_SERVICE; guidService
0x180077891  call    MFGetService
0x180077896  mov     ebx, eax
0x180077898  test    eax, eax
0x18007789a  jns     loc_180077931
0x1800778a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800778a7  test    rcx, rcx
0x1800778aa  jnz     short loc_1800778F3
0x1800778ac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800778b3  nop     dword ptr [rax+rax+00h]
0x1800778b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800778bf  mov     rcx, rax
0x1800778c2  test    rax, rax
0x1800778c5  jz      short loc_1800778E5
0x1800778c7  mov     rax, [rax]
0x1800778ca  mov     edx, 7F0h
0x1800778cf  mov     rax, [rax+8]
0x1800778d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778d8  test    eax, eax
0x1800778da  jz      short loc_1800778E5
0x1800778dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800778e3  jmp     short loc_1800778F3
0x1800778e5  lea     rcx, qword_1801B97E0; this
0x1800778ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800778f3  cmp     byte ptr [rcx+8], 0
0x1800778f7  jz      short loc_18007791A
0x1800778f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800778fe  cmp     [rax+7CCh], ebx
0x180077904  jz      short loc_18007791A
0x180077906  mov     r9d, ebx; int
0x180077909  mov     r8d, 0B35h; int
0x18007790f  mov     rdx, r12; char *
0x180077912  mov     rcx, rax; this
0x180077915  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007791a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077921  jb      loc_180077B7C
0x180077927  mov     edx, 10Bh
0x18007792c  jmp     loc_180077855
0x180077931  mov     rcx, [rbp+pszFile]; pszFile
0x180077935  lea     r8, [rbp+ppstm]; ppstm
0x180077939  mov     edx, 1; grfMode
0x18007793e  call    cs:__imp_SHCreateStreamOnFileW
0x180077945  nop     dword ptr [rax+rax+00h]
0x18007794a  test    eax, eax
0x18007794c  jns     loc_180077A03
0x180077952  mov     rcx, [rbp+pszFile]; pszFile
0x180077956  lea     r8, [rbp+ppstm]; ppstm
0x18007795a  xor     edx, edx; grfMode
0x18007795c  call    cs:__imp_SHCreateStreamOnFileW
0x180077963  nop     dword ptr [rax+rax+00h]
0x180077968  mov     ebx, eax
0x18007796a  test    eax, eax
0x18007796c  jns     loc_180077A03
0x180077972  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077979  test    rcx, rcx
0x18007797c  jnz     short loc_1800779C5
0x18007797e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077985  nop     dword ptr [rax+rax+00h]
0x18007798a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077991  mov     rcx, rax
0x180077994  test    rax, rax
0x180077997  jz      short loc_1800779B7
0x180077999  mov     rax, [rax]
0x18007799c  mov     edx, 7F0h
0x1800779a1  mov     rax, [rax+8]
0x1800779a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779aa  test    eax, eax
0x1800779ac  jz      short loc_1800779B7
0x1800779ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800779b5  jmp     short loc_1800779C5
0x1800779b7  lea     rcx, qword_1801B97E0; this
0x1800779be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800779c5  cmp     byte ptr [rcx+8], 0
0x1800779c9  jz      short loc_1800779EC
0x1800779cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800779d0  cmp     [rax+7CCh], ebx
0x1800779d6  jz      short loc_1800779EC
0x1800779d8  mov     r9d, ebx; int
0x1800779db  mov     r8d, 0B3Dh; int
0x1800779e1  mov     rdx, r12; char *
0x1800779e4  mov     rcx, rax; this
0x1800779e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800779ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800779f3  jb      loc_180077B7C
0x1800779f9  mov     edx, 10Ch
0x1800779fe  jmp     loc_180077855
0x180077a03  mov     rcx, [rbp+ppvObject]
0x180077a07  xor     r8d, r8d
0x180077a0a  mov     rdx, [rbp+ppstm]
0x180077a0e  mov     rax, [rcx]
0x180077a11  mov     rax, [rax+18h]
0x180077a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a1a  mov     ebx, eax
0x180077a1c  test    eax, eax
0x180077a1e  jns     loc_180077AB5
0x180077a24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077a2b  test    rcx, rcx
0x180077a2e  jnz     short loc_180077A77
0x180077a30  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077a37  nop     dword ptr [rax+rax+00h]
0x180077a3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077a43  mov     rcx, rax
0x180077a46  test    rax, rax
0x180077a49  jz      short loc_180077A69
0x180077a4b  mov     rax, [rax]
0x180077a4e  mov     edx, 7F0h
0x180077a53  mov     rax, [rax+8]
0x180077a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a5c  test    eax, eax
0x180077a5e  jz      short loc_180077A69
0x180077a60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077a67  jmp     short loc_180077A77
0x180077a69  lea     rcx, qword_1801B97E0; this
0x180077a70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180077a77  cmp     byte ptr [rcx+8], 0
0x180077a7b  jz      short loc_180077A9E
0x180077a7d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077a82  cmp     [rax+7CCh], ebx
0x180077a88  jz      short loc_180077A9E
0x180077a8a  mov     r9d, ebx; int
0x180077a8d  mov     r8d, 0B40h; int
0x180077a93  mov     rdx, r12; char *
0x180077a96  mov     rcx, rax; this
0x180077a99  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077a9e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077aa5  jb      loc_180077B7C
0x180077aab  mov     edx, 10Dh
0x180077ab0  jmp     loc_180077855
0x180077ab5  mov     rcx, [rbp+ppvObject]
0x180077ab9  lea     rdx, IID_IPropertyStore
0x180077ac0  mov     r8, rsi
0x180077ac3  mov     rax, [rcx]
0x180077ac6  mov     rax, [rax]
0x180077ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077ace  mov     ebx, eax
0x180077ad0  test    eax, eax
0x180077ad2  jns     loc_180077B65
0x180077ad8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077adf  test    rcx, rcx
0x180077ae2  jnz     short loc_180077B2B
0x180077ae4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077aeb  nop     dword ptr [rax+rax+00h]
0x180077af0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077af7  mov     rcx, rax
0x180077afa  test    rax, rax
0x180077afd  jz      short loc_180077B1D
0x180077aff  mov     rax, [rax]
0x180077b02  mov     edx, 7F0h
0x180077b07  mov     rax, [rax+8]
0x180077b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b10  test    eax, eax
0x180077b12  jz      short loc_180077B1D
0x180077b14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077b1b  jmp     short loc_180077B2B
0x180077b1d  lea     rcx, qword_1801B97E0; this
0x180077b24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180077b2b  cmp     byte ptr [rcx+8], 0
0x180077b2f  jz      short loc_180077B52
0x180077b31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077b36  cmp     [rax+7CCh], ebx
0x180077b3c  jz      short loc_180077B52
0x180077b3e  mov     r9d, ebx; int
0x180077b41  mov     r8d, 0B42h; int
0x180077b47  mov     rdx, r12; char *
0x180077b4a  mov     rcx, rax; this
0x180077b4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077b52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077b59  jb      short loc_180077B7C
0x180077b5b  mov     edx, 10Eh
0x180077b60  jmp     loc_180077855
0x180077b65  mov     rcx, [rsi]
0x180077b68  mov     [r14], rcx
0x180077b6b  test    rcx, rcx
0x180077b6e  jz      short loc_180077B7C
0x180077b70  mov     rax, [rcx]
0x180077b73  mov     rax, [rax+8]
0x180077b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b7c  mov     rcx, [rbp+pszFile]; pv
0x180077b80  call    cs:__imp_CoTaskMemFree
0x180077b87  nop     dword ptr [rax+rax+00h]
0x180077b8c  lea     rcx, [rbp+ppstm]; void *
0x180077b90  mov     [rbp+pszFile], 0
0x180077b98  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180077b9d  lea     rcx, [rbp+ppvObject]; void *
0x180077ba1  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180077ba6  lea     rcx, [rbp+arg_0]; this
0x180077baa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180077baf  mov     eax, ebx
0x180077bb1  mov     rbx, [rsp+40h+arg_8]
0x180077bb6  add     rsp, 40h
0x180077bba  pop     r14
0x180077bbc  pop     r12
0x180077bbe  pop     rdi
0x180077bbf  pop     rsi
0x180077bc0  pop     rbp
0x180077bc1  retn
```
