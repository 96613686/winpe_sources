# AlgCleanupProtocol(void)

- ea: `0x180086950`
- end: `0x180086a77`
- name: `?AlgCleanupProtocol@@YAXXZ`
- size: `295`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ca20`
- `0x18003afe4`
- `0x180086950`
- `0x180087e08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008699a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008699a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800869ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800869ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180086a21`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180086a21`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800869d5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800869d5`
- `ntdll!NtClose` at `0x1800869f8`
- `ntdll!NtClose` at `0x1800869f8`

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
0x180086950  mov     [rsp+arg_0], rbx
0x180086955  push    rsi
0x180086956  sub     rsp, 20h
0x18008695a  mov     rcx, cs:WPP_GLOBAL_Control
0x180086961  lea     rsi, WPP_GLOBAL_Control
0x180086968  cmp     rcx, rsi
0x18008696b  jz      short loc_18008698E
0x18008696d  test    byte ptr [rcx+1Ch], 1
0x180086971  jz      short loc_18008698E
0x180086973  cmp     byte ptr [rcx+19h], 6
0x180086977  jb      short loc_18008698E
0x180086979  mov     rcx, [rcx+10h]
0x18008697d  lea     r8, WPP_98163cc445f73b00785e759405df1b1d_Traceguids
0x180086984  mov     edx, 14h
0x180086989  call    WPP_SF_
0x18008698e  mov     rbx, cs:?AlgGlobalInfo@@3PEAUIP_ALG_GLOBAL_INFO@@EA; IP_ALG_GLOBAL_INFO * AlgGlobalInfo
0x180086995  test    rbx, rbx
0x180086998  jz      short loc_1800869C5
0x18008699a  call    cs:__imp_GetProcessHeap
0x1800869a1  nop     dword ptr [rax+rax+00h]
0x1800869a6  mov     r8, rbx; lpMem
0x1800869a9  xor     edx, edx; dwFlags
0x1800869ab  mov     rcx, rax; hHeap
0x1800869ae  call    cs:__imp_HeapFree
0x1800869b5  nop     dword ptr [rax+rax+00h]
0x1800869ba  mov     cs:?AlgGlobalInfo@@3PEAUIP_ALG_GLOBAL_INFO@@EA, 0; IP_ALG_GLOBAL_INFO * AlgGlobalInfo
0x1800869c5  mov     rcx, cs:?AlgTimerQueueHandle@@3PEAXEA; TimerQueue
0x1800869cc  test    rcx, rcx
0x1800869cf  jz      short loc_1800869EC
0x1800869d1  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800869d5  call    cs:__imp_DeleteTimerQueueEx
0x1800869dc  nop     dword ptr [rax+rax+00h]
0x1800869e1  mov     cs:?AlgTimerQueueHandle@@3PEAXEA, 0; void * AlgTimerQueueHandle
0x1800869ec  mov     rcx, cs:?AlgTranslatorHandle@@3PEAXEA; Handle
0x1800869f3  test    rcx, rcx
0x1800869f6  jz      short loc_180086A0F
0x1800869f8  call    cs:__imp_NtClose
0x1800869ff  nop     dword ptr [rax+rax+00h]
0x180086a04  mov     cs:?AlgTranslatorHandle@@3PEAXEA, 0; void * AlgTranslatorHandle
0x180086a0f  mov     eax, 1
0x180086a14  xchg    eax, cs:?AlgProtocolStopped@@3KA; ulong AlgProtocolStopped
0x180086a1a  mov     rcx, cs:?AlgNotificationEvent@@3PEAXEA; hEvent
0x180086a21  call    cs:__imp_SetEvent
0x180086a28  nop     dword ptr [rax+rax+00h]
0x180086a2d  lea     rcx, ?AlgComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180086a34  call    ?ResetComponentReference@@YAXPEAU_COMPONENT_REFERENCE@@@Z; ResetComponentReference(_COMPONENT_REFERENCE *)
0x180086a39  call    ?FreeAlgControllerInterface@@YAXXZ; FreeAlgControllerInterface(void)
0x180086a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180086a45  cmp     rcx, rsi
0x180086a48  jz      short loc_180086A6B
0x180086a4a  test    byte ptr [rcx+1Ch], 1
0x180086a4e  jz      short loc_180086A6B
0x180086a50  cmp     byte ptr [rcx+19h], 6
0x180086a54  jb      short loc_180086A6B
0x180086a56  mov     rcx, [rcx+10h]
0x180086a5a  lea     r8, WPP_98163cc445f73b00785e759405df1b1d_Traceguids
0x180086a61  mov     edx, 15h
0x180086a66  call    WPP_SF_
0x180086a6b  mov     rbx, [rsp+28h+arg_0]
0x180086a70  add     rsp, 20h
0x180086a74  pop     rsi
0x180086a75  retn
```
