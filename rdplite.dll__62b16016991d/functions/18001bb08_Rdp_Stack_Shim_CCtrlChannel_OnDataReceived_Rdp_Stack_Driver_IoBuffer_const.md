# Rdp::Stack::Shim::CCtrlChannel::OnDataReceived(Rdp::Stack::Driver::IoBuffer const *)

- ea: `0x18001bb08`
- end: `0x18001c205`
- name: `?OnDataReceived@CCtrlChannel@Shim@Stack@Rdp@@AEAAXPEBUIoBuffer@Driver@34@@Z`
- size: `1789`
- prototype: `void __fastcall(Rdp::Stack::Shim::CCtrlChannel *__hidden this, const struct Rdp::Stack::Driver::IoBuffer *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b698`

## callees

- `0x18000208c`
- `0x180007b28`
- `0x18000cea4`
- `0x1800109dc`
- `0x1800192c4`
- `0x18001bb08`
- `0x18001ce84`
- `0x18001cf84`
- `0x18001e010`
- `0x18001ef38`

## string_xrefs

- `0x18001c09d`: `Buffer size is too small to cast to RDPCTRL_SRC_CREATE_FRAME_PROCESSOR`
- `0x18001c165`: `Dropping CreateFrameProcessor request for monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x18001bb9e`: `ResourceUpdate`
- `0x18001bbfb`: `Buffer size is too small to cast to RDPCTRL_SRC_RESOURCE_UPDATE`
- `0x18001bd08`: `Dropping ResourceUpdate request for monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x18001bd32`: `ResourceUpdate - done`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CCtrlChannel::OnDataReceived(
        Rdp::Stack::Shim::CCtrlChannel *this,
        const struct Rdp::Stack::Driver::IoBuffer *a2)
{
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // r14
  const unsigned __int8 *v7; // rax
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // r14
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // r15
  Rdp::Stack::Shim::CMonitorShim **v14; // rcx
  __int64 v15; // r14
  int v16; // r8d
  int v17; // r9d
  char *v18; // [rsp+28h] [rbp-41h]
  char *v19; // [rsp+28h] [rbp-41h]
  char *v20; // [rsp+28h] [rbp-41h]
  char *v21; // [rsp+28h] [rbp-41h]
  char *v22; // [rsp+30h] [rbp-39h]
  char *v23; // [rsp+30h] [rbp-39h]
  char *v24; // [rsp+30h] [rbp-39h]
  char *v25; // [rsp+30h] [rbp-39h]
  char *v26; // [rsp+30h] [rbp-39h]
  char *v27; // [rsp+30h] [rbp-39h]
  struct tagRECT *v28; // [rsp+38h] [rbp-31h]
  const char *v29; // [rsp+80h] [rbp+17h] BYREF
  _QWORD v30[7]; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  Rdp::Stack::Shim::CMonitorShim *v32; // [rsp+D8h] [rbp+6Fh] BYREF
  Rdp::Stack::Shim::CMonitorShim *v33; // [rsp+E0h] [rbp+77h] BYREF
  const char *v34; // [rsp+E8h] [rbp+7Fh] BYREF

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xF6,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
    (const char *)0x8007007ALL,
    *((_DWORD *)a2 + 16) < 0xCu,
    (bool)"Buffer size is too small to cast to RDPCTRL_HEADER",
    v22);
  switch ( *(_DWORD *)(*((_QWORD *)a2 + 5) + 8LL) )
  {
    case 1:
      if ( (unsigned int)dword_18003C058 > 5 )
      {
        v33 = (Rdp::Stack::Shim::CMonitorShim *)"StartFrameProcessor";
        v34 = "Rdp::Stack::Shim::CCtrlChannel::OnDataReceived";
        LODWORD(v32) = 257;
        v30[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)word_180035AFA,
          v4,
          v5,
          (__int64)v30,
          (__int64)&v32,
          (__int64)&v34,
          (__int64)&v33);
      }
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
        (const char *)0x8007007ALL,
        *((_DWORD *)a2 + 16) < 0x28u,
        (bool)"Buffer size is too small to cast to RDPCTRL_SRC_CREATE_FRAME_PROCESSOR",
        v23);
      v15 = *((_QWORD *)a2 + 5);
      Rdp::Stack::Shim::CAdapterShim::FindMonitor(*((_QWORD *)this + 64), &v33, v15 + 12);
      if ( v33 )
      {
        Rdp::Stack::Shim::CMonitorShim::CreateFrameProcessor(v33, *(_QWORD *)(v15 + 28), *(_DWORD *)(v15 + 36) != 0);
      }
      else
      {
        LODWORD(v28) = *(unsigned __int16 *)(v15 + 18);
        LODWORD(v27) = *(unsigned __int16 *)(v15 + 16);
        LODWORD(v21) = *(_DWORD *)(v15 + 12);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
          (const char *)0x80070490LL,
          (int)"Dropping CreateFrameProcessor request for monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
          v21,
          v27,
          v28,
          *(unsigned __int8 *)(v15 + 20),
          *(unsigned __int8 *)(v15 + 21),
          *(unsigned __int8 *)(v15 + 22),
          *(unsigned __int8 *)(v15 + 23),
          *(unsigned __int8 *)(v15 + 24),
          *(unsigned __int8 *)(v15 + 25),
          *(unsigned __int8 *)(v15 + 26),
          *(unsigned __int8 *)(v15 + 27));
      }
      if ( (unsigned int)dword_18003C058 > 5 )
      {
        v34 = "StartFrameProcessor - done";
        v30[0] = "Rdp::Stack::Shim::CCtrlChannel::OnDataReceived";
        LODWORD(v32) = 283;
        v29 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_180035ABD,
          v16,
          v17,
          (__int64)&v29,
          (__int64)&v32,
          (__int64)v30,
          (__int64)&v34);
      }
      break;
    case 2:
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x125,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
        (const char *)0x8007007ALL,
        *((_DWORD *)a2 + 16) < 0x24u,
        (bool)"Buffer size is too small to cast to RDPCTRL_SRC_STOP_FRAME_PROCESSOR",
        v23);
      v13 = *((_QWORD *)a2 + 5);
      Rdp::Stack::Shim::CAdapterShim::FindMonitor(*((_QWORD *)this + 64), &v32, v13 + 12);
      if ( v32 )
      {
        Rdp::Stack::Shim::CMonitorShim::StopFrameProcessor(v32, *(_QWORD *)(v13 + 28));
      }
      else
      {
        LODWORD(v26) = *(unsigned __int16 *)(v13 + 16);
        LODWORD(v20) = *(_DWORD *)(v13 + 12);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x133,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
          (const char *)0x80070490LL,
          (int)"Dropping StopFrameProcessor request for monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
          v20,
          v26,
          *(unsigned __int16 *)(v13 + 18),
          *(unsigned __int8 *)(v13 + 20),
          *(unsigned __int8 *)(v13 + 21),
          *(unsigned __int8 *)(v13 + 22),
          *(unsigned __int8 *)(v13 + 23),
          *(unsigned __int8 *)(v13 + 24),
          *(unsigned __int8 *)(v13 + 25),
          *(unsigned __int8 *)(v13 + 26),
          *(unsigned __int8 *)(v13 + 27));
      }
      v14 = &v32;
      goto LABEL_35;
    case 3:
      if ( (unsigned int)dword_18003C058 > 5 )
      {
        v33 = (Rdp::Stack::Shim::CMonitorShim *)"SetRenderDevice";
        v34 = "Rdp::Stack::Shim::CCtrlChannel::OnDataReceived";
        LODWORD(v32) = 316;
        v30[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)qword_180035A80,
          v4,
          v5,
          (__int64)v30,
          (__int64)&v32,
          (__int64)&v34,
          (__int64)&v33);
      }
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x141,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
        (const char *)0x8007007ALL,
        *((_DWORD *)a2 + 16) < 0x2Cu,
        (bool)"Buffer size is too small to cast to RDPCTRL_SRC_SET_RENDER_DEVICE",
        v23);
      v10 = *((_QWORD *)a2 + 5);
      Rdp::Stack::Shim::CAdapterShim::FindMonitor(*((_QWORD *)this + 64), &v33, v10 + 12);
      if ( v33 )
      {
        Rdp::Stack::Shim::CMonitorShim::SetRenderDevice(v33, *(_QWORD *)(v10 + 28), (const struct _LUID *)(v10 + 36));
      }
      else
      {
        LODWORD(v28) = *(unsigned __int16 *)(v10 + 18);
        LODWORD(v25) = *(unsigned __int16 *)(v10 + 16);
        LODWORD(v19) = *(_DWORD *)(v10 + 12);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x14F,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
          (const char *)0x80070490LL,
          (int)"Dropping SetRenderDevice request for monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
          v19,
          v25,
          v28,
          *(unsigned __int8 *)(v10 + 20),
          *(unsigned __int8 *)(v10 + 21),
          *(unsigned __int8 *)(v10 + 22),
          *(unsigned __int8 *)(v10 + 23),
          *(unsigned __int8 *)(v10 + 24),
          *(unsigned __int8 *)(v10 + 25),
          *(unsigned __int8 *)(v10 + 26),
          *(unsigned __int8 *)(v10 + 27));
      }
      if ( (unsigned int)dword_18003C058 > 5 )
      {
        v34 = "SetRenderDeviceDone";
        v30[0] = "Rdp::Stack::Shim::CCtrlChannel::OnDataReceived";
        LODWORD(v32) = 340;
        v29 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_180035A43,
          v11,
          v12,
          (__int64)&v29,
          (__int64)&v32,
          (__int64)v30,
          (__int64)&v34);
      }
      break;
    case 4:
      if ( (unsigned int)dword_18003C058 > 5 )
      {
        v33 = (Rdp::Stack::Shim::CMonitorShim *)"ResourceUpdate";
        v34 = "Rdp::Stack::Shim::CCtrlChannel::OnDataReceived";
        LODWORD(v32) = 349;
        v29 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)&word_180035A06,
          v4,
          v5,
          (__int64)&v29,
          (__int64)&v32,
          (__int64)&v34,
          (__int64)&v33);
      }
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
        (const char *)0x8007007ALL,
        *((_DWORD *)a2 + 16) < 0x64u,
        (bool)"Buffer size is too small to cast to RDPCTRL_SRC_RESOURCE_UPDATE",
        v23);
      v6 = *((_QWORD *)a2 + 5);
      Rdp::Stack::Shim::CAdapterShim::FindMonitor(*((_QWORD *)this + 64), &v33, v6 + 12);
      v7 = 0;
      if ( v33 )
      {
        if ( *(_DWORD *)(v6 + 80) )
          v7 = (const unsigned __int8 *)(v6 + *(unsigned int *)(v6 + 80));
        Rdp::Stack::Shim::CMonitorShim::ResourceUpdate(
          v33,
          *(_QWORD *)(v6 + 28),
          *(void **)(v6 + 36),
          *(void **)(v6 + 44),
          *(_DWORD *)(v6 + 52),
          *(_QWORD *)(v6 + 56),
          *(_DWORD *)(v6 + 72),
          (struct tagRECT *)(v6 + 84),
          *(_QWORD *)(v6 + 64),
          *(_DWORD *)(v6 + 76),
          v7);
      }
      else
      {
        LODWORD(v28) = *(unsigned __int16 *)(v6 + 18);
        LODWORD(v24) = *(unsigned __int16 *)(v6 + 16);
        LODWORD(v18) = *(_DWORD *)(v6 + 12);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x180,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
          (const char *)0x80070490LL,
          (int)"Dropping ResourceUpdate request for monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
          v18,
          v24,
          v28,
          *(unsigned __int8 *)(v6 + 20),
          *(unsigned __int8 *)(v6 + 21),
          *(unsigned __int8 *)(v6 + 22),
          *(unsigned __int8 *)(v6 + 23),
          *(unsigned __int8 *)(v6 + 24),
          *(unsigned __int8 *)(v6 + 25),
          *(unsigned __int8 *)(v6 + 26),
          *(unsigned __int8 *)(v6 + 27));
      }
      if ( (unsigned int)dword_18003C058 > 5 )
      {
        v34 = "ResourceUpdate - done";
        v29 = "Rdp::Stack::Shim::CCtrlChannel::OnDataReceived";
        LODWORD(v32) = 390;
        v30[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_1800359C9,
          v8,
          v9,
          (__int64)v30,
          (__int64)&v32,
          (__int64)&v29,
          (__int64)&v34);
      }
      break;
    default:
      return;
  }
  v14 = &v33;
