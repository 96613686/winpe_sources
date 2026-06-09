# CByteStreamCacheReaderEx::ReturnResult(void)

- ea: `0x180017f40`
- end: `0x18001886c`
- name: `?ReturnResult@CByteStreamCacheReaderEx@@IEAAJXZ`
- size: `2348`
- prototype: `__int64 __fastcall(CByteStreamCacheReaderEx *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800177b4`
- `0x18003a170`

## callees

- `0x180005cf4`
- `0x180017f40`
- `0x18001c6c0`
- `0x180077708`
- `0x180079680`
- `0x180110a94`
- `0x1801726dc`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017faf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018104`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018449`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017faf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018104`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001841e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001841e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800183fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800183fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017fe5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017fe5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018498`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018498`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017f94`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800180e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001842f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017f94`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800180e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001842f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001875b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001875b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018747`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018747`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018315`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001863a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018675`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018315`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001863a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018675`

## string_xrefs

- `0x180017f69`: `CByteStreamCacheReaderEx::ReturnResult`
- `0x1800186bb`: `CByteStreamCacheReaderEx::ReturnResult`
- `0x180018124`: `CCacheReaderBufferList::Initialize`

## pseudocode

```c
__int64 __fastcall CByteStreamCacheReaderEx::ReturnResult(CByteStreamCacheReaderEx *this, __int64 a2)
{
  wchar_t *v2; // rsi
  int v4; // ebp
  wchar_t *v5; // rbx
  DWORD LastError; // r14d
  wchar_t *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // r14
  __int64 v13; // rcx
  CallStackTracing *v14; // rbp
  unsigned __int64 v15; // rsi
  int v16; // r12d
  unsigned __int64 v17; // r13
  char *v18; // rsi
  DWORD v19; // r15d
  char *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rax
  unsigned __int64 v38; // rax
  __int64 *v39; // rsi
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // r15
  _QWORD *v42; // rax
  __int64 v43; // r13
  _QWORD *v44; // rcx
  __int64 v45; // rax
  CallStackTracing *v46; // rax
  wchar_t *v47; // rcx
  struct CallStackContext *ThreadRelativeContext; // rsi
  int v49; // eax
  int v50; // eax
  DWORD CurrentThreadId; // eax
  CallStackTracing *v52; // rbx
  GUID *v53; // rdi
  DWORD v54; // esi
  GUID *v55; // rax
  int v56; // eax
  int v57; // eax
  CallStackTracing *v59; // rcx
  __int64 v60; // rax
  CallStackTracing *v61; // rcx
  __int64 v62; // rax
  CallStackTracing *v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rcx
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  struct CallStackContext *v70; // rax
  SIZE_T v71; // rsi
  HANDLE ProcessHeap; // rax
  _QWORD *v73; // r9
  __int64 i; // r8
  __int64 v75; // rdx
  _QWORD *v76; // rdx
  __int64 v77; // rdx
  unsigned __int64 v78; // [rsp+60h] [rbp+8h]
  _QWORD *v79; // [rsp+60h] [rbp+8h]

  v2 = (wchar_t *)CallStackTracing::s_wpInstance;
  v4 = 0;
  if ( !CallStackTracing::s_wpInstance )
  {
    v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v46;
    if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
    {
      v2 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v2 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v5 = v2 + 104;
    LastError = GetLastError();
    Value = (wchar_t *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v59 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v59 = CallStackTracing::s_wpInstance;
      }
      v60 = (**(__int64 (__fastcall ***)(CallStackTracing *))v59)(v59);
      if ( v60 )
        v5 = (wchar_t *)v60;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[4 * v9] = "CByteStreamCacheReaderEx::ReturnResult";
      *(_DWORD *)&v5[4 * v9 + 4] = 365;
    }
    ++*((_DWORD *)v5 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  if ( *((_DWORD *)this + 122) )
  {
    if ( *((_DWORD *)this + 124)
       - *((_QWORD *)this + 63) % (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 65) + 64LL) < *((_DWORD *)this + 6) )
    {
      v4 = 1;
    }
    else
    {
      v10 = operator new(0x1D8u);
      v12 = v10;
      if ( v10 )
      {
        *v10 = &CCacheReaderBufferList::`vftable';
        v10[1] = 0;
        v10[2] = 0;
        *((_DWORD *)v10 + 6) = 0;
        *((_DWORD *)v10 + 112) = 0;
        v10[55] = 0;
        v10[54] = 0;
        v10[53] = 0;
        v10[57] = 0;
        v10[58] = 0;
        (*(void (__fastcall **)(_QWORD *))(*v10 + 8LL))(v10);
        v13 = *((_QWORD *)this + 4);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        v14 = CallStackTracing::s_wpInstance;
        *((_QWORD *)this + 4) = v12;
        v15 = *((_QWORD *)this + 63);
        v16 = *((_DWORD *)this + 6);
        v78 = v15;
        v17 = *(unsigned int *)(*((_QWORD *)this + 65) + 64LL);
        if ( !v14 )
        {
          CallStackTracing::InitInstance();
          v14 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v18 = (char *)v14 + 208;
          v19 = GetLastError();
          v20 = (char *)TlsGetValue(*((_DWORD *)v14 + 3));
          if ( v20 )
          {
            v18 = v20;
          }
          else if ( !GetLastError() )
          {
            v63 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v63 = CallStackTracing::s_wpInstance;
            }
            v64 = (**(__int64 (__fastcall ***)(CallStackTracing *))v63)(v63);
            if ( v64 )
              v18 = (char *)v64;
          }
          SetLastError(v19);
          v21 = *((unsigned int *)v18 + 497);
          if ( (unsigned int)v21 < *((_DWORD *)v18 + 498) )
          {
            v22 = 2 * v21;
            *(_QWORD *)&v18[8 * v22] = "CCacheReaderBufferList::Initialize";
            *(_DWORD *)&v18[8 * v22 + 8] = 550;
          }
          ++*((_DWORD *)v18 + 497);
          v15 = v78;
        }
        v12[53] = 0;
        if ( !v12[2] )
        {
          *((_DWORD *)v12 + 6) = 1;
          v12[2] = v12 + 4;
          v12[4] = 0;
          v12[6] = v12[1];
          v12[1] = v12 + 5;
          v23 = v12[2];
          *(_QWORD *)(v23 + 40) = v12 + 5;
          v23 += 32;
          v12[1] = v23;
          v24 = v12[2];
          *(_QWORD *)(v24 + 64) = v23;
          v24 += 56;
          v12[1] = v24;
          v25 = v12[2];
          *(_QWORD *)(v25 + 88) = v24;
          v25 += 80;
          v12[1] = v25;
          v26 = v12[2];
          *(_QWORD *)(v26 + 112) = v25;
          v26 += 104;
          v12[1] = v26;
          v27 = v12[2] + 128LL;
          *(_QWORD *)(v27 + 8) = v26;
          v12[1] = v27;
          v28 = v12[2] + 152LL;
          *(_QWORD *)(v28 + 8) = v27;
          v12[1] = v28;
          v29 = v12[2] + 176LL;
          *(_QWORD *)(v29 + 8) = v28;
          v12[1] = v29;
          v30 = v12[2] + 200LL;
          *(_QWORD *)(v30 + 8) = v29;
          v12[1] = v30;
          v31 = v12[2] + 224LL;
          *(_QWORD *)(v31 + 8) = v30;
          v12[1] = v31;
          v32 = v12[2] + 248LL;
          *(_QWORD *)(v32 + 8) = v31;
          v12[1] = v32;
          v33 = v12[2] + 272LL;
          *(_QWORD *)(v33 + 8) = v32;
          v12[1] = v33;
          v34 = v12[2] + 296LL;
          *(_QWORD *)(v34 + 8) = v33;
          v12[1] = v34;
          v35 = v12[2] + 320LL;
          *(_QWORD *)(v35 + 8) = v34;
          v12[1] = v35;
          v36 = v12[2] + 344LL;
          *(_QWORD *)(v36 + 8) = v35;
          v12[1] = v36;
          v37 = v12[2] + 368LL;
          *(_QWORD *)(v37 + 8) = v36;
          v12[1] = v37;
        }
        v38 = v15;
        v39 = (__int64 *)*((_QWORD *)this + 59);
        v4 = 0;
        v40 = v38 % v17;
        v41 = v38 % v17;
        while ( v39 )
        {
          v42 = (_QWORD *)v39[1];
          v43 = *v39;
          v79 = v42;
          if ( !v12[1] )
          {
            v71 = 24LL * (unsigned int)(*((_DWORD *)v12 + 6) - 1) + 32;
            ProcessHeap = GetProcessHeap();
            v73 = HeapAlloc(ProcessHeap, 0, v71);
            if ( !v73 )
            {
              v4 = -2147024882;
              break;
            }
            for ( i = 0; (unsigned int)i < *((_DWORD *)v12 + 6); v12[1] = v76 )
            {
              v75 = (unsigned int)i + 1LL + 2 * i;
              i = (unsigned int)(i + 1);
              v76 = &v73[v75];
              v76[1] = v12[1];
            }
            *v73 = v12[2];
            v42 = v79;
            v12[2] = v73;
          }
          v44 = (_QWORD *)v12[1];
          v39 = v42;
          v12[1] = v44[1];
          *v44 = v43;
          v44[1] = 0;
          v44[2] = v12[55];
          v45 = v12[55];
          if ( v45 )
            *(_QWORD *)(v45 + 8) = v44;
          else
            v12[54] = v44;
          ++*((_DWORD *)v12 + 112);
          v12[55] = v44;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
        }
        *((_DWORD *)v12 + 114) = v41;
        *((_DWORD *)v12 + 116) = v16;
        v47 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
          v49 = *((_DWORD *)ThreadRelativeContext + 497);
          if ( !v49 || (v50 = v49 - 1, (*((_DWORD *)ThreadRelativeContext + 497) = v50) != 0) )
          {
            v47 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            *((_DWORD *)ThreadRelativeContext + 497) = 0;
            *((_QWORD *)ThreadRelativeContext + 252) = 0;
            *((_DWORD *)ThreadRelativeContext + 499) = 0;
            *((GUID *)ThreadRelativeContext + 125) = GUID_00000000_0000_0000_0000_000000000000;
            *((_DWORD *)ThreadRelativeContext + 506) = 0;
            CurrentThreadId = GetCurrentThreadId();
            v47 = (wchar_t *)CallStackTracing::s_wpInstance;
            *((_DWORD *)ThreadRelativeContext + 496) = CurrentThreadId;
          }
        }
        if ( v4 < 0 )
        {
          if ( !v47 )
          {
            v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
            CallStackTracing::s_wpInstance = v68;
            if ( v68 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
            {
              v47 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v47 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v47 + 8) )
          {
            v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
            if ( *((_DWORD *)v69 + 499) != v4 )
              CallStackContext::TraceFailure(v69, "CByteStreamCacheReaderEx::ReturnResult", 386, v4);
          }
          if ( g_wppLevels )
          {
            v77 = 30;
LABEL_97:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v77,
              WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids,
              this,
              v4);
          }
        }
      }
      else
      {
        v65 = *((_QWORD *)this + 4);
        if ( v65 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
          *((_QWORD *)this + 4) = 0;
        }
        v66 = (wchar_t *)CallStackTracing::s_wpInstance;
        v4 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v67;
          if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
          {
            v66 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v66 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v66 + 8) )
        {
          v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
          if ( *((_DWORD *)v70 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v70, "CByteStreamCacheReaderEx::ReturnResult", 384, -2147024882);
        }
        if ( g_wppLevels )
        {
          v77 = 29;
          goto LABEL_97;
        }
      }
    }
  }
  if ( *((_QWORD *)this + 4) )
  {
    *((_QWORD *)this + 63) += *((unsigned int *)this + 6);
    if ( *((_QWORD *)this + 63) / (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 65) + 64LL) != *((_QWORD *)this + 5) )
    {
      CByteStreamCacheReaderEx::FlushBuffers(this, *((_QWORD *)this + 63));
      *((_QWORD *)this + 5) = *((_QWORD *)this + 63)
                            / (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 65) + 64LL);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  v52 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v53 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v54 = GetLastError();
    v55 = (GUID *)TlsGetValue(*((_DWORD *)v52 + 3));
    if ( v55 )
    {
      v53 = v55;
    }
    else if ( !GetLastError() )
    {
      v61 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v61 = CallStackTracing::s_wpInstance;
      }
      v62 = (**(__int64 (__fastcall ***)(CallStackTracing *))v61)(v61);
      if ( v62 )
        v53 = (GUID *)v62;
    }
    SetLastError(v54);
    v56 = *(_DWORD *)&v53[124].Data2;
    if ( v56 )
    {
      v57 = v56 - 1;
      *(_DWORD *)&v53[124].Data2 = v57;
      if ( !v57 )
      {
        *(_DWORD *)&v53[124].Data2 = 0;
        *(_QWORD *)&v53[126].Data1 = 0;
        *(_DWORD *)&v53[124].Data4[4] = 0;
        v53[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v53[126].Data4 = 0;
        v53[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017f40  push    rbx
0x180017f42  push    rbp
0x180017f43  push    rsi
0x180017f44  push    rdi
0x180017f45  push    r15
0x180017f47  sub     rsp, 30h
0x180017f4b  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180017f52  xor     r15d, r15d
0x180017f55  mov     [rsp+58h+arg_8], r12
0x180017f5a  mov     rdi, rcx
0x180017f5d  mov     ebp, r15d
0x180017f60  test    rsi, rsi
0x180017f63  jz      loc_180018315
0x180017f69  lea     r12, aCbytestreamcac; "CByteStreamCacheReaderEx::ReturnResult"
0x180017f70  mov     [rsp+58h+arg_18], r14
0x180017f75  cmp     [rsi+8], bpl
0x180017f79  jz      short loc_180017FDE
0x180017f7b  lea     rbx, [rsi+0D0h]
0x180017f82  call    cs:__imp_GetLastError
0x180017f89  nop     dword ptr [rax+rax+00h]
0x180017f8e  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180017f91  mov     r14d, eax
0x180017f94  call    cs:__imp_TlsGetValue
0x180017f9b  nop     dword ptr [rax+rax+00h]
0x180017fa0  test    rax, rax
0x180017fa3  jz      loc_180018539
0x180017fa9  mov     rbx, rax
0x180017fac  mov     ecx, r14d; dwErrCode
0x180017faf  call    cs:__imp_SetLastError
0x180017fb6  nop     dword ptr [rax+rax+00h]
0x180017fbb  mov     eax, [rbx+7C4h]
0x180017fc1  cmp     eax, [rbx+7C8h]
0x180017fc7  jnb     short loc_180017FD8
0x180017fc9  add     rax, rax
0x180017fcc  mov     [rbx+rax*8], r12
0x180017fd0  mov     dword ptr [rbx+rax*8+8], 16Dh
0x180017fd8  inc     dword ptr [rbx+7C4h]
0x180017fde  lea     rcx, [rdi+238h]; lpCriticalSection
0x180017fe5  call    cs:__imp_EnterCriticalSection
0x180017fec  nop     dword ptr [rax+rax+00h]
0x180017ff1  cmp     [rdi+1E8h], ebp
0x180017ff7  jz      loc_1800183DE
0x180017ffd  mov     rax, [rdi+208h]
0x180018004  xor     edx, edx
0x180018006  mov     ecx, [rax+40h]
0x180018009  mov     rax, [rdi+1F8h]
0x180018010  div     rcx
0x180018013  mov     eax, [rdi+1F0h]
0x180018019  sub     eax, edx
0x18001801b  cmp     eax, [rdi+18h]
0x18001801e  jb      loc_18001850F
0x180018024  mov     ecx, 1D8h; Size
0x180018029  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001802e  mov     r14, rax
0x180018031  test    rax, rax
0x180018034  jz      loc_180018618
0x18001803a  lea     rax, ??_7CCacheReaderBufferList@@6B@; const CCacheReaderBufferList::`vftable'
0x180018041  mov     [rsp+58h+arg_10], r13
0x180018046  mov     [r14], rax
0x180018049  mov     rcx, r14
0x18001804c  mov     [r14+8], r15
0x180018050  mov     [r14+10h], r15
0x180018054  mov     [r14+18h], r15d
0x180018058  mov     [r14+1C0h], r15d
0x18001805f  mov     [r14+1B8h], r15
0x180018066  mov     [r14+1B0h], r15
0x18001806d  mov     [r14+1A8h], r15
0x180018074  mov     [r14+1C8h], r15
0x18001807b  mov     [r14+1D0h], r15
0x180018082  mov     rax, [r14]
0x180018085  mov     rax, [rax+8]
0x180018089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001808e  mov     rcx, [rdi+20h]
0x180018092  test    rcx, rcx
0x180018095  jnz     loc_180018724
0x18001809b  mov     rbp, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800180a2  mov     [rdi+20h], r14
0x1800180a6  mov     rax, [rdi+208h]
0x1800180ad  mov     rsi, [rdi+1F8h]
0x1800180b4  mov     r12d, [rdi+18h]
0x1800180b8  mov     [rsp+58h+arg_0], rsi
0x1800180bd  mov     r13d, [rax+40h]
0x1800180c1  test    rbp, rbp
0x1800180c4  jz      loc_180018519
0x1800180ca  cmp     [rbp+8], r15b
0x1800180ce  jz      short loc_180018142
0x1800180d0  lea     rsi, [rbp+0D0h]
0x1800180d7  call    cs:__imp_GetLastError
0x1800180de  nop     dword ptr [rax+rax+00h]
0x1800180e3  mov     ecx, [rbp+0Ch]; dwTlsIndex
0x1800180e6  mov     r15d, eax
0x1800180e9  call    cs:__imp_TlsGetValue
0x1800180f0  nop     dword ptr [rax+rax+00h]
0x1800180f5  test    rax, rax
0x1800180f8  jz      loc_1800185AB
0x1800180fe  mov     rsi, rax
0x180018101  mov     ecx, r15d; dwErrCode
0x180018104  call    cs:__imp_SetLastError
0x18001810b  nop     dword ptr [rax+rax+00h]
0x180018110  mov     eax, [rsi+7C4h]
0x180018116  xor     r15d, r15d
0x180018119  cmp     eax, [rsi+7C8h]
0x18001811f  jnb     short loc_180018137
0x180018121  add     rax, rax
0x180018124  lea     rcx, aCcachereaderbu_3; "CCacheReaderBufferList::Initialize"
0x18001812b  mov     [rsi+rax*8], rcx
0x18001812f  mov     dword ptr [rsi+rax*8+8], 226h
0x180018137  inc     dword ptr [rsi+7C4h]
0x18001813d  mov     rsi, [rsp+58h+arg_0]
0x180018142  mov     [r14+1A8h], r15
0x180018149  cmp     qword ptr [r14+10h], 0
0x18001814e  jnz     loc_180018284
0x180018154  mov     dword ptr [r14+18h], 1
0x18001815c  lea     rax, [r14+20h]
0x180018160  mov     [r14+10h], rax
0x180018164  lea     rdx, [rax+8]
0x180018168  mov     [rax], r15
0x18001816b  mov     rax, [r14+8]
0x18001816f  mov     [rdx+8], rax
0x180018173  mov     [r14+8], rdx
0x180018177  mov     rcx, [r14+10h]
0x18001817b  mov     [rcx+28h], rdx
0x18001817f  add     rcx, 20h ; ' '
0x180018183  mov     [r14+8], rcx
0x180018187  mov     rdx, [r14+10h]
0x18001818b  mov     [rdx+40h], rcx
0x18001818f  add     rdx, 38h ; '8'
0x180018193  mov     [r14+8], rdx
0x180018197  mov     rcx, [r14+10h]
0x18001819b  mov     [rcx+58h], rdx
0x18001819f  add     rcx, 50h ; 'P'
0x1800181a3  mov     [r14+8], rcx
0x1800181a7  mov     rdx, [r14+10h]
0x1800181ab  mov     [rdx+70h], rcx
0x1800181af  add     rdx, 68h ; 'h'
0x1800181b3  mov     [r14+8], rdx
0x1800181b7  mov     rcx, [r14+10h]
0x1800181bb  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800181bf  mov     [rcx+8], rdx
0x1800181c3  mov     [r14+8], rcx
0x1800181c7  mov     rdx, [r14+10h]
0x1800181cb  add     rdx, 98h
0x1800181d2  mov     [rdx+8], rcx
0x1800181d6  mov     [r14+8], rdx
0x1800181da  mov     rcx, [r14+10h]
0x1800181de  add     rcx, 0B0h
0x1800181e5  mov     [rcx+8], rdx
0x1800181e9  mov     [r14+8], rcx
0x1800181ed  mov     rdx, [r14+10h]
0x1800181f1  add     rdx, 0C8h
0x1800181f8  mov     [rdx+8], rcx
0x1800181fc  mov     [r14+8], rdx
0x180018200  mov     rcx, [r14+10h]
0x180018204  add     rcx, 0E0h
0x18001820b  mov     [rcx+8], rdx
0x18001820f  mov     [r14+8], rcx
0x180018213  mov     rdx, [r14+10h]
0x180018217  add     rdx, 0F8h
0x18001821e  mov     [rdx+8], rcx
0x180018222  mov     [r14+8], rdx
0x180018226  mov     rcx, [r14+10h]
0x18001822a  add     rcx, 110h
0x180018231  mov     [rcx+8], rdx
0x180018235  mov     [r14+8], rcx
0x180018239  mov     rdx, [r14+10h]
0x18001823d  add     rdx, 128h
0x180018244  mov     [rdx+8], rcx
0x180018248  mov     [r14+8], rdx
0x18001824c  mov     rcx, [r14+10h]
0x180018250  add     rcx, 140h
0x180018257  mov     [rcx+8], rdx
0x18001825b  mov     [r14+8], rcx
0x18001825f  mov     rdx, [r14+10h]
0x180018263  add     rdx, 158h
0x18001826a  mov     [rdx+8], rcx
0x18001826e  mov     [r14+8], rdx
0x180018272  mov     rax, [r14+10h]
0x180018276  add     rax, 170h
0x18001827c  mov     [rax+8], rdx
0x180018280  mov     [r14+8], rax
0x180018284  mov     rax, rsi
0x180018287  xor     edx, edx
0x180018289  mov     rsi, [rdi+1D8h]
0x180018290  mov     ebp, r15d
0x180018293  div     r13
0x180018296  mov     r15, rdx
0x180018299  test    rsi, rsi
0x18001829c  jz      loc_180018347
0x1800182a2  cmp     qword ptr [r14+8], 0
0x1800182a7  mov     rax, [rsi+8]
0x1800182ab  mov     r13, [rsi]
0x1800182ae  mov     [rsp+58h+arg_0], rax
0x1800182b3  jz      loc_180018735
0x1800182b9  mov     rcx, [r14+8]
0x1800182bd  mov     rsi, rax
0x1800182c0  mov     rax, [rcx+8]
0x1800182c4  mov     [r14+8], rax
0x1800182c8  mov     [rcx], r13
0x1800182cb  mov     qword ptr [rcx+8], 0
0x1800182d3  mov     rax, [r14+1B8h]
0x1800182da  mov     [rcx+10h], rax
0x1800182de  mov     rax, [r14+1B8h]
0x1800182e5  test    rax, rax
0x1800182e8  jnz     loc_18001860F
0x1800182ee  mov     [r14+1B0h], rcx
0x1800182f5  inc     dword ptr [r14+1C0h]
0x1800182fc  mov     [r14+1B8h], rcx
0x180018303  mov     rcx, r13
0x180018306  mov     rax, [r13+0]
0x18001830a  mov     rax, [rax+8]
0x18001830e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018313  jmp     short loc_180018299
0x180018315  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001831c  nop     dword ptr [rax+rax+00h]
0x180018321  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018328  mov     rcx, rax
0x18001832b  test    rax, rax
0x18001832e  jnz     loc_1800186FF
0x180018334  lea     rsi, qword_1801B97E0
0x18001833b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x180018342  jmp     loc_180017F69
0x180018347  mov     [r14+1C8h], r15d
0x18001834e  mov     [r14+1D0h], r12d
0x180018355  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001835c  mov     r13, [rsp+58h+arg_10]
0x180018361  cmp     byte ptr [rcx+8], 0
0x180018365  jz      loc_180018531
0x18001836b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018370  mov     rsi, rax
0x180018373  mov     eax, [rax+7C4h]
0x180018379  test    eax, eax
0x18001837b  jz      loc_18001852A
0x180018381  sub     eax, 1
0x180018384  mov     [rsi+7C4h], eax
0x18001838a  jnz     loc_18001852A
0x180018390  xor     r15d, r15d
0x180018393  mov     [rsi+7C4h], r15d
0x18001839a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800183a1  mov     [rsi+7E0h], r15
0x1800183a8  mov     [rsi+7CCh], r15d
0x1800183af  movups  xmmword ptr [rsi+7D0h], xmm0
0x1800183b6  mov     [rsi+7E8h], r15d
0x1800183bd  call    cs:__imp_GetCurrentThreadId
0x1800183c4  nop     dword ptr [rax+rax+00h]
0x1800183c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800183d0  mov     [rsi+7C0h], eax
0x1800183d6  test    ebp, ebp
0x1800183d8  js      loc_18001866C
0x1800183de  cmp     qword ptr [rdi+20h], 0
0x1800183e3  mov     r14, [rsp+58h+arg_18]
0x1800183e8  mov     r12, [rsp+58h+arg_8]
0x1800183ed  jnz     loc_1800184B8
0x1800183f3  lea     rcx, [rdi+238h]; lpCriticalSection
0x1800183fa  call    cs:__imp_LeaveCriticalSection
0x180018401  nop     dword ptr [rax+rax+00h]
0x180018406  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001840d  cmp     byte ptr [rbx+8], 0
0x180018411  jz      loc_1800184AA
0x180018417  lea     rdi, [rbx+0D0h]
0x18001841e  call    cs:__imp_GetLastError
0x180018425  nop     dword ptr [rax+rax+00h]
0x18001842a  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001842d  mov     esi, eax
0x18001842f  call    cs:__imp_TlsGetValue
0x180018436  nop     dword ptr [rax+rax+00h]
0x18001843b  test    rax, rax
0x18001843e  jz      loc_180018574
0x180018444  mov     rdi, rax
0x180018447  mov     ecx, esi; dwErrCode
0x180018449  call    cs:__imp_SetLastError
0x180018450  nop     dword ptr [rax+rax+00h]
0x180018455  mov     eax, [rdi+7C4h]
0x18001845b  test    eax, eax
0x18001845d  jz      short loc_1800184AA
0x18001845f  sub     eax, 1
0x180018462  mov     [rdi+7C4h], eax
0x180018468  jnz     short loc_1800184AA
0x18001846a  mov     [rdi+7C4h], r15d
0x180018471  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180018478  mov     qword ptr [rdi+7E0h], 0
0x180018483  mov     [rdi+7CCh], r15d
0x18001848a  movups  xmmword ptr [rdi+7D0h], xmm0
0x180018491  mov     [rdi+7E8h], r15d
0x180018498  call    cs:__imp_GetCurrentThreadId
0x18001849f  nop     dword ptr [rax+rax+00h]
0x1800184a4  mov     [rdi+7C0h], eax
0x1800184aa  mov     eax, ebp
0x1800184ac  add     rsp, 30h
0x1800184b0  pop     r15
0x1800184b2  pop     rdi
0x1800184b3  pop     rsi
0x1800184b4  pop     rbp
0x1800184b5  pop     rbx
0x1800184b6  retn
0x1800184b8  mov     eax, [rdi+18h]
0x1800184bb  xor     edx, edx
0x1800184bd  add     [rdi+1F8h], rax
0x1800184c4  mov     rax, [rdi+208h]
0x1800184cb  mov     r8, [rdi+1F8h]
0x1800184d2  mov     ecx, [rax+40h]
  ... truncated ...
```
