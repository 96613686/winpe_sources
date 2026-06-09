# DaSiteMgrUninitialize

- ea: `0x18006fa5c`
- end: `0x18006fb3d`
- name: `DaSiteMgrUninitialize`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d874`
- `0x18006f8d0`

## callees

- `0x18003ed7c`
- `0x18006fa5c`
- `0x1800702fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006faf1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006faf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fad7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fad7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006fb17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006fb2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006fb17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006fb2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fb04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fb04`

## pseudocode

```c
void DaSiteMgrUninitialize()
{
  bool v0; // bl

  if ( g_DaSiteMgrModuleReferenceObject != 1 && !_InterlockedCompareExchange(&g_DaSiteMgrCleanupRun, 1, 0) )
  {
    v0 = _InterlockedDecrement(&g_DaSiteMgrModuleReferenceObject) == 1;
    EnterCriticalSection(&g_DaSiteMgrLock);
    if ( g_DaSiteMgrInstance )
    {
      DaSiteMgrDestroyInstance();
      DaSiteMgrDestroyInstanceStub(g_DaSiteMgrInstance);
      g_DaSiteMgrInstance = 0;
    }
    LeaveCriticalSection(&g_DaSiteMgrLock);
    if ( !v0 )
      WaitForSingleObject(g_DaSiteMgrModuleReferenceObjectEvent, 0xFFFFFFFF);
    CloseHandle(g_DaSiteMgrModuleReferenceObjectEvent);
    DeleteCriticalSection(&g_DaSiteMgrConfigLock);
    DeleteCriticalSection(&g_DaSiteMgrLock);
  }
}

```

## disassembly

```asm
0x18006fa5c  push    rbx
0x18006fa5e  sub     rsp, 20h
0x18006fa62  mov     eax, cs:g_DaSiteMgrModuleReferenceObject
0x18006fa68  mov     ecx, 1
0x18006fa6d  cmp     eax, ecx
0x18006fa6f  jz      loc_18006FB36
0x18006fa75  xor     eax, eax
0x18006fa77  lock cmpxchg cs:g_DaSiteMgrCleanupRun, ecx
0x18006fa7f  jnz     loc_18006FB36
0x18006fa85  or      eax, 0FFFFFFFFh
0x18006fa88  lock xadd cs:g_DaSiteMgrModuleReferenceObject, eax
0x18006fa90  dec     eax
0x18006fa92  cmp     eax, ecx
0x18006fa94  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006fa9b  setz    bl
0x18006fa9e  call    cs:__imp_EnterCriticalSection
0x18006faa5  nop     dword ptr [rax+rax+00h]
0x18006faaa  cmp     cs:g_DaSiteMgrInstance, 0
0x18006fab2  jz      short loc_18006FAD0
0x18006fab4  call    DaSiteMgrDestroyInstance
0x18006fab9  mov     rcx, cs:g_DaSiteMgrInstance
0x18006fac0  call    DaSiteMgrDestroyInstanceStub
0x18006fac5  mov     cs:g_DaSiteMgrInstance, 0
0x18006fad0  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006fad7  call    cs:__imp_LeaveCriticalSection
0x18006fade  nop     dword ptr [rax+rax+00h]
0x18006fae3  test    bl, bl
0x18006fae5  jnz     short loc_18006FAFD
0x18006fae7  mov     rcx, cs:g_DaSiteMgrModuleReferenceObjectEvent; hHandle
0x18006faee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006faf1  call    cs:__imp_WaitForSingleObject
0x18006faf8  nop     dword ptr [rax+rax+00h]
0x18006fafd  mov     rcx, cs:g_DaSiteMgrModuleReferenceObjectEvent; hObject
0x18006fb04  call    cs:__imp_CloseHandle
0x18006fb0b  nop     dword ptr [rax+rax+00h]
0x18006fb10  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18006fb17  call    cs:__imp_DeleteCriticalSection
0x18006fb1e  nop     dword ptr [rax+rax+00h]
0x18006fb23  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006fb2a  call    cs:__imp_DeleteCriticalSection
0x18006fb31  nop     dword ptr [rax+rax+00h]
0x18006fb36  add     rsp, 20h
0x18006fb3a  pop     rbx
0x18006fb3b  retn
```
