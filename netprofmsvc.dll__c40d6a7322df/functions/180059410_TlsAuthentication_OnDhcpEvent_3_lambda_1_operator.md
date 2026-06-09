# _TlsAuthentication::OnDhcpEvent_::_3_::_lambda_1_::operator()

- ea: `0x180059410`
- end: `0x1800597b9`
- name: `_TlsAuthentication::OnDhcpEvent_::_3_::_lambda_1_::operator()`
- size: `937`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180059400`

## callees

- `0x180009990`
- `0x18000e190`
- `0x180013748`
- `0x18002a2b4`
- `0x18002bd40`
- `0x18003f6cc`
- `0x180040738`
- `0x1800496c4`
- `0x18004b7b4`
- `0x18004cdc8`
- `0x18004da8c`
- `0x18004ef08`
- `0x180059410`
- `0x180090944`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800aba25`
- `0x180124428`
- `0x1801244cc`
- `0x180125b14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800596d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059705`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800596d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059705`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005971a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005971a`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x1800594fb`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x1800594fb`

## string_xrefs

- `0x1800597a6`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\tlsauthentication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall TlsAuthentication::OnDhcpEvent_::_3_::_lambda_1_::operator()(_QWORD *a1)
{
  const char *v1; // r9
  __int64 v2; // r14
  __int64 *v3; // r12
  unsigned int v4; // eax
  __int64 i; // rsi
  size_t v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // rax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  unsigned int v11; // r9d
  __int64 v12; // r9
  __int16 v13; // ax
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  const char *v18; // r9
  _QWORD *v19; // r15
  unsigned int v20; // [rsp+20h] [rbp-378h]
  char v21; // [rsp+30h] [rbp-368h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp-360h] BYREF
  _BYTE v23[8]; // [rsp+40h] [rbp-358h] BYREF
  __int64 v24; // [rsp+48h] [rbp-350h] BYREF
  _QWORD *v25; // [rsp+50h] [rbp-348h]
  _QWORD v26[2]; // [rsp+58h] [rbp-340h] BYREF
  char v27; // [rsp+68h] [rbp-330h]
  char v28; // [rsp+69h] [rbp-32Fh]
  _QWORD v29[3]; // [rsp+70h] [rbp-328h] BYREF
  __int128 v30; // [rsp+88h] [rbp-310h] BYREF
  __int64 v31; // [rsp+98h] [rbp-300h]
  std::_Ref_count_base *v32[2]; // [rsp+A0h] [rbp-2F8h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-2E8h]
  std::_Ref_count_base *v34[2]; // [rsp+B8h] [rbp-2E0h] BYREF
  __int128 v35; // [rsp+C8h] [rbp-2D0h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-2C0h]
  void **v37; // [rsp+E0h] [rbp-2B8h] BYREF
  _BYTE v38[136]; // [rsp+E8h] [rbp-2B0h] BYREF
  WCHAR InterfaceName[256]; // [rsp+170h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  try
  {
    v19 = a1;
    v25 = a1;
    *(_OWORD *)v34 = 0;
    ctl::ctNetAdapterAddresses::ctNetAdapterAddresses((ctl::ctNetAdapterAddresses *)v34, 0, 0x26u);
    *(_OWORD *)v32 = 0;
    v33 = 0;
    ctl::ctNetAdapterAddresses::begin(v34, v32);
    v35 = 0;
    v36 = 0;
    while ( (unsigned __int8)ctl::ctNetAdapterAddresses::iterator::operator!=(v32, &v35) )
    {
      v2 = ctl::ctNetAdapterAddresses::iterator::operator*(v32);
      v3 = (__int64 *)(v2 + 224);
      memset_0(InterfaceName, 0, sizeof(InterfaceName));
      v4 = ConvertInterfaceLuidToNameW((const NET_LUID *)(v2 + 224), InterfaceName, 0x100u);
      try
      {
        if ( v4 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x5F3,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\tlsauthentication.cpp",
            (const char *)v4,
            v20);
        v30 = 0;
        v31 = 0;
        for ( i = *(_QWORD *)(v2 + 48); i; i = *(_QWORD *)(i + 8) )
        {
          v37 = &ctl::ctSockaddr::`vftable';
          v6 = 128;
          if ( (unsigned __int64)*(int *)(i + 24) <= 0x80 )
            v6 = *(int *)(i + 24);
          memset_0(v38, 0, 0x80u);
          memcpy_0(v38, *(const void **)(i + 16), v6);
          std::vector<ctl::ctSockaddr>::_Emplace_one_at_back<ctl::ctSockaddr const &>(&v30, &v37);
          if ( (unsigned int)dword_1801BD288 > 4 )
          {
            v7 = (struct _RTL_CRITICAL_SECTION *)ctl::ctSockaddr::writeAddress(&v37, v26);
            if ( v7->LockSemaphore > HANDLE_FLAG_PROTECT_FROM_CLOSE|HANDLE_FLAG_INHERIT|0x4 )
              v7 = (struct _RTL_CRITICAL_SECTION *)v7->DebugInfo;
            lpCriticalSection = v7;
            v24 = *v3;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
              v8,
              (unsigned int)&byte_1801980A7,
              v9,
              v10,
              (__int64)&v24,
              (__int64)&lpCriticalSection);
            std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(v26);
          }
        }
        v11 = *(_DWORD *)(v2 + 92);
        if ( (v11 & 0x80u) == 0 )
        {
          HIBYTE(v13) = 0;
        }
        else
        {
          v12 = v11 >> 2;
          LOBYTE(v12) = v12 & 1;
          v13 = *(_WORD *)IsV4DhcpStable(v23, v3, InterfaceName, v12);
          v21 = v13;
        }
        v26[0] = *v19;
        v14 = v26[0];
        v26[1] = *v3;
        v27 = v21;
        v28 = HIBYTE(v13);
        v15 = v31;
        v31 = 0;
        v16 = *((_QWORD *)&v30 + 1);
        v17 = v30;
        v30 = 0u;
        v29[0] = v17;
        v29[1] = v16;
        v29[2] = v15;
        lpCriticalSection = 0;
        wil::EnterCriticalSection(&lpCriticalSection, v26[0] + 136LL);
        if ( *(_BYTE *)(v14 + 400) )
        {
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
        }
        else
        {
          if ( *(_DWORD *)(v14 + 128) == 1 )
            std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back___TlsAuthentication::OnDhcpEvent_::_3_::_lambda_1_::operator()_::_8_::_lambda_1___(
              v14 + 280,
              v26);
          else
            std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back___TlsAuthentication::OnDhcpEvent_::_3_::_lambda_1_::operator()_::_8_::_lambda_1___(
              v14 + 360,
              v26);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          _InterlockedIncrement64((volatile signed __int64 *)(v14 + 264));
          SubmitThreadpoolWork(*(PTP_WORK *)(v14 + 256));
        }
        std::vector<ctl::ctSockaddr>::_Tidy(v29);
        std::vector<ctl::ctSockaddr>::_Tidy(&v30);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x61D,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\tlsauthentication.cpp",
          v18);
        v19 = v25;
      }
      ctl::ctNetAdapterAddresses::iterator::operator++(v32);
    }
    if ( v32[1] )
      std::_Ref_count_base::_Decref(v32[1]);
    if ( v34[1] )
      std::_Ref_count_base::_Decref(v34[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x620,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\tlsauthentication.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x180059410  mov     [rsp+arg_8], rbx
0x180059415  mov     [rsp+arg_10], rsi
0x18005941a  push    r12
0x18005941c  push    r14
0x18005941e  push    r15
0x180059420  sub     rsp, 380h
0x180059427  mov     rax, cs:__security_cookie
0x18005942e  xor     rax, rsp
0x180059431  mov     [rsp+398h+var_28], rax
0x180059439  mov     r15, rcx
0x18005943c  mov     [rsp+398h+var_348], rcx
0x180059441  xorps   xmm0, xmm0
0x180059444  movups  xmmword ptr [rsp+398h+var_2E0], xmm0
0x18005944c  xor     edx, edx; unsigned int
0x18005944e  lea     r8d, [rdx+26h]; unsigned int
0x180059452  lea     rcx, [rsp+398h+var_2E0]; this
0x18005945a  call    ??0ctNetAdapterAddresses@ctl@@QEAA@IK@Z; ctl::ctNetAdapterAddresses::ctNetAdapterAddresses(uint,ulong)
0x18005945f  nop
0x180059460  xorps   xmm0, xmm0
0x180059463  xor     eax, eax
0x180059465  movups  xmmword ptr [rsp+398h+var_2F8], xmm0
0x18005946d  mov     [rsp+398h+var_2E8], rax
0x180059475  lea     rdx, [rsp+398h+var_2F8]
0x18005947d  lea     rcx, [rsp+398h+var_2E0]
0x180059485  call    ?begin@ctNetAdapterAddresses@ctl@@QEBA?AViterator@12@XZ; ctl::ctNetAdapterAddresses::begin(void)
0x18005948a  nop
0x18005948b  xor     eax, eax
0x18005948d  xorps   xmm1, xmm1
0x180059490  movdqu  [rsp+398h+var_2D0], xmm1
0x180059499  mov     [rsp+398h+var_2C0], rax
0x1800594a1  lea     rdx, [rsp+398h+var_2D0]
0x1800594a9  lea     rcx, [rsp+398h+var_2F8]
0x1800594b1  call    ??9iterator@ctNetAdapterAddresses@ctl@@QEBA_NAEBV012@@Z; ctl::ctNetAdapterAddresses::iterator::operator!=(ctl::ctNetAdapterAddresses::iterator const &)
0x1800594b6  test    al, al
0x1800594b8  jz      loc_180059753
0x1800594be  lea     rcx, [rsp+398h+var_2F8]
0x1800594c6  call    ??Diterator@ctNetAdapterAddresses@ctl@@QEBAAEAU_IP_ADAPTER_ADDRESSES_LH@@XZ; ctl::ctNetAdapterAddresses::iterator::operator*(void)
0x1800594cb  mov     r14, rax
0x1800594ce  lea     r12, [rax+0E0h]
0x1800594d5  xor     edx, edx; Val
0x1800594d7  mov     r8d, 200h; Size
0x1800594dd  lea     rcx, [rsp+398h+InterfaceName]; void *
0x1800594e5  call    memset_0
0x1800594ea  mov     r8d, 100h; Length
0x1800594f0  lea     rdx, [rsp+398h+InterfaceName]; InterfaceName
0x1800594f8  mov     rcx, r12; InterfaceLuid
0x1800594fb  call    cs:__imp_ConvertInterfaceLuidToNameW
0x180059501  mov     rcx, [rsp+398h]; this
0x180059509  test    eax, eax
0x18005950b  jnz     loc_1800597A3
0x180059511  xor     eax, eax
0x180059513  xorps   xmm1, xmm1
0x180059516  movdqu  [rsp+398h+var_310], xmm1
0x18005951f  mov     [rsp+398h+var_300], rax
0x180059527  mov     rsi, [r14+30h]
0x18005952b  test    rsi, rsi
0x18005952e  jz      loc_1800595F9
0x180059534  lea     rax, ??_7ctSockaddr@ctl@@6B@; const ctl::ctSockaddr::`vftable'
0x18005953b  mov     [rsp+398h+var_2B8], rax
0x180059543  movsxd  rax, dword ptr [rsi+18h]
0x180059547  mov     ebx, 80h
0x18005954c  cmp     rax, rbx
0x18005954f  cmovbe  rbx, rax
0x180059553  xor     edx, edx; Val
0x180059555  mov     r8d, 80h; Size
0x18005955b  lea     rcx, [rsp+398h+var_2B0]; void *
0x180059563  call    memset_0
0x180059568  mov     r8, rbx; Size
0x18005956b  mov     rdx, [rsi+10h]; Src
0x18005956f  lea     rcx, [rsp+398h+var_2B0]; void *
0x180059577  call    memcpy_0
0x18005957c  lea     rdx, [rsp+398h+var_2B8]
0x180059584  lea     rcx, [rsp+398h+var_310]
0x18005958c  call    ??$_Emplace_one_at_back@AEBVctSockaddr@ctl@@@?$vector@VctSockaddr@ctl@@V?$allocator@VctSockaddr@ctl@@@std@@@std@@AEAAAEAVctSockaddr@ctl@@AEBV23@@Z; std::vector<ctl::ctSockaddr>::_Emplace_one_at_back<ctl::ctSockaddr const &>(ctl::ctSockaddr const &)
0x180059591  mov     eax, cs:dword_1801BD288
0x180059597  cmp     eax, 4
0x18005959a  jbe     short loc_1800595F0
0x18005959c  lea     rdx, [rsp+398h+var_340]
0x1800595a1  lea     rcx, [rsp+398h+var_2B8]
0x1800595a9  call    ?writeAddress@ctSockaddr@ctl@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ctl::ctSockaddr::writeAddress(void)
0x1800595ae  cmp     qword ptr [rax+18h], 7
0x1800595b3  jbe     short loc_1800595B8
0x1800595b5  mov     rax, [rax]
0x1800595b8  mov     [rsp+398h+lpCriticalSection], rax
0x1800595bd  mov     rax, [r12]
0x1800595c1  mov     [rsp+398h+var_350], rax
0x1800595c6  lea     rax, [rsp+398h+lpCriticalSection]
0x1800595cb  mov     [rsp+398h+var_370], rax
0x1800595d0  lea     rax, [rsp+398h+var_350]
0x1800595d5  mov     [rsp+398h+var_378], rax
0x1800595da  lea     rdx, byte_1801980A7
0x1800595e1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &)
0x1800595e6  lea     rcx, [rsp+398h+var_340]; void *
0x1800595eb  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; std::pair<std::wstring,Marshal::UnmarshalError>::~pair<std::wstring,Marshal::UnmarshalError>(void)
0x1800595f0  mov     rsi, [rsi+8]
0x1800595f4  jmp     loc_18005952B
0x1800595f9  mov     [rsp+398h+var_368+1], 0
0x1800595fe  mov     r9d, [r14+5Ch]
0x180059602  test    r9b, r9b
0x180059605  jns     short loc_18005962E
0x180059607  shr     r9d, 2
0x18005960b  and     r9b, 1
0x18005960f  lea     r8, [rsp+398h+InterfaceName]
0x180059617  mov     rdx, r12
0x18005961a  lea     rcx, [rsp+398h+var_358]
0x18005961f  call    IsV4DhcpStable
0x180059624  movzx   eax, word ptr [rax]
0x180059627  mov     word ptr [rsp+398h+var_368], ax
0x18005962c  jmp     short loc_180059633
0x18005962e  movzx   eax, word ptr [rsp+398h+var_368]
0x180059633  mov     rbx, [r15]
0x180059636  mov     [rsp+398h+var_340], rbx
0x18005963b  mov     rcx, [r12]
0x18005963f  mov     [rsp+398h+var_338], rcx
0x180059644  mov     cl, [rsp+398h+var_368]
0x180059648  mov     [rsp+398h+var_330], cl
0x18005964c  shr     ax, 8
0x180059650  mov     [rsp+398h+var_32F], al
0x180059654  mov     rdx, [rsp+398h+var_300]
0x18005965c  mov     [rsp+398h+var_300], 0
0x180059668  mov     rcx, qword ptr [rsp+398h+var_310+8]
0x180059670  mov     qword ptr [rsp+398h+var_310+8], 0
0x18005967c  mov     rax, qword ptr [rsp+398h+var_310]
0x180059684  mov     qword ptr [rsp+398h+var_310], 0
0x180059690  mov     [rsp+398h+var_328], rax
0x180059695  mov     [rsp+398h+var_320], rcx
0x18005969a  mov     [rsp+398h+var_318], rdx
0x1800596a2  mov     [rsp+398h+lpCriticalSection], 0
0x1800596ab  lea     rdx, [rbx+88h]
0x1800596b2  lea     rcx, [rsp+398h+lpCriticalSection]
0x1800596b7  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800596bc  nop
0x1800596bd  lea     rcx, [rbx+118h]
0x1800596c4  cmp     byte ptr [rcx+78h], 0
0x1800596c8  jz      short loc_1800596DC
0x1800596ca  mov     rcx, [rsp+398h+lpCriticalSection]; lpCriticalSection
0x1800596cf  test    rcx, rcx
0x1800596d2  jz      short loc_180059721
0x1800596d4  call    cs:__imp_LeaveCriticalSection
0x1800596da  jmp     short loc_180059721
0x1800596dc  lea     rdx, [rsp+398h+var_340]
0x1800596e1  cmp     dword ptr [rbx+80h], 1
0x1800596e8  jnz     short loc_1800596F1
0x1800596ea  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back___TlsAuthentication__OnDhcpEvent____3____lambda_1___operator______8____lambda_1___
0x1800596ef  jmp     short loc_1800596FB
0x1800596f1  add     rcx, 50h ; 'P'
0x1800596f5  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back___TlsAuthentication__OnDhcpEvent____3____lambda_1___operator______8____lambda_1___
0x1800596fa  nop
0x1800596fb  mov     rcx, [rsp+398h+lpCriticalSection]; lpCriticalSection
0x180059700  test    rcx, rcx
0x180059703  jz      short loc_18005970B
0x180059705  call    cs:__imp_LeaveCriticalSection
0x18005970b  lock inc qword ptr [rbx+108h]
0x180059713  mov     rcx, [rbx+100h]; pwk
0x18005971a  call    cs:__imp_SubmitThreadpoolWork
0x180059720  nop
0x180059721  lea     rcx, [rsp+398h+var_328]
0x180059726  call    ?_Tidy@?$vector@VctSockaddr@ctl@@V?$allocator@VctSockaddr@ctl@@@std@@@std@@AEAAXXZ; std::vector<ctl::ctSockaddr>::_Tidy(void)
0x18005972b  nop
0x18005972c  lea     rcx, [rsp+398h+var_310]
0x180059734  call    ?_Tidy@?$vector@VctSockaddr@ctl@@V?$allocator@VctSockaddr@ctl@@@std@@@std@@AEAAXXZ; std::vector<ctl::ctSockaddr>::_Tidy(void)
0x180059739  nop
0x18005973a  jmp     short loc_180059741
0x18005973c  mov     r15, [rsp+398h+var_348]
0x180059741  lea     rcx, [rsp+398h+var_2F8]
0x180059749  call    ??Eiterator@ctNetAdapterAddresses@ctl@@QEAAAEAV012@XZ; ctl::ctNetAdapterAddresses::iterator::operator++(void)
0x18005974e  jmp     loc_1800594A1
0x180059753  mov     rcx, [rsp+398h+var_2F8+8]; this
0x18005975b  test    rcx, rcx
0x18005975e  jz      short loc_180059766
0x180059760  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180059765  nop
0x180059766  mov     rcx, [rsp+398h+var_2E0+8]; this
0x18005976e  test    rcx, rcx
0x180059771  jz      short loc_180059779
0x180059773  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180059778  nop
0x180059779  mov     rcx, [rsp+398h+var_28]
0x180059781  xor     rcx, rsp; StackCookie
0x180059784  call    __security_check_cookie
0x180059789  lea     r11, [rsp+398h+var_18]
0x180059791  mov     rbx, [r11+28h]
0x180059795  mov     rsi, [r11+30h]
0x180059799  mov     rsp, r11
0x18005979c  pop     r15
0x18005979e  pop     r14
0x1800597a0  pop     r12
0x1800597a2  retn
0x1800597a3  mov     r9d, eax; char *
0x1800597a6  lea     r8, aOnecoreNetNetp_56; "onecore\\net\\netprofiles\\service\\src"...
0x1800597ad  mov     edx, 5F3h; void *
0x1800597b2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
