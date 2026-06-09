# PublicNetworkListManager::NLMServiceStateChangeCallback(ulong,void *)

- ea: `0x1800272f0`
- end: `0x180027622`
- name: `?NLMServiceStateChangeCallback@PublicNetworkListManager@@SAXKPEAX@Z`
- size: `818`
- prototype: `static void(unsigned int, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180001084`
- `0x1800011a0`
- `0x1800086b0`
- `0x180009184`
- `0x180009d08`
- `0x18000b624`
- `0x1800120d0`
- `0x180026c04`
- `0x1800272f0`
- `0x180029678`
- `0x18002a9b4`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800275a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800275a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002755e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002755e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800273c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800273c4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180027318`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180027318`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PublicNetworkListManager::NLMServiceStateChangeCallback(char a1, char *a2)
{
  HRESULT v4; // r14d
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  char v11; // bl
  int v12; // r15d
  bool v13; // bl
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  char *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  int PrivateNetworkListManager; // ebx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  char *v25; // rdx
  __int64 v26; // [rsp+40h] [rbp-28h] BYREF
  int v27; // [rsp+48h] [rbp-20h] BYREF
  BOOL v28; // [rsp+4Ch] [rbp-1Ch] BYREF
  struct INetworkListManagerPrivate *v29; // [rsp+50h] [rbp-18h] BYREF

  v4 = CoInitializeEx(0, 0);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
  {
    if ( (unsigned int)dword_18005F140 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18005F140, 0x400000000000LL) )
      {
        v29 = (struct INetworkListManagerPrivate *)2048;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v5,
          (int)&word_180055D86,
          v6,
          v7,
          (__int64)&v29);
      }
    }
    return;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl'::`2'::impl) )
  {
    v29 = 0;
    wil::EnterCriticalSection((struct _RTL_CRITICAL_SECTION **)&v29, (struct _RTL_CRITICAL_SECTION *)(a2 + 232));
    v11 = a2[276];
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>((struct _RTL_CRITICAL_SECTION **)&v29);
    if ( v11 )
      goto LABEL_8;
  }
  v12 = a1 & 8;
  v13 = v12 != 0;
  LOBYTE(v8) = a2[208];
  a2[208] = v12 != 0;
  if ( (v12 != 0) == (_BYTE)v8 )
    goto LABEL_8;
  if ( (unsigned int)dword_18005F140 > 5 )
  {
    v26 = 2048;
    v27 = (unsigned __int8)v8;
    v28 = v13;
    LODWORD(v29) = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v8,
      (int)&word_180055C86,
      v9,
      v10,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26);
  }
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl'::`2'::impl) )
  {
    if ( v12 )
    {
      if ( (int)PublicNetworkListManager::RetryStartPrivateNlm((PublicNetworkListManager *)a2) < 0
        && (unsigned int)dword_18005F140 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_18005F140, 0x400000000000LL) )
      {
        v26 = 2048;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v18,
          (int)&unk_180055E88,
          v19,
          v20,
          (__int64)&v26);
      }
      goto LABEL_8;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 232));
    if ( *((_DWORD *)a2 + 68) != -1 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 28) + 32LL))(*((_QWORD *)a2 + 28));
      *((_DWORD *)a2 + 68) = -1;
    }
    v29 = 0;
    PrivateNetworkListManager = PublicNetworkListManager::GetPrivateNetworkListManager(
                                  (PublicNetworkListManager *)a2,
                                  &v29);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 232));
    if ( PrivateNetworkListManager < 0 )
    {
      if ( (unsigned int)dword_18005F140 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_18005F140, 0x400000000000LL) )
        goto LABEL_38;
      v25 = byte_180055EE3;
    }
    else
    {
      if ( (unsigned int)dword_18005F140 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_18005F140, 0x400000000000LL) )
        goto LABEL_38;
      v25 = byte_180055DE3;
    }
    v26 = 2048;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v22,
      (int)v25,
      v23,
      v24,
      (__int64)&v26);
LABEL_38:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
    goto LABEL_8;
  }
  if ( (int)PublicNetworkListManager::RetryStartPrivateNlm((PublicNetworkListManager *)a2) < 0 )
  {
    if ( (unsigned int)dword_18005F140 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005F140, 0x400000000000LL) )
    {
      v17 = byte_180055D19;
      goto LABEL_22;
    }
  }
  else if ( (unsigned int)dword_18005F140 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005F140, 0x400000000000LL) )
  {
    v17 = byte_180055FC5;
LABEL_22:
    LODWORD(v29) = v13;
    v26 = 2048;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v14,
      (int)v17,
      v15,
      v16,
      (__int64)&v29,
      (__int64)&v26);
  }
