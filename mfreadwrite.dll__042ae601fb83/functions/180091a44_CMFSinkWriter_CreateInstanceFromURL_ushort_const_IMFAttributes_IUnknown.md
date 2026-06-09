# CMFSinkWriter::CreateInstanceFromURL(ushort const *,IMFAttributes *,IUnknown * *)

- ea: `0x180091a44`
- end: `0x180091fc1`
- name: `?CreateInstanceFromURL@CMFSinkWriter@@SAJPEBGPEAUIMFAttributes@@PEAPEAUIUnknown@@@Z`
- size: `1405`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IMFAttributes *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180071020`

## callees

- `0x180006bd4`
- `0x18000b3b8`
- `0x18000e590`
- `0x180012640`
- `0x1800252a0`
- `0x180091a44`
- `0x180091fc8`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091b7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091cb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091dfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091f40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091b7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091cb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091dfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091ed7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180091b01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180091c38`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180091d81`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180091ec7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180091b01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180091c38`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180091d81`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180091ec7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091aa6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091b27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091bdd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091c5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091d26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091da7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091e6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091eed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091aa6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091b27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091bdd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091c5e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091d26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091da7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091e6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180091eed`
- `MFPlat!MFCreateFile` at `0x180091d05`
- `MFPlat!MFCreateFile` at `0x180091d05`

## string_xrefs

- `0x180091a63`: `CMFSinkWriter::CreateInstanceFromURL`

## pseudocode

