# DaSiteMgrDestroyInstance

- ea: `0x1800702dc`
- end: `0x1800703f7`
- name: `DaSiteMgrDestroyInstance`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18003a930`
- `0x18006fa3c`

## callees

- `0x180039220`
- `0x1800459a4`
- `0x18006fe78`
- `0x18007078c`
- `0x1800707bc`
- `0x180072de4`
- `0x180073514`
- `0x180076dac`
- `0x180076e04`
- `0x180079e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070317`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180070317`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007038a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007038a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800703eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007035f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007039d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800703c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007035f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007039d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800703c2`

## string_xrefs

- `0x180070301`: `onecoreuap\net\netio\iphlpsvc\service\stmgri.c`

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
0x1800702dc  mov     [rsp+arg_0], rbx
0x1800702e1  push    rdi
0x1800702e2  sub     rsp, 20h
0x1800702e6  mov     rdi, cs:g_DaSiteMgrInstance
0x1800702ed  lock dec cs:g_DaSiteMgrReferenceObject
0x1800702f4  mov     rcx, rdi; lpCriticalSection
0x1800702f7  call    DaSiteMgrStateUninitialize
0x1800702fc  mov     edx, 10Fh
0x180070301  lea     rcx, aOnecoreuapNetN_44; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180070308  call    DaSiteMgrInstanceDereferenceEx
0x18007030d  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hHandle
0x180070314  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180070317  call    cs:__imp_WaitForSingleObject
0x18007031e  nop     dword ptr [rax+rax+00h]
0x180070323  mov     rcx, rdi
0x180070326  call    DaSiteMgrUnsubscribeFromCsEvents
0x18007032b  mov     rcx, rdi
0x18007032e  call    DaSiteMgrUnsubscribeFromNetworkChanges
0x180070333  mov     rcx, [rdi+1E8h]; lpCriticalSection
0x18007033a  call    NlmCacheUninitialize
0x18007033f  mov     rdx, [rdi+130h]
0x180070346  lea     rcx, word_180087660
0x18007034d  xor     r9d, r9d
0x180070350  mov     r8b, 1
0x180070353  call    TpclDestroyTimer
0x180070358  mov     rcx, [rdi+138h]; hObject
0x18007035f  call    cs:__imp_CloseHandle
0x180070366  nop     dword ptr [rax+rax+00h]
0x18007036b  mov     rcx, [rdi+120h]; hObject
0x180070372  call    cs:__imp_CloseHandle
0x180070379  nop     dword ptr [rax+rax+00h]
0x18007037e  call    CleanupProbeApi
0x180070383  lea     rcx, [rdi+180h]; lpCriticalSection
0x18007038a  call    cs:__imp_DeleteCriticalSection
0x180070391  nop     dword ptr [rax+rax+00h]
0x180070396  mov     rcx, [rdi+178h]; hObject
0x18007039d  call    cs:__imp_CloseHandle
0x1800703a4  nop     dword ptr [rax+rax+00h]
0x1800703a9  lea     rcx, [rdi+28h]
0x1800703ad  call    StopWorkQueue
0x1800703b2  lea     rcx, [rdi+28h]
0x1800703b6  call    UninitializeWorkQueue
0x1800703bb  mov     rcx, cs:g_DaSiteMgrReferenceObjectEvent; hObject
0x1800703c2  call    cs:__imp_CloseHandle
0x1800703c9  nop     dword ptr [rax+rax+00h]
0x1800703ce  mov     cs:g_DaSiteMgrReferenceObjectEvent, 0
0x1800703d9  call    DaSiteMgrAdTableUninitialize
0x1800703de  mov     rcx, rdi
0x1800703e1  mov     rbx, [rsp+28h+arg_0]
0x1800703e6  add     rsp, 20h
0x1800703ea  pop     rdi
0x1800703eb  jmp     cs:__imp_DeleteCriticalSection
```
