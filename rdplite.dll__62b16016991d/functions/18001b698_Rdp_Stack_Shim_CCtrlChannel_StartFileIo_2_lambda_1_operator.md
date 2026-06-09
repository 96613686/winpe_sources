# _Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1_::operator()

- ea: `0x18001b698`
- end: `0x18001b969`
- name: `_Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1_::operator()`
- size: `721`
- prototype: `char __fastcall(Rdp::Stack::Shim::CCtrlChannel **, __int64, signed int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c3b0`

## callees

- `0x18000208c`
- `0x180004cb4`
- `0x180007b28`
- `0x18000a0e4`
- `0x18000cef0`
- `0x180011a1c`
- `0x18001265c`
- `0x1800197e4`
- `0x18001b698`
- `0x18001bab0`
- `0x18001bb08`
- `0x18001c2a8`

## string_xrefs

- `0x18001b7e5`: `Control channel read I/O stopped`
- `0x18001b94a`: `Failed to read from control channel file I/O`
- `0x18001b740`: `Failed to write to control channel file I/O`
- `0x18001b90d`: `Received unknown I/O command on control channel`

## pseudocode

```c
char __fastcall Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1_::operator()(
        Rdp::Stack::Shim::CCtrlChannel **a1,
        __int64 a2,
        signed int a3,
        int a4)
{
  int v7; // ecx
  Rdp::Stack::Shim::CCtrlChannel *v8; // rbx
  bool v9; // al
  __int64 *v10; // rcx
  Rdp::Stack::Shim::CCtrlChannel *v11; // rbx
  int v12; // r8d
  int v13; // r9d
  unsigned __int64 v14; // rbx
  Rdp::Stack::Shim::CCtrlChannel *v15; // rdi
  char result; // al
  wil *v17; // rcx
  const char *v18; // r9
  const char *v19; // r9
  unsigned int v20; // eax
  Rdp::Utils::System *v21; // rcx
  const char *v22; // [rsp+28h] [rbp-70h]
  int v23; // [rsp+20h] [rbp-78h]
  const char *v24; // [rsp+28h] [rbp-70h]
  const char *v25; // [rsp+30h] [rbp-68h]
  unsigned __int64 v26; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp-50h] BYREF
  const char *v28; // [rsp+50h] [rbp-48h] BYREF
  const char *v29; // [rsp+58h] [rbp-40h] BYREF
  const char *v30; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v32; // [rsp+A8h] [rbp+10h] BYREF

  try
  {
    v7 = *(_DWORD *)(a2 - 80 + 112);
    if ( v7 )
    {
      if ( v7 != 1 )
      {
        v18 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xBB,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
          v18,
          (int)"Received unknown I/O command on control channel",
          v24);
      }
      v32 = 0;
      wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(&v32);
      v8 = *a1;
      wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        &v27,
        v32);
      Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Shim::CCtrlChannel *)((char *)v8 + 312));
      v9 = a3 && a3 != 22 && a3 != 31 && a3 != 995 && a3 != 1235 && a3 != 1291;
      if ( a3 > 0 )
        a3 = (unsigned __int16)a3 | 0x80070000;
      LOBYTE(v23) = v9;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
        (const char *)(unsigned int)a3,
        v23,
        (bool)"Failed to write to control channel file I/O",
        v25);
      v10 = &v32;
    }
    else
    {
      v26 = 0;
      wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(&v26);
      if ( a3 )
      {
        v11 = *a1;
        wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
          &v32,
          v26);
        Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Shim::CCtrlChannel *)((char *)v11 + 112));
        if ( a3 != 22 && a3 != 31 && a3 != 995 && a3 != 1235 && a3 != 1291 )
        {
          if ( a3 > 0 )
            a3 = (unsigned __int16)a3 | 0x80070000;
          v19 = (const char *)(unsigned int)wil::verify_hresult<long>((unsigned int)a3);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x95,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
            v19,
            (int)"Failed to read from control channel file I/O",
            v24);
        }
        if ( (unsigned int)dword_18003C058 > 4 )
        {
          v28 = "Control channel read I/O stopped";
          v29 = "Rdp::Stack::Shim::CCtrlChannel::StartFileIo::<lambda_1>::operator ()";
          LODWORD(v32) = 141;
          v30 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)&dword_18003C058,
            (unsigned int)&byte_180035B37,
            v12,
            v13,
            (__int64)&v30,
            (__int64)&v32,
            (__int64)&v29,
            (__int64)&v28);
        }
      }
      else
      {
        v14 = v26;
        *(_DWORD *)(v26 + 144) = a4;
        Rdp::Stack::Shim::CCtrlChannel::OnDataReceived(
          *a1,
          (const struct Rdp::Stack::Driver::IoBuffer *)((v14 + 80) & ((unsigned __int128)-(__int128)v14 >> 64)));
        v15 = *a1;
        wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
          &v32,
          v14);
        Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Shim::CCtrlChannel *)((char *)v15 + 112));
        Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Pop((Rdp::Stack::Shim::CCtrlChannel *)((char *)*a1 + 112));
        if ( (unsigned __int8)Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::StartRead(
                                *a1,
                                (v27 + 80) & ((unsigned __int128)-(__int128)v27 >> 64)) )
          v27 = 0;
        wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v27);
      }
      v10 = (__int64 *)&v26;
    }
    result = wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(v10);
  }
  catch ( ... )
  {
    v20 = wil::ResultFromCaughtException(v17);
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\ctrlchannel.cpp",
      (const char *)v20,
      (int)"Control channel I/O halted",
      v22);
    result = Rdp::Utils::System::IsKernelDebuggerPresent(v21);
    if ( result )
      __debugbreak();
  }
  return result;
}

```

