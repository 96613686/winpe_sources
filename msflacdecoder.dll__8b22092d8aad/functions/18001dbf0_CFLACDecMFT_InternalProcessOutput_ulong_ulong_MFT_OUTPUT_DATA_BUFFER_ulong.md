# CFLACDecMFT::InternalProcessOutput(ulong,ulong,_MFT_OUTPUT_DATA_BUFFER *,ulong *)

- ea: `0x18001dbf0`
- end: `0x18001e1a9`
- name: `?InternalProcessOutput@CFLACDecMFT@@EEAAJKKPEAU_MFT_OUTPUT_DATA_BUFFER@@PEAK@Z`
- size: `1465`
- prototype: `__int64 __fastcall(CFLACDecMFT *this, int, __int64, struct _MFT_OUTPUT_DATA_BUFFER *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001e80`
- `0x180016e48`
- `0x18001c638`
- `0x18001dbf0`
- `0x18001e834`
- `0x18001ec88`
- `0x18001efc4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001dcda`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001dcda`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001dffd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001dffd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e030`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e030`

## string_xrefs

- `0x18001dcff`: `Neither of the events are set - eSTATE_FLUSH_ALL_SAMPLES, eSTATE_DECODER_DRAIN_COMPLETE, eSTATE_INPUT_SAMPLE_EMPTY, eSTATE_OUTPUT_SAMPLE_AVAILABLE`
- `0x18001de69`: `MF_E_BUFFERTOOSMALL - Current frame size is greater than the current output buffer size and will reasult in a Read Access Violation`

## pseudocode

```c
__int64 __fastcall CFLACDecMFT::InternalProcessOutput(
        CFLACDecMFT *this,
        int a2,
        __int64 a3,
        struct _MFT_OUTPUT_DATA_BUFFER *a4)
{
  IMFSample *pSample; // r12
  int v6; // edx
  __int64 v7; // rcx
  void *v8; // rcx
  void *v9; // rax
  DWORD v10; // eax
  DWORD v11; // esi
  unsigned int v12; // ebx
  TraceLoggingHelperBase *v14; // rbx
  int v15; // esi
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  __int64 v20; // [rsp+50h] [rbp-11h] BYREF
  rsize_t DestinationSize; // [rsp+58h] [rbp-9h] BYREF
  int v22; // [rsp+60h] [rbp-1h]
  void *Destination; // [rsp+68h] [rbp+7h] BYREF
  IMFSample *v24; // [rsp+70h] [rbp+Fh] BYREF
  HANDLE Handles[3]; // [rsp+78h] [rbp+17h] BYREF

