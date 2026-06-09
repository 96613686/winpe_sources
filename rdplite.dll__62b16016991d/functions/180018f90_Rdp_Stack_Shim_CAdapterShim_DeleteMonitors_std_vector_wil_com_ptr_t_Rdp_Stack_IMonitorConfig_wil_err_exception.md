# Rdp::Stack::Shim::CAdapterShim::DeleteMonitors(std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>> const &)

- ea: `0x180018f90`
- end: `0x18001925c`
- name: `?DeleteMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXAEBV?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019894`

## callees

- `0x18000141c`
- `0x1800023fc`
- `0x180004cb4`
- `0x180007dd4`
- `0x18000cef0`
- `0x18000d98c`
- `0x180018170`
- `0x180018388`
- `0x1800187f8`
- `0x180018f90`
- `0x18001ae70`
- `0x18001b2f4`
- `0x18001ec84`
- `0x18002a010`

## string_xrefs

- `0x180019086`: `Rdp::Stack::Shim::CAdapterShim::DeleteMonitors`
- `0x1800191b0`: `Rdp::Stack::Shim::CAdapterShim::DeleteMonitors`
- `0x18001908d`: `AdapterShimDeleteMonitors: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Shim::CAdapterShim::DeleteMonitors(__int64 a1, _QWORD *a2)
{
  int v4; // r8d
  int v5; // r9d
  _QWORD *v6; // rbx
  _QWORD *v7; // rsi
  __int64 v8; // r13
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  int v13; // ebx
  int v14; // edi
  int v15; // esi
  int v16; // r14d
  int v17; // r15d
  Rdp::Modern::Utils::CInflightRecorder *Ifr; // rax
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  int v22; // r10d
  int v23; // r11d
  int v24; // ebx
  int v25; // edi
  int v26; // esi
  int v27; // r14d
  int v28; // r15d
  int v29; // r12d
  int v30; // r13d
  unsigned int v31; // eax
  int v32; // edx
  int v33; // r10d
  int v34; // r11d
  char *v35; // [rsp+28h] [rbp-61h]
  char *v36; // [rsp+28h] [rbp-61h]
  __int64 v37; // [rsp+30h] [rbp-59h]
  __int64 v38; // [rsp+30h] [rbp-59h]
  __int64 v39; // [rsp+38h] [rbp-51h]
  __int64 v40; // [rsp+38h] [rbp-51h]
  __int64 v41; // [rsp+40h] [rbp-49h]
  __int64 v42; // [rsp+40h] [rbp-49h]
  __int64 v43; // [rsp+48h] [rbp-41h]
  __int64 v44; // [rsp+48h] [rbp-41h]
  int v45; // [rsp+50h] [rbp-39h]
  __int64 v46; // [rsp+50h] [rbp-39h]
  int v47; // [rsp+58h] [rbp-31h]
  __int64 v48; // [rsp+58h] [rbp-31h]
  int v49; // [rsp+60h] [rbp-29h]
  __int64 v50; // [rsp+60h] [rbp-29h]
  int v51; // [rsp+68h] [rbp-21h]
  __int64 v52; // [rsp+68h] [rbp-21h]
  int v53; // [rsp+70h] [rbp-19h]
  __int64 v54; // [rsp+70h] [rbp-19h]
  int v55; // [rsp+78h] [rbp-11h]
  __int64 v56; // [rsp+78h] [rbp-11h]
  __int64 v57; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v58[11]; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  __int64 v60; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v61; // [rsp+F8h] [rbp+6Fh] BYREF
  __int128 *v62; // [rsp+100h] [rbp+77h] BYREF
  const char *v63; // [rsp+108h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v61 = (__int64)(a2[1] - *a2) >> 3;
    LODWORD(v60) = *(_DWORD *)(a1 + 336);
    v62 = &xmmword_18003CA50;
    v63 = "RdpLite";
    v57 = 0x1000000;
    v58[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&dword_180035754,
      v4,
      v5,
      (__int64)v58,
      (__int64)&v57,
      (__int64)&v63,
      (__int64)&v62,
      (__int64)&v60,
      (__int64)&v61);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterShimDeleteMonitors: %d",
    "Rdp::Stack::Shim::CAdapterShim::DeleteMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0x216u,
    (__int64)(a2[1] - *a2) >> 3);
  std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(v58, a1 + 176);
  v6 = (_QWORD *)a2[1];
  v7 = (_QWORD *)*a2;
  while ( v6 != v7 )
  {
    --v6;
    v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 40LL))(*v6);
    v61 = v8;
    std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(
      a1 + 160,
      &v60,
      v8);
    v9 = v60;
    if ( v60 == *(_QWORD *)(a1 + 160) )
    {
      v13 = *(unsigned __int8 *)(v8 + 10);
      v14 = *(unsigned __int8 *)(v8 + 9);
      v15 = *(unsigned __int8 *)(v8 + 8);
      v16 = *(unsigned __int16 *)(v8 + 6);
      v17 = *(unsigned __int16 *)(v8 + 4);
      Ifr = Rdp::Modern::Utils::CInflightRecorder::GetIfr();
      v55 = v19;
      v53 = v20;
      v51 = v21;
      v49 = v22;
      v47 = v23;
      v45 = v13;
      LODWORD(v43) = v14;
      LODWORD(v41) = v15;
      LODWORD(v39) = v16;
      LODWORD(v37) = v17;
      LODWORD(v35) = *(_DWORD *)v8;
      Rdp::Modern::Utils::CInflightRecorder::pushN(
        Ifr,
        (wchar_t *)L"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
        "Rdp::Stack::Shim::CAdapterShim::DeleteMonitors",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
        0x225u,
        v35,
        v37,
        v39,
        v41,
        v43,
        v45,
        v47,
        v49,
        v51,
        v53,
        v55);
      v24 = *(unsigned __int8 *)(v8 + 12);
      v25 = *(unsigned __int8 *)(v8 + 11);
      v26 = *(unsigned __int8 *)(v8 + 10);
      v27 = *(unsigned __int8 *)(v8 + 9);
      v28 = *(unsigned __int8 *)(v8 + 8);
      v29 = *(unsigned __int16 *)(v8 + 6);
      v30 = *(unsigned __int16 *)(v8 + 4);
      v31 = wil::verify_hresult<long>(2147943568LL);
      LODWORD(v56) = v32;
      LODWORD(v54) = v33;
      LODWORD(v52) = v34;
      LODWORD(v50) = v24;
      LODWORD(v48) = v25;
      LODWORD(v46) = v26;
      LODWORD(v44) = v27;
      LODWORD(v42) = v28;
      LODWORD(v40) = v29;
      LODWORD(v38) = v30;
      LODWORD(v36) = *(_DWORD *)v61;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x22A,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
        (const char *)v31,
        (int)"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
        v36,
        v38,
        v40,
        v42,
        v44,
        v46,
        v48,
        v50,
        v52,
        v54,
        v56);
    }
    Rdp::Stack::Shim::CMonitorShim::Stop(*(Rdp::Stack::Shim::CMonitorShim **)(v60 + 48));
    v10 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Extract(
            a1 + 160,
            v9);
    std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>>>(
      v11,
      v10);
  }
  return std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(v58);
}

```

