# CByteStreamCacheReaderEx::BeginRead(ulong,IMFAsyncCallback *,IUnknown *)

- ea: `0x1800177b4`
- end: `0x180017f36`
- name: `?BeginRead@CByteStreamCacheReaderEx@@QEAAJKPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `1922`
- prototype: `__int64 __fastcall(CByteStreamCacheReaderEx *__hidden this, unsigned int, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `7`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015630`
- `0x180017630`
- `0x18007395c`
- `0x180089f28`
- `0x1800d9670`
- `0x1800fd590`
- `0x1800fd69c`

## callees

- `0x180005cf4`
- `0x1800177b4`
- `0x180017f40`
- `0x180018a3c`
- `0x18001c6c0`
- `0x18004f030`
- `0x180051afc`
- `0x180074194`
- `0x180077708`
- `0x180079680`
- `0x1800f0e3c`
- `0x180110a94`
- `0x1801488b0`
- `0x1801726dc`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001782f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017a0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001782f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017a0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800179bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800179bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001786f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001786f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017a57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017a57`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017814`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800179f1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017814`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800179f1`
- `MFPlat!MFPutWorkItemEx2` at `0x1800179ad`
- `MFPlat!MFPutWorkItemEx2` at `0x1800179ad`
- `MFPlat!MFLockPlatform` at `0x1800178c1`
- `MFPlat!MFLockPlatform` at `0x1800178c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017a8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017ad4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017bad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017bef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017c31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017a8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017ad4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017bad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017bef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180017c31`

## string_xrefs

- `0x1800177e9`: `CByteStreamCacheReaderEx::BeginRead`
- `0x180017841`: `CByteStreamCacheReaderEx::BeginRead`
- `0x180017c77`: `CByteStreamCacheReaderEx::BeginRead`
- `0x180017ca5`: `CByteStreamCacheReaderEx::BeginRead`
- `0x180017cd3`: `CByteStreamCacheReaderEx::BeginRead`
- `0x180017d01`: `CByteStreamCacheReaderEx::BeginRead`

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
      v4 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v34 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v40 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v42 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
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
        v44 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800177b4  mov     [rsp+arg_8], rbx
0x1800177b9  mov     [rsp+arg_18], r9
0x1800177be  push    rbp
0x1800177bf  push    rsi
0x1800177c0  push    rdi
0x1800177c1  push    r12
0x1800177c3  push    r13
0x1800177c5  push    r14
0x1800177c7  push    r15
0x1800177c9  sub     rsp, 30h
0x1800177cd  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800177d4  xor     r13d, r13d
0x1800177d7  mov     r14, r8
0x1800177da  mov     r12d, edx
0x1800177dd  mov     rbx, rcx
0x1800177e0  test    rdi, rdi
0x1800177e3  jz      loc_180017A8D
0x1800177e9  lea     rcx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x1800177f0  mov     ebp, 1
0x1800177f5  cmp     [rdi+8], r13b
0x1800177f9  jz      short loc_180017865
0x1800177fb  lea     rsi, [rdi+0D0h]
0x180017802  call    cs:__imp_GetLastError
0x180017809  nop     dword ptr [rax+rax+00h]
0x18001780e  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180017811  mov     r15d, eax
0x180017814  call    cs:__imp_TlsGetValue
0x18001781b  nop     dword ptr [rax+rax+00h]
0x180017820  test    rax, rax
0x180017823  jz      loc_180017B13
0x180017829  mov     rsi, rax
0x18001782c  mov     ecx, r15d; dwErrCode
0x18001782f  call    cs:__imp_SetLastError
0x180017836  nop     dword ptr [rax+rax+00h]
0x18001783b  mov     eax, [rsi+7C4h]
0x180017841  lea     rcx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x180017848  cmp     eax, [rsi+7C8h]
0x18001784e  jnb     short loc_18001785F
0x180017850  add     rax, rax
0x180017853  mov     [rsi+rax*8], rcx
0x180017857  mov     dword ptr [rsi+rax*8+8], 0E9h
0x18001785f  add     [rsi+7C4h], ebp
0x180017865  lea     r15, [rbx+238h]
0x18001786c  mov     rcx, r15; lpCriticalSection
0x18001786f  call    cs:__imp_EnterCriticalSection
0x180017876  nop     dword ptr [rax+rax+00h]
0x18001787b  mov     ecx, 68h ; 'h'; Size
0x180017880  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017885  mov     rdi, rax
0x180017888  test    rax, rax
0x18001788b  jz      loc_180017ABF
0x180017891  mov     rcx, rax; this
0x180017894  call    ??0tagMFASYNCRESULT@@QEAA@XZ; tagMFASYNCRESULT::tagMFASYNCRESULT(void)
0x180017899  lea     rax, ??_7CMFRefCounted@@6B@; const CMFRefCounted::`vftable'
0x1800178a0  mov     [rcx+40h], rax
0x1800178a4  lea     rax, ??_7CMP3ByteStreamPluginResult@@6BtagMFASYNCRESULT@@@; const CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'}
0x1800178ab  mov     [rcx+48h], r13d
0x1800178af  mov     [rcx], rax
0x1800178b2  lea     rax, ??_7CAsyncResult@@6BCMFRefCounted@@@; const CAsyncResult::`vftable'{for `CMFRefCounted'}
0x1800178b9  mov     [rcx+40h], rax
0x1800178bd  mov     [rcx+60h], r13d
0x1800178c1  call    cs:__imp_MFLockPlatform
0x1800178c8  nop     dword ptr [rax+rax+00h]
0x1800178cd  mov     [rdi+64h], r13d
0x1800178d1  mov     [rdi+30h], r13d
0x1800178d5  mov     [rdi+38h], r13
0x1800178d9  mov     [rdi+50h], r13
0x1800178dd  mov     [rdi+58h], r13
0x1800178e1  mov     [rdi+28h], r14
0x1800178e5  test    r14, r14
0x1800178e8  jz      short loc_1800178F9
0x1800178ea  mov     rax, [r14]
0x1800178ed  mov     rcx, r14
0x1800178f0  mov     rax, [rax+8]
0x1800178f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178f9  xorps   xmm0, xmm0
0x1800178fc  mov     rcx, rdi
0x1800178ff  movups  xmmword ptr [rdi+8], xmm0
0x180017903  movups  xmmword ptr [rdi+18h], xmm0
0x180017907  mov     [rdi+34h], r13d
0x18001790b  mov     rax, [rdi]
0x18001790e  mov     rax, [rax+8]
0x180017912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017917  mov     r8, [rbx+200h]
0x18001791e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180017922  mov     [rbx+10h], rdi
0x180017926  cmp     r8, r14
0x180017929  jnz     loc_180017D40
0x18001792f  mov     [rbx+18h], r12d
0x180017933  mov     rcx, [rbx+20h]
0x180017937  test    rcx, rcx
0x18001793a  jnz     loc_180017DE6
0x180017940  mov     rcx, rbx; this
0x180017943  call    ?ReturnResult@CByteStreamCacheReaderEx@@IEAAJXZ; CByteStreamCacheReaderEx::ReturnResult(void)
0x180017948  mov     edi, eax
0x18001794a  test    eax, eax
0x18001794c  js      loc_180017BDF
0x180017952  cmp     [rbx+20h], r13
0x180017956  jz      loc_180017E3C
0x18001795c  mov     rbx, [rbx+10h]
0x180017960  mov     rcx, [rbx+28h]
0x180017964  mov     [rbx+30h], r13d
0x180017968  test    rcx, rcx
0x18001796b  jz      loc_180017B06
0x180017971  mov     [rsp+68h+arg_0], r13d
0x180017976  lea     r8, [rsp+68h+arg_18]
0x18001797e  mov     dword ptr [rsp+68h+arg_18], r13d
0x180017986  lea     rdx, [rsp+68h+arg_0]
0x18001798b  mov     rax, [rcx]
0x18001798e  mov     rax, [rax+18h]
0x180017992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017997  test    eax, eax
0x180017999  jns     loc_180017A81
0x18001799f  mov     dword ptr [rsp+68h+arg_18], ebp
0x1800179a6  mov     r8, rbx; pResult
0x1800179a9  xor     edx, edx; Priority
0x1800179ab  mov     ecx, ebp; dwQueue
0x1800179ad  call    cs:__imp_MFPutWorkItemEx2
0x1800179b4  nop     dword ptr [rax+rax+00h]
0x1800179b9  mov     rcx, r15; lpCriticalSection
0x1800179bc  call    cs:__imp_LeaveCriticalSection
0x1800179c3  nop     dword ptr [rax+rax+00h]
0x1800179c8  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800179cf  cmp     [rsi+8], r13b
0x1800179d3  jz      loc_180017A69
0x1800179d9  lea     rbx, [rsi+0D0h]
0x1800179e0  call    cs:__imp_GetLastError
0x1800179e7  nop     dword ptr [rax+rax+00h]
0x1800179ec  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x1800179ef  mov     ebp, eax
0x1800179f1  call    cs:__imp_TlsGetValue
0x1800179f8  nop     dword ptr [rax+rax+00h]
0x1800179fd  test    rax, rax
0x180017a00  jz      loc_180017B4A
0x180017a06  mov     rbx, rax
0x180017a09  mov     ecx, ebp; dwErrCode
0x180017a0b  call    cs:__imp_SetLastError
0x180017a12  nop     dword ptr [rax+rax+00h]
0x180017a17  mov     eax, [rbx+7C4h]
0x180017a1d  test    eax, eax
0x180017a1f  jz      short loc_180017A69
0x180017a21  sub     eax, 1
0x180017a24  mov     [rbx+7C4h], eax
0x180017a2a  jnz     short loc_180017A69
0x180017a2c  mov     [rbx+7C4h], r13d
0x180017a33  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180017a3a  mov     [rbx+7E0h], r13
0x180017a41  mov     [rbx+7CCh], r13d
0x180017a48  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x180017a50  mov     [rbx+7E8h], r13d
0x180017a57  call    cs:__imp_GetCurrentThreadId
0x180017a5e  nop     dword ptr [rax+rax+00h]
0x180017a63  mov     [rbx+7C0h], eax
0x180017a69  mov     rbx, [rsp+68h+arg_8]
0x180017a6e  mov     eax, edi
0x180017a70  add     rsp, 30h
0x180017a74  pop     r15
0x180017a76  pop     r14
0x180017a78  pop     r13
0x180017a7a  pop     r12
0x180017a7c  pop     rdi
0x180017a7d  pop     rsi
0x180017a7e  pop     rbp
0x180017a7f  retn
0x180017a81  mov     ebp, dword ptr [rsp+68h+arg_18]
0x180017a88  jmp     loc_1800179A6
0x180017a8d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017a94  nop     dword ptr [rax+rax+00h]
0x180017a99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017aa0  mov     rcx, rax
0x180017aa3  test    rax, rax
0x180017aa6  jnz     loc_180017D1B
0x180017aac  lea     rdi, qword_1801B97E0
0x180017ab3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180017aba  jmp     loc_1800177E9
0x180017abf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017ac6  mov     edi, 8007000Eh
0x180017acb  test    rcx, rcx
0x180017ace  jnz     loc_180017EF2
0x180017ad4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017adb  nop     dword ptr [rax+rax+00h]
0x180017ae0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017ae7  mov     rcx, rax
0x180017aea  test    rax, rax
0x180017aed  jnz     loc_180017ED2
0x180017af3  lea     rcx, qword_1801B97E0
0x180017afa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017b01  jmp     loc_180017EF2
0x180017b06  mov     rcx, rbx; struct tagMFASYNCRESULT *
0x180017b09  call    ?SignalEvent@CAsyncResult@@SAXPEAUtagMFASYNCRESULT@@@Z; CAsyncResult::SignalEvent(tagMFASYNCRESULT *)
0x180017b0e  jmp     loc_1800179B9
0x180017b13  call    cs:__imp_GetLastError
0x180017b1a  nop     dword ptr [rax+rax+00h]
0x180017b1f  test    eax, eax
0x180017b21  jnz     loc_18001782C
0x180017b27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017b2e  test    rcx, rcx
0x180017b31  jz      short loc_180017B81
0x180017b33  mov     rax, [rcx]
0x180017b36  mov     rax, [rax]
0x180017b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b3e  test    rax, rax
0x180017b41  cmovnz  rsi, rax
0x180017b45  jmp     loc_18001782C
0x180017b4a  call    cs:__imp_GetLastError
0x180017b51  nop     dword ptr [rax+rax+00h]
0x180017b56  test    eax, eax
0x180017b58  jnz     loc_180017A09
0x180017b5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017b65  test    rcx, rcx
0x180017b68  jz      short loc_180017B8F
0x180017b6a  mov     rax, [rcx]
0x180017b6d  mov     rax, [rax]
0x180017b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b75  test    rax, rax
0x180017b78  cmovnz  rbx, rax
0x180017b7c  jmp     loc_180017A09
0x180017b81  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180017b86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017b8d  jmp     short loc_180017B33
0x180017b8f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180017b94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017b9b  jmp     short loc_180017B6A
0x180017b9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017ba4  test    rcx, rcx
0x180017ba7  jnz     loc_180017DC5
0x180017bad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017bb4  nop     dword ptr [rax+rax+00h]
0x180017bb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017bc0  mov     rcx, rax
0x180017bc3  test    rax, rax
0x180017bc6  jnz     loc_180017DA5
0x180017bcc  lea     rcx, qword_1801B97E0
0x180017bd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017bda  jmp     loc_180017DC5
0x180017bdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017be6  test    rcx, rcx
0x180017be9  jnz     loc_180017E1B
0x180017bef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017bf6  nop     dword ptr [rax+rax+00h]
0x180017bfb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c02  mov     rcx, rax
0x180017c05  test    rax, rax
0x180017c08  jnz     loc_180017DFB
0x180017c0e  lea     rcx, qword_1801B97E0
0x180017c15  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c1c  jmp     loc_180017E1B
0x180017c21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c28  test    rcx, rcx
0x180017c2b  jnz     loc_180017EB8
0x180017c31  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180017c38  nop     dword ptr [rax+rax+00h]
0x180017c3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c44  mov     rcx, rax
0x180017c47  test    rax, rax
0x180017c4a  jnz     loc_180017E98
0x180017c50  lea     rcx, qword_1801B97E0
0x180017c57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180017c5e  jmp     loc_180017EB8
0x180017c63  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017c68  cmp     [rax+7CCh], edi
0x180017c6e  jz      loc_180017DCF
0x180017c74  mov     r9d, edi; int
0x180017c77  lea     rdx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x180017c7e  mov     r8d, 112h; int
0x180017c84  mov     rcx, rax; this
0x180017c87  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017c8c  jmp     loc_180017DCF
0x180017c91  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017c96  cmp     [rax+7CCh], edi
0x180017c9c  jz      loc_180017E25
0x180017ca2  mov     r9d, edi; int
0x180017ca5  lea     rdx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x180017cac  mov     r8d, 11Fh; int
0x180017cb2  mov     rcx, rax; this
0x180017cb5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017cba  jmp     loc_180017E25
0x180017cbf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017cc4  cmp     [rax+7CCh], edi
0x180017cca  jz      loc_180017EC2
0x180017cd0  mov     r9d, edi; int
0x180017cd3  lea     rdx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x180017cda  mov     r8d, 12Ch; int
0x180017ce0  mov     rcx, rax; this
0x180017ce3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017ce8  jmp     loc_180017EC2
0x180017ced  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180017cf2  cmp     [rax+7CCh], edi
0x180017cf8  jz      loc_180017EFC
0x180017cfe  mov     r9d, edi; int
0x180017d01  lea     rdx, aCbytestreamcac_34; "CByteStreamCacheReaderEx::BeginRead"
0x180017d08  mov     r8d, 0FEh; int
0x180017d0e  mov     rcx, rax; this
0x180017d11  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180017d16  jmp     loc_180017EFC
0x180017d1b  mov     rax, [rax]
0x180017d1e  mov     edx, 7F0h
0x180017d23  mov     rax, [rax+8]
0x180017d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d2c  test    eax, eax
  ... truncated ...
```
