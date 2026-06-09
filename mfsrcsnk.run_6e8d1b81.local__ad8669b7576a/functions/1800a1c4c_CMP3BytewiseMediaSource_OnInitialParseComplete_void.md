# CMP3BytewiseMediaSource::OnInitialParseComplete(void)

- ea: `0x1800a1c4c`
- end: `0x1800a1faf`
- name: `?OnInitialParseComplete@CMP3BytewiseMediaSource@@IEAAJXZ`
- size: `867`
- prototype: `__int64 __fastcall(CMP3BytewiseMediaSource *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b9ac`
- `0x18000c4e0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18004c264`
- `0x180073b14`
- `0x180076fc0`
- `0x1800a1c4c`
- `0x1800a1fb8`
- `0x18014786c`
- `0x18014c4c0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1f4b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a1f3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a1f3d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a1f77`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a1f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1f6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1f6d`
- `MFPlat!MFPutWorkItemEx2` at `0x1800a1f23`
- `MFPlat!MFPutWorkItemEx2` at `0x1800a1f23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1e1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1e1f`

## string_xrefs

- `0x1800a1c86`: `CMP3BytewiseMediaSource::OnInitialParseComplete`
- `0x1800a1d95`: `CMP3BytewiseMediaSource::OnInitialParseComplete`
- `0x1800a1e77`: `CMP3BytewiseMediaSource::OnInitialParseComplete`

## pseudocode

```c
__int64 __fastcall CMP3BytewiseMediaSource::OnInitialParseComplete(CMP3BytewiseMediaSource *this)
{
  DWORD v2; // r14d
  unsigned int v3; // ecx
  unsigned int v4; // eax
  int v5; // r9d
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  int PresentationDescriptor; // r15d
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  struct CallStackContext *v12; // rdi
  int v13; // ebx
  __int128 *v14; // rax
  __int128 v15; // xmm0
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v22; // sf
  _BYTE v24[16]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v25; // [rsp+80h] [rbp+30h] BYREF
  int v26; // [rsp+88h] [rbp+38h] BYREF

  v2 = 1;
  v3 = *((_DWORD *)this + 259);
  if ( v3 )
  {
    v4 = *((_DWORD *)this + 258) / v3;
    *((_DWORD *)this + 238) = v4;
    *((_DWORD *)this + 190) = v4 >> 3;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v25,
      "CMP3BytewiseMediaSource::OnInitialParseComplete",
      1001);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 139) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 139) + 296LL))(*((_QWORD *)this + 139));
      v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 139) + 280LL))(
                        *((_QWORD *)this + 139),
                        v24);
      *((_DWORD *)ThreadRelativeContext + 504) = v7;
      *((_OWORD *)ThreadRelativeContext + 125) = v8;
    }
    if ( (unsigned __int8)byte_1801B110B >= 8u )
      WPP_SF_qddd(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        93,
        &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
        this,
        *((_DWORD *)this + 238),
        *((_DWORD *)this + 258),
        *((_DWORD *)this + 259));
    LOBYTE(v5) = 1;
    v25 = *((unsigned int *)this + 238);
    CAggregateTelemetryLazyUpdate<CMP3SourceAggregateData,enum MP3SourceTelemetryType,MP3SourceTelemetryData *,0,0>::AddData(
      (_DWORD)this + 1120,
      2,
      (unsigned int)&v25,
      v5,
      1);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
  }
  PresentationDescriptor = CMediaSourceBase::CreatePresentationDescriptor(this);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v25,
    "CMP3BytewiseMediaSource::OnInitialParseComplete",
    1013);
  v11 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 139) )
  {
    v12 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 139) + 296LL))(*((_QWORD *)this + 139));
    v14 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 139) + 280LL))(
                        *((_QWORD *)this + 139),
                        v24);
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    v15 = *v14;
    *((_DWORD *)v12 + 504) = v13;
    *((_OWORD *)v12 + 125) = v15;
  }
  if ( PresentationDescriptor >= 0 )
  {
    *((_DWORD *)this + 236) = 1;
    CMP3BytewiseMediaSource::ConfigureByteStreamBuffering(this, v10);
    v18 = *((_QWORD *)this + 127);
    v19 = *(_QWORD *)(v18 + 40);
    *(_DWORD *)(v18 + 48) = 0;
    if ( v19 )
    {
      v26 = 0;
      LODWORD(v25) = 0;
      if ( (*(int (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v19 + 24LL))(v19, &v26, &v25) >= 0 )
        v2 = v25;
      else
        LODWORD(v25) = 1;
      MFPutWorkItemEx2(v2, 0, (IMFAsyncResult *)v18);
    }
    else
    {
      if ( !*(_QWORD *)(v18 + 56) )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        if ( EventW )
        {
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 56), (signed __int64)EventW, 0) )
            CloseHandle(EventW);
        }
        else
        {
          LastError = GetLastError();
          v22 = LastError < 0;
          if ( LastError > 0 )
            v22 = 1;
          if ( v22 )
            goto LABEL_36;
        }
      }
      SetEvent(*(HANDLE *)(v18 + 56));
    }
