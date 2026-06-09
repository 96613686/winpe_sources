# NatStartSharedConnectionManagement(uchar)

- ea: `0x18004be98`
- end: `0x18004c126`
- name: `?NatStartSharedConnectionManagement@@YAKE@Z`
- size: `654`
- prototype: `unsigned int __fastcall(unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ff48`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000d090`
- `0x180014f6c`
- `0x18004561c`
- `0x1800466fc`
- `0x18004be98`
- `0x1800533e8`
- `0x180075f14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bf94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004bf94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bfb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c003`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c0dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bfb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c003`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c0dd`
- `ntdll!RtlQueueWorkItem` at `0x18004c0c7`
- `ntdll!RtlQueueWorkItem` at `0x18004c0c7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004bf20`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18004bf20`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004bf6f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004bf7e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004bf6f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004bf7e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18004bf60`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18004bf60`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004bf44`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004bf44`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasQuerySharedAutoDial` at `0x18004beff`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasQuerySharedAutoDial` at `0x18004beff`

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
0x18004be98  push    rbx
0x18004be9a  push    rsi
0x18004be9b  push    rdi
0x18004be9c  push    r12
0x18004be9e  push    r13
0x18004bea0  push    r15
0x18004bea2  sub     rsp, 28h
0x18004bea6  mov     dil, cl
0x18004bea9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004beb0  lea     r13, WPP_GLOBAL_Control
0x18004beb7  lea     r12, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18004bebe  mov     r15d, 200h
0x18004bec4  cmp     rcx, r13
0x18004bec7  jz      short loc_18004BEE9
0x18004bec9  test    [rcx+1Ch], r15d
0x18004becd  jz      short loc_18004BEE9
0x18004becf  cmp     byte ptr [rcx+19h], 6
0x18004bed3  jb      short loc_18004BEE9
0x18004bed5  mov     rcx, [rcx+10h]
0x18004bed9  mov     edx, 0AFh
0x18004bede  mov     r9b, dil
0x18004bee1  mov     r8, r12
0x18004bee4  call    WPP_SF_c
0x18004bee9  mov     [rsp+58h+arg_8], 0
0x18004bef1  call    IsRasQuerySharedAutoDialPresent
0x18004bef6  test    al, al
0x18004bef8  jz      short loc_18004BF0F
0x18004befa  lea     rcx, [rsp+58h+arg_8]
0x18004beff  call    cs:__imp_RasQuerySharedAutoDial
0x18004bf06  nop     dword ptr [rax+rax+00h]
0x18004bf0b  test    eax, eax
0x18004bf0d  jnz     short loc_18004BF8A
0x18004bf0f  cmp     [rsp+58h+arg_8], 0
0x18004bf14  jz      short loc_18004BF8A
0x18004bf16  xor     edx, edx; lpDatabaseName
0x18004bf18  xor     ecx, ecx; lpMachineName
0x18004bf1a  mov     r8d, 0F003Fh; dwDesiredAccess
0x18004bf20  call    cs:__imp_OpenSCManagerW
0x18004bf27  nop     dword ptr [rax+rax+00h]
0x18004bf2c  mov     rbx, rax
0x18004bf2f  test    rax, rax
0x18004bf32  jz      short loc_18004BF8A
0x18004bf34  mov     r8d, 0F01FFh; dwDesiredAccess
0x18004bf3a  lea     rdx, aRasauto; "RasAuto"
0x18004bf41  mov     rcx, rax; hSCManager
0x18004bf44  call    cs:__imp_OpenServiceW
0x18004bf4b  nop     dword ptr [rax+rax+00h]
0x18004bf50  mov     rsi, rax
0x18004bf53  test    rax, rax
0x18004bf56  jz      short loc_18004BF7B
0x18004bf58  xor     r8d, r8d; lpServiceArgVectors
0x18004bf5b  xor     edx, edx; dwNumServiceArgs
0x18004bf5d  mov     rcx, rax; hService
0x18004bf60  call    cs:__imp_StartServiceW
0x18004bf67  nop     dword ptr [rax+rax+00h]
0x18004bf6c  mov     rcx, rsi; hSCObject
0x18004bf6f  call    cs:__imp_CloseServiceHandle
0x18004bf76  nop     dword ptr [rax+rax+00h]
0x18004bf7b  mov     rcx, rbx; hSCObject
0x18004bf7e  call    cs:__imp_CloseServiceHandle
0x18004bf85  nop     dword ptr [rax+rax+00h]
0x18004bf8a  lea     rsi, NatInterfaceLock
0x18004bf91  mov     rcx, rsi; lpCriticalSection
0x18004bf94  call    cs:__imp_EnterCriticalSection
0x18004bf9b  nop     dword ptr [rax+rax+00h]
0x18004bfa0  cmp     cs:?g_ConnectionManagementAlreadyStarted@@3HA, 0; int g_ConnectionManagementAlreadyStarted
0x18004bfa7  jz      short loc_18004BFEB
0x18004bfa9  call    ?SignalBeaconSvr@@YAJXZ; SignalBeaconSvr(void)
0x18004bfae  mov     rcx, rsi; lpCriticalSection
0x18004bfb1  call    cs:__imp_LeaveCriticalSection
0x18004bfb8  nop     dword ptr [rax+rax+00h]
0x18004bfbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bfc4  cmp     rcx, r13
0x18004bfc7  jz      loc_18004C115
0x18004bfcd  test    [rcx+1Ch], r15d
0x18004bfd1  jz      loc_18004C115
0x18004bfd7  cmp     byte ptr [rcx+19h], 6
0x18004bfdb  jb      loc_18004C115
0x18004bfe1  mov     edx, 0B0h
0x18004bfe6  jmp     loc_18004C106
0x18004bfeb  test    dil, dil
0x18004bfee  jnz     short loc_18004C047
0x18004bff0  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x18004bff7  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18004bffc  test    al, al
0x18004bffe  jnz     short loc_18004C047
0x18004c000  mov     rcx, rsi; lpCriticalSection
0x18004c003  call    cs:__imp_LeaveCriticalSection
0x18004c00a  nop     dword ptr [rax+rax+00h]
0x18004c00f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c016  mov     ebx, 3EBh
0x18004c01b  cmp     rcx, r13
0x18004c01e  jz      short loc_18004C040
0x18004c020  test    [rcx+1Ch], r15d
0x18004c024  jz      short loc_18004C040
0x18004c026  cmp     byte ptr [rcx+19h], 6
0x18004c02a  jb      short loc_18004C040
0x18004c02c  mov     edx, 0B1h
0x18004c031  mov     rcx, [rcx+10h]
0x18004c035  mov     r9d, ebx
0x18004c038  mov     r8, r12
0x18004c03b  call    WPP_SF_d
0x18004c040  mov     eax, ebx
0x18004c042  jmp     loc_18004C117
0x18004c047  call    ?NhStartICSProtocols@@YAKXZ; NhStartICSProtocols(void)
0x18004c04c  mov     ebx, eax
0x18004c04e  test    eax, eax
0x18004c050  jz      short loc_18004C0AB
0x18004c052  cmp     cs:?g_ConnectionManagementAlreadyStarted@@3HA, 0; int g_ConnectionManagementAlreadyStarted
0x18004c059  jz      short loc_18004C065
0x18004c05b  mov     cs:?g_ConnectionManagementAlreadyStarted@@3HA, 0; int g_ConnectionManagementAlreadyStarted
0x18004c065  mov     rcx, rsi; lpCriticalSection
0x18004c068  call    cs:__imp_LeaveCriticalSection
0x18004c06f  nop     dword ptr [rax+rax+00h]
0x18004c074  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18004c07b  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18004c080  lea     rcx, ?NatComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x18004c087  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18004c08c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c093  cmp     rcx, r13
0x18004c096  jz      short loc_18004C040
0x18004c098  test    [rcx+1Ch], r15d
0x18004c09c  jz      short loc_18004C040
0x18004c09e  cmp     byte ptr [rcx+19h], 6
0x18004c0a2  jb      short loc_18004C040
0x18004c0a4  mov     edx, 0B3h
0x18004c0a9  jmp     short loc_18004C031
0x18004c0ab  mov     ebx, 1
0x18004c0b0  mov     cs:?g_ConnectionManagementAlreadyStarted@@3HA, ebx; int g_ConnectionManagementAlreadyStarted
0x18004c0b6  test    dil, dil
0x18004c0b9  jnz     short loc_18004C0D3
0x18004c0bb  mov     r8d, ebx; Flags
0x18004c0be  lea     rcx, ?NatRoutingFailureWorkerRoutine@@YAXPEAX@Z; Function
0x18004c0c5  xor     edx, edx; Context
0x18004c0c7  call    cs:__imp_RtlQueueWorkItem
0x18004c0ce  nop     dword ptr [rax+rax+00h]
0x18004c0d3  mov     cl, bl; unsigned __int8
0x18004c0d5  call    ?NatIndicateToDriverICSPresence@@YAJE@Z; NatIndicateToDriverICSPresence(uchar)
0x18004c0da  mov     rcx, rsi; lpCriticalSection
0x18004c0dd  call    cs:__imp_LeaveCriticalSection
0x18004c0e4  nop     dword ptr [rax+rax+00h]
0x18004c0e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0f0  cmp     rcx, r13
0x18004c0f3  jz      short loc_18004C115
0x18004c0f5  test    [rcx+1Ch], r15d
0x18004c0f9  jz      short loc_18004C115
0x18004c0fb  cmp     byte ptr [rcx+19h], 6
0x18004c0ff  jb      short loc_18004C115
0x18004c101  mov     edx, 0B2h
0x18004c106  mov     rcx, [rcx+10h]
0x18004c10a  xor     r9d, r9d
0x18004c10d  mov     r8, r12
0x18004c110  call    WPP_SF_d
0x18004c115  xor     eax, eax
0x18004c117  add     rsp, 28h
0x18004c11b  pop     r15
0x18004c11d  pop     r13
0x18004c11f  pop     r12
0x18004c121  pop     rdi
0x18004c122  pop     rsi
0x18004c123  pop     rbx
0x18004c124  retn
```
