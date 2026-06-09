# MFMkvPropertyHandler::LoadSourceAsync(void)

- ea: `0x180050060`
- end: `0x180050451`
- name: `?LoadSourceAsync@MFMkvPropertyHandler@@AEAAJXZ`
- size: `1009`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004fde0`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000e670`
- `0x180010d70`
- `0x180050060`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005009b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005009b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005042b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005042b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800500c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050186`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050265`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050313`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005039b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800500c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050186`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050265`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180050313`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005039b`
- `MFPlat!MFCreateAsyncResult` at `0x1800502f5`
- `MFPlat!MFCreateAsyncResult` at `0x1800502f5`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x180050168`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x180050168`
- `MFPlat!MFCreateTelemetrySession` at `0x180050219`
- `MFPlat!MFCreateTelemetrySession` at `0x180050219`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MFMkvPropertyHandler::LoadSourceAsync(MFMkvPropertyHandler *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  MkvMfSourceLib::MkvMfSource **v5; // rsi
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  HRESULT Source; // ebx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  GUID v33; // [rsp+20h] [rbp-28h] BYREF
  GUID v34; // [rsp+30h] [rbp-18h] BYREF
  char *v35; // [rsp+80h] [rbp+38h] BYREF
  struct IMFTelemetrySession *v36; // [rsp+88h] [rbp+40h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+90h] [rbp+48h] BYREF
  IMFByteStream *ppByteStream; // [rsp+98h] [rbp+50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v35, "MFMkvPropertyHandler::LoadSourceAsync", 98);
  v35 = (char *)this + 1960;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 49);
  v5 = (MkvMfSourceLib::MkvMfSource **)((char *)this + 2008);
  if ( !*((_QWORD *)this + 251) )
  {
    ppByteStream = 0;
    v36 = 0;
    ppAsyncResult = 0;
    Source = MFCreateMFByteStreamOnStream(*((IStream **)this + 115), &ppByteStream);
    if ( Source >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      v33 = GUID_00000000_0000_0000_0000_000000000000;
      v34 = GUID_00000000_0000_0000_0000_000000000000;
      if ( (int)MFCreateTelemetrySession(&v34, &v33, &v36) >= 0 )
        (*(void (__fastcall **)(struct IMFTelemetrySession *, __int64 *))(*(_QWORD *)v36 + 304LL))(
          v36,
          MF_TELEMETRY_FLAG_DO_NOT_LOG);
      Source = MkvMfSourceLib::MkvMfSource::CreateSource(
                 ppByteStream,
                 v36,
                 (struct MkvMfSourceLib::MkvMfSource **)this + 251);
      if ( Source >= 0 )
      {
        *((_BYTE *)*v5 + 524) = 1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
        Source = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 250, 0, &ppAsyncResult);
        if ( Source >= 0 )
        {
          Source = MkvMfSourceLib::MkvMfSource::BeginLoad(*v5, ppAsyncResult);
          if ( Source >= 0 )
            goto LABEL_49;
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
            CallStackTracing::s_wpInstance = v31;
            if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
            {
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v30 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( !*((_BYTE *)v30 + 8) )
            goto LABEL_49;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == Source )
            goto LABEL_49;
          v16 = 121;
        }
        else
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( !*((_BYTE *)v25 + 8) )
            goto LABEL_49;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == Source )
            goto LABEL_49;
          v16 = 119;
        }
      }
      else
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( !*((_BYTE *)v20 + 8) )
          goto LABEL_49;
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)ThreadRelativeContext + 499) == Source )
          goto LABEL_49;
        v16 = 116;
      }
    }
    else
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( !*((_BYTE *)v13 + 8) )
        goto LABEL_49;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == Source )
        goto LABEL_49;
      v16 = 111;
    }
    CallStackContext::TraceFailure(ThreadRelativeContext, "MFMkvPropertyHandler::LoadSourceAsync", v16, Source);
LABEL_49:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppByteStream);
    goto LABEL_50;
  }
  v6 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2, v3, v4);
    CallStackTracing::s_wpInstance = v7;
    if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
    {
      v6 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v6 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  Source = -1072875845;
  if ( *((_BYTE *)v6 + 8) )
  {
    v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
    if ( *((_DWORD *)v9 + 499) != -1072875845 )
      CallStackContext::TraceFailure(v9, "MFMkvPropertyHandler::LoadSourceAsync", 104, -1072875845);
  }
LABEL_50:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 49);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v35);
  return (unsigned int)Source;
}

```

