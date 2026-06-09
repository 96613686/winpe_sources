# DusmCache::QueryCostAsync(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *)

- ea: `0x18001c508`
- end: `0x18001c9f0`
- name: `?QueryCostAsync@DusmCache@@AEAAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@@Z`
- size: `1256`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bfec`
- `0x18001c23c`
- `0x18001d1d0`

## callees

- `0x180001f90`
- `0x1800020fc`
- `0x180003e08`
- `0x180003f44`
- `0x1800040e4`
- `0x1800043ec`
- `0x180007c90`
- `0x18000ea78`
- `0x180010e28`
- `0x180012368`
- `0x180012a90`
- `0x180012fcc`
- `0x1800132f4`
- `0x180013444`
- `0x18001742c`
- `0x180018a6c`
- `0x180018c04`
- `0x18001a8f4`
- `0x18001ae20`
- `0x18001aed4`
- `0x18001af48`
- `0x18001b888`
- `0x18001b8cc`
- `0x18001b944`
- `0x18001c508`
- `0x18001c9f8`
- `0x18001d87c`
- `0x18001db50`
- `0x18001dd00`
- `0x18002f5d4`

## string_xrefs

- `0x18001c7d5`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001c97e`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001c9a9`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001c9de`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001c997`: `DusmCache::QueryCostAsync::source`
- `0x18001c9cc`: `DusmCache::QueryCostAsync::mediaType`
- `0x18001c96f`: `DusmCache::QueryCostAsync::timeout`
- `0x18001c7c6`: `DusmCache::QueryCostAsync::completion`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DusmCache::QueryCostAsync(__int64 a1, const struct DusmConnection *a2, unsigned int a3, _QWORD *a4)
{
  unsigned int v7; // ebx
  DusmCache *v8; // r12
  __int64 v9; // rdx
  std::_Ref_count_base *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // ebx
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rdx
  __int64 ProfileName; // rax
  __int64 v21; // rax
  const WCHAR **v22; // rdx
  const WCHAR **v23; // r8
  const wchar_t **v24; // r9
  int v25; // r10d
  const struct _tlgProvider_t *v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  const WCHAR **v29; // rax
  const wchar_t **v30; // r8
  __int64 v31; // r9
  int v32; // r10d
  char *v33; // [rsp+28h] [rbp-D8h]
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 InterfaceGuid; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  char v39[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v42[56]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+E8h] [rbp-18h]
  DusmCache *v44; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v45; // [rsp+F8h] [rbp-8h]
  _BYTE v46[320]; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v47; // [rsp+240h] [rbp+140h]
  _QWORD v48[3]; // [rsp+248h] [rbp+148h] BYREF
  std::_Ref_count_base *v49[2]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( a3 - 1 > 2 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::QueryCostAsync::source",
      v33);
  v7 = *((_DWORD *)a2 + 4);
  if ( v7 != 1 && (unsigned int)(*((_DWORD *)a2 + 4) - 2) > 1 )
  {
    *a4 = UNKNOWN_COST_DATA;
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x197,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::QueryCostAsync::mediaType",
      v33);
  }
  v8 = DusmCache::s_pInstance;
  LODWORD(v34) = 0;
  DusmCache::QueryCostCache(DusmCache::s_pInstance);
  *(_OWORD *)v49 = 0;
  std::make_shared__DusmCache::QueryCostAsync_::_2_::QueryCostCompletion_(v49);
  v44 = v8;
  v45 = v7;
  DusmConnection::DusmConnection((DusmConnection *)v46, a2);
  v47 = a3;
  std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(
    v48,
    v49);
  v43 = 0;
  v43 = std::_Global_new_std::_Func_impl_no_alloc__DusmCache::QueryCostAsync_::_2_::_lambda_1__void___DusmCache::QueryCostAsync_::_2_::_lambda_1___(&v44);
  DusmAsync::SubmitWork(v42);
  std::function<long (void)>::~function<long (void)>((__int64)v42, v9);
  DusmCache::QueryCostAsync_::_2_::_lambda_1_::__lambda_1_(&v44);
  v10 = v49[0];
  if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                           (char *)v49[0] + 24,
                           1000) )
  {
    v15 = DusmTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v15 > 5u && (unsigned __int8)tlgKeywordOn(v15, 0) )
    {
      v34 = 0x3E8000005B4LL;
      v16 = EnumToString(a3);
      wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v41, v16);
      v17 = DusmMediaTypeToSz(v7);
      v18 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v36, v17);
      ProfileName = DusmConnection::GetProfileName(a2, v19, v18);
      v21 = std::wstring::c_str(ProfileName);
      wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v37, v21);
      InterfaceGuid = (__int64)DusmConnection::GetInterfaceGuid(a2);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v25,
        (int)&byte_180056FD9,
        (__int64)v23,
        (__int64)v24,
        &InterfaceGuid,
        v22,
        v23,
        v24,
        (__int64)&v34,
        (__int64)&v34 + 4);
    }
    v26 = DusmTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v26 > 5u && (unsigned __int8)tlgKeywordOn(v26, 0x400000000000LL) )
    {
      v27 = EnumToString(a3);
      wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v41, v27);
      v28 = DusmMediaTypeToSz(v7);
      v29 = (const WCHAR **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                              &v36,
                              v28);
      InterfaceGuid = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        v32,
        (int)&word_180056F7A,
        (__int64)v30,
        v31,
        (__int64)&InterfaceGuid,
        v29,
        v30);
    }
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x5B4,
      (unsigned int)"DusmCache::QueryCostAsync::timeout",
      v33);
  }
  if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8) > 5u )
  {
    InterfaceGuid = EnumToString(*((unsigned int *)v10 + 4));
    v36 = EnumToString(*((unsigned int *)v10 + 3));
    HIDWORD(v34) = *((_DWORD *)v10 + 2);
    LODWORD(v34) = 0;
    LODWORD(v38) = *(_DWORD *)v10;
    v37 = EnumToString(a3);
    v40 = DusmMediaTypeToSz(v7);
    *(_QWORD *)v39 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a2 + 48);
    v41 = (__int64)a2 + 32;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v11,
      (int)&dword_180056EEC,
      v11,
      v12,
      &v41,
      (const WCHAR **)v39,
      (const WCHAR **)&v40,
      (const wchar_t **)&v37,
      (__int64)&v38,
      (__int64)&v34,
      (__int64)&v34 + 4,
      (const wchar_t **)&v36,
      (const wchar_t **)&InterfaceGuid);
  }
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x20C,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
    (const char *)*(unsigned int *)v10,
    (unsigned int)"DusmCache::QueryCostAsync::completion",
    v33);
  *a4 = *(_QWORD *)((char *)v10 + 12);
  v13 = *((_DWORD *)v10 + 2);
  if ( v49[1] )
    std::_Ref_count_base::_Decref(v49[1]);
  return v13;
}

```

