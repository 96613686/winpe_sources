# CNetProfileEventSink::CNetProfileEventSink(void)

- ea: `0x180092424`
- end: `0x1800925c6`
- name: `??0CNetProfileEventSink@@QEAA@XZ`
- size: `418`
- prototype: `CNetProfileEventSink *__fastcall(CNetProfileEventSink *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180095b40`

## callees

- `0x18000a710`
- `0x18006ba5c`
- `0x180092424`
- `0x1800944c4`
- `0x180094610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800924ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009251e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800924ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009251e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180092498`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180092498`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180092449`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180092449`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180092598`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180092598`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180092509`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180092509`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, (unsigned int)v4);
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
0x180092424  mov     [rsp+arg_8], rbx
0x180092429  mov     [rsp+arg_0], rcx
0x18009242e  push    rdi
0x18009242f  sub     rsp, 30h
0x180092433  mov     rdi, rcx
0x180092436  lea     rax, ??_7CNetProfileEventSink@@6B@; const CNetProfileEventSink::`vftable'
0x18009243d  mov     [rcx], rax
0x180092440  add     rcx, 28h ; '('; lpCriticalSection
0x180092444  xor     r8d, r8d; Flags
0x180092447  xor     edx, edx; dwSpinCount
0x180092449  call    cs:__imp_InitializeCriticalSectionEx
0x180092450  nop     dword ptr [rax+rax+00h]
0x180092455  nop
0x180092456  mov     qword ptr [rdi+50h], 0
0x18009245e  mov     qword ptr [rdi+58h], 0
0x180092466  mov     qword ptr [rdi+60h], 0
0x18009246e  mov     qword ptr [rdi+8], 0
0x180092476  mov     qword ptr [rdi+18h], 0
0x18009247e  mov     qword ptr [rdi+10h], 0
0x180092486  mov     qword ptr [rdi+20h], 0
0x18009248e  xor     r9d, r9d; lpName
0x180092491  xor     r8d, r8d; bInitialState
0x180092494  xor     edx, edx; bManualReset
0x180092496  xor     ecx, ecx; lpEventAttributes
0x180092498  call    cs:__imp_CreateEventW
0x18009249f  nop     dword ptr [rax+rax+00h]
0x1800924a4  mov     [rdi+10h], rax
0x1800924a8  test    rax, rax
0x1800924ab  jnz     short loc_1800924F0
0x1800924ad  call    cs:__imp_GetLastError
0x1800924b4  nop     dword ptr [rax+rax+00h]
0x1800924b9  mov     ebx, eax
0x1800924bb  test    eax, eax
0x1800924bd  jle     short loc_1800924C8
0x1800924bf  movzx   ebx, ax
0x1800924c2  or      ebx, 80070000h
0x1800924c8  lea     rax, WPP_GLOBAL_Control
0x1800924cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800924d6  cmp     rcx, rax
0x1800924d9  jz      loc_18009256A
0x1800924df  test    byte ptr [rcx+1Ch], 1
0x1800924e3  jz      loc_18009256A
0x1800924e9  mov     edx, 65h ; 'e'
0x1800924ee  jmp     short loc_180092557
0x1800924f0  mov     [rsp+38h+var_18], 0
0x1800924f8  or      r9d, 0FFFFFFFFh
0x1800924fc  xor     r8d, r8d
0x1800924ff  lea     rdx, FwDynDataConnectivityUpdate
0x180092506  mov     rcx, rax
0x180092509  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180092510  nop     dword ptr [rax+rax+00h]
0x180092515  mov     [rdi+18h], rax
0x180092519  test    rax, rax
0x18009251c  jnz     short loc_18009257B
0x18009251e  call    cs:__imp_GetLastError
0x180092525  nop     dword ptr [rax+rax+00h]
0x18009252a  mov     ebx, eax
0x18009252c  test    eax, eax
0x18009252e  jle     short loc_180092539
0x180092530  movzx   ebx, ax
0x180092533  or      ebx, 80070000h
0x180092539  lea     rax, WPP_GLOBAL_Control
0x180092540  mov     rcx, cs:WPP_GLOBAL_Control
0x180092547  cmp     rcx, rax
0x18009254a  jz      short loc_18009256A
0x18009254c  test    byte ptr [rcx+1Ch], 1
0x180092550  jz      short loc_18009256A
0x180092552  mov     edx, 66h ; 'f'
0x180092557  mov     r9d, ebx
0x18009255a  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x180092561  mov     rcx, [rcx+10h]
0x180092565  call    WPP_SF_d
0x18009256a  mov     [rdi+0Ch], ebx
0x18009256d  test    ebx, ebx
0x18009256f  jns     short loc_1800925B7
0x180092571  mov     rcx, rdi; this
0x180092574  call    ?Shutdown@CNetProfileEventSink@@AEAAXXZ; CNetProfileEventSink::Shutdown(void)
0x180092579  jmp     short loc_1800925B7
0x18009257b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall> `wil::Feature<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::GetImpl(void)'::`2'::impl
0x180092582  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_NLM_Updates_In_Firewall>::__private_IsEnabled(void)
0x180092587  test    al, al
0x180092589  jz      short loc_1800925B0
0x18009258b  xor     r8d, r8d; pcbe
0x18009258e  mov     rdx, rdi; pv
0x180092591  lea     rcx, _lambda_e1b127cf6690f9e0535032c48ea1ca74____lambda_invoker_cdecl_; pfnti
0x180092598  call    cs:__imp_CreateThreadpoolTimer
0x18009259f  nop     dword ptr [rax+rax+00h]
0x1800925a4  mov     rdx, rax
0x1800925a7  lea     rcx, [rdi+50h]
0x1800925ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800925b0  mov     dword ptr [rdi+0Ch], 0
0x1800925b7  mov     rax, rdi
0x1800925ba  mov     rbx, [rsp+38h+arg_8]
0x1800925bf  add     rsp, 30h
0x1800925c3  pop     rdi
0x1800925c4  retn
```
