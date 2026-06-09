# CBytewiseMediaStream::CreateAndAddSampleToQueue(IMFMediaBuffer *,__int64,__int64)

- ea: `0x180008968`
- end: `0x1800090f4`
- name: `?CreateAndAddSampleToQueue@CBytewiseMediaStream@@QEAAJPEAUIMFMediaBuffer@@_J1@Z`
- size: `1932`
- prototype: `__int64 __fastcall(CBytewiseMediaStream *__hidden this, struct IMFMediaBuffer *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800090fc`

## callees

- `0x18000844c`
- `0x180008474`
- `0x1800086c8`
- `0x180008968`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180034d10`
- `0x180071a44`
- `0x180073b14`
- `0x18011b1e4`
- `0x1801477b4`
- `0x180163dcc`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008fb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008fb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800090bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ee6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ee6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008a7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008b4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008bfd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008cca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008d79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008f16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009039`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008a7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008b4e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008bfd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008cca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008d79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180008f16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009039`
- `MFPlat!MFCreateSample` at `0x180008a60`
- `MFPlat!MFCreateSample` at `0x180008a60`
- `MFPlat!MFPutWorkItem` at `0x18000901d`
- `MFPlat!MFPutWorkItem` at `0x18000901d`

## string_xrefs

- `0x1800089a1`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`
- `0x180008a0e`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`
- `0x180008ad3`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`
- `0x180008ba5`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`
- `0x180008c54`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`
- `0x180008d21`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`
- `0x180008dd0`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`
- `0x180008f6d`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`
- `0x180009090`: `CBytewiseMediaStream::CreateAndAddSampleToQueue`

## pseudocode

```c
__int64 __fastcall CBytewiseMediaStream::CreateAndAddSampleToQueue(
        CBytewiseMediaStream *this,
        struct IMFMediaBuffer *a2,
        __int64 a3,
        __int64 a4)
{
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  HRESULT v12; // ebx
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  IMFSample *v27; // rcx
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  int v36; // eax
  char v37; // dl
  unsigned int v38; // edx
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  IMFSample *ppIMFSample; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v50[4]; // [rsp+58h] [rbp-18h] BYREF
  int v51; // [rsp+5Ch] [rbp-14h] BYREF
  __int64 v52; // [rsp+60h] [rbp-10h] BYREF
  int v53; // [rsp+68h] [rbp-8h] BYREF

  v5 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v5 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
    v10 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v10 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v11 = 2 * v10;
      *((_QWORD *)ThreadRelativeContext + v11) = "CBytewiseMediaStream::CreateAndAddSampleToQueue";
      *((_DWORD *)ThreadRelativeContext + 2 * v11 + 2) = 761;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v5 = CallStackTracing::s_wpInstance;
  }
  if ( !a2 )
  {
    v12 = -2147467261;
    if ( !v5 )
    {
      CallStackTracing::InitInstance();
      v5 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)v13 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v13, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 770, -2147467261);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids,
        this,
        -2147467261);
    goto LABEL_112;
  }
  ppIMFSample = 0;
  v12 = MFCreateSample(&ppIMFSample);
  if ( v12 < 0 )
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
      if ( *((_DWORD *)v17 + 499) != v12 )
        CallStackContext::TraceFailure(v17, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 774, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v18 = 57;
    goto LABEL_26;
  }
  v12 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, a3);
  if ( v12 < 0 )
  {
    v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != v12 )
        CallStackContext::TraceFailure(v22, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 777, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v18 = 58;
    goto LABEL_26;
  }
  v12 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleDuration)(ppIMFSample, a4);
  if ( v12 < 0 )
  {
    v24 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
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
      if ( *((_DWORD *)v26 + 499) != v12 )
        CallStackContext::TraceFailure(v26, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 780, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v18 = 59;
    goto LABEL_26;
  }
  if ( *((_DWORD *)this + 56) )
  {
    v27 = ppIMFSample;
    *((_DWORD *)this + 56) = 0;
    v12 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))v27->lpVtbl->SetUINT32)(
            v27,
            &MFSampleExtension_CleanPoint,
            1);
    if ( v12 < 0 )
    {
      v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != v12 )
          CallStackContext::TraceFailure(v31, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 789, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 60;
      goto LABEL_26;
    }
  }
  v12 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, a2);
  if ( v12 < 0 )
  {
    v33 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v33 + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( *((_DWORD *)v35 + 499) != v12 )
        CallStackContext::TraceFailure(v35, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 794, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_27;
    v18 = 62;
LABEL_26:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this, v12);
LABEL_27:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
    goto LABEL_112;
  }
  v51 = 0;
  if ( ((int (__fastcall *)(IMFSample *, int *))ppIMFSample->lpVtbl->GetTotalLength)(ppIMFSample, &v51) >= 0 )
    *((_DWORD *)this + 34) += v51;
  v52 = 0x7FFFFFFFFFFFFFFFLL;
  v36 = ((__int64 (__fastcall *)(IMFSample *, __int64 *))ppIMFSample->lpVtbl->GetSampleTime)(ppIMFSample, &v52);
  v37 = v52;
  if ( v36 >= 0 )
    *((_QWORD *)this + 18) = v52;
  LOBYTE(v53) = Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 8) != 0 )
  {
    v53 = 1110659149;
    McTemplateU0s4pupqii_EventWriteTransfer(
      (_DWORD)ppIMFSample,
      (unsigned int)Process_Output,
      (unsigned int)&v53,
      (_DWORD)this,
      3,
      (char)ppIMFSample,
      v51,
      v37);
  }
  if ( (unsigned __int8)byte_1801B110B >= 8u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 63, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this);
    if ( (unsigned __int8)byte_1801B110B >= 8u )
      MFTRACE_SAMPLE_IMPL(0x30003u, v38, ppIMFSample);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !CVPtrList::AddTail((CBytewiseMediaStream *)((char *)this + 720), ppIMFSample) )
  {
    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
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
      if ( *((_DWORD *)v42 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v42, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 837, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_94;
    v43 = 64;
LABEL_93:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this, v12);
LABEL_94:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    goto LABEL_27;
  }
  ppIMFSample = 0;
  if ( (unsigned int)CBytewiseMediaStream::RefillingBuffer(this)
    && (unsigned int)CAudioBurstBufferStream::NeedMoreSamplesForBuffer((CBytewiseMediaStream *)((char *)this + 128)) )
  {
    if ( (unsigned __int8)byte_1801B110B >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 65, &WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids, this);
    v12 = MFPutWorkItem(5u, (IMFAsyncCallback *)this + 26, 0);
    if ( v12 < 0 )
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
          v45 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
        if ( *((_DWORD *)v47 + 499) != v12 )
          CallStackContext::TraceFailure(v47, "CBytewiseMediaStream::CreateAndAddSampleToQueue", 846, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_94;
      v43 = 66;
      goto LABEL_93;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ppIMFSample )
    ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
LABEL_112:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v50);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180008968  push    rbp
0x18000896a  push    rbx
0x18000896b  push    rsi
0x18000896c  push    rdi
0x18000896d  push    r12
0x18000896f  push    r14
0x180008971  push    r15
0x180008973  mov     rbp, rsp
0x180008976  sub     rsp, 70h
0x18000897a  mov     rdi, rcx
0x18000897d  xor     r12d, r12d
0x180008980  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008987  mov     r15, r9
0x18000898a  mov     r14, r8
0x18000898d  mov     rsi, rdx
0x180008990  test    rcx, rcx
0x180008993  jnz     short loc_1800089A1
0x180008995  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000899a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800089a1  lea     rbx, aCbytewisemedia_12; "CBytewiseMediaStream::CreateAndAddSampl"...
0x1800089a8  cmp     [rcx+8], r12b
0x1800089ac  jz      short loc_1800089DD
0x1800089ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800089b3  mov     ecx, [rax+7C4h]
0x1800089b9  cmp     ecx, [rax+7C8h]
0x1800089bf  jnb     short loc_1800089D0
0x1800089c1  add     rcx, rcx
0x1800089c4  mov     [rax+rcx*8], rbx
0x1800089c8  mov     dword ptr [rax+rcx*8+8], 2F9h
0x1800089d0  inc     dword ptr [rax+7C4h]
0x1800089d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800089dd  test    rsi, rsi
0x1800089e0  jnz     short loc_180008A58
0x1800089e2  mov     ebx, 80004003h
0x1800089e7  test    rcx, rcx
0x1800089ea  jnz     short loc_1800089F8
0x1800089ec  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800089f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800089f8  cmp     [rcx+8], r12b
0x1800089fc  jz      short loc_180008A23
0x1800089fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180008a03  cmp     [rax+7CCh], ebx
0x180008a09  jz      short loc_180008A23
0x180008a0b  mov     r9d, ebx; int
0x180008a0e  lea     rdx, aCbytewisemedia_12; "CBytewiseMediaStream::CreateAndAddSampl"...
0x180008a15  mov     r8d, 302h; int
0x180008a1b  mov     rcx, rax; this
0x180008a1e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180008a23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008a2a  jb      loc_1800090DA
0x180008a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a37  lea     r8, WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids
0x180008a3e  mov     edx, 38h ; '8'
0x180008a43  mov     [rsp+70h+var_50], ebx
0x180008a47  mov     r9, rdi
0x180008a4a  mov     rcx, [rcx+10h]
0x180008a4e  call    WPP_SF_qD
0x180008a53  jmp     loc_1800090DA
0x180008a58  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180008a5c  mov     [rbp+ppIMFSample], r12
0x180008a60  call    cs:__imp_MFCreateSample
0x180008a66  mov     ebx, eax
0x180008a68  test    eax, eax
0x180008a6a  jns     loc_180008B22
0x180008a70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008a77  test    rcx, rcx
0x180008a7a  jnz     short loc_180008ABD
0x180008a7c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180008a82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180008a89  mov     rcx, rax
0x180008a8c  test    rax, rax
0x180008a8f  jz      short loc_180008AAF
0x180008a91  mov     rax, [rax]
0x180008a94  mov     edx, 7F0h
0x180008a99  mov     rax, [rax+8]
0x180008a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aa2  test    eax, eax
0x180008aa4  jz      short loc_180008AAF
0x180008aa6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008aad  jmp     short loc_180008ABD
0x180008aaf  lea     rcx, qword_1801B07E0; this
0x180008ab6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008abd  cmp     [rcx+8], r12b
0x180008ac1  jz      short loc_180008AE8
0x180008ac3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180008ac8  cmp     [rax+7CCh], ebx
0x180008ace  jz      short loc_180008AE8
0x180008ad0  mov     r9d, ebx; int
0x180008ad3  lea     rdx, aCbytewisemedia_12; "CBytewiseMediaStream::CreateAndAddSampl"...
0x180008ada  mov     r8d, 306h; int
0x180008ae0  mov     rcx, rax; this
0x180008ae3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180008ae8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008aef  jb      short loc_180008B14
0x180008af1  mov     edx, 39h ; '9'
0x180008af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008afd  lea     r8, WPP_947c3c6429ea3ad5277d9afb636453c5_Traceguids
0x180008b04  mov     r9, rdi
0x180008b07  mov     [rsp+70h+var_50], ebx
0x180008b0b  mov     rcx, [rcx+10h]
0x180008b0f  call    WPP_SF_qD
0x180008b14  lea     rcx, [rbp+ppIMFSample]; void *
0x180008b18  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180008b1d  jmp     loc_1800090DA
0x180008b22  mov     rcx, [rbp+ppIMFSample]
0x180008b26  mov     rdx, r14
0x180008b29  mov     rax, [rcx]
0x180008b2c  mov     rax, [rax+120h]
0x180008b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b38  mov     ebx, eax
0x180008b3a  test    eax, eax
0x180008b3c  jns     loc_180008BD1
0x180008b42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008b49  test    rcx, rcx
0x180008b4c  jnz     short loc_180008B8F
0x180008b4e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180008b54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180008b5b  mov     rcx, rax
0x180008b5e  test    rax, rax
0x180008b61  jz      short loc_180008B81
0x180008b63  mov     rax, [rax]
0x180008b66  mov     edx, 7F0h
0x180008b6b  mov     rax, [rax+8]
0x180008b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b74  test    eax, eax
0x180008b76  jz      short loc_180008B81
0x180008b78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008b7f  jmp     short loc_180008B8F
0x180008b81  lea     rcx, qword_1801B07E0; this
0x180008b88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008b8f  cmp     [rcx+8], r12b
0x180008b93  jz      short loc_180008BBA
0x180008b95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180008b9a  cmp     [rax+7CCh], ebx
0x180008ba0  jz      short loc_180008BBA
0x180008ba2  mov     r9d, ebx; int
0x180008ba5  lea     rdx, aCbytewisemedia_12; "CBytewiseMediaStream::CreateAndAddSampl"...
0x180008bac  mov     r8d, 309h; int
0x180008bb2  mov     rcx, rax; this
0x180008bb5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180008bba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008bc1  jb      loc_180008B14
0x180008bc7  mov     edx, 3Ah ; ':'
0x180008bcc  jmp     loc_180008AF6
0x180008bd1  mov     rcx, [rbp+ppIMFSample]
0x180008bd5  mov     rdx, r15
0x180008bd8  mov     rax, [rcx]
0x180008bdb  mov     rax, [rax+130h]
0x180008be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008be7  mov     ebx, eax
0x180008be9  test    eax, eax
0x180008beb  jns     loc_180008C80
0x180008bf1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008bf8  test    rcx, rcx
0x180008bfb  jnz     short loc_180008C3E
0x180008bfd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180008c03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180008c0a  mov     rcx, rax
0x180008c0d  test    rax, rax
0x180008c10  jz      short loc_180008C30
0x180008c12  mov     rax, [rax]
0x180008c15  mov     edx, 7F0h
0x180008c1a  mov     rax, [rax+8]
0x180008c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c23  test    eax, eax
0x180008c25  jz      short loc_180008C30
0x180008c27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008c2e  jmp     short loc_180008C3E
0x180008c30  lea     rcx, qword_1801B07E0; this
0x180008c37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008c3e  cmp     [rcx+8], r12b
0x180008c42  jz      short loc_180008C69
0x180008c44  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180008c49  cmp     [rax+7CCh], ebx
0x180008c4f  jz      short loc_180008C69
0x180008c51  mov     r9d, ebx; int
0x180008c54  lea     rdx, aCbytewisemedia_12; "CBytewiseMediaStream::CreateAndAddSampl"...
0x180008c5b  mov     r8d, 30Ch; int
0x180008c61  mov     rcx, rax; this
0x180008c64  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180008c69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008c70  jb      loc_180008B14
0x180008c76  mov     edx, 3Bh ; ';'
0x180008c7b  jmp     loc_180008AF6
0x180008c80  cmp     [rdi+0E0h], r12d
0x180008c87  jz      loc_180008D4D
0x180008c8d  mov     rcx, [rbp+ppIMFSample]
0x180008c91  lea     rdx, MFSampleExtension_CleanPoint
0x180008c98  mov     [rdi+0E0h], r12d
0x180008c9f  mov     r8d, 1
0x180008ca5  mov     rax, [rcx]
0x180008ca8  mov     rax, [rax+0A8h]
0x180008caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb4  mov     ebx, eax
0x180008cb6  test    eax, eax
0x180008cb8  jns     loc_180008D4D
0x180008cbe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008cc5  test    rcx, rcx
0x180008cc8  jnz     short loc_180008D0B
0x180008cca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180008cd0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180008cd7  mov     rcx, rax
0x180008cda  test    rax, rax
0x180008cdd  jz      short loc_180008CFD
0x180008cdf  mov     rax, [rax]
0x180008ce2  mov     edx, 7F0h
0x180008ce7  mov     rax, [rax+8]
0x180008ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf0  test    eax, eax
0x180008cf2  jz      short loc_180008CFD
0x180008cf4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008cfb  jmp     short loc_180008D0B
0x180008cfd  lea     rcx, qword_1801B07E0; this
0x180008d04  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008d0b  cmp     [rcx+8], r12b
0x180008d0f  jz      short loc_180008D36
0x180008d11  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180008d16  cmp     [rax+7CCh], ebx
0x180008d1c  jz      short loc_180008D36
0x180008d1e  mov     r9d, ebx; int
0x180008d21  lea     rdx, aCbytewisemedia_12; "CBytewiseMediaStream::CreateAndAddSampl"...
0x180008d28  mov     r8d, 315h; int
0x180008d2e  mov     rcx, rax; this
0x180008d31  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180008d36  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008d3d  jb      loc_180008B14
0x180008d43  mov     edx, 3Ch ; '<'
0x180008d48  jmp     loc_180008AF6
0x180008d4d  mov     rcx, [rbp+ppIMFSample]
0x180008d51  mov     rdx, rsi
0x180008d54  mov     rax, [rcx]
0x180008d57  mov     rax, [rax+150h]
0x180008d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d63  mov     ebx, eax
0x180008d65  test    eax, eax
0x180008d67  jns     loc_180008DFC
0x180008d6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008d74  test    rcx, rcx
0x180008d77  jnz     short loc_180008DBA
0x180008d79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180008d7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180008d86  mov     rcx, rax
0x180008d89  test    rax, rax
0x180008d8c  jz      short loc_180008DAC
0x180008d8e  mov     rax, [rax]
0x180008d91  mov     edx, 7F0h
0x180008d96  mov     rax, [rax+8]
0x180008d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d9f  test    eax, eax
0x180008da1  jz      short loc_180008DAC
0x180008da3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008daa  jmp     short loc_180008DBA
0x180008dac  lea     rcx, qword_1801B07E0; this
0x180008db3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180008dba  cmp     [rcx+8], r12b
0x180008dbe  jz      short loc_180008DE5
0x180008dc0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180008dc5  cmp     [rax+7CCh], ebx
0x180008dcb  jz      short loc_180008DE5
0x180008dcd  mov     r9d, ebx; int
0x180008dd0  lea     rdx, aCbytewisemedia_12; "CBytewiseMediaStream::CreateAndAddSampl"...
0x180008dd7  mov     r8d, 31Ah; int
0x180008ddd  mov     rcx, rax; this
0x180008de0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180008de5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008dec  jb      loc_180008B14
0x180008df2  mov     edx, 3Eh ; '>'
0x180008df7  jmp     loc_180008AF6
0x180008dfc  mov     rcx, [rbp+ppIMFSample]
0x180008e00  lea     rdx, [rbp+var_14]
0x180008e04  mov     [rbp+var_14], r12d
0x180008e08  mov     rax, [rcx]
0x180008e0b  mov     rax, [rax+168h]
0x180008e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e17  test    eax, eax
0x180008e19  js      short loc_180008E24
0x180008e1b  mov     eax, [rbp+var_14]
0x180008e1e  add     [rdi+88h], eax
0x180008e24  mov     rcx, [rbp+ppIMFSample]
0x180008e28  lea     rdx, [rbp+var_10]
0x180008e2c  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008e36  mov     [rbp+var_10], rax
0x180008e3a  mov     rax, [rcx]
0x180008e3d  mov     rax, [rax+118h]
0x180008e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e49  mov     rdx, [rbp+var_10]
0x180008e4d  test    eax, eax
0x180008e4f  js      short loc_180008E58
0x180008e51  mov     [rdi+90h], rdx
0x180008e58  mov     al, cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits
0x180008e5e  mov     r14b, 8
0x180008e61  and     al, r14b
0x180008e64  mov     byte ptr [rbp+var_8], al
0x180008e67  jz      short loc_180008E9D
0x180008e69  mov     eax, [rbp+var_14]
0x180008e6c  lea     r8, [rbp+var_8]
0x180008e70  mov     rcx, [rbp+ppIMFSample]
0x180008e74  mov     r9, rdi
0x180008e77  mov     [rsp+70h+var_38], rdx
0x180008e7c  lea     rdx, Process_Output
  ... truncated ...
```
