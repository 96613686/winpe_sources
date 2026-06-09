# CMP3ByteStreamPlugin::OnMP3SourceCreation(IMFAsyncResult *)

- ea: `0x18009baec`
- end: `0x18009bec6`
- name: `?OnMP3SourceCreation@CMP3ByteStreamPlugin@@IEAAJPEAUIMFAsyncResult@@@Z`
- size: `986`
- prototype: `int(CMP3ByteStreamPlugin *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010fc40`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x18009baec`
- `0x1800a0fb8`
- `0x1801099f0`
- `0x180117dd0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009be48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009be48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009be3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009be3a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009be74`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18009be74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009be6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009be6a`
- `MFPlat!MFPutWorkItemEx2` at `0x18009be21`
- `MFPlat!MFPutWorkItemEx2` at `0x18009be21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bba1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bc5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bd29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bba1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bc5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009bd29`

## string_xrefs

- `0x18009bb0e`: `CMP3ByteStreamPlugin::OnMP3SourceCreation`
- `0x18009bbf8`: `CMP3ByteStreamPlugin::OnMP3SourceCreation`
- `0x18009bcb4`: `CMP3ByteStreamPlugin::OnMP3SourceCreation`
- `0x18009bd80`: `CMP3ByteStreamPlugin::OnMP3SourceCreation`

## pseudocode

