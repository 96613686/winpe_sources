# AlgRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)

- ea: `0x180081400`
- end: `0x180081648`
- name: `?AlgRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z`
- size: `584`
- prototype: `__int64 __fastcall(void *, struct _SUPPORT_FUNCTIONS_50 *, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x180032024`
- `0x18004ed64`
- `0x180081400`
- `0x1800818e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800814aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800814aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800814bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800814bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800814a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800814a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800815fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800815fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800815c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800815c3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800815b1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x1800815b1`

## pseudocode

```c
__int64 __fastcall AlgRmStartProtocol(void *a1, struct _SUPPORT_FUNCTIONS_50 *a2, _QWORD *a3)
{
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  ULONG LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
  }
  if ( !AcquireComponentReference(&AlgComponentReference) )
    return 1003;
  if ( a3 )
  {
    EnterCriticalSection(&AlgGlobalInfoLock);
    ProcessHeap = GetProcessHeap();
    v7 = 8;
    AlgGlobalInfo = HeapAlloc(ProcessHeap, 8u, 8u);
    if ( !AlgGlobalInfo )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
      }
      goto LABEL_33;
    }
    *(_QWORD *)AlgGlobalInfo = *a3;
    AlgNotificationEvent = a1;
    if ( a2 )
      AlgSupportFunctions = *a2;
    else
      memset_0(&AlgSupportFunctions, 0, sizeof(AlgSupportFunctions));
    LastError = NatOpenDriver(&AlgTranslatorHandle);
    v7 = LastError;
    if ( LastError )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 34;
LABEL_26:
        WPP_SF_d(v10[2], v11, WPP_98163cc445f73b00785e759405df1b1d_Traceguids, LastError);
      }
    }
    else
    {
      AlgTimerQueueHandle = CreateTimerQueue();
      if ( AlgTimerQueueHandle )
      {
        Initialise_ALG();
        _InterlockedExchange((volatile __int32 *)&AlgProtocolStopped, 0);
        goto LABEL_33;
      }
      LastError = GetLastError();
      v7 = LastError;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 35;
        goto LABEL_26;
      }
    }
LABEL_33:
    LeaveCriticalSection(&AlgGlobalInfoLock);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
    }
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
  }
  v7 = 87;
LABEL_37:
  ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&AlgComponentReference);
  return v7;
}

```

## disassembly

