# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18002958c`
- end: `0x1800296b2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `294`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007bbb0`

## callees

- `0x18002958c`
- `0x1800296b8`
- `0x18002a490`
- `0x18002a514`
- `0x1800330fc`
- `0x180033564`
- `0x180038dec`
- `0x18003a3e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029643`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029675`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029643`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029675`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rdi
  struct _TP_TIMER *v4; // rdi
  wil::details *v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rcx
  wil::details *v7; // rcx
  void *v8; // rdx
  wil::details *v9; // rcx
  struct _TP_TIMER *v10; // rcx
  struct _TP_TIMER *v11; // rcx
  void *v12; // rcx
  char v13; // [rsp+30h] [rbp+8h] BYREF

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v13);
  }
  *((_QWORD *)this + 7) = 0;
  v5 = (wil::details *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v5 )
    wil::details::FreeProcessHeap(v5, a2);
  v6 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v6 )
    wil::details::UnsubscribeProcessWideUsageFlush(v6, a2);
  v7 = (wil::details *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v7 )
    wil::details::FreeProcessHeap(v7, a2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
  v9 = (wil::details *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v9 )
    wil::details::FreeProcessHeap(v9, v8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v10 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v10);
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v11 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v11);
  v12 = (void *)*((_QWORD *)this + 2);
  if ( v12 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v12);
}

```

## disassembly

```asm
0x18002958c  mov     [rsp+arg_8], rbx
0x180029591  push    rdi
0x180029592  sub     rsp, 20h
0x180029596  mov     rbx, rcx
0x180029599  mov     byte ptr [rcx], 0
0x18002959c  mov     rdi, [rcx+30h]
0x1800295a0  test    rdi, rdi
0x1800295a3  jz      short loc_1800295C1
0x1800295a5  lea     rcx, [rsp+28h+arg_0]; this
0x1800295aa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800295af  mov     rcx, rdi; pti
0x1800295b2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800295b7  lea     rcx, [rsp+28h+arg_0]; this
0x1800295bc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800295c1  mov     qword ptr [rbx+30h], 0
0x1800295c9  mov     rdi, [rbx+38h]
0x1800295cd  test    rdi, rdi
0x1800295d0  jz      short loc_1800295EE
0x1800295d2  lea     rcx, [rsp+28h+arg_0]; this
0x1800295d7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800295dc  mov     rcx, rdi; pti
0x1800295df  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800295e4  lea     rcx, [rsp+28h+arg_0]; this
0x1800295e9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800295ee  mov     qword ptr [rbx+38h], 0
0x1800295f6  mov     rcx, [rbx+100h]; this
0x1800295fd  mov     qword ptr [rbx+100h], 0
0x180029608  test    rcx, rcx
0x18002960b  jz      short loc_180029612
0x18002960d  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180029612  mov     rcx, [rbx+0E0h]; this
0x180029619  test    rcx, rcx
0x18002961c  jz      short loc_180029623
0x18002961e  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180029623  lea     rdi, [rbx+98h]
0x18002962a  mov     rcx, [rdi+40h]; this
0x18002962e  mov     qword ptr [rdi+40h], 0
0x180029636  test    rcx, rcx
0x180029639  jz      short loc_180029640
0x18002963b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180029640  mov     rcx, rdi; lpCriticalSection
0x180029643  call    cs:__imp_DeleteCriticalSection
0x180029649  lea     rcx, [rbx+90h]
0x180029650  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180029655  mov     rcx, [rbx+88h]; this
0x18002965c  mov     qword ptr [rbx+88h], 0
0x180029667  test    rcx, rcx
0x18002966a  jz      short loc_180029671
0x18002966c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180029671  lea     rcx, [rbx+48h]; lpCriticalSection
0x180029675  call    cs:__imp_DeleteCriticalSection
0x18002967b  mov     rcx, [rbx+38h]; pti
0x18002967f  test    rcx, rcx
0x180029682  jz      short loc_180029689
0x180029684  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180029689  mov     rcx, [rbx+30h]; pti
0x18002968d  test    rcx, rcx
0x180029690  jz      short loc_180029698
0x180029692  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180029697  nop
0x180029698  mov     rcx, [rbx+10h]; lpMem
0x18002969c  test    rcx, rcx
0x18002969f  jz      short loc_1800296A7
0x1800296a1  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800296a6  nop
0x1800296a7  mov     rbx, [rsp+28h+arg_8]
0x1800296ac  add     rsp, 20h
0x1800296b0  pop     rdi
0x1800296b1  retn
```
