# CBaseMediaSink::GetStreamSinkById(ulong,IMFStreamSink * *)

- ea: `0x1800f58f0`
- end: `0x1800f5d39`
- name: `?GetStreamSinkById@CBaseMediaSink@@UEAAJKPEAPEAUIMFStreamSink@@@Z`
- size: `1097`
- prototype: `__int64 __fastcall(CBaseMediaSink *__hidden this, unsigned int, struct IMFStreamSink **)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016f5b0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x1800f58f0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5948`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5a95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5b2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5beb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5c81`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5948`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5a95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5b2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5beb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5c81`

## string_xrefs

- `0x1800f590a`: `CBaseMediaSink::GetStreamSinkById`
- `0x1800f59a8`: `CBaseMediaSink::GetStreamSinkById`
- `0x1800f5aee`: `CBaseMediaSink::GetStreamSinkById`
- `0x1800f5b83`: `CBaseMediaSink::GetStreamSinkById`
- `0x1800f5c44`: `CBaseMediaSink::GetStreamSinkById`
- `0x1800f5cda`: `CBaseMediaSink::GetStreamSinkById`

## pseudocode

```c
__int64 __fastcall CBaseMediaSink::GetStreamSinkById(CBaseMediaSink *this, int a2, struct IMFStreamSink **a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  char *v7; // rsi
  wchar_t *v8; // rdi
  int v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  char *v13; // r9
  __int64 v14; // rax
  __int64 v15; // rdx
  unsigned int i; // esi
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  struct IMFStreamSink *v20; // rcx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  struct IMFStreamSink *v35; // [rsp+30h] [rbp-10h] BYREF
  char *v36; // [rsp+38h] [rbp-8h]
  unsigned int v38; // [rsp+80h] [rbp+40h] BYREF
  int v39; // [rsp+88h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CBaseMediaSink::GetStreamSinkById", 261);
  v7 = (char *)this - 136;
  v36 = (char *)this - 136;
  if ( a3 )
  {
    v14 = *(_QWORD *)this;
    v38 = 0;
    v9 = (*(__int64 (__fastcall **)(CBaseMediaSink *, unsigned int *))(v14 + 48))(this, &v38);
    for ( i = 0; i < v38; ++i )
    {
      v17 = *(_QWORD *)this;
      v35 = 0;
      v9 = (*(__int64 (__fastcall **)(CBaseMediaSink *, _QWORD, struct IMFStreamSink **))(v17 + 56))(this, i, &v35);
      if ( v9 < 0 )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CBaseMediaSink::GetStreamSinkById", 283, v9);
        }
        v7 = v36;
        if ( g_wppLevels )
        {
          v24 = 30;
LABEL_42:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids, v7, v9);
        }
LABEL_43:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v35);
LABEL_46:
        v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != v9 )
            CallStackContext::TraceFailure(v30, "CBaseMediaSink::GetStreamSinkById", 311, v9);
        }
        if ( g_wppLevels )
        {
          v12 = 32;
          goto LABEL_12;
        }
        goto LABEL_67;
      }
      v39 = 0;
      v9 = ((__int64 (__fastcall *)(struct IMFStreamSink *, int *))v35->lpVtbl->GetIdentifier)(v35, &v39);
      if ( v9 < 0 )
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v9 )
            CallStackContext::TraceFailure(v23, "CBaseMediaSink::GetStreamSinkById", 290, v9);
        }
        v7 = v36;
        if ( g_wppLevels )
        {
          v24 = 31;
          goto LABEL_42;
        }
        goto LABEL_43;
      }
      if ( v39 == a2 )
      {
        v20 = v35;
        *a3 = v35;
        if ( v20 )
          ((void (__fastcall *)(struct IMFStreamSink *))v20->lpVtbl->AddRef)(v20);
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v35);
        goto LABEL_67;
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v35);
    }
    if ( v9 < 0 )
    {
      v7 = v36;
      goto LABEL_46;
    }
    v31 = (wchar_t *)CallStackTracing::s_wpInstance;
    v9 = -1072875853;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
      CallStackTracing::s_wpInstance = v32;
      if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
      {
        v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v31 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)v33 + 499) != -1072875853 )
        CallStackContext::TraceFailure(v33, "CBaseMediaSink::GetStreamSinkById", 315, -1072875853);
    }
    if ( g_wppLevels )
    {
      v13 = v36;
      v12 = 33;
      goto LABEL_66;
    }
  }
  else
  {
    v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    v9 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v6, v5);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v11 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v11, "CBaseMediaSink::GetStreamSinkById", 268, -2147467261);
    }
    if ( g_wppLevels )
    {
      v12 = 29;
LABEL_12:
      v13 = v7;
LABEL_66:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids, v13, v9);
    }
  }
