# DaSiteMgrDestroyInstance

- ea: `0x1800702fc`
- end: `0x180070417`
- name: `DaSiteMgrDestroyInstance`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18003a940`
- `0x18006fa5c`

## callees

- `0x180039230`
- `0x180045964`
- `0x18006fe98`
- `0x1800707ac`
- `0x1800707dc`
- `0x180072e04`
- `0x180073534`
- `0x180076dcc`
- `0x180076e24`
- `0x180079e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070337`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070337`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800703aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800703aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007040b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007037f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800703bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800703e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007037f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800703bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800703e2`

## string_xrefs

- `0x180070321`: `onecoreuap\net\netio\iphlpsvc\service\stmgri.c`

## pseudocode

```c
void DaSiteMgrDestroyInstance()
{
  LPCRITICAL_SECTION v0; // rdi
  __int64 v1; // r8

  v0 = g_DaSiteMgrInstance;
  _InterlockedDecrement(&g_DaSiteMgrReferenceObject);
  DaSiteMgrStateUninitialize(g_DaSiteMgrInstance);
  DaSiteMgrInstanceDereferenceEx("onecoreuap\\net\\netio\\iphlpsvc\\service\\stmgri.c", 271);
  WaitForSingleObject(g_DaSiteMgrReferenceObjectEvent, 0xFFFFFFFF);
  DaSiteMgrUnsubscribeFromCsEvents(v0);
  DaSiteMgrUnsubscribeFromNetworkChanges(v0);
  NlmCacheUninitialize(*(LPCRITICAL_SECTION *)&v0[12].LockCount);
  LOBYTE(v1) = 1;
  TpclDestroyTimer(&word_180087660, v0[7].LockSemaphore, v1, 0);
  CloseHandle((HANDLE)v0[7].SpinCount);
  CloseHandle(*(HANDLE *)&v0[7].LockCount);
  CleanupProbeApi();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v0 + 384));
  CloseHandle(v0[9].OwningThread);
  StopWorkQueue(&v0[1]);
  UninitializeWorkQueue(&v0[1]);
  CloseHandle(g_DaSiteMgrReferenceObjectEvent);
  g_DaSiteMgrReferenceObjectEvent = 0;
  DaSiteMgrAdTableUninitialize();
  DeleteCriticalSection(v0);
}

```

## disassembly

```asm
0x1800702fc  mov     [rsp+arg_0], rbx
0x180070301  push    rdi
0x180070302  sub     rsp, 20h
0x180070306  mov     rdi, cs:g_DaSiteMgrInstance
0x18007030d  lock dec cs:g_DaSiteMgrReferenceObject
0x180070314  mov     rcx, rdi; lpCriticalSection
0x180070317  call    DaSiteMgrStateUninitialize
0x18007031c  mov     edx, 10Fh
0x180070321  lea     rcx, aOnecoreuapNetN_44; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180070328  call    DaSiteMgrInstanceDereferenceEx
0x18007032d  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hHandle
0x180070334  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180070337  call    cs:__imp_WaitForSingleObject
0x18007033e  nop     dword ptr [rax+rax+00h]
0x180070343  mov     rcx, rdi
0x180070346  call    DaSiteMgrUnsubscribeFromCsEvents
0x18007034b  mov     rcx, rdi
0x18007034e  call    DaSiteMgrUnsubscribeFromNetworkChanges
0x180070353  mov     rcx, [rdi+1E8h]; lpCriticalSection
0x18007035a  call    NlmCacheUninitialize
0x18007035f  mov     rdx, [rdi+130h]
0x180070366  lea     rcx, word_180087660
0x18007036d  xor     r9d, r9d
0x180070370  mov     r8b, 1
0x180070373  call    TpclDestroyTimer
0x180070378  mov     rcx, [rdi+138h]; hObject
0x18007037f  call    cs:__imp_CloseHandle
0x180070386  nop     dword ptr [rax+rax+00h]
0x18007038b  mov     rcx, [rdi+120h]; hObject
0x180070392  call    cs:__imp_CloseHandle
0x180070399  nop     dword ptr [rax+rax+00h]
0x18007039e  call    CleanupProbeApi
0x1800703a3  lea     rcx, [rdi+180h]; lpCriticalSection
0x1800703aa  call    cs:__imp_DeleteCriticalSection
0x1800703b1  nop     dword ptr [rax+rax+00h]
0x1800703b6  mov     rcx, [rdi+178h]; hObject
0x1800703bd  call    cs:__imp_CloseHandle
0x1800703c4  nop     dword ptr [rax+rax+00h]
0x1800703c9  lea     rcx, [rdi+28h]
0x1800703cd  call    StopWorkQueue
0x1800703d2  lea     rcx, [rdi+28h]
0x1800703d6  call    UninitializeWorkQueue
0x1800703db  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hObject
0x1800703e2  call    cs:__imp_CloseHandle
0x1800703e9  nop     dword ptr [rax+rax+00h]
0x1800703ee  mov     cs:g_DaSiteMgrReferenceObjectEvent, 0
0x1800703f9  call    DaSiteMgrAdTableUninitialize
0x1800703fe  mov     rcx, rdi
0x180070401  mov     rbx, [rsp+28h+arg_0]
0x180070406  add     rsp, 20h
0x18007040a  pop     rdi
0x18007040b  jmp     cs:__imp_DeleteCriticalSection
```
