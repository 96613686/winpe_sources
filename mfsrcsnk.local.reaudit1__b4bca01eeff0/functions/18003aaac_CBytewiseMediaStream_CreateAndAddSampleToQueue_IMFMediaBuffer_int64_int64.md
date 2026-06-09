# CBytewiseMediaStream::CreateAndAddSampleToQueue(IMFMediaBuffer *,__int64,__int64)

- ea: `0x18003aaac`
- end: `0x18003b231`
- name: `?CreateAndAddSampleToQueue@CBytewiseMediaStream@@QEAAJPEAUIMFMediaBuffer@@_J1@Z`
- size: `1925`
- prototype: `__int64 __fastcall(CBytewiseMediaStream *__hidden this, struct IMFMediaBuffer *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022758`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18003aaac`
- `0x18003b238`
- `0x18003b32c`
- `0x18003b580`
- `0x180077708`
- `0x180079680`
- `0x180121750`
- `0x18014f8fc`
- `0x18016ccc0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b0d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b1f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b0d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b1f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b004`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b004`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ab90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ac64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ad15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ade4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ae95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b03a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b16b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ab90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ac64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ad15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ade4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ae95`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b03a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b16b`
- `MFPlat!MFCreateSample` at `0x18003ab6e`
- `MFPlat!MFCreateSample` at `0x18003ab6e`
- `MFPlat!MFPutWorkItem` at `0x18003b149`
- `MFPlat!MFPutWorkItem` at `0x18003b149`

## string_xrefs

