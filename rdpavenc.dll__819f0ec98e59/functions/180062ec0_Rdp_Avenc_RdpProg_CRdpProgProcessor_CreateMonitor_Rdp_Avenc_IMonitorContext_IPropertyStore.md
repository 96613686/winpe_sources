# Rdp::Avenc::RdpProg::CRdpProgProcessor::CreateMonitor(Rdp::Avenc::IMonitorContext * *,IPropertyStore *)

- ea: `0x180062ec0`
- end: `0x180063378`
- name: `?CreateMonitor@CRdpProgProcessor@RdpProg@Avenc@Rdp@@UEAAJPEAPEAUIMonitorContext@34@PEAUIPropertyStore@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(Rdp::Avenc::RdpProg::CRdpProgProcessor *__hidden this, struct Rdp::Avenc::IMonitorContext **, struct IPropertyStore *)`
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
- `0x180062ec0`
- `0x180082e84`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800632ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800632ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063134`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063134`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062f26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063304`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062f26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063304`

## string_xrefs

- `0x180062ff7`: `Create monitor context`
- `0x18006309e`: `MonitorCreate`
- `0x180063097`: `Rdp::Avenc::RdpProg::CRdpProgProcessor::CreateMonitor`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgProcessor::CreateMonitor(
        Rdp::Avenc::RdpProg::CRdpProgProcessor *this,
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
      &WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
        (const char *)0x80004003LL,
        v28);
    LOBYTE(v28) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
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
        (unsigned int)byte_1800B4E3D,
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
      "Rdp::Avenc::RdpProg::CRdpProgProcessor::CreateMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
      0xA5u);
    v13 = (char *)operator new(0xE0u);
    v45 = v13;
    Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(
      v13,
      (char *)this - 80,
      a3);
    *(_QWORD *)v13 = &Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'};
    v36 = (unsigned __int64)(v13 + 80);
    *((_QWORD *)v13 + 10) = &Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'};
    *((_QWORD *)v13 + 11) = &Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'};
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
        &WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids,
        v24);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB3,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x180062ec0  mov     [rsp+arg_0], rbx
