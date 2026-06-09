# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140006928`
- end: `0x140006b16`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140011d40`

## callees

- `0x1400065d4`
- `0x140006928`
- `0x14000c2bc`
- `0x14000e0f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006a4d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006a8e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006a4d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006a8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400069e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006a36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006a76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400069e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006a36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006a76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400069f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006a44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006a84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400069f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006a44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000698f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000698f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006978`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400069c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006978`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400069c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006967`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400069b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006ab6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006ae7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006967`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400069b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006ab6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006ae7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006970`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400069b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006abf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006af0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006970`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400069b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006abf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006af0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006959`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400069a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006aa8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006ad9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006959`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400069a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006aa8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006ad9`

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
  if ( v8 && qword_14001A088 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14001A088[25], qword_14001A088, v8);
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
0x140006928  mov     [rsp+arg_0], rbx
0x14000692d  mov     [rsp+arg_8], rsi
0x140006932  push    rdi
0x140006933  sub     rsp, 20h
0x140006937  mov     rdi, rcx
0x14000693a  mov     byte ptr [rcx], 0
0x14000693d  mov     rsi, [rcx+30h]
0x140006941  test    rsi, rsi
0x140006944  jz      short loc_14000697E
0x140006946  call    cs:__imp_GetLastError
0x14000694c  mov     ebx, eax
0x14000694e  xor     r9d, r9d; msWindowLength
0x140006951  xor     r8d, r8d; msPeriod
0x140006954  xor     edx, edx; pftDueTime
0x140006956  mov     rcx, rsi; pti
0x140006959  call    cs:__imp_SetThreadpoolTimer
0x14000695f  mov     edx, 1; fCancelPendingCallbacks
0x140006964  mov     rcx, rsi; pti
0x140006967  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000696d  mov     rcx, rsi; pti
0x140006970  call    cs:__imp_CloseThreadpoolTimer
0x140006976  mov     ecx, ebx; dwErrCode
0x140006978  call    cs:__imp_SetLastError
0x14000697e  mov     qword ptr [rdi+30h], 0
0x140006986  mov     rsi, [rdi+38h]
0x14000698a  test    rsi, rsi
0x14000698d  jz      short loc_1400069C7
0x14000698f  call    cs:__imp_GetLastError
0x140006995  mov     ebx, eax
0x140006997  xor     r9d, r9d; msWindowLength
0x14000699a  xor     r8d, r8d; msPeriod
0x14000699d  xor     edx, edx; pftDueTime
0x14000699f  mov     rcx, rsi; pti
0x1400069a2  call    cs:__imp_SetThreadpoolTimer
0x1400069a8  mov     edx, 1; fCancelPendingCallbacks
0x1400069ad  mov     rcx, rsi; pti
0x1400069b0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400069b6  mov     rcx, rsi; pti
0x1400069b9  call    cs:__imp_CloseThreadpoolTimer
0x1400069bf  mov     ecx, ebx; dwErrCode
0x1400069c1  call    cs:__imp_SetLastError
0x1400069c7  mov     qword ptr [rdi+38h], 0
0x1400069cf  mov     rbx, [rdi+100h]
0x1400069d6  mov     qword ptr [rdi+100h], 0
0x1400069e1  test    rbx, rbx
0x1400069e4  jz      short loc_1400069FA
0x1400069e6  call    cs:__imp_GetProcessHeap
0x1400069ec  mov     rcx, rax; hHeap
0x1400069ef  mov     r8, rbx; lpMem
0x1400069f2  xor     edx, edx; dwFlags
0x1400069f4  call    cs:__imp_HeapFree
0x1400069fa  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140006a01  test    r8, r8
0x140006a04  jz      short loc_140006A1E
0x140006a06  mov     rdx, cs:qword_14001A088; SRWLock
0x140006a0d  test    rdx, rdx
0x140006a10  jz      short loc_140006A1E
0x140006a12  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140006a19  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140006a1e  lea     rbx, [rdi+98h]
0x140006a25  mov     rsi, [rbx+40h]
0x140006a29  mov     qword ptr [rbx+40h], 0
0x140006a31  test    rsi, rsi
0x140006a34  jz      short loc_140006A4A
0x140006a36  call    cs:__imp_GetProcessHeap
0x140006a3c  mov     rcx, rax; hHeap
0x140006a3f  mov     r8, rsi; lpMem
0x140006a42  xor     edx, edx; dwFlags
0x140006a44  call    cs:__imp_HeapFree
0x140006a4a  mov     rcx, rbx; lpCriticalSection
0x140006a4d  call    cs:__imp_DeleteCriticalSection
0x140006a53  lea     rcx, [rdi+90h]
0x140006a5a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140006a5f  mov     rsi, [rdi+88h]
0x140006a66  mov     qword ptr [rdi+88h], 0
0x140006a71  test    rsi, rsi
0x140006a74  jz      short loc_140006A8A
0x140006a76  call    cs:__imp_GetProcessHeap
0x140006a7c  mov     rcx, rax; hHeap
0x140006a7f  mov     r8, rsi; lpMem
0x140006a82  xor     edx, edx; dwFlags
0x140006a84  call    cs:__imp_HeapFree
0x140006a8a  lea     rcx, [rdi+48h]; lpCriticalSection
0x140006a8e  call    cs:__imp_DeleteCriticalSection
0x140006a94  mov     rbx, [rdi+38h]
0x140006a98  test    rbx, rbx
0x140006a9b  jz      short loc_140006AC5
0x140006a9d  xor     r9d, r9d; msWindowLength
0x140006aa0  xor     r8d, r8d; msPeriod
0x140006aa3  xor     edx, edx; pftDueTime
0x140006aa5  mov     rcx, rbx; pti
0x140006aa8  call    cs:__imp_SetThreadpoolTimer
0x140006aae  mov     edx, 1; fCancelPendingCallbacks
0x140006ab3  mov     rcx, rbx; pti
0x140006ab6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006abc  mov     rcx, rbx; pti
0x140006abf  call    cs:__imp_CloseThreadpoolTimer
0x140006ac5  mov     rbx, [rdi+30h]
0x140006ac9  test    rbx, rbx
0x140006acc  jz      short loc_140006AF7
0x140006ace  xor     r9d, r9d; msWindowLength
0x140006ad1  xor     r8d, r8d; msPeriod
0x140006ad4  xor     edx, edx; pftDueTime
0x140006ad6  mov     rcx, rbx; pti
0x140006ad9  call    cs:__imp_SetThreadpoolTimer
0x140006adf  mov     edx, 1; fCancelPendingCallbacks
0x140006ae4  mov     rcx, rbx; pti
0x140006ae7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006aed  mov     rcx, rbx; pti
0x140006af0  call    cs:__imp_CloseThreadpoolTimer
0x140006af6  nop
0x140006af7  mov     rcx, [rdi+10h]; lpMem
0x140006afb  test    rcx, rcx
0x140006afe  jz      short loc_140006B06
0x140006b00  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140006b05  nop
0x140006b06  mov     rbx, [rsp+28h+arg_0]
0x140006b0b  mov     rsi, [rsp+28h+arg_8]
0x140006b10  add     rsp, 20h
0x140006b14  pop     rdi
0x140006b15  retn
```
