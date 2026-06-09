# NatStartConnectionManagement

- ea: `0x180042370`
- end: `0x1800427ca`
- name: `NatStartConnectionManagement`
- size: `1114`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006e294`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x18001ec08`
- `0x180042370`
- `0x18004c214`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800423c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800423c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800423d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004244a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004247d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004267e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042784`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800423d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004244a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004247d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004267e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042784`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800424c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800424f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042576`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800425d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800424c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800424f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042576`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800425d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800425e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800425e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004270e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004272b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800426d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004270e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004272b`
- `ntdll!RtlRegisterWait` at `0x180042529`
- `ntdll!RtlRegisterWait` at `0x180042632`
- `ntdll!RtlRegisterWait` at `0x180042529`
- `ntdll!RtlRegisterWait` at `0x180042632`
- `ntdll!RtlNtStatusToDosError` at `0x180042537`
- `ntdll!RtlNtStatusToDosError` at `0x180042644`
- `ntdll!RtlNtStatusToDosError` at `0x180042537`
- `ntdll!RtlNtStatusToDosError` at `0x180042644`
- `ntdll!RtlDeregisterWaitEx` at `0x180042697`
- `ntdll!RtlDeregisterWaitEx` at `0x1800426f1`
- `ntdll!RtlDeregisterWaitEx` at `0x180042697`
- `ntdll!RtlDeregisterWaitEx` at `0x1800426f1`
- `WS2_32!__imp_htonl` at `0x18004240e`
- `WS2_32!__imp_htonl` at `0x18004240e`

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
    qword_1800A8950 = (__int64)&NatConnectionList;
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
0x180042370  push    rbx
0x180042372  push    rbp
0x180042373  push    rdi
0x180042374  push    r13
0x180042376  push    r14
0x180042378  push    r15
0x18004237a  sub     rsp, 38h
0x18004237e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042385  lea     r14, WPP_GLOBAL_Control
0x18004238c  lea     r15, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x180042393  mov     ebp, 200h
0x180042398  cmp     rcx, r14
0x18004239b  jz      short loc_1800423B9
0x18004239d  test    [rcx+1Ch], ebp
0x1800423a0  jz      short loc_1800423B9
0x1800423a2  cmp     byte ptr [rcx+19h], 6
0x1800423a6  jb      short loc_1800423B9
0x1800423a8  mov     rcx, [rcx+10h]
0x1800423ac  mov     edx, 0C2h
0x1800423b1  mov     r8, r15
0x1800423b4  call    WPP_SF_
0x1800423b9  lea     r13, NatInterfaceLock
0x1800423c0  mov     rcx, r13; lpCriticalSection
0x1800423c3  call    cs:__imp_EnterCriticalSection
0x1800423c9  cmp     cs:NatConnectionNotifyEvent, 0
0x1800423d1  jz      short loc_180042409
0x1800423d3  mov     rcx, r13; lpCriticalSection
0x1800423d6  call    cs:__imp_LeaveCriticalSection
0x1800423dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423e3  cmp     rcx, r14
0x1800423e6  jz      loc_1800427BA
0x1800423ec  test    [rcx+1Ch], ebp
0x1800423ef  jz      loc_1800427BA
0x1800423f5  cmp     byte ptr [rcx+19h], 6
0x1800423f9  jb      loc_1800427BA
0x1800423ff  mov     edx, 0C3h
0x180042404  jmp     loc_1800427AB
0x180042409  mov     ecx, 7F000001h; hostlong
0x18004240e  call    cs:__imp_htonl
0x180042414  mov     cs:?INADDR_LOOPBACK_NO@@3KA, eax; ulong INADDR_LOOPBACK_NO
0x18004241a  lea     rdi, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; _COMPONENT_REFERENCE NatComponentReference
0x180042421  lea     rax, NatConnectionList
0x180042428  mov     rcx, rdi; lpCriticalSection
0x18004242b  mov     cs:qword_1800A8950, rax
0x180042432  mov     cs:NatConnectionList, rax
0x180042439  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18004243e  mov     ebx, 3EBh
0x180042443  test    al, al
0x180042445  jnz     short loc_18004246E
0x180042447  mov     rcx, r13; lpCriticalSection
0x18004244a  call    cs:__imp_LeaveCriticalSection
0x180042450  mov     rcx, cs:WPP_GLOBAL_Control
0x180042457  cmp     rcx, r14
0x18004245a  jz      short loc_1800424B6
0x18004245c  test    [rcx+1Ch], ebp
0x18004245f  jz      short loc_1800424B6
0x180042461  cmp     byte ptr [rcx+19h], 6
0x180042465  jb      short loc_1800424B6
0x180042467  mov     edx, 0C4h
0x18004246c  jmp     short loc_1800424A7
0x18004246e  mov     rcx, rdi; lpCriticalSection
0x180042471  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x180042476  test    al, al
0x180042478  jnz     short loc_1800424BD
0x18004247a  mov     rcx, r13; lpCriticalSection
0x18004247d  call    cs:__imp_LeaveCriticalSection
0x180042483  mov     rcx, rdi; struct _COMPONENT_REFERENCE *
0x180042486  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18004248b  mov     rcx, cs:WPP_GLOBAL_Control
0x180042492  cmp     rcx, r14
0x180042495  jz      short loc_1800424B6
0x180042497  test    [rcx+1Ch], ebp
0x18004249a  jz      short loc_1800424B6
0x18004249c  cmp     byte ptr [rcx+19h], 6
0x1800424a0  jb      short loc_1800424B6
0x1800424a2  mov     edx, 0C5h
0x1800424a7  mov     rcx, [rcx+10h]
0x1800424ab  mov     r9d, ebx
0x1800424ae  mov     r8, r15
0x1800424b1  call    WPP_SF_d
0x1800424b6  mov     eax, ebx
0x1800424b8  jmp     loc_1800427BC
0x1800424bd  xor     r9d, r9d; lpName
0x1800424c0  xor     r8d, r8d; bInitialState
0x1800424c3  xor     edx, edx; bManualReset
0x1800424c5  xor     ecx, ecx; lpEventAttributes
0x1800424c7  call    cs:__imp_CreateEventW
0x1800424cd  mov     cs:NatConnectionNotifyEvent, rax
0x1800424d4  test    rax, rax
0x1800424d7  jnz     short loc_1800424E6
0x1800424d9  call    cs:__imp_GetLastError
0x1800424df  mov     ebx, eax
0x1800424e1  jmp     loc_18004267B
0x1800424e6  xor     r9d, r9d; lpName
0x1800424e9  xor     r8d, r8d; bInitialState
0x1800424ec  xor     edx, edx; bManualReset
0x1800424ee  xor     ecx, ecx; lpEventAttributes
0x1800424f0  call    cs:__imp_CreateEventW
0x1800424f6  mov     cs:?NatConnectionNotifyRundownEvent@@3PEAXEA, rax; void * NatConnectionNotifyRundownEvent
0x1800424fd  test    rax, rax
0x180042500  jz      short loc_1800424D9
0x180042502  mov     rdx, cs:NatConnectionNotifyEvent; hObject
0x180042509  lea     r8, ?NatConnectionNotifyCallbackRoutine@@YAXPEAXE@Z; Callback
0x180042510  or      ebx, 0FFFFFFFFh
0x180042513  mov     [rsp+68h+ulFlags], 0; ulFlags
0x18004251b  xor     r9d, r9d; pvContext
0x18004251e  mov     [rsp+68h+ulMilliseconds], ebx; ulMilliseconds
0x180042522  lea     rcx, ?NatConnectionNotifyWaitHandle@@3PEAXEA; phNewWaitObject
0x180042529  call    cs:__imp_RtlRegisterWait
0x18004252f  mov     edi, eax
0x180042531  test    eax, eax
0x180042533  jns     short loc_18004256C
0x180042535  mov     ecx, eax; Status
0x180042537  call    cs:__imp_RtlNtStatusToDosError
0x18004253d  mov     ebx, eax
0x18004253f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042546  cmp     rcx, r14
0x180042549  jz      loc_18004267B
0x18004254f  test    [rcx+1Ch], ebp
0x180042552  jz      loc_18004267B
0x180042558  cmp     byte ptr [rcx+19h], 2
0x18004255c  jb      loc_18004267B
0x180042562  mov     edx, 0C6h
0x180042567  jmp     loc_180042668
0x18004256c  xor     r9d, r9d; lpName
0x18004256f  xor     r8d, r8d; bInitialState
0x180042572  xor     edx, edx; bManualReset
0x180042574  xor     ecx, ecx; lpEventAttributes
0x180042576  call    cs:__imp_CreateEventW
0x18004257c  mov     cs:NatConfigurationChangedEvent, rax
0x180042583  test    rax, rax
0x180042586  jnz     short loc_1800425CC
0x180042588  call    cs:__imp_GetLastError
0x18004258e  mov     ebx, eax
0x180042590  mov     rcx, cs:WPP_GLOBAL_Control
0x180042597  cmp     rcx, r14
0x18004259a  jz      loc_18004267B
0x1800425a0  test    [rcx+1Ch], ebp
0x1800425a3  jz      loc_18004267B
0x1800425a9  cmp     byte ptr [rcx+19h], 2
0x1800425ad  jb      loc_18004267B
0x1800425b3  mov     edx, 0C7h
0x1800425b8  mov     rcx, [rcx+10h]
0x1800425bc  mov     r9d, eax
0x1800425bf  mov     r8, r15
0x1800425c2  call    WPP_SF_d
0x1800425c7  jmp     loc_18004267B
0x1800425cc  xor     r9d, r9d; lpName
0x1800425cf  xor     r8d, r8d; bInitialState
0x1800425d2  xor     edx, edx; bManualReset
0x1800425d4  xor     ecx, ecx; lpEventAttributes
0x1800425d6  call    cs:__imp_CreateEventW
0x1800425dc  mov     cs:?NatConfigurationChangedRundownEvent@@3PEAXEA, rax; void * NatConfigurationChangedRundownEvent
0x1800425e3  test    rax, rax
0x1800425e6  jnz     short loc_18004260E
0x1800425e8  call    cs:__imp_GetLastError
0x1800425ee  mov     ebx, eax
0x1800425f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800425f7  cmp     rcx, r14
0x1800425fa  jz      short loc_18004267B
0x1800425fc  test    [rcx+1Ch], ebp
0x1800425ff  jz      short loc_18004267B
0x180042601  cmp     byte ptr [rcx+19h], 2
0x180042605  jb      short loc_18004267B
0x180042607  mov     edx, 0C8h
0x18004260c  jmp     short loc_1800425B8
0x18004260e  mov     rdx, cs:NatConfigurationChangedEvent; hObject
0x180042615  lea     r8, ?NatConfigurationChangedCallbackRoutine@@YAXPEAXE@Z; Callback
0x18004261c  mov     [rsp+68h+ulFlags], 0; ulFlags
0x180042624  lea     rcx, ?NatConfigurationChangedWaitHandle@@3PEAXEA; phNewWaitObject
0x18004262b  xor     r9d, r9d; pvContext
0x18004262e  mov     [rsp+68h+ulMilliseconds], ebx; ulMilliseconds
0x180042632  call    cs:__imp_RtlRegisterWait
0x180042638  mov     edi, eax
0x18004263a  test    eax, eax
0x18004263c  jns     loc_180042781
0x180042642  mov     ecx, eax; Status
0x180042644  call    cs:__imp_RtlNtStatusToDosError
0x18004264a  mov     ebx, eax
0x18004264c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042653  cmp     rcx, r14
0x180042656  jz      short loc_18004267B
0x180042658  test    [rcx+1Ch], ebp
0x18004265b  jz      short loc_18004267B
0x18004265d  cmp     byte ptr [rcx+19h], 2
0x180042661  jb      short loc_18004267B
0x180042663  mov     edx, 0C9h
0x180042668  mov     rcx, [rcx+10h]
0x18004266c  mov     r9d, edi
0x18004266f  mov     r8, r15
0x180042672  mov     [rsp+68h+ulMilliseconds], eax
0x180042676  call    WPP_SF_Dd
0x18004267b  mov     rcx, r13; lpCriticalSection
0x18004267e  call    cs:__imp_LeaveCriticalSection
0x180042684  mov     rcx, cs:?NatConfigurationChangedWaitHandle@@3PEAXEA; hWaitHandle
0x18004268b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004268f  test    rcx, rcx
0x180042692  jz      short loc_1800426A8
0x180042694  mov     rdx, rdi; hCompletionEvent
0x180042697  call    cs:__imp_RtlDeregisterWaitEx
0x18004269d  mov     cs:?NatConfigurationChangedWaitHandle@@3PEAXEA, 0; void * NatConfigurationChangedWaitHandle
0x1800426a8  mov     rcx, cs:NatConfigurationChangedEvent; hObject
0x1800426af  test    rcx, rcx
0x1800426b2  jz      short loc_1800426C5
0x1800426b4  call    cs:__imp_CloseHandle
0x1800426ba  mov     cs:NatConfigurationChangedEvent, 0
0x1800426c5  mov     rcx, cs:?NatConfigurationChangedRundownEvent@@3PEAXEA; hObject
0x1800426cc  test    rcx, rcx
0x1800426cf  jz      short loc_1800426E2
0x1800426d1  call    cs:__imp_CloseHandle
0x1800426d7  mov     cs:?NatConfigurationChangedRundownEvent@@3PEAXEA, 0; void * NatConfigurationChangedRundownEvent
0x1800426e2  mov     rcx, cs:?NatConnectionNotifyWaitHandle@@3PEAXEA; hWaitHandle
0x1800426e9  test    rcx, rcx
0x1800426ec  jz      short loc_180042702
0x1800426ee  mov     rdx, rdi; hCompletionEvent
0x1800426f1  call    cs:__imp_RtlDeregisterWaitEx
0x1800426f7  mov     cs:?NatConnectionNotifyWaitHandle@@3PEAXEA, 0; void * NatConnectionNotifyWaitHandle
0x180042702  mov     rcx, cs:NatConnectionNotifyEvent; hObject
0x180042709  test    rcx, rcx
0x18004270c  jz      short loc_18004271F
0x18004270e  call    cs:__imp_CloseHandle
0x180042714  mov     cs:NatConnectionNotifyEvent, 0
0x18004271f  mov     rcx, cs:?NatConnectionNotifyRundownEvent@@3PEAXEA; hObject
0x180042726  test    rcx, rcx
0x180042729  jz      short loc_18004273C
0x18004272b  call    cs:__imp_CloseHandle
0x180042731  mov     cs:?NatConnectionNotifyRundownEvent@@3PEAXEA, 0; void * NatConnectionNotifyRundownEvent
0x18004273c  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180042743  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180042748  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18004274f  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180042754  mov     rcx, cs:WPP_GLOBAL_Control
0x18004275b  cmp     rcx, r14
0x18004275e  jz      loc_1800424B6
0x180042764  test    [rcx+1Ch], ebp
0x180042767  jz      loc_1800424B6
0x18004276d  cmp     byte ptr [rcx+19h], 6
0x180042771  jb      loc_1800424B6
0x180042777  mov     edx, 0CBh
0x18004277c  jmp     loc_1800424A7
0x180042781  mov     rcx, r13; lpCriticalSection
0x180042784  call    cs:__imp_LeaveCriticalSection
0x18004278a  call    ?NatProcessConfigurationChanged@@YAXXZ; NatProcessConfigurationChanged(void)
0x18004278f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042796  cmp     rcx, r14
0x180042799  jz      short loc_1800427BA
0x18004279b  test    [rcx+1Ch], ebp
0x18004279e  jz      short loc_1800427BA
0x1800427a0  cmp     byte ptr [rcx+19h], 6
0x1800427a4  jb      short loc_1800427BA
0x1800427a6  mov     edx, 0CAh
0x1800427ab  mov     rcx, [rcx+10h]
0x1800427af  xor     r9d, r9d
0x1800427b2  mov     r8, r15
0x1800427b5  call    WPP_SF_d
0x1800427ba  xor     eax, eax
0x1800427bc  add     rsp, 38h
0x1800427c0  pop     r15
0x1800427c2  pop     r14
0x1800427c4  pop     r13
0x1800427c6  pop     rdi
0x1800427c7  pop     rbp
0x1800427c8  pop     rbx
0x1800427c9  retn
```
