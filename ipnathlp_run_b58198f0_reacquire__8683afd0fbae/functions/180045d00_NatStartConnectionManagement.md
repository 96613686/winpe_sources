# NatStartConnectionManagement

- ea: `0x180045d00`
- end: `0x1800461f7`
- name: `NatStartConnectionManagement`
- size: `1271`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180073a7c`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x1800202e0`
- `0x180045d00`
- `0x18004ff48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045d53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045d53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045dec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004607a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800461aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045d6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045dec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004607a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800461aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045e75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045eaa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045f42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045fae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045e75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045eaa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045f42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800460bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800460df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004614b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800460bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800460df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004614b`
- `ntdll!RtlRegisterWait` at `0x180045ee9`
- `ntdll!RtlRegisterWait` at `0x180046022`
- `ntdll!RtlRegisterWait` at `0x180045ee9`
- `ntdll!RtlRegisterWait` at `0x180046022`
- `ntdll!RtlNtStatusToDosError` at `0x180045efd`
- `ntdll!RtlNtStatusToDosError` at `0x18004603a`
- `ntdll!RtlNtStatusToDosError` at `0x180045efd`
- `ntdll!RtlNtStatusToDosError` at `0x18004603a`
- `ntdll!RtlDeregisterWaitEx` at `0x180046099`
- `ntdll!RtlDeregisterWaitEx` at `0x180046105`
- `ntdll!RtlDeregisterWaitEx` at `0x180046099`
- `ntdll!RtlDeregisterWaitEx` at `0x180046105`
- `WS2_32!__imp_htonl` at `0x180045daa`
- `WS2_32!__imp_htonl` at `0x180045daa`

## pseudocode

