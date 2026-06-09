# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18002ba08`
- end: `0x18002bb3b`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `307`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180081090`

## callees

- `0x18002ba08`
- `0x18002bb44`
- `0x18002c88c`
- `0x18002c91c`
- `0x180035a5c`
- `0x180035ec4`
- `0x18003bac4`
- `0x18003d1a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002babf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002baf7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002babf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002baf7`

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
0x18002ba08  mov     [rsp+arg_8], rbx
0x18002ba0d  push    rdi
0x18002ba0e  sub     rsp, 20h
0x18002ba12  mov     rbx, rcx
0x18002ba15  mov     byte ptr [rcx], 0
0x18002ba18  mov     rdi, [rcx+30h]
0x18002ba1c  test    rdi, rdi
0x18002ba1f  jz      short loc_18002BA3D
0x18002ba21  lea     rcx, [rsp+28h+arg_0]; this
0x18002ba26  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002ba2b  mov     rcx, rdi; pti
0x18002ba2e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002ba33  lea     rcx, [rsp+28h+arg_0]; this
0x18002ba38  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002ba3d  mov     qword ptr [rbx+30h], 0
0x18002ba45  mov     rdi, [rbx+38h]
0x18002ba49  test    rdi, rdi
0x18002ba4c  jz      short loc_18002BA6A
0x18002ba4e  lea     rcx, [rsp+28h+arg_0]; this
0x18002ba53  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002ba58  mov     rcx, rdi; pti
0x18002ba5b  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002ba60  lea     rcx, [rsp+28h+arg_0]; this
0x18002ba65  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002ba6a  mov     qword ptr [rbx+38h], 0
0x18002ba72  mov     rcx, [rbx+100h]; this
0x18002ba79  mov     qword ptr [rbx+100h], 0
0x18002ba84  test    rcx, rcx
0x18002ba87  jz      short loc_18002BA8E
0x18002ba89  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002ba8e  mov     rcx, [rbx+0E0h]; this
0x18002ba95  test    rcx, rcx
0x18002ba98  jz      short loc_18002BA9F
0x18002ba9a  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18002ba9f  lea     rdi, [rbx+98h]
0x18002baa6  mov     rcx, [rdi+40h]; this
0x18002baaa  mov     qword ptr [rdi+40h], 0
0x18002bab2  test    rcx, rcx
0x18002bab5  jz      short loc_18002BABC
0x18002bab7  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002babc  mov     rcx, rdi; lpCriticalSection
0x18002babf  call    cs:__imp_DeleteCriticalSection
0x18002bac6  nop     dword ptr [rax+rax+00h]
0x18002bacb  lea     rcx, [rbx+90h]
0x18002bad2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002bad7  mov     rcx, [rbx+88h]; this
0x18002bade  mov     qword ptr [rbx+88h], 0
0x18002bae9  test    rcx, rcx
0x18002baec  jz      short loc_18002BAF3
0x18002baee  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002baf3  lea     rcx, [rbx+48h]; lpCriticalSection
0x18002baf7  call    cs:__imp_DeleteCriticalSection
0x18002bafe  nop     dword ptr [rax+rax+00h]
0x18002bb03  mov     rcx, [rbx+38h]; pti
0x18002bb07  test    rcx, rcx
0x18002bb0a  jz      short loc_18002BB11
0x18002bb0c  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002bb11  mov     rcx, [rbx+30h]; pti
0x18002bb15  test    rcx, rcx
0x18002bb18  jz      short loc_18002BB20
0x18002bb1a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18002bb1f  nop
0x18002bb20  mov     rcx, [rbx+10h]; lpMem
0x18002bb24  test    rcx, rcx
0x18002bb27  jz      short loc_18002BB2F
0x18002bb29  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18002bb2e  nop
0x18002bb2f  mov     rbx, [rsp+28h+arg_8]
0x18002bb34  add     rsp, 20h
0x18002bb38  pop     rdi
0x18002bb39  retn
```
