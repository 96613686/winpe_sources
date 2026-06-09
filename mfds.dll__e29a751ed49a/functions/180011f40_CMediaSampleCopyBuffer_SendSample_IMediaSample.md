# CMediaSampleCopyBuffer::SendSample(IMediaSample *)

- ea: `0x180011f40`
- end: `0x18001284d`
- name: `?SendSample@CMediaSampleCopyBuffer@@AEAAJPEAUIMediaSample@@@Z`
- size: `2317`
- prototype: `__int64 __fastcall(CMediaSampleCopyBuffer *__hidden this, struct IMediaSample *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x180010400`
- `0x1800141a0`

## callees

- `0x180002820`
- `0x1800052c0`
- `0x18000b8c0`
- `0x180011950`
- `0x180011f40`
- `0x1800140b0`
- `0x18002329c`
- `0x18002d514`
- `0x180049d04`
- `0x180051ce4`
- `0x180074160`
- `0x18007c8e8`
- `0x1800a3738`
- `0x1800a5ca0`
- `0x1800b977c`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800122aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800122aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800122c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800122c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012377`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001234a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001234a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012564`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800123c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800123c6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001235c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001235c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800127fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800127fe`

## string_xrefs

- `0x180012304`: `CMediaSampleCopyBuffer::SendSample`

## pseudocode

```c
__int64 __fastcall CMediaSampleCopyBuffer::SendSample(LPCRITICAL_SECTION *this, struct IMediaSample *a2)
{
  LPCRITICAL_SECTION v4; // r14
  int v5; // r13d
  struct IMediaSampleVtbl *lpVtbl; // rax
  __int64 v7; // rbx
  int v8; // esi
  int (__fastcall *v9)(__int64, struct IMediaSample **, _OWORD *, __int64 *); // rax
  struct IMediaSampleVtbl *v10; // rax
  struct IMediaSampleVtbl *v11; // rax
  unsigned int *OwningThread; // r12
  bool v13; // zf
  struct IMediaSampleVtbl *v14; // rax
  int v15; // eax
  struct IMediaSampleVtbl *v16; // rcx
  __int64 v17; // rsi
  _QWORD *v18; // rax
  _DWORD *v19; // rcx
  struct IMediaSampleVtbl *v20; // rax
  unsigned int *v21; // rbx
  __int64 v22; // rax
  int (__fastcall *v23)(struct _AMMediaType *, GUID *, _OWORD *, __int64 *); // rax
  __int64 v24; // rax
  CMMCSSOutputQueue *v25; // rcx
  int v26; // esi
  CallStackTracing *v27; // rbx
  struct CallStackContext *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  GUID *v31; // rdi
  DWORD LastError; // r14d
  GUID *Value; // rax
  int v34; // eax
  int v35; // eax
  CallStackTracing *v37; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v39; // rcx
  __int64 v40; // rcx
  _QWORD *v41; // rax
  _DWORD *v42; // rcx
  unsigned int (__fastcall *v43)(_QWORD, _QWORD, _QWORD); // rax
  _OWORD *v44; // rax
  __int128 v45; // xmm1
  CallStackTracing *v46; // rcx
  __int64 v47; // rax
  unsigned int (__fastcall *v48)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v49; // rcx
  int v50; // eax
  int v51; // eax
  __int64 v52; // rax
  int v53; // eax
  CallStackTracing *v54; // rax
  char v55[8]; // [rsp+40h] [rbp-89h] BYREF
  __int64 v56; // [rsp+48h] [rbp-81h] BYREF
  struct _AMMediaType *pv; // [rsp+50h] [rbp-79h] BYREF
  __int64 v58; // [rsp+58h] [rbp-71h] BYREF
  struct IMediaSample *v59[2]; // [rsp+60h] [rbp-69h] BYREF
  __int128 v60; // [rsp+70h] [rbp-59h]
  __int128 v61; // [rsp+80h] [rbp-49h]
  __int64 v62; // [rsp+90h] [rbp-39h]
  GUID v63; // [rsp+A0h] [rbp-29h] BYREF
  int v64; // [rsp+B0h] [rbp-19h]
  _OWORD v65[2]; // [rsp+C0h] [rbp-9h] BYREF

  ((void (__fastcall *)(struct IMediaSample *))a2->lpVtbl->AddRef)(a2);
  LeaveCriticalSection(this[6]);
  v4 = this[4];
  v5 = 0;
  v58 = 0;
  pv = 0;
  v56 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)v4[1].LockSemaphore);
  if ( *(_QWORD *)&v4[9].LockCount )
  {
    if ( !((unsigned int (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsDiscontinuity)(a2)
      && (unsigned int)CMPEG2Demultiplexer::IsSeekable((CMPEG2Demultiplexer *)v4[2].DebugInfo)
      && (int)CMpeg2DemuxMediaSeekingCore::RecvThreadGetSegmentValues(
                (CMpeg2DemuxMediaSeekingCore *)v4[12].DebugInfo,
                &v58,
                &v56,
                (double *)&pv) >= 0 )
    {
      CMMCSSOutputQueue::NewSegment(*(CMMCSSOutputQueue **)&v4[9].LockCount, v58, v56, *(double *)&pv);
    }
    ((void (__fastcall *)(struct IMediaSample *))a2->lpVtbl->AddRef)(a2);
    lpVtbl = a2->lpVtbl;
    v56 = 0;
    v7 = 0;
    v8 = ((__int64 (__fastcall *)(struct IMediaSample *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a2,
           &IID_IAttributeGet,
           &v56);
    if ( v8 >= 0 && v56 )
    {
      LODWORD(v58) = 28;
      memset(v65, 0, 28);
      v9 = *(int (__fastcall **)(__int64, struct IMediaSample **, _OWORD *, __int64 *))(*(_QWORD *)v56 + 40LL);
      *(GUID *)v59 = DSATTRIB_PBDATAG_ATTRIBUTE;
      v7 = v9(v56, v59, v65, &v58) >= 0;
      LODWORD(v58) = 20;
      v64 = 0;
      *(GUID *)v59 = DSATTRIB_DSHOW_STREAM_DESC;
      v63 = 0;
      if ( (*(int (__fastcall **)(__int64, struct IMediaSample **, GUID *, __int64 *))(*(_QWORD *)v56 + 40LL))(
             v56,
             v59,
             &v63,
             &v58) >= 0 )
        v7 |= 4uLL;
    }
    else
    {
      v37 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v37 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v37);
        v39 = *((unsigned int *)ThreadRelativeContext + 497);
        if ( (unsigned int)v39 < *((_DWORD *)ThreadRelativeContext + 498) )
        {
          v40 = 2 * v39;
          *((_QWORD *)ThreadRelativeContext + v40) = "CMPEG2DemuxOutputPin::GetDemuxSampleAttrib";
          *((_DWORD *)ThreadRelativeContext + 2 * v40 + 2) = 715;
        }
        ++*((_DWORD *)ThreadRelativeContext + 497);
      }
      if ( byte_1800EACCB )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 29, &WPP_89c6d11f487739c3770de58ece25afb2_Traceguids, v4, v8);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
    }
    v10 = a2->lpVtbl;
    pv = 0;
    if ( ((int (__fastcall *)(struct IMediaSample *, struct _AMMediaType **))v10->GetMediaType)(a2, &pv) >= 0 && pv )
    {
      v7 |= 2uLL;
      DeleteMediaType(pv);
    }
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v11 = a2->lpVtbl;
    OwningThread = (unsigned int *)v4[9].OwningThread;
    pv = 0;
    v59[0] = 0;
    LOBYTE(v5) = ((unsigned int (__fastcall *)(struct IMediaSample *))v11->IsSyncPoint)(a2) == 0;
    v13 = ((unsigned int (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsDiscontinuity)(a2) == 0;
    v14 = a2->lpVtbl;
    LODWORD(v58) = v13;
    v15 = ((__int64 (__fastcall *)(struct IMediaSample *))v14->GetActualDataLength)(a2);
    v16 = a2->lpVtbl;
    LODWORD(v56) = v15;
    if ( ((int (__fastcall *)(struct IMediaSample *, struct _AMMediaType **, struct IMediaSample **))v16->GetTime)(
           a2,
           &pv,
           v59) < 0 )
      LODWORD(v17) = -1;
    else
      v17 = (__int64)pv / 10000;
    v18 = (_QWORD *)*((_QWORD *)OwningThread + 1132);
    v19 = (_DWORD *)*v18;
    if ( *(_DWORD *)*v18 )
    {
      if ( *((_QWORD *)OwningThread + 1129) )
      {
        v48 = *(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(v18[2] + 48LL);
        if ( v48 )
        {
          if ( v48((unsigned int)v19[1], OwningThread[2260], *((unsigned __int8 *)OwningThread + 9044)) )
          {
            v49 = *((_QWORD *)OwningThread + 1129);
            v50 = v58;
            *(_DWORD *)v49 = 0;
            *(_DWORD *)(v49 + 4) = v17;
            *(_DWORD *)(v49 + 8) = v5;
            *(_DWORD *)(v49 + 12) = v50;
            v51 = v56;
            *(_DWORD *)(v49 + 16) = -1;
            *(_DWORD *)(v49 + 20) = v51;
            v52 = v62;
            *(_QWORD *)(v49 + 24) = v7;
            *(_QWORD *)(v49 + 32) = v52;
            Mpeg2DemuxTrace::CeHomeETWDLL::ehTraceEvent(
              *(Mpeg2DemuxTrace::CeHomeETWDLL **)(*((_QWORD *)OwningThread + 1132) + 16LL),
              *(_DWORD *)(**((_QWORD **)OwningThread + 1132) + 4LL),
              OwningThread[2262],
              *((void **)OwningThread + 1129),
              OwningThread[2260],
              *((_BYTE *)OwningThread + 9044),
              *((_BYTE *)OwningThread + 9045));
          }
        }
      }
    }
    if ( *(_QWORD *)OwningThread )
      ++*(_QWORD *)(*(_QWORD *)OwningThread + 96LL);
    v20 = a2->lpVtbl;
    v21 = (unsigned int *)v4[9].OwningThread;
    pv = 0;
    if ( ((int (__fastcall *)(struct IMediaSample *, GUID *, struct _AMMediaType **))v20->QueryInterface)(
           a2,
           &IID_IAttributeGet,
           &pv) >= 0 )
    {
      if ( !pv )
      {
LABEL_23:
        v25 = *(CMMCSSOutputQueue **)&v4[9].LockCount;
        v59[0] = a2;
        LODWORD(v56) = 0;
        v26 = CMMCSSOutputQueue::ReceiveMultiple(v25, v59, 1, (int *)&v56);
        if ( v26 )
        {
          CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v55, "CMPEG2DemuxOutputPin::SendSample", 647);
          if ( byte_1800EACCB )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              27,
              &WPP_89c6d11f487739c3770de58ece25afb2_Traceguids,
              v4,
              v26);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
          if ( v26 >= 0 )
            v26 = -2147467259;
        }
        else
        {
          v26 = 0;
        }
        goto LABEL_25;
      }
      v59[0] = 0;
      LODWORD(v56) = 24;
      memset(v65, 0, 24);
      LODWORD(v58) = 8;
      v22 = *(_QWORD *)&pv->majortype.Data1;
      v60 = 0;
      v61 = 0;
      v23 = *(int (__fastcall **)(struct _AMMediaType *, GUID *, _OWORD *, __int64 *))(v22 + 40);
      v63 = DSATTRIB_TRANSPORT_PROPERTIES;
      if ( v23(pv, &v63, v65, &v56) >= 0 )
      {
        v24 = *(_QWORD *)&pv->majortype.Data1;
        v63 = DSATTRIB_CAPTURE_STREAMTIME;
        if ( (*(int (__fastcall **)(struct _AMMediaType *, GUID *, struct IMediaSample **, __int64 *))(v24 + 40))(
               pv,
               &v63,
               v59,
               &v58) >= 0 )
        {
          LODWORD(v60) = v65[0];
          *((_QWORD *)&v60 + 1) = *((_QWORD *)&v65[0] + 1);
          *(struct IMediaSample **)&v61 = v59[0];
          BYTE8(v61) = v65[1];
          v41 = (_QWORD *)*((_QWORD *)v21 + 1137);
          v42 = (_DWORD *)*v41;
          if ( *(_DWORD *)*v41 )
          {
            if ( *((_QWORD *)v21 + 1134) )
            {
              v43 = *(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(v41[2] + 48LL);
              if ( v43 )
              {
                if ( v43((unsigned int)v42[1], v21[2270], *((unsigned __int8 *)v21 + 9084)) )
                {
                  v44 = (_OWORD *)*((_QWORD *)v21 + 1134);
                  v45 = v61;
                  *v44 = v60;
                  v44[1] = v45;
                  Mpeg2DemuxTrace::CeHomeETWDLL::ehTraceEvent(
                    *(Mpeg2DemuxTrace::CeHomeETWDLL **)(*((_QWORD *)v21 + 1137) + 16LL),
                    *(_DWORD *)(**((_QWORD **)v21 + 1137) + 4LL),
                    v21[2272],
                    *((void **)v21 + 1134),
                    v21[2270],
                    *((_BYTE *)v21 + 9084),
                    *((_BYTE *)v21 + 9085));
                }
              }
            }
          }
        }
      }
    }
    if ( pv )
      (*(void (__fastcall **)(struct _AMMediaType *))(*(_QWORD *)&pv->majortype.Data1 + 16LL))(pv);
    goto LABEL_23;
  }
  v26 = -2147220983;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v55, "CMPEG2DemuxOutputPin::SendSample", 659);
  if ( byte_1800EACCB )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 28, &WPP_89c6d11f487739c3770de58ece25afb2_Traceguids, v4);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
LABEL_25:
  LeaveCriticalSection((LPCRITICAL_SECTION)v4[1].LockSemaphore);
  ((void (__fastcall *)(struct IMediaSample *))a2->lpVtbl->Release)(a2);
  EnterCriticalSection(this[6]);
  v27 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v27 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v27 + 8) )
  {
    v28 = CallStackTracing::GetThreadRelativeContext(v27);
    v29 = *((unsigned int *)v28 + 497);
    if ( (unsigned int)v29 < *((_DWORD *)v28 + 498) )
    {
      v30 = 2 * v29;
      *((_QWORD *)v28 + v30) = "CMediaSampleCopyBuffer::SendSample";
      *((_DWORD *)v28 + 2 * v30 + 2) = 458;
    }
    ++*((_DWORD *)v28 + 497);
    v27 = CallStackTracing::s_wpInstance;
  }
  if ( (unsigned __int8)byte_1800EACCB >= 4u )
  {
    v53 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->GetActualDataLength)(a2);
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      23,
      &WPP_b467d45eb0bb36498164de9a7182f43b_Traceguids,
      this,
      a2,
      v53);
    v27 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v27 + 8) )
  {
    v31 = (GUID *)((char *)v27 + 208);
    LastError = GetLastError();
    Value = (GUID *)TlsGetValue(*((_DWORD *)v27 + 3));
    if ( Value )
    {
      v31 = Value;
    }
    else if ( !GetLastError() )
    {
      v46 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v54;
        if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
        {
          v46 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v47 = (**(__int64 (__fastcall ***)(CallStackTracing *))v46)(v46);
      if ( v47 )
        v31 = (GUID *)v47;
    }
    SetLastError(LastError);
    v34 = *(_DWORD *)&v31[124].Data2;
    if ( v34 )
    {
      v35 = v34 - 1;
      *(_DWORD *)&v31[124].Data2 = v35;
      if ( !v35 )
      {
        *(_DWORD *)&v31[124].Data2 = 0;
        *(_QWORD *)&v31[126].Data1 = 0;
        *(_DWORD *)&v31[124].Data4[4] = 0;
        v31[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v31[126].Data4 = 0;
        v31[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180011f40  push    rbp
0x180011f42  push    rbx
0x180011f43  push    rsi
0x180011f44  push    rdi
0x180011f45  push    r13
0x180011f47  push    r14
0x180011f49  lea     rbp, [rsp-2Fh]
0x180011f4e  sub     rsp, 0F8h
0x180011f55  mov     rax, cs:__security_cookie
0x180011f5c  xor     rax, rsp
0x180011f5f  mov     [rbp+57h+var_40], rax
0x180011f63  mov     rax, [rdx]
0x180011f66  mov     rdi, rdx
0x180011f69  mov     [rsp+120h+var_30], r15
0x180011f71  mov     r15, rcx
0x180011f74  mov     rcx, rdx
0x180011f77  mov     rax, [rax+8]
0x180011f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f80  mov     rcx, [r15+30h]; lpCriticalSection
0x180011f84  call    cs:__imp_LeaveCriticalSection
0x180011f8b  nop     dword ptr [rax+rax+00h]
0x180011f90  mov     r14, [r15+20h]
0x180011f94  xor     r13d, r13d
0x180011f97  xorps   xmm0, xmm0
0x180011f9a  mov     [rbp+57h+var_C8], r13
0x180011f9e  movsd   [rbp+57h+pv], xmm0
0x180011fa3  mov     [rsp+120h+var_D8], r13
0x180011fa8  mov     rcx, [r14+40h]; lpCriticalSection
0x180011fac  call    cs:__imp_EnterCriticalSection
0x180011fb3  nop     dword ptr [rax+rax+00h]
0x180011fb8  cmp     [r14+170h], r13
0x180011fbf  jz      loc_18001252C
0x180011fc5  mov     rax, [rdi]
0x180011fc8  mov     rcx, rdi
0x180011fcb  mov     [rsp+120h+arg_10], r12
0x180011fd3  mov     rax, [rax+78h]
0x180011fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fdc  test    eax, eax
0x180011fde  jz      loc_18001259F
0x180011fe4  mov     rax, [rdi]
0x180011fe7  mov     rcx, rdi
0x180011fea  mov     rax, [rax+8]
0x180011fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ff3  mov     rax, [rdi]
0x180011ff6  lea     r8, [rsp+120h+var_D8]
0x180011ffb  lea     rdx, IID_IAttributeGet
0x180012002  mov     [rsp+120h+var_D8], r13
0x180012007  mov     rcx, rdi
0x18001200a  mov     rbx, r13
0x18001200d  mov     rax, [rax]
0x180012010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012015  mov     esi, eax
0x180012017  test    eax, eax
0x180012019  js      loc_1800123F7
0x18001201f  mov     rcx, [rsp+120h+var_D8]
0x180012024  test    rcx, rcx
0x180012027  jz      loc_1800123F7
0x18001202d  xorps   xmm0, xmm0
0x180012030  mov     dword ptr [rbp+57h+var_C8], 1Ch
0x180012037  movups  [rbp+57h+var_60], xmm0
0x18001203b  lea     r9, [rbp+57h+var_C8]
0x18001203f  movups  [rbp+57h+var_60+0Ch], xmm0
0x180012043  mov     rax, [rcx]
0x180012046  lea     r8, [rbp+57h+var_60]
0x18001204a  movups  xmm0, xmmword ptr cs:DSATTRIB_PBDATAG_ATTRIBUTE.Data1
0x180012051  lea     rdx, [rbp+57h+var_C0]
0x180012055  mov     rax, [rax+28h]
0x180012059  movaps  xmmword ptr [rbp+57h+var_C0], xmm0
0x18001205d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012062  test    eax, eax
0x180012064  jns     loc_1800125F0
0x18001206a  mov     rcx, [rsp+120h+var_D8]
0x18001206f  lea     r9, [rbp+57h+var_C8]
0x180012073  movups  xmm1, xmmword ptr cs:DSATTRIB_DSHOW_STREAM_DESC.Data1
0x18001207a  xor     eax, eax
0x18001207c  mov     dword ptr [rbp+57h+var_C8], 14h
0x180012083  mov     [rbp+57h+var_70], eax
0x180012086  lea     r8, [rbp+57h+var_80]
0x18001208a  xorps   xmm0, xmm0
0x18001208d  movaps  xmmword ptr [rbp+57h+var_C0], xmm1
0x180012091  movups  [rbp+57h+var_80], xmm0
0x180012095  mov     rax, [rcx]
0x180012098  lea     rdx, [rbp+57h+var_C0]
0x18001209c  mov     rax, [rax+28h]
0x1800120a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a5  test    eax, eax
0x1800120a7  jns     loc_1800125FA
0x1800120ad  mov     rax, [rdi]
0x1800120b0  lea     rdx, [rbp+57h+pv]
0x1800120b4  mov     rcx, rdi
0x1800120b7  mov     [rbp+57h+pv], r13
0x1800120bb  mov     rax, [rax+68h]
0x1800120bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c4  test    eax, eax
0x1800120c6  js      short loc_1800120D5
0x1800120c8  mov     rcx, [rbp+57h+pv]; pv
0x1800120cc  test    rcx, rcx
0x1800120cf  jnz     loc_18001263F
0x1800120d5  mov     rcx, [rsp+120h+var_D8]
0x1800120da  test    rcx, rcx
0x1800120dd  jz      short loc_1800120EB
0x1800120df  mov     rax, [rcx]
0x1800120e2  mov     rax, [rax+10h]
0x1800120e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120eb  mov     rax, [rdi]
0x1800120ee  mov     rcx, rdi
0x1800120f1  mov     r12, [r14+178h]
0x1800120f8  mov     [rbp+57h+pv], r13
0x1800120fc  mov     [rbp+57h+var_C0], r13
0x180012100  mov     rax, [rax+38h]
0x180012104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012109  test    eax, eax
0x18001210b  mov     rcx, rdi
0x18001210e  mov     rax, [rdi]
0x180012111  setz    r13b
0x180012115  mov     rax, [rax+78h]
0x180012119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001211e  xor     ecx, ecx
0x180012120  test    eax, eax
0x180012122  mov     rax, [rdi]
0x180012125  setz    cl
0x180012128  mov     dword ptr [rbp+57h+var_C8], ecx
0x18001212b  mov     rcx, rdi
0x18001212e  mov     rax, [rax+58h]
0x180012132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012137  mov     rcx, [rdi]
0x18001213a  lea     r8, [rbp+57h+var_C0]
0x18001213e  mov     dword ptr [rsp+120h+var_D8], eax
0x180012142  lea     rdx, [rbp+57h+pv]
0x180012146  mov     rax, [rcx+28h]
0x18001214a  mov     rcx, rdi
0x18001214d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012152  test    eax, eax
0x180012154  js      loc_180012522
0x18001215a  mov     rax, 346DC5D63886594Bh
0x180012164  imul    [rbp+57h+pv]
0x180012168  mov     rsi, rdx
0x18001216b  sar     rsi, 0Bh
0x18001216f  mov     rax, rsi
0x180012172  shr     rax, 3Fh
0x180012176  add     rsi, rax
0x180012179  mov     rax, [r12+2360h]
0x180012181  mov     rcx, [rax]
0x180012184  cmp     dword ptr [rcx], 0
0x180012187  jnz     loc_18001264D
0x18001218d  mov     rax, [r12]
0x180012191  mov     r12, [rsp+120h+arg_10]
0x180012199  test    rax, rax
0x18001219c  jnz     loc_180012715
0x1800121a2  mov     rax, [rdi]
0x1800121a5  lea     r8, [rbp+57h+pv]
0x1800121a9  mov     rbx, [r14+178h]
0x1800121b0  lea     rdx, IID_IAttributeGet
0x1800121b7  xor     r13d, r13d
0x1800121ba  mov     rcx, rdi
0x1800121bd  mov     [rbp+57h+pv], r13
0x1800121c1  mov     rax, [rax]
0x1800121c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121c9  test    eax, eax
0x1800121cb  js      loc_180012260
0x1800121d1  mov     rcx, [rbp+57h+pv]
0x1800121d5  test    rcx, rcx
0x1800121d8  jz      loc_180012275
0x1800121de  xor     eax, eax
0x1800121e0  mov     [rbp+57h+var_C0], r13
0x1800121e4  xorps   xmm0, xmm0
0x1800121e7  mov     [rbp+57h+var_50], rax
0x1800121eb  xorps   xmm1, xmm1
0x1800121ee  mov     dword ptr [rsp+120h+var_D8], 18h
0x1800121f6  movups  [rbp+57h+var_60], xmm1
0x1800121fa  mov     dword ptr [rbp+57h+var_C8], 8
0x180012201  lea     r9, [rsp+120h+var_D8]
0x180012206  mov     rax, [rcx]
0x180012209  lea     r8, [rbp+57h+var_60]
0x18001220d  movups  [rbp+57h+var_B0], xmm0
0x180012211  lea     rdx, [rbp+57h+var_80]
0x180012215  movups  [rbp+57h+var_A0], xmm0
0x180012219  mov     rax, [rax+28h]
0x18001221d  movups  xmm0, xmmword ptr cs:DSATTRIB_TRANSPORT_PROPERTIES.Data1
0x180012224  movaps  [rbp+57h+var_80], xmm0
0x180012228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001222d  test    eax, eax
0x18001222f  js      short loc_180012260
0x180012231  mov     rcx, [rbp+57h+pv]
0x180012235  lea     r9, [rbp+57h+var_C8]
0x180012239  movups  xmm0, xmmword ptr cs:DSATTRIB_CAPTURE_STREAMTIME.Data1
0x180012240  lea     r8, [rbp+57h+var_C0]
0x180012244  lea     rdx, [rbp+57h+var_80]
0x180012248  mov     rax, [rcx]
0x18001224b  movaps  [rbp+57h+var_80], xmm0
0x18001224f  mov     rax, [rax+28h]
0x180012253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012258  test    eax, eax
0x18001225a  jns     loc_180012457
0x180012260  mov     rcx, [rbp+57h+pv]
0x180012264  test    rcx, rcx
0x180012267  jz      short loc_180012275
0x180012269  mov     rax, [rcx]
0x18001226c  mov     rax, [rax+10h]
0x180012270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012275  mov     rcx, [r14+170h]; this
0x18001227c  lea     r9, [rsp+120h+var_D8]; int *
0x180012281  mov     r8d, 1; int
0x180012287  mov     [rbp+57h+var_C0], rdi
0x18001228b  lea     rdx, [rbp+57h+var_C0]; struct IMediaSample **
0x18001228f  mov     dword ptr [rsp+120h+var_D8], r13d
0x180012294  call    ?ReceiveMultiple@CMMCSSOutputQueue@@QEAAJPEAPEAUIMediaSample@@JPEAJ@Z; CMMCSSOutputQueue::ReceiveMultiple(IMediaSample * *,long,long *)
0x180012299  mov     esi, eax
0x18001229b  test    eax, eax
0x18001229d  jnz     loc_18001271E
0x1800122a3  mov     esi, r13d
0x1800122a6  mov     rcx, [r14+40h]; lpCriticalSection
0x1800122aa  call    cs:__imp_LeaveCriticalSection
0x1800122b1  nop     dword ptr [rax+rax+00h]
0x1800122b6  mov     rax, [rdi]
0x1800122b9  mov     rcx, rdi
0x1800122bc  mov     rax, [rax+10h]
0x1800122c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122c5  mov     rcx, [r15+30h]; lpCriticalSection
0x1800122c9  call    cs:__imp_EnterCriticalSection
0x1800122d0  nop     dword ptr [rax+rax+00h]
0x1800122d5  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800122dc  test    rbx, rbx
0x1800122df  jz      loc_1800127A7
0x1800122e5  cmp     byte ptr [rbx+8], 0
0x1800122e9  jz      short loc_180012324
0x1800122eb  mov     rcx, rbx; this
0x1800122ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800122f3  mov     ecx, [rax+7C4h]
0x1800122f9  cmp     ecx, [rax+7C8h]
0x1800122ff  jnb     short loc_180012317
0x180012301  add     rcx, rcx
0x180012304  lea     rdx, aCmediasampleco_0; "CMediaSampleCopyBuffer::SendSample"
0x18001230b  mov     [rax+rcx*8], rdx
0x18001230f  mov     dword ptr [rax+rcx*8+8], 1CAh
0x180012317  inc     dword ptr [rax+7C4h]
0x18001231d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012324  cmp     cs:byte_1800EACCB, 4
0x18001232b  jnb     loc_1800127B8
0x180012331  cmp     byte ptr [rbx+8], 0
0x180012335  mov     r15, [rsp+120h+var_30]
0x18001233d  jz      loc_1800123D8
0x180012343  lea     rdi, [rbx+0D0h]
0x18001234a  call    cs:__imp_GetLastError
0x180012351  nop     dword ptr [rax+rax+00h]
0x180012356  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180012359  mov     r14d, eax
0x18001235c  call    cs:__imp_TlsGetValue
0x180012363  nop     dword ptr [rax+rax+00h]
0x180012368  test    rax, rax
0x18001236b  jz      loc_180012564
0x180012371  mov     rdi, rax
0x180012374  mov     ecx, r14d; dwErrCode
0x180012377  call    cs:__imp_SetLastError
0x18001237e  nop     dword ptr [rax+rax+00h]
0x180012383  mov     eax, [rdi+7C4h]
0x180012389  test    eax, eax
0x18001238b  jz      short loc_1800123D8
0x18001238d  sub     eax, 1
0x180012390  mov     [rdi+7C4h], eax
0x180012396  jnz     short loc_1800123D8
0x180012398  mov     [rdi+7C4h], r13d
0x18001239f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800123a6  mov     qword ptr [rdi+7E0h], 0
0x1800123b1  mov     [rdi+7CCh], r13d
0x1800123b8  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800123bf  mov     [rdi+7E8h], r13d
0x1800123c6  call    cs:__imp_GetCurrentThreadId
0x1800123cd  nop     dword ptr [rax+rax+00h]
0x1800123d2  mov     [rdi+7C0h], eax
0x1800123d8  mov     eax, esi
0x1800123da  mov     rcx, [rbp+57h+var_40]
0x1800123de  xor     rcx, rsp; StackCookie
0x1800123e1  call    __security_check_cookie
0x1800123e6  add     rsp, 0F8h
0x1800123ed  pop     r14
0x1800123ef  pop     r13
0x1800123f1  pop     rdi
0x1800123f2  pop     rsi
0x1800123f3  pop     rbx
0x1800123f4  pop     rbp
0x1800123f5  retn
0x1800123f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800123fe  test    rcx, rcx
0x180012401  jz      loc_180012603
0x180012407  cmp     [rcx+8], bl
0x18001240a  jz      short loc_18001243B
0x18001240c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012411  mov     ecx, [rax+7C4h]
0x180012417  cmp     ecx, [rax+7C8h]
0x18001241d  jnb     short loc_180012435
0x18001241f  add     rcx, rcx
0x180012422  lea     rdx, aCmpeg2demuxout_3; "CMPEG2DemuxOutputPin::GetDemuxSampleAtt"...
0x180012429  mov     [rax+rcx*8], rdx
0x18001242d  mov     dword ptr [rax+rcx*8+8], 2CBh
0x180012435  inc     dword ptr [rax+7C4h]
0x18001243b  cmp     cs:byte_1800EACCB, 1
0x180012442  jnb     loc_180012614
0x180012448  lea     rcx, [rsp+120h+var_E0]; this
0x18001244d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
  ... truncated ...
```
