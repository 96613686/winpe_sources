# Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrame(void *,void *,uint,unsigned __int64,uint,tagRECT *,unsigned __int64,uint,uchar const *)

- ea: `0x180021640`
- end: `0x180021b70`
- name: `?ProcessFrame@CFrameProcessorShim@Shim@Stack@Rdp@@AEAAXPEAX0I_KIPEAUtagRECT@@1IPEBE@Z`
- size: `1328`
- prototype: `void __fastcall(Rdp::Stack::Shim::CFrameProcessorShim *this, struct ID3D11Fence *, void *, unsigned int, const char *, unsigned int, struct tagRECT *, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cf84`

## callees

- `0x18000208c`
- `0x180002f68`
- `0x180003080`
- `0x180007b28`
- `0x18000b1bc`
- `0x18000cea4`
- `0x18000d590`
- `0x18001971c`
- `0x18001add8`
- `0x1800201fc`
- `0x18002097c`
- `0x180020e30`
- `0x180020fdc`
- `0x180021048`
- `0x180021640`
- `0x180022fe0`
- `0x1800232c8`
- `0x180023510`
- `0x18002a010`

## string_xrefs

- `0x180021b49`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180021b5e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrame(
        Rdp::Stack::Shim::CFrameProcessorShim *this,
        struct ID3D11Fence *a2,
        void *a3,
        unsigned int a4,
        const char *a5,
        unsigned int a6,
        struct tagRECT *a7,
        unsigned __int64 a8,
        unsigned int a9,
        unsigned __int8 *a10)
{
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rdi
  int v17; // r8d
  int v18; // r9d
  struct ID3D11Texture2D *v19; // rbx
  int v20; // r8d
  int v21; // r9d
  struct ID3D11Fence *v22; // rdi
  unsigned __int64 v23; // r15
  __int64 (__fastcall ***v24)(_QWORD, GUID *, const char **); // rcx
  int v25; // eax
  unsigned int v26; // ebx
  struct IDXGIDevice2 *DxgiDevice; // rax
  __int64 (__fastcall ***v28)(_QWORD, GUID *, const char **); // rcx
  int v29; // eax
  __int64 v30; // rax
  Rdp::Stack::Shim::CAdapterShim *v31; // rdi
  unsigned __int64 v32; // rbx
  const struct _GUID *v33; // rax
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  struct tagRECT *v36; // [rsp+28h] [rbp-D8h]
  const char *v37; // [rsp+30h] [rbp-D0h]
  const char *v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h] BYREF
  const char *v40; // [rsp+70h] [rbp-90h] BYREF
  struct ID3D11Fence *v41; // [rsp+78h] [rbp-88h] BYREF
  const char *v42; // [rsp+80h] [rbp-80h] BYREF
  const char *v43; // [rsp+88h] [rbp-78h] BYREF
  const char *v44; // [rsp+90h] [rbp-70h] BYREF
  struct ID3D11Texture2D *v45; // [rsp+98h] [rbp-68h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v49; // [rsp+B8h] [rbp-48h]
  _BYTE v50[8]; // [rsp+C0h] [rbp-40h] BYREF
  signed __int32 v51[18]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v52[320]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]
  char v54; // [rsp+260h] [rbp+160h] BYREF

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x127,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    (const char *)0x8000FFFFLL,
    *((_BYTE *)this + 312) == 0,
    (bool)"Frame processor shim is not started",
    v37);
  std::atomic<std::shared_ptr<Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>>>::load(
    (char *)this + 112,
    &v48);
  std::atomic<std::shared_ptr<Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>>>::load(
    (char *)this + 128,
    &v46);
  if ( v48 && (v16 = v46) != 0 )
  {
    Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Texture2D>::GetResourceByHandle(v48, &v45, a2);
    v19 = v45;
    if ( v45 )
    {
      Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>::GetResourceByHandle(v16, &v41, a3);
      v22 = v41;
      if ( v41 )
      {
        v54 = 0;
        v23 = (unsigned __int64)a5;
        if ( (unsigned int)dword_18003C058 > 5 )
        {
          v39 = *((unsigned __int8 *)this + 313);
          v40 = a5;
          v42 = "Start";
          v43 = "Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrame";
          LODWORD(v38) = 341;
          v44 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18003C058,
            (unsigned int)&byte_180036127,
            v20,
            v21,
            (__int64)&v44,
            (__int64)&v38,
            (__int64)&v43,
            (__int64)&v42,
            (__int64)&v40,
            (__int64)&v39);
        }
        if ( *((_BYTE *)this + 313) )
        {
          Rdp::Stack::Shim::CFrameDxBufferShim::CFrameDxBufferShim(
            (Rdp::Stack::Shim::CFrameDxBufferShim *)v50,
            v19,
            a4,
            v23,
            a7,
            a6,
            a3,
            v22,
            a8,
            a9,
            a10);
          _InterlockedIncrement(v51);
          v24 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))*((_QWORD *)this + 38);
          v38 = 0;
          v25 = (**v24)(v24, &GUID_69d16ddb_b90e_47d0_865d_b8f17e7dad6d, &v38);
          if ( v25 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v25,
              v34);
          v26 = (*(__int64 (__fastcall **)(const char *, _BYTE *, char *))(*(_QWORD *)v38 + 64LL))(v38, v52, &v54);
          wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v38);
          Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameDxBuffer,Rdp::Avenc::IFrameBuffer1>::~CFrameBufferShim<Rdp::Avenc::IFrameDxBuffer,Rdp::Avenc::IFrameBuffer1>(v50);
        }
        else
        {
          DxgiDevice = Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(*((Rdp::Utils::Graphics::CRenderDevice **)this
                                                                          + 12));
          Rdp::Stack::Shim::CFrameSystemBufferShim::CFrameSystemBufferShim(
            (Rdp::Stack::Shim::CFrameSystemBufferShim *)v50,
            DxgiDevice,
            v19,
            a4,
            v23,
            a7,
            a6);
          _InterlockedIncrement(v51);
          v28 = (__int64 (__fastcall ***)(_QWORD, GUID *, const char **))*((_QWORD *)this + 38);
          v38 = 0;
          v29 = (**v28)(v28, &GUID_743ce3e5_a291_458d_ab1b_3fc4e1445c48, &v38);
          if ( v29 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v29,
              v35);
          v26 = (*(__int64 (__fastcall **)(const char *, _BYTE *, char *))(*(_QWORD *)v38 + 64LL))(v38, v52, &v54);
          wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v38);
          Rdp::Stack::Shim::CFrameSystemBufferShim::~CFrameSystemBufferShim((Rdp::Stack::Shim::CFrameSystemBufferShim *)v50);
        }
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x180,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
          (const char *)v26,
          (int)"Failed to process frame",
          (const char *)v36);
        v30 = *((_QWORD *)this + 37);
        v31 = *(Rdp::Stack::Shim::CAdapterShim **)(v30 + 232);
        v32 = *((_QWORD *)this + 36);
        v33 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v30 + 240) + 40LL))(*(_QWORD *)(v30 + 240));
        Rdp::Stack::Shim::CAdapterShim::OnReleaseResource(v31, v33, v32, a2, a3);
      }
      else if ( (unsigned int)dword_18003C058 > 3 )
      {
        v44 = (const char *)a3;
        v43 = "Failed to obtain shared fence handle, skipping frame";
        v40 = "Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrame";
        LODWORD(v38) = 329;
        v42 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          (unsigned int)&dword_18003C058,
          (unsigned int)&dword_18003618C,
          v20,
          v21,
          (__int64)&v42,
          (__int64)&v38,
          (__int64)&v40,
          (__int64)&v43,
          (__int64)&v44);
      }
      wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v41);
    }
    else if ( (unsigned int)dword_18003C058 > 3 )
    {
      v41 = a2;
      v38 = "Failed to obtain shared texture by handle, skipping frame";
      v42 = "Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrame";
      v39 = 318;
      v40 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_18003C058,
        (unsigned int)&word_1800361DE,
        v17,
        v18,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v42,
        (__int64)&v38,
        (__int64)&v41);
    }
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v45);
  }
  else if ( (unsigned int)dword_18003C058 > 3 )
  {
    v44 = "Failed to obtain shared resource pools, skipping frame";
    v43 = "Rdp::Stack::Shim::CFrameProcessorShim::ProcessFrame";
    LODWORD(v38) = 304;
    v40 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)word_180036232,
      v14,
      v15,
      (__int64)&v40,
      (__int64)&v38,
      (__int64)&v43,
      (__int64)&v44);
  }
  if ( v47 )
    std::_Ref_count_base::_Decref(v47);
  if ( v49 )
    std::_Ref_count_base::_Decref(v49);
}