  v22 = a2;
  pSample = a4->pSample;
  v24 = pSample;
  if ( pSample )
    ((void (__fastcall *)(IMFSample *))pSample->lpVtbl->AddRef)(pSample);
  v20 = 0;
  Destination = 0;
  DestinationSize = 0;
  if ( (*((_DWORD *)this + 60) & 0xFFFFFFFD) == 0 )
  {
    TraceLoggingHelperBase::TraceVA(
      (CFLACDecMFT *)((char *)this + 960),
      2u,
      "CFLACDecMFT::InternalProcessOutput",
      0x354u,
      "MF_E_TRANSFORM_NEED_MORE_INPUT - core decoder not started");
    ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v20);
    ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v24);
    return 3222105458LL;
  }
  if ( !pSample )
  {
    TraceLoggingHelperBase::TraceVA(
      (CFLACDecMFT *)((char *)this + 960),
      2u,
      "CFLACDecMFT::InternalProcessOutput",
      0x35Au,
      "E_INVALIDARG - sample pointer is NULL");
    v7 = 2147942487LL;
LABEL_13:
    v12 = MF::OriginateError((MF *)v7, v6);
    ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v20);
    ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v24);
    return v12;
  }
  v8 = (void *)*((_QWORD *)this + 116);
  Handles[0] = *((HANDLE *)this + 119);
  Handles[1] = v8;
  if ( *((_DWORD *)this + 56) )
    v9 = (void *)*((_QWORD *)this + 118);
  else
    v9 = (void *)*((_QWORD *)this + 113);
  Handles[2] = v9;
  v10 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xFFFFFFFF, 0);
  v11 = v10;
  if ( !v10 )
    goto LABEL_36;
  if ( v10 != 1 )
  {
    if ( v10 != 2 )
    {
      TraceLoggingHelperBase::TraceVA(
        (CFLACDecMFT *)((char *)this + 960),
        2u,
        "CFLACDecMFT::InternalProcessOutput",
        0x375u,
        "Neither of the events are set - eSTATE_FLUSH_ALL_SAMPLES, eSTATE_DECODER_DRAIN_COMPLETE, eSTATE_INPUT_SAMPLE_EMP"
        "TY, eSTATE_OUTPUT_SAMPLE_AVAILABLE");
      v7 = 3222091451LL;
      goto LABEL_13;
    }
LABEL_36:
    v14 = (CFLACDecMFT *)((char *)this + 960);
    TraceLoggingHelperBase::TraceVA(
      (CFLACDecMFT *)((char *)this + 960),
      5u,
      "CFLACDecMFT::InternalProcessOutput",
      0x37Eu,
      "MF_E_TRANSFORM_NEED_MORE_INPUT - received event 0x%x",
      v10);
    if ( !v11 || v11 == 2 && *((_DWORD *)this + 56) )
    {
      if ( *((_QWORD *)this + 29) )
        CFLACDecMFT::Reset(this);
      if ( v11 == 2 && *((_DWORD *)this + 56) )
        *((_DWORD *)this + 56) = 0;
    }
    v15 = -1072861838;
    goto LABEL_45;
  }
  v14 = (CFLACDecMFT *)((char *)this + 960);
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecMFT *)((char *)this + 960),
    5u,
    "CFLACDecMFT::InternalProcessOutput",
    0x395u,
    "eSTATE_OUTPUT_SAMPLE_AVAILABLE received");
  if ( *((_QWORD *)this + 35) )
  {
    if ( !*((_DWORD *)this + 62) )
    {
      TraceLoggingHelperBase::TraceVA(
        (CFLACDecMFT *)((char *)this + 960),
        2u,
        "CFLACDecMFT::InternalProcessOutput",
        0x39Du,
        "MF_E_UNEXPECTED - current frame size is 0");
      v15 = MF::OriginateError((MF *)0xC00D36BBLL, v16);
      if ( v15 < 0 )
        goto LABEL_45;
    }
    v15 = ((__int64 (__fastcall *)(IMFSample *, __int64 *))pSample->lpVtbl->ConvertToContiguousBuffer)(pSample, &v20);
    if ( v15 < 0 )
      goto LABEL_45;
    if ( v20 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, rsize_t *))(*(_QWORD *)v20 + 56LL))(v20, &DestinationSize);
      if ( v15 < 0 )
        goto LABEL_45;
      if ( (unsigned int)DestinationSize < *((_DWORD *)this + 23) )
      {
        TraceLoggingHelperBase::TraceVA(
          (CFLACDecMFT *)((char *)this + 960),
          2u,
          "CFLACDecMFT::InternalProcessOutput",
          0x3AAu,
          "MF_E_BUFFERTOOSMALL - Max output buffer size is less than current sample buffer size");
        v15 = MF::OriginateError((MF *)0xC00D36B1LL, v17);
        if ( v15 < 0 )
          goto LABEL_45;
      }
      if ( *((_DWORD *)this + 62) > *((_DWORD *)this + 23) )
      {
        TraceLoggingHelperBase::TraceVA(
          (CFLACDecMFT *)((char *)this + 960),
          2u,
          "CFLACDecMFT::InternalProcessOutput",
          0x3B0u,
          "MF_E_BUFFERTOOSMALL - Current frame size is greater than the current output buffer size and will reasult in a "
          "Read Access Violation");
        v15 = MF::OriginateError((MF *)0xC00D36B1LL, v18);
        if ( v15 < 0 )
          goto LABEL_45;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, char *))(*(_QWORD *)v20 + 24LL))(
              v20,
              &Destination,
              0,
              (char *)&DestinationSize + 4);
      if ( v15 < 0 )
        goto LABEL_45;
      if ( memcpy_s(
             Destination,
             (unsigned int)DestinationSize,
             *((const void *const *)this + 35),
             *((unsigned int *)this + 62)) )
      {
        TraceLoggingHelperBase::TraceVA(
          (CFLACDecMFT *)((char *)this + 960),
          2u,
          "CFLACDecMFT::InternalProcessOutput",
          0x3B8u,
          "E_FAIL - failed in memcpy of buffers");
        v15 = MF::OriginateError((MF *)0x80004005LL, v19);
        if ( v15 < 0 )
          goto LABEL_45;
      }
      v15 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))pSample->lpVtbl->SetSampleTime)(
              pSample,
              *((_QWORD *)this + 33));
      if ( v15 < 0 )
        goto LABEL_45;
      v15 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))pSample->lpVtbl->SetSampleDuration)(
              pSample,
              *((_QWORD *)this + 32));
      if ( v15 < 0 )
        goto LABEL_45;
      *((_QWORD *)this + 33) += *((_QWORD *)this + 32);
      if ( *((_DWORD *)this + 77) )
      {
        v15 = ((__int64 (__fastcall *)(IMFSample *, const GUID *))pSample->lpVtbl->SetUINT32)(
                pSample,
                &MFSampleExtension_Discontinuity);
        if ( v15 < 0 )
          goto LABEL_45;
        *((_DWORD *)this + 77) = 0;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 48LL))(v20, *((unsigned int *)this + 62));
      if ( v15 >= 0 )
      {
        TraceLoggingHelperBase::TraceVA(
          (CFLACDecMFT *)((char *)this + 960),
          5u,
          "CFLACDecMFT::InternalProcessOutput",
          0x3C9u,
          "ResetEvent(m_hProcessSampleEvents[eSTATE_INPUT_SAMPLE_EMPTY])");
        ResetEvent(*((HANDLE *)this + 116));
        TraceLoggingHelperBase::TraceVA(
          (CFLACDecMFT *)((char *)this + 960),
          5u,
          "CFLACDecMFT::InternalProcessOutput",
          0x3CCu,
          "SetEvent(m_hProcessSampleEvents[eSTATE_OUTPUT_SAMPLE_EMPTY])");
        SetEvent(*((HANDLE *)this + 115));
        ++*((_DWORD *)this + 223);
        dword_18006F440 += *((_DWORD *)this + 62);
      }
      goto LABEL_45;
    }
    v15 = -2147467261;
  }
  else
  {
    v15 = -2147418113;
  }
