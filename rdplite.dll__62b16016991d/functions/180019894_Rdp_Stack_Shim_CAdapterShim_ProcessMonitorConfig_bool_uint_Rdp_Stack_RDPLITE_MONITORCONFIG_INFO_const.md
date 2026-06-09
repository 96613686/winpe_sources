# Rdp::Stack::Shim::CAdapterShim::ProcessMonitorConfig(bool,uint,Rdp::Stack::RDPLITE_MONITORCONFIG_INFO const *)

- ea: `0x180019894`
- end: `0x180019e0b`
- name: `?ProcessMonitorConfig@CAdapterShim@Shim@Stack@Rdp@@QEAAX_NIPEBURDPLITE_MONITORCONFIG_INFO@34@@Z`
- size: `1399`
- prototype: `void __fastcall(Rdp::Stack::Shim::CAdapterShim *this, char, unsigned int, const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b578`

## callees

- `0x18000141c`
- `0x1800023fc`
- `0x1800049b8`
- `0x180004cb4`
- `0x180007b28`
- `0x180009a78`
- `0x180009bc0`
- `0x18000a0e4`
- `0x18000cea4`
- `0x18000cef0`
- `0x18000d98c`
- `0x180018afc`
- `0x180018d7c`
- `0x180018f90`
- `0x180019894`
- `0x18001a974`
- `0x18001aac8`
- `0x18001b2f4`
- `0x18002a010`

## string_xrefs

