# CFLACDecMFT::ReadInputSample(uchar *,ulong *)

- ea: `0x18001e860`
- end: `0x18001ec0d`
- name: `?ReadInputSample@CFLACDecMFT@@MEAAJPEAEPEAK@Z`
- size: `941`
- prototype: `__int64 __fastcall(CFLACDecMFT *__hidden this, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001e80`
- `0x180016e48`
- `0x18001c638`
- `0x18001e860`
- `0x18001efc4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e904`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001e904`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001eb35`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001eb35`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001eb68`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001eb68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e98b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ebb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e98b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ebb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e957`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e957`

## string_xrefs

- `0x18001e897`: `ReadInputSample`
- `0x18001e8a9`: `CFLACDecMFT::ReadInputSample`
- `0x18001ea12`: `CFLACDecMFT::ReadInputSample`
- `0x18001ea59`: `CFLACDecMFT::ReadInputSample`
- `0x18001ea9b`: `CFLACDecMFT::ReadInputSample`
- `0x18001eb1a`: `CFLACDecMFT::ReadInputSample`
- `0x18001eb4d`: `CFLACDecMFT::ReadInputSample`
- `0x18001eb97`: `CFLACDecMFT::ReadInputSample`
- `0x18001ea47`: `Input Sample count and read sample size: %u %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACDecMFT::ReadInputSample(CFLACDecMFT *this, unsigned __int8 *a2, unsigned int *a3)
{
  TraceLoggingHelperBase *v5; // r14
  DWORD v6; // eax
  __int64 v8; // rcx
  int v9; // edi
  unsigned int v10; // eax
  unsigned int v11; // r12d
  __int64 v12; // rcx
  int v13; // [rsp+40h] [rbp-29h] BYREF
  __int64 v14; // [rsp+48h] [rbp-21h] BYREF
  __int64 v15; // [rsp+50h] [rbp-19h] BYREF
  void *Destination; // [rsp+58h] [rbp-11h]
  char *v17; // [rsp+60h] [rbp-9h]
  HANDLE Handles[4]; // [rsp+68h] [rbp-1h] BYREF

  Destination = a2;
  v5 = (CFLACDecMFT *)((char *)this + 808);
  TraceLoggingHelperBase::TraceVA(
    (CFLACDecMFT *)((char *)this + 808),
    5u,
    "CFLACDecMFT::ReadInputSample",
    0x482u,
    "ReadInputSample");
  Handles[0] = *((HANDLE *)this + 100);
  Handles[1] = *((HANDLE *)this + 95);
  Handles[2] = *((HANDLE *)this + 98);
  Handles[3] = *((HANDLE *)this + 99);
  v6 = WaitForMultipleObjectsEx(4u, Handles, 0, 0xFFFFFFFF, 0);
  if ( !v6 )
  {
LABEL_25:
    TraceLoggingHelperBase::TraceVA(v5, 2u, "CFLACDecMFT::ReadInputSample", 0x499u, "0x%x reached end of stream", v6);
    return 1;
  }
  if ( v6 != 1 )
  {
    if ( v6 != 2 )
    {
      TraceLoggingHelperBase::TraceVA(
        v5,
        2u,
        "CFLACDecMFT::ReadInputSample",
        0x493u,
        "Neither of the events are set - eSTATE_FLUSH_ALL_SAMPLES, eSTATE_INPUT_SAMPLE_AVAILABLE, eSTATE_DECODER_DRAIN_START");
      return 3222091451LL;
    }
    goto LABEL_25;
  }
  v17 = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v8 = *((_QWORD *)this - 10);
  if ( v8 )
  {
    v14 = 0;
    v15 = 0;
    v13 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 328LL))(v8, &v14);
    if ( v9 >= 0 )
    {
      if ( v14 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, int *))(*(_QWORD *)v14 + 24LL))(v14, &v15, 0, &v13);
        if ( v9 >= 0 )
        {
          TraceLoggingHelperBase::TraceVA(v5, 5u, "CFLACDecMFT::ReadInputSample", 0x4B0u, "Input sample size %u", v13);
          v10 = *a3;
          if ( v13 - *((_DWORD *)this + 23) <= *a3 )
            v10 = v13 - *((_DWORD *)this + 23);
          v11 = v10;
          TraceLoggingHelperBase::TraceVA(
            v5,
            5u,
            "CFLACDecMFT::ReadInputSample",
            0x4B8u,
            "Input Sample count and read sample size: %u %u",
            *((_DWORD *)this + 184),
            v10);
          if ( memcpy_s(Destination, *a3, (const void *const)(v15 + *((unsigned int *)this + 23)), v11) )
          {
            TraceLoggingHelperBase::TraceVA(
              v5,
              2u,
              "CFLACDecMFT::ReadInputSample",
              0x4BCu,
              "E_FAIL - failed in memcpy of buffers");
            v9 = -2147467259;
          }
          else
          {
            *((_DWORD *)this + 23) += v11;
            *a3 = v11;
          }
        }
      }
      else
      {
        v9 = -2147467261;
      }
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
    if ( v9 )
    {
      TraceLoggingHelperBase::TraceVA(
        v5,
        2u,
        "CFLACDecMFT::ReadInputSample",
        0x4D5u,
        "Error %08X returned: File: %s, Line: %d",
        v9,
        "avcore\\codecdsp\\audio\\flac\\flacdec\\mft\\flacdecmft.cpp",
        1237);
    }
    else if ( *((_DWORD *)this + 23) == v13 )
    {
      v12 = *((_QWORD *)this - 10);
      if ( v12 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        *((_QWORD *)this - 10) = 0;
      }
      *((_DWORD *)this + 23) = 0;
      TraceLoggingHelperBase::TraceVA(
        v5,
        5u,
        "CFLACDecMFT::ReadInputSample",
        0x4CFu,
        "ResetEvent(m_hProcessSampleEvents[eSTATE_INPUT_SAMPLE_AVAILABLE])");
      ResetEvent(*((HANDLE *)this + 95));
      TraceLoggingHelperBase::TraceVA(
        v5,
        5u,
        "CFLACDecMFT::ReadInputSample",
        0x4D2u,
        "SetEvent(m_hProcessSampleEvents[eSTATE_INPUT_SAMPLE_EMPTY])");
      SetEvent(*((HANDLE *)this + 94));
    }
    ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v14);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    return (unsigned int)v9;
  }
  else
  {
    TraceLoggingHelperBase::TraceVA(
      v5,
      2u,
      "CFLACDecMFT::ReadInputSample",
      0x4A1u,
      "MF_E_INVALIDREQUEST - input sample is NULL");
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    return 3222091442LL;
  }
}

```

