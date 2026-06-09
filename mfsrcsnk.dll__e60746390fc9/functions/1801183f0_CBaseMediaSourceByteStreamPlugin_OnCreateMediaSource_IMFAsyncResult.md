# CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource(IMFAsyncResult *)

- ea: `0x1801183f0`
- end: `0x180118884`
- name: `?OnCreateMediaSource@CBaseMediaSourceByteStreamPlugin@@IEAAJPEAUIMFAsyncResult@@@Z`
- size: `1172`
- prototype: `__int64 __fastcall(CBaseMediaSourceByteStreamPlugin *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010fc20`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180047a00`
- `0x180073b14`
- `0x1801183f0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011882d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011882d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011881f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011881f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180118859`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180118859`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011884f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011884f`
- `MFPlat!MFPutWorkItemEx2` at `0x180118807`
- `MFPlat!MFPutWorkItemEx2` at `0x180118807`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180118444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011850d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801185ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011864f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011871c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180118444`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011850d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801185ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011864f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011871c`

## string_xrefs

- `0x180118407`: `CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource`

## pseudocode

```c
__int64 __fastcall CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource(
        CBaseMediaSourceByteStreamPlugin *this,
        struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  wchar_t *v5; // rcx
  int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  IMFAsyncResult *v14; // rsi
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  DWORD v18; // edi
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v30; // sf
  int v32; // [rsp+80h] [rbp+48h] BYREF
  int v33; // [rsp+88h] [rbp+50h] BYREF
  __int64 v34; // [rsp+90h] [rbp+58h] BYREF
  IMFAsyncResult *pResult; // [rsp+98h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v32,
    "CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource",
    158);
  pResult = 0;
  if ( a2 )
  {
    v6 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, IMFAsyncResult **))a2->lpVtbl->GetState)(a2, &pResult);
    if ( v6 >= 0 )
    {
      v14 = pResult;
      if ( pResult )
      {
        v18 = 1;
        if ( LODWORD(pResult[12].lpVtbl) )
        {
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          v6 = -2147467260;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467260 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource",
                183,
                -2147467260);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids,
              this,
              -2147467260);
        }
        else
        {
          v22 = *(_QWORD *)this;
          v34 = 0;
          v6 = (*(__int64 (__fastcall **)(CBaseMediaSourceByteStreamPlugin *, struct IMFAsyncResult *, __int64 *))(v22 + 88))(
                 this,
                 a2,
                 &v34);
          if ( v6 >= 0 )
          {
            ComSmartPtr<CMPEGFrame>::operator=(&v14[15], v34);
            LODWORD(v14[13].lpVtbl) = 0;
          }
          else
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v24 + 8) )
            {
              v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)v26 + 499) != v6 )
                CallStackContext::TraceFailure(v26, "CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource", 191, v6);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids,
                this,
                v6);
          }
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v34);
        }
        lpVtbl = v14[5].lpVtbl;
        LODWORD(v14[6].lpVtbl) = v6;
        if ( lpVtbl )
        {
          v33 = 0;
          v32 = 0;
          if ( (*((int (__fastcall **)(struct IMFAsyncResultVtbl *, int *, int *))lpVtbl->QueryInterface + 3))(
                 lpVtbl,
                 &v33,
                 &v32) >= 0 )
            v18 = v32;
          else
            v32 = 1;
          MFPutWorkItemEx2(v18, 0, v14);
          goto LABEL_73;
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
            v30 = LastError < 0;
            if ( LastError > 0 )
              v30 = 1;
            if ( v30 )
              goto LABEL_73;
          }
        }
        SetEvent(v14[7].lpVtbl);
        goto LABEL_73;
      }
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
          CallStackContext::TraceFailure(v17, "CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource", 176, -2147024809);
      }
      if ( g_wppLevels )
      {
        v9 = 28;
        goto LABEL_12;
      }
    }
    else
    {
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
          CallStackContext::TraceFailure(v13, "CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource", 174, v6);
      }
      if ( g_wppLevels )
      {
        v9 = 27;
        goto LABEL_12;
      }
    }
  }
  else
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
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v8 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v8, "CBaseMediaSourceByteStreamPlugin::OnCreateMediaSource", 168, -2147467261);
    }
    if ( g_wppLevels )
    {
      v9 = 26;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids, this, v6);
    }
  }
