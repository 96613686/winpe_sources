# CMFMediaStream::CMFMediaStream(IByteStreamMediaSource *,IMFStreamDescriptor *,long *)

- ea: `0x18009dd6c`
- end: `0x18009e39b`
- name: `??0CMFMediaStream@@IEAA@PEAVIByteStreamMediaSource@@PEAUIMFStreamDescriptor@@PEAJ@Z`
- size: `1583`
- prototype: `CMFMediaStream *__fastcall(CMFMediaStream *__hidden this, struct IByteStreamMediaSource *, struct IMFStreamDescriptor *, int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801519c0`

## callees

- `0x180005cf4`
- `0x18000a080`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18004a8a8`
- `0x18006dec0`
- `0x180079680`
- `0x18009dd6c`
- `0x1800d2f10`
- `0x18011234c`
- `0x180151390`
- `0x1801513a8`
- `0x180151dc4`
- `0x180153a38`
- `0x180153aac`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009de08`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009de08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009df9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e09c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e152`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e1f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009df9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e09c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e152`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e1f9`
- `MFPlat!MFGetConfigurationDWORD` at `0x18009e2c6`
- `MFPlat!MFGetConfigurationDWORD` at `0x18009e2fe`
- `MFPlat!MFGetConfigurationDWORD` at `0x18009e2c6`
- `MFPlat!MFGetConfigurationDWORD` at `0x18009e2fe`

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
  _InterlockedIncrement(&dword_1801B979C);
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
          if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
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
              v23 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v19 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v15 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v10 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x18009dd6c  mov     [rsp+arg_18], r9
0x18009dd71  mov     [rsp+arg_8], rdx
0x18009dd76  push    rbx
0x18009dd77  push    rbp
0x18009dd78  push    rsi
0x18009dd79  push    rdi
0x18009dd7a  push    r12
0x18009dd7c  push    r13
0x18009dd7e  push    r14
0x18009dd80  push    r15
0x18009dd82  sub     rsp, 58h
0x18009dd86  mov     rdi, rcx
0x18009dd89  mov     r14, r9
0x18009dd8c  add     rcx, 28h ; '('; this
0x18009dd90  mov     rsi, r8
0x18009dd93  call    ??0CAudioBurstBufferStream@@QEAA@XZ; CAudioBurstBufferStream::CAudioBurstBufferStream(void)
0x18009dd98  lock inc cs:dword_1801B979C
0x18009dd9f  lea     rax, ??_7CMFMediaStream@@6BIMFGetService@@@; const CMFMediaStream::`vftable'{for `IMFGetService'}
0x18009dda6  mov     [rdi], rax
0x18009dda9  lea     r13, [rdi+8]
0x18009ddad  lea     rax, ??_7CMFMediaStream@@6BIMFMediaStream@@@; const CMFMediaStream::`vftable'{for `IMFMediaStream'}
0x18009ddb4  mov     [r13+0], rax
0x18009ddb8  lea     rcx, [rdi+78h]; this
0x18009ddbc  lea     rax, ??_7CMFMediaStream@@6BIMFQualityAdvise@@@; const CMFMediaStream::`vftable'{for `IMFQualityAdvise'}
0x18009ddc3  mov     [rdi+10h], rax
0x18009ddc7  lea     rax, ??_7CMFMediaStream@@6BIMFQualityAdviseInternal@@@; const CMFMediaStream::`vftable'{for `IMFQualityAdviseInternal'}
0x18009ddce  mov     [rdi+18h], rax
0x18009ddd2  lea     rax, ??_7CMFMediaStream@@6BIMFSampleProtection@@@; const CMFMediaStream::`vftable'{for `IMFSampleProtection'}
0x18009ddd9  mov     [rdi+20h], rax
0x18009dddd  lea     rax, ??_7CMFMediaStream@@6BCAudioBurstBufferStream@@@; const CMFMediaStream::`vftable'{for `CAudioBurstBufferStream'}
0x18009dde4  mov     [rdi+28h], rax
0x18009dde8  call    ??0CompleteEOSAsyncCallback@CMFMediaStream@@QEAA@XZ; CMFMediaStream::CompleteEOSAsyncCallback::CompleteEOSAsyncCallback(void)
0x18009dded  lea     rcx, [rdi+80h]; this
0x18009ddf4  call    ??0RequestMoreSamplesAsyncCallback@CMFMediaStream@@QEAA@XZ; CMFMediaStream::RequestMoreSamplesAsyncCallback::RequestMoreSamplesAsyncCallback(void)
0x18009ddf9  xor     ebx, ebx
0x18009ddfb  lea     rcx, [rdi+90h]; lpCriticalSection
0x18009de02  mov     [rdi+88h], ebx
0x18009de08  call    cs:__imp_InitializeCriticalSection
0x18009de0f  nop     dword ptr [rax+rax+00h]
0x18009de14  mov     [rdi+0B8h], rbx
0x18009de1b  lea     rcx, [rdi+118h]; this
0x18009de22  mov     rdx, r14; int *
0x18009de25  mov     [rdi+0C0h], rbx
0x18009de2c  mov     [rdi+0C8h], rbx
0x18009de33  mov     [rdi+0D0h], ebx
0x18009de39  mov     dword ptr [rdi+0D4h], 1
0x18009de43  mov     [rdi+0D8h], rbx
0x18009de4a  mov     [rdi+0E0h], rbx
0x18009de51  mov     qword ptr [rdi+0E8h], 1C9C380h
0x18009de5c  mov     qword ptr [rdi+0F0h], 2FAF080h
0x18009de67  mov     [rdi+0F8h], rbx
0x18009de6e  mov     [rdi+100h], rbx
0x18009de75  mov     qword ptr [rdi+108h], 4
0x18009de80  mov     [rdi+110h], ebx
0x18009de86  call    ??0CMFMediaEventGenerator@@QEAA@PEAJ@Z; CMFMediaEventGenerator::CMFMediaEventGenerator(long *)
0x18009de8b  lea     rbp, [rdi+190h]
0x18009de92  mov     [rbp+0], rbx
0x18009de96  mov     [rdi+198h], rsi
0x18009de9d  test    rsi, rsi
0x18009dea0  jz      short loc_18009DEB1
0x18009dea2  mov     rax, [rsi]
0x18009dea5  mov     rcx, rsi
0x18009dea8  mov     rax, [rax+8]
0x18009deac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009deb1  mov     [rdi+1B4h], ebx
0x18009deb7  lea     rsi, [rdi+378h]
0x18009debe  lea     r14, [rdi+1B8h]
0x18009dec5  lea     r15, [rdi+1B0h]
0x18009decc  mov     [r15], ebx
0x18009decf  lea     r12, [rdi+550h]
0x18009ded6  mov     [r14], rbx
0x18009ded9  mov     [r14+8], rbx
0x18009dedd  mov     [r14+10h], ebx
0x18009dee1  mov     [r14+1B8h], ebx
0x18009dee8  mov     [r14+1B0h], rbx
0x18009deef  mov     [r14+1A8h], rbx
0x18009def6  mov     [r14+1A0h], rbx
0x18009defd  mov     [rsi], rbx
0x18009df00  mov     [rsi+8], rbx
0x18009df04  mov     [rsi+10h], ebx
0x18009df07  mov     [rsi+1B8h], ebx
0x18009df0d  mov     [rsi+1B0h], rbx
0x18009df14  mov     [rsi+1A8h], rbx
0x18009df1b  mov     [rsi+1A0h], rbx
0x18009df22  mov     [rsi+1C0h], ebx
0x18009df28  mov     [rdi+540h], rbx
0x18009df2f  mov     [rdi+548h], ebx
0x18009df35  mov     [r12], rbx
0x18009df39  mov     [rdi+558h], ebx
0x18009df3f  lea     rbx, [rdi+560h]
0x18009df46  mov     rcx, rbx
0x18009df49  mov     dword ptr [rdi+55Ch], 3F800000h
0x18009df53  call    ??0?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@QEAA@I@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CMFAttributesImpl<IMFAttributes,CMFCSLock>(uint)
0x18009df58  lea     rax, ??_7CMFNotifyAttributes_ParentClass@CMFMediaStream@@6B@; const CMFMediaStream::CMFNotifyAttributes_ParentClass::`vftable'
0x18009df5f  mov     r8d, 203h; int
0x18009df65  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x18009df6c  mov     [rbx], rax
0x18009df6f  lea     rcx, [rsp+98h+arg_0]; this
0x18009df77  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009df7c  mov     rbx, [rsp+98h+arg_18]
0x18009df84  mov     ebx, [rbx]
0x18009df86  test    ebx, ebx
0x18009df88  jns     loc_18009E041
0x18009df8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009df95  test    rcx, rcx
0x18009df98  jnz     short loc_18009DFE1
0x18009df9a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009dfa1  nop     dword ptr [rax+rax+00h]
0x18009dfa6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009dfad  mov     rcx, rax
0x18009dfb0  test    rax, rax
0x18009dfb3  jz      short loc_18009DFD3
0x18009dfb5  mov     rax, [rax]
0x18009dfb8  mov     edx, 7F0h
0x18009dfbd  mov     rax, [rax+8]
0x18009dfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dfc6  test    eax, eax
0x18009dfc8  jz      short loc_18009DFD3
0x18009dfca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009dfd1  jmp     short loc_18009DFE1
0x18009dfd3  lea     rcx, qword_1801B97E0; this
0x18009dfda  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009dfe1  cmp     byte ptr [rcx+8], 0
0x18009dfe5  jz      short loc_18009E00C
0x18009dfe7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009dfec  cmp     [rax+7CCh], ebx
0x18009dff2  jz      short loc_18009E00C
0x18009dff4  mov     r9d, ebx; int
0x18009dff7  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x18009dffe  mov     r8d, 203h; int
0x18009e004  mov     rcx, rax; this
0x18009e007  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e00c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e013  jb      loc_18009E36F
0x18009e019  mov     edx, 27h ; '''
0x18009e01e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e025  lea     r8, WPP_fc8c5d8c44273bdd34ec62b5fce42adb_Traceguids
0x18009e02c  mov     r9, rdi
0x18009e02f  mov     dword ptr [rsp+98h+var_78], ebx
0x18009e033  mov     rcx, [rcx+10h]
0x18009e037  call    WPP_SF_qD
0x18009e03c  jmp     loc_18009E36F
0x18009e041  mov     rdx, [rsp+98h+arg_8]
0x18009e049  mov     rcx, rbp
0x18009e04c  call    ??4?$ComSmartPtr@VCMPEGFrame@@@@QEAAPEAVCMPEGFrame@@PEAV1@@Z; ComSmartPtr<CMPEGFrame>::operator=(CMPEGFrame *)
0x18009e051  mov     rcx, [rbp+0]
0x18009e055  lea     rdx, IID_IMFSampleProtection
0x18009e05c  mov     r8, r12
0x18009e05f  mov     rax, [rcx]
0x18009e062  mov     rax, [rax]
0x18009e065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e06a  mov     rcx, [rdi+198h]
0x18009e071  mov     rdx, r15
0x18009e074  mov     rax, [rcx]
0x18009e077  mov     rax, [rax+108h]
0x18009e07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e083  xor     r12d, r12d
0x18009e086  mov     ebx, eax
0x18009e088  test    eax, eax
0x18009e08a  jns     loc_18009E125
0x18009e090  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e097  test    rcx, rcx
0x18009e09a  jnz     short loc_18009E0E3
0x18009e09c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e0a3  nop     dword ptr [rax+rax+00h]
0x18009e0a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e0af  mov     rcx, rax
0x18009e0b2  test    rax, rax
0x18009e0b5  jz      short loc_18009E0D5
0x18009e0b7  mov     rax, [rax]
0x18009e0ba  mov     edx, 7F0h
0x18009e0bf  mov     rax, [rax+8]
0x18009e0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e0c8  test    eax, eax
0x18009e0ca  jz      short loc_18009E0D5
0x18009e0cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e0d3  jmp     short loc_18009E0E3
0x18009e0d5  lea     rcx, qword_1801B97E0; this
0x18009e0dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e0e3  cmp     [rcx+8], r12b
0x18009e0e7  jz      short loc_18009E10E
0x18009e0e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e0ee  cmp     [rax+7CCh], ebx
0x18009e0f4  jz      short loc_18009E10E
0x18009e0f6  mov     r9d, ebx; int
0x18009e0f9  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x18009e100  mov     r8d, 210h; int
0x18009e106  mov     rcx, rax; this
0x18009e109  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e10e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e115  jb      loc_18009E36F
0x18009e11b  mov     edx, 28h ; '('
0x18009e120  jmp     loc_18009E01E
0x18009e125  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18009e12c  mov     rcx, rdi; this
0x18009e12f  movdqu  xmmword ptr [rdi+1A0h], xmm0
0x18009e137  call    ?DetermineMediaType@CMFMediaStream@@IEAAJXZ; CMFMediaStream::DetermineMediaType(void)
0x18009e13c  mov     ebx, eax
0x18009e13e  test    eax, eax
0x18009e140  jns     loc_18009E1DB
0x18009e146  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e14d  test    rcx, rcx
0x18009e150  jnz     short loc_18009E199
0x18009e152  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e159  nop     dword ptr [rax+rax+00h]
0x18009e15e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e165  mov     rcx, rax
0x18009e168  test    rax, rax
0x18009e16b  jz      short loc_18009E18B
0x18009e16d  mov     rax, [rax]
0x18009e170  mov     edx, 7F0h
0x18009e175  mov     rax, [rax+8]
0x18009e179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e17e  test    eax, eax
0x18009e180  jz      short loc_18009E18B
0x18009e182  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e189  jmp     short loc_18009E199
0x18009e18b  lea     rcx, qword_1801B97E0; this
0x18009e192  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e199  cmp     [rcx+8], r12b
0x18009e19d  jz      short loc_18009E1C4
0x18009e19f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e1a4  cmp     [rax+7CCh], ebx
0x18009e1aa  jz      short loc_18009E1C4
0x18009e1ac  mov     r9d, ebx; int
0x18009e1af  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x18009e1b6  mov     r8d, 213h; int
0x18009e1bc  mov     rcx, rax; this
0x18009e1bf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e1c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e1cb  jb      loc_18009E36F
0x18009e1d1  mov     edx, 29h ; ')'
0x18009e1d6  jmp     loc_18009E01E
0x18009e1db  mov     rcx, rdi; this
0x18009e1de  call    ?ConfigureSampleDropper@CMFMediaStream@@IEAAJXZ; CMFMediaStream::ConfigureSampleDropper(void)
0x18009e1e3  mov     ebx, eax
0x18009e1e5  test    eax, eax
0x18009e1e7  jns     loc_18009E282
0x18009e1ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e1f4  test    rcx, rcx
0x18009e1f7  jnz     short loc_18009E240
0x18009e1f9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e200  nop     dword ptr [rax+rax+00h]
0x18009e205  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e20c  mov     rcx, rax
0x18009e20f  test    rax, rax
0x18009e212  jz      short loc_18009E232
0x18009e214  mov     rax, [rax]
0x18009e217  mov     edx, 7F0h
0x18009e21c  mov     rax, [rax+8]
0x18009e220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e225  test    eax, eax
0x18009e227  jz      short loc_18009E232
0x18009e229  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e230  jmp     short loc_18009E240
0x18009e232  lea     rcx, qword_1801B97E0; this
0x18009e239  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e240  cmp     [rcx+8], r12b
0x18009e244  jz      short loc_18009E26B
0x18009e246  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e24b  cmp     [rax+7CCh], ebx
0x18009e251  jz      short loc_18009E26B
0x18009e253  mov     r9d, ebx; int
0x18009e256  lea     rdx, aCmfmediastream_14; "CMFMediaStream::CMFMediaStream"
0x18009e25d  mov     r8d, 215h; int
0x18009e263  mov     rcx, rax; this
0x18009e266  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e26b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e272  jb      loc_18009E36F
0x18009e278  mov     edx, 2Ah ; '*'
0x18009e27d  jmp     loc_18009E01E
0x18009e282  mov     edx, 1
0x18009e287  mov     [r14+1A0h], r12
0x18009e28e  mov     rcx, r14
0x18009e291  call    ?Init@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXK@Z; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init(ulong)
0x18009e296  mov     edx, 1
0x18009e29b  mov     [rsi+1A0h], r12
0x18009e2a2  mov     rcx, rsi
0x18009e2a5  call    ?Init@?$CTNodePool@UNODEBLOCK@CVPtrList@@UNODE@2@$0BA@@@QEAAXK@Z; CTNodePool<CVPtrList::NODEBLOCK,CVPtrList::NODE,16>::Init(ulong)
0x18009e2aa  lea     r8, [rsp+98h+arg_10]
0x18009e2b2  mov     [rsp+98h+arg_10], r12d
0x18009e2ba  lea     rdx, aNetworkBurstti; "Network\\BurstTimeMs"
0x18009e2c1  xor     ecx, ecx
0x18009e2c3  mov     ebx, r12d
0x18009e2c6  call    cs:__imp_MFGetConfigurationDWORD
0x18009e2cd  nop     dword ptr [rax+rax+00h]
0x18009e2d2  mov     eax, [rsp+98h+arg_10]
0x18009e2d9  test    eax, eax
0x18009e2db  jz      short loc_18009E2EB
0x18009e2dd  imul    rcx, rax, 2710h
0x18009e2e4  mov     [rdi+0F0h], rcx
0x18009e2eb  lea     r8, [rsp+98h+var_58]
0x18009e2f0  mov     [rsp+98h+var_58], r12d
0x18009e2f5  lea     rdx, aNetworkEnablen; "Network\\EnableNetworkSampleBasedBursti"...
0x18009e2fc  xor     ecx, ecx
0x18009e2fe  call    cs:__imp_MFGetConfigurationDWORD
0x18009e305  nop     dword ptr [rax+rax+00h]
0x18009e30a  cmp     [rsp+98h+var_58], r12d
0x18009e30f  jnz     short loc_18009E32C
0x18009e311  mov     rcx, [rbp+0]
  ... truncated ...
```
