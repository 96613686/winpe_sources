# NatServiceHandler(ulong)

- ea: `0x18001ff60`
- end: `0x1800202da`
- name: `?NatServiceHandler@@YAXK@Z`
- size: `890`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18001ff60`
- `0x1800202e0`
- `0x180021cf0`
- `0x1800417cc`
- `0x1800732c0`
- `0x180074694`
- `0x18007523c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ff9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ff9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020011`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020011`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200ec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800201fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800202ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800202c9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800201fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800202ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800202c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002015f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002015f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001ffdd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001ffdd`

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
  switch ( dwControl )
  {
    case 4u:
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
LABEL_22:
        LeaveCriticalSection(&gNatMain);
        goto LABEL_12;
      }
      goto LABEL_11;
    case 1u:
      NhDhcpv6PrefixCleanupNeeded = 1;
      goto LABEL_43;
    case 5u:
LABEL_43:
      if ( (_BYTE)word_1800AE400 )
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
        HIBYTE(word_1800AE400) = 1;
      }
      NatServiceChangeState(3u, 0);
      goto LABEL_11;
    case 0x87u:
      NatUpdatePortMappingServiceControlQueuePushBack(0x87u);
      break;
    default:
      NatServiceControlQueuePushBack(dwControl);
      break;
  }
  if ( (_BYTE)word_1800AE400 )
  {
    SetEvent(hObject);
    goto LABEL_22;
  }
LABEL_11:
  LeaveCriticalSection(&gNatMain);
  if ( v2 )
  {
    if ( *(&WaitHandle + 1) )
      SetEvent(*(&WaitHandle + 1));
    if ( *(&xmmword_1800AE3F0 + 1) )
      SetEvent(*(&xmmword_1800AE3F0 + 1));
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
0x18001ff60  mov     [rsp+arg_0], rbx
0x18001ff65  mov     [rsp+arg_8], rsi
0x18001ff6a  push    rdi
0x18001ff6b  sub     rsp, 30h
0x18001ff6f  mov     ebx, ecx
0x18001ff71  mov     r10, cs:WPP_GLOBAL_Control
0x18001ff78  lea     rsi, WPP_GLOBAL_Control
0x18001ff7f  cmp     r10, rsi
0x18001ff82  jz      short loc_18001FF92
0x18001ff84  test    dword ptr [r10+1Ch], 200h
0x18001ff8c  jnz     loc_1800200FD
0x18001ff92  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x18001ff99  xor     edi, edi
0x18001ff9b  call    cs:__imp_EnterCriticalSection
0x18001ffa2  nop     dword ptr [rax+rax+00h]
0x18001ffa7  cmp     ebx, 4
0x18001ffaa  jnz     loc_1800201C6
0x18001ffb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffb7  cmp     rcx, rsi
0x18001ffba  jnz     loc_18002008B
0x18001ffc0  mov     rax, cs:hServiceStatus
0x18001ffc7  xor     ebx, ebx
0x18001ffc9  test    rax, rax
0x18001ffcc  jz      short loc_18001FFF8
0x18001ffce  cmp     rcx, rsi
0x18001ffd1  jnz     short loc_180020046
0x18001ffd3  lea     rdx, ServiceStatus; lpServiceStatus
0x18001ffda  mov     rcx, rax; hServiceStatus
0x18001ffdd  call    cs:__imp_SetServiceStatus
0x18001ffe4  nop     dword ptr [rax+rax+00h]
0x18001ffe9  test    eax, eax
0x18001ffeb  jz      loc_18002015F
0x18001fff1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fff8  cmp     rcx, rsi
0x18001fffb  jz      short loc_18002000A
0x18001fffd  test    dword ptr [rcx+1Ch], 200h
0x180020004  jnz     loc_1800200C3
0x18002000a  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x180020011  call    cs:__imp_LeaveCriticalSection
0x180020018  nop     dword ptr [rax+rax+00h]
0x18002001d  test    edi, edi
0x18002001f  jnz     loc_1800202A1
0x180020025  mov     rcx, cs:WPP_GLOBAL_Control
0x18002002c  cmp     rcx, rsi
0x18002002f  jnz     loc_18002012E
0x180020035  mov     rbx, [rsp+38h+arg_0]
0x18002003a  mov     rsi, [rsp+38h+arg_8]
0x18002003f  add     rsp, 30h
0x180020043  pop     rdi
0x180020044  retn
0x180020046  test    dword ptr [rcx+1Ch], 200h
0x18002004d  jz      short loc_18001FFD3
0x18002004f  cmp     byte ptr [rcx+19h], 4
0x180020053  jb      loc_18001FFD3
0x180020059  mov     eax, cs:ServiceStatus.dwControlsAccepted
0x18002005f  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180020066  mov     r9d, cs:ServiceStatus.dwCurrentState
0x18002006d  mov     edx, 111h
0x180020072  mov     rcx, [rcx+10h]
0x180020076  mov     [rsp+38h+var_18], eax
0x18002007a  call    WPP_SF_Dd
0x18002007f  mov     rax, cs:hServiceStatus
0x180020086  jmp     loc_18001FFD3
0x18002008b  test    dword ptr [rcx+1Ch], 200h
0x180020092  jz      loc_18001FFC0
0x180020098  cmp     byte ptr [rcx+19h], 6
0x18002009c  jb      loc_18001FFC0
0x1800200a2  mov     rcx, [rcx+10h]
0x1800200a6  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800200ad  mov     edx, 110h
0x1800200b2  call    WPP_SF_
0x1800200b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200be  jmp     loc_18001FFC0
0x1800200c3  cmp     byte ptr [rcx+19h], 6
0x1800200c7  jb      loc_18002000A
0x1800200cd  mov     rcx, [rcx+10h]
0x1800200d1  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800200d8  mov     edx, 113h
0x1800200dd  mov     r9d, ebx
0x1800200e0  call    WPP_SF_d
0x1800200e5  lea     rcx, ?gNatMain@@3UNAT_MAIN_COMPONENT_@@A; lpCriticalSection
0x1800200ec  call    cs:__imp_LeaveCriticalSection
0x1800200f3  nop     dword ptr [rax+rax+00h]
0x1800200f8  jmp     loc_180020025
0x1800200fd  cmp     byte ptr [r10+19h], 6
0x180020102  jb      loc_18001FF92
0x180020108  call    ?GetServiceControlCodeDescription@@YAPEBDK@Z; GetServiceControlCodeDescription(ulong)
0x18002010d  mov     rcx, [r10+10h]
0x180020111  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180020118  mov     r9, rax
0x18002011b  mov     [rsp+38h+var_18], ebx
0x18002011f  mov     edx, 0F0h
0x180020124  call    WPP_SF_sD
0x180020129  jmp     loc_18001FF92
0x18002012e  test    dword ptr [rcx+1Ch], 200h
0x180020135  jz      loc_180020035
0x18002013b  cmp     byte ptr [rcx+19h], 6
0x18002013f  jb      loc_180020035
0x180020145  mov     rcx, [rcx+10h]
0x180020149  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180020150  mov     edx, 0F3h
0x180020155  call    WPP_SF_
0x18002015a  jmp     loc_180020035
0x18002015f  call    cs:__imp_GetLastError
0x180020166  nop     dword ptr [rax+rax+00h]
0x18002016b  mov     ebx, eax
0x18002016d  test    eax, eax
0x18002016f  jle     short loc_18002017A
0x180020171  movzx   ebx, ax
0x180020174  or      ebx, 80070000h
0x18002017a  test    ebx, ebx
0x18002017c  jns     loc_18001FFF1
0x180020182  mov     rcx, cs:WPP_GLOBAL_Control
0x180020189  cmp     rcx, rsi
0x18002018c  jz      loc_18002000A
0x180020192  test    dword ptr [rcx+1Ch], 200h
0x180020199  jz      loc_18001FFF8
0x18002019f  cmp     byte ptr [rcx+19h], 2
0x1800201a3  jb      loc_18001FFF8
0x1800201a9  mov     rcx, [rcx+10h]
0x1800201ad  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800201b4  mov     edx, 112h
0x1800201b9  mov     r9d, ebx
0x1800201bc  call    WPP_SF_d
0x1800201c1  jmp     loc_18001FFF1
0x1800201c6  mov     eax, ebx
0x1800201c8  sub     eax, 1
0x1800201cb  jz      short loc_18002020F
0x1800201cd  cmp     eax, 4
0x1800201d0  jz      short loc_180020219
0x1800201d2  cmp     ebx, 87h
0x1800201d8  jnz     short loc_1800201E3
0x1800201da  mov     ecx, ebx; unsigned int
0x1800201dc  call    ?NatUpdatePortMappingServiceControlQueuePushBack@@YAJK@Z; NatUpdatePortMappingServiceControlQueuePushBack(ulong)
0x1800201e1  jmp     short loc_1800201EA
0x1800201e3  mov     ecx, ebx; unsigned int
0x1800201e5  call    ?NatServiceControlQueuePushBack@@YAJK@Z; NatServiceControlQueuePushBack(ulong)
0x1800201ea  cmp     byte ptr cs:word_1800AE400, dil
0x1800201f1  jz      loc_18002000A
0x1800201f7  mov     rcx, cs:hObject; hEvent
0x1800201fe  call    cs:__imp_SetEvent
0x180020205  nop     dword ptr [rax+rax+00h]
0x18002020a  jmp     loc_1800200E5
0x18002020f  mov     cs:?NhDhcpv6PrefixCleanupNeeded@@3HA, 1; int NhDhcpv6PrefixCleanupNeeded
0x180020219  cmp     byte ptr cs:word_1800AE400, dil
0x180020220  jz      short loc_180020259
0x180020222  mov     rcx, cs:WPP_GLOBAL_Control
0x180020229  cmp     rcx, rsi
0x18002022c  jz      short loc_180020252
0x18002022e  test    dword ptr [rcx+1Ch], 200h
0x180020235  jz      short loc_180020252
0x180020237  cmp     byte ptr [rcx+19h], 4
0x18002023b  jb      short loc_180020252
0x18002023d  mov     rcx, [rcx+10h]
0x180020241  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180020248  mov     edx, 0F1h
0x18002024d  call    WPP_SF_
0x180020252  mov     edi, 1
0x180020257  jmp     short loc_180020290
0x180020259  mov     rcx, cs:WPP_GLOBAL_Control
0x180020260  cmp     rcx, rsi
0x180020263  jz      short loc_180020289
0x180020265  test    dword ptr [rcx+1Ch], 200h
0x18002026c  jz      short loc_180020289
0x18002026e  cmp     byte ptr [rcx+19h], 4
0x180020272  jb      short loc_180020289
0x180020274  mov     rcx, [rcx+10h]
0x180020278  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18002027f  mov     edx, 0F2h
0x180020284  call    WPP_SF_
0x180020289  mov     byte ptr cs:word_1800AE400+1, 1
0x180020290  xor     edx, edx; bool
0x180020292  mov     ecx, 3; unsigned int
0x180020297  call    ?NatServiceChangeState@@YAJK_N@Z; NatServiceChangeState(ulong,bool)
0x18002029c  jmp     loc_18002000A
0x1800202a1  mov     rcx, qword ptr cs:WaitHandle+8; hEvent
0x1800202a8  test    rcx, rcx
0x1800202ab  jz      short loc_1800202B9
0x1800202ad  call    cs:__imp_SetEvent
0x1800202b4  nop     dword ptr [rax+rax+00h]
0x1800202b9  mov     rcx, qword ptr cs:xmmword_1800AE3F0+8; hEvent
0x1800202c0  test    rcx, rcx
0x1800202c3  jz      loc_180020025
0x1800202c9  call    cs:__imp_SetEvent
0x1800202d0  nop     dword ptr [rax+rax+00h]
0x1800202d5  jmp     loc_180020025
```
