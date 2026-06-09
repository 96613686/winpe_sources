# DaSiteMgrCreateInstance

- ea: `0x18006feb8`
- end: `0x18007024a`
- name: `DaSiteMgrCreateInstance`
- size: `914`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task`

## callers

- `0x18003a930`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180012dbc`
- `0x18002da48`
- `0x180035d0c`
- `0x180039220`
- `0x180039c68`
- `0x180041390`
- `0x180041fe8`
- `0x180042f6c`
- `0x1800459a4`
- `0x18006fe78`
- `0x18006feb8`
- `0x180070664`
- `0x18007078c`
- `0x1800707bc`
- `0x180071994`
- `0x180073514`
- `0x180076dac`
- `0x180076e04`
- `0x180079e40`
- `0x180079fec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800700c6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800700c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070132`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070132`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ff21`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ff7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ffd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fffa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ff21`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ff7b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ffd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fffa`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006fee8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006fefb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006ffaf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180070086`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006fee8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006fefb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006ffaf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180070086`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007019d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007022a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007019d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007022a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070176`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070189`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007020b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070176`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070189`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007020b`

## string_xrefs

- `0x1800700e1`: `onecoreuap\net\netio\iphlpsvc\service\stmgri.c`
- `0x180070117`: `onecoreuap\net\netio\iphlpsvc\service\stmgri.c`
- `0x1800700f0`: `DaSiteMgrCreateInstance queueing DaSiteMgrInitializeEvt event, event type %d`

## pseudocode

```c
__int64 DaSiteMgrCreateInstance()
{
  LPCRITICAL_SECTION v0; // rbx
  struct _RTL_CRITICAL_SECTION *v1; // rcx
  HANDLE EventW; // rax
  HANDLE v3; // rax
  HANDLE v4; // rax
  __int64 v5; // rax
  __int64 v6; // r8
  HANDLE OwningThread; // rcx

  v0 = g_DaSiteMgrInstance;
  if ( g_DaSiteMgrInstance[3].OwningThread == &g_DaSiteMgrInstance[3].OwningThread )
    return 0;
  v1 = g_DaSiteMgrInstance;
  g_DaSiteMgrInstance[3].LockCount = 0;
  InitializeCriticalSection(v1);
  InitializeCriticalSection(&g_DaSiteMgrAdTableLock);
  g_DaSiteMgrAdSiteTable = 0;
  g_DaSiteMgrReferenceObjectEvent = CreateEventW(0, 1, 1, 0);
  if ( !g_DaSiteMgrReferenceObjectEvent )
  {
LABEL_28:
    DaSiteMgrAdTableUninitialize();
    DeleteCriticalSection(v0);
    return 0;
  }
  if ( !(unsigned int)InitializeWorkQueue(v0 + 1) )
  {
LABEL_27:
    CloseHandle(g_DaSiteMgrReferenceObjectEvent);
    g_DaSiteMgrReferenceObjectEvent = 0;
    goto LABEL_28;
  }
  StartWorkQueue(&v0[1]);
  if ( !(unsigned int)DaSiteMgrStatePrepareNetLocalityAddressTable(v0) )
  {
LABEL_26:
    StopWorkQueue(&v0[1]);
    UninitializeWorkQueue(&v0[1]);
    goto LABEL_27;
  }
  EventW = CreateEventW(0, 1, 1, 0);
  v0[9].OwningThread = EventW;
  if ( !EventW )
  {
LABEL_22:
    if ( !*(_QWORD *)&v0[8].LockCount )
    {
      FREE(0);
      *(_QWORD *)&v0[8].LockCount = 0;
    }
    OwningThread = v0[8].OwningThread;
    if ( OwningThread )
    {
      FREE(OwningThread);
      v0[8].OwningThread = 0;
    }
    goto LABEL_26;
  }
  v0[10].SpinCount = (ULONG_PTR)&v0[10].LockSemaphore;
  v0[10].LockSemaphore = &v0[10].LockSemaphore;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v0 + 384));
  if ( (unsigned int)InitializeProbeApi() )
  {
LABEL_21:
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v0 + 384));
    CloseHandle(v0[9].OwningThread);
    goto LABEL_22;
  }
  v3 = CreateEventW(0, 1, 1, 0);
  *(_QWORD *)&v0[7].LockCount = v3;
  if ( !v3 )
  {
LABEL_20:
    CleanupProbeApi();
    goto LABEL_21;
  }
  v4 = CreateEventW(0, 1, 1, 0);
  v0[7].SpinCount = (ULONG_PTR)v4;
  if ( !v4 )
  {
LABEL_19:
    CloseHandle(*(HANDLE *)&v0[7].LockCount);
    goto LABEL_20;
  }
  if ( !(unsigned int)TpclCreateTimer(
                        &v0[7].LockSemaphore,
                        &word_180087660,
                        &DaSiteMgrStateTimerCallbackRoutine,
                        v0,
                        1,
                        0,
                        0) )
  {
LABEL_18:
    CloseHandle((HANDLE)v0[7].SpinCount);
    goto LABEL_19;
  }
  *(_QWORD *)&v0[12].LockCount = 0;
  v5 = MALLOC(0x30u);
  *(_QWORD *)&v0[12].LockCount = v5;
  if ( !v5 )
  {
LABEL_17:
    LOBYTE(v6) = 1;
    TpclDestroyTimer(&word_180087660, v0[7].LockSemaphore, v6, 0);
    goto LABEL_18;
  }
  *(_QWORD *)(v5 + 40) = 0;
  InitializeCriticalSection(*(LPCRITICAL_SECTION *)&v0[12].LockCount);
  if ( !(unsigned int)DaSiteMgrSubscribeToNetworkChanges(v0) )
  {
LABEL_16:
    NlmCacheUninitialize(*(LPCRITICAL_SECTION *)&v0[12].LockCount);
    goto LABEL_17;
  }
  if ( (unsigned int)UtillibRegisterCSNotification(&DaSiteMgrCsNotificationCallback, 0, &v0[5].LockSemaphore) )
  {
LABEL_15:
    DaSiteMgrUnsubscribeFromNetworkChanges(v0);
    goto LABEL_16;
  }
  ResetEvent(g_DaSiteMgrReferenceObjectEvent);
  g_DaSiteMgrReferenceObject = 2;
  DaSiteMgrInstanceReferenceEx("onecoreuap\\net\\netio\\iphlpsvc\\service\\stmgri.c", 200);
  EventWrite0(0x80000000LL, L"DaSiteMgrCreateInstance queueing DaSiteMgrInitializeEvt event, event type %d", 0);
  if ( !(unsigned int)DaSiteMgrEventQueue(0) )
  {
    _InterlockedDecrement(&g_DaSiteMgrReferenceObject);
    DaSiteMgrInstanceDereferenceEx("onecoreuap\\net\\netio\\iphlpsvc\\service\\stmgri.c", 217);
    WaitForSingleObject(g_DaSiteMgrReferenceObjectEvent, 0xFFFFFFFF);
    DaSiteMgrUnsubscribeFromCsEvents(v0);
    goto LABEL_15;
  }
  return 1;
}