## disassembly

```asm
0x180018f90  push    rbp
0x180018f92  push    rbx
0x180018f93  push    rsi
0x180018f94  push    rdi
0x180018f95  push    r12
0x180018f97  push    r13
0x180018f99  push    r14
0x180018f9b  push    r15
0x180018f9d  lea     rbp, [rsp-1Fh]
0x180018fa2  sub     rsp, 0A8h
0x180018fa9  mov     rsi, rdx
0x180018fac  mov     r14, rcx
0x180018faf  mov     eax, cs:dword_18003C058
0x180018fb5  cmp     eax, 4
0x180018fb8  jbe     loc_180019067
0x180018fbe  mov     rdx, 470000000000h
0x180018fc8  lea     rcx, dword_18003C058
0x180018fcf  call    _tlgKeywordOn
0x180018fd4  test    al, al
0x180018fd6  jz      loc_180019067
0x180018fdc  mov     rax, [rsi+8]
0x180018fe0  sub     rax, [rsi]
0x180018fe3  sar     rax, 3
0x180018fe7  mov     [rbp+57h+arg_8], rax
0x180018feb  mov     eax, [r14+150h]
0x180018ff2  mov     dword ptr [rbp+57h+arg_0], eax
0x180018ff5  lea     rax, xmmword_18003CA50
0x180018ffc  mov     [rbp+57h+arg_10], rax
0x180019000  lea     rax, aRdplite; "RdpLite"
0x180019007  mov     [rbp+57h+arg_18], rax
0x18001900b  mov     [rbp+57h+var_60], 1000000h
0x180019013  lea     rax, aCheckpoint; "Checkpoint"
0x18001901a  mov     [rbp+57h+var_58], rax
0x18001901e  lea     rax, [rbp+57h+arg_8]
0x180019022  mov     [rsp+0E0h+var_98], rax
0x180019027  lea     rax, [rbp+57h+arg_0]
0x18001902b  mov     [rsp+0E0h+var_A0], rax
0x180019030  lea     rax, [rbp+57h+arg_10]
0x180019034  mov     [rsp+0E0h+var_A8], rax
0x180019039  lea     rax, [rbp+57h+arg_18]
0x18001903d  mov     [rsp+0E0h+var_B0], rax
0x180019042  lea     rax, [rbp+57h+var_60]
0x180019046  mov     [rsp+0E0h+var_B8], rax
0x18001904b  lea     rax, [rbp+57h+var_58]
0x18001904f  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180019054  lea     rdx, dword_180035754
0x18001905b  lea     rcx, dword_18003C058
0x180019062  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180019067  mov     rax, [rsi+8]
0x18001906b  sub     rax, [rsi]
0x18001906e  sar     rax, 3
0x180019072  mov     [rsp+0E0h+var_B8], rax
0x180019077  mov     [rsp+0E0h+var_C0], 216h; unsigned int
0x18001907f  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180019086  lea     r8, aRdpStackShimCa_1; "Rdp::Stack::Shim::CAdapterShim::DeleteM"...
0x18001908d  lea     rdx, aAdaptershimdel; "AdapterShimDeleteMonitors: %d"
0x180019094  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001909b  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800190a0  lea     rdx, [r14+0B0h]
0x1800190a7  lea     rcx, [rbp+57h+var_58]
0x1800190ab  call    ??0?$unique_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::unique_lock<std::shared_mutex>::unique_lock<std::shared_mutex>(std::shared_mutex &)
0x1800190b0  nop
0x1800190b1  mov     rbx, [rsi+8]
0x1800190b5  mov     rsi, [rsi]
0x1800190b8  cmp     rbx, rsi
0x1800190bb  jz      short loc_180019114
0x1800190bd  add     rbx, 0FFFFFFFFFFFFFFF8h
0x1800190c1  mov     rcx, [rbx]
0x1800190c4  mov     rax, [rcx]
0x1800190c7  mov     rax, [rax+28h]
0x1800190cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190d0  mov     r13, rax
0x1800190d3  mov     [rbp+57h+arg_8], rax
0x1800190d7  lea     r15, [r14+0A0h]
0x1800190de  mov     r8, rax
0x1800190e1  lea     rdx, [rbp+57h+arg_0]
0x1800190e5  mov     rcx, r15
0x1800190e8  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(_GUID const &)
0x1800190ed  mov     rdi, [rbp+57h+arg_0]
0x1800190f1  cmp     rdi, [r15]
0x1800190f4  jz      short loc_180019131
0x1800190f6  mov     rcx, [rdi+30h]; this
0x1800190fa  call    ?Stop@CMonitorShim@Shim@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Shim::CMonitorShim::Stop(void)
0x1800190ff  mov     rdx, rdi
0x180019102  mov     rcx, r15
0x180019105  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>>,std::_Iterator_base0>)
0x18001910a  mov     rdx, rax
0x18001910d  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *>> &,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>,void *> *)
0x180019112  jmp     short loc_1800190B8
0x180019114  lea     rcx, [rbp+57h+var_58]
0x180019118  call    ??1?$unique_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::shared_mutex>::~unique_lock<std::shared_mutex>(void)
0x18001911d  add     rsp, 0A8h
0x180019124  pop     r15
0x180019126  pop     r14
0x180019128  pop     r13
0x18001912a  pop     r12
0x18001912c  pop     rdi
0x18001912d  pop     rsi
0x18001912e  pop     rbx
0x18001912f  pop     rbp
0x180019130  retn
0x180019131  movzx   edx, byte ptr [r13+0Fh]
0x180019136  movzx   r8d, byte ptr [r13+0Eh]
0x18001913b  movzx   r9d, byte ptr [r13+0Dh]
0x180019140  movzx   r10d, byte ptr [r13+0Ch]
0x180019145  movzx   r11d, byte ptr [r13+0Bh]
0x18001914a  movzx   ebx, byte ptr [r13+0Ah]
0x18001914f  movzx   edi, byte ptr [r13+9]
0x180019154  movzx   esi, byte ptr [r13+8]
0x180019159  movzx   r14d, word ptr [r13+6]
0x18001915e  movzx   r15d, word ptr [r13+4]
0x180019163  call    ?GetIfr@CInflightRecorder@Utils@Modern@Rdp@@SAAEAV1234@XZ; Rdp::Modern::Utils::CInflightRecorder::GetIfr(void)
0x180019168  mov     rcx, rax; this
0x18001916b  mov     dword ptr [rsp+0E0h+var_68], edx
0x18001916f  mov     dword ptr [rsp+0E0h+var_70], r8d
0x180019174  mov     dword ptr [rsp+0E0h+var_78], r9d
0x180019179  mov     dword ptr [rsp+0E0h+var_80], r10d
0x18001917e  mov     dword ptr [rsp+0E0h+var_88], r11d
0x180019183  mov     dword ptr [rsp+0E0h+var_90], ebx
0x180019187  mov     dword ptr [rsp+0E0h+var_98], edi
0x18001918b  mov     dword ptr [rsp+0E0h+var_A0], esi
0x18001918f  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x180019194  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x180019199  mov     eax, [r13+0]
0x18001919d  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800191a1  mov     [rsp+0E0h+var_C0], 225h; unsigned int
0x1800191a9  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800191b0  lea     r8, aRdpStackShimCa_1; "Rdp::Stack::Shim::CAdapterShim::DeleteM"...
0x1800191b7  lea     rdx, aMonitor08lx04h; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x1800191be  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800191c3  movzx   edx, byte ptr [r13+0Fh]
0x1800191c8  movzx   r10d, byte ptr [r13+0Eh]
0x1800191cd  movzx   r11d, byte ptr [r13+0Dh]
0x1800191d2  movzx   ebx, byte ptr [r13+0Ch]
0x1800191d7  movzx   edi, byte ptr [r13+0Bh]
0x1800191dc  movzx   esi, byte ptr [r13+0Ah]
0x1800191e1  movzx   r14d, byte ptr [r13+9]
0x1800191e6  movzx   r15d, byte ptr [r13+8]
0x1800191eb  movzx   r12d, word ptr [r13+6]
0x1800191f0  movzx   r13d, word ptr [r13+4]
0x1800191f5  mov     ecx, 80070490h
0x1800191fa  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800191ff  mov     r9d, eax; char *
0x180019202  mov     rcx, [rbp+5Fh]; this
0x180019206  mov     dword ptr [rsp+0E0h+var_68], edx
0x18001920a  mov     dword ptr [rsp+0E0h+var_70], r10d
0x18001920f  mov     dword ptr [rsp+0E0h+var_78], r11d
0x180019214  mov     dword ptr [rsp+0E0h+var_80], ebx
0x180019218  mov     dword ptr [rsp+0E0h+var_88], edi
0x18001921c  mov     dword ptr [rsp+0E0h+var_90], esi
0x180019220  mov     dword ptr [rsp+0E0h+var_98], r14d
0x180019225  mov     dword ptr [rsp+0E0h+var_A0], r15d
0x18001922a  mov     dword ptr [rsp+0E0h+var_A8], r12d
0x18001922f  mov     dword ptr [rsp+0E0h+var_B0], r13d
0x180019234  mov     rax, [rbp+57h+arg_8]
0x180019238  mov     eax, [rax]
0x18001923a  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18001923e  lea     rax, aMonitor08lx04h_0; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x180019245  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001924a  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180019251  mov     edx, 22Ah; void *
0x180019256  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
