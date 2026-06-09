# Mso::OfficeWebServiceApi::ServiceRequestHelper::ServiceRequestHelper(long,Mso::OfficeWebServiceApi::IUrlBuilder &,Mso::OfficeWebServiceApi::HttpVerb::Enum,uchar const *,uint,Mso::TCntPtr<Mso::OfficeWebServiceApi::ServiceRequestHeaders> const &,Mso::OfficeWebServiceApi::AServiceRequestCallback *,unsigned __int64,Mso::TCntPtr<Mso::OfficeWebServiceApi::ICacheInfo> const &,Mso::Authentication::IOfficeIdentity const *,std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &,std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestAuthentication> const &)

- ea: `0x180029008`
- end: `0x18002931c`
- name: `??0ServiceRequestHelper@OfficeWebServiceApi@Mso@@QEAA@JAEAUIUrlBuilder@12@W4Enum@HttpVerb@12@PEBEIAEBV?$TCntPtr@VServiceRequestHeaders@OfficeWebServiceApi@Mso@@@2@PEAVAServiceRequestCallback@12@_KAEBV?$TCntPtr@UICacheInfo@OfficeWebServiceApi@Mso@@@2@PEBUIOfficeIdentity@Authentication@2@AEBV?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@AEBV?$shared_ptr@UIServiceRequestAuthentication@OfficeWebServiceApi@Mso@@@std@@@Z`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028f18`

## callees

- `0x180003980`
- `0x180009488`
- `0x180009748`
- `0x18000adf0`
- `0x18000c2dc`
- `0x18000f4c0`
- `0x180010a84`
- `0x180012bf8`
- `0x18001cd54`
- `0x180029008`
- `0x18002931c`
- `0x180029f58`
- `0x18003e690`
- `0x180052cd0`
- `0x18007c0ec`
- `0x1800807ec`
- `0x180091198`
- `0x180146090`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x1800291af`
- `KERNEL32!CreateEventExW` at `0x1800291af`
- `KERNEL32!CloseHandle` at `0x1800291c8`
- `KERNEL32!CloseHandle` at `0x1800291c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::OfficeWebServiceApi::ServiceRequestHelper::ServiceRequestHelper(
        __int64 a1,
        int a2,
        void (__fastcall ***a3)(_QWORD),
        int a4,
        __int64 a5,
        int a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  HANDLE Event; // rsi
  void *v17; // rcx
  void *v18; // rax
  unsigned __int64 v19; // r8
  __int64 *ServiceRequestAuthentication; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  std::_Ref_count_base *v23; // rcx
  __int64 v24; // rax
  __int64 v26; // [rsp+28h] [rbp-79h] BYREF
  _BYTE v27[8]; // [rsp+38h] [rbp-69h] BYREF
  __int64 v28; // [rsp+40h] [rbp-61h]
  _BYTE v29[8]; // [rsp+78h] [rbp-29h] BYREF
  std::_Ref_count_base *v30; // [rsp+80h] [rbp-21h]

  v26 = a13;
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &Mso::OfficeWebServiceApi::ServiceRequestHelper::`vftable';
  *(_QWORD *)(a1 + 16) = a3;
  (**a3)(a3);
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = a2;
  *(_DWORD *)(a1 + 44) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 52) = a4;
  *(_QWORD *)(a1 + 56) = *a10;
  Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<Mso::OfficeWebServiceApi::IServiceTicketInfo>(a1 + 56);
  *(_OWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 15;
  *(_BYTE *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 96) = a6;
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 7;
  *(_WORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 136) = a8;
  Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<Mso::OfficeWebServiceApi::IServiceTicketInfo>(a1 + 136);
  *(_QWORD *)(a1 + 144) = *a7;
  Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<Mso::OfficeWebServiceApi::IServiceTicketInfo>(a1 + 144);
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_OWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 7;
  *(_WORD *)(a1 + 176) = 0;
  *(_BYTE *)(a1 + 208) = 0;
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(a1 + 216), 256);
  std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
    a1 + 296,
    a12);
  *(_QWORD *)(a1 + 312) = a9;
  *(_BYTE *)(a1 + 320) = 0;
  *(_DWORD *)(a1 + 44) = 0;
  if ( *(_DWORD *)(a1 + 96) && a5 )
    std::basic_string<char8_t>::assign((void *)(a1 + 64));
  Event = CreateEventExW(0, 0, 3u, 0x1F0003u);
  v17 = *(void **)(a1 + 24);
  if ( v17 )
  {
    *(_QWORD *)(a1 + 24) = 0;
    CloseHandle(v17);
  }
  *(_QWORD *)(a1 + 24) = Event;
  if ( a11 )
  {
    v18 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a11 + 32LL))(a11);
    std::wstring::assign((void *)(a1 + 104), v18);
  }
  v19 = (unsigned __int64)*(unsigned int *)(a1 + 312) >> 13;
  LOBYTE(v19) = (*(_DWORD *)(a1 + 312) & 0x2000LL) != 0;
  ServiceRequestAuthentication = (__int64 *)Mso::OfficeWebServiceApi::GetServiceRequestAuthentication(
                                              v29,
                                              v26,
                                              v19,
                                              a1 + 104);
  v21 = *ServiceRequestAuthentication;
  v22 = ServiceRequestAuthentication[1];
  *ServiceRequestAuthentication = 0;
  ServiceRequestAuthentication[1] = 0;
  *(_QWORD *)(a1 + 160) = v21;
  v23 = *(std::_Ref_count_base **)(a1 + 168);
  *(_QWORD *)(a1 + 168) = v22;
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  if ( !*(_QWORD *)(a1 + 160) )
    CrashWithRecovery(0x1E407446u, 0);
  if ( (*(_DWORD *)(a1 + 312) & 0x40000) != 0 )
  {
    std::wstring::assign((void *)(a1 + 176), (void *)&LocaleName);
    if ( *(_QWORD *)(a1 + 144) )
    {
      v24 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(a1 + 144);
      std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(v27, v24 + 16);
      std::wstring::wstring(v29, L"X-CorrelationId");
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
        v27,
        &v26,
        v29);
      std::wstring::~wstring(v29);
      if ( v26 != v28 )
      {
        std::wstring::operator=(a1 + 176, v26 + 48);
        *(_BYTE *)(a1 + 208) = 1;
      }
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v27);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180029008  mov     rax, rsp
0x18002900b  mov     [rax+10h], rbx
0x18002900f  mov     [rax+18h], rsi
0x180029013  mov     [rax+20h], rdi
0x180029017  push    rbp
0x180029018  push    r12
0x18002901a  push    r13
0x18002901c  push    r14
0x18002901e  push    r15
0x180029020  lea     rbp, [rax-2Fh]
0x180029024  sub     rsp, 0A0h
0x18002902b  mov     rax, cs:__security_cookie
0x180029032  xor     rax, rsp
0x180029035  mov     [rbp+27h+var_30], rax
0x180029039  mov     edi, r9d
0x18002903c  mov     ebx, edx
0x18002903e  mov     r14, rcx
0x180029041  mov     r12, [rbp+27h+arg_20]
0x180029045  mov     r15, [rbp+27h+arg_50]
0x18002904c  mov     rsi, [rbp+27h+arg_58]
0x180029053  mov     rax, [rbp+27h+arg_60]
0x18002905a  mov     [rbp+27h+var_A0], rax
0x18002905e  mov     dword ptr [rcx+8], 1
0x180029065  lea     rax, ??_7ServiceRequestHelper@OfficeWebServiceApi@Mso@@6B@; const Mso::OfficeWebServiceApi::ServiceRequestHelper::`vftable'
0x18002906c  mov     [rcx], rax
0x18002906f  mov     [rcx+10h], r8
0x180029073  mov     rax, [r8]
0x180029076  mov     rcx, r8
0x180029079  mov     rax, [rax]
0x18002907c  call    cs:__guard_dispatch_icall_fptr
0x180029082  xor     r13d, r13d
0x180029085  mov     [r14+18h], r13
0x180029089  mov     [r14+20h], r13
0x18002908d  mov     [r14+28h], ebx
0x180029091  mov     [r14+2Ch], r13d
0x180029095  mov     [r14+30h], r13d
0x180029099  mov     [r14+34h], edi
0x18002909d  mov     rax, [rbp+27h+arg_48]
0x1800290a1  mov     rcx, [rax]
0x1800290a4  mov     [r14+38h], rcx
0x1800290a8  lea     rcx, [r14+38h]
0x1800290ac  call    ??$CheckedAddRefOnNewlyAssignedPtr@UIServiceTicketInfo@OfficeWebServiceApi@Mso@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAUIServiceTicketInfo@OfficeWebServiceApi@2@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<Mso::OfficeWebServiceApi::IServiceTicketInfo>(Mso::OfficeWebServiceApi::IServiceTicketInfo * *)
0x1800290b1  xorps   xmm0, xmm0
0x1800290b4  movups  xmmword ptr [r14+40h], xmm0
0x1800290b9  mov     [r14+50h], r13
0x1800290bd  mov     qword ptr [r14+58h], 0Fh
0x1800290c5  mov     [r14+40h], r13b
0x1800290c9  mov     eax, [rbp+27h+arg_28]
0x1800290cc  mov     [r14+60h], eax
0x1800290d0  lea     rdi, [r14+68h]
0x1800290d4  movups  xmmword ptr [rdi], xmm0
0x1800290d7  mov     [rdi+10h], r13
0x1800290db  mov     qword ptr [rdi+18h], 7
0x1800290e3  mov     [rdi], r13w
0x1800290e7  lea     rcx, [r14+88h]
0x1800290ee  mov     rax, [rbp+27h+arg_38]
0x1800290f2  mov     [rcx], rax
0x1800290f5  call    ??$CheckedAddRefOnNewlyAssignedPtr@UIServiceTicketInfo@OfficeWebServiceApi@Mso@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAUIServiceTicketInfo@OfficeWebServiceApi@2@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<Mso::OfficeWebServiceApi::IServiceTicketInfo>(Mso::OfficeWebServiceApi::IServiceTicketInfo * *)
0x1800290fa  lea     r13, [r14+90h]
0x180029101  mov     rax, [rbp+27h+arg_30]
0x180029105  mov     rcx, [rax]
0x180029108  mov     [r13+0], rcx
0x18002910c  mov     rcx, r13
0x18002910f  call    ??$CheckedAddRefOnNewlyAssignedPtr@UIServiceTicketInfo@OfficeWebServiceApi@Mso@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAUIServiceTicketInfo@OfficeWebServiceApi@2@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<Mso::OfficeWebServiceApi::IServiceTicketInfo>(Mso::OfficeWebServiceApi::IServiceTicketInfo * *)
0x180029114  xor     eax, eax
0x180029116  mov     [r14+98h], rax
0x18002911d  mov     [r14+0A0h], rax
0x180029124  mov     [r14+0A8h], rax
0x18002912b  lea     rbx, [r14+0B0h]
0x180029132  xorps   xmm0, xmm0
0x180029135  movups  xmmword ptr [rbx], xmm0
0x180029138  mov     [rbx+10h], rax
0x18002913c  mov     qword ptr [rbx+18h], 7
0x180029144  mov     [rbx], ax
0x180029147  mov     [r14+0D0h], al
0x18002914e  lea     rcx, [r14+0D8h]; this
0x180029155  mov     edx, 100h; int
0x18002915a  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x18002915f  lea     rcx, [r14+128h]
0x180029166  mov     rdx, rsi
0x180029169  call    ??0?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &)
0x18002916e  mov     rax, [rbp+27h+arg_40]
0x180029172  mov     [r14+138h], rax
0x180029179  xor     eax, eax
0x18002917b  mov     [r14+140h], al
0x180029182  mov     [r14+2Ch], eax
0x180029186  cmp     [r14+60h], eax
0x18002918a  jbe     short loc_1800291A1
0x18002918c  test    r12, r12
0x18002918f  jz      short loc_1800291A1
0x180029191  mov     r8d, [rbp+27h+arg_28]
0x180029195  mov     rdx, r12
0x180029198  lea     rcx, [r14+40h]; void *
0x18002919c  call    ?assign@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEAAAEAV12@QEB_Q_K@Z; std::basic_string<char8_t>::assign(char8_t const * const,unsigned __int64)
0x1800291a1  xor     edx, edx; lpName
0x1800291a3  xor     ecx, ecx; lpEventAttributes
0x1800291a5  mov     r9d, 1F0003h; dwDesiredAccess
0x1800291ab  lea     r8d, [rdx+3]; dwFlags
0x1800291af  call    cs:__imp_CreateEventExW
0x1800291b5  mov     rsi, rax
0x1800291b8  mov     rcx, [r14+18h]; hObject
0x1800291bc  xor     r12d, r12d
0x1800291bf  test    rcx, rcx
0x1800291c2  jz      short loc_1800291CF
0x1800291c4  mov     [r14+18h], r12
0x1800291c8  call    cs:__imp_CloseHandle
0x1800291ce  nop
0x1800291cf  mov     [r14+18h], rsi
0x1800291d3  test    r15, r15
0x1800291d6  jz      short loc_1800291F3
0x1800291d8  mov     rax, [r15]
0x1800291db  mov     rcx, r15
0x1800291de  mov     rax, [rax+20h]
0x1800291e2  call    cs:__guard_dispatch_icall_fptr
0x1800291e8  mov     rdx, rax; Src
0x1800291eb  mov     rcx, rdi; void *
0x1800291ee  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800291f3  mov     r8d, [r14+138h]
0x1800291fa  shr     r8, 0Dh
0x1800291fe  and     r8b, 1
0x180029202  mov     r9, rdi
0x180029205  mov     rdx, [rbp+27h+var_A0]
0x180029209  lea     rcx, [rbp+27h+var_50]
0x18002920d  call    ?GetServiceRequestAuthentication@OfficeWebServiceApi@Mso@@YA?AV?$shared_ptr@UIServiceRequestAuthentication@OfficeWebServiceApi@Mso@@@std@@AEBV34@_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Mso::OfficeWebServiceApi::GetServiceRequestAuthentication(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestAuthentication> const &,bool,std::wstring &)
0x180029212  mov     rcx, [rax]
0x180029215  mov     rdx, [rax+8]
0x180029219  mov     [rax], r12
0x18002921c  mov     [rax+8], r12
0x180029220  mov     [r14+0A0h], rcx
0x180029227  mov     rcx, [r14+0A8h]; this
0x18002922e  mov     [r14+0A8h], rdx
0x180029235  test    rcx, rcx
0x180029238  jz      short loc_18002923F
0x18002923a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002923f  mov     rcx, [rbp+27h+var_48]; this
0x180029243  test    rcx, rcx
0x180029246  jz      short loc_18002924D
0x180029248  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002924d  cmp     [r14+0A0h], r12
0x180029254  jnz     short loc_180029263
0x180029256  xor     edx, edx; struct CrashContext *
0x180029258  mov     ecx, 1E407446h; unsigned int
0x18002925d  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180029263  mov     eax, [r14+138h]
0x18002926a  bt      rax, 12h
0x18002926f  jnb     short loc_1800292EC
0x180029271  lea     rdx, LocaleName; Src
0x180029278  mov     rcx, rbx; void *
0x18002927b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180029280  cmp     [r13+0], r12
0x180029284  jz      short loc_1800292EC
0x180029286  mov     rcx, r13
0x180029289  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x18002928e  lea     rdx, [rax+10h]
0x180029292  lea     rcx, [rbp+27h+var_90]
0x180029296  call    ??0?$unordered_map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@AEBV01@@Z; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(std::unordered_map<std::wstring,std::wstring> const &)
0x18002929b  lea     rdx, aXCorrelationid; "X-CorrelationId"
0x1800292a2  lea     rcx, [rbp+27h+var_50]
0x1800292a6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800292ab  lea     r8, [rbp+27h+var_50]
0x1800292af  lea     rdx, [rbp+27h+var_A0]
0x1800292b3  lea     rcx, [rbp+27h+var_90]
0x1800292b7  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800292bc  lea     rcx, [rbp+27h+var_50]; void *
0x1800292c0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800292c5  mov     rdx, [rbp+27h+var_A0]
0x1800292c9  cmp     rdx, [rbp+27h+var_88]
0x1800292cd  jz      short loc_1800292E3
0x1800292cf  add     rdx, 30h ; '0'
0x1800292d3  mov     rcx, rbx
0x1800292d6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800292db  mov     byte ptr [r14+0D0h], 1
0x1800292e3  lea     rcx, [rbp+27h+var_90]
0x1800292e7  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800292ec  mov     rax, r14
0x1800292ef  mov     rcx, [rbp+27h+var_30]
0x1800292f3  xor     rcx, rsp; StackCookie
0x1800292f6  call    __security_check_cookie
0x1800292fb  lea     r11, [rsp+0C0h+var_20]
0x180029303  mov     rbx, [r11+38h]
0x180029307  mov     rsi, [r11+40h]
0x18002930b  mov     rdi, [r11+48h]
0x18002930f  mov     rsp, r11
0x180029312  pop     r15
0x180029314  pop     r14
0x180029316  pop     r13
0x180029318  pop     r12
0x18002931a  pop     rbp
0x18002931b  retn
```