## disassembly

```asm
0x18001c508  push    rbp
0x18001c50a  push    rbx
0x18001c50b  push    rsi
0x18001c50c  push    rdi
0x18001c50d  push    r12
0x18001c50f  push    r14
0x18001c511  push    r15
0x18001c513  lea     rbp, [rsp-180h]
0x18001c51b  sub     rsp, 280h
0x18001c522  mov     rax, cs:__security_cookie
0x18001c529  xor     rax, rsp
0x18001c52c  mov     [rbp+1B0h+var_40], rax
0x18001c533  mov     r15, r9
0x18001c536  mov     r14d, r8d
0x18001c539  mov     rsi, rdx
0x18001c53c  lea     eax, [r8-1]
0x18001c540  cmp     eax, 2
0x18001c543  ja      loc_18001C990
0x18001c549  mov     ebx, [rdx+10h]
0x18001c54c  mov     ecx, ebx
0x18001c54e  sub     ecx, 1
0x18001c551  jz      short loc_18001C561
0x18001c553  sub     ecx, 1
0x18001c556  jz      short loc_18001C561
0x18001c558  cmp     ecx, 1
0x18001c55b  jnz     loc_18001C9BB
0x18001c561  mov     r12, cs:?s_pInstance@DusmCache@@0PEAV1@EA; DusmCache * DusmCache::s_pInstance
0x18001c568  mov     dword ptr [rsp+2B0h+var_240], 0
0x18001c570  lea     rax, [rsp+2B0h+var_240]
0x18001c575  mov     qword ptr [rsp+2B0h+var_290], rax
0x18001c57a  mov     rcx, r12
0x18001c57d  call    ?QueryCostCache@DusmCache@@AEAAHAEBVDusmConnection@@W4_DUSM_SOURCE@@PEAU_DUSM_CONNECTION_COST_DATA@@PEAH@Z; DusmCache::QueryCostCache(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA *,int *)
0x18001c582  mov     edi, eax
0x18001c584  cmp     dword ptr [rsp+2B0h+var_240], 0
0x18001c589  jz      loc_18001C657
0x18001c58f  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001c594  mov     r8, [rax+8]
0x18001c598  mov     ecx, [r8]
0x18001c59b  cmp     ecx, 5
0x18001c59e  jbe     loc_18001C650
0x18001c5a4  mov     ecx, [r15+4]
0x18001c5a8  call    ?EnumToString@@YAPEBDW4COST_SET_SOURCE@@@Z; EnumToString(COST_SET_SOURCE)
0x18001c5ad  mov     [rbp+1B0h+var_220], rax
0x18001c5b1  mov     ecx, [r15]
0x18001c5b4  call    ?EnumToString@@YAPEBDW4_DUSM_CONNECTION_COST@@@Z; EnumToString(_DUSM_CONNECTION_COST)
0x18001c5b9  mov     qword ptr [rbp+1B0h+var_218], rax
0x18001c5bd  mov     dword ptr [rsp+2B0h+var_240], edi
0x18001c5c1  mov     dword ptr [rsp+2B0h+var_240+4], 1
0x18001c5c9  mov     ecx, r14d
0x18001c5cc  call    ?EnumToString@@YAPEBDW4_DUSM_SOURCE@@@Z; EnumToString(_DUSM_SOURCE)
0x18001c5d1  mov     [rbp+1B0h+var_210], rax
0x18001c5d5  mov     ecx, ebx
0x18001c5d7  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18001c5dc  mov     [rbp+1B0h+var_228], rax
0x18001c5e0  lea     rcx, [rsi+30h]
0x18001c5e4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c5e9  mov     [rbp+1B0h+var_230], rax
0x18001c5ed  lea     rax, [rsi+20h]
0x18001c5f1  mov     [rsp+2B0h+var_238], rax
0x18001c5f6  lea     rax, [rbp+1B0h+var_220]
0x18001c5fa  mov     [rsp+2B0h+var_258], rax; __int64
0x18001c5ff  lea     rax, [rbp+1B0h+var_218]
0x18001c603  mov     [rsp+2B0h+var_260], rax; __int64
0x18001c608  lea     rax, [rsp+2B0h+var_240]
0x18001c60d  mov     [rsp+2B0h+var_268], rax; __int64
0x18001c612  lea     rax, [rsp+2B0h+var_240+4]
0x18001c617  mov     [rsp+2B0h+var_270], rax; __int64
0x18001c61c  lea     rax, [rbp+1B0h+var_210]
0x18001c620  mov     [rsp+2B0h+var_278], rax; __int64
0x18001c625  lea     rax, [rbp+1B0h+var_228]
0x18001c629  mov     [rsp+2B0h+var_280], rax; __int64
0x18001c62e  lea     rax, [rbp+1B0h+var_230]
0x18001c632  mov     [rsp+2B0h+var_288], rax; __int64
0x18001c637  lea     rax, [rsp+2B0h+var_238]
0x18001c63c  mov     qword ptr [rsp+2B0h+var_290], rax; __int64
0x18001c641  lea     rdx, word_18005704A; int
0x18001c648  mov     rcx, r8; int
0x18001c64b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@655@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001c650  mov     eax, edi
0x18001c652  jmp     loc_18001C803
0x18001c657  xorps   xmm0, xmm0
0x18001c65a  movups  xmmword ptr [rbp+1B0h+var_50], xmm0
0x18001c661  lea     rcx, [rbp+1B0h+var_50]
0x18001c668  call    std__make_shared__DusmCache__QueryCostAsync____2___QueryCostCompletion_
0x18001c66d  nop
0x18001c66e  mov     [rbp+1B0h+var_1C0], r12
0x18001c672  mov     [rbp+1B0h+var_1B8], ebx
0x18001c675  mov     rdx, rsi; struct DusmConnection *
0x18001c678  lea     rcx, [rbp+1B0h+var_1B0]; this
0x18001c67c  call    ??0DusmConnection@@QEAA@AEBV0@@Z; DusmConnection::DusmConnection(DusmConnection const &)
0x18001c681  mov     [rbp+1B0h+var_70], r14d
0x18001c688  lea     rdx, [rbp+1B0h+var_50]
0x18001c68f  lea     rcx, [rbp+1B0h+var_68]
0x18001c696  call    ??$?0V?$ThreadPoolWaitableResult@J@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<long>> const &)
0x18001c69b  nop
0x18001c69c  mov     [rbp+1B0h+var_1C8], 0
0x18001c6a4  lea     rcx, [rbp+1B0h+var_1C0]
0x18001c6a8  call    std___Global_new_std___Func_impl_no_alloc__DusmCache__QueryCostAsync____2____lambda_1__void___DusmCache__QueryCostAsync____2____lambda_1___
0x18001c6ad  mov     [rbp+1B0h+var_1C8], rax
0x18001c6b1  lea     rcx, [rbp+1B0h+var_200]
0x18001c6b5  call    ?SubmitWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitWork(std::function<void (void)> &&)
0x18001c6ba  lea     rcx, [rbp+1B0h+var_200]
0x18001c6be  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18001c6c3  nop
0x18001c6c4  lea     rcx, [rbp+1B0h+var_1C0]
0x18001c6c8  call    _DusmCache__QueryCostAsync____2____lambda_1_____lambda_1_
0x18001c6cd  mov     rdi, [rbp+1B0h+var_50]
0x18001c6d4  lea     rcx, [rdi+18h]
0x18001c6d8  mov     r12d, 3E8h
0x18001c6de  mov     edx, r12d
0x18001c6e1  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x18001c6e6  test    al, al
0x18001c6e8  jz      loc_18001C824
0x18001c6ee  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001c6f3  mov     r8, [rax+8]
0x18001c6f7  mov     eax, [r8]
0x18001c6fa  cmp     eax, 5
0x18001c6fd  jbe     loc_18001C7BF
0x18001c703  mov     ecx, [rdi+10h]
0x18001c706  call    ?EnumToString@@YAPEBDW4COST_SET_SOURCE@@@Z; EnumToString(COST_SET_SOURCE)
0x18001c70b  mov     [rsp+2B0h+var_238], rax
0x18001c710  mov     ecx, [rdi+0Ch]
0x18001c713  call    ?EnumToString@@YAPEBDW4_DUSM_CONNECTION_COST@@@Z; EnumToString(_DUSM_CONNECTION_COST)
0x18001c718  mov     [rbp+1B0h+var_230], rax
0x18001c71c  mov     eax, [rdi+8]
0x18001c71f  mov     dword ptr [rsp+2B0h+var_240+4], eax
0x18001c723  mov     dword ptr [rsp+2B0h+var_240], 0
0x18001c72b  mov     eax, [rdi]
0x18001c72d  mov     dword ptr [rbp+1B0h+var_220], eax
0x18001c730  mov     ecx, r14d
0x18001c733  call    ?EnumToString@@YAPEBDW4_DUSM_SOURCE@@@Z; EnumToString(_DUSM_SOURCE)
0x18001c738  mov     [rbp+1B0h+var_228], rax
0x18001c73c  mov     ecx, ebx
0x18001c73e  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18001c743  mov     [rbp+1B0h+var_210], rax
0x18001c747  lea     rcx, [rsi+30h]
0x18001c74b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c750  mov     qword ptr [rbp+1B0h+var_218], rax
0x18001c754  lea     rax, [rsi+20h]
0x18001c758  mov     [rbp+1B0h+var_208], rax
0x18001c75c  lea     rax, [rsp+2B0h+var_238]
0x18001c761  mov     [rsp+2B0h+var_250], rax; __int64
0x18001c766  lea     rax, [rbp+1B0h+var_230]
0x18001c76a  mov     [rsp+2B0h+var_258], rax; __int64
0x18001c76f  lea     rax, [rsp+2B0h+var_240+4]
0x18001c774  mov     [rsp+2B0h+var_260], rax; __int64
0x18001c779  lea     rax, [rsp+2B0h+var_240]
0x18001c77e  mov     [rsp+2B0h+var_268], rax; __int64
0x18001c783  lea     rax, [rbp+1B0h+var_220]
0x18001c787  mov     [rsp+2B0h+var_270], rax; __int64
0x18001c78c  lea     rax, [rbp+1B0h+var_228]
0x18001c790  mov     [rsp+2B0h+var_278], rax; __int64
0x18001c795  lea     rax, [rbp+1B0h+var_210]
0x18001c799  mov     [rsp+2B0h+var_280], rax; __int64
0x18001c79e  lea     rax, [rbp+1B0h+var_218]
0x18001c7a2  mov     [rsp+2B0h+var_288], rax; char *
0x18001c7a7  lea     rax, [rbp+1B0h+var_208]
0x18001c7ab  mov     qword ptr [rsp+2B0h+var_290], rax; __int64
0x18001c7b0  lea     rdx, dword_180056EEC; int
0x18001c7b7  mov     rcx, r8; int
0x18001c7ba  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@U4@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@6655@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001c7bf  mov     rcx, [rbp+1B8h]; this
0x18001c7c6  lea     rax, aDusmcacheQuery_2; "DusmCache::QueryCostAsync::completion"
0x18001c7cd  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x18001c7d2  mov     r9d, [rdi]; char *
0x18001c7d5  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001c7dc  mov     edx, 20Ch; void *
0x18001c7e1  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18001c7e6  mov     rax, [rdi+0Ch]
0x18001c7ea  mov     [r15], rax
0x18001c7ed  mov     ebx, [rdi+8]
0x18001c7f0  mov     rcx, [rbp+1B0h+var_50+8]; this
0x18001c7f7  test    rcx, rcx
0x18001c7fa  jz      short loc_18001C801
0x18001c7fc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c801  mov     eax, ebx
0x18001c803  mov     rcx, [rbp+1B0h+var_40]
0x18001c80a  xor     rcx, rsp; StackCookie
0x18001c80d  call    __security_check_cookie
0x18001c812  add     rsp, 280h
0x18001c819  pop     r15
0x18001c81b  pop     r14
0x18001c81d  pop     r12
0x18001c81f  pop     rdi
0x18001c820  pop     rsi
0x18001c821  pop     rbx
0x18001c822  pop     rbp
0x18001c823  retn
0x18001c824  call    ?Provider@DusmTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DusmTraceLoggingProvider::Provider(void)
0x18001c829  nop
0x18001c82a  mov     r10, rax
0x18001c82d  mov     ecx, [rax]
0x18001c82f  mov     edi, 5B4h
0x18001c834  cmp     ecx, 5
0x18001c837  jbe     loc_18001C8ED
0x18001c83d  xor     edx, edx
0x18001c83f  mov     rcx, rax
0x18001c842  call    _tlgKeywordOn
0x18001c847  test    al, al
0x18001c849  jz      loc_18001C8ED
0x18001c84f  mov     dword ptr [rsp+2B0h+var_240+4], r12d
0x18001c854  mov     dword ptr [rsp+2B0h+var_240], edi
0x18001c858  mov     ecx, r14d
0x18001c85b  call    ?EnumToString@@YAPEBDW4_DUSM_SOURCE@@@Z; EnumToString(_DUSM_SOURCE)
0x18001c860  mov     rdx, rax
0x18001c863  lea     rcx, [rbp+1B0h+var_208]
0x18001c867  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001c86c  mov     r9, rax
0x18001c86f  mov     ecx, ebx
0x18001c871  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18001c876  mov     rdx, rax
0x18001c879  lea     rcx, [rbp+1B0h+var_230]
0x18001c87d  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001c882  mov     r8, rax
0x18001c885  mov     rcx, rsi
0x18001c888  call    ?GetProfileName@DusmConnection@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; DusmConnection::GetProfileName(void)
0x18001c88d  mov     rcx, rax
0x18001c890  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18001c895  mov     rdx, rax
0x18001c898  lea     rcx, [rbp+1B0h+var_228]
0x18001c89c  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001c8a1  mov     rdx, rax
0x18001c8a4  mov     rcx, rsi; this
0x18001c8a7  call    ?GetInterfaceGuid@DusmConnection@@QEBAAEBU_GUID@@XZ; DusmConnection::GetInterfaceGuid(void)
0x18001c8ac  mov     [rsp+2B0h+var_238], rax
0x18001c8b1  lea     rax, [rsp+2B0h+var_240+4]
0x18001c8b6  mov     [rsp+2B0h+var_268], rax; __int64
0x18001c8bb  lea     rax, [rsp+2B0h+var_240]
0x18001c8c0  mov     [rsp+2B0h+var_270], rax; __int64
0x18001c8c5  mov     [rsp+2B0h+var_278], r9; __int64
0x18001c8ca  mov     [rsp+2B0h+var_280], r8; __int64
0x18001c8cf  mov     [rsp+2B0h+var_288], rdx; __int64
0x18001c8d4  lea     rax, [rsp+2B0h+var_238]
0x18001c8d9  mov     qword ptr [rsp+2B0h+var_290], rax; __int64
0x18001c8de  lea     rdx, byte_180056FD9; int
0x18001c8e5  mov     rcx, r10; int
0x18001c8e8  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c8ed  call    ?Provider@DusmTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DusmTraceLoggingProvider::Provider(void)
0x18001c8f2  mov     r10, rax
0x18001c8f5  mov     ecx, [rax]
0x18001c8f7  cmp     ecx, 5
0x18001c8fa  jbe     short loc_18001C968
0x18001c8fc  mov     rdx, 400000000000h
0x18001c906  mov     rcx, rax
0x18001c909  call    _tlgKeywordOn
0x18001c90e  test    al, al
0x18001c910  jz      short loc_18001C968
0x18001c912  mov     ecx, r14d
0x18001c915  call    ?EnumToString@@YAPEBDW4_DUSM_SOURCE@@@Z; EnumToString(_DUSM_SOURCE)
0x18001c91a  mov     rdx, rax
0x18001c91d  lea     rcx, [rbp+1B0h+var_208]
0x18001c921  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001c926  mov     r8, rax
0x18001c929  mov     ecx, ebx
0x18001c92b  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18001c930  mov     rdx, rax
0x18001c933  lea     rcx, [rbp+1B0h+var_230]
0x18001c937  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001c93c  mov     [rsp+2B0h+var_238], 800h
0x18001c945  mov     [rsp+2B0h+var_280], r8; __int64
0x18001c94a  mov     [rsp+2B0h+var_288], rax; char *
0x18001c94f  lea     rax, [rsp+2B0h+var_238]
0x18001c954  mov     qword ptr [rsp+2B0h+var_290], rax; __int64
0x18001c959  lea     rdx, word_180056F7A; int
0x18001c960  mov     rcx, r10; int
0x18001c963  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x18001c968  mov     rcx, [rbp+1B8h]; this
0x18001c96f  lea     rax, aDusmcacheQuery_1; "DusmCache::QueryCostAsync::timeout"
0x18001c976  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x18001c97b  mov     r9d, edi; char *
0x18001c97e  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001c985  mov     edx, 1FBh; void *
0x18001c98a  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001c990  mov     rcx, [rbp+1B8h]; this
0x18001c997  lea     rax, aDusmcacheQuery_3; "DusmCache::QueryCostAsync::source"
0x18001c99e  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x18001c9a3  mov     r9d, 57h ; 'W'; char *
0x18001c9a9  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001c9b0  mov     edx, 189h; void *
0x18001c9b5  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001c9bb  mov     rax, cs:?UNKNOWN_COST_DATA@@3U_DUSM_CONNECTION_COST_DATA@@B; _DUSM_CONNECTION_COST_DATA const UNKNOWN_COST_DATA
0x18001c9c2  mov     [r9], rax
0x18001c9c5  mov     rcx, [rbp+1B8h]; this
0x18001c9cc  lea     rax, aDusmcacheQuery_4; "DusmCache::QueryCostAsync::mediaType"
0x18001c9d3  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x18001c9d8  mov     r9d, 57h ; 'W'; char *
0x18001c9de  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001c9e5  mov     edx, 197h; void *
0x18001c9ea  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
