# CID3Header::OnTagRead(IMFAsyncResult *)

- ea: `0x1800e2c40`
- end: `0x1800e2f58`
- name: `?OnTagRead@CID3Header@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `792`
- prototype: `void __fastcall(CID3Header *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180169e10`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18003f85c`
- `0x180041f68`
- `0x180065024`
- `0x180073b14`
- `0x1800e2c40`
- `0x180169e30`
- `0x18016ada4`
- `0x18016b328`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2f09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e2efb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e2efb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e2f35`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e2f35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e2f2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e2f2b`
- `MFPlat!MFPutWorkItemEx2` at `0x1800e2ee2`
- `MFPlat!MFPutWorkItemEx2` at `0x1800e2ee2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2ca4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2dc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2ca4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e2dc7`

## string_xrefs

- `0x1800e2c5b`: `CID3Header::OnTagRead`
- `0x1800e2cfb`: `CID3Header::OnTagRead`
- `0x1800e2e1e`: `CID3Header::OnTagRead`

## pseudocode

```c
// bad sp value at call has been detected, the output may be wrong!
void __fastcall CID3Header::OnTagRead(CID3Header *this, struct IMFAsyncResult *a2)
{
  CByteStreamCacheReaderEx *v4; // rcx
  __int64 v5; // rdx
  int CurrentPosition; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD v9; // esi
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rdx
  int Frames; // r14d
  CByteStreamCacheReaderEx *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 v26; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v29; // sf
  _BYTE v30[8]; // [rsp+40h] [rbp-20h] BYREF
  struct CCacheReaderBufferList *v31; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v32[2]; // [rsp+50h] [rbp-10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v30, "CID3Header::OnTagRead", 786);
  v4 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 5);
  v31 = 0;
  CurrentPosition = CByteStreamCacheReaderEx::EndRead(v4, a2, &v31);
  v9 = 1;
  if ( CurrentPosition < 0 )
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != CurrentPosition )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CID3Header::OnTagRead", 792, CurrentPosition);
    }
    if ( !g_wppLevels )
      goto LABEL_35;
    v13 = 68;
    goto LABEL_12;
  }
  if ( !*((_DWORD *)this + 134) || (CurrentPosition = CID3Header::ReadExtHdr(this, v31), CurrentPosition >= 0) )
  {
    if ( (unsigned int)CID3Header::IsValid(this) )
    {
      Frames = CID3Header::ReadFrames(this, v31);
      if ( Frames < 0 )
      {
        CurrentPosition = 0;
        if ( !(unsigned int)CID3Header::IsValid(this) )
          CurrentPosition = Frames;
        goto LABEL_35;
      }
      v15 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 5);
      v32[0] = 0;
      CurrentPosition = CByteStreamCacheReaderEx::GetCurrentPosition(v15, v32);
      if ( CurrentPosition >= 0 )
      {
        v22 = *((_QWORD *)this + 3);
        v23 = *((unsigned int *)this + 133);
        v24 = v23 + v22 + 10;
        if ( v24 < v32[0] )
        {
          if ( g_wppLevels >= 0x10u )
            WPP_SF_qidii(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v32[0], this, v22, v23, v23 + v22 + 10, v32[0]);
          CurrentPosition = -2147467259;
        }
        goto LABEL_35;
      }
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
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
        if ( *((_DWORD *)v21 + 499) != CurrentPosition )
          CallStackContext::TraceFailure(v21, "CID3Header::OnTagRead", 819, CurrentPosition);
      }
      if ( g_wppLevels )
      {
        v13 = 69;
LABEL_12:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          &WPP_37a327c391a7379b3721a372142db134_Traceguids,
          this,
          CurrentPosition);
      }
    }
  }
LABEL_35:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v31);
  v25 = *((_QWORD *)this + 6);
  v26 = *(_QWORD *)(v25 + 40);
  *(_DWORD *)(v25 + 48) = CurrentPosition;
  if ( v26 )
  {
    LODWORD(v31) = 0;
    LODWORD(v32[0]) = 0;
    if ( (*(int (__fastcall **)(__int64, struct CCacheReaderBufferList **, unsigned __int64 *))(*(_QWORD *)v26 + 24LL))(
           v26,
           &v31,
           v32) >= 0 )
      v9 = v32[0];
    else
      LODWORD(v32[0]) = 1;
    MFPutWorkItemEx2(v9, 0, (IMFAsyncResult *)v25);
    goto LABEL_49;
  }
  if ( *(_QWORD *)(v25 + 56) )
    goto LABEL_48;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v25 + 56), (signed __int64)EventW, 0) )
      CloseHandle(EventW);
    goto LABEL_48;
  }
  LastError = GetLastError();
  v29 = LastError < 0;
  if ( LastError > 0 )
    v29 = 1;
  if ( !v29 )
LABEL_48:
    SetEvent(*(HANDLE *)(v25 + 56));
LABEL_49:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
}

```

## disassembly

```asm
0x1800e2c40  mov     [rsp-18h+arg_10], rbx
0x1800e2c45  mov     [rsp-18h+arg_18], rsi
0x1800e2c4a  push    rbp
0x1800e2c4b  push    rdi
0x1800e2c4c  push    r14
0x1800e2c4e  mov     rbp, rsp
0x1800e2c51  sub     rsp, 60h
0x1800e2c55  mov     rbx, rdx
0x1800e2c58  mov     rdi, rcx
0x1800e2c5b  lea     rdx, aCid3headerOnta; "CID3Header::OnTagRead"
0x1800e2c62  mov     r8d, 312h; int
0x1800e2c68  lea     rcx, [rbp+var_20]; this
0x1800e2c6c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e2c71  mov     rcx, [rdi+28h]; this
0x1800e2c75  lea     r8, [rbp+var_18]; struct CCacheReaderBufferList **
0x1800e2c79  mov     rdx, rbx; struct IMFAsyncResult *
0x1800e2c7c  mov     [rbp+var_18], 0
0x1800e2c84  call    ?EndRead@CByteStreamCacheReaderEx@@QEAAJPEAUIMFAsyncResult@@PEAPEAVCCacheReaderBufferList@@@Z; CByteStreamCacheReaderEx::EndRead(IMFAsyncResult *,CCacheReaderBufferList * *)
0x1800e2c89  mov     ebx, eax
0x1800e2c8b  mov     esi, 1
0x1800e2c90  test    eax, eax
0x1800e2c92  jns     loc_1800E2D45
0x1800e2c98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2c9f  test    rcx, rcx
0x1800e2ca2  jnz     short loc_1800E2CE5
0x1800e2ca4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2caa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2cb1  mov     rcx, rax
0x1800e2cb4  test    rax, rax
0x1800e2cb7  jz      short loc_1800E2CD7
0x1800e2cb9  mov     rax, [rax]
0x1800e2cbc  mov     edx, 7F0h
0x1800e2cc1  mov     rax, [rax+8]
0x1800e2cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2cca  test    eax, eax
0x1800e2ccc  jz      short loc_1800E2CD7
0x1800e2cce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2cd5  jmp     short loc_1800E2CE5
0x1800e2cd7  lea     rcx, qword_1801B07E0; this
0x1800e2cde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2ce5  cmp     byte ptr [rcx+8], 0
0x1800e2ce9  jz      short loc_1800E2D10
0x1800e2ceb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2cf0  cmp     [rax+7CCh], ebx
0x1800e2cf6  jz      short loc_1800E2D10
0x1800e2cf8  mov     r9d, ebx; int
0x1800e2cfb  lea     rdx, aCid3headerOnta; "CID3Header::OnTagRead"
0x1800e2d02  mov     r8d, 318h; int
0x1800e2d08  mov     rcx, rax; this
0x1800e2d0b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2d10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800e2d17  jb      loc_1800E2E94
0x1800e2d1d  mov     edx, 44h ; 'D'
0x1800e2d22  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2d29  lea     r8, WPP_37a327c391a7379b3721a372142db134_Traceguids
0x1800e2d30  mov     r9, rdi
0x1800e2d33  mov     dword ptr [rsp+60h+var_40], ebx
0x1800e2d37  mov     rcx, [rcx+10h]
0x1800e2d3b  call    WPP_SF_qD
0x1800e2d40  jmp     loc_1800E2E94
0x1800e2d45  cmp     dword ptr [rdi+218h], 0
0x1800e2d4c  jz      short loc_1800E2D64
0x1800e2d4e  mov     rdx, [rbp+var_18]; struct CCacheReaderBufferList *
0x1800e2d52  mov     rcx, rdi; this
0x1800e2d55  call    ?ReadExtHdr@CID3Header@@AEAAJPEAVCCacheReaderBufferList@@@Z; CID3Header::ReadExtHdr(CCacheReaderBufferList *)
0x1800e2d5a  mov     ebx, eax
0x1800e2d5c  test    eax, eax
0x1800e2d5e  js      loc_1800E2E94
0x1800e2d64  mov     rcx, rdi; this
0x1800e2d67  call    ?IsValid@CID3Header@@QEBAHXZ; CID3Header::IsValid(void)
0x1800e2d6c  test    eax, eax
0x1800e2d6e  jz      loc_1800E2E94
0x1800e2d74  mov     rdx, [rbp+var_18]; struct CCacheReaderBufferList *
0x1800e2d78  mov     rcx, rdi; this
0x1800e2d7b  call    ?ReadFrames@CID3Header@@AEAAJPEAVCCacheReaderBufferList@@@Z; CID3Header::ReadFrames(CCacheReaderBufferList *)
0x1800e2d80  mov     r14d, eax
0x1800e2d83  test    eax, eax
0x1800e2d85  jns     short loc_1800E2D9C
0x1800e2d87  mov     rcx, rdi; this
0x1800e2d8a  call    ?IsValid@CID3Header@@QEBAHXZ; CID3Header::IsValid(void)
0x1800e2d8f  xor     ebx, ebx
0x1800e2d91  test    eax, eax
0x1800e2d93  cmovz   ebx, r14d
0x1800e2d97  jmp     loc_1800E2E94
0x1800e2d9c  mov     rcx, [rdi+28h]; this
0x1800e2da0  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x1800e2da4  mov     [rbp+var_10], 0
0x1800e2dac  call    ?GetCurrentPosition@CByteStreamCacheReaderEx@@QEAAJPEA_K@Z; CByteStreamCacheReaderEx::GetCurrentPosition(unsigned __int64 *)
0x1800e2db1  mov     ebx, eax
0x1800e2db3  test    eax, eax
0x1800e2db5  jns     loc_1800E2E46
0x1800e2dbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2dc2  test    rcx, rcx
0x1800e2dc5  jnz     short loc_1800E2E08
0x1800e2dc7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e2dcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2dd4  mov     rcx, rax
0x1800e2dd7  test    rax, rax
0x1800e2dda  jz      short loc_1800E2DFA
0x1800e2ddc  mov     rax, [rax]
0x1800e2ddf  mov     edx, 7F0h
0x1800e2de4  mov     rax, [rax+8]
0x1800e2de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2ded  test    eax, eax
0x1800e2def  jz      short loc_1800E2DFA
0x1800e2df1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2df8  jmp     short loc_1800E2E08
0x1800e2dfa  lea     rcx, qword_1801B07E0; this
0x1800e2e01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e2e08  cmp     byte ptr [rcx+8], 0
0x1800e2e0c  jz      short loc_1800E2E33
0x1800e2e0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e2e13  cmp     [rax+7CCh], ebx
0x1800e2e19  jz      short loc_1800E2E33
0x1800e2e1b  mov     r9d, ebx; int
0x1800e2e1e  lea     rdx, aCid3headerOnta; "CID3Header::OnTagRead"
0x1800e2e25  mov     r8d, 333h; int
0x1800e2e2b  mov     rcx, rax; this
0x1800e2e2e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e2e33  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800e2e3a  jb      short loc_1800E2E94
0x1800e2e3c  mov     edx, 45h ; 'E'
0x1800e2e41  jmp     loc_1800E2D22
0x1800e2e46  mov     rax, [rdi+18h]
0x1800e2e4a  mov     ecx, [rdi+214h]
0x1800e2e50  mov     r8, [rbp+var_10]
0x1800e2e54  lea     rdx, [rax+0Ah]
0x1800e2e58  add     rdx, rcx
0x1800e2e5b  cmp     rdx, r8
0x1800e2e5e  jnb     short loc_1800E2E94
0x1800e2e60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 10h; MFWppLevels g_wppLevels
0x1800e2e67  jb      short loc_1800E2E8F
0x1800e2e69  mov     [rsp+60h+var_28], r8
0x1800e2e6e  mov     r9, rdi
0x1800e2e71  mov     [rsp+60h+var_30], rdx
0x1800e2e76  mov     [rsp+60h+var_38], ecx
0x1800e2e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2e81  mov     [rsp+60h+var_40], rax
0x1800e2e86  mov     rcx, [rcx+10h]
0x1800e2e8a  call    WPP_SF_qidii
0x1800e2e8f  mov     ebx, 80004005h
0x1800e2e94  lea     rcx, [rbp+var_18]; void *
0x1800e2e98  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800e2e9d  mov     rdi, [rdi+30h]
0x1800e2ea1  mov     rcx, [rdi+28h]
0x1800e2ea5  mov     [rdi+30h], ebx
0x1800e2ea8  test    rcx, rcx
0x1800e2eab  jz      short loc_1800E2EEA
0x1800e2ead  mov     dword ptr [rbp+var_18], 0
0x1800e2eb4  lea     r8, [rbp+var_10]
0x1800e2eb8  mov     dword ptr [rbp+var_10], 0
0x1800e2ebf  lea     rdx, [rbp+var_18]
0x1800e2ec3  mov     rax, [rcx]
0x1800e2ec6  mov     rax, [rax+18h]
0x1800e2eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2ecf  test    eax, eax
0x1800e2ed1  jns     short loc_1800E2ED8
0x1800e2ed3  mov     dword ptr [rbp+var_10], esi
0x1800e2ed6  jmp     short loc_1800E2EDB
0x1800e2ed8  mov     esi, dword ptr [rbp+var_10]
0x1800e2edb  mov     r8, rdi; pResult
0x1800e2ede  xor     edx, edx; Priority
0x1800e2ee0  mov     ecx, esi; dwQueue
0x1800e2ee2  call    cs:__imp_MFPutWorkItemEx2
0x1800e2ee8  jmp     short loc_1800E2F3B
0x1800e2eea  cmp     qword ptr [rdi+38h], 0
0x1800e2eef  jnz     short loc_1800E2F31
0x1800e2ef1  xor     r9d, r9d; lpName
0x1800e2ef4  xor     r8d, r8d; bInitialState
0x1800e2ef7  mov     edx, esi; bManualReset
0x1800e2ef9  xor     ecx, ecx; lpEventAttributes
0x1800e2efb  call    cs:__imp_CreateEventW
0x1800e2f01  mov     rcx, rax; hObject
0x1800e2f04  test    rax, rax
0x1800e2f07  jnz     short loc_1800E2F21
0x1800e2f09  call    cs:__imp_GetLastError
0x1800e2f0f  test    eax, eax
0x1800e2f11  jle     short loc_1800E2F1D
0x1800e2f13  movzx   eax, ax
0x1800e2f16  or      eax, 80070000h
0x1800e2f1b  test    eax, eax
0x1800e2f1d  js      short loc_1800E2F3B
0x1800e2f1f  jmp     short loc_1800E2F31
0x1800e2f21  xor     eax, eax
0x1800e2f23  lock cmpxchg [rdi+38h], rcx
0x1800e2f29  jz      short loc_1800E2F31
0x1800e2f2b  call    cs:__imp_CloseHandle
0x1800e2f31  mov     rcx, [rdi+38h]; hEvent
0x1800e2f35  call    cs:__imp_SetEvent
0x1800e2f3b  lea     rcx, [rbp+var_20]; this
0x1800e2f3f  lea     r11, [rsp+60h+var_s0]
0x1800e2f44  mov     rbx, [r11+30h]
0x1800e2f48  mov     rsi, [r11+38h]
0x1800e2f4c  mov     rsp, r11
0x1800e2f4f  pop     r14
0x1800e2f51  pop     rdi
0x1800e2f52  pop     rbp
0x1800e2f53  jmp     ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
```