- `0x18003aac3`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`

## pseudocode

```c
__int64 __fastcall CBytewiseMediaStream::CreateAndAddSampleToQueue(
        CBytewiseMediaStream *this,
        struct IMFMediaBuffer *a2,
        __int64 a3,
        __int64 a4)
{
  CallStackTracing *v8; // rcx
  HRESULT v9; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  IMFSample *v24; // rcx
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  int v33; // eax
  char v34; // dl
  unsigned int v35; // edx
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  IMFSample *ppIMFSample; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v47[4]; // [rsp+58h] [rbp-20h] BYREF
  int v48; // [rsp+5Ch] [rbp-1Ch] BYREF
  __int64 v49; // [rsp+60h] [rbp-18h] BYREF
  int v50; // [rsp+68h] [rbp-10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v47,
    "CBytewiseMediaStream::CreateAndAddSampleToQueue",
    761);
  if ( !a2 )
  {
    v8 = CallStackTracing::s_wpInstance;
    v9 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v8 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CBytewiseMediaStream::CreateAndAddSampleToQueue",
          770,
          -2147467261);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids,
        this,
        -2147467261);
    goto LABEL_106;
  }
  ppIMFSample = 0;
  v9 = MFCreateSample(&ppIMFSample);
  if ( v9 < 0 )
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v9 )
        CallStackContext::TraceFailure(v14, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 774, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_21;
    v15 = 57;
    goto LABEL_20;
  }
  v9 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, a3);
  if ( v9 < 0 )
  {
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != v9 )
        CallStackContext::TraceFailure(v19, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 777, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_21;
    v15 = 58;
    goto LABEL_20;
  }
  v9 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleDuration)(ppIMFSample, a4);
  if ( v9 < 0 )
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
      if ( *((_DWORD *)v23 + 499) != v9 )
        CallStackContext::TraceFailure(v23, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 780, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_21;
    v15 = 59;
    goto LABEL_20;
  }
  if ( *((_DWORD *)this + 56) )
  {
    v24 = ppIMFSample;
    *((_DWORD *)this + 56) = 0;
    v9 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))v24->lpVtbl->SetUINT32)(
           v24,
           &MFSampleExtension_CleanPoint,
           1);
    if ( v9 < 0 )
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
        if ( *((_DWORD *)v28 + 499) != v9 )
          CallStackContext::TraceFailure(v28, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 789, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_21;
      v15 = 60;
      goto LABEL_20;
    }
  }
  v9 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, a2);
  if ( v9 < 0 )
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
      if ( *((_DWORD *)v32 + 499) != v9 )
        CallStackContext::TraceFailure(v32, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 794, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_21;
    v15 = 62;
LABEL_20:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this, v9);
LABEL_21:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
    goto LABEL_106;
  }
  v48 = 0;
  if ( ((int (__fastcall *)(IMFSample *, int *))ppIMFSample->lpVtbl->GetTotalLength)(ppIMFSample, &v48) >= 0 )
    *((_DWORD *)this + 34) += v48;
  v49 = 0x7FFFFFFFFFFFFFFFLL;
  v33 = ((__int64 (__fastcall *)(IMFSample *, __int64 *))ppIMFSample->lpVtbl->GetSampleTime)(ppIMFSample, &v49);
  v34 = v49;
  if ( v33 >= 0 )
    *((_QWORD *)this + 18) = v49;
  LOBYTE(v50) = Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8) != 0 )
  {
    v50 = 1110659149;
    McTemplateU0s4pupqii_EventWriteTransfer(
      (_DWORD)ppIMFSample,
      (unsigned int)Process_Output,
      (unsigned int)&v50,
      (_DWORD)this,
      3,
      (char)ppIMFSample,
      v48,
      v34);
  }
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 63, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this);
    if ( (unsigned __int8)byte_1801BA10B >= 8u )
      MFTRACE_SAMPLE_IMPL(0x30003u, v35, ppIMFSample);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !CVPtrList::AddTail((CBytewiseMediaStream *)((char *)this + 720), ppIMFSample) )
  {
    v37 = (wchar_t *)CallStackTracing::s_wpInstance;
    v9 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
      if ( *((_DWORD *)v39 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v39, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 837, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_88;
    v40 = 64;
LABEL_87:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this, v9);
LABEL_88:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    goto LABEL_21;
  }
  ppIMFSample = 0;
  if ( (unsigned int)CBytewiseMediaStream::RefillingBuffer(this)
    && (unsigned int)CAudioBurstBufferStream::NeedMoreSamplesForBuffer((CBytewiseMediaStream *)((char *)this + 128)) )
  {
    if ( (unsigned __int8)byte_1801BA10B >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 65, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this);
    v9 = MFPutWorkItem(5u, (IMFAsyncCallback *)this + 26, 0);
    if ( v9 < 0 )
    {
      v42 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
        if ( *((_DWORD *)v44 + 499) != v9 )
          CallStackContext::TraceFailure(v44, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 846, v9);
      }
      if ( !g_wppLevels )
        goto LABEL_88;
      v40 = 66;
      goto LABEL_87;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ppIMFSample )
    ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
LABEL_106:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v47);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003aaac  push    rbp
0x18003aaae  push    rbx
0x18003aaaf  push    rsi
0x18003aab0  push    rdi
0x18003aab1  push    r12
0x18003aab3  push    r13
0x18003aab5  push    r14
0x18003aab7  push    r15
0x18003aab9  mov     rbp, rsp
0x18003aabc  sub     rsp, 78h
0x18003aac0  mov     rsi, r8
0x18003aac3  lea     r13, aCbytewisemedia_12; "CBytewiseMediaStream::CreateAndAddSampl"...
0x18003aaca  mov     r14, rdx
0x18003aacd  mov     rdi, rcx
0x18003aad0  mov     rdx, r13; char *
0x18003aad3  lea     rcx, [rbp+var_20]; this
0x18003aad7  mov     r8d, 2F9h; int
0x18003aadd  mov     r15, r9
0x18003aae0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003aae5  xor     r12d, r12d
0x18003aae8  test    r14, r14
0x18003aaeb  jnz     short loc_18003AB66
0x18003aaed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aaf4  mov     ebx, 80004003h
0x18003aaf9  test    rcx, rcx
0x18003aafc  jnz     short loc_18003AB0A
0x18003aafe  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003ab03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003ab0a  cmp     [rcx+8], r12b
0x18003ab0e  jz      short loc_18003AB31
0x18003ab10  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ab15  cmp     [rax+7CCh], ebx
0x18003ab1b  jz      short loc_18003AB31
0x18003ab1d  mov     r9d, ebx; int
0x18003ab20  mov     r8d, 302h; int
0x18003ab26  mov     rdx, r13; char *
0x18003ab29  mov     rcx, rax; this
0x18003ab2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ab31  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ab38  jb      loc_18003B214
0x18003ab3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ab45  lea     r8, WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids
0x18003ab4c  mov     edx, 38h ; '8'
0x18003ab51  mov     [rsp+78h+var_58], ebx
0x18003ab55  mov     r9, rdi
0x18003ab58  mov     rcx, [rcx+10h]
0x18003ab5c  call    WPP_SF_qD
0x18003ab61  jmp     loc_18003B214
0x18003ab66  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x18003ab6a  mov     [rbp+ppIMFSample], r12
0x18003ab6e  call    cs:__imp_MFCreateSample
0x18003ab75  nop     dword ptr [rax+rax+00h]
0x18003ab7a  mov     ebx, eax
0x18003ab7c  test    eax, eax
0x18003ab7e  jns     loc_18003AC38
0x18003ab84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ab8b  test    rcx, rcx
0x18003ab8e  jnz     short loc_18003ABD7
0x18003ab90  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ab97  nop     dword ptr [rax+rax+00h]
0x18003ab9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aba3  mov     rcx, rax
0x18003aba6  test    rax, rax
0x18003aba9  jz      short loc_18003ABC9
0x18003abab  mov     rax, [rax]
0x18003abae  mov     edx, 7F0h
0x18003abb3  mov     rax, [rax+8]
0x18003abb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abbc  test    eax, eax
0x18003abbe  jz      short loc_18003ABC9
0x18003abc0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003abc7  jmp     short loc_18003ABD7
0x18003abc9  lea     rcx, qword_1801B97E0; this
0x18003abd0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003abd7  cmp     [rcx+8], r12b
0x18003abdb  jz      short loc_18003ABFE
0x18003abdd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003abe2  cmp     [rax+7CCh], ebx
0x18003abe8  jz      short loc_18003ABFE
0x18003abea  mov     r9d, ebx; int
0x18003abed  mov     r8d, 306h; int
0x18003abf3  mov     rdx, r13; char *
0x18003abf6  mov     rcx, rax; this
0x18003abf9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003abfe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ac05  jb      short loc_18003AC2A
0x18003ac07  mov     edx, 39h ; '9'
0x18003ac0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac13  lea     r8, WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids
0x18003ac1a  mov     r9, rdi
0x18003ac1d  mov     [rsp+78h+var_58], ebx
0x18003ac21  mov     rcx, [rcx+10h]
0x18003ac25  call    WPP_SF_qD
0x18003ac2a  lea     rcx, [rbp+ppIMFSample]; void *
0x18003ac2e  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18003ac33  jmp     loc_18003B214
0x18003ac38  mov     rcx, [rbp+ppIMFSample]
0x18003ac3c  mov     rdx, rsi
0x18003ac3f  mov     rax, [rcx]
0x18003ac42  mov     rax, [rax+120h]
0x18003ac49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac4e  mov     ebx, eax
0x18003ac50  test    eax, eax
0x18003ac52  jns     loc_18003ACE9
0x18003ac58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ac5f  test    rcx, rcx
0x18003ac62  jnz     short loc_18003ACAB
0x18003ac64  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ac6b  nop     dword ptr [rax+rax+00h]
0x18003ac70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ac77  mov     rcx, rax
0x18003ac7a  test    rax, rax
0x18003ac7d  jz      short loc_18003AC9D
0x18003ac7f  mov     rax, [rax]
0x18003ac82  mov     edx, 7F0h
0x18003ac87  mov     rax, [rax+8]
0x18003ac8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac90  test    eax, eax
0x18003ac92  jz      short loc_18003AC9D
0x18003ac94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ac9b  jmp     short loc_18003ACAB
0x18003ac9d  lea     rcx, qword_1801B97E0; this
0x18003aca4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003acab  cmp     [rcx+8], r12b
0x18003acaf  jz      short loc_18003ACD2
0x18003acb1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003acb6  cmp     [rax+7CCh], ebx
0x18003acbc  jz      short loc_18003ACD2
0x18003acbe  mov     r9d, ebx; int
0x18003acc1  mov     r8d, 309h; int
0x18003acc7  mov     rdx, r13; char *
0x18003acca  mov     rcx, rax; this
0x18003accd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003acd2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003acd9  jb      loc_18003AC2A
0x18003acdf  mov     edx, 3Ah ; ':'
0x18003ace4  jmp     loc_18003AC0C
0x18003ace9  mov     rcx, [rbp+ppIMFSample]
0x18003aced  mov     rdx, r15
0x18003acf0  mov     rax, [rcx]
0x18003acf3  mov     rax, [rax+130h]
0x18003acfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acff  mov     ebx, eax
0x18003ad01  test    eax, eax
0x18003ad03  jns     loc_18003AD9A
0x18003ad09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad10  test    rcx, rcx
0x18003ad13  jnz     short loc_18003AD5C
0x18003ad15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ad1c  nop     dword ptr [rax+rax+00h]
0x18003ad21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad28  mov     rcx, rax
0x18003ad2b  test    rax, rax
0x18003ad2e  jz      short loc_18003AD4E
0x18003ad30  mov     rax, [rax]
0x18003ad33  mov     edx, 7F0h
0x18003ad38  mov     rax, [rax+8]
0x18003ad3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad41  test    eax, eax
0x18003ad43  jz      short loc_18003AD4E
0x18003ad45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad4c  jmp     short loc_18003AD5C
0x18003ad4e  lea     rcx, qword_1801B97E0; this
0x18003ad55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ad5c  cmp     [rcx+8], r12b
0x18003ad60  jz      short loc_18003AD83
0x18003ad62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ad67  cmp     [rax+7CCh], ebx
0x18003ad6d  jz      short loc_18003AD83
0x18003ad6f  mov     r9d, ebx; int
0x18003ad72  mov     r8d, 30Ch; int
0x18003ad78  mov     rdx, r13; char *
0x18003ad7b  mov     rcx, rax; this
0x18003ad7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ad83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ad8a  jb      loc_18003AC2A
0x18003ad90  mov     edx, 3Bh ; ';'
0x18003ad95  jmp     loc_18003AC0C
0x18003ad9a  cmp     [rdi+0E0h], r12d
0x18003ada1  jz      loc_18003AE69
0x18003ada7  mov     rcx, [rbp+ppIMFSample]
0x18003adab  lea     rdx, MFSampleExtension_CleanPoint
0x18003adb2  mov     [rdi+0E0h], r12d
0x18003adb9  mov     r8d, 1
0x18003adbf  mov     rax, [rcx]
0x18003adc2  mov     rax, [rax+0A8h]
0x18003adc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adce  mov     ebx, eax
0x18003add0  test    eax, eax
0x18003add2  jns     loc_18003AE69
0x18003add8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003addf  test    rcx, rcx
0x18003ade2  jnz     short loc_18003AE2B
0x18003ade4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003adeb  nop     dword ptr [rax+rax+00h]
0x18003adf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003adf7  mov     rcx, rax
0x18003adfa  test    rax, rax
0x18003adfd  jz      short loc_18003AE1D
0x18003adff  mov     rax, [rax]
0x18003ae02  mov     edx, 7F0h
0x18003ae07  mov     rax, [rax+8]
0x18003ae0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae10  test    eax, eax
0x18003ae12  jz      short loc_18003AE1D
0x18003ae14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae1b  jmp     short loc_18003AE2B
0x18003ae1d  lea     rcx, qword_1801B97E0; this
0x18003ae24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae2b  cmp     [rcx+8], r12b
0x18003ae2f  jz      short loc_18003AE52
0x18003ae31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ae36  cmp     [rax+7CCh], ebx
0x18003ae3c  jz      short loc_18003AE52
0x18003ae3e  mov     r9d, ebx; int
0x18003ae41  mov     r8d, 315h; int
0x18003ae47  mov     rdx, r13; char *
0x18003ae4a  mov     rcx, rax; this
0x18003ae4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ae52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ae59  jb      loc_18003AC2A
0x18003ae5f  mov     edx, 3Ch ; '<'
0x18003ae64  jmp     loc_18003AC0C
0x18003ae69  mov     rcx, [rbp+ppIMFSample]
0x18003ae6d  mov     rdx, r14
0x18003ae70  mov     rax, [rcx]
0x18003ae73  mov     rax, [rax+150h]
0x18003ae7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae7f  mov     ebx, eax
0x18003ae81  test    eax, eax
0x18003ae83  jns     loc_18003AF1A
0x18003ae89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ae90  test    rcx, rcx
0x18003ae93  jnz     short loc_18003AEDC
0x18003ae95  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ae9c  nop     dword ptr [rax+rax+00h]
0x18003aea1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aea8  mov     rcx, rax
0x18003aeab  test    rax, rax
0x18003aeae  jz      short loc_18003AECE
0x18003aeb0  mov     rax, [rax]
0x18003aeb3  mov     edx, 7F0h
0x18003aeb8  mov     rax, [rax+8]
0x18003aebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aec1  test    eax, eax
0x18003aec3  jz      short loc_18003AECE
0x18003aec5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aecc  jmp     short loc_18003AEDC
0x18003aece  lea     rcx, qword_1801B97E0; this
0x18003aed5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003aedc  cmp     [rcx+8], r12b
0x18003aee0  jz      short loc_18003AF03
0x18003aee2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003aee7  cmp     [rax+7CCh], ebx
0x18003aeed  jz      short loc_18003AF03
0x18003aeef  mov     r9d, ebx; int
0x18003aef2  mov     r8d, 31Ah; int
0x18003aef8  mov     rdx, r13; char *
0x18003aefb  mov     rcx, rax; this
0x18003aefe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003af03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003af0a  jb      loc_18003AC2A
0x18003af10  mov     edx, 3Eh ; '>'
0x18003af15  jmp     loc_18003AC0C
0x18003af1a  mov     rcx, [rbp+ppIMFSample]
0x18003af1e  lea     rdx, [rbp+var_1C]
0x18003af22  mov     [rbp+var_1C], r12d
0x18003af26  mov     rax, [rcx]
0x18003af29  mov     rax, [rax+168h]
0x18003af30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af35  test    eax, eax
0x18003af37  js      short loc_18003AF42
0x18003af39  mov     eax, [rbp+var_1C]
0x18003af3c  add     [rdi+88h], eax
0x18003af42  mov     rcx, [rbp+ppIMFSample]
0x18003af46  lea     rdx, [rbp+var_18]
0x18003af4a  mov     rax, 7FFFFFFFFFFFFFFFh
0x18003af54  mov     [rbp+var_18], rax
0x18003af58  mov     rax, [rcx]
0x18003af5b  mov     rax, [rax+118h]
0x18003af62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af67  mov     rdx, [rbp+var_18]
0x18003af6b  test    eax, eax
0x18003af6d  js      short loc_18003AF76
0x18003af6f  mov     [rdi+90h], rdx
0x18003af76  mov     al, cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits
0x18003af7c  mov     r14b, 8
0x18003af7f  and     al, r14b
0x18003af82  mov     byte ptr [rbp+var_10], al
0x18003af85  jz      short loc_18003AFBB
0x18003af87  mov     eax, [rbp+var_1C]
0x18003af8a  lea     r8, [rbp+var_10]
0x18003af8e  mov     rcx, [rbp+ppIMFSample]
0x18003af92  mov     r9, rdi
0x18003af95  mov     [rsp+78h+var_40], rdx
0x18003af9a  lea     rdx, Process_Output
0x18003afa1  mov     [rsp+78h+var_48], eax
0x18003afa5  mov     [rsp+78h+var_50], rcx
0x18003afaa  mov     byte ptr [rsp+78h+var_58], 3
0x18003afaf  mov     [rbp+var_10], 4233504Dh
  ... truncated ...
```