```c
__int64 __fastcall CMFSinkWriter::CreateInstanceFromURL(
        const unsigned __int16 *a1,
        struct IMFAttributes *a2,
        struct IUnknown **a3)
{
  int v6; // edx
  HRESULT v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  CallStackTracing *v10; // rdi
  HRESULT Instance; // ebx
  CallStackTracing *v12; // rax
  CallStackContext *v13; // rsi
  DWORD v14; // r14d
  CallStackContext *v15; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  HRESULT v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  CallStackTracing *v24; // rdi
  CallStackTracing *v25; // rax
  CallStackContext *v26; // rsi
  DWORD v27; // r14d
  CallStackContext *v28; // rax
  __int64 v29; // rdx
  CallStackTracing *v30; // rcx
  CallStackTracing *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  CallStackTracing *v35; // rdi
  CallStackTracing *v36; // rax
  CallStackContext *v37; // rsi
  DWORD v38; // r14d
  CallStackContext *v39; // rax
  __int64 v40; // rdx
  CallStackTracing *v41; // rcx
  CallStackTracing *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  CallStackTracing *v46; // rdi
  CallStackTracing *v47; // rax
  CallStackContext *v48; // rsi
  DWORD LastError; // r14d
  CallStackContext *Value; // rax
  __int64 v51; // rdx
  CallStackTracing *v52; // rcx
  CallStackTracing *v53; // rax
  __int64 v54; // rax
  char v56; // [rsp+60h] [rbp+8h] BYREF
  IMFByteStream *ppIByteStream; // [rsp+78h] [rbp+20h] BYREF

  ppIByteStream = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v56, "CMFSinkWriter::CreateInstanceFromURL", 60);
  if ( a1 )
  {
    if ( a3 )
    {
      Instance = MFCreateFile(MF_ACCESSMODE_WRITE, MF_OPENMODE_DELETE_IF_EXIST, MF_FILEFLAGS_NONE, a1, &ppIByteStream);
      if ( Instance >= 0 )
      {
        Instance = CMFSinkWriter::CreateInstance(1u, a1, ppIByteStream, 0, a2, a3);
        if ( Instance < 0 )
        {
          v46 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v45, v44);
            CallStackTracing::s_wpInstance = v47;
            if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
            {
              v46 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v46 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          if ( *((_BYTE *)v46 + 8) )
          {
            v48 = (CallStackTracing *)((char *)v46 + 208);
            LastError = GetLastError();
            Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v46 + 3));
            if ( Value )
            {
              v48 = Value;
            }
            else if ( !GetLastError() )
            {
              v52 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
                CallStackTracing::s_wpInstance = v53;
                if ( v53
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                {
                  v52 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v52 = (CallStackTracing *)&qword_18010C230;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
                }
              }
              v54 = (**(__int64 (__fastcall ***)(CallStackTracing *))v52)(v52);
              if ( v54 )
                v48 = (CallStackContext *)v54;
            }
            SetLastError(LastError);
            if ( *((_DWORD *)v48 + 499) != Instance )
              CallStackContext::TraceFailure(v48, "CMFSinkWriter::CreateInstanceFromURL", 77, Instance);
          }
          if ( g_wppLevels )
          {
            v20 = 13;
            goto LABEL_87;
          }
        }
      }
      else
      {
        v35 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v34, v33);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = (CallStackTracing *)((char *)v35 + 208);
          v38 = GetLastError();
          v39 = (CallStackContext *)TlsGetValue(*((_DWORD *)v35 + 3));
          if ( v39 )
          {
            v37 = v39;
          }
          else if ( !GetLastError() )
          {
            v41 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
              CallStackTracing::s_wpInstance = v42;
              if ( v42
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
              {
                v41 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v41 = (CallStackTracing *)&qword_18010C230;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
              }
            }
            v43 = (**(__int64 (__fastcall ***)(CallStackTracing *))v41)(v41);
            if ( v43 )
              v37 = (CallStackContext *)v43;
          }
          SetLastError(v38);
          if ( *((_DWORD *)v37 + 499) != Instance )
            CallStackContext::TraceFailure(v37, "CMFSinkWriter::CreateInstanceFromURL", 67, Instance);
        }
        if ( g_wppLevels )
        {
          v20 = 12;
          goto LABEL_87;
        }
      }
    }
    else
    {
      v21 = MF::OriginateError((MF *)0x80004003LL, v6);
      v24 = CallStackTracing::s_wpInstance;
      Instance = v21;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v22);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = (CallStackTracing *)((char *)v24 + 208);
        v27 = GetLastError();
        v28 = (CallStackContext *)TlsGetValue(*((_DWORD *)v24 + 3));
        if ( v28 )
        {
          v26 = v28;
        }
        else if ( !GetLastError() )
        {
          v30 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
            CallStackTracing::s_wpInstance = v31;
            if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
            {
              v30 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v30 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v32 = (**(__int64 (__fastcall ***)(CallStackTracing *))v30)(v30);
          if ( v32 )
            v26 = (CallStackContext *)v32;
        }
        SetLastError(v27);
        if ( Instance < 0 && *((_DWORD *)v26 + 499) != Instance )
          CallStackContext::TraceFailure(v26, "CMFSinkWriter::CreateInstanceFromURL", 61, Instance);
      }
      if ( g_wppLevels )
      {
        v20 = 11;
        goto LABEL_87;
      }
    }
  }
  else
  {
    v7 = MF::OriginateError((MF *)0x80070057LL, v6);
    v10 = CallStackTracing::s_wpInstance;
    Instance = v7;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v13 = (CallStackTracing *)((char *)v10 + 208);
      v14 = GetLastError();
      v15 = (CallStackContext *)TlsGetValue(*((_DWORD *)v10 + 3));
      if ( v15 )
      {
        v13 = v15;
      }
      else if ( !GetLastError() )
      {
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v19 = (**(__int64 (__fastcall ***)(CallStackTracing *))v17)(v17);
        if ( v19 )
          v13 = (CallStackContext *)v19;
      }
      SetLastError(v14);
      if ( Instance < 0 && *((_DWORD *)v13 + 499) != Instance )
        CallStackContext::TraceFailure(v13, "CMFSinkWriter::CreateInstanceFromURL", 60, Instance);
    }
    if ( g_wppLevels )
    {
      v20 = 10;
LABEL_87:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_4d1f6947f0d43fe86eef9ca62ba9bf82_Traceguids, 0, Instance);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v56);
  if ( ppIByteStream )
    ((void (__fastcall *)(IMFByteStream *))ppIByteStream->lpVtbl->Release)(ppIByteStream);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180091a44  mov     [rsp+arg_8], rbx
0x180091a49  push    rbp
0x180091a4a  push    rsi
0x180091a4b  push    rdi
0x180091a4c  push    r13
0x180091a4e  push    r14
0x180091a50  sub     rsp, 30h
0x180091a54  mov     rsi, r8
0x180091a57  mov     [rsp+58h+arg_18], 0
0x180091a60  mov     rbp, rdx
0x180091a63  lea     r13, aCmfsinkwriterC_0; "CMFSinkWriter::CreateInstanceFromURL"
0x180091a6a  mov     rdi, rcx
0x180091a6d  mov     rdx, r13; char *
0x180091a70  mov     r8d, 3Ch ; '<'; int
0x180091a76  lea     rcx, [rsp+58h+arg_0]; this
0x180091a7b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180091a80  test    rdi, rdi
0x180091a83  jnz     loc_180091BB7
0x180091a89  mov     ecx, 80070057h; this
0x180091a8e  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x180091a93  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091a9a  mov     ebx, eax
0x180091a9c  mov     ebp, 7F0h
0x180091aa1  test    rdi, rdi
0x180091aa4  jnz     short loc_180091AE4
0x180091aa6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091aac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180091ab3  mov     rcx, rax
0x180091ab6  test    rax, rax
0x180091ab9  jz      short loc_180091AD6
0x180091abb  mov     rdx, [rax]
0x180091abe  mov     rax, [rdx+8]
0x180091ac2  mov     edx, ebp
0x180091ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091ac9  test    eax, eax
0x180091acb  jz      short loc_180091AD6
0x180091acd  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091ad4  jmp     short loc_180091AE4
0x180091ad6  lea     rdi, qword_18010C230
0x180091add  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180091ae4  cmp     byte ptr [rdi+8], 0
0x180091ae8  jz      loc_180091BA0
0x180091aee  lea     rsi, [rdi+0D0h]
0x180091af5  call    cs:__imp_GetLastError
0x180091afb  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180091afe  mov     r14d, eax
0x180091b01  call    cs:__imp_TlsGetValue
0x180091b07  test    rax, rax
0x180091b0a  jz      short loc_180091B11
0x180091b0c  mov     rsi, rax
0x180091b0f  jmp     short loc_180091B77
0x180091b11  call    cs:__imp_GetLastError
0x180091b17  test    eax, eax
0x180091b19  jnz     short loc_180091B77
0x180091b1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091b22  test    rcx, rcx
0x180091b25  jnz     short loc_180091B65
0x180091b27  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091b2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180091b34  mov     rcx, rax
0x180091b37  test    rax, rax
0x180091b3a  jz      short loc_180091B57
0x180091b3c  mov     rax, [rax]
0x180091b3f  mov     edx, ebp
0x180091b41  mov     rax, [rax+8]
0x180091b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091b4a  test    eax, eax
0x180091b4c  jz      short loc_180091B57
0x180091b4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091b55  jmp     short loc_180091B65
0x180091b57  lea     rcx, qword_18010C230
0x180091b5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180091b65  mov     rax, [rcx]
0x180091b68  mov     rax, [rax]
0x180091b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091b70  test    rax, rax
0x180091b73  cmovnz  rsi, rax
0x180091b77  mov     ecx, r14d; dwErrCode
0x180091b7a  call    cs:__imp_SetLastError
0x180091b80  test    ebx, ebx
0x180091b82  jns     short loc_180091BA0
0x180091b84  cmp     [rsi+7CCh], ebx
0x180091b8a  jz      short loc_180091BA0
0x180091b8c  mov     r9d, ebx; int
0x180091b8f  mov     r8d, 3Ch ; '<'; int
0x180091b95  mov     rdx, r13; char *
0x180091b98  mov     rcx, rsi; this
0x180091b9b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180091ba0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180091ba7  jb      loc_180091F8E
0x180091bad  mov     edx, 0Ah
0x180091bb2  jmp     loc_180091F70
0x180091bb7  test    rsi, rsi
0x180091bba  jnz     loc_180091CEE
0x180091bc0  mov     ecx, 80004003h; this
0x180091bc5  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x180091bca  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091bd1  mov     ebx, eax
0x180091bd3  mov     ebp, 7F0h
0x180091bd8  test    rdi, rdi
0x180091bdb  jnz     short loc_180091C1B
0x180091bdd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091be3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180091bea  mov     rcx, rax
0x180091bed  test    rax, rax
0x180091bf0  jz      short loc_180091C0D
0x180091bf2  mov     rax, [rax]
0x180091bf5  mov     edx, ebp
0x180091bf7  mov     rax, [rax+8]
0x180091bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091c00  test    eax, eax
0x180091c02  jz      short loc_180091C0D
0x180091c04  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091c0b  jmp     short loc_180091C1B
0x180091c0d  lea     rdi, qword_18010C230
0x180091c14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180091c1b  cmp     byte ptr [rdi+8], 0
0x180091c1f  jz      loc_180091CD7
0x180091c25  lea     rsi, [rdi+0D0h]
0x180091c2c  call    cs:__imp_GetLastError
0x180091c32  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180091c35  mov     r14d, eax
0x180091c38  call    cs:__imp_TlsGetValue
0x180091c3e  test    rax, rax
0x180091c41  jz      short loc_180091C48
0x180091c43  mov     rsi, rax
0x180091c46  jmp     short loc_180091CAE
0x180091c48  call    cs:__imp_GetLastError
0x180091c4e  test    eax, eax
0x180091c50  jnz     short loc_180091CAE
0x180091c52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091c59  test    rcx, rcx
0x180091c5c  jnz     short loc_180091C9C
0x180091c5e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091c64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180091c6b  mov     rcx, rax
0x180091c6e  test    rax, rax
0x180091c71  jz      short loc_180091C8E
0x180091c73  mov     rax, [rax]
0x180091c76  mov     edx, ebp
0x180091c78  mov     rax, [rax+8]
0x180091c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091c81  test    eax, eax
0x180091c83  jz      short loc_180091C8E
0x180091c85  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091c8c  jmp     short loc_180091C9C
0x180091c8e  lea     rcx, qword_18010C230
0x180091c95  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180091c9c  mov     rax, [rcx]
0x180091c9f  mov     rax, [rax]
0x180091ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091ca7  test    rax, rax
0x180091caa  cmovnz  rsi, rax
0x180091cae  mov     ecx, r14d; dwErrCode
0x180091cb1  call    cs:__imp_SetLastError
0x180091cb7  test    ebx, ebx
0x180091cb9  jns     short loc_180091CD7
0x180091cbb  cmp     [rsi+7CCh], ebx
0x180091cc1  jz      short loc_180091CD7
0x180091cc3  mov     r9d, ebx; int
0x180091cc6  mov     r8d, 3Dh ; '='; int
0x180091ccc  mov     rdx, r13; char *
0x180091ccf  mov     rcx, rsi; this
0x180091cd2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180091cd7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180091cde  jb      loc_180091F8E
0x180091ce4  mov     edx, 0Bh
0x180091ce9  jmp     loc_180091F70
0x180091cee  xor     r8d, r8d; fFlags
0x180091cf1  lea     rax, [rsp+58h+arg_18]
0x180091cf6  mov     r9, rdi; pwszFileURL
0x180091cf9  mov     [rsp+58h+ppIByteStream], rax; ppIByteStream
0x180091cfe  lea     edx, [r8+4]; OpenMode
0x180091d02  lea     ecx, [rdx-2]; AccessMode
0x180091d05  call    cs:__imp_MFCreateFile
0x180091d0b  mov     ebx, eax
0x180091d0d  test    eax, eax
0x180091d0f  jns     loc_180091E33
0x180091d15  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091d1c  mov     ebp, 7F0h
0x180091d21  test    rdi, rdi
0x180091d24  jnz     short loc_180091D64
0x180091d26  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091d2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180091d33  mov     rcx, rax
0x180091d36  test    rax, rax
0x180091d39  jz      short loc_180091D56
0x180091d3b  mov     rax, [rax]
0x180091d3e  mov     edx, ebp
0x180091d40  mov     rax, [rax+8]
0x180091d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091d49  test    eax, eax
0x180091d4b  jz      short loc_180091D56
0x180091d4d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091d54  jmp     short loc_180091D64
0x180091d56  lea     rdi, qword_18010C230
0x180091d5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180091d64  cmp     byte ptr [rdi+8], 0
0x180091d68  jz      loc_180091E1C
0x180091d6e  lea     rsi, [rdi+0D0h]
0x180091d75  call    cs:__imp_GetLastError
0x180091d7b  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180091d7e  mov     r14d, eax
0x180091d81  call    cs:__imp_TlsGetValue
0x180091d87  test    rax, rax
0x180091d8a  jz      short loc_180091D91
0x180091d8c  mov     rsi, rax
0x180091d8f  jmp     short loc_180091DF7
0x180091d91  call    cs:__imp_GetLastError
0x180091d97  test    eax, eax
0x180091d99  jnz     short loc_180091DF7
0x180091d9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091da2  test    rcx, rcx
0x180091da5  jnz     short loc_180091DE5
0x180091da7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091dad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180091db4  mov     rcx, rax
0x180091db7  test    rax, rax
0x180091dba  jz      short loc_180091DD7
0x180091dbc  mov     rax, [rax]
0x180091dbf  mov     edx, ebp
0x180091dc1  mov     rax, [rax+8]
0x180091dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091dca  test    eax, eax
0x180091dcc  jz      short loc_180091DD7
0x180091dce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091dd5  jmp     short loc_180091DE5
0x180091dd7  lea     rcx, qword_18010C230
0x180091dde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180091de5  mov     rax, [rcx]
0x180091de8  mov     rax, [rax]
0x180091deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091df0  test    rax, rax
0x180091df3  cmovnz  rsi, rax
0x180091df7  mov     ecx, r14d; dwErrCode
0x180091dfa  call    cs:__imp_SetLastError
0x180091e00  cmp     [rsi+7CCh], ebx
0x180091e06  jz      short loc_180091E1C
0x180091e08  mov     r9d, ebx; int
0x180091e0b  mov     r8d, 43h ; 'C'; int
0x180091e11  mov     rdx, r13; char *
0x180091e14  mov     rcx, rsi; this
0x180091e17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180091e1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180091e23  jb      loc_180091F8E
0x180091e29  mov     edx, 0Ch
0x180091e2e  jmp     loc_180091F70
0x180091e33  mov     r8, [rsp+58h+arg_18]; struct IMFByteStream *
0x180091e38  xor     r9d, r9d; struct IMFMediaSink *
0x180091e3b  mov     [rsp+58h+var_30], rsi; struct IUnknown **
0x180091e40  mov     rdx, rdi; unsigned __int16 *
0x180091e43  mov     [rsp+58h+ppIByteStream], rbp; struct IMFAttributes *
0x180091e48  lea     ecx, [r9+1]; unsigned int
0x180091e4c  call    ?CreateInstance@CMFSinkWriter@@CAJKPEBGPEAUIMFByteStream@@PEAUIMFMediaSink@@PEAUIMFAttributes@@PEAPEAUIUnknown@@@Z; CMFSinkWriter::CreateInstance(ulong,ushort const *,IMFByteStream *,IMFMediaSink *,IMFAttributes *,IUnknown * *)
0x180091e51  mov     ebx, eax
0x180091e53  test    eax, eax
0x180091e55  jns     loc_180091F8E
0x180091e5b  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091e62  mov     ebp, 7F0h
0x180091e67  test    rdi, rdi
0x180091e6a  jnz     short loc_180091EAA
0x180091e6c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091e72  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180091e79  mov     rcx, rax
0x180091e7c  test    rax, rax
0x180091e7f  jz      short loc_180091E9C
0x180091e81  mov     rax, [rax]
0x180091e84  mov     edx, ebp
0x180091e86  mov     rax, [rax+8]
0x180091e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091e8f  test    eax, eax
0x180091e91  jz      short loc_180091E9C
0x180091e93  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091e9a  jmp     short loc_180091EAA
0x180091e9c  lea     rdi, qword_18010C230
0x180091ea3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180091eaa  cmp     byte ptr [rdi+8], 0
0x180091eae  jz      loc_180091F62
0x180091eb4  lea     rsi, [rdi+0D0h]
0x180091ebb  call    cs:__imp_GetLastError
0x180091ec1  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180091ec4  mov     r14d, eax
0x180091ec7  call    cs:__imp_TlsGetValue
0x180091ecd  test    rax, rax
0x180091ed0  jz      short loc_180091ED7
0x180091ed2  mov     rsi, rax
0x180091ed5  jmp     short loc_180091F3D
0x180091ed7  call    cs:__imp_GetLastError
0x180091edd  test    eax, eax
0x180091edf  jnz     short loc_180091F3D
0x180091ee1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180091ee8  test    rcx, rcx
0x180091eeb  jnz     short loc_180091F2B
0x180091eed  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180091ef3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180091efa  mov     rcx, rax
0x180091efd  test    rax, rax
0x180091f00  jz      short loc_180091F1D
0x180091f02  mov     rax, [rax]
0x180091f05  mov     edx, ebp
  ... truncated ...
```