```

## disassembly

```asm
0x180021640  push    rbp
0x180021642  push    rbx
0x180021643  push    rsi
0x180021644  push    rdi
0x180021645  push    r12
0x180021647  push    r13
0x180021649  push    r14
0x18002164b  push    r15
0x18002164d  lea     rbp, [rsp-118h]
0x180021655  sub     rsp, 218h
0x18002165c  mov     r13d, r9d
0x18002165f  mov     r14, r8
0x180021662  mov     r12, rdx
0x180021665  mov     rsi, rcx
0x180021668  xor     r15d, r15d
0x18002166b  cmp     [rcx+138h], r15b
0x180021672  setz    al
0x180021675  mov     rcx, [rbp+158h]; this
0x18002167c  lea     rdx, aFrameProcessor; "Frame processor shim is not started"
0x180021683  mov     [rsp+250h+var_228], rdx; bool
0x180021688  mov     byte ptr [rsp+250h+var_230], al; char
0x18002168c  mov     r9d, 8000FFFFh; char *
0x180021692  lea     rbx, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180021699  mov     r8, rbx; unsigned int
0x18002169c  mov     edx, 127h; void *
0x1800216a1  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800216a6  lea     rcx, [rsi+70h]
0x1800216aa  lea     rdx, [rbp+150h+var_1A0]
0x1800216ae  call    ?load@?$atomic@V?$shared_ptr@V?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@@std@@@std@@QEBA?AV?$shared_ptr@V?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>>>::load(std::memory_order)
0x1800216b3  nop
0x1800216b4  lea     rcx, [rsi+80h]
0x1800216bb  lea     rdx, [rbp+150h+var_1B0]
0x1800216bf  call    ?load@?$atomic@V?$shared_ptr@V?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@@std@@@std@@QEBA?AV?$shared_ptr@V?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>>>::load(std::memory_order)
0x1800216c4  nop
0x1800216c5  mov     rcx, [rbp+150h+var_1A0]
0x1800216c9  test    rcx, rcx
0x1800216cc  jz      loc_180021AAD
0x1800216d2  mov     rdi, [rbp+150h+var_1B0]
0x1800216d6  test    rdi, rdi
0x1800216d9  jz      loc_180021AAD
0x1800216df  mov     r8, r12
0x1800216e2  lea     rdx, [rbp+150h+var_1B8]
0x1800216e6  call    ?GetResourceByHandle@?$CSharedResourcePoolOwner@UID3D11Texture2D@@@Graphics@Utils@Rdp@@QEAA?AV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@PEAX@Z; Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Texture2D>::GetResourceByHandle(void *)
0x1800216eb  nop
0x1800216ec  mov     rbx, [rbp+150h+var_1B8]
0x1800216f0  test    rbx, rbx
0x1800216f3  jnz     loc_180021787
0x1800216f9  mov     eax, cs:dword_18003C058
0x1800216ff  cmp     eax, 3
0x180021702  jbe     short loc_180021779
0x180021704  mov     [rsp+250h+var_1D8], r12
0x180021709  lea     rax, aFailedToObtain_0; "Failed to obtain shared texture by hand"...
0x180021710  mov     [rsp+250h+var_1F0], rax
0x180021715  lea     rax, aRdpStackShimCf_0; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x18002171c  mov     [rbp+150h+var_1D0], rax
0x180021720  mov     [rsp+250h+var_1E8], 13Eh
0x180021728  lea     rax, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002172f  mov     [rsp+250h+var_1E0], rax
0x180021734  lea     rax, [rsp+250h+var_1D8]
0x180021739  mov     [rsp+250h+var_210], rax
0x18002173e  lea     rax, [rsp+250h+var_1F0]
0x180021743  mov     [rsp+250h+var_218], rax
0x180021748  lea     rax, [rbp+150h+var_1D0]
0x18002174c  mov     [rsp+250h+var_220], rax
0x180021751  lea     rax, [rsp+250h+var_1E8]
0x180021756  mov     [rsp+250h+var_228], rax
0x18002175b  lea     rax, [rsp+250h+var_1E0]
0x180021760  mov     [rsp+250h+var_230], rax
0x180021765  lea     rdx, word_1800361DE
0x18002176c  lea     rcx, dword_18003C058
0x180021773  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180021778  nop
0x180021779  lea     rcx, [rbp+150h+var_1B8]
0x18002177d  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021782  jmp     loc_180021B15
0x180021787  mov     r8, r14
0x18002178a  lea     rdx, [rsp+250h+var_1D8]
0x18002178f  mov     rcx, rdi
0x180021792  call    ?GetResourceByHandle@?$CSharedResourcePoolOwner@UID3D11Fence@@@Graphics@Utils@Rdp@@QEAA?AV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@PEAX@Z; Rdp::Utils::Graphics::CSharedResourcePoolOwner<ID3D11Fence>::GetResourceByHandle(void *)
0x180021797  nop
0x180021798  mov     rdi, [rsp+250h+var_1D8]
0x18002179d  mov     eax, cs:dword_18003C058
0x1800217a3  test    rdi, rdi
0x1800217a6  jz      loc_180021A33
0x1800217ac  mov     [rbp+150h+arg_0], r15b
0x1800217b3  mov     r15, [rbp+150h+arg_20]
0x1800217ba  cmp     eax, 5
0x1800217bd  jbe     loc_180021848
0x1800217c3  movzx   eax, byte ptr [rsi+139h]
0x1800217ca  mov     [rsp+250h+var_1E8], eax
0x1800217ce  mov     [rsp+250h+var_1E0], r15
0x1800217d3  lea     rax, aStart; "Start"
0x1800217da  mov     [rbp+150h+var_1D0], rax
0x1800217de  lea     rax, aRdpStackShimCf_0; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x1800217e5  mov     [rbp+150h+var_1C8], rax
0x1800217e9  mov     dword ptr [rsp+250h+var_1F0], 155h
0x1800217f1  lea     rax, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800217f8  mov     [rbp+150h+var_1C0], rax
0x1800217fc  lea     rax, [rsp+250h+var_1E8]
0x180021801  mov     qword ptr [rsp+250h+var_208], rax
0x180021806  lea     rax, [rsp+250h+var_1E0]
0x18002180b  mov     [rsp+250h+var_210], rax
0x180021810  lea     rax, [rbp+150h+var_1D0]
0x180021814  mov     [rsp+250h+var_218], rax
0x180021819  lea     rax, [rbp+150h+var_1C8]
0x18002181d  mov     [rsp+250h+var_220], rax
0x180021822  lea     rax, [rsp+250h+var_1F0]
0x180021827  mov     [rsp+250h+var_228], rax
0x18002182c  lea     rax, [rbp+150h+var_1C0]
0x180021830  mov     [rsp+250h+var_230], rax
0x180021835  lea     rdx, byte_180036127
0x18002183c  lea     rcx, dword_18003C058
0x180021843  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180021848  cmp     byte ptr [rsi+139h], 0
0x18002184f  jz      loc_18002191B
0x180021855  mov     rax, [rbp+150h+arg_48]
0x18002185c  mov     [rsp+250h+var_200], rax; unsigned __int8 *
0x180021861  mov     eax, [rbp+150h+arg_40]
0x180021867  mov     [rsp+250h+var_208], eax; unsigned int
0x18002186b  mov     rax, [rbp+150h+arg_38]
0x180021872  mov     [rsp+250h+var_210], rax; unsigned __int64
0x180021877  mov     [rsp+250h+var_218], rdi; struct ID3D11Fence *
0x18002187c  mov     [rsp+250h+var_220], r14; void *
0x180021881  mov     eax, [rbp+150h+arg_28]
0x180021887  mov     dword ptr [rsp+250h+var_228], eax; unsigned int
0x18002188b  mov     rax, [rbp+150h+arg_30]
0x180021892  mov     [rsp+250h+var_230], rax; int
0x180021897  mov     r9, r15; unsigned __int64
0x18002189a  mov     r8d, r13d; unsigned int
0x18002189d  mov     rdx, rbx; struct ID3D11Texture2D *
0x1800218a0  lea     rcx, [rbp+150h+var_190]; this
0x1800218a4  call    ??0CFrameDxBufferShim@Shim@Stack@Rdp@@QEAA@PEAUID3D11Texture2D@@I_KPEAUtagRECT@@IPEAXPEAUID3D11Fence@@1IPEBE@Z; Rdp::Stack::Shim::CFrameDxBufferShim::CFrameDxBufferShim(ID3D11Texture2D *,uint,unsigned __int64,tagRECT *,uint,void *,ID3D11Fence *,unsigned __int64,uint,uchar const *)
0x1800218a9  nop
0x1800218aa  lock inc [rbp+150h+var_188]
0x1800218ae  mov     rcx, [rsi+130h]
0x1800218b5  mov     [rsp+250h+var_1F0], 0
0x1800218be  mov     rax, [rcx]
0x1800218c1  lea     r8, [rsp+250h+var_1F0]
0x1800218c6  lea     rdx, _GUID_69d16ddb_b90e_47d0_865d_b8f17e7dad6d
0x1800218cd  mov     rax, [rax]
0x1800218d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218d5  mov     rcx, [rbp+158h]; this
0x1800218dc  test    eax, eax
0x1800218de  js      loc_180021B5B
0x1800218e4  mov     rcx, [rsp+250h+var_1F0]
0x1800218e9  mov     rax, [rcx]
0x1800218ec  lea     r8, [rbp+150h+arg_0]
0x1800218f3  lea     rdx, [rbp+150h+var_140]
0x1800218f7  mov     rax, [rax+40h]
0x1800218fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021900  mov     ebx, eax
0x180021902  lea     rcx, [rsp+250h+var_1F0]
0x180021907  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18002190c  nop
0x18002190d  lea     rcx, [rbp+150h+var_190]
0x180021911  call    ??1?$CFrameBufferShim@UIFrameDxBuffer@Avenc@Rdp@@UIFrameBuffer1@23@@Shim@Stack@Rdp@@UEAA@XZ; Rdp::Stack::Shim::CFrameBufferShim<Rdp::Avenc::IFrameDxBuffer,Rdp::Avenc::IFrameBuffer1>::~CFrameBufferShim<Rdp::Avenc::IFrameDxBuffer,Rdp::Avenc::IFrameBuffer1>(void)
0x180021916  jmp     loc_1800219BE
0x18002191b  mov     rcx, [rsi+60h]; this
0x18002191f  call    ?GetDxgiDevice@CRenderDevice@Graphics@Utils@Rdp@@QEAAPEAUIDXGIDevice2@@XZ; Rdp::Utils::Graphics::CRenderDevice::GetDxgiDevice(void)
0x180021924  mov     ecx, [rbp+150h+arg_28]
0x18002192a  mov     dword ptr [rsp+250h+var_220], ecx; unsigned int
0x18002192e  mov     rcx, [rbp+150h+arg_30]
0x180021935  mov     [rsp+250h+var_228], rcx; char *
0x18002193a  mov     [rsp+250h+var_230], r15; int
0x18002193f  mov     r9d, r13d; unsigned int
0x180021942  mov     r8, rbx; struct ID3D11Texture2D *
0x180021945  mov     rdx, rax; struct IDXGIDevice2 *
0x180021948  lea     rcx, [rbp+150h+var_190]; this
0x18002194c  call    ??0CFrameSystemBufferShim@Shim@Stack@Rdp@@QEAA@PEAUIDXGIDevice2@@PEAUID3D11Texture2D@@I_KPEAUtagRECT@@I@Z; Rdp::Stack::Shim::CFrameSystemBufferShim::CFrameSystemBufferShim(IDXGIDevice2 *,ID3D11Texture2D *,uint,unsigned __int64,tagRECT *,uint)
0x180021951  nop
0x180021952  lock inc [rbp+150h+var_188]
0x180021956  mov     rcx, [rsi+130h]
0x18002195d  mov     [rsp+250h+var_1F0], 0
0x180021966  mov     rax, [rcx]
0x180021969  lea     r8, [rsp+250h+var_1F0]
0x18002196e  lea     rdx, _GUID_743ce3e5_a291_458d_ab1b_3fc4e1445c48
0x180021975  mov     rax, [rax]
0x180021978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002197d  mov     rcx, [rbp+158h]; this
0x180021984  test    eax, eax
0x180021986  js      loc_180021B46
0x18002198c  mov     rcx, [rsp+250h+var_1F0]
0x180021991  mov     rax, [rcx]
0x180021994  lea     r8, [rbp+150h+arg_0]
0x18002199b  lea     rdx, [rbp+150h+var_140]
0x18002199f  mov     rax, [rax+40h]
0x1800219a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219a8  mov     ebx, eax
0x1800219aa  lea     rcx, [rsp+250h+var_1F0]
0x1800219af  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800219b4  nop
0x1800219b5  lea     rcx, [rbp+150h+var_190]; this
0x1800219b9  call    ??1CFrameSystemBufferShim@Shim@Stack@Rdp@@UEAA@XZ; Rdp::Stack::Shim::CFrameSystemBufferShim::~CFrameSystemBufferShim(void)
0x1800219be  mov     rcx, [rbp+158h]; this
0x1800219c5  lea     rax, aFailedToProces; "Failed to process frame"
0x1800219cc  mov     [rsp+250h+var_230], rax; int
0x1800219d1  mov     r9d, ebx; char *
0x1800219d4  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800219db  mov     edx, 180h; void *
0x1800219e0  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800219e5  mov     rax, [rsi+128h]
0x1800219ec  mov     rdi, [rax+0E8h]
0x1800219f3  mov     rbx, [rsi+120h]
0x1800219fa  mov     rcx, [rax+0F0h]
0x180021a01  mov     rax, [rcx]
0x180021a04  mov     rax, [rax+28h]
0x180021a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a0d  mov     [rsp+250h+var_230], r14; void *
0x180021a12  mov     r9, r12; void *
0x180021a15  mov     r8, rbx; unsigned __int64
0x180021a18  mov     rdx, rax; struct _GUID *
0x180021a1b  mov     rcx, rdi; this
0x180021a1e  call    ?OnReleaseResource@CAdapterShim@Shim@Stack@Rdp@@QEAAXAEBU_GUID@@_KPEAX2@Z; Rdp::Stack::Shim::CAdapterShim::OnReleaseResource(_GUID const &,unsigned __int64,void *,void *)
0x180021a23  nop
0x180021a24  lea     rcx, [rsp+250h+var_1D8]
0x180021a29  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021a2e  jmp     loc_180021779
0x180021a33  cmp     eax, 3
0x180021a36  jbe     short loc_180021A24
0x180021a38  mov     [rbp+150h+var_1C0], r14
0x180021a3c  lea     rax, aFailedToObtain; "Failed to obtain shared fence handle, s"...
0x180021a43  mov     [rbp+150h+var_1C8], rax
0x180021a47  lea     rax, aRdpStackShimCf_0; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x180021a4e  mov     [rsp+250h+var_1E0], rax
0x180021a53  mov     dword ptr [rsp+250h+var_1F0], 149h
0x180021a5b  lea     rax, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180021a62  mov     [rbp+150h+var_1D0], rax
0x180021a66  lea     rax, [rbp+150h+var_1C0]
0x180021a6a  mov     [rsp+250h+var_210], rax
0x180021a6f  lea     rax, [rbp+150h+var_1C8]
0x180021a73  mov     [rsp+250h+var_218], rax
0x180021a78  lea     rax, [rsp+250h+var_1E0]
0x180021a7d  mov     [rsp+250h+var_220], rax
0x180021a82  lea     rax, [rsp+250h+var_1F0]
0x180021a87  mov     [rsp+250h+var_228], rax
0x180021a8c  lea     rax, [rbp+150h+var_1D0]
0x180021a90  mov     [rsp+250h+var_230], rax
0x180021a95  lea     rdx, dword_18003618C
0x180021a9c  lea     rcx, dword_18003C058
0x180021aa3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180021aa8  jmp     loc_180021A24
0x180021aad  mov     eax, cs:dword_18003C058
0x180021ab3  cmp     eax, 3
0x180021ab6  jbe     short loc_180021B15
0x180021ab8  lea     rax, aFailedToObtain_1; "Failed to obtain shared resource pools,"...
0x180021abf  mov     [rbp+150h+var_1C0], rax
0x180021ac3  lea     rax, aRdpStackShimCf_0; "Rdp::Stack::Shim::CFrameProcessorShim::"...
0x180021aca  mov     [rbp+150h+var_1C8], rax
0x180021ace  mov     dword ptr [rsp+250h+var_1F0], 130h
0x180021ad6  mov     [rsp+250h+var_1E0], rbx
0x180021adb  lea     rax, [rbp+150h+var_1C0]
0x180021adf  mov     [rsp+250h+var_218], rax
0x180021ae4  lea     rax, [rbp+150h+var_1C8]
0x180021ae8  mov     [rsp+250h+var_220], rax
0x180021aed  lea     rax, [rsp+250h+var_1F0]
0x180021af2  mov     [rsp+250h+var_228], rax
0x180021af7  lea     rax, [rsp+250h+var_1E0]
0x180021afc  mov     [rsp+250h+var_230], rax
0x180021b01  lea     rdx, word_180036232
0x180021b08  lea     rcx, dword_18003C058
0x180021b0f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180021b14  nop
0x180021b15  mov     rcx, [rbp+150h+var_1A8]; this
0x180021b19  test    rcx, rcx
0x180021b1c  jz      short loc_180021B24
0x180021b1e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021b23  nop
0x180021b24  mov     rcx, [rbp+150h+var_198]; this
0x180021b28  test    rcx, rcx
0x180021b2b  jz      short loc_180021B32
0x180021b2d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021b32  add     rsp, 218h
0x180021b39  pop     r15
0x180021b3b  pop     r14
0x180021b3d  pop     r13
0x180021b3f  pop     r12
0x180021b41  pop     rdi
0x180021b42  pop     rsi
0x180021b43  pop     rbx
0x180021b44  pop     rbp
0x180021b45  retn
0x180021b46  mov     r9d, eax; char *
0x180021b49  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021b50  mov     edx, 1CBEh; void *
0x180021b55  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021b5b  mov     r9d, eax; char *
0x180021b5e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021b65  mov     edx, 1CBEh; void *
0x180021b6a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
