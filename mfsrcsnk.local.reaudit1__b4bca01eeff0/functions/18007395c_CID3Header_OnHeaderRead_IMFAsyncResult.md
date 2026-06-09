# CID3Header::OnHeaderRead(IMFAsyncResult *)

- ea: `0x18007395c`
- end: `0x18007418c`
- name: `?OnHeaderRead@CID3Header@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `2096`
- prototype: `void __fastcall(CID3Header *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180172e00`

## callees

- `0x180005cf4`
- `0x1800177b4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x18001edd0`
- `0x180024890`
- `0x180036c30`
- `0x180041414`
- `0x180043c84`
- `0x18007395c`
- `0x180074194`
- `0x180079680`
- `0x1800796d4`
- `0x1800ebe54`
- `0x180110ed0`
- `0x18011cbac`
- `0x18017277c`
- `0x1801729e0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFPutWorkItemEx2` at `0x180074148`
- `MFPlat!MFPutWorkItemEx2` at `0x180074148`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800739cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073aba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073ba7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073c86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073d35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073df9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073ebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073f74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074062`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800739cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073aba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073ba7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073c86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073d35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073df9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073ebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180073f74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180074062`

## string_xrefs

- `0x180073984`: `CID3Header::OnHeaderRead`
- `0x180073c04`: `CID3Header::OnHeaderRead`
- `0x180073ce3`: `CID3Header::OnHeaderRead`
- `0x180073d92`: `CID3Header::OnHeaderRead`
- `0x180073e56`: `CID3Header::OnHeaderRead`
- `0x180073f18`: `CID3Header::OnHeaderRead`
- `0x180073fd1`: `CID3Header::OnHeaderRead`
- `0x1800740bf`: `CID3Header::OnHeaderRead`

## pseudocode

```c
void __fastcall CID3Header::OnHeaderRead(CID3Header *this, struct IMFAsyncResult *a2)
{
  CByteStreamCacheReaderEx *v4; // rcx
  __int64 v5; // rdx
  int Buffer; // edi
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  DWORD v10; // esi
  __int64 v11; // rdx
  CCacheReaderBufferList *v12; // rbx
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  bool v17; // cf
  int v18; // eax
  unsigned __int8 *v19; // r12
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned int *v33; // r13
  __int64 v34; // rdx
  struct IUnknown *v35; // r9
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  CByteStreamCacheReaderEx *v39; // rcx
  __int64 v40; // rdx
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  struct tagMFASYNCRESULT *v52; // rbx
  IMFAsyncCallback *pCallback; // rcx
  CCacheReaderBufferList *v54; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v55[2]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int8 v56[4]; // [rsp+48h] [rbp-18h] BYREF
  int v57; // [rsp+4Ch] [rbp-14h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v56, "CID3Header::OnHeaderRead", 701);
  v4 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 5);
  v54 = 0;
  Buffer = CByteStreamCacheReaderEx::EndRead(v4, a2, &v54);
  if ( Buffer < 0 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != Buffer )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Header::OnHeaderRead", 707, Buffer);
    }
    v10 = 1;
    if ( g_wppLevels )
    {
      v11 = 54;
LABEL_118:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_37a327c391a7379b3721a372142db134_Traceguids,
        this,
        Buffer);
      goto LABEL_119;
    }
    goto LABEL_119;
  }
  if ( g_wppLevels >= 0x10u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
  v12 = v54;
  v55[0] = 3;
  v55[1] = (unsigned __int64)&v57;
  Buffer = CCacheReaderBufferList::GetBuffer(v54, (const struct MFBUFFER::CBuffer *)v55);
  if ( Buffer >= 0 )
  {
    v10 = 1;
    v17 = (unsigned __int8)v57 < (unsigned __int8)s_szID3v2HeaderTag;
    if ( (_BYTE)v57 == (_BYTE)s_szID3v2HeaderTag
      && (v17 = BYTE1(v57) < 0x44u, BYTE1(v57) == 68)
      && (v17 = BYTE2(v57) < 0x33u, BYTE2(v57) == 51) )
    {
      v18 = 0;
    }
    else
    {
      v18 = v17 ? -1 : 1;
    }
    if ( v18 )
      goto LABEL_31;
    v19 = (unsigned __int8 *)this + 520;
    Buffer = CCacheReaderBufferList::GetBYTE(v12, (unsigned __int8 *)this + 520);
    if ( Buffer < 0 )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
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
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != Buffer )
          CallStackContext::TraceFailure(v23, "CID3Header::OnHeaderRead", 725, Buffer);
      }
      if ( g_wppLevels )
      {
        v11 = 57;
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    if ( *v19 >= 2u )
    {
      Buffer = CCacheReaderBufferList::GetBYTE(v12, (unsigned __int8 *)this + 521);
      if ( Buffer < 0 )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v26 + 8) )
        {
          v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
          if ( *((_DWORD *)v28 + 499) != Buffer )
            CallStackContext::TraceFailure(v28, "CID3Header::OnHeaderRead", 736, Buffer);
        }
        if ( g_wppLevels )
        {
          v11 = 59;
          goto LABEL_118;
        }
        goto LABEL_119;
      }
      v56[0] = 0;
      Buffer = CCacheReaderBufferList::GetBYTE(v12, v56);
      if ( Buffer < 0 )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != Buffer )
            CallStackContext::TraceFailure(v32, "CID3Header::OnHeaderRead", 741, Buffer);
        }
        if ( g_wppLevels )
        {
          v11 = 60;
          goto LABEL_118;
        }
        goto LABEL_119;
      }
      CID3Header::DecodeFlags(this, *v19, v56[0]);
      v33 = (unsigned int *)((char *)this + 532);
      Buffer = CId3SyncSafe::GetDWORD(v12, (unsigned int *)this + 133);
      if ( Buffer < 0 )
      {
        v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
          if ( *((_DWORD *)v38 + 499) != Buffer )
            CallStackContext::TraceFailure(v38, "CID3Header::OnHeaderRead", 747, Buffer);
        }
        if ( g_wppLevels )
        {
          v11 = 61;
          goto LABEL_118;
        }
        goto LABEL_119;
      }
      if ( *v19 <= 4u )
      {
        if ( g_wppLevels >= 0x10u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
        Buffer = CByteStreamCacheReaderEx::BeginRead(
                   *((CByteStreamCacheReaderEx **)this + 5),
                   *v33,
                   (struct IMFAsyncCallback *)this + 64,
                   v35);
        if ( Buffer < 0 )
        {
          v49 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
            CallStackTracing::s_wpInstance = v50;
            if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
            {
              v49 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v49 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v49 + 8) )
          {
            v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
            if ( *((_DWORD *)v51 + 499) != Buffer )
              CallStackContext::TraceFailure(v51, "CID3Header::OnHeaderRead", 772, Buffer);
          }
          if ( g_wppLevels )
          {
            v11 = 66;
            goto LABEL_118;
          }
        }
        goto LABEL_119;
      }
      v39 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 5);
      v55[0] = 0;
      Buffer = CByteStreamCacheReaderEx::GetCurrentPosition(v39, v55);
      if ( Buffer < 0 )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v43 + 499) != Buffer )
            CallStackContext::TraceFailure(v43, "CID3Header::OnHeaderRead", 755, Buffer);
        }
        if ( g_wppLevels )
        {
          v11 = 62;
          goto LABEL_118;
        }
        goto LABEL_119;
      }
      Buffer = CByteStreamCacheReaderEx::SetCurrentPosition(*((CByteStreamCacheReaderEx **)this + 5), *v33 + v55[0] - 1);
      if ( Buffer < 0 )
      {
        v45 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
          if ( *((_DWORD *)v47 + 499) != Buffer )
            CallStackContext::TraceFailure(v47, "CID3Header::OnHeaderRead", 756, Buffer);
        }
        if ( g_wppLevels )
        {
          v11 = 63;
          goto LABEL_118;
        }
        goto LABEL_119;
      }
      if ( g_wppLevels >= 4u )
      {
        v24 = 64;
        goto LABEL_46;
      }
    }
    else if ( g_wppLevels >= 4u )
    {
      v24 = 58;
LABEL_46:
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_37a327c391a7379b3721a372142db134_Traceguids);
    }