LABEL_45:
  if ( Destination )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20);
  TraceLoggingHelperBase::TraceVA(
    v14,
    4u,
    "CFLACDecMFT::InternalProcessOutput",
    0x3DEu,
    "InternalProcessOutput, dwFlags=0x%X, number of samples received: %u, size of current sample: %u, timestamp: %I64d, T"
    "otal size written: %u",
    v22,
    *((_DWORD *)this + 223),
    *((_DWORD *)this + 62),
    *((_QWORD *)this + 33),
    dword_18006F440);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v20);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v24);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001dbf0  mov     [rsp-8+arg_10], rbx
0x18001dbf5  mov     [rsp-8+arg_18], rsi
0x18001dbfa  push    rbp
0x18001dbfb  push    rdi
0x18001dbfc  push    r12
0x18001dbfe  lea     rbp, [rsp-3Fh]
0x18001dc03  sub     rsp, 0A0h
0x18001dc0a  mov     rax, cs:__security_cookie
0x18001dc11  xor     rax, rsp
0x18001dc14  mov     [rbp+4Fh+var_20], rax
0x18001dc18  mov     [rbp+4Fh+var_50], edx
0x18001dc1b  mov     rdi, rcx
0x18001dc1e  mov     r12, [r9+8]
0x18001dc22  mov     [rbp+4Fh+var_40], r12
0x18001dc26  xor     ebx, ebx
0x18001dc28  test    r12, r12
0x18001dc2b  jz      short loc_18001DC3E
0x18001dc2d  mov     rax, [r12]
0x18001dc31  mov     rcx, r12
0x18001dc34  mov     rax, [rax+8]
0x18001dc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc3d  nop
0x18001dc3e  mov     [rbp+4Fh+var_60], rbx
0x18001dc42  mov     [rbp+4Fh+Destination], rbx
0x18001dc46  mov     dword ptr [rbp+4Fh+DestinationSize], ebx
0x18001dc49  mov     dword ptr [rbp+4Fh+DestinationSize+4], ebx
0x18001dc4c  test    dword ptr [rdi+0F0h], 0FFFFFFFDh
0x18001dc56  jz      loc_18001E142
0x18001dc5c  test    r12, r12
0x18001dc5f  jnz     short loc_18001DC95
0x18001dc61  lea     rcx, [rdi+3C0h]; this
0x18001dc68  lea     rax, aEInvalidargSam; "E_INVALIDARG - sample pointer is NULL"
0x18001dc6f  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001dc74  mov     r9d, 35Ah; unsigned int
0x18001dc7a  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001dc81  lea     edx, [r12+2]; unsigned __int8
0x18001dc86  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001dc8b  mov     ecx, 80070057h
0x18001dc90  jmp     loc_18001DD27
0x18001dc95  mov     rax, [rdi+3B8h]
0x18001dc9c  mov     rcx, [rdi+3A0h]
0x18001dca3  mov     [rbp+4Fh+Handles], rax
0x18001dca7  mov     [rbp+4Fh+var_30], rcx
0x18001dcab  mov     [rsp+0B0h+bAlertable], ebx; bAlertable
0x18001dcaf  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001dcb3  xor     r8d, r8d; bWaitAll
0x18001dcb6  lea     rdx, [rbp+4Fh+Handles]; lpHandles
0x18001dcba  lea     ecx, [r8+3]; nCount
0x18001dcbe  cmp     [rdi+0E0h], ebx
0x18001dcc4  jz      short loc_18001DCCF
0x18001dcc6  mov     rax, [rdi+3B0h]
0x18001dccd  jmp     short loc_18001DCD6
0x18001dccf  mov     rax, [rdi+388h]
0x18001dcd6  mov     [rbp+4Fh+var_28], rax
0x18001dcda  call    cs:__imp_WaitForMultipleObjectsEx
0x18001dce0  mov     esi, eax
0x18001dce2  test    eax, eax
0x18001dce4  jz      loc_18001E04A
0x18001dcea  cmp     eax, 1
0x18001dced  jz      short loc_18001DD48
0x18001dcef  cmp     eax, 2
0x18001dcf2  jz      loc_18001E04A
0x18001dcf8  lea     rcx, [rdi+3C0h]; this
0x18001dcff  lea     rax, aNeitherOfTheEv_0; "Neither of the events are set - eSTATE_"...
0x18001dd06  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001dd0b  mov     r9d, 375h; unsigned int
0x18001dd11  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001dd18  mov     edx, 2; unsigned __int8
0x18001dd1d  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001dd22  mov     ecx, 0C00D36BBh; this
0x18001dd27  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18001dd2c  mov     ebx, eax
0x18001dd2e  lea     rcx, [rbp+4Fh+var_60]
0x18001dd32  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001dd37  nop
0x18001dd38  lea     rcx, [rbp+4Fh+var_40]
0x18001dd3c  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001dd41  mov     eax, ebx
0x18001dd43  jmp     loc_18001E185
0x18001dd48  lea     rbx, [rdi+3C0h]
0x18001dd4f  lea     rax, aEstateOutputSa; "eSTATE_OUTPUT_SAMPLE_AVAILABLE received"
0x18001dd56  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001dd5b  mov     r9d, 395h; unsigned int
0x18001dd61  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001dd68  mov     edx, 5; unsigned __int8
0x18001dd6d  mov     rcx, rbx; this
0x18001dd70  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001dd75  cmp     qword ptr [rdi+118h], 0
0x18001dd7d  jnz     short loc_18001DD89
0x18001dd7f  mov     esi, 8000FFFFh
0x18001dd84  jmp     loc_18001E0BC
0x18001dd89  cmp     dword ptr [rdi+0F8h], 0
0x18001dd90  jnz     short loc_18001DDCC
0x18001dd92  lea     rax, aMfEUnexpectedC; "MF_E_UNEXPECTED - current frame size is"...
0x18001dd99  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001dd9e  mov     r9d, 39Dh; unsigned int
0x18001dda4  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001ddab  mov     edx, 2; unsigned __int8
0x18001ddb0  mov     rcx, rbx; this
0x18001ddb3  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001ddb8  mov     ecx, 0C00D36BBh; this
0x18001ddbd  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18001ddc2  mov     esi, eax
0x18001ddc4  test    eax, eax
0x18001ddc6  js      loc_18001E0BC
0x18001ddcc  mov     rax, [r12]
0x18001ddd0  lea     rdx, [rbp+4Fh+var_60]
0x18001ddd4  mov     rcx, r12
0x18001ddd7  mov     rax, [rax+148h]
0x18001ddde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dde3  mov     esi, eax
0x18001dde5  test    eax, eax
0x18001dde7  js      loc_18001E0BC
0x18001dded  cmp     [rbp+4Fh+var_60], 0
0x18001ddf2  jnz     short loc_18001DDFE
0x18001ddf4  mov     esi, 80004003h
0x18001ddf9  jmp     loc_18001E0BC
0x18001ddfe  mov     rcx, [rbp+4Fh+var_60]
0x18001de02  mov     rax, [rcx]
0x18001de05  lea     rdx, [rbp+4Fh+DestinationSize]
0x18001de09  mov     rax, [rax+38h]
0x18001de0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de12  mov     esi, eax
0x18001de14  test    eax, eax
0x18001de16  js      loc_18001E0BC
0x18001de1c  mov     eax, [rdi+5Ch]
0x18001de1f  cmp     dword ptr [rbp+4Fh+DestinationSize], eax
0x18001de22  jnb     short loc_18001DE5E
0x18001de24  lea     rax, aMfEBuffertoosm_1; "MF_E_BUFFERTOOSMALL - Max output buffer"...
0x18001de2b  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001de30  mov     r9d, 3AAh; unsigned int
0x18001de36  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001de3d  mov     edx, 2; unsigned __int8
0x18001de42  mov     rcx, rbx; this
0x18001de45  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001de4a  mov     ecx, 0C00D36B1h; this
0x18001de4f  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18001de54  mov     esi, eax
0x18001de56  test    eax, eax
0x18001de58  js      loc_18001E0BC
0x18001de5e  mov     eax, [rdi+5Ch]
0x18001de61  cmp     [rdi+0F8h], eax
0x18001de67  jbe     short loc_18001DEA3
0x18001de69  lea     rax, aMfEBuffertoosm; "MF_E_BUFFERTOOSMALL - Current frame siz"...
0x18001de70  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001de75  mov     r9d, 3B0h; unsigned int
0x18001de7b  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001de82  mov     edx, 2; unsigned __int8
0x18001de87  mov     rcx, rbx; this
0x18001de8a  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001de8f  mov     ecx, 0C00D36B1h; this
0x18001de94  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18001de99  mov     esi, eax
0x18001de9b  test    eax, eax
0x18001de9d  js      loc_18001E0BC
0x18001dea3  mov     rcx, [rbp+4Fh+var_60]
0x18001dea7  mov     rax, [rcx]
0x18001deaa  lea     r9, [rbp+4Fh+DestinationSize+4]
0x18001deae  xor     r8d, r8d
0x18001deb1  lea     rdx, [rbp+4Fh+Destination]
0x18001deb5  mov     rax, [rax+18h]
0x18001deb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001debe  mov     esi, eax
0x18001dec0  test    eax, eax
0x18001dec2  js      loc_18001E0BC
0x18001dec8  mov     r9d, [rdi+0F8h]; SourceSize
0x18001decf  mov     edx, dword ptr [rbp+4Fh+DestinationSize]; DestinationSize
0x18001ded2  mov     r8, [rdi+118h]; Source
0x18001ded9  mov     rcx, [rbp+4Fh+Destination]; Destination
0x18001dedd  call    memcpy_s
0x18001dee2  test    eax, eax
0x18001dee4  jz      short loc_18001DF20
0x18001dee6  lea     rax, aEFailFailedInM; "E_FAIL - failed in memcpy of buffers"
0x18001deed  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001def2  mov     r9d, 3B8h; unsigned int
0x18001def8  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001deff  mov     edx, 2; unsigned __int8
0x18001df04  mov     rcx, rbx; this
0x18001df07  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001df0c  mov     ecx, 80004005h; this
0x18001df11  call    ?OriginateError@MF@@YAJJ@Z; MF::OriginateError(long)
0x18001df16  mov     esi, eax
0x18001df18  test    eax, eax
0x18001df1a  js      loc_18001E0BC
0x18001df20  mov     rax, [r12]
0x18001df24  mov     rdx, [rdi+108h]
0x18001df2b  mov     rcx, r12
0x18001df2e  mov     rax, [rax+120h]
0x18001df35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df3a  mov     esi, eax
0x18001df3c  test    eax, eax
0x18001df3e  js      loc_18001E0BC
0x18001df44  mov     rax, [r12]
0x18001df48  mov     rdx, [rdi+100h]
0x18001df4f  mov     rcx, r12
0x18001df52  mov     rax, [rax+130h]
0x18001df59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df5e  mov     esi, eax
0x18001df60  test    eax, eax
0x18001df62  js      loc_18001E0BC
0x18001df68  mov     rax, [rdi+100h]
0x18001df6f  add     [rdi+108h], rax
0x18001df76  mov     r8d, [rdi+134h]
0x18001df7d  test    r8d, r8d
0x18001df80  jz      short loc_18001DFB0
0x18001df82  mov     rax, [r12]
0x18001df86  lea     rdx, MFSampleExtension_Discontinuity
0x18001df8d  mov     rcx, r12
0x18001df90  mov     rax, [rax+0A8h]
0x18001df97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df9c  mov     esi, eax
0x18001df9e  test    eax, eax
0x18001dfa0  js      loc_18001E0BC
0x18001dfa6  mov     dword ptr [rdi+134h], 0
0x18001dfb0  mov     rcx, [rbp+4Fh+var_60]
0x18001dfb4  mov     rax, [rcx]
0x18001dfb7  mov     edx, [rdi+0F8h]
0x18001dfbd  mov     rax, [rax+30h]
0x18001dfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfc6  mov     esi, eax
0x18001dfc8  test    eax, eax
0x18001dfca  js      loc_18001E0BC
0x18001dfd0  lea     rax, aReseteventMHpr; "ResetEvent(m_hProcessSampleEvents[eSTAT"...
0x18001dfd7  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001dfdc  mov     r9d, 3C9h; unsigned int
0x18001dfe2  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001dfe9  mov     edx, 5; unsigned __int8
0x18001dfee  mov     rcx, rbx; this
0x18001dff1  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001dff6  mov     rcx, [rdi+3A0h]; hEvent
0x18001dffd  call    cs:__imp_ResetEvent
0x18001e003  lea     rax, aSeteventMHproc_2; "SetEvent(m_hProcessSampleEvents[eSTATE_"...
0x18001e00a  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001e00f  mov     r9d, 3CCh; unsigned int
0x18001e015  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001e01c  mov     edx, 5; unsigned __int8
0x18001e021  mov     rcx, rbx; this
0x18001e024  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001e029  mov     rcx, [rdi+398h]; hEvent
0x18001e030  call    cs:__imp_SetEvent
0x18001e036  inc     dword ptr [rdi+37Ch]
0x18001e03c  mov     eax, [rdi+0F8h]
0x18001e042  add     cs:dword_18006F440, eax
0x18001e048  jmp     short loc_18001E0BC
0x18001e04a  lea     rbx, [rdi+3C0h]
0x18001e051  mov     [rsp+0B0h+var_88], esi
0x18001e055  lea     rax, aMfETransformNe_0; "MF_E_TRANSFORM_NEED_MORE_INPUT - receiv"...
0x18001e05c  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001e061  mov     r9d, 37Eh; unsigned int
0x18001e067  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001e06e  mov     edx, 5; unsigned __int8
0x18001e073  mov     rcx, rbx; this
0x18001e076  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001e07b  test    esi, esi
0x18001e07d  jz      short loc_18001E08D
0x18001e07f  cmp     esi, 2
0x18001e082  jnz     short loc_18001E0B7
0x18001e084  cmp     dword ptr [rdi+0E0h], 0
0x18001e08b  jz      short loc_18001E0B7
0x18001e08d  cmp     qword ptr [rdi+0E8h], 0
0x18001e095  jz      short loc_18001E09F
0x18001e097  mov     rcx, rdi; this
0x18001e09a  call    ?Reset@CFLACDecMFT@@AEAAJXZ; CFLACDecMFT::Reset(void)
0x18001e09f  cmp     esi, 2
0x18001e0a2  jnz     short loc_18001E0B7
0x18001e0a4  cmp     dword ptr [rdi+0E0h], 0
0x18001e0ab  jz      short loc_18001E0B7
0x18001e0ad  mov     dword ptr [rdi+0E0h], 0
0x18001e0b7  mov     esi, 0C00D6D72h
0x18001e0bc  cmp     [rbp+4Fh+Destination], 0
0x18001e0c1  jz      short loc_18001E0D3
0x18001e0c3  mov     rcx, [rbp+4Fh+var_60]
0x18001e0c7  mov     rax, [rcx]
0x18001e0ca  mov     rax, [rax+20h]
0x18001e0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0d3  mov     eax, cs:dword_18006F440
0x18001e0d9  mov     [rsp+0B0h+var_68], eax
0x18001e0dd  mov     rax, [rdi+108h]
0x18001e0e4  mov     [rsp+0B0h+var_70], rax
0x18001e0e9  mov     eax, [rdi+0F8h]
0x18001e0ef  mov     [rsp+0B0h+var_78], eax
0x18001e0f3  mov     eax, [rdi+37Ch]
0x18001e0f9  mov     [rsp+0B0h+var_80], eax
0x18001e0fd  mov     eax, [rbp+4Fh+var_50]
0x18001e100  mov     [rsp+0B0h+var_88], eax
0x18001e104  lea     rax, aInternalproces; "InternalProcessOutput, dwFlags=0x%X, nu"...
0x18001e10b  mov     qword ptr [rsp+0B0h+bAlertable], rax; Format
0x18001e110  mov     r9d, 3DEh; unsigned int
0x18001e116  lea     r8, aCflacdecmftInt_0; "CFLACDecMFT::InternalProcessOutput"
0x18001e11d  mov     edx, 4; unsigned __int8
0x18001e122  mov     rcx, rbx; this
0x18001e125  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001e12a  nop
0x18001e12b  lea     rcx, [rbp+4Fh+var_60]
0x18001e12f  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001e134  nop
0x18001e135  lea     rcx, [rbp+4Fh+var_40]
0x18001e139  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001e13e  mov     eax, esi
0x18001e140  jmp     short loc_18001E185
  ... truncated ...
```
