# Rdp::Stack::Shim::CAdapterShim::AddMonitors(std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>> const &)

- ea: `0x180018afc`
- end: `0x180018cc8`
- name: `?AddMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXAEBV?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct Rdp::Stack::Shim::CAdapterShim *, struct Rdp::Stack::IMonitorConfig ***)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019894`

## callees

- `0x18000141c`
- `0x1800023fc`
- `0x180003714`
- `0x180007b28`
- `0x18000a0e4`
- `0x18000d98c`
- `0x1800181d0`
- `0x180018388`
- `0x1800187f8`
- `0x180018afc`
- `0x18001c914`
- `0x18001e824`
- `0x18002a010`

## string_xrefs

- `0x180018bef`: `AdapterShimCreateMonitors: %d`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Shim::CAdapterShim::AddMonitors(
        struct Rdp::Stack::Shim::CAdapterShim *a1,
        struct Rdp::Stack::IMonitorConfig ***a2)
{
  int v4; // r8d
  int v5; // r9d
  struct Rdp::Stack::IMonitorConfig **v6; // rdi
  struct Rdp::Stack::IMonitorConfig **v7; // r14
  __int64 v8; // rax
  Rdp::Stack::Shim::CMonitorShim *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD v14[2]; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v15[3]; // [rsp+60h] [rbp-18h] BYREF
  Rdp::Stack::Shim::CMonitorShim *v16; // [rsp+B0h] [rbp+38h] BYREF
  __int64 v17; // [rsp+B8h] [rbp+40h] BYREF
  __int128 *v18; // [rsp+C0h] [rbp+48h] BYREF
  const char *v19; // [rsp+C8h] [rbp+50h] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v17 = a2[1] - *a2;
    LODWORD(v16) = *((_DWORD *)a1 + 84);
    v18 = &xmmword_18003CA50;
    v19 = "RdpLite";
    v14[0] = 0x1000000;
    v15[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&word_1800357EE,
      v4,
      v5,
      (__int64)v15,
      (__int64)v14,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v16,
      (__int64)&v17);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterShimCreateMonitors: %d",
    "Rdp::Stack::Shim::CAdapterShim::AddMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0x1E3u,
    a2[1] - *a2);
  std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(v15, (char *)a1 + 176);
  v6 = *a2;
  v7 = a2[1];
  while ( v6 != v7 )
  {
    v17 = (__int64)operator new(0x100u);
    v8 = Rdp::Stack::Shim::CMonitorShim::CMonitorShim((Rdp::Stack::Shim::CMonitorShim *)v17, *v6, a1);
    wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
      &v16,
      v8);
    v9 = v16;
    Rdp::Stack::Shim::CMonitorShim::Start(v16);
    v10 = (*(__int64 (__fastcall **)(struct Rdp::Stack::IMonitorConfig *))(*(_QWORD *)*v6 + 40LL))(*v6);
    v11 = *(_QWORD *)std::map<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Try_emplace<_GUID const &,>(
                       (char *)a1 + 160,
                       v14,
                       v10);
    v16 = 0;
    v12 = *(_QWORD *)(v11 + 48);
    *(_QWORD *)(v11 + 48) = v9;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v16);
    ++v6;
  }
  return std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(v15);
}

