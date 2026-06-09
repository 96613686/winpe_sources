# Rdp::Stack::Graphics::CChannelPipeline::OnFileIoCompleteLegacy(void *,ulong,unsigned __int64)

- ea: `0x180011048`
- end: `0x18001147e`
- name: `?OnFileIoCompleteLegacy@CChannelPipeline@Graphics@Stack@Rdp@@IEAAXPEAXK_K@Z`
- size: `1078`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CChannelPipeline *this, _DWORD *, signed int, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800122e0`

## callees

- `0x180001d88`
- `0x180004cb4`
- `0x180007b28`
- `0x18000a0e4`
- `0x18000cef0`
- `0x18000f2c0`
- `0x18000ffa8`
- `0x180010324`
- `0x180011048`
- `0x180011634`
- `0x18001174c`
- `0x180011a1c`
- `0x180011ee4`
- `0x18001265c`
- `0x180012688`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001121b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001121b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180011215`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180011215`

## string_xrefs

- `0x180011155`: `Read I/O stopped`
- `0x1800113fe`: `Failed to read from %s file I/O channel`
- `0x1800113ad`: `Received unknown I/O command on %s channel`
- `0x180011161`: `Rdp::Stack::Graphics::CChannelPipeline::OnFileIoCompleteLegacy`
- `0x18001145f`: `Failed to write buffer to %s Dvc`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CChannelPipeline::OnFileIoCompleteLegacy(
        Rdp::Stack::Graphics::CChannelPipeline *this,
        _DWORD *a2,
        signed int a3,
        int a4)
{
  int v7; // ecx
  unsigned __int64 *p_NumberOfBytesTransferred; // rcx
  int v9; // r9d
  _QWORD *v10; // rdi
  int v11; // esi
  unsigned __int64 v12; // rbx
  int v13; // esi
  unsigned __int64 v14; // rbx
  __int64 IoBuffer; // rax
  wil *v16; // rcx
  const char *v17; // r9
  const char *v18; // rdx
  const char *v19; // r9
  const char *v20; // rdx
  unsigned int v21; // eax
  const char *v22; // rdx
  unsigned int v23; // edi
  const char *v24; // rdx
  Rdp::Utils::System *v25; // rcx
  unsigned __int64 v26; // [rsp+50h] [rbp-48h] BYREF
  _QWORD *v27; // [rsp+58h] [rbp-40h] BYREF
  const char *v28; // [rsp+60h] [rbp-38h] BYREF
  const char *v29; // [rsp+68h] [rbp-30h] BYREF
  _QWORD v30[2]; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  unsigned __int64 NumberOfBytesTransferred; // [rsp+A8h] [rbp+10h] BYREF

  try
  {
    v7 = a2[8];
    if ( v7 )
    {
      if ( (unsigned int)(v7 - 1) > 1 )
      {
        std::wstring::c_str((char *)this + 536);
        v17 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x1D0,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
          v17,
          (int)"Received unknown I/O command on %s channel",
          v18);
      }
      NumberOfBytesTransferred = 0;
      wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(&NumberOfBytesTransferred);
      wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        &v26,
        NumberOfBytesTransferred);
      Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Graphics::CChannelPipeline *)((char *)this + 288));
      p_NumberOfBytesTransferred = &NumberOfBytesTransferred;
    }
    else
    {
      v26 = 0;
      wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(&v26);
      if ( a3 )
      {
        wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
          &NumberOfBytesTransferred,
          v26);
        Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Graphics::CChannelPipeline *)((char *)this + 88));
        if ( a3 != 22 && a3 != 31 && a3 != 995 && a3 != 1235 && a3 != 1291 )
        {
          std::wstring::c_str((char *)this + 536);
          if ( a3 > 0 )
            a3 = (unsigned __int16)a3 | 0x80070000;
          v19 = (const char *)(unsigned int)wil::verify_hresult<long>((unsigned int)a3);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x179,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
            v19,
            (int)"Failed to read from %s file I/O channel",
            v20);
        }
        if ( (unsigned int)dword_18003C058 > 4 )
        {
          v10 = (_QWORD *)((char *)this + 536);
          if ( v10[3] > 7u )
            v10 = (_QWORD *)*v10;
          v27 = v10;
          v28 = "Read I/O stopped";
          v29 = "Rdp::Stack::Graphics::CChannelPipeline::OnFileIoCompleteLegacy";
          LODWORD(NumberOfBytesTransferred) = 368;
          v30[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_18003C058,
            (unsigned int)&dword_180035124,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
            v9,
            (__int64)v30,
            (__int64)&NumberOfBytesTransferred,
            (__int64)&v29,
            (__int64)&v28,
            (__int64)&v27);
        }
      }
      else
      {
        v11 = 0;
        v12 = v26;
        if ( !*((_DWORD *)this + 201) )
        {
          v11 = 1;
          LODWORD(NumberOfBytesTransferred) = 0;
          GetOverlappedResult(
            *((HANDLE *)this + 71),
            (LPOVERLAPPED)((v26 + 80) & ((unsigned __int128)-(__int128)v26 >> 64)),
            (LPDWORD)&NumberOfBytesTransferred,
            0);
          if ( GetLastError() == 234 )
          {
            LODWORD(NumberOfBytesTransferred) = 0;
            Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::Peek(
              (char *)this + 568,
              &NumberOfBytesTransferred,
              (char *)this + 800);
          }
          else
          {
            *((_DWORD *)this + 200) = a4;
          }
        }
        *(_DWORD *)(v12 + 144) = a4;
        *((_DWORD *)this + 201) += a4;
        if ( *((_DWORD *)this + 201) == *((_DWORD *)this + 200) )
        {
          v11 |= 2u;
          *((_DWORD *)this + 201) = 0;
        }
        *(_DWORD *)(v12 + 136) = v11;
        v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, _DWORD, int, unsigned __int64))(**((_QWORD **)this + 99) + 24LL))(
                *((_QWORD *)this + 99),
                *(unsigned int *)(v12 + 144),
                *(_QWORD *)(v12 + 120),
                2,
                1,
                *((_DWORD *)this + 200),
                v11,
                v12);
        if ( v13 < 0 )
        {
          wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>(
            &NumberOfBytesTransferred,
            &v26);
          Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((Rdp::Stack::Graphics::CChannelPipeline *)((char *)this + 88));
          std::wstring::c_str((char *)this + 536);
          v21 = wil::verify_hresult<long>((unsigned int)v13);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x1B0,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
            (const char *)v21,
            (int)"Failed to write buffer to %s Dvc",
            v22);
        }
        v30[0] = 2500;
        Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(
          (char *)this + 88,
          &NumberOfBytesTransferred,
          v30);
        v14 = NumberOfBytesTransferred;
        if ( !NumberOfBytesTransferred )
        {
          IoBuffer = Rdp::Stack::Graphics::CChannelPipeline::CreateReadIoBuffer(this, v30);
          wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::operator=(
            &NumberOfBytesTransferred,
            IoBuffer);
          wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(v30);
          v14 = NumberOfBytesTransferred;
        }
        if ( (unsigned __int8)Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartRead(
                                (char *)this + 568,
                                (v14 + 80) & ((unsigned __int128)-(__int128)v14 >> 64)) )
          v14 = 0;
        NumberOfBytesTransferred = v14;
        wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&NumberOfBytesTransferred);
      }
      p_NumberOfBytesTransferred = &v26;
    }
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(p_NumberOfBytesTransferred);
  }
  catch ( ... )
  {
    if ( *((_BYTE *)this + 832) )
    {
      v23 = wil::ResultFromCaughtException(v16);
      v24 = (char *)this + 536;
      if ( *((_QWORD *)this + 70) > 7u )
        v24 = *(const char **)v24;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
        (const char *)v23,
        (int)"%s channel I/O halted",
        v24);
      if ( Rdp::Utils::System::IsKernelDebuggerPresent(v25) )
        __debugbreak();
      Rdp::Stack::Graphics::CGrfxPipeline::Fallback(*((Rdp::Stack::Graphics::CGrfxPipeline **)this + 103), v23);
      *((_BYTE *)this + 832) = 0;
    }
  }
}

```