```c
__int64 __fastcall CMP3ByteStreamPlugin::OnMP3SourceCreation(CMP3ByteStreamPlugin *this, struct IMFAsyncResult *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  wchar_t *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  __int128 *v10; // rax
  __int128 v11; // xmm0
  DWORD v12; // r14d
  int v13; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  CMP3ByteStreamPluginResult **v16; // rdi
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  CMP3BytewiseMediaSource *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  CMP3ByteStreamPluginResult *v27; // rbp
  __int64 v28; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v31; // sf
  __int64 v32; // rcx
  _BYTE v34[4]; // [rsp+30h] [rbp-58h] BYREF
  int v35; // [rsp+34h] [rbp-54h] BYREF
  _DWORD v36[4]; // [rsp+38h] [rbp-50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v34, "CMP3ByteStreamPlugin::OnMP3SourceCreation", 247);
  v7 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 15) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 296LL))(*((_QWORD *)this + 15));
    v10 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 15) + 280LL))(
                        *((_QWORD *)this + 15),
                        v36);
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    v11 = *v10;
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v11;
  }
  v12 = 1;
  if ( !a2 )
  {
    v13 = -2147467261;
    if ( !v7 )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
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
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v15 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v15, "CMP3ByteStreamPlugin::OnMP3SourceCreation", 247, -2147467261);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids,
        this,
        -2147467261);
    v16 = (CMP3ByteStreamPluginResult **)((char *)this + 104);
    goto LABEL_42;
  }
  v16 = (CMP3ByteStreamPluginResult **)((char *)this + 104);
  if ( *(_DWORD *)(*((_QWORD *)this + 13) + 96LL) )
  {
    v13 = -2147467260;
    if ( !v7 )
    {
      v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v17;
      if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
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
      v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v18 + 499) != -2147467260 )
        CallStackContext::TraceFailure(v18, "CMP3ByteStreamPlugin::OnMP3SourceCreation", 254, -2147467260);
    }
    if ( !g_wppLevels )
      goto LABEL_42;
    v19 = 27;
  }
  else
  {
    v20 = (CMP3BytewiseMediaSource *)*((_QWORD *)this + 14);
    if ( !v20 )
    {
      v13 = 0;
      goto LABEL_42;
    }
    v13 = CMP3BytewiseMediaSource::EndOpen(v20, a2);
    if ( v13 >= 0 )
    {
      CMP3ByteStreamPluginResult::SetResultObject(*v16, *((struct IUnknown **)this + 14));
      goto LABEL_42;
    }
    v24 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v26 + 499) != v13 )
        CallStackContext::TraceFailure(v26, "CMP3ByteStreamPlugin::OnMP3SourceCreation", 260, v13);
    }
    if ( !g_wppLevels )
      goto LABEL_42;
    v19 = 28;
  }
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids, this, v13);
LABEL_42:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v34);
  if ( v13 >= 0 )
    *((_DWORD *)*v16 + 26) = 0;
  else
    CMP3ByteStreamPluginResult::SetResultObject(*v16, 0);
  v27 = *v16;
  v28 = *((_QWORD *)*v16 + 5);
  *((_DWORD *)*v16 + 12) = v13;
  if ( v28 )
  {
    v36[0] = 0;
    v35 = 0;
    if ( (*(int (__fastcall **)(__int64, _DWORD *, int *))(*(_QWORD *)v28 + 24LL))(v28, v36, &v35) >= 0 )
      v12 = v35;
    else
      v35 = 1;
    MFPutWorkItemEx2(v12, 0, (IMFAsyncResult *)v27);
    goto LABEL_59;
  }
  if ( *((_QWORD *)v27 + 7) )
    goto LABEL_58;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)v27 + 7, (signed __int64)EventW, 0) )
      CloseHandle(EventW);
    goto LABEL_58;
  }
  LastError = GetLastError();
  v31 = LastError < 0;
  if ( LastError > 0 )
    v31 = 1;
  if ( !v31 )
LABEL_58:
    SetEvent(*((HANDLE *)v27 + 7));
LABEL_59:
  if ( *v16 )
  {
    (*(void (__fastcall **)(CMP3ByteStreamPluginResult *))(*(_QWORD *)*v16 + 16LL))(*v16);
    *v16 = 0;
  }
  v32 = *((_QWORD *)this + 14);
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    *((_QWORD *)this + 14) = 0;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18009baec  push    rbx
0x18009baee  push    rbp
0x18009baef  push    rsi
0x18009baf0  push    rdi
0x18009baf1  push    r14
0x18009baf3  push    r15
0x18009baf5  sub     rsp, 58h
0x18009baf9  mov     rax, cs:__security_cookie
0x18009bb00  xor     rax, rsp
0x18009bb03  mov     [rsp+88h+var_40], rax
0x18009bb08  mov     rbp, rdx
0x18009bb0b  mov     rsi, rcx
0x18009bb0e  lea     rdx, aCmp3bytestream; "CMP3ByteStreamPlugin::OnMP3SourceCreati"...
0x18009bb15  mov     r8d, 0F7h; int
0x18009bb1b  lea     rcx, [rsp+88h+var_58]; this
0x18009bb20  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009bb25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18009bb2c  xor     r15d, r15d
0x18009bb2f  cmp     [rcx+8], r15b
0x18009bb33  jz      short loc_18009BB88
0x18009bb35  cmp     [rsi+78h], r15
0x18009bb39  jz      short loc_18009BB88
0x18009bb3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009bb40  mov     rcx, [rsi+78h]
0x18009bb44  mov     rdi, rax
0x18009bb47  mov     rdx, [rcx]
0x18009bb4a  mov     rax, [rdx+128h]
0x18009bb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bb56  mov     rcx, [rsi+78h]
0x18009bb5a  mov     ebx, eax
0x18009bb5c  mov     rdx, [rcx]
0x18009bb5f  mov     rax, [rdx+118h]
0x18009bb66  lea     rdx, [rsp+88h+var_50]
0x18009bb6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bb70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bb77  movups  xmm0, xmmword ptr [rax]
0x18009bb7a  mov     [rdi+7E0h], ebx
0x18009bb80  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18009bb88  mov     r14d, 1
0x18009bb8e  test    rbp, rbp
0x18009bb91  jnz     loc_18009BC42
0x18009bb97  mov     ebx, 80004003h
0x18009bb9c  test    rcx, rcx
0x18009bb9f  jnz     short loc_18009BBE2
0x18009bba1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009bba7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bbae  mov     rcx, rax
0x18009bbb1  test    rax, rax
0x18009bbb4  jz      short loc_18009BBD4
0x18009bbb6  mov     rax, [rax]
0x18009bbb9  mov     edx, 7F0h
0x18009bbbe  mov     rax, [rax+8]
0x18009bbc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bbc7  test    eax, eax
0x18009bbc9  jz      short loc_18009BBD4
0x18009bbcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bbd2  jmp     short loc_18009BBE2
0x18009bbd4  lea     rcx, qword_1801B07E0; this
0x18009bbdb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bbe2  cmp     [rcx+8], r15b
0x18009bbe6  jz      short loc_18009BC0D
0x18009bbe8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009bbed  cmp     [rax+7CCh], ebx
0x18009bbf3  jz      short loc_18009BC0D
0x18009bbf5  mov     r9d, ebx; int
0x18009bbf8  lea     rdx, aCmp3bytestream; "CMP3ByteStreamPlugin::OnMP3SourceCreati"...
0x18009bbff  mov     r8d, 0F7h; int
0x18009bc05  mov     rcx, rax; this
0x18009bc08  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009bc0d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18009bc14  jb      short loc_18009BC39
0x18009bc16  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bc1d  lea     r8, WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids
0x18009bc24  mov     edx, 1Ah
0x18009bc29  mov     [rsp+88h+var_68], ebx
0x18009bc2d  mov     r9, rsi
0x18009bc30  mov     rcx, [rcx+10h]
0x18009bc34  call    WPP_SF_qD
0x18009bc39  lea     rdi, [rsi+68h]
0x18009bc3d  jmp     loc_18009BDB9
0x18009bc42  lea     rdi, [rsi+68h]
0x18009bc46  mov     rax, [rdi]
0x18009bc49  cmp     [rax+60h], r15d
0x18009bc4d  jz      loc_18009BCFE
0x18009bc53  mov     ebx, 80004004h
0x18009bc58  test    rcx, rcx
0x18009bc5b  jnz     short loc_18009BC9E
0x18009bc5d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009bc63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bc6a  mov     rcx, rax
0x18009bc6d  test    rax, rax
0x18009bc70  jz      short loc_18009BC90
0x18009bc72  mov     rax, [rax]
0x18009bc75  mov     edx, 7F0h
0x18009bc7a  mov     rax, [rax+8]
0x18009bc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bc83  test    eax, eax
0x18009bc85  jz      short loc_18009BC90
0x18009bc87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bc8e  jmp     short loc_18009BC9E
0x18009bc90  lea     rcx, qword_1801B07E0; this
0x18009bc97  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bc9e  cmp     [rcx+8], r15b
0x18009bca2  jz      short loc_18009BCC9
0x18009bca4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009bca9  cmp     [rax+7CCh], ebx
0x18009bcaf  jz      short loc_18009BCC9
0x18009bcb1  mov     r9d, ebx; int
0x18009bcb4  lea     rdx, aCmp3bytestream; "CMP3ByteStreamPlugin::OnMP3SourceCreati"...
0x18009bcbb  mov     r8d, 0FEh; int
0x18009bcc1  mov     rcx, rax; this
0x18009bcc4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009bcc9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18009bcd0  jb      loc_18009BDB9
0x18009bcd6  mov     edx, 1Bh
0x18009bcdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bce2  lea     r8, WPP_b4ae0bf7ed0435f21fb1fe83437c97de_Traceguids
0x18009bce9  mov     r9, rsi
0x18009bcec  mov     [rsp+88h+var_68], ebx
0x18009bcf0  mov     rcx, [rcx+10h]
0x18009bcf4  call    WPP_SF_qD
0x18009bcf9  jmp     loc_18009BDB9
0x18009bcfe  mov     rcx, [rsi+70h]; this
0x18009bd02  test    rcx, rcx
0x18009bd05  jz      loc_18009BDB6
0x18009bd0b  mov     rdx, rbp; struct IMFAsyncResult *
0x18009bd0e  call    ?EndOpen@CMP3BytewiseMediaSource@@QEAAJPEAUIMFAsyncResult@@@Z; CMP3BytewiseMediaSource::EndOpen(IMFAsyncResult *)
0x18009bd13  mov     ebx, eax
0x18009bd15  test    eax, eax
0x18009bd17  jns     loc_18009BDA8
0x18009bd1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bd24  test    rcx, rcx
0x18009bd27  jnz     short loc_18009BD6A
0x18009bd29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009bd2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bd36  mov     rcx, rax
0x18009bd39  test    rax, rax
0x18009bd3c  jz      short loc_18009BD5C
0x18009bd3e  mov     rax, [rax]
0x18009bd41  mov     edx, 7F0h
0x18009bd46  mov     rax, [rax+8]
0x18009bd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bd4f  test    eax, eax
0x18009bd51  jz      short loc_18009BD5C
0x18009bd53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bd5a  jmp     short loc_18009BD6A
0x18009bd5c  lea     rcx, qword_1801B07E0; this
0x18009bd63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009bd6a  cmp     [rcx+8], r15b
0x18009bd6e  jz      short loc_18009BD95
0x18009bd70  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009bd75  cmp     [rax+7CCh], ebx
0x18009bd7b  jz      short loc_18009BD95
0x18009bd7d  mov     r9d, ebx; int
0x18009bd80  lea     rdx, aCmp3bytestream; "CMP3ByteStreamPlugin::OnMP3SourceCreati"...
0x18009bd87  mov     r8d, 104h; int
0x18009bd8d  mov     rcx, rax; this
0x18009bd90  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009bd95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18009bd9c  jb      short loc_18009BDB9
0x18009bd9e  mov     edx, 1Ch
0x18009bda3  jmp     loc_18009BCDB
0x18009bda8  mov     rdx, [rsi+70h]; struct IUnknown *
0x18009bdac  mov     rcx, [rdi]; this
0x18009bdaf  call    ?SetResultObject@CMP3ByteStreamPluginResult@@QEAAXPEAUIUnknown@@@Z; CMP3ByteStreamPluginResult::SetResultObject(IUnknown *)
0x18009bdb4  jmp     short loc_18009BDB9
0x18009bdb6  mov     ebx, r15d
0x18009bdb9  lea     rcx, [rsp+88h+var_58]; this
0x18009bdbe  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009bdc3  mov     rax, [rdi]
0x18009bdc6  test    ebx, ebx
0x18009bdc8  jns     short loc_18009BDD6
0x18009bdca  xor     edx, edx; struct IUnknown *
0x18009bdcc  mov     rcx, rax; this
0x18009bdcf  call    ?SetResultObject@CMP3ByteStreamPluginResult@@QEAAXPEAUIUnknown@@@Z; CMP3ByteStreamPluginResult::SetResultObject(IUnknown *)
0x18009bdd4  jmp     short loc_18009BDDA
0x18009bdd6  mov     [rax+68h], r15d
0x18009bdda  mov     rbp, [rdi]
0x18009bddd  mov     rcx, [rbp+28h]
0x18009bde1  mov     [rbp+30h], ebx
0x18009bde4  test    rcx, rcx
0x18009bde7  jz      short loc_18009BE29
0x18009bde9  mov     [rsp+88h+var_50], r15d
0x18009bdee  lea     r8, [rsp+88h+var_54]
0x18009bdf3  mov     [rsp+88h+var_54], r15d
0x18009bdf8  lea     rdx, [rsp+88h+var_50]
0x18009bdfd  mov     rax, [rcx]
0x18009be00  mov     rax, [rax+18h]
0x18009be04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009be09  test    eax, eax
0x18009be0b  jns     short loc_18009BE14
0x18009be0d  mov     [rsp+88h+var_54], r14d
0x18009be12  jmp     short loc_18009BE19
0x18009be14  mov     r14d, [rsp+88h+var_54]
0x18009be19  mov     r8, rbp; pResult
0x18009be1c  xor     edx, edx; Priority
0x18009be1e  mov     ecx, r14d; dwQueue
0x18009be21  call    cs:__imp_MFPutWorkItemEx2
0x18009be27  jmp     short loc_18009BE7A
0x18009be29  cmp     [rbp+38h], r15
0x18009be2d  jnz     short loc_18009BE70
0x18009be2f  xor     r9d, r9d; lpName
0x18009be32  xor     r8d, r8d; bInitialState
0x18009be35  mov     edx, r14d; bManualReset
0x18009be38  xor     ecx, ecx; lpEventAttributes
0x18009be3a  call    cs:__imp_CreateEventW
0x18009be40  mov     rcx, rax; hObject
0x18009be43  test    rax, rax
0x18009be46  jnz     short loc_18009BE60
0x18009be48  call    cs:__imp_GetLastError
0x18009be4e  test    eax, eax
0x18009be50  jle     short loc_18009BE5C
0x18009be52  movzx   eax, ax
0x18009be55  or      eax, 80070000h
0x18009be5a  test    eax, eax
0x18009be5c  js      short loc_18009BE7A
0x18009be5e  jmp     short loc_18009BE70
0x18009be60  xor     eax, eax
0x18009be62  lock cmpxchg [rbp+38h], rcx
0x18009be68  jz      short loc_18009BE70
0x18009be6a  call    cs:__imp_CloseHandle
0x18009be70  mov     rcx, [rbp+38h]; hEvent
0x18009be74  call    cs:__imp_SetEvent
0x18009be7a  mov     rcx, [rdi]
0x18009be7d  test    rcx, rcx
0x18009be80  jz      short loc_18009BE91
0x18009be82  mov     rax, [rcx]
0x18009be85  mov     rax, [rax+10h]
0x18009be89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009be8e  mov     [rdi], r15
0x18009be91  mov     rcx, [rsi+70h]
0x18009be95  test    rcx, rcx
0x18009be98  jz      short loc_18009BEAA
0x18009be9a  mov     rax, [rcx]
0x18009be9d  mov     rax, [rax+10h]
0x18009bea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bea6  mov     [rsi+70h], r15
0x18009beaa  mov     eax, ebx
0x18009beac  mov     rcx, [rsp+88h+var_40]
0x18009beb1  xor     rcx, rsp; StackCookie
0x18009beb4  call    __security_check_cookie
0x18009beb9  add     rsp, 58h
0x18009bebd  pop     r15
0x18009bebf  pop     r14
0x18009bec1  pop     rdi
0x18009bec2  pop     rsi
0x18009bec3  pop     rbp
0x18009bec4  pop     rbx
0x18009bec5  retn
```
