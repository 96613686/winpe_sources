# AsyncThread

- ea: `0x1802b2860`
- end: `0x1802b2a04`
- name: `AsyncThread`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0x180173260`
- `0x180173e2c`
- `0x1802b2860`
- `0x1802b31dc`
- `0x1802b4e60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x1802b29eb`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x1802b29eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b29a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802b29a1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1802b29ac`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1802b29ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802b294c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18046c796`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802b294c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18046c796`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802b2910`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802b2910`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802b2880`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802b28fb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802b2880`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1802b28fb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802b293e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802b293e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802b2980`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802b2980`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1802b29c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18046c7bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1802b29c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18046c7bb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1802b28d0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1802b28d0`

## pseudocode

```c
__int64 AsyncThread()
{
  HANDLE *v0; // rbx
  int v1; // eax
  int v2; // ebx
  HANDLE CurrentThread; // rax
  HANDLE Handles[3]; // [rsp+50h] [rbp-18h] BYREF

  WaitForSingleObject(hevDRASetup, 0xFFFFFFFF);
  while ( !eServiceShutdown )
  {
    fAsyncThreadAlive = 1;
    Handles[0] = hevEntriesInAOList;
    Handles[1] = hServDoneEvent;
    WaitForMultipleObjects(2u, Handles, 0, 0x1B7740u);
    if ( eServiceShutdown || dsaUserMode == 1 )
      break;
    WaitForSingleObject(hmtxAsyncThread, 0xFFFFFFFF);
    _InterlockedIncrement(&ulcActiveReplicationThreads);
    EnterCriticalSection(&csAOList);
    v0 = (HANDLE *)paoFirst;
    if ( paoFirst )
      paoFirst = *(void **)paoFirst;
    if ( !v0 )
      ResetEvent(hevEntriesInAOList);
    LeaveCriticalSection(&csAOList);
    if ( v0 )
    {
      lastSeen = 12;
      v1 = DispatchPao((__int64)v0);
      if ( ((_BYTE)v0[3] & 1) != 0 )
      {
        FreeAO(v0);
      }
      else
      {
        *((_DWORD *)v0 + 11) = v1;
        SetEvent(v0[6]);
      }
      lastSeen = 13;
    }
    else if ( gfInitSyncsFinished )
    {
      v2 = dword_180528678;
      CurrentThread = GetCurrentThread();
      SetThreadPriority(CurrentThread, v2);
    }
    _InterlockedDecrement(&ulcActiveReplicationThreads);
    ReleaseMutex(hmtxAsyncThread);
  }
  fAsyncThreadExists = 0;
  return 0;
}

