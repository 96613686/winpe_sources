# CMFSinkWriter::GetServiceForStream(ulong,_GUID const &,_GUID const &,void * *)

- ea: `0x180098ab0`
- end: `0x180099021`
- name: `?GetServiceForStream@CMFSinkWriter@@UEAAJKAEBU_GUID@@0PEAPEAX@Z`
- size: `1393`
- prototype: `__int64 __fastcall(CMFSinkWriter *__hidden this, unsigned int, GUID *guidService, IID *riid, LPVOID *ppvObject)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180006bd4`
- `0x18000dee0`
- `0x18000e590`
- `0x180012640`
- `0x1800252a0`
- `0x18002e8a0`
- `0x180098ab0`
- `0x1800db3a0`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098fea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098fea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098c03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098c03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180098bb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180098d09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180098f24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180098bb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180098d09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180098f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098eb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098e9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098eb8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180098b39`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180098c8d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180098ea8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180098b39`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180098c8d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180098ea8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098b5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098c30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098cb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098e4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098ece`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098b5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098c30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098cb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098e4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098ece`
- `MFCORE!MFGetService` at `0x180098d6e`
- `MFCORE!MFGetService` at `0x180098df4`
- `MFCORE!MFGetService` at `0x180098f8e`
- `MFCORE!MFGetService` at `0x180098d6e`
- `MFCORE!MFGetService` at `0x180098df4`
- `MFCORE!MFGetService` at `0x180098f8e`

## string_xrefs

- `0x180098aea`: `CMFSinkWriter::GetServiceForStream`
- `0x180098d1b`: `CMFSinkWriter::GetServiceForStream`
- `0x180098f35`: `CMFSinkWriter::GetServiceForStream`

## pseudocode

