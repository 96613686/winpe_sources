# Rdp::Stack::Shim::CAdapterShim::UpdateMonitors(std::vector<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::IMonitorConfig,wil::err_exception_policy>>> const &)

- ea: `0x18001aac8`
- end: `0x18001add1`
- name: `?UpdateMonitors@CAdapterShim@Shim@Stack@Rdp@@AEAAXAEBV?$vector@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMonitorConfig@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `777`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180019894`

## callees

- `0x18000141c`
- `0x1800023fc`
- `0x180004cb4`
- `0x180007dd4`
- `0x18000cef0`
- `0x18000d98c`
- `0x180018360`
- `0x1800187a0`
- `0x18001a92c`
- `0x18001aac8`
- `0x18001b2f4`
- `0x18001cdfc`
- `0x18002a010`

## string_xrefs

- `0x18001abbd`: `Rdp::Stack::Shim::CAdapterShim::UpdateMonitors`
- `0x18001ad25`: `Rdp::Stack::Shim::CAdapterShim::UpdateMonitors`
- `0x18001abc4`: `AdapterShimUpdateMonitors: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Shim::CAdapterShim::UpdateMonitors(__int64 a1, _QWORD *a2)
{
  int v4; // r8d
  int v5; // r9d
  _QWORD *v6; // rdi
  _QWORD *v7; // r15
  _QWORD *v8; // r14
  __int64 v9; // r13
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rsi
  unsigned int v14; // eax
  int v16; // ebx
  int v17; // edi
  int v18; // esi
  int v19; // r14d
  int v20; // r15d
  Rdp::Modern::Utils::CInflightRecorder *Ifr; // rax
  int v22; // edx
  int v23; // r8d
  int v24; // r9d
  int v25; // r10d
  int v26; // r11d
  int v27; // ebx
  int v28; // edi
  int v29; // esi
  int v30; // r14d
  int v31; // r15d
  int v32; // r12d
  int v33; // r13d
  unsigned int v34; // eax
  int v35; // edx
  int v36; // r10d
  int v37; // r11d
  char *v38; // [rsp+28h] [rbp-61h]
  char *v39; // [rsp+28h] [rbp-61h]
  __int64 v40; // [rsp+30h] [rbp-59h]
  __int64 v41; // [rsp+30h] [rbp-59h]
  __int64 v42; // [rsp+38h] [rbp-51h]
  __int64 v43; // [rsp+38h] [rbp-51h]
  __int64 v44; // [rsp+40h] [rbp-49h]
  __int64 v45; // [rsp+40h] [rbp-49h]
  __int64 v46; // [rsp+48h] [rbp-41h]
  __int64 v47; // [rsp+48h] [rbp-41h]
  int v48; // [rsp+50h] [rbp-39h]
  __int64 v49; // [rsp+50h] [rbp-39h]
  int v50; // [rsp+58h] [rbp-31h]
  __int64 v51; // [rsp+58h] [rbp-31h]
  int v52; // [rsp+60h] [rbp-29h]
  __int64 v53; // [rsp+60h] [rbp-29h]
  int v54; // [rsp+68h] [rbp-21h]
  __int64 v55; // [rsp+68h] [rbp-21h]
  int v56; // [rsp+70h] [rbp-19h]
  __int64 v57; // [rsp+70h] [rbp-19h]
  int v58; // [rsp+78h] [rbp-11h]
  __int64 v59; // [rsp+78h] [rbp-11h]
  __int64 v60; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v61[11]; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  __int64 v63; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v64; // [rsp+F8h] [rbp+6Fh] BYREF
  __int128 *v65; // [rsp+100h] [rbp+77h] BYREF
  const char *v66; // [rsp+108h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v64 = (__int64)(a2[1] - *a2) >> 3;
    LODWORD(v63) = *(_DWORD *)(a1 + 336);
    v65 = &xmmword_18003CA50;
    v66 = "RdpLite";
    v60 = 0x1000000;
    v61[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)word_180035622,
      v4,
      v5,
      (__int64)v61,
      (__int64)&v60,
      (__int64)&v66,
      (__int64)&v65,
      (__int64)&v63,
      (__int64)&v64);
  }
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterShimUpdateMonitors: %d",
    "Rdp::Stack::Shim::CAdapterShim::UpdateMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
    0x27Eu,
    (__int64)(a2[1] - *a2) >> 3);
  std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v61, a1 + 176);
  v6 = (_QWORD *)*a2;
  v7 = (_QWORD *)a2[1];
  if ( (_QWORD *)*a2 != v7 )
  {
    v8 = (_QWORD *)(a1 + 160);
    do
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 40LL))(*v6);
      v64 = v9;
      std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(
        v8,
        &v63,
        v9);
      v10 = v63;
      if ( v63 == *v8 )
      {
        v16 = *(unsigned __int8 *)(v9 + 10);
        v17 = *(unsigned __int8 *)(v9 + 9);
        v18 = *(unsigned __int8 *)(v9 + 8);
        v19 = *(unsigned __int16 *)(v9 + 6);
        v20 = *(unsigned __int16 *)(v9 + 4);
        Ifr = Rdp::Modern::Utils::CInflightRecorder::GetIfr();
        v58 = v22;
        v56 = v23;
        v54 = v24;
        v52 = v25;
        v50 = v26;
        v48 = v16;
        LODWORD(v46) = v17;
        LODWORD(v44) = v18;
        LODWORD(v42) = v19;
        LODWORD(v40) = v20;
        LODWORD(v38) = *(_DWORD *)v9;
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          Ifr,
          (wchar_t *)L"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
          "Rdp::Stack::Shim::CAdapterShim::UpdateMonitors",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
          0x290u,
          v38,
          v40,
          v42,
          v44,
          v46,
          v48,
          v50,
          v52,
          v54,
          v56,
          v58);
        v27 = *(unsigned __int8 *)(v9 + 12);
        v28 = *(unsigned __int8 *)(v9 + 11);
        v29 = *(unsigned __int8 *)(v9 + 10);
        v30 = *(unsigned __int8 *)(v9 + 9);
        v31 = *(unsigned __int8 *)(v9 + 8);
        v32 = *(unsigned __int16 *)(v9 + 6);
        v33 = *(unsigned __int16 *)(v9 + 4);
        v34 = wil::verify_hresult<long>(2147943568LL);
        LODWORD(v59) = v35;
        LODWORD(v57) = v36;
        LODWORD(v55) = v37;
        LODWORD(v53) = v27;
        LODWORD(v51) = v28;
        LODWORD(v49) = v29;
        LODWORD(v47) = v30;
        LODWORD(v45) = v31;
        LODWORD(v43) = v32;
        LODWORD(v41) = v33;
        LODWORD(v39) = *(_DWORD *)v64;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x295,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
          (const char *)v34,
          (int)"Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX} is not found",
          v39,
          v41,
          v43,
          v45,
          v47,
          v49,
          v51,
          v53,
          v55,
          v57,
          v59);
      }
      v11 = *(_QWORD *)(v63 + 48);
      v12 = *v6;
      v13 = *(_QWORD *)(v11 + 240);
      *(_QWORD *)(v11 + 240) = *v6;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v14 = Rdp::Stack::Shim::CMonitorShim::ApplyMonitorConfiguration(*(_QWORD *)(v10 + 48));
      Rdp::Stack::Shim::CMonitorShim::TriggerModeChange(*(_QWORD *)(v10 + 48), v14);
      ++v6;
    }
    while ( v6 != v7 );
  }
  return std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v61);
}

```

