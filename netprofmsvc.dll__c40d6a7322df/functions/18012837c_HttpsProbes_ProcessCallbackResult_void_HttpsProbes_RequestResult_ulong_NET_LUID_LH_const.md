# HttpsProbes::ProcessCallbackResult(void *,HttpsProbes::RequestResult,ulong,_NET_LUID_LH const &)

- ea: `0x18012837c`
- end: `0x180128a52`
- name: `?ProcessCallbackResult@HttpsProbes@@AEAAXPEAXW4RequestResult@1@KAEBT_NET_LUID_LH@@@Z`
- size: `1750`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180128040`

## callees

- `0x1800054f4`
- `0x1800058a8`
- `0x1800059dc`
- `0x180009990`
- `0x180015608`
- `0x180018968`
- `0x18001c994`
- `0x18002bd40`
- `0x180039f88`
- `0x18003d290`
- `0x180048608`
- `0x1800801ac`
- `0x18008f1e4`
- `0x180097df4`
- `0x1800a88a0`
- `0x1801270fc`
- `0x180127228`
- `0x18012837c`
- `0x180128ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012857c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012858d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801285f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180128608`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012876f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180128780`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801288eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801288fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801289cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801289dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012857c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012858d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801285f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180128608`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012876f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180128780`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801288eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801288fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801289cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801289dd`
- `DNSAPI!DnsFlushResolverCache` at `0x180128984`
- `DNSAPI!DnsFlushResolverCache` at `0x180128984`

## string_xrefs

- `0x180128a27`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`
- `0x180128a3f`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\httpsprobes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall HttpsProbes::ProcessCallbackResult(__int64 a1, __int64 a2, int a3, int a4, _QWORD *a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  _QWORD *v13; // rdi
  __int64 v14; // r11
  __int64 v15; // r11
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const wchar_t *v20; // rax
  const wchar_t *v21; // rax
  const char *v22; // r9
  _QWORD *v23; // rcx
  bool v24; // al
  const wchar_t *v25; // rax
  const wchar_t *v26; // rax
  const wchar_t *v27; // rax
  const wchar_t *v28; // rax
  int v29; // eax
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // r9
  unsigned int v33; // eax
  int *v34; // [rsp+20h] [rbp-128h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-E8h] BYREF
  unsigned __int64 v36; // [rsp+68h] [rbp-E0h] BYREF
  int v37; // [rsp+70h] [rbp-D8h]
  LPCRITICAL_SECTION v38; // [rsp+78h] [rbp-D0h] BYREF
  const wchar_t *v39; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+88h] [rbp-C0h]
  const wchar_t *v41; // [rsp+90h] [rbp-B8h]
  const wchar_t *v42; // [rsp+98h] [rbp-B0h]
  int v43[2]; // [rsp+A0h] [rbp-A8h] BYREF
  _QWORD v44[5]; // [rsp+A8h] [rbp-A0h] BYREF
  _BYTE v45[24]; // [rsp+D0h] [rbp-78h] BYREF
  _QWORD v46[3]; // [rsp+E8h] [rbp-60h] BYREF
  unsigned __int64 v47; // [rsp+100h] [rbp-48h]
  unsigned __int64 v48; // [rsp+108h] [rbp-40h]
  int v49; // [rsp+110h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v38 = 0;
  wil::EnterCriticalSection(&v38, a1);
  v13 = (_QWORD *)(a1 + 40);
  v14 = *(_QWORD *)(a1 + 40);
  try
  {
    while ( 1 )
    {
      if ( v14 == *(_QWORD *)(a1 + 48) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11, v12);
        v33 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1FC,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
          (const char *)v33,
          (int)v34);
      }
      if ( *(_QWORD *)(v14 + 16) == a2 )
        break;
      v14 += 72;
    }
    v44[1] = 1;
    v44[0] = a1;
    HttpsProbes::HttpsRequest::HttpsRequest(v45, v14);
    std::vector<HttpsProbes::HttpsRequest>::erase(a1 + 40, &v36, v15);
    if ( v48 >= *(_QWORD *)(a1 + 112) )
    {
      if ( *(_BYTE *)(a1 + 124) )
      {
        if ( (unsigned int)dword_1801BD288 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v17,
            &dword_180199134);
        HttpsProbes::HttpsRequest::~HttpsRequest((HttpsProbes::HttpsRequest *)v45);
        lpCriticalSection = 0;
        wil::EnterCriticalSection(&lpCriticalSection, a1);
        if ( *(_QWORD *)(a1 + 48) == *v13 )
          _SetEvent___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(a1 + 88);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        if ( v38 )
          LeaveCriticalSection(v38);
      }
      else
      {
        v23 = a5;
        v24 = v49 == 1 && *a5 == *(_QWORD *)(a1 + 96);
        if ( a3 == 2 && (v49 == 2 || v24) )
        {
          *(_BYTE *)(a1 + 124) = 1;
          if ( (unsigned int)dword_1801BD288 > 4 )
          {
            v36 = v48;
            v25 = L"Global";
            if ( v49 != 1 )
              v25 = L"PerInterface";
            v39 = v25;
            v26 = (const wchar_t *)v46;
            if ( v47 > 7 )
              v26 = (const wchar_t *)v46[0];
            v42 = v26;
            v41 = (const wchar_t *)*(unsigned int *)(a1 + 104);
            v40 = *(_QWORD *)(a1 + 96);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(
              L"PerInterface",
              byte_180198F15);
          }
          Authentication::InterfaceInfo::OnHttpsProbeCompletedEvent(*(_QWORD *)(a1 + 136), 2, v46);
          HttpsProbes::HttpsRequest::~HttpsRequest((HttpsProbes::HttpsRequest *)v45);
          lpCriticalSection = 0;
          wil::EnterCriticalSection(&lpCriticalSection, a1);
          if ( *(_QWORD *)(a1 + 48) == *v13 )
            _SetEvent___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(a1 + 88);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          if ( v38 )
            LeaveCriticalSection(v38);
        }
        else
        {
          if ( (unsigned int)dword_1801BD288 > 5 )
          {
            v37 = *(_DWORD *)(a1 + 120);
            v36 = v48;
            v39 = (const wchar_t *)*a5;
            v27 = L"Global";
            if ( v49 != 1 )
              v27 = L"PerInterface";
            v42 = v27;
            v28 = (const wchar_t *)v46;
            if ( v47 > 7 )
              v28 = (const wchar_t *)v46[0];
            v41 = v28;
            LODWORD(lpCriticalSection) = a4;
            v40 = *(unsigned int *)(a1 + 104);
            *(_QWORD *)v43 = *(_QWORD *)(a1 + 96);
            v34 = v43;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              L"PerInterface",
              &dword_180198E2C);
          }
          if ( !*(_DWORD *)(a1 + 120) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v23, v16, v18, v19);
          v29 = *(_DWORD *)(a1 + 120);
          if ( !v29 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x245,
              (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
              (const char *)0x8000FFFFLL,
              (int)v34);
          v30 = v29 - 1;
          *(_DWORD *)(a1 + 120) = v30;
          if ( v30 )
          {
            HttpsProbes::HttpsRequest::~HttpsRequest((HttpsProbes::HttpsRequest *)v45);
            lpCriticalSection = 0;
            wil::EnterCriticalSection(&lpCriticalSection, a1);
            if ( *(_QWORD *)(a1 + 48) == *(_QWORD *)(a1 + 40) )
              _SetEvent___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(a1 + 88);
            if ( lpCriticalSection )
              LeaveCriticalSection(lpCriticalSection);
            if ( v38 )
              LeaveCriticalSection(v38);
          }
          else
          {
            if ( (unsigned int)dword_1801BD288 > 4 )
            {
              v36 = *(unsigned int *)(a1 + 104);
              v39 = *(const wchar_t **)(a1 + 96);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                (_DWORD)retaddr,
                (unsigned int)&unk_180198DC8,
                v18,
                v19,
                (__int64)&v39,
                (__int64)&v36);
            }
            v31 = std::wstring::wstring(v44);
            Authentication::InterfaceInfo::OnHttpsProbeCompletedEvent(v32, 1, v31);
            std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(v44);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
              &v38,
              0);
            DnsFlushResolverCache();
            HttpsProbes::HttpsRequest::~HttpsRequest((HttpsProbes::HttpsRequest *)v45);
            lpCriticalSection = 0;
            wil::EnterCriticalSection(&lpCriticalSection, a1);
            if ( *(_QWORD *)(a1 + 48) == *(_QWORD *)(a1 + 40) )
              _SetEvent___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(a1 + 88);
            if ( lpCriticalSection )
              LeaveCriticalSection(lpCriticalSection);
            if ( v38 )
              LeaveCriticalSection(v38);
          }
        }
      }
    }
    else
    {
      if ( (unsigned int)dword_1801BD288 > 5 )
      {
        lpCriticalSection = *(LPCRITICAL_SECTION *)(a1 + 112);
        *(_QWORD *)v43 = v48;
        v40 = *a5;
        v20 = L"Global";
        if ( v49 != 1 )
          v20 = L"PerInterface";
        v41 = v20;
        v37 = a4;
        v21 = (const wchar_t *)v46;
        if ( v47 > 7 )
          v21 = (const wchar_t *)v46[0];
        v42 = v21;
        v39 = (const wchar_t *)*(unsigned int *)(a1 + 104);
        v36 = *(_QWORD *)(a1 + 96);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          L"PerInterface",
          byte_180199189);
      }
      HttpsProbes::HttpsRequest::~HttpsRequest((HttpsProbes::HttpsRequest *)v45);
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, a1);
      if ( *(_QWORD *)(a1 + 48) == *v13 )
        _SetEvent___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(a1 + 88);
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      if ( v38 )
        LeaveCriticalSection(v38);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x25B,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\httpsprobes.cpp",
      v22);
  }
}

