# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180018cf4`
- end: `0x180018e46`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `338`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180083d40`

## callees

- `0x180018cf4`
- `0x180021270`
- `0x1800212f4`
- `0x180033d60`
- `0x180036f60`
- `0x180074dd4`
- `0x180075abc`
- `0x180076044`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018dab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018e09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018dab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018e09`

## string_xrefs

- `0x180018dc9`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
  __int64 v9; // rdi
  __int64 (*NtDllProcedureAddress)(void); // rax
  wil::details *v11; // rcx
  struct _TP_TIMER *v12; // rcx
  struct _TP_TIMER *v13; // rcx
  void *v14; // rcx
  char v15; // [rsp+30h] [rbp+8h] BYREF

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
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
  v9 = *((_QWORD *)this + 18);
  if ( v9 )
  {
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))NtDllProcedureAddress)(v9);
    }
  }
  v11 = (wil::details *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
    wil::details::FreeProcessHeap(v11, v8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v12 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v12);
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v13 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v13);
  v14 = (void *)*((_QWORD *)this + 2);
  if ( v14 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v14);
}

```

## disassembly

```asm
0x180018cf4  mov     [rsp+arg_8], rbx
0x180018cf9  push    rdi
0x180018cfa  sub     rsp, 20h
0x180018cfe  mov     rbx, rcx
0x180018d01  mov     byte ptr [rcx], 0
0x180018d04  mov     rdi, [rcx+30h]
0x180018d08  test    rdi, rdi
0x180018d0b  jz      short loc_180018D29
0x180018d0d  lea     rcx, [rsp+28h+arg_0]; this
0x180018d12  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018d17  mov     rcx, rdi; pti
0x180018d1a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180018d1f  lea     rcx, [rsp+28h+arg_0]; this
0x180018d24  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018d29  mov     qword ptr [rbx+30h], 0
0x180018d31  mov     rdi, [rbx+38h]
0x180018d35  test    rdi, rdi
0x180018d38  jz      short loc_180018D56
0x180018d3a  lea     rcx, [rsp+28h+arg_0]; this
0x180018d3f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018d44  mov     rcx, rdi; pti
0x180018d47  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180018d4c  lea     rcx, [rsp+28h+arg_0]; this
0x180018d51  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018d56  mov     qword ptr [rbx+38h], 0
0x180018d5e  mov     rcx, [rbx+100h]; this
0x180018d65  mov     qword ptr [rbx+100h], 0
0x180018d70  test    rcx, rcx
0x180018d73  jz      short loc_180018D7A
0x180018d75  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180018d7a  mov     rcx, [rbx+0E0h]; this
0x180018d81  test    rcx, rcx
0x180018d84  jz      short loc_180018D8B
0x180018d86  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180018d8b  lea     rdi, [rbx+98h]
0x180018d92  mov     rcx, [rdi+40h]; this
0x180018d96  mov     qword ptr [rdi+40h], 0
0x180018d9e  test    rcx, rcx
0x180018da1  jz      short loc_180018DA8
0x180018da3  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180018da8  mov     rcx, rdi; lpCriticalSection
0x180018dab  call    cs:__imp_DeleteCriticalSection
0x180018db1  mov     rdi, [rbx+90h]
0x180018db8  test    rdi, rdi
0x180018dbb  jz      short loc_180018DE9
0x180018dbd  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180018dc4  test    rax, rax
0x180018dc7  jnz     short loc_180018DE1
0x180018dc9  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180018dd0  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180018dd5  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180018ddc  test    rax, rax
0x180018ddf  jz      short loc_180018DE9
0x180018de1  mov     rcx, rdi
0x180018de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018de9  mov     rcx, [rbx+88h]; this
0x180018df0  mov     qword ptr [rbx+88h], 0
0x180018dfb  test    rcx, rcx
0x180018dfe  jz      short loc_180018E05
0x180018e00  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180018e05  lea     rcx, [rbx+48h]; lpCriticalSection
0x180018e09  call    cs:__imp_DeleteCriticalSection
0x180018e0f  mov     rcx, [rbx+38h]; pti
0x180018e13  test    rcx, rcx
0x180018e16  jz      short loc_180018E1D
0x180018e18  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180018e1d  mov     rcx, [rbx+30h]; pti
0x180018e21  test    rcx, rcx
0x180018e24  jz      short loc_180018E2C
0x180018e26  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180018e2b  nop
0x180018e2c  mov     rcx, [rbx+10h]; lpMem
0x180018e30  test    rcx, rcx
0x180018e33  jz      short loc_180018E3B
0x180018e35  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180018e3a  nop
0x180018e3b  mov     rbx, [rsp+28h+arg_8]
0x180018e40  add     rsp, 20h
0x180018e44  pop     rdi
0x180018e45  retn
```
