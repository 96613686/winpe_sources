# CreatePhysicalInterfaceTimer(void)

- ea: `0x1800ca664`
- end: `0x1800ca816`
- name: `?CreatePhysicalInterfaceTimer@@YAKXZ`
- size: `434`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004a944`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x1800ca664`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ca703`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ca703`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca7d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ca7d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca6bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca7a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca6bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca7a3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800ca720`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800ca720`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800ca799`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800ca799`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800ca6ad`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800ca6ad`

## pseudocode

```c
__int64 CreatePhysicalInterfaceTimer(void)
{
  DWORD v0; // ebx
  DWORD LastError; // eax
  PVOID *v2; // rcx
  DWORD v3; // eax
  DWORD v4; // eax

  v0 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
  if ( g_hTimerQueue )
    goto LABEL_10;
  g_hTimerQueue = CreateTimerQueue();
  if ( g_hTimerQueue )
    goto LABEL_10;
  LastError = GetLastError();
  v0 = LastError;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, LastError);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v0 )
  {
LABEL_10:
    EnterCriticalSection(&g_csInterfaceContext);
    if ( !g_hPhysicalInterfaceCallbackTimeoutTimer )
      goto LABEL_19;
    if ( DeleteTimerQueueTimer(g_hTimerQueue, g_hPhysicalInterfaceCallbackTimeoutTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      g_hPhysicalInterfaceCallbackTimeoutTimer = 0;
    }
    else
    {
      v3 = GetLastError();
      v0 = v3;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v3);
    }
    if ( !v0 )
    {
LABEL_19:
      if ( !CreateTimerQueueTimer(
              &g_hPhysicalInterfaceCallbackTimeoutTimer,
              g_hTimerQueue,
              NetworkListManager::PhysicalInterfaceTimeOutTimerCallback,
              0,
              0x2710u,
              0,
              0) )
      {
        v4 = GetLastError();
        v0 = v4;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v4);
      }
    }
    LeaveCriticalSection(&g_csInterfaceContext);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(v2[2], 94, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x1800ca664  mov     [rsp+arg_0], rbx
0x1800ca669  mov     [rsp+arg_8], rbp
0x1800ca66e  push    rsi
0x1800ca66f  sub     rsp, 40h
0x1800ca673  xor     ebx, ebx
0x1800ca675  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca67c  lea     rsi, WPP_GLOBAL_Control
0x1800ca683  lea     rbp, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800ca68a  cmp     rcx, rsi
0x1800ca68d  jz      short loc_1800CA6A4
0x1800ca68f  test    byte ptr [rcx+1Ch], 8
0x1800ca693  jz      short loc_1800CA6A4
0x1800ca695  mov     rcx, [rcx+10h]
0x1800ca699  lea     edx, [rbx+5Ah]
0x1800ca69c  mov     r8, rbp
0x1800ca69f  call    WPP_SF_
0x1800ca6a4  cmp     cs:?g_hTimerQueue@@3PEAXEA, rbx; void * g_hTimerQueue
0x1800ca6ab  jnz     short loc_1800CA6FC
0x1800ca6ad  call    cs:__imp_CreateTimerQueue
0x1800ca6b3  mov     cs:?g_hTimerQueue@@3PEAXEA, rax; void * g_hTimerQueue
0x1800ca6ba  test    rax, rax
0x1800ca6bd  jnz     short loc_1800CA6FC
0x1800ca6bf  call    cs:__imp_GetLastError
0x1800ca6c5  mov     ebx, eax
0x1800ca6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca6ce  cmp     rcx, rsi
0x1800ca6d1  jz      short loc_1800CA6F4
0x1800ca6d3  test    byte ptr [rcx+1Ch], 1
0x1800ca6d7  jz      short loc_1800CA6F4
0x1800ca6d9  mov     rcx, [rcx+10h]
0x1800ca6dd  mov     edx, 5Bh ; '['
0x1800ca6e2  mov     r9d, eax
0x1800ca6e5  mov     r8, rbp
0x1800ca6e8  call    WPP_SF_d
0x1800ca6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca6f4  test    ebx, ebx
0x1800ca6f6  jnz     loc_1800CA7E5
0x1800ca6fc  lea     rcx, ?g_csInterfaceContext@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800ca703  call    cs:__imp_EnterCriticalSection
0x1800ca709  mov     rdx, cs:?g_hPhysicalInterfaceCallbackTimeoutTimer@@3PEAXEA; Timer
0x1800ca710  test    rdx, rdx
0x1800ca713  jz      short loc_1800CA769
0x1800ca715  mov     rcx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x1800ca71c  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800ca720  call    cs:__imp_DeleteTimerQueueTimer
0x1800ca726  test    eax, eax
0x1800ca728  jnz     short loc_1800CA75A
0x1800ca72a  call    cs:__imp_GetLastError
0x1800ca730  mov     ebx, eax
0x1800ca732  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca739  cmp     rcx, rsi
0x1800ca73c  jz      short loc_1800CA765
0x1800ca73e  test    byte ptr [rcx+1Ch], 1
0x1800ca742  jz      short loc_1800CA765
0x1800ca744  mov     rcx, [rcx+10h]
0x1800ca748  mov     edx, 5Ch ; '\'
0x1800ca74d  mov     r9d, eax
0x1800ca750  mov     r8, rbp
0x1800ca753  call    WPP_SF_d
0x1800ca758  jmp     short loc_1800CA765
0x1800ca75a  mov     cs:?g_hPhysicalInterfaceCallbackTimeoutTimer@@3PEAXEA, 0; void * g_hPhysicalInterfaceCallbackTimeoutTimer
0x1800ca765  test    ebx, ebx
0x1800ca767  jnz     short loc_1800CA7D1
0x1800ca769  mov     rdx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x1800ca770  lea     r8, ?PhysicalInterfaceTimeOutTimerCallback@NetworkListManager@@SAXPEAXE@Z; Callback
0x1800ca777  mov     [rsp+48h+Flags], 0; Flags
0x1800ca77f  lea     rcx, ?g_hPhysicalInterfaceCallbackTimeoutTimer@@3PEAXEA; phNewTimer
0x1800ca786  mov     [rsp+48h+Period], 0; Period
0x1800ca78e  xor     r9d, r9d; Parameter
0x1800ca791  mov     [rsp+48h+DueTime], 2710h; DueTime
0x1800ca799  call    cs:__imp_CreateTimerQueueTimer
0x1800ca79f  test    eax, eax
0x1800ca7a1  jnz     short loc_1800CA7D1
0x1800ca7a3  call    cs:__imp_GetLastError
0x1800ca7a9  mov     ebx, eax
0x1800ca7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca7b2  cmp     rcx, rsi
0x1800ca7b5  jz      short loc_1800CA7D1
0x1800ca7b7  test    byte ptr [rcx+1Ch], 1
0x1800ca7bb  jz      short loc_1800CA7D1
0x1800ca7bd  mov     rcx, [rcx+10h]
0x1800ca7c1  mov     edx, 5Dh ; ']'
0x1800ca7c6  mov     r9d, eax
0x1800ca7c9  mov     r8, rbp
0x1800ca7cc  call    WPP_SF_d
0x1800ca7d1  lea     rcx, ?g_csInterfaceContext@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800ca7d8  call    cs:__imp_LeaveCriticalSection
0x1800ca7de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca7e5  cmp     rcx, rsi
0x1800ca7e8  jz      short loc_1800CA804
0x1800ca7ea  test    byte ptr [rcx+1Ch], 8
0x1800ca7ee  jz      short loc_1800CA804
0x1800ca7f0  mov     rcx, [rcx+10h]
0x1800ca7f4  mov     edx, 5Eh ; '^'
0x1800ca7f9  mov     r9d, ebx
0x1800ca7fc  mov     r8, rbp
0x1800ca7ff  call    WPP_SF_d
0x1800ca804  mov     rbp, [rsp+48h+arg_8]
0x1800ca809  mov     eax, ebx
0x1800ca80b  mov     rbx, [rsp+48h+arg_0]
0x1800ca810  add     rsp, 40h
0x1800ca814  pop     rsi
0x1800ca815  retn
```
