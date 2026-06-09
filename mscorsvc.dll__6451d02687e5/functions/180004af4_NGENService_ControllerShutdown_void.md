# NGENService::ControllerShutdown(void)

- ea: `0x180004af4`
- end: `0x180004c59`
- name: `?ControllerShutdown@NGENService@@YAXXZ`
- size: `357`
- prototype: `void __fastcall(NGENService *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800046c4`
- `0x18001a9d8`
- `0x18001b340`

## callees

- `0x180004af4`
- `0x18002e1d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180004b6b`
- `ADVAPI32!RegCloseKey` at `0x180004b85`
- `ADVAPI32!RegCloseKey` at `0x180004b6b`
- `ADVAPI32!RegCloseKey` at `0x180004b85`
- `KERNEL32!EnterCriticalSection` at `0x180004c36`
- `KERNEL32!EnterCriticalSection` at `0x180004c36`
- `KERNEL32!LeaveCriticalSection` at `0x180004c43`
- `KERNEL32!LeaveCriticalSection` at `0x180004c43`
- `KERNEL32!SetEvent` at `0x180004b0b`
- `KERNEL32!SetEvent` at `0x180004b0b`
- `KERNEL32!WaitForSingleObject` at `0x180004b2a`
- `KERNEL32!WaitForSingleObject` at `0x180004b4c`
- `KERNEL32!WaitForSingleObject` at `0x180004b2a`
- `KERNEL32!WaitForSingleObject` at `0x180004b4c`
- `KERNEL32!CloseHandle` at `0x180004b37`
- `KERNEL32!CloseHandle` at `0x180004b59`
- `KERNEL32!CloseHandle` at `0x180004b9f`
- `KERNEL32!CloseHandle` at `0x180004bb9`
- `KERNEL32!CloseHandle` at `0x180004bd3`
- `KERNEL32!CloseHandle` at `0x180004bed`
- `KERNEL32!CloseHandle` at `0x180004c07`
- `KERNEL32!CloseHandle` at `0x180004b37`
- `KERNEL32!CloseHandle` at `0x180004b59`
- `KERNEL32!CloseHandle` at `0x180004b9f`
- `KERNEL32!CloseHandle` at `0x180004bb9`
- `KERNEL32!CloseHandle` at `0x180004bd3`
- `KERNEL32!CloseHandle` at `0x180004bed`
- `KERNEL32!CloseHandle` at `0x180004c07`
- `OLEAUT32!__imp_SysFreeString` at `0x180004c21`
- `OLEAUT32!__imp_SysFreeString` at `0x180004c21`

## string_xrefs

- `0x180004c49`: `ShutdownController(): Completed\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NGENService::ControllerShutdown(NGENService *this)
{
  HANDLE v1; // rcx
  const unsigned __int16 *v2; // rdx

  v1 = NGENService::g_hListenerShutdownEvent;
  NGENService::g_bStopEventListener = 1;
  if ( NGENService::g_hListenerShutdownEvent )
  {
    SetEvent(NGENService::g_hListenerShutdownEvent);
    v1 = NGENService::g_hListenerShutdownEvent;
  }
  if ( NGENService::g_hListenerThread )
  {
    WaitForSingleObject(NGENService::g_hListenerThread, 0xFFFFFFFF);
    CloseHandle(NGENService::g_hListenerThread);
    v1 = NGENService::g_hListenerShutdownEvent;
  }
  if ( v1 )
  {
    WaitForSingleObject(v1, 0xFFFFFFFF);
    CloseHandle(NGENService::g_hListenerShutdownEvent);
  }
  if ( NGENService::g_hkNGENServiceListenedState )
  {
    RegCloseKey(NGENService::g_hkNGENServiceListenedState);
    NGENService::g_hkNGENServiceListenedState = 0;
  }
  if ( NGENService::g_hkNGENServicePersistentState )
  {
    RegCloseKey(NGENService::g_hkNGENServicePersistentState);
    NGENService::g_hkNGENServicePersistentState = 0;
  }
  if ( NGENService::g_hSCMRequestEvent )
  {
    CloseHandle(NGENService::g_hSCMRequestEvent);
    NGENService::g_hSCMRequestEvent = 0;
  }
  if ( NGENService::g_hRootStoreDirtyEvent )
  {
    CloseHandle(NGENService::g_hRootStoreDirtyEvent);
    NGENService::g_hRootStoreDirtyEvent = 0;
  }
  if ( NGENService::g_hInterruptEvent )
  {
    CloseHandle(NGENService::g_hInterruptEvent);
    NGENService::g_hInterruptEvent = 0;
  }
  if ( NGENService::g_hInterruptProcessedEvent )
  {
    CloseHandle(NGENService::g_hInterruptProcessedEvent);
    NGENService::g_hInterruptProcessedEvent = 0;
  }
  if ( NGENService::g_hControllerStateChange )
  {
    CloseHandle(NGENService::g_hControllerStateChange);
    NGENService::g_hControllerStateChange = 0;
  }
  if ( NGENService::g_bstrInterruptEventName )
  {
    SysFreeString((BSTR)NGENService::g_bstrInterruptEventName);
    NGENService::g_bstrInterruptEventName = 0;
  }
  EnterCriticalSection(&NGENService::g_IdleCS);
  LeaveCriticalSection(&NGENService::g_IdleCS);
  NGENService::DebugLog((NGENService *)L"ShutdownController(): Completed\n", v2);
}

```

## disassembly