## disassembly

```asm
0x18001b698  push    rbx
0x18001b69a  push    rsi
0x18001b69b  push    rdi
0x18001b69c  push    r14
0x18001b69e  sub     rsp, 78h
0x18001b6a2  mov     r14, r9
0x18001b6a5  mov     edi, r8d
0x18001b6a8  mov     rsi, rcx
0x18001b6ab  add     rdx, 0FFFFFFFFFFFFFFB0h
0x18001b6af  mov     ecx, [rdx+70h]
0x18001b6b2  test    ecx, ecx
0x18001b6b4  jz      loc_18001B772
0x18001b6ba  cmp     ecx, 1
0x18001b6bd  jnz     loc_18001B8F8
0x18001b6c3  mov     [rsp+98h+arg_8], 0
0x18001b6cf  lea     rcx, [rsp+98h+arg_8]
0x18001b6d7  call    ?attach@?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUCIoBuffer@Driver@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(Rdp::Stack::Driver::CIoBuffer *)
0x18001b6dc  mov     rbx, [rsi]
0x18001b6df  mov     rdx, [rsp+98h+arg_8]
0x18001b6e7  lea     rcx, [rsp+98h+var_50]
0x18001b6ec  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001b6f1  lea     rdx, [rsp+98h+var_50]
0x18001b6f6  lea     rcx, [rbx+138h]; _Mtx_t
0x18001b6fd  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x18001b702  test    edi, edi
0x18001b704  jz      short loc_18001B729
0x18001b706  mov     eax, edi
0x18001b708  sub     eax, 16h
0x18001b70b  jz      short loc_18001B729
0x18001b70d  sub     eax, 9
0x18001b710  jz      short loc_18001B729
0x18001b712  sub     eax, 3C4h
0x18001b717  jz      short loc_18001B729
0x18001b719  sub     eax, 0F0h
0x18001b71e  jz      short loc_18001B729
0x18001b720  cmp     eax, 38h ; '8'
0x18001b723  jz      short loc_18001B729
0x18001b725  mov     al, 1
0x18001b727  jmp     short loc_18001B72B
0x18001b729  xor     eax, eax
0x18001b72b  test    edi, edi
0x18001b72d  jle     short loc_18001B738
0x18001b72f  movzx   edi, di
0x18001b732  or      edi, 80070000h
0x18001b738  mov     rcx, [rsp+98h]; this
0x18001b740  lea     rdx, aFailedToWriteT; "Failed to write to control channel file"...
0x18001b747  mov     qword ptr [rsp+98h+var_70], rdx; bool
0x18001b74c  mov     byte ptr [rsp+98h+var_78], al; int
0x18001b750  mov     r9d, edi; char *
0x18001b753  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001b75a  mov     edx, 0B4h; void *
0x18001b75f  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001b764  nop
0x18001b765  lea     rcx, [rsp+98h+arg_8]
0x18001b76d  jmp     loc_18001B8E8
0x18001b772  mov     [rsp+98h+var_58], 0
0x18001b77b  lea     rcx, [rsp+98h+var_58]
0x18001b780  call    ?attach@?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUCIoBuffer@Driver@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(Rdp::Stack::Driver::CIoBuffer *)
0x18001b785  test    edi, edi
0x18001b787  jz      loc_18001B857
0x18001b78d  mov     rbx, [rsi]
0x18001b790  mov     rdx, [rsp+98h+var_58]
0x18001b795  lea     rcx, [rsp+98h+arg_8]
0x18001b79d  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001b7a2  lea     rdx, [rsp+98h+arg_8]
0x18001b7aa  lea     rcx, [rbx+70h]; _Mtx_t
0x18001b7ae  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x18001b7b3  mov     eax, edi
0x18001b7b5  sub     eax, 16h
0x18001b7b8  jz      short loc_18001B7D6
0x18001b7ba  sub     eax, 9
0x18001b7bd  jz      short loc_18001B7D6
0x18001b7bf  sub     eax, 3C4h
0x18001b7c4  jz      short loc_18001B7D6
0x18001b7c6  sub     eax, 0F0h
0x18001b7cb  jz      short loc_18001B7D6
0x18001b7cd  cmp     eax, 38h ; '8'
0x18001b7d0  jnz     loc_18001B92B
0x18001b7d6  mov     eax, cs:dword_18003C058
0x18001b7dc  cmp     eax, 4
0x18001b7df  jbe     loc_18001B8E3
0x18001b7e5  lea     rax, aControlChannel_0; "Control channel read I/O stopped"
0x18001b7ec  mov     [rsp+98h+var_48], rax
0x18001b7f1  lea     rax, aRdpStackShimCc; "Rdp::Stack::Shim::CCtrlChannel::StartFi"...
0x18001b7f8  mov     [rsp+98h+var_40], rax
0x18001b7fd  mov     dword ptr [rsp+98h+arg_8], 8Dh
0x18001b808  lea     rax, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001b80f  mov     [rsp+98h+var_38], rax
0x18001b814  lea     rax, [rsp+98h+var_48]
0x18001b819  mov     [rsp+98h+var_60], rax
0x18001b81e  lea     rax, [rsp+98h+var_40]
0x18001b823  mov     [rsp+98h+var_68], rax
0x18001b828  lea     rax, [rsp+98h+arg_8]
0x18001b830  mov     qword ptr [rsp+98h+var_70], rax
0x18001b835  lea     rax, [rsp+98h+var_38]
0x18001b83a  mov     qword ptr [rsp+98h+var_78], rax
0x18001b83f  lea     rdx, byte_180035B37
0x18001b846  lea     rcx, dword_18003C058
0x18001b84d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001b852  jmp     loc_18001B8E3
0x18001b857  mov     rbx, [rsp+98h+var_58]
0x18001b85c  mov     [rbx+90h], r14d
0x18001b863  mov     rax, rbx
0x18001b866  lea     rcx, [rbx+50h]
0x18001b86a  neg     rax
0x18001b86d  sbb     rdx, rdx
0x18001b870  and     rdx, rcx; struct Rdp::Stack::Driver::IoBuffer *
0x18001b873  mov     rcx, [rsi]; this
0x18001b876  call    ?OnDataReceived@CCtrlChannel@Shim@Stack@Rdp@@AEAAXPEBUIoBuffer@Driver@34@@Z; Rdp::Stack::Shim::CCtrlChannel::OnDataReceived(Rdp::Stack::Driver::IoBuffer const *)
0x18001b87b  mov     rdi, [rsi]
0x18001b87e  mov     rdx, rbx
0x18001b881  lea     rcx, [rsp+98h+arg_8]
0x18001b889  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001b88e  lea     rdx, [rsp+98h+arg_8]
0x18001b896  lea     rcx, [rdi+70h]; _Mtx_t
0x18001b89a  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x18001b89f  mov     rcx, [rsi]
0x18001b8a2  add     rcx, 70h ; 'p'; _Mtx_t
0x18001b8a6  lea     rdx, [rsp+98h+var_50]
0x18001b8ab  call    ?Pop@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Pop(void)
0x18001b8b0  nop
0x18001b8b1  mov     rax, [rsp+98h+var_50]
0x18001b8b6  lea     rcx, [rax+50h]
0x18001b8ba  neg     rax
0x18001b8bd  sbb     rdx, rdx
0x18001b8c0  and     rdx, rcx
0x18001b8c3  mov     rcx, [rsi]
0x18001b8c6  call    ?StartRead@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::StartRead(Rdp::Stack::Driver::IoBuffer *)
0x18001b8cb  test    al, al
0x18001b8cd  jz      short loc_18001B8D8
0x18001b8cf  mov     [rsp+98h+var_50], 0
0x18001b8d8  lea     rcx, [rsp+98h+var_50]
0x18001b8dd  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001b8e2  nop
0x18001b8e3  lea     rcx, [rsp+98h+var_58]
0x18001b8e8  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001b8ed  nop
0x18001b8ee  add     rsp, 78h
0x18001b8f2  pop     r14
0x18001b8f4  pop     rdi
0x18001b8f5  pop     rsi
0x18001b8f6  pop     rbx
0x18001b8f7  retn
0x18001b8f8  mov     ecx, 8000FFFFh
0x18001b8fd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001b902  mov     r9d, eax; char *
0x18001b905  mov     rcx, [rsp+98h]; this
0x18001b90d  lea     rax, aReceivedUnknow_0; "Received unknown I/O command on control"...
0x18001b914  mov     qword ptr [rsp+98h+var_78], rax; int
0x18001b919  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001b920  mov     edx, 0BBh; void *
0x18001b925  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001b92b  test    edi, edi
0x18001b92d  jle     short loc_18001B938
0x18001b92f  movzx   edi, di
0x18001b932  or      edi, 80070000h
0x18001b938  mov     ecx, edi
0x18001b93a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001b93f  mov     r9d, eax; char *
0x18001b942  mov     rcx, [rsp+98h]; this
0x18001b94a  lea     rax, aFailedToReadFr_0; "Failed to read from control channel fil"...
0x18001b951  mov     qword ptr [rsp+98h+var_78], rax; int
0x18001b956  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001b95d  mov     edx, 95h; void *
0x18001b962  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
