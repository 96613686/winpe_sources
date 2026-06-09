# CPluginForByteStreamMediaSource::OnSourceOpened(IMFAsyncResult *)

- ea: `0x180115048`
- end: `0x180115564`
- name: `?OnSourceOpened@CPluginForByteStreamMediaSource@@IEAAJPEAUIMFAsyncResult@@@Z`
- size: `1308`
- prototype: `int(CPluginForByteStreamMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180114b10`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x180115048`
- `0x180142428`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115506`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801154f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801154f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180115532`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180115532`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180115528`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180115528`
- `MFPlat!MFPutWorkItemEx2` at `0x1801154df`
- `MFPlat!MFPutWorkItemEx2` at `0x1801154df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801150a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011516c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011520e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801152c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180115368`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180115409`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801150a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011516c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18011520e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801152c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180115368`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180115409`

## string_xrefs

- `0x18011505d`: `CPluginForByteStreamMediaSource::OnSourceOpened`

## pseudocode

```c
__int64 __fastcall CPluginForByteStreamMediaSource::OnSourceOpened(
        CPluginForByteStreamMediaSource *this,
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
  IMFAsyncResult *v18; // r14
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  DWORD v25; // edi
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  struct IMFAsyncResultVtbl *lpVtbl; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v42; // sf
  int v44; // [rsp+70h] [rbp+40h] BYREF
  int v45; // [rsp+78h] [rbp+48h] BYREF
  CMFByteStreamMediaSource *v46; // [rsp+80h] [rbp+50h] BYREF
  IMFAsyncResult *pResult; // [rsp+88h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v44,
    "CPluginForByteStreamMediaSource::OnSourceOpened",
    260);
  pResult = 0;
  v46 = 0;
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
          "CPluginForByteStreamMediaSource::OnSourceOpened",
          271,
          -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 44;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids, this, v8);
      goto LABEL_84;
    }
    goto LABEL_84;
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
          CallStackContext::TraceFailure(v21, "CPluginForByteStreamMediaSource::OnSourceOpened", 278, -2147024809);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          &WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids,
          this,
          -2147024809);
      goto LABEL_84;
    }
    v8 = (*(__int64 (__fastcall **)(struct IMFAsyncResultVtbl *, GUID *, CMFByteStreamMediaSource **))pResult[15].lpVtbl->QueryInterface)(
           pResult[15].lpVtbl,
           &IID_IMFMediaSource,
           &v46);
    v25 = 1;
    if ( v8 >= 0 )
    {
      if ( v46 )
      {
        v8 = CMFByteStreamMediaSource::EndOpen(v46, a2);
        if ( v8 < 0 )
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
              CallStackContext::TraceFailure(v38, "CPluginForByteStreamMediaSource::OnSourceOpened", 289, v8);
          }
          if ( g_wppLevels )
          {
            v29 = 49;
            goto LABEL_69;
          }
        }
      }
      else
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        v8 = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
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
          if ( *((_DWORD *)v32 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v32, "CPluginForByteStreamMediaSource::OnSourceOpened", 287, -2147024809);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            &WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids,
            this,
            -2147024809);
      }
    }
    else
    {
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != v8 )
          CallStackContext::TraceFailure(v28, "CPluginForByteStreamMediaSource::OnSourceOpened", 284, v8);
      }
      if ( g_wppLevels )
      {
        v29 = 47;
LABEL_69:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, &WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids, this, v8);
      }
    }
    lpVtbl = v18[5].lpVtbl;
    LODWORD(v18[6].lpVtbl) = v8;
    if ( lpVtbl )
    {
      v45 = 0;
      v44 = 0;
      if ( (*((int (__fastcall **)(struct IMFAsyncResultVtbl *, int *, int *))lpVtbl->QueryInterface + 3))(
             lpVtbl,
             &v45,
             &v44) >= 0 )
        v25 = v44;
      else
        v44 = 1;
      MFPutWorkItemEx2(v25, 0, v18);
      goto LABEL_84;
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
        v42 = LastError < 0;
        if ( LastError > 0 )
          v42 = 1;
        if ( v42 )
          goto LABEL_84;
      }
    }
    SetEvent(v18[7].lpVtbl);
    goto LABEL_84;
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
      CallStackContext::TraceFailure(v17, "CPluginForByteStreamMediaSource::OnSourceOpened", 276, v8);
  }
  if ( g_wppLevels )
  {
    v11 = 45;
    goto LABEL_12;
  }