LABEL_35:
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(v14);
}

```

## disassembly

```asm
0x18001bb08  mov     [rsp-8+arg_0], rbx
0x18001bb0d  push    rbp
0x18001bb0e  push    rsi
0x18001bb0f  push    rdi
0x18001bb10  push    r12
0x18001bb12  push    r13
0x18001bb14  push    r14
0x18001bb16  push    r15
0x18001bb18  lea     rbp, [rsp-27h]
0x18001bb1d  sub     rsp, 90h
0x18001bb24  mov     r14, rdx
0x18001bb27  mov     rbx, rcx
0x18001bb2a  cmp     dword ptr [rdx+40h], 0Ch
0x18001bb2e  setb    al
0x18001bb31  mov     rcx, [rbp+5Fh]; this
0x18001bb35  lea     rdx, aBufferSizeIsTo_3; "Buffer size is too small to cast to RDP"...
0x18001bb3c  mov     [rsp+0C0h+var_98], rdx; bool
0x18001bb41  mov     [rsp+0C0h+var_A0], al; char
0x18001bb45  mov     edi, 8007007Ah
0x18001bb4a  mov     r9d, edi; char *
0x18001bb4d  lea     r13, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001bb54  mov     r8, r13; unsigned int
0x18001bb57  mov     edx, 0F6h; void *
0x18001bb5c  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001bb61  mov     rcx, [r14+28h]
0x18001bb65  mov     edx, [rcx+8]
0x18001bb68  sub     edx, 1
0x18001bb6b  jz      loc_18001C02E
0x18001bb71  sub     edx, 1
0x18001bb74  jz      loc_18001BF3B
0x18001bb7a  sub     edx, 1
0x18001bb7d  jz      loc_18001BD89
0x18001bb83  cmp     edx, 1
0x18001bb86  jnz     loc_18001C1EA
0x18001bb8c  mov     eax, cs:dword_18003C058
0x18001bb92  lea     r15, aRdpStackShimCc_0; "Rdp::Stack::Shim::CCtrlChannel::OnDataR"...
0x18001bb99  cmp     eax, 5
0x18001bb9c  jbe     short loc_18001BBEF
0x18001bb9e  lea     rax, aResourceupdate; "ResourceUpdate"
0x18001bba5  mov     [rbp+57h+arg_10], rax
0x18001bba9  mov     [rbp+57h+arg_18], r15
0x18001bbad  mov     dword ptr [rbp+57h+arg_8], 15Dh
0x18001bbb4  mov     [rbp+57h+var_40], r13
0x18001bbb8  lea     rax, [rbp+57h+arg_10]
0x18001bbbc  mov     [rsp+0C0h+var_88], rax
0x18001bbc1  lea     rax, [rbp+57h+arg_18]
0x18001bbc5  mov     [rsp+0C0h+var_90], rax; char *
0x18001bbca  lea     rax, [rbp+57h+arg_8]
0x18001bbce  mov     [rsp+0C0h+var_98], rax
0x18001bbd3  lea     rax, [rbp+57h+var_40]
0x18001bbd7  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001bbdc  lea     rdx, word_180035A06
0x18001bbe3  lea     rcx, dword_18003C058
0x18001bbea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001bbef  cmp     dword ptr [r14+40h], 64h ; 'd'
0x18001bbf4  setb    al
0x18001bbf7  mov     rcx, [rbp+5Fh]; this
0x18001bbfb  lea     rdx, aBufferSizeIsTo_4; "Buffer size is too small to cast to RDP"...
0x18001bc02  mov     [rsp+0C0h+var_98], rdx; bool
0x18001bc07  mov     [rsp+0C0h+var_A0], al; char
0x18001bc0b  mov     r9d, edi; char *
0x18001bc0e  mov     r8, r13; unsigned int
0x18001bc11  mov     edx, 163h; void *
0x18001bc16  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001bc1b  mov     r14, [r14+28h]
0x18001bc1f  lea     r12, [r14+0Ch]
0x18001bc23  mov     r8, r12
0x18001bc26  lea     rdx, [rbp+57h+arg_10]
0x18001bc2a  mov     rcx, [rbx+200h]
0x18001bc31  call    ?FindMonitor@CAdapterShim@Shim@Stack@Rdp@@QEAA?BV?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBU_GUID@@@Z; Rdp::Stack::Shim::CAdapterShim::FindMonitor(_GUID const &)
0x18001bc36  nop
0x18001bc37  mov     rcx, [rbp+57h+arg_10]; this
0x18001bc3b  xor     eax, eax
0x18001bc3d  test    rcx, rcx
0x18001bc40  jz      short loc_18001BC9D
0x18001bc42  cmp     [r14+50h], eax
0x18001bc46  jz      short loc_18001BC4F
0x18001bc48  mov     eax, [r14+50h]
0x18001bc4c  add     rax, r14
0x18001bc4f  lea     r8, [r14+54h]
0x18001bc53  mov     [rsp+0C0h+var_70], rax; unsigned __int8 *
0x18001bc58  mov     eax, [r14+4Ch]
0x18001bc5c  mov     [rsp+0C0h+var_78], eax; unsigned int
0x18001bc60  mov     rax, [r14+40h]
0x18001bc64  mov     [rsp+0C0h+var_80], rax; unsigned __int64
0x18001bc69  mov     [rsp+0C0h+var_88], r8; struct tagRECT *
0x18001bc6e  mov     eax, [r14+48h]
0x18001bc72  mov     dword ptr [rsp+0C0h+var_90], eax; unsigned int
0x18001bc76  mov     rax, [r14+38h]
0x18001bc7a  mov     [rsp+0C0h+var_98], rax; unsigned __int64
0x18001bc7f  mov     eax, [r14+34h]
0x18001bc83  mov     dword ptr [rsp+0C0h+var_A0], eax; unsigned int
0x18001bc87  mov     r9, [r14+2Ch]; void *
0x18001bc8b  mov     r8, [r14+24h]; void *
0x18001bc8f  mov     rdx, [r14+1Ch]; unsigned __int64
0x18001bc93  call    ?ResourceUpdate@CMonitorShim@Shim@Stack@Rdp@@QEAAX_KPEAX1I0IPEAUtagRECT@@0IPEBE@Z; Rdp::Stack::Shim::CMonitorShim::ResourceUpdate(unsigned __int64,void *,void *,uint,unsigned __int64,uint,tagRECT *,unsigned __int64,uint,uchar const *)
0x18001bc98  jmp     loc_18001BD27
0x18001bc9d  movzx   eax, byte ptr [r14+1Bh]
0x18001bca2  movzx   edx, byte ptr [r14+1Ah]
0x18001bca7  movzx   r8d, byte ptr [r14+19h]
0x18001bcac  movzx   r9d, byte ptr [r14+18h]
0x18001bcb1  movzx   r10d, byte ptr [r14+17h]
0x18001bcb6  movzx   r11d, byte ptr [r14+16h]
0x18001bcbb  movzx   ebx, byte ptr [r14+15h]
0x18001bcc0  movzx   edi, byte ptr [r14+14h]
0x18001bcc5  movzx   esi, word ptr [r14+12h]
0x18001bcca  movzx   r14d, word ptr [r14+10h]
0x18001bccf  mov     rcx, [rbp+5Fh]; this
0x18001bcd3  mov     [rsp+0C0h+var_48], eax
0x18001bcd7  mov     [rsp+0C0h+var_50], edx
0x18001bcdb  mov     [rsp+0C0h+var_58], r8d
0x18001bce0  mov     [rsp+0C0h+var_60], r9d
0x18001bce5  mov     [rsp+0C0h+var_68], r10d
0x18001bcea  mov     dword ptr [rsp+0C0h+var_70], r11d
0x18001bcef  mov     [rsp+0C0h+var_78], ebx
0x18001bcf3  mov     dword ptr [rsp+0C0h+var_80], edi
0x18001bcf7  mov     dword ptr [rsp+0C0h+var_88], esi
0x18001bcfb  mov     dword ptr [rsp+0C0h+var_90], r14d
0x18001bd00  mov     eax, [r12]
0x18001bd04  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18001bd08  lea     rax, aDroppingResour_0; "Dropping ResourceUpdate request for mon"...
0x18001bd0f  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18001bd14  mov     r9d, 80070490h; char *
0x18001bd1a  mov     r8, r13; unsigned int
0x18001bd1d  mov     edx, 180h; void *
0x18001bd22  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001bd27  mov     eax, cs:dword_18003C058
0x18001bd2d  cmp     eax, 5
0x18001bd30  jbe     short loc_18001BD84
0x18001bd32  lea     rax, aResourceupdate_0; "ResourceUpdate - done"
0x18001bd39  mov     [rbp+57h+arg_18], rax
0x18001bd3d  mov     [rbp+57h+var_40], r15
0x18001bd41  mov     dword ptr [rbp+57h+arg_8], 186h
0x18001bd48  mov     [rbp+57h+var_38], r13
0x18001bd4c  lea     rax, [rbp+57h+arg_18]
0x18001bd50  mov     [rsp+0C0h+var_88], rax
0x18001bd55  lea     rax, [rbp+57h+var_40]
0x18001bd59  mov     [rsp+0C0h+var_90], rax
0x18001bd5e  lea     rax, [rbp+57h+arg_8]
0x18001bd62  mov     [rsp+0C0h+var_98], rax
0x18001bd67  lea     rax, [rbp+57h+var_38]
0x18001bd6b  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001bd70  lea     rdx, byte_1800359C9
0x18001bd77  lea     rcx, dword_18003C058
0x18001bd7e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001bd83  nop
0x18001bd84  jmp     loc_18001C1E1
0x18001bd89  mov     eax, cs:dword_18003C058
0x18001bd8f  lea     r15, aRdpStackShimCc_0; "Rdp::Stack::Shim::CCtrlChannel::OnDataR"...
0x18001bd96  cmp     eax, 5
0x18001bd99  jbe     short loc_18001BDEC
0x18001bd9b  lea     rax, aSetrenderdevic; "SetRenderDevice"
0x18001bda2  mov     [rbp+57h+arg_10], rax
0x18001bda6  mov     [rbp+57h+arg_18], r15
0x18001bdaa  mov     dword ptr [rbp+57h+arg_8], 13Ch
0x18001bdb1  mov     [rbp+57h+var_38], r13
0x18001bdb5  lea     rax, [rbp+57h+arg_10]
0x18001bdb9  mov     [rsp+0C0h+var_88], rax
0x18001bdbe  lea     rax, [rbp+57h+arg_18]
0x18001bdc2  mov     [rsp+0C0h+var_90], rax; char *
0x18001bdc7  lea     rax, [rbp+57h+arg_8]
0x18001bdcb  mov     [rsp+0C0h+var_98], rax
0x18001bdd0  lea     rax, [rbp+57h+var_38]
0x18001bdd4  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001bdd9  lea     rdx, qword_180035A80
0x18001bde0  lea     rcx, dword_18003C058
0x18001bde7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001bdec  cmp     dword ptr [r14+40h], 2Ch ; ','
0x18001bdf1  setb    al
0x18001bdf4  mov     rcx, [rbp+5Fh]; this
0x18001bdf8  lea     rdx, aBufferSizeIsTo; "Buffer size is too small to cast to RDP"...
0x18001bdff  mov     [rsp+0C0h+var_98], rdx; bool
0x18001be04  mov     [rsp+0C0h+var_A0], al; char
0x18001be08  mov     r9d, edi; char *
0x18001be0b  mov     r8, r13; unsigned int
0x18001be0e  mov     edx, 141h; void *
0x18001be13  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001be18  mov     r14, [r14+28h]
0x18001be1c  lea     r12, [r14+0Ch]
0x18001be20  mov     r8, r12
0x18001be23  lea     rdx, [rbp+57h+arg_10]
0x18001be27  mov     rcx, [rbx+200h]
0x18001be2e  call    ?FindMonitor@CAdapterShim@Shim@Stack@Rdp@@QEAA?BV?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBU_GUID@@@Z; Rdp::Stack::Shim::CAdapterShim::FindMonitor(_GUID const &)
0x18001be33  nop
0x18001be34  mov     rcx, [rbp+57h+arg_10]; this
0x18001be38  test    rcx, rcx
0x18001be3b  jz      short loc_18001BE4F
0x18001be3d  lea     r8, [r14+24h]; struct _LUID *
0x18001be41  mov     rdx, [r14+1Ch]; unsigned __int64
0x18001be45  call    ?SetRenderDevice@CMonitorShim@Shim@Stack@Rdp@@QEAAX_KAEBU_LUID@@@Z; Rdp::Stack::Shim::CMonitorShim::SetRenderDevice(unsigned __int64,_LUID const &)
0x18001be4a  jmp     loc_18001BED9
0x18001be4f  movzx   eax, byte ptr [r14+1Bh]
0x18001be54  movzx   edx, byte ptr [r14+1Ah]
0x18001be59  movzx   r8d, byte ptr [r14+19h]
0x18001be5e  movzx   r9d, byte ptr [r14+18h]
0x18001be63  movzx   r10d, byte ptr [r14+17h]
0x18001be68  movzx   r11d, byte ptr [r14+16h]
0x18001be6d  movzx   ebx, byte ptr [r14+15h]
0x18001be72  movzx   edi, byte ptr [r14+14h]
0x18001be77  movzx   esi, word ptr [r14+12h]
0x18001be7c  movzx   r14d, word ptr [r14+10h]
0x18001be81  mov     rcx, [rbp+5Fh]; this
0x18001be85  mov     [rsp+0C0h+var_48], eax
0x18001be89  mov     [rsp+0C0h+var_50], edx
0x18001be8d  mov     [rsp+0C0h+var_58], r8d
0x18001be92  mov     [rsp+0C0h+var_60], r9d
0x18001be97  mov     [rsp+0C0h+var_68], r10d
0x18001be9c  mov     dword ptr [rsp+0C0h+var_70], r11d
0x18001bea1  mov     [rsp+0C0h+var_78], ebx
0x18001bea5  mov     dword ptr [rsp+0C0h+var_80], edi
0x18001bea9  mov     dword ptr [rsp+0C0h+var_88], esi
0x18001bead  mov     dword ptr [rsp+0C0h+var_90], r14d
0x18001beb2  mov     eax, [r12]
0x18001beb6  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18001beba  lea     rax, aDroppingSetren; "Dropping SetRenderDevice request for mo"...
0x18001bec1  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18001bec6  mov     r9d, 80070490h; char *
0x18001becc  mov     r8, r13; unsigned int
0x18001becf  mov     edx, 14Fh; void *
0x18001bed4  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001bed9  mov     eax, cs:dword_18003C058
0x18001bedf  cmp     eax, 5
0x18001bee2  jbe     short loc_18001BF36
0x18001bee4  lea     rax, aSetrenderdevic_0; "SetRenderDeviceDone"
0x18001beeb  mov     [rbp+57h+arg_18], rax
0x18001beef  mov     [rbp+57h+var_38], r15
0x18001bef3  mov     dword ptr [rbp+57h+arg_8], 154h
0x18001befa  mov     [rbp+57h+var_40], r13
0x18001befe  lea     rax, [rbp+57h+arg_18]
0x18001bf02  mov     [rsp+0C0h+var_88], rax
0x18001bf07  lea     rax, [rbp+57h+var_38]
0x18001bf0b  mov     [rsp+0C0h+var_90], rax
0x18001bf10  lea     rax, [rbp+57h+arg_8]
0x18001bf14  mov     [rsp+0C0h+var_98], rax
0x18001bf19  lea     rax, [rbp+57h+var_40]
0x18001bf1d  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001bf22  lea     rdx, byte_180035A43
0x18001bf29  lea     rcx, dword_18003C058
0x18001bf30  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001bf35  nop
0x18001bf36  jmp     loc_18001C1E1
0x18001bf3b  cmp     dword ptr [r14+40h], 24h ; '$'
0x18001bf40  setb    al
0x18001bf43  mov     rcx, [rbp+5Fh]; this
0x18001bf47  lea     rdx, aBufferSizeIsTo_10; "Buffer size is too small to cast to RDP"...
0x18001bf4e  mov     [rsp+0C0h+var_98], rdx; bool
0x18001bf53  mov     [rsp+0C0h+var_A0], al; char
0x18001bf57  mov     r9d, edi; char *
0x18001bf5a  mov     r8, r13; unsigned int
0x18001bf5d  mov     edx, 125h; void *
0x18001bf62  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001bf67  mov     r15, [r14+28h]
0x18001bf6b  lea     r12, [r15+0Ch]
0x18001bf6f  mov     r8, r12
0x18001bf72  lea     rdx, [rbp+57h+arg_8]
0x18001bf76  mov     rcx, [rbx+200h]
0x18001bf7d  call    ?FindMonitor@CAdapterShim@Shim@Stack@Rdp@@QEAA?BV?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBU_GUID@@@Z; Rdp::Stack::Shim::CAdapterShim::FindMonitor(_GUID const &)
0x18001bf82  nop
0x18001bf83  mov     rcx, [rbp+57h+arg_8]; this
0x18001bf87  test    rcx, rcx
0x18001bf8a  jz      short loc_18001BF9A
0x18001bf8c  mov     rdx, [r15+1Ch]; unsigned __int64
0x18001bf90  call    ?StopFrameProcessor@CMonitorShim@Shim@Stack@Rdp@@QEAAX_K@Z; Rdp::Stack::Shim::CMonitorShim::StopFrameProcessor(unsigned __int64)
0x18001bf95  jmp     loc_18001C025
0x18001bf9a  movzx   eax, byte ptr [r15+1Bh]
0x18001bf9f  movzx   edx, byte ptr [r15+1Ah]
0x18001bfa4  movzx   r9d, byte ptr [r15+19h]
0x18001bfa9  movzx   r10d, byte ptr [r15+18h]
0x18001bfae  movzx   r11d, byte ptr [r15+17h]
0x18001bfb3  movzx   ebx, byte ptr [r15+16h]
0x18001bfb8  movzx   edi, byte ptr [r15+15h]
0x18001bfbd  movzx   esi, byte ptr [r15+14h]
0x18001bfc2  movzx   r14d, word ptr [r15+12h]
0x18001bfc7  movzx   r15d, word ptr [r15+10h]
0x18001bfcc  mov     rcx, [rbp+5Fh]; this
0x18001bfd0  mov     [rsp+0C0h+var_48], eax
0x18001bfd4  mov     [rsp+0C0h+var_50], edx
0x18001bfd8  mov     [rsp+0C0h+var_58], r9d
0x18001bfdd  mov     [rsp+0C0h+var_60], r10d
0x18001bfe2  mov     [rsp+0C0h+var_68], r11d
0x18001bfe7  mov     dword ptr [rsp+0C0h+var_70], ebx
0x18001bfeb  mov     [rsp+0C0h+var_78], edi
0x18001bfef  mov     dword ptr [rsp+0C0h+var_80], esi
0x18001bff3  mov     dword ptr [rsp+0C0h+var_88], r14d
0x18001bff8  mov     dword ptr [rsp+0C0h+var_90], r15d
0x18001bffd  mov     eax, [r12]
0x18001c001  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18001c005  lea     rax, aDroppingStopfr; "Dropping StopFrameProcessor request for"...
0x18001c00c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18001c011  mov     r9d, 80070490h; char *
0x18001c017  mov     r8, r13; unsigned int
0x18001c01a  mov     edx, 133h; void *
0x18001c01f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c024  nop
0x18001c025  lea     rcx, [rbp+57h+arg_8]
0x18001c029  jmp     loc_18001C1E5
0x18001c02e  mov     eax, cs:dword_18003C058
0x18001c034  lea     r15, aRdpStackShimCc_0; "Rdp::Stack::Shim::CCtrlChannel::OnDataR"...
0x18001c03b  cmp     eax, 5
0x18001c03e  jbe     short loc_18001C091
  ... truncated ...
```