- `0x180019979`: `Rdp::Stack::Shim::CAdapterShim::ProcessMonitorConfig`
- `0x180019980`: `AdapterShimProcessMonitorConfig: %d`
- `0x180019b97`: `Monitor cannot be added because another monitor with same ID already exists`
- `0x180019ad3`: `Monitor configuration cannot be updated because it does not exist`
- `0x180019d8f`: `RDPCFG_MONITORCONFIG_ACTION_TYPE_UPDATE is available only for incremental updates`
- `0x180019a28`: `Monitor cannot be deleted because it does not exist`
- `0x180019dbe`: `RDPCFG_MONITORCONFIG_ACTION_TYPE_DELETE is available only for incremental updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Rdp::Stack::Shim::CAdapterShim::ProcessMonitorConfig(
        Rdp::Stack::Shim::CAdapterShim *this,
        char a2,
        unsigned int a3,
        const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *a4)
{
  __int64 v5; // rbx
  int v8; // r8d
  int v9; // r9d
  char v10; // r12
  const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *v11; // r14
  __int64 v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // rax
  __int128 **v15; // rcx
  __int64 v16; // rax
  _QWORD *v17; // rax
  const char *v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int128 *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  char *v25; // [rsp+28h] [rbp-61h]
  char *v26; // [rsp+28h] [rbp-61h]
  const char *v27; // [rsp+30h] [rbp-59h]
  const char *v28; // [rsp+50h] [rbp-39h] BYREF
  __int128 *v29; // [rsp+58h] [rbp-31h] BYREF
  __int128 v30; // [rsp+60h] [rbp-29h] BYREF
  __int64 v31; // [rsp+70h] [rbp-19h]
  __int128 v32; // [rsp+78h] [rbp-11h] BYREF
  __int64 v33; // [rsp+88h] [rbp-1h]
  __int128 v34; // [rsp+90h] [rbp+7h] BYREF
  __int64 v35; // [rsp+A0h] [rbp+17h]
  __int64 v36; // [rsp+A8h] [rbp+1Fh] BYREF
  const char *v37; // [rsp+B0h] [rbp+27h] BYREF
  _BYTE v38[8]; // [rsp+B8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v40; // [rsp+100h] [rbp+77h] BYREF
  __int64 v41; // [rsp+108h] [rbp+7Fh] BYREF

  v5 = a3;
  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v41 = v5;
    v40 = *((_DWORD *)this + 84);
    v29 = &xmmword_18003CA50;
    v28 = "RdpLite";
    v36 = 0x1000000;
    v37 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)byte_1800354FB,
      v8,
      v9,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v28,
      (__int64)&v29,
      (__int64)&v40,
      (__int64)&v41);
  }
  LODWORD(v25) = v5;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterShimProcessMonitorConfig: %d",
    "Rdp::Stack::Shim::CAdapterShim::ProcessMonitorConfig",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0x2EBu,
    v25);
  v30 = 0;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  v10 = 0;
  v11 = (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)((char *)a4 + 16 * v5);
  while ( a4 != v11 )
  {
    switch ( *(_DWORD *)a4 )
    {
      case 1:
        if ( a2 )
        {
          v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a4 + 1) + 40LL))(*((_QWORD *)a4 + 1));
          v20 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(
                            (char *)this + 160,
                            v38,
                            v19);
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x305,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
            (const char *)0x8000FFFFLL,
            *v20 != *((_QWORD *)this + 20),
            (bool)"Monitor cannot be added because another monitor with same ID already exists",
            v27);
        }
        v10 = 1;
        wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
          &v29,
          *((_QWORD *)a4 + 1));
        if ( *((_QWORD *)&v30 + 1) == v31 )
        {
          std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(
            &v30,
            *((_QWORD *)&v30 + 1),
            &v29);
        }
        else
        {
          v21 = v29;
          v29 = 0;
          **((_QWORD **)&v30 + 1) = v21;
          *((_QWORD *)&v30 + 1) += 8LL;
        }
        v15 = &v29;
        break;
      case 2:
        if ( !a2 )
        {
          v22 = wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x319,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
            (const char *)v22,
            (int)"RDPCFG_MONITORCONFIG_ACTION_TYPE_UPDATE is available only for incremental updates",
            v26);
        }
        v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a4 + 1) + 40LL))(*((_QWORD *)a4 + 1));
        v17 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(
                          (char *)this + 160,
                          &v36,
                          v16);
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0x312,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
          (const char *)0x80070490LL,
          *v17 == *((_QWORD *)this + 20),
          (bool)"Monitor configuration cannot be updated because it does not exist",
          v27);
        if ( (*(_BYTE *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a4 + 1) + 32LL))(*((_QWORD *)a4 + 1)) & 2) != 0 )
          v10 = 1;
        wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
          &v28,
          *((_QWORD *)a4 + 1));
        if ( *((_QWORD *)&v32 + 1) == v33 )
        {
          std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(
            &v32,
            *((_QWORD *)&v32 + 1),
            &v28);
        }
        else
        {
          v18 = v28;
          v28 = 0;
          **((_QWORD **)&v32 + 1) = v18;
          *((_QWORD *)&v32 + 1) += 8LL;
        }
        v15 = (__int128 **)&v28;
        break;
      case 3:
        if ( !a2 )
        {
          v23 = wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x334,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
            (const char *)v23,
            (int)"RDPCFG_MONITORCONFIG_ACTION_TYPE_DELETE is available only for incremental updates",
            v26);
        }
        v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a4 + 1) + 40LL))(*((_QWORD *)a4 + 1));
        v13 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(
                          (char *)this + 160,
                          &v37,
                          v12);
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0x32D,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
          (const char *)0x80070490LL,
          *v13 == *((_QWORD *)this + 20),
          (bool)"Monitor cannot be deleted because it does not exist",
          v27);
        v10 = 1;
        wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
          &v41,
          *((_QWORD *)a4 + 1));
        if ( *((_QWORD *)&v34 + 1) == v35 )
        {
          std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(
            &v34,
            *((_QWORD *)&v34 + 1),
            &v41);
        }
        else
        {
          v14 = v41;
          v41 = 0;
          **((_QWORD **)&v34 + 1) = v14;
          *((_QWORD *)&v34 + 1) += 8LL;
        }
        v15 = (__int128 **)&v41;
        break;
      default:
        v24 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x33D,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
          (const char *)v24,
          (int)"Invalid Action specified",
          v26);
    }
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(v15);
    a4 = (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)((char *)a4 + 16);
  }
  if ( !a2 )
  {
    if ( *((_QWORD *)this + 21) )
      Rdp::Stack::Shim::CAdapterShim::DeleteAllMonitors(this);
    if ( (__int64)(*((_QWORD *)&v30 + 1) - v30) >> 3 )
      Rdp::Stack::Shim::CAdapterShim::AddMonitors(this);
    goto LABEL_34;
  }
  if ( (__int64)(*((_QWORD *)&v34 + 1) - v34) >> 3 )
    Rdp::Stack::Shim::CAdapterShim::DeleteMonitors(this, &v34);
  if ( (__int64)(*((_QWORD *)&v30 + 1) - v30) >> 3 )
    Rdp::Stack::Shim::CAdapterShim::AddMonitors(this);
  if ( v10 )
  {
LABEL_34:
    if ( *((_QWORD *)this + 21) )
      Rdp::Stack::Shim::CAdapterShim::UpdateAllMonitors(this);
    goto LABEL_36;
  }
  if ( (__int64)(*((_QWORD *)&v32 + 1) - v32) >> 3 )
    Rdp::Stack::Shim::CAdapterShim::UpdateMonitors(this, &v32);
LABEL_36:
  if ( (_QWORD)v32 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
      v32,
      *((_QWORD *)&v32 + 1));
    std::_Deallocate<16>(v32, (v33 - v32) & 0xFFFFFFFFFFFFFFF8uLL);
    v32 = 0;
    v33 = 0;
  }
  if ( (_QWORD)v34 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
      v34,
      *((_QWORD *)&v34 + 1));
    std::_Deallocate<16>(v34, (v35 - v34) & 0xFFFFFFFFFFFFFFF8uLL);
    v34 = 0;
    v35 = 0;
  }
  if ( (_QWORD)v30 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(
      v30,
      *((_QWORD *)&v30 + 1));
    std::_Deallocate<16>(v30, (v31 - v30) & 0xFFFFFFFFFFFFFFF8uLL);
  }
}

```

