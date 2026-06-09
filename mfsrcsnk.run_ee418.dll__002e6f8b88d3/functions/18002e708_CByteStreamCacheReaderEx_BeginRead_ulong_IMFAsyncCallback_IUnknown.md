# CByteStreamCacheReaderEx::BeginRead(ulong,IMFAsyncCallback *,IUnknown *)

- ea: `0x18002e708`
- end: `0x18002ee19`
- name: `?BeginRead@CByteStreamCacheReaderEx@@QEAAJKPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `1809`
- prototype: `__int64 __fastcall(CByteStreamCacheReaderEx *__hidden this, unsigned int, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `7`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002cb50`
- `0x18002e470`
- `0x18007dfa8`
- `0x180085304`
- `0x1800d35b0`
- `0x1800f6920`
- `0x1800f6a24`

## callees

- `0x180010190`
- `0x18001303c`
- `0x18002e708`
- `0x18002ee20`
- `0x18002f904`
- `0x18002f918`
- `0x18004c264`
- `0x180071a44`
- `0x180072124`
- `0x180073b14`
- `0x1800ea240`
- `0x1801095a8`
- `0x180140b84`
- `0x1801696ec`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e777`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e777`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e8ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e8ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e7b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e7b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e96b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e96b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e762`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e911`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e762`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e911`
- `MFPlat!MFPutWorkItemEx2` at `0x18002e8e3`
- `MFPlat!MFPutWorkItemEx2` at `0x18002e8e3`
- `MFPlat!MFLockPlatform` at `0x18002e7fd`
- `MFPlat!MFLockPlatform` at `0x18002e7fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e99a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e9db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eaa2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eade`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eb1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e99a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e9db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eaa2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eade`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eb1a`

## string_xrefs

- `0x18002e73d`: `CByteStreamCacheReaderEx::BeginRead`
- `0x18002e783`: `CByteStreamCacheReaderEx::BeginRead`
- `0x18002eb5a`: `CByteStreamCacheReaderEx::BeginRead`
- `0x18002eb88`: `CByteStreamCacheReaderEx::BeginRead`
- `0x18002ebb6`: `CByteStreamCacheReaderEx::BeginRead`
- `0x18002ebe4`: `CByteStreamCacheReaderEx::BeginRead`

## pseudocode

```c
__int64 __fastcall CByteStreamCacheReaderEx::BeginRead(
        CByteStreamCacheReaderEx *this,
        __int64 a2,
        struct IMFAsyncCallback *a3,
        struct IUnknown *a4)
{
  wchar_t *v4; // rdi
  int v6; // r12d
  DWORD v8; // ebp
  wchar_t *v9; // rsi
  DWORD LastError; // r15d
  wchar_t *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  struct _RTL_CRITICAL_SECTION *v14; // r15
  tagMFASYNCRESULT *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  tagMFASYNCRESULT *v19; // rdi
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 v22; // r9
  unsigned __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // edi
  __int64 v27; // r8
  __int64 v28; // r9
  struct tagMFASYNCRESULT *v29; // rbx
  IMFAsyncCallback *pCallback; // rcx
  CallStackTracing *v31; // rsi
  GUID *v32; // rbx
  DWORD v33; // ebp
  GUID *v34; // rax
  int v35; // eax
  int v36; // eax
  CallStackTracing *v38; // rax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  CallStackTracing *v41; // rcx
  __int64 v42; // rax
  CallStackTracing *v43; // rcx
  __int64 v44; // rax
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  struct CallStackContext *v52; // rax
  struct CallStackContext *v53; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int64 v55; // rax
  unsigned __int64 v56; // rsi
  unsigned __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  int v62; // [rsp+70h] [rbp+8h] BYREF
  struct IUnknown *v63; // [rsp+88h] [rbp+20h] BYREF

  v63 = a4;
  v4 = (wchar_t *)CallStackTracing::s_wpInstance;
  v6 = a2;
  if ( !CallStackTracing::s_wpInstance )
  {
    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2, a3, a4);
    CallStackTracing::s_wpInstance = v38;
    if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
    {
      v4 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v4 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  v8 = 1;
  if ( *((_BYTE *)v4 + 8) )
  {
    v9 = v4 + 104;
    LastError = GetLastError();
    Value = (wchar_t *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v41 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v41 = CallStackTracing::s_wpInstance;
      }
      v42 = (**(__int64 (__fastcall ***)(CallStackTracing *))v41)(v41);
      if ( v42 )
        v9 = (wchar_t *)v42;
    }
    SetLastError(LastError);
    v12 = *((unsigned int *)v9 + 497);
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[4 * v13] = "CByteStreamCacheReaderEx::BeginRead";
      *(_DWORD *)&v9[4 * v13 + 4] = 233;
    }
    ++*((_DWORD *)v9 + 497);
  }
  v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 568);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v15 = (tagMFASYNCRESULT *)operator new(0x68u);
  v19 = v15;
  if ( !v15 )
  {
    v39 = (wchar_t *)CallStackTracing::s_wpInstance;
    v26 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CByteStreamCacheReaderEx::BeginRead", 254, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_96;
    v58 = 19;
    goto LABEL_95;
  }
  tagMFASYNCRESULT::tagMFASYNCRESULT(v15);
  *(_QWORD *)(v20 + 64) = &CMFRefCounted::`vftable';
  *(_DWORD *)(v20 + 72) = 0;
  *(_QWORD *)v20 = &CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'};
  *(_QWORD *)(v20 + 64) = &CAsyncResult::`vftable'{for `CMFRefCounted'};
  *(_DWORD *)(v20 + 96) = 0;
  MFLockPlatform();
  HIDWORD(v19[1].overlapped.hEvent) = 0;
  v19->hrStatusResult = 0;
  v19->hEvent = 0;
  v19[1].overlapped.InternalHigh = 0;
  v19[1].overlapped.Pointer = 0;
  v19->pCallback = a3;
  if ( a3 )
    ((void (__fastcall *)(struct IMFAsyncCallback *))a3->lpVtbl->AddRef)(a3);
  *(_OWORD *)&v19->overlapped.Internal = 0;
  *(_OWORD *)&v19->overlapped.Offset = 0;
  v19->dwBytesTransferred = 0;
  ((void (__fastcall *)(tagMFASYNCRESULT *))v19->AsyncResult.lpVtbl->AddRef)(v19);
  v23 = *((_QWORD *)this + 64);
  *((_QWORD *)this + 2) = v19;
  if ( v23 != -1 )
  {
    v55 = v23 / *(unsigned int *)(*((_QWORD *)this + 65) + 64LL);
    v21 = v23 % *(unsigned int *)(*((_QWORD *)this + 65) + 64LL);
    v56 = v55;
    if ( v55 != *((_QWORD *)this + 5) )
    {
      v57 = -1;
      if ( v55 > *((_QWORD *)this + 5) )
        v57 = v23;
      CByteStreamCacheReaderEx::FlushBuffers(this, v57);
      v26 = CByteStreamCacheReader2::SetCurrentPosition(
              *((CByteStreamCacheReader2 **)this + 65),
              v56 * *(unsigned int *)(*((_QWORD *)this + 65) + 64LL));
      if ( v26 < 0 )
      {
        v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v23, v22);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
          if ( *((_DWORD *)v51 + 499) != v26 )
            CallStackContext::TraceFailure(v51, "CByteStreamCacheReaderEx::BeginRead", 274, v26);
        }
        if ( !g_wppLevels )
          goto LABEL_96;
        v58 = 20;
        goto LABEL_95;
      }
      *((_QWORD *)this + 5) = v56;
    }
    *((_QWORD *)this + 63) = *((_QWORD *)this + 64);
    *((_QWORD *)this + 64) = -1;
  }
  *((_DWORD *)this + 6) = v6;
  v24 = *((_QWORD *)this + 4);
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    *((_QWORD *)this + 4) = 0;
  }
  v26 = CByteStreamCacheReaderEx::ReturnResult(this, v21, v23, v22);
  if ( v26 < 0 )
  {
    v47 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v27, v28);
      CallStackTracing::s_wpInstance = v48;
      if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
      {
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v47 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v47 + 8) )
    {
      v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
      if ( *((_DWORD *)v52 + 499) != v26 )
        CallStackContext::TraceFailure(v52, "CByteStreamCacheReaderEx::BeginRead", 287, v26);
    }
    if ( !g_wppLevels )
      goto LABEL_96;
    v58 = 21;
    goto LABEL_95;
  }
  if ( *((_QWORD *)this + 4) )
  {
    v29 = (struct tagMFASYNCRESULT *)*((_QWORD *)this + 2);
    pCallback = v29->pCallback;
    v29->hrStatusResult = 0;
    if ( pCallback )
    {
      v62 = 0;
      LODWORD(v63) = 0;
      if ( ((int (__fastcall *)(IMFAsyncCallback *, int *, struct IUnknown **))pCallback->lpVtbl->GetParameters)(
             pCallback,
             &v62,
             &v63) >= 0 )
        v8 = (unsigned int)v63;
      else
        LODWORD(v63) = 1;
      MFPutWorkItemEx2(v8, 0, &v29->AsyncResult);
    }
    else
    {
      CAsyncResult::SignalEvent(v29);
    }
    goto LABEL_20;
  }
  if ( (unsigned __int8)byte_1801B110B >= 0x10u )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      22,
      &WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids,
      this,
      *((_QWORD *)this + 63));
  v26 = CByteStreamCacheReader2::BeginCacheRead(
          *((CByteStreamCacheReader2 **)this + 65),
          (struct IMFAsyncCallback *)this + 66,
          0);
  if ( v26 < 0 )
  {
    v49 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59, v60, v61);
      CallStackTracing::s_wpInstance = v50;
      if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
      {
        v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v49 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v49 + 8) )
    {
      v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
      if ( *((_DWORD *)v53 + 499) != v26 )
        CallStackContext::TraceFailure(v53, "CByteStreamCacheReaderEx::BeginRead", 300, v26);
    }
    if ( !g_wppLevels )
      goto LABEL_96;
    v58 = 23;