LABEL_84:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v46);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&pResult);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180115048  push    rbp
0x18011504a  push    rbx
0x18011504b  push    rsi
0x18011504c  push    rdi
0x18011504d  push    r13
0x18011504f  push    r14
0x180115051  push    r15
0x180115053  mov     rbp, rsp
0x180115056  sub     rsp, 30h
0x18011505a  mov     rsi, rdx
0x18011505d  lea     r13, aCpluginforbyte; "CPluginForByteStreamMediaSource::OnSour"...
0x180115064  mov     r15, rcx
0x180115067  mov     rdx, r13; char *
0x18011506a  mov     r8d, 104h; int
0x180115070  lea     rcx, [rbp+arg_0]; this
0x180115074  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180115079  mov     [rbp+pResult], 0
0x180115081  mov     [rbp+arg_10], 0
0x180115089  test    rsi, rsi
0x18011508c  jnz     loc_180115143
0x180115092  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180115099  mov     ebx, 80004003h
0x18011509e  test    rcx, rcx
0x1801150a1  jnz     short loc_1801150E4
0x1801150a3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801150a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801150b0  mov     rcx, rax
0x1801150b3  test    rax, rax
0x1801150b6  jz      short loc_1801150D6
0x1801150b8  mov     rax, [rax]
0x1801150bb  mov     edx, 7F0h
0x1801150c0  mov     rax, [rax+8]
0x1801150c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801150c9  test    eax, eax
0x1801150cb  jz      short loc_1801150D6
0x1801150cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801150d4  jmp     short loc_1801150E4
0x1801150d6  lea     rcx, qword_1801B07E0; this
0x1801150dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801150e4  cmp     byte ptr [rcx+8], 0
0x1801150e8  jz      short loc_18011510B
0x1801150ea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801150ef  cmp     [rax+7CCh], ebx
0x1801150f5  jz      short loc_18011510B
0x1801150f7  mov     r9d, ebx; int
0x1801150fa  mov     r8d, 10Fh; int
0x180115100  mov     rdx, r13; char *
0x180115103  mov     rcx, rax; this
0x180115106  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18011510b  mov     edi, 1
0x180115110  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180115117  jb      loc_180115538
0x18011511d  lea     edx, [rdi+2Bh]
0x180115120  mov     [rsp+30h+var_10], ebx
0x180115124  mov     rcx, cs:WPP_GLOBAL_Control
0x18011512b  lea     r8, WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids
0x180115132  mov     r9, r15
0x180115135  mov     rcx, [rcx+10h]
0x180115139  call    WPP_SF_qD
0x18011513e  jmp     loc_180115538
0x180115143  mov     rax, [rsi]
0x180115146  lea     rdx, [rbp+pResult]
0x18011514a  mov     rcx, rsi
0x18011514d  mov     rax, [rax+18h]
0x180115151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115156  mov     ebx, eax
0x180115158  test    eax, eax
0x18011515a  jns     loc_1801151EE
0x180115160  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180115167  test    rcx, rcx
0x18011516a  jnz     short loc_1801151AD
0x18011516c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180115172  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180115179  mov     rcx, rax
0x18011517c  test    rax, rax
0x18011517f  jz      short loc_18011519F
0x180115181  mov     rax, [rax]
0x180115184  mov     edx, 7F0h
0x180115189  mov     rax, [rax+8]
0x18011518d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115192  test    eax, eax
0x180115194  jz      short loc_18011519F
0x180115196  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011519d  jmp     short loc_1801151AD
0x18011519f  lea     rcx, qword_1801B07E0; this
0x1801151a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801151ad  cmp     byte ptr [rcx+8], 0
0x1801151b1  jz      short loc_1801151D4
0x1801151b3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801151b8  cmp     [rax+7CCh], ebx
0x1801151be  jz      short loc_1801151D4
0x1801151c0  mov     r9d, ebx; int
0x1801151c3  mov     r8d, 114h; int
0x1801151c9  mov     rdx, r13; char *
0x1801151cc  mov     rcx, rax; this
0x1801151cf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801151d4  mov     edi, 1
0x1801151d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801151e0  jb      loc_180115538
0x1801151e6  lea     edx, [rdi+2Ch]
0x1801151e9  jmp     loc_180115120
0x1801151ee  mov     r14, [rbp+pResult]
0x1801151f2  test    r14, r14
0x1801151f5  jnz     loc_180115294
0x1801151fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180115202  mov     esi, 80070057h
0x180115207  mov     ebx, esi
0x180115209  test    rcx, rcx
0x18011520c  jnz     short loc_18011524F
0x18011520e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180115214  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18011521b  mov     rcx, rax
0x18011521e  test    rax, rax
0x180115221  jz      short loc_180115241
0x180115223  mov     rax, [rax]
0x180115226  mov     edx, 7F0h
0x18011522b  mov     rax, [rax+8]
0x18011522f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115234  test    eax, eax
0x180115236  jz      short loc_180115241
0x180115238  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011523f  jmp     short loc_18011524F
0x180115241  lea     rcx, qword_1801B07E0; this
0x180115248  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011524f  cmp     byte ptr [rcx+8], 0
0x180115253  jz      short loc_180115276
0x180115255  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18011525a  cmp     [rax+7CCh], esi
0x180115260  jz      short loc_180115276
0x180115262  mov     r9d, esi; int
0x180115265  mov     r8d, 116h; int
0x18011526b  mov     rdx, r13; char *
0x18011526e  mov     rcx, rax; this
0x180115271  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180115276  mov     edi, 1
0x18011527b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180115282  jb      loc_180115538
0x180115288  lea     edx, [rdi+2Dh]
0x18011528b  mov     [rsp+30h+var_10], esi
0x18011528f  jmp     loc_180115124
0x180115294  mov     rcx, [r14+78h]
0x180115298  lea     r8, [rbp+arg_10]
0x18011529c  lea     rdx, IID_IMFMediaSource
0x1801152a3  mov     rax, [rcx]
0x1801152a6  mov     rax, [rax]
0x1801152a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801152ae  mov     ebx, eax
0x1801152b0  mov     edi, 1
0x1801152b5  test    eax, eax
0x1801152b7  jns     loc_180115348
0x1801152bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801152c4  test    rcx, rcx
0x1801152c7  jnz     short loc_18011530A
0x1801152c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801152cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801152d6  mov     rcx, rax
0x1801152d9  test    rax, rax
0x1801152dc  jz      short loc_1801152FC
0x1801152de  mov     rax, [rax]
0x1801152e1  mov     edx, 7F0h
0x1801152e6  mov     rax, [rax+8]
0x1801152ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801152ef  test    eax, eax
0x1801152f1  jz      short loc_1801152FC
0x1801152f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801152fa  jmp     short loc_18011530A
0x1801152fc  lea     rcx, qword_1801B07E0; this
0x180115303  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011530a  cmp     byte ptr [rcx+8], 0
0x18011530e  jz      short loc_180115331
0x180115310  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180115315  cmp     [rax+7CCh], ebx
0x18011531b  jz      short loc_180115331
0x18011531d  mov     r9d, ebx; int
0x180115320  mov     r8d, 11Ch; int
0x180115326  mov     rdx, r13; char *
0x180115329  mov     rcx, rax; this
0x18011532c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180115331  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180115338  jb      loc_18011549D
0x18011533e  mov     edx, 2Fh ; '/'
0x180115343  jmp     loc_18011547F
0x180115348  mov     rcx, [rbp+arg_10]; this
0x18011534c  test    rcx, rcx
0x18011534f  jnz     loc_1801153EB
0x180115355  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011535c  mov     esi, 80070057h
0x180115361  mov     ebx, esi
0x180115363  test    rcx, rcx
0x180115366  jnz     short loc_1801153A9
0x180115368  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011536e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180115375  mov     rcx, rax
0x180115378  test    rax, rax
0x18011537b  jz      short loc_18011539B
0x18011537d  mov     rax, [rax]
0x180115380  mov     edx, 7F0h
0x180115385  mov     rax, [rax+8]
0x180115389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011538e  test    eax, eax
0x180115390  jz      short loc_18011539B
0x180115392  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180115399  jmp     short loc_1801153A9
0x18011539b  lea     rcx, qword_1801B07E0; this
0x1801153a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801153a9  cmp     byte ptr [rcx+8], 0
0x1801153ad  jz      short loc_1801153D0
0x1801153af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801153b4  cmp     [rax+7CCh], esi
0x1801153ba  jz      short loc_1801153D0
0x1801153bc  mov     r9d, esi; int
0x1801153bf  mov     r8d, 11Fh; int
0x1801153c5  mov     rdx, r13; char *
0x1801153c8  mov     rcx, rax; this
0x1801153cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801153d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1801153d7  jb      loc_18011549D
0x1801153dd  mov     edx, 30h ; '0'
0x1801153e2  mov     [rsp+30h+var_10], esi
0x1801153e6  jmp     loc_180115483
0x1801153eb  mov     rdx, rsi; struct IMFAsyncResult *
0x1801153ee  call    ?EndOpen@CMFByteStreamMediaSource@@QEAAJPEAUIMFAsyncResult@@@Z; CMFByteStreamMediaSource::EndOpen(IMFAsyncResult *)
0x1801153f3  mov     ebx, eax
0x1801153f5  test    eax, eax
0x1801153f7  jns     loc_18011549D
0x1801153fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180115404  test    rcx, rcx
0x180115407  jnz     short loc_18011544A
0x180115409  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18011540f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180115416  mov     rcx, rax
0x180115419  test    rax, rax
0x18011541c  jz      short loc_18011543C
0x18011541e  mov     rax, [rax]
0x180115421  mov     edx, 7F0h
0x180115426  mov     rax, [rax+8]
0x18011542a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011542f  test    eax, eax
0x180115431  jz      short loc_18011543C
0x180115433  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18011543a  jmp     short loc_18011544A
0x18011543c  lea     rcx, qword_1801B07E0; this
0x180115443  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011544a  cmp     byte ptr [rcx+8], 0
0x18011544e  jz      short loc_180115471
0x180115450  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180115455  cmp     [rax+7CCh], ebx
0x18011545b  jz      short loc_180115471
0x18011545d  mov     r9d, ebx; int
0x180115460  mov     r8d, 121h; int
0x180115466  mov     rdx, r13; char *
0x180115469  mov     rcx, rax; this
0x18011546c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180115471  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180115478  jb      short loc_18011549D
0x18011547a  mov     edx, 31h ; '1'
0x18011547f  mov     [rsp+30h+var_10], ebx
0x180115483  mov     rcx, cs:WPP_GLOBAL_Control
0x18011548a  lea     r8, WPP_7480abd032773c8d3cc81d2ec55f9c51_Traceguids
0x180115491  mov     r9, r15
0x180115494  mov     rcx, [rcx+10h]
0x180115498  call    WPP_SF_qD
0x18011549d  mov     rcx, [r14+28h]
0x1801154a1  mov     [r14+30h], ebx
0x1801154a5  test    rcx, rcx
0x1801154a8  jz      short loc_1801154E7
0x1801154aa  mov     [rbp+arg_8], 0
0x1801154b1  lea     r8, [rbp+arg_0]
0x1801154b5  mov     [rbp+arg_0], 0
0x1801154bc  lea     rdx, [rbp+arg_8]
0x1801154c0  mov     rax, [rcx]
0x1801154c3  mov     rax, [rax+18h]
0x1801154c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801154cc  test    eax, eax
0x1801154ce  jns     short loc_1801154D5
0x1801154d0  mov     [rbp+arg_0], edi
0x1801154d3  jmp     short loc_1801154D8
0x1801154d5  mov     edi, [rbp+arg_0]
0x1801154d8  mov     r8, r14; pResult
0x1801154db  xor     edx, edx; Priority
0x1801154dd  mov     ecx, edi; dwQueue
0x1801154df  call    cs:__imp_MFPutWorkItemEx2
0x1801154e5  jmp     short loc_180115538
0x1801154e7  cmp     qword ptr [r14+38h], 0
0x1801154ec  jnz     short loc_18011552E
0x1801154ee  xor     r9d, r9d; lpName
0x1801154f1  xor     r8d, r8d; bInitialState
0x1801154f4  mov     edx, edi; bManualReset
0x1801154f6  xor     ecx, ecx; lpEventAttributes
0x1801154f8  call    cs:__imp_CreateEventW
0x1801154fe  mov     rcx, rax; hObject
0x180115501  test    rax, rax
0x180115504  jnz     short loc_18011551E
0x180115506  call    cs:__imp_GetLastError
0x18011550c  test    eax, eax
0x18011550e  jle     short loc_18011551A
0x180115510  movzx   eax, ax
0x180115513  or      eax, 80070000h
0x180115518  test    eax, eax
0x18011551a  js      short loc_180115538
  ... truncated ...
```
