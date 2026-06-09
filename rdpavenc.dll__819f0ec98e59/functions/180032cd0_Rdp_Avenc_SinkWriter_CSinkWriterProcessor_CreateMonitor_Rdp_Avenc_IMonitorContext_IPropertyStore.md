# Rdp::Avenc::SinkWriter::CSinkWriterProcessor::CreateMonitor(Rdp::Avenc::IMonitorContext * *,IPropertyStore *)

- ea: `0x180032cd0`
- end: `0x180033188`
- name: `?CreateMonitor@CSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UEAAJPEAPEAUIMonitorContext@34@PEAUIPropertyStore@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *__hidden this, struct Rdp::Avenc::IMonitorContext **, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018c4`
- `0x1800065a4`
- `0x18000ec04`
- `0x1800146bc`
- `0x180014e7c`
- `0x1800150ac`
- `0x1800153f8`
- `0x180015480`
- `0x1800223f8`
- `0x180032cd0`
- `0x180082e84`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800330bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800330bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032f44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032f44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033114`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033114`

## string_xrefs

- `0x180032e07`: `Create monitor context`
- `0x180032eae`: `MonitorCreate`
- `0x180032d74`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x180032ea0`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x180032ea7`: `Rdp::Avenc::SinkWriter::CSinkWriterProcessor::CreateMonitor`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterProcessor::CreateMonitor(
        Rdp::Avenc::SinkWriter::CSinkWriterProcessor *this,
        struct Rdp::Avenc::IMonitorContext **a2,
        struct IPropertyStore *a3)
{
  char v5; // si
  bool v6; // bl
  bool v7; // r15
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  char *v13; // rbx
  char *v14; // r13
  const void *v15; // rax
  int v16; // r12d
  const char *v17; // r15
  const char *v18; // r14
  __int64 v19; // r14
  _OWORD *v20; // r14
  const char *v21; // rax
  const char *v22; // r9
  bool v23; // bl
  char v24; // al
  int v25; // r8d
  int v26; // edx
  __int64 result; // rax
  int v28; // [rsp+20h] [rbp-A8h]
  int v29; // [rsp+20h] [rbp-A8h]
  int v30; // [rsp+28h] [rbp-A0h]
  int v31; // [rsp+28h] [rbp-A0h]
  char *v32; // [rsp+30h] [rbp-98h]
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-78h] BYREF
  char v34; // [rsp+58h] [rbp-70h]
  int *v35; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int64 v36; // [rsp+68h] [rbp-60h] BYREF
  int v37[4]; // [rsp+70h] [rbp-58h] BYREF
  const char *v38; // [rsp+80h] [rbp-48h] BYREF
  int v39; // [rsp+88h] [rbp-40h]
  int v40; // [rsp+8Ch] [rbp-3Ch]
  char *v41; // [rsp+90h] [rbp-38h]
  __int64 v42; // [rsp+98h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  const char *v45; // [rsp+E8h] [rbp+20h] BYREF

  v5 = 1;
  v6 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v28,
      v30,
      14,
      &WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
        (const char *)0x80004003LL,
        v28);
    LOBYTE(v28) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v28,
      (bool)"Processor is not started",
      v32);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      LODWORD(v45) = *((_DWORD *)this + 20);
      SRWLock = (PSRWLOCK)"Create monitor context";
      v35 = &xmmword_1800C21A0;
      v36 = (unsigned __int64)"RdpAvenc";
      *(_QWORD *)v37 = 0x1000000;
      v38 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800AEE52,
        v11,
        v12,
        (__int64)&v38,
        (__int64)v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&SRWLock,
        (__int64)&v45);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"MonitorCreate",
      "Rdp::Avenc::SinkWriter::CSinkWriterProcessor::CreateMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
      0x9Bu);
    v13 = (char *)operator new(0xE0u);
    v45 = v13;
    Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(
      v13,
      (char *)this - 80,
      a3);
    *(_QWORD *)v13 = &Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'};
    v36 = (unsigned __int64)(v13 + 80);
    *((_QWORD *)v13 + 10) = &Rdp::Avenc::SinkWriter::CMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'};
    *((_QWORD *)v13 + 11) = &Rdp::Avenc::SinkWriter::CMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'};
    *((_QWORD *)v13 + 26) = 0;
    *((_QWORD *)v13 + 27) = 0;
    v35 = (int *)v13;
    ((void (__fastcall *)(char *))Rdp::Utils::Com::ComObject<Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::Yuv::CYuvProcessor,>,Rdp::Avenc::IMonitorContext1,Rdp::Avenc::ICursorControl1>::AddRef)(v13);
    SRWLock = (PSRWLOCK)((char *)this + 64);
    AcquireSRWLockExclusive((PSRWLOCK)this + 8);
    v34 = 1;
    v14 = (char *)this + 48;
    v15 = v13 + 120;
    v38 = (const char *)*((_QWORD *)this + 6);
    v45 = (const char *)*((_QWORD *)v38 + 1);
    v16 = 0;
    *(_QWORD *)v37 = 0;
    v17 = v38;
    v18 = v45;
    if ( !v45[25] )
    {
      do
      {
        v45 = v18;
        if ( memcmp_0(v18 + 32, v15, 0x10u) >= 0 )
        {
          v16 = 1;
          v17 = v18;
          v18 = *(const char **)v18;
        }
        else
        {
          v16 = 0;
          v18 = (const char *)*((_QWORD *)v18 + 2);
        }
        v15 = v13 + 120;
      }
      while ( !v18[25] );
      v15 = v13 + 120;
    }
    if ( v17[25] || memcmp_0(v15, v17 + 32, 0x10u) < 0 )
    {
      if ( *((_QWORD *)v14 + 1) == 0x492492492492492LL )
        std::_Throw_tree_length_error();
      v41 = v14;
      v42 = 0;
      v20 = operator new(0x38u);
      v20[2] = *(_OWORD *)(v13 + 120);
      *((_QWORD *)v20 + 6) = v13;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
      v21 = v38;
      *(_QWORD *)v20 = v38;
      *((_QWORD *)v20 + 1) = v21;
      *((_QWORD *)v20 + 2) = v21;
      *((_WORD *)v20 + 12) = 0;
      v38 = v45;
      v39 = v16;
      v40 = v37[0];
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(
        v14,
        &v38,
        v20);
    }
    else
    {
      v19 = *((_QWORD *)v17 + 6);
      *((_QWORD *)v17 + 6) = v13;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    ReleaseSRWLockExclusive(SRWLock);
    *a2 = (struct Rdp::Avenc::IMonitorContext *)(v36 & -(__int64)(v13 != 0));
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v23 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v24 = GetCurrentThreadId();
      LOBYTE(v25) = v23;
      LOBYTE(v26) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v26,
        v25,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v29,
        v31,
        15,
        &WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids,
        v24);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA9,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x180032cd0  mov     [rsp+arg_0], rbx
