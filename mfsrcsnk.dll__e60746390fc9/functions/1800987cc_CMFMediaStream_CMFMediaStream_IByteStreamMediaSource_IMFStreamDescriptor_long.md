# CMFMediaStream::CMFMediaStream(IByteStreamMediaSource *,IMFStreamDescriptor *,long *)

- ea: `0x1800987cc`
- end: `0x180098dd0`
- name: `??0CMFMediaStream@@IEAA@PEAVIByteStreamMediaSource@@PEAUIMFStreamDescriptor@@PEAJ@Z`
- size: `1540`
- prototype: `CMFMediaStream *__fastcall(CMFMediaStream *__hidden this, struct IByteStreamMediaSource *, struct IMFStreamDescriptor *, int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801497a0`

## callees

- `0x1800041d0`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180047a00`
- `0x18006c6b0`
- `0x180073b14`
- `0x1800987cc`
- `0x1800cd1a4`
- `0x18010ae30`
- `0x180149188`
- `0x18014919c`
- `0x180149b84`
- `0x18014b6b0`
- `0x18014b720`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180098868`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180098868`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800989f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098af0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098ba0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098c41`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800989f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098af0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098ba0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180098c41`
- `MFPlat!MFGetConfigurationDWORD` at `0x180098d08`
- `MFPlat!MFGetConfigurationDWORD` at `0x180098d3a`
- `MFPlat!MFGetConfigurationDWORD` at `0x180098d08`
- `MFPlat!MFGetConfigurationDWORD` at `0x180098d3a`

## pseudocode

```c
CMFMediaStream *__fastcall CMFMediaStream::CMFMediaStream(
        CMFMediaStream *this,
        struct IByteStreamMediaSource *a2,
        struct IMFStreamDescriptor *a3,
        int *a4)
{
  _QWORD *v7; // rbp
  __int64 v8; // rdx
  int v9; // ebx
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  _DWORD v29[22]; // [rsp+40h] [rbp-58h] BYREF
  char v30; // [rsp+A0h] [rbp+8h] BYREF
  struct IByteStreamMediaSource *v31; // [rsp+A8h] [rbp+10h]
  unsigned int v32; // [rsp+B0h] [rbp+18h] BYREF
  int *v33; // [rsp+B8h] [rbp+20h]

  v33 = a4;
  v31 = a2;
  CAudioBurstBufferStream::CAudioBurstBufferStream((CMFMediaStream *)((char *)this + 40));
  _InterlockedIncrement(&dword_1801B079C);
  *(_QWORD *)this = &CMFMediaStream::`vftable'{for `IMFGetService'};
  *((_QWORD *)this + 1) = &CMFMediaStream::`vftable'{for `IMFMediaStream'};
  *((_QWORD *)this + 2) = &CMFMediaStream::`vftable'{for `IMFQualityAdvise'};
  *((_QWORD *)this + 3) = &CMFMediaStream::`vftable'{for `IMFQualityAdviseInternal'};
  *((_QWORD *)this + 4) = &CMFMediaStream::`vftable'{for `IMFSampleProtection'};
  *((_QWORD *)this + 5) = &CMFMediaStream::`vftable'{for `CAudioBurstBufferStream'};
  CMFMediaStream::CompleteEOSAsyncCallback::CompleteEOSAsyncCallback((CMFMediaStream *)((char *)this + 120));
  CMFMediaStream::RequestMoreSamplesAsyncCallback::RequestMoreSamplesAsyncCallback((CMFMediaStream *)((char *)this + 128));
  *((_DWORD *)this + 34) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_DWORD *)this + 53) = 1;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 30000000;
  *((_QWORD *)this + 30) = 50000000;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 4;
  *((_DWORD *)this + 68) = 0;
  CMFMediaEventGenerator::CMFMediaEventGenerator((CMFMediaStream *)((char *)this + 280), a4);
  v7 = (_QWORD *)((char *)this + 400);
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = a3;
  if ( a3 )
    ((void (__fastcall *)(struct IMFStreamDescriptor *))a3->lpVtbl->AddRef)(a3);
  *((_DWORD *)this + 109) = 0;
  *((_DWORD *)this + 108) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_DWORD *)this + 114) = 0;
  *((_DWORD *)this + 220) = 0;
  *((_QWORD *)this + 109) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 111) = 0;
  *((_QWORD *)this + 112) = 0;
  *((_DWORD *)this + 226) = 0;
  *((_DWORD *)this + 332) = 0;
  *((_QWORD *)this + 165) = 0;
  *((_QWORD *)this + 164) = 0;
  *((_QWORD *)this + 163) = 0;
  *((_DWORD *)this + 334) = 0;
  *((_QWORD *)this + 168) = 0;
  *((_DWORD *)this + 338) = 0;
  *((_QWORD *)this + 170) = 0;
  *((_DWORD *)this + 342) = 0;
  *((_DWORD *)this + 343) = 1065353216;
  CMFAttributesImpl<IMFAttributes,CMFCSLock>::CMFAttributesImpl<IMFAttributes,CMFCSLock>((char *)this + 1376);
  *((_QWORD *)this + 172) = &CMFMediaStream::CMFNotifyAttributes_ParentClass::`vftable';
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v30, "CMFMediaStream::CMFMediaStream", 515);
  v9 = *v33;
  if ( *v33 >= 0 )
  {
    ComSmartPtr<CMPEGFrame>::operator=((char *)this + 400, v31);
    (**(void (__fastcall ***)(_QWORD, GUID *, char *))*v7)(*v7, &IID_IMFSampleProtection, (char *)this + 1360);
    v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 51) + 264LL))(
           *((_QWORD *)this + 51),
           (char *)this + 432);
    if ( v9 >= 0 )
    {
      *((GUID *)this + 26) = GUID_00000000_0000_0000_0000_000000000000;
      v9 = CMFMediaStream::DetermineMediaType(this);
      if ( v9 >= 0 )
      {
        v9 = CMFMediaStream::ConfigureSampleDropper(this);
        if ( v9 >= 0 )
        {
          *((_QWORD *)this + 107) = 0;
          CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init((char *)this + 440, 1);
          *((_QWORD *)this + 163) = 0;
          CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init((char *)this + 888, 1);
          v32 = 0;
          v9 = 0;
          MFGetConfigurationDWORD(0, L"Network\\BurstTimeMs", &v32);
          if ( v32 )
            *((_QWORD *)this + 30) = 10000LL * v32;
          v29[0] = 0;
          MFGetConfigurationDWORD(0, L"Network\\EnableNetworkSampleBasedBursting", v29);
          if ( !v29[0] && (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 48LL))(*v7) )
            *((_QWORD *)this + 30) = 0;
          if ( (unsigned __int8)byte_1801B110B >= 0x10u )
            WPP_SF_qqqD(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              v26,
              v27,
              this,
              (char *)this + 280,
              ((unsigned __int64)this + 8) & -(__int64)(this != 0),
              *((_DWORD *)this + 108));
        }
        else
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CMFMediaStream::CMFMediaStream", 533, v9);
          }
          if ( g_wppLevels )
          {
            v13 = 42;
            goto LABEL_14;
          }
        }
      }
      else
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
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
          if ( *((_DWORD *)v21 + 499) != v9 )
            CallStackContext::TraceFailure(v21, "CMFMediaStream::CMFMediaStream", 531, v9);
        }
        if ( g_wppLevels )
        {
          v13 = 41;
          goto LABEL_14;
        }
      }
    }
    else
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != v9 )
          CallStackContext::TraceFailure(v17, "CMFMediaStream::CMFMediaStream", 528, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 40;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
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
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v9 )
        CallStackContext::TraceFailure(v12, "CMFMediaStream::CMFMediaStream", 515, v9);
    }
    if ( g_wppLevels )
    {
      v13 = 39;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids, this, v9);
    }
  }
  *v33 = v9;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v30);
  return this;
}

```