```c
__int64 __fastcall CMFSinkWriter::GetServiceForStream(
        CMFSinkWriter *this,
        unsigned int a2,
        GUID *guidService,
        IID *riid,
        LPVOID *ppvObject)
{
  CallStackTracing *v9; // rbx
  char *v10; // rdi
  DWORD LastError; // r13d
  char *Value; // rax
  __int64 v13; // rdx
  CallStackTracing *v14; // rcx
  CallStackTracing *v15; // rax
  __int64 v16; // rax
  int v17; // ebx
  __int128 v18; // xmm0
  IUnknown *v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int SinkWriterStream; // edi
  CallStackTracing *v23; // rsi
  CallStackTracing *v24; // rax
  CallStackContext *v25; // r14
  DWORD v26; // r12d
  CallStackContext *v27; // rax
  __int64 v28; // rdx
  CallStackTracing *v29; // rcx
  CallStackTracing *v30; // rax
  __int64 v31; // rax
  HRESULT v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rax
  IUnknown *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  CallStackTracing *v38; // rbx
  CallStackTracing *v39; // rax
  CallStackContext *v40; // rsi
  DWORD v41; // r14d
  CallStackContext *v42; // rax
  __int64 v43; // rdx
  CallStackTracing *v44; // rcx
  CallStackTracing *v45; // rax
  __int64 v46; // rax
  char v48[8]; // [rsp+30h] [rbp-58h] BYREF
  IUnknown *punkObject[2]; // [rsp+38h] [rbp-50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v48, "CMFSinkWriter::GetServiceForStream", 1302);
  v9 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 75) )
  {
    v10 = (char *)CallStackTracing::s_wpInstance + 208;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)v9 + 3));
      if ( Value )
      {
        v10 = Value;
      }
      else if ( !GetLastError() )
      {
        v14 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v16 = (**(__int64 (__fastcall ***)(CallStackTracing *))v14)(v14);
        if ( v16 )
          v10 = (char *)v16;
      }
      SetLastError(LastError);
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 296LL))(*((_QWORD *)this + 75));
    v18 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, IUnknown **))(**((_QWORD **)this + 75) + 280LL))(
                       *((_QWORD *)this + 75),
                       punkObject);
    *((_DWORD *)v10 + 504) = v17;
    *((_OWORD *)v10 + 125) = v18;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v19 = 0;
  punkObject[0] = 0;
  SinkWriterStream = CMFSinkWriter::CheckState(this, 0);
  if ( SinkWriterStream < 0 )
  {
    v23 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v21, v20);
      CallStackTracing::s_wpInstance = v24;
      if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
      {
        v23 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v23 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v23 + 8) )
    {
      v25 = (CallStackTracing *)((char *)v23 + 208);
      v26 = GetLastError();
      v27 = (CallStackContext *)TlsGetValue(*((_DWORD *)v23 + 3));
      if ( v27 )
      {
        v25 = v27;
      }
      else if ( !GetLastError() )
      {
        v29 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v31 = (**(__int64 (__fastcall ***)(CallStackTracing *))v29)(v29);
        if ( v31 )
          v25 = (CallStackContext *)v31;
      }
      SetLastError(v26);
      if ( *((_DWORD *)v25 + 499) != SinkWriterStream )
        CallStackContext::TraceFailure(v25, "CMFSinkWriter::GetServiceForStream", 1308, SinkWriterStream);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        145,
        &WPP_4d1f6947f0d43fe86eef9ca62ba9bf82_Traceguids,
        this,
        SinkWriterStream);
    goto LABEL_79;
  }
  if ( a2 == -1 )
  {
    if ( *((_DWORD *)this + 34) == 1 )
    {
      v32 = MFGetService(*((IUnknown **)this + 18), guidService, riid, ppvObject);
      SinkWriterStream = v32;
      if ( v32 < 0 )
      {
        if ( g_wppLevels < 0x10u )
          goto LABEL_79;
        v33 = 146;
        goto LABEL_78;
      }
LABEL_51:
      if ( SinkWriterStream >= 0 )
        goto LABEL_81;
      goto LABEL_79;
    }
    v34 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 - *(_QWORD *)&guidService->Data1;
    if ( *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 == *(_QWORD *)&guidService->Data1 )
      v34 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 - *(_QWORD *)guidService->Data4;
    v35 = (IUnknown *)*((_QWORD *)this + 19);
    if ( !v34 )
    {
      v32 = ((__int64 (__fastcall *)(IUnknown *, IID *, LPVOID *))v35->lpVtbl->QueryInterface)(v35, riid, ppvObject);
      SinkWriterStream = v32;
      if ( v32 < 0 )
      {
        if ( g_wppLevels < 0x10u )
          goto LABEL_79;
        v33 = 147;
        goto LABEL_78;
      }
      goto LABEL_51;
    }
    v32 = MFGetService(v35, guidService, riid, ppvObject);
    SinkWriterStream = v32;
    if ( v32 >= 0 )
      goto LABEL_51;
    if ( g_wppLevels < 0x10u )
      goto LABEL_79;
    v33 = 148;
  }
  else
  {
    SinkWriterStream = CMFSinkWriter::GetSinkWriterStream(this, a2, (struct IMFSinkWriterStream **)punkObject);
    if ( SinkWriterStream < 0 )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v37, v36);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = (CallStackTracing *)((char *)v38 + 208);
        v41 = GetLastError();
        v42 = (CallStackContext *)TlsGetValue(*((_DWORD *)v38 + 3));
        if ( v42 )
        {
          v40 = v42;
        }
        else if ( !GetLastError() )
        {
          v44 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
            CallStackTracing::s_wpInstance = v45;
            if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
            {
              v44 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v44 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v46 = (**(__int64 (__fastcall ***)(CallStackTracing *))v44)(v44);
          if ( v46 )
            v40 = (CallStackContext *)v46;
        }
        SetLastError(v41);
        if ( *((_DWORD *)v40 + 499) != SinkWriterStream )
          CallStackContext::TraceFailure(v40, "CMFSinkWriter::GetServiceForStream", 1339, SinkWriterStream);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          149,
          &WPP_4d1f6947f0d43fe86eef9ca62ba9bf82_Traceguids,
          this,
          SinkWriterStream);
      v19 = punkObject[0];
      goto LABEL_79;
    }
    v19 = punkObject[0];
    v32 = MFGetService(punkObject[0], guidService, riid, ppvObject);
    SinkWriterStream = v32;
    if ( v32 >= 0 )
      goto LABEL_81;
    if ( g_wppLevels < 0x10u )
      goto LABEL_79;
    v33 = 150;
  }
LABEL_78:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, &WPP_4d1f6947f0d43fe86eef9ca62ba9bf82_Traceguids, this, v32);
LABEL_79:
  if ( ppvObject )
    *ppvObject = 0;
LABEL_81:
  if ( v19 )
    ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
  return (unsigned int)SinkWriterStream;
}

```

## disassembly

