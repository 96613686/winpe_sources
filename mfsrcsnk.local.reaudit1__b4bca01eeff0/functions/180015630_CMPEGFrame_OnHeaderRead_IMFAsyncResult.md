# CMPEGFrame::OnHeaderRead(IMFAsyncResult *)

- ea: `0x180015630`
- end: `0x180015f4f`
- name: `?OnHeaderRead@CMPEGFrame@@QEAAXPEAUIMFAsyncResult@@@Z`
- size: `2335`
- prototype: `void __fastcall(CMPEGFrame *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180015610`

## callees

- `0x180005cf4`
- `0x180015630`
- `0x1800177b4`
- `0x18001c6c0`
- `0x18001c7b0`
- `0x180036c30`
- `0x180074194`
- `0x180077708`
- `0x180079680`
- `0x180174d9c`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015699`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001572e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015699`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001572e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001566e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001566e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001576b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001576b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001581d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015ae8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001581d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015ae8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001567f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015713`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001567f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015713`
- `MFPlat!MFPutWorkItemEx2` at `0x180015a88`
- `MFPlat!MFPutWorkItemEx2` at `0x180015a88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015c8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015cc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015d07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015c8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015cc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015d07`

## string_xrefs

- `0x18001565e`: `CMPEGFrame::OnHeaderRead`
- `0x1800156ab`: `CMPEGFrame::OnHeaderRead`
- `0x180015d77`: `CMPEGFrame::OnHeaderRead`
- `0x180015da5`: `CMPEGFrame::OnHeaderRead`
- `0x180015dd3`: `CMPEGFrame::OnHeaderRead`
- `0x1800156ee`: `CByteStreamCacheReaderEx::EndRead`
- `0x180015740`: `CByteStreamCacheReaderEx::EndRead`

## pseudocode