## disassembly

```asm
0x180011048  mov     [rsp+arg_10], rbx
0x18001104d  mov     [rsp+arg_18], rsi
0x180011052  mov     [rsp+arg_0], rcx
0x180011057  push    rdi
0x180011058  push    r14
0x18001105a  push    r15
0x18001105c  sub     rsp, 80h
0x180011063  mov     r14, r9
0x180011066  mov     ebx, r8d
0x180011069  mov     rdi, rcx
0x18001106c  add     rdx, 0FFFFFFFFFFFFFFB0h
0x180011070  mov     ecx, [rdx+70h]
0x180011073  test    ecx, ecx
0x180011075  jz      short loc_1800110CF
0x180011077  sub     ecx, 1
0x18001107a  jz      short loc_180011085
0x18001107c  cmp     ecx, 1
0x18001107f  jnz     loc_180011384
0x180011085  mov     [rsp+98h+NumberOfBytesTransferred], 0
0x180011091  lea     rcx, [rsp+98h+NumberOfBytesTransferred]
0x180011099  call    ?attach@?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUCIoBuffer@Driver@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(Rdp::Stack::Driver::CIoBuffer *)
0x18001109e  mov     rdx, [rsp+98h+NumberOfBytesTransferred]
0x1800110a6  lea     rcx, [rsp+98h+var_48]
0x1800110ab  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x1800110b0  lea     rcx, [rdi+120h]; _Mtx_t
0x1800110b7  lea     rdx, [rsp+98h+var_48]
0x1800110bc  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x1800110c1  nop
0x1800110c2  lea     rcx, [rsp+98h+NumberOfBytesTransferred]
0x1800110ca  jmp     loc_180011365
0x1800110cf  mov     [rsp+98h+var_48], 0
0x1800110d8  lea     rcx, [rsp+98h+var_48]
0x1800110dd  call    ?attach@?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAUCIoBuffer@Driver@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::attach(Rdp::Stack::Driver::CIoBuffer *)
0x1800110e2  test    ebx, ebx
0x1800110e4  jz      loc_1800111D1
0x1800110ea  mov     rdx, [rsp+98h+var_48]
0x1800110ef  lea     rcx, [rsp+98h+NumberOfBytesTransferred]
0x1800110f7  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x1800110fc  lea     rcx, [rdi+58h]; _Mtx_t
0x180011100  lea     rdx, [rsp+98h+NumberOfBytesTransferred]
0x180011108  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x18001110d  mov     eax, ebx
0x18001110f  sub     eax, 16h
0x180011112  jz      short loc_180011130
0x180011114  sub     eax, 9
0x180011117  jz      short loc_180011130
0x180011119  sub     eax, 3C4h
0x18001111e  jz      short loc_180011130
0x180011120  sub     eax, 0F0h
0x180011125  jz      short loc_180011130
0x180011127  cmp     eax, 38h ; '8'
0x18001112a  jnz     loc_1800113CB
0x180011130  mov     eax, cs:dword_18003C058
0x180011136  cmp     eax, 4
0x180011139  jbe     loc_180011360
0x18001113f  add     rdi, 218h
0x180011146  cmp     qword ptr [rdi+18h], 7
0x18001114b  jbe     short loc_180011150
0x18001114d  mov     rdi, [rdi]
0x180011150  mov     [rsp+98h+var_40], rdi
0x180011155  lea     rax, aReadIOStopped; "Read I/O stopped"
0x18001115c  mov     [rsp+98h+var_38], rax
0x180011161  lea     rax, aRdpStackGraphi_5; "Rdp::Stack::Graphics::CChannelPipeline:"...
0x180011168  mov     [rsp+98h+var_30], rax
0x18001116d  mov     dword ptr [rsp+98h+NumberOfBytesTransferred], 170h
0x180011178  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001117f  mov     [rsp+98h+var_28], r8
0x180011184  lea     rax, [rsp+98h+var_40]
0x180011189  mov     [rsp+98h+var_58], rax
0x18001118e  lea     rax, [rsp+98h+var_38]
0x180011193  mov     [rsp+98h+var_60], rax
0x180011198  lea     rax, [rsp+98h+var_30]
0x18001119d  mov     [rsp+98h+var_68], rax
0x1800111a2  lea     rax, [rsp+98h+NumberOfBytesTransferred]
0x1800111aa  mov     [rsp+98h+var_70], rax
0x1800111af  lea     rax, [rsp+98h+var_28]
0x1800111b4  mov     qword ptr [rsp+98h+var_78], rax
0x1800111b9  lea     rdx, dword_180035124
0x1800111c0  lea     rcx, dword_18003C058
0x1800111c7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800111cc  jmp     loc_180011360
0x1800111d1  xor     esi, esi
0x1800111d3  mov     rbx, [rsp+98h+var_48]
0x1800111d8  cmp     [rdi+324h], esi
0x1800111de  jnz     short loc_180011253
0x1800111e0  mov     esi, 1
0x1800111e5  lea     r15, [rdi+238h]
0x1800111ec  mov     dword ptr [rsp+98h+NumberOfBytesTransferred], 0
0x1800111f7  mov     rax, rbx
0x1800111fa  lea     rcx, [rbx+50h]
0x1800111fe  neg     rax
0x180011201  sbb     rdx, rdx
0x180011204  and     rdx, rcx; lpOverlapped
0x180011207  xor     r9d, r9d; bWait
0x18001120a  lea     r8, [rsp+98h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180011212  mov     rcx, [r15]; hFile
0x180011215  call    cs:__imp_GetOverlappedResult
0x18001121b  call    cs:__imp_GetLastError
0x180011221  cmp     eax, 0EAh
0x180011226  jnz     short loc_18001124C
0x180011228  lea     r8, [rdi+320h]
0x18001122f  mov     dword ptr [rsp+98h+NumberOfBytesTransferred], 0
0x18001123a  lea     rdx, [rsp+98h+NumberOfBytesTransferred]
0x180011242  mov     rcx, r15
0x180011245  call    ?Peek@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAAXPEAI00@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::Peek(uint *,uint *,uint *)
0x18001124a  jmp     short loc_180011253
0x18001124c  mov     [rdi+320h], r14d
0x180011253  mov     [rbx+90h], r14d
0x18001125a  add     [rdi+324h], r14d
0x180011261  mov     eax, [rdi+324h]
0x180011267  cmp     eax, [rdi+320h]
0x18001126d  jnz     short loc_18001127C
0x18001126f  or      esi, 2
0x180011272  mov     dword ptr [rdi+324h], 0
0x18001127c  mov     [rbx+88h], esi
0x180011282  mov     rcx, [rdi+318h]
0x180011289  mov     rax, [rcx]
0x18001128c  mov     [rsp+98h+var_60], rbx
0x180011291  mov     dword ptr [rsp+98h+var_68], esi
0x180011295  mov     edx, [rdi+320h]
0x18001129b  mov     dword ptr [rsp+98h+var_70], edx
0x18001129f  mov     [rsp+98h+var_78], 1
0x1800112a7  mov     r9d, 2
0x1800112ad  mov     r8, [rbx+78h]
0x1800112b1  mov     edx, [rbx+90h]
0x1800112b7  mov     rax, [rax+18h]
0x1800112bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112c0  mov     esi, eax
0x1800112c2  test    eax, eax
0x1800112c4  js      loc_18001141B
0x1800112ca  mov     [rsp+98h+var_28], 9C4h
0x1800112d3  lea     r8, [rsp+98h+var_28]
0x1800112d8  lea     rdx, [rsp+98h+NumberOfBytesTransferred]
0x1800112e0  lea     rcx, [rdi+58h]
0x1800112e4  call    ?PopAndWait@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@AEBUnothrow_t@9@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::nothrow_t const &)
0x1800112e9  nop
0x1800112ea  mov     rbx, [rsp+98h+NumberOfBytesTransferred]
0x1800112f2  test    rbx, rbx
0x1800112f5  jnz     short loc_180011326
0x1800112f7  lea     rdx, [rsp+98h+var_28]
0x1800112fc  mov     rcx, rdi
0x1800112ff  call    ?CreateReadIoBuffer@CChannelPipeline@Graphics@Stack@Rdp@@IEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Stack::Graphics::CChannelPipeline::CreateReadIoBuffer(void)
0x180011304  mov     rdx, rax
0x180011307  lea     rcx, [rsp+98h+NumberOfBytesTransferred]
0x18001130f  call    ??4?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::operator=(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> &&)
0x180011314  lea     rcx, [rsp+98h+var_28]
0x180011319  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001131e  mov     rbx, [rsp+98h+NumberOfBytesTransferred]
0x180011326  mov     rax, rbx
0x180011329  lea     rcx, [rbx+50h]
0x18001132d  neg     rax
0x180011330  sbb     rdx, rdx
0x180011333  and     rdx, rcx
0x180011336  lea     rcx, [rdi+238h]
0x18001133d  call    ?StartRead@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartRead(Rdp::Stack::Driver::IoBuffer *)
0x180011342  xor     ecx, ecx
0x180011344  test    al, al
0x180011346  cmovnz  rbx, rcx
0x18001134a  mov     [rsp+98h+NumberOfBytesTransferred], rbx
0x180011352  lea     rcx, [rsp+98h+NumberOfBytesTransferred]
0x18001135a  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001135f  nop
0x180011360  lea     rcx, [rsp+98h+var_48]
0x180011365  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001136a  nop
0x18001136b  lea     r11, [rsp+98h+var_18]
0x180011373  mov     rbx, [r11+30h]
0x180011377  mov     rsi, [r11+38h]
0x18001137b  mov     rsp, r11
0x18001137e  pop     r15
0x180011380  pop     r14
0x180011382  pop     rdi
0x180011383  retn
0x180011384  lea     rcx, [rdi+218h]
0x18001138b  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180011390  mov     rdx, rax
0x180011393  mov     ecx, 8000FFFFh
0x180011398  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001139d  mov     r9d, eax; char *
0x1800113a0  mov     rcx, [rsp+98h]; this
0x1800113a8  mov     [rsp+98h+var_70], rdx; char *
0x1800113ad  lea     rax, aReceivedUnknow; "Received unknown I/O command on %s chan"...
0x1800113b4  mov     qword ptr [rsp+98h+var_78], rax; int
0x1800113b9  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800113c0  mov     edx, 1D0h; void *
0x1800113c5  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800113cb  lea     rcx, [rdi+218h]
0x1800113d2  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800113d7  mov     rdx, rax
0x1800113da  test    ebx, ebx
0x1800113dc  jle     short loc_1800113E7
0x1800113de  movzx   ebx, bx
0x1800113e1  or      ebx, 80070000h
0x1800113e7  mov     ecx, ebx
0x1800113e9  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800113ee  mov     r9d, eax; char *
0x1800113f1  mov     rcx, [rsp+98h]; this
0x1800113f9  mov     [rsp+98h+var_70], rdx; char *
0x1800113fe  lea     rax, aFailedToReadFr; "Failed to read from %s file I/O channel"
0x180011405  mov     qword ptr [rsp+98h+var_78], rax; int
0x18001140a  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011411  mov     edx, 179h; void *
0x180011416  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001141b  lea     rdx, [rsp+98h+var_48]
0x180011420  lea     rcx, [rsp+98h+NumberOfBytesTransferred]
0x180011428  call    ??0?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &)
0x18001142d  mov     rdx, rax
0x180011430  lea     rcx, [rdi+58h]; _Mtx_t
0x180011434  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x180011439  lea     rcx, [rdi+218h]
0x180011440  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180011445  mov     rdx, rax
0x180011448  mov     ecx, esi
0x18001144a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001144f  mov     r9d, eax; char *
0x180011452  mov     rcx, [rsp+98h]; this
0x18001145a  mov     [rsp+98h+var_70], rdx; char *
0x18001145f  lea     rax, aFailedToWriteB; "Failed to write buffer to %s Dvc"
0x180011466  mov     qword ptr [rsp+98h+var_78], rax; int
0x18001146b  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180011472  mov     edx, 1B0h; void *
0x180011477  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
