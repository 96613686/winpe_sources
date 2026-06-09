# Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrameAsync(void *,void *,uint,unsigned __int64,uint,tagRECT *,unsigned __int64,uint,uchar const *)

- ea: `0x180021b78`
- end: `0x18002207f`
- name: `?ProcessFrameAsync@CFrameProcessorShim@Shim@Stack@Rdp@@AEAAXPEAX0I_KIPEAUtagRECT@@1IPEBE@Z`
- size: `1287`
- prototype: `void __fastcall(Rdp::Stack::Shim::CFrameProcessorShim *this, const char *, void *, unsigned int, unsigned __int64, unsigned int, struct tagRECT *, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cf84`

## callees

- `0x18000208c`
- `0x180002f68`
- `0x180003714`
- `0x180007b28`
- `0x18000a0e4`
- `0x18000b1bc`
- `0x18000cea4`
- `0x18000d590`
- `0x18001add8`
- `0x1800201fc`
- `0x180020cec`
- `0x180020e30`
- `0x180020fdc`
- `0x180021048`
- `0x180021b78`
- `0x1800220b0`
- `0x180022fe0`
- `0x1800232c8`
- `0x18002a010`

## string_xrefs

- `0x180022058`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002206d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrameAsync(
        Rdp::Stack::Shim::CFrameProcessorShim *this,
        const char *a2,
        void *a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned int a6,
        struct tagRECT *a7,
        unsigned __int64 a8,
        unsigned int a9,
        unsigned __int8 *a10)
{
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rdi
  int v17; // r9d
  struct ID3D11Texture2D *v18; // rbx
  int v19; // r9d
  struct ID3D11Fence *v20; // rdi
  Rdp::Stack::Shim::CFrameDxBufferShim *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  Rdp::Stack::Shim::CFrameSystemBufferShim *v25; // rbx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rcx
  int v27; // eax
  int v28; // edi
  struct IDXGIDevice2 *DxgiDevice; // rax
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  Rdp::Stack::Shim::CFrameSystemBufferShim *v33; // rbx
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // rcx
  int v35; // eax
  int v36; // [rsp+20h] [rbp-99h]
  int v37; // [rsp+20h] [rbp-99h]
  struct tagRECT *v38; // [rsp+28h] [rbp-91h]
  const char *v39; // [rsp+30h] [rbp-89h]
  const char *v40; // [rsp+60h] [rbp-59h] BYREF
  Rdp::Stack::Shim::CFrameSystemBufferShim *v41; // [rsp+68h] [rbp-51h] BYREF
  struct ID3D11Fence *v42; // [rsp+70h] [rbp-49h] BYREF
  const char *v43; // [rsp+78h] [rbp-41h] BYREF
  struct ID3D11Texture2D *v44; // [rsp+80h] [rbp-39h] BYREF
  _QWORD v45[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v46; // [rsp+98h] [rbp-21h] BYREF
  std::_Ref_count_base *v47; // [rsp+A0h] [rbp-19h]
  __int64 v48; // [rsp+A8h] [rbp-11h] BYREF
  std::_Ref_count_base *v49; // [rsp+B0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+2Fh]
  __int64 v51; // [rsp+F0h] [rbp+37h] BYREF

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x1C3,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    (const char *)0x8000FFFFLL,
    *((_BYTE *)this + 312) == 0,
    (bool)"Frame processor shim is not started",
    v39);
  std::atomic<std::shared_ptr<Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>>>::load(
    (char *)this + 112,
    &v48);
  std::atomic<std::shared_ptr<Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>>>::load(
    (char *)this + 128,
    &v46);
  if ( v48 && (v16 = v46) != 0 )
  {
    Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Texture2D>::GetResourceByHandle(v48, &v44, a2);
    v18 = v44;
    if ( v44 )
    {
      Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>::GetResourceByHandle(v16, &v42, a3);
      v20 = v42;
      if ( v42 )
      {
        if ( *((_BYTE *)this + 313) )
        {
          v21 = (Rdp::Stack::Shim::CFrameDxBufferShim *)operator new(0x128u);
          v22 = Rdp::Stack::Shim::CFrameDxBufferShim::CFrameDxBufferShim(v21, v18, a4, a5, a7, a6, a3, v20, a8, a9, a10);
          v23 = v22 + 88;
          v24 = -v22;
          v25 = (Rdp::Stack::Shim::CFrameSystemBufferShim *)(v23 & -(__int64)(v24 != 0));
          v41 = v25;
          if ( v25 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v23 & -(__int64)(v24 != 0));
          v26 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 38);
          v51 = 0;
          v27 = (**v26)(v26, &GUID_8c63637c_6495_4510_857a_56ecf16a21fd, &v51);
          if ( v27 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v27,
              v36);
          wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
            &v40,
            v25);
          Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::AddFrame((char *)this + 144, &v40, a2);
          wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v40);
          v28 = (*(__int64 (__fastcall **)(__int64, Rdp::Stack::Shim::CFrameSystemBufferShim *))(*(_QWORD *)v51 + 72LL))(
                  v51,
                  v25);
          if ( v28 < 0 )
          {
            Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::ReleaseFrame((char *)this + 144, v45, v25);
            wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(v45);
          }
        }
        else
        {
          v41 = (Rdp::Stack::Shim::CFrameSystemBufferShim *)operator new(0x148u);
          DxgiDevice = Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(*((Rdp::Utils::Graphics::CRenderDevice **)this
                                                                          + 12));
          v30 = Rdp::Stack::Shim::CFrameSystemBufferShim::CFrameSystemBufferShim(v41, DxgiDevice, v18, a4, a5, a7, a6);
          v31 = v30 + 88;
          v32 = -v30;
          v33 = (Rdp::Stack::Shim::CFrameSystemBufferShim *)(v31 & -(__int64)(v32 != 0));
          v41 = v33;
          if ( v33 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v31 & -(__int64)(v32 != 0));
          v34 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 38);
          v51 = 0;
          v35 = (**v34)(v34, &GUID_08cc0257_9444_40c8_85b1_1498bd6fcdfb, &v51);
          if ( v35 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v35,
              v37);
          wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
            &v40,
            v33);
          Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::AddFrame((char *)this + 144, &v40, a2);
          wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v40);
          v28 = (*(__int64 (__fastcall **)(__int64, Rdp::Stack::Shim::CFrameSystemBufferShim *))(*(_QWORD *)v51 + 72LL))(
                  v51,
                  v33);
          if ( v28 < 0 )
          {
            Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::ReleaseFrame((char *)this + 144, v45, v33);
            wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(v45);
          }
        }
        wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v51);
        wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v41);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
          (const char *)(unsigned int)v28,
          (int)"Failed to schedule frame processing",
          (const char *)v38);
      }
      else if ( (unsigned int)dword_18003C058 > 3 )
      {
        v45[0] = a3;
        v43 = "Failed to obtain shared fence handle, skipping frame";
        v40 = "Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrameAsync";
        LODWORD(v51) = 485;
        v41 = (Rdp::Stack::Shim::CFrameSystemBufferShim *)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\fram"
                                                          "eprocessorshim.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)&dword_180036044,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
          v19,
          (__int64)&v41,
          (__int64)&v51,
          (__int64)&v40,
          (__int64)&v43,
          (__int64)v45);
      }
      wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v42);
    }
    else if ( (unsigned int)dword_18003C058 > 3 )
    {
      v40 = a2;
      v42 = (struct ID3D11Fence *)"Failed to obtain shared texture by handle, skipping frame";
      v43 = "Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrameAsync";
      LODWORD(v51) = 474;
      v45[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_18003C058,
        (unsigned int)&word_180036096,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
        v17,
        (__int64)v45,
        (__int64)&v51,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v40);
    }
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v44);
  }
  else if ( (unsigned int)dword_18003C058 > 3 )
  {
    v41 = (Rdp::Stack::Shim::CFrameSystemBufferShim *)"Failed to obtain shared resource pools, skipping frame";
    v45[0] = "Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrameAsync";
    LODWORD(v51) = 460;
    v43 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)word_1800360EA,
      v14,
      v15,
      (__int64)&v43,
      (__int64)&v51,
      (__int64)v45,
      (__int64)&v41);
  }
  if ( v47 )
    std::_Ref_count_base::_Decref(v47);
  if ( v49 )
    std::_Ref_count_base::_Decref(v49);
}

