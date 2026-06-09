# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140012fec`
- end: `0x1400131d8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400184e0`

## callees

- `0x140012ea8`
- `0x140012fec`
- `0x140016560`
- `0x14001716c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400130b8`
- `KERNEL32!HeapFree` at `0x140013108`
- `KERNEL32!HeapFree` at `0x140013148`
- `KERNEL32!HeapFree` at `0x1400130b8`
- `KERNEL32!HeapFree` at `0x140013108`
- `KERNEL32!HeapFree` at `0x140013148`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14001302b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140013074`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14001317a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400131ab`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14001302b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140013074`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14001317a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400131ab`
- `KERNEL32!CloseThreadpoolTimer` at `0x140013034`
- `KERNEL32!CloseThreadpoolTimer` at `0x14001307d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140013183`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400131b4`
- `KERNEL32!CloseThreadpoolTimer` at `0x140013034`
- `KERNEL32!CloseThreadpoolTimer` at `0x14001307d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140013183`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400131b4`
- `KERNEL32!GetProcessHeap` at `0x1400130aa`
- `KERNEL32!GetProcessHeap` at `0x1400130fa`
- `KERNEL32!GetProcessHeap` at `0x14001313a`
- `KERNEL32!GetProcessHeap` at `0x1400130aa`
- `KERNEL32!GetProcessHeap` at `0x1400130fa`
- `KERNEL32!GetProcessHeap` at `0x14001313a`
- `KERNEL32!GetLastError` at `0x14001300a`
- `KERNEL32!GetLastError` at `0x140013053`
- `KERNEL32!GetLastError` at `0x14001300a`
- `KERNEL32!GetLastError` at `0x140013053`
- `KERNEL32!SetThreadpoolTimer` at `0x14001301d`
- `KERNEL32!SetThreadpoolTimer` at `0x140013066`
- `KERNEL32!SetThreadpoolTimer` at `0x14001316c`
- `KERNEL32!SetThreadpoolTimer` at `0x14001319d`
- `KERNEL32!SetThreadpoolTimer` at `0x14001301d`
- `KERNEL32!SetThreadpoolTimer` at `0x140013066`
- `KERNEL32!SetThreadpoolTimer` at `0x14001316c`
- `KERNEL32!SetThreadpoolTimer` at `0x14001319d`
- `KERNEL32!SetLastError` at `0x14001303c`
- `KERNEL32!SetLastError` at `0x140013085`
- `KERNEL32!SetLastError` at `0x14001303c`
- `KERNEL32!SetLastError` at `0x140013085`
- `KERNEL32!DeleteCriticalSection` at `0x140013111`
- `KERNEL32!DeleteCriticalSection` at `0x140013152`
- `KERNEL32!DeleteCriticalSection` at `0x140013111`
- `KERNEL32!DeleteCriticalSection` at `0x140013152`

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
  if ( v8 && qword_140020168 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140020168[25], qword_140020168, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
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
0x140012fec  mov     [rsp+arg_0], rbx
0x140012ff1  mov     [rsp+arg_8], rsi
0x140012ff6  push    rdi
0x140012ff7  sub     rsp, 20h
0x140012ffb  mov     byte ptr [rcx], 0
0x140012ffe  mov     rdi, rcx
0x140013001  mov     rsi, [rcx+30h]
0x140013005  test    rsi, rsi
0x140013008  jz      short loc_140013042
0x14001300a  call    cs:__imp_GetLastError
0x140013010  xor     r9d, r9d; msWindowLength
0x140013013  xor     r8d, r8d; msPeriod
0x140013016  xor     edx, edx; pftDueTime
0x140013018  mov     rcx, rsi; pti
0x14001301b  mov     ebx, eax
0x14001301d  call    cs:__imp_SetThreadpoolTimer
0x140013023  mov     edx, 1; fCancelPendingCallbacks
0x140013028  mov     rcx, rsi; pti
0x14001302b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013031  mov     rcx, rsi; pti
0x140013034  call    cs:__imp_CloseThreadpoolTimer
0x14001303a  mov     ecx, ebx; dwErrCode
0x14001303c  call    cs:__imp_SetLastError
0x140013042  mov     qword ptr [rdi+30h], 0
0x14001304a  mov     rsi, [rdi+38h]
0x14001304e  test    rsi, rsi
0x140013051  jz      short loc_14001308B
0x140013053  call    cs:__imp_GetLastError
0x140013059  xor     r9d, r9d; msWindowLength
0x14001305c  xor     r8d, r8d; msPeriod
0x14001305f  xor     edx, edx; pftDueTime
0x140013061  mov     rcx, rsi; pti
0x140013064  mov     ebx, eax
0x140013066  call    cs:__imp_SetThreadpoolTimer
0x14001306c  mov     edx, 1; fCancelPendingCallbacks
0x140013071  mov     rcx, rsi; pti
0x140013074  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14001307a  mov     rcx, rsi; pti
0x14001307d  call    cs:__imp_CloseThreadpoolTimer
0x140013083  mov     ecx, ebx; dwErrCode
0x140013085  call    cs:__imp_SetLastError
0x14001308b  mov     qword ptr [rdi+38h], 0
0x140013093  mov     rbx, [rdi+100h]
0x14001309a  mov     qword ptr [rdi+100h], 0
0x1400130a5  test    rbx, rbx
0x1400130a8  jz      short loc_1400130BE
0x1400130aa  call    cs:__imp_GetProcessHeap
0x1400130b0  mov     r8, rbx; lpMem
0x1400130b3  xor     edx, edx; dwFlags
0x1400130b5  mov     rcx, rax; hHeap
0x1400130b8  call    cs:__imp_HeapFree
0x1400130be  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1400130c5  test    r8, r8
0x1400130c8  jz      short loc_1400130E2
0x1400130ca  mov     rdx, cs:qword_140020168; SRWLock
0x1400130d1  test    rdx, rdx
0x1400130d4  jz      short loc_1400130E2
0x1400130d6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400130dd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400130e2  lea     rbx, [rdi+98h]
0x1400130e9  mov     rsi, [rbx+40h]
0x1400130ed  mov     qword ptr [rbx+40h], 0
0x1400130f5  test    rsi, rsi
0x1400130f8  jz      short loc_14001310E
0x1400130fa  call    cs:__imp_GetProcessHeap
0x140013100  mov     r8, rsi; lpMem
0x140013103  xor     edx, edx; dwFlags
0x140013105  mov     rcx, rax; hHeap
0x140013108  call    cs:__imp_HeapFree
0x14001310e  mov     rcx, rbx; lpCriticalSection
0x140013111  call    cs:__imp_DeleteCriticalSection
0x140013117  lea     rcx, [rdi+90h]
0x14001311e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140013123  mov     rsi, [rdi+88h]
0x14001312a  mov     qword ptr [rdi+88h], 0
0x140013135  test    rsi, rsi
0x140013138  jz      short loc_14001314E
0x14001313a  call    cs:__imp_GetProcessHeap
0x140013140  mov     r8, rsi; lpMem
0x140013143  xor     edx, edx; dwFlags
0x140013145  mov     rcx, rax; hHeap
0x140013148  call    cs:__imp_HeapFree
0x14001314e  lea     rcx, [rdi+48h]; lpCriticalSection
0x140013152  call    cs:__imp_DeleteCriticalSection
0x140013158  mov     rbx, [rdi+38h]
0x14001315c  test    rbx, rbx
0x14001315f  jz      short loc_140013189
0x140013161  xor     r9d, r9d; msWindowLength
0x140013164  xor     r8d, r8d; msPeriod
0x140013167  xor     edx, edx; pftDueTime
0x140013169  mov     rcx, rbx; pti
0x14001316c  call    cs:__imp_SetThreadpoolTimer
0x140013172  mov     edx, 1; fCancelPendingCallbacks
0x140013177  mov     rcx, rbx; pti
0x14001317a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013180  mov     rcx, rbx; pti
0x140013183  call    cs:__imp_CloseThreadpoolTimer
0x140013189  mov     rbx, [rdi+30h]
0x14001318d  test    rbx, rbx
0x140013190  jz      short loc_1400131BA
0x140013192  xor     r9d, r9d; msWindowLength
0x140013195  xor     r8d, r8d; msPeriod
0x140013198  xor     edx, edx; pftDueTime
0x14001319a  mov     rcx, rbx; pti
0x14001319d  call    cs:__imp_SetThreadpoolTimer
0x1400131a3  mov     edx, 1; fCancelPendingCallbacks
0x1400131a8  mov     rcx, rbx; pti
0x1400131ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400131b1  mov     rcx, rbx; pti
0x1400131b4  call    cs:__imp_CloseThreadpoolTimer
0x1400131ba  mov     rcx, [rdi+10h]; lpMem
0x1400131be  test    rcx, rcx
0x1400131c1  jz      short loc_1400131C8
0x1400131c3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1400131c8  mov     rbx, [rsp+28h+arg_0]
0x1400131cd  mov     rsi, [rsp+28h+arg_8]
0x1400131d2  add     rsp, 20h
0x1400131d6  pop     rdi
0x1400131d7  retn
```
