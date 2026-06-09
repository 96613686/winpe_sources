# Rdp::Avenc::RdpProg::CRdpProgProcessor::Start(IUnknown *)

- ea: `0x180064900`
- end: `0x180064d89`
- name: `?Start@CRdpProgProcessor@RdpProg@Avenc@Rdp@@UEAAJPEAUIUnknown@@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(Rdp::Avenc::RdpProg::CRdpProgProcessor *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x1800065a4`
- `0x18000e848`
- `0x18000ec04`
- `0x180010bc8`
- `0x180011490`
- `0x180012580`
- `0x180012618`
- `0x1800126b0`
- `0x1800153f8`
- `0x180015480`
- `0x180064900`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180064cb6`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180064cb6`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180064c96`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180064c96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064966`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064d14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064966`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064d14`

## string_xrefs

- `0x1800649c3`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x180064a88`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x180064d63`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgProcessor::Start(
        Rdp::Avenc::RdpProg::CRdpProgProcessor *this,
        struct IUnknown *a2)
{
  char v4; // di
  bool v5; // bl
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  char *v10; // rbx
  Rdp::Utils::Props **v11; // rsi
  int v12; // eax
  struct _GUID *v13; // r9
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int Guid; // eax
  unsigned int *v18; // r9
  unsigned int UInt32; // eax
  struct IPropertyStore *v20; // rdx
  struct _LUID *v21; // r9
  unsigned int Luid; // eax
  int v23; // r8d
  int v24; // r9d
  _QWORD *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  const char *v28; // r9
  int v29; // ecx
  int v30; // eax
  bool v31; // bl
  char v32; // al
  int v33; // r8d
  int v34; // edx
  __int64 result; // rax
  int v36; // [rsp+20h] [rbp-98h]
  int v37; // [rsp+28h] [rbp-90h]
  char *v38; // [rsp+28h] [rbp-90h]
  char *v39; // [rsp+28h] [rbp-90h]
  const char *v40; // [rsp+60h] [rbp-58h] BYREF
  __int64 v41; // [rsp+68h] [rbp-50h] BYREF
  struct _tagpropertykey v42; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  _QWORD *v44; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v45; // [rsp+C8h] [rbp+10h] BYREF
  const char *v46; // [rsp+D0h] [rbp+18h] BYREF
  int *v47; // [rsp+D8h] [rbp+20h] BYREF

  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v36,
      v37,
      10,
      &WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids,
      CurrentThreadId);
  }
  v10 = (char *)this - 80;
  v11 = (Rdp::Utils::Props **)((char *)this + 32);
  try
  {
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      196,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      2147549183LL);
    v44 = 0;
    v12 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD **))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a,
            &v44);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v12,
        (_DWORD)this - 80 + 112);
    v14 = v44;
    v15 = 0;
    v44 = 0;
    v16 = *((_QWORD *)v10 + 15);
    *((_QWORD *)v10 + 15) = v14;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v15 = v44;
    }
    if ( v15 )
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    v42.fmtid = 0;
    Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(*v11, (struct IPropertyStore *)&PKEY_Activity_Id, &v42, v13);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Guid,
      (int)"Failed to retrieve PKEY_Activity_Id property",
      "PropertyStore is not initialized");
    *(GUID *)&xmmword_1800C21A0 = v42.fmtid;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *v11,
               (struct IPropertyStore *)&PKEY_Session_Id,
               (const struct _tagpropertykey *)v10 + 8,
               v18);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_Session_Id property",
      v38);
    Luid = Rdp::Utils::Props::IPropertyStore_GetLuid(*v11, v20, (const struct _tagpropertykey *)(v10 + 152), v21);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Luid,
      (int)"Failed to retrieve PKEY_Terminal_Luid property",
      v39);
    v10[256] = 1;
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v45 = *((_QWORD *)this + 9);
      LODWORD(v44) = *((_DWORD *)this + 20);
      v46 = "Start RdpProg processor";
      v47 = &xmmword_1800C21A0;
      v40 = "RdpAvenc";
      v41 = 0x1000000;
      *(_QWORD *)&v42.fmtid.Data1 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&dword_1800B4F0C,
        v23,
        v24,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v44,
        (__int64)&v45);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"RdpProgProcessorStart",
      "Rdp::Avenc::RdpProg::CRdpProgProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
      0x3Bu);
    v10[496] = 1;
    v25 = operator new(0x18u);
    *v25 = v10;
    v25[1] = Rdp::Avenc::RdpProg::CRdpProgProcessor::PacketWriterThreadProc;
    *((_DWORD *)v25 + 4) = 0;
    *((_DWORD *)v25 + 5) = *(_DWORD *)&v42.fmtid.Data4[4];
    v44 = v25;
    v26 = _o__beginthreadex(
            0,
            0,
            std::thread::_Invoke<std::tuple<void (Rdp::Avenc::RdpProg::CRdpProgProcessor::*)(void),Rdp::Avenc::RdpProg::CRdpProgProcessor *>,0,1>,
            v25);
    *(_QWORD *)&v42.fmtid.Data1 = v26;
    if ( !v26 )
    {
      *(_DWORD *)v42.fmtid.Data4 = 0;
      std::_Throw_Cpp_error(6);
    }
    if ( *((_DWORD *)v10 + 84) )
    {
      _o_terminate(v27, v26);
      __debugbreak();
    }
    v29 = *(_DWORD *)v42.fmtid.Data4;
    v30 = *(_DWORD *)&v42.fmtid.Data4[4];
    *((_QWORD *)v10 + 41) = v26;
    *((_DWORD *)v10 + 84) = v29;
    *((_DWORD *)v10 + 85) = v30;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v31 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = GetCurrentThreadId();
      LOBYTE(v33) = v31;
      LOBYTE(v34) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v34,
        v33,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        0,
        (int)v42.fmtid.Data4,
        11,
        &WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids,
        v32);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x48,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
                           v28);
  }
  return result;
}

