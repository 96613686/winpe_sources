# DaSiteMgrUninitialize

- ea: `0x18006fa3c`
- end: `0x18006fb1d`
- name: `DaSiteMgrUninitialize`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d864`
- `0x18006f8b0`

## callees

- `0x18003edbc`
- `0x18006fa3c`
- `0x1800702dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006fad1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006fad1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fab7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fab7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006faf7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006fb0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006faf7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006fb0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fae4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fae4`

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
0x18006fa3c  push    rbx
0x18006fa3e  sub     rsp, 20h
0x18006fa42  mov     eax, cs:g_DaSiteMgrModuleReferenceObject
0x18006fa48  mov     ecx, 1
0x18006fa4d  cmp     eax, ecx
0x18006fa4f  jz      loc_18006FB16
0x18006fa55  xor     eax, eax
0x18006fa57  lock cmpxchg cs:g_DaSiteMgrCleanupRun, ecx
0x18006fa5f  jnz     loc_18006FB16
0x18006fa65  or      eax, 0FFFFFFFFh
0x18006fa68  lock xadd cs:g_DaSiteMgrModuleReferenceObject, eax
0x18006fa70  dec     eax
0x18006fa72  cmp     eax, ecx
0x18006fa74  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006fa7b  setz    bl
0x18006fa7e  call    cs:__imp_EnterCriticalSection
0x18006fa85  nop     dword ptr [rax+rax+00h]
0x18006fa8a  cmp     cs:g_DaSiteMgrInstance, 0
0x18006fa92  jz      short loc_18006FAB0
0x18006fa94  call    DaSiteMgrDestroyInstance
0x18006fa99  mov     rcx, cs:g_DaSiteMgrInstance
0x18006faa0  call    DaSiteMgrDestroyInstanceStub
0x18006faa5  mov     cs:g_DaSiteMgrInstance, 0
0x18006fab0  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006fab7  call    cs:__imp_LeaveCriticalSection
0x18006fabe  nop     dword ptr [rax+rax+00h]
0x18006fac3  test    bl, bl
0x18006fac5  jnz     short loc_18006FADD
0x18006fac7  mov     rcx, cs:g_DaSiteMgrModuleReferenceObjectEvent; hHandle
0x18006face  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006fad1  call    cs:__imp_WaitForSingleObject
0x18006fad8  nop     dword ptr [rax+rax+00h]
0x18006fadd  mov     rcx, cs:g_DaSiteMgrModuleReferenceObjectEvent; hObject
0x18006fae4  call    cs:__imp_CloseHandle
0x18006faeb  nop     dword ptr [rax+rax+00h]
0x18006faf0  lea     rcx, g_DaSiteMgrConfigLock; lpCriticalSection
0x18006faf7  call    cs:__imp_DeleteCriticalSection
0x18006fafe  nop     dword ptr [rax+rax+00h]
0x18006fb03  lea     rcx, g_DaSiteMgrLock; lpCriticalSection
0x18006fb0a  call    cs:__imp_DeleteCriticalSection
0x18006fb11  nop     dword ptr [rax+rax+00h]
0x18006fb16  add     rsp, 20h
0x18006fb1a  pop     rbx
0x18006fb1b  retn
```
