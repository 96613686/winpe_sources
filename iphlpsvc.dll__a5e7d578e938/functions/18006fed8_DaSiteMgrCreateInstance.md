# DaSiteMgrCreateInstance

- ea: `0x18006fed8`
- end: `0x18007026a`
- name: `DaSiteMgrCreateInstance`
- size: `914`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task`

## callers

- `0x18003a940`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180012dcc`
- `0x18002da58`
- `0x180035d1c`
- `0x180039230`
- `0x180039c78`
- `0x180041350`
- `0x180041fa8`
- `0x180042f2c`
- `0x180045964`
- `0x18006fe98`
- `0x18006fed8`
- `0x180070684`
- `0x1800707ac`
- `0x1800707dc`
- `0x1800719b4`
- `0x180073534`
- `0x180076dcc`
- `0x180076e24`
- `0x180079e60`
- `0x18007a00c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800700e6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800700e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070152`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070152`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ff41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ff9b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fff3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007001a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ff41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ff9b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006fff3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007001a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006ff08`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006ff1b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006ffcf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800700a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006ff08`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006ff1b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006ffcf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800700a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800701bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007024a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800701bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007024a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007022b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007022b`

## string_xrefs

- `0x180070101`: `onecoreuap\net\netio\iphlpsvc\service\stmgri.c`
- `0x180070137`: `onecoreuap\net\netio\iphlpsvc\service\stmgri.c`
- `0x180070110`: `DaSiteMgrCreateInstance queueing DaSiteMgrInitializeEvt event, event type %d`

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
0x18006fed8  push    rbx
0x18006feda  push    rsi
0x18006fedb  push    rdi
0x18006fedc  push    r14
0x18006fede  push    r15
0x18006fee0  sub     rsp, 40h
0x18006fee4  mov     rbx, cs:g_DaSiteMgrInstance
0x18006feeb  lea     rax, [rbx+88h]
0x18006fef2  cmp     [rax], rax
0x18006fef5  jz      loc_180070256
0x18006fefb  mov     rcx, rbx; lpCriticalSection
0x18006fefe  mov     dword ptr [rbx+80h], 0
0x18006ff08  call    cs:__imp_InitializeCriticalSection
0x18006ff0f  nop     dword ptr [rax+rax+00h]
0x18006ff14  lea     rcx, g_DaSiteMgrAdTableLock; lpCriticalSection
0x18006ff1b  call    cs:__imp_InitializeCriticalSection
0x18006ff22  nop     dword ptr [rax+rax+00h]
0x18006ff27  xor     r9d, r9d; lpName
0x18006ff2a  mov     cs:g_DaSiteMgrAdSiteTable, 0
0x18006ff35  xor     ecx, ecx; lpEventAttributes
0x18006ff37  lea     r15d, [r9+1]
0x18006ff3b  mov     r8d, r15d; bInitialState
0x18006ff3e  mov     edx, r15d; bManualReset
0x18006ff41  call    cs:__imp_CreateEventW
0x18006ff48  nop     dword ptr [rax+rax+00h]
0x18006ff4d  mov     cs:g_DaSiteMgrReferenceObjectEvent, rax
0x18006ff54  test    rax, rax
0x18006ff57  jz      loc_180070242
0x18006ff5d  lea     rdi, [rbx+28h]
0x18006ff61  mov     rcx, rdi; lpCriticalSection
0x18006ff64  lea     rdx, CallbackEnvironment
0x18006ff6b  call    InitializeWorkQueue
0x18006ff70  test    eax, eax
0x18006ff72  jz      loc_180070224
0x18006ff78  mov     rcx, rdi
0x18006ff7b  call    StartWorkQueue
0x18006ff80  mov     rcx, rbx
0x18006ff83  call    DaSiteMgrStatePrepareNetLocalityAddressTable
0x18006ff88  test    eax, eax
0x18006ff8a  jz      loc_180070214
0x18006ff90  xor     r9d, r9d; lpName
0x18006ff93  mov     r8d, r15d; bInitialState
0x18006ff96  mov     edx, r15d; bManualReset
0x18006ff99  xor     ecx, ecx; lpEventAttributes
0x18006ff9b  call    cs:__imp_CreateEventW
0x18006ffa2  nop     dword ptr [rax+rax+00h]
0x18006ffa7  mov     [rbx+178h], rax
0x18006ffae  test    rax, rax
0x18006ffb1  jz      loc_1800701DC
0x18006ffb7  lea     rax, [rbx+1A8h]
0x18006ffbe  lea     rsi, [rbx+180h]
0x18006ffc5  mov     [rax+8], rax
0x18006ffc9  mov     rcx, rsi; lpCriticalSection
0x18006ffcc  mov     [rax], rax
0x18006ffcf  call    cs:__imp_InitializeCriticalSection
0x18006ffd6  nop     dword ptr [rax+rax+00h]
0x18006ffdb  call    InitializeProbeApi
0x18006ffe0  test    eax, eax
0x18006ffe2  jnz     loc_1800701BA
0x18006ffe8  xor     r9d, r9d; lpName
0x18006ffeb  mov     r8d, r15d; bInitialState
0x18006ffee  mov     edx, r15d; bManualReset
0x18006fff1  xor     ecx, ecx; lpEventAttributes
0x18006fff3  call    cs:__imp_CreateEventW
0x18006fffa  nop     dword ptr [rax+rax+00h]
0x18006ffff  mov     [rbx+120h], rax
0x180070006  test    rax, rax
0x180070009  jz      loc_1800701B5
0x18007000f  xor     r9d, r9d; lpName
0x180070012  mov     r8d, r15d; bInitialState
0x180070015  mov     edx, r15d; bManualReset
0x180070018  xor     ecx, ecx; lpEventAttributes
0x18007001a  call    cs:__imp_CreateEventW
0x180070021  nop     dword ptr [rax+rax+00h]
0x180070026  mov     [rbx+138h], rax
0x18007002d  test    rax, rax
0x180070030  jz      loc_1800701A2
0x180070036  mov     [rsp+68h+var_38], 0
0x18007003e  lea     r14, [rbx+130h]
0x180070045  mov     rcx, r14
0x180070048  mov     [rsp+68h+var_40], 0
0x180070050  mov     r9, rbx
0x180070053  mov     [rsp+68h+var_48], r15d
0x180070058  lea     r8, DaSiteMgrStateTimerCallbackRoutine
0x18007005f  lea     rdx, word_180087660
0x180070066  call    TpclCreateTimer
0x18007006b  test    eax, eax
0x18007006d  jz      loc_18007018F
0x180070073  lea     ecx, [r15+2Fh]; dwBytes
0x180070077  mov     qword ptr [rbx+1E8h], 0
0x180070082  call    MALLOC
0x180070087  mov     [rbx+1E8h], rax
0x18007008e  test    rax, rax
0x180070091  jz      loc_18007017A
0x180070097  mov     qword ptr [rax+28h], 0
0x18007009f  mov     rcx, [rbx+1E8h]; lpCriticalSection
0x1800700a6  call    cs:__imp_InitializeCriticalSection
0x1800700ad  nop     dword ptr [rax+rax+00h]
0x1800700b2  mov     rcx, rbx
0x1800700b5  call    DaSiteMgrSubscribeToNetworkChanges
0x1800700ba  test    eax, eax
0x1800700bc  jz      loc_18007016E
0x1800700c2  lea     r8, [rbx+0E0h]
0x1800700c9  xor     edx, edx
0x1800700cb  lea     rcx, DaSiteMgrCsNotificationCallback
0x1800700d2  call    UtillibRegisterCSNotification
0x1800700d7  test    eax, eax
0x1800700d9  jnz     loc_180070166
0x1800700df  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hEvent
0x1800700e6  call    cs:__imp_ResetEvent
0x1800700ed  nop     dword ptr [rax+rax+00h]
0x1800700f2  mov     edx, 0C8h
0x1800700f7  mov     cs:g_DaSiteMgrReferenceObject, 2
0x180070101  lea     rcx, aOnecoreuapNetN_44; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180070108  call    DaSiteMgrInstanceReferenceEx
0x18007010d  xor     r8d, r8d
0x180070110  lea     rdx, aDasitemgrcreat; "DaSiteMgrCreateInstance queueing DaSite"...
0x180070117  mov     ecx, 80000000h
0x18007011c  call    EventWrite0
0x180070121  xor     ecx, ecx
0x180070123  call    DaSiteMgrEventQueue
0x180070128  test    eax, eax
0x18007012a  jnz     loc_180070265
0x180070130  lock dec cs:g_DaSiteMgrReferenceObject
0x180070137  lea     rcx, aOnecoreuapNetN_44; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18007013e  mov     edx, 0D9h
0x180070143  call    DaSiteMgrInstanceDereferenceEx
0x180070148  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hHandle
0x18007014f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180070152  call    cs:__imp_WaitForSingleObject
0x180070159  nop     dword ptr [rax+rax+00h]
0x18007015e  mov     rcx, rbx
0x180070161  call    DaSiteMgrUnsubscribeFromCsEvents
0x180070166  mov     rcx, rbx
0x180070169  call    DaSiteMgrUnsubscribeFromNetworkChanges
0x18007016e  mov     rcx, [rbx+1E8h]; lpCriticalSection
0x180070175  call    NlmCacheUninitialize
0x18007017a  mov     rdx, [r14]
0x18007017d  lea     rcx, word_180087660
0x180070184  xor     r9d, r9d
0x180070187  mov     r8b, r15b
0x18007018a  call    TpclDestroyTimer
0x18007018f  mov     rcx, [rbx+138h]; hObject
0x180070196  call    cs:__imp_CloseHandle
0x18007019d  nop     dword ptr [rax+rax+00h]
0x1800701a2  mov     rcx, [rbx+120h]; hObject
0x1800701a9  call    cs:__imp_CloseHandle
0x1800701b0  nop     dword ptr [rax+rax+00h]
0x1800701b5  call    CleanupProbeApi
0x1800701ba  mov     rcx, rsi; lpCriticalSection
0x1800701bd  call    cs:__imp_DeleteCriticalSection
0x1800701c4  nop     dword ptr [rax+rax+00h]
0x1800701c9  mov     rcx, [rbx+178h]; hObject
0x1800701d0  call    cs:__imp_CloseHandle
0x1800701d7  nop     dword ptr [rax+rax+00h]
0x1800701dc  cmp     qword ptr [rbx+148h], 0
0x1800701e4  jnz     short loc_1800701F8
0x1800701e6  xor     ecx, ecx
0x1800701e8  call    FREE
0x1800701ed  mov     qword ptr [rbx+148h], 0
0x1800701f8  mov     rcx, [rbx+150h]
0x1800701ff  test    rcx, rcx
0x180070202  jz      short loc_180070214
0x180070204  call    FREE
0x180070209  mov     qword ptr [rbx+150h], 0
0x180070214  mov     rcx, rdi
0x180070217  call    StopWorkQueue
0x18007021c  mov     rcx, rdi
0x18007021f  call    UninitializeWorkQueue
0x180070224  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hObject
0x18007022b  call    cs:__imp_CloseHandle
0x180070232  nop     dword ptr [rax+rax+00h]
0x180070237  mov     cs:g_DaSiteMgrReferenceObjectEvent, 0
0x180070242  call    DaSiteMgrAdTableUninitialize
0x180070247  mov     rcx, rbx; lpCriticalSection
0x18007024a  call    cs:__imp_DeleteCriticalSection
0x180070251  nop     dword ptr [rax+rax+00h]
0x180070256  xor     eax, eax
0x180070258  add     rsp, 40h
0x18007025c  pop     r15
0x18007025e  pop     r14
0x180070260  pop     rdi
0x180070261  pop     rsi
0x180070262  pop     rbx
0x180070263  retn
0x180070265  mov     eax, r15d
0x180070268  jmp     short loc_180070258
```
