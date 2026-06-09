# SockSanCleanup

- ea: `0x1800423ec`
- end: `0x180042704`
- name: `SockSanCleanup`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x1800028b8`
- `0x180038104`
- `0x180042344`
- `0x1800423ec`
- `0x180042b50`

## import_xrefs

- `ntdll!NtAlertThread` at `0x1800425ce`
- `ntdll!NtAlertThread` at `0x1800425ce`
- `ntdll!NtClose` at `0x18004250a`
- `ntdll!NtClose` at `0x180042524`
- `ntdll!NtClose` at `0x1800425e1`
- `ntdll!NtClose` at `0x18004250a`
- `ntdll!NtClose` at `0x180042524`
- `ntdll!NtClose` at `0x1800425e1`
- `ntdll!RtlFreeHeap` at `0x180042414`
- `ntdll!RtlFreeHeap` at `0x180042442`
- `ntdll!RtlFreeHeap` at `0x180042414`
- `ntdll!RtlFreeHeap` at `0x180042442`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004266f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042687`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004266f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042687`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004254f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800426ab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004254f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800426ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800424b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800425ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042658`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800424b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800425ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042658`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042479`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004255e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042616`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042479`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004255e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426c8`

## pseudocode

```c
int SockSanCleanup()
{
  PVOID *v0; // rax
  int v1; // ecx
  volatile signed __int32 *v2; // rcx
  __int64 v3; // rax
  char v4; // bl
  int result; // eax

  SockSanStartup = 0;
  if ( SockSanSubnetMap )
  {
    RtlFreeHeap(SockPrivateHeap, 0, SockSanSubnetMap);
    SockSanSubnetMap = 0;
    SockSanSubnetCount = 0;
  }
  if ( SockSanV6AddressMap )
  {
    RtlFreeHeap(SockPrivateHeap, 0, SockSanV6AddressMap);
    SockSanV6AddressMap = 0;
    SockSanV6AddressCount = 0;
  }
  if ( SockAsyncQueuePort )
    SockSanCheckAsyncPort();
  SockSanProviderCount = 0;
  EnterCriticalSection(&SockSanProvListCritSec);
  v0 = (PVOID *)SockSanProviderList;
  if ( SockSanProviderList != &SockSanProviderList )
  {
    v1 = SockSanProviderCount;
    do
    {
      v0 = (PVOID *)*v0;
      ++v1;
    }
    while ( v0 != &SockSanProviderList );
    SockSanProviderCount = v1;
  }
  LeaveCriticalSection(&SockSanProvListCritSec);
  if ( SockSanProviderCount )
  {
    if ( (unsigned __int8)SockCheckAndReferenceAsyncThread() )
      goto LABEL_20;
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 17, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
    SockSanProviderCount = 0;
  }
  else if ( SockSanHelperHandle )
  {
    NtClose(SockSanHelperHandle);
    SockSanHelperHandle = 0;
    NtClose(SockSanEvent);
    SockSanEvent = 0;
  }
  if ( _InterlockedIncrement(&SockSanCleanUpCompleteCount) == 2 )
    SetEvent(SockSanCleanUpCompleteEvent);
LABEL_20:
  EnterCriticalSection(&SockSanProvListCritSec);
  while ( 1 )
  {
    v2 = (volatile signed __int32 *)SockSanProviderList;
    if ( SockSanProviderList == &SockSanProviderList )
      break;
    if ( *((PVOID **)SockSanProviderList + 1) != &SockSanProviderList
      || (v3 = *(_QWORD *)SockSanProviderList, *(PVOID *)(*(_QWORD *)SockSanProviderList + 8LL) != SockSanProviderList) )
    {
      __fastfail(3u);
    }
    SockSanProviderList = *(PVOID *)SockSanProviderList;
    *(_QWORD *)(v3 + 8) = &SockSanProviderList;
    if ( _InterlockedExchangeAdd(v2 + 4, 0xFFFFFFFF) == 1 )
      SockSanFreeProvider((PVOID)v2);
  }
  LeaveCriticalSection(&SockSanProvListCritSec);
  if ( SockSanConnectThreadCreated )
  {
    ExitConnectThread = 1;
    NtAlertThread(ConnectThreadHandle);
    NtClose(ConnectThreadHandle);
    ConnectThreadHandle = 0;
    SockSanConnectThreadCreated = 0;
  }
  if ( SockSanFlowThreadCreated )
  {
    _InterlockedDecrement(&SockAsyncThreadReferenceCount);
    SockSanFlowThreadCreated = 0;
  }
  EnterCriticalSection(&SockSanListCritSec);
  if ( (__int64 *)SockSanOpenList == &SockSanOpenList && (__int64 *)SockSanClosingList == &SockSanClosingList )
  {
    v4 = 1;
  }
  else
  {
    v4 = 0;
    SockSanDeleteListCritSec = 1;
  }
  LeaveCriticalSection(&SockSanListCritSec);
  if ( v4 )
  {
    DeleteCriticalSection(&SockSanListCritSec);
    if ( !SockSanCacheCallbackRegistered )
      DeleteCriticalSection(&SockSanProvListCritSec);
    if ( _InterlockedIncrement(&SockSanCleanUpCompleteCount) == 2 )
      SetEvent(SockSanCleanUpCompleteEvent);
  }
  result = (_DWORD)SockSanSCAutostartEvent - 1;
  if ( (char *)SockSanSCAutostartEvent - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    result = CloseHandle(SockSanSCAutostartEvent);
  SockSanEnabled = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    return WPP_SF_(1025, 19, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800423ec  push    rbx
0x1800423ee  push    rsi
0x1800423ef  push    rdi
0x1800423f0  push    r14
0x1800423f2  sub     rsp, 28h
0x1800423f6  mov     r8, cs:SockSanSubnetMap; P
0x1800423fd  xor     edi, edi
0x1800423ff  mov     cs:SockSanStartup, dil
0x180042406  test    r8, r8
0x180042409  jz      short loc_18004242D
0x18004240b  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180042412  xor     edx, edx; Flags
0x180042414  call    cs:__imp_RtlFreeHeap
0x18004241b  nop     dword ptr [rax+rax+00h]
0x180042420  mov     cs:SockSanSubnetMap, rdi
0x180042427  mov     cs:SockSanSubnetCount, edi
0x18004242d  mov     r8, cs:SockSanV6AddressMap; P
0x180042434  test    r8, r8
0x180042437  jz      short loc_18004245B
0x180042439  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180042440  xor     edx, edx; Flags
0x180042442  call    cs:__imp_RtlFreeHeap
0x180042449  nop     dword ptr [rax+rax+00h]
0x18004244e  mov     cs:SockSanV6AddressMap, rdi
0x180042455  mov     cs:SockSanV6AddressCount, edi
0x18004245b  cmp     cs:SockAsyncQueuePort, rdi
0x180042462  jz      short loc_180042469
0x180042464  call    SockSanCheckAsyncPort
0x180042469  lea     r14, SockSanProvListCritSec
0x180042470  mov     cs:SockSanProviderCount, edi
0x180042476  mov     rcx, r14; lpCriticalSection
0x180042479  call    cs:__imp_EnterCriticalSection
0x180042480  nop     dword ptr [rax+rax+00h]
0x180042485  mov     rax, cs:SockSanProviderList
0x18004248c  lea     rbx, SockSanProviderList
0x180042493  mov     esi, 1
0x180042498  cmp     rax, rbx
0x18004249b  jz      short loc_1800424B3
0x18004249d  mov     ecx, cs:SockSanProviderCount
0x1800424a3  mov     rax, [rax]
0x1800424a6  add     ecx, esi
0x1800424a8  cmp     rax, rbx
0x1800424ab  jnz     short loc_1800424A3
0x1800424ad  mov     cs:SockSanProviderCount, ecx
0x1800424b3  mov     rcx, r14; lpCriticalSection
0x1800424b6  call    cs:__imp_LeaveCriticalSection
0x1800424bd  nop     dword ptr [rax+rax+00h]
0x1800424c2  cmp     cs:SockSanProviderCount, edi
0x1800424c8  jz      short loc_1800424FE
0x1800424ca  call    SockCheckAndReferenceAsyncThread
0x1800424cf  test    al, al
0x1800424d1  jnz     loc_18004255B
0x1800424d7  test    byte ptr cs:xmmword_180063D60, 2
0x1800424de  jz      short loc_1800424F6
0x1800424e0  mov     edx, 11h
0x1800424e5  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800424ec  mov     ecx, 401h
0x1800424f1  call    WPP_SF_
0x1800424f6  mov     cs:SockSanProviderCount, edi
0x1800424fc  jmp     short loc_180042537
0x1800424fe  mov     rcx, cs:SockSanHelperHandle; Handle
0x180042505  test    rcx, rcx
0x180042508  jz      short loc_180042537
0x18004250a  call    cs:__imp_NtClose
0x180042511  nop     dword ptr [rax+rax+00h]
0x180042516  mov     rcx, cs:SockSanEvent; Handle
0x18004251d  mov     cs:SockSanHelperHandle, rdi
0x180042524  call    cs:__imp_NtClose
0x18004252b  nop     dword ptr [rax+rax+00h]
0x180042530  mov     cs:SockSanEvent, rdi
0x180042537  mov     eax, esi
0x180042539  lock xadd cs:SockSanCleanUpCompleteCount, eax
0x180042541  add     eax, esi
0x180042543  cmp     eax, 2
0x180042546  jnz     short loc_18004255B
0x180042548  mov     rcx, cs:SockSanCleanUpCompleteEvent; hEvent
0x18004254f  call    cs:__imp_SetEvent
0x180042556  nop     dword ptr [rax+rax+00h]
0x18004255b  mov     rcx, r14; lpCriticalSection
0x18004255e  call    cs:__imp_EnterCriticalSection
0x180042565  nop     dword ptr [rax+rax+00h]
0x18004256a  mov     rcx, cs:SockSanProviderList; CompletionContext
0x180042571  cmp     rcx, rbx
0x180042574  jz      short loc_1800425AA
0x180042576  cmp     [rcx+8], rbx
0x18004257a  jnz     short loc_1800425A3
0x18004257c  mov     rax, [rcx]
0x18004257f  cmp     [rax+8], rcx
0x180042583  jnz     short loc_1800425A3
0x180042585  mov     cs:SockSanProviderList, rax
0x18004258c  mov     [rax+8], rbx
0x180042590  or      eax, 0FFFFFFFFh
0x180042593  lock xadd [rcx+10h], eax
0x180042598  cmp     eax, esi
0x18004259a  jnz     short loc_18004256A
0x18004259c  call    SockSanFreeProvider
0x1800425a1  jmp     short loc_18004256A
0x1800425a3  mov     ecx, 3
0x1800425a8  int     29h; Win8: RtlFailFast(ecx)
0x1800425aa  mov     rcx, r14; lpCriticalSection
0x1800425ad  call    cs:__imp_LeaveCriticalSection
0x1800425b4  nop     dword ptr [rax+rax+00h]
0x1800425b9  cmp     cs:SockSanConnectThreadCreated, edi
0x1800425bf  jz      short loc_1800425FA
0x1800425c1  mov     rcx, cs:ConnectThreadHandle; ThreadHandle
0x1800425c8  mov     cs:ExitConnectThread, esi
0x1800425ce  call    cs:__imp_NtAlertThread
0x1800425d5  nop     dword ptr [rax+rax+00h]
0x1800425da  mov     rcx, cs:ConnectThreadHandle; Handle
0x1800425e1  call    cs:__imp_NtClose
0x1800425e8  nop     dword ptr [rax+rax+00h]
0x1800425ed  mov     cs:ConnectThreadHandle, rdi
0x1800425f4  mov     cs:SockSanConnectThreadCreated, edi
0x1800425fa  cmp     cs:SockSanFlowThreadCreated, edi
0x180042600  jz      short loc_18004260F
0x180042602  lock dec cs:SockAsyncThreadReferenceCount
0x180042609  mov     cs:SockSanFlowThreadCreated, edi
0x18004260f  lea     rcx, SockSanListCritSec; lpCriticalSection
0x180042616  call    cs:__imp_EnterCriticalSection
0x18004261d  nop     dword ptr [rax+rax+00h]
0x180042622  lea     rax, SockSanOpenList
0x180042629  cmp     cs:SockSanOpenList, rax
0x180042630  jnz     short loc_180042647
0x180042632  lea     rax, SockSanClosingList
0x180042639  cmp     cs:SockSanClosingList, rax
0x180042640  jnz     short loc_180042647
0x180042642  mov     bl, sil
0x180042645  jmp     short loc_180042651
0x180042647  mov     bl, dil
0x18004264a  mov     cs:SockSanDeleteListCritSec, sil
0x180042651  lea     rcx, SockSanListCritSec; lpCriticalSection
0x180042658  call    cs:__imp_LeaveCriticalSection
0x18004265f  nop     dword ptr [rax+rax+00h]
0x180042664  test    bl, bl
0x180042666  jz      short loc_1800426B7
0x180042668  lea     rcx, SockSanListCritSec; lpCriticalSection
0x18004266f  call    cs:__imp_DeleteCriticalSection
0x180042676  nop     dword ptr [rax+rax+00h]
0x18004267b  cmp     cs:SockSanCacheCallbackRegistered, dil
0x180042682  jnz     short loc_180042693
0x180042684  mov     rcx, r14; lpCriticalSection
0x180042687  call    cs:__imp_DeleteCriticalSection
0x18004268e  nop     dword ptr [rax+rax+00h]
0x180042693  mov     eax, esi
0x180042695  lock xadd cs:SockSanCleanUpCompleteCount, eax
0x18004269d  add     eax, esi
0x18004269f  cmp     eax, 2
0x1800426a2  jnz     short loc_1800426B7
0x1800426a4  mov     rcx, cs:SockSanCleanUpCompleteEvent; hEvent
0x1800426ab  call    cs:__imp_SetEvent
0x1800426b2  nop     dword ptr [rax+rax+00h]
0x1800426b7  mov     rcx, cs:SockSanSCAutostartEvent; hObject
0x1800426be  lea     rax, [rcx-1]
0x1800426c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800426c6  ja      short loc_1800426D4
0x1800426c8  call    cs:__imp_CloseHandle
0x1800426cf  nop     dword ptr [rax+rax+00h]
0x1800426d4  mov     cs:SockSanEnabled, edi
0x1800426da  test    byte ptr cs:xmmword_180063D60, 2
0x1800426e1  jz      short loc_1800426F9
0x1800426e3  mov     edx, 13h
0x1800426e8  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800426ef  mov     ecx, 401h
0x1800426f4  call    WPP_SF_
0x1800426f9  add     rsp, 28h
0x1800426fd  pop     r14
0x1800426ff  pop     rdi
0x180042700  pop     rsi
0x180042701  pop     rbx
0x180042702  retn
```