## disassembly

```asm
0x180050060  push    rbp
0x180050062  push    rbx
0x180050063  push    rsi
0x180050064  push    rdi
0x180050065  push    r12
0x180050067  push    r14
0x180050069  mov     rbp, rsp
0x18005006c  sub     rsp, 48h
0x180050070  mov     rdi, rcx
0x180050073  mov     r8d, 62h ; 'b'; int
0x180050079  lea     r12, aMfmkvpropertyh_4; "MFMkvPropertyHandler::LoadSourceAsync"
0x180050080  mov     rdx, r12; char *
0x180050083  lea     rcx, [rbp+arg_0]; this
0x180050087  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005008c  nop
0x18005008d  lea     r14, [rdi+7A8h]
0x180050094  mov     [rbp+arg_0], r14
0x180050098  mov     rcx, r14; lpCriticalSection
0x18005009b  call    cs:__imp_EnterCriticalSection
0x1800500a2  nop     dword ptr [rax+rax+00h]
0x1800500a7  nop
0x1800500a8  lea     rsi, [rdi+7D8h]
0x1800500af  cmp     qword ptr [rsi], 0
0x1800500b3  jz      loc_180050145
0x1800500b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500c0  test    rcx, rcx
0x1800500c3  jnz     short loc_18005010C
0x1800500c5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800500cc  nop     dword ptr [rax+rax+00h]
0x1800500d1  mov     rcx, rax
0x1800500d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500db  test    rax, rax
0x1800500de  jz      short loc_1800500FE
0x1800500e0  mov     rax, [rax]
0x1800500e3  mov     edx, 7F0h
0x1800500e8  mov     rax, [rax+8]
0x1800500ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500f1  test    eax, eax
0x1800500f3  jz      short loc_1800500FE
0x1800500f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800500fc  jmp     short loc_18005010C
0x1800500fe  lea     rcx, qword_1800DBF70; this
0x180050105  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005010c  mov     ebx, 0C00D36BBh
0x180050111  cmp     byte ptr [rcx+8], 0
0x180050115  jz      loc_180050428
0x18005011b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050120  cmp     [rax+7CCh], ebx
0x180050126  jz      loc_180050428
0x18005012c  mov     r9d, ebx; int
0x18005012f  mov     r8d, 68h ; 'h'; int
0x180050135  mov     rdx, r12; char *
0x180050138  mov     rcx, rax; this
0x18005013b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050140  jmp     loc_180050428
0x180050145  mov     [rbp+ppByteStream], 0
0x18005014d  mov     [rbp+arg_8], 0
0x180050155  mov     [rbp+ppAsyncResult], 0
0x18005015d  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x180050161  mov     rcx, [rdi+398h]; pStream
0x180050168  call    cs:__imp_MFCreateMFByteStreamOnStream
0x18005016f  nop     dword ptr [rax+rax+00h]
0x180050174  mov     ebx, eax
0x180050176  test    eax, eax
0x180050178  jns     short loc_1800501F3
0x18005017a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050181  test    rcx, rcx
0x180050184  jnz     short loc_1800501CD
0x180050186  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005018d  nop     dword ptr [rax+rax+00h]
0x180050192  mov     rcx, rax
0x180050195  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005019c  test    rax, rax
0x18005019f  jz      short loc_1800501BF
0x1800501a1  mov     rax, [rax]
0x1800501a4  mov     edx, 7F0h
0x1800501a9  mov     rax, [rax+8]
0x1800501ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501b2  test    eax, eax
0x1800501b4  jz      short loc_1800501BF
0x1800501b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800501bd  jmp     short loc_1800501CD
0x1800501bf  lea     rcx, qword_1800DBF70; this
0x1800501c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800501cd  cmp     byte ptr [rcx+8], 0
0x1800501d1  jz      loc_18005040A
0x1800501d7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800501dc  cmp     [rax+7CCh], ebx
0x1800501e2  jz      loc_18005040A
0x1800501e8  mov     r8d, 6Fh ; 'o'
0x1800501ee  jmp     loc_1800503FB
0x1800501f3  lea     rcx, [rbp+arg_8]
0x1800501f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800501fc  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180050203  movdqu  [rbp+var_28], xmm0
0x180050208  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x18005020d  lea     r8, [rbp+arg_8]
0x180050211  lea     rdx, [rbp+var_28]
0x180050215  lea     rcx, [rbp+var_18]
0x180050219  call    cs:__imp_MFCreateTelemetrySession
0x180050220  nop     dword ptr [rax+rax+00h]
0x180050225  test    eax, eax
0x180050227  js      short loc_180050243
0x180050229  mov     rcx, [rbp+arg_8]
0x18005022d  mov     rax, [rcx]
0x180050230  lea     rdx, MF_TELEMETRY_FLAG_DO_NOT_LOG
0x180050237  mov     rax, [rax+130h]
0x18005023e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050243  mov     r8, rsi; struct MkvMfSourceLib::MkvMfSource **
0x180050246  mov     rdx, [rbp+arg_8]; struct IMFTelemetrySession *
0x18005024a  mov     rcx, [rbp+ppByteStream]; struct IMFByteStream *
0x18005024e  call    ?CreateSource@MkvMfSource@MkvMfSourceLib@@SAJPEAUIMFByteStream@@PEAUIMFTelemetrySession@@PEAPEAV12@@Z; MkvMfSourceLib::MkvMfSource::CreateSource(IMFByteStream *,IMFTelemetrySession *,MkvMfSourceLib::MkvMfSource * *)
0x180050253  mov     ebx, eax
0x180050255  test    eax, eax
0x180050257  jns     short loc_1800502D2
0x180050259  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050260  test    rcx, rcx
0x180050263  jnz     short loc_1800502AC
0x180050265  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005026c  nop     dword ptr [rax+rax+00h]
0x180050271  mov     rcx, rax
0x180050274  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005027b  test    rax, rax
0x18005027e  jz      short loc_18005029E
0x180050280  mov     rax, [rax]
0x180050283  mov     edx, 7F0h
0x180050288  mov     rax, [rax+8]
0x18005028c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050291  test    eax, eax
0x180050293  jz      short loc_18005029E
0x180050295  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005029c  jmp     short loc_1800502AC
0x18005029e  lea     rcx, qword_1800DBF70; this
0x1800502a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800502ac  cmp     byte ptr [rcx+8], 0
0x1800502b0  jz      loc_18005040A
0x1800502b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800502bb  cmp     [rax+7CCh], ebx
0x1800502c1  jz      loc_18005040A
0x1800502c7  mov     r8d, 74h ; 't'
0x1800502cd  jmp     loc_1800503FB
0x1800502d2  mov     rax, [rsi]
0x1800502d5  mov     byte ptr [rax+20Ch], 1
0x1800502dc  lea     rcx, [rbp+ppAsyncResult]
0x1800502e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800502e5  lea     rdx, [rdi+7D0h]; pCallback
0x1800502ec  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x1800502f0  xor     r8d, r8d; punkState
0x1800502f3  xor     ecx, ecx; punkObject
0x1800502f5  call    cs:__imp_MFCreateAsyncResult
0x1800502fc  nop     dword ptr [rax+rax+00h]
0x180050301  mov     ebx, eax
0x180050303  test    eax, eax
0x180050305  jns     short loc_18005037D
0x180050307  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005030e  test    rcx, rcx
0x180050311  jnz     short loc_18005035A
0x180050313  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005031a  nop     dword ptr [rax+rax+00h]
0x18005031f  mov     rcx, rax
0x180050322  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180050329  test    rax, rax
0x18005032c  jz      short loc_18005034C
0x18005032e  mov     rax, [rax]
0x180050331  mov     edx, 7F0h
0x180050336  mov     rax, [rax+8]
0x18005033a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005033f  test    eax, eax
0x180050341  jz      short loc_18005034C
0x180050343  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005034a  jmp     short loc_18005035A
0x18005034c  lea     rcx, qword_1800DBF70; this
0x180050353  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005035a  cmp     byte ptr [rcx+8], 0
0x18005035e  jz      loc_18005040A
0x180050364  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180050369  cmp     [rax+7CCh], ebx
0x18005036f  jz      loc_18005040A
0x180050375  mov     r8d, 77h ; 'w'
0x18005037b  jmp     short loc_1800503FB
0x18005037d  mov     rdx, [rbp+ppAsyncResult]; struct IMFAsyncResult *
0x180050381  mov     rcx, [rsi]; this
0x180050384  call    ?BeginLoad@MkvMfSource@MkvMfSourceLib@@QEAAJPEAUIMFAsyncResult@@@Z; MkvMfSourceLib::MkvMfSource::BeginLoad(IMFAsyncResult *)
0x180050389  mov     ebx, eax
0x18005038b  test    eax, eax
0x18005038d  jns     short loc_18005040A
0x18005038f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180050396  test    rcx, rcx
0x180050399  jnz     short loc_1800503E2
0x18005039b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800503a2  nop     dword ptr [rax+rax+00h]
0x1800503a7  mov     rcx, rax
0x1800503aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800503b1  test    rax, rax
0x1800503b4  jz      short loc_1800503D4
0x1800503b6  mov     rax, [rax]
0x1800503b9  mov     edx, 7F0h
0x1800503be  mov     rax, [rax+8]
0x1800503c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503c7  test    eax, eax
0x1800503c9  jz      short loc_1800503D4
0x1800503cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800503d2  jmp     short loc_1800503E2
0x1800503d4  lea     rcx, qword_1800DBF70; this
0x1800503db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800503e2  cmp     byte ptr [rcx+8], 0
0x1800503e6  jz      short loc_18005040A
0x1800503e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800503ed  cmp     [rax+7CCh], ebx
0x1800503f3  jz      short loc_18005040A
0x1800503f5  mov     r8d, 79h ; 'y'; int
0x1800503fb  mov     r9d, ebx; int
0x1800503fe  mov     rdx, r12; char *
0x180050401  mov     rcx, rax; this
0x180050404  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180050409  nop
0x18005040a  lea     rcx, [rbp+ppAsyncResult]
0x18005040e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050413  nop
0x180050414  lea     rcx, [rbp+arg_8]
0x180050418  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005041d  nop
0x18005041e  lea     rcx, [rbp+ppByteStream]
0x180050422  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180050427  nop
0x180050428  mov     rcx, r14; lpCriticalSection
0x18005042b  call    cs:__imp_LeaveCriticalSection
0x180050432  nop     dword ptr [rax+rax+00h]
0x180050437  nop
0x180050438  lea     rcx, [rbp+arg_0]; this
0x18005043c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180050441  mov     eax, ebx
0x180050443  add     rsp, 48h
0x180050447  pop     r14
0x180050449  pop     r12
0x18005044b  pop     rdi
0x18005044c  pop     rsi
0x18005044d  pop     rbx
0x18005044e  pop     rbp
0x18005044f  retn
```
