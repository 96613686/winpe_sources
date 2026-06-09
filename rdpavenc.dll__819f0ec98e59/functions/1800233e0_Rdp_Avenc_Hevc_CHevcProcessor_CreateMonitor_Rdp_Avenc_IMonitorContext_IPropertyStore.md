# Rdp::Avenc::Hevc::CHevcProcessor::CreateMonitor(Rdp::Avenc::IMonitorContext * *,IPropertyStore *)

- ea: `0x1800233e0`
- end: `0x180023898`
- name: `?CreateMonitor@CHevcProcessor@Hevc@Avenc@Rdp@@UEAAJPEAPEAUIMonitorContext@34@PEAUIPropertyStore@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(Rdp::Avenc::Hevc::CHevcProcessor *__hidden this, struct Rdp::Avenc::IMonitorContext **, struct IPropertyStore *)`
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
- `0x1800233e0`
- `0x180082e84`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800237cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800237cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023654`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023654`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023824`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023824`

## string_xrefs

- `0x180023517`: `Create monitor context`
- `0x1800235be`: `MonitorCreate`
- `0x1800235b7`: `Rdp::Avenc::Hevc::CHevcProcessor::CreateMonitor`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Rdp::Avenc::Hevc::CHevcProcessor::CreateMonitor(
        Rdp::Avenc::Hevc::CHevcProcessor *this,
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
      &WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)0x80004003LL,
        v28);
    LOBYTE(v28) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
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
        (unsigned int)&byte_1800ADE47,
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
      "Rdp::Avenc::Hevc::CHevcProcessor::CreateMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
      0xC0u);
    v13 = (char *)operator new(0xE0u);
    v45 = v13;
    Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(
      v13,
      (char *)this - 80,
      a3);
    *(_QWORD *)v13 = &Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'};
    v36 = (unsigned __int64)(v13 + 80);
    *((_QWORD *)v13 + 10) = &Rdp::Avenc::Hevc::CMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'};
    *((_QWORD *)v13 + 11) = &Rdp::Avenc::Hevc::CMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'};
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
        &WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids,
        v24);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xCE,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x1800233e0  mov     [rsp+arg_0], rbx