## disassembly

```asm
0x180019894  mov     [rsp-8+arg_0], rbx
0x180019899  mov     [rsp-8+arg_8], rsi
0x18001989e  push    rbp
0x18001989f  push    rdi
0x1800198a0  push    r12
0x1800198a2  push    r14
0x1800198a4  push    r15
0x1800198a6  lea     rbp, [rsp-37h]
0x1800198ab  sub     rsp, 0C0h
0x1800198b2  mov     rsi, r9
0x1800198b5  mov     ebx, r8d
0x1800198b8  mov     r15b, dl
0x1800198bb  mov     rdi, rcx
0x1800198be  mov     eax, cs:dword_18003C058
0x1800198c4  cmp     eax, 4
0x1800198c7  jbe     loc_180019966
0x1800198cd  mov     rdx, 470000000000h
0x1800198d7  lea     rcx, dword_18003C058
0x1800198de  call    _tlgKeywordOn
0x1800198e3  test    al, al
0x1800198e5  jz      short loc_180019966
0x1800198e7  mov     [rbp+57h+arg_18], rbx
0x1800198eb  mov     eax, [rdi+150h]
0x1800198f1  mov     [rbp+57h+arg_10], eax
0x1800198f4  lea     rax, xmmword_18003CA50
0x1800198fb  mov     [rbp+57h+var_88], rax
0x1800198ff  lea     rax, aRdplite; "RdpLite"
0x180019906  mov     [rbp+57h+var_90], rax
0x18001990a  mov     [rbp+57h+var_38], 1000000h
0x180019912  lea     rax, aCheckpoint; "Checkpoint"
0x180019919  mov     [rbp+57h+var_30], rax
0x18001991d  lea     rax, [rbp+57h+arg_18]
0x180019921  mov     [rsp+0E0h+var_98], rax
0x180019926  lea     rax, [rbp+57h+arg_10]
0x18001992a  mov     [rsp+0E0h+var_A0], rax
0x18001992f  lea     rax, [rbp+57h+var_88]
0x180019933  mov     [rsp+0E0h+var_A8], rax
0x180019938  lea     rax, [rbp+57h+var_90]
0x18001993c  mov     [rsp+0E0h+var_B0], rax
0x180019941  lea     rax, [rbp+57h+var_38]
0x180019945  mov     [rsp+0E0h+var_B8], rax
0x18001994a  lea     rax, [rbp+57h+var_30]
0x18001994e  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180019953  lea     rdx, byte_1800354FB
0x18001995a  lea     rcx, dword_18003C058
0x180019961  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180019966  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18001996a  mov     dword ptr [rsp+0E0h+var_C0], 2EBh; unsigned int
0x180019972  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180019979  lea     r8, aRdpStackShimCa_5; "Rdp::Stack::Shim::CAdapterShim::Process"...
0x180019980  lea     rdx, aAdaptershimpro; "AdapterShimProcessMonitorConfig: %d"
0x180019987  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001998e  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180019993  xorps   xmm0, xmm0
0x180019996  movdqu  [rbp+57h+var_80], xmm0
0x18001999b  mov     [rbp+57h+var_70], 0
0x1800199a3  movdqu  [rbp+57h+var_50], xmm0
0x1800199a8  mov     [rbp+57h+var_40], 0
0x1800199b0  movdqu  [rbp+57h+var_68], xmm0
0x1800199b5  mov     [rbp+57h+var_58], 0
0x1800199bd  xor     r12b, r12b
0x1800199c0  mov     r14, rbx
0x1800199c3  shl     r14, 4
0x1800199c7  add     r14, rsi
0x1800199ca  jmp     loc_180019C0A
0x1800199cf  mov     ecx, [rsi]
0x1800199d1  sub     ecx, 1
0x1800199d4  jz      loc_180019B5F
0x1800199da  sub     ecx, 1
0x1800199dd  jz      loc_180019A97
0x1800199e3  cmp     ecx, 1
0x1800199e6  jnz     loc_180019DDC
0x1800199ec  test    r15b, r15b
0x1800199ef  jz      loc_180019DAD
0x1800199f5  mov     rcx, [rsi+8]
0x1800199f9  lea     rbx, [rdi+0A0h]
0x180019a00  mov     rax, [rcx]
0x180019a03  mov     rax, [rax+28h]
0x180019a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a0c  mov     r8, rax
0x180019a0f  lea     rdx, [rbp+57h+var_30]
0x180019a13  mov     rcx, rbx
0x180019a16  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(_GUID const &)
0x180019a1b  mov     rcx, [rbx]
0x180019a1e  cmp     [rax], rcx
0x180019a21  setz    al
0x180019a24  mov     rcx, [rbp+5Fh]; this
0x180019a28  lea     rdx, aMonitorCannotB_0; "Monitor cannot be deleted because it do"...
0x180019a2f  mov     [rsp+0E0h+var_B8], rdx; bool
0x180019a34  mov     [rsp+0E0h+var_C0], al; char
0x180019a38  mov     r9d, 80070490h; char *
0x180019a3e  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180019a45  mov     edx, 32Dh; void *
0x180019a4a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180019a4f  mov     r12b, 1
0x180019a52  mov     rdx, [rsi+8]
0x180019a56  lea     rcx, [rbp+57h+arg_18]
0x180019a5a  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180019a5f  nop
0x180019a60  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x180019a64  cmp     rdx, [rbp+57h+var_40]
0x180019a68  jz      short loc_180019A80
0x180019a6a  mov     rax, [rbp+57h+arg_18]
0x180019a6e  mov     [rbp+57h+arg_18], 0
0x180019a76  mov     [rdx], rax
0x180019a79  add     qword ptr [rbp+57h+var_50+8], 8
0x180019a7e  jmp     short loc_180019A8E
0x180019a80  lea     r8, [rbp+57h+arg_18]
0x180019a84  lea     rcx, [rbp+57h+var_50]
0x180019a88  call    ??$_Emplace_reallocate@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> &&)
0x180019a8d  nop
0x180019a8e  lea     rcx, [rbp+57h+arg_18]
0x180019a92  jmp     loc_180019C01
0x180019a97  test    r15b, r15b
0x180019a9a  jz      loc_180019D7E
0x180019aa0  mov     rcx, [rsi+8]
0x180019aa4  lea     rbx, [rdi+0A0h]
0x180019aab  mov     rax, [rcx]
0x180019aae  mov     rax, [rax+28h]
0x180019ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ab7  mov     r8, rax
0x180019aba  lea     rdx, [rbp+57h+var_38]
0x180019abe  mov     rcx, rbx
0x180019ac1  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(_GUID const &)
0x180019ac6  mov     rcx, [rbx]
0x180019ac9  cmp     [rax], rcx
0x180019acc  setz    al
0x180019acf  mov     rcx, [rbp+5Fh]; this
0x180019ad3  lea     rdx, aMonitorConfigu; "Monitor configuration cannot be updated"...
0x180019ada  mov     [rsp+0E0h+var_B8], rdx; bool
0x180019adf  mov     [rsp+0E0h+var_C0], al; char
0x180019ae3  mov     r9d, 80070490h; char *
0x180019ae9  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180019af0  mov     edx, 312h; void *
0x180019af5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180019afa  mov     rcx, [rsi+8]
0x180019afe  mov     rax, [rcx]
0x180019b01  mov     rax, [rax+20h]
0x180019b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b0a  test    byte ptr [rax], 2
0x180019b0d  movzx   r12d, r12b
0x180019b11  mov     eax, 1
0x180019b16  cmovnz  r12d, eax
0x180019b1a  mov     rdx, [rsi+8]
0x180019b1e  lea     rcx, [rbp+57h+var_90]
0x180019b22  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180019b27  nop
0x180019b28  mov     rdx, qword ptr [rbp+57h+var_68+8]
0x180019b2c  cmp     rdx, [rbp+57h+var_58]
0x180019b30  jz      short loc_180019B48
0x180019b32  mov     rax, [rbp+57h+var_90]
0x180019b36  mov     [rbp+57h+var_90], 0
0x180019b3e  mov     [rdx], rax
0x180019b41  add     qword ptr [rbp+57h+var_68+8], 8
0x180019b46  jmp     short loc_180019B56
0x180019b48  lea     r8, [rbp+57h+var_90]
0x180019b4c  lea     rcx, [rbp+57h+var_68]
0x180019b50  call    ??$_Emplace_reallocate@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> &&)
0x180019b55  nop
0x180019b56  lea     rcx, [rbp+57h+var_90]
0x180019b5a  jmp     loc_180019C01
0x180019b5f  test    r15b, r15b
0x180019b62  jz      short loc_180019BBE
0x180019b64  mov     rcx, [rsi+8]
0x180019b68  lea     rbx, [rdi+0A0h]
0x180019b6f  mov     rax, [rcx]
0x180019b72  mov     rax, [rax+28h]
0x180019b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b7b  mov     r8, rax
0x180019b7e  lea     rdx, [rbp+57h+var_28]
0x180019b82  mov     rcx, rbx
0x180019b85  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(_GUID const &)
0x180019b8a  mov     rcx, [rbx]
0x180019b8d  cmp     [rax], rcx
0x180019b90  setnz   al
0x180019b93  mov     rcx, [rbp+5Fh]; this
0x180019b97  lea     rdx, aMonitorCannotB; "Monitor cannot be added because another"...
0x180019b9e  mov     [rsp+0E0h+var_B8], rdx; char *
0x180019ba3  mov     [rsp+0E0h+var_C0], al; char
0x180019ba7  mov     r9d, 8000FFFFh; char *
0x180019bad  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180019bb4  mov     edx, 305h; void *
0x180019bb9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180019bbe  mov     r12b, 1
0x180019bc1  mov     rdx, [rsi+8]
0x180019bc5  lea     rcx, [rbp+57h+var_88]
0x180019bc9  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180019bce  nop
0x180019bcf  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x180019bd3  cmp     rdx, [rbp+57h+var_70]
0x180019bd7  jz      short loc_180019BEF
0x180019bd9  mov     rax, [rbp+57h+var_88]
0x180019bdd  mov     [rbp+57h+var_88], 0
0x180019be5  mov     [rdx], rax
0x180019be8  add     qword ptr [rbp+57h+var_80+8], 8
0x180019bed  jmp     short loc_180019BFD
0x180019bef  lea     r8, [rbp+57h+var_88]
0x180019bf3  lea     rcx, [rbp+57h+var_80]
0x180019bf7  call    ??$_Emplace_reallocate@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> &&)
0x180019bfc  nop
0x180019bfd  lea     rcx, [rbp+57h+var_88]
0x180019c01  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180019c06  add     rsi, 10h
0x180019c0a  cmp     rsi, r14
0x180019c0d  jnz     loc_1800199CF
0x180019c13  test    r15b, r15b
0x180019c16  jz      loc_180019D46
0x180019c1c  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180019c20  sub     rax, qword ptr [rbp+57h+var_50]
0x180019c24  sar     rax, 3
0x180019c28  test    rax, rax
0x180019c2b  jz      short loc_180019C39
0x180019c2d  lea     rdx, [rbp+57h+var_50]
0x180019c31  mov     rcx, rdi
0x180019c34  call    ?DeleteMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXAEBV?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z; Rdp::Stack::Shim::CAdapterShim::DeleteMonitors(std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> const &)
0x180019c39  mov     rax, qword ptr [rbp+57h+var_80+8]
0x180019c3d  sub     rax, qword ptr [rbp+57h+var_80]
0x180019c41  sar     rax, 3
0x180019c45  test    rax, rax
0x180019c48  jz      short loc_180019C56
0x180019c4a  lea     rdx, [rbp+57h+var_80]
0x180019c4e  mov     rcx, rdi
0x180019c51  call    ?AddMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXAEBV?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z; Rdp::Stack::Shim::CAdapterShim::AddMonitors(std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> const &)
0x180019c56  test    r12b, r12b
0x180019c59  jz      loc_180019D20
0x180019c5f  cmp     qword ptr [rdi+0A8h], 0
0x180019c67  jbe     short loc_180019C72
0x180019c69  mov     rcx, rdi; this
0x180019c6c  call    ?UpdateAllMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Shim::CAdapterShim::UpdateAllMonitors(void)
0x180019c71  nop
0x180019c72  mov     rcx, qword ptr [rbp+57h+var_68]
0x180019c76  test    rcx, rcx
0x180019c79  jz      short loc_180019CA8
0x180019c7b  mov     rdx, qword ptr [rbp+57h+var_68+8]
0x180019c7f  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x180019c84  mov     rcx, qword ptr [rbp+57h+var_68]
0x180019c88  mov     rdx, [rbp+57h+var_58]
0x180019c8c  sub     rdx, rcx
0x180019c8f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180019c93  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180019c98  xorps   xmm0, xmm0
0x180019c9b  movdqu  [rbp+57h+var_68], xmm0
0x180019ca0  mov     [rbp+57h+var_58], 0
0x180019ca8  mov     rcx, qword ptr [rbp+57h+var_50]
0x180019cac  test    rcx, rcx
0x180019caf  jz      short loc_180019CDE
0x180019cb1  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x180019cb5  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x180019cba  mov     rcx, qword ptr [rbp+57h+var_50]
0x180019cbe  mov     rdx, [rbp+57h+var_40]
0x180019cc2  sub     rdx, rcx
0x180019cc5  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180019cc9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180019cce  xorps   xmm0, xmm0
0x180019cd1  movdqu  [rbp+57h+var_50], xmm0
0x180019cd6  mov     [rbp+57h+var_40], 0
0x180019cde  mov     rcx, qword ptr [rbp+57h+var_80]
0x180019ce2  test    rcx, rcx
0x180019ce5  jz      short loc_180019D04
0x180019ce7  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x180019ceb  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>>(wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> *,wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy> * const,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> &)
0x180019cf0  mov     rcx, qword ptr [rbp+57h+var_80]
0x180019cf4  mov     rdx, [rbp+57h+var_70]
0x180019cf8  sub     rdx, rcx
0x180019cfb  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180019cff  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180019d04  lea     r11, [rsp+0E0h+var_20]
0x180019d0c  mov     rbx, [r11+30h]
0x180019d10  mov     rsi, [r11+38h]
0x180019d14  mov     rsp, r11
0x180019d17  pop     r15
0x180019d19  pop     r14
0x180019d1b  pop     r12
0x180019d1d  pop     rdi
0x180019d1e  pop     rbp
0x180019d1f  retn
0x180019d20  mov     rax, qword ptr [rbp+57h+var_68+8]
0x180019d24  sub     rax, qword ptr [rbp+57h+var_68]
0x180019d28  sar     rax, 3
0x180019d2c  test    rax, rax
0x180019d2f  jz      loc_180019C72
0x180019d35  lea     rdx, [rbp+57h+var_68]
0x180019d39  mov     rcx, rdi
0x180019d3c  call    ?UpdateMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXAEBV?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z; Rdp::Stack::Shim::CAdapterShim::UpdateMonitors(std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> const &)
0x180019d41  jmp     loc_180019C72
0x180019d46  cmp     qword ptr [rdi+0A8h], 0
0x180019d4e  jbe     short loc_180019D58
0x180019d50  mov     rcx, rdi; this
0x180019d53  call    ?DeleteAllMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Shim::CAdapterShim::DeleteAllMonitors(void)
0x180019d58  mov     rax, qword ptr [rbp+57h+var_80+8]
0x180019d5c  sub     rax, qword ptr [rbp+57h+var_80]
0x180019d60  sar     rax, 3
0x180019d64  test    rax, rax
0x180019d67  jz      loc_180019C5F
0x180019d6d  lea     rdx, [rbp+57h+var_80]
0x180019d71  mov     rcx, rdi
0x180019d74  call    ?AddMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXAEBV?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z; Rdp::Stack::Shim::CAdapterShim::AddMonitors(std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>> const &)
0x180019d79  jmp     loc_180019C5F
0x180019d7e  mov     ecx, 8000FFFFh
0x180019d83  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
  ... truncated ...
```