## disassembly

```asm
0x18001e860  push    rbp
0x18001e862  push    rbx
0x18001e863  push    rdi
0x18001e864  push    r12
0x18001e866  push    r13
0x18001e868  push    r14
0x18001e86a  push    r15
0x18001e86c  lea     rbp, [rsp-27h]
0x18001e871  sub     rsp, 90h
0x18001e878  mov     rax, cs:__security_cookie
0x18001e87f  xor     rax, rsp
0x18001e882  mov     [rbp+57h+var_38], rax
0x18001e886  mov     r13, r8
0x18001e889  mov     [rbp+57h+Destination], rdx
0x18001e88d  mov     rbx, rcx
0x18001e890  lea     r14, [rcx+328h]
0x18001e897  lea     rax, aReadinputsampl; "ReadInputSample"
0x18001e89e  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001e8a3  mov     r9d, 482h; unsigned int
0x18001e8a9  lea     rdi, aCflacdecmftRea; "CFLACDecMFT::ReadInputSample"
0x18001e8b0  mov     r8, rdi; char *
0x18001e8b3  mov     edx, 5; unsigned __int8
0x18001e8b8  mov     rcx, r14; this
0x18001e8bb  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001e8c0  mov     rax, [rbx+320h]
0x18001e8c7  mov     [rbp+57h+Handles], rax
0x18001e8cb  mov     rax, [rbx+2F8h]
0x18001e8d2  mov     [rbp+57h+var_50], rax
0x18001e8d6  mov     rax, [rbx+310h]
0x18001e8dd  mov     [rbp+57h+var_48], rax
0x18001e8e1  mov     rax, [rbx+318h]
0x18001e8e8  mov     [rbp+57h+var_40], rax
0x18001e8ec  xor     r12d, r12d
0x18001e8ef  mov     [rsp+0C0h+bAlertable], r12d; bAlertable
0x18001e8f4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001e8f8  xor     r8d, r8d; bWaitAll
0x18001e8fb  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18001e8ff  lea     ecx, [r12+4]; nCount
0x18001e904  call    cs:__imp_WaitForMultipleObjectsEx
0x18001e90a  test    eax, eax
0x18001e90c  jz      loc_18001EBC3
0x18001e912  cmp     eax, 1
0x18001e915  jz      short loc_18001E94C
0x18001e917  cmp     eax, 2
0x18001e91a  jz      loc_18001EBC3
0x18001e920  lea     rax, aNeitherOfTheEv; "Neither of the events are set - eSTATE_"...
0x18001e927  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001e92c  mov     r9d, 493h; unsigned int
0x18001e932  mov     r8, rdi; char *
0x18001e935  lea     edx, [r12+2]; unsigned __int8
0x18001e93a  mov     rcx, r14; this
0x18001e93d  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001e942  mov     eax, 0C00D36BBh
0x18001e947  jmp     loc_18001EBEE
0x18001e94c  lea     r15, [rbx+20h]
0x18001e950  mov     [rbp+57h+var_60], r15
0x18001e954  mov     rcx, r15; lpCriticalSection
0x18001e957  call    cs:__imp_EnterCriticalSection
0x18001e95d  nop
0x18001e95e  mov     rcx, [rbx-50h]
0x18001e962  test    rcx, rcx
0x18001e965  jnz     short loc_18001E99B
0x18001e967  lea     rax, aMfEInvalidrequ; "MF_E_INVALIDREQUEST - input sample is N"...
0x18001e96e  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001e973  mov     r9d, 4A1h; unsigned int
0x18001e979  mov     r8, rdi; char *
0x18001e97c  lea     edx, [rcx+2]; unsigned __int8
0x18001e97f  mov     rcx, r14; this
0x18001e982  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001e987  nop
0x18001e988  mov     rcx, r15; lpCriticalSection
0x18001e98b  call    cs:__imp_LeaveCriticalSection
0x18001e991  mov     eax, 0C00D36B2h
0x18001e996  jmp     loc_18001EBEE
0x18001e99b  mov     [rbp+57h+var_78], r12
0x18001e99f  mov     [rbp+57h+var_70], r12
0x18001e9a3  mov     [rbp+57h+var_80], r12d
0x18001e9a7  mov     rax, [rcx]
0x18001e9aa  lea     rdx, [rbp+57h+var_78]
0x18001e9ae  mov     rax, [rax+148h]
0x18001e9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9ba  mov     edi, eax
0x18001e9bc  test    eax, eax
0x18001e9be  js      loc_18001EAC1
0x18001e9c4  cmp     [rbp+57h+var_78], r12
0x18001e9c8  jnz     short loc_18001E9D4
0x18001e9ca  mov     edi, 80004003h
0x18001e9cf  jmp     loc_18001EAC1
0x18001e9d4  mov     rcx, [rbp+57h+var_78]
0x18001e9d8  mov     rax, [rcx]
0x18001e9db  lea     r9, [rbp+57h+var_80]
0x18001e9df  xor     r8d, r8d
0x18001e9e2  lea     rdx, [rbp+57h+var_70]
0x18001e9e6  mov     rax, [rax+18h]
0x18001e9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9ef  mov     edi, eax
0x18001e9f1  test    eax, eax
0x18001e9f3  js      loc_18001EAC1
0x18001e9f9  mov     eax, [rbp+57h+var_80]
0x18001e9fc  mov     [rsp+0C0h+var_98], eax
0x18001ea00  lea     rax, aInputSampleSiz; "Input sample size %u"
0x18001ea07  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001ea0c  mov     r9d, 4B0h; unsigned int
0x18001ea12  lea     r8, aCflacdecmftRea; "CFLACDecMFT::ReadInputSample"
0x18001ea19  mov     edx, 5; unsigned __int8
0x18001ea1e  mov     rcx, r14; this
0x18001ea21  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001ea26  mov     ecx, [rbp+57h+var_80]
0x18001ea29  sub     ecx, [rbx+5Ch]
0x18001ea2c  mov     eax, [r13+0]
0x18001ea30  cmp     ecx, eax
0x18001ea32  cmovbe  eax, ecx
0x18001ea35  mov     r12d, eax
0x18001ea38  mov     dword ptr [rsp+0C0h+var_90], r12d
0x18001ea3d  mov     eax, [rbx+2E0h]
0x18001ea43  mov     [rsp+0C0h+var_98], eax
0x18001ea47  lea     rax, aInputSampleCou; "Input Sample count and read sample size"...
0x18001ea4e  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001ea53  mov     r9d, 4B8h; unsigned int
0x18001ea59  lea     r8, aCflacdecmftRea; "CFLACDecMFT::ReadInputSample"
0x18001ea60  mov     edx, 5; unsigned __int8
0x18001ea65  mov     rcx, r14; this
0x18001ea68  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001ea6d  mov     r9d, r12d; SourceSize
0x18001ea70  mov     r8d, [rbx+5Ch]
0x18001ea74  add     r8, [rbp+57h+var_70]; Source
0x18001ea78  mov     edx, [r13+0]; DestinationSize
0x18001ea7c  mov     rcx, [rbp+57h+Destination]; Destination
0x18001ea80  call    memcpy_s
0x18001ea85  test    eax, eax
0x18001ea87  jz      short loc_18001EAB6
0x18001ea89  lea     rax, aEFailFailedInM; "E_FAIL - failed in memcpy of buffers"
0x18001ea90  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001ea95  mov     r9d, 4BCh; unsigned int
0x18001ea9b  lea     r8, aCflacdecmftRea; "CFLACDecMFT::ReadInputSample"
0x18001eaa2  mov     edx, 2; unsigned __int8
0x18001eaa7  mov     rcx, r14; this
0x18001eaaa  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001eaaf  mov     edi, 80004005h
0x18001eab4  jmp     short loc_18001EABE
0x18001eab6  add     [rbx+5Ch], r12d
0x18001eaba  mov     [r13+0], r12d
0x18001eabe  xor     r12d, r12d
0x18001eac1  cmp     [rbp+57h+var_70], r12
0x18001eac5  jz      short loc_18001EAD7
0x18001eac7  mov     rcx, [rbp+57h+var_78]
0x18001eacb  mov     rax, [rcx]
0x18001eace  mov     rax, [rax+20h]
0x18001ead2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ead7  test    edi, edi
0x18001ead9  jnz     loc_18001EB70
0x18001eadf  mov     eax, [rbp+57h+var_80]
0x18001eae2  cmp     [rbx+5Ch], eax
0x18001eae5  jnz     loc_18001EBAC
0x18001eaeb  mov     rcx, [rbx-50h]
0x18001eaef  test    rcx, rcx
0x18001eaf2  jz      short loc_18001EB04
0x18001eaf4  mov     rax, [rcx]
0x18001eaf7  mov     rax, [rax+10h]
0x18001eafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb00  mov     [rbx-50h], r12
0x18001eb04  mov     [rbx+5Ch], r12d
0x18001eb08  lea     rax, aReseteventMHpr_0; "ResetEvent(m_hProcessSampleEvents[eSTAT"...
0x18001eb0f  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001eb14  mov     r9d, 4CFh; unsigned int
0x18001eb1a  lea     r8, aCflacdecmftRea; "CFLACDecMFT::ReadInputSample"
0x18001eb21  mov     edx, 5; unsigned __int8
0x18001eb26  mov     rcx, r14; this
0x18001eb29  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001eb2e  mov     rcx, [rbx+2F8h]; hEvent
0x18001eb35  call    cs:__imp_ResetEvent
0x18001eb3b  lea     rax, aSeteventMHproc_0; "SetEvent(m_hProcessSampleEvents[eSTATE_"...
0x18001eb42  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001eb47  mov     r9d, 4D2h; unsigned int
0x18001eb4d  lea     r8, aCflacdecmftRea; "CFLACDecMFT::ReadInputSample"
0x18001eb54  mov     edx, 5; unsigned __int8
0x18001eb59  mov     rcx, r14; this
0x18001eb5c  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001eb61  mov     rcx, [rbx+2F0h]; hEvent
0x18001eb68  call    cs:__imp_SetEvent
0x18001eb6e  jmp     short loc_18001EBAC
0x18001eb70  mov     r9d, 4D5h; unsigned int
0x18001eb76  mov     [rsp+0C0h+var_88], r9d
0x18001eb7b  lea     rax, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\flac\\flacdec"...
0x18001eb82  mov     [rsp+0C0h+var_90], rax
0x18001eb87  mov     [rsp+0C0h+var_98], edi
0x18001eb8b  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18001eb92  mov     qword ptr [rsp+0C0h+bAlertable], rax; Format
0x18001eb97  lea     r8, aCflacdecmftRea; "CFLACDecMFT::ReadInputSample"
0x18001eb9e  mov     edx, 2; unsigned __int8
0x18001eba3  mov     rcx, r14; this
0x18001eba6  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001ebab  nop
0x18001ebac  lea     rcx, [rbp+57h+var_78]
0x18001ebb0  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18001ebb5  nop
0x18001ebb6  mov     rcx, r15; lpCriticalSection
0x18001ebb9  call    cs:__imp_LeaveCriticalSection
0x18001ebbf  mov     eax, edi
0x18001ebc1  jmp     short loc_18001EBEE
0x18001ebc3  mov     [rsp+0C0h+var_98], eax
0x18001ebc7  lea     rcx, a0xXReachedEndO; "0x%x reached end of stream"
0x18001ebce  mov     qword ptr [rsp+0C0h+bAlertable], rcx; Format
0x18001ebd3  mov     r9d, 499h; unsigned int
0x18001ebd9  mov     r8, rdi; char *
0x18001ebdc  mov     edx, 2; unsigned __int8
0x18001ebe1  mov     rcx, r14; this
0x18001ebe4  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18001ebe9  mov     eax, 1
0x18001ebee  mov     rcx, [rbp+57h+var_38]
0x18001ebf2  xor     rcx, rsp; StackCookie
0x18001ebf5  call    __security_check_cookie
0x18001ebfa  add     rsp, 90h
0x18001ec01  pop     r15
0x18001ec03  pop     r14
0x18001ec05  pop     r13
0x18001ec07  pop     r12
0x18001ec09  pop     rdi
0x18001ec0a  pop     rbx
0x18001ec0b  pop     rbp
0x18001ec0c  retn
```
