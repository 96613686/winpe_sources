# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1000d370`
- end: `0x1000d4db`
- name: `??1EnabledStateManager@details@wil@@QAE@XZ`
- size: `363`
- prototype: `void __usercall(wil::details::EnabledStateManager *__hidden this@<ecx>)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x10062970`

## callees

- `0x1000d370`
- `0x1000d4f0`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000d47a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000d498`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000d47a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000d498`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000d481`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000d49f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000d481`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000d49f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000d3cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1000d3cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000d3a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000d3a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000d3b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000d4b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000d3b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1000d4b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000d3c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000d4c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000d3c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1000d4c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000d3be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000d4bc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000d3be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1000d4bc`

## pseudocode

```c
void __thiscall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // ebx
  DWORD LastError; // esi
  int v4; // eax
  void (__thiscall *v5)(_DWORD, int); // ebx
  void (__thiscall *v6)(_DWORD, int); // esi
  int v7; // eax
  void *v8; // eax
  HANDLE ProcessHeap; // eax
  void *v10; // eax
  HANDLE v11; // eax
  struct _TP_TIMER *v12; // esi
  void *v13; // [esp-4h] [ebp-20h]
  void *v14; // [esp-4h] [ebp-20h]

  *(_DWORD *)this = 0;
  v2 = (struct _TP_TIMER *)*((_DWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_DWORD *)this + 2) = 0;
  wil::details::EnabledStateManager::ProcessShutdown(this);
  v4 = *((_DWORD *)this + 14);
  if ( !v4 )
  {
    v5 = (void (__thiscall *)(_DWORD, int))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v6 = (void (__thiscall *)(_DWORD, int))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_11;
  }
  v5 = (void (__thiscall *)(_DWORD, int))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    g_wil_details_internalUnsubscribeFeatureStateChangeNotification(
      g_wil_details_internalUnsubscribeFeatureStateChangeNotification,
      v4);
  }
  else
  {
    v6 = (void (__thiscall *)(_DWORD, int))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_11;
    g_wil_details_apiUnsubscribeFeatureStateChangeNotification(
      g_wil_details_apiUnsubscribeFeatureStateChangeNotification,
      v4);
  }
  v6 = (void (__thiscall *)(_DWORD, int))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v5 = (void (__thiscall *)(_DWORD, int))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_11:
  v7 = *((_DWORD *)this + 13);
  if ( v7 )
  {
    if ( v5 )
    {
      v5(v5, v7);
    }
    else if ( v6 )
    {
      v6(v6, v7);
    }
  }
  v8 = (void *)*((_DWORD *)this + 12);
  *((_DWORD *)this + 12) = 0;
  if ( v8 )
  {
    v13 = v8;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
  }
  v10 = (void *)*((_DWORD *)this + 8);
  *((_DWORD *)this + 8) = 0;
  if ( v10 )
  {
    v14 = v10;
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v14);
  }
  v12 = (struct _TP_TIMER *)*((_DWORD *)this + 2);
  if ( v12 )
  {
    SetThreadpoolTimer(v12, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
  }
}