0x180062ec5  mov     [rsp+arg_8], rdx
0x180062eca  push    rsi
0x180062ecb  push    r12
0x180062ecd  push    r13
0x180062ecf  push    r14
0x180062ed1  push    r15
0x180062ed3  sub     rsp, 0A0h
0x180062eda  mov     r12, r8
0x180062edd  mov     r14, rcx
0x180062ee0  lea     rcx, WPP_GLOBAL_Control
0x180062ee7  mov     rax, cs:WPP_GLOBAL_Control
0x180062eee  mov     esi, 1
0x180062ef3  cmp     rax, rcx
0x180062ef6  jz      short loc_180062F09
0x180062ef8  test    [rax+1Ch], sil
0x180062efc  jz      short loc_180062F09
0x180062efe  cmp     byte ptr [rax+19h], 4
0x180062f02  jb      short loc_180062F09
0x180062f04  mov     bl, sil
0x180062f07  jmp     short loc_180062F0B
0x180062f09  xor     bl, bl
0x180062f0b  lea     rax, WPP_RECORDER_INITIALIZED
0x180062f12  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180062f19  setnz   r15b
0x180062f1d  test    bl, bl
0x180062f1f  jnz     short loc_180062F26
0x180062f21  test    r15b, r15b
0x180062f24  jz      short loc_180062F5C
0x180062f26  call    cs:__imp_GetCurrentThreadId
0x180062f2c  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180062f30  lea     r13, WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids
0x180062f37  mov     [rsp+0C8h+MessageGuid], r13; MessageGuid
0x180062f3c  mov     word ptr [rsp+0C8h+var_98], 0Eh; char *
0x180062f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f4a  mov     r9, [rcx+28h]; int
0x180062f4e  mov     r8b, r15b; int
0x180062f51  mov     dl, bl; int
0x180062f53  mov     rcx, [rcx+10h]; int
0x180062f57  call    WPP_RECORDER_AND_TRACE_SF_D
0x180062f5c  mov     rcx, [rsp+0C8h]; this
0x180062f64  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180062f6b  cmp     [rsp+0C8h+arg_8], 0
0x180062f74  jz      loc_180063360
0x180062f7a  cmp     byte ptr [r14+0B0h], 0
0x180062f82  setz    al
0x180062f85  mov     rcx, [rsp+0C8h]; this
0x180062f8d  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180062f94  mov     qword ptr [rsp+0C8h+var_A0], rdx; bool
0x180062f99  mov     byte ptr [rsp+0C8h+var_A8], al; int
0x180062f9d  mov     r9d, 8000FFFFh; char *
0x180062fa3  mov     edx, 9Eh; void *
0x180062fa8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180062fad  mov     eax, cs:dword_1800C1058
0x180062fb3  cmp     eax, 4
0x180062fb6  jbe     loc_180063088
0x180062fbc  mov     rcx, cs:qword_1800C1070
0x180062fc3  mov     rax, cs:qword_1800C1068
0x180062fca  mov     rdx, 470000000000h
0x180062fd4  test    rdx, rax
0x180062fd7  jz      loc_180063088
0x180062fdd  mov     rax, rcx
0x180062fe0  and     rax, rdx
0x180062fe3  cmp     rax, rcx
0x180062fe6  jnz     loc_180063088
0x180062fec  mov     eax, [r14+50h]
0x180062ff0  mov     dword ptr [rsp+0C8h+arg_18], eax
0x180062ff7  lea     rax, aCreateMonitorC; "Create monitor context"
0x180062ffe  mov     [rsp+0C8h+SRWLock], rax
0x180063003  lea     rax, xmmword_1800C21A0
0x18006300a  mov     [rsp+0C8h+var_68], rax
0x18006300f  lea     rax, aRdpavenc; "RdpAvenc"
0x180063016  mov     [rsp+0C8h+var_60], rax
0x18006301b  mov     qword ptr [rsp+0C8h+var_58], 1000000h
0x180063024  lea     rax, aCheckpoint; "Checkpoint"
0x18006302b  mov     [rsp+0C8h+var_48], rax
0x180063033  lea     rax, [rsp+0C8h+arg_18]
0x18006303b  mov     [rsp+0C8h+var_80], rax
0x180063040  lea     rax, [rsp+0C8h+SRWLock]
0x180063045  mov     qword ptr [rsp+0C8h+var_88], rax
0x18006304a  lea     rax, [rsp+0C8h+var_68]
0x18006304f  mov     [rsp+0C8h+MessageGuid], rax
0x180063054  lea     rax, [rsp+0C8h+var_60]
0x180063059  mov     [rsp+0C8h+var_98], rax
0x18006305e  lea     rax, [rsp+0C8h+var_58]
0x180063063  mov     qword ptr [rsp+0C8h+var_A0], rax; int
0x180063068  lea     rax, [rsp+0C8h+var_48]
0x180063070  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180063075  lea     rdx, byte_1800B4E3D
0x18006307c  lea     rcx, dword_1800C1058
0x180063083  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180063088  mov     [rsp+0C8h+var_A8], 0A5h; int
0x180063090  lea     r9, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180063097  lea     r8, aRdpAvencRdppro_5; "Rdp::Avenc::RdpProg::CRdpProgProcessor:"...
0x18006309e  lea     rdx, aMonitorcreate; "MonitorCreate"
0x1800630a5  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800630ac  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800630b1  mov     ecx, 0E0h; Size
0x1800630b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800630bb  mov     rbx, rax
0x1800630be  mov     [rsp+0C8h+arg_18], rax
0x1800630c6  lea     rdx, [r14-50h]
0x1800630ca  mov     r8, r12
0x1800630cd  mov     rcx, rax
0x1800630d0  call    ??0?$CMonitorContextBase@VCSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UICursorControl1@34@@Avenc@Rdp@@QEAA@PEAVCSinkWriterProcessor@SinkWriter@12@PEAUIPropertyStore@@@Z; Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *,IPropertyStore *)
0x1800630d5  lea     rax, ??_7CRdpProgMonitorContext@RdpProg@Avenc@Rdp@@6BIUnknownBase@Com@Utils@3@@; const Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'}
0x1800630dc  mov     [rbx], rax
0x1800630df  lea     rax, [rbx+50h]
0x1800630e3  mov     [rsp+0C8h+var_60], rax
0x1800630e8  lea     rcx, ??_7CRdpProgMonitorContext@RdpProg@Avenc@Rdp@@6BIMonitorContext1@23@@; const Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'}
0x1800630ef  mov     [rax], rcx
0x1800630f2  lea     rax, ??_7CRdpProgMonitorContext@RdpProg@Avenc@Rdp@@6BICursorControl1@23@@; const Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'}
0x1800630f9  mov     [rbx+58h], rax
0x1800630fd  mov     qword ptr [rbx+0D0h], 0
0x180063108  mov     qword ptr [rbx+0D8h], 0
0x180063113  mov     [rsp+0C8h+var_68], rbx
0x180063118  mov     rcx, rbx
0x18006311b  mov     rax, cs:off_18008AFE8
0x180063122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063127  nop
0x180063128  lea     rax, [r14+40h]
0x18006312c  mov     [rsp+0C8h+SRWLock], rax
0x180063131  mov     rcx, rax; SRWLock
0x180063134  call    cs:__imp_AcquireSRWLockExclusive
0x18006313a  mov     [rsp+0C8h+var_70], sil
0x18006313f  lea     r13, [r14+30h]
0x180063143  lea     rax, [rbx+78h]
0x180063147  mov     rdx, [r13+0]
0x18006314b  mov     [rsp+0C8h+var_48], rdx
0x180063153  mov     rcx, [rdx+8]
0x180063157  mov     [rsp+0C8h+arg_18], rcx
0x18006315f  xor     r12d, r12d
0x180063162  xor     r8d, r8d
0x180063165  mov     qword ptr [rsp+0C8h+var_58], r8
0x18006316a  mov     r15, rdx
0x18006316d  mov     r14, rcx
0x180063170  cmp     [rcx+19h], r8b
0x180063174  jnz     short loc_1800631B5
0x180063176  mov     [rsp+0C8h+arg_18], r14
0x18006317e  lea     rcx, [r14+20h]; Buf1
0x180063182  mov     r8d, 10h; Size
0x180063188  mov     rdx, rax; Buf2
0x18006318b  call    memcmp_0
0x180063190  test    eax, eax
0x180063192  jns     short loc_18006319D
0x180063194  xor     r12d, r12d
0x180063197  mov     r14, [r14+10h]
0x18006319b  jmp     short loc_1800631A6
0x18006319d  mov     r12d, esi
0x1800631a0  mov     r15, r14
0x1800631a3  mov     r14, [r14]
0x1800631a6  cmp     byte ptr [r14+19h], 0
0x1800631ab  lea     rax, [rbx+78h]
0x1800631af  jz      short loc_180063176
0x1800631b1  lea     rax, [rbx+78h]
0x1800631b5  cmp     byte ptr [r15+19h], 0
0x1800631ba  jnz     short loc_180063203
0x1800631bc  lea     rdx, [r15+20h]; Buf2
0x1800631c0  mov     r8d, 10h; Size
0x1800631c6  mov     rcx, rax; Buf1
0x1800631c9  call    memcmp_0
0x1800631ce  test    eax, eax
0x1800631d0  js      short loc_180063203
0x1800631d2  mov     r14, [r15+30h]
0x1800631d6  mov     [r15+30h], rbx
0x1800631da  mov     rax, [rbx]
0x1800631dd  mov     rcx, rbx
0x1800631e0  mov     rax, [rax+8]
0x1800631e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631e9  test    r14, r14
0x1800631ec  jz      short loc_1800631FE
0x1800631ee  mov     rax, [r14]
0x1800631f1  mov     rcx, r14
0x1800631f4  mov     rax, [rax+10h]
0x1800631f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631fd  nop
0x1800631fe  jmp     loc_1800632A7
0x180063203  mov     rax, 492492492492492h
0x18006320d  cmp     [r13+8], rax
0x180063211  jz      loc_180063371
0x180063217  mov     [rsp+0C8h+var_38], r13
0x18006321f  mov     [rsp+0C8h+var_30], 0
0x18006322b  mov     ecx, 38h ; '8'; Size
0x180063230  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063235  mov     r14, rax
0x180063238  movups  xmm0, xmmword ptr [rbx+78h]
0x18006323c  movdqu  xmmword ptr [rax+20h], xmm0
0x180063241  mov     [rax+30h], rbx
0x180063245  mov     rcx, [rbx]
0x180063248  mov     rax, [rcx+8]
0x18006324c  mov     rcx, rbx
0x18006324f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063254  nop
0x180063255  mov     rax, [rsp+0C8h+var_48]
0x18006325d  mov     [r14], rax
0x180063260  mov     [r14+8], rax
0x180063264  mov     [r14+10h], rax
0x180063268  mov     word ptr [r14+18h], 0
0x18006326f  mov     rax, [rsp+0C8h+arg_18]
0x180063277  mov     [rsp+0C8h+var_48], rax
0x18006327f  mov     [rsp+0C8h+var_40], r12d
0x180063287  mov     rax, qword ptr [rsp+0C8h+var_58]
0x18006328c  mov     [rsp+0C8h+var_3C], eax
0x180063293  mov     r8, r14
0x180063296  lea     rdx, [rsp+0C8h+var_48]
0x18006329e  mov     rcx, r13
0x1800632a1  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> *>,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> * const)
0x1800632a6  nop
0x1800632a7  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x1800632ac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800632b2  neg     rbx
0x1800632b5  sbb     rax, rax
0x1800632b8  and     rax, [rsp+0C8h+var_60]
0x1800632bd  mov     rcx, [rsp+0C8h+arg_8]
0x1800632c5  mov     [rcx], rax
0x1800632c8  mov     rax, cs:WPP_GLOBAL_Control
0x1800632cf  lea     rcx, WPP_GLOBAL_Control
0x1800632d6  cmp     rax, rcx
0x1800632d9  jz      short loc_1800632E7
0x1800632db  test    [rax+1Ch], sil
0x1800632df  jz      short loc_1800632E7
0x1800632e1  cmp     byte ptr [rax+19h], 4
0x1800632e5  jnb     short loc_1800632EA
0x1800632e7  xor     sil, sil
0x1800632ea  lea     rax, WPP_RECORDER_INITIALIZED
0x1800632f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800632f8  setnz   bl
0x1800632fb  test    sil, sil
0x1800632fe  jnz     short loc_180063304
0x180063300  test    bl, bl
0x180063302  jz      short loc_18006333C
0x180063304  call    cs:__imp_GetCurrentThreadId
0x18006330a  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18006330e  lea     rax, WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids
0x180063315  mov     [rsp+0C8h+MessageGuid], rax; MessageGuid
0x18006331a  mov     word ptr [rsp+0C8h+var_98], 0Fh; __int16
0x180063321  mov     rcx, cs:WPP_GLOBAL_Control
0x180063328  mov     r9, [rcx+28h]; int
0x18006332c  mov     r8b, bl; int
0x18006332f  mov     dl, sil; int
0x180063332  mov     rcx, [rcx+10h]; int
0x180063336  call    WPP_RECORDER_AND_TRACE_SF_D
0x18006333b  nop
0x18006333c  xor     eax, eax
0x18006333e  jmp     short loc_180063347
0x180063340  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x180063347  mov     rbx, [rsp+0C8h+arg_0]
0x18006334f  add     rsp, 0A0h
0x180063356  pop     r15
0x180063358  pop     r14
0x18006335a  pop     r13
0x18006335c  pop     r12
0x18006335e  pop     rsi
0x18006335f  retn
0x180063360  mov     r9d, 80004003h; char *
0x180063366  mov     edx, 9Dh; void *
0x18006336b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180063371  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
