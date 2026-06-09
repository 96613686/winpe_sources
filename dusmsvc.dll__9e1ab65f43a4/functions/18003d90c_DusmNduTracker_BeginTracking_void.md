# DusmNduTracker::BeginTracking(void)

- ea: `0x18003d90c`
- end: `0x18003da6c`
- name: `?BeginTracking@DusmNduTracker@@QEAAXXZ`
- size: `352`
- prototype: `void __fastcall(DusmNduTracker *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180019d9c`

## callees

- `0x180005a60`
- `0x180012304`
- `0x180012368`
- `0x180013444`
- `0x18001374c`
- `0x1800171a8`
- `0x18003d90c`
- `0x18003db50`
- `0x18003de20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d957`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d957`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003da16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003da16`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003d99b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003d99b`
- `NduProv!__imp_NduOpenHandle` at `0x18003d922`
- `NduProv!__imp_NduOpenHandle` at `0x18003d922`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18003d9e0`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18003d9e0`

## string_xrefs

- `0x18003d93c`: `DusmNduTracker::BeginTracking::NduOpenHandle`
- `0x18003d9b5`: `DusmNduTracker::BeginTracking::CreateThreadpoolWait`
- `0x18003d971`: `DusmNduTracker::BeginTracking::CreateEventW`

## pseudocode

```c
void __fastcall DusmNduTracker::BeginTracking(DusmNduTracker *this)
{
  unsigned int v2; // eax
  HANDLE EventW; // rax
  __int64 LastErrorIfNull; // rax
  PTP_WAIT ThreadpoolWait; // rax
  __int64 v6; // rax
  unsigned int v7; // eax
  __int64 **v8; // rdi
  __int64 *i; // rbx
  _DWORD *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  const char *v13; // [rsp+28h] [rbp-40h]
  const char *v14; // [rsp+28h] [rbp-40h]
  char *v15; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this,
    0);
  v2 = NduOpenHandle(this);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x10,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmndutracker.cpp",
    (const char *)v2,
    (unsigned int)"DusmNduTracker::BeginTracking::NduOpenHandle",
    v13);
  EventW = CreateEventW(0, 0, 0, 0);
  LastErrorIfNull = wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
                      retaddr,
                      19,
                      "onecoreuap\\net\\dusm\\lib\\dusmndutracker.cpp",
                      EventW,
                      "DusmNduTracker::BeginTracking::CreateEventW");
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 8,
    LastErrorIfNull);
  ThreadpoolWait = CreateThreadpoolWait(DusmNduTracker::NduByteLimitCallback, this, 0);
  v6 = wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
         retaddr,
         22,
         "onecoreuap\\net\\dusm\\lib\\dusmndutracker.cpp",
         ThreadpoolWait,
         "DusmNduTracker::BeginTracking::CreateThreadpoolWait");
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)this + 16,
    v6);
  v7 = ConvertInterfaceGuidToLuid((const GUID *)((char *)this + 24), (PNET_LUID)this + 16);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x19,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmndutracker.cpp",
    (const char *)v7,
    (int)"DusmNduTracker::BeginTracking::ConvertInterfaceGuidToLuid",
    v14);
  SetThreadpoolWait(*((PTP_WAIT *)this + 2), *((HANDLE *)this + 1), 0);
  v8 = (__int64 **)*((_QWORD *)this + 7);
  for ( i = *v8; i != (__int64 *)v8; i = (__int64 *)*i )
    DusmNduTracker::RegisterNotificationForProfile(this, *((_DWORD *)i + 4));
  v10 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get() + 8);
  if ( *v10 > 5u )
  {
    v15 = (char *)this + 24;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
      (_DWORD)v10,
      (unsigned int)byte_18005BCC9,
      v11,
      v12,
      (__int64)&v15);
  }
}

