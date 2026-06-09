# CSAMIByteStreamPlugin::OnSAMISourceOpened(IMFAsyncResult *)

- ea: `0x180116e10`
- end: `0x180117286`
- name: `?OnSAMISourceOpened@CSAMIByteStreamPlugin@@IEAAJPEAUIMFAsyncResult@@@Z`
- size: `1142`
- prototype: `int(CSAMIByteStreamPlugin *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010fc80`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x1800d2f08`
- `0x180116e10`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117231`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180117223`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180117223`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011725d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011725d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117253`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117253`
- `MFPlat!MFPutWorkItemEx2` at `0x18011720a`
- `MFPlat!MFPutWorkItemEx2` at `0x18011720a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180116e63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180116f2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180116fcc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011708b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011712c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180116e63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180116f2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180116fcc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011708b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011712c`

## string_xrefs

- `0x180116e25`: `CSAMIByteStreamPlugin::OnSAMISourceOpened`

## pseudocode

```c
__int64 __fastcall CSAMIByteStreamPlugin::OnSAMISourceOpened(CSAMIByteStreamPlugin *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  wchar_t *v5; // rcx
  int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  IMFAsyncResult *v14; // rsi
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  DWORD v19; // edi
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v31; // sf
  int v33; // [rsp+70h] [rbp+40h] BYREF
  int v34; // [rsp+78h] [rbp+48h] BYREF
  CSAMIMediaSource *v35; // [rsp+80h] [rbp+50h] BYREF
  IMFAsyncResult *pResult; // [rsp+88h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v33,
    "CSAMIByteStreamPlugin::OnSAMISourceOpened",
    276);
  pResult = 0;
  if ( !a2 )
  {
    v5 = (wchar_t *)CallStackTracing::s_wpInstance;
    v6 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CSAMIByteStreamPlugin::OnSAMISourceOpened",
          286,
          -2147467261);
    }
    if ( g_wppLevels )
    {
      v9 = 39;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_dc4445c74a623006578798248b483e8b_Traceguids, this, v6);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  v6 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, IMFAsyncResult **))a2->lpVtbl->GetState)(a2, &pResult);
  if ( v6 >= 0 )
  {
    v14 = pResult;
    if ( !pResult )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      v6 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
        if ( *((_DWORD *)v17 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v17, "CSAMIByteStreamPlugin::OnSAMISourceOpened", 294, -2147024809);
      }
      if ( g_wppLevels )
      {
        v9 = 41;
        goto LABEL_12;
      }
      goto LABEL_72;
    }
    v35 = 0;
    v6 = (*(__int64 (__fastcall **)(struct IMFAsyncResultVtbl *, GUID *, CSAMIMediaSource **))pResult[15].lpVtbl->QueryInterface)(
           pResult[15].lpVtbl,
           &IID_IMFMediaSource,
           &v35);
    v19 = 1;
    if ( v6 >= 0 )
    {
      v6 = CSAMIMediaSource::EndOpen(v35, a2);
      if ( v6 < 0 )
      {
        v25 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != v6 )
            CallStackContext::TraceFailure(v27, "CSAMIByteStreamPlugin::OnSAMISourceOpened", 305, v6);
        }
        if ( g_wppLevels )
        {
          v23 = 43;
          goto LABEL_57;
        }
      }
    }
    else
    {
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != v6 )
          CallStackContext::TraceFailure(v22, "CSAMIByteStreamPlugin::OnSAMISourceOpened", 302, v6);
      }
      if ( g_wppLevels )
      {
        v23 = 42;
LABEL_57:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, WPP_dc4445c74a623006578798248b483e8b_Traceguids, this, v6);
      }
    }
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v35);
    lpVtbl = v14[5].lpVtbl;
    LODWORD(v14[6].lpVtbl) = v6;
    if ( lpVtbl )
    {
      v34 = 0;
      v33 = 0;
      if ( (*((int (__fastcall **)(struct IMFAsyncResultVtbl *, int *, int *))lpVtbl->QueryInterface + 3))(
             lpVtbl,
             &v34,
             &v33) >= 0 )
        v19 = v33;
      else
        v33 = 1;
      MFPutWorkItemEx2(v19, 0, v14);
      goto LABEL_72;
    }
    if ( !v14[7].lpVtbl )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&v14[7], (signed __int64)EventW, 0) )
          CloseHandle(EventW);
      }
      else
      {
        LastError = GetLastError();
        v31 = LastError < 0;
        if ( LastError > 0 )
          v31 = 1;
        if ( v31 )
          goto LABEL_72;
      }
    }
    SetEvent(v14[7].lpVtbl);
    goto LABEL_72;
  }
  v11 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
    CallStackTracing::s_wpInstance = v12;
    if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
    {
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v13 + 499) != v6 )
      CallStackContext::TraceFailure(v13, "CSAMIByteStreamPlugin::OnSAMISourceOpened", 292, v6);
  }
  if ( g_wppLevels )
  {
    v9 = 40;
    goto LABEL_12;
  }
LABEL_72:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v33);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180116e10  push    rbp
0x180116e12  push    rbx
0x180116e13  push    rsi
0x180116e14  push    rdi
0x180116e15  push    r13
0x180116e17  push    r14
0x180116e19  push    r15
0x180116e1b  mov     rbp, rsp
0x180116e1e  sub     rsp, 30h
0x180116e22  mov     r14, rdx
0x180116e25  lea     r13, aCsamibytestrea_3; "CSAMIByteStreamPlugin::OnSAMISourceOpen"...
0x180116e2c  mov     r15, rcx
0x180116e2f  mov     rdx, r13; char *
0x180116e32  mov     r8d, 114h; int
0x180116e38  lea     rcx, [rbp+arg_0]; this
0x180116e3c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180116e41  mov     [rbp+pResult], 0
0x180116e49  test    r14, r14
0x180116e4c  jnz     loc_180116F03
0x180116e52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180116e59  mov     ebx, 80004003h
0x180116e5e  test    rcx, rcx
0x180116e61  jnz     short loc_180116EA4
0x180116e63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180116e69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180116e70  mov     rcx, rax
0x180116e73  test    rax, rax
0x180116e76  jz      short loc_180116E96
0x180116e78  mov     rax, [rax]
0x180116e7b  mov     edx, 7F0h
0x180116e80  mov     rax, [rax+8]
0x180116e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116e89  test    eax, eax
0x180116e8b  jz      short loc_180116E96
0x180116e8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180116e94  jmp     short loc_180116EA4
0x180116e96  lea     rcx, qword_1801B07E0; this
0x180116e9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180116ea4  cmp     byte ptr [rcx+8], 0
0x180116ea8  jz      short loc_180116ECB
0x180116eaa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180116eaf  cmp     [rax+7CCh], ebx
0x180116eb5  jz      short loc_180116ECB
0x180116eb7  mov     r9d, ebx; int
0x180116eba  mov     r8d, 11Eh; int
0x180116ec0  mov     rdx, r13; char *
0x180116ec3  mov     rcx, rax; this
0x180116ec6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180116ecb  mov     edi, 1
0x180116ed0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180116ed7  jb      loc_180117263
0x180116edd  lea     edx, [rdi+26h]
0x180116ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180116ee7  lea     r8, WPP_dc4445c74a623006578798248b483e8b_Traceguids
0x180116eee  mov     r9, r15
0x180116ef1  mov     [rsp+30h+var_10], ebx
0x180116ef5  mov     rcx, [rcx+10h]
0x180116ef9  call    WPP_SF_qD
0x180116efe  jmp     loc_180117263
0x180116f03  mov     rax, [r14]
0x180116f06  lea     rdx, [rbp+pResult]
0x180116f0a  mov     rcx, r14
0x180116f0d  mov     rax, [rax+18h]
0x180116f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116f16  mov     ebx, eax
0x180116f18  test    eax, eax
0x180116f1a  jns     loc_180116FAE
0x180116f20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180116f27  test    rcx, rcx
0x180116f2a  jnz     short loc_180116F6D
0x180116f2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180116f32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180116f39  mov     rcx, rax
0x180116f3c  test    rax, rax
0x180116f3f  jz      short loc_180116F5F
0x180116f41  mov     rax, [rax]
0x180116f44  mov     edx, 7F0h
0x180116f49  mov     rax, [rax+8]
0x180116f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116f52  test    eax, eax
0x180116f54  jz      short loc_180116F5F
0x180116f56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180116f5d  jmp     short loc_180116F6D
0x180116f5f  lea     rcx, qword_1801B07E0; this
0x180116f66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180116f6d  cmp     byte ptr [rcx+8], 0
0x180116f71  jz      short loc_180116F94
0x180116f73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180116f78  cmp     [rax+7CCh], ebx
0x180116f7e  jz      short loc_180116F94
0x180116f80  mov     r9d, ebx; int
0x180116f83  mov     r8d, 124h; int
0x180116f89  mov     rdx, r13; char *
0x180116f8c  mov     rcx, rax; this
0x180116f8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180116f94  mov     edi, 1
0x180116f99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180116fa0  jb      loc_180117263
0x180116fa6  lea     edx, [rdi+27h]
0x180116fa9  jmp     loc_180116EE0
0x180116fae  mov     rsi, [rbp+pResult]
0x180116fb2  test    rsi, rsi
0x180116fb5  jnz     loc_18011704E
0x180116fbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180116fc2  mov     ebx, 80070057h
0x180116fc7  test    rcx, rcx
0x180116fca  jnz     short loc_18011700D
0x180116fcc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180116fd2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180116fd9  mov     rcx, rax
0x180116fdc  test    rax, rax
0x180116fdf  jz      short loc_180116FFF
0x180116fe1  mov     rax, [rax]
0x180116fe4  mov     edx, 7F0h
0x180116fe9  mov     rax, [rax+8]
0x180116fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116ff2  test    eax, eax
0x180116ff4  jz      short loc_180116FFF
0x180116ff6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180116ffd  jmp     short loc_18011700D
0x180116fff  lea     rcx, qword_1801B07E0; this
0x180117006  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011700d  cmp     byte ptr [rcx+8], 0
0x180117011  jz      short loc_180117034
0x180117013  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180117018  cmp     [rax+7CCh], ebx
0x18011701e  jz      short loc_180117034
0x180117020  mov     r9d, ebx; int
0x180117023  mov     r8d, 126h; int
0x180117029  mov     rdx, r13; char *
0x18011702c  mov     rcx, rax; this
0x18011702f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180117034  mov     edi, 1
0x180117039  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180117040  jb      loc_180117263
0x180117046  lea     edx, [rdi+28h]
0x180117049  jmp     loc_180116EE0
0x18011704e  mov     [rbp+arg_10], 0
0x180117056  lea     r8, [rbp+arg_10]
0x18011705a  mov     rcx, [rsi+78h]
0x18011705e  lea     rdx, IID_IMFMediaSource
0x180117065  mov     rax, [rcx]
0x180117068  mov     rax, [rax]
0x18011706b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117070  mov     ebx, eax
0x180117072  mov     edi, 1
0x180117077  test    eax, eax
0x180117079  jns     loc_18011710A
0x18011707f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180117086  test    rcx, rcx
0x180117089  jnz     short loc_1801170CC
0x18011708b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180117091  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180117098  mov     rcx, rax
0x18011709b  test    rax, rax
0x18011709e  jz      short loc_1801170BE
0x1801170a0  mov     rax, [rax]
0x1801170a3  mov     edx, 7F0h
0x1801170a8  mov     rax, [rax+8]
0x1801170ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801170b1  test    eax, eax
0x1801170b3  jz      short loc_1801170BE
0x1801170b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801170bc  jmp     short loc_1801170CC
0x1801170be  lea     rcx, qword_1801B07E0; this
0x1801170c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801170cc  cmp     byte ptr [rcx+8], 0
0x1801170d0  jz      short loc_1801170F3
0x1801170d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801170d7  cmp     [rax+7CCh], ebx
0x1801170dd  jz      short loc_1801170F3
0x1801170df  mov     r9d, ebx; int
0x1801170e2  mov     r8d, 12Eh; int
0x1801170e8  mov     rdx, r13; char *
0x1801170eb  mov     rcx, rax; this
0x1801170ee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801170f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801170fa  jb      loc_1801171C0
0x180117100  mov     edx, 2Ah ; '*'
0x180117105  jmp     loc_1801171A2
0x18011710a  mov     rcx, [rbp+arg_10]; this
0x18011710e  mov     rdx, r14; struct IMFAsyncResult *
0x180117111  call    ?EndOpen@CSAMIMediaSource@@QEAAJPEAUIMFAsyncResult@@@Z; CSAMIMediaSource::EndOpen(IMFAsyncResult *)
0x180117116  mov     ebx, eax
0x180117118  test    eax, eax
0x18011711a  jns     loc_1801171C0
0x180117120  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180117127  test    rcx, rcx
0x18011712a  jnz     short loc_18011716D
0x18011712c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180117132  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180117139  mov     rcx, rax
0x18011713c  test    rax, rax
0x18011713f  jz      short loc_18011715F
0x180117141  mov     rax, [rax]
0x180117144  mov     edx, 7F0h
0x180117149  mov     rax, [rax+8]
0x18011714d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117152  test    eax, eax
0x180117154  jz      short loc_18011715F
0x180117156  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011715d  jmp     short loc_18011716D
0x18011715f  lea     rcx, qword_1801B07E0; this
0x180117166  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011716d  cmp     byte ptr [rcx+8], 0
0x180117171  jz      short loc_180117194
0x180117173  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180117178  cmp     [rax+7CCh], ebx
0x18011717e  jz      short loc_180117194
0x180117180  mov     r9d, ebx; int
0x180117183  mov     r8d, 131h; int
0x180117189  mov     rdx, r13; char *
0x18011718c  mov     rcx, rax; this
0x18011718f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180117194  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18011719b  jb      short loc_1801171C0
0x18011719d  mov     edx, 2Bh ; '+'
0x1801171a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801171a9  lea     r8, WPP_dc4445c74a623006578798248b483e8b_Traceguids
0x1801171b0  mov     r9, r15
0x1801171b3  mov     [rsp+30h+var_10], ebx
0x1801171b7  mov     rcx, [rcx+10h]
0x1801171bb  call    WPP_SF_qD
0x1801171c0  lea     rcx, [rbp+arg_10]; void *
0x1801171c4  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1801171c9  mov     rcx, [rsi+28h]
0x1801171cd  mov     [rsi+30h], ebx
0x1801171d0  test    rcx, rcx
0x1801171d3  jz      short loc_180117212
0x1801171d5  mov     [rbp+arg_8], 0
0x1801171dc  lea     r8, [rbp+arg_0]
0x1801171e0  mov     [rbp+arg_0], 0
0x1801171e7  lea     rdx, [rbp+arg_8]
0x1801171eb  mov     rax, [rcx]
0x1801171ee  mov     rax, [rax+18h]
0x1801171f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801171f7  test    eax, eax
0x1801171f9  jns     short loc_180117200
0x1801171fb  mov     [rbp+arg_0], edi
0x1801171fe  jmp     short loc_180117203
0x180117200  mov     edi, [rbp+arg_0]
0x180117203  mov     r8, rsi; pResult
0x180117206  xor     edx, edx; Priority
0x180117208  mov     ecx, edi; dwQueue
0x18011720a  call    cs:__imp_MFPutWorkItemEx2
0x180117210  jmp     short loc_180117263
0x180117212  cmp     qword ptr [rsi+38h], 0
0x180117217  jnz     short loc_180117259
0x180117219  xor     r9d, r9d; lpName
0x18011721c  xor     r8d, r8d; bInitialState
0x18011721f  mov     edx, edi; bManualReset
0x180117221  xor     ecx, ecx; lpEventAttributes
0x180117223  call    cs:__imp_CreateEventW
0x180117229  mov     rcx, rax; hObject
0x18011722c  test    rax, rax
0x18011722f  jnz     short loc_180117249
0x180117231  call    cs:__imp_GetLastError
0x180117237  test    eax, eax
0x180117239  jle     short loc_180117245
0x18011723b  movzx   eax, ax
0x18011723e  or      eax, 80070000h
0x180117243  test    eax, eax
0x180117245  js      short loc_180117263
0x180117247  jmp     short loc_180117259
0x180117249  xor     eax, eax
0x18011724b  lock cmpxchg [rsi+38h], rcx
0x180117251  jz      short loc_180117259
0x180117253  call    cs:__imp_CloseHandle
0x180117259  mov     rcx, [rsi+38h]; hEvent
0x18011725d  call    cs:__imp_SetEvent
0x180117263  lea     rcx, [rbp+pResult]; void *
0x180117267  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18011726c  lea     rcx, [rbp+arg_0]; this
0x180117270  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180117275  mov     eax, ebx
0x180117277  add     rsp, 30h
0x18011727b  pop     r15
0x18011727d  pop     r14
0x18011727f  pop     r13
0x180117281  pop     rdi
0x180117282  pop     rsi
0x180117283  pop     rbx
0x180117284  pop     rbp
0x180117285  retn
```
