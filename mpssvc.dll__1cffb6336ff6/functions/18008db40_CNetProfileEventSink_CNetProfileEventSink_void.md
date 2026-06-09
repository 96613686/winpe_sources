# CNetProfileEventSink::CNetProfileEventSink(void)

- ea: `0x18008db40`
- end: `0x18008dcb5`
- name: `??0CNetProfileEventSink@@QEAA@XZ`
- size: `373`
- prototype: `CNetProfileEventSink *__fastcall(CNetProfileEventSink *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180090ff0`

## callees

- `0x18000af3c`
- `0x1800680d0`
- `0x18008db40`
- `0x18008fb24`
- `0x18008fc50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008dbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008dc1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008dbbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008dc1a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18008db65`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18008db65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008dbae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008dbae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18008dc8e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18008dc8e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18008dc0b`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18008dc0b`

## pseudocode

```c
CNetProfileEventSink *__fastcall CNetProfileEventSink::CNetProfileEventSink(CNetProfileEventSink *this)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  signed int v8; // eax
  PTP_TIMER ThreadpoolTimer; // rax

  *(_QWORD *)this = &CNetProfileEventSink::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 1, 0, 0);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 4) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v6 = 101;
LABEL_13:
    WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, (unsigned int)v4);
LABEL_14:
    *((_DWORD *)this + 3) = v4;
    if ( v4 < 0 )
      CNetProfileEventSink::Shutdown(this);
    return this;
  }
  v7 = RegisterWaitForSingleObjectEx(EventW, FwDynDataConnectivityUpdate, 0, 0xFFFFFFFFLL, 0);
  *((_QWORD *)this + 3) = v7;
  if ( !v7 )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_14;
    v6 = 102;
    goto LABEL_13;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl'::`2'::impl) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(lambda_e1b127cf6690f9e0535032c48ea1ca74_::_lambda_invoker_cdecl_, this, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      (char *)this + 80,
      ThreadpoolTimer);
  }
  *((_DWORD *)this + 3) = 0;
  return this;
}

```

## disassembly

```asm
0x18008db40  mov     [rsp+arg_8], rbx
0x18008db45  mov     [rsp+arg_0], rcx
0x18008db4a  push    rdi
0x18008db4b  sub     rsp, 30h
0x18008db4f  mov     rdi, rcx
0x18008db52  lea     rax, ??_7CNetProfileEventSink@@6B@; const CNetProfileEventSink::`vftable'
0x18008db59  mov     [rcx], rax
0x18008db5c  add     rcx, 28h ; '('; lpCriticalSection
0x18008db60  xor     r8d, r8d; Flags
0x18008db63  xor     edx, edx; dwSpinCount
0x18008db65  call    cs:__imp_InitializeCriticalSectionEx
0x18008db6b  nop
0x18008db6c  mov     qword ptr [rdi+50h], 0
0x18008db74  mov     qword ptr [rdi+58h], 0
0x18008db7c  mov     qword ptr [rdi+60h], 0
0x18008db84  mov     qword ptr [rdi+8], 0
0x18008db8c  mov     qword ptr [rdi+18h], 0
0x18008db94  mov     qword ptr [rdi+10h], 0
0x18008db9c  mov     qword ptr [rdi+20h], 0
0x18008dba4  xor     r9d, r9d; lpName
0x18008dba7  xor     r8d, r8d; bInitialState
0x18008dbaa  xor     edx, edx; bManualReset
0x18008dbac  xor     ecx, ecx; lpEventAttributes
0x18008dbae  call    cs:__imp_CreateEventW
0x18008dbb4  mov     [rdi+10h], rax
0x18008dbb8  test    rax, rax
0x18008dbbb  jnz     short loc_18008DBF2
0x18008dbbd  call    cs:__imp_GetLastError
0x18008dbc3  mov     ebx, eax
0x18008dbc5  test    eax, eax
0x18008dbc7  jle     short loc_18008DBD2
0x18008dbc9  movzx   ebx, ax
0x18008dbcc  or      ebx, 80070000h
0x18008dbd2  lea     rax, WPP_GLOBAL_Control
0x18008dbd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dbe0  cmp     rcx, rax
0x18008dbe3  jz      short loc_18008DC60
0x18008dbe5  test    byte ptr [rcx+1Ch], 1
0x18008dbe9  jz      short loc_18008DC60
0x18008dbeb  mov     edx, 65h ; 'e'
0x18008dbf0  jmp     short loc_18008DC4D
0x18008dbf2  mov     [rsp+38h+var_18], 0
0x18008dbfa  or      r9d, 0FFFFFFFFh
0x18008dbfe  xor     r8d, r8d
0x18008dc01  lea     rdx, FwDynDataConnectivityUpdate
0x18008dc08  mov     rcx, rax
0x18008dc0b  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18008dc11  mov     [rdi+18h], rax
0x18008dc15  test    rax, rax
0x18008dc18  jnz     short loc_18008DC71
0x18008dc1a  call    cs:__imp_GetLastError
0x18008dc20  mov     ebx, eax
0x18008dc22  test    eax, eax
0x18008dc24  jle     short loc_18008DC2F
0x18008dc26  movzx   ebx, ax
0x18008dc29  or      ebx, 80070000h
0x18008dc2f  lea     rax, WPP_GLOBAL_Control
0x18008dc36  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dc3d  cmp     rcx, rax
0x18008dc40  jz      short loc_18008DC60
0x18008dc42  test    byte ptr [rcx+1Ch], 1
0x18008dc46  jz      short loc_18008DC60
0x18008dc48  mov     edx, 66h ; 'f'
0x18008dc4d  mov     r9d, ebx
0x18008dc50  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x18008dc57  mov     rcx, [rcx+10h]
0x18008dc5b  call    WPP_SF_d
0x18008dc60  mov     [rdi+0Ch], ebx
0x18008dc63  test    ebx, ebx
0x18008dc65  jns     short loc_18008DCA7
0x18008dc67  mov     rcx, rdi; this
0x18008dc6a  call    ?Shutdown@CNetProfileEventSink@@AEAAXXZ; CNetProfileEventSink::Shutdown(void)
0x18008dc6f  jmp     short loc_18008DCA7
0x18008dc71  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x18008dc78  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x18008dc7d  test    al, al
0x18008dc7f  jz      short loc_18008DCA0
0x18008dc81  xor     r8d, r8d; pcbe
0x18008dc84  mov     rdx, rdi; pv
0x18008dc87  lea     rcx, _lambda_e1b127cf6690f9e0535032c48ea1ca74____lambda_invoker_cdecl_; pfnti
0x18008dc8e  call    cs:__imp_CreateThreadpoolTimer
0x18008dc94  mov     rdx, rax
0x18008dc97  lea     rcx, [rdi+50h]
0x18008dc9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18008dca0  mov     dword ptr [rdi+0Ch], 0
0x18008dca7  mov     rax, rdi
0x18008dcaa  mov     rbx, [rsp+38h+arg_8]
0x18008dcaf  add     rsp, 30h
0x18008dcb3  pop     rdi
0x18008dcb4  retn
```
