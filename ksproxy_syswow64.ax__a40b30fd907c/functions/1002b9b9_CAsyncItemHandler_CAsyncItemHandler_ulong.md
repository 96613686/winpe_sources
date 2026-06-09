# CAsyncItemHandler::CAsyncItemHandler(ulong *)

- ea: `0x1002b9b9`
- end: `0x1002bc67`
- name: `??0CAsyncItemHandler@@QAE@PAK@Z`
- size: `686`
- prototype: `CAsyncItemHandler *__thiscall(CAsyncItemHandler *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10018450`
- `0x1001df3d`
- `0x1001dfb0`

## callees

- `0x1000665f`
- `0x1002b9b9`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1002ba1d`
- `KERNEL32!GetLastError` at `0x1002ba56`
- `KERNEL32!GetLastError` at `0x1002bab3`
- `KERNEL32!GetLastError` at `0x1002bafa`
- `KERNEL32!GetLastError` at `0x1002bb43`
- `KERNEL32!GetLastError` at `0x1002bb92`
- `KERNEL32!GetLastError` at `0x1002ba1d`
- `KERNEL32!GetLastError` at `0x1002ba56`
- `KERNEL32!GetLastError` at `0x1002bab3`
- `KERNEL32!GetLastError` at `0x1002bafa`
- `KERNEL32!GetLastError` at `0x1002bb43`
- `KERNEL32!GetLastError` at `0x1002bb92`
- `KERNEL32!CreateEventW` at `0x1002ba46`
- `KERNEL32!CreateEventW` at `0x1002bb33`
- `KERNEL32!CreateEventW` at `0x1002ba46`
- `KERNEL32!CreateEventW` at `0x1002bb33`
- `KERNEL32!CloseHandle` at `0x1002bbcf`
- `KERNEL32!CloseHandle` at `0x1002bbf4`
- `KERNEL32!CloseHandle` at `0x1002bc0f`
- `KERNEL32!CloseHandle` at `0x1002bc2a`
- `KERNEL32!CloseHandle` at `0x1002bc45`
- `KERNEL32!CloseHandle` at `0x1002bbcf`
- `KERNEL32!CloseHandle` at `0x1002bbf4`
- `KERNEL32!CloseHandle` at `0x1002bc0f`
- `KERNEL32!CloseHandle` at `0x1002bc2a`
- `KERNEL32!CloseHandle` at `0x1002bc45`
- `KERNEL32!CreateThread` at `0x1002bb7e`
- `KERNEL32!CreateThread` at `0x1002bb7e`
- `KERNEL32!CreateSemaphoreW` at `0x1002baa3`
- `KERNEL32!CreateSemaphoreW` at `0x1002baa3`
- `KERNEL32!CreateMutexW` at `0x1002ba10`
- `KERNEL32!CreateMutexW` at `0x1002baea`
- `KERNEL32!CreateMutexW` at `0x1002ba10`
- `KERNEL32!CreateMutexW` at `0x1002baea`

## pseudocode

```c
CAsyncItemHandler *__thiscall CAsyncItemHandler::CAsyncItemHandler(CAsyncItemHandler *this, unsigned int *a2)
{
  HANDLE MutexW; // eax
  DWORD LastError; // esi
  _QWORD *v5; // eax
  USHORT v6; // cx
  HANDLE EventW; // eax
  HANDLE SemaphoreW; // eax
  HANDLE v9; // eax
  HANDLE v10; // eax
  HANDLE Thread; // eax
  void *m_hWakeupEvent; // eax

  this->m_arrayCount = 0;
  this->m_AsyncEvent = 0;
  this->m_hWakeupEvent = 0;
  this->m_hSlotSemaphore = 0;
  this->m_hItemMutex = 0;
  this->m_hThread = 0;
  this->m_wakeupReason = WAKEUP_EXIT;
  this->m_threadId = 0;
  this->m_eventList.head.bLink = &this->m_eventList.tail;
  this->m_eventList.head.fLink = &this->m_eventList.tail;
  this->m_eventList.tail.bLink = &this->m_eventList.head;
  this->m_eventList.tail.fLink = &this->m_eventList.head;
  this->m_eventList.count = 0;
  MutexW = CreateMutexW(0, 0, 0);
  this->m_eventList.mutex = MutexW;
  if ( MutexW )
  {
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_10;
      v6 = 199;
      goto LABEL_9;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  this->m_hWakeupEvent = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      v6 = 200;
LABEL_9:
      WPP_SF_q(v6, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v5[2], LastError);
    }
  }