LABEL_95:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v58, &WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v26);
LABEL_96:
    ComSmartPtr<CBaseStreamSink>::operator=((char *)this + 16);
  }
LABEL_20:
  LeaveCriticalSection(v14);
  v31 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v32 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v33 = GetLastError();
    v34 = (GUID *)TlsGetValue(*((_DWORD *)v31 + 3));
    if ( v34 )
    {
      v32 = v34;
    }
    else if ( !GetLastError() )
    {
      v43 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v43 = CallStackTracing::s_wpInstance;
      }
      v44 = (**(__int64 (__fastcall ***)(CallStackTracing *))v43)(v43);
      if ( v44 )
        v32 = (GUID *)v44;
    }
    SetLastError(v33);
    v35 = *(_DWORD *)&v32[124].Data2;
    if ( v35 )
    {
      v36 = v35 - 1;
      *(_DWORD *)&v32[124].Data2 = v36;
      if ( !v36 )
      {
        *(_DWORD *)&v32[124].Data2 = 0;
        *(_QWORD *)&v32[126].Data1 = 0;
        *(_DWORD *)&v32[124].Data4[4] = 0;
        v32[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v32[126].Data4 = 0;
        v32[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18002e708  mov     [rsp+arg_8], rbx
0x18002e70d  mov     [rsp+arg_18], r9
0x18002e712  push    rbp
0x18002e713  push    rsi
0x18002e714  push    rdi
0x18002e715  push    r12
0x18002e717  push    r13
0x18002e719  push    r14
0x18002e71b  push    r15
0x18002e71d  sub     rsp, 30h
0x18002e721  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e728  xor     r13d, r13d
0x18002e72b  mov     r14, r8
0x18002e72e  mov     r12d, edx
0x18002e731  mov     rbx, rcx
0x18002e734  test    rdi, rdi
0x18002e737  jz      loc_18002E99A
0x18002e73d  lea     rcx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x18002e744  mov     ebp, 1
0x18002e749  cmp     [rdi+8], r13b
0x18002e74d  jz      short loc_18002E7A7
0x18002e74f  lea     rsi, [rdi+0D0h]
0x18002e756  call    cs:__imp_GetLastError
0x18002e75c  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002e75f  mov     r15d, eax
0x18002e762  call    cs:__imp_TlsGetValue
0x18002e768  test    rax, rax
0x18002e76b  jz      loc_18002EA14
0x18002e771  mov     rsi, rax
0x18002e774  mov     ecx, r15d; dwErrCode
0x18002e777  call    cs:__imp_SetLastError
0x18002e77d  mov     eax, [rsi+7C4h]
0x18002e783  lea     rcx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x18002e78a  cmp     eax, [rsi+7C8h]
0x18002e790  jnb     short loc_18002E7A1
0x18002e792  add     rax, rax
0x18002e795  mov     [rsi+rax*8], rcx
0x18002e799  mov     dword ptr [rsi+rax*8+8], 0E9h
0x18002e7a1  add     [rsi+7C4h], ebp
0x18002e7a7  lea     r15, [rbx+238h]
0x18002e7ae  mov     rcx, r15; lpCriticalSection
0x18002e7b1  call    cs:__imp_EnterCriticalSection
0x18002e7b7  mov     ecx, 68h ; 'h'; Size
0x18002e7bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e7c1  mov     rdi, rax
0x18002e7c4  test    rax, rax
0x18002e7c7  jz      loc_18002E9C6
0x18002e7cd  mov     rcx, rax; this
0x18002e7d0  call    ??0tagMFASYNCRESULT@@QEAA@XZ; tagMFASYNCRESULT::tagMFASYNCRESULT(void)
0x18002e7d5  lea     rax, ??_7CMFRefCounted@@6B@; const CMFRefCounted::`vftable'
0x18002e7dc  mov     [rcx+40h], rax
0x18002e7e0  lea     rax, ??_7CMP3ByteStreamPluginResult@@6BtagMFASYNCRESULT@@@; const CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'}
0x18002e7e7  mov     [rcx+48h], r13d
0x18002e7eb  mov     [rcx], rax
0x18002e7ee  lea     rax, ??_7CAsyncResult@@6BCMFRefCounted@@@; const CAsyncResult::`vftable'{for `CMFRefCounted'}
0x18002e7f5  mov     [rcx+40h], rax
0x18002e7f9  mov     [rcx+60h], r13d
0x18002e7fd  call    cs:__imp_MFLockPlatform
0x18002e803  mov     [rdi+64h], r13d
0x18002e807  mov     [rdi+30h], r13d
0x18002e80b  mov     [rdi+38h], r13
0x18002e80f  mov     [rdi+50h], r13
0x18002e813  mov     [rdi+58h], r13
0x18002e817  mov     [rdi+28h], r14
0x18002e81b  test    r14, r14
0x18002e81e  jz      short loc_18002E82F
0x18002e820  mov     rax, [r14]
0x18002e823  mov     rcx, r14
0x18002e826  mov     rax, [rax+8]
0x18002e82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e82f  xorps   xmm0, xmm0
0x18002e832  mov     rcx, rdi
0x18002e835  movups  xmmword ptr [rdi+8], xmm0
0x18002e839  movups  xmmword ptr [rdi+18h], xmm0
0x18002e83d  mov     [rdi+34h], r13d
0x18002e841  mov     rax, [rdi]
0x18002e844  mov     rax, [rax+8]
0x18002e848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e84d  mov     r8, [rbx+200h]
0x18002e854  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002e858  mov     [rbx+10h], rdi
0x18002e85c  cmp     r8, r14
0x18002e85f  jnz     loc_18002EC23
0x18002e865  mov     [rbx+18h], r12d
0x18002e869  mov     rcx, [rbx+20h]
0x18002e86d  test    rcx, rcx
0x18002e870  jnz     loc_18002ECC9
0x18002e876  mov     rcx, rbx; this
0x18002e879  call    ?ReturnResult@CByteStreamCacheReaderEx@@IEAAJXZ; CByteStreamCacheReaderEx::ReturnResult(void)
0x18002e87e  mov     edi, eax
0x18002e880  test    eax, eax
0x18002e882  js      loc_18002EACE
0x18002e888  cmp     [rbx+20h], r13
0x18002e88c  jz      loc_18002ED1F
0x18002e892  mov     rbx, [rbx+10h]
0x18002e896  mov     rcx, [rbx+28h]
0x18002e89a  mov     [rbx+30h], r13d
0x18002e89e  test    rcx, rcx
0x18002e8a1  jz      loc_18002EA07
0x18002e8a7  mov     [rsp+68h+arg_0], r13d
0x18002e8ac  lea     r8, [rsp+68h+arg_18]
0x18002e8b4  mov     dword ptr [rsp+68h+arg_18], r13d
0x18002e8bc  lea     rdx, [rsp+68h+arg_0]
0x18002e8c1  mov     rax, [rcx]
0x18002e8c4  mov     rax, [rax+18h]
0x18002e8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8cd  test    eax, eax
0x18002e8cf  jns     loc_18002E98E
0x18002e8d5  mov     dword ptr [rsp+68h+arg_18], ebp
0x18002e8dc  mov     r8, rbx; pResult
0x18002e8df  xor     edx, edx; Priority
0x18002e8e1  mov     ecx, ebp; dwQueue
0x18002e8e3  call    cs:__imp_MFPutWorkItemEx2
0x18002e8e9  mov     rcx, r15; lpCriticalSection
0x18002e8ec  call    cs:__imp_LeaveCriticalSection
0x18002e8f2  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e8f9  cmp     [rsi+8], r13b
0x18002e8fd  jz      short loc_18002E977
0x18002e8ff  lea     rbx, [rsi+0D0h]
0x18002e906  call    cs:__imp_GetLastError
0x18002e90c  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18002e90f  mov     ebp, eax
0x18002e911  call    cs:__imp_TlsGetValue
0x18002e917  test    rax, rax
0x18002e91a  jz      loc_18002EA45
0x18002e920  mov     rbx, rax
0x18002e923  mov     ecx, ebp; dwErrCode
0x18002e925  call    cs:__imp_SetLastError
0x18002e92b  mov     eax, [rbx+7C4h]
0x18002e931  test    eax, eax
0x18002e933  jz      short loc_18002E977
0x18002e935  sub     eax, 1
0x18002e938  mov     [rbx+7C4h], eax
0x18002e93e  jnz     short loc_18002E977
0x18002e940  mov     [rbx+7C4h], r13d
0x18002e947  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002e94e  mov     [rbx+7E0h], r13
0x18002e955  mov     [rbx+7CCh], r13d
0x18002e95c  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x18002e964  mov     [rbx+7E8h], r13d
0x18002e96b  call    cs:__imp_GetCurrentThreadId
0x18002e971  mov     [rbx+7C0h], eax
0x18002e977  mov     rbx, [rsp+68h+arg_8]
0x18002e97c  mov     eax, edi
0x18002e97e  add     rsp, 30h
0x18002e982  pop     r15
0x18002e984  pop     r14
0x18002e986  pop     r13
0x18002e988  pop     r12
0x18002e98a  pop     rdi
0x18002e98b  pop     rsi
0x18002e98c  pop     rbp
0x18002e98d  retn
0x18002e98e  mov     ebp, dword ptr [rsp+68h+arg_18]
0x18002e995  jmp     loc_18002E8DC
0x18002e99a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e9a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e9a7  mov     rcx, rax
0x18002e9aa  test    rax, rax
0x18002e9ad  jnz     loc_18002EBFE
0x18002e9b3  lea     rdi, qword_1801B07E0
0x18002e9ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e9c1  jmp     loc_18002E73D
0x18002e9c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e9cd  mov     edi, 8007000Eh
0x18002e9d2  test    rcx, rcx
0x18002e9d5  jnz     loc_18002EDD5
0x18002e9db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e9e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e9e8  mov     rcx, rax
0x18002e9eb  test    rax, rax
0x18002e9ee  jnz     loc_18002EDB5
0x18002e9f4  lea     rcx, qword_1801B07E0
0x18002e9fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea02  jmp     loc_18002EDD5
0x18002ea07  mov     rcx, rbx; struct tagMFASYNCRESULT *
0x18002ea0a  call    ?SignalEvent@CAsyncResult@@SAXPEAUtagMFASYNCRESULT@@@Z; CAsyncResult::SignalEvent(tagMFASYNCRESULT *)
0x18002ea0f  jmp     loc_18002E8E9
0x18002ea14  call    cs:__imp_GetLastError
0x18002ea1a  test    eax, eax
0x18002ea1c  jnz     loc_18002E774
0x18002ea22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea29  test    rcx, rcx
0x18002ea2c  jz      short loc_18002EA76
0x18002ea2e  mov     rax, [rcx]
0x18002ea31  mov     rax, [rax]
0x18002ea34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea39  test    rax, rax
0x18002ea3c  cmovnz  rsi, rax
0x18002ea40  jmp     loc_18002E774
0x18002ea45  call    cs:__imp_GetLastError
0x18002ea4b  test    eax, eax
0x18002ea4d  jnz     loc_18002E923
0x18002ea53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea5a  test    rcx, rcx
0x18002ea5d  jz      short loc_18002EA84
0x18002ea5f  mov     rax, [rcx]
0x18002ea62  mov     rax, [rax]
0x18002ea65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea6a  test    rax, rax
0x18002ea6d  cmovnz  rbx, rax
0x18002ea71  jmp     loc_18002E923
0x18002ea76  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002ea7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea82  jmp     short loc_18002EA2E
0x18002ea84  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002ea89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea90  jmp     short loc_18002EA5F
0x18002ea92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea99  test    rcx, rcx
0x18002ea9c  jnz     loc_18002ECA8
0x18002eaa2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002eaa8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eaaf  mov     rcx, rax
0x18002eab2  test    rax, rax
0x18002eab5  jnz     loc_18002EC88
0x18002eabb  lea     rcx, qword_1801B07E0
0x18002eac2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eac9  jmp     loc_18002ECA8
0x18002eace  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ead5  test    rcx, rcx
0x18002ead8  jnz     loc_18002ECFE
0x18002eade  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002eae4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eaeb  mov     rcx, rax
0x18002eaee  test    rax, rax
0x18002eaf1  jnz     loc_18002ECDE
0x18002eaf7  lea     rcx, qword_1801B07E0
0x18002eafe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb05  jmp     loc_18002ECFE
0x18002eb0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb11  test    rcx, rcx
0x18002eb14  jnz     loc_18002ED9B
0x18002eb1a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002eb20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb27  mov     rcx, rax
0x18002eb2a  test    rax, rax
0x18002eb2d  jnz     loc_18002ED7B
0x18002eb33  lea     rcx, qword_1801B07E0
0x18002eb3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb41  jmp     loc_18002ED9B
0x18002eb46  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002eb4b  cmp     [rax+7CCh], edi
0x18002eb51  jz      loc_18002ECB2
0x18002eb57  mov     r9d, edi; int
0x18002eb5a  lea     rdx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x18002eb61  mov     r8d, 112h; int
0x18002eb67  mov     rcx, rax; this
0x18002eb6a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002eb6f  jmp     loc_18002ECB2
0x18002eb74  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002eb79  cmp     [rax+7CCh], edi
0x18002eb7f  jz      loc_18002ED08
0x18002eb85  mov     r9d, edi; int
0x18002eb88  lea     rdx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x18002eb8f  mov     r8d, 11Fh; int
0x18002eb95  mov     rcx, rax; this
0x18002eb98  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002eb9d  jmp     loc_18002ED08
0x18002eba2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002eba7  cmp     [rax+7CCh], edi
0x18002ebad  jz      loc_18002EDA5
0x18002ebb3  mov     r9d, edi; int
0x18002ebb6  lea     rdx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x18002ebbd  mov     r8d, 12Ch; int
0x18002ebc3  mov     rcx, rax; this
0x18002ebc6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002ebcb  jmp     loc_18002EDA5
0x18002ebd0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002ebd5  cmp     [rax+7CCh], edi
0x18002ebdb  jz      loc_18002EDDF
0x18002ebe1  mov     r9d, edi; int
0x18002ebe4  lea     rdx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x18002ebeb  mov     r8d, 0FEh; int
0x18002ebf1  mov     rcx, rax; this
0x18002ebf4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002ebf9  jmp     loc_18002EDDF
0x18002ebfe  mov     rax, [rax]
0x18002ec01  mov     edx, 7F0h
0x18002ec06  mov     rax, [rax+8]
0x18002ec0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec0f  test    eax, eax
0x18002ec11  jz      loc_18002E9B3
0x18002ec17  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ec1e  jmp     loc_18002E73D
0x18002ec23  mov     rax, [rbx+208h]
0x18002ec2a  xor     edx, edx
0x18002ec2c  mov     ecx, [rax+40h]
0x18002ec2f  mov     rax, r8
0x18002ec32  div     rcx
0x18002ec35  mov     rsi, rax
0x18002ec38  cmp     rax, [rbx+28h]
0x18002ec3c  jz      short loc_18002EC6E
0x18002ec3e  mov     rdx, r14
0x18002ec41  mov     rcx, rbx; this
0x18002ec44  cmova   rdx, r8; unsigned __int64
0x18002ec48  call    ?FlushBuffers@CByteStreamCacheReaderEx@@IEAAX_K@Z; CByteStreamCacheReaderEx::FlushBuffers(unsigned __int64)
0x18002ec4d  mov     rcx, [rbx+208h]; this
0x18002ec54  mov     edx, [rcx+40h]
0x18002ec57  imul    rdx, rsi; unsigned __int64
  ... truncated ...
```