```

## disassembly

```asm
0x18012837c  mov     [rsp+arg_8], rbx
0x180128381  mov     [rsp+arg_10], rsi
0x180128386  push    rdi
0x180128387  push    r14
0x180128389  push    r15
0x18012838b  sub     rsp, 130h
0x180128392  mov     rax, cs:__security_cookie
0x180128399  xor     rax, rsp
0x18012839c  mov     [rsp+148h+var_28], rax
0x1801283a4  mov     r15d, r9d
0x1801283a7  mov     r14d, r8d
0x1801283aa  mov     rsi, rdx
0x1801283ad  mov     rbx, rcx
0x1801283b0  mov     [rsp+148h+var_D0], 0
0x1801283b9  mov     rdx, rcx
0x1801283bc  lea     rcx, [rsp+148h+var_D0]
0x1801283c1  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1801283c6  nop
0x1801283c7  lea     rdi, [rbx+28h]
0x1801283cb  mov     r11, [rdi]
0x1801283ce  jmp     short loc_1801283DA
0x1801283d0  cmp     [r11+10h], rsi
0x1801283d4  jz      short loc_1801283E6
0x1801283d6  add     r11, 48h ; 'H'
0x1801283da  cmp     r11, [rdi+8]
0x1801283de  jz      loc_180128A0D
0x1801283e4  jmp     short loc_1801283D0
0x1801283e6  xorps   xmm0, xmm0
0x1801283e9  movups  xmmword ptr [rsp+148h+var_A0], xmm0
0x1801283f1  mov     [rsp+148h+var_A0], rbx
0x1801283f9  mov     esi, 1
0x1801283fe  mov     byte ptr [rsp+148h+var_A0+8], sil
0x180128406  mov     rdx, r11
0x180128409  lea     rcx, [rsp+148h+var_78]
0x180128411  call    ??0HttpsRequest@HttpsProbes@@QEAA@$$QEAU01@@Z; HttpsProbes::HttpsRequest::HttpsRequest(HttpsProbes::HttpsRequest &&)
0x180128416  nop
0x180128417  mov     r8, r11
0x18012841a  lea     rdx, [rsp+148h+var_E0]
0x18012841f  mov     rcx, rdi
0x180128422  call    ?erase@?$vector@UHttpsRequest@HttpsProbes@@V?$allocator@UHttpsRequest@HttpsProbes@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UHttpsRequest@HttpsProbes@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UHttpsRequest@HttpsProbes@@@std@@@std@@@2@@Z; std::vector<HttpsProbes::HttpsRequest>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<HttpsProbes::HttpsRequest>>>)
0x180128427  mov     rax, [rbx+70h]
0x18012842b  cmp     [rsp+148h+var_40], rax
0x180128433  jnb     loc_180128599
0x180128439  mov     eax, cs:dword_1801BD288
0x18012843f  cmp     eax, 5
0x180128442  jbe     loc_18012853C
0x180128448  mov     rax, [rbx+70h]
0x18012844c  mov     [rsp+148h+lpCriticalSection], rax
0x180128451  mov     rax, [rsp+148h+var_40]
0x180128459  mov     qword ptr [rsp+148h+var_A8], rax
0x180128461  mov     rax, [rsp+148h+arg_20]
0x180128469  mov     rcx, [rax]
0x18012846c  mov     [rsp+148h+var_C0], rcx
0x180128474  lea     rax, aGlobal; "Global"
0x18012847b  lea     rcx, aPerinterface; "PerInterface"
0x180128482  cmp     [rsp+148h+var_38], esi
0x180128489  cmovnz  rax, rcx
0x18012848d  mov     [rsp+148h+var_B8], rax
0x180128495  mov     [rsp+148h+var_D8], r15d
0x18012849a  lea     rax, [rsp+148h+var_60]
0x1801284a2  cmp     [rsp+148h+var_48], 7
0x1801284ab  cmova   rax, [rsp+148h+var_60]
0x1801284b4  mov     [rsp+148h+var_B0], rax
0x1801284bc  mov     eax, [rbx+68h]
0x1801284bf  mov     [rsp+148h+var_C8], rax
0x1801284c7  mov     rax, [rbx+60h]
0x1801284cb  mov     [rsp+148h+var_E0], rax
0x1801284d0  lea     rax, [rsp+148h+lpCriticalSection]
0x1801284d5  mov     [rsp+148h+var_F0], rax
0x1801284da  lea     rax, [rsp+148h+var_A8]
0x1801284e2  mov     [rsp+148h+var_F8], rax
0x1801284e7  lea     rax, [rsp+148h+var_C0]
0x1801284ef  mov     [rsp+148h+var_100], rax
0x1801284f4  lea     rax, [rsp+148h+var_B8]
0x1801284fc  mov     [rsp+148h+var_108], rax
0x180128501  lea     rax, [rsp+148h+var_D8]
0x180128506  mov     [rsp+148h+var_110], rax
0x18012850b  lea     rax, [rsp+148h+var_B0]
0x180128513  mov     [rsp+148h+var_118], rax
0x180128518  lea     rax, [rsp+148h+var_C8]
0x180128520  mov     [rsp+148h+var_120], rax
0x180128525  lea     rax, [rsp+148h+var_E0]
0x18012852a  mov     qword ptr [rsp+148h+var_128], rax
0x18012852f  lea     rdx, byte_180199189
0x180128536  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U2@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@4333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18012853b  nop
0x18012853c  lea     rcx, [rsp+148h+var_78]; this
0x180128544  call    ??1HttpsRequest@HttpsProbes@@QEAA@XZ; HttpsProbes::HttpsRequest::~HttpsRequest(void)
0x180128549  nop
0x18012854a  mov     [rsp+148h+lpCriticalSection], 0
0x180128553  mov     rdx, rbx
0x180128556  lea     rcx, [rsp+148h+lpCriticalSection]
0x18012855b  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180128560  mov     rax, [rdi+8]
0x180128564  cmp     rax, [rdi]
0x180128567  jnz     short loc_180128572
0x180128569  lea     rcx, [rbx+58h]
0x18012856d  call    ?SetEvent@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x180128572  mov     rcx, [rsp+148h+lpCriticalSection]; lpCriticalSection
0x180128577  test    rcx, rcx
0x18012857a  jz      short loc_180128583
0x18012857c  call    cs:__imp_LeaveCriticalSection
0x180128582  nop
0x180128583  mov     rcx, [rsp+148h+var_D0]; lpCriticalSection
0x180128588  test    rcx, rcx
0x18012858b  jz      short loc_180128594
0x18012858d  call    cs:__imp_LeaveCriticalSection
0x180128593  nop
0x180128594  jmp     loc_1801289E4
0x180128599  cmp     byte ptr [rbx+7Ch], 0
0x18012859d  jz      short loc_180128614
0x18012859f  mov     eax, cs:dword_1801BD288
0x1801285a5  cmp     eax, 5
0x1801285a8  jbe     short loc_1801285B7
0x1801285aa  lea     rdx, dword_180199134
0x1801285b1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801285b6  nop
0x1801285b7  lea     rcx, [rsp+148h+var_78]; this
0x1801285bf  call    ??1HttpsRequest@HttpsProbes@@QEAA@XZ; HttpsProbes::HttpsRequest::~HttpsRequest(void)
0x1801285c4  nop
0x1801285c5  mov     [rsp+148h+lpCriticalSection], 0
0x1801285ce  mov     rdx, rbx
0x1801285d1  lea     rcx, [rsp+148h+lpCriticalSection]
0x1801285d6  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1801285db  mov     rax, [rdi+8]
0x1801285df  cmp     rax, [rdi]
0x1801285e2  jnz     short loc_1801285ED
0x1801285e4  lea     rcx, [rbx+58h]
0x1801285e8  call    ?SetEvent@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x1801285ed  mov     rcx, [rsp+148h+lpCriticalSection]; lpCriticalSection
0x1801285f2  test    rcx, rcx
0x1801285f5  jz      short loc_1801285FE
0x1801285f7  call    cs:__imp_LeaveCriticalSection
0x1801285fd  nop
0x1801285fe  mov     rcx, [rsp+148h+var_D0]; lpCriticalSection
0x180128603  test    rcx, rcx
0x180128606  jz      short loc_18012860F
0x180128608  call    cs:__imp_LeaveCriticalSection
0x18012860e  nop
0x18012860f  jmp     loc_1801289E4
0x180128614  mov     rcx, [rsp+148h+arg_20]
0x18012861c  cmp     [rsp+148h+var_38], esi
0x180128623  jnz     short loc_180128633
0x180128625  mov     rax, [rbx+60h]
0x180128629  cmp     [rcx], rax
0x18012862c  jnz     short loc_180128633
0x18012862e  mov     al, sil
0x180128631  jmp     short loc_180128635
0x180128633  xor     al, al
0x180128635  cmp     r14d, 2
0x180128639  jnz     loc_18012878C
0x18012863f  cmp     [rsp+148h+var_38], r14d
0x180128647  jz      short loc_180128651
0x180128649  test    al, al
0x18012864b  jz      loc_18012878C
0x180128651  mov     [rbx+7Ch], sil
0x180128655  mov     eax, cs:dword_1801BD288
0x18012865b  cmp     eax, 4
0x18012865e  jbe     loc_180128715
0x180128664  mov     rax, [rsp+148h+var_40]
0x18012866c  mov     [rsp+148h+var_E0], rax
0x180128671  lea     rax, aGlobal; "Global"
0x180128678  lea     rcx, aPerinterface; "PerInterface"
0x18012867f  cmp     [rsp+148h+var_38], esi
0x180128686  cmovnz  rax, rcx
0x18012868a  mov     [rsp+148h+var_C8], rax
0x180128692  lea     rax, [rsp+148h+var_60]
0x18012869a  cmp     [rsp+148h+var_48], 7
0x1801286a3  cmova   rax, [rsp+148h+var_60]
0x1801286ac  mov     [rsp+148h+var_B0], rax
0x1801286b4  mov     eax, [rbx+68h]
0x1801286b7  mov     [rsp+148h+var_B8], rax
0x1801286bf  mov     rax, [rbx+60h]
0x1801286c3  mov     [rsp+148h+var_C0], rax
0x1801286cb  lea     rax, [rsp+148h+var_E0]
0x1801286d0  mov     [rsp+148h+var_108], rax
0x1801286d5  lea     rax, [rsp+148h+var_C8]
0x1801286dd  mov     [rsp+148h+var_110], rax
0x1801286e2  lea     rax, [rsp+148h+var_B0]
0x1801286ea  mov     [rsp+148h+var_118], rax
0x1801286ef  lea     rax, [rsp+148h+var_B8]
0x1801286f7  mov     [rsp+148h+var_120], rax
0x1801286fc  lea     rax, [rsp+148h+var_C0]
0x180128704  mov     qword ptr [rsp+148h+var_128], rax
0x180128709  lea     rdx, byte_180198F15
0x180128710  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@_W@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@_W@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &)
0x180128715  lea     r8, [rsp+148h+var_60]
0x18012871d  mov     edx, 2
0x180128722  mov     rcx, [rbx+88h]
0x180128729  call    ?OnHttpsProbeCompletedEvent@InterfaceInfo@Authentication@@AEAAXW4RequestResult@HttpsProbes@@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Authentication::InterfaceInfo::OnHttpsProbeCompletedEvent(HttpsProbes::RequestResult,std::wstring &&)
0x18012872e  nop
0x18012872f  lea     rcx, [rsp+148h+var_78]; this
0x180128737  call    ??1HttpsRequest@HttpsProbes@@QEAA@XZ; HttpsProbes::HttpsRequest::~HttpsRequest(void)
0x18012873c  nop
0x18012873d  mov     [rsp+148h+lpCriticalSection], 0
0x180128746  mov     rdx, rbx
0x180128749  lea     rcx, [rsp+148h+lpCriticalSection]
0x18012874e  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180128753  mov     rax, [rdi+8]
0x180128757  cmp     rax, [rdi]
0x18012875a  jnz     short loc_180128765
0x18012875c  lea     rcx, [rbx+58h]
0x180128760  call    ?SetEvent@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x180128765  mov     rcx, [rsp+148h+lpCriticalSection]; lpCriticalSection
0x18012876a  test    rcx, rcx
0x18012876d  jz      short loc_180128776
0x18012876f  call    cs:__imp_LeaveCriticalSection
0x180128775  nop
0x180128776  mov     rcx, [rsp+148h+var_D0]; lpCriticalSection
0x18012877b  test    rcx, rcx
0x18012877e  jz      short loc_180128787
0x180128780  call    cs:__imp_LeaveCriticalSection
0x180128786  nop
0x180128787  jmp     loc_1801289E4
0x18012878c  mov     eax, cs:dword_1801BD288
0x180128792  cmp     eax, 5
0x180128795  jbe     loc_180128884
0x18012879b  mov     eax, [rbx+78h]
0x18012879e  mov     [rsp+148h+var_D8], eax
0x1801287a2  mov     rax, [rsp+148h+var_40]
0x1801287aa  mov     [rsp+148h+var_E0], rax
0x1801287af  mov     rax, [rcx]
0x1801287b2  mov     [rsp+148h+var_C8], rax
0x1801287ba  lea     rax, aGlobal; "Global"
0x1801287c1  lea     rcx, aPerinterface; "PerInterface"
0x1801287c8  cmp     [rsp+148h+var_38], esi
0x1801287cf  cmovnz  rax, rcx
0x1801287d3  mov     [rsp+148h+var_B0], rax
0x1801287db  lea     rax, [rsp+148h+var_60]
0x1801287e3  cmp     [rsp+148h+var_48], 7
0x1801287ec  cmova   rax, [rsp+148h+var_60]
0x1801287f5  mov     [rsp+148h+var_B8], rax
0x1801287fd  mov     dword ptr [rsp+148h+lpCriticalSection], r15d
0x180128802  mov     eax, [rbx+68h]
0x180128805  mov     [rsp+148h+var_C0], rax
0x18012880d  mov     rax, [rbx+60h]
0x180128811  mov     qword ptr [rsp+148h+var_A8], rax
0x180128819  lea     rax, [rsp+148h+var_D8]
0x18012881e  mov     [rsp+148h+var_F0], rax
0x180128823  lea     rax, [rsp+148h+var_E0]
0x180128828  mov     [rsp+148h+var_F8], rax
0x18012882d  lea     rax, [rsp+148h+var_C8]
0x180128835  mov     [rsp+148h+var_100], rax
0x18012883a  lea     rax, [rsp+148h+var_B0]
0x180128842  mov     [rsp+148h+var_108], rax
0x180128847  lea     rax, [rsp+148h+var_B8]
0x18012884f  mov     [rsp+148h+var_110], rax
0x180128854  lea     rax, [rsp+148h+lpCriticalSection]
0x180128859  mov     [rsp+148h+var_118], rax
0x18012885e  lea     rax, [rsp+148h+var_C0]
0x180128866  mov     [rsp+148h+var_120], rax
0x18012886b  lea     rax, [rsp+148h+var_A8]
0x180128873  mov     qword ptr [rsp+148h+var_128], rax; int
0x180128878  lea     rdx, dword_180198E2C
0x18012887f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@5334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180128884  cmp     dword ptr [rbx+78h], 0
0x180128888  ja      short loc_18012888F
0x18012888a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18012888f  mov     eax, [rbx+78h]
0x180128892  mov     rcx, [rsp+148h]; this
0x18012889a  test    eax, eax
0x18012889c  jz      loc_180128A39
0x1801288a2  sub     eax, 1
0x1801288a5  mov     [rbx+78h], eax
0x1801288a8  jz      short loc_180128908
0x1801288aa  lea     rcx, [rsp+148h+var_78]; this
0x1801288b2  call    ??1HttpsRequest@HttpsProbes@@QEAA@XZ; HttpsProbes::HttpsRequest::~HttpsRequest(void)
0x1801288b7  nop
0x1801288b8  mov     [rsp+148h+lpCriticalSection], 0
0x1801288c1  mov     rdx, rbx
0x1801288c4  lea     rcx, [rsp+148h+lpCriticalSection]
0x1801288c9  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1801288ce  mov     rax, [rbx+30h]
0x1801288d2  cmp     rax, [rbx+28h]
0x1801288d6  jnz     short loc_1801288E1
0x1801288d8  lea     rcx, [rbx+58h]
0x1801288dc  call    ?SetEvent@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x1801288e1  mov     rcx, [rsp+148h+lpCriticalSection]; lpCriticalSection
0x1801288e6  test    rcx, rcx
0x1801288e9  jz      short loc_1801288F2
0x1801288eb  call    cs:__imp_LeaveCriticalSection
0x1801288f1  nop
0x1801288f2  mov     rcx, [rsp+148h+var_D0]; lpCriticalSection
0x1801288f7  test    rcx, rcx
0x1801288fa  jz      short loc_180128903
0x1801288fc  call    cs:__imp_LeaveCriticalSection
0x180128902  nop
0x180128903  jmp     loc_1801289E4
0x180128908  mov     eax, cs:dword_1801BD288
0x18012890e  cmp     eax, 4
0x180128911  jbe     short loc_18012894A
0x180128913  mov     eax, [rbx+68h]
0x180128916  mov     [rsp+148h+var_E0], rax
0x18012891b  mov     rax, [rbx+60h]
0x18012891f  mov     [rsp+148h+var_C8], rax
0x180128927  lea     rax, [rsp+148h+var_E0]
0x18012892c  mov     [rsp+148h+var_120], rax
0x180128931  lea     rax, [rsp+148h+var_C8]
0x180128939  mov     qword ptr [rsp+148h+var_128], rax
0x18012893e  lea     rdx, unk_180198DC8
  ... truncated ...
```