LABEL_8:
  if ( v4 != -2147417850 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800272f0  push    rbp
0x1800272f2  push    rbx
0x1800272f3  push    rsi
0x1800272f4  push    rdi
0x1800272f5  push    r14
0x1800272f7  push    r15
0x1800272f9  mov     rbp, rsp
0x1800272fc  sub     rsp, 68h
0x180027300  mov     rax, cs:__security_cookie
0x180027307  xor     rax, rsp
0x18002730a  mov     [rbp+var_10], rax
0x18002730e  mov     rsi, rdx
0x180027311  mov     r15d, ecx
0x180027314  xor     edx, edx; dwCoInit
0x180027316  xor     ecx, ecx; pvReserved
0x180027318  call    cs:__imp_CoInitializeEx
0x18002731e  mov     r14d, eax
0x180027321  mov     eax, 80000000h
0x180027326  lea     edx, [r14+rax]
0x18002732a  test    eax, edx
0x18002732c  jnz     short loc_180027380
0x18002732e  cmp     r14d, 80010106h
0x180027335  jz      short loc_180027380
0x180027337  mov     eax, cs:dword_18005F140
0x18002733d  cmp     eax, 5
0x180027340  jbe     loc_1800273CA
0x180027346  mov     rdx, 400000000000h
0x180027350  lea     rcx, dword_18005F140
0x180027357  call    _tlgKeywordOn
0x18002735c  test    al, al
0x18002735e  jz      short loc_1800273CA
0x180027360  mov     edi, 800h
0x180027365  mov     [rbp+var_18], rdi
0x180027369  lea     rax, [rbp+var_18]
0x18002736d  mov     [rsp+68h+var_48], rax
0x180027372  lea     rdx, word_180055D86
0x180027379  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18002737e  jmp     short loc_1800273CA
0x180027380  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl(void)'::`2'::impl
0x180027387  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled(void)
0x18002738c  test    al, al
0x18002738e  jz      short loc_1800273E3
0x180027390  mov     [rbp+var_18], 0
0x180027398  lea     rdx, [rsi+0E8h]
0x18002739f  lea     rcx, [rbp+var_18]
0x1800273a3  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800273a8  mov     bl, [rsi+114h]
0x1800273ae  lea     rcx, [rbp+var_18]
0x1800273b2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800273b7  test    bl, bl
0x1800273b9  jz      short loc_1800273E3
0x1800273bb  cmp     r14d, 80010106h
0x1800273c2  jz      short loc_1800273CA
0x1800273c4  call    cs:__imp_CoUninitialize
0x1800273ca  mov     rcx, [rbp+var_10]
0x1800273ce  xor     rcx, rsp; StackCookie
0x1800273d1  call    __security_check_cookie
0x1800273d6  add     rsp, 68h
0x1800273da  pop     r15
0x1800273dc  pop     r14
0x1800273de  pop     rdi
0x1800273df  pop     rsi
0x1800273e0  pop     rbx
0x1800273e1  pop     rbp
0x1800273e2  retn
0x1800273e3  and     r15d, 8
0x1800273e7  setnz   bl
0x1800273ea  mov     cl, bl
0x1800273ec  xchg    cl, [rsi+0D0h]
0x1800273f2  cmp     bl, cl
0x1800273f4  jz      short loc_1800273BB
0x1800273f6  mov     eax, cs:dword_18005F140
0x1800273fc  mov     edi, 800h
0x180027401  cmp     eax, 5
0x180027404  jbe     short loc_18002744A
0x180027406  mov     [rbp+var_28], rdi
0x18002740a  movzx   eax, cl
0x18002740d  mov     [rbp+var_20], eax
0x180027410  movzx   eax, bl
0x180027413  mov     [rbp+var_1C], eax
0x180027416  mov     dword ptr [rbp+var_18], r14d
0x18002741a  lea     rax, [rbp+var_28]
0x18002741e  mov     [rsp+68h+var_30], rax
0x180027423  lea     rax, [rbp+var_20]
0x180027427  mov     [rsp+68h+var_38], rax
0x18002742c  lea     rax, [rbp+var_1C]
0x180027430  mov     [rsp+68h+var_40], rax
0x180027435  lea     rax, [rbp+var_18]
0x180027439  mov     [rsp+68h+var_48], rax
0x18002743e  lea     rdx, word_180055C86
0x180027445  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18002744a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::GetImpl(void)'::`2'::impl
0x180027451  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_SubscribeDuringFinalRelease>::__private_IsEnabled(void)
0x180027456  test    al, al
0x180027458  jz      loc_1800274F4
0x18002745e  mov     rcx, rsi; this
0x180027461  call    ?RetryStartPrivateNlm@PublicNetworkListManager@@AEAAJXZ; PublicNetworkListManager::RetryStartPrivateNlm(void)
0x180027466  test    eax, eax
0x180027468  mov     eax, cs:dword_18005F140
0x18002746e  js      short loc_1800274A0
0x180027470  cmp     eax, 5
0x180027473  jbe     loc_1800273BB
0x180027479  mov     rdx, 400000000000h
0x180027483  lea     rcx, dword_18005F140
0x18002748a  call    _tlgKeywordOn
0x18002748f  test    al, al
0x180027491  jz      loc_1800273BB
0x180027497  lea     rdx, byte_180055FC5
0x18002749e  jmp     short loc_1800274CE
0x1800274a0  cmp     eax, 5
0x1800274a3  jbe     loc_1800273BB
0x1800274a9  mov     rdx, 400000000000h
0x1800274b3  lea     rcx, dword_18005F140
0x1800274ba  call    _tlgKeywordOn
0x1800274bf  test    al, al
0x1800274c1  jz      loc_1800273BB
0x1800274c7  lea     rdx, byte_180055D19
0x1800274ce  movzx   eax, bl
0x1800274d1  mov     dword ptr [rbp+var_18], eax
0x1800274d4  lea     rax, [rbp+var_28]
0x1800274d8  mov     [rsp+68h+var_40], rax
0x1800274dd  lea     rax, [rbp+var_18]
0x1800274e1  mov     [rsp+68h+var_48], rax
0x1800274e6  mov     [rbp+var_28], rdi
0x1800274ea  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800274ef  jmp     loc_1800273BB
0x1800274f4  test    r15d, r15d
0x1800274f7  jz      short loc_180027554
0x1800274f9  mov     rcx, rsi; this
0x1800274fc  call    ?RetryStartPrivateNlm@PublicNetworkListManager@@AEAAJXZ; PublicNetworkListManager::RetryStartPrivateNlm(void)
0x180027501  test    eax, eax
0x180027503  jns     loc_1800273BB
0x180027509  mov     eax, cs:dword_18005F140
0x18002750f  cmp     eax, 5
0x180027512  jbe     loc_1800273BB
0x180027518  mov     rdx, 400000000000h
0x180027522  lea     rcx, dword_18005F140
0x180027529  call    _tlgKeywordOn
0x18002752e  test    al, al
0x180027530  jz      loc_1800273BB
0x180027536  mov     [rbp+var_28], rdi
0x18002753a  lea     rax, [rbp+var_28]
0x18002753e  mov     [rsp+68h+var_48], rax
0x180027543  lea     rdx, unk_180055E88
0x18002754a  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18002754f  jmp     loc_1800273BB
0x180027554  lea     r15, [rsi+0E8h]
0x18002755b  mov     rcx, r15; lpCriticalSection
0x18002755e  call    cs:__imp_EnterCriticalSection
0x180027564  mov     edx, [rsi+110h]
0x18002756a  or      ebx, 0FFFFFFFFh
0x18002756d  cmp     edx, ebx
0x18002756f  jz      short loc_18002758A
0x180027571  mov     rcx, [rsi+0E0h]
0x180027578  mov     rax, [rcx]
0x18002757b  mov     rax, [rax+20h]
0x18002757f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027584  mov     [rsi+110h], ebx
0x18002758a  mov     [rbp+var_18], 0
0x180027592  lea     rdx, [rbp+var_18]; struct INetworkListManagerPrivate **
0x180027596  mov     rcx, rsi; this
0x180027599  call    ?GetPrivateNetworkListManager@PublicNetworkListManager@@QEAAJPEAPEAUINetworkListManagerPrivate@@@Z; PublicNetworkListManager::GetPrivateNetworkListManager(INetworkListManagerPrivate * *)
0x18002759e  mov     ebx, eax
0x1800275a0  mov     rcx, r15; lpCriticalSection
0x1800275a3  call    cs:__imp_LeaveCriticalSection
0x1800275a9  mov     eax, cs:dword_18005F140
0x1800275af  test    ebx, ebx
0x1800275b1  js      short loc_1800275DB
0x1800275b3  cmp     eax, 5
0x1800275b6  jbe     short loc_180027614
0x1800275b8  mov     rdx, 400000000000h
0x1800275c2  lea     rcx, dword_18005F140
0x1800275c9  call    _tlgKeywordOn
0x1800275ce  test    al, al
0x1800275d0  jz      short loc_180027614
0x1800275d2  lea     rdx, byte_180055DE3
0x1800275d9  jmp     short loc_180027601
0x1800275db  cmp     eax, 5
0x1800275de  jbe     short loc_180027614
0x1800275e0  mov     rdx, 400000000000h
0x1800275ea  lea     rcx, dword_18005F140
0x1800275f1  call    _tlgKeywordOn
0x1800275f6  test    al, al
0x1800275f8  jz      short loc_180027614
0x1800275fa  lea     rdx, byte_180055EE3
0x180027601  lea     rax, [rbp+var_28]
0x180027605  mov     [rsp+68h+var_48], rax
0x18002760a  mov     [rbp+var_28], rdi
0x18002760e  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180027613  nop
0x180027614  lea     rcx, [rbp+var_18]
0x180027618  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002761d  jmp     loc_1800273BB
```
