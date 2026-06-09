# NatServiceHandler(ulong)

- ea: `0x18001e8b0`
- end: `0x18001ec02`
- name: `?NatServiceHandler@@YAXK@Z`
- size: `850`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18001e8b0`
- `0x18001ec08`
- `0x18002ee44`
- `0x18003e6ec`
- `0x18006db38`
- `0x18006ee48`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e8eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e8eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e955`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ea25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eb38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e955`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ea25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eb38`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001eb2b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001ebe1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001ebf7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001eb2b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001ebe1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001ebf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ea92`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001e927`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001e927`

## pseudocode

```c
void __fastcall NatServiceHandler(DWORD dwControl)
{
  int v2; // edi
  PVOID *v3; // rcx
  SERVICE_STATUS_HANDLE v4; // rax
  unsigned int v5; // ebx
  unsigned int ServiceControlCodeDescription; // eax
  __int64 v7; // r10
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    ServiceControlCodeDescription = (unsigned int)GetServiceControlCodeDescription(dwControl);
    WPP_SF_sD(
      *(_QWORD *)(v7 + 16),
      240,
      (unsigned int)&WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      ServiceControlCodeDescription,
      dwControl);
  }
  v2 = 0;
  EnterCriticalSection(&gNatMain);
  if ( dwControl == 4 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 272, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = hServiceStatus;
    v5 = 0;
    if ( hServiceStatus )
    {
      if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x200) != 0 && *((_BYTE *)v3 + 25) >= 4u )
      {
        WPP_SF_Dd(
          v3[2],
          273,
          &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          ServiceStatus.dwCurrentState,
          ServiceStatus.dwControlsAccepted);
        v4 = hServiceStatus;
      }
      if ( !SetServiceStatus(v4, &ServiceStatus) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( (v5 & 0x80000000) != 0 )
        {
          v3 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_11;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_9;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 274, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v5);
        }
      }
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_9:
    if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x200) != 0 && *((_BYTE *)v3 + 25) >= 6u )
    {
      WPP_SF_d(v3[2], 275, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v5);
      LeaveCriticalSection(&gNatMain);
      goto LABEL_12;
    }
    goto LABEL_11;
  }
  if ( dwControl == 1 )
  {
    NhDhcpv6PrefixCleanupNeeded = 1;
  }
  else if ( dwControl != 5 )
  {
    if ( dwControl == 135 )
      NatUpdatePortMappingServiceControlQueuePushBack(0x87u);
    else
      NatServiceControlQueuePushBack(dwControl);
    if ( (_BYTE)word_1800A7340 )
    {
      SetEvent(hObject);
      LeaveCriticalSection(&gNatMain);
      goto LABEL_12;
    }
    goto LABEL_11;
  }
  if ( (_BYTE)word_1800A7340 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 241, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    }
    v2 = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    }
    HIBYTE(word_1800A7340) = 1;
  }
  NatServiceChangeState(3u, 0);
LABEL_11:
  LeaveCriticalSection(&gNatMain);
  if ( v2 )
  {
    if ( *(&WaitHandle + 1) )
      SetEvent(*(&WaitHandle + 1));
    if ( *(&xmmword_1800A7330 + 1) )
      SetEvent(*(&xmmword_1800A7330 + 1));
  }
LABEL_12:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 243, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
}