LABEL_31:
    Buffer = -1072873850;
    goto LABEL_119;
  }
  v14 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
    CallStackTracing::s_wpInstance = v15;
    if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
    {
      v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v14 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v14 + 8) )
  {
    v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
    if ( *((_DWORD *)v16 + 499) != Buffer )
      CallStackContext::TraceFailure(v16, "CID3Header::OnHeaderRead", 716, Buffer);
  }
  v10 = 1;
  if ( g_wppLevels )
  {
    v11 = 56;
    goto LABEL_118;
  }
LABEL_119:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v54);
  if ( Buffer < 0 )
  {
    v52 = (struct tagMFASYNCRESULT *)*((_QWORD *)this + 6);
    pCallback = v52->pCallback;
    v52->hrStatusResult = Buffer;
    if ( pCallback )
    {
      LODWORD(v54) = 0;
      v57 = 0;
      if ( ((int (__fastcall *)(IMFAsyncCallback *, CCacheReaderBufferList **, int *))pCallback->lpVtbl->GetParameters)(
             pCallback,
             &v54,
             &v57) >= 0 )
        v10 = v57;
      else
        v57 = 1;
      MFPutWorkItemEx2(v10, 0, &v52->AsyncResult);
    }
    else
    {
      CAsyncResult::SignalEvent(v52);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
}

```

## disassembly

```asm
0x18007395c  mov     [rsp-38h+arg_10], rbx
0x180073961  push    rbp
0x180073962  push    rsi
0x180073963  push    rdi
0x180073964  push    r12
0x180073966  push    r13
0x180073968  push    r14
0x18007396a  push    r15
0x18007396c  mov     rbp, rsp
0x18007396f  sub     rsp, 60h
0x180073973  mov     rax, cs:__security_cookie
0x18007397a  xor     rax, rsp
0x18007397d  mov     [rbp+var_10], rax
0x180073981  mov     rbx, rdx
0x180073984  lea     rsi, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x18007398b  mov     r14, rcx
0x18007398e  mov     rdx, rsi; char *
0x180073991  mov     r8d, 2BDh; int
0x180073997  lea     rcx, [rbp+var_18]; this
0x18007399b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800739a0  mov     rcx, [r14+28h]; this
0x1800739a4  lea     r8, [rbp+var_30]; struct CCacheReaderBufferList **
0x1800739a8  xor     r13d, r13d
0x1800739ab  mov     rdx, rbx; struct IMFAsyncResult *
0x1800739ae  mov     [rbp+var_30], r13
0x1800739b2  call    ?EndRead@CByteStreamCacheReaderEx@@QEAAJPEAUIMFAsyncResult@@PEAPEAVCCacheReaderBufferList@@@Z; CByteStreamCacheReaderEx::EndRead(IMFAsyncResult *,CCacheReaderBufferList * *)
0x1800739b7  mov     edi, eax
0x1800739b9  test    eax, eax
0x1800739bb  jns     loc_180073A5C
0x1800739c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800739c8  test    rcx, rcx
0x1800739cb  jnz     short loc_180073A14
0x1800739cd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800739d4  nop     dword ptr [rax+rax+00h]
0x1800739d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800739e0  mov     rcx, rax
0x1800739e3  test    rax, rax
0x1800739e6  jz      short loc_180073A06
0x1800739e8  mov     rax, [rax]
0x1800739eb  mov     edx, 7F0h
0x1800739f0  mov     rax, [rax+8]
0x1800739f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800739f9  test    eax, eax
0x1800739fb  jz      short loc_180073A06
0x1800739fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073a04  jmp     short loc_180073A14
0x180073a06  lea     rcx, qword_1801B97E0; this
0x180073a0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073a14  cmp     [rcx+8], r13b
0x180073a18  jz      short loc_180073A3B
0x180073a1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073a1f  cmp     [rax+7CCh], edi
0x180073a25  jz      short loc_180073A3B
0x180073a27  mov     r9d, edi; int
0x180073a2a  mov     r8d, 2C3h; int
0x180073a30  mov     rdx, rsi; char *
0x180073a33  mov     rcx, rax; this
0x180073a36  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073a3b  mov     esi, 1
0x180073a40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180073a47  jb      loc_1800740FC
0x180073a4d  lea     edx, [rsi+35h]
0x180073a50  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180073a57  jmp     loc_1800740E5
0x180073a5c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x180073a63  lea     r15, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x180073a6a  jb      short loc_180073A84
0x180073a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a73  mov     edx, 37h ; '7'
0x180073a78  mov     r8, r15
0x180073a7b  mov     rcx, [rcx+10h]
0x180073a7f  call    WPP_SF_
0x180073a84  mov     rbx, [rbp+var_30]
0x180073a88  lea     rax, [rbp+var_14]
0x180073a8c  mov     rcx, rbx; this
0x180073a8f  mov     [rbp+var_28], 3
0x180073a97  lea     rdx, [rbp+var_28]; struct MFBUFFER::CBuffer *
0x180073a9b  mov     [rbp+var_20], rax
0x180073a9f  call    ?GetBuffer@CCacheReaderBufferList@@QEAAJAEBVCBuffer@MFBUFFER@@@Z; CCacheReaderBufferList::GetBuffer(MFBUFFER::CBuffer const &)
0x180073aa4  mov     edi, eax
0x180073aa6  test    eax, eax
0x180073aa8  jns     loc_180073B42
0x180073aae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073ab5  test    rcx, rcx
0x180073ab8  jnz     short loc_180073B01
0x180073aba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073ac1  nop     dword ptr [rax+rax+00h]
0x180073ac6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073acd  mov     rcx, rax
0x180073ad0  test    rax, rax
0x180073ad3  jz      short loc_180073AF3
0x180073ad5  mov     rax, [rax]
0x180073ad8  mov     edx, 7F0h
0x180073add  mov     rax, [rax+8]
0x180073ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ae6  test    eax, eax
0x180073ae8  jz      short loc_180073AF3
0x180073aea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073af1  jmp     short loc_180073B01
0x180073af3  lea     rcx, qword_1801B97E0; this
0x180073afa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073b01  cmp     [rcx+8], r13b
0x180073b05  jz      short loc_180073B28
0x180073b07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073b0c  cmp     [rax+7CCh], edi
0x180073b12  jz      short loc_180073B28
0x180073b14  mov     r9d, edi; int
0x180073b17  mov     r8d, 2CCh; int
0x180073b1d  mov     rdx, rsi; char *
0x180073b20  mov     rcx, rax; this
0x180073b23  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073b28  mov     esi, 1
0x180073b2d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180073b34  jb      loc_1800740FC
0x180073b3a  lea     edx, [rsi+37h]
0x180073b3d  jmp     loc_1800740E2
0x180073b42  mov     al, byte ptr [rbp+var_14]
0x180073b45  mov     esi, 1
0x180073b4a  cmp     al, cs:?s_szID3v2HeaderTag@@3QBDB; char const near * const s_szID3v2HeaderTag
0x180073b50  jnz     short loc_180073B6D
0x180073b52  mov     al, byte ptr [rbp+var_14+1]
0x180073b55  cmp     al, cs:byte_18018CB1D
0x180073b5b  jnz     short loc_180073B6D
0x180073b5d  mov     al, byte ptr [rbp+var_14+2]
0x180073b60  cmp     al, cs:byte_18018CB1E
0x180073b66  jnz     short loc_180073B6D
0x180073b68  mov     eax, r13d
0x180073b6b  jmp     short loc_180073B71
0x180073b6d  sbb     eax, eax
0x180073b6f  or      eax, esi
0x180073b71  test    eax, eax
0x180073b73  jz      short loc_180073B7F
0x180073b75  mov     edi, 0C00D3E86h
0x180073b7a  jmp     loc_1800740FC
0x180073b7f  lea     r12, [r14+208h]
0x180073b86  mov     rcx, rbx; this
0x180073b89  mov     rdx, r12; unsigned __int8 *
0x180073b8c  call    ?GetBYTE@CCacheReaderBufferList@@QEAAJPEAE@Z; CCacheReaderBufferList::GetBYTE(uchar *)
0x180073b91  mov     edi, eax
0x180073b93  test    eax, eax
0x180073b95  jns     loc_180073C30
0x180073b9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073ba2  test    rcx, rcx
0x180073ba5  jnz     short loc_180073BEE
0x180073ba7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073bae  nop     dword ptr [rax+rax+00h]
0x180073bb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073bba  mov     rcx, rax
0x180073bbd  test    rax, rax
0x180073bc0  jz      short loc_180073BE0
0x180073bc2  mov     rax, [rax]
0x180073bc5  mov     edx, 7F0h
0x180073bca  mov     rax, [rax+8]
0x180073bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073bd3  test    eax, eax
0x180073bd5  jz      short loc_180073BE0
0x180073bd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073bde  jmp     short loc_180073BEE
0x180073be0  lea     rcx, qword_1801B97E0; this
0x180073be7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073bee  cmp     [rcx+8], r13b
0x180073bf2  jz      short loc_180073C19
0x180073bf4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073bf9  cmp     [rax+7CCh], edi
0x180073bff  jz      short loc_180073C19
0x180073c01  mov     r9d, edi; int
0x180073c04  lea     rdx, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x180073c0b  mov     r8d, 2D5h; int
0x180073c11  mov     rcx, rax; this
0x180073c14  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073c19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180073c20  jb      loc_1800740FC
0x180073c26  mov     edx, 39h ; '9'
0x180073c2b  jmp     loc_1800740E2
0x180073c30  cmp     byte ptr [r12], 2
0x180073c35  jnb     short loc_180073C61
0x180073c37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x180073c3e  jb      loc_180073B75
0x180073c44  mov     edx, 3Ah ; ':'
0x180073c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c50  mov     r8, r15
0x180073c53  mov     rcx, [rcx+10h]
0x180073c57  call    WPP_SF_
0x180073c5c  jmp     loc_180073B75
0x180073c61  lea     rdx, [r14+209h]; unsigned __int8 *
0x180073c68  mov     rcx, rbx; this
0x180073c6b  call    ?GetBYTE@CCacheReaderBufferList@@QEAAJPEAE@Z; CCacheReaderBufferList::GetBYTE(uchar *)
0x180073c70  mov     edi, eax
0x180073c72  test    eax, eax
0x180073c74  jns     loc_180073D0F
0x180073c7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073c81  test    rcx, rcx
0x180073c84  jnz     short loc_180073CCD
0x180073c86  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073c8d  nop     dword ptr [rax+rax+00h]
0x180073c92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073c99  mov     rcx, rax
0x180073c9c  test    rax, rax
0x180073c9f  jz      short loc_180073CBF
0x180073ca1  mov     rax, [rax]
0x180073ca4  mov     edx, 7F0h
0x180073ca9  mov     rax, [rax+8]
0x180073cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cb2  test    eax, eax
0x180073cb4  jz      short loc_180073CBF
0x180073cb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073cbd  jmp     short loc_180073CCD
0x180073cbf  lea     rcx, qword_1801B97E0; this
0x180073cc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073ccd  cmp     [rcx+8], r13b
0x180073cd1  jz      short loc_180073CF8
0x180073cd3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073cd8  cmp     [rax+7CCh], edi
0x180073cde  jz      short loc_180073CF8
0x180073ce0  mov     r9d, edi; int
0x180073ce3  lea     rdx, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x180073cea  mov     r8d, 2E0h; int
0x180073cf0  mov     rcx, rax; this
0x180073cf3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073cf8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180073cff  jb      loc_1800740FC
0x180073d05  mov     edx, 3Bh ; ';'
0x180073d0a  jmp     loc_1800740E2
0x180073d0f  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x180073d13  mov     [rbp+var_18], r13b
0x180073d17  mov     rcx, rbx; this
0x180073d1a  call    ?GetBYTE@CCacheReaderBufferList@@QEAAJPEAE@Z; CCacheReaderBufferList::GetBYTE(uchar *)
0x180073d1f  mov     edi, eax
0x180073d21  test    eax, eax
0x180073d23  jns     loc_180073DBE
0x180073d29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073d30  test    rcx, rcx
0x180073d33  jnz     short loc_180073D7C
0x180073d35  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073d3c  nop     dword ptr [rax+rax+00h]
0x180073d41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073d48  mov     rcx, rax
0x180073d4b  test    rax, rax
0x180073d4e  jz      short loc_180073D6E
0x180073d50  mov     rax, [rax]
0x180073d53  mov     edx, 7F0h
0x180073d58  mov     rax, [rax+8]
0x180073d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d61  test    eax, eax
0x180073d63  jz      short loc_180073D6E
0x180073d65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073d6c  jmp     short loc_180073D7C
0x180073d6e  lea     rcx, qword_1801B97E0; this
0x180073d75  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073d7c  cmp     [rcx+8], r13b
0x180073d80  jz      short loc_180073DA7
0x180073d82  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073d87  cmp     [rax+7CCh], edi
0x180073d8d  jz      short loc_180073DA7
0x180073d8f  mov     r9d, edi; int
0x180073d92  lea     rdx, aCid3headerOnhe; "CID3Header::OnHeaderRead"
0x180073d99  mov     r8d, 2E5h; int
0x180073d9f  mov     rcx, rax; this
0x180073da2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180073da7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180073dae  jb      loc_1800740FC
0x180073db4  mov     edx, 3Ch ; '<'
0x180073db9  jmp     loc_1800740E2
0x180073dbe  mov     r8b, [rbp+var_18]; unsigned __int8
0x180073dc2  mov     rcx, r14; this
0x180073dc5  mov     dl, [r12]; unsigned __int8
0x180073dc9  call    ?DecodeFlags@CID3Header@@IEAAJEE@Z; CID3Header::DecodeFlags(uchar,uchar)
0x180073dce  lea     r13, [r14+214h]
0x180073dd5  mov     rcx, rbx; this
0x180073dd8  mov     rdx, r13; unsigned int *
0x180073ddb  call    ?GetDWORD@CId3SyncSafe@@SAJPEAVCCacheReaderBufferList@@PEAK@Z; CId3SyncSafe::GetDWORD(CCacheReaderBufferList *,ulong *)
0x180073de0  mov     edi, eax
0x180073de2  test    eax, eax
0x180073de4  jns     loc_180073E82
0x180073dea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073df1  xor     r13d, r13d
0x180073df4  test    rcx, rcx
0x180073df7  jnz     short loc_180073E40
0x180073df9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180073e00  nop     dword ptr [rax+rax+00h]
0x180073e05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180073e0c  mov     rcx, rax
0x180073e0f  test    rax, rax
0x180073e12  jz      short loc_180073E32
0x180073e14  mov     rax, [rax]
0x180073e17  mov     edx, 7F0h
0x180073e1c  mov     rax, [rax+8]
0x180073e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e25  test    eax, eax
0x180073e27  jz      short loc_180073E32
0x180073e29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180073e30  jmp     short loc_180073E40
0x180073e32  lea     rcx, qword_1801B97E0; this
0x180073e39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180073e40  cmp     [rcx+8], r13b
0x180073e44  jz      short loc_180073E6B
0x180073e46  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180073e4b  cmp     [rax+7CCh], edi
0x180073e51  jz      short loc_180073E6B
0x180073e53  mov     r9d, edi; int
  ... truncated ...
```