LABEL_73:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v32);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801183f0  push    rbp
0x1801183f2  push    rbx
0x1801183f3  push    rsi
0x1801183f4  push    rdi
0x1801183f5  push    r12
0x1801183f7  push    r13
0x1801183f9  push    r14
0x1801183fb  push    r15
0x1801183fd  mov     rbp, rsp
0x180118400  sub     rsp, 38h
0x180118404  mov     r14, rdx
0x180118407  lea     r13, aCbasemediasour_2; "CBaseMediaSourceByteStreamPlugin::OnCre"...
0x18011840e  mov     r15, rcx
0x180118411  mov     rdx, r13; char *
0x180118414  mov     r8d, 9Eh; int
0x18011841a  lea     rcx, [rbp+arg_0]; this
0x18011841e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180118423  xor     r12d, r12d
0x180118426  mov     [rbp+pResult], r12
0x18011842a  test    r14, r14
0x18011842d  jnz     loc_1801184E4
0x180118433  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011843a  mov     ebx, 80004003h
0x18011843f  test    rcx, rcx
0x180118442  jnz     short loc_180118485
0x180118444  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011844a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180118451  mov     rcx, rax
0x180118454  test    rax, rax
0x180118457  jz      short loc_180118477
0x180118459  mov     rax, [rax]
0x18011845c  mov     edx, 7F0h
0x180118461  mov     rax, [rax+8]
0x180118465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011846a  test    eax, eax
0x18011846c  jz      short loc_180118477
0x18011846e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118475  jmp     short loc_180118485
0x180118477  lea     rcx, qword_1801B07E0; this
0x18011847e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180118485  cmp     [rcx+8], r12b
0x180118489  jz      short loc_1801184AC
0x18011848b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180118490  cmp     [rax+7CCh], ebx
0x180118496  jz      short loc_1801184AC
0x180118498  mov     r9d, ebx; int
0x18011849b  mov     r8d, 0A8h; int
0x1801184a1  mov     rdx, r13; char *
0x1801184a4  mov     rcx, rax; this
0x1801184a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801184ac  mov     edi, 1
0x1801184b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801184b8  jb      loc_18011885F
0x1801184be  lea     edx, [rdi+19h]
0x1801184c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801184c8  lea     r8, WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids
0x1801184cf  mov     r9, r15
0x1801184d2  mov     [rsp+38h+var_18], ebx
0x1801184d6  mov     rcx, [rcx+10h]
0x1801184da  call    WPP_SF_qD
0x1801184df  jmp     loc_18011885F
0x1801184e4  mov     rax, [r14]
0x1801184e7  lea     rdx, [rbp+pResult]
0x1801184eb  mov     rcx, r14
0x1801184ee  mov     rax, [rax+18h]
0x1801184f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801184f7  mov     ebx, eax
0x1801184f9  test    eax, eax
0x1801184fb  jns     loc_18011858F
0x180118501  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118508  test    rcx, rcx
0x18011850b  jnz     short loc_18011854E
0x18011850d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180118513  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011851a  mov     rcx, rax
0x18011851d  test    rax, rax
0x180118520  jz      short loc_180118540
0x180118522  mov     rax, [rax]
0x180118525  mov     edx, 7F0h
0x18011852a  mov     rax, [rax+8]
0x18011852e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118533  test    eax, eax
0x180118535  jz      short loc_180118540
0x180118537  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011853e  jmp     short loc_18011854E
0x180118540  lea     rcx, qword_1801B07E0; this
0x180118547  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011854e  cmp     [rcx+8], r12b
0x180118552  jz      short loc_180118575
0x180118554  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180118559  cmp     [rax+7CCh], ebx
0x18011855f  jz      short loc_180118575
0x180118561  mov     r9d, ebx; int
0x180118564  mov     r8d, 0AEh; int
0x18011856a  mov     rdx, r13; char *
0x18011856d  mov     rcx, rax; this
0x180118570  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180118575  mov     edi, 1
0x18011857a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180118581  jb      loc_18011885F
0x180118587  lea     edx, [rdi+1Ah]
0x18011858a  jmp     loc_1801184C1
0x18011858f  mov     rsi, [rbp+pResult]
0x180118593  test    rsi, rsi
0x180118596  jnz     loc_18011862F
0x18011859c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801185a3  mov     ebx, 80070057h
0x1801185a8  test    rcx, rcx
0x1801185ab  jnz     short loc_1801185EE
0x1801185ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801185b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801185ba  mov     rcx, rax
0x1801185bd  test    rax, rax
0x1801185c0  jz      short loc_1801185E0
0x1801185c2  mov     rax, [rax]
0x1801185c5  mov     edx, 7F0h
0x1801185ca  mov     rax, [rax+8]
0x1801185ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801185d3  test    eax, eax
0x1801185d5  jz      short loc_1801185E0
0x1801185d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801185de  jmp     short loc_1801185EE
0x1801185e0  lea     rcx, qword_1801B07E0; this
0x1801185e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801185ee  cmp     [rcx+8], r12b
0x1801185f2  jz      short loc_180118615
0x1801185f4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801185f9  cmp     [rax+7CCh], ebx
0x1801185ff  jz      short loc_180118615
0x180118601  mov     r9d, ebx; int
0x180118604  mov     r8d, 0B0h; int
0x18011860a  mov     rdx, r13; char *
0x18011860d  mov     rcx, rax; this
0x180118610  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180118615  mov     edi, 1
0x18011861a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180118621  jb      loc_18011885F
0x180118627  lea     edx, [rdi+1Bh]
0x18011862a  jmp     loc_1801184C1
0x18011862f  mov     edi, 1
0x180118634  cmp     [rsi+60h], r12d
0x180118638  jz      loc_1801186EC
0x18011863e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118645  mov     ebx, 80004004h
0x18011864a  test    rcx, rcx
0x18011864d  jnz     short loc_180118690
0x18011864f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180118655  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011865c  mov     rcx, rax
0x18011865f  test    rax, rax
0x180118662  jz      short loc_180118682
0x180118664  mov     rax, [rax]
0x180118667  mov     edx, 7F0h
0x18011866c  mov     rax, [rax+8]
0x180118670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118675  test    eax, eax
0x180118677  jz      short loc_180118682
0x180118679  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118680  jmp     short loc_180118690
0x180118682  lea     rcx, qword_1801B07E0; this
0x180118689  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180118690  cmp     [rcx+8], r12b
0x180118694  jz      short loc_1801186B7
0x180118696  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011869b  cmp     [rax+7CCh], ebx
0x1801186a1  jz      short loc_1801186B7
0x1801186a3  mov     r9d, ebx; int
0x1801186a6  mov     r8d, 0B7h; int
0x1801186ac  mov     rdx, r13; char *
0x1801186af  mov     rcx, rax; this
0x1801186b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801186b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801186be  jb      loc_1801187CC
0x1801186c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801186cb  lea     r8, WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids
0x1801186d2  mov     edx, 1Dh
0x1801186d7  mov     [rsp+38h+var_18], ebx
0x1801186db  mov     r9, r15
0x1801186de  mov     rcx, [rcx+10h]
0x1801186e2  call    WPP_SF_qD
0x1801186e7  jmp     loc_1801187CC
0x1801186ec  mov     rax, [r15]
0x1801186ef  lea     r8, [rbp+arg_10]
0x1801186f3  mov     rdx, r14
0x1801186f6  mov     [rbp+arg_10], r12
0x1801186fa  mov     rcx, r15
0x1801186fd  mov     rax, [rax+58h]
0x180118701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118706  mov     ebx, eax
0x180118708  test    eax, eax
0x18011870a  jns     loc_1801187B2
0x180118710  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180118717  test    rcx, rcx
0x18011871a  jnz     short loc_18011875D
0x18011871c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180118722  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180118729  mov     rcx, rax
0x18011872c  test    rax, rax
0x18011872f  jz      short loc_18011874F
0x180118731  mov     rax, [rax]
0x180118734  mov     edx, 7F0h
0x180118739  mov     rax, [rax+8]
0x18011873d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118742  test    eax, eax
0x180118744  jz      short loc_18011874F
0x180118746  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011874d  jmp     short loc_18011875D
0x18011874f  lea     rcx, qword_1801B07E0; this
0x180118756  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011875d  cmp     [rcx+8], r12b
0x180118761  jz      short loc_180118784
0x180118763  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180118768  cmp     [rax+7CCh], ebx
0x18011876e  jz      short loc_180118784
0x180118770  mov     r9d, ebx; int
0x180118773  mov     r8d, 0BFh; int
0x180118779  mov     rdx, r13; char *
0x18011877c  mov     rcx, rax; this
0x18011877f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180118784  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18011878b  jb      short loc_1801187C3
0x18011878d  mov     rcx, cs:WPP_GLOBAL_Control
0x180118794  lea     r8, WPP_bb4b85f11d0837ec2f3505640830e6cd_Traceguids
0x18011879b  mov     edx, 1Eh
0x1801187a0  mov     [rsp+38h+var_18], ebx
0x1801187a4  mov     r9, r15
0x1801187a7  mov     rcx, [rcx+10h]
0x1801187ab  call    WPP_SF_qD
0x1801187b0  jmp     short loc_1801187C3
0x1801187b2  mov     rdx, [rbp+arg_10]
0x1801187b6  lea     rcx, [rsi+78h]
0x1801187ba  call    ??4?$ComSmartPtr@VCMPEGFrame@@@@QEAAPEAVCMPEGFrame@@PEAV1@@Z; ComSmartPtr<CMPEGFrame>::operator=(CMPEGFrame *)
0x1801187bf  mov     [rsi+68h], r12d
0x1801187c3  lea     rcx, [rbp+arg_10]; void *
0x1801187c7  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1801187cc  mov     rcx, [rsi+28h]
0x1801187d0  mov     [rsi+30h], ebx
0x1801187d3  test    rcx, rcx
0x1801187d6  jz      short loc_18011880F
0x1801187d8  mov     [rbp+arg_8], r12d
0x1801187dc  lea     r8, [rbp+arg_0]
0x1801187e0  mov     [rbp+arg_0], r12d
0x1801187e4  lea     rdx, [rbp+arg_8]
0x1801187e8  mov     rax, [rcx]
0x1801187eb  mov     rax, [rax+18h]
0x1801187ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801187f4  test    eax, eax
0x1801187f6  jns     short loc_1801187FD
0x1801187f8  mov     [rbp+arg_0], edi
0x1801187fb  jmp     short loc_180118800
0x1801187fd  mov     edi, [rbp+arg_0]
0x180118800  mov     r8, rsi; pResult
0x180118803  xor     edx, edx; Priority
0x180118805  mov     ecx, edi; dwQueue
0x180118807  call    cs:__imp_MFPutWorkItemEx2
0x18011880d  jmp     short loc_18011885F
0x18011880f  cmp     [rsi+38h], r12
0x180118813  jnz     short loc_180118855
0x180118815  xor     r9d, r9d; lpName
0x180118818  xor     r8d, r8d; bInitialState
0x18011881b  mov     edx, edi; bManualReset
0x18011881d  xor     ecx, ecx; lpEventAttributes
0x18011881f  call    cs:__imp_CreateEventW
0x180118825  mov     rcx, rax; hObject
0x180118828  test    rax, rax
0x18011882b  jnz     short loc_180118845
0x18011882d  call    cs:__imp_GetLastError
0x180118833  test    eax, eax
0x180118835  jle     short loc_180118841
0x180118837  movzx   eax, ax
0x18011883a  or      eax, 80070000h
0x18011883f  test    eax, eax
0x180118841  js      short loc_18011885F
0x180118843  jmp     short loc_180118855
0x180118845  xor     eax, eax
0x180118847  lock cmpxchg [rsi+38h], rcx
0x18011884d  jz      short loc_180118855
0x18011884f  call    cs:__imp_CloseHandle
0x180118855  mov     rcx, [rsi+38h]; hEvent
0x180118859  call    cs:__imp_SetEvent
0x18011885f  lea     rcx, [rbp+pResult]; void *
0x180118863  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180118868  lea     rcx, [rbp+arg_0]; this
0x18011886c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180118871  mov     eax, ebx
0x180118873  add     rsp, 38h
0x180118877  pop     r15
0x180118879  pop     r14
0x18011887b  pop     r13
0x18011887d  pop     r12
0x18011887f  pop     rdi
0x180118880  pop     rsi
0x180118881  pop     rbx
0x180118882  pop     rbp
0x180118883  retn
```