```

## disassembly

```asm
0x1802b2860  push    rbx
0x1802b2862  sub     rsp, 60h
0x1802b2866  mov     [rsp+68h+var_38], 0
0x1802b286e  mov     [rsp+68h+var_34], 0
0x1802b2876  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1802b2879  mov     rcx, cs:hevDRASetup; hHandle
0x1802b2880  call    cs:__imp_WaitForSingleObject
0x1802b2886  mov     eax, cs:eServiceShutdown
0x1802b288c  test    eax, eax
0x1802b288e  jnz     loc_1802B29D1
0x1802b2894  xorps   xmm0, xmm0
0x1802b2897  movups  xmmword ptr [rsp+68h+Handles], xmm0
0x1802b289c  mov     cs:fAsyncThreadAlive, 1
0x1802b28a6  mov     rax, cs:hevEntriesInAOList
0x1802b28ad  mov     [rsp+68h+Handles], rax
0x1802b28b2  mov     rax, cs:hServDoneEvent
0x1802b28b9  mov     [rsp+68h+Handles+8], rax
0x1802b28be  mov     r9d, 1B7740h; dwMilliseconds
0x1802b28c4  xor     r8d, r8d; bWaitAll
0x1802b28c7  lea     rdx, [rsp+68h+Handles]; lpHandles
0x1802b28cc  lea     ecx, [r8+2]; nCount
0x1802b28d0  call    cs:__imp_WaitForMultipleObjects
0x1802b28d6  mov     eax, cs:eServiceShutdown
0x1802b28dc  test    eax, eax
0x1802b28de  jnz     loc_1802B29D1
0x1802b28e4  cmp     cs:dsaUserMode, 1
0x1802b28eb  jz      loc_1802B29D1
0x1802b28f1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1802b28f4  mov     rcx, cs:hmtxAsyncThread; hHandle
0x1802b28fb  call    cs:__imp_WaitForSingleObject
0x1802b2901  lock inc cs:ulcActiveReplicationThreads
0x1802b2908  nop
0x1802b2909  lea     rcx, csAOList; lpCriticalSection
0x1802b2910  call    cs:__imp_EnterCriticalSection
0x1802b2916  nop
0x1802b2917  mov     rbx, cs:paoFirst
0x1802b291e  test    rbx, rbx
0x1802b2921  jz      short loc_1802B292D
0x1802b2923  mov     rax, [rbx]
0x1802b2926  mov     cs:paoFirst, rax
0x1802b292d  mov     [rsp+68h+var_28], rbx
0x1802b2932  test    rbx, rbx
0x1802b2935  jnz     short loc_1802B2945
0x1802b2937  mov     rcx, cs:hevEntriesInAOList; hEvent
0x1802b293e  call    cs:__imp_ResetEvent
0x1802b2944  nop
0x1802b2945  lea     rcx, csAOList; lpCriticalSection
0x1802b294c  call    cs:__imp_LeaveCriticalSection
0x1802b2952  test    rbx, rbx
0x1802b2955  jz      short loc_1802B2992
0x1802b2957  mov     cs:lastSeen, 0Ch
0x1802b2961  mov     rcx, rbx; __int64
0x1802b2964  call    DispatchPao
0x1802b2969  test    byte ptr [rbx+18h], 1
0x1802b296d  jz      short loc_1802B2979
0x1802b296f  mov     rcx, rbx; void *
0x1802b2972  call    FreeAO
0x1802b2977  jmp     short loc_1802B2986
0x1802b2979  mov     [rbx+2Ch], eax
0x1802b297c  mov     rcx, [rbx+30h]; hEvent
0x1802b2980  call    cs:__imp_SetEvent
0x1802b2986  mov     cs:lastSeen, 0Dh
0x1802b2990  jmp     short loc_1802B29B3
0x1802b2992  cmp     cs:gfInitSyncsFinished, 0
0x1802b2999  jz      short loc_1802B29B3
0x1802b299b  mov     ebx, cs:dword_180528678
0x1802b29a1  call    cs:__imp_GetCurrentThread
0x1802b29a7  mov     rcx, rax; hThread
0x1802b29aa  mov     edx, ebx; nPriority
0x1802b29ac  call    cs:__imp_SetThreadPriority
0x1802b29b2  nop
0x1802b29b3  lock dec cs:ulcActiveReplicationThreads
0x1802b29ba  mov     rcx, cs:hmtxAsyncThread; hMutex
0x1802b29c1  call    cs:__imp_ReleaseMutex
0x1802b29c7  jmp     loc_1802B2886
0x1802b29cc  jmp     loc_1802B2908
0x1802b29d1  jmp     short loc_1802B29F2
0x1802b29d3  mov     cs:fAsyncThreadAlive, 0
0x1802b29dd  mov     cs:fAsyncThreadExists, 0
0x1802b29e7  mov     ecx, [rsp+68h+var_38]
0x1802b29eb  call    cs:__imp__o__endthreadex
0x1802b29f1  nop
0x1802b29f2  mov     cs:fAsyncThreadExists, 0
0x1802b29fc  xor     eax, eax
0x1802b29fe  add     rsp, 60h
0x1802b2a02  pop     rbx
0x1802b2a03  retn
0x18046c765  push    rbp
0x18046c767  sub     rsp, 30h
0x18046c76b  mov     rbp, rdx
0x18046c76e  mov     rdx, [rcx]
0x18046c771  mov     edx, [rdx]
0x18046c773  mov     r8d, 1010340h
0x18046c779  call    DoHandleMostExceptions
0x18046c77e  nop
0x18046c77f  add     rsp, 30h
0x18046c783  pop     rbp
0x18046c784  retn
0x18046c786  push    rbp
0x18046c788  sub     rsp, 30h
0x18046c78c  mov     rbp, rdx
0x18046c78f  lea     rcx, csAOList; lpCriticalSection
0x18046c796  call    cs:__imp_LeaveCriticalSection
0x18046c79c  nop
0x18046c79d  add     rsp, 30h
0x18046c7a1  pop     rbp
0x18046c7a2  retn
0x18046c7a4  push    rbp
0x18046c7a6  sub     rsp, 30h
0x18046c7aa  mov     rbp, rdx
0x18046c7ad  lock dec cs:ulcActiveReplicationThreads
0x18046c7b4  mov     rcx, cs:hmtxAsyncThread; hMutex
0x18046c7bb  call    cs:__imp_ReleaseMutex
0x18046c7c1  nop
0x18046c7c2  add     rsp, 30h
0x18046c7c6  pop     rbp
0x18046c7c7  retn
0x18046c7c9  push    rbp
0x18046c7cb  sub     rsp, 30h
0x18046c7cf  mov     rbp, rdx
0x18046c7d2  lea     rax, [rbp+34h]
0x18046c7d6  mov     [rsp+38h+Handles+8], rax
0x18046c7db  mov     [rsp+38h+Handles], 0
0x18046c7e4  lea     r9, [rbp+38h]
0x18046c7e8  lea     r8, [rbp+48h]
0x18046c7ec  lea     rdx, [rbp+30h]
0x18046c7f0  call    GetExceptionDataEx
0x18046c7f5  nop
0x18046c7f6  add     rsp, 30h
0x18046c7fa  pop     rbp
0x18046c7fb  retn
```