```c
void __fastcall CMPEGFrame::OnHeaderRead(CMPEGFrame *this, struct IMFAsyncResult *a2)
{
  CallStackTracing *v2; // rdi
  char *v5; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbp
  __int64 v11; // rbx
  char *v12; // rsi
  DWORD v13; // r12d
  char *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // edi
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  struct CallStackContext *v22; // rax
  int v23; // ecx
  int v24; // ecx
  unsigned int *v25; // rsi
  __int64 v26; // r8
  __int64 v27; // rdx
  BOOL v28; // ecx
  unsigned int v29; // ecx
  __int64 v30; // r8
  __int64 v31; // rdx
  int v32; // edi
  __int64 v33; // r11
  int v34; // esi
  int v35; // ebp
  __int64 v36; // r10
  struct IUnknown *v37; // r9
  __int64 v38; // rcx
  int v39; // eax
  int v40; // r8d
  unsigned int v41; // edx
  unsigned int v42; // eax
  unsigned int v43; // edx
  CByteStreamCacheReaderEx *v44; // rcx
  unsigned int v45; // edx
  __int64 v46; // rdx
  DWORD v47; // ecx
  struct CallStackContext *v48; // rax
  int v49; // ecx
  int v50; // ecx
  CallStackTracing *v51; // rcx
  struct tagMFASYNCRESULT *v52; // rbx
  IMFAsyncCallback *pCallback; // rcx
  CallStackTracing *v54; // rcx
  __int64 v55; // rax
  CallStackTracing *v56; // rcx
  __int64 v57; // rax
  wchar_t *v58; // rcx
  CallStackTracing *v59; // rax
  CallStackTracing *v60; // rax
  wchar_t *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v64; // rax
  struct CallStackContext *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  int v68; // [rsp+40h] [rbp-58h] BYREF
  __int64 v69; // [rsp+48h] [rbp-50h] BYREF
  const char *v70[9]; // [rsp+50h] [rbp-48h] BYREF

  v2 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v2 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v5 = (char *)v2 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v54 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v54 = CallStackTracing::s_wpInstance;
      }
      v55 = (**(__int64 (__fastcall ***)(CallStackTracing *))v54)(v54);
      if ( v55 )
        v5 = (char *)v55;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    v2 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CMPEGFrame::OnHeaderRead";
      *(_DWORD *)&v5[8 * v9 + 8] = 718;
    }
    ++*((_DWORD *)v5 + 497);
  }
  v10 = *((_QWORD *)this + 5);
  v11 = 0;
  v69 = 0;
  if ( !v2 )
  {
    CallStackTracing::InitInstance();
    v2 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v12 = (char *)v2 + 208;
    v13 = GetLastError();
    v14 = (char *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( v14 )
    {
      v12 = v14;
    }
    else if ( !GetLastError() )
    {
      v56 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v56 = CallStackTracing::s_wpInstance;
      }
      v57 = (**(__int64 (__fastcall ***)(CallStackTracing *))v56)(v56);
      if ( v57 )
        v12 = (char *)v57;
    }
    SetLastError(v13);
    v15 = *((unsigned int *)v12 + 497);
    if ( (unsigned int)v15 < *((_DWORD *)v12 + 498) )
    {
      v16 = 2 * v15;
      *(_QWORD *)&v12[8 * v16] = "CByteStreamCacheReaderEx::EndRead";
      *(_DWORD *)&v12[8 * v16 + 8] = 205;
    }
    ++*((_DWORD *)v12 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 568));
  v17 = *(_QWORD *)(v10 + 16);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *(_QWORD *)(v10 + 16) = 0;
  }
  v19 = ((__int64 (__fastcall *)(struct IMFAsyncResult *))a2->lpVtbl->GetStatus)(a2);
  if ( v19 < 0 )
  {
    v58 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v59;
      if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
      {
        v58 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v58 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v58 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v19 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CByteStreamCacheReaderEx::EndRead", 215, v19);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, v10, v19);
  }
  else
  {
    v11 = *(_QWORD *)(v10 + 32);
    v69 = v11;
    *(_QWORD *)(v10 + 32) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 568));
  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v22 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v23 = *((_DWORD *)v22 + 497);
    if ( v23 )
    {
      v24 = v23 - 1;
      *((_DWORD *)v22 + 497) = v24;
      if ( !v24 )
      {
        *((_DWORD *)v22 + 497) = 0;
        *((_QWORD *)v22 + 252) = 0;
        *((_DWORD *)v22 + 499) = 0;
        *((GUID *)v22 + 125) = GUID_00000000_0000_0000_0000_000000000000;
        *((_DWORD *)v22 + 506) = 0;
        *((_DWORD *)v22 + 496) = GetCurrentThreadId();
      }
    }
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( v19 < 0 )
  {
    if ( !v21 )
    {
      v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
      CallStackTracing::s_wpInstance = v60;
      if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
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
      v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v64 + 499) != v19 )
        CallStackContext::TraceFailure(v64, "CMPEGFrame::OnHeaderRead", 725, v19);
    }
    if ( !g_wppLevels )
      goto LABEL_106;
    v67 = 53;
    goto LABEL_105;
  }
  v25 = (unsigned int *)((char *)this + 56);
  v70[0] = (const char *)4;
  v70[1] = (char *)this + 56;
  v19 = CCacheReaderBufferList::Get((__int64 **)v11, v70);
  if ( v19 < 0 )
  {
    v51 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v51 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v51 + 8) )
    {
      v65 = CallStackTracing::GetThreadRelativeContext(v51);
      if ( *((_DWORD *)v65 + 499) != v19 )
        CallStackContext::TraceFailure(v65, "CMPEGFrame::OnHeaderRead", 732, v19);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids, this, v19);
    if ( !v11 )
      goto LABEL_56;
    goto LABEL_55;
  }
  v27 = *v25;
  v28 = (*v25 & 0xFFE00000) == -2097152;
  *((_DWORD *)this + 15) = v28;
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qddDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      v26,
      this,
      *(_DWORD *)(v11 + 460),
      *(_DWORD *)(v11 + 464),
      v27,
      v28);
  if ( !*((_DWORD *)this + 15) )
  {
    v19 = -1072873850;
    if ( !v11 )
      goto LABEL_56;
    goto LABEL_55;
  }
  v29 = *v25;
  v30 = (*v25 >> 19) & 3;
  v31 = (*v25 >> 17) & 3;
  *((_DWORD *)this + 16) = v30;
  *((_DWORD *)this + 17) = v31;
  v32 = v29 & 0x10000;
  *((_DWORD *)this + 18) = (v29 & 0x10000) == 0;
  v33 = (v29 >> 10) & 3;
  *((_DWORD *)this + 19) = (unsigned __int16)v29 >> 12;
  v34 = v29 & 0x200;
  *((_DWORD *)this + 20) = v33;
  *((_DWORD *)this + 21) = v34 != 0;
  *((_DWORD *)this + 22) = (v29 >> 8) & 1;
  *((_DWORD *)this + 23) = (unsigned __int8)v29 >> 6;
  *((_DWORD *)this + 24) = (v29 >> 4) & 3;
  *((_DWORD *)this + 25) = (v29 >> 3) & 1;
  *((_DWORD *)this + 27) = v29 & 3;
  *((_DWORD *)this + 26) = (v29 >> 2) & 1;
  v35 = *((unsigned __int8 *)&qword_1801A3560[6] + v30 + 4);
  if ( !(_BYTE)v35
    || !*((_BYTE *)&qword_1801A3560[6] + v31)
    || (v36 = 4 * (((unsigned __int16)v29 >> 12) + 16 * (v31 + 4 * v30)) + 1716480,
        !*(_DWORD *)((char *)&_ImageBase + v36))
    || (v37 = (struct IUnknown *)(4 * (v30 + 4 * v33) + 1717504), !*(_DWORD *)((char *)&_ImageBase + (_QWORD)v37))
    || (v38 = 4 * (v30 + 4 * v31) + 1717584, !*(_DWORD *)((char *)&_ImageBase + v38)) )
  {
    v19 = -1072873850;
    if ( !v11 )
      goto LABEL_56;
LABEL_55:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_56;
  }
  *((_DWORD *)this + 34) = v35;
  *((_DWORD *)this + 35) = *((unsigned __int8 *)&qword_1801A3560[6] + v31);
  *((_DWORD *)this + 36) = 1000 * *(_DWORD *)((char *)&_ImageBase + v36);
  *((_DWORD *)this + 37) = *(_DWORD *)((char *)&_ImageBase + (_QWORD)v37);
  v39 = *(_DWORD *)((char *)&_ImageBase + v38);
  *((_DWORD *)this + 38) = v39;
  v40 = dword_1801A3540[v31];
  *((_DWORD *)this + 39) = v40;
  v41 = 1000
      * *(_DWORD *)((char *)&_ImageBase + v36)
      * v39
      / (unsigned int)(*(_DWORD *)((char *)&_ImageBase + (_QWORD)v37) * v40)
      + (v34 != 0);
  v42 = 6;
  *((_DWORD *)this + 40) = v41;
  v43 = (v40 * v41) >> 3;
  *((_DWORD *)this + 29) = v43;
  *((_DWORD *)this + 30) = v43;
  if ( v32 )
    v42 = 4;
  if ( v42 >= v43 )
  {
    v19 = -1072873850;
    if ( !v11 )
      goto LABEL_56;
    goto LABEL_55;
  }
  v44 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 5);
  v45 = v43 - 4;
  *((_DWORD *)this + 29) = v45;
  v19 = CByteStreamCacheReaderEx::BeginRead(v44, v45, (struct IMFAsyncCallback *)this + 42, v37);
  if ( v19 < 0 )
  {
    v61 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
      CallStackTracing::s_wpInstance = v62;
      if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
      {
        v61 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v61 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v61 + 8) )
    {
      v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
      if ( *((_DWORD *)v66 + 499) != v19 )
        CallStackContext::TraceFailure(v66, "CMPEGFrame::OnHeaderRead", 792, v19);
    }
    if ( !g_wppLevels )
      goto LABEL_106;
    v67 = 56;
LABEL_105:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v67, &WPP_b8003b5036f03cbb8c477decc5c1127e_Traceguids, this, v19);
LABEL_106:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v69);
LABEL_56:
    v52 = (struct tagMFASYNCRESULT *)*((_QWORD *)this + 6);
    pCallback = v52->pCallback;
    v52->hrStatusResult = v19;
    if ( pCallback )
    {
      LODWORD(v69) = 0;
      v68 = 0;
      if ( ((int (__fastcall *)(IMFAsyncCallback *, __int64 *, int *))pCallback->lpVtbl->GetParameters)(
             pCallback,
             &v69,
             &v68) < 0 )
      {
        v47 = 1;
        v68 = 1;
      }
      else
      {
        v47 = v68;
      }
      MFPutWorkItemEx2(v47, 0, &v52->AsyncResult);
    }
    else
    {
      CAsyncResult::SignalEvent(v52);
    }
    goto LABEL_44;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_44:
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v48 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v49 = *((_DWORD *)v48 + 497);
    if ( v49 )
    {
      v50 = v49 - 1;
      *((_DWORD *)v48 + 497) = v50;
      if ( !v50 )
      {
        *((_DWORD *)v48 + 497) = 0;
        *((_QWORD *)v48 + 252) = 0;
        *((_DWORD *)v48 + 499) = 0;
        *((GUID *)v48 + 125) = GUID_00000000_0000_0000_0000_000000000000;
        *((_DWORD *)v48 + 506) = 0;
        *((_DWORD *)v48 + 496) = GetCurrentThreadId();
      }
    }
  }
}

```

