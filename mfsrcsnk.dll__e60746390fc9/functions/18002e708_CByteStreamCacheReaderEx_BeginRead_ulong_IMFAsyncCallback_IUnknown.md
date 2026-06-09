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
  tagMFASYNCRESULT *v17; // rdi
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rdx
  int v23; // edi
  struct tagMFASYNCRESULT *v24; // rbx
  IMFAsyncCallback *pCallback; // rcx
  CallStackTracing *v26; // rsi
  GUID *v27; // rbx
  DWORD v28; // ebp
  GUID *v29; // rax
  int v30; // eax
  int v31; // eax
  CallStackTracing *v33; // rax
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  CallStackTracing *v36; // rcx
  __int64 v37; // rax
  CallStackTracing *v38; // rcx
  __int64 v39; // rax
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  struct CallStackContext *v47; // rax
  struct CallStackContext *v48; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rsi
  unsigned __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  int v55; // [rsp+70h] [rbp+8h] BYREF
  struct IUnknown *v56; // [rsp+88h] [rbp+20h] BYREF

  v56 = a4;
  v4 = (wchar_t *)CallStackTracing::s_wpInstance;
  v6 = a2;
  if ( !CallStackTracing::s_wpInstance )
  {
    v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v33;
    if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
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
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v36 = CallStackTracing::s_wpInstance;
      }
      v37 = (**(__int64 (__fastcall ***)(CallStackTracing *))v36)(v36);
      if ( v37 )
        v9 = (wchar_t *)v37;
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
  v17 = v15;
  if ( !v15 )
  {
    v34 = (wchar_t *)CallStackTracing::s_wpInstance;
    v23 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CByteStreamCacheReaderEx::BeginRead", 254, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_96;
    v53 = 19;
    goto LABEL_95;
  }
  tagMFASYNCRESULT::tagMFASYNCRESULT(v15);
  *(_QWORD *)(v18 + 64) = &CMFRefCounted::`vftable';
  *(_DWORD *)(v18 + 72) = 0;
  *(_QWORD *)v18 = &CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'};
  *(_QWORD *)(v18 + 64) = &CAsyncResult::`vftable'{for `CMFRefCounted'};
  *(_DWORD *)(v18 + 96) = 0;
  MFLockPlatform();
  HIDWORD(v17[1].overlapped.hEvent) = 0;
  v17->hrStatusResult = 0;
  v17->hEvent = 0;
  v17[1].overlapped.InternalHigh = 0;
  v17[1].overlapped.Pointer = 0;
  v17->pCallback = a3;
  if ( a3 )
    ((void (__fastcall *)(struct IMFAsyncCallback *))a3->lpVtbl->AddRef)(a3);
  *(_OWORD *)&v17->overlapped.Internal = 0;
  *(_OWORD *)&v17->overlapped.Offset = 0;
  v17->dwBytesTransferred = 0;
  ((void (__fastcall *)(tagMFASYNCRESULT *))v17->AsyncResult.lpVtbl->AddRef)(v17);
  v20 = *((_QWORD *)this + 64);
  *((_QWORD *)this + 2) = v17;
  if ( v20 != -1 )
  {
    v50 = v20 / *(unsigned int *)(*((_QWORD *)this + 65) + 64LL);
    v19 = v20 % *(unsigned int *)(*((_QWORD *)this + 65) + 64LL);
    v51 = v50;
    if ( v50 != *((_QWORD *)this + 5) )
    {
      v52 = -1;
      if ( v50 > *((_QWORD *)this + 5) )
        v52 = v20;
      CByteStreamCacheReaderEx::FlushBuffers(this, v52);
      v23 = CByteStreamCacheReader2::SetCurrentPosition(
              *((CByteStreamCacheReader2 **)this + 65),
              v51 * *(unsigned int *)(*((_QWORD *)this + 65) + 64LL));
      if ( v23 < 0 )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v46 + 499) != v23 )
            CallStackContext::TraceFailure(v46, "CByteStreamCacheReaderEx::BeginRead", 274, v23);
        }
        if ( !g_wppLevels )
          goto LABEL_96;
        v53 = 20;
        goto LABEL_95;
      }
      *((_QWORD *)this + 5) = v51;
    }
    *((_QWORD *)this + 63) = *((_QWORD *)this + 64);
    *((_QWORD *)this + 64) = -1;
  }
  *((_DWORD *)this + 6) = v6;
  v21 = *((_QWORD *)this + 4);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    *((_QWORD *)this + 4) = 0;
  }
  v23 = CByteStreamCacheReaderEx::ReturnResult(this, v19);
  if ( v23 < 0 )
  {
    v42 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
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
      v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
      if ( *((_DWORD *)v47 + 499) != v23 )
        CallStackContext::TraceFailure(v47, "CByteStreamCacheReaderEx::BeginRead", 287, v23);
    }
    if ( !g_wppLevels )
      goto LABEL_96;
    v53 = 21;
    goto LABEL_95;
  }
  if ( *((_QWORD *)this + 4) )
  {
    v24 = (struct tagMFASYNCRESULT *)*((_QWORD *)this + 2);
    pCallback = v24->pCallback;
    v24->hrStatusResult = 0;
    if ( pCallback )
    {
      v55 = 0;
      LODWORD(v56) = 0;
      if ( ((int (__fastcall *)(IMFAsyncCallback *, int *, struct IUnknown **))pCallback->lpVtbl->GetParameters)(
             pCallback,
             &v55,
             &v56) >= 0 )
        v8 = (unsigned int)v56;
      else
        LODWORD(v56) = 1;
      MFPutWorkItemEx2(v8, 0, &v24->AsyncResult);
    }
    else
    {
      CAsyncResult::SignalEvent(v24);
    }
    goto LABEL_20;
  }
  if ( (unsigned __int8)byte_1801B110B >= 0x10u )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      22,
      WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids,
      this,
      *((_QWORD *)this + 63));
  v23 = CByteStreamCacheReader2::BeginCacheRead(
          *((CByteStreamCacheReader2 **)this + 65),
          (struct IMFAsyncCallback *)this + 66,
          0);
  if ( v23 < 0 )
  {
    v44 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
      CallStackTracing::s_wpInstance = v45;
      if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v44 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v44 + 8) )
    {
      v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
      if ( *((_DWORD *)v48 + 499) != v23 )
        CallStackContext::TraceFailure(v48, "CByteStreamCacheReaderEx::BeginRead", 300, v23);
    }
    if ( !g_wppLevels )
      goto LABEL_96;
    v53 = 23;
LABEL_95:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v53, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v23);
LABEL_96:
    ComSmartPtr<CBaseStreamSink>::operator=((char *)this + 16);
  }
LABEL_20:
  LeaveCriticalSection(v14);
  v26 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v27 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v28 = GetLastError();
    v29 = (GUID *)TlsGetValue(*((_DWORD *)v26 + 3));
    if ( v29 )
    {
      v27 = v29;
    }
    else if ( !GetLastError() )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v38 = CallStackTracing::s_wpInstance;
      }
      v39 = (**(__int64 (__fastcall ***)(CallStackTracing *))v38)(v38);
      if ( v39 )
        v27 = (GUID *)v39;
    }
    SetLastError(v28);
    v30 = *(_DWORD *)&v27[124].Data2;
    if ( v30 )
    {
      v31 = v30 - 1;
      *(_DWORD *)&v27[124].Data2 = v31;
      if ( !v31 )
      {
        *(_DWORD *)&v27[124].Data2 = 0;
        *(_QWORD *)&v27[126].Data1 = 0;
        *(_DWORD *)&v27[124].Data4[4] = 0;
        v27[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v27[126].Data4 = 0;
        v27[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v23;
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