```

## disassembly

```asm
0x180018afc  push    rbp
0x180018afe  push    rbx
0x180018aff  push    rsi
0x180018b00  push    rdi
0x180018b01  push    r14
0x180018b03  push    r15
0x180018b05  mov     rbp, rsp
0x180018b08  sub     rsp, 78h
0x180018b0c  mov     rbx, rdx
0x180018b0f  mov     rsi, rcx
0x180018b12  mov     eax, cs:dword_18003C058
0x180018b18  cmp     eax, 4
0x180018b1b  jbe     loc_180018BC9
0x180018b21  mov     rdx, 470000000000h
0x180018b2b  lea     rcx, dword_18003C058
0x180018b32  call    _tlgKeywordOn
0x180018b37  test    al, al
0x180018b39  jz      loc_180018BC9
0x180018b3f  mov     rax, [rbx+8]
0x180018b43  sub     rax, [rbx]
0x180018b46  sar     rax, 3
0x180018b4a  mov     [rbp+arg_8], rax
0x180018b4e  mov     eax, [rsi+150h]
0x180018b54  mov     dword ptr [rbp+arg_0], eax
0x180018b57  lea     rax, xmmword_18003CA50
0x180018b5e  mov     [rbp+arg_10], rax
0x180018b62  lea     rax, aRdplite; "RdpLite"
0x180018b69  mov     [rbp+arg_18], rax
0x180018b6d  mov     [rbp+var_28], 1000000h
0x180018b75  lea     rax, aCheckpoint; "Checkpoint"
0x180018b7c  mov     [rbp+var_18], rax
0x180018b80  lea     rax, [rbp+arg_8]
0x180018b84  mov     [rsp+78h+var_30], rax
0x180018b89  lea     rax, [rbp+arg_0]
0x180018b8d  mov     [rsp+78h+var_38], rax
0x180018b92  lea     rax, [rbp+arg_10]
0x180018b96  mov     [rsp+78h+var_40], rax
0x180018b9b  lea     rax, [rbp+arg_18]
0x180018b9f  mov     [rsp+78h+var_48], rax
0x180018ba4  lea     rax, [rbp+var_28]
0x180018ba8  mov     [rsp+78h+var_50], rax
0x180018bad  lea     rax, [rbp+var_18]
0x180018bb1  mov     qword ptr [rsp+78h+var_58], rax
0x180018bb6  lea     rdx, word_1800357EE
0x180018bbd  lea     rcx, dword_18003C058
0x180018bc4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180018bc9  mov     rax, [rbx+8]
0x180018bcd  sub     rax, [rbx]
0x180018bd0  sar     rax, 3
0x180018bd4  mov     [rsp+78h+var_50], rax
0x180018bd9  mov     [rsp+78h+var_58], 1E3h; unsigned int
0x180018be1  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180018be8  lea     r8, aRdpStackShimCa_3; "Rdp::Stack::Shim::CAdapterShim::AddMoni"...
0x180018bef  lea     rdx, aAdaptershimcre; "AdapterShimCreateMonitors: %d"
0x180018bf6  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180018bfd  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180018c02  lea     rdx, [rsi+0B0h]
0x180018c09  lea     rcx, [rbp+var_18]
0x180018c0d  call    ??0?$unique_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(std::shared_mutex &)
0x180018c12  nop
0x180018c13  mov     rdi, [rbx]
0x180018c16  mov     r14, [rbx+8]
0x180018c1a  jmp     loc_180018CA9
0x180018c1f  mov     ecx, 100h; Size
0x180018c24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018c29  mov     [rbp+arg_8], rax
0x180018c2d  mov     r8, rsi; struct Rdp::Stack::Shim::CAdapterShim *
0x180018c30  mov     rdx, [rdi]; struct Rdp::Stack::IMonitorConfig *
0x180018c33  mov     rcx, rax; this
0x180018c36  call    ??0CMonitorShim@Shim@Stack@Rdp@@QEAA@PEAUIMonitorConfig@23@PEAVCAdapterShim@123@@Z; Rdp::Stack::Shim::CMonitorShim::CMonitorShim(Rdp::Stack::IMonitorConfig *,Rdp::Stack::Shim::CAdapterShim *)
0x180018c3b  nop
0x180018c3c  mov     rdx, rax
0x180018c3f  lea     rcx, [rbp+arg_0]
0x180018c43  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180018c48  nop
0x180018c49  mov     rbx, [rbp+arg_0]
0x180018c4d  mov     rcx, rbx; this
0x180018c50  call    ?Start@CMonitorShim@Shim@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Shim::CMonitorShim::Start(void)
0x180018c55  mov     rcx, [rdi]
0x180018c58  mov     rax, [rcx]
0x180018c5b  mov     rax, [rax+28h]
0x180018c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c64  mov     r8, rax
0x180018c67  lea     rdx, [rbp+var_28]
0x180018c6b  lea     rcx, [rsi+0A0h]
0x180018c72  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180018c77  mov     rdx, [rax]
0x180018c7a  mov     [rbp+arg_0], 0
0x180018c82  mov     rcx, [rdx+30h]
0x180018c86  mov     [rdx+30h], rbx
0x180018c8a  test    rcx, rcx
0x180018c8d  jz      short loc_180018C9C
0x180018c8f  mov     rax, [rcx]
0x180018c92  mov     rax, [rax+10h]
0x180018c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c9b  nop
0x180018c9c  lea     rcx, [rbp+arg_0]
0x180018ca0  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180018ca5  add     rdi, 8
0x180018ca9  cmp     rdi, r14
0x180018cac  jnz     loc_180018C1F
0x180018cb2  lea     rcx, [rbp+var_18]
0x180018cb6  call    ??1?$unique_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(void)
0x180018cbb  add     rsp, 78h
0x180018cbf  pop     r15
0x180018cc1  pop     r14
0x180018cc3  pop     rdi
0x180018cc4  pop     rsi
0x180018cc5  pop     rbx
0x180018cc6  pop     rbp
0x180018cc7  retn
```