```

## disassembly

```asm
0x18006feb8  push    rbx
0x18006feba  push    rsi
0x18006febb  push    rdi
0x18006febc  push    r14
0x18006febe  push    r15
0x18006fec0  sub     rsp, 40h
0x18006fec4  mov     rbx, cs:g_DaSiteMgrInstance
0x18006fecb  lea     rax, [rbx+88h]
0x18006fed2  cmp     [rax], rax
0x18006fed5  jz      loc_180070236
0x18006fedb  mov     rcx, rbx; lpCriticalSection
0x18006fede  mov     dword ptr [rbx+80h], 0
0x18006fee8  call    cs:__imp_InitializeCriticalSection
0x18006feef  nop     dword ptr [rax+rax+00h]
0x18006fef4  lea     rcx, g_DaSiteMgrAdTableLock; lpCriticalSection
0x18006fefb  call    cs:__imp_InitializeCriticalSection
0x18006ff02  nop     dword ptr [rax+rax+00h]
0x18006ff07  xor     r9d, r9d; lpName
0x18006ff0a  mov     cs:g_DaSiteMgrAdSiteTable, 0
0x18006ff15  xor     ecx, ecx; lpEventAttributes
0x18006ff17  lea     r15d, [r9+1]
0x18006ff1b  mov     r8d, r15d; bInitialState
0x18006ff1e  mov     edx, r15d; bManualReset
0x18006ff21  call    cs:__imp_CreateEventW
0x18006ff28  nop     dword ptr [rax+rax+00h]
0x18006ff2d  mov     cs:g_DaSiteMgrReferenceObjectEvent, rax
0x18006ff34  test    rax, rax
0x18006ff37  jz      loc_180070222
0x18006ff3d  lea     rdi, [rbx+28h]
0x18006ff41  mov     rcx, rdi; lpCriticalSection
0x18006ff44  lea     rdx, CallbackEnvironment
0x18006ff4b  call    InitializeWorkQueue
0x18006ff50  test    eax, eax
0x18006ff52  jz      loc_180070204
0x18006ff58  mov     rcx, rdi
0x18006ff5b  call    StartWorkQueue
0x18006ff60  mov     rcx, rbx
0x18006ff63  call    DaSiteMgrStatePrepareNetLocalityAddressTable
0x18006ff68  test    eax, eax
0x18006ff6a  jz      loc_1800701F4
0x18006ff70  xor     r9d, r9d; lpName
0x18006ff73  mov     r8d, r15d; bInitialState
0x18006ff76  mov     edx, r15d; bManualReset
0x18006ff79  xor     ecx, ecx; lpEventAttributes
0x18006ff7b  call    cs:__imp_CreateEventW
0x18006ff82  nop     dword ptr [rax+rax+00h]
0x18006ff87  mov     [rbx+178h], rax
0x18006ff8e  test    rax, rax
0x18006ff91  jz      loc_1800701BC
0x18006ff97  lea     rax, [rbx+1A8h]
0x18006ff9e  lea     rsi, [rbx+180h]
0x18006ffa5  mov     [rax+8], rax
0x18006ffa9  mov     rcx, rsi; lpCriticalSection
0x18006ffac  mov     [rax], rax
0x18006ffaf  call    cs:__imp_InitializeCriticalSection
0x18006ffb6  nop     dword ptr [rax+rax+00h]
0x18006ffbb  call    InitializeProbeApi
0x18006ffc0  test    eax, eax
0x18006ffc2  jnz     loc_18007019A
0x18006ffc8  xor     r9d, r9d; lpName
0x18006ffcb  mov     r8d, r15d; bInitialState
0x18006ffce  mov     edx, r15d; bManualReset
0x18006ffd1  xor     ecx, ecx; lpEventAttributes
0x18006ffd3  call    cs:__imp_CreateEventW
0x18006ffda  nop     dword ptr [rax+rax+00h]
0x18006ffdf  mov     [rbx+120h], rax
0x18006ffe6  test    rax, rax
0x18006ffe9  jz      loc_180070195
0x18006ffef  xor     r9d, r9d; lpName
0x18006fff2  mov     r8d, r15d; bInitialState
0x18006fff5  mov     edx, r15d; bManualReset
0x18006fff8  xor     ecx, ecx; lpEventAttributes
0x18006fffa  call    cs:__imp_CreateEventW
0x180070001  nop     dword ptr [rax+rax+00h]
0x180070006  mov     [rbx+138h], rax
0x18007000d  test    rax, rax
0x180070010  jz      loc_180070182
0x180070016  mov     [rsp+68h+var_38], 0
0x18007001e  lea     r14, [rbx+130h]
0x180070025  mov     rcx, r14
0x180070028  mov     [rsp+68h+var_40], 0
0x180070030  mov     r9, rbx
0x180070033  mov     [rsp+68h+var_48], r15d
0x180070038  lea     r8, DaSiteMgrStateTimerCallbackRoutine
0x18007003f  lea     rdx, word_180087660
0x180070046  call    TpclCreateTimer
0x18007004b  test    eax, eax
0x18007004d  jz      loc_18007016F
0x180070053  lea     ecx, [r15+2Fh]; dwBytes
0x180070057  mov     qword ptr [rbx+1E8h], 0
0x180070062  call    MALLOC
0x180070067  mov     [rbx+1E8h], rax
0x18007006e  test    rax, rax
0x180070071  jz      loc_18007015A
0x180070077  mov     qword ptr [rax+28h], 0
0x18007007f  mov     rcx, [rbx+1E8h]; lpCriticalSection
0x180070086  call    cs:__imp_InitializeCriticalSection
0x18007008d  nop     dword ptr [rax+rax+00h]
0x180070092  mov     rcx, rbx
0x180070095  call    DaSiteMgrSubscribeToNetworkChanges
0x18007009a  test    eax, eax
0x18007009c  jz      loc_18007014E
0x1800700a2  lea     r8, [rbx+0E0h]
0x1800700a9  xor     edx, edx
0x1800700ab  lea     rcx, DaSiteMgrCsNotificationCallback
0x1800700b2  call    UtillibRegisterCSNotification
0x1800700b7  test    eax, eax
0x1800700b9  jnz     loc_180070146
0x1800700bf  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hEvent
0x1800700c6  call    cs:__imp_ResetEvent
0x1800700cd  nop     dword ptr [rax+rax+00h]
0x1800700d2  mov     edx, 0C8h
0x1800700d7  mov     cs:g_DaSiteMgrReferenceObject, 2
0x1800700e1  lea     rcx, aOnecoreuapNetN_44; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800700e8  call    DaSiteMgrInstanceReferenceEx
0x1800700ed  xor     r8d, r8d
0x1800700f0  lea     rdx, aDasitemgrcreat; "DaSiteMgrCreateInstance queueing DaSite"...
0x1800700f7  mov     ecx, 80000000h
0x1800700fc  call    EventWrite0
0x180070101  xor     ecx, ecx
0x180070103  call    DaSiteMgrEventQueue
0x180070108  test    eax, eax
0x18007010a  jnz     loc_180070245
0x180070110  lock dec cs:g_DaSiteMgrReferenceObject
0x180070117  lea     rcx, aOnecoreuapNetN_44; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18007011e  mov     edx, 0D9h
0x180070123  call    DaSiteMgrInstanceDereferenceEx
0x180070128  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hHandle
0x18007012f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180070132  call    cs:__imp_WaitForSingleObject
0x180070139  nop     dword ptr [rax+rax+00h]
0x18007013e  mov     rcx, rbx
0x180070141  call    DaSiteMgrUnsubscribeFromCsEvents
0x180070146  mov     rcx, rbx
0x180070149  call    DaSiteMgrUnsubscribeFromNetworkChanges
0x18007014e  mov     rcx, [rbx+1E8h]; lpCriticalSection
0x180070155  call    NlmCacheUninitialize
0x18007015a  mov     rdx, [r14]
0x18007015d  lea     rcx, word_180087660
0x180070164  xor     r9d, r9d
0x180070167  mov     r8b, r15b
0x18007016a  call    TpclDestroyTimer
0x18007016f  mov     rcx, [rbx+138h]; hObject
0x180070176  call    cs:__imp_CloseHandle
0x18007017d  nop     dword ptr [rax+rax+00h]
0x180070182  mov     rcx, [rbx+120h]; hObject
0x180070189  call    cs:__imp_CloseHandle
0x180070190  nop     dword ptr [rax+rax+00h]
0x180070195  call    CleanupProbeApi
0x18007019a  mov     rcx, rsi; lpCriticalSection
0x18007019d  call    cs:__imp_DeleteCriticalSection
0x1800701a4  nop     dword ptr [rax+rax+00h]
0x1800701a9  mov     rcx, [rbx+178h]; hObject
0x1800701b0  call    cs:__imp_CloseHandle
0x1800701b7  nop     dword ptr [rax+rax+00h]
0x1800701bc  cmp     qword ptr [rbx+148h], 0
0x1800701c4  jnz     short loc_1800701D8
0x1800701c6  xor     ecx, ecx
0x1800701c8  call    FREE
0x1800701cd  mov     qword ptr [rbx+148h], 0
0x1800701d8  mov     rcx, [rbx+150h]
0x1800701df  test    rcx, rcx
0x1800701e2  jz      short loc_1800701F4
0x1800701e4  call    FREE
0x1800701e9  mov     qword ptr [rbx+150h], 0
0x1800701f4  mov     rcx, rdi
0x1800701f7  call    StopWorkQueue
0x1800701fc  mov     rcx, rdi
0x1800701ff  call    UninitializeWorkQueue
0x180070204  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hObject
0x18007020b  call    cs:__imp_CloseHandle
0x180070212  nop     dword ptr [rax+rax+00h]
0x180070217  mov     cs:g_DaSiteMgrReferenceObjectEvent, 0
0x180070222  call    DaSiteMgrAdTableUninitialize
0x180070227  mov     rcx, rbx; lpCriticalSection
0x18007022a  call    cs:__imp_DeleteCriticalSection
0x180070231  nop     dword ptr [rax+rax+00h]
0x180070236  xor     eax, eax
0x180070238  add     rsp, 40h
0x18007023c  pop     r15
0x18007023e  pop     r14
0x180070240  pop     rdi
0x180070241  pop     rsi
0x180070242  pop     rbx
0x180070243  retn
0x180070245  mov     eax, r15d
0x180070248  jmp     short loc_180070238
```
