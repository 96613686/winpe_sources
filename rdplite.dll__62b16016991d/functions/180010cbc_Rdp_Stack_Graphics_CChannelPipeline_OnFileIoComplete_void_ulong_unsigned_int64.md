# Rdp::Stack::Graphics::CChannelPipeline::OnFileIoComplete(void *,ulong,unsigned __int64)

- ea: `0x180010cbc`
- end: `0x180011041`
- name: `?OnFileIoComplete@CChannelPipeline@Graphics@Stack@Rdp@@IEAAXPEAXK_K@Z`
- size: `901`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CChannelPipeline *this, _DWORD *, signed int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800122c0`

## callees

- `0x180001d88`
- `0x180004cb4`
- `0x180007b28`
- `0x18000a0e4`
- `0x18000cef0`
- `0x18000f2e0`
- `0x18000fbe4`
- `0x180010cbc`
- `0x1800118a4`
- `0x180011a1c`
- `0x180011b5c`
- `0x18001265c`
- `0x180012688`

## string_xrefs

- `0x180010ecd`: `Read I/O stopped`
- `0x180010ded`: `Rdp::Stack::Graphics::CChannelPipeline::OnFileIoComplete`
- `0x180010ed9`: `Rdp::Stack::Graphics::CChannelPipeline::OnFileIoComplete`
- `0x180010de1`: `Read I/O cancelled`
- `0x180011022`: `Failed to read from %s file I/O channel`
- `0x180010fd1`: `Received unknown I/O command on %s channel`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Rdp::Stack::Graphics::CChannelPipeline::OnFileIoComplete(
        Rdp::Stack::Graphics::CChannelPipeline *this,
        _DWORD *a2,
        signed int a3,
        unsigned int a4)
{
  int v7; // ecx
  __int64 *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  const char *v11; // rax
  char v12; // di
  const char *v13; // rbx
  wil *v14; // rcx
  unsigned int v15; // eax
  const char *v16; // rdx
  unsigned int v17; // eax
  const char *v18; // rdx
  unsigned int v19; // edi
  const char *v20; // rdx
  Rdp::Utils::System *v21; // rcx
  __int64 v22; // [rsp+50h] [rbp-38h] BYREF
  const char *v23; // [rsp+58h] [rbp-30h] BYREF
  const char *v24; // [rsp+60h] [rbp-28h] BYREF
  const char *v25; // [rsp+68h] [rbp-20h] BYREF
  const char *v26; // [rsp+70h] [rbp-18h] BYREF
  char v27; // [rsp+78h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v30; // [rsp+98h] [rbp+10h] BYREF

  try
  {
    v7 = a2[8];
    if ( v7 )
    {
      if ( (unsigned int)(v7 - 1) > 1 )
      {
        std::wstring::c_str((char *)this + 536);
        v15 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x126,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
          (const char *)v15,
          (int)"Received unknown I/O command on %s channel",
          v16);
      }
      v30 = 0;
      wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(&v30);
      wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        &v22,
        v30);
      Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Graphics::CChannelPipeline *)((char *)this + 288));
      v8 = &v30;
      goto LABEL_29;
    }
    v22 = 0;
    wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(&v22);
    if ( a3 )
    {
      wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        &v30,
        v22);
      Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Graphics::CChannelPipeline *)((char *)this + 88));
      if ( a3 == 22 || a3 == 31 || a3 == 995 || a3 == 1235 || a3 == 1291 )
      {
        if ( (unsigned int)dword_18003C058 > 4 )
        {
          v13 = (char *)this + 536;
          if ( *((_QWORD *)v13 + 3) > 7u )
            v13 = *(const char **)v13;
          v26 = v13;
          v25 = "Read I/O stopped";
          v24 = "Rdp::Stack::Graphics::CChannelPipeline::OnFileIoComplete";
          LODWORD(v30) = 236;
          v23 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_18003C058,
            (unsigned int)&word_1800351B6,
            v9,
            v10,
            (__int64)&v23,
            (__int64)&v30,
            (__int64)&v24,
            (__int64)&v25,
            (__int64)&v26);
        }
        goto LABEL_28;
      }
      if ( a3 != 57345 )
      {
        std::wstring::c_str((char *)this + 536);
        if ( a3 > 0 )
          a3 = (unsigned __int16)a3 | 0x80070000;
        v17 = wil::verify_hresult<long>((unsigned int)a3);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
          (const char *)v17,
          (int)"Failed to read from %s file I/O channel",
          v18);
      }
      if ( (unsigned int)dword_18003C058 > 4 )
      {
        v11 = (char *)this + 536;
        if ( *((_QWORD *)this + 70) > 7u )
          v11 = *(const char **)v11;
        v23 = v11;
        v24 = "Read I/O cancelled";
        v25 = "Rdp::Stack::Graphics::CChannelPipeline::OnFileIoComplete";
        LODWORD(v30) = 243;
        v26 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)byte_18003516D,
          v9,
          v10,
          (__int64)&v26,
          (__int64)&v30,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v23);
      }
      std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(
        &v26,
        (char *)this + 584);
      if ( !v27 || (v12 = 1, (unsigned __int64)(*((_QWORD *)this + 71) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL) )
        v12 = 0;
      std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(&v26);
      if ( v12 )
        goto LABEL_27;
    }
    else
    {
      if ( (int)Rdp::Stack::Graphics::CChannelPipeline::ProcessReadBuffer((__int64)this, &v22, a4) >= 0 )
      {
LABEL_27:
        Rdp::Stack::Graphics::CChannelPipeline::ScheduleNextReadRequest(this);
        goto LABEL_28;
      }
      wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        &v30,
        v22);
      Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Graphics::CChannelPipeline *)((char *)this + 88));
    }
LABEL_28:
    v8 = &v22;
LABEL_29:
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(v8);
  }
  catch ( ... )
  {
    if ( *((_BYTE *)this + 832) )
    {
      v19 = wil::ResultFromCaughtException(v14);
      v20 = (char *)this + 536;
      if ( *((_QWORD *)this + 70) > 7u )
        v20 = *(const char **)v20;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x12F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
        (const char *)v19,
        (int)"%s channel I/O halted",
        v20);
      if ( Rdp::Utils::System::IsKernelDebuggerPresent(v21) )
        __debugbreak();
      Rdp::Stack::Graphics::CGrfxPipeline::Fallback(*((Rdp::Stack::Graphics::CGrfxPipeline **)this + 103), v19);
      *((_BYTE *)this + 832) = 0;
    }
  }
}

```