```

## disassembly

```asm
0x18003d90c  push    rbx
0x18003d90e  push    rbp
0x18003d90f  push    rsi
0x18003d910  push    rdi
0x18003d911  sub     rsp, 48h
0x18003d915  xor     edx, edx
0x18003d917  mov     rsi, rcx
0x18003d91a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003d91f  mov     rcx, rsi
0x18003d922  call    cs:__imp_NduOpenHandle
0x18003d928  mov     rcx, [rsp+68h]; this
0x18003d92d  lea     r8, aOnecoreuapNetD_10; "onecoreuap\\net\\dusm\\lib\\dusmndutrac"...
0x18003d934  mov     r9d, eax; char *
0x18003d937  mov     edx, 10h; void *
0x18003d93c  lea     rax, aDusmndutracker; "DusmNduTracker::BeginTracking::NduOpenH"...
0x18003d943  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18003d948  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003d94d  xor     r9d, r9d; lpName
0x18003d950  xor     r8d, r8d; bInitialState
0x18003d953  xor     edx, edx; bManualReset
0x18003d955  xor     ecx, ecx; lpEventAttributes
0x18003d957  call    cs:__imp_CreateEventW
0x18003d95d  mov     rcx, [rsp+68h]
0x18003d962  lea     r8, aOnecoreuapNetD_10; "onecoreuap\\net\\dusm\\lib\\dusmndutrac"...
0x18003d969  mov     r9, rax
0x18003d96c  mov     edx, 13h
0x18003d971  lea     rax, aDusmndutracker_0; "DusmNduTracker::BeginTracking::CreateEv"...
0x18003d978  mov     qword ptr [rsp+68h+var_48], rax
0x18003d97d  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x18003d982  mov     rdx, rax
0x18003d985  lea     rcx, [rsi+8]
0x18003d989  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003d98e  xor     r8d, r8d; pcbe
0x18003d991  lea     rcx, ?NduByteLimitCallback@DusmNduTracker@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18003d998  mov     rdx, rsi; pv
0x18003d99b  call    cs:__imp_CreateThreadpoolWait
0x18003d9a1  mov     rcx, [rsp+68h]
0x18003d9a6  lea     r8, aOnecoreuapNetD_10; "onecoreuap\\net\\dusm\\lib\\dusmndutrac"...
0x18003d9ad  mov     r9, rax
0x18003d9b0  mov     edx, 16h
0x18003d9b5  lea     rax, aDusmndutracker_2; "DusmNduTracker::BeginTracking::CreateTh"...
0x18003d9bc  mov     qword ptr [rsp+68h+var_48], rax
0x18003d9c1  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x18003d9c6  mov     rdx, rax
0x18003d9c9  lea     rcx, [rsi+10h]
0x18003d9cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18003d9d2  lea     rbp, [rsi+18h]
0x18003d9d6  mov     rcx, rbp; InterfaceGuid
0x18003d9d9  lea     rdx, [rsi+80h]; InterfaceLuid
0x18003d9e0  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18003d9e6  mov     rcx, [rsp+68h]; this
0x18003d9eb  lea     r8, aOnecoreuapNetD_10; "onecoreuap\\net\\dusm\\lib\\dusmndutrac"...
0x18003d9f2  mov     r9d, eax; char *
0x18003d9f5  mov     edx, 19h; void *
0x18003d9fa  lea     rax, aDusmndutracker_1; "DusmNduTracker::BeginTracking::ConvertI"...
0x18003da01  mov     qword ptr [rsp+68h+var_48], rax; int
0x18003da06  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003da0b  mov     rdx, [rsi+8]; h
0x18003da0f  xor     r8d, r8d; pftTimeout
0x18003da12  mov     rcx, [rsi+10h]; pwa
0x18003da16  call    cs:__imp_SetThreadpoolWait
0x18003da1c  mov     rdi, [rsi+38h]
0x18003da20  mov     rbx, [rdi]
0x18003da23  cmp     rbx, rdi
0x18003da26  jz      short loc_18003DA38
0x18003da28  mov     edx, [rbx+10h]; unsigned int
0x18003da2b  mov     rcx, rsi; this
0x18003da2e  call    ?RegisterNotificationForProfile@DusmNduTracker@@AEAAXK@Z; DusmNduTracker::RegisterNotificationForProfile(ulong)
0x18003da33  mov     rbx, [rbx]
0x18003da36  jmp     short loc_18003DA23
0x18003da38  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003da3d  mov     rcx, [rax+8]
0x18003da41  mov     eax, [rcx]
0x18003da43  cmp     eax, 5
0x18003da46  jbe     short loc_18003DA63
0x18003da48  lea     rax, [rsp+68h+var_38]
0x18003da4d  mov     [rsp+68h+var_38], rbp
0x18003da52  lea     rdx, byte_18005BCC9
0x18003da59  mov     qword ptr [rsp+68h+var_48], rax
0x18003da5e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18003da63  add     rsp, 48h
0x18003da67  pop     rdi
0x18003da68  pop     rsi
0x18003da69  pop     rbp
0x18003da6a  pop     rbx
0x18003da6b  retn
```