```

## disassembly

```asm
0x180021b78  mov     [rsp-8+arg_8], rbx
0x180021b7d  mov     [rsp-8+arg_10], rsi
0x180021b82  push    rbp
0x180021b83  push    rdi
0x180021b84  push    r12
0x180021b86  push    r14
0x180021b88  push    r15
0x180021b8a  lea     rbp, [rsp-7]
0x180021b8f  sub     rsp, 0C0h
0x180021b96  mov     r12d, r9d
0x180021b99  mov     r14, r8
0x180021b9c  mov     r15, rdx
0x180021b9f  mov     rsi, rcx
0x180021ba2  cmp     byte ptr [rcx+138h], 0
0x180021ba9  setz    al
0x180021bac  mov     rcx, [rbp+2Fh]; this
0x180021bb0  lea     rdx, aFrameProcessor; "Frame processor shim is not started"
0x180021bb7  mov     [rsp+0E0h+var_B8], rdx; bool
0x180021bbc  mov     byte ptr [rsp+0E0h+var_C0], al; char
0x180021bc0  mov     r9d, 8000FFFFh; char *
0x180021bc6  lea     rbx, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180021bcd  mov     r8, rbx; unsigned int
0x180021bd0  mov     edx, 1C3h; void *
0x180021bd5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180021bda  lea     rcx, [rsi+70h]
0x180021bde  lea     rdx, [rbp+27h+var_38]
0x180021be2  call    ?load@?$atomic@V?$shared_ptr@V?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@@std@@@std@@QEBA?AV?$shared_ptr@V?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>>>::load(std::memory_order)
0x180021be7  nop
0x180021be8  lea     rcx, [rsi+80h]
0x180021bef  lea     rdx, [rbp+27h+var_48]
0x180021bf3  call    ?load@?$atomic@V?$shared_ptr@V?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@@std@@@std@@QEBA?AV?$shared_ptr@V?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>>>::load(std::memory_order)
0x180021bf8  nop
0x180021bf9  mov     rcx, [rbp+27h+var_38]
0x180021bfd  test    rcx, rcx
0x180021c00  jz      loc_180021FB8
0x180021c06  mov     rdi, [rbp+27h+var_48]
0x180021c0a  test    rdi, rdi
0x180021c0d  jz      loc_180021FB8
0x180021c13  mov     r8, r15
0x180021c16  lea     rdx, [rbp+27h+var_60]
0x180021c1a  call    ?GetResourceByHandle@?$CSharedResourcePoolOwner@UID3D11Texture2D@@@Graphics@Utils@Rdp@@QEAA?AV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@PEAX@Z; Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Texture2D>::GetResourceByHandle(void *)
0x180021c1f  nop
0x180021c20  mov     rbx, [rbp+27h+var_60]
0x180021c24  test    rbx, rbx
0x180021c27  jnz     loc_180021CB3
0x180021c2d  mov     eax, cs:dword_18003C058
0x180021c33  cmp     eax, 3
0x180021c36  jbe     short loc_180021CA5
0x180021c38  mov     [rbp+27h+var_80], r15
0x180021c3c  lea     rax, aFailedToObtain_0; "Failed to obtain shared texture by hand"...
0x180021c43  mov     [rbp+27h+var_70], rax
0x180021c47  lea     rax, aRdpStackShimCf; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x180021c4e  mov     [rbp+27h+var_68], rax
0x180021c52  mov     dword ptr [rbp+27h+arg_0], 1DAh
0x180021c59  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180021c60  mov     [rbp+27h+var_58], r8
0x180021c64  lea     rax, [rbp+27h+var_80]
0x180021c68  mov     [rsp+0E0h+var_A0], rax
0x180021c6d  lea     rax, [rbp+27h+var_70]
0x180021c71  mov     [rsp+0E0h+var_A8], rax
0x180021c76  lea     rax, [rbp+27h+var_68]
0x180021c7a  mov     [rsp+0E0h+var_B0], rax
0x180021c7f  lea     rax, [rbp+27h+arg_0]
0x180021c83  mov     [rsp+0E0h+var_B8], rax
0x180021c88  lea     rax, [rbp+27h+var_58]
0x180021c8c  mov     [rsp+0E0h+var_C0], rax
0x180021c91  lea     rdx, word_180036096
0x180021c98  lea     rcx, dword_18003C058
0x180021c9f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180021ca4  nop
0x180021ca5  lea     rcx, [rbp+27h+var_60]
0x180021ca9  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021cae  jmp     loc_18002201C
0x180021cb3  mov     r8, r14
0x180021cb6  lea     rdx, [rbp+27h+var_70]
0x180021cba  mov     rcx, rdi
0x180021cbd  call    ?GetResourceByHandle@?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@QEAA?AV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@PEAX@Z; Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>::GetResourceByHandle(void *)
0x180021cc2  nop
0x180021cc3  mov     rdi, [rbp+27h+var_70]
0x180021cc7  test    rdi, rdi
0x180021cca  jnz     loc_180021D56
0x180021cd0  mov     eax, cs:dword_18003C058
0x180021cd6  cmp     eax, 3
0x180021cd9  jbe     short loc_180021D48
0x180021cdb  mov     [rbp+27h+var_58], r14
0x180021cdf  lea     rax, aFailedToObtain; "Failed to obtain shared fence handle, s"...
0x180021ce6  mov     [rbp+27h+var_68], rax
0x180021cea  lea     rax, aRdpStackShimCf; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x180021cf1  mov     [rbp+27h+var_80], rax
0x180021cf5  mov     dword ptr [rbp+27h+arg_0], 1E5h
0x180021cfc  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180021d03  mov     [rbp+27h+var_78], r8
0x180021d07  lea     rax, [rbp+27h+var_58]
0x180021d0b  mov     [rsp+0E0h+var_A0], rax
0x180021d10  lea     rax, [rbp+27h+var_68]
0x180021d14  mov     [rsp+0E0h+var_A8], rax
0x180021d19  lea     rax, [rbp+27h+var_80]
0x180021d1d  mov     [rsp+0E0h+var_B0], rax
0x180021d22  lea     rax, [rbp+27h+arg_0]
0x180021d26  mov     [rsp+0E0h+var_B8], rax
0x180021d2b  lea     rax, [rbp+27h+var_78]
0x180021d2f  mov     [rsp+0E0h+var_C0], rax
0x180021d34  lea     rdx, dword_180036044
0x180021d3b  lea     rcx, dword_18003C058
0x180021d42  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180021d47  nop
0x180021d48  lea     rcx, [rbp+27h+var_70]
0x180021d4c  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021d51  jmp     loc_180021CA5
0x180021d56  cmp     byte ptr [rsi+139h], 0
0x180021d5d  jz      loc_180021E83
0x180021d63  mov     ecx, 128h; Size
0x180021d68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021d6d  mov     [rbp+27h+var_78], rax
0x180021d71  mov     rcx, [rbp+27h+arg_48]
0x180021d75  mov     [rsp+0E0h+var_90], rcx; unsigned __int8 *
0x180021d7a  mov     ecx, [rbp+27h+arg_40]
0x180021d7d  mov     [rsp+0E0h+var_98], ecx; unsigned int
0x180021d81  mov     rcx, [rbp+27h+arg_38]
0x180021d85  mov     [rsp+0E0h+var_A0], rcx; unsigned __int64
0x180021d8a  mov     [rsp+0E0h+var_A8], rdi; struct ID3D11Fence *
0x180021d8f  mov     [rsp+0E0h+var_B0], r14; void *
0x180021d94  mov     ecx, [rbp+27h+arg_28]
0x180021d97  mov     dword ptr [rsp+0E0h+var_B8], ecx; unsigned int
0x180021d9b  mov     rcx, [rbp+27h+arg_30]
0x180021d9f  mov     [rsp+0E0h+var_C0], rcx; int
0x180021da4  mov     r9, [rbp+27h+arg_20]; unsigned __int64
0x180021da8  mov     r8d, r12d; unsigned int
0x180021dab  mov     rdx, rbx; struct ID3D11Texture2D *
0x180021dae  mov     rcx, rax; this
0x180021db1  call    ??0CFrameDxBufferShim@Shim@Stack@Rdp@@QEAA@PEAUID3D11Texture2D@@I_KPEAUtagRECT@@IPEAXPEAUID3D11Fence@@1IPEBE@Z; Rdp::Stack::Shim::CFrameDxBufferShim::CFrameDxBufferShim(ID3D11Texture2D *,uint,unsigned __int64,tagRECT *,uint,void *,ID3D11Fence *,unsigned __int64,uint,uchar const *)
0x180021db6  nop
0x180021db7  lea     rcx, [rax+58h]
0x180021dbb  neg     rax
0x180021dbe  sbb     rbx, rbx
0x180021dc1  and     rbx, rcx
0x180021dc4  mov     [rbp+27h+var_78], rbx
0x180021dc8  jz      short loc_180021DDA
0x180021dca  mov     rax, [rbx]
0x180021dcd  mov     rcx, rbx
0x180021dd0  mov     rax, [rax+8]
0x180021dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dd9  nop
0x180021dda  mov     rcx, [rsi+130h]
0x180021de1  mov     [rbp+27h+arg_0], 0
0x180021de9  mov     rax, [rcx]
0x180021dec  lea     r8, [rbp+27h+arg_0]
0x180021df0  lea     rdx, _GUID_8c63637c_6495_4510_857a_56ecf16a21fd
0x180021df7  mov     rax, [rax]
0x180021dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dff  mov     rcx, [rbp+2Fh]; this
0x180021e03  test    eax, eax
0x180021e05  js      loc_18002206A
0x180021e0b  mov     rdx, rbx
0x180021e0e  lea     rcx, [rbp+27h+var_80]
0x180021e12  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180021e17  nop
0x180021e18  mov     r8, r15
0x180021e1b  lea     rdx, [rbp+27h+var_80]
0x180021e1f  lea     rcx, [rsi+90h]
0x180021e26  call    ?AddFrame@AsyncFrameBufferPool@CFrameProcessorShim@Shim@Stack@Rdp@@QEAAXAEBV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@Z; Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::AddFrame(wil::com_ptr_t<IUnknown,wil::err_exception_policy> const &,void *)
0x180021e2b  nop
0x180021e2c  lea     rcx, [rbp+27h+var_80]
0x180021e30  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021e35  mov     rcx, [rbp+27h+arg_0]
0x180021e39  mov     rax, [rcx]
0x180021e3c  mov     rdx, rbx
0x180021e3f  mov     rax, [rax+48h]
0x180021e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e48  mov     edi, eax
0x180021e4a  test    eax, eax
0x180021e4c  jns     short loc_180021E6B
0x180021e4e  mov     r8, rbx
0x180021e51  lea     rdx, [rbp+27h+var_58]
0x180021e55  lea     rcx, [rsi+90h]
0x180021e5c  call    ?ReleaseFrame@AsyncFrameBufferPool@CFrameProcessorShim@Shim@Stack@Rdp@@QEAA?AU?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@PEAUIUnknown@@@Z; Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::ReleaseFrame(IUnknown *)
0x180021e61  lea     rcx, [rbp+27h+var_58]
0x180021e65  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021e6a  nop
0x180021e6b  lea     rcx, [rbp+27h+arg_0]
0x180021e6f  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021e74  nop
0x180021e75  lea     rcx, [rbp+27h+var_78]
0x180021e79  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021e7e  jmp     loc_180021F8F
0x180021e83  mov     ecx, 148h; Size
0x180021e88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021e8d  mov     rdi, rax
0x180021e90  mov     [rbp+27h+var_78], rax
0x180021e94  mov     rcx, [rsi+60h]; this
0x180021e98  call    ?GetDxgiDevice@CRenderDevice@Graphics@Utils@Rdp@@QEAAPEAUIDXGIDevice2@@XZ; Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(void)
0x180021e9d  mov     ecx, [rbp+27h+arg_28]
0x180021ea0  mov     dword ptr [rsp+0E0h+var_B0], ecx; unsigned int
0x180021ea4  mov     rcx, [rbp+27h+arg_30]
0x180021ea8  mov     [rsp+0E0h+var_B8], rcx; char *
0x180021ead  mov     rcx, [rbp+27h+arg_20]
0x180021eb1  mov     [rsp+0E0h+var_C0], rcx; int
0x180021eb6  mov     r9d, r12d; unsigned int
0x180021eb9  mov     r8, rbx; struct ID3D11Texture2D *
0x180021ebc  mov     rdx, rax; struct IDXGIDevice2 *
0x180021ebf  mov     rcx, rdi; this
0x180021ec2  call    ??0CFrameSystemBufferShim@Shim@Stack@Rdp@@QEAA@PEAUIDXGIDevice2@@PEAUID3D11Texture2D@@I_KPEAUtagRECT@@I@Z; Rdp::Stack::Shim::CFrameSystemBufferShim::CFrameSystemBufferShim(IDXGIDevice2 *,ID3D11Texture2D *,uint,unsigned __int64,tagRECT *,uint)
0x180021ec7  nop
0x180021ec8  lea     rcx, [rax+58h]
0x180021ecc  neg     rax
0x180021ecf  sbb     rbx, rbx
0x180021ed2  and     rbx, rcx
0x180021ed5  mov     [rbp+27h+var_78], rbx
0x180021ed9  jz      short loc_180021EEB
0x180021edb  mov     rax, [rbx]
0x180021ede  mov     rcx, rbx
0x180021ee1  mov     rax, [rax+8]
0x180021ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021eea  nop
0x180021eeb  mov     rcx, [rsi+130h]
0x180021ef2  mov     [rbp+27h+arg_0], 0
0x180021efa  mov     rax, [rcx]
0x180021efd  lea     r8, [rbp+27h+arg_0]
0x180021f01  lea     rdx, _GUID_08cc0257_9444_40c8_85b1_1498bd6fcdfb
0x180021f08  mov     rax, [rax]
0x180021f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f10  mov     rcx, [rbp+2Fh]; this
0x180021f14  test    eax, eax
0x180021f16  js      loc_180022055
0x180021f1c  mov     rdx, rbx
0x180021f1f  lea     rcx, [rbp+27h+var_80]
0x180021f23  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180021f28  nop
0x180021f29  mov     r8, r15
0x180021f2c  lea     rdx, [rbp+27h+var_80]
0x180021f30  lea     rcx, [rsi+90h]
0x180021f37  call    ?AddFrame@AsyncFrameBufferPool@CFrameProcessorShim@Shim@Stack@Rdp@@QEAAXAEBV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@Z; Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::AddFrame(wil::com_ptr_t<IUnknown,wil::err_exception_policy> const &,void *)
0x180021f3c  nop
0x180021f3d  lea     rcx, [rbp+27h+var_80]
0x180021f41  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021f46  mov     rcx, [rbp+27h+arg_0]
0x180021f4a  mov     rax, [rcx]
0x180021f4d  mov     rdx, rbx
0x180021f50  mov     rax, [rax+48h]
0x180021f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f59  mov     edi, eax
0x180021f5b  test    eax, eax
0x180021f5d  jns     short loc_180021F7C
0x180021f5f  mov     r8, rbx
0x180021f62  lea     rdx, [rbp+27h+var_58]
0x180021f66  lea     rcx, [rsi+90h]
0x180021f6d  call    ?ReleaseFrame@AsyncFrameBufferPool@CFrameProcessorShim@Shim@Stack@Rdp@@QEAA?AU?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@PEAUIUnknown@@@Z; Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::ReleaseFrame(IUnknown *)
0x180021f72  lea     rcx, [rbp+27h+var_58]
0x180021f76  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021f7b  nop
0x180021f7c  lea     rcx, [rbp+27h+arg_0]
0x180021f80  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021f85  nop
0x180021f86  lea     rcx, [rbp+27h+var_78]
0x180021f8a  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021f8f  mov     rcx, [rbp+2Fh]; this
0x180021f93  lea     rax, aFailedToSchedu; "Failed to schedule frame processing"
0x180021f9a  mov     [rsp+0E0h+var_C0], rax; int
0x180021f9f  mov     r9d, edi; char *
0x180021fa2  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180021fa9  mov     edx, 221h; void *
0x180021fae  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180021fb3  jmp     loc_180021D48
0x180021fb8  mov     eax, cs:dword_18003C058
0x180021fbe  cmp     eax, 3
0x180021fc1  jbe     short loc_18002201C
0x180021fc3  lea     rax, aFailedToObtain_1; "Failed to obtain shared resource pools,"...
0x180021fca  mov     [rbp+27h+var_78], rax
0x180021fce  lea     rax, aRdpStackShimCf; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x180021fd5  mov     [rbp+27h+var_58], rax
0x180021fd9  mov     dword ptr [rbp+27h+arg_0], 1CCh
0x180021fe0  mov     [rbp+27h+var_68], rbx
0x180021fe4  lea     rax, [rbp+27h+var_78]
0x180021fe8  mov     [rsp+0E0h+var_A8], rax
0x180021fed  lea     rax, [rbp+27h+var_58]
0x180021ff1  mov     [rsp+0E0h+var_B0], rax
0x180021ff6  lea     rax, [rbp+27h+arg_0]
0x180021ffa  mov     [rsp+0E0h+var_B8], rax
0x180021fff  lea     rax, [rbp+27h+var_68]
0x180022003  mov     [rsp+0E0h+var_C0], rax
0x180022008  lea     rdx, word_1800360EA
0x18002200f  lea     rcx, dword_18003C058
0x180022016  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18002201b  nop
0x18002201c  mov     rcx, [rbp+27h+var_40]; this
0x180022020  test    rcx, rcx
0x180022023  jz      short loc_18002202B
0x180022025  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002202a  nop
0x18002202b  mov     rcx, [rbp+27h+var_30]; this
0x18002202f  test    rcx, rcx
0x180022032  jz      short loc_180022039
0x180022034  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022039  lea     r11, [rsp+0E0h+var_20]
0x180022041  mov     rbx, [r11+38h]
0x180022045  mov     rsi, [r11+40h]
0x180022049  mov     rsp, r11
0x18002204c  pop     r15
0x18002204e  pop     r14
0x180022050  pop     r12
  ... truncated ...
```
