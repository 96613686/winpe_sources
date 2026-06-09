# Rdp::Avenc::Umrdp::CUmrdpProcessor::CreateMonitor(Rdp::Avenc::IMonitorContext * *,IPropertyStore *)

- ea: `0x180011ed0`
- end: `0x180012390`
- name: `?CreateMonitor@CUmrdpProcessor@Umrdp@Avenc@Rdp@@UEAAJPEAPEAUIMonitorContext@34@PEAUIPropertyStore@@@Z`
- size: `1216`
- prototype: `int(Rdp::Avenc::Umrdp::CUmrdpProcessor *__hidden this, struct Rdp::Avenc::IMonitorContext **, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x1800018c4`
- `0x1800065a4`
- `0x18000ec04`
- `0x180011ed0`
- `0x1800146bc`
- `0x180014e7c`
- `0x1800150ac`
- `0x1800153f8`
- `0x180015480`
- `0x180019fbc`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012315`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012315`

## string_xrefs

- `0x180012004`: `Create monitor context`
- `0x180012259`: `Create monitor context`
- `0x1800120a0`: `Rdp::Avenc::Umrdp::CUmrdpProcessor::CreateMonitor`
- `0x180012268`: `Rdp::Avenc::Umrdp::CUmrdpProcessor::CreateMonitor`
- `0x1800120a7`: `MonitorCreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Rdp::Avenc::Umrdp::CUmrdpProcessor::CreateMonitor(
        Rdp::Avenc::Umrdp::CUmrdpProcessor *this,
        struct Rdp::Avenc::IMonitorContext **a2,
        struct IPropertyStore *a3)
{
  char v6; // si
  bool v7; // bl
  bool v8; // r14
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rax
  int v15; // r8d
  const char *v16; // r9
  struct Rdp::Avenc::IMonitorContext *v17; // rbx
  const char **v18; // r13
  char *v19; // r15
  const char *v20; // rcx
  const char *v21; // rax
  __int64 v22; // r14
  const char **v23; // r14
  const char *v24; // rax
  bool v25; // bl
  char v26; // al
  int v27; // r8d
  int v28; // edx
  __int64 result; // rax
  int v30; // [rsp+20h] [rbp-98h]
  int v31; // [rsp+20h] [rbp-98h]
  int v32; // [rsp+28h] [rbp-90h]
  int v33; // [rsp+28h] [rbp-90h]
  char *v34; // [rsp+30h] [rbp-88h]
  const char *v35; // [rsp+50h] [rbp-68h] BYREF
  _QWORD v36[2]; // [rsp+58h] [rbp-60h] BYREF
  int v37[2]; // [rsp+68h] [rbp-50h] BYREF
  _QWORD v38[2]; // [rsp+70h] [rbp-48h] BYREF
  const char *v39; // [rsp+80h] [rbp-38h] BYREF
  int v40; // [rsp+88h] [rbp-30h]
  int v41; // [rsp+8Ch] [rbp-2Ch]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  Rdp::Avenc::Umrdp::CMonitorContext *v44; // [rsp+D8h] [rbp+20h] BYREF

  v6 = 1;
  v7 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v30,
      v32,
      16,
      &WPP_44e245a864023212cc554d824265b257_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
        (const char *)0x80004003LL,
        v30);
    LOBYTE(v30) = *((_BYTE *)this + 16) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v30,
      (bool)"Processor is not started",
      v34);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      LODWORD(v44) = *((_DWORD *)this + 29);
      v35 = "Create monitor context";
      v36[0] = &xmmword_1800C21A0;
      *(_QWORD *)v37 = "RdpAvenc";
      v38[0] = 0x1000000;
      v39 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&dword_1800AC79C,
        v12,
        v13,
        (__int64)&v39,
        (__int64)v38,
        (__int64)v37,
        (__int64)v36,
        (__int64)&v35,
        (__int64)&v44);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"MonitorCreate",
      "Rdp::Avenc::Umrdp::CUmrdpProcessor::CreateMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      0x10Eu);
    v44 = (Rdp::Avenc::Umrdp::CMonitorContext *)operator new(0xB0u);
    v14 = Rdp::Avenc::Umrdp::CMonitorContext::CMonitorContext(
            v44,
            (Rdp::Avenc::Umrdp::CUmrdpProcessor *)((char *)this - 80),
            a3);
    v17 = (struct Rdp::Avenc::IMonitorContext *)v14;
    *(_QWORD *)v37 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    v18 = (const char **)((char *)this + 40);
    if ( v17 )
      v19 = (char *)v17 + 80;
    else
      v19 = 0;
    v39 = *v18;
    v35 = (const char *)*((_QWORD *)v39 + 1);
    LODWORD(v44) = 0;
    v38[0] = 0;
    v20 = v39;
    v21 = v35;
    while ( !v21[25] )
    {
      v35 = v21;
      if ( *((_QWORD *)v21 + 4) >= (unsigned __int64)v19 )
      {
        LODWORD(v44) = 1;
        v20 = v21;
        v21 = *(const char **)v21;
      }
      else
      {
        LODWORD(v44) = 0;
        v21 = (const char *)*((_QWORD *)v21 + 2);
      }
    }
    if ( v20[25] || (unsigned __int64)v19 < *((_QWORD *)v20 + 4) )
    {
      if ( v18[1] == (const char *)0x555555555555555LL )
        std::_Throw_tree_length_error();
      v36[0] = v18;
      v36[1] = 0;
      v23 = (const char **)operator new(0x30u);
      v23[4] = v19;
      v23[5] = (const char *)v17;
      if ( v17 )
        (*(void (__fastcall **)(struct Rdp::Avenc::IMonitorContext *))(*(_QWORD *)v17 + 8LL))(v17);
      v24 = v39;
      *v23 = v39;
      v23[1] = v24;
      v23[2] = v24;
      *((_WORD *)v23 + 12) = 0;
      v39 = v35;
      v40 = (int)v44;
      v41 = v38[0];
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(
        v18,
        &v39,
        v23);
    }
    else
    {
      v22 = *((_QWORD *)v20 + 5);
      *((_QWORD *)v20 + 5) = v17;
      if ( v17 )
        (*(void (__fastcall **)(struct Rdp::Avenc::IMonitorContext *))(*(_QWORD *)v17 + 8LL))(v17);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v39 = "Create monitor context";
      v38[0] = "Rdp::Avenc::Umrdp::CUmrdpProcessor::CreateMonitor";
      LODWORD(v44) = 274;
      *(_QWORD *)v37 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800AC766,
        v15,
        (_DWORD)v16,
        (__int64)v37,
        (__int64)&v44,
        (__int64)v38,
        (__int64)&v39);
    }
    if ( v17 )
      v17 = (struct Rdp::Avenc::IMonitorContext *)((char *)v17 + 80);
    *a2 = v17;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v6 = 0;
    }
    v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v26 = GetCurrentThreadId();
      LOBYTE(v27) = v25;
      LOBYTE(v28) = v6;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v27,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v31,
        v33,
        17,
        &WPP_44e245a864023212cc554d824265b257_Traceguids,
        v26);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x119,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180011ed0  mov     [rsp+arg_0], rbx
0x180011ed5  mov     [rsp+arg_8], rdx
0x180011eda  push    rsi
0x180011edb  push    r12
0x180011edd  push    r13
0x180011edf  push    r14
0x180011ee1  push    r15
0x180011ee3  sub     rsp, 90h
0x180011eea  mov     r13, r8
0x180011eed  mov     r12, rdx
0x180011ef0  mov     r15, rcx
0x180011ef3  lea     rcx, WPP_GLOBAL_Control
0x180011efa  mov     rax, cs:WPP_GLOBAL_Control
0x180011f01  mov     esi, 1
0x180011f06  cmp     rax, rcx
0x180011f09  jz      short loc_180011F1C
0x180011f0b  test    [rax+1Ch], sil
0x180011f0f  jz      short loc_180011F1C
0x180011f11  cmp     byte ptr [rax+19h], 4
0x180011f15  jb      short loc_180011F1C
0x180011f17  mov     bl, sil
0x180011f1a  jmp     short loc_180011F1E
0x180011f1c  xor     bl, bl
0x180011f1e  lea     rax, WPP_RECORDER_INITIALIZED
0x180011f25  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180011f2c  setnz   r14b
0x180011f30  test    bl, bl
0x180011f32  jnz     short loc_180011F39
0x180011f34  test    r14b, r14b
0x180011f37  jz      short loc_180011F6F
0x180011f39  call    cs:__imp_GetCurrentThreadId
0x180011f3f  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180011f43  lea     rax, WPP_44e245a864023212cc554d824265b257_Traceguids
0x180011f4a  mov     [rsp+0B8h+MessageGuid], rax; MessageGuid
0x180011f4f  mov     word ptr [rsp+0B8h+var_88], 10h; char *
0x180011f56  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f5d  mov     r9, [rcx+28h]; int
0x180011f61  mov     r8b, r14b; int
0x180011f64  mov     dl, bl; int
0x180011f66  mov     rcx, [rcx+10h]; int
0x180011f6a  call    WPP_RECORDER_AND_TRACE_SF_D
0x180011f6f  mov     rcx, [rsp+0B8h]; this
0x180011f77  test    r12, r12
0x180011f7a  jz      loc_180012371
0x180011f80  cmp     byte ptr [r15+10h], 0
0x180011f85  setz    al
0x180011f88  mov     rcx, [rsp+0B8h]; this
0x180011f90  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180011f97  mov     qword ptr [rsp+0B8h+var_90], rdx; bool
0x180011f9c  mov     byte ptr [rsp+0B8h+var_98], al; int
0x180011fa0  mov     r9d, 8000FFFFh; char *
0x180011fa6  lea     r12, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180011fad  mov     r8, r12; unsigned int
0x180011fb0  mov     edx, 107h; void *
0x180011fb5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180011fba  mov     eax, cs:dword_1800C1058
0x180011fc0  cmp     eax, 4
0x180011fc3  jbe     loc_180012095
0x180011fc9  mov     rcx, cs:qword_1800C1070
0x180011fd0  mov     rax, cs:qword_1800C1068
0x180011fd7  mov     rdx, 470000000000h
0x180011fe1  test    rdx, rax
0x180011fe4  jz      loc_180012095
0x180011fea  mov     rax, rcx
0x180011fed  and     rax, rdx
0x180011ff0  cmp     rax, rcx
0x180011ff3  jnz     loc_180012095
0x180011ff9  mov     eax, [r15+74h]
0x180011ffd  mov     dword ptr [rsp+0B8h+arg_18], eax
0x180012004  lea     rbx, aCreateMonitorC; "Create monitor context"
0x18001200b  mov     [rsp+0B8h+var_68], rbx
0x180012010  lea     rax, xmmword_1800C21A0
0x180012017  mov     [rsp+0B8h+var_60], rax
0x18001201c  lea     rax, aRdpavenc; "RdpAvenc"
0x180012023  mov     qword ptr [rsp+0B8h+var_50], rax
0x180012028  mov     [rsp+0B8h+var_48], 1000000h
0x180012031  lea     rax, aCheckpoint; "Checkpoint"
0x180012038  mov     [rsp+0B8h+var_38], rax
0x180012040  lea     rax, [rsp+0B8h+arg_18]
0x180012048  mov     [rsp+0B8h+var_70], rax
0x18001204d  lea     rax, [rsp+0B8h+var_68]
0x180012052  mov     qword ptr [rsp+0B8h+var_78], rax
0x180012057  lea     rax, [rsp+0B8h+var_60]
0x18001205c  mov     [rsp+0B8h+MessageGuid], rax
0x180012061  lea     rax, [rsp+0B8h+var_50]
0x180012066  mov     [rsp+0B8h+var_88], rax
0x18001206b  lea     rax, [rsp+0B8h+var_48]
0x180012070  mov     qword ptr [rsp+0B8h+var_90], rax
0x180012075  lea     rax, [rsp+0B8h+var_38]
0x18001207d  mov     qword ptr [rsp+0B8h+var_98], rax
0x180012082  lea     rdx, dword_1800AC79C
0x180012089  lea     rcx, dword_1800C1058
0x180012090  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180012095  mov     [rsp+0B8h+var_98], 10Eh; unsigned int
0x18001209d  mov     r9, r12; char *
0x1800120a0  lea     r8, aRdpAvencUmrdpC_22; "Rdp::Avenc::Umrdp::CUmrdpProcessor::Cre"...
0x1800120a7  lea     rdx, aMonitorcreate; "MonitorCreate"
0x1800120ae  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800120b5  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800120ba  mov     ecx, 0B0h; Size
0x1800120bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800120c4  mov     [rsp+0B8h+arg_18], rax
0x1800120cc  lea     rdx, [r15-50h]; struct Rdp::Avenc::Umrdp::CUmrdpProcessor *
0x1800120d0  mov     r8, r13; struct IPropertyStore *
0x1800120d3  mov     rcx, rax; this
0x1800120d6  call    ??0CMonitorContext@Umrdp@Avenc@Rdp@@QEAA@PEAVCUmrdpProcessor@123@PEAUIPropertyStore@@@Z; Rdp::Avenc::Umrdp::CMonitorContext::CMonitorContext(Rdp::Avenc::Umrdp::CUmrdpProcessor *,IPropertyStore *)
0x1800120db  mov     rbx, rax
0x1800120de  mov     qword ptr [rsp+0B8h+var_50], rax
0x1800120e3  test    rax, rax
0x1800120e6  jz      short loc_1800120F8
0x1800120e8  mov     rax, [rax]
0x1800120eb  mov     rcx, rbx
0x1800120ee  mov     rax, [rax+8]
0x1800120f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120f7  nop
0x1800120f8  lea     r13, [r15+28h]
0x1800120fc  test    rbx, rbx
0x1800120ff  jz      short loc_180012107
0x180012101  lea     r15, [rbx+50h]
0x180012105  jmp     short loc_18001210A
0x180012107  xor     r15d, r15d
0x18001210a  mov     rax, [r13+0]
0x18001210e  mov     [rsp+0B8h+var_38], rax
0x180012116  mov     rdx, [rax+8]
0x18001211a  mov     [rsp+0B8h+var_68], rdx
0x18001211f  mov     dword ptr [rsp+0B8h+arg_18], 0
0x18001212a  xor     ecx, ecx
0x18001212c  mov     [rsp+0B8h+var_48], rcx
0x180012131  mov     rcx, rax
0x180012134  mov     rax, rdx
0x180012137  cmp     byte ptr [rdx+19h], 0
0x18001213b  jnz     short loc_18001216C
0x18001213d  mov     [rsp+0B8h+var_68], rax
0x180012142  cmp     [rax+20h], r15
0x180012146  jnb     short loc_180012159
0x180012148  mov     dword ptr [rsp+0B8h+arg_18], 0
0x180012153  mov     rax, [rax+10h]
0x180012157  jmp     short loc_180012166
0x180012159  mov     dword ptr [rsp+0B8h+arg_18], esi
0x180012160  mov     rcx, rax
0x180012163  mov     rax, [rax]
0x180012166  cmp     byte ptr [rax+19h], 0
0x18001216a  jz      short loc_18001213D
0x18001216c  cmp     byte ptr [rcx+19h], 0
0x180012170  jnz     short loc_1800121AE
0x180012172  cmp     r15, [rcx+20h]
0x180012176  jb      short loc_1800121AE
0x180012178  mov     r14, [rcx+28h]
0x18001217c  mov     [rcx+28h], rbx
0x180012180  test    rbx, rbx
0x180012183  jz      short loc_180012194
0x180012185  mov     rax, [rbx]
0x180012188  mov     rcx, rbx
0x18001218b  mov     rax, [rax+8]
0x18001218f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012194  test    r14, r14
0x180012197  jz      short loc_1800121A9
0x180012199  mov     rax, [r14]
0x18001219c  mov     rcx, r14
0x18001219f  mov     rax, [rax+10h]
0x1800121a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121a8  nop
0x1800121a9  jmp     loc_18001224E
0x1800121ae  mov     rax, 555555555555555h
0x1800121b8  cmp     [r13+8], rax
0x1800121bc  jz      loc_180012389
0x1800121c2  mov     [rsp+0B8h+var_60], r13
0x1800121c7  mov     [rsp+0B8h+var_58], 0
0x1800121d0  mov     ecx, 30h ; '0'; Size
0x1800121d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800121da  mov     r14, rax
0x1800121dd  mov     [rax+20h], r15
0x1800121e1  mov     [rax+28h], rbx
0x1800121e5  test    rbx, rbx
0x1800121e8  jz      short loc_1800121FA
0x1800121ea  mov     rcx, [rbx]
0x1800121ed  mov     rax, [rcx+8]
0x1800121f1  mov     rcx, rbx
0x1800121f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121f9  nop
0x1800121fa  mov     rax, [rsp+0B8h+var_38]
0x180012202  mov     [r14], rax
0x180012205  mov     [r14+8], rax
0x180012209  mov     [r14+10h], rax
0x18001220d  mov     word ptr [r14+18h], 0
0x180012214  mov     rax, [rsp+0B8h+var_68]
0x180012219  mov     [rsp+0B8h+var_38], rax
0x180012221  mov     eax, dword ptr [rsp+0B8h+arg_18]
0x180012228  mov     [rsp+0B8h+var_30], eax
0x18001222f  mov     rax, [rsp+0B8h+var_48]
0x180012234  mov     [rsp+0B8h+var_2C], eax
0x18001223b  mov     r8, r14
0x18001223e  lea     rdx, [rsp+0B8h+var_38]
0x180012246  mov     rcx, r13
0x180012249  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> *>,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> * const)
0x18001224e  mov     eax, cs:dword_1800C1058
0x180012254  cmp     eax, 4
0x180012257  jbe     short loc_1800122C5
0x180012259  lea     rax, aCreateMonitorC; "Create monitor context"
0x180012260  mov     [rsp+0B8h+var_38], rax
0x180012268  lea     rax, aRdpAvencUmrdpC_22; "Rdp::Avenc::Umrdp::CUmrdpProcessor::Cre"...
0x18001226f  mov     [rsp+0B8h+var_48], rax
0x180012274  mov     dword ptr [rsp+0B8h+arg_18], 112h
0x18001227f  mov     qword ptr [rsp+0B8h+var_50], r12
0x180012284  lea     rax, [rsp+0B8h+var_38]
0x18001228c  mov     [rsp+0B8h+MessageGuid], rax
0x180012291  lea     rax, [rsp+0B8h+var_48]
0x180012296  mov     [rsp+0B8h+var_88], rax
0x18001229b  lea     rax, [rsp+0B8h+arg_18]
0x1800122a3  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x1800122a8  lea     rax, [rsp+0B8h+var_50]
0x1800122ad  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x1800122b2  lea     rdx, word_1800AC766
0x1800122b9  lea     rcx, dword_1800C1058
0x1800122c0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800122c5  test    rbx, rbx
0x1800122c8  jz      short loc_1800122CE
0x1800122ca  add     rbx, 50h ; 'P'
0x1800122ce  mov     rax, [rsp+0B8h+arg_8]
0x1800122d6  mov     [rax], rbx
0x1800122d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800122e0  lea     rcx, WPP_GLOBAL_Control
0x1800122e7  cmp     rax, rcx
0x1800122ea  jz      short loc_1800122F8
0x1800122ec  test    [rax+1Ch], sil
0x1800122f0  jz      short loc_1800122F8
0x1800122f2  cmp     byte ptr [rax+19h], 4
0x1800122f6  jnb     short loc_1800122FB
0x1800122f8  xor     sil, sil
0x1800122fb  lea     rax, WPP_RECORDER_INITIALIZED
0x180012302  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180012309  setnz   bl
0x18001230c  test    sil, sil
0x18001230f  jnz     short loc_180012315
0x180012311  test    bl, bl
0x180012313  jz      short loc_18001234D
0x180012315  call    cs:__imp_GetCurrentThreadId
0x18001231b  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001231f  lea     rax, WPP_44e245a864023212cc554d824265b257_Traceguids
0x180012326  mov     [rsp+0B8h+MessageGuid], rax; MessageGuid
0x18001232b  mov     word ptr [rsp+0B8h+var_88], 11h; __int16
0x180012332  mov     rcx, cs:WPP_GLOBAL_Control
0x180012339  mov     r9, [rcx+28h]; int
0x18001233d  mov     r8b, bl; int
0x180012340  mov     dl, sil; int
0x180012343  mov     rcx, [rcx+10h]; int
0x180012347  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001234c  nop
0x18001234d  xor     eax, eax
0x18001234f  jmp     short loc_180012358
0x180012351  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x180012358  mov     rbx, [rsp+0B8h+arg_0]
0x180012360  add     rsp, 90h
0x180012367  pop     r15
0x180012369  pop     r14
0x18001236b  pop     r13
0x18001236d  pop     r12
0x18001236f  pop     rsi
0x180012370  retn
0x180012371  mov     r9d, 80004003h; char *
0x180012377  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001237e  mov     edx, 106h; void *
0x180012383  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012389  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