```asm
0x180081400  push    rbx
0x180081402  push    rbp
0x180081403  push    rsi
0x180081404  push    rdi
0x180081405  push    r12
0x180081407  push    r15
0x180081409  sub     rsp, 28h
0x18008140d  mov     rsi, r8
0x180081410  mov     rdi, rdx
0x180081413  mov     rbp, rcx
0x180081416  mov     rcx, cs:WPP_GLOBAL_Control
0x18008141d  lea     r15, WPP_GLOBAL_Control
0x180081424  lea     r12, WPP_98163cc445f73b00785e759405df1b1d_Traceguids
0x18008142b  cmp     rcx, r15
0x18008142e  jz      short loc_18008144D
0x180081430  test    byte ptr [rcx+1Ch], 1
0x180081434  jz      short loc_18008144D
0x180081436  cmp     byte ptr [rcx+19h], 6
0x18008143a  jb      short loc_18008144D
0x18008143c  mov     rcx, [rcx+10h]
0x180081440  mov     edx, 1Fh
0x180081445  mov     r8, r12
0x180081448  call    WPP_SF_
0x18008144d  lea     rcx, ?AlgComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x180081454  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x180081459  test    al, al
0x18008145b  jnz     short loc_180081467
0x18008145d  mov     eax, 3EBh
0x180081462  jmp     loc_18008163B
0x180081467  test    rsi, rsi
0x18008146a  jnz     short loc_18008149D
0x18008146c  mov     rcx, cs:WPP_GLOBAL_Control
0x180081473  cmp     rcx, r15
0x180081476  jz      short loc_180081493
0x180081478  test    byte ptr [rcx+1Ch], 1
0x18008147c  jz      short loc_180081493
0x18008147e  cmp     byte ptr [rcx+19h], 6
0x180081482  jb      short loc_180081493
0x180081484  mov     rcx, [rcx+10h]
0x180081488  lea     edx, [rsi+20h]
0x18008148b  mov     r8, r12
0x18008148e  call    WPP_SF_
0x180081493  mov     ebx, 57h ; 'W'
0x180081498  jmp     loc_18008162D
0x18008149d  lea     rcx, ?AlgGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800814a4  call    cs:__imp_EnterCriticalSection
0x1800814aa  call    cs:__imp_GetProcessHeap
0x1800814b0  mov     ebx, 8
0x1800814b5  mov     rcx, rax; hHeap
0x1800814b8  mov     r8d, ebx; dwBytes
0x1800814bb  mov     edx, ebx; dwFlags
0x1800814bd  call    cs:__imp_HeapAlloc
0x1800814c3  mov     cs:?AlgGlobalInfo@@3PEAUIP_ALG_GLOBAL_INFO@@EA, rax; IP_ALG_GLOBAL_INFO * AlgGlobalInfo
0x1800814ca  mov     rcx, rax
0x1800814cd  test    rax, rax
0x1800814d0  jnz     short loc_18008150A
0x1800814d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800814d9  cmp     rcx, r15
0x1800814dc  jz      loc_1800815F7
0x1800814e2  test    byte ptr [rcx+1Ch], 1
0x1800814e6  jz      loc_1800815F7
0x1800814ec  cmp     byte ptr [rcx+19h], 2
0x1800814f0  jb      loc_1800815F7
0x1800814f6  mov     rcx, [rcx+10h]
0x1800814fa  lea     edx, [rbx+19h]
0x1800814fd  mov     r8, r12
0x180081500  call    WPP_SF_
0x180081505  jmp     loc_1800815F7
0x18008150a  mov     rax, [rsi]
0x18008150d  mov     [rcx], rax
0x180081510  mov     cs:?AlgNotificationEvent@@3PEAXEA, rbp; void * AlgNotificationEvent
0x180081517  test    rdi, rdi
0x18008151a  jnz     short loc_180081530
0x18008151c  xor     edx, edx; Val
0x18008151e  lea     r8d, [rdi+60h]; Size
0x180081522  lea     rcx, ?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A; void *
0x180081529  call    memset_0
0x18008152e  jmp     short loc_180081571
0x180081530  movups  xmm0, xmmword ptr [rdi]
0x180081533  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A, xmm0; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x18008153a  movups  xmm1, xmmword ptr [rdi+10h]
0x18008153e  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+10h, xmm1; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180081545  movups  xmm0, xmmword ptr [rdi+20h]
0x180081549  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+20h, xmm0; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180081550  movups  xmm1, xmmword ptr [rdi+30h]
0x180081554  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+30h, xmm1; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x18008155b  movups  xmm0, xmmword ptr [rdi+40h]
0x18008155f  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+40h, xmm0; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180081566  movups  xmm1, xmmword ptr [rdi+50h]
0x18008156a  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+50h, xmm1; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180081571  lea     rcx, ?AlgTranslatorHandle@@3PEAXEA; FileHandle
0x180081578  call    NatOpenDriver
0x18008157d  mov     ebx, eax
0x18008157f  test    eax, eax
0x180081581  jz      short loc_1800815B1
0x180081583  mov     rcx, cs:WPP_GLOBAL_Control
0x18008158a  cmp     rcx, r15
0x18008158d  jz      short loc_1800815F7
0x18008158f  test    byte ptr [rcx+1Ch], 1
0x180081593  jz      short loc_1800815F7
0x180081595  cmp     byte ptr [rcx+19h], 2
0x180081599  jb      short loc_1800815F7
0x18008159b  mov     edx, 22h ; '"'
0x1800815a0  mov     rcx, [rcx+10h]
0x1800815a4  mov     r9d, eax
0x1800815a7  mov     r8, r12
0x1800815aa  call    WPP_SF_d
0x1800815af  jmp     short loc_1800815F7
0x1800815b1  call    cs:__imp_CreateTimerQueue
0x1800815b7  mov     cs:?AlgTimerQueueHandle@@3PEAXEA, rax; void * AlgTimerQueueHandle
0x1800815be  test    rax, rax
0x1800815c1  jnz     short loc_1800815EA
0x1800815c3  call    cs:__imp_GetLastError
0x1800815c9  mov     ebx, eax
0x1800815cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800815d2  cmp     rcx, r15
0x1800815d5  jz      short loc_1800815F7
0x1800815d7  test    byte ptr [rcx+1Ch], 1
0x1800815db  jz      short loc_1800815F7
0x1800815dd  cmp     byte ptr [rcx+19h], 2
0x1800815e1  jb      short loc_1800815F7
0x1800815e3  mov     edx, 23h ; '#'
0x1800815e8  jmp     short loc_1800815A0
0x1800815ea  call    ?Initialise_ALG@@YAJXZ; Initialise_ALG(void)
0x1800815ef  xor     eax, eax
0x1800815f1  xchg    eax, cs:?AlgProtocolStopped@@3KA; ulong AlgProtocolStopped
0x1800815f7  lea     rcx, ?AlgGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800815fe  call    cs:__imp_LeaveCriticalSection
0x180081604  mov     rcx, cs:WPP_GLOBAL_Control
0x18008160b  cmp     rcx, r15
0x18008160e  jz      short loc_18008162D
0x180081610  test    byte ptr [rcx+1Ch], 1
0x180081614  jz      short loc_18008162D
0x180081616  cmp     byte ptr [rcx+19h], 6
0x18008161a  jb      short loc_18008162D
0x18008161c  mov     rcx, [rcx+10h]
0x180081620  mov     edx, 24h ; '$'
0x180081625  mov     r8, r12
0x180081628  call    WPP_SF_
0x18008162d  lea     rcx, ?AlgComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180081634  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180081639  mov     eax, ebx
0x18008163b  add     rsp, 28h
0x18008163f  pop     r15
0x180081641  pop     r12
0x180081643  pop     rdi
0x180081644  pop     rsi
0x180081645  pop     rbp
0x180081646  pop     rbx
0x180081647  retn
```