```asm
0x180004af4  sub     rsp, 28h
0x180004af8  mov     rcx, cs:?g_hListenerShutdownEvent@NGENService@@3PEAXEA; hEvent
0x180004aff  mov     cs:?g_bStopEventListener@NGENService@@3V?$Volatile@_N@@A, 1; Volatile<bool> NGENService::g_bStopEventListener
0x180004b06  test    rcx, rcx
0x180004b09  jz      short loc_180004B18
0x180004b0b  call    cs:__imp_SetEvent
0x180004b11  mov     rcx, cs:?g_hListenerShutdownEvent@NGENService@@3PEAXEA; void * NGENService::g_hListenerShutdownEvent
0x180004b18  mov     rax, cs:?g_hListenerThread@NGENService@@3PEAXEA; void * NGENService::g_hListenerThread
0x180004b1f  test    rax, rax
0x180004b22  jz      short loc_180004B44
0x180004b24  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004b27  mov     rcx, rax; hHandle
0x180004b2a  call    cs:__imp_WaitForSingleObject
0x180004b30  mov     rcx, cs:?g_hListenerThread@NGENService@@3PEAXEA; hObject
0x180004b37  call    cs:__imp_CloseHandle
0x180004b3d  mov     rcx, cs:?g_hListenerShutdownEvent@NGENService@@3PEAXEA; hHandle
0x180004b44  test    rcx, rcx
0x180004b47  jz      short loc_180004B5F
0x180004b49  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004b4c  call    cs:__imp_WaitForSingleObject
0x180004b52  mov     rcx, cs:?g_hListenerShutdownEvent@NGENService@@3PEAXEA; hObject
0x180004b59  call    cs:__imp_CloseHandle
0x180004b5f  mov     rcx, cs:?g_hkNGENServiceListenedState@NGENService@@3PEAUHKEY__@@EA; hKey
0x180004b66  test    rcx, rcx
0x180004b69  jz      short loc_180004B79
0x180004b6b  call    cs:__imp_RegCloseKey
0x180004b71  and     cs:?g_hkNGENServiceListenedState@NGENService@@3PEAUHKEY__@@EA, 0; HKEY__ * NGENService::g_hkNGENServiceListenedState
0x180004b79  mov     rcx, cs:?g_hkNGENServicePersistentState@NGENService@@3PEAUHKEY__@@EA; hKey
0x180004b80  test    rcx, rcx
0x180004b83  jz      short loc_180004B93
0x180004b85  call    cs:__imp_RegCloseKey
0x180004b8b  and     cs:?g_hkNGENServicePersistentState@NGENService@@3PEAUHKEY__@@EA, 0; HKEY__ * NGENService::g_hkNGENServicePersistentState
0x180004b93  mov     rcx, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; hObject
0x180004b9a  test    rcx, rcx
0x180004b9d  jz      short loc_180004BAD
0x180004b9f  call    cs:__imp_CloseHandle
0x180004ba5  and     cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA, 0; void * NGENService::g_hSCMRequestEvent
0x180004bad  mov     rcx, cs:?g_hRootStoreDirtyEvent@NGENService@@3PEAXEA; hObject
0x180004bb4  test    rcx, rcx
0x180004bb7  jz      short loc_180004BC7
0x180004bb9  call    cs:__imp_CloseHandle
0x180004bbf  and     cs:?g_hRootStoreDirtyEvent@NGENService@@3PEAXEA, 0; void * NGENService::g_hRootStoreDirtyEvent
0x180004bc7  mov     rcx, cs:?g_hInterruptEvent@NGENService@@3PEAXEA; hObject
0x180004bce  test    rcx, rcx
0x180004bd1  jz      short loc_180004BE1
0x180004bd3  call    cs:__imp_CloseHandle
0x180004bd9  and     cs:?g_hInterruptEvent@NGENService@@3PEAXEA, 0; void * NGENService::g_hInterruptEvent
0x180004be1  mov     rcx, cs:?g_hInterruptProcessedEvent@NGENService@@3PEAXEA; hObject
0x180004be8  test    rcx, rcx
0x180004beb  jz      short loc_180004BFB
0x180004bed  call    cs:__imp_CloseHandle
0x180004bf3  and     cs:?g_hInterruptProcessedEvent@NGENService@@3PEAXEA, 0; void * NGENService::g_hInterruptProcessedEvent
0x180004bfb  mov     rcx, cs:?g_hControllerStateChange@NGENService@@3PEAXEA; hObject
0x180004c02  test    rcx, rcx
0x180004c05  jz      short loc_180004C15
0x180004c07  call    cs:__imp_CloseHandle
0x180004c0d  and     cs:?g_hControllerStateChange@NGENService@@3PEAXEA, 0; void * NGENService::g_hControllerStateChange
0x180004c15  mov     rcx, cs:?g_bstrInterruptEventName@NGENService@@3PEAGEA; bstrString
0x180004c1c  test    rcx, rcx
0x180004c1f  jz      short loc_180004C2F
0x180004c21  call    cs:__imp_SysFreeString
0x180004c27  and     cs:?g_bstrInterruptEventName@NGENService@@3PEAGEA, 0; ushort * NGENService::g_bstrInterruptEventName
0x180004c2f  lea     rcx, ?g_IdleCS@NGENService@@3VCriticalSection@@A; lpCriticalSection
0x180004c36  call    cs:__imp_EnterCriticalSection
0x180004c3c  lea     rcx, ?g_IdleCS@NGENService@@3VCriticalSection@@A; lpCriticalSection
0x180004c43  call    cs:__imp_LeaveCriticalSection
0x180004c49  lea     rcx, aShutdowncontro; "ShutdownController(): Completed\n"
0x180004c50  add     rsp, 28h
0x180004c54  jmp     ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
```
