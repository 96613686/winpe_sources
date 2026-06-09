# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000538c`
- end: `0x14000557a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140010710`

## callees

- `0x1400050d0`
- `0x14000538c`
- `0x14000a2a0`
- `0x14000c71c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000544a`
- `KERNEL32!GetProcessHeap` at `0x14000549a`
- `KERNEL32!GetProcessHeap` at `0x1400054da`
- `KERNEL32!GetProcessHeap` at `0x14000544a`
- `KERNEL32!GetProcessHeap` at `0x14000549a`
- `KERNEL32!GetProcessHeap` at `0x1400054da`
- `KERNEL32!HeapFree` at `0x140005458`
- `KERNEL32!HeapFree` at `0x1400054a8`
- `KERNEL32!HeapFree` at `0x1400054e8`
- `KERNEL32!HeapFree` at `0x140005458`
- `KERNEL32!HeapFree` at `0x1400054a8`
- `KERNEL32!HeapFree` at `0x1400054e8`
- `KERNEL32!SetLastError` at `0x1400053dc`
- `KERNEL32!SetLastError` at `0x140005425`
- `KERNEL32!SetLastError` at `0x1400053dc`
- `KERNEL32!SetLastError` at `0x140005425`
- `KERNEL32!SetThreadpoolTimer` at `0x1400053bd`
- `KERNEL32!SetThreadpoolTimer` at `0x140005406`
- `KERNEL32!SetThreadpoolTimer` at `0x14000550c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000553d`
- `KERNEL32!SetThreadpoolTimer` at `0x1400053bd`
- `KERNEL32!SetThreadpoolTimer` at `0x140005406`
- `KERNEL32!SetThreadpoolTimer` at `0x14000550c`
- `KERNEL32!SetThreadpoolTimer` at `0x14000553d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400053cb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005414`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000551a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000554b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400053cb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005414`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000551a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000554b`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400053d4`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000541d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005523`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005554`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400053d4`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000541d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005523`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005554`
- `KERNEL32!DeleteCriticalSection` at `0x1400054b1`
- `KERNEL32!DeleteCriticalSection` at `0x1400054f2`
- `KERNEL32!DeleteCriticalSection` at `0x1400054b1`
- `KERNEL32!DeleteCriticalSection` at `0x1400054f2`
- `KERNEL32!GetLastError` at `0x1400053aa`
- `KERNEL32!GetLastError` at `0x1400053f3`
- `KERNEL32!GetLastError` at `0x1400053aa`
- `KERNEL32!GetLastError` at `0x1400053f3`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // r8
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rsi
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx
  void *v15; // rcx

  *(_BYTE *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v5);
  }
  *((_QWORD *)this + 7) = 0;
  v6 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v8 && qword_1400180B0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400180B0[25], qword_1400180B0, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v11 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (void *)*((_QWORD *)this + 2);
  if ( v15 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x14000538c  mov     [rsp+arg_0], rbx
0x140005391  mov     [rsp+arg_8], rsi
0x140005396  push    rdi
0x140005397  sub     rsp, 20h
0x14000539b  mov     rdi, rcx
0x14000539e  mov     byte ptr [rcx], 0
0x1400053a1  mov     rsi, [rcx+30h]
0x1400053a5  test    rsi, rsi
0x1400053a8  jz      short loc_1400053E2
0x1400053aa  call    cs:__imp_GetLastError
0x1400053b0  mov     ebx, eax
0x1400053b2  xor     r9d, r9d; msWindowLength
0x1400053b5  xor     r8d, r8d; msPeriod
0x1400053b8  xor     edx, edx; pftDueTime
0x1400053ba  mov     rcx, rsi; pti
0x1400053bd  call    cs:__imp_SetThreadpoolTimer
0x1400053c3  mov     edx, 1; fCancelPendingCallbacks
0x1400053c8  mov     rcx, rsi; pti
0x1400053cb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400053d1  mov     rcx, rsi; pti
0x1400053d4  call    cs:__imp_CloseThreadpoolTimer
0x1400053da  mov     ecx, ebx; dwErrCode
0x1400053dc  call    cs:__imp_SetLastError
0x1400053e2  mov     qword ptr [rdi+30h], 0
0x1400053ea  mov     rsi, [rdi+38h]
0x1400053ee  test    rsi, rsi
0x1400053f1  jz      short loc_14000542B
0x1400053f3  call    cs:__imp_GetLastError
0x1400053f9  mov     ebx, eax
0x1400053fb  xor     r9d, r9d; msWindowLength
0x1400053fe  xor     r8d, r8d; msPeriod
0x140005401  xor     edx, edx; pftDueTime
0x140005403  mov     rcx, rsi; pti
0x140005406  call    cs:__imp_SetThreadpoolTimer
0x14000540c  mov     edx, 1; fCancelPendingCallbacks
0x140005411  mov     rcx, rsi; pti
0x140005414  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000541a  mov     rcx, rsi; pti
0x14000541d  call    cs:__imp_CloseThreadpoolTimer
0x140005423  mov     ecx, ebx; dwErrCode
0x140005425  call    cs:__imp_SetLastError
0x14000542b  mov     qword ptr [rdi+38h], 0
0x140005433  mov     rbx, [rdi+100h]
0x14000543a  mov     qword ptr [rdi+100h], 0
0x140005445  test    rbx, rbx
0x140005448  jz      short loc_14000545E
0x14000544a  call    cs:__imp_GetProcessHeap
0x140005450  mov     rcx, rax; hHeap
0x140005453  mov     r8, rbx; lpMem
0x140005456  xor     edx, edx; dwFlags
0x140005458  call    cs:__imp_HeapFree
0x14000545e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140005465  test    r8, r8
0x140005468  jz      short loc_140005482
0x14000546a  mov     rdx, cs:qword_1400180B0; SRWLock
0x140005471  test    rdx, rdx
0x140005474  jz      short loc_140005482
0x140005476  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000547d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140005482  lea     rbx, [rdi+98h]
0x140005489  mov     rsi, [rbx+40h]
0x14000548d  mov     qword ptr [rbx+40h], 0
0x140005495  test    rsi, rsi
0x140005498  jz      short loc_1400054AE
0x14000549a  call    cs:__imp_GetProcessHeap
0x1400054a0  mov     rcx, rax; hHeap
0x1400054a3  mov     r8, rsi; lpMem
0x1400054a6  xor     edx, edx; dwFlags
0x1400054a8  call    cs:__imp_HeapFree
0x1400054ae  mov     rcx, rbx; lpCriticalSection
0x1400054b1  call    cs:__imp_DeleteCriticalSection
0x1400054b7  lea     rcx, [rdi+90h]
0x1400054be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400054c3  mov     rsi, [rdi+88h]
0x1400054ca  mov     qword ptr [rdi+88h], 0
0x1400054d5  test    rsi, rsi
0x1400054d8  jz      short loc_1400054EE
0x1400054da  call    cs:__imp_GetProcessHeap
0x1400054e0  mov     rcx, rax; hHeap
0x1400054e3  mov     r8, rsi; lpMem
0x1400054e6  xor     edx, edx; dwFlags
0x1400054e8  call    cs:__imp_HeapFree
0x1400054ee  lea     rcx, [rdi+48h]; lpCriticalSection
0x1400054f2  call    cs:__imp_DeleteCriticalSection
0x1400054f8  mov     rbx, [rdi+38h]
0x1400054fc  test    rbx, rbx
0x1400054ff  jz      short loc_140005529
0x140005501  xor     r9d, r9d; msWindowLength
0x140005504  xor     r8d, r8d; msPeriod
0x140005507  xor     edx, edx; pftDueTime
0x140005509  mov     rcx, rbx; pti
0x14000550c  call    cs:__imp_SetThreadpoolTimer
0x140005512  mov     edx, 1; fCancelPendingCallbacks
0x140005517  mov     rcx, rbx; pti
0x14000551a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005520  mov     rcx, rbx; pti
0x140005523  call    cs:__imp_CloseThreadpoolTimer
0x140005529  mov     rbx, [rdi+30h]
0x14000552d  test    rbx, rbx
0x140005530  jz      short loc_14000555B
0x140005532  xor     r9d, r9d; msWindowLength
0x140005535  xor     r8d, r8d; msPeriod
0x140005538  xor     edx, edx; pftDueTime
0x14000553a  mov     rcx, rbx; pti
0x14000553d  call    cs:__imp_SetThreadpoolTimer
0x140005543  mov     edx, 1; fCancelPendingCallbacks
0x140005548  mov     rcx, rbx; pti
0x14000554b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005551  mov     rcx, rbx; pti
0x140005554  call    cs:__imp_CloseThreadpoolTimer
0x14000555a  nop
0x14000555b  mov     rcx, [rdi+10h]; lpMem
0x14000555f  test    rcx, rcx
0x140005562  jz      short loc_14000556A
0x140005564  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140005569  nop
0x14000556a  mov     rbx, [rsp+28h+arg_0]
0x14000556f  mov     rsi, [rsp+28h+arg_8]
0x140005574  add     rsp, 20h
0x140005578  pop     rdi
0x140005579  retn
```