0x1800233e5  mov     [rsp+arg_8], rdx
0x1800233ea  push    rsi
0x1800233eb  push    r12
0x1800233ed  push    r13
0x1800233ef  push    r14
0x1800233f1  push    r15
0x1800233f3  sub     rsp, 0A0h
0x1800233fa  mov     r12, r8
0x1800233fd  mov     r14, rcx
0x180023400  lea     rcx, WPP_GLOBAL_Control
0x180023407  mov     rax, cs:WPP_GLOBAL_Control
0x18002340e  mov     esi, 1
0x180023413  cmp     rax, rcx
0x180023416  jz      short loc_180023429
0x180023418  test    [rax+1Ch], sil
0x18002341c  jz      short loc_180023429
0x18002341e  cmp     byte ptr [rax+19h], 4
0x180023422  jb      short loc_180023429
0x180023424  mov     bl, sil
0x180023427  jmp     short loc_18002342B
0x180023429  xor     bl, bl
0x18002342b  lea     rax, WPP_RECORDER_INITIALIZED
0x180023432  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180023439  setnz   r15b
0x18002343d  test    bl, bl
0x18002343f  jnz     short loc_180023446
0x180023441  test    r15b, r15b
0x180023444  jz      short loc_18002347C
0x180023446  call    cs:__imp_GetCurrentThreadId
0x18002344c  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180023450  lea     r13, WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids
0x180023457  mov     [rsp+0C8h+MessageGuid], r13; MessageGuid
0x18002345c  mov     word ptr [rsp+0C8h+var_98], 0Eh; char *
0x180023463  mov     rcx, cs:WPP_GLOBAL_Control
0x18002346a  mov     r9, [rcx+28h]; int
0x18002346e  mov     r8b, r15b; int
0x180023471  mov     dl, bl; int
0x180023473  mov     rcx, [rcx+10h]; int
0x180023477  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002347c  mov     rcx, [rsp+0C8h]; this
0x180023484  lea     r8, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002348b  cmp     [rsp+0C8h+arg_8], 0
0x180023494  jz      loc_180023880
0x18002349a  cmp     byte ptr [r14+0B0h], 0
0x1800234a2  setz    al
0x1800234a5  mov     rcx, [rsp+0C8h]; this
0x1800234ad  lea     rdx, aProcessorIsNot; "Processor is not started"
0x1800234b4  mov     qword ptr [rsp+0C8h+var_A0], rdx; bool
0x1800234b9  mov     byte ptr [rsp+0C8h+var_A8], al; int
0x1800234bd  mov     r9d, 8000FFFFh; char *
0x1800234c3  mov     edx, 0B9h; void *
0x1800234c8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800234cd  mov     eax, cs:dword_1800C1058
0x1800234d3  cmp     eax, 4
0x1800234d6  jbe     loc_1800235A8
0x1800234dc  mov     rcx, cs:qword_1800C1070
0x1800234e3  mov     rax, cs:qword_1800C1068
0x1800234ea  mov     rdx, 470000000000h
0x1800234f4  test    rdx, rax
0x1800234f7  jz      loc_1800235A8
0x1800234fd  mov     rax, rcx
0x180023500  and     rax, rdx
0x180023503  cmp     rax, rcx
0x180023506  jnz     loc_1800235A8
0x18002350c  mov     eax, [r14+50h]
0x180023510  mov     dword ptr [rsp+0C8h+arg_18], eax
0x180023517  lea     rax, aCreateMonitorC; "Create monitor context"
0x18002351e  mov     [rsp+0C8h+SRWLock], rax
0x180023523  lea     rax, xmmword_1800C21A0
0x18002352a  mov     [rsp+0C8h+var_68], rax
0x18002352f  lea     rax, aRdpavenc; "RdpAvenc"
0x180023536  mov     [rsp+0C8h+var_60], rax
0x18002353b  mov     qword ptr [rsp+0C8h+var_58], 1000000h
0x180023544  lea     rax, aCheckpoint; "Checkpoint"
0x18002354b  mov     [rsp+0C8h+var_48], rax
0x180023553  lea     rax, [rsp+0C8h+arg_18]
0x18002355b  mov     [rsp+0C8h+var_80], rax
0x180023560  lea     rax, [rsp+0C8h+SRWLock]
0x180023565  mov     qword ptr [rsp+0C8h+var_88], rax
0x18002356a  lea     rax, [rsp+0C8h+var_68]
0x18002356f  mov     [rsp+0C8h+MessageGuid], rax
0x180023574  lea     rax, [rsp+0C8h+var_60]
0x180023579  mov     [rsp+0C8h+var_98], rax
0x18002357e  lea     rax, [rsp+0C8h+var_58]
0x180023583  mov     qword ptr [rsp+0C8h+var_A0], rax; int
0x180023588  lea     rax, [rsp+0C8h+var_48]
0x180023590  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180023595  lea     rdx, byte_1800ADE47
0x18002359c  lea     rcx, dword_1800C1058
0x1800235a3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800235a8  mov     [rsp+0C8h+var_A8], 0C0h; int
0x1800235b0  lea     r9, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800235b7  lea     r8, aRdpAvencHevcCh_0; "Rdp::Avenc::Hevc::CHevcProcessor::Creat"...
0x1800235be  lea     rdx, aMonitorcreate; "MonitorCreate"
0x1800235c5  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800235cc  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800235d1  mov     ecx, 0E0h; Size
0x1800235d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800235db  mov     rbx, rax
0x1800235de  mov     [rsp+0C8h+arg_18], rax
0x1800235e6  lea     rdx, [r14-50h]
0x1800235ea  mov     r8, r12
0x1800235ed  mov     rcx, rax
0x1800235f0  call    ??0?$CMonitorContextBase@VCSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UICursorControl1@34@@Avenc@Rdp@@QEAA@PEAVCSinkWriterProcessor@SinkWriter@12@PEAUIPropertyStore@@@Z; Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *,IPropertyStore *)
0x1800235f5  lea     rax, ??_7CRdpProgMonitorContext@RdpProg@Avenc@Rdp@@6BIUnknownBase@Com@Utils@3@@; const Rdp::Avenc::RdpProg::CRdpProgMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'}
0x1800235fc  mov     [rbx], rax
0x1800235ff  lea     rax, [rbx+50h]
0x180023603  mov     [rsp+0C8h+var_60], rax
0x180023608  lea     rcx, ??_7CMonitorContext@Hevc@Avenc@Rdp@@6BIMonitorContext1@23@@; const Rdp::Avenc::Hevc::CMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'}
0x18002360f  mov     [rax], rcx
0x180023612  lea     rax, ??_7CMonitorContext@Hevc@Avenc@Rdp@@6BICursorControl1@23@@; const Rdp::Avenc::Hevc::CMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'}
0x180023619  mov     [rbx+58h], rax
0x18002361d  mov     qword ptr [rbx+0D0h], 0
0x180023628  mov     qword ptr [rbx+0D8h], 0
0x180023633  mov     [rsp+0C8h+var_68], rbx
0x180023638  mov     rcx, rbx
0x18002363b  mov     rax, cs:off_18008AFE8
0x180023642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023647  nop
0x180023648  lea     rax, [r14+40h]
0x18002364c  mov     [rsp+0C8h+SRWLock], rax
0x180023651  mov     rcx, rax; SRWLock
0x180023654  call    cs:__imp_AcquireSRWLockExclusive
0x18002365a  mov     [rsp+0C8h+var_70], sil
0x18002365f  lea     r13, [r14+30h]
0x180023663  lea     rax, [rbx+78h]
0x180023667  mov     rdx, [r13+0]
0x18002366b  mov     [rsp+0C8h+var_48], rdx
0x180023673  mov     rcx, [rdx+8]
0x180023677  mov     [rsp+0C8h+arg_18], rcx
0x18002367f  xor     r12d, r12d
0x180023682  xor     r8d, r8d
0x180023685  mov     qword ptr [rsp+0C8h+var_58], r8
0x18002368a  mov     r15, rdx
0x18002368d  mov     r14, rcx
0x180023690  cmp     [rcx+19h], r8b
0x180023694  jnz     short loc_1800236D5
0x180023696  mov     [rsp+0C8h+arg_18], r14
0x18002369e  lea     rcx, [r14+20h]; Buf1
0x1800236a2  mov     r8d, 10h; Size
0x1800236a8  mov     rdx, rax; Buf2
0x1800236ab  call    memcmp_0
0x1800236b0  test    eax, eax
0x1800236b2  jns     short loc_1800236BD
0x1800236b4  xor     r12d, r12d
0x1800236b7  mov     r14, [r14+10h]
0x1800236bb  jmp     short loc_1800236C6
0x1800236bd  mov     r12d, esi
0x1800236c0  mov     r15, r14
0x1800236c3  mov     r14, [r14]
0x1800236c6  cmp     byte ptr [r14+19h], 0
0x1800236cb  lea     rax, [rbx+78h]
0x1800236cf  jz      short loc_180023696
0x1800236d1  lea     rax, [rbx+78h]
0x1800236d5  cmp     byte ptr [r15+19h], 0
0x1800236da  jnz     short loc_180023723
0x1800236dc  lea     rdx, [r15+20h]; Buf2
0x1800236e0  mov     r8d, 10h; Size
0x1800236e6  mov     rcx, rax; Buf1
0x1800236e9  call    memcmp_0
0x1800236ee  test    eax, eax
0x1800236f0  js      short loc_180023723
0x1800236f2  mov     r14, [r15+30h]
0x1800236f6  mov     [r15+30h], rbx
0x1800236fa  mov     rax, [rbx]
0x1800236fd  mov     rcx, rbx
0x180023700  mov     rax, [rax+8]
0x180023704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023709  test    r14, r14
0x18002370c  jz      short loc_18002371E
0x18002370e  mov     rax, [r14]
0x180023711  mov     rcx, r14
0x180023714  mov     rax, [rax+10h]
0x180023718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002371d  nop
0x18002371e  jmp     loc_1800237C7
0x180023723  mov     rax, 492492492492492h
0x18002372d  cmp     [r13+8], rax
0x180023731  jz      loc_180023891
0x180023737  mov     [rsp+0C8h+var_38], r13
0x18002373f  mov     [rsp+0C8h+var_30], 0
0x18002374b  mov     ecx, 38h ; '8'; Size
0x180023750  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023755  mov     r14, rax
0x180023758  movups  xmm0, xmmword ptr [rbx+78h]
0x18002375c  movdqu  xmmword ptr [rax+20h], xmm0
0x180023761  mov     [rax+30h], rbx
0x180023765  mov     rcx, [rbx]
0x180023768  mov     rax, [rcx+8]
0x18002376c  mov     rcx, rbx
0x18002376f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023774  nop
0x180023775  mov     rax, [rsp+0C8h+var_48]
0x18002377d  mov     [r14], rax
0x180023780  mov     [r14+8], rax
0x180023784  mov     [r14+10h], rax
0x180023788  mov     word ptr [r14+18h], 0
0x18002378f  mov     rax, [rsp+0C8h+arg_18]
0x180023797  mov     [rsp+0C8h+var_48], rax
0x18002379f  mov     [rsp+0C8h+var_40], r12d
0x1800237a7  mov     rax, qword ptr [rsp+0C8h+var_58]
0x1800237ac  mov     [rsp+0C8h+var_3C], eax
0x1800237b3  mov     r8, r14
0x1800237b6  lea     rdx, [rsp+0C8h+var_48]
0x1800237be  mov     rcx, r13
0x1800237c1  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> *>,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> * const)
0x1800237c6  nop
0x1800237c7  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x1800237cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800237d2  neg     rbx
0x1800237d5  sbb     rax, rax
0x1800237d8  and     rax, [rsp+0C8h+var_60]
0x1800237dd  mov     rcx, [rsp+0C8h+arg_8]
0x1800237e5  mov     [rcx], rax
0x1800237e8  mov     rax, cs:WPP_GLOBAL_Control
0x1800237ef  lea     rcx, WPP_GLOBAL_Control
0x1800237f6  cmp     rax, rcx
0x1800237f9  jz      short loc_180023807
0x1800237fb  test    [rax+1Ch], sil
0x1800237ff  jz      short loc_180023807
0x180023801  cmp     byte ptr [rax+19h], 4
0x180023805  jnb     short loc_18002380A
0x180023807  xor     sil, sil
0x18002380a  lea     rax, WPP_RECORDER_INITIALIZED
0x180023811  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180023818  setnz   bl
0x18002381b  test    sil, sil
0x18002381e  jnz     short loc_180023824
0x180023820  test    bl, bl
0x180023822  jz      short loc_18002385C
0x180023824  call    cs:__imp_GetCurrentThreadId
0x18002382a  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18002382e  lea     rax, WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids
0x180023835  mov     [rsp+0C8h+MessageGuid], rax; MessageGuid
0x18002383a  mov     word ptr [rsp+0C8h+var_98], 0Fh; __int16
0x180023841  mov     rcx, cs:WPP_GLOBAL_Control
0x180023848  mov     r9, [rcx+28h]; int
0x18002384c  mov     r8b, bl; int
0x18002384f  mov     dl, sil; int
0x180023852  mov     rcx, [rcx+10h]; int
0x180023856  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002385b  nop
0x18002385c  xor     eax, eax
0x18002385e  jmp     short loc_180023867
0x180023860  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x180023867  mov     rbx, [rsp+0C8h+arg_0]
0x18002386f  add     rsp, 0A0h
0x180023876  pop     r15
0x180023878  pop     r14
0x18002387a  pop     r13
0x18002387c  pop     r12
0x18002387e  pop     rsi
0x18002387f  retn
0x180023880  mov     r9d, 80004003h; char *
0x180023886  mov     edx, 0B8h; void *
0x18002388b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023891  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