## disassembly

```asm
0x180015630  mov     [rsp+arg_10], rbx
0x180015635  push    rbp
0x180015636  push    rsi
0x180015637  push    rdi
0x180015638  push    r12
0x18001563a  push    r13
0x18001563c  push    r14
0x18001563e  push    r15
0x180015640  sub     rsp, 60h
0x180015644  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001564b  mov     r15, rdx
0x18001564e  mov     r14, rcx
0x180015651  test    rdi, rdi
0x180015654  jz      loc_180015B13
0x18001565a  cmp     byte ptr [rdi+8], 0
0x18001565e  lea     rcx, aCmpegframeOnhe; "CMPEGFrame::OnHeaderRead"
0x180015665  jz      short loc_1800156D6
0x180015667  lea     rbx, [rdi+0D0h]
0x18001566e  call    cs:__imp_GetLastError
0x180015675  nop     dword ptr [rax+rax+00h]
0x18001567a  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18001567d  mov     esi, eax
0x18001567f  call    cs:__imp_TlsGetValue
0x180015686  nop     dword ptr [rax+rax+00h]
0x18001568b  test    rax, rax
0x18001568e  jz      loc_180015BBF
0x180015694  mov     rbx, rax
0x180015697  mov     ecx, esi; dwErrCode
0x180015699  call    cs:__imp_SetLastError
0x1800156a0  nop     dword ptr [rax+rax+00h]
0x1800156a5  mov     eax, [rbx+7C4h]
0x1800156ab  lea     rcx, aCmpegframeOnhe; "CMPEGFrame::OnHeaderRead"
0x1800156b2  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800156b9  cmp     eax, [rbx+7C8h]
0x1800156bf  jnb     short loc_1800156D0
0x1800156c1  add     rax, rax
0x1800156c4  mov     [rbx+rax*8], rcx
0x1800156c8  mov     dword ptr [rbx+rax*8+8], 2CEh
0x1800156d0  inc     dword ptr [rbx+7C4h]
0x1800156d6  mov     rbp, [r14+28h]
0x1800156da  xor     r13d, r13d
0x1800156dd  mov     ebx, r13d
0x1800156e0  mov     [rsp+98h+var_50], rbx
0x1800156e5  test    rdi, rdi
0x1800156e8  jz      loc_180015B24
0x1800156ee  lea     r12, aCbytestreamcac_14; "CByteStreamCacheReaderEx::EndRead"
0x1800156f5  cmp     [rdi+8], bl
0x1800156f8  jz      short loc_180015764
0x1800156fa  lea     rsi, [rdi+0D0h]
0x180015701  call    cs:__imp_GetLastError
0x180015708  nop     dword ptr [rax+rax+00h]
0x18001570d  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180015710  mov     r12d, eax
0x180015713  call    cs:__imp_TlsGetValue
0x18001571a  nop     dword ptr [rax+rax+00h]
0x18001571f  test    rax, rax
0x180015722  jz      loc_180015BF6
0x180015728  mov     rsi, rax
0x18001572b  mov     ecx, r12d; dwErrCode
0x18001572e  call    cs:__imp_SetLastError
0x180015735  nop     dword ptr [rax+rax+00h]
0x18001573a  mov     eax, [rsi+7C4h]
0x180015740  lea     r12, aCbytestreamcac_14; "CByteStreamCacheReaderEx::EndRead"
0x180015747  cmp     eax, [rsi+7C8h]
0x18001574d  jnb     short loc_18001575E
0x18001574f  add     rax, rax
0x180015752  mov     [rsi+rax*8], r12
0x180015756  mov     dword ptr [rsi+rax*8+8], 0CDh
0x18001575e  inc     dword ptr [rsi+7C4h]
0x180015764  lea     rcx, [rbp+238h]; lpCriticalSection
0x18001576b  call    cs:__imp_EnterCriticalSection
0x180015772  nop     dword ptr [rax+rax+00h]
0x180015777  mov     rcx, [rbp+10h]
0x18001577b  test    rcx, rcx
0x18001577e  jz      short loc_180015790
0x180015780  mov     rax, [rcx]
0x180015783  mov     rax, [rax+10h]
0x180015787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001578c  mov     [rbp+10h], r13
0x180015790  mov     rax, [r15]
0x180015793  mov     rcx, r15
0x180015796  mov     rax, [rax+20h]
0x18001579a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001579f  mov     edi, eax
0x1800157a1  test    eax, eax
0x1800157a3  js      loc_180015C7A
0x1800157a9  mov     rbx, [rbp+20h]
0x1800157ad  mov     [rsp+98h+var_50], rbx
0x1800157b2  mov     [rbp+20h], r13
0x1800157b6  lea     rcx, [rbp+238h]; lpCriticalSection
0x1800157bd  call    cs:__imp_LeaveCriticalSection
0x1800157c4  nop     dword ptr [rax+rax+00h]
0x1800157c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800157d0  cmp     [rcx+8], r13b
0x1800157d4  jz      short loc_180015836
0x1800157d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800157db  mov     rsi, rax
0x1800157de  mov     ecx, [rax+7C4h]
0x1800157e4  test    ecx, ecx
0x1800157e6  jz      short loc_18001582F
0x1800157e8  sub     ecx, 1
0x1800157eb  mov     [rax+7C4h], ecx
0x1800157f1  jnz     short loc_18001582F
0x1800157f3  mov     [rax+7C4h], r13d
0x1800157fa  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180015801  mov     [rax+7E0h], r13
0x180015808  mov     [rax+7CCh], r13d
0x18001580f  movups  xmmword ptr [rax+7D0h], xmm0
0x180015816  mov     [rax+7E8h], r13d
0x18001581d  call    cs:__imp_GetCurrentThreadId
0x180015824  nop     dword ptr [rax+rax+00h]
0x180015829  mov     [rsi+7C0h], eax
0x18001582f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015836  test    edi, edi
0x180015838  js      loc_180015CBC
0x18001583e  mov     r15d, 4
0x180015844  lea     rsi, [r14+38h]
0x180015848  lea     rdx, [rsp+98h+var_48]; struct MFBUFFER::CBuffer *
0x18001584d  mov     [rsp+98h+var_48], r15
0x180015852  mov     rcx, rbx; this
0x180015855  mov     [rsp+98h+var_40], rsi
0x18001585a  call    ?Get@CCacheReaderBufferList@@QEAAJAEBVCBuffer@MFBUFFER@@@Z; CCacheReaderBufferList::Get(MFBUFFER::CBuffer const &)
0x18001585f  mov     edi, eax
0x180015861  test    eax, eax
0x180015863  js      loc_180015B35
0x180015869  mov     edx, [rsi]
0x18001586b  mov     ecx, r13d
0x18001586e  mov     eax, edx
0x180015870  and     eax, 0FFE00000h
0x180015875  cmp     eax, 0FFE00000h
0x18001587a  setz    cl
0x18001587d  mov     [r14+3Ch], ecx
0x180015881  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180015888  jnb     loc_180015EDF
0x18001588e  cmp     [r14+3Ch], r13d
0x180015892  jz      loc_180015B8D
0x180015898  mov     ecx, [rsi]
0x18001589a  lea     r12, __ImageBase
0x1800158a1  mov     r8d, ecx
0x1800158a4  mov     eax, r13d
0x1800158a7  shr     r8d, 13h
0x1800158ab  mov     edx, ecx
0x1800158ad  and     r8d, 3
0x1800158b1  shr     edx, 11h
0x1800158b4  and     edx, 3
0x1800158b7  mov     [r14+40h], r8d
0x1800158bb  mov     edi, ecx
0x1800158bd  mov     [r14+44h], edx
0x1800158c1  and     edi, 10000h
0x1800158c7  mov     r9d, ecx
0x1800158ca  mov     r11d, ecx
0x1800158cd  mov     esi, ecx
0x1800158cf  setz    al
0x1800158d2  shr     r9d, 0Ch
0x1800158d6  mov     [r14+48h], eax
0x1800158da  and     r9d, 0Fh
0x1800158de  shr     r11d, 0Ah
0x1800158e2  mov     eax, r13d
0x1800158e5  and     r11d, 3
0x1800158e9  mov     [r14+4Ch], r9d
0x1800158ed  and     esi, 200h
0x1800158f3  mov     [r14+50h], r11d
0x1800158f7  setnz   al
0x1800158fa  mov     [r14+54h], eax
0x1800158fe  mov     eax, ecx
0x180015900  shr     eax, 8
0x180015903  and     eax, 1
0x180015906  mov     [r14+58h], eax
0x18001590a  mov     eax, ecx
0x18001590c  shr     eax, 6
0x18001590f  and     eax, 3
0x180015912  mov     [r14+5Ch], eax
0x180015916  mov     eax, ecx
0x180015918  shr     eax, 4
0x18001591b  and     eax, 3
0x18001591e  mov     [r14+60h], eax
0x180015922  mov     eax, ecx
0x180015924  shr     eax, 3
0x180015927  and     eax, 1
0x18001592a  mov     [r14+64h], eax
0x18001592e  mov     eax, ecx
0x180015930  shr     eax, 2
0x180015933  and     ecx, 3
0x180015936  and     eax, 1
0x180015939  mov     [r14+6Ch], ecx
0x18001593d  mov     [r14+68h], eax
0x180015941  movzx   ebp, byte ptr [r8+r12+1A3594h]
0x18001594a  test    bpl, bpl
0x18001594d  jz      loc_180015BB3
0x180015953  cmp     [rdx+r12+1A3590h], r13b
0x18001595b  jz      loc_180015BB3
0x180015961  lea     rcx, [rdx+r8*4]
0x180015965  mov     eax, r9d
0x180015968  shl     rcx, 4
0x18001596c  add     rcx, rax
0x18001596f  lea     r10, ds:1A3100h[rcx*4]
0x180015977  cmp     [r10+r12], r13d
0x18001597b  jz      loc_180015BB3
0x180015981  lea     rcx, [r8+r11*4]
0x180015985  lea     r9, ds:1A3500h[rcx*4]; struct IUnknown *
0x18001598d  cmp     [r9+r12], r13d
0x180015991  jz      loc_180015BB3
0x180015997  lea     rax, [r8+rdx*4]
0x18001599b  lea     rcx, ds:1A3550h[rax*4]
0x1800159a3  cmp     [rcx+r12], r13d
0x1800159a7  jz      loc_180015BB3
0x1800159ad  mov     [r14+88h], ebp
0x1800159b4  movzx   eax, byte ptr [rdx+r12+1A3590h]
0x1800159bd  mov     [r14+8Ch], eax
0x1800159c4  imul    eax, [r10+r12], 3E8h
0x1800159cc  mov     [r14+90h], eax
0x1800159d3  mov     eax, [r9+r12]
0x1800159d7  mov     [r14+94h], eax
0x1800159de  mov     eax, [rcx+r12]
0x1800159e2  mov     [r14+98h], eax
0x1800159e9  mov     r8d, ds:rva dword_1801A3540[r12+rdx*4]
0x1800159f1  xor     edx, edx
0x1800159f3  mov     [r14+9Ch], r8d
0x1800159fa  mov     ecx, r8d
0x1800159fd  imul    eax, [r10+r12]
0x180015a02  imul    ecx, [r9+r12]
0x180015a07  imul    eax, 3E8h
0x180015a0d  div     ecx
0x180015a0f  test    esi, esi
0x180015a11  mov     ecx, r13d
0x180015a14  setnz   cl
0x180015a17  lea     edx, [rax+rcx]
0x180015a1a  mov     eax, 6
0x180015a1f  mov     [r14+0A0h], edx
0x180015a26  imul    edx, r8d
0x180015a2a  shr     edx, 3
0x180015a2d  test    edi, edi
0x180015a2f  mov     [r14+74h], edx
0x180015a33  mov     [r14+78h], edx
0x180015a37  cmovnz  eax, r15d
0x180015a3b  cmp     eax, edx
0x180015a3d  jnb     loc_180015BA7
0x180015a43  mov     rcx, [r14+28h]; this
0x180015a47  lea     r8, [r14+150h]; struct IMFAsyncCallback *
0x180015a4e  add     edx, 0FFFFFFFCh; unsigned int
0x180015a51  mov     [r14+74h], edx
0x180015a55  call    ?BeginRead@CByteStreamCacheReaderEx@@QEAAJKPEAUIMFAsyncCallback@@PEAUIUnknown@@@Z; CByteStreamCacheReaderEx::BeginRead(ulong,IMFAsyncCallback *,IUnknown *)
0x180015a5a  mov     edi, eax
0x180015a5c  test    eax, eax
0x180015a5e  js      loc_180015CF7
0x180015a64  test    rbx, rbx
0x180015a67  jz      short loc_180015A94
0x180015a69  mov     rax, [rbx]
0x180015a6c  mov     rcx, rbx
0x180015a6f  mov     rax, [rax+10h]
0x180015a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a78  jmp     short loc_180015A94
0x180015a7a  mov     ecx, 1; dwQueue
0x180015a7f  mov     [rsp+98h+var_58], ecx
0x180015a83  mov     r8, rbx; pResult
0x180015a86  xor     edx, edx; Priority
0x180015a88  call    cs:__imp_MFPutWorkItemEx2
0x180015a8f  nop     dword ptr [rax+rax+00h]
0x180015a94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180015a9b  cmp     [rcx+8], r13b
0x180015a9f  jz      short loc_180015AFA
0x180015aa1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015aa6  mov     rbx, rax
0x180015aa9  mov     ecx, [rax+7C4h]
0x180015aaf  test    ecx, ecx
0x180015ab1  jz      short loc_180015AFA
0x180015ab3  sub     ecx, 1
0x180015ab6  mov     [rax+7C4h], ecx
0x180015abc  jnz     short loc_180015AFA
0x180015abe  mov     [rax+7C4h], r13d
0x180015ac5  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180015acc  mov     [rax+7E0h], r13
0x180015ad3  mov     [rax+7CCh], r13d
0x180015ada  movups  xmmword ptr [rax+7D0h], xmm0
0x180015ae1  mov     [rax+7E8h], r13d
0x180015ae8  call    cs:__imp_GetCurrentThreadId
0x180015aef  nop     dword ptr [rax+rax+00h]
0x180015af4  mov     [rbx+7C0h], eax
0x180015afa  mov     rbx, [rsp+98h+arg_10]
0x180015b02  add     rsp, 60h
0x180015b06  pop     r15
0x180015b08  pop     r14
0x180015b0a  pop     r13
0x180015b0c  pop     r12
0x180015b0e  pop     rdi
0x180015b0f  pop     rsi
0x180015b10  pop     rbp
0x180015b11  retn
0x180015b13  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180015b18  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015b1f  jmp     loc_18001565A
0x180015b24  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180015b29  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015b30  jmp     loc_1800156EE
0x180015b35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180015b3c  test    rcx, rcx
0x180015b3f  jz      short loc_180015B99
0x180015b41  cmp     [rcx+8], r13b
0x180015b45  jnz     loc_180015D91
0x180015b4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