```

## disassembly

```asm
0x18001e8b0  mov     [rsp+arg_0], rbx
0x18001e8b5  mov     [rsp+arg_8], rsi
0x18001e8ba  push    rdi
0x18001e8bb  sub     rsp, 30h
0x18001e8bf  mov     ebx, ecx
0x18001e8c1  mov     r10, cs:WPP_GLOBAL_Control
0x18001e8c8  lea     rsi, WPP_GLOBAL_Control
0x18001e8cf  cmp     r10, rsi
0x18001e8d2  jz      short loc_18001E8E2
0x18001e8d4  test    dword ptr [r10+1Ch], 200h
0x18001e8dc  jnz     loc_18001EA30
0x18001e8e2  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18001e8e9  xor     edi, edi
0x18001e8eb  call    cs:__imp_EnterCriticalSection
0x18001e8f1  cmp     ebx, 4
0x18001e8f4  jnz     loc_18001EAF3
0x18001e8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e901  cmp     rcx, rsi
0x18001e904  jnz     loc_18001E9C4
0x18001e90a  mov     rax, cs:hServiceStatus
0x18001e911  xor     ebx, ebx
0x18001e913  test    rax, rax
0x18001e916  jz      short loc_18001E93C
0x18001e918  cmp     rcx, rsi
0x18001e91b  jnz     short loc_18001E983
0x18001e91d  lea     rdx, ServiceStatus; lpServiceStatus
0x18001e924  mov     rcx, rax; hServiceStatus
0x18001e927  call    cs:__imp_SetServiceStatus
0x18001e92d  test    eax, eax
0x18001e92f  jz      loc_18001EA92
0x18001e935  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e93c  cmp     rcx, rsi
0x18001e93f  jz      short loc_18001E94E
0x18001e941  test    dword ptr [rcx+1Ch], 200h
0x18001e948  jnz     loc_18001E9FC
0x18001e94e  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18001e955  call    cs:__imp_LeaveCriticalSection
0x18001e95b  test    edi, edi
0x18001e95d  jnz     loc_18001EBD5
0x18001e963  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e96a  cmp     rcx, rsi
0x18001e96d  jnz     loc_18001EA61
0x18001e973  mov     rbx, [rsp+38h+arg_0]
0x18001e978  mov     rsi, [rsp+38h+arg_8]
0x18001e97d  add     rsp, 30h
0x18001e981  pop     rdi
0x18001e982  retn
0x18001e983  test    dword ptr [rcx+1Ch], 200h
0x18001e98a  jz      short loc_18001E91D
0x18001e98c  cmp     byte ptr [rcx+19h], 4
0x18001e990  jb      short loc_18001E91D
0x18001e992  mov     eax, cs:ServiceStatus.dwControlsAccepted
0x18001e998  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18001e99f  mov     r9d, cs:ServiceStatus.dwCurrentState
0x18001e9a6  mov     edx, 111h
0x18001e9ab  mov     rcx, [rcx+10h]
0x18001e9af  mov     [rsp+38h+var_18], eax
0x18001e9b3  call    WPP_SF_Dd
0x18001e9b8  mov     rax, cs:hServiceStatus
0x18001e9bf  jmp     loc_18001E91D
0x18001e9c4  test    dword ptr [rcx+1Ch], 200h
0x18001e9cb  jz      loc_18001E90A
0x18001e9d1  cmp     byte ptr [rcx+19h], 6
0x18001e9d5  jb      loc_18001E90A
0x18001e9db  mov     rcx, [rcx+10h]
0x18001e9df  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18001e9e6  mov     edx, 110h
0x18001e9eb  call    WPP_SF_
0x18001e9f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9f7  jmp     loc_18001E90A
0x18001e9fc  cmp     byte ptr [rcx+19h], 6
0x18001ea00  jb      loc_18001E94E
0x18001ea06  mov     rcx, [rcx+10h]
0x18001ea0a  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18001ea11  mov     edx, 113h
0x18001ea16  mov     r9d, ebx
0x18001ea19  call    WPP_SF_d
0x18001ea1e  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18001ea25  call    cs:__imp_LeaveCriticalSection
0x18001ea2b  jmp     loc_18001E963
0x18001ea30  cmp     byte ptr [r10+19h], 6
0x18001ea35  jb      loc_18001E8E2
0x18001ea3b  call    ?GetServiceControlCodeDescription@@YAPEBDK@Z; GetServiceControlCodeDescription(ulong)
0x18001ea40  mov     rcx, [r10+10h]
0x18001ea44  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18001ea4b  mov     r9, rax
0x18001ea4e  mov     [rsp+38h+var_18], ebx
0x18001ea52  mov     edx, 0F0h
0x18001ea57  call    WPP_SF_sD
0x18001ea5c  jmp     loc_18001E8E2
0x18001ea61  test    dword ptr [rcx+1Ch], 200h
0x18001ea68  jz      loc_18001E973
0x18001ea6e  cmp     byte ptr [rcx+19h], 6
0x18001ea72  jb      loc_18001E973
0x18001ea78  mov     rcx, [rcx+10h]
0x18001ea7c  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18001ea83  mov     edx, 0F3h
0x18001ea88  call    WPP_SF_
0x18001ea8d  jmp     loc_18001E973
0x18001ea92  call    cs:__imp_GetLastError
0x18001ea98  mov     ebx, eax
0x18001ea9a  test    eax, eax
0x18001ea9c  jle     short loc_18001EAA7
0x18001ea9e  movzx   ebx, ax
0x18001eaa1  or      ebx, 80070000h
0x18001eaa7  test    ebx, ebx
0x18001eaa9  jns     loc_18001E935
0x18001eaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eab6  cmp     rcx, rsi
0x18001eab9  jz      loc_18001E94E
0x18001eabf  test    dword ptr [rcx+1Ch], 200h
0x18001eac6  jz      loc_18001E93C
0x18001eacc  cmp     byte ptr [rcx+19h], 2
0x18001ead0  jb      loc_18001E93C
0x18001ead6  mov     rcx, [rcx+10h]
0x18001eada  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18001eae1  mov     edx, 112h
0x18001eae6  mov     r9d, ebx
0x18001eae9  call    WPP_SF_d
0x18001eaee  jmp     loc_18001E935
0x18001eaf3  mov     eax, ebx
0x18001eaf5  sub     eax, 1
0x18001eaf8  jz      short loc_18001EB43
0x18001eafa  cmp     eax, 4
0x18001eafd  jz      short loc_18001EB4D
0x18001eaff  cmp     ebx, 87h
0x18001eb05  jnz     short loc_18001EB10
0x18001eb07  mov     ecx, ebx; unsigned int
0x18001eb09  call    ?NatUpdatePortMappingServiceControlQueuePushBack@@YAJK@Z; NatUpdatePortMappingServiceControlQueuePushBack(ulong)
0x18001eb0e  jmp     short loc_18001EB17
0x18001eb10  mov     ecx, ebx; unsigned int
0x18001eb12  call    ?NatServiceControlQueuePushBack@@YAJK@Z; NatServiceControlQueuePushBack(ulong)
0x18001eb17  cmp     byte ptr cs:word_1800A7340, dil
0x18001eb1e  jz      loc_18001E94E
0x18001eb24  mov     rcx, cs:hObject; hEvent
0x18001eb2b  call    cs:__imp_SetEvent
0x18001eb31  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18001eb38  call    cs:__imp_LeaveCriticalSection
0x18001eb3e  jmp     loc_18001E963
0x18001eb43  mov     cs:?NhDhcpv6PrefixCleanupNeeded@@3HA, 1; int NhDhcpv6PrefixCleanupNeeded
0x18001eb4d  cmp     byte ptr cs:word_1800A7340, dil
0x18001eb54  jz      short loc_18001EB8D
0x18001eb56  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb5d  cmp     rcx, rsi
0x18001eb60  jz      short loc_18001EB86
0x18001eb62  test    dword ptr [rcx+1Ch], 200h
0x18001eb69  jz      short loc_18001EB86
0x18001eb6b  cmp     byte ptr [rcx+19h], 4
0x18001eb6f  jb      short loc_18001EB86
0x18001eb71  mov     rcx, [rcx+10h]
0x18001eb75  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18001eb7c  mov     edx, 0F1h
0x18001eb81  call    WPP_SF_
0x18001eb86  mov     edi, 1
0x18001eb8b  jmp     short loc_18001EBC4
0x18001eb8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb94  cmp     rcx, rsi
0x18001eb97  jz      short loc_18001EBBD
0x18001eb99  test    dword ptr [rcx+1Ch], 200h
0x18001eba0  jz      short loc_18001EBBD
0x18001eba2  cmp     byte ptr [rcx+19h], 4
0x18001eba6  jb      short loc_18001EBBD
0x18001eba8  mov     rcx, [rcx+10h]
0x18001ebac  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18001ebb3  mov     edx, 0F2h
0x18001ebb8  call    WPP_SF_
0x18001ebbd  mov     byte ptr cs:word_1800A7340+1, 1
0x18001ebc4  xor     edx, edx; bool
0x18001ebc6  mov     ecx, 3; unsigned int
0x18001ebcb  call    ?NatServiceChangeState@@YAJK_N@Z; NatServiceChangeState(ulong,bool)
0x18001ebd0  jmp     loc_18001E94E
0x18001ebd5  mov     rcx, qword ptr cs:WaitHandle+8; hEvent
0x18001ebdc  test    rcx, rcx
0x18001ebdf  jz      short loc_18001EBE7
0x18001ebe1  call    cs:__imp_SetEvent
0x18001ebe7  mov     rcx, qword ptr cs:xmmword_1800A7330+8; hEvent
0x18001ebee  test    rcx, rcx
0x18001ebf1  jz      loc_18001E963
0x18001ebf7  call    cs:__imp_SetEvent
0x18001ebfd  jmp     loc_18001E963
```
