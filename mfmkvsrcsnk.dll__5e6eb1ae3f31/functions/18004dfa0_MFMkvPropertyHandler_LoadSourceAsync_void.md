# MFMkvPropertyHandler::LoadSourceAsync(void)

- ea: `0x18004dfa0`
- end: `0x18004e354`
- name: `?LoadSourceAsync@MFMkvPropertyHandler@@AEAAJXZ`
- size: `948`
- prototype: `__int64 __fastcall(MFMkvPropertyHandler *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004dd50`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000e060`
- `0x18001065c`
- `0x18004dfa0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dfdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dfdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e335`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e335`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dfff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e0b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e187`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e229`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e2ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004dfff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e0b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e187`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e229`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e2ab`
- `MFPlat!MFCreateAsyncResult` at `0x18004e211`
- `MFPlat!MFCreateAsyncResult` at `0x18004e211`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18004e09c`
- `MFPlat!MFCreateMFByteStreamOnStream` at `0x18004e09c`
- `MFPlat!MFCreateTelemetrySession` at `0x18004e141`
- `MFPlat!MFCreateTelemetrySession` at `0x18004e141`

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
              v30 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v25 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v20 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v13 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v6 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18004dfa0  push    rbp
0x18004dfa2  push    rbx
0x18004dfa3  push    rsi
0x18004dfa4  push    rdi
0x18004dfa5  push    r12
0x18004dfa7  push    r14
0x18004dfa9  mov     rbp, rsp
0x18004dfac  sub     rsp, 48h
0x18004dfb0  mov     rdi, rcx
0x18004dfb3  mov     r8d, 62h ; 'b'; int
0x18004dfb9  lea     r12, aMfmkvpropertyh_4; "MFMkvPropertyHandler::LoadSourceAsync"
0x18004dfc0  mov     rdx, r12; char *
0x18004dfc3  lea     rcx, [rbp+arg_0]; this
0x18004dfc7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004dfcc  nop
0x18004dfcd  lea     r14, [rdi+7A8h]
0x18004dfd4  mov     [rbp+arg_0], r14
0x18004dfd8  mov     rcx, r14; lpCriticalSection
0x18004dfdb  call    cs:__imp_EnterCriticalSection
0x18004dfe1  nop
0x18004dfe2  lea     rsi, [rdi+7D8h]
0x18004dfe9  cmp     qword ptr [rsi], 0
0x18004dfed  jz      loc_18004E079
0x18004dff3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004dffa  test    rcx, rcx
0x18004dffd  jnz     short loc_18004E040
0x18004dfff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e005  mov     rcx, rax
0x18004e008  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e00f  test    rax, rax
0x18004e012  jz      short loc_18004E032
0x18004e014  mov     rax, [rax]
0x18004e017  mov     edx, 7F0h
0x18004e01c  mov     rax, [rax+8]
0x18004e020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e025  test    eax, eax
0x18004e027  jz      short loc_18004E032
0x18004e029  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e030  jmp     short loc_18004E040
0x18004e032  lea     rcx, qword_1800D6F70; this
0x18004e039  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e040  mov     ebx, 0C00D36BBh
0x18004e045  cmp     byte ptr [rcx+8], 0
0x18004e049  jz      loc_18004E332
0x18004e04f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e054  cmp     [rax+7CCh], ebx
0x18004e05a  jz      loc_18004E332
0x18004e060  mov     r9d, ebx; int
0x18004e063  mov     r8d, 68h ; 'h'; int
0x18004e069  mov     rdx, r12; char *
0x18004e06c  mov     rcx, rax; this
0x18004e06f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e074  jmp     loc_18004E332
0x18004e079  mov     [rbp+ppByteStream], 0
0x18004e081  mov     [rbp+arg_8], 0
0x18004e089  mov     [rbp+ppAsyncResult], 0
0x18004e091  lea     rdx, [rbp+ppByteStream]; ppByteStream
0x18004e095  mov     rcx, [rdi+398h]; pStream
0x18004e09c  call    cs:__imp_MFCreateMFByteStreamOnStream
0x18004e0a2  mov     ebx, eax
0x18004e0a4  test    eax, eax
0x18004e0a6  jns     short loc_18004E11B
0x18004e0a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e0af  test    rcx, rcx
0x18004e0b2  jnz     short loc_18004E0F5
0x18004e0b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e0ba  mov     rcx, rax
0x18004e0bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e0c4  test    rax, rax
0x18004e0c7  jz      short loc_18004E0E7
0x18004e0c9  mov     rax, [rax]
0x18004e0cc  mov     edx, 7F0h
0x18004e0d1  mov     rax, [rax+8]
0x18004e0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0da  test    eax, eax
0x18004e0dc  jz      short loc_18004E0E7
0x18004e0de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e0e5  jmp     short loc_18004E0F5
0x18004e0e7  lea     rcx, qword_1800D6F70; this
0x18004e0ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e0f5  cmp     byte ptr [rcx+8], 0
0x18004e0f9  jz      loc_18004E314
0x18004e0ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e104  cmp     [rax+7CCh], ebx
0x18004e10a  jz      loc_18004E314
0x18004e110  mov     r8d, 6Fh ; 'o'
0x18004e116  jmp     loc_18004E305
0x18004e11b  lea     rcx, [rbp+arg_8]
0x18004e11f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e124  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004e12b  movdqu  [rbp+var_28], xmm0
0x18004e130  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x18004e135  lea     r8, [rbp+arg_8]
0x18004e139  lea     rdx, [rbp+var_28]
0x18004e13d  lea     rcx, [rbp+var_18]
0x18004e141  call    cs:__imp_MFCreateTelemetrySession
0x18004e147  test    eax, eax
0x18004e149  js      short loc_18004E165
0x18004e14b  mov     rcx, [rbp+arg_8]
0x18004e14f  mov     rax, [rcx]
0x18004e152  lea     rdx, MF_TELEMETRY_FLAG_DO_NOT_LOG
0x18004e159  mov     rax, [rax+130h]
0x18004e160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e165  mov     r8, rsi; struct MkvMfSourceLib::MkvMfSource **
0x18004e168  mov     rdx, [rbp+arg_8]; struct IMFTelemetrySession *
0x18004e16c  mov     rcx, [rbp+ppByteStream]; struct IMFByteStream *
0x18004e170  call    ?CreateSource@MkvMfSource@MkvMfSourceLib@@SAJPEAUIMFByteStream@@PEAUIMFTelemetrySession@@PEAPEAV12@@Z; MkvMfSourceLib::MkvMfSource::CreateSource(IMFByteStream *,IMFTelemetrySession *,MkvMfSourceLib::MkvMfSource * *)
0x18004e175  mov     ebx, eax
0x18004e177  test    eax, eax
0x18004e179  jns     short loc_18004E1EE
0x18004e17b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e182  test    rcx, rcx
0x18004e185  jnz     short loc_18004E1C8
0x18004e187  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e18d  mov     rcx, rax
0x18004e190  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e197  test    rax, rax
0x18004e19a  jz      short loc_18004E1BA
0x18004e19c  mov     rax, [rax]
0x18004e19f  mov     edx, 7F0h
0x18004e1a4  mov     rax, [rax+8]
0x18004e1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1ad  test    eax, eax
0x18004e1af  jz      short loc_18004E1BA
0x18004e1b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e1b8  jmp     short loc_18004E1C8
0x18004e1ba  lea     rcx, qword_1800D6F70; this
0x18004e1c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e1c8  cmp     byte ptr [rcx+8], 0
0x18004e1cc  jz      loc_18004E314
0x18004e1d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e1d7  cmp     [rax+7CCh], ebx
0x18004e1dd  jz      loc_18004E314
0x18004e1e3  mov     r8d, 74h ; 't'
0x18004e1e9  jmp     loc_18004E305
0x18004e1ee  mov     rax, [rsi]
0x18004e1f1  mov     byte ptr [rax+20Ch], 1
0x18004e1f8  lea     rcx, [rbp+ppAsyncResult]
0x18004e1fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e201  lea     rdx, [rdi+7D0h]; pCallback
0x18004e208  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x18004e20c  xor     r8d, r8d; punkState
0x18004e20f  xor     ecx, ecx; punkObject
0x18004e211  call    cs:__imp_MFCreateAsyncResult
0x18004e217  mov     ebx, eax
0x18004e219  test    eax, eax
0x18004e21b  jns     short loc_18004E28D
0x18004e21d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e224  test    rcx, rcx
0x18004e227  jnz     short loc_18004E26A
0x18004e229  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e22f  mov     rcx, rax
0x18004e232  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e239  test    rax, rax
0x18004e23c  jz      short loc_18004E25C
0x18004e23e  mov     rax, [rax]
0x18004e241  mov     edx, 7F0h
0x18004e246  mov     rax, [rax+8]
0x18004e24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e24f  test    eax, eax
0x18004e251  jz      short loc_18004E25C
0x18004e253  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e25a  jmp     short loc_18004E26A
0x18004e25c  lea     rcx, qword_1800D6F70; this
0x18004e263  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e26a  cmp     byte ptr [rcx+8], 0
0x18004e26e  jz      loc_18004E314
0x18004e274  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e279  cmp     [rax+7CCh], ebx
0x18004e27f  jz      loc_18004E314
0x18004e285  mov     r8d, 77h ; 'w'
0x18004e28b  jmp     short loc_18004E305
0x18004e28d  mov     rdx, [rbp+ppAsyncResult]; struct IMFAsyncResult *
0x18004e291  mov     rcx, [rsi]; this
0x18004e294  call    ?BeginLoad@MkvMfSource@MkvMfSourceLib@@QEAAJPEAUIMFAsyncResult@@@Z; MkvMfSourceLib::MkvMfSource::BeginLoad(IMFAsyncResult *)
0x18004e299  mov     ebx, eax
0x18004e29b  test    eax, eax
0x18004e29d  jns     short loc_18004E314
0x18004e29f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e2a6  test    rcx, rcx
0x18004e2a9  jnz     short loc_18004E2EC
0x18004e2ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e2b1  mov     rcx, rax
0x18004e2b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e2bb  test    rax, rax
0x18004e2be  jz      short loc_18004E2DE
0x18004e2c0  mov     rax, [rax]
0x18004e2c3  mov     edx, 7F0h
0x18004e2c8  mov     rax, [rax+8]
0x18004e2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2d1  test    eax, eax
0x18004e2d3  jz      short loc_18004E2DE
0x18004e2d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e2dc  jmp     short loc_18004E2EC
0x18004e2de  lea     rcx, qword_1800D6F70; this
0x18004e2e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e2ec  cmp     byte ptr [rcx+8], 0
0x18004e2f0  jz      short loc_18004E314
0x18004e2f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e2f7  cmp     [rax+7CCh], ebx
0x18004e2fd  jz      short loc_18004E314
0x18004e2ff  mov     r8d, 79h ; 'y'; int
0x18004e305  mov     r9d, ebx; int
0x18004e308  mov     rdx, r12; char *
0x18004e30b  mov     rcx, rax; this
0x18004e30e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e313  nop
0x18004e314  lea     rcx, [rbp+ppAsyncResult]
0x18004e318  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e31d  nop
0x18004e31e  lea     rcx, [rbp+arg_8]
0x18004e322  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e327  nop
0x18004e328  lea     rcx, [rbp+ppByteStream]
0x18004e32c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e331  nop
0x18004e332  mov     rcx, r14; lpCriticalSection
0x18004e335  call    cs:__imp_LeaveCriticalSection
0x18004e33b  nop
0x18004e33c  lea     rcx, [rbp+arg_0]; this
0x18004e340  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004e345  mov     eax, ebx
0x18004e347  add     rsp, 48h
0x18004e34b  pop     r14
0x18004e34d  pop     r12
0x18004e34f  pop     rdi
0x18004e350  pop     rsi
0x18004e351  pop     rbx
0x18004e352  pop     rbp
0x18004e353  retn
```