```c
__int64 NatStartConnectionManagement()
{
  _QWORD *v0; // rcx
  __int64 v1; // rdx
  DWORD v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v6; // eax
  unsigned int v7; // edi
  ULONG v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD LastError; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  int v14; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
  EnterCriticalSection(&NatInterfaceLock);
  if ( !NatConnectionNotifyEvent )
  {
    INADDR_LOOPBACK_NO = htonl(0x7F000001u);
    qword_1800AFA10 = (__int64)&NatConnectionList;
    NatConnectionList = (struct _NAT_CONNECTION_INFO *)&NatConnectionList;
    v2 = 1003;
    if ( !AcquireComponentReference(&NatComponentReference) )
    {
      LeaveCriticalSection(&NatInterfaceLock);
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return v2;
      }
      v4 = 196;
LABEL_20:
      WPP_SF_d(v3[2], v4, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v2);
      return v2;
    }
    if ( !AcquireComponentReference(&NatComponentReference) )
    {
      LeaveCriticalSection(&NatInterfaceLock);
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&NatComponentReference);
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return v2;
      }
      v4 = 197;
      goto LABEL_20;
    }
    NatConnectionNotifyEvent = CreateEventW(0, 0, 0, 0);
    if ( NatConnectionNotifyEvent && (NatConnectionNotifyRundownEvent = CreateEventW(0, 0, 0, 0)) != 0 )
    {
      v6 = RtlRegisterWait(
             &NatConnectionNotifyWaitHandle,
             NatConnectionNotifyEvent,
             NatConnectionNotifyCallbackRoutine,
             0,
             0xFFFFFFFF,
             0);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = RtlNtStatusToDosError(v6);
        v2 = v8;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_47;
        }
        v10 = 198;
        goto LABEL_46;
      }
      NatConfigurationChangedEvent = CreateEventW(0, 0, 0, 0);
      if ( NatConfigurationChangedEvent )
      {
        NatConfigurationChangedRundownEvent = CreateEventW(0, 0, 0, 0);
        if ( NatConfigurationChangedRundownEvent )
        {
          v14 = RtlRegisterWait(
                  &NatConfigurationChangedWaitHandle,
                  NatConfigurationChangedEvent,
                  NatConfigurationChangedCallbackRoutine,
                  0,
                  0xFFFFFFFF,
                  0);
          v7 = v14;
          if ( v14 >= 0 )
          {
            LeaveCriticalSection(&NatInterfaceLock);
            NatProcessConfigurationChanged();
            v0 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
            {
              return 0;
            }
            v1 = 202;
            goto LABEL_67;
          }
          v8 = RtlNtStatusToDosError(v14);
          v2 = v8;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_47;
          }
          v10 = 201;
LABEL_46:
          WPP_SF_Dd(v9[2], v10, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v7, v8);
          goto LABEL_47;
        }
        LastError = GetLastError();
        v2 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_47;
        }
        v13 = 200;
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_47;
        }
        v13 = 199;
      }
      WPP_SF_d(v12[2], v13, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, LastError);
    }
    else
    {
      v2 = GetLastError();
    }
LABEL_47:
    LeaveCriticalSection(&NatInterfaceLock);
    if ( NatConfigurationChangedWaitHandle )
    {
      RtlDeregisterWaitEx(NatConfigurationChangedWaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      NatConfigurationChangedWaitHandle = 0;
    }
    if ( NatConfigurationChangedEvent )
    {
      CloseHandle(NatConfigurationChangedEvent);
      NatConfigurationChangedEvent = 0;
    }
    if ( NatConfigurationChangedRundownEvent )
    {
      CloseHandle(NatConfigurationChangedRundownEvent);
      NatConfigurationChangedRundownEvent = 0;
    }
    if ( NatConnectionNotifyWaitHandle )
    {
      RtlDeregisterWaitEx(NatConnectionNotifyWaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      NatConnectionNotifyWaitHandle = 0;
    }
    if ( NatConnectionNotifyEvent )
    {
      CloseHandle(NatConnectionNotifyEvent);
      NatConnectionNotifyEvent = 0;
    }
    if ( NatConnectionNotifyRundownEvent )
    {
      CloseHandle(NatConnectionNotifyRundownEvent);
      NatConnectionNotifyRundownEvent = 0;
    }
    ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&NatComponentReference);
    ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&NatComponentReference);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
    {
      return v2;
    }
    v4 = 203;
    goto LABEL_20;
  }
  LeaveCriticalSection(&NatInterfaceLock);
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
  {
    return 0;
  }
  v1 = 195;
LABEL_67:
  WPP_SF_d(v0[2], v1, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180045d00  push    rbx
0x180045d02  push    rbp
0x180045d03  push    rdi
0x180045d04  push    r13
0x180045d06  push    r14
0x180045d08  push    r15
0x180045d0a  sub     rsp, 38h
0x180045d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d15  lea     r14, WPP_GLOBAL_Control
0x180045d1c  lea     r15, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180045d23  mov     ebp, 200h
0x180045d28  cmp     rcx, r14
0x180045d2b  jz      short loc_180045D49
0x180045d2d  test    [rcx+1Ch], ebp
0x180045d30  jz      short loc_180045D49
0x180045d32  cmp     byte ptr [rcx+19h], 6
0x180045d36  jb      short loc_180045D49
0x180045d38  mov     rcx, [rcx+10h]
0x180045d3c  mov     edx, 0C2h
0x180045d41  mov     r8, r15
0x180045d44  call    WPP_SF_
0x180045d49  lea     r13, NatInterfaceLock
0x180045d50  mov     rcx, r13; lpCriticalSection
0x180045d53  call    cs:__imp_EnterCriticalSection
0x180045d5a  nop     dword ptr [rax+rax+00h]
0x180045d5f  cmp     cs:NatConnectionNotifyEvent, 0
0x180045d67  jz      short loc_180045DA5
0x180045d69  mov     rcx, r13; lpCriticalSection
0x180045d6c  call    cs:__imp_LeaveCriticalSection
0x180045d73  nop     dword ptr [rax+rax+00h]
0x180045d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d7f  cmp     rcx, r14
0x180045d82  jz      loc_1800461E6
0x180045d88  test    [rcx+1Ch], ebp
0x180045d8b  jz      loc_1800461E6
0x180045d91  cmp     byte ptr [rcx+19h], 6
0x180045d95  jb      loc_1800461E6
0x180045d9b  mov     edx, 0C3h
0x180045da0  jmp     loc_1800461D7
0x180045da5  mov     ecx, 7F000001h; hostlong
0x180045daa  call    cs:__imp_htonl
0x180045db1  nop     dword ptr [rax+rax+00h]
0x180045db6  mov     cs:?INADDR_LOOPBACK_NO@@3KA, eax; ulong INADDR_LOOPBACK_NO
0x180045dbc  lea     rdi, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; _COMPONENT_REFERENCE NatComponentReference
0x180045dc3  lea     rax, NatConnectionList
0x180045dca  mov     rcx, rdi; lpCriticalSection
0x180045dcd  mov     cs:qword_1800AFA10, rax
0x180045dd4  mov     cs:NatConnectionList, rax
0x180045ddb  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x180045de0  mov     ebx, 3EBh
0x180045de5  test    al, al
0x180045de7  jnz     short loc_180045E16
0x180045de9  mov     rcx, r13; lpCriticalSection
0x180045dec  call    cs:__imp_LeaveCriticalSection
0x180045df3  nop     dword ptr [rax+rax+00h]
0x180045df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180045dff  cmp     rcx, r14
0x180045e02  jz      short loc_180045E64
0x180045e04  test    [rcx+1Ch], ebp
0x180045e07  jz      short loc_180045E64
0x180045e09  cmp     byte ptr [rcx+19h], 6
0x180045e0d  jb      short loc_180045E64
0x180045e0f  mov     edx, 0C4h
0x180045e14  jmp     short loc_180045E55
0x180045e16  mov     rcx, rdi; lpCriticalSection
0x180045e19  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x180045e1e  test    al, al
0x180045e20  jnz     short loc_180045E6B
0x180045e22  mov     rcx, r13; lpCriticalSection
0x180045e25  call    cs:__imp_LeaveCriticalSection
0x180045e2c  nop     dword ptr [rax+rax+00h]
0x180045e31  mov     rcx, rdi; struct _COMPONENT_REFERENCE *
0x180045e34  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180045e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e40  cmp     rcx, r14
0x180045e43  jz      short loc_180045E64
0x180045e45  test    [rcx+1Ch], ebp
0x180045e48  jz      short loc_180045E64
0x180045e4a  cmp     byte ptr [rcx+19h], 6
0x180045e4e  jb      short loc_180045E64
0x180045e50  mov     edx, 0C5h
0x180045e55  mov     rcx, [rcx+10h]
0x180045e59  mov     r9d, ebx
0x180045e5c  mov     r8, r15
0x180045e5f  call    WPP_SF_d
0x180045e64  mov     eax, ebx
0x180045e66  jmp     loc_1800461E8
0x180045e6b  xor     r9d, r9d; lpName
0x180045e6e  xor     r8d, r8d; bInitialState
0x180045e71  xor     edx, edx; bManualReset
0x180045e73  xor     ecx, ecx; lpEventAttributes
0x180045e75  call    cs:__imp_CreateEventW
0x180045e7c  nop     dword ptr [rax+rax+00h]
0x180045e81  mov     cs:NatConnectionNotifyEvent, rax
0x180045e88  test    rax, rax
0x180045e8b  jnz     short loc_180045EA0
0x180045e8d  call    cs:__imp_GetLastError
0x180045e94  nop     dword ptr [rax+rax+00h]
0x180045e99  mov     ebx, eax
0x180045e9b  jmp     loc_180046077
0x180045ea0  xor     r9d, r9d; lpName
0x180045ea3  xor     r8d, r8d; bInitialState
0x180045ea6  xor     edx, edx; bManualReset
0x180045ea8  xor     ecx, ecx; lpEventAttributes
0x180045eaa  call    cs:__imp_CreateEventW
0x180045eb1  nop     dword ptr [rax+rax+00h]
0x180045eb6  mov     cs:?NatConnectionNotifyRundownEvent@@3PEAXEA, rax; void * NatConnectionNotifyRundownEvent
0x180045ebd  test    rax, rax
0x180045ec0  jz      short loc_180045E8D
0x180045ec2  mov     rdx, cs:NatConnectionNotifyEvent; hObject
0x180045ec9  lea     r8, ?NatConnectionNotifyCallbackRoutine@@YAXPEAXE@Z; Callback
0x180045ed0  or      ebx, 0FFFFFFFFh
0x180045ed3  mov     [rsp+68h+ulFlags], 0; ulFlags
0x180045edb  xor     r9d, r9d; pvContext
0x180045ede  mov     [rsp+68h+ulMilliseconds], ebx; ulMilliseconds
0x180045ee2  lea     rcx, ?NatConnectionNotifyWaitHandle@@3PEAXEA; phNewWaitObject
0x180045ee9  call    cs:__imp_RtlRegisterWait
0x180045ef0  nop     dword ptr [rax+rax+00h]
0x180045ef5  mov     edi, eax
0x180045ef7  test    eax, eax
0x180045ef9  jns     short loc_180045F38
0x180045efb  mov     ecx, eax; Status
0x180045efd  call    cs:__imp_RtlNtStatusToDosError
0x180045f04  nop     dword ptr [rax+rax+00h]
0x180045f09  mov     ebx, eax
0x180045f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f12  cmp     rcx, r14
0x180045f15  jz      loc_180046077
0x180045f1b  test    [rcx+1Ch], ebp
0x180045f1e  jz      loc_180046077
0x180045f24  cmp     byte ptr [rcx+19h], 2
0x180045f28  jb      loc_180046077
0x180045f2e  mov     edx, 0C6h
0x180045f33  jmp     loc_180046064
0x180045f38  xor     r9d, r9d; lpName
0x180045f3b  xor     r8d, r8d; bInitialState
0x180045f3e  xor     edx, edx; bManualReset
0x180045f40  xor     ecx, ecx; lpEventAttributes
0x180045f42  call    cs:__imp_CreateEventW
0x180045f49  nop     dword ptr [rax+rax+00h]
0x180045f4e  mov     cs:NatConfigurationChangedEvent, rax
0x180045f55  test    rax, rax
0x180045f58  jnz     short loc_180045FA4
0x180045f5a  call    cs:__imp_GetLastError
0x180045f61  nop     dword ptr [rax+rax+00h]
0x180045f66  mov     ebx, eax
0x180045f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f6f  cmp     rcx, r14
0x180045f72  jz      loc_180046077
0x180045f78  test    [rcx+1Ch], ebp
0x180045f7b  jz      loc_180046077
0x180045f81  cmp     byte ptr [rcx+19h], 2
0x180045f85  jb      loc_180046077
0x180045f8b  mov     edx, 0C7h
0x180045f90  mov     rcx, [rcx+10h]
0x180045f94  mov     r9d, eax
0x180045f97  mov     r8, r15
0x180045f9a  call    WPP_SF_d
0x180045f9f  jmp     loc_180046077
0x180045fa4  xor     r9d, r9d; lpName
0x180045fa7  xor     r8d, r8d; bInitialState
0x180045faa  xor     edx, edx; bManualReset
0x180045fac  xor     ecx, ecx; lpEventAttributes
0x180045fae  call    cs:__imp_CreateEventW
0x180045fb5  nop     dword ptr [rax+rax+00h]
0x180045fba  mov     cs:?NatConfigurationChangedRundownEvent@@3PEAXEA, rax; void * NatConfigurationChangedRundownEvent
0x180045fc1  test    rax, rax
0x180045fc4  jnz     short loc_180045FFE
0x180045fc6  call    cs:__imp_GetLastError
0x180045fcd  nop     dword ptr [rax+rax+00h]
0x180045fd2  mov     ebx, eax
0x180045fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180045fdb  cmp     rcx, r14
0x180045fde  jz      loc_180046077
0x180045fe4  test    [rcx+1Ch], ebp
0x180045fe7  jz      loc_180046077
0x180045fed  cmp     byte ptr [rcx+19h], 2
0x180045ff1  jb      loc_180046077
0x180045ff7  mov     edx, 0C8h
0x180045ffc  jmp     short loc_180045F90
0x180045ffe  mov     rdx, cs:NatConfigurationChangedEvent; hObject
0x180046005  lea     r8, ?NatConfigurationChangedCallbackRoutine@@YAXPEAXE@Z; Callback
0x18004600c  mov     [rsp+68h+ulFlags], 0; ulFlags
0x180046014  lea     rcx, ?NatConfigurationChangedWaitHandle@@3PEAXEA; phNewWaitObject
0x18004601b  xor     r9d, r9d; pvContext
0x18004601e  mov     [rsp+68h+ulMilliseconds], ebx; ulMilliseconds
0x180046022  call    cs:__imp_RtlRegisterWait
0x180046029  nop     dword ptr [rax+rax+00h]
0x18004602e  mov     edi, eax
0x180046030  test    eax, eax
0x180046032  jns     loc_1800461A7
0x180046038  mov     ecx, eax; Status
0x18004603a  call    cs:__imp_RtlNtStatusToDosError
0x180046041  nop     dword ptr [rax+rax+00h]
0x180046046  mov     ebx, eax
0x180046048  mov     rcx, cs:WPP_GLOBAL_Control
0x18004604f  cmp     rcx, r14
0x180046052  jz      short loc_180046077
0x180046054  test    [rcx+1Ch], ebp
0x180046057  jz      short loc_180046077
0x180046059  cmp     byte ptr [rcx+19h], 2
0x18004605d  jb      short loc_180046077
0x18004605f  mov     edx, 0C9h
0x180046064  mov     rcx, [rcx+10h]
0x180046068  mov     r9d, edi
0x18004606b  mov     r8, r15
0x18004606e  mov     [rsp+68h+ulMilliseconds], eax
0x180046072  call    WPP_SF_Dd
0x180046077  mov     rcx, r13; lpCriticalSection
0x18004607a  call    cs:__imp_LeaveCriticalSection
0x180046081  nop     dword ptr [rax+rax+00h]
0x180046086  mov     rcx, cs:?NatConfigurationChangedWaitHandle@@3PEAXEA; hWaitHandle
0x18004608d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180046091  test    rcx, rcx
0x180046094  jz      short loc_1800460B0
0x180046096  mov     rdx, rdi; hCompletionEvent
0x180046099  call    cs:__imp_RtlDeregisterWaitEx
0x1800460a0  nop     dword ptr [rax+rax+00h]
0x1800460a5  mov     cs:?NatConfigurationChangedWaitHandle@@3PEAXEA, 0; void * NatConfigurationChangedWaitHandle
0x1800460b0  mov     rcx, cs:NatConfigurationChangedEvent; hObject
0x1800460b7  test    rcx, rcx
0x1800460ba  jz      short loc_1800460D3
0x1800460bc  call    cs:__imp_CloseHandle
0x1800460c3  nop     dword ptr [rax+rax+00h]
0x1800460c8  mov     cs:NatConfigurationChangedEvent, 0
0x1800460d3  mov     rcx, cs:?NatConfigurationChangedRundownEvent@@3PEAXEA; hObject
0x1800460da  test    rcx, rcx
0x1800460dd  jz      short loc_1800460F6
0x1800460df  call    cs:__imp_CloseHandle
0x1800460e6  nop     dword ptr [rax+rax+00h]
0x1800460eb  mov     cs:?NatConfigurationChangedRundownEvent@@3PEAXEA, 0; void * NatConfigurationChangedRundownEvent
0x1800460f6  mov     rcx, cs:?NatConnectionNotifyWaitHandle@@3PEAXEA; hWaitHandle
0x1800460fd  test    rcx, rcx
0x180046100  jz      short loc_18004611C
0x180046102  mov     rdx, rdi; hCompletionEvent
0x180046105  call    cs:__imp_RtlDeregisterWaitEx
0x18004610c  nop     dword ptr [rax+rax+00h]
0x180046111  mov     cs:?NatConnectionNotifyWaitHandle@@3PEAXEA, 0; void * NatConnectionNotifyWaitHandle
0x18004611c  mov     rcx, cs:NatConnectionNotifyEvent; hObject
0x180046123  test    rcx, rcx
0x180046126  jz      short loc_18004613F
0x180046128  call    cs:__imp_CloseHandle
0x18004612f  nop     dword ptr [rax+rax+00h]
0x180046134  mov     cs:NatConnectionNotifyEvent, 0
0x18004613f  mov     rcx, cs:?NatConnectionNotifyRundownEvent@@3PEAXEA; hObject
0x180046146  test    rcx, rcx
0x180046149  jz      short loc_180046162
0x18004614b  call    cs:__imp_CloseHandle
0x180046152  nop     dword ptr [rax+rax+00h]
0x180046157  mov     cs:?NatConnectionNotifyRundownEvent@@3PEAXEA, 0; void * NatConnectionNotifyRundownEvent
0x180046162  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180046169  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18004616e  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180046175  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18004617a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046181  cmp     rcx, r14
0x180046184  jz      loc_180045E64
0x18004618a  test    [rcx+1Ch], ebp
0x18004618d  jz      loc_180045E64
0x180046193  cmp     byte ptr [rcx+19h], 6
0x180046197  jb      loc_180045E64
0x18004619d  mov     edx, 0CBh
0x1800461a2  jmp     loc_180045E55
0x1800461a7  mov     rcx, r13; lpCriticalSection
0x1800461aa  call    cs:__imp_LeaveCriticalSection
0x1800461b1  nop     dword ptr [rax+rax+00h]
0x1800461b6  call    ?NatProcessConfigurationChanged@@YAXXZ; NatProcessConfigurationChanged(void)
0x1800461bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800461c2  cmp     rcx, r14
0x1800461c5  jz      short loc_1800461E6
0x1800461c7  test    [rcx+1Ch], ebp
0x1800461ca  jz      short loc_1800461E6
0x1800461cc  cmp     byte ptr [rcx+19h], 6
0x1800461d0  jb      short loc_1800461E6
0x1800461d2  mov     edx, 0CAh
0x1800461d7  mov     rcx, [rcx+10h]
0x1800461db  xor     r9d, r9d
0x1800461de  mov     r8, r15
0x1800461e1  call    WPP_SF_d
0x1800461e6  xor     eax, eax
0x1800461e8  add     rsp, 38h
0x1800461ec  pop     r15
0x1800461ee  pop     r14
0x1800461f0  pop     r13
0x1800461f2  pop     rdi
0x1800461f3  pop     rbp
0x1800461f4  pop     rbx
0x1800461f5  retn
```
