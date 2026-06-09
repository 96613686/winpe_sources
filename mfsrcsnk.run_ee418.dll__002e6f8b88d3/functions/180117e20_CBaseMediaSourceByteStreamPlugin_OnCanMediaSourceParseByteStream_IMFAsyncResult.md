# CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream(IMFAsyncResult *)

- ea: `0x180117e20`
- end: `0x1801183e7`
- name: `?OnCanMediaSourceParseByteStream@CBaseMediaSourceByteStreamPlugin@@IEAAJPEAUIMFAsyncResult@@@Z`
- size: `1479`
- prototype: `__int64 __fastcall(CBaseMediaSourceByteStreamPlugin *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010fc00`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x180117e20`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180118392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180118392`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180118384`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180118384`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801183be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801183be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801183b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801183b4`
- `MFPlat!MFPutWorkItemEx2` at `0x18011836c`
- `MFPlat!MFPutWorkItemEx2` at `0x18011836c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180117e72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180117f3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180117fdb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180118078`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180118122`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801181df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011829a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180117e72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180117f3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180117fdb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180118078`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180118122`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801181df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011829a`

## string_xrefs

- `0x180117e35`: `CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream`

## pseudocode

```c
__int64 __fastcall CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream(
        CBaseMediaSourceByteStreamPlugin *this,
        struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  wchar_t *v7; // rcx
  int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  IMFAsyncResult *v18; // rsi
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v48; // sf
  int v50; // [rsp+70h] [rbp+40h] BYREF
  int v51; // [rsp+78h] [rbp+48h] BYREF
  IMFAsyncResult *pResult; // [rsp+80h] [rbp+50h] BYREF
  __int64 v53; // [rsp+88h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v50,
    "CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream",
    96);
  pResult = 0;
  if ( !a2 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream",
          106,
          -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 18;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids, this, v8);
      goto LABEL_94;
    }
    goto LABEL_94;
  }
  v8 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, IMFAsyncResult **))a2->lpVtbl->GetState)(a2, &pResult);
  if ( v8 >= 0 )
  {
    v18 = pResult;
    if ( !pResult )
    {
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      v8 = -2147024809;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != -2147024809 )
          CallStackContext::TraceFailure(
            v21,
            "CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream",
            114,
            -2147024809);
      }
      if ( g_wppLevels )
      {
        v11 = 20;
        goto LABEL_12;
      }
      goto LABEL_94;
    }
    if ( LODWORD(pResult[12].lpVtbl) )
    {
      v22 = (wchar_t *)CallStackTracing::s_wpInstance;
      v8 = -2147467260;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
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
        if ( *((_DWORD *)v24 + 499) != -2147467260 )
          CallStackContext::TraceFailure(
            v24,
            "CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream",
            121,
            -2147467260);
      }
      v25 = 1;
      if ( g_wppLevels )
      {
        v26 = 21;
LABEL_79:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids, this, v8);
      }
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(CBaseMediaSourceByteStreamPlugin *, struct IMFAsyncResult *))(*(_QWORD *)this
                                                                                                  + 72LL))(
             this,
             a2);
      if ( v8 >= 0 )
      {
        v53 = 0;
        v8 = (*((__int64 (__fastcall **)(struct IMFAsyncResultVtbl *, _QWORD, _QWORD, _QWORD, __int64 *))v18[14].lpVtbl->QueryInterface
              + 15))(
               v18[14].lpVtbl,
               0,
               0,
               0,
               &v53);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(CBaseMediaSourceByteStreamPlugin *, struct IMFAsyncResultVtbl *, struct IMFAsyncResultVtbl *, char *, IMFAsyncResult *))(*(_QWORD *)this + 80LL))(
                 this,
                 v18[14].lpVtbl,
                 v18[16].lpVtbl,
                 (char *)this + 16,
                 v18);
          if ( v8 >= 0 )
            goto LABEL_94;
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
            CallStackTracing::s_wpInstance = v43;
            if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
            {
              v42 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v42 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v42 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
            if ( *((_DWORD *)v44 + 499) != v8 )
              CallStackContext::TraceFailure(
                v44,
                "CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream",
                142,
                v8);
          }
          v25 = 1;
          if ( g_wppLevels )
          {
            v26 = 24;
            goto LABEL_79;
          }
        }
        else
        {
          v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != v8 )
              CallStackContext::TraceFailure(
                v38,
                "CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream",
                136,
                v8);
          }
          v25 = 1;
          if ( g_wppLevels )
          {
            v26 = 23;
            goto LABEL_79;
          }
        }
      }
      else
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != v8 )
            CallStackContext::TraceFailure(
              v32,
              "CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream",
              128,
              v8);
        }
        v25 = 1;
        if ( g_wppLevels )
        {
          v26 = 22;
          goto LABEL_79;
        }
      }
    }
    lpVtbl = v18[5].lpVtbl;
    LODWORD(v18[6].lpVtbl) = v8;
    if ( lpVtbl )
    {
      v51 = 0;
      v50 = 0;
      if ( (*((int (__fastcall **)(struct IMFAsyncResultVtbl *, int *, int *))lpVtbl->QueryInterface + 3))(
             lpVtbl,
             &v51,
             &v50) >= 0 )
        v25 = v50;
      else
        v50 = 1;
      MFPutWorkItemEx2(v25, 0, v18);
      goto LABEL_94;
    }
    if ( !v18[7].lpVtbl )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)&v18[7], (signed __int64)EventW, 0) )
          CloseHandle(EventW);
      }
      else
      {
        LastError = GetLastError();
        v48 = LastError < 0;
        if ( LastError > 0 )
          v48 = 1;
        if ( v48 )
          goto LABEL_94;
      }
    }
    SetEvent(v18[7].lpVtbl);
    goto LABEL_94;
  }
  v15 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
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
    if ( *((_DWORD *)v17 + 499) != v8 )
      CallStackContext::TraceFailure(v17, "CBaseMediaSourceByteStreamPlugin::OnCanMediaSourceParseByteStream", 112, v8);
  }
  if ( g_wppLevels )
  {
    v11 = 19;
    goto LABEL_12;
  }