## disassembly

```asm
0x1800987cc  mov     [rsp+arg_18], r9
0x1800987d1  mov     [rsp+arg_8], rdx
0x1800987d6  push    rbx
0x1800987d7  push    rbp
0x1800987d8  push    rsi
0x1800987d9  push    rdi
0x1800987da  push    r12
0x1800987dc  push    r13
0x1800987de  push    r14
0x1800987e0  push    r15
0x1800987e2  sub     rsp, 58h
0x1800987e6  mov     rdi, rcx
0x1800987e9  mov     r14, r9
0x1800987ec  add     rcx, 28h ; '('; this
0x1800987f0  mov     rsi, r8
0x1800987f3  call    ??0CAudioBurstBufferStream@@QEAA@XZ; CAudioBurstBufferStream::CAudioBurstBufferStream(void)
0x1800987f8  lock inc cs:dword_1801B079C
0x1800987ff  lea     rax, ??_7CMFMediaStream@@6BIMFGetService@@@; const CMFMediaStream::`vftable'{for `IMFGetService'}
0x180098806  mov     [rdi], rax
0x180098809  lea     r13, [rdi+8]
0x18009880d  lea     rax, ??_7CMFMediaStream@@6BIMFMediaStream@@@; const CMFMediaStream::`vftable'{for `IMFMediaStream'}
0x180098814  mov     [r13+0], rax
0x180098818  lea     rcx, [rdi+78h]; this
0x18009881c  lea     rax, ??_7CMFMediaStream@@6BIMFQualityAdvise@@@; const CMFMediaStream::`vftable'{for `IMFQualityAdvise'}
0x180098823  mov     [rdi+10h], rax
0x180098827  lea     rax, ??_7CMFMediaStream@@6BIMFQualityAdviseInternal@@@; const CMFMediaStream::`vftable'{for `IMFQualityAdviseInternal'}
0x18009882e  mov     [rdi+18h], rax
0x180098832  lea     rax, ??_7CMFMediaStream@@6BIMFSampleProtection@@@; const CMFMediaStream::`vftable'{for `IMFSampleProtection'}
0x180098839  mov     [rdi+20h], rax
0x18009883d  lea     rax, ??_7CMFMediaStream@@6BCAudioBurstBufferStream@@@; const CMFMediaStream::`vftable'{for `CAudioBurstBufferStream'}
0x180098844  mov     [rdi+28h], rax
0x180098848  call    ??0CompleteEOSAsyncCallback@CMFMediaStream@@QEAA@XZ; CMFMediaStream::CompleteEOSAsyncCallback::CompleteEOSAsyncCallback(void)
0x18009884d  lea     rcx, [rdi+80h]; this
0x180098854  call    ??0RequestMoreSamplesAsyncCallback@CMFMediaStream@@QEAA@XZ; CMFMediaStream::RequestMoreSamplesAsyncCallback::RequestMoreSamplesAsyncCallback(void)
0x180098859  xor     ebx, ebx
0x18009885b  lea     rcx, [rdi+90h]; lpCriticalSection
0x180098862  mov     [rdi+88h], ebx
0x180098868  call    cs:__imp_InitializeCriticalSection
0x18009886e  mov     [rdi+0B8h], rbx
0x180098875  lea     rcx, [rdi+118h]; this
0x18009887c  mov     rdx, r14; int *
0x18009887f  mov     [rdi+0C0h], rbx
0x180098886  mov     [rdi+0C8h], rbx
0x18009888d  mov     [rdi+0D0h], ebx
0x180098893  mov     dword ptr [rdi+0D4h], 1
0x18009889d  mov     [rdi+0D8h], rbx
0x1800988a4  mov     [rdi+0E0h], rbx
0x1800988ab  mov     qword ptr [rdi+0E8h], 1C9C380h
0x1800988b6  mov     qword ptr [rdi+0F0h], 2FAF080h
0x1800988c1  mov     [rdi+0F8h], rbx
0x1800988c8  mov     [rdi+100h], rbx
0x1800988cf  mov     qword ptr [rdi+108h], 4
0x1800988da  mov     [rdi+110h], ebx
0x1800988e0  call    ??0CMFMediaEventGenerator@@QEAA@PEAJ@Z; CMFMediaEventGenerator::CMFMediaEventGenerator(long *)
0x1800988e5  lea     rbp, [rdi+190h]
0x1800988ec  mov     [rbp+0], rbx
0x1800988f0  mov     [rdi+198h], rsi
0x1800988f7  test    rsi, rsi
0x1800988fa  jz      short loc_18009890B
0x1800988fc  mov     rax, [rsi]
0x1800988ff  mov     rcx, rsi
0x180098902  mov     rax, [rax+8]
0x180098906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009890b  mov     [rdi+1B4h], ebx
0x180098911  lea     rsi, [rdi+378h]
0x180098918  lea     r14, [rdi+1B8h]
0x18009891f  lea     r15, [rdi+1B0h]
0x180098926  mov     [r15], ebx
0x180098929  lea     r12, [rdi+550h]
0x180098930  mov     [r14], rbx
0x180098933  mov     [r14+8], rbx
0x180098937  mov     [r14+10h], ebx
0x18009893b  mov     [r14+1B8h], ebx
0x180098942  mov     [r14+1B0h], rbx
0x180098949  mov     [r14+1A8h], rbx
0x180098950  mov     [r14+1A0h], rbx
0x180098957  mov     [rsi], rbx
0x18009895a  mov     [rsi+8], rbx
0x18009895e  mov     [rsi+10h], ebx
0x180098961  mov     [rsi+1B8h], ebx
0x180098967  mov     [rsi+1B0h], rbx
0x18009896e  mov     [rsi+1A8h], rbx
0x180098975  mov     [rsi+1A0h], rbx
0x18009897c  mov     [rsi+1C0h], ebx
0x180098982  mov     [rdi+540h], rbx
0x180098989  mov     [rdi+548h], ebx
0x18009898f  mov     [r12], rbx
0x180098993  mov     [rdi+558h], ebx
0x180098999  lea     rbx, [rdi+560h]
0x1800989a0  mov     rcx, rbx
0x1800989a3  mov     dword ptr [rdi+55Ch], 3F800000h
0x1800989ad  call    ??0?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@QEAA@I@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CMFAttributesImpl<IMFAttributes,CMFCSLock>(uint)
0x1800989b2  lea     rax, ??_7CMFNotifyAttributes_ParentClass@CMFMediaStream@@6B@; const CMFMediaStream::CMFNotifyAttributes_ParentClass::`vftable'
0x1800989b9  mov     r8d, 203h; int
0x1800989bf  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x1800989c6  mov     [rbx], rax
0x1800989c9  lea     rcx, [rsp+98h+arg_0]; this
0x1800989d1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800989d6  mov     rbx, [rsp+98h+arg_18]
0x1800989de  mov     ebx, [rbx]
0x1800989e0  test    ebx, ebx
0x1800989e2  jns     loc_180098A95
0x1800989e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800989ef  test    rcx, rcx
0x1800989f2  jnz     short loc_180098A35
0x1800989f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800989fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098a01  mov     rcx, rax
0x180098a04  test    rax, rax
0x180098a07  jz      short loc_180098A27
0x180098a09  mov     rax, [rax]
0x180098a0c  mov     edx, 7F0h
0x180098a11  mov     rax, [rax+8]
0x180098a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098a1a  test    eax, eax
0x180098a1c  jz      short loc_180098A27
0x180098a1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098a25  jmp     short loc_180098A35
0x180098a27  lea     rcx, qword_1801B07E0; this
0x180098a2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098a35  cmp     byte ptr [rcx+8], 0
0x180098a39  jz      short loc_180098A60
0x180098a3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098a40  cmp     [rax+7CCh], ebx
0x180098a46  jz      short loc_180098A60
0x180098a48  mov     r9d, ebx; int
0x180098a4b  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x180098a52  mov     r8d, 203h; int
0x180098a58  mov     rcx, rax; this
0x180098a5b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098a60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180098a67  jb      loc_180098DA5
0x180098a6d  mov     edx, 27h ; '''
0x180098a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180098a79  lea     r8, WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids
0x180098a80  mov     r9, rdi
0x180098a83  mov     dword ptr [rsp+98h+var_78], ebx
0x180098a87  mov     rcx, [rcx+10h]
0x180098a8b  call    WPP_SF_qD
0x180098a90  jmp     loc_180098DA5
0x180098a95  mov     rdx, [rsp+98h+arg_8]
0x180098a9d  mov     rcx, rbp
0x180098aa0  call    ??4?$ComSmartPtr@VCMPEGFrame@@@@QEAAPEAVCMPEGFrame@@PEAV1@@Z; ComSmartPtr<CMPEGFrame>::operator=(CMPEGFrame *)
0x180098aa5  mov     rcx, [rbp+0]
0x180098aa9  lea     rdx, IID_IMFSampleProtection
0x180098ab0  mov     r8, r12
0x180098ab3  mov     rax, [rcx]
0x180098ab6  mov     rax, [rax]
0x180098ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098abe  mov     rcx, [rdi+198h]
0x180098ac5  mov     rdx, r15
0x180098ac8  mov     rax, [rcx]
0x180098acb  mov     rax, [rax+108h]
0x180098ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098ad7  xor     r12d, r12d
0x180098ada  mov     ebx, eax
0x180098adc  test    eax, eax
0x180098ade  jns     loc_180098B73
0x180098ae4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098aeb  test    rcx, rcx
0x180098aee  jnz     short loc_180098B31
0x180098af0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098af6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098afd  mov     rcx, rax
0x180098b00  test    rax, rax
0x180098b03  jz      short loc_180098B23
0x180098b05  mov     rax, [rax]
0x180098b08  mov     edx, 7F0h
0x180098b0d  mov     rax, [rax+8]
0x180098b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098b16  test    eax, eax
0x180098b18  jz      short loc_180098B23
0x180098b1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098b21  jmp     short loc_180098B31
0x180098b23  lea     rcx, qword_1801B07E0; this
0x180098b2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098b31  cmp     [rcx+8], r12b
0x180098b35  jz      short loc_180098B5C
0x180098b37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098b3c  cmp     [rax+7CCh], ebx
0x180098b42  jz      short loc_180098B5C
0x180098b44  mov     r9d, ebx; int
0x180098b47  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x180098b4e  mov     r8d, 210h; int
0x180098b54  mov     rcx, rax; this
0x180098b57  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098b5c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180098b63  jb      loc_180098DA5
0x180098b69  mov     edx, 28h ; '('
0x180098b6e  jmp     loc_180098A72
0x180098b73  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180098b7a  mov     rcx, rdi; this
0x180098b7d  movdqu  xmmword ptr [rdi+1A0h], xmm0
0x180098b85  call    ?DetermineMediaType@CMFMediaStream@@IEAAJXZ; CMFMediaStream::DetermineMediaType(void)
0x180098b8a  mov     ebx, eax
0x180098b8c  test    eax, eax
0x180098b8e  jns     loc_180098C23
0x180098b94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098b9b  test    rcx, rcx
0x180098b9e  jnz     short loc_180098BE1
0x180098ba0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098ba6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098bad  mov     rcx, rax
0x180098bb0  test    rax, rax
0x180098bb3  jz      short loc_180098BD3
0x180098bb5  mov     rax, [rax]
0x180098bb8  mov     edx, 7F0h
0x180098bbd  mov     rax, [rax+8]
0x180098bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098bc6  test    eax, eax
0x180098bc8  jz      short loc_180098BD3
0x180098bca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098bd1  jmp     short loc_180098BE1
0x180098bd3  lea     rcx, qword_1801B07E0; this
0x180098bda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098be1  cmp     [rcx+8], r12b
0x180098be5  jz      short loc_180098C0C
0x180098be7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098bec  cmp     [rax+7CCh], ebx
0x180098bf2  jz      short loc_180098C0C
0x180098bf4  mov     r9d, ebx; int
0x180098bf7  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x180098bfe  mov     r8d, 213h; int
0x180098c04  mov     rcx, rax; this
0x180098c07  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098c0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180098c13  jb      loc_180098DA5
0x180098c19  mov     edx, 29h ; ')'
0x180098c1e  jmp     loc_180098A72
0x180098c23  mov     rcx, rdi; this
0x180098c26  call    ?ConfigureSampleDropper@CMFMediaStream@@IEAAJXZ; CMFMediaStream::ConfigureSampleDropper(void)
0x180098c2b  mov     ebx, eax
0x180098c2d  test    eax, eax
0x180098c2f  jns     loc_180098CC4
0x180098c35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098c3c  test    rcx, rcx
0x180098c3f  jnz     short loc_180098C82
0x180098c41  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180098c47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180098c4e  mov     rcx, rax
0x180098c51  test    rax, rax
0x180098c54  jz      short loc_180098C74
0x180098c56  mov     rax, [rax]
0x180098c59  mov     edx, 7F0h
0x180098c5e  mov     rax, [rax+8]
0x180098c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c67  test    eax, eax
0x180098c69  jz      short loc_180098C74
0x180098c6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180098c72  jmp     short loc_180098C82
0x180098c74  lea     rcx, qword_1801B07E0; this
0x180098c7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180098c82  cmp     [rcx+8], r12b
0x180098c86  jz      short loc_180098CAD
0x180098c88  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180098c8d  cmp     [rax+7CCh], ebx
0x180098c93  jz      short loc_180098CAD
0x180098c95  mov     r9d, ebx; int
0x180098c98  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x180098c9f  mov     r8d, 215h; int
0x180098ca5  mov     rcx, rax; this
0x180098ca8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180098cad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180098cb4  jb      loc_180098DA5
0x180098cba  mov     edx, 2Ah ; '*'
0x180098cbf  jmp     loc_180098A72
0x180098cc4  mov     edx, 1
0x180098cc9  mov     [r14+1A0h], r12
0x180098cd0  mov     rcx, r14
0x180098cd3  call    ?Init@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXK@Z; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init(ulong)
0x180098cd8  mov     edx, 1
0x180098cdd  mov     [rsi+1A0h], r12
0x180098ce4  mov     rcx, rsi
0x180098ce7  call    ?Init@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXK@Z; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init(ulong)
0x180098cec  lea     r8, [rsp+98h+arg_10]
0x180098cf4  mov     [rsp+98h+arg_10], r12d
0x180098cfc  lea     rdx, aNetworkBurstti; "Network\\BurstTimeMs"
0x180098d03  xor     ecx, ecx
0x180098d05  mov     ebx, r12d
0x180098d08  call    cs:__imp_MFGetConfigurationDWORD
0x180098d0e  mov     eax, [rsp+98h+arg_10]
0x180098d15  test    eax, eax
0x180098d17  jz      short loc_180098D27
0x180098d19  imul    rcx, rax, 2710h
0x180098d20  mov     [rdi+0F0h], rcx
0x180098d27  lea     r8, [rsp+98h+var_58]
0x180098d2c  mov     [rsp+98h+var_58], r12d
0x180098d31  lea     rdx, aNetworkEnablen; "Network\\EnableNetworkSampleBasedBursti"...
0x180098d38  xor     ecx, ecx
0x180098d3a  call    cs:__imp_MFGetConfigurationDWORD
0x180098d40  cmp     [rsp+98h+var_58], r12d
0x180098d45  jnz     short loc_180098D62
0x180098d47  mov     rcx, [rbp+0]
0x180098d4b  mov     rax, [rcx]
0x180098d4e  mov     rax, [rax+30h]
0x180098d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d57  test    eax, eax
0x180098d59  jz      short loc_180098D62
0x180098d5b  mov     [rdi+0F0h], r12
0x180098d62  cmp     cs:byte_1801B110B, 10h
  ... truncated ...
```
