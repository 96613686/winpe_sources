# AlgCleanupProtocol(void)

- ea: `0x1800803a0`
- end: `0x1800804a8`
- name: `?AlgCleanupProtocol@@YAXXZ`
- size: `264`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c110`
- `0x180038204`
- `0x1800803a0`
- `0x1800817c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800803ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800803ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800803f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800803f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180080459`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180080459`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180080419`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180080419`
- `ntdll!NtClose` at `0x180080436`
- `ntdll!NtClose` at `0x180080436`

## pseudocode

```c
void AlgCleanupProtocol(void)
{
  void *v0; // rbx
  HANDLE ProcessHeap; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
  }
  v0 = AlgGlobalInfo;
  if ( AlgGlobalInfo )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v0);
    AlgGlobalInfo = 0;
  }
  if ( AlgTimerQueueHandle )
  {
    DeleteTimerQueueEx(AlgTimerQueueHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    AlgTimerQueueHandle = 0;
  }
  if ( AlgTranslatorHandle )
  {
    NtClose(AlgTranslatorHandle);
    AlgTranslatorHandle = 0;
  }
  _InterlockedExchange((volatile __int32 *)&AlgProtocolStopped, 1);
  SetEvent(AlgNotificationEvent);
  ResetComponentReference((struct _COMPONENT_REFERENCE *)&AlgComponentReference);
  FreeAlgControllerInterface();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
  }
}

```

## disassembly

```asm
0x1800803a0  mov     [rsp+arg_0], rbx
0x1800803a5  push    rsi
0x1800803a6  sub     rsp, 20h
0x1800803aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800803b1  lea     rsi, WPP_GLOBAL_Control
0x1800803b8  cmp     rcx, rsi
0x1800803bb  jz      short loc_1800803DE
0x1800803bd  test    byte ptr [rcx+1Ch], 1
0x1800803c1  jz      short loc_1800803DE
0x1800803c3  cmp     byte ptr [rcx+19h], 6
0x1800803c7  jb      short loc_1800803DE
0x1800803c9  mov     rcx, [rcx+10h]
0x1800803cd  lea     r8, WPP_98163cc445f73b00785e759405df1b1d_Traceguids
0x1800803d4  mov     edx, 14h
0x1800803d9  call    WPP_SF_
0x1800803de  mov     rbx, cs:?AlgGlobalInfo@@3PEAUIP_ALG_GLOBAL_INFO@@EA; IP_ALG_GLOBAL_INFO * AlgGlobalInfo
0x1800803e5  test    rbx, rbx
0x1800803e8  jz      short loc_180080409
0x1800803ea  call    cs:__imp_GetProcessHeap
0x1800803f0  mov     r8, rbx; lpMem
0x1800803f3  xor     edx, edx; dwFlags
0x1800803f5  mov     rcx, rax; hHeap
0x1800803f8  call    cs:__imp_HeapFree
0x1800803fe  mov     cs:?AlgGlobalInfo@@3PEAUIP_ALG_GLOBAL_INFO@@EA, 0; IP_ALG_GLOBAL_INFO * AlgGlobalInfo
0x180080409  mov     rcx, cs:?AlgTimerQueueHandle@@3PEAXEA; TimerQueue
0x180080410  test    rcx, rcx
0x180080413  jz      short loc_18008042A
0x180080415  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180080419  call    cs:__imp_DeleteTimerQueueEx
0x18008041f  mov     cs:?AlgTimerQueueHandle@@3PEAXEA, 0; void * AlgTimerQueueHandle
0x18008042a  mov     rcx, cs:?AlgTranslatorHandle@@3PEAXEA; Handle
0x180080431  test    rcx, rcx
0x180080434  jz      short loc_180080447
0x180080436  call    cs:__imp_NtClose
0x18008043c  mov     cs:?AlgTranslatorHandle@@3PEAXEA, 0; void * AlgTranslatorHandle
0x180080447  mov     eax, 1
0x18008044c  xchg    eax, cs:?AlgProtocolStopped@@3KA; ulong AlgProtocolStopped
0x180080452  mov     rcx, cs:?AlgNotificationEvent@@3PEAXEA; hEvent
0x180080459  call    cs:__imp_SetEvent
0x18008045f  lea     rcx, ?AlgComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180080466  call    ?ResetComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; ResetComponentReference(_COMPONENT_REFERENCE *)
0x18008046b  call    ?FreeAlgControllerInterface@@YAXXZ; FreeAlgControllerInterface(void)
0x180080470  mov     rcx, cs:WPP_GLOBAL_Control
0x180080477  cmp     rcx, rsi
0x18008047a  jz      short loc_18008049D
0x18008047c  test    byte ptr [rcx+1Ch], 1
0x180080480  jz      short loc_18008049D
0x180080482  cmp     byte ptr [rcx+19h], 6
0x180080486  jb      short loc_18008049D
0x180080488  mov     rcx, [rcx+10h]
0x18008048c  lea     r8, WPP_98163cc445f73b00785e759405df1b1d_Traceguids
0x180080493  mov     edx, 15h
0x180080498  call    WPP_SF_
0x18008049d  mov     rbx, [rsp+28h+arg_0]
0x1800804a2  add     rsp, 20h
0x1800804a6  pop     rsi
0x1800804a7  retn
```
