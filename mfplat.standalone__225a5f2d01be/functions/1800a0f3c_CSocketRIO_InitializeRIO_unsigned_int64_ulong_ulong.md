# CSocketRIO::InitializeRIO(unsigned __int64,ulong,ulong)

- ea: `0x1800a0f3c`
- end: `0x1800a1d6d`
- name: `?InitializeRIO@CSocketRIO@@QEAAJ_KKK@Z`
- size: `3633`
- prototype: `__int64 __fastcall(CSocketRIO *__hidden this, SOCKET s, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800ccb10`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18005cea0`
- `0x180098f98`
- `0x1800a0bdc`
- `0x1800a0f3c`
- `0x18012003c`
- `0x1801200d0`
- `0x180120ecc`
- `0x18012be28`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a10ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a10ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a10cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a10cd`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x1800a1236`
- `RTWorkQ!RtwqPutWaitingWorkItem` at `0x1800a1236`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x1800a1187`
- `RTWorkQ!RtwqCreateAsyncResult` at `0x1800a1187`
- `WS2_32!WSAIoctl` at `0x1800a0feb`
- `WS2_32!WSAIoctl` at `0x1800a0feb`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a0ffe`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a1317`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a140a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a1b5a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a0ffe`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a1317`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a140a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800a1b5a`

## pseudocode

```c
__int64 __fastcall CSocketRIO::InitializeRIO(CSocketRIO *this, SOCKET s, unsigned int a3, unsigned int a4)
{
  unsigned __int64 v4; // rsi
  int Error; // eax
  int AsyncResult; // r14d
  CallStackTracing *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 (__fastcall *v21)(__int64, _QWORD *); // rax
  __int64 v22; // rax
  int v23; // eax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  __int64 v26; // rax
  int v27; // eax
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  unsigned __int64 v30; // rdi
  void *v31; // rax
  void **v32; // rsi
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  void *v36; // rax
  _QWORD *v37; // r13
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  void *v40; // rax
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  void *v43; // rax
  void **v44; // r12
  CallStackTracing *v45; // rcx
  struct CallStackContext *v46; // rax
  __int64 v47; // rax
  bool v48; // cf
  unsigned __int64 v49; // rax
  unsigned __int64 *v50; // rax
  _QWORD *v51; // rbx
  CallStackTracing *v52; // rcx
  struct CallStackContext *v53; // rax
  unsigned int v54; // r13d
  void **v55; // r8
  char *v56; // r10
  char *v57; // rdi
  __int64 v58; // rcx
  char *v59; // rax
  char *v60; // rdx
  void **v61; // rdi
  void **v62; // rbx
  unsigned __int64 v63; // r9
  void **v64; // r10
  unsigned __int64 v65; // r11
  __int64 v66; // rax
  unsigned __int64 v67; // rbx
  unsigned int v68; // esi
  unsigned int v69; // edx
  __int64 v70; // rcx
  __int64 v71; // rdi
  unsigned __int64 v72; // r12
  __int64 v73; // rcx
  int v74; // eax
  CallStackTracing *v76; // rcx
  struct CallStackContext *v77; // rax
  CallStackTracing *v78; // rcx
  struct CallStackContext *v79; // rax
  CallStackScopeTrace v80; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v81; // [rsp+54h] [rbp-ACh]
  unsigned int v82; // [rsp+58h] [rbp-A8h] BYREF
  DWORD lpcbBytesReturned; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v84; // [rsp+60h] [rbp-A0h] BYREF
  void *v85; // [rsp+68h] [rbp-98h]
  void *v86; // [rsp+70h] [rbp-90h]
  _QWORD v87[2]; // [rsp+78h] [rbp-88h] BYREF
  int v88; // [rsp+88h] [rbp-78h]
  __int64 v89; // [rsp+8Ch] [rbp-74h]
  int v90; // [rsp+94h] [rbp-6Ch]
  _DWORD vInBuffer[6]; // [rsp+98h] [rbp-68h] BYREF
  char v92[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v93; // [rsp+D0h] [rbp-30h]
  __int64 v94; // [rsp+D8h] [rbp-28h]
  unsigned int *v95; // [rsp+E0h] [rbp-20h]
  __int64 v96; // [rsp+E8h] [rbp-18h]

  v4 = a3;
  v81 = a3;
  v82 = a4;
  CallStackScopeTrace::CallStackScopeTrace(&v80, "CSocketRIO::InitializeRIO", 69);
  vInBuffer[0] = -2062950271;
  vInBuffer[1] = 1074108125;
  vInBuffer[2] = 782132657;
  vInBuffer[3] = 1067370472;
  lpcbBytesReturned = 0;
  if ( WSAIoctl(s, 0xC8000024, vInBuffer, 0x10u, (char *)this + 216, 0x70u, &lpcbBytesReturned, 0, 0) )
  {
    Error = WSAGetLastError();
    AsyncResult = Error;
    if ( Error > 0 )
      AsyncResult = (unsigned __int16)Error | 0x80070000;
    if ( AsyncResult < 0 )
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v10 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v10->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v10);
        if ( ThreadRelativeContext->m_result != AsyncResult )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CSocketRIO::InitializeRIO", 79, AsyncResult);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_197;
      v12 = 10;
      goto LABEL_14;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 3) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    AsyncResult = LastError;
    if ( LastError > 0 )
      AsyncResult = (unsigned __int16)LastError | 0x80070000;
    if ( AsyncResult < 0 )
    {
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v15 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v15->m_fEnabled )
      {
        v16 = CallStackTracing::GetThreadRelativeContext(v15);
        if ( v16->m_result != AsyncResult )
          CallStackContext::TraceFailure(v16, "CSocketRIO::InitializeRIO", 85, AsyncResult);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_197;
      v12 = 11;
      goto LABEL_14;
    }
  }
  AsyncResult = RtwqCreateAsyncResult(0, (IRtwqAsyncCallback *)((char *)this + 8), 0, (IRtwqAsyncResult **)this + 4);
  if ( AsyncResult < 0 )
  {
    v17 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v17 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v17->m_fEnabled )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v17);
      if ( v18->m_result != AsyncResult )
        CallStackContext::TraceFailure(v18, "CSocketRIO::InitializeRIO", 88, AsyncResult);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_197;
    v12 = 12;
    goto LABEL_14;
  }
  AsyncResult = RtwqPutWaitingWorkItem(
                  *((HANDLE *)this + 3),
                  0,
                  *((IRtwqAsyncResult **)this + 4),
                  (RTWQWORKITEM_KEY *)this + 5);
  if ( AsyncResult < 0 )
  {
    v19 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v19 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v19->m_fEnabled )
    {
      v20 = CallStackTracing::GetThreadRelativeContext(v19);
      if ( v20->m_result != AsyncResult )
        CallStackContext::TraceFailure(v20, "CSocketRIO::InitializeRIO", 89, AsyncResult);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_197;
    v12 = 13;
    goto LABEL_14;
  }
  v87[1] = *((_QWORD *)this + 3);
  v21 = (__int64 (__fastcall *)(__int64, _QWORD *))*((_QWORD *)this + 33);
  v87[0] = 1;
  v89 = 0;
  v90 = 0;
  v88 = 0;
  v22 = v21(401, v87);
  *((_QWORD *)this + 6) = v22;
  if ( !v22 )
  {
    v23 = WSAGetLastError();
    AsyncResult = v23;
    if ( v23 > 0 )
      AsyncResult = (unsigned __int16)v23 | 0x80070000;
    if ( AsyncResult < 0 )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v24->m_fEnabled )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( v25->m_result != AsyncResult )
          CallStackContext::TraceFailure(v25, "CSocketRIO::InitializeRIO", 99, AsyncResult);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_197;
      v12 = 14;
      goto LABEL_14;
    }
  }
  v26 = (*((__int64 (__fastcall **)(SOCKET, __int64, __int64, __int64, int, _QWORD, _QWORD, _QWORD))this + 34))(
          s,
          200,
          1,
          201,
          1,
          *((_QWORD *)this + 6),
          *((_QWORD *)this + 6),
          0);
  *((_QWORD *)this + 7) = v26;
  if ( v26 )
    goto LABEL_74;
  v27 = WSAGetLastError();
  AsyncResult = v27;
  if ( v27 > 0 )
    AsyncResult = (unsigned __int16)v27 | 0x80070000;
  if ( AsyncResult >= 0 )
  {
LABEL_74:
    *((_DWORD *)this + 24) = v4;
    *((_DWORD *)this + 25) = a4;
    v30 = v4;
    v31 = operator new[](saturated_mul(v4, 8u));
    v32 = (void **)((char *)this + 72);
    *((_QWORD *)this + 9) = v31;
    if ( !v31 )
    {
      v33 = CallStackTracing::s_wpInstance;
      AsyncResult = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v33 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v33->m_fEnabled )
      {
        v34 = CallStackTracing::GetThreadRelativeContext(v33);
        if ( v34->m_result != -2147024882 )
          CallStackContext::TraceFailure(v34, "CSocketRIO::InitializeRIO", 112, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_197;
      v35 = 16;
      goto LABEL_84;
    }
    v36 = operator new[](saturated_mul(v30, 8u));
    v37 = (_QWORD *)((char *)this + 64);
    *((_QWORD *)this + 8) = v36;
    if ( !v36 )
    {
      v38 = CallStackTracing::s_wpInstance;
      AsyncResult = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v38 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v38->m_fEnabled )
      {
        v39 = CallStackTracing::GetThreadRelativeContext(v38);
        if ( v39->m_result != -2147024882 )
          CallStackContext::TraceFailure(v39, "CSocketRIO::InitializeRIO", 115, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_197;
      v35 = 17;
      goto LABEL_84;
    }
    v40 = operator new[](saturated_mul(v30, 4u));
    *((_QWORD *)this + 10) = v40;
    if ( !v40 )
    {
      v41 = CallStackTracing::s_wpInstance;
      AsyncResult = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v41 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v41->m_fEnabled )
      {
        v42 = CallStackTracing::GetThreadRelativeContext(v41);
        if ( v42->m_result != -2147024882 )
          CallStackContext::TraceFailure(v42, "CSocketRIO::InitializeRIO", 118, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_197;
      v35 = 18;
      goto LABEL_84;
    }
    v43 = operator new[](v30);
    v44 = (void **)((char *)this + 88);
    *((_QWORD *)this + 11) = v43;
    if ( !v43 )
    {
      v45 = CallStackTracing::s_wpInstance;
      AsyncResult = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v45 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v45->m_fEnabled )
      {
        v46 = CallStackTracing::GetThreadRelativeContext(v45);
        if ( v46->m_result != -2147024882 )
          CallStackContext::TraceFailure(v46, "CSocketRIO::InitializeRIO", 121, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_197;
      v35 = 19;
      goto LABEL_84;
    }
    v47 = 8 * v30;
    if ( !is_mul_ok(v30, 8u) )
      v47 = -1;
    v48 = __CFADD__(v47, 8);
    v49 = v47 + 8;
    if ( v48 )
      v49 = -1;
    v50 = (unsigned __int64 *)operator new[](v49);
    if ( v50 )
    {
      v51 = v50 + 1;
      *v50 = v30;
      `vector constructor iterator'(
        v50 + 1,
        8u,
        v30,
        ComSmartPtr<CSocketRIO::CRIOSendResult>::ComSmartPtr<CSocketRIO::CRIOSendResult>);
    }
    else
    {
      v51 = 0;
    }
    *((_QWORD *)this + 14) = v51;
    if ( !v51 )
    {
      v52 = CallStackTracing::s_wpInstance;
      AsyncResult = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v52 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v52->m_fEnabled )
      {
        v53 = CallStackTracing::GetThreadRelativeContext(v52);
        if ( v53->m_result != -2147024882 )
          CallStackContext::TraceFailure(v53, "CSocketRIO::InitializeRIO", 124, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_197;
      v35 = 20;
LABEL_84:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v35,
        WPP_aba7331d81f734ed0cdb9b63a6662b3c_Traceguids,
        this,
        -2147024882);
      goto LABEL_197;
    }
    if ( (_DWORD)v30 )
    {
      v54 = 0;
      v55 = (void **)((char *)this + 80);
      if ( (unsigned int)v30 < 2
        || (v56 = (char *)*v44,
            v57 = (char *)*v55,
            v58 = v81 - 1,
            v59 = (char *)*v44 + v58,
            v85 = v57,
            v86 = v56,
            v60 = &v57[4 * v58],
            v56 <= v60)
        && v59 >= v57 )
      {
        v61 = (void **)((char *)this + 64);
      }
      else
      {
        v61 = (void **)((char *)this + 64);
        v62 = (void **)*((_QWORD *)this + 8);
        v84 = (__int64)v62;
        v63 = (unsigned __int64)&v62[v58];
        if ( (unsigned __int64)v56 > v63 || v59 < (char *)v62 )
        {
          v64 = (void **)*v32;
          v65 = (unsigned __int64)*v32 + 8 * v58;
          if ( ((unsigned __int64)v86 > v65 || v59 < (char *)v64)
            && (v86 > v61 || v59 < (char *)v61)
            && (v86 > v32 || v59 < (char *)v32)
            && (v86 > v55 || v59 < (char *)v55)
            && (v86 > v44 || v59 < (char *)v44)
            && ((unsigned __int64)v85 > v63 || v60 < (char *)v62)
            && ((unsigned __int64)v85 > v65 || v60 < (char *)v64)
            && (v85 > v61 || v60 < (char *)v61)
            && (v85 > v32 || v60 < (char *)v32)
            && (v85 > v55 || v60 < (char *)v55)
            && (v85 > v44 || v60 < (char *)v44)
            && ((unsigned __int64)v62 > v65 || v63 < (unsigned __int64)v64)
            && (v62 > v61 || v63 < (unsigned __int64)v61)
            && (v62 > v32 || v63 < (unsigned __int64)v32)
            && (v62 > v55 || v63 < (unsigned __int64)v55)
            && (v62 > v44 || v63 < (unsigned __int64)v44)
            && (v64 > v61 || v65 < (unsigned __int64)v61)
            && (v64 > v32 || v65 < (unsigned __int64)v32)
            && (v64 > v55 || v65 < (unsigned __int64)v55)
            && (v64 > v44 || v65 < (unsigned __int64)v44) )
          {
            v66 = v81 & 0xFFFFFFFE;
            do
              v54 += 2;
            while ( v54 < (unsigned int)v66 );
            v67 = 8 * v66;
            v68 = v81 & 0xFFFFFFFE;
            memset_0(v64, 0, 8 * v66);
            memset64((void *)v84, 0xFFFFFFFF, v67 >> 3);
            memset_0(v85, 0, 4LL * v68);
            memset_0(v86, 0, v68);
            v32 = (void **)((char *)this + 72);
            v61 = (void **)((char *)this + 64);
            v55 = (void **)((char *)this + 80);
          }
        }
      }
      v69 = v81;
      if ( v54 < v81 )
      {
        v70 = v54;
        do
        {
          ++v54;
          *((_QWORD *)*v32 + v70) = 0;
          *((_QWORD *)*v61 + v70) = 0xFFFFFFFFLL;
          *((_DWORD *)*v55 + v70) = 0;
          *((_BYTE *)*v44 + v70++) = 0;
        }
        while ( v54 < v69 );
        v71 = 0;
        v37 = (_QWORD *)((char *)this + 64);
LABEL_189:
        v72 = v82;
        while ( 1 )
        {
          *(_QWORD *)(*((_QWORD *)this + 9) + 8 * v71) = operator new[](v72);
          v73 = *(_QWORD *)(*((_QWORD *)this + 9) + 8 * v71);
          if ( !v73 )
            break;
          *(_QWORD *)(*v37 + 8 * v71) = (*((__int64 (__fastcall **)(__int64, _QWORD))this + 38))(v73, (unsigned int)v72);
          if ( *(_QWORD *)(*v37 + 8 * v71) == 0xFFFFFFFFLL )
          {
            v74 = WSAGetLastError();
            AsyncResult = v74;
            if ( v74 > 0 )
              AsyncResult = (unsigned __int16)v74 | 0x80070000;
            if ( AsyncResult < 0 )
            {
              v76 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v76 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v76 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v76->m_fEnabled )
              {
                v77 = CallStackTracing::GetThreadRelativeContext(v76);
                if ( v77->m_result != AsyncResult )
                  CallStackContext::TraceFailure(v77, "CSocketRIO::InitializeRIO", 142, AsyncResult);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v12 = 22;
                goto LABEL_14;
              }
              goto LABEL_197;
            }
          }
          v71 = (unsigned int)(v71 + 1);
          if ( (unsigned int)v71 >= v81 )
            goto LABEL_200;
        }
        v78 = CallStackTracing::s_wpInstance;
        AsyncResult = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v78 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v78 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v78->m_fEnabled )
        {
          v79 = CallStackTracing::GetThreadRelativeContext(v78);
          if ( v79->m_result != -2147024882 )
            CallStackContext::TraceFailure(v79, "CSocketRIO::InitializeRIO", 137, -2147024882);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v35 = 21;
          goto LABEL_84;
        }
        goto LABEL_197;
      }
      v37 = (_QWORD *)((char *)this + 64);
    }
    else
    {
      v69 = 0;
    }
    v71 = 0;
    if ( !v69 )
      goto LABEL_200;
    goto LABEL_189;
  }
  v28 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v28 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v28 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v28->m_fEnabled )
  {
    v29 = CallStackTracing::GetThreadRelativeContext(v28);
    if ( v29->m_result != AsyncResult )
      CallStackContext::TraceFailure(v29, "CSocketRIO::InitializeRIO", 105, AsyncResult);
  }
  if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
    goto LABEL_197;
  v12 = 15;
LABEL_14:
  WPP_SF_qD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v12,
    WPP_aba7331d81f734ed0cdb9b63a6662b3c_Traceguids,
    this,
    AsyncResult);
LABEL_197:
  CSocketRIO::Close(this);
  if ( (unsigned int)dword_1801F81A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801F81A0, 0x400000000000LL) )
  {
    v82 = AsyncResult;
    v95 = &v82;
    v84 = 0x1000000;
    v93 = &v84;
    v96 = 4;
    v94 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_1801F81A0, word_1801E614A, 0, 0, 4, v92);
  }
LABEL_200:
  CallStackScopeTrace::~CallStackScopeTrace(&v80);
  return (unsigned int)AsyncResult;
}

```

## disassembly

```asm
0x1800a0f3c  push    rbp
0x1800a0f3e  push    rbx
0x1800a0f3f  push    rsi
0x1800a0f40  push    rdi
0x1800a0f41  push    r12
0x1800a0f43  push    r13
0x1800a0f45  push    r14
0x1800a0f47  push    r15
0x1800a0f49  lea     rbp, [rsp-8]
0x1800a0f4e  sub     rsp, 108h
0x1800a0f55  mov     rax, cs:__security_cookie
0x1800a0f5c  xor     rax, rsp
0x1800a0f5f  mov     [rbp+40h+var_50], rax
0x1800a0f63  mov     esi, r8d
0x1800a0f66  mov     rbx, rdx
0x1800a0f69  mov     r15, rcx
0x1800a0f6c  mov     [rsp+140h+var_EC], esi
0x1800a0f70  mov     r8d, 45h ; 'E'; int
0x1800a0f76  mov     dword ptr [rsp+140h+var_E8], r9d
0x1800a0f7b  lea     rdx, aCsocketrioInit; "CSocketRIO::InitializeRIO"
0x1800a0f82  mov     r12d, r9d
0x1800a0f85  lea     rcx, [rsp+140h+var_F0]; this
0x1800a0f8a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a0f8f  xor     r13d, r13d
0x1800a0f92  mov     [rbp+40h+vInBuffer], 8509E081h
0x1800a0f99  mov     [rsp+140h+lpCompletionRoutine], r13; lpCompletionRoutine
0x1800a0f9e  lea     rcx, [rsp+140h+var_E8+4]
0x1800a0fa3  mov     [rsp+140h+lpOverlapped], r13; lpOverlapped
0x1800a0fa8  lea     rax, [r15+0D8h]
0x1800a0faf  mov     [rsp+140h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x1800a0fb4  lea     r8, [rbp+40h+vInBuffer]; lpvInBuffer
0x1800a0fb8  mov     [rsp+140h+cbOutBuffer], 70h ; 'p'; cbOutBuffer
0x1800a0fc0  lea     r9d, [r13+10h]; cbInBuffer
0x1800a0fc4  mov     rcx, rbx; s
0x1800a0fc7  mov     [rsp+140h+lpvOutBuffer], rax; lpvOutBuffer
0x1800a0fcc  mov     edx, 0C8000024h; dwIoControlCode
0x1800a0fd1  mov     [rbp+40h+var_A4], 400596DDh
0x1800a0fd8  mov     [rbp+40h+var_A0], 2E9E65B1h
0x1800a0fdf  mov     [rbp+40h+var_9C], 3F9EC7E8h
0x1800a0fe6  mov     dword ptr [rsp+140h+var_E8+4], r13d
0x1800a0feb  call    cs:__imp_WSAIoctl
0x1800a0ff1  mov     edi, 80070000h
0x1800a0ff6  test    eax, eax
0x1800a0ff8  jz      loc_1800A10B0
0x1800a0ffe  call    cs:__imp_WSAGetLastError
0x1800a1004  mov     r14d, eax
0x1800a1007  test    eax, eax
0x1800a1009  jle     short loc_1800A1012
0x1800a100b  movzx   r14d, ax
0x1800a100f  or      r14d, edi
0x1800a1012  test    r14d, r14d
0x1800a1015  jns     loc_1800A10B0
0x1800a101b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1022  test    rcx, rcx
0x1800a1025  jnz     short loc_1800A1068
0x1800a1027  mov     rax, cs:stru_1801FC290.__vftable
0x1800a102e  lea     rdi, stru_1801FC290
0x1800a1035  mov     edx, 7F0h
0x1800a103a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1041  mov     rcx, rdi
0x1800a1044  mov     rax, [rax+8]
0x1800a1048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a104d  test    eax, eax
0x1800a104f  jnz     short loc_1800A1061
0x1800a1051  lea     rcx, stru_1801F8A30
0x1800a1058  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a105f  jmp     short loc_1800A1068
0x1800a1061  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a1068  cmp     [rcx+8], r13b
0x1800a106c  jz      short loc_1800A1094
0x1800a106e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1073  cmp     [rax+7CCh], r14d
0x1800a107a  jz      short loc_1800A1094
0x1800a107c  mov     r9d, r14d; int
0x1800a107f  lea     rdx, aCsocketrioInit; "CSocketRIO::InitializeRIO"
0x1800a1086  mov     r8d, 4Fh ; 'O'; int
0x1800a108c  mov     rcx, rax; this
0x1800a108f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1094  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a109b  jb      loc_1800A1B8C
0x1800a10a1  mov     edx, 0Ah
0x1800a10a6  mov     dword ptr [rsp+140h+lpvOutBuffer], r14d
0x1800a10ab  jmp     loc_1800A1583
0x1800a10b0  xor     r9d, r9d; lpName
0x1800a10b3  xor     r8d, r8d; bInitialState
0x1800a10b6  xor     edx, edx; bManualReset
0x1800a10b8  xor     ecx, ecx; lpEventAttributes
0x1800a10ba  call    cs:__imp_CreateEventW
0x1800a10c0  mov     [r15+18h], rax
0x1800a10c4  test    rax, rax
0x1800a10c7  jnz     loc_1800A117A
0x1800a10cd  call    cs:__imp_GetLastError
0x1800a10d3  mov     r14d, eax
0x1800a10d6  test    eax, eax
0x1800a10d8  jle     short loc_1800A10E1
0x1800a10da  movzx   r14d, ax
0x1800a10de  or      r14d, edi
0x1800a10e1  test    r14d, r14d
0x1800a10e4  jns     loc_1800A117A
0x1800a10ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a10f1  test    rcx, rcx
0x1800a10f4  jnz     short loc_1800A1137
0x1800a10f6  mov     rax, cs:stru_1801FC290.__vftable
0x1800a10fd  lea     rdi, stru_1801FC290
0x1800a1104  mov     edx, 7F0h
0x1800a1109  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1110  mov     rcx, rdi
0x1800a1113  mov     rax, [rax+8]
0x1800a1117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a111c  test    eax, eax
0x1800a111e  jnz     short loc_1800A1130
0x1800a1120  lea     rcx, stru_1801F8A30
0x1800a1127  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a112e  jmp     short loc_1800A1137
0x1800a1130  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a1137  cmp     [rcx+8], r13b
0x1800a113b  jz      short loc_1800A1163
0x1800a113d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1142  cmp     [rax+7CCh], r14d
0x1800a1149  jz      short loc_1800A1163
0x1800a114b  mov     r9d, r14d; int
0x1800a114e  lea     rdx, aCsocketrioInit; "CSocketRIO::InitializeRIO"
0x1800a1155  mov     r8d, 55h ; 'U'; int
0x1800a115b  mov     rcx, rax; this
0x1800a115e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1163  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a116a  jb      loc_1800A1B8C
0x1800a1170  mov     edx, 0Bh
0x1800a1175  jmp     loc_1800A10A6
0x1800a117a  lea     rdx, [r15+8]; callback
0x1800a117e  xor     r8d, r8d; appState
0x1800a1181  lea     r9, [r15+20h]; asyncResult
0x1800a1185  xor     ecx, ecx; appObject
0x1800a1187  call    cs:__imp_RtwqCreateAsyncResult
0x1800a118d  mov     r14d, eax
0x1800a1190  test    eax, eax
0x1800a1192  jns     loc_1800A1228
0x1800a1198  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a119f  test    rcx, rcx
0x1800a11a2  jnz     short loc_1800A11E5
0x1800a11a4  mov     rcx, cs:stru_1801FC290.__vftable
0x1800a11ab  lea     rdi, stru_1801FC290
0x1800a11b2  mov     edx, 7F0h
0x1800a11b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a11be  mov     rax, [rcx+8]
0x1800a11c2  mov     rcx, rdi
0x1800a11c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a11ca  test    eax, eax
0x1800a11cc  jnz     short loc_1800A11DE
0x1800a11ce  lea     rcx, stru_1801F8A30
0x1800a11d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a11dc  jmp     short loc_1800A11E5
0x1800a11de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a11e5  cmp     [rcx+8], r13b
0x1800a11e9  jz      short loc_1800A1211
0x1800a11eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a11f0  cmp     [rax+7CCh], r14d
0x1800a11f7  jz      short loc_1800A1211
0x1800a11f9  mov     r9d, r14d; int
0x1800a11fc  lea     rdx, aCsocketrioInit; "CSocketRIO::InitializeRIO"
0x1800a1203  mov     r8d, 58h ; 'X'; int
0x1800a1209  mov     rcx, rax; this
0x1800a120c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1211  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a1218  jb      loc_1800A1B8C
0x1800a121e  mov     edx, 0Ch
0x1800a1223  jmp     loc_1800A10A6
0x1800a1228  mov     r8, [r15+20h]; result
0x1800a122c  lea     r9, [r15+28h]; key
0x1800a1230  mov     rcx, [r15+18h]; hEvent
0x1800a1234  xor     edx, edx; lPriority
0x1800a1236  call    cs:__imp_RtwqPutWaitingWorkItem
0x1800a123c  mov     r14d, eax
0x1800a123f  test    eax, eax
0x1800a1241  jns     loc_1800A12D7
0x1800a1247  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a124e  test    rcx, rcx
0x1800a1251  jnz     short loc_1800A1294
0x1800a1253  mov     rax, cs:stru_1801FC290.__vftable
0x1800a125a  lea     rdi, stru_1801FC290
0x1800a1261  mov     edx, 7F0h
0x1800a1266  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a126d  mov     rcx, rdi
0x1800a1270  mov     rax, [rax+8]
0x1800a1274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1279  test    eax, eax
0x1800a127b  jnz     short loc_1800A128D
0x1800a127d  lea     rcx, stru_1801F8A30
0x1800a1284  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a128b  jmp     short loc_1800A1294
0x1800a128d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a1294  cmp     [rcx+8], r13b
0x1800a1298  jz      short loc_1800A12C0
0x1800a129a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a129f  cmp     [rax+7CCh], r14d
0x1800a12a6  jz      short loc_1800A12C0
0x1800a12a8  mov     r9d, r14d; int
0x1800a12ab  lea     rdx, aCsocketrioInit; "CSocketRIO::InitializeRIO"
0x1800a12b2  mov     r8d, 59h ; 'Y'; int
0x1800a12b8  mov     rcx, rax; this
0x1800a12bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a12c0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a12c7  jb      loc_1800A1B8C
0x1800a12cd  mov     edx, 0Dh
0x1800a12d2  jmp     loc_1800A10A6
0x1800a12d7  mov     rax, [r15+18h]
0x1800a12db  lea     rdx, [rsp+140h+var_C8]
0x1800a12e0  mov     [rbp+40h+var_C0], rax
0x1800a12e4  mov     ecx, 191h
0x1800a12e9  mov     rax, [r15+108h]
0x1800a12f0  mov     [rsp+140h+var_C8], 1
0x1800a12f9  mov     [rbp+40h+var_B4], r13
0x1800a12fd  mov     [rbp+40h+var_AC], r13d
0x1800a1301  mov     [rbp+40h+var_B8], r13d
0x1800a1305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a130a  mov     [r15+30h], rax
0x1800a130e  test    rax, rax
0x1800a1311  jnz     loc_1800A13C4
0x1800a1317  call    cs:__imp_WSAGetLastError
0x1800a131d  mov     r14d, eax
0x1800a1320  test    eax, eax
0x1800a1322  jle     short loc_1800A132B
0x1800a1324  movzx   r14d, ax
0x1800a1328  or      r14d, edi
0x1800a132b  test    r14d, r14d
0x1800a132e  jns     loc_1800A13C4
0x1800a1334  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a133b  test    rcx, rcx
0x1800a133e  jnz     short loc_1800A1381
0x1800a1340  mov     rax, cs:stru_1801FC290.__vftable
0x1800a1347  lea     rdi, stru_1801FC290
0x1800a134e  mov     edx, 7F0h
0x1800a1353  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a135a  mov     rcx, rdi
0x1800a135d  mov     rax, [rax+8]
0x1800a1361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1366  test    eax, eax
0x1800a1368  jnz     short loc_1800A137A
0x1800a136a  lea     rcx, stru_1801F8A30
0x1800a1371  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1378  jmp     short loc_1800A1381
0x1800a137a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a1381  cmp     [rcx+8], r13b
0x1800a1385  jz      short loc_1800A13AD
0x1800a1387  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a138c  cmp     [rax+7CCh], r14d
0x1800a1393  jz      short loc_1800A13AD
0x1800a1395  mov     r9d, r14d; int
0x1800a1398  lea     rdx, aCsocketrioInit; "CSocketRIO::InitializeRIO"
0x1800a139f  mov     r8d, 63h ; 'c'; int
0x1800a13a5  mov     rcx, rax; this
0x1800a13a8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a13ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a13b4  jb      loc_1800A1B8C
0x1800a13ba  mov     edx, 0Eh
0x1800a13bf  jmp     loc_1800A10A6
0x1800a13c4  mov     rcx, [r15+30h]
0x1800a13c8  mov     edx, 0C8h
0x1800a13cd  mov     rax, [r15+110h]
0x1800a13d4  mov     r8d, 1
0x1800a13da  mov     [rsp+140h+lpOverlapped], r13
0x1800a13df  mov     [rsp+140h+lpcbBytesReturned], rcx
0x1800a13e4  mov     qword ptr [rsp+140h+cbOutBuffer], rcx
0x1800a13e9  lea     r9d, [rdx+1]
0x1800a13ed  mov     rcx, rbx
0x1800a13f0  mov     dword ptr [rsp+140h+lpvOutBuffer], 1
0x1800a13f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a13fd  mov     [r15+38h], rax
0x1800a1401  test    rax, rax
0x1800a1404  jnz     loc_1800A14B7
0x1800a140a  call    cs:__imp_WSAGetLastError
0x1800a1410  mov     r14d, eax
0x1800a1413  test    eax, eax
0x1800a1415  jle     short loc_1800A141E
0x1800a1417  movzx   r14d, ax
0x1800a141b  or      r14d, edi
0x1800a141e  test    r14d, r14d
0x1800a1421  jns     loc_1800A14B7
0x1800a1427  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a142e  test    rcx, rcx
0x1800a1431  jnz     short loc_1800A1474
0x1800a1433  mov     rax, cs:stru_1801FC290.__vftable
0x1800a143a  lea     rdi, stru_1801FC290
0x1800a1441  mov     edx, 7F0h
0x1800a1446  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a144d  mov     rcx, rdi
0x1800a1450  mov     rax, [rax+8]
0x1800a1454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1459  test    eax, eax
0x1800a145b  jnz     short loc_1800A146D
0x1800a145d  lea     rcx, stru_1801F8A30
0x1800a1464  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a146b  jmp     short loc_1800A1474
0x1800a146d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a1474  cmp     [rcx+8], r13b
0x1800a1478  jz      short loc_1800A14A0
0x1800a147a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a147f  cmp     [rax+7CCh], r14d
0x1800a1486  jz      short loc_1800A14A0
0x1800a1488  mov     r9d, r14d; int
  ... truncated ...
```