```

## disassembly

```asm
0x1000d370  mov     edi, edi
0x1000d372  push    ebp
0x1000d373  mov     ebp, esp
0x1000d375  push    0FFFFFFFFh
0x1000d377  push    offset ??1EnabledStateManager@details@wil@@QAE@XZ_SEH
0x1000d37c  mov     eax, large fs:0
0x1000d382  push    eax
0x1000d383  push    ebx
0x1000d384  push    esi
0x1000d385  push    edi
0x1000d386  mov     eax, ___security_cookie
0x1000d38b  xor     eax, ebp
0x1000d38d  push    eax; unsigned int
0x1000d38e  lea     eax, [ebp+var_C]
0x1000d391  mov     large fs:0, eax
0x1000d397  mov     edi, ecx
0x1000d399  mov     dword ptr [edi], 0
0x1000d39f  mov     ebx, [edi+8]
0x1000d3a2  test    ebx, ebx
0x1000d3a4  jz      short loc_1000D3D2
0x1000d3a6  call    ds:__imp__GetLastError@0; GetLastError()
0x1000d3ac  push    0; msWindowLength
0x1000d3ae  push    0; msPeriod
0x1000d3b0  push    0; pftDueTime
0x1000d3b2  push    ebx; pti
0x1000d3b3  mov     esi, eax
0x1000d3b5  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1000d3bb  push    1; fCancelPendingCallbacks
0x1000d3bd  push    ebx; pti
0x1000d3be  call    ds:__imp__WaitForThreadpoolTimerCallbacks@8; WaitForThreadpoolTimerCallbacks(x,x)
0x1000d3c4  push    ebx; pti
0x1000d3c5  call    ds:__imp__CloseThreadpoolTimer@4; CloseThreadpoolTimer(x)
0x1000d3cb  push    esi; dwErrCode
0x1000d3cc  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1000d3d2  mov     ecx, edi; this
0x1000d3d4  mov     dword ptr [edi+8], 0
0x1000d3db  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QAEXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1000d3e0  mov     eax, [edi+38h]
0x1000d3e3  test    eax, eax
0x1000d3e5  jz      short loc_1000D42F
0x1000d3e7  mov     [ebp+var_4], 0
0x1000d3ee  mov     ebx, _g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1000d3f4  test    ebx, ebx
0x1000d3f6  jz      short loc_1000D405
0x1000d3f8  push    eax; void *
0x1000d3f9  mov     ecx, ebx
0x1000d3fb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d401  call    ebx ; _g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1000d403  jmp     short loc_1000D41A
0x1000d405  mov     esi, _g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1000d40b  test    esi, esi
0x1000d40d  jz      short loc_1000D426
0x1000d40f  push    eax; void *
0x1000d410  mov     ecx, esi
0x1000d412  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d418  call    esi ; _g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1000d41a  mov     esi, _g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1000d420  mov     ebx, _g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1000d426  mov     [ebp+var_4], 0FFFFFFFFh
0x1000d42d  jmp     short loc_1000D43B
0x1000d42f  mov     ebx, _g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1000d435  mov     esi, _g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1000d43b  mov     eax, [edi+34h]
0x1000d43e  test    eax, eax
0x1000d440  jz      short loc_1000D469
0x1000d442  mov     [ebp+var_4], 1
0x1000d449  test    ebx, ebx
0x1000d44b  jz      short loc_1000D45A
0x1000d44d  push    eax; void *
0x1000d44e  mov     ecx, ebx
0x1000d450  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d456  call    ebx ; _g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1000d458  jmp     short loc_1000D469
0x1000d45a  test    esi, esi
0x1000d45c  jz      short loc_1000D469
0x1000d45e  push    eax; void *
0x1000d45f  mov     ecx, esi
0x1000d461  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d467  call    esi ; _g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1000d469  mov     eax, [edi+30h]
0x1000d46c  mov     dword ptr [edi+30h], 0
0x1000d473  test    eax, eax
0x1000d475  jz      short loc_1000D487
0x1000d477  push    eax; lpMem
0x1000d478  push    0; dwFlags
0x1000d47a  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000d480  push    eax; hHeap
0x1000d481  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000d487  mov     eax, [edi+20h]
0x1000d48a  mov     dword ptr [edi+20h], 0
0x1000d491  test    eax, eax
0x1000d493  jz      short loc_1000D4A5
0x1000d495  push    eax; lpMem
0x1000d496  push    0; dwFlags
0x1000d498  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000d49e  push    eax; hHeap
0x1000d49f  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000d4a5  mov     esi, [edi+8]
0x1000d4a8  test    esi, esi
0x1000d4aa  jz      short loc_1000D4C9
0x1000d4ac  push    0; msWindowLength
0x1000d4ae  push    0; msPeriod
0x1000d4b0  push    0; pftDueTime
0x1000d4b2  push    esi; pti
0x1000d4b3  call    ds:__imp__SetThreadpoolTimer@16; SetThreadpoolTimer(x,x,x,x)
0x1000d4b9  push    1; fCancelPendingCallbacks
0x1000d4bb  push    esi; pti
0x1000d4bc  call    ds:__imp__WaitForThreadpoolTimerCallbacks@8; WaitForThreadpoolTimerCallbacks(x,x)
0x1000d4c2  push    esi; pti
0x1000d4c3  call    ds:__imp__CloseThreadpoolTimer@4; CloseThreadpoolTimer(x)
0x1000d4c9  mov     ecx, [ebp+var_C]
0x1000d4cc  mov     large fs:0, ecx
0x1000d4d3  pop     ecx
0x1000d4d4  pop     edi
0x1000d4d5  pop     esi
0x1000d4d6  pop     ebx
0x1000d4d7  mov     esp, ebp
0x1000d4d9  pop     ebp
0x1000d4da  retn
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f860  nop
0x1005f861  nop
0x1005f862  mov     edx, [esp-4+arg_4]
0x1005f866  lea     eax, [edx+0Ch]
0x1005f869  mov     ecx, [edx-10h]
0x1005f86c  xor     ecx, eax; StackCookie
0x1005f86e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f873  mov     eax, offset stru_10062C18
0x1005f878  jmp     ___CxxFrameHandler3
```