LABEL_10:
  this->m_hEvents[this->m_arrayCount++] = this->m_hWakeupEvent;
  if ( LastError )
    goto LABEL_42;
  SemaphoreW = CreateSemaphoreW(0, 63, 63, 0);
  this->m_hSlotSemaphore = SemaphoreW;
  if ( !SemaphoreW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_q(0xC9u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    if ( LastError )
      goto LABEL_42;
  }
  v9 = CreateMutexW(0, 0, 0);
  this->m_hItemMutex = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_q(0xCAu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    if ( LastError )
      goto LABEL_42;
  }
  v10 = CreateEventW(0, 0, 1, 0);
  this->m_AsyncEvent = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_q(0xCBu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    if ( LastError )
      goto LABEL_42;
  }
  Thread = CreateThread(0, 0, CAsyncItemHandler::AsyncItemProc, this, 0, &this->m_threadId);
  this->m_hThread = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_q(0xCCu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    if ( LastError )
    {
LABEL_42:
      if ( this->m_eventList.mutex )
      {
        CloseHandle(this->m_eventList.mutex);
        this->m_eventList.mutex = 0;
      }
      m_hWakeupEvent = this->m_hWakeupEvent;
      this->m_arrayCount = 0;
      if ( m_hWakeupEvent )
      {
        CloseHandle(m_hWakeupEvent);
        this->m_hWakeupEvent = 0;
      }
      if ( this->m_hSlotSemaphore )
      {
        CloseHandle(this->m_hSlotSemaphore);
        this->m_hSlotSemaphore = 0;
      }
      if ( this->m_hItemMutex )
      {
        CloseHandle(this->m_hItemMutex);
        this->m_hItemMutex = 0;
      }
      if ( this->m_AsyncEvent )
      {
        CloseHandle(this->m_AsyncEvent);
        this->m_AsyncEvent = 0;
      }
    }
  }
  if ( a2 )
    *a2 = LastError;
  return this;
}