```asm
0x180098ab0  mov     [rsp+arg_8], rbx
0x180098ab5  push    rbp
0x180098ab6  push    rsi
0x180098ab7  push    rdi
0x180098ab8  push    r12
0x180098aba  push    r13
0x180098abc  push    r14
0x180098abe  push    r15
0x180098ac0  sub     rsp, 50h
0x180098ac4  mov     rax, cs:__security_cookie
0x180098acb  xor     rax, rsp
0x180098ace  mov     [rsp+88h+var_40], rax
0x180098ad3  mov     r15, [rsp+88h+ppvObject]
0x180098adb  mov     rsi, r8
0x180098ade  mov     r12d, edx
0x180098ae1  mov     rbp, rcx
0x180098ae4  mov     r8d, 516h; int
0x180098aea  lea     rdx, aCmfsinkwriterG_1; "CMFSinkWriter::GetServiceForStream"
0x180098af1  lea     rcx, [rsp+88h+var_58]; this
0x180098af6  mov     r14, r9
0x180098af9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180098afe  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098b05  xor     eax, eax
0x180098b07  cmp     [rbx+8], al
0x180098b0a  jz      loc_180098BFF
0x180098b10  cmp     [rbp+258h], rax
0x180098b17  jz      loc_180098BFF
0x180098b1d  lea     rdi, [rbx+0D0h]
0x180098b24  cmp     [rbx+8], al
0x180098b27  jz      loc_180098BBB
0x180098b2d  call    cs:__imp_GetLastError
0x180098b33  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180098b36  mov     r13d, eax
0x180098b39  call    cs:__imp_TlsGetValue
0x180098b3f  test    rax, rax
0x180098b42  jz      short loc_180098B49
0x180098b44  mov     rdi, rax
0x180098b47  jmp     short loc_180098BB2
0x180098b49  call    cs:__imp_GetLastError
0x180098b4f  test    eax, eax
0x180098b51  jnz     short loc_180098BB2
0x180098b53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098b5a  test    rcx, rcx
0x180098b5d  jnz     short loc_180098BA0
0x180098b5f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098b65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098b6c  mov     rcx, rax
0x180098b6f  test    rax, rax
0x180098b72  jz      short loc_180098B92
0x180098b74  mov     rax, [rax]
0x180098b77  mov     edx, 7F0h
0x180098b7c  mov     rax, [rax+8]
0x180098b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098b85  test    eax, eax
0x180098b87  jz      short loc_180098B92
0x180098b89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098b90  jmp     short loc_180098BA0
0x180098b92  lea     rcx, qword_18010C230
0x180098b99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098ba0  mov     rax, [rcx]
0x180098ba3  mov     rax, [rax]
0x180098ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098bab  test    rax, rax
0x180098bae  cmovnz  rdi, rax
0x180098bb2  mov     ecx, r13d; dwErrCode
0x180098bb5  call    cs:__imp_SetLastError
0x180098bbb  mov     rcx, [rbp+258h]
0x180098bc2  mov     rax, [rcx]
0x180098bc5  mov     rax, [rax+128h]
0x180098bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098bd1  mov     rcx, [rbp+258h]
0x180098bd8  mov     ebx, eax
0x180098bda  mov     rdx, [rcx]
0x180098bdd  mov     rax, [rdx+118h]
0x180098be4  lea     rdx, [rsp+88h+punkObject]
0x180098be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098bee  movups  xmm0, xmmword ptr [rax]
0x180098bf1  mov     [rdi+7E0h], ebx
0x180098bf7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180098bff  lea     rcx, [rbp+58h]; lpCriticalSection
0x180098c03  call    cs:__imp_EnterCriticalSection
0x180098c09  xor     ebx, ebx
0x180098c0b  xor     edx, edx
0x180098c0d  mov     rcx, rbp
0x180098c10  mov     [rsp+88h+punkObject], rbx
0x180098c15  call    ?CheckState@CMFSinkWriter@@AEAAJW4SINK_WRITER_STATE@1@@Z; CMFSinkWriter::CheckState(CMFSinkWriter::SINK_WRITER_STATE)
0x180098c1a  mov     edi, eax
0x180098c1c  test    eax, eax
0x180098c1e  jns     loc_180098D4B
0x180098c24  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098c2b  test    rsi, rsi
0x180098c2e  jnz     short loc_180098C71
0x180098c30  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098c36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098c3d  mov     rcx, rax
0x180098c40  test    rax, rax
0x180098c43  jz      short loc_180098C63
0x180098c45  mov     rax, [rax]
0x180098c48  mov     edx, 7F0h
0x180098c4d  mov     rax, [rax+8]
0x180098c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c56  test    eax, eax
0x180098c58  jz      short loc_180098C63
0x180098c5a  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098c61  jmp     short loc_180098C71
0x180098c63  lea     rsi, qword_18010C230
0x180098c6a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x180098c71  cmp     [rsi+8], bl
0x180098c74  jz      loc_180098D30
0x180098c7a  lea     r14, [rsi+0D0h]
0x180098c81  call    cs:__imp_GetLastError
0x180098c87  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180098c8a  mov     r12d, eax
0x180098c8d  call    cs:__imp_TlsGetValue
0x180098c93  test    rax, rax
0x180098c96  jz      short loc_180098C9D
0x180098c98  mov     r14, rax
0x180098c9b  jmp     short loc_180098D06
0x180098c9d  call    cs:__imp_GetLastError
0x180098ca3  test    eax, eax
0x180098ca5  jnz     short loc_180098D06
0x180098ca7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098cae  test    rcx, rcx
0x180098cb1  jnz     short loc_180098CF4
0x180098cb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098cb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098cc0  mov     rcx, rax
0x180098cc3  test    rax, rax
0x180098cc6  jz      short loc_180098CE6
0x180098cc8  mov     rax, [rax]
0x180098ccb  mov     edx, 7F0h
0x180098cd0  mov     rax, [rax+8]
0x180098cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cd9  test    eax, eax
0x180098cdb  jz      short loc_180098CE6
0x180098cdd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098ce4  jmp     short loc_180098CF4
0x180098ce6  lea     rcx, qword_18010C230
0x180098ced  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098cf4  mov     rax, [rcx]
0x180098cf7  mov     rax, [rax]
0x180098cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cff  test    rax, rax
0x180098d02  cmovnz  r14, rax
0x180098d06  mov     ecx, r12d; dwErrCode
0x180098d09  call    cs:__imp_SetLastError
0x180098d0f  cmp     [r14+7CCh], edi
0x180098d16  jz      short loc_180098D30
0x180098d18  mov     r9d, edi; int
0x180098d1b  lea     rdx, aCmfsinkwriterG_1; "CMFSinkWriter::GetServiceForStream"
0x180098d22  mov     r8d, 51Ch; int
0x180098d28  mov     rcx, r14; this
0x180098d2b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098d30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180098d37  jb      loc_180098FC6
0x180098d3d  mov     edx, 91h
0x180098d42  mov     [rsp+88h+var_68], edi
0x180098d46  jmp     loc_180098FAC
0x180098d4b  cmp     r12d, 0FFFFFFFFh
0x180098d4f  jnz     loc_180098E24
0x180098d55  cmp     dword ptr [rbp+88h], 1
0x180098d5c  jnz     short loc_180098D95
0x180098d5e  mov     rcx, [rbp+90h]; punkObject
0x180098d65  mov     r9, r15; ppvObject
0x180098d68  mov     r8, r14; riid
0x180098d6b  mov     rdx, rsi; guidService
0x180098d6e  call    cs:__imp_MFGetService
0x180098d74  mov     edi, eax
0x180098d76  test    eax, eax
0x180098d78  jns     loc_180098E17
0x180098d7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180098d85  jb      loc_180098FC6
0x180098d8b  mov     edx, 92h
0x180098d90  jmp     loc_180098FA8
0x180098d95  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180098d9c  sub     rax, [rsi]
0x180098d9f  jnz     short loc_180098DAC
0x180098da1  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180098da8  sub     rax, [rsi+8]
0x180098dac  mov     rcx, [rbp+98h]; punkObject
0x180098db3  test    rax, rax
0x180098db6  setz    al
0x180098db9  test    al, al
0x180098dbb  jz      short loc_180098DEB
0x180098dbd  mov     rax, [rcx]
0x180098dc0  mov     r8, r15
0x180098dc3  mov     rdx, r14
0x180098dc6  mov     rax, [rax]
0x180098dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098dce  mov     edi, eax
0x180098dd0  test    eax, eax
0x180098dd2  jns     short loc_180098E17
0x180098dd4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180098ddb  jb      loc_180098FC6
0x180098de1  mov     edx, 93h
0x180098de6  jmp     loc_180098FA8
0x180098deb  mov     r9, r15; ppvObject
0x180098dee  mov     r8, r14; riid
0x180098df1  mov     rdx, rsi; guidService
0x180098df4  call    cs:__imp_MFGetService
0x180098dfa  mov     edi, eax
0x180098dfc  test    eax, eax
0x180098dfe  jns     short loc_180098E17
0x180098e00  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180098e07  jb      loc_180098FC6
0x180098e0d  mov     edx, 94h
0x180098e12  jmp     loc_180098FA8
0x180098e17  test    edi, edi
0x180098e19  js      loc_180098FC6
0x180098e1f  jmp     loc_180098FD2
0x180098e24  lea     r8, [rsp+88h+punkObject]; struct IMFSinkWriterStream **
0x180098e29  mov     edx, r12d; unsigned int
0x180098e2c  mov     rcx, rbp; this
0x180098e2f  call    ?GetSinkWriterStream@CMFSinkWriter@@AEAAJKPEAPEAUIMFSinkWriterStream@@@Z; CMFSinkWriter::GetSinkWriterStream(ulong,IMFSinkWriterStream * *)
0x180098e34  mov     edi, eax
0x180098e36  test    eax, eax
0x180098e38  jns     loc_180098F7D
0x180098e3e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098e45  test    rbx, rbx
0x180098e48  jnz     short loc_180098E8B
0x180098e4a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098e50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098e57  mov     rcx, rax
0x180098e5a  test    rax, rax
0x180098e5d  jz      short loc_180098E7D
0x180098e5f  mov     rax, [rax]
0x180098e62  mov     edx, 7F0h
0x180098e67  mov     rax, [rax+8]
0x180098e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098e70  test    eax, eax
0x180098e72  jz      short loc_180098E7D
0x180098e74  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098e7b  jmp     short loc_180098E8B
0x180098e7d  lea     rbx, qword_18010C230
0x180098e84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098e8b  cmp     byte ptr [rbx+8], 0
0x180098e8f  jz      loc_180098F4A
0x180098e95  lea     rsi, [rbx+0D0h]
0x180098e9c  call    cs:__imp_GetLastError
0x180098ea2  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180098ea5  mov     r14d, eax
0x180098ea8  call    cs:__imp_TlsGetValue
0x180098eae  test    rax, rax
0x180098eb1  jz      short loc_180098EB8
0x180098eb3  mov     rsi, rax
0x180098eb6  jmp     short loc_180098F21
0x180098eb8  call    cs:__imp_GetLastError
0x180098ebe  test    eax, eax
0x180098ec0  jnz     short loc_180098F21
0x180098ec2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098ec9  test    rcx, rcx
0x180098ecc  jnz     short loc_180098F0F
0x180098ece  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098ed4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098edb  mov     rcx, rax
0x180098ede  test    rax, rax
0x180098ee1  jz      short loc_180098F01
0x180098ee3  mov     rax, [rax]
0x180098ee6  mov     edx, 7F0h
0x180098eeb  mov     rax, [rax+8]
0x180098eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098ef4  test    eax, eax
0x180098ef6  jz      short loc_180098F01
0x180098ef8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098eff  jmp     short loc_180098F0F
0x180098f01  lea     rcx, qword_18010C230
0x180098f08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098f0f  mov     rax, [rcx]
0x180098f12  mov     rax, [rax]
0x180098f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098f1a  test    rax, rax
0x180098f1d  cmovnz  rsi, rax
0x180098f21  mov     ecx, r14d; dwErrCode
0x180098f24  call    cs:__imp_SetLastError
0x180098f2a  cmp     [rsi+7CCh], edi
0x180098f30  jz      short loc_180098F4A
0x180098f32  mov     r9d, edi; int
0x180098f35  lea     rdx, aCmfsinkwriterG_1; "CMFSinkWriter::GetServiceForStream"
0x180098f3c  mov     r8d, 53Bh; int
0x180098f42  mov     rcx, rsi; this
0x180098f45  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098f4a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180098f51  jb      short loc_180098F76
0x180098f53  mov     rcx, cs:WPP_GLOBAL_Control
0x180098f5a  lea     r8, WPP_4d1f6947f0d43fe86eef9ca62ba9bf82_Traceguids
0x180098f61  mov     edx, 95h
0x180098f66  mov     [rsp+88h+var_68], edi
0x180098f6a  mov     r9, rbp
0x180098f6d  mov     rcx, [rcx+10h]
0x180098f71  call    WPP_SF_qD
0x180098f76  mov     rbx, [rsp+88h+punkObject]
0x180098f7b  jmp     short loc_180098FC6
0x180098f7d  mov     rbx, [rsp+88h+punkObject]
0x180098f82  mov     r9, r15; ppvObject
0x180098f85  mov     rcx, rbx; punkObject
0x180098f88  mov     r8, r14; riid
0x180098f8b  mov     rdx, rsi; guidService
0x180098f8e  call    cs:__imp_MFGetService
0x180098f94  mov     edi, eax
0x180098f96  test    eax, eax
  ... truncated ...
```