LABEL_36:
    ComSmartPtr<CBaseStreamSink>::operator=((char *)this + 1016);
    *((_DWORD *)this + 210) = 0;
    goto LABEL_37;
  }
  if ( !v11 )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v17 + 499) != PresentationDescriptor )
      CallStackContext::TraceFailure(
        v17,
        "CMP3BytewiseMediaSource::OnInitialParseComplete",
        1013,
        PresentationDescriptor);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
      this,
      PresentationDescriptor);
LABEL_37:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
  return (unsigned int)PresentationDescriptor;
}

```

## disassembly

```asm
0x1800a1c4c  mov     [rsp-28h+arg_10], rbx
0x1800a1c51  push    rbp
0x1800a1c52  push    rsi
0x1800a1c53  push    rdi
0x1800a1c54  push    r14
0x1800a1c56  push    r15
0x1800a1c58  mov     rbp, rsp
0x1800a1c5b  sub     rsp, 50h
0x1800a1c5f  mov     rsi, rcx
0x1800a1c62  mov     r14d, 1
0x1800a1c68  mov     ecx, [rcx+40Ch]
0x1800a1c6e  test    ecx, ecx
0x1800a1c70  jz      loc_1800A1D87
0x1800a1c76  mov     eax, [rsi+408h]
0x1800a1c7c  xor     edx, edx
0x1800a1c7e  div     ecx
0x1800a1c80  mov     r8d, 3E9h; int
0x1800a1c86  lea     rdx, aCmp3bytewiseme_13; "CMP3BytewiseMediaSource::OnInitialParse"...
0x1800a1c8d  mov     [rsi+3B8h], eax
0x1800a1c93  lea     rcx, [rbp+arg_0]; this
0x1800a1c97  shr     eax, 3
0x1800a1c9a  mov     [rsi+2F8h], eax
0x1800a1ca0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a1ca5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a1cac  cmp     byte ptr [rcx+8], 0
0x1800a1cb0  jz      short loc_1800A1D07
0x1800a1cb2  cmp     qword ptr [rsi+458h], 0
0x1800a1cba  jz      short loc_1800A1D07
0x1800a1cbc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1cc1  mov     rcx, [rsi+458h]
0x1800a1cc8  mov     rdi, rax
0x1800a1ccb  mov     rdx, [rcx]
0x1800a1cce  mov     rax, [rdx+128h]
0x1800a1cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1cda  mov     rcx, [rsi+458h]
0x1800a1ce1  mov     ebx, eax
0x1800a1ce3  mov     rdx, [rcx]
0x1800a1ce6  mov     rax, [rdx+118h]
0x1800a1ced  lea     rdx, [rbp+var_10]
0x1800a1cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1cf6  movups  xmm0, xmmword ptr [rax]
0x1800a1cf9  mov     [rdi+7E0h], ebx
0x1800a1cff  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a1d07  cmp     cs:byte_1801B110B, 8
0x1800a1d0e  jb      short loc_1800A1D50
0x1800a1d10  mov     eax, [rsi+40Ch]
0x1800a1d16  lea     r8, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x1800a1d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1d24  mov     edx, 5Dh ; ']'
0x1800a1d29  mov     [rsp+50h+var_20], eax
0x1800a1d2d  mov     r9, rsi
0x1800a1d30  mov     eax, [rsi+408h]
0x1800a1d36  mov     [rsp+50h+var_28], eax
0x1800a1d3a  mov     eax, [rsi+3B8h]
0x1800a1d40  mov     rcx, [rcx+88h]
0x1800a1d47  mov     [rsp+50h+var_30], eax
0x1800a1d4b  call    WPP_SF_qddd
0x1800a1d50  mov     eax, [rsi+3B8h]
0x1800a1d56  lea     rcx, [rsi+460h]
0x1800a1d5d  mov     [rbp+arg_0], 0
0x1800a1d65  lea     r8, [rbp+arg_0]
0x1800a1d69  mov     r9b, r14b
0x1800a1d6c  mov     dword ptr [rbp+arg_0], eax
0x1800a1d6f  mov     edx, 2
0x1800a1d74  mov     byte ptr [rsp+50h+var_30], r14b
0x1800a1d79  call    ?AddData@?$CAggregateTelemetryLazyUpdate@VCMP3SourceAggregateData@@W4MP3SourceTelemetryType@@PEATMP3SourceTelemetryData@@$0A@$0A@@@UEAAXW4MP3SourceTelemetryType@@PEATMP3SourceTelemetryData@@_N2@Z; CAggregateTelemetryLazyUpdate<CMP3SourceAggregateData,MP3SourceTelemetryType,MP3SourceTelemetryData *,0,0>::AddData(MP3SourceTelemetryType,MP3SourceTelemetryData *,bool,bool)
0x1800a1d7e  lea     rcx, [rbp+arg_0]; this
0x1800a1d82  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a1d87  mov     rcx, rsi; this
0x1800a1d8a  call    ?CreatePresentationDescriptor@CMediaSourceBase@@IEAAJXZ; CMediaSourceBase::CreatePresentationDescriptor(void)
0x1800a1d8f  mov     r8d, 3F5h; int
0x1800a1d95  lea     rdx, aCmp3bytewiseme_13; "CMP3BytewiseMediaSource::OnInitialParse"...
0x1800a1d9c  lea     rcx, [rbp+arg_0]; this
0x1800a1da0  mov     r15d, eax
0x1800a1da3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a1da8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a1daf  cmp     byte ptr [rcx+8], 0
0x1800a1db3  jz      short loc_1800A1E11
0x1800a1db5  cmp     qword ptr [rsi+458h], 0
0x1800a1dbd  jz      short loc_1800A1E11
0x1800a1dbf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1dc4  mov     rcx, [rsi+458h]
0x1800a1dcb  mov     rdi, rax
0x1800a1dce  mov     rdx, [rcx]
0x1800a1dd1  mov     rax, [rdx+128h]
0x1800a1dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1ddd  mov     rcx, [rsi+458h]
0x1800a1de4  mov     ebx, eax
0x1800a1de6  mov     rdx, [rcx]
0x1800a1de9  mov     rax, [rdx+118h]
0x1800a1df0  lea     rdx, [rbp+var_10]
0x1800a1df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1df9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1e00  movups  xmm0, xmmword ptr [rax]
0x1800a1e03  mov     [rdi+7E0h], ebx
0x1800a1e09  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a1e11  test    r15d, r15d
0x1800a1e14  jns     loc_1800A1EC2
0x1800a1e1a  test    rcx, rcx
0x1800a1e1d  jnz     short loc_1800A1E60
0x1800a1e1f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1e25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1e2c  mov     rcx, rax
0x1800a1e2f  test    rax, rax
0x1800a1e32  jz      short loc_1800A1E52
0x1800a1e34  mov     rax, [rax]
0x1800a1e37  mov     edx, 7F0h
0x1800a1e3c  mov     rax, [rax+8]
0x1800a1e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1e45  test    eax, eax
0x1800a1e47  jz      short loc_1800A1E52
0x1800a1e49  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1e50  jmp     short loc_1800A1E60
0x1800a1e52  lea     rcx, qword_1801B07E0; this
0x1800a1e59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1e60  cmp     byte ptr [rcx+8], 0
0x1800a1e64  jz      short loc_1800A1E8C
0x1800a1e66  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1e6b  cmp     [rax+7CCh], r15d
0x1800a1e72  jz      short loc_1800A1E8C
0x1800a1e74  mov     r9d, r15d; int
0x1800a1e77  lea     rdx, aCmp3bytewiseme_13; "CMP3BytewiseMediaSource::OnInitialParse"...
0x1800a1e7e  mov     r8d, 3F5h; int
0x1800a1e84  mov     rcx, rax; this
0x1800a1e87  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1e8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1800a1e93  jb      loc_1800A1F8F
0x1800a1e99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1ea0  lea     r8, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x1800a1ea7  mov     edx, 5Eh ; '^'
0x1800a1eac  mov     [rsp+50h+var_30], r15d
0x1800a1eb1  mov     r9, rsi
0x1800a1eb4  mov     rcx, [rcx+10h]
0x1800a1eb8  call    WPP_SF_qD
0x1800a1ebd  jmp     loc_1800A1F8F
0x1800a1ec2  mov     rcx, rsi; this
0x1800a1ec5  mov     [rsi+3B0h], r14d
0x1800a1ecc  call    ?ConfigureByteStreamBuffering@CMP3BytewiseMediaSource@@AEAAJH@Z; CMP3BytewiseMediaSource::ConfigureByteStreamBuffering(int)
0x1800a1ed1  lea     rdi, [rsi+3F8h]
0x1800a1ed8  mov     rbx, [rdi]
0x1800a1edb  mov     rcx, [rbx+28h]
0x1800a1edf  mov     dword ptr [rbx+30h], 0
0x1800a1ee6  test    rcx, rcx
0x1800a1ee9  jz      short loc_1800A1F2B
0x1800a1eeb  mov     [rbp+arg_8], 0
0x1800a1ef2  lea     r8, [rbp+arg_0]
0x1800a1ef6  mov     dword ptr [rbp+arg_0], 0
0x1800a1efd  lea     rdx, [rbp+arg_8]
0x1800a1f01  mov     rax, [rcx]
0x1800a1f04  mov     rax, [rax+18h]
0x1800a1f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f0d  test    eax, eax
0x1800a1f0f  jns     short loc_1800A1F17
0x1800a1f11  mov     dword ptr [rbp+arg_0], r14d
0x1800a1f15  jmp     short loc_1800A1F1B
0x1800a1f17  mov     r14d, dword ptr [rbp+arg_0]
0x1800a1f1b  mov     r8, rbx; pResult
0x1800a1f1e  xor     edx, edx; Priority
0x1800a1f20  mov     ecx, r14d; dwQueue
0x1800a1f23  call    cs:__imp_MFPutWorkItemEx2
0x1800a1f29  jmp     short loc_1800A1F7D
0x1800a1f2b  cmp     qword ptr [rbx+38h], 0
0x1800a1f30  jnz     short loc_1800A1F73
0x1800a1f32  xor     r9d, r9d; lpName
0x1800a1f35  xor     r8d, r8d; bInitialState
0x1800a1f38  mov     edx, r14d; bManualReset
0x1800a1f3b  xor     ecx, ecx; lpEventAttributes
0x1800a1f3d  call    cs:__imp_CreateEventW
0x1800a1f43  mov     rcx, rax; hObject
0x1800a1f46  test    rax, rax
0x1800a1f49  jnz     short loc_1800A1F63
0x1800a1f4b  call    cs:__imp_GetLastError
0x1800a1f51  test    eax, eax
0x1800a1f53  jle     short loc_1800A1F5F
0x1800a1f55  movzx   eax, ax
0x1800a1f58  or      eax, 80070000h
0x1800a1f5d  test    eax, eax
0x1800a1f5f  js      short loc_1800A1F7D
0x1800a1f61  jmp     short loc_1800A1F73
0x1800a1f63  xor     eax, eax
0x1800a1f65  lock cmpxchg [rbx+38h], rcx
0x1800a1f6b  jz      short loc_1800A1F73
0x1800a1f6d  call    cs:__imp_CloseHandle
0x1800a1f73  mov     rcx, [rbx+38h]; hEvent
0x1800a1f77  call    cs:__imp_SetEvent
0x1800a1f7d  mov     rcx, rdi
0x1800a1f80  call    ??4?$ComSmartPtr@VCBaseStreamSink@@@@QEAAPEAVCBaseStreamSink@@PEAV1@@Z; ComSmartPtr<CBaseStreamSink>::operator=(CBaseStreamSink *)
0x1800a1f85  mov     dword ptr [rsi+348h], 0
0x1800a1f8f  lea     rcx, [rbp+arg_0]; this
0x1800a1f93  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a1f98  mov     rbx, [rsp+50h+arg_10]
0x1800a1fa0  mov     eax, r15d
0x1800a1fa3  add     rsp, 50h
0x1800a1fa7  pop     r15
0x1800a1fa9  pop     r14
0x1800a1fab  pop     rdi
0x1800a1fac  pop     rsi
0x1800a1fad  pop     rbp
0x1800a1fae  retn
```