LABEL_67:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800f58f0  mov     [rsp-28h+arg_0], rbx
0x1800f58f5  mov     [rsp-28h+arg_8], edx
0x1800f58f9  push    rbp
0x1800f58fa  push    rsi
0x1800f58fb  push    rdi
0x1800f58fc  push    r12
0x1800f58fe  push    r15
0x1800f5900  mov     rbp, rsp
0x1800f5903  sub     rsp, 40h
0x1800f5907  mov     r12, r8
0x1800f590a  lea     rdx, aCbasemediasink_2; "CBaseMediaSink::GetStreamSinkById"
0x1800f5911  mov     r15, rcx
0x1800f5914  mov     r8d, 105h; int
0x1800f591a  lea     rcx, [rbp+arg_10]; this
0x1800f591e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f5923  lea     rsi, [r15-88h]
0x1800f592a  mov     [rbp+var_8], rsi
0x1800f592e  test    r12, r12
0x1800f5931  jnz     loc_1800F59D7
0x1800f5937  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f593e  mov     ebx, 80004003h
0x1800f5943  test    rdi, rdi
0x1800f5946  jnz     short loc_1800F598F
0x1800f5948  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f594f  nop     dword ptr [rax+rax+00h]
0x1800f5954  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f595b  mov     rcx, rax
0x1800f595e  test    rax, rax
0x1800f5961  jz      short loc_1800F5981
0x1800f5963  mov     rax, [rax]
0x1800f5966  mov     edx, 7F0h
0x1800f596b  mov     rax, [rax+8]
0x1800f596f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5974  test    eax, eax
0x1800f5976  jz      short loc_1800F5981
0x1800f5978  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f597f  jmp     short loc_1800F598F
0x1800f5981  lea     rdi, qword_1801B97E0
0x1800f5988  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f598f  cmp     byte ptr [rdi+8], 0
0x1800f5993  jz      short loc_1800F59BD
0x1800f5995  mov     rcx, rdi; this
0x1800f5998  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f599d  cmp     [rax+7CCh], ebx
0x1800f59a3  jz      short loc_1800F59BD
0x1800f59a5  mov     r9d, ebx; int
0x1800f59a8  lea     rdx, aCbasemediasink_2; "CBaseMediaSink::GetStreamSinkById"
0x1800f59af  mov     r8d, 10Ch; int
0x1800f59b5  mov     rcx, rax; this
0x1800f59b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f59bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f59c4  jb      loc_1800F5D1C
0x1800f59ca  mov     edx, 1Dh
0x1800f59cf  mov     r9, rsi
0x1800f59d2  jmp     loc_1800F5D01
0x1800f59d7  mov     rax, [r15]
0x1800f59da  lea     rdx, [rbp+arg_10]
0x1800f59de  mov     rcx, r15
0x1800f59e1  mov     [rbp+arg_10], 0
0x1800f59e8  mov     rax, [rax+30h]
0x1800f59ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f59f1  mov     ebx, eax
0x1800f59f3  xor     esi, esi
0x1800f59f5  lea     rdi, qword_1801B97E0
0x1800f59fc  cmp     esi, [rbp+arg_10]
0x1800f59ff  jnb     loc_1800F5BD3
0x1800f5a05  mov     rax, [r15]
0x1800f5a08  lea     r8, [rbp+var_10]
0x1800f5a0c  mov     edx, esi
0x1800f5a0e  mov     [rbp+var_10], 0
0x1800f5a16  mov     rcx, r15
0x1800f5a19  mov     rax, [rax+38h]
0x1800f5a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5a22  mov     ebx, eax
0x1800f5a24  test    eax, eax
0x1800f5a26  js      loc_1800F5B1E
0x1800f5a2c  mov     rcx, [rbp+var_10]
0x1800f5a30  lea     rdx, [rbp+arg_18]
0x1800f5a34  mov     [rbp+arg_18], 0
0x1800f5a3b  mov     rax, [rcx]
0x1800f5a3e  mov     rax, [rax+40h]
0x1800f5a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5a47  mov     ebx, eax
0x1800f5a49  test    eax, eax
0x1800f5a4b  js      short loc_1800F5A89
0x1800f5a4d  mov     eax, [rbp+arg_8]
0x1800f5a50  cmp     [rbp+arg_18], eax
0x1800f5a53  jz      short loc_1800F5A62
0x1800f5a55  lea     rcx, [rbp+var_10]; void *
0x1800f5a59  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f5a5e  inc     esi
0x1800f5a60  jmp     short loc_1800F59F5
0x1800f5a62  mov     rcx, [rbp+var_10]
0x1800f5a66  mov     [r12], rcx
0x1800f5a6a  test    rcx, rcx
0x1800f5a6d  jz      short loc_1800F5A7B
0x1800f5a6f  mov     rax, [rcx]
0x1800f5a72  mov     rax, [rax+8]
0x1800f5a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5a7b  lea     rcx, [rbp+var_10]; void *
0x1800f5a7f  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f5a84  jmp     loc_1800F5D1C
0x1800f5a89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5a90  test    rcx, rcx
0x1800f5a93  jnz     short loc_1800F5AD8
0x1800f5a95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f5a9c  nop     dword ptr [rax+rax+00h]
0x1800f5aa1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5aa8  mov     rcx, rax
0x1800f5aab  test    rax, rax
0x1800f5aae  jz      short loc_1800F5ACE
0x1800f5ab0  mov     rax, [rax]
0x1800f5ab3  mov     edx, 7F0h
0x1800f5ab8  mov     rax, [rax+8]
0x1800f5abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5ac1  test    eax, eax
0x1800f5ac3  jz      short loc_1800F5ACE
0x1800f5ac5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5acc  jmp     short loc_1800F5AD8
0x1800f5ace  mov     rcx, rdi; this
0x1800f5ad1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5ad8  cmp     byte ptr [rcx+8], 0
0x1800f5adc  jz      short loc_1800F5B03
0x1800f5ade  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f5ae3  cmp     [rax+7CCh], ebx
0x1800f5ae9  jz      short loc_1800F5B03
0x1800f5aeb  mov     r9d, ebx; int
0x1800f5aee  lea     rdx, aCbasemediasink_2; "CBaseMediaSink::GetStreamSinkById"
0x1800f5af5  mov     r8d, 122h; int
0x1800f5afb  mov     rcx, rax; this
0x1800f5afe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f5b03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f5b0a  mov     rsi, [rbp+var_8]
0x1800f5b0e  jb      loc_1800F5BC8
0x1800f5b14  mov     edx, 1Fh
0x1800f5b19  jmp     loc_1800F5BAA
0x1800f5b1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5b25  test    rcx, rcx
0x1800f5b28  jnz     short loc_1800F5B6D
0x1800f5b2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f5b31  nop     dword ptr [rax+rax+00h]
0x1800f5b36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5b3d  mov     rcx, rax
0x1800f5b40  test    rax, rax
0x1800f5b43  jz      short loc_1800F5B63
0x1800f5b45  mov     rax, [rax]
0x1800f5b48  mov     edx, 7F0h
0x1800f5b4d  mov     rax, [rax+8]
0x1800f5b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5b56  test    eax, eax
0x1800f5b58  jz      short loc_1800F5B63
0x1800f5b5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5b61  jmp     short loc_1800F5B6D
0x1800f5b63  mov     rcx, rdi; this
0x1800f5b66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5b6d  cmp     byte ptr [rcx+8], 0
0x1800f5b71  jz      short loc_1800F5B98
0x1800f5b73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f5b78  cmp     [rax+7CCh], ebx
0x1800f5b7e  jz      short loc_1800F5B98
0x1800f5b80  mov     r9d, ebx; int
0x1800f5b83  lea     rdx, aCbasemediasink_2; "CBaseMediaSink::GetStreamSinkById"
0x1800f5b8a  mov     r8d, 11Bh; int
0x1800f5b90  mov     rcx, rax; this
0x1800f5b93  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f5b98  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f5b9f  mov     rsi, [rbp+var_8]
0x1800f5ba3  jb      short loc_1800F5BC8
0x1800f5ba5  mov     edx, 1Eh
0x1800f5baa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f5bb1  lea     r8, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids
0x1800f5bb8  mov     r9, rsi
0x1800f5bbb  mov     [rsp+40h+var_20], ebx
0x1800f5bbf  mov     rcx, [rcx+10h]
0x1800f5bc3  call    WPP_SF_qD
0x1800f5bc8  lea     rcx, [rbp+var_10]; void *
0x1800f5bcc  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f5bd1  jmp     short loc_1800F5BDF
0x1800f5bd3  test    ebx, ebx
0x1800f5bd5  jns     loc_1800F5C70
0x1800f5bdb  mov     rsi, [rbp+var_8]
0x1800f5bdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5be6  test    rcx, rcx
0x1800f5be9  jnz     short loc_1800F5C2E
0x1800f5beb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f5bf2  nop     dword ptr [rax+rax+00h]
0x1800f5bf7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5bfe  mov     rcx, rax
0x1800f5c01  test    rax, rax
0x1800f5c04  jz      short loc_1800F5C24
0x1800f5c06  mov     rax, [rax]
0x1800f5c09  mov     edx, 7F0h
0x1800f5c0e  mov     rax, [rax+8]
0x1800f5c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5c17  test    eax, eax
0x1800f5c19  jz      short loc_1800F5C24
0x1800f5c1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5c22  jmp     short loc_1800F5C2E
0x1800f5c24  mov     rcx, rdi; this
0x1800f5c27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5c2e  cmp     byte ptr [rcx+8], 0
0x1800f5c32  jz      short loc_1800F5C59
0x1800f5c34  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f5c39  cmp     [rax+7CCh], ebx
0x1800f5c3f  jz      short loc_1800F5C59
0x1800f5c41  mov     r9d, ebx; int
0x1800f5c44  lea     rdx, aCbasemediasink_2; "CBaseMediaSink::GetStreamSinkById"
0x1800f5c4b  mov     r8d, 137h; int
0x1800f5c51  mov     rcx, rax; this
0x1800f5c54  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f5c59  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f5c60  jb      loc_1800F5D1C
0x1800f5c66  mov     edx, 20h ; ' '
0x1800f5c6b  jmp     loc_1800F59CF
0x1800f5c70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5c77  mov     ebx, 0C00D36B3h
0x1800f5c7c  test    rcx, rcx
0x1800f5c7f  jnz     short loc_1800F5CC4
0x1800f5c81  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f5c88  nop     dword ptr [rax+rax+00h]
0x1800f5c8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5c94  mov     rcx, rax
0x1800f5c97  test    rax, rax
0x1800f5c9a  jz      short loc_1800F5CBA
0x1800f5c9c  mov     rax, [rax]
0x1800f5c9f  mov     edx, 7F0h
0x1800f5ca4  mov     rax, [rax+8]
0x1800f5ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5cad  test    eax, eax
0x1800f5caf  jz      short loc_1800F5CBA
0x1800f5cb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5cb8  jmp     short loc_1800F5CC4
0x1800f5cba  mov     rcx, rdi; this
0x1800f5cbd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f5cc4  cmp     byte ptr [rcx+8], 0
0x1800f5cc8  jz      short loc_1800F5CEF
0x1800f5cca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f5ccf  cmp     [rax+7CCh], ebx
0x1800f5cd5  jz      short loc_1800F5CEF
0x1800f5cd7  mov     r9d, ebx; int
0x1800f5cda  lea     rdx, aCbasemediasink_2; "CBaseMediaSink::GetStreamSinkById"
0x1800f5ce1  mov     r8d, 13Bh; int
0x1800f5ce7  mov     rcx, rax; this
0x1800f5cea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f5cef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f5cf6  jb      short loc_1800F5D1C
0x1800f5cf8  mov     r9, [rbp+var_8]
0x1800f5cfc  mov     edx, 21h ; '!'
0x1800f5d01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f5d08  lea     r8, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids
0x1800f5d0f  mov     [rsp+40h+var_20], ebx
0x1800f5d13  mov     rcx, [rcx+10h]
0x1800f5d17  call    WPP_SF_qD
0x1800f5d1c  lea     rcx, [rbp+arg_10]; this
0x1800f5d20  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800f5d25  mov     eax, ebx
0x1800f5d27  mov     rbx, [rsp+40h+arg_0]
0x1800f5d2c  add     rsp, 40h
0x1800f5d30  pop     r15
0x1800f5d32  pop     r12
0x1800f5d34  pop     rdi
0x1800f5d35  pop     rsi
0x1800f5d36  pop     rbp
0x1800f5d37  retn
```