LABEL_94:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v50);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180117e20  push    rbp
0x180117e22  push    rbx
0x180117e23  push    rsi
0x180117e24  push    rdi
0x180117e25  push    r12
0x180117e27  push    r14
0x180117e29  push    r15
0x180117e2b  mov     rbp, rsp
0x180117e2e  sub     rsp, 30h
0x180117e32  mov     rdi, rdx
0x180117e35  lea     r12, aCbasemediasour; "CBaseMediaSourceByteStreamPlugin::OnCan"...
0x180117e3c  mov     r14, rcx
0x180117e3f  mov     rdx, r12; char *
0x180117e42  mov     r8d, 60h ; '`'; int
0x180117e48  lea     rcx, [rbp+arg_0]; this
0x180117e4c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180117e51  xor     r15d, r15d
0x180117e54  mov     [rbp+pResult], r15
0x180117e58  test    rdi, rdi
0x180117e5b  jnz     loc_180117F12
0x180117e61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180117e68  mov     ebx, 80004003h
0x180117e6d  test    rcx, rcx
0x180117e70  jnz     short loc_180117EB3
0x180117e72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180117e78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180117e7f  mov     rcx, rax
0x180117e82  test    rax, rax
0x180117e85  jz      short loc_180117EA5
0x180117e87  mov     rax, [rax]
0x180117e8a  mov     edx, 7F0h
0x180117e8f  mov     rax, [rax+8]
0x180117e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117e98  test    eax, eax
0x180117e9a  jz      short loc_180117EA5
0x180117e9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180117ea3  jmp     short loc_180117EB3
0x180117ea5  lea     rcx, qword_1801B07E0; this
0x180117eac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180117eb3  cmp     [rcx+8], r15b
0x180117eb7  jz      short loc_180117EDA
0x180117eb9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180117ebe  cmp     [rax+7CCh], ebx
0x180117ec4  jz      short loc_180117EDA
0x180117ec6  mov     r9d, ebx; int
0x180117ec9  mov     r8d, 6Ah ; 'j'; int
0x180117ecf  mov     rdx, r12; char *
0x180117ed2  mov     rcx, rax; this
0x180117ed5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180117eda  mov     edi, 1
0x180117edf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180117ee6  jb      loc_1801183C4
0x180117eec  lea     edx, [rdi+11h]
0x180117eef  mov     rcx, cs:WPP_GLOBAL_Control
0x180117ef6  lea     r8, WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids
0x180117efd  mov     r9, r14
0x180117f00  mov     dword ptr [rsp+30h+var_10], ebx
0x180117f04  mov     rcx, [rcx+10h]
0x180117f08  call    WPP_SF_qD
0x180117f0d  jmp     loc_1801183C4
0x180117f12  mov     rax, [rdi]
0x180117f15  lea     rdx, [rbp+pResult]
0x180117f19  mov     rcx, rdi
0x180117f1c  mov     rax, [rax+18h]
0x180117f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117f25  mov     ebx, eax
0x180117f27  test    eax, eax
0x180117f29  jns     loc_180117FBD
0x180117f2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180117f36  test    rcx, rcx
0x180117f39  jnz     short loc_180117F7C
0x180117f3b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180117f41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180117f48  mov     rcx, rax
0x180117f4b  test    rax, rax
0x180117f4e  jz      short loc_180117F6E
0x180117f50  mov     rax, [rax]
0x180117f53  mov     edx, 7F0h
0x180117f58  mov     rax, [rax+8]
0x180117f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117f61  test    eax, eax
0x180117f63  jz      short loc_180117F6E
0x180117f65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180117f6c  jmp     short loc_180117F7C
0x180117f6e  lea     rcx, qword_1801B07E0; this
0x180117f75  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180117f7c  cmp     [rcx+8], r15b
0x180117f80  jz      short loc_180117FA3
0x180117f82  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180117f87  cmp     [rax+7CCh], ebx
0x180117f8d  jz      short loc_180117FA3
0x180117f8f  mov     r9d, ebx; int
0x180117f92  mov     r8d, 70h ; 'p'; int
0x180117f98  mov     rdx, r12; char *
0x180117f9b  mov     rcx, rax; this
0x180117f9e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180117fa3  mov     edi, 1
0x180117fa8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180117faf  jb      loc_1801183C4
0x180117fb5  lea     edx, [rdi+12h]
0x180117fb8  jmp     loc_180117EEF
0x180117fbd  mov     rsi, [rbp+pResult]
0x180117fc1  test    rsi, rsi
0x180117fc4  jnz     loc_18011805D
0x180117fca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180117fd1  mov     ebx, 80070057h
0x180117fd6  test    rcx, rcx
0x180117fd9  jnz     short loc_18011801C
0x180117fdb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180117fe1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180117fe8  mov     rcx, rax
0x180117feb  test    rax, rax
0x180117fee  jz      short loc_18011800E
0x180117ff0  mov     rax, [rax]
0x180117ff3  mov     edx, 7F0h
0x180117ff8  mov     rax, [rax+8]
0x180117ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118001  test    eax, eax
0x180118003  jz      short loc_18011800E
0x180118005  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011800c  jmp     short loc_18011801C
0x18011800e  lea     rcx, qword_1801B07E0; this
0x180118015  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011801c  cmp     [rcx+8], r15b
0x180118020  jz      short loc_180118043
0x180118022  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180118027  cmp     [rax+7CCh], ebx
0x18011802d  jz      short loc_180118043
0x18011802f  mov     r9d, ebx; int
0x180118032  mov     r8d, 72h ; 'r'; int
0x180118038  mov     rdx, r12; char *
0x18011803b  mov     rcx, rax; this
0x18011803e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180118043  mov     edi, 1
0x180118048  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18011804f  jb      loc_1801183C4
0x180118055  lea     edx, [rdi+13h]
0x180118058  jmp     loc_180117EEF
0x18011805d  cmp     [rsi+60h], r15d
0x180118061  jz      loc_1801180FA
0x180118067  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011806e  mov     ebx, 80004004h
0x180118073  test    rcx, rcx
0x180118076  jnz     short loc_1801180B9
0x180118078  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011807e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180118085  mov     rcx, rax
0x180118088  test    rax, rax
0x18011808b  jz      short loc_1801180AB
0x18011808d  mov     rax, [rax]
0x180118090  mov     edx, 7F0h
0x180118095  mov     rax, [rax+8]
0x180118099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011809e  test    eax, eax
0x1801180a0  jz      short loc_1801180AB
0x1801180a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801180a9  jmp     short loc_1801180B9
0x1801180ab  lea     rcx, qword_1801B07E0; this
0x1801180b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801180b9  cmp     [rcx+8], r15b
0x1801180bd  jz      short loc_1801180E0
0x1801180bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801180c4  cmp     [rax+7CCh], ebx
0x1801180ca  jz      short loc_1801180E0
0x1801180cc  mov     r9d, ebx; int
0x1801180cf  mov     r8d, 79h ; 'y'; int
0x1801180d5  mov     rdx, r12; char *
0x1801180d8  mov     rcx, rax; this
0x1801180db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801180e0  mov     edi, 1
0x1801180e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801180ec  jb      loc_180118331
0x1801180f2  lea     edx, [rdi+14h]
0x1801180f5  jmp     loc_180118313
0x1801180fa  mov     rax, [r14]
0x1801180fd  mov     rdx, rdi
0x180118100  mov     rcx, r14
0x180118103  mov     rax, [rax+48h]
0x180118107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011810c  mov     ebx, eax
0x18011810e  test    eax, eax
0x180118110  jns     loc_1801181A4
0x180118116  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011811d  test    rcx, rcx
0x180118120  jnz     short loc_180118163
0x180118122  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180118128  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011812f  mov     rcx, rax
0x180118132  test    rax, rax
0x180118135  jz      short loc_180118155
0x180118137  mov     rax, [rax]
0x18011813a  mov     edx, 7F0h
0x18011813f  mov     rax, [rax+8]
0x180118143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118148  test    eax, eax
0x18011814a  jz      short loc_180118155
0x18011814c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118153  jmp     short loc_180118163
0x180118155  lea     rcx, qword_1801B07E0; this
0x18011815c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180118163  cmp     [rcx+8], r15b
0x180118167  jz      short loc_18011818A
0x180118169  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011816e  cmp     [rax+7CCh], ebx
0x180118174  jz      short loc_18011818A
0x180118176  mov     r9d, ebx; int
0x180118179  mov     r8d, 80h; int
0x18011817f  mov     rdx, r12; char *
0x180118182  mov     rcx, rax; this
0x180118185  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011818a  mov     edi, 1
0x18011818f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180118196  jb      loc_180118331
0x18011819c  lea     edx, [rdi+15h]
0x18011819f  jmp     loc_180118313
0x1801181a4  mov     [rbp+arg_18], r15
0x1801181a8  lea     rdx, [rbp+arg_18]
0x1801181ac  mov     rcx, [rsi+70h]
0x1801181b0  xor     r9d, r9d
0x1801181b3  mov     [rsp+30h+var_10], rdx
0x1801181b8  xor     r8d, r8d
0x1801181bb  xor     edx, edx
0x1801181bd  mov     rax, [rcx]
0x1801181c0  mov     rax, [rax+78h]
0x1801181c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801181c9  mov     ebx, eax
0x1801181cb  test    eax, eax
0x1801181cd  jns     loc_180118261
0x1801181d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801181da  test    rcx, rcx
0x1801181dd  jnz     short loc_180118220
0x1801181df  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801181e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801181ec  mov     rcx, rax
0x1801181ef  test    rax, rax
0x1801181f2  jz      short loc_180118212
0x1801181f4  mov     rax, [rax]
0x1801181f7  mov     edx, 7F0h
0x1801181fc  mov     rax, [rax+8]
0x180118200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118205  test    eax, eax
0x180118207  jz      short loc_180118212
0x180118209  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118210  jmp     short loc_180118220
0x180118212  lea     rcx, qword_1801B07E0; this
0x180118219  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180118220  cmp     [rcx+8], r15b
0x180118224  jz      short loc_180118247
0x180118226  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011822b  cmp     [rax+7CCh], ebx
0x180118231  jz      short loc_180118247
0x180118233  mov     r9d, ebx; int
0x180118236  mov     r8d, 88h; int
0x18011823c  mov     rdx, r12; char *
0x18011823f  mov     rcx, rax; this
0x180118242  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180118247  mov     edi, 1
0x18011824c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180118253  jb      loc_180118331
0x180118259  lea     edx, [rdi+16h]
0x18011825c  jmp     loc_180118313
0x180118261  mov     rax, [r14]
0x180118264  lea     r9, [r14+10h]
0x180118268  mov     r8, [rsi+80h]
0x18011826f  mov     rcx, r14
0x180118272  mov     rdx, [rsi+70h]
0x180118276  mov     [rsp+30h+var_10], rsi
0x18011827b  mov     rax, [rax+50h]
0x18011827f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118284  mov     ebx, eax
0x180118286  test    eax, eax
0x180118288  jns     loc_1801183C4
0x18011828e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118295  test    rcx, rcx
0x180118298  jnz     short loc_1801182DB
0x18011829a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801182a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801182a7  mov     rcx, rax
0x1801182aa  test    rax, rax
0x1801182ad  jz      short loc_1801182CD
0x1801182af  mov     rax, [rax]
0x1801182b2  mov     edx, 7F0h
0x1801182b7  mov     rax, [rax+8]
0x1801182bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801182c0  test    eax, eax
0x1801182c2  jz      short loc_1801182CD
0x1801182c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801182cb  jmp     short loc_1801182DB
0x1801182cd  lea     rcx, qword_1801B07E0; this
0x1801182d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801182db  cmp     [rcx+8], r15b
0x1801182df  jz      short loc_180118302
0x1801182e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801182e6  cmp     [rax+7CCh], ebx
0x1801182ec  jz      short loc_180118302
0x1801182ee  mov     r9d, ebx; int
0x1801182f1  mov     r8d, 8Eh; int
0x1801182f7  mov     rdx, r12; char *
0x1801182fa  mov     rcx, rax; this
0x1801182fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
