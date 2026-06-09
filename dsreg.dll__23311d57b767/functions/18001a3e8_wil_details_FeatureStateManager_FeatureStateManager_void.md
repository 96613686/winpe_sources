# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18001a3e8`
- end: `0x18001a574`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `396`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001a390`

## callees

- `0x180018d58`
- `0x18001a3e8`
- `0x18001a57c`
- `0x18001a5c4`
- `0x18001a600`
- `0x18001e858`
- `0x1800426ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a4f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a522`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a4f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a522`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a46c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a49d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a46c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a49d`

## pseudocode

```c
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
  DWORD dwErrCode; // [rsp+34h] [rbp+Ch]

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
    if ( !v13 )
      SetLastError(dwErrCode);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v13);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    if ( !v13 )
      SetLastError(dwErrCode);
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
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
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
0x18001a3e8  mov     [rsp+arg_8], rbx
0x18001a3ed  push    rdi
0x18001a3ee  sub     rsp, 20h
0x18001a3f2  mov     rbx, rcx
0x18001a3f5  mov     byte ptr [rcx], 0
0x18001a3f8  mov     rdi, [rcx+30h]
0x18001a3fc  test    rdi, rdi
0x18001a3ff  jnz     loc_18001A4D5
0x18001a405  mov     qword ptr [rbx+30h], 0
0x18001a40d  mov     rdi, [rbx+38h]
0x18001a411  test    rdi, rdi
0x18001a414  jnz     loc_18001A501
0x18001a41a  mov     qword ptr [rbx+38h], 0
0x18001a422  mov     rcx, [rbx+100h]; this
0x18001a429  mov     qword ptr [rbx+100h], 0
0x18001a434  test    rcx, rcx
0x18001a437  jnz     loc_18001A52D
0x18001a43d  mov     rcx, [rbx+0E0h]; this
0x18001a444  test    rcx, rcx
0x18001a447  jnz     loc_18001A537
0x18001a44d  lea     rdi, [rbx+98h]
0x18001a454  mov     rcx, [rdi+40h]; this
0x18001a458  mov     qword ptr [rdi+40h], 0
0x18001a460  test    rcx, rcx
0x18001a463  jnz     loc_18001A541
0x18001a469  mov     rcx, rdi; lpCriticalSection
0x18001a46c  call    cs:__imp_DeleteCriticalSection
0x18001a472  lea     rcx, [rbx+90h]
0x18001a479  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001a47e  mov     rcx, [rbx+88h]; this
0x18001a485  mov     qword ptr [rbx+88h], 0
0x18001a490  test    rcx, rcx
0x18001a493  jnz     loc_18001A54B
0x18001a499  lea     rcx, [rbx+48h]; lpCriticalSection
0x18001a49d  call    cs:__imp_DeleteCriticalSection
0x18001a4a3  mov     rcx, [rbx+38h]; pti
0x18001a4a7  test    rcx, rcx
0x18001a4aa  jnz     loc_18001A555
0x18001a4b0  mov     rcx, [rbx+30h]; pti
0x18001a4b4  test    rcx, rcx
0x18001a4b7  jnz     loc_18001A55F
0x18001a4bd  mov     rcx, [rbx+10h]; lpMem
0x18001a4c1  test    rcx, rcx
0x18001a4c4  jnz     loc_18001A569
0x18001a4ca  mov     rbx, [rsp+28h+arg_8]
0x18001a4cf  add     rsp, 20h
0x18001a4d3  pop     rdi
0x18001a4d4  retn
0x18001a4d5  lea     rcx, [rsp+28h+arg_0]; this
0x18001a4da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a4df  mov     rcx, rdi; pti
0x18001a4e2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001a4e7  cmp     [rsp+28h+arg_0], 0
0x18001a4ec  jnz     loc_18001A405
0x18001a4f2  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x18001a4f6  call    cs:__imp_SetLastError
0x18001a4fc  jmp     loc_18001A405
0x18001a501  lea     rcx, [rsp+28h+arg_0]; this
0x18001a506  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001a50b  mov     rcx, rdi; pti
0x18001a50e  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001a513  cmp     [rsp+28h+arg_0], 0
0x18001a518  jnz     loc_18001A41A
0x18001a51e  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x18001a522  call    cs:__imp_SetLastError
0x18001a528  jmp     loc_18001A41A
0x18001a52d  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001a532  jmp     loc_18001A43D
0x18001a537  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18001a53c  jmp     loc_18001A44D
0x18001a541  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001a546  jmp     loc_18001A469
0x18001a54b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001a550  jmp     loc_18001A499
0x18001a555  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001a55a  jmp     loc_18001A4B0
0x18001a55f  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18001a564  jmp     loc_18001A4BD
0x18001a569  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18001a56e  jmp     loc_18001A4CA
```
