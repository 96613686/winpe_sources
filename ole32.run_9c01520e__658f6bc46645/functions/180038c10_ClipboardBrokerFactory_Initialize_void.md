# ClipboardBrokerFactory::Initialize(void)

- ea: `0x180038c10`
- end: `0x180038d22`
- name: `?Initialize@ClipboardBrokerFactory@@CAJXZ`
- size: `274`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038b04`

## callees

- `0x180038c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038d0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038d0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038c23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038c23`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038c46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038c6c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038c46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038c6c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038cc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038cc1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180038c9d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180038c9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038cef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038cef`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180038cdc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180038cdc`

## pseudocode

```c
__int64 __fastcall ClipboardBrokerFactory::Initialize()
{
  unsigned int v0; // ebx
  HRESULT hr; // [rsp+40h] [rbp+8h] BYREF

  hr = 0;
  EnterCriticalSection(&ClipboardBrokerFactory::s_initCS.cs_);
  if ( !ClipboardBrokerFactory::s_pServerBroker )
  {
    ClipboardBrokerFactory::s_hServerThreadEvent = CreateEventW(0, 0, 0, 0);
    if ( ClipboardBrokerFactory::s_hServerThreadEvent )
    {
      ClipboardBrokerFactory::s_hServerThreadStopEvent = CreateEventW(0, 0, 0, 0);
      if ( ClipboardBrokerFactory::s_hServerThreadStopEvent )
      {
        ClipboardBrokerFactory::s_hWorkerThread = CreateThread(
                                                    0,
                                                    0,
                                                    (LPTHREAD_START_ROUTINE)ClipboardBrokerFactory::serverThreadStart,
                                                    &hr,
                                                    0,
                                                    0);
        if ( ClipboardBrokerFactory::s_hWorkerThread )
        {
          if ( WaitForSingleObject(ClipboardBrokerFactory::s_hServerThreadEvent, 0x3E8u) )
          {
            hr = -2147418113;
            RoOriginateError(2147549183LL, 0);
            CloseHandle(ClipboardBrokerFactory::s_hWorkerThread);
            ClipboardBrokerFactory::s_hWorkerThread = 0;
          }
        }
      }
    }
  }
  v0 = hr;
  LeaveCriticalSection(&ClipboardBrokerFactory::s_initCS.cs_);
  return v0;
}

```

## disassembly

```asm
0x180038c10  push    rbx
0x180038c12  sub     rsp, 30h
0x180038c16  xor     ebx, ebx
0x180038c18  lea     rcx, ?s_initCS@ClipboardBrokerFactory@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x180038c1f  mov     [rsp+38h+hr], ebx
0x180038c23  call    cs:__imp_EnterCriticalSection
0x180038c2a  nop     dword ptr [rax+rax+00h]
0x180038c2f  cmp     cs:?s_pServerBroker@ClipboardBrokerFactory@@0PEAVCBrokerInstanceHolder@@EA, rbx; CBrokerInstanceHolder * ClipboardBrokerFactory::s_pServerBroker
0x180038c36  jnz     loc_180038D02
0x180038c3c  xor     r9d, r9d; lpName
0x180038c3f  xor     r8d, r8d; bInitialState
0x180038c42  xor     edx, edx; bManualReset
0x180038c44  xor     ecx, ecx; lpEventAttributes
0x180038c46  call    cs:__imp_CreateEventW
0x180038c4d  nop     dword ptr [rax+rax+00h]
0x180038c52  mov     cs:?s_hServerThreadEvent@ClipboardBrokerFactory@@0PEAXEA, rax; void * ClipboardBrokerFactory::s_hServerThreadEvent
0x180038c59  test    rax, rax
0x180038c5c  jz      loc_180038D02
0x180038c62  xor     r9d, r9d; lpName
0x180038c65  xor     r8d, r8d; bInitialState
0x180038c68  xor     edx, edx; bManualReset
0x180038c6a  xor     ecx, ecx; lpEventAttributes
0x180038c6c  call    cs:__imp_CreateEventW
0x180038c73  nop     dword ptr [rax+rax+00h]
0x180038c78  mov     cs:?s_hServerThreadStopEvent@ClipboardBrokerFactory@@0PEAXEA, rax; void * ClipboardBrokerFactory::s_hServerThreadStopEvent
0x180038c7f  test    rax, rax
0x180038c82  jz      short loc_180038D02
0x180038c84  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x180038c89  lea     r9, [rsp+38h+hr]; lpParameter
0x180038c8e  lea     r8, ?serverThreadStart@ClipboardBrokerFactory@@CAKPEAX@Z; lpStartAddress
0x180038c95  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180038c99  xor     edx, edx; dwStackSize
0x180038c9b  xor     ecx, ecx; lpThreadAttributes
0x180038c9d  call    cs:__imp_CreateThread
0x180038ca4  nop     dword ptr [rax+rax+00h]
0x180038ca9  mov     cs:?s_hWorkerThread@ClipboardBrokerFactory@@0PEAXEA, rax; void * ClipboardBrokerFactory::s_hWorkerThread
0x180038cb0  test    rax, rax
0x180038cb3  jz      short loc_180038D02
0x180038cb5  mov     rcx, cs:?s_hServerThreadEvent@ClipboardBrokerFactory@@0PEAXEA; hHandle
0x180038cbc  mov     edx, 3E8h; dwMilliseconds
0x180038cc1  call    cs:__imp_WaitForSingleObject
0x180038cc8  nop     dword ptr [rax+rax+00h]
0x180038ccd  test    eax, eax
0x180038ccf  jz      short loc_180038D02
0x180038cd1  mov     ecx, 8000FFFFh
0x180038cd6  xor     edx, edx
0x180038cd8  mov     [rsp+38h+hr], ecx
0x180038cdc  call    cs:__imp_RoOriginateError
0x180038ce3  nop     dword ptr [rax+rax+00h]
0x180038ce8  mov     rcx, cs:?s_hWorkerThread@ClipboardBrokerFactory@@0PEAXEA; hObject
0x180038cef  call    cs:__imp_CloseHandle
0x180038cf6  nop     dword ptr [rax+rax+00h]
0x180038cfb  mov     cs:?s_hWorkerThread@ClipboardBrokerFactory@@0PEAXEA, rbx; void * ClipboardBrokerFactory::s_hWorkerThread
0x180038d02  mov     ebx, [rsp+38h+hr]
0x180038d06  lea     rcx, ?s_initCS@ClipboardBrokerFactory@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x180038d0d  call    cs:__imp_LeaveCriticalSection
0x180038d14  nop     dword ptr [rax+rax+00h]
0x180038d19  mov     eax, ebx
0x180038d1b  add     rsp, 30h
0x180038d1f  pop     rbx
0x180038d20  retn
```
