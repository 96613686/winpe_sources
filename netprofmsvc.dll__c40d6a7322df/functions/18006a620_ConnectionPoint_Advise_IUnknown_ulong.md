# ConnectionPoint::Advise(IUnknown *,ulong *)

- ea: `0x18006a620`
- end: `0x18006a91b`
- name: `?Advise@ConnectionPoint@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `763`
- prototype: `__int64 __fastcall(ConnectionPoint *__hidden this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009990`
- `0x18000e190`
- `0x18000eab0`
- `0x180015628`
- `0x180015710`
- `0x180035fec`
- `0x180048b30`
- `0x180048d68`
- `0x18004ee88`
- `0x18004ef4c`
- `0x180069f20`
- `0x18006a620`
- `0x1800903a8`
- `0x180092b30`
- `0x1800a88a0`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a8ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a8ba`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006a742`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006a7d3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006a8ed`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006a742`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006a7d3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18006a8ed`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006a686`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006a686`

## string_xrefs

- `0x18006a670`: `onecore\net\netprofiles\service\src\common\connectionpoint.cpp`
- `0x18006a6a5`: `onecore\net\netprofiles\service\src\common\connectionpoint.cpp`
- `0x18006a722`: `onecore\net\netprofiles\service\src\common\connectionpoint.cpp`
- `0x18006a7a5`: `onecore\net\netprofiles\service\src\common\connectionpoint.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall ConnectionPoint::Advise(ConnectionPoint *this, struct IUnknown *a2, unsigned int *a3)
{
  HRESULT v7; // eax
  int v8; // ebx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rax
  _DWORD *v14; // rbx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // ecx
  int v18; // [rsp+20h] [rbp-A8h]
  int v19; // [rsp+44h] [rbp-84h] BYREF
  int v20; // [rsp+48h] [rbp-80h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-78h] BYREF
  ConnectedProcess *v22[2]; // [rsp+58h] [rbp-70h] BYREF
  char *v23; // [rsp+68h] [rbp-60h] BYREF
  std::_Ref_count_base *v24; // [rsp+70h] [rbp-58h]
  _BYTE v25[16]; // [rsp+78h] [rbp-50h] BYREF
  __int64 v26; // [rsp+88h] [rbp-40h] BYREF
  __int64 v27; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  StandbyMonitor::ProcessClientActivity(94);
  *a3 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectionpoint.cpp",
      (const char *)0x80070057LL,
      v18);
    return 2147942487LL;
  }
  v7 = CoImpersonateClient();
  v8 = 0;
  if ( v7 != -2147417833 )
    v8 = v7;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectionpoint.cpp",
      (const char *)(unsigned int)v8,
      v18);
    return (unsigned int)v8;
  }
  SetProxyBlanket(a2);
  v26 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::reset(&v26);
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, char *, __int64 *))QueryInterface)(a2, (char *)this + 16, &v26);
  v11 = v10;
  if ( v10 == -2147467262 )
  {
    v11 = -2147220990;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectionpoint.cpp",
      (const char *)v11,
      v18);
    wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(&v26);
    CoRevertToSelf();
    return v11;
  }
  if ( v10 < 0 )
    goto LABEL_10;
  SetProxyBlanket(v26);
  v12 = *((_QWORD *)this + 4);
  v27 = 0;
  (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v12 + 24LL))(
    v12,
    &GUID_16aa7b9f_e8af_4552_a88c_8fecd5f1d464,
    &v27);
  if ( v27 )
  {
    *(_OWORD *)v22 = 0;
    ConnectionPointContainer::GetConnectedProcessForCaller(v27, v22);
    ConnectedProcess::IncrementRef(v22[0]);
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 40);
    v13 = std::make_shared<ConnectionPoint::Connection,wil::com_ptr_t<IUnknown,wil::err_exception_policy> &,std::shared_ptr<ConnectedProcess> &>(
            &v23,
            &v26,
            v22);
    v14 = (_DWORD *)((char *)this + 96);
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<ConnectionPoint::Connection>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<ConnectionPoint::Connection>>>,0>>::_Emplace<unsigned long &,std::shared_ptr<ConnectionPoint::Connection>>(
      (char *)this + 80,
      v25,
      (char *)this + 96,
      v13);
    if ( v24 )
      std::_Ref_count_base::_Decref(v24);
    v17 = (*v14)++;
    *a3 = v17;
    if ( (unsigned int)dword_1801BD288 > 4 )
    {
      v23 = (char *)this + 16;
      v20 = *((_DWORD *)v22[0] + 70);
      v19 = *a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        v20,
        (unsigned int)qword_18019A1E0,
        v15,
        v16,
        (__int64)&v19,
        (__int64)&v20,
        (__int64)&v23);
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    if ( v22[1] )
      std::_Ref_count_base::_Decref(v22[1]);
    wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::~com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>(&v27);
    wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(&v26);
    CoRevertToSelf();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectionpoint.cpp",
      (const char *)0x80070015LL,
      v18);
    wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::~com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>(&v27);
    wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(&v26);
    CoRevertToSelf();
    return 2147942421LL;
  }
}

```

## disassembly

```asm
0x18006a620  push    rbx
0x18006a622  push    rsi
0x18006a623  push    rdi
0x18006a624  push    r14
0x18006a626  push    r15
0x18006a628  sub     rsp, 0A0h
0x18006a62f  mov     rax, cs:__security_cookie
0x18006a636  xor     rax, rsp
0x18006a639  mov     [rsp+0C8h+var_30], rax
0x18006a641  mov     r14, r8
0x18006a644  mov     rdi, rdx
0x18006a647  mov     rsi, rcx
0x18006a64a  mov     ecx, 5Eh ; '^'
0x18006a64f  call    ?ProcessClientActivity@StandbyMonitor@@YAXW4ClientActivity@1@@Z; StandbyMonitor::ProcessClientActivity(StandbyMonitor::ClientActivity)
0x18006a654  mov     dword ptr [r14], 0
0x18006a65b  test    rdi, rdi
0x18006a65e  jnz     short loc_18006A686
0x18006a660  mov     rcx, [rsp+0C8h]; this
0x18006a668  mov     ebx, 80070057h
0x18006a66d  mov     r9d, ebx; char *
0x18006a670  lea     r8, aOnecoreNetNetp_34; "onecore\\net\\netprofiles\\service\\src"...
0x18006a677  lea     edx, [rdi+35h]; void *
0x18006a67a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a67f  mov     eax, ebx
0x18006a681  jmp     loc_18006A8FB
0x18006a686  call    cs:__imp_CoImpersonateClient
0x18006a68c  xor     ebx, ebx
0x18006a68e  cmp     eax, 80010117h
0x18006a693  cmovnz  ebx, eax
0x18006a696  test    ebx, ebx
0x18006a698  jns     short loc_18006A6BD
0x18006a69a  mov     rcx, [rsp+0C8h]; this
0x18006a6a2  mov     r9d, ebx; char *
0x18006a6a5  lea     r8, aOnecoreNetNetp_34; "onecore\\net\\netprofiles\\service\\src"...
0x18006a6ac  mov     edx, 3Ch ; '<'; void *
0x18006a6b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a6b6  mov     eax, ebx
0x18006a6b8  jmp     loc_18006A8FB
0x18006a6bd  mov     [rsp+0C8h+var_88], 1
0x18006a6c2  mov     rcx, rdi
0x18006a6c5  call    SetProxyBlanket
0x18006a6ca  mov     [rsp+0C8h+var_40], 0
0x18006a6d6  mov     rax, [rdi]
0x18006a6d9  mov     rbx, [rax]
0x18006a6dc  lea     rcx, [rsp+0C8h+var_40]
0x18006a6e4  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::reset(void)
0x18006a6e9  lea     r15, [rsi+10h]
0x18006a6ed  lea     r8, [rsp+0C8h+var_40]
0x18006a6f5  mov     rdx, r15
0x18006a6f8  mov     rcx, rdi
0x18006a6fb  mov     rax, rbx
0x18006a6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a703  mov     ebx, eax
0x18006a705  cmp     eax, 80004002h
0x18006a70a  jnz     short loc_18006A713
0x18006a70c  mov     ebx, 80040202h
0x18006a711  jmp     short loc_18006A717
0x18006a713  test    eax, eax
0x18006a715  jns     short loc_18006A74F
0x18006a717  mov     rcx, [rsp+0C8h]; this
0x18006a71f  mov     r9d, ebx; char *
0x18006a722  lea     r8, aOnecoreNetNetp_34; "onecore\\net\\netprofiles\\service\\src"...
0x18006a729  mov     edx, 47h ; 'G'; void *
0x18006a72e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a733  nop
0x18006a734  lea     rcx, [rsp+0C8h+var_40]
0x18006a73c  call    ??1?$com_ptr_t@UINetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(void)
0x18006a741  nop
0x18006a742  call    cs:__imp_CoRevertToSelf
0x18006a748  mov     eax, ebx
0x18006a74a  jmp     loc_18006A8FB
0x18006a74f  mov     rcx, [rsp+0C8h+var_40]
0x18006a757  call    SetProxyBlanket
0x18006a75c  mov     rcx, [rsi+20h]
0x18006a760  mov     [rsp+0C8h+var_38], 0
0x18006a76c  mov     rax, [rcx]
0x18006a76f  lea     r8, [rsp+0C8h+var_38]
0x18006a777  lea     rdx, _GUID_16aa7b9f_e8af_4552_a88c_8fecd5f1d464
0x18006a77e  mov     rax, [rax+18h]
0x18006a782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a787  nop
0x18006a788  mov     rcx, [rsp+0C8h+var_38]
0x18006a790  test    rcx, rcx
0x18006a793  jnz     short loc_18006A7E0
0x18006a795  mov     rcx, [rsp+0C8h]; this
0x18006a79d  mov     ebx, 80070015h
0x18006a7a2  mov     r9d, ebx; char *
0x18006a7a5  lea     r8, aOnecoreNetNetp_34; "onecore\\net\\netprofiles\\service\\src"...
0x18006a7ac  mov     edx, 4Bh ; 'K'; void *
0x18006a7b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a7b6  nop
0x18006a7b7  lea     rcx, [rsp+0C8h+var_38]
0x18006a7bf  call    ??1?$com_ptr_t@VConnectionPointContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::~com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>(void)
0x18006a7c4  nop
0x18006a7c5  lea     rcx, [rsp+0C8h+var_40]
0x18006a7cd  call    ??1?$com_ptr_t@UINetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(void)
0x18006a7d2  nop
0x18006a7d3  call    cs:__imp_CoRevertToSelf
0x18006a7d9  mov     eax, ebx
0x18006a7db  jmp     loc_18006A8FB
0x18006a7e0  xorps   xmm0, xmm0
0x18006a7e3  movups  xmmword ptr [rsp+0C8h+var_70], xmm0
0x18006a7e8  lea     rdx, [rsp+0C8h+var_70]
0x18006a7ed  call    ?GetConnectedProcessForCaller@ConnectionPointContainer@@QEAA?AV?$shared_ptr@VConnectedProcess@@@std@@XZ; ConnectionPointContainer::GetConnectedProcessForCaller(void)
0x18006a7f2  nop
0x18006a7f3  mov     rcx, [rsp+0C8h+var_70]; this
0x18006a7f8  call    ?IncrementRef@ConnectedProcess@@QEAAXXZ; ConnectedProcess::IncrementRef(void)
0x18006a7fd  mov     [rsp+0C8h+lpCriticalSection], 0
0x18006a806  lea     rdx, [rsi+28h]
0x18006a80a  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x18006a80f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18006a814  nop
0x18006a815  lea     r8, [rsp+0C8h+var_70]
0x18006a81a  lea     rdx, [rsp+0C8h+var_40]
0x18006a822  lea     rcx, [rsp+0C8h+var_60]
0x18006a827  call    ??$make_shared@VConnection@ConnectionPoint@@AEAV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@AEAV?$shared_ptr@VConnectedProcess@@@std@@@std@@YA?AV?$shared_ptr@VConnection@ConnectionPoint@@@0@AEAV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@AEAV?$shared_ptr@VConnectedProcess@@@0@@Z; std::make_shared<ConnectionPoint::Connection,wil::com_ptr_t<IUnknown,wil::err_exception_policy> &,std::shared_ptr<ConnectedProcess> &>(wil::com_ptr_t<IUnknown,wil::err_exception_policy> &,std::shared_ptr<ConnectedProcess> &)
0x18006a82c  nop
0x18006a82d  lea     rbx, [rsi+60h]
0x18006a831  lea     rcx, [rsi+50h]
0x18006a835  mov     r9, rax
0x18006a838  mov     r8, rbx
0x18006a83b  lea     rdx, [rsp+0C8h+var_50]
0x18006a840  call    ??$_Emplace@AEAKV?$shared_ptr@VConnection@ConnectionPoint@@@std@@@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VConnection@ConnectionPoint@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VConnection@ConnectionPoint@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VConnection@ConnectionPoint@@@std@@@std@@PEAX@std@@_N@1@AEAK$$QEAV?$shared_ptr@VConnection@ConnectionPoint@@@1@@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<ConnectionPoint::Connection>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<ConnectionPoint::Connection>>>,0>>::_Emplace<ulong &,std::shared_ptr<ConnectionPoint::Connection>>(ulong &,std::shared_ptr<ConnectionPoint::Connection> &&)
0x18006a845  nop
0x18006a846  mov     rcx, [rsp+0C8h+var_58]; this
0x18006a84b  test    rcx, rcx
0x18006a84e  jz      short loc_18006A855
0x18006a850  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006a855  mov     ecx, [rbx]
0x18006a857  lea     eax, [rcx+1]
0x18006a85a  mov     [rbx], eax
0x18006a85c  mov     [r14], ecx
0x18006a85f  mov     eax, cs:dword_1801BD288
0x18006a865  cmp     eax, 4
0x18006a868  jbe     short loc_18006A8B0
0x18006a86a  mov     [rsp+0C8h+var_60], r15
0x18006a86f  mov     rax, [rsp+0C8h+var_70]
0x18006a874  mov     ecx, [rax+118h]
0x18006a87a  mov     [rsp+0C8h+var_80], ecx
0x18006a87e  mov     eax, [r14]
0x18006a881  mov     [rsp+0C8h+var_84], eax
0x18006a885  lea     rax, [rsp+0C8h+var_60]
0x18006a88a  mov     [rsp+0C8h+var_98], rax
0x18006a88f  lea     rax, [rsp+0C8h+var_80]
0x18006a894  mov     [rsp+0C8h+var_A0], rax
0x18006a899  lea     rax, [rsp+0C8h+var_84]
0x18006a89e  mov     [rsp+0C8h+var_A8], rax
0x18006a8a3  lea     rdx, qword_18019A1E0
0x18006a8aa  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18006a8af  nop
0x18006a8b0  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x18006a8b5  test    rcx, rcx
0x18006a8b8  jz      short loc_18006A8C1
0x18006a8ba  call    cs:__imp_LeaveCriticalSection
0x18006a8c0  nop
0x18006a8c1  mov     rcx, [rsp+0C8h+var_70+8]; this
0x18006a8c6  test    rcx, rcx
0x18006a8c9  jz      short loc_18006A8D1
0x18006a8cb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006a8d0  nop
0x18006a8d1  lea     rcx, [rsp+0C8h+var_38]
0x18006a8d9  call    ??1?$com_ptr_t@VConnectionPointContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>::~com_ptr_t<ConnectionPointContainer,wil::err_exception_policy>(void)
0x18006a8de  nop
0x18006a8df  lea     rcx, [rsp+0C8h+var_40]
0x18006a8e7  call    ??1?$com_ptr_t@UINetworkInterfacePrivate@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>::~com_ptr_t<INetworkInterfacePrivate,wil::err_exception_policy>(void)
0x18006a8ec  nop
0x18006a8ed  call    cs:__imp_CoRevertToSelf
0x18006a8f3  xor     eax, eax
0x18006a8f5  jmp     short loc_18006A8FB
0x18006a8f7  mov     eax, [rsp+0C8h+var_84]
0x18006a8fb  mov     rcx, [rsp+0C8h+var_30]
0x18006a903  xor     rcx, rsp; StackCookie
0x18006a906  call    __security_check_cookie
0x18006a90b  add     rsp, 0A0h
0x18006a912  pop     r15
0x18006a914  pop     r14
0x18006a916  pop     rdi
0x18006a917  pop     rsi
0x18006a918  pop     rbx
0x18006a919  retn
```
