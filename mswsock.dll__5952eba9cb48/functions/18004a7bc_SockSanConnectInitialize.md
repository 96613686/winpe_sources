# SockSanConnectInitialize

- ea: `0x18004a7bc`
- end: `0x18004aa78`
- name: `SockSanConnectInitialize`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180049768`

## callees

- `0x180004558`
- `0x180022bd2`
- `0x1800239e4`
- `0x180038104`
- `0x18003aec4`
- `0x18004a7bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004a989`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004a989`
- `ntdll!NtCreateEvent` at `0x18004a874`
- `ntdll!NtCreateEvent` at `0x18004a8dc`
- `ntdll!NtCreateEvent` at `0x18004a874`
- `ntdll!NtCreateEvent` at `0x18004a8dc`
- `ntdll!NtClose` at `0x18004a9e3`
- `ntdll!NtClose` at `0x18004aa02`
- `ntdll!NtClose` at `0x18004a9e3`
- `ntdll!NtClose` at `0x18004aa02`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004aa31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004aa31`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004a8b5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004a8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a835`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18004a818`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18004a818`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004aa54`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004aa54`

## pseudocode

```c
__int64 SockSanConnectInitialize()
{
  DWORD LastError; // eax
  __int64 v1; // rcx
  __int64 v2; // rsi
  NTSTATUS v3; // eax
  __int64 v4; // rcx
  int v5; // r15d
  NTSTATUS Event; // eax
  __int64 v7; // rcx
  __int64 WinsockThreadData; // rax
  signed int i; // r12d
  void *EventHandle; // [rsp+70h] [rbp+8h] BYREF
  HMODULE phModule; // [rsp+78h] [rbp+10h] BYREF

  phModule = 0;
  EventHandle = 0;
  ExitConnectThread = 0;
  memset_0(ConnectData, 0, 0x200u);
  SockSanNumWaitEvents = 0;
  CheckForStuckLargeSendsThreadIdleCount = 0;
  ConnectThreadWaitTimeout = 1;
  if ( GetModuleHandleExA(4u, (LPCSTR)WSPStartup, &phModule) )
  {
    v2 = 0;
    v3 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0);
    if ( v3 >= 0 )
    {
      InitializeCriticalSection(&ConnCritSec);
      v5 = 1;
      Event = NtCreateEvent(ConnectData, 0x1F0003u, 0, SynchronizationEvent, 0);
      if ( Event >= 0 )
      {
        SockSanNumWaitEvents = 1;
        WinsockThreadData = AllocateWinsockThreadData();
        v2 = WinsockThreadData;
        if ( WinsockThreadData )
        {
          *(_QWORD *)(WinsockThreadData + 24) = phModule;
          *(_QWORD *)(WinsockThreadData + 16) = EventHandle;
          *(_DWORD *)(WinsockThreadData + 40) = 0;
          *(_QWORD *)(WinsockThreadData + 48) = 0;
          *(_QWORD *)(WinsockThreadData + 56) = 0;
          ConnectThreadHandle = CreateThread(
                                  0,
                                  0,
                                  (LPTHREAD_START_ROUTINE)ConnectThread,
                                  (LPVOID)WinsockThreadData,
                                  0,
                                  &ConnectThreadId);
          if ( ConnectThreadHandle )
            return 1;
        }
        else if ( (xmmword_180063D60 & 2) != 0 )
        {
          WPP_SF_(1025, 259, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
        }
      }
      else if ( (xmmword_180063D60 & 2) != 0 )
      {
        WPP_SF_l(v7, 258, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, (unsigned int)Event);
      }
      if ( EventHandle )
        NtClose(EventHandle);
    }
    else
    {
      v5 = 0;
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v4, 256, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, (unsigned int)v3);
      EventHandle = 0;
    }
    for ( i = 0; i < (int)SockSanNumWaitEvents; ++i )
    {
      NtClose(ConnectData[i]);
      ConnectData[i] = 0;
    }
    SockSanNumWaitEvents = 0;
    if ( v5 )
      DeleteCriticalSection(&ConnCritSec);
    if ( v2 )
      FreeWinsockThreadData(v2);
    if ( phModule )
      FreeLibrary(phModule);
  }
  else if ( (xmmword_180063D60 & 2) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_l(v1, 255, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x18004a7bc  mov     [rsp+arg_18], rbx
0x18004a7c1  push    rsi
0x18004a7c2  push    rdi
0x18004a7c3  push    r12
0x18004a7c5  push    r13
0x18004a7c7  push    r15
0x18004a7c9  sub     rsp, 40h
0x18004a7cd  xor     edi, edi
0x18004a7cf  mov     [rsp+68h+phModule], rdi
0x18004a7d4  mov     [rsp+68h+EventHandle], rdi
0x18004a7d9  mov     cs:ExitConnectThread, edi
0x18004a7df  xor     edx, edx; Val
0x18004a7e1  mov     r8d, 200h; Size
0x18004a7e7  lea     r13, ConnectData
0x18004a7ee  mov     rcx, r13; void *
0x18004a7f1  call    memset_0
0x18004a7f6  mov     cs:SockSanNumWaitEvents, edi
0x18004a7fc  mov     cs:CheckForStuckLargeSendsThreadIdleCount, edi
0x18004a802  mov     cs:ConnectThreadWaitTimeout, 1
0x18004a809  lea     r8, [rsp+68h+phModule]; phModule
0x18004a80e  lea     rdx, WSPStartup; lpModuleName
0x18004a815  lea     ecx, [rdi+4]; dwFlags
0x18004a818  call    cs:__imp_GetModuleHandleExA
0x18004a81f  nop     dword ptr [rax+rax+00h]
0x18004a824  test    eax, eax
0x18004a826  jnz     short loc_18004A85A
0x18004a828  test    byte ptr cs:xmmword_180063D60, 2
0x18004a82f  jz      loc_18004AA60
0x18004a835  call    cs:__imp_GetLastError
0x18004a83c  nop     dword ptr [rax+rax+00h]
0x18004a841  mov     r9d, eax
0x18004a844  mov     edx, 0FFh
0x18004a849  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a850  call    WPP_SF_l
0x18004a855  jmp     loc_18004AA60
0x18004a85a  mov     rsi, rdi
0x18004a85d  mov     [rsp+68h+InitialState], dil; InitialState
0x18004a862  xor     r9d, r9d; EventType
0x18004a865  xor     r8d, r8d; ObjectAttributes
0x18004a868  mov     ebx, 1F0003h
0x18004a86d  mov     edx, ebx; DesiredAccess
0x18004a86f  lea     rcx, [rsp+68h+EventHandle]; EventHandle
0x18004a874  call    cs:__imp_NtCreateEvent
0x18004a87b  nop     dword ptr [rax+rax+00h]
0x18004a880  test    eax, eax
0x18004a882  jns     short loc_18004A8AE
0x18004a884  mov     r15d, edi
0x18004a887  test    byte ptr cs:xmmword_180063D60, 2
0x18004a88e  jz      short loc_18004A8A4
0x18004a890  mov     edx, 100h
0x18004a895  mov     r9d, eax
0x18004a898  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a89f  call    WPP_SF_l
0x18004a8a4  mov     [rsp+68h+EventHandle], rdi
0x18004a8a9  jmp     loc_18004A9EF
0x18004a8ae  lea     rcx, ConnCritSec; lpCriticalSection
0x18004a8b5  call    cs:__imp_InitializeCriticalSection
0x18004a8bc  nop     dword ptr [rax+rax+00h]
0x18004a8c1  mov     r15d, 1
0x18004a8c7  mov     [rsp+68h+var_38], r15d
0x18004a8cc  mov     [rsp+68h+InitialState], dil; InitialState
0x18004a8d1  mov     r9d, r15d; EventType
0x18004a8d4  xor     r8d, r8d; ObjectAttributes
0x18004a8d7  mov     edx, ebx; DesiredAccess
0x18004a8d9  mov     rcx, r13; EventHandle
0x18004a8dc  call    cs:__imp_NtCreateEvent
0x18004a8e3  nop     dword ptr [rax+rax+00h]
0x18004a8e8  test    eax, eax
0x18004a8ea  jns     short loc_18004A912
0x18004a8ec  test    byte ptr cs:xmmword_180063D60, 2
0x18004a8f3  jz      loc_18004A9D9
0x18004a8f9  mov     edx, 102h
0x18004a8fe  mov     r9d, eax
0x18004a901  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a908  call    WPP_SF_l
0x18004a90d  jmp     loc_18004A9D9
0x18004a912  mov     cs:SockSanNumWaitEvents, r15d
0x18004a919  call    AllocateWinsockThreadData
0x18004a91e  mov     rsi, rax
0x18004a921  test    rax, rax
0x18004a924  jnz     short loc_18004A94E
0x18004a926  test    byte ptr cs:xmmword_180063D60, 2
0x18004a92d  jz      loc_18004A9D9
0x18004a933  mov     edx, 103h
0x18004a938  mov     ecx, 401h
0x18004a93d  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a944  call    WPP_SF_
0x18004a949  jmp     loc_18004A9D9
0x18004a94e  mov     rax, [rsp+68h+phModule]
0x18004a953  mov     [rsi+18h], rax
0x18004a957  mov     rax, [rsp+68h+EventHandle]
0x18004a95c  mov     [rsi+10h], rax
0x18004a960  mov     [rsi+28h], edi
0x18004a963  mov     [rsi+30h], rdi
0x18004a967  mov     [rsi+38h], rdi
0x18004a96b  lea     rax, ConnectThreadId
0x18004a972  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18004a977  mov     dword ptr [rsp+68h+InitialState], edi; dwCreationFlags
0x18004a97b  mov     r9, rsi; lpParameter
0x18004a97e  lea     r8, ConnectThread; lpStartAddress
0x18004a985  xor     edx, edx; dwStackSize
0x18004a987  xor     ecx, ecx; lpThreadAttributes
0x18004a989  call    cs:__imp_CreateThread
0x18004a990  nop     dword ptr [rax+rax+00h]
0x18004a995  mov     cs:ConnectThreadHandle, rax
0x18004a99c  test    rax, rax
0x18004a99f  jz      short loc_18004A9D9
0x18004a9a1  mov     eax, r15d
0x18004a9a4  jmp     loc_18004AA62
0x18004a9a9  xor     r15d, r15d
0x18004a9ac  mov     [rsp+68h+var_38], r15d
0x18004a9b1  test    byte ptr cs:xmmword_180063D60, 2
0x18004a9b8  jz      short loc_18004A9CE
0x18004a9ba  mov     r9d, eax
0x18004a9bd  mov     edx, 101h
0x18004a9c2  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a9c9  call    WPP_SF_l
0x18004a9ce  xor     edi, edi
0x18004a9d0  lea     r13, ConnectData
0x18004a9d7  mov     esi, edi
0x18004a9d9  mov     rcx, [rsp+68h+EventHandle]; Handle
0x18004a9de  test    rcx, rcx
0x18004a9e1  jz      short loc_18004A9EF
0x18004a9e3  call    cs:__imp_NtClose
0x18004a9ea  nop     dword ptr [rax+rax+00h]
0x18004a9ef  mov     r12d, edi
0x18004a9f2  cmp     cs:SockSanNumWaitEvents, edi
0x18004a9f8  jle     short loc_18004AA1F
0x18004a9fa  movsxd  rbx, r12d
0x18004a9fd  mov     rcx, [r13+rbx*8+0]; Handle
0x18004aa02  call    cs:__imp_NtClose
0x18004aa09  nop     dword ptr [rax+rax+00h]
0x18004aa0e  mov     [r13+rbx*8+0], rdi
0x18004aa13  inc     r12d
0x18004aa16  cmp     r12d, cs:SockSanNumWaitEvents
0x18004aa1d  jl      short loc_18004A9FA
0x18004aa1f  mov     cs:SockSanNumWaitEvents, edi
0x18004aa25  test    r15d, r15d
0x18004aa28  jz      short loc_18004AA3D
0x18004aa2a  lea     rcx, ConnCritSec; lpCriticalSection
0x18004aa31  call    cs:__imp_DeleteCriticalSection
0x18004aa38  nop     dword ptr [rax+rax+00h]
0x18004aa3d  test    rsi, rsi
0x18004aa40  jz      short loc_18004AA4A
0x18004aa42  mov     rcx, rsi
0x18004aa45  call    FreeWinsockThreadData
0x18004aa4a  mov     rcx, [rsp+68h+phModule]; hLibModule
0x18004aa4f  test    rcx, rcx
0x18004aa52  jz      short loc_18004AA60
0x18004aa54  call    cs:__imp_FreeLibrary
0x18004aa5b  nop     dword ptr [rax+rax+00h]
0x18004aa60  xor     eax, eax
0x18004aa62  mov     rbx, [rsp+68h+arg_18]
0x18004aa6a  add     rsp, 40h
0x18004aa6e  pop     r15
0x18004aa70  pop     r13
0x18004aa72  pop     r12
0x18004aa74  pop     rdi
0x18004aa75  pop     rsi
0x18004aa76  retn
```