```

## disassembly

```asm
0x1002b9b9  mov     edi, edi
0x1002b9bb  push    ebp
0x1002b9bc  mov     ebp, esp
0x1002b9be  push    ebx
0x1002b9bf  push    esi
0x1002b9c0  push    edi
0x1002b9c1  mov     edi, ecx
0x1002b9c3  xor     ecx, ecx
0x1002b9c5  push    ecx; lpName
0x1002b9c6  push    ecx; bInitialOwner
0x1002b9c7  push    ecx; lpMutexAttributes
0x1002b9c8  lea     esi, [edi+210h]
0x1002b9ce  mov     [edi+200h], ecx
0x1002b9d4  mov     [edi+20Ch], ecx
0x1002b9da  lea     eax, [esi+8]
0x1002b9dd  mov     [edi+228h], ecx
0x1002b9e3  lea     ebx, [edi+238h]
0x1002b9e9  mov     [edi+22Ch], ecx
0x1002b9ef  mov     [edi+230h], ecx
0x1002b9f5  mov     [edi+234h], ecx
0x1002b9fb  mov     [edi+204h], ecx
0x1002ba01  mov     [ebx], ecx
0x1002ba03  mov     [esi+4], eax
0x1002ba06  mov     [esi], eax
0x1002ba08  mov     [esi+0Ch], esi
0x1002ba0b  mov     [eax], esi
0x1002ba0d  mov     [esi+10h], ecx
0x1002ba10  call    ds:__imp__CreateMutexW@12; CreateMutexW(x,x,x)
0x1002ba16  mov     [esi+14h], eax
0x1002ba19  test    eax, eax
0x1002ba1b  jnz     short loc_1002BA3C
0x1002ba1d  call    ds:__imp__GetLastError@0; GetLastError()
0x1002ba23  mov     esi, eax
0x1002ba25  test    esi, esi
0x1002ba27  jz      short loc_1002BA3E
0x1002ba29  mov     eax, _WPP_GLOBAL_Control
0x1002ba2e  cmp     eax, offset _WPP_GLOBAL_Control
0x1002ba33  jz      short loc_1002BA80
0x1002ba35  mov     ecx, 0C7h
0x1002ba3a  jmp     short loc_1002BA6F
0x1002ba3c  xor     esi, esi
0x1002ba3e  push    0; lpName
0x1002ba40  push    0; bInitialState
0x1002ba42  push    0; bManualReset
0x1002ba44  push    0; lpEventAttributes
0x1002ba46  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1002ba4c  mov     [edi+228h], eax
0x1002ba52  test    eax, eax
0x1002ba54  jnz     short loc_1002BA80
0x1002ba56  call    ds:__imp__GetLastError@0; GetLastError()
0x1002ba5c  mov     esi, eax
0x1002ba5e  mov     eax, _WPP_GLOBAL_Control
0x1002ba63  cmp     eax, offset _WPP_GLOBAL_Control
0x1002ba68  jz      short loc_1002BA80
0x1002ba6a  mov     ecx, 0C8h; MessageNumber
0x1002ba6f  push    esi; char
0x1002ba70  push    dword ptr [eax+14h]
0x1002ba73  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002ba78  push    dword ptr [eax+10h]; LoggerHandle
0x1002ba7b  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002ba80  mov     ecx, [edi+200h]
0x1002ba86  mov     eax, [edi+228h]
0x1002ba8c  mov     [edi+ecx*4], eax
0x1002ba8f  inc     dword ptr [edi+200h]
0x1002ba95  test    esi, esi
0x1002ba97  jnz     loc_1002BBC4
0x1002ba9d  push    esi; lpName
0x1002ba9e  push    3Fh ; '?'; lMaximumCount
0x1002baa0  push    3Fh ; '?'; lInitialCount
0x1002baa2  push    esi; lpSemaphoreAttributes
0x1002baa3  call    ds:__imp__CreateSemaphoreW@16; CreateSemaphoreW(x,x,x,x)
0x1002baa9  mov     [edi+22Ch], eax
0x1002baaf  test    eax, eax
0x1002bab1  jnz     short loc_1002BAE5
0x1002bab3  call    ds:__imp__GetLastError@0; GetLastError()
0x1002bab9  mov     esi, eax
0x1002babb  mov     eax, _WPP_GLOBAL_Control
0x1002bac0  cmp     eax, offset _WPP_GLOBAL_Control
0x1002bac5  jz      short loc_1002BADD
0x1002bac7  push    esi; char
0x1002bac8  push    dword ptr [eax+14h]
0x1002bacb  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002bad0  mov     ecx, 0C9h; MessageNumber
0x1002bad5  push    dword ptr [eax+10h]; LoggerHandle
0x1002bad8  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002badd  test    esi, esi
0x1002badf  jnz     loc_1002BBC4
0x1002bae5  xor     eax, eax
0x1002bae7  push    eax; lpName
0x1002bae8  push    eax; bInitialOwner
0x1002bae9  push    eax; lpMutexAttributes
0x1002baea  call    ds:__imp__CreateMutexW@12; CreateMutexW(x,x,x)
0x1002baf0  mov     [edi+230h], eax
0x1002baf6  test    eax, eax
0x1002baf8  jnz     short loc_1002BB2C
0x1002bafa  call    ds:__imp__GetLastError@0; GetLastError()
0x1002bb00  mov     esi, eax
0x1002bb02  mov     eax, _WPP_GLOBAL_Control
0x1002bb07  cmp     eax, offset _WPP_GLOBAL_Control
0x1002bb0c  jz      short loc_1002BB24
0x1002bb0e  push    esi; char
0x1002bb0f  push    dword ptr [eax+14h]
0x1002bb12  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002bb17  mov     ecx, 0CAh; MessageNumber
0x1002bb1c  push    dword ptr [eax+10h]; LoggerHandle
0x1002bb1f  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002bb24  test    esi, esi
0x1002bb26  jnz     loc_1002BBC4
0x1002bb2c  xor     eax, eax
0x1002bb2e  push    eax; lpName
0x1002bb2f  push    1; bInitialState
0x1002bb31  push    eax; bManualReset
0x1002bb32  push    eax; lpEventAttributes
0x1002bb33  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1002bb39  mov     [edi+20Ch], eax
0x1002bb3f  test    eax, eax
0x1002bb41  jnz     short loc_1002BB71
0x1002bb43  call    ds:__imp__GetLastError@0; GetLastError()
0x1002bb49  mov     esi, eax
0x1002bb4b  mov     eax, _WPP_GLOBAL_Control
0x1002bb50  cmp     eax, offset _WPP_GLOBAL_Control
0x1002bb55  jz      short loc_1002BB6D
0x1002bb57  push    esi; char
0x1002bb58  push    dword ptr [eax+14h]
0x1002bb5b  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002bb60  mov     ecx, 0CBh; MessageNumber
0x1002bb65  push    dword ptr [eax+10h]; LoggerHandle
0x1002bb68  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002bb6d  test    esi, esi
0x1002bb6f  jnz     short loc_1002BBC4
0x1002bb71  push    ebx; lpThreadId
0x1002bb72  push    0; dwCreationFlags
0x1002bb74  push    edi; lpParameter
0x1002bb75  push    offset ?AsyncItemProc@CAsyncItemHandler@@KGKPAV1@@Z; lpStartAddress
0x1002bb7a  push    0; dwStackSize
0x1002bb7c  push    0; lpThreadAttributes
0x1002bb7e  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x1002bb84  mov     [edi+234h], eax
0x1002bb8a  test    eax, eax
0x1002bb8c  jnz     loc_1002BC55
0x1002bb92  call    ds:__imp__GetLastError@0; GetLastError()
0x1002bb98  mov     esi, eax
0x1002bb9a  mov     eax, _WPP_GLOBAL_Control
0x1002bb9f  cmp     eax, offset _WPP_GLOBAL_Control
0x1002bba4  jz      short loc_1002BBBC
0x1002bba6  push    esi; char
0x1002bba7  push    dword ptr [eax+14h]
0x1002bbaa  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002bbaf  mov     ecx, 0CCh; MessageNumber
0x1002bbb4  push    dword ptr [eax+10h]; LoggerHandle
0x1002bbb7  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002bbbc  test    esi, esi
0x1002bbbe  jz      loc_1002BC55
0x1002bbc4  mov     eax, [edi+224h]
0x1002bbca  test    eax, eax
0x1002bbcc  jz      short loc_1002BBDF
0x1002bbce  push    eax; hObject
0x1002bbcf  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1002bbd5  mov     dword ptr [edi+224h], 0
0x1002bbdf  mov     eax, [edi+228h]
0x1002bbe5  mov     dword ptr [edi+200h], 0
0x1002bbef  test    eax, eax
0x1002bbf1  jz      short loc_1002BC04
0x1002bbf3  push    eax; hObject
0x1002bbf4  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1002bbfa  mov     dword ptr [edi+228h], 0
0x1002bc04  mov     eax, [edi+22Ch]
0x1002bc0a  test    eax, eax
0x1002bc0c  jz      short loc_1002BC1F
0x1002bc0e  push    eax; hObject
0x1002bc0f  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1002bc15  mov     dword ptr [edi+22Ch], 0
0x1002bc1f  mov     eax, [edi+230h]
0x1002bc25  test    eax, eax
0x1002bc27  jz      short loc_1002BC3A
0x1002bc29  push    eax; hObject
0x1002bc2a  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1002bc30  mov     dword ptr [edi+230h], 0
0x1002bc3a  mov     eax, [edi+20Ch]
0x1002bc40  test    eax, eax
0x1002bc42  jz      short loc_1002BC55
0x1002bc44  push    eax; hObject
0x1002bc45  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1002bc4b  mov     dword ptr [edi+20Ch], 0
0x1002bc55  mov     eax, [ebp+arg_0]
0x1002bc58  test    eax, eax
0x1002bc5a  jz      short loc_1002BC5E
0x1002bc5c  mov     [eax], esi
0x1002bc5e  mov     eax, edi
0x1002bc60  pop     edi
0x1002bc61  pop     esi
0x1002bc62  pop     ebx
0x1002bc63  pop     ebp
0x1002bc64  retn    4
```