## disassembly

```asm
0x18001aac8  push    rbp
0x18001aaca  push    rbx
0x18001aacb  push    rsi
0x18001aacc  push    rdi
0x18001aacd  push    r12
0x18001aacf  push    r13
0x18001aad1  push    r14
0x18001aad3  push    r15
0x18001aad5  lea     rbp, [rsp-1Fh]
0x18001aada  sub     rsp, 0A8h
0x18001aae1  mov     rbx, rdx
0x18001aae4  mov     rsi, rcx
0x18001aae7  mov     eax, cs:dword_18003C058
0x18001aaed  cmp     eax, 4
0x18001aaf0  jbe     loc_18001AB9E
0x18001aaf6  mov     rdx, 470000000000h
0x18001ab00  lea     rcx, dword_18003C058
0x18001ab07  call    _tlgKeywordOn
0x18001ab0c  test    al, al
0x18001ab0e  jz      loc_18001AB9E
0x18001ab14  mov     rax, [rbx+8]
0x18001ab18  sub     rax, [rbx]
0x18001ab1b  sar     rax, 3
0x18001ab1f  mov     [rbp+57h+arg_8], rax
0x18001ab23  mov     eax, [rsi+150h]
0x18001ab29  mov     dword ptr [rbp+57h+arg_0], eax
0x18001ab2c  lea     rax, xmmword_18003CA50
0x18001ab33  mov     [rbp+57h+arg_10], rax
0x18001ab37  lea     rax, aRdplite; "RdpLite"
0x18001ab3e  mov     [rbp+57h+arg_18], rax
0x18001ab42  mov     [rbp+57h+var_60], 1000000h
0x18001ab4a  lea     rax, aCheckpoint; "Checkpoint"
0x18001ab51  mov     [rbp+57h+var_58], rax
0x18001ab55  lea     rax, [rbp+57h+arg_8]
0x18001ab59  mov     [rsp+0E0h+var_98], rax
0x18001ab5e  lea     rax, [rbp+57h+arg_0]
0x18001ab62  mov     [rsp+0E0h+var_A0], rax
0x18001ab67  lea     rax, [rbp+57h+arg_10]
0x18001ab6b  mov     [rsp+0E0h+var_A8], rax
0x18001ab70  lea     rax, [rbp+57h+arg_18]
0x18001ab74  mov     [rsp+0E0h+var_B0], rax
0x18001ab79  lea     rax, [rbp+57h+var_60]
0x18001ab7d  mov     [rsp+0E0h+var_B8], rax
0x18001ab82  lea     rax, [rbp+57h+var_58]
0x18001ab86  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18001ab8b  lea     rdx, word_180035622
0x18001ab92  lea     rcx, dword_18003C058
0x18001ab99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001ab9e  mov     rax, [rbx+8]
0x18001aba2  sub     rax, [rbx]
0x18001aba5  sar     rax, 3
0x18001aba9  mov     [rsp+0E0h+var_B8], rax
0x18001abae  mov     [rsp+0E0h+var_C0], 27Eh; unsigned int
0x18001abb6  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001abbd  lea     r8, aRdpStackShimCa; "Rdp::Stack::Shim::CAdapterShim::UpdateM"...
0x18001abc4  lea     rdx, aAdaptershimupd; "AdapterShimUpdateMonitors: %d"
0x18001abcb  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001abd2  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001abd7  lea     rdx, [rsi+0B0h]
0x18001abde  lea     rcx, [rbp+57h+var_58]
0x18001abe2  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18001abe7  nop
0x18001abe8  mov     rdi, [rbx]
0x18001abeb  mov     r15, [rbx+8]
0x18001abef  cmp     rdi, r15
0x18001abf2  jz      loc_18001AC89
0x18001abf8  lea     r14, [rsi+0A0h]
0x18001abff  mov     rcx, [rdi]
0x18001ac02  mov     rax, [rcx]
0x18001ac05  mov     rax, [rax+28h]
0x18001ac09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac0e  mov     r13, rax
0x18001ac11  mov     [rbp+57h+arg_8], rax
0x18001ac15  mov     r8, rax
0x18001ac18  lea     rdx, [rbp+57h+arg_0]
0x18001ac1c  mov     rcx, r14
0x18001ac1f  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@UMonitorIdComparer@CAdapterShim@Shim@Stack@Rdp@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>,Rdp::Stack::Shim::CAdapterShim::MonitorIdComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>>>,0>>::find(_GUID const &)
0x18001ac24  mov     rbx, [rbp+57h+arg_0]
0x18001ac28  cmp     rbx, [r14]
0x18001ac2b  jz      short loc_18001ACA6
0x18001ac2d  mov     rax, [rbx+30h]
0x18001ac31  mov     rcx, [rdi]
0x18001ac34  mov     rsi, [rax+0F0h]
0x18001ac3b  mov     [rax+0F0h], rcx
0x18001ac42  test    rcx, rcx
0x18001ac45  jz      short loc_18001AC53
0x18001ac47  mov     rax, [rcx]
0x18001ac4a  mov     rax, [rax+8]
0x18001ac4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac53  test    rsi, rsi
0x18001ac56  jz      short loc_18001AC68
0x18001ac58  mov     rax, [rsi]
0x18001ac5b  mov     rcx, rsi
0x18001ac5e  mov     rax, [rax+10h]
0x18001ac62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac67  nop
0x18001ac68  mov     rcx, [rbx+30h]
0x18001ac6c  call    ?ApplyMonitorConfiguration@CMonitorShim@Shim@Stack@Rdp@@QEAA?AW4AVENC_MONITOR_UPDATE_FLAGS@Avenc@4@XZ; Rdp::Stack::Shim::CMonitorShim::ApplyMonitorConfiguration(void)
0x18001ac71  mov     edx, eax
0x18001ac73  mov     rcx, [rbx+30h]
0x18001ac77  call    ?TriggerModeChange@CMonitorShim@Shim@Stack@Rdp@@QEAAXW4AVENC_MONITOR_UPDATE_FLAGS@Avenc@4@@Z; Rdp::Stack::Shim::CMonitorShim::TriggerModeChange(Rdp::Avenc::AVENC_MONITOR_UPDATE_FLAGS)
0x18001ac7c  add     rdi, 8
0x18001ac80  cmp     rdi, r15
0x18001ac83  jnz     loc_18001ABFF
0x18001ac89  lea     rcx, [rbp+57h+var_58]
0x18001ac8d  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x18001ac92  add     rsp, 0A8h
0x18001ac99  pop     r15
0x18001ac9b  pop     r14
0x18001ac9d  pop     r13
0x18001ac9f  pop     r12
0x18001aca1  pop     rdi
0x18001aca2  pop     rsi
0x18001aca3  pop     rbx
0x18001aca4  pop     rbp
0x18001aca5  retn
0x18001aca6  movzx   edx, byte ptr [r13+0Fh]
0x18001acab  movzx   r8d, byte ptr [r13+0Eh]
0x18001acb0  movzx   r9d, byte ptr [r13+0Dh]
0x18001acb5  movzx   r10d, byte ptr [r13+0Ch]
0x18001acba  movzx   r11d, byte ptr [r13+0Bh]
0x18001acbf  movzx   ebx, byte ptr [r13+0Ah]
0x18001acc4  movzx   edi, byte ptr [r13+9]
0x18001acc9  movzx   esi, byte ptr [r13+8]
0x18001acce  movzx   r14d, word ptr [r13+6]
0x18001acd3  movzx   r15d, word ptr [r13+4]
0x18001acd8  call    ?GetIfr@CInflightRecorder@Utils@Modern@Rdp@@SAAEAV1234@XZ; Rdp::Modern::Utils::CInflightRecorder::GetIfr(void)
0x18001acdd  mov     rcx, rax; this
0x18001ace0  mov     dword ptr [rsp+0E0h+var_68], edx
0x18001ace4  mov     dword ptr [rsp+0E0h+var_70], r8d
0x18001ace9  mov     dword ptr [rsp+0E0h+var_78], r9d
0x18001acee  mov     dword ptr [rsp+0E0h+var_80], r10d
0x18001acf3  mov     dword ptr [rsp+0E0h+var_88], r11d
0x18001acf8  mov     dword ptr [rsp+0E0h+var_90], ebx
0x18001acfc  mov     dword ptr [rsp+0E0h+var_98], edi
0x18001ad00  mov     dword ptr [rsp+0E0h+var_A0], esi
0x18001ad04  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x18001ad09  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x18001ad0e  mov     eax, [r13+0]
0x18001ad12  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18001ad16  mov     [rsp+0E0h+var_C0], 290h; unsigned int
0x18001ad1e  lea     r9, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001ad25  lea     r8, aRdpStackShimCa; "Rdp::Stack::Shim::CAdapterShim::UpdateM"...
0x18001ad2c  lea     rdx, aMonitor08lx04h; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x18001ad33  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001ad38  movzx   edx, byte ptr [r13+0Fh]
0x18001ad3d  movzx   r10d, byte ptr [r13+0Eh]
0x18001ad42  movzx   r11d, byte ptr [r13+0Dh]
0x18001ad47  movzx   ebx, byte ptr [r13+0Ch]
0x18001ad4c  movzx   edi, byte ptr [r13+0Bh]
0x18001ad51  movzx   esi, byte ptr [r13+0Ah]
0x18001ad56  movzx   r14d, byte ptr [r13+9]
0x18001ad5b  movzx   r15d, byte ptr [r13+8]
0x18001ad60  movzx   r12d, word ptr [r13+6]
0x18001ad65  movzx   r13d, word ptr [r13+4]
0x18001ad6a  mov     ecx, 80070490h
0x18001ad6f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001ad74  mov     r9d, eax; char *
0x18001ad77  mov     rcx, [rbp+5Fh]; this
0x18001ad7b  mov     dword ptr [rsp+0E0h+var_68], edx
0x18001ad7f  mov     dword ptr [rsp+0E0h+var_70], r10d
0x18001ad84  mov     dword ptr [rsp+0E0h+var_78], r11d
0x18001ad89  mov     dword ptr [rsp+0E0h+var_80], ebx
0x18001ad8d  mov     dword ptr [rsp+0E0h+var_88], edi
0x18001ad91  mov     dword ptr [rsp+0E0h+var_90], esi
0x18001ad95  mov     dword ptr [rsp+0E0h+var_98], r14d
0x18001ad9a  mov     dword ptr [rsp+0E0h+var_A0], r15d
0x18001ad9f  mov     dword ptr [rsp+0E0h+var_A8], r12d
0x18001ada4  mov     dword ptr [rsp+0E0h+var_B0], r13d
0x18001ada9  mov     rax, [rbp+57h+arg_8]
0x18001adad  mov     eax, [rax]
0x18001adaf  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18001adb3  lea     rax, aMonitor08lx04h_0; "Monitor {%08lX-%04hX-%04hX-%02hhX%02hhX"...
0x18001adba  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18001adbf  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001adc6  mov     edx, 295h; void *
0x18001adcb  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
