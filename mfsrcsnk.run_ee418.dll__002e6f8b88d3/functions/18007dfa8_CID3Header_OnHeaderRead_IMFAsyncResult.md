# CID3Header::OnHeaderRead(IMFAsyncResult *)

- ea: `0x18007dfa8`
- end: `0x18007e7e7`
- name: `?OnHeaderRead@CID3Header@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `2111`
- prototype: `void __fastcall(CID3Header *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180169df0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18002c030`
- `0x18002e708`
- `0x180034d10`
- `0x18003f85c`
- `0x180041f68`
- `0x180073b14`
- `0x180073b64`
- `0x18007dfa8`
- `0x1800e5510`
- `0x1801099f0`
- `0x180115a1c`
- `0x18016978c`
- `0x1801699d8`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e788`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e77a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e77a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007e7b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007e7b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e7aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e7aa`
- `MFPlat!MFPutWorkItemEx2` at `0x18007e762`
- `MFPlat!MFPutWorkItemEx2` at `0x18007e762`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e019`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e100`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e1e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e2c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e369`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e427`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e4e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e596`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e67e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e019`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e100`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e1e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e2c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e369`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e427`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e4e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e596`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e67e`

## string_xrefs

- `0x18007dfd0`: `CID3Header::OnHeaderRead`
- `0x18007e23e`: `CID3Header::OnHeaderRead`
- `0x18007e317`: `CID3Header::OnHeaderRead`
- `0x18007e3c0`: `CID3Header::OnHeaderRead`
- `0x18007e47e`: `CID3Header::OnHeaderRead`
- `0x18007e53a`: `CID3Header::OnHeaderRead`
- `0x18007e5ed`: `CID3Header::OnHeaderRead`
- `0x18007e6d5`: `CID3Header::OnHeaderRead`

## pseudocode

```c
void __fastcall CID3Header::OnHeaderRead(CID3Header *this, struct IMFAsyncResult *a2)
{
  CByteStreamCacheReaderEx *v4; // rcx
  __int64 v5; // rdx
  int Buffer; // edi
  __int64 v7; // r8
  size_t v8; // r9
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  DWORD v12; // esi
  __int64 v13; // rdx
  CCacheReaderBufferList *v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  bool v21; // cf
  int v22; // eax
  unsigned __int8 *v23; // r12
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  unsigned int *v43; // r13
  __int64 v44; // rdx
  __int64 v45; // r8
  struct IUnknown *v46; // r9
  wchar_t *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  CByteStreamCacheReaderEx *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r9
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 v69; // rbx
  __int64 v70; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v73; // sf
  CCacheReaderBufferList *v74; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v75[2]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int8 v76[4]; // [rsp+48h] [rbp-18h] BYREF
  int v77; // [rsp+4Ch] [rbp-14h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v76, "CID3Header::OnHeaderRead", 701);
  v4 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 5);
  v74 = 0;
  Buffer = CByteStreamCacheReaderEx::EndRead(v4, a2, &v74);
  if ( Buffer < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Buffer )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Header::OnHeaderRead", 707, Buffer);
    }
    v12 = 1;
    if ( !g_wppLevels )
      goto LABEL_119;
    v13 = 54;
    goto LABEL_118;
  }
  if ( g_wppLevels >= 0x10u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
  v14 = v74;
  v75[0] = 3;
  v75[1] = (unsigned __int64)&v77;
  Buffer = CCacheReaderBufferList::GetBuffer(v74, (const struct MFBUFFER::CBuffer *)v75, v7, v8);
  if ( Buffer < 0 )
  {
    v18 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != Buffer )
        CallStackContext::TraceFailure(v20, "CID3Header::OnHeaderRead", 716, Buffer);
    }
    v12 = 1;
    if ( !g_wppLevels )
      goto LABEL_119;
    v13 = 56;
    goto LABEL_118;
  }
  v12 = 1;
  v21 = (unsigned __int8)v77 < (unsigned __int8)s_szID3v2HeaderTag;
  if ( (_BYTE)v77 == (_BYTE)s_szID3v2HeaderTag
    && (v21 = BYTE1(v77) < 0x44u, BYTE1(v77) == 68)
    && (v21 = BYTE2(v77) < 0x33u, BYTE2(v77) == 51) )
  {
    v22 = 0;
  }
  else
  {
    v22 = v21 ? -1 : 1;
  }
  if ( !v22 )
  {
    v23 = (unsigned __int8 *)this + 520;
    Buffer = CCacheReaderBufferList::GetBYTE(v14, (unsigned __int8 *)this + 520);
    if ( Buffer < 0 )
    {
      v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != Buffer )
          CallStackContext::TraceFailure(v29, "CID3Header::OnHeaderRead", 725, Buffer);
      }
      if ( !g_wppLevels )
        goto LABEL_119;
      v13 = 57;
      goto LABEL_118;
    }
    if ( *v23 < 2u )
    {
      if ( g_wppLevels < 4u )
        goto LABEL_31;
      v30 = 58;
LABEL_46:
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
      goto LABEL_31;
    }
    Buffer = CCacheReaderBufferList::GetBYTE(v14, (unsigned __int8 *)this + 521);
    if ( Buffer >= 0 )
    {
      v76[0] = 0;
      Buffer = CCacheReaderBufferList::GetBYTE(v14, v76);
      if ( Buffer >= 0 )
      {
        CID3Header::DecodeFlags(this, *v23, v76[0]);
        v43 = (unsigned int *)((char *)this + 532);
        Buffer = CId3SyncSafe::GetDWORD(v14, (unsigned int *)this + 133);
        if ( Buffer >= 0 )
        {
          if ( *v23 <= 4u )
          {
            if ( g_wppLevels >= 0x10u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
            Buffer = CByteStreamCacheReaderEx::BeginRead(
                       *((CByteStreamCacheReaderEx **)this + 5),
                       *v43,
                       (struct IMFAsyncCallback *)this + 64,
                       v46);
            if ( Buffer >= 0 )
              goto LABEL_119;
            v66 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64, v65);
              CallStackTracing::s_wpInstance = v67;
              if ( v67
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
              {
                v66 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v66 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v66 + 8) )
            {
              v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
              if ( *((_DWORD *)v68 + 499) != Buffer )
                CallStackContext::TraceFailure(v68, "CID3Header::OnHeaderRead", 772, Buffer);
            }
            if ( !g_wppLevels )
              goto LABEL_119;
            v13 = 66;
          }
          else
          {
            v50 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 5);
            v75[0] = 0;
            Buffer = CByteStreamCacheReaderEx::GetCurrentPosition(v50, v75);
            if ( Buffer >= 0 )
            {
              Buffer = CByteStreamCacheReaderEx::SetCurrentPosition(
                         *((CByteStreamCacheReaderEx **)this + 5),
                         *v43 + v75[0] - 1);
              if ( Buffer >= 0 )
              {
                if ( g_wppLevels < 4u )
                  goto LABEL_31;
                v30 = 64;
                goto LABEL_46;
              }
              v60 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58, v59);
                CallStackTracing::s_wpInstance = v61;
                if ( v61
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
                {
                  v60 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v60 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v60 + 8) )
              {
                v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
                if ( *((_DWORD *)v62 + 499) != Buffer )
                  CallStackContext::TraceFailure(v62, "CID3Header::OnHeaderRead", 756, Buffer);
              }
              if ( !g_wppLevels )
                goto LABEL_119;
              v13 = 63;
            }
            else
            {
              v54 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
                CallStackTracing::s_wpInstance = v55;
                if ( v55
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
                {
                  v54 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v54 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v54 + 8) )
              {
                v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
                if ( *((_DWORD *)v56 + 499) != Buffer )
                  CallStackContext::TraceFailure(v56, "CID3Header::OnHeaderRead", 755, Buffer);
              }
              if ( !g_wppLevels )
                goto LABEL_119;
              v13 = 62;
            }
          }
        }
        else
        {
          v47 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45, v46);
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
            v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
            if ( *((_DWORD *)v49 + 499) != Buffer )
              CallStackContext::TraceFailure(v49, "CID3Header::OnHeaderRead", 747, Buffer);
          }
          if ( !g_wppLevels )
            goto LABEL_119;
          v13 = 61;
        }
      }
      else
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
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
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != Buffer )
            CallStackContext::TraceFailure(v42, "CID3Header::OnHeaderRead", 741, Buffer);
        }
        if ( !g_wppLevels )
          goto LABEL_119;
        v13 = 60;
      }
    }
    else
    {
      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
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
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != Buffer )
          CallStackContext::TraceFailure(v36, "CID3Header::OnHeaderRead", 736, Buffer);
      }
      if ( !g_wppLevels )
        goto LABEL_119;
      v13 = 59;
    }
LABEL_118:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_37a327c391a7379b3721a372142db134_Traceguids, this, Buffer);
    goto LABEL_119;
  }
LABEL_31:
  Buffer = -1072873850;
LABEL_119:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v74);
  if ( Buffer >= 0 )
    goto LABEL_134;
  v69 = *((_QWORD *)this + 6);
  v70 = *(_QWORD *)(v69 + 40);
  *(_DWORD *)(v69 + 48) = Buffer;
  if ( v70 )
  {
    LODWORD(v74) = 0;
    v77 = 0;
    if ( (*(int (__fastcall **)(__int64, CCacheReaderBufferList **, int *))(*(_QWORD *)v70 + 24LL))(v70, &v74, &v77) >= 0 )
      v12 = v77;
    else
      v77 = 1;
    MFPutWorkItemEx2(v12, 0, (IMFAsyncResult *)v69);
    goto LABEL_134;
  }
  if ( *(_QWORD *)(v69 + 56) )
    goto LABEL_133;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v69 + 56), (signed __int64)EventW, 0) )
      CloseHandle(EventW);
    goto LABEL_133;
  }
  LastError = GetLastError();
  v73 = LastError < 0;
  if ( LastError > 0 )
    v73 = 1;
  if ( !v73 )
LABEL_133:
    SetEvent(*(HANDLE *)(v69 + 56));
LABEL_134:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v76);
}

```

## disassembly

```asm
0x18007dfa8  mov     [rsp-38h+arg_10], rbx
0x18007dfad  push    rbp
0x18007dfae  push    rsi
0x18007dfaf  push    rdi
0x18007dfb0  push    r12
0x18007dfb2  push    r13
0x18007dfb4  push    r14
0x18007dfb6  push    r15
0x18007dfb8  mov     rbp, rsp
0x18007dfbb  sub     rsp, 60h
0x18007dfbf  mov     rax, cs:__security_cookie
0x18007dfc6  xor     rax, rsp
0x18007dfc9  mov     [rbp+var_10], rax
0x18007dfcd  mov     rbx, rdx
0x18007dfd0  lea     rsi, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x18007dfd7  mov     r14, rcx
0x18007dfda  mov     rdx, rsi; char *
0x18007dfdd  mov     r8d, 2BDh; int
0x18007dfe3  lea     rcx, [rbp+var_18]; this
0x18007dfe7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007dfec  mov     rcx, [r14+28h]; this
0x18007dff0  lea     r8, [rbp+var_30]; struct CCacheReaderBufferList **
0x18007dff4  xor     r13d, r13d
0x18007dff7  mov     rdx, rbx; struct IMFAsyncResult *
0x18007dffa  mov     [rbp+var_30], r13
0x18007dffe  call    ?EndRead@CByteStreamCacheReaderEx@@QEAAJPEAUIMFAsyncResult@@PEAPEAVCCacheReaderBufferList@@@Z; CByteStreamCacheReaderEx::EndRead(IMFAsyncResult *,CCacheReaderBufferList * *)
0x18007e003  mov     edi, eax
0x18007e005  test    eax, eax
0x18007e007  jns     loc_18007E0A2
0x18007e00d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e014  test    rcx, rcx
0x18007e017  jnz     short loc_18007E05A
0x18007e019  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e01f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e026  mov     rcx, rax
0x18007e029  test    rax, rax
0x18007e02c  jz      short loc_18007E04C
0x18007e02e  mov     rax, [rax]
0x18007e031  mov     edx, 7F0h
0x18007e036  mov     rax, [rax+8]
0x18007e03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e03f  test    eax, eax
0x18007e041  jz      short loc_18007E04C
0x18007e043  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e04a  jmp     short loc_18007E05A
0x18007e04c  lea     rcx, qword_1801B07E0; this
0x18007e053  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e05a  cmp     [rcx+8], r13b
0x18007e05e  jz      short loc_18007E081
0x18007e060  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e065  cmp     [rax+7CCh], edi
0x18007e06b  jz      short loc_18007E081
0x18007e06d  mov     r9d, edi; int
0x18007e070  mov     r8d, 2C3h; int
0x18007e076  mov     rdx, rsi; char *
0x18007e079  mov     rcx, rax; this
0x18007e07c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007e081  mov     esi, 1
0x18007e086  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18007e08d  jb      loc_18007E712
0x18007e093  lea     edx, [rsi+35h]
0x18007e096  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x18007e09d  jmp     loc_18007E6FB
0x18007e0a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x18007e0a9  lea     r15, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x18007e0b0  jb      short loc_18007E0CA
0x18007e0b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e0b9  mov     edx, 37h ; '7'
0x18007e0be  mov     r8, r15
0x18007e0c1  mov     rcx, [rcx+10h]
0x18007e0c5  call    WPP_SF_
0x18007e0ca  mov     rbx, [rbp+var_30]
0x18007e0ce  lea     rax, [rbp+var_14]
0x18007e0d2  mov     rcx, rbx; this
0x18007e0d5  mov     [rbp+var_28], 3
0x18007e0dd  lea     rdx, [rbp+var_28]; struct MFBUFFER::CBuffer *
0x18007e0e1  mov     [rbp+var_20], rax
0x18007e0e5  call    ?GetBuffer@CCacheReaderBufferList@@QEAAJAEBVCBuffer@MFBUFFER@@@Z; CCacheReaderBufferList::GetBuffer(MFBUFFER::CBuffer const &)
0x18007e0ea  mov     edi, eax
0x18007e0ec  test    eax, eax
0x18007e0ee  jns     loc_18007E182
0x18007e0f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e0fb  test    rcx, rcx
0x18007e0fe  jnz     short loc_18007E141
0x18007e100  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e106  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e10d  mov     rcx, rax
0x18007e110  test    rax, rax
0x18007e113  jz      short loc_18007E133
0x18007e115  mov     rax, [rax]
0x18007e118  mov     edx, 7F0h
0x18007e11d  mov     rax, [rax+8]
0x18007e121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e126  test    eax, eax
0x18007e128  jz      short loc_18007E133
0x18007e12a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e131  jmp     short loc_18007E141
0x18007e133  lea     rcx, qword_1801B07E0; this
0x18007e13a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e141  cmp     [rcx+8], r13b
0x18007e145  jz      short loc_18007E168
0x18007e147  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e14c  cmp     [rax+7CCh], edi
0x18007e152  jz      short loc_18007E168
0x18007e154  mov     r9d, edi; int
0x18007e157  mov     r8d, 2CCh; int
0x18007e15d  mov     rdx, rsi; char *
0x18007e160  mov     rcx, rax; this
0x18007e163  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007e168  mov     esi, 1
0x18007e16d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18007e174  jb      loc_18007E712
0x18007e17a  lea     edx, [rsi+37h]
0x18007e17d  jmp     loc_18007E6F8
0x18007e182  mov     al, byte ptr [rbp+var_14]
0x18007e185  mov     esi, 1
0x18007e18a  cmp     al, cs:?s_szID3v2HeaderTag@@3QBDB; char const near * const s_szID3v2HeaderTag
0x18007e190  jnz     short loc_18007E1AD
0x18007e192  mov     al, byte ptr [rbp+var_14+1]
0x18007e195  cmp     al, cs:byte_180183FFD
0x18007e19b  jnz     short loc_18007E1AD
0x18007e19d  mov     al, byte ptr [rbp+var_14+2]
0x18007e1a0  cmp     al, cs:byte_180183FFE
0x18007e1a6  jnz     short loc_18007E1AD
0x18007e1a8  mov     eax, r13d
0x18007e1ab  jmp     short loc_18007E1B1
0x18007e1ad  sbb     eax, eax
0x18007e1af  or      eax, esi
0x18007e1b1  test    eax, eax
0x18007e1b3  jz      short loc_18007E1BF
0x18007e1b5  mov     edi, 0C00D3E86h
0x18007e1ba  jmp     loc_18007E712
0x18007e1bf  lea     r12, [r14+208h]
0x18007e1c6  mov     rcx, rbx; this
0x18007e1c9  mov     rdx, r12; unsigned __int8 *
0x18007e1cc  call    ?GetBYTE@CCacheReaderBufferList@@QEAAJPEAE@Z; CCacheReaderBufferList::GetBYTE(uchar *)
0x18007e1d1  mov     edi, eax
0x18007e1d3  test    eax, eax
0x18007e1d5  jns     loc_18007E26A
0x18007e1db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e1e2  test    rcx, rcx
0x18007e1e5  jnz     short loc_18007E228
0x18007e1e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e1ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e1f4  mov     rcx, rax
0x18007e1f7  test    rax, rax
0x18007e1fa  jz      short loc_18007E21A
0x18007e1fc  mov     rax, [rax]
0x18007e1ff  mov     edx, 7F0h
0x18007e204  mov     rax, [rax+8]
0x18007e208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e20d  test    eax, eax
0x18007e20f  jz      short loc_18007E21A
0x18007e211  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e218  jmp     short loc_18007E228
0x18007e21a  lea     rcx, qword_1801B07E0; this
0x18007e221  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e228  cmp     [rcx+8], r13b
0x18007e22c  jz      short loc_18007E253
0x18007e22e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e233  cmp     [rax+7CCh], edi
0x18007e239  jz      short loc_18007E253
0x18007e23b  mov     r9d, edi; int
0x18007e23e  lea     rdx, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x18007e245  mov     r8d, 2D5h; int
0x18007e24b  mov     rcx, rax; this
0x18007e24e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007e253  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18007e25a  jb      loc_18007E712
0x18007e260  mov     edx, 39h ; '9'
0x18007e265  jmp     loc_18007E6F8
0x18007e26a  cmp     byte ptr [r12], 2
0x18007e26f  jnb     short loc_18007E29B
0x18007e271  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x18007e278  jb      loc_18007E1B5
0x18007e27e  mov     edx, 3Ah ; ':'
0x18007e283  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e28a  mov     r8, r15
0x18007e28d  mov     rcx, [rcx+10h]
0x18007e291  call    WPP_SF_
0x18007e296  jmp     loc_18007E1B5
0x18007e29b  lea     rdx, [r14+209h]; unsigned __int8 *
0x18007e2a2  mov     rcx, rbx; this
0x18007e2a5  call    ?GetBYTE@CCacheReaderBufferList@@QEAAJPEAE@Z; CCacheReaderBufferList::GetBYTE(uchar *)
0x18007e2aa  mov     edi, eax
0x18007e2ac  test    eax, eax
0x18007e2ae  jns     loc_18007E343
0x18007e2b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e2bb  test    rcx, rcx
0x18007e2be  jnz     short loc_18007E301
0x18007e2c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e2c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e2cd  mov     rcx, rax
0x18007e2d0  test    rax, rax
0x18007e2d3  jz      short loc_18007E2F3
0x18007e2d5  mov     rax, [rax]
0x18007e2d8  mov     edx, 7F0h
0x18007e2dd  mov     rax, [rax+8]
0x18007e2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e2e6  test    eax, eax
0x18007e2e8  jz      short loc_18007E2F3
0x18007e2ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e2f1  jmp     short loc_18007E301
0x18007e2f3  lea     rcx, qword_1801B07E0; this
0x18007e2fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e301  cmp     [rcx+8], r13b
0x18007e305  jz      short loc_18007E32C
0x18007e307  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e30c  cmp     [rax+7CCh], edi
0x18007e312  jz      short loc_18007E32C
0x18007e314  mov     r9d, edi; int
0x18007e317  lea     rdx, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x18007e31e  mov     r8d, 2E0h; int
0x18007e324  mov     rcx, rax; this
0x18007e327  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007e32c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18007e333  jb      loc_18007E712
0x18007e339  mov     edx, 3Bh ; ';'
0x18007e33e  jmp     loc_18007E6F8
0x18007e343  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x18007e347  mov     [rbp+var_18], r13b
0x18007e34b  mov     rcx, rbx; this
0x18007e34e  call    ?GetBYTE@CCacheReaderBufferList@@QEAAJPEAE@Z; CCacheReaderBufferList::GetBYTE(uchar *)
0x18007e353  mov     edi, eax
0x18007e355  test    eax, eax
0x18007e357  jns     loc_18007E3EC
0x18007e35d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e364  test    rcx, rcx
0x18007e367  jnz     short loc_18007E3AA
0x18007e369  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e36f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e376  mov     rcx, rax
0x18007e379  test    rax, rax
0x18007e37c  jz      short loc_18007E39C
0x18007e37e  mov     rax, [rax]
0x18007e381  mov     edx, 7F0h
0x18007e386  mov     rax, [rax+8]
0x18007e38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e38f  test    eax, eax
0x18007e391  jz      short loc_18007E39C
0x18007e393  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e39a  jmp     short loc_18007E3AA
0x18007e39c  lea     rcx, qword_1801B07E0; this
0x18007e3a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e3aa  cmp     [rcx+8], r13b
0x18007e3ae  jz      short loc_18007E3D5
0x18007e3b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e3b5  cmp     [rax+7CCh], edi
0x18007e3bb  jz      short loc_18007E3D5
0x18007e3bd  mov     r9d, edi; int
0x18007e3c0  lea     rdx, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x18007e3c7  mov     r8d, 2E5h; int
0x18007e3cd  mov     rcx, rax; this
0x18007e3d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007e3d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18007e3dc  jb      loc_18007E712
0x18007e3e2  mov     edx, 3Ch ; '<'
0x18007e3e7  jmp     loc_18007E6F8
0x18007e3ec  mov     r8b, [rbp+var_18]; unsigned __int8
0x18007e3f0  mov     rcx, r14; this
0x18007e3f3  mov     dl, [r12]; unsigned __int8
0x18007e3f7  call    ?DecodeFlags@CID3Header@@IEAAJEE@Z; CID3Header::DecodeFlags(uchar,uchar)
0x18007e3fc  lea     r13, [r14+214h]
0x18007e403  mov     rcx, rbx; this
0x18007e406  mov     rdx, r13; unsigned int *
0x18007e409  call    ?GetDWORD@CId3SyncSafe@@SAJPEAVCCacheReaderBufferList@@PEAK@Z; CId3SyncSafe::GetDWORD(CCacheReaderBufferList *,ulong *)
0x18007e40e  mov     edi, eax
0x18007e410  test    eax, eax
0x18007e412  jns     loc_18007E4AA
0x18007e418  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e41f  xor     r13d, r13d
0x18007e422  test    rcx, rcx
0x18007e425  jnz     short loc_18007E468
0x18007e427  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e42d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e434  mov     rcx, rax
0x18007e437  test    rax, rax
0x18007e43a  jz      short loc_18007E45A
0x18007e43c  mov     rax, [rax]
0x18007e43f  mov     edx, 7F0h
0x18007e444  mov     rax, [rax+8]
0x18007e448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e44d  test    eax, eax
0x18007e44f  jz      short loc_18007E45A
0x18007e451  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e458  jmp     short loc_18007E468
0x18007e45a  lea     rcx, qword_1801B07E0; this
0x18007e461  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e468  cmp     [rcx+8], r13b
0x18007e46c  jz      short loc_18007E493
0x18007e46e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e473  cmp     [rax+7CCh], edi
0x18007e479  jz      short loc_18007E493
0x18007e47b  mov     r9d, edi; int
0x18007e47e  lea     rdx, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x18007e485  mov     r8d, 2EBh; int
0x18007e48b  mov     rcx, rax; this
0x18007e48e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007e493  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18007e49a  jb      loc_18007E712
  ... truncated ...
```