## disassembly

```asm
0x180010cbc  mov     [rsp+arg_10], rbx
0x180010cc1  mov     [rsp+arg_18], rsi
0x180010cc6  mov     [rsp+arg_0], rcx
0x180010ccb  push    rdi
0x180010ccc  sub     rsp, 80h
0x180010cd3  mov     rsi, r9
0x180010cd6  mov     edi, r8d
0x180010cd9  mov     rbx, rcx
0x180010cdc  add     rdx, 0FFFFFFFFFFFFFFB0h
0x180010ce0  mov     ecx, [rdx+70h]
0x180010ce3  test    ecx, ecx
0x180010ce5  jz      short loc_180010D3F
0x180010ce7  sub     ecx, 1
0x180010cea  jz      short loc_180010CF5
0x180010cec  cmp     ecx, 1
0x180010cef  jnz     loc_180010FA8
0x180010cf5  mov     [rsp+88h+arg_8], 0
0x180010d01  lea     rcx, [rsp+88h+arg_8]
0x180010d09  call    ?attach@?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUCIoBuffer@Driver@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(Rdp::Stack::Driver::CIoBuffer *)
0x180010d0e  mov     rdx, [rsp+88h+arg_8]
0x180010d16  lea     rcx, [rsp+88h+var_38]
0x180010d1b  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180010d20  lea     rcx, [rbx+120h]; _Mtx_t
0x180010d27  lea     rdx, [rsp+88h+var_38]
0x180010d2c  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x180010d31  nop
0x180010d32  lea     rcx, [rsp+88h+arg_8]
0x180010d3a  jmp     loc_180010F8D
0x180010d3f  mov     [rsp+88h+var_38], 0
0x180010d48  lea     rcx, [rsp+88h+var_38]
0x180010d4d  call    ?attach@?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUCIoBuffer@Driver@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(Rdp::Stack::Driver::CIoBuffer *)
0x180010d52  test    edi, edi
0x180010d54  jz      loc_180010F46
0x180010d5a  mov     rdx, [rsp+88h+var_38]
0x180010d5f  lea     rcx, [rsp+88h+arg_8]
0x180010d67  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180010d6c  lea     rcx, [rbx+58h]; _Mtx_t
0x180010d70  lea     rdx, [rsp+88h+arg_8]
0x180010d78  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x180010d7d  mov     eax, edi
0x180010d7f  sub     eax, 16h
0x180010d82  jz      loc_180010EA8
0x180010d88  sub     eax, 9
0x180010d8b  jz      loc_180010EA8
0x180010d91  sub     eax, 3C4h
0x180010d96  jz      loc_180010EA8
0x180010d9c  sub     eax, 0F0h
0x180010da1  jz      loc_180010EA8
0x180010da7  cmp     eax, 38h ; '8'
0x180010daa  jz      loc_180010EA8
0x180010db0  cmp     edi, 0E001h
0x180010db6  jnz     loc_180010FEF
0x180010dbc  mov     eax, cs:dword_18003C058
0x180010dc2  cmp     eax, 4
0x180010dc5  jbe     loc_180010E58
0x180010dcb  lea     rax, [rbx+218h]
0x180010dd2  cmp     qword ptr [rax+18h], 7
0x180010dd7  jbe     short loc_180010DDC
0x180010dd9  mov     rax, [rax]
0x180010ddc  mov     [rsp+88h+var_30], rax
0x180010de1  lea     rax, aReadIOCancelle; "Read I/O cancelled"
0x180010de8  mov     [rsp+88h+var_28], rax
0x180010ded  lea     rax, aRdpStackGraphi_3; "Rdp::Stack::Graphics::CChannelPipeline:"...
0x180010df4  mov     [rsp+88h+var_20], rax
0x180010df9  mov     dword ptr [rsp+88h+arg_8], 0F3h
0x180010e04  lea     rax, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010e0b  mov     [rsp+88h+var_18], rax
0x180010e10  lea     rax, [rsp+88h+var_30]
0x180010e15  mov     [rsp+88h+var_48], rax
0x180010e1a  lea     rax, [rsp+88h+var_28]
0x180010e1f  mov     [rsp+88h+var_50], rax
0x180010e24  lea     rax, [rsp+88h+var_20]
0x180010e29  mov     [rsp+88h+var_58], rax
0x180010e2e  lea     rax, [rsp+88h+arg_8]
0x180010e36  mov     [rsp+88h+var_60], rax
0x180010e3b  lea     rax, [rsp+88h+var_18]
0x180010e40  mov     qword ptr [rsp+88h+var_68], rax
0x180010e45  lea     rdx, byte_18003516D
0x180010e4c  lea     rcx, dword_18003C058
0x180010e53  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180010e58  lea     rdx, [rbx+248h]
0x180010e5f  lea     rcx, [rsp+88h+var_18]
0x180010e64  call    ??0?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@Utry_to_lock_t@1@@Z; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &,std::try_to_lock_t)
0x180010e69  cmp     [rsp+88h+var_10], 0
0x180010e6e  jz      short loc_180010E85
0x180010e70  mov     rax, [rbx+238h]
0x180010e77  mov     edi, 1
0x180010e7c  sub     rax, rdi
0x180010e7f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010e83  jbe     short loc_180010E88
0x180010e85  xor     dil, dil
0x180010e88  lea     rcx, [rsp+88h+var_18]
0x180010e8d  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x180010e92  test    dil, dil
0x180010e95  jz      loc_180010F88
0x180010e9b  mov     rcx, rbx; this
0x180010e9e  call    ?ScheduleNextReadRequest@CChannelPipeline@Graphics@Stack@Rdp@@IEAAXXZ; Rdp::Stack::Graphics::CChannelPipeline::ScheduleNextReadRequest(void)
0x180010ea3  jmp     loc_180010F7D
0x180010ea8  mov     eax, cs:dword_18003C058
0x180010eae  cmp     eax, 4
0x180010eb1  jbe     loc_180010F88
0x180010eb7  add     rbx, 218h
0x180010ebe  cmp     qword ptr [rbx+18h], 7
0x180010ec3  jbe     short loc_180010EC8
0x180010ec5  mov     rbx, [rbx]
0x180010ec8  mov     [rsp+88h+var_18], rbx
0x180010ecd  lea     rax, aReadIOStopped; "Read I/O stopped"
0x180010ed4  mov     [rsp+88h+var_20], rax
0x180010ed9  lea     rax, aRdpStackGraphi_3; "Rdp::Stack::Graphics::CChannelPipeline:"...
0x180010ee0  mov     [rsp+88h+var_28], rax
0x180010ee5  mov     dword ptr [rsp+88h+arg_8], 0ECh
0x180010ef0  lea     rax, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010ef7  mov     [rsp+88h+var_30], rax
0x180010efc  lea     rax, [rsp+88h+var_18]
0x180010f01  mov     [rsp+88h+var_48], rax
0x180010f06  lea     rax, [rsp+88h+var_20]
0x180010f0b  mov     [rsp+88h+var_50], rax
0x180010f10  lea     rax, [rsp+88h+var_28]
0x180010f15  mov     [rsp+88h+var_58], rax
0x180010f1a  lea     rax, [rsp+88h+arg_8]
0x180010f22  mov     [rsp+88h+var_60], rax
0x180010f27  lea     rax, [rsp+88h+var_30]
0x180010f2c  mov     qword ptr [rsp+88h+var_68], rax
0x180010f31  lea     rdx, word_1800351B6
0x180010f38  lea     rcx, dword_18003C058
0x180010f3f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180010f44  jmp     short loc_180010F88
0x180010f46  mov     r8d, esi
0x180010f49  lea     rdx, [rsp+88h+var_38]
0x180010f4e  mov     rcx, rbx
0x180010f51  call    ?ProcessReadBuffer@CChannelPipeline@Graphics@Stack@Rdp@@IEAAJAEBV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@I@Z; Rdp::Stack::Graphics::CChannelPipeline::ProcessReadBuffer(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &,uint)
0x180010f56  test    eax, eax
0x180010f58  jns     short loc_180010F7F
0x180010f5a  mov     rdx, [rsp+88h+var_38]
0x180010f5f  lea     rcx, [rsp+88h+arg_8]
0x180010f67  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180010f6c  lea     rcx, [rbx+58h]; _Mtx_t
0x180010f70  lea     rdx, [rsp+88h+arg_8]
0x180010f78  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x180010f7d  jmp     short loc_180010F88
0x180010f7f  mov     rcx, rbx; this
0x180010f82  call    ?ScheduleNextReadRequest@CChannelPipeline@Graphics@Stack@Rdp@@IEAAXXZ; Rdp::Stack::Graphics::CChannelPipeline::ScheduleNextReadRequest(void)
0x180010f87  nop
0x180010f88  lea     rcx, [rsp+88h+var_38]
0x180010f8d  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180010f92  nop
0x180010f93  lea     r11, [rsp+88h+var_8]
0x180010f9b  mov     rbx, [r11+20h]
0x180010f9f  mov     rsi, [r11+28h]
0x180010fa3  mov     rsp, r11
0x180010fa6  pop     rdi
0x180010fa7  retn
0x180010fa8  lea     rcx, [rbx+218h]
0x180010faf  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180010fb4  mov     rdx, rax
0x180010fb7  mov     ecx, 8000FFFFh
0x180010fbc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180010fc1  mov     r9d, eax; char *
0x180010fc4  mov     rcx, [rsp+88h]; this
0x180010fcc  mov     [rsp+88h+var_60], rdx; char *
0x180010fd1  lea     rax, aReceivedUnknow; "Received unknown I/O command on %s chan"...
0x180010fd8  mov     qword ptr [rsp+88h+var_68], rax; int
0x180010fdd  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010fe4  mov     edx, 126h; void *
0x180010fe9  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180010fef  lea     rcx, [rbx+218h]
0x180010ff6  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180010ffb  mov     rdx, rax
0x180010ffe  test    edi, edi
0x180011000  jle     short loc_18001100B
0x180011002  movzx   edi, di
0x180011005  or      edi, 80070000h
0x18001100b  mov     ecx, edi
0x18001100d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180011012  mov     r9d, eax; char *
0x180011015  mov     rcx, [rsp+88h]; this
0x18001101d  mov     [rsp+88h+var_60], rdx; char *
0x180011022  lea     rax, aFailedToReadFr; "Failed to read from %s file I/O channel"
0x180011029  mov     qword ptr [rsp+88h+var_68], rax; int
0x18001102e  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011035  mov     edx, 100h; void *
0x18001103a  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