```

## disassembly

```asm
0x180064900  push    rbx
0x180064902  push    rsi
0x180064903  push    rdi
0x180064904  push    r13
0x180064906  push    r14
0x180064908  push    r15
0x18006490a  sub     rsp, 88h
0x180064911  mov     r14, rdx
0x180064914  mov     r13, rcx
0x180064917  lea     rcx, WPP_GLOBAL_Control
0x18006491e  mov     rax, cs:WPP_GLOBAL_Control
0x180064925  mov     edi, 1
0x18006492a  cmp     rax, rcx
0x18006492d  jz      short loc_180064940
0x18006492f  test    [rax+1Ch], dil
0x180064933  jz      short loc_180064940
0x180064935  cmp     byte ptr [rax+19h], 4
0x180064939  jb      short loc_180064940
0x18006493b  mov     bl, dil
0x18006493e  jmp     short loc_180064942
0x180064940  xor     bl, bl
0x180064942  lea     rax, WPP_RECORDER_INITIALIZED
0x180064949  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064950  setnz   sil
0x180064954  test    bl, bl
0x180064956  jnz     short loc_180064966
0x180064958  test    sil, sil
0x18006495b  jnz     short loc_180064966
0x18006495d  lea     r15, WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids
0x180064964  jmp     short loc_18006499C
0x180064966  call    cs:__imp_GetCurrentThreadId
0x18006496c  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180064970  lea     r15, WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids
0x180064977  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18006497c  mov     [rsp+0B8h+var_88], 0Ah; __int16
0x180064983  mov     rcx, cs:WPP_GLOBAL_Control
0x18006498a  mov     r9, [rcx+28h]; int
0x18006498e  mov     r8b, sil; int
0x180064991  mov     dl, bl; int
0x180064993  mov     rcx, [rcx+10h]; int
0x180064997  call    WPP_RECORDER_AND_TRACE_SF_D
0x18006499c  lea     rbx, [r13-50h]
0x1800649a0  lea     rsi, [rbx+70h]
0x1800649a4  mov     rcx, [rsp+0B8h]
0x1800649ac  lea     rax, aPropertystoreI; "PropertyStore is not initialized"
0x1800649b3  mov     [rsp+0B8h+var_90], rax; char *
0x1800649b8  mov     qword ptr [rsp+0B8h+var_98], rsi; int
0x1800649bd  mov     r9d, 8000FFFFh
0x1800649c3  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800649ca  mov     edx, 0C4h
0x1800649cf  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x1800649d4  mov     [rsp+0B8h+arg_0], 0
0x1800649e0  mov     rax, [r14]
0x1800649e3  lea     r8, [rsp+0B8h+arg_0]
0x1800649eb  lea     rdx, _GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a
0x1800649f2  mov     rcx, r14
0x1800649f5  mov     rax, [rax]
0x1800649f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800649fd  mov     rcx, [rsp+0B8h]; this
0x180064a05  test    eax, eax
0x180064a07  js      loc_180064D60
0x180064a0d  mov     rax, [rsp+0B8h+arg_0]
0x180064a15  xor     ecx, ecx
0x180064a17  mov     [rsp+0B8h+arg_0], rcx
0x180064a1f  mov     rdx, [rbx+78h]
0x180064a23  mov     [rbx+78h], rax
0x180064a27  test    rdx, rdx
0x180064a2a  jz      short loc_180064A43
0x180064a2c  mov     rax, [rdx]
0x180064a2f  mov     rcx, rdx
0x180064a32  mov     rax, [rax+10h]
0x180064a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a3b  mov     rcx, [rsp+0B8h+arg_0]
0x180064a43  test    rcx, rcx
0x180064a46  jz      short loc_180064A55
0x180064a48  mov     rax, [rcx]
0x180064a4b  mov     rax, [rax+10h]
0x180064a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a54  nop
0x180064a55  xorps   xmm0, xmm0
0x180064a58  movups  xmmword ptr [rsp+0B8h+var_48.fmtid.Data1], xmm0
0x180064a5d  lea     r8, [rsp+0B8h+var_48]; struct _tagpropertykey *
0x180064a62  lea     rdx, PKEY_Activity_Id; struct IPropertyStore *
0x180064a69  mov     rcx, [rsi]; this
0x180064a6c  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x180064a71  mov     rcx, [rsp+0B8h]; this
0x180064a79  lea     rdx, aFailedToRetrie_17; "Failed to retrieve PKEY_Activity_Id pro"...
0x180064a80  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180064a85  mov     r9d, eax; char *
0x180064a88  lea     r14, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180064a8f  mov     r8, r14; unsigned int
0x180064a92  mov     edx, 0D1h; void *
0x180064a97  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180064a9c  movups  xmm0, xmmword ptr [rsp+0B8h+var_48.fmtid.Data1]
0x180064aa1  movdqu  cs:xmmword_1800C21A0, xmm0
0x180064aa9  lea     r8, [rbx+0A0h]; struct _tagpropertykey *
0x180064ab0  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x180064ab7  mov     rcx, [rsi]; this
0x180064aba  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180064abf  mov     rcx, [rsp+0B8h]; this
0x180064ac7  lea     rdx, aFailedToRetrie_19; "Failed to retrieve PKEY_Session_Id prop"...
0x180064ace  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180064ad3  mov     r9d, eax; char *
0x180064ad6  mov     r8, r14; unsigned int
0x180064ad9  mov     edx, 0DDh; void *
0x180064ade  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180064ae3  lea     r8, [rbx+98h]; struct _tagpropertykey *
0x180064aea  mov     rcx, [rsi]; this
0x180064aed  call    ?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)
0x180064af2  mov     rcx, [rsp+0B8h]; this
0x180064afa  lea     rdx, aFailedToRetrie_12; "Failed to retrieve PKEY_Terminal_Luid p"...
0x180064b01  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180064b06  mov     r9d, eax; char *
0x180064b09  mov     r8, r14; unsigned int
0x180064b0c  mov     edx, 0E7h; void *
0x180064b11  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180064b16  mov     [rbx+100h], dil
0x180064b1d  mov     eax, cs:dword_1800C1058
0x180064b23  cmp     eax, 4
0x180064b26  jbe     loc_180064C17
0x180064b2c  mov     rcx, cs:qword_1800C1070
0x180064b33  mov     rax, cs:qword_1800C1068
0x180064b3a  mov     rdx, 470000000000h
0x180064b44  test    rdx, rax
0x180064b47  jz      loc_180064C17
0x180064b4d  mov     rax, rcx
0x180064b50  and     rax, rdx
0x180064b53  cmp     rax, rcx
0x180064b56  jnz     loc_180064C17
0x180064b5c  mov     rax, [r13+48h]
0x180064b60  mov     [rsp+0B8h+arg_8], rax
0x180064b68  mov     eax, [r13+50h]
0x180064b6c  mov     dword ptr [rsp+0B8h+arg_0], eax
0x180064b73  lea     rax, aStartRdpprogPr; "Start RdpProg processor"
0x180064b7a  mov     [rsp+0B8h+arg_10], rax
0x180064b82  lea     rax, xmmword_1800C21A0
0x180064b89  mov     [rsp+0B8h+arg_18], rax
0x180064b91  lea     rax, aRdpavenc; "RdpAvenc"
0x180064b98  mov     [rsp+0B8h+var_58], rax
0x180064b9d  mov     [rsp+0B8h+var_50], 1000000h
0x180064ba6  lea     rax, aCheckpoint; "Checkpoint"
0x180064bad  mov     qword ptr [rsp+0B8h+var_48.fmtid.Data1], rax
0x180064bb2  lea     rax, [rsp+0B8h+arg_8]
0x180064bba  mov     [rsp+0B8h+var_68], rax
0x180064bbf  lea     rax, [rsp+0B8h+arg_0]
0x180064bc7  mov     [rsp+0B8h+var_70], rax
0x180064bcc  lea     rax, [rsp+0B8h+arg_10]
0x180064bd4  mov     qword ptr [rsp+0B8h+var_78], rax
0x180064bd9  lea     rax, [rsp+0B8h+arg_18]
0x180064be1  mov     [rsp+0B8h+MessageGuid], rax
0x180064be6  lea     rax, [rsp+0B8h+var_58]
0x180064beb  mov     qword ptr [rsp+0B8h+var_88], rax
0x180064bf0  lea     rax, [rsp+0B8h+var_50]
0x180064bf5  mov     [rsp+0B8h+var_90], rax
0x180064bfa  lea     rax, [rsp+0B8h+var_48]
0x180064bff  mov     qword ptr [rsp+0B8h+var_98], rax
0x180064c04  lea     rdx, dword_1800B4F0C
0x180064c0b  lea     rcx, dword_1800C1058
0x180064c12  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180064c17  mov     [rsp+0B8h+var_98], 3Bh ; ';'; unsigned int
0x180064c1f  lea     r9, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180064c26  lea     r8, aRdpAvencRdppro_0; "Rdp::Avenc::RdpProg::CRdpProgProcessor:"...
0x180064c2d  lea     rdx, aRdpprogprocess; "RdpProgProcessorStart"
0x180064c34  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180064c3b  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180064c40  mov     eax, edi
0x180064c42  xchg    al, [rbx+1F0h]
0x180064c48  mov     ecx, 18h; Size
0x180064c4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064c52  mov     [rax], rbx
0x180064c55  lea     rcx, ?PacketWriterThreadProc@CRdpProgProcessor@RdpProg@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::RdpProg::CRdpProgProcessor::PacketWriterThreadProc(void)
0x180064c5c  mov     [rax+8], rcx
0x180064c60  mov     dword ptr [rax+10h], 0
0x180064c67  mov     ecx, dword ptr [rsp+0B8h+var_48.fmtid.Data4+4]
0x180064c6b  mov     [rax+14h], ecx
0x180064c6e  mov     [rsp+0B8h+arg_0], rax
0x180064c76  lea     rcx, [rsp+0B8h+var_48.fmtid.Data4]
0x180064c7b  mov     [rsp+0B8h+var_90], rcx; int
0x180064c80  mov     [rsp+0B8h+var_98], 0; int
0x180064c88  mov     r9, rax
0x180064c8b  lea     r8, ??$_Invoke@V?$tuple@P8CRdpProgProcessor@RdpProg@Avenc@Rdp@@EAAXXZPEAV1234@@std@@$0A@$00@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (Rdp::Avenc::RdpProg::CRdpProgProcessor::*)(void),Rdp::Avenc::RdpProg::CRdpProgProcessor *>,0,1>(void *)
0x180064c92  xor     edx, edx
0x180064c94  xor     ecx, ecx
0x180064c96  call    cs:__imp__o__beginthreadex
0x180064c9c  mov     rdx, rax
0x180064c9f  mov     qword ptr [rsp+0B8h+var_48.fmtid.Data1], rax
0x180064ca4  test    rax, rax
0x180064ca7  jz      loc_180064D75
0x180064cad  cmp     dword ptr [rbx+150h], 0
0x180064cb4  jz      short loc_180064CBD
0x180064cb6  call    cs:__imp__o_terminate
0x180064cbc  int     3; Trap to Debugger
0x180064cbd  mov     ecx, dword ptr [rsp+0B8h+var_48.fmtid.Data4]
0x180064cc1  mov     eax, dword ptr [rsp+0B8h+var_48.fmtid.Data4+4]
0x180064cc5  mov     [rbx+148h], rdx
0x180064ccc  mov     [rbx+150h], ecx
0x180064cd2  mov     [rbx+154h], eax
0x180064cd8  mov     rax, cs:WPP_GLOBAL_Control
0x180064cdf  lea     rcx, WPP_GLOBAL_Control
0x180064ce6  cmp     rax, rcx
0x180064ce9  jz      short loc_180064CF7
0x180064ceb  test    [rax+1Ch], dil
0x180064cef  jz      short loc_180064CF7
0x180064cf1  cmp     byte ptr [rax+19h], 4
0x180064cf5  jnb     short loc_180064CFA
0x180064cf7  xor     dil, dil
0x180064cfa  lea     rax, WPP_RECORDER_INITIALIZED
0x180064d01  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180064d08  setnz   bl
0x180064d0b  test    dil, dil
0x180064d0e  jnz     short loc_180064D14
0x180064d10  test    bl, bl
0x180064d12  jz      short loc_180064D44
0x180064d14  call    cs:__imp_GetCurrentThreadId
0x180064d1a  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180064d1e  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x180064d23  mov     [rsp+0B8h+var_88], 0Bh; __int16
0x180064d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180064d31  mov     r9, [rcx+28h]; int
0x180064d35  mov     r8b, bl; int
0x180064d38  mov     dl, dil; int
0x180064d3b  mov     rcx, [rcx+10h]; int
0x180064d3f  call    WPP_RECORDER_AND_TRACE_SF_D
0x180064d44  xor     eax, eax
0x180064d46  jmp     short loc_180064D4F
0x180064d48  mov     eax, dword ptr [rsp+0B8h+arg_0]
0x180064d4f  add     rsp, 88h
0x180064d56  pop     r15
0x180064d58  pop     r14
0x180064d5a  pop     r13
0x180064d5c  pop     rdi
0x180064d5d  pop     rsi
0x180064d5e  pop     rbx
0x180064d5f  retn
0x180064d60  mov     r9d, eax; char *
0x180064d63  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180064d6a  mov     edx, 1CBEh; void *
0x180064d6f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180064d75  mov     dword ptr [rsp+0B8h+var_48.fmtid.Data4], 0
0x180064d7d  mov     ecx, 6; int
0x180064d82  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
