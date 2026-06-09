# NatStartSharedConnectionManagement(uchar)

- ea: `0x1800482c0`
- end: `0x180048505`
- name: `?NatStartSharedConnectionManagement@@YAKE@Z`
- size: `581`
- prototype: `unsigned int __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004c214`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c750`
- `0x180013ef8`
- `0x18004215c`
- `0x180042df4`
- `0x1800482c0`
- `0x18004f558`
- `0x180070598`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048398`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800483af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800483fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004845a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800484c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800483af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800483fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004845a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800484c3`
- `ntdll!RtlQueueWorkItem` at `0x1800484b3`
- `ntdll!RtlQueueWorkItem` at `0x1800484b3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180048342`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180048342`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004837f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180048388`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004837f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180048388`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180048376`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180048376`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180048360`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180048360`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasQuerySharedAutoDial` at `0x180048327`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasQuerySharedAutoDial` at `0x180048327`

## pseudocode

```c
__int64 __fastcall NatStartSharedConnectionManagement(char a1, __int64 a2, __int64 a3, __int64 a4)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rbx
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rsi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  unsigned int started; // ebx
  __int64 v13; // rdx
  int v15; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a1;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, a4);
  }
  v15 = 0;
  if ( !(unsigned __int8)IsRasQuerySharedAutoDialPresent() || !(unsigned int)RasQuerySharedAutoDial(&v15) )
  {
    if ( v15 )
    {
      v5 = OpenSCManagerW(0, 0, 0xF003Fu);
      v6 = v5;
      if ( v5 )
      {
        v7 = OpenServiceW(v5, L"RasAuto", 0xF01FFu);
        v8 = v7;
        if ( v7 )
        {
          StartServiceW(v7, 0, 0);
          CloseServiceHandle(v8);
        }
        CloseServiceHandle(v6);
      }
    }
  }
  EnterCriticalSection(&NatInterfaceLock);
  if ( !g_ConnectionManagementAlreadyStarted )
  {
    if ( a1 || AcquireComponentReference(&NatComponentReference) )
    {
      started = NhStartICSProtocols();
      if ( !started )
      {
        g_ConnectionManagementAlreadyStarted = 1;
        if ( !a1 )
          RtlQueueWorkItem(NatRoutingFailureWorkerRoutine, 0, 1u);
        NatIndicateToDriverICSPresence(1u);
        LeaveCriticalSection(&NatInterfaceLock);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
        {
          return 0;
        }
        v10 = 178;
        goto LABEL_38;
      }
      if ( g_ConnectionManagementAlreadyStarted )
        g_ConnectionManagementAlreadyStarted = 0;
      LeaveCriticalSection(&NatInterfaceLock);
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&NatComponentReference);
      ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&NatComponentReference);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return started;
      }
      v13 = 179;
    }
    else
    {
      LeaveCriticalSection(&NatInterfaceLock);
      v11 = WPP_GLOBAL_Control;
      started = 1003;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return started;
      }
      v13 = 177;
    }
    WPP_SF_d(v11[2], v13, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, started);
    return started;
  }
  SignalBeaconSvr();
  LeaveCriticalSection(&NatInterfaceLock);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
  {
    return 0;
  }
  v10 = 176;
LABEL_38:
  WPP_SF_d(v9[2], v10, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x1800482c0  push    rbx
0x1800482c2  push    rsi
0x1800482c3  push    rdi
0x1800482c4  push    r12
0x1800482c6  push    r13
0x1800482c8  push    r15
0x1800482ca  sub     rsp, 28h
0x1800482ce  mov     dil, cl
0x1800482d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482d8  lea     r13, WPP_GLOBAL_Control
0x1800482df  lea     r12, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x1800482e6  mov     r15d, 200h
0x1800482ec  cmp     rcx, r13
0x1800482ef  jz      short loc_180048311
0x1800482f1  test    [rcx+1Ch], r15d
0x1800482f5  jz      short loc_180048311
0x1800482f7  cmp     byte ptr [rcx+19h], 6
0x1800482fb  jb      short loc_180048311
0x1800482fd  mov     rcx, [rcx+10h]
0x180048301  mov     edx, 0AFh
0x180048306  mov     r9b, dil
0x180048309  mov     r8, r12
0x18004830c  call    WPP_SF_c
0x180048311  mov     [rsp+58h+arg_8], 0
0x180048319  call    IsRasQuerySharedAutoDialPresent
0x18004831e  test    al, al
0x180048320  jz      short loc_180048331
0x180048322  lea     rcx, [rsp+58h+arg_8]
0x180048327  call    cs:__imp_RasQuerySharedAutoDial
0x18004832d  test    eax, eax
0x18004832f  jnz     short loc_18004838E
0x180048331  cmp     [rsp+58h+arg_8], 0
0x180048336  jz      short loc_18004838E
0x180048338  xor     edx, edx; lpDatabaseName
0x18004833a  xor     ecx, ecx; lpMachineName
0x18004833c  mov     r8d, 0F003Fh; dwDesiredAccess
0x180048342  call    cs:__imp_OpenSCManagerW
0x180048348  mov     rbx, rax
0x18004834b  test    rax, rax
0x18004834e  jz      short loc_18004838E
0x180048350  mov     r8d, 0F01FFh; dwDesiredAccess
0x180048356  lea     rdx, aRasauto; "RasAuto"
0x18004835d  mov     rcx, rax; hSCManager
0x180048360  call    cs:__imp_OpenServiceW
0x180048366  mov     rsi, rax
0x180048369  test    rax, rax
0x18004836c  jz      short loc_180048385
0x18004836e  xor     r8d, r8d; lpServiceArgVectors
0x180048371  xor     edx, edx; dwNumServiceArgs
0x180048373  mov     rcx, rax; hService
0x180048376  call    cs:__imp_StartServiceW
0x18004837c  mov     rcx, rsi; hSCObject
0x18004837f  call    cs:__imp_CloseServiceHandle
0x180048385  mov     rcx, rbx; hSCObject
0x180048388  call    cs:__imp_CloseServiceHandle
0x18004838e  lea     rsi, NatInterfaceLock
0x180048395  mov     rcx, rsi; lpCriticalSection
0x180048398  call    cs:__imp_EnterCriticalSection
0x18004839e  cmp     cs:?g_ConnectionManagementAlreadyStarted@@3HA, 0; int g_ConnectionManagementAlreadyStarted
0x1800483a5  jz      short loc_1800483E3
0x1800483a7  call    ?SignalBeaconSvr@@YAJXZ; SignalBeaconSvr(void)
0x1800483ac  mov     rcx, rsi; lpCriticalSection
0x1800483af  call    cs:__imp_LeaveCriticalSection
0x1800483b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483bc  cmp     rcx, r13
0x1800483bf  jz      loc_1800484F5
0x1800483c5  test    [rcx+1Ch], r15d
0x1800483c9  jz      loc_1800484F5
0x1800483cf  cmp     byte ptr [rcx+19h], 6
0x1800483d3  jb      loc_1800484F5
0x1800483d9  mov     edx, 0B0h
0x1800483de  jmp     loc_1800484E6
0x1800483e3  test    dil, dil
0x1800483e6  jnz     short loc_180048439
0x1800483e8  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x1800483ef  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x1800483f4  test    al, al
0x1800483f6  jnz     short loc_180048439
0x1800483f8  mov     rcx, rsi; lpCriticalSection
0x1800483fb  call    cs:__imp_LeaveCriticalSection
0x180048401  mov     rcx, cs:WPP_GLOBAL_Control
0x180048408  mov     ebx, 3EBh
0x18004840d  cmp     rcx, r13
0x180048410  jz      short loc_180048432
0x180048412  test    [rcx+1Ch], r15d
0x180048416  jz      short loc_180048432
0x180048418  cmp     byte ptr [rcx+19h], 6
0x18004841c  jb      short loc_180048432
0x18004841e  mov     edx, 0B1h
0x180048423  mov     rcx, [rcx+10h]
0x180048427  mov     r9d, ebx
0x18004842a  mov     r8, r12
0x18004842d  call    WPP_SF_d
0x180048432  mov     eax, ebx
0x180048434  jmp     loc_1800484F7
0x180048439  call    ?NhStartICSProtocols@@YAKXZ; NhStartICSProtocols(void)
0x18004843e  mov     ebx, eax
0x180048440  test    eax, eax
0x180048442  jz      short loc_180048497
0x180048444  cmp     cs:?g_ConnectionManagementAlreadyStarted@@3HA, 0; int g_ConnectionManagementAlreadyStarted
0x18004844b  jz      short loc_180048457
0x18004844d  mov     cs:?g_ConnectionManagementAlreadyStarted@@3HA, 0; int g_ConnectionManagementAlreadyStarted
0x180048457  mov     rcx, rsi; lpCriticalSection
0x18004845a  call    cs:__imp_LeaveCriticalSection
0x180048460  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180048467  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18004846c  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180048473  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180048478  mov     rcx, cs:WPP_GLOBAL_Control
0x18004847f  cmp     rcx, r13
0x180048482  jz      short loc_180048432
0x180048484  test    [rcx+1Ch], r15d
0x180048488  jz      short loc_180048432
0x18004848a  cmp     byte ptr [rcx+19h], 6
0x18004848e  jb      short loc_180048432
0x180048490  mov     edx, 0B3h
0x180048495  jmp     short loc_180048423
0x180048497  mov     ebx, 1
0x18004849c  mov     cs:?g_ConnectionManagementAlreadyStarted@@3HA, ebx; int g_ConnectionManagementAlreadyStarted
0x1800484a2  test    dil, dil
0x1800484a5  jnz     short loc_1800484B9
0x1800484a7  mov     r8d, ebx; Flags
0x1800484aa  lea     rcx, ?NatRoutingFailureWorkerRoutine@@YAXPEAX@Z; Function
0x1800484b1  xor     edx, edx; Context
0x1800484b3  call    cs:__imp_RtlQueueWorkItem
0x1800484b9  mov     cl, bl; unsigned __int8
0x1800484bb  call    ?NatIndicateToDriverICSPresence@@YAJE@Z; NatIndicateToDriverICSPresence(uchar)
0x1800484c0  mov     rcx, rsi; lpCriticalSection
0x1800484c3  call    cs:__imp_LeaveCriticalSection
0x1800484c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484d0  cmp     rcx, r13
0x1800484d3  jz      short loc_1800484F5
0x1800484d5  test    [rcx+1Ch], r15d
0x1800484d9  jz      short loc_1800484F5
0x1800484db  cmp     byte ptr [rcx+19h], 6
0x1800484df  jb      short loc_1800484F5
0x1800484e1  mov     edx, 0B2h
0x1800484e6  mov     rcx, [rcx+10h]
0x1800484ea  xor     r9d, r9d
0x1800484ed  mov     r8, r12
0x1800484f0  call    WPP_SF_d
0x1800484f5  xor     eax, eax
0x1800484f7  add     rsp, 28h
0x1800484fb  pop     r15
0x1800484fd  pop     r13
0x1800484ff  pop     r12
0x180048501  pop     rdi
0x180048502  pop     rsi
0x180048503  pop     rbx
0x180048504  retn
```