0x180032cd5  mov     [rsp+arg_8], rdx
0x180032cda  push    rsi
0x180032cdb  push    r12
0x180032cdd  push    r13
0x180032cdf  push    r14
0x180032ce1  push    r15
0x180032ce3  sub     rsp, 0A0h
0x180032cea  mov     r12, r8
0x180032ced  mov     r14, rcx
0x180032cf0  lea     rcx, WPP_GLOBAL_Control
0x180032cf7  mov     rax, cs:WPP_GLOBAL_Control
0x180032cfe  mov     esi, 1
0x180032d03  cmp     rax, rcx
0x180032d06  jz      short loc_180032D19
0x180032d08  test    [rax+1Ch], sil
0x180032d0c  jz      short loc_180032D19
0x180032d0e  cmp     byte ptr [rax+19h], 4
0x180032d12  jb      short loc_180032D19
0x180032d14  mov     bl, sil
0x180032d17  jmp     short loc_180032D1B
0x180032d19  xor     bl, bl
0x180032d1b  lea     rax, WPP_RECORDER_INITIALIZED
0x180032d22  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180032d29  setnz   r15b
0x180032d2d  test    bl, bl
0x180032d2f  jnz     short loc_180032D36
0x180032d31  test    r15b, r15b
0x180032d34  jz      short loc_180032D6C
0x180032d36  call    cs:__imp_GetCurrentThreadId
0x180032d3c  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180032d40  lea     r13, WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids
0x180032d47  mov     [rsp+0C8h+MessageGuid], r13; MessageGuid
0x180032d4c  mov     word ptr [rsp+0C8h+var_98], 0Eh; char *
0x180032d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d5a  mov     r9, [rcx+28h]; int
0x180032d5e  mov     r8b, r15b; int
0x180032d61  mov     dl, bl; int
0x180032d63  mov     rcx, [rcx+10h]; int
0x180032d67  call    WPP_RECORDER_AND_TRACE_SF_D
0x180032d6c  mov     rcx, [rsp+0C8h]; this
0x180032d74  lea     r8, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180032d7b  cmp     [rsp+0C8h+arg_8], 0
0x180032d84  jz      loc_180033170
0x180032d8a  cmp     byte ptr [r14+0B0h], 0
0x180032d92  setz    al
0x180032d95  mov     rcx, [rsp+0C8h]; this
0x180032d9d  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180032da4  mov     qword ptr [rsp+0C8h+var_A0], rdx; bool
0x180032da9  mov     byte ptr [rsp+0C8h+var_A8], al; int
0x180032dad  mov     r9d, 8000FFFFh; char *
0x180032db3  mov     edx, 94h; void *
0x180032db8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180032dbd  mov     eax, cs:dword_1800C1058
0x180032dc3  cmp     eax, 4
0x180032dc6  jbe     loc_180032E98
0x180032dcc  mov     rcx, cs:qword_1800C1070
0x180032dd3  mov     rax, cs:qword_1800C1068
0x180032dda  mov     rdx, 470000000000h
0x180032de4  test    rdx, rax
0x180032de7  jz      loc_180032E98
0x180032ded  mov     rax, rcx
0x180032df0  and     rax, rdx
0x180032df3  cmp     rax, rcx
0x180032df6  jnz     loc_180032E98
0x180032dfc  mov     eax, [r14+50h]
0x180032e00  mov     dword ptr [rsp+0C8h+arg_18], eax
0x180032e07  lea     rax, aCreateMonitorC; "Create monitor context"
0x180032e0e  mov     [rsp+0C8h+SRWLock], rax
0x180032e13  lea     rax, xmmword_1800C21A0
0x180032e1a  mov     [rsp+0C8h+var_68], rax
0x180032e1f  lea     rax, aRdpavenc; "RdpAvenc"
0x180032e26  mov     [rsp+0C8h+var_60], rax
0x180032e2b  mov     qword ptr [rsp+0C8h+var_58], 1000000h
0x180032e34  lea     rax, aCheckpoint; "Checkpoint"
0x180032e3b  mov     [rsp+0C8h+var_48], rax
0x180032e43  lea     rax, [rsp+0C8h+arg_18]
0x180032e4b  mov     [rsp+0C8h+var_80], rax
0x180032e50  lea     rax, [rsp+0C8h+SRWLock]
0x180032e55  mov     qword ptr [rsp+0C8h+var_88], rax
0x180032e5a  lea     rax, [rsp+0C8h+var_68]
0x180032e5f  mov     [rsp+0C8h+MessageGuid], rax
0x180032e64  lea     rax, [rsp+0C8h+var_60]
0x180032e69  mov     [rsp+0C8h+var_98], rax
0x180032e6e  lea     rax, [rsp+0C8h+var_58]
0x180032e73  mov     qword ptr [rsp+0C8h+var_A0], rax; int
0x180032e78  lea     rax, [rsp+0C8h+var_48]
0x180032e80  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180032e85  lea     rdx, word_1800AEE52
0x180032e8c  lea     rcx, dword_1800C1058
0x180032e93  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180032e98  mov     [rsp+0C8h+var_A8], 9Bh; int
0x180032ea0  lea     r9, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180032ea7  lea     r8, aRdpAvencSinkwr; "Rdp::Avenc::SinkWriter::CSinkWriterProc"...
0x180032eae  lea     rdx, aMonitorcreate; "MonitorCreate"
0x180032eb5  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180032ebc  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180032ec1  mov     ecx, 0E0h; Size
0x180032ec6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032ecb  mov     rbx, rax
0x180032ece  mov     [rsp+0C8h+arg_18], rax
0x180032ed6  lea     rdx, [r14-50h]
0x180032eda  mov     r8, r12
0x180032edd  mov     rcx, rax
0x180032ee0  call    ??0?$CMonitorContextBase@VCSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UICursorControl1@34@@Avenc@Rdp@@QEAA@PEAVCSinkWriterProcessor@SinkWriter@12@PEAUIPropertyStore@@@Z; Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *,IPropertyStore *)
0x180032ee5  lea     rax, ??_7CRdpProgMonitorContext@RdpProg@Avenc@Rdp@@6BIUnknownBase@Com@Utils@3@@; const Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'}
0x180032eec  mov     [rbx], rax
0x180032eef  lea     rax, [rbx+50h]
0x180032ef3  mov     [rsp+0C8h+var_60], rax
0x180032ef8  lea     rcx, ??_7CMonitorContext@SinkWriter@Avenc@Rdp@@6BIMonitorContext1@23@@; const Rdp::Avenc::SinkWriter::CMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'}
0x180032eff  mov     [rax], rcx
0x180032f02  lea     rax, ??_7CMonitorContext@SinkWriter@Avenc@Rdp@@6BICursorControl1@23@@; const Rdp::Avenc::SinkWriter::CMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'}
0x180032f09  mov     [rbx+58h], rax
0x180032f0d  mov     qword ptr [rbx+0D0h], 0
0x180032f18  mov     qword ptr [rbx+0D8h], 0
0x180032f23  mov     [rsp+0C8h+var_68], rbx
0x180032f28  mov     rcx, rbx
0x180032f2b  mov     rax, cs:off_18008AFE8
0x180032f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f37  nop
0x180032f38  lea     rax, [r14+40h]
0x180032f3c  mov     [rsp+0C8h+SRWLock], rax
0x180032f41  mov     rcx, rax; SRWLock
0x180032f44  call    cs:__imp_AcquireSRWLockExclusive
0x180032f4a  mov     [rsp+0C8h+var_70], sil
0x180032f4f  lea     r13, [r14+30h]
0x180032f53  lea     rax, [rbx+78h]
0x180032f57  mov     rdx, [r13+0]
0x180032f5b  mov     [rsp+0C8h+var_48], rdx
0x180032f63  mov     rcx, [rdx+8]
0x180032f67  mov     [rsp+0C8h+arg_18], rcx
0x180032f6f  xor     r12d, r12d
0x180032f72  xor     r8d, r8d
0x180032f75  mov     qword ptr [rsp+0C8h+var_58], r8
0x180032f7a  mov     r15, rdx
0x180032f7d  mov     r14, rcx
0x180032f80  cmp     [rcx+19h], r8b
0x180032f84  jnz     short loc_180032FC5
0x180032f86  mov     [rsp+0C8h+arg_18], r14
0x180032f8e  lea     rcx, [r14+20h]; Buf1
0x180032f92  mov     r8d, 10h; Size
0x180032f98  mov     rdx, rax; Buf2
0x180032f9b  call    memcmp_0
0x180032fa0  test    eax, eax
0x180032fa2  jns     short loc_180032FAD
0x180032fa4  xor     r12d, r12d
0x180032fa7  mov     r14, [r14+10h]
0x180032fab  jmp     short loc_180032FB6
0x180032fad  mov     r12d, esi
0x180032fb0  mov     r15, r14
0x180032fb3  mov     r14, [r14]
0x180032fb6  cmp     byte ptr [r14+19h], 0
0x180032fbb  lea     rax, [rbx+78h]
0x180032fbf  jz      short loc_180032F86
0x180032fc1  lea     rax, [rbx+78h]
0x180032fc5  cmp     byte ptr [r15+19h], 0
0x180032fca  jnz     short loc_180033013
0x180032fcc  lea     rdx, [r15+20h]; Buf2
0x180032fd0  mov     r8d, 10h; Size
0x180032fd6  mov     rcx, rax; Buf1
0x180032fd9  call    memcmp_0
0x180032fde  test    eax, eax
0x180032fe0  js      short loc_180033013
0x180032fe2  mov     r14, [r15+30h]
0x180032fe6  mov     [r15+30h], rbx
0x180032fea  mov     rax, [rbx]
0x180032fed  mov     rcx, rbx
0x180032ff0  mov     rax, [rax+8]
0x180032ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ff9  test    r14, r14
0x180032ffc  jz      short loc_18003300E
0x180032ffe  mov     rax, [r14]
0x180033001  mov     rcx, r14
0x180033004  mov     rax, [rax+10h]
0x180033008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003300d  nop
0x18003300e  jmp     loc_1800330B7
0x180033013  mov     rax, 492492492492492h
0x18003301d  cmp     [r13+8], rax
0x180033021  jz      loc_180033181
0x180033027  mov     [rsp+0C8h+var_38], r13
0x18003302f  mov     [rsp+0C8h+var_30], 0
0x18003303b  mov     ecx, 38h ; '8'; Size
0x180033040  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033045  mov     r14, rax
0x180033048  movups  xmm0, xmmword ptr [rbx+78h]
0x18003304c  movdqu  xmmword ptr [rax+20h], xmm0
0x180033051  mov     [rax+30h], rbx
0x180033055  mov     rcx, [rbx]
0x180033058  mov     rax, [rcx+8]
0x18003305c  mov     rcx, rbx
0x18003305f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033064  nop
0x180033065  mov     rax, [rsp+0C8h+var_48]
0x18003306d  mov     [r14], rax
0x180033070  mov     [r14+8], rax
0x180033074  mov     [r14+10h], rax
0x180033078  mov     word ptr [r14+18h], 0
0x18003307f  mov     rax, [rsp+0C8h+arg_18]
0x180033087  mov     [rsp+0C8h+var_48], rax
0x18003308f  mov     [rsp+0C8h+var_40], r12d
0x180033097  mov     rax, qword ptr [rsp+0C8h+var_58]
0x18003309c  mov     [rsp+0C8h+var_3C], eax
0x1800330a3  mov     r8, r14
0x1800330a6  lea     rdx, [rsp+0C8h+var_48]
0x1800330ae  mov     rcx, r13
0x1800330b1  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> *>,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> * const)
0x1800330b6  nop
0x1800330b7  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x1800330bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800330c2  neg     rbx
0x1800330c5  sbb     rax, rax
0x1800330c8  and     rax, [rsp+0C8h+var_60]
0x1800330cd  mov     rcx, [rsp+0C8h+arg_8]
0x1800330d5  mov     [rcx], rax
0x1800330d8  mov     rax, cs:WPP_GLOBAL_Control
0x1800330df  lea     rcx, WPP_GLOBAL_Control
0x1800330e6  cmp     rax, rcx
0x1800330e9  jz      short loc_1800330F7
0x1800330eb  test    [rax+1Ch], sil
0x1800330ef  jz      short loc_1800330F7
0x1800330f1  cmp     byte ptr [rax+19h], 4
0x1800330f5  jnb     short loc_1800330FA
0x1800330f7  xor     sil, sil
0x1800330fa  lea     rax, WPP_RECORDER_INITIALIZED
0x180033101  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180033108  setnz   bl
0x18003310b  test    sil, sil
0x18003310e  jnz     short loc_180033114
0x180033110  test    bl, bl
0x180033112  jz      short loc_18003314C
0x180033114  call    cs:__imp_GetCurrentThreadId
0x18003311a  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18003311e  lea     rax, WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids
0x180033125  mov     [rsp+0C8h+MessageGuid], rax; MessageGuid
0x18003312a  mov     word ptr [rsp+0C8h+var_98], 0Fh; __int16
0x180033131  mov     rcx, cs:WPP_GLOBAL_Control
0x180033138  mov     r9, [rcx+28h]; int
0x18003313c  mov     r8b, bl; int
0x18003313f  mov     dl, sil; int
0x180033142  mov     rcx, [rcx+10h]; int
0x180033146  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003314b  nop
0x18003314c  xor     eax, eax
0x18003314e  jmp     short loc_180033157
0x180033150  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x180033157  mov     rbx, [rsp+0C8h+arg_0]
0x18003315f  add     rsp, 0A0h
0x180033166  pop     r15
0x180033168  pop     r14
0x18003316a  pop     r13
0x18003316c  pop     r12
0x18003316e  pop     rsi
0x18003316f  retn
0x180033170  mov     r9d, 80004003h; char *
0x180033176  mov     edx, 93h; void *
0x18003317b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033181  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
