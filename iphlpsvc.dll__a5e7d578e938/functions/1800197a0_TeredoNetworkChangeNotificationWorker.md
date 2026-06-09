# TeredoNetworkChangeNotificationWorker

- ea: `0x1800197a0`
- end: `0x180019a28`
- name: `TeredoNetworkChangeNotificationWorker`
- size: `648`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005510`
- `0x18000d7c0`
- `0x1800190f0`
- `0x1800197a0`
- `0x180019a30`
- `0x180019be4`
- `0x18001a0b0`
- `0x180040fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001992b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001992b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800197da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019874`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800197da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019874`

## string_xrefs

- `0x180019974`: `DereferenceService: --%u (%hs) @ %ls:%u`
- `0x18001984f`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18001988c`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18001993b`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18001996a`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x180019903`: `Teredo compartment network change: Managed flag = %d\n`
- `0x1800199e0`: `Managed network detection is complete. Managed:(%d)`

## pseudocode

```c
void __fastcall TeredoNetworkChangeNotificationWorker(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  unsigned int v2; // ebx
  unsigned int v3; // esi
  HANDLE v4; // rdi
  DWORD v5; // eax
  const wchar_t *v6; // rdx
  DWORD v7; // ebx
  __int64 v8; // rbx
  int v9; // edi
  HANDLE v10; // rbx
  __int64 v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+28h] [rbp-30h]
  __int64 v13; // [rsp+30h] [rbp-28h]
  unsigned int v14; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v14 = 1;
  while ( 1 )
  {
    if ( v2 >= 0x14 )
      goto LABEL_7;
    if ( !WaitForSingleObject(hHandle, 0xBB8u) )
    {
      EventWrite0(0x100000, L"StopNetworkDetection signalled");
LABEL_7:
      v3 = v14;
      goto LABEL_8;
    }
    if ( !(unsigned int)TeredoNewManagedNetworkDetection(&v14) )
      break;
    EventWriteError0(0x100000, L"Could not deteremine managed network. Loop(%d)", v2++);
  }
  v3 = v14;
  EventWrite0(0x100000, L"Managed network detection is complete. Managed:(%d)", v14);
LABEL_8:
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(MS_IPHLPSVC_ETW_PROVIDER_ID_Context, EVENT_IPHLPSVC_ETW_NLM_DOMAIN_DETECTION, v3);
  v4 = g_TeredoLock;
  EventWrite0(
    0x800000,
    L"Get lock (%p) invoked at %S : %S : %u",
    g_TeredoLock,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
    "TeredoNetworkChangeNotificationWorker",
    2172);
  v5 = WaitForSingleObject(v4, 0xFFFFFFFF);
  v6 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
  v7 = v5;
  LODWORD(v11) = 2172;
  if ( v5 )
    v6 = L"Lock (%p) failed at %S : %S : %u. Return %d";
  EventWrite0(
    0x800000,
    v6,
    v4,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
    "TeredoNetworkChangeNotificationWorker",
    v11,
    v5);
  if ( !v7 )
  {
    dword_1800CA0A4 = 0;
    if ( dword_1800CA09C != 3 )
    {
      v8 = g_ProtocolStateTeredo;
      if ( g_ProtocolStateTeredo )
      {
        if ( (__int64 *)g_ProtocolStateTeredo != &g_ProtocolStateTeredo )
        {
          v9 = v3 != 0;
          do
          {
            if ( *(_DWORD *)(v8 + 2772) != v9 )
            {
              *(_DWORD *)(v8 + 2772) = v9;
              TeredoCompartmentConfigurationChangeNotification(v8, (unsigned int)dword_1800CA09C);
            }
            EventWrite0(0x100000, L"Teredo compartment network change: Managed flag = %d\n", v3 != 0);
            CheckDefaultGateways();
            v8 = *(_QWORD *)v8;
          }
          while ( (__int64 *)v8 != &g_ProtocolStateTeredo );
        }
      }
    }
    v10 = g_TeredoLock;
    LODWORD(v13) = ReleaseMutex(g_TeredoLock);
    LODWORD(v12) = 2188;
    EventWrite0(
      0x800000,
      L"Lock (%p) released at %S : %S : %u. Return %d",
      v10,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
      "TeredoNetworkChangeNotificationWorker",
      v12,
      v13);
  }
  LODWORD(v12) = 2192;
  dword_1800CA0A4 = 0;
  EventWrite0(
    0x40000,
    L"DereferenceService: --%u (%hs) @ %ls:%u",
    ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
    "TeredoNetworkChangeNotificationWorker",
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
    v12);
  if ( _InterlockedExchangeAdd(&g_Reference, 0xFFFFFFFE) == 3 )
    CleanupHelperService();
}

```

## disassembly

```asm
0x1800197a0  sub     rsp, 58h
0x1800197a4  mov     [rsp+58h+arg_0], rbx
0x1800197a9  mov     [rsp+58h+arg_8], rbp
0x1800197ae  xor     ebp, ebp
0x1800197b0  mov     [rsp+58h+var_10], rdi
0x1800197b5  mov     ebx, ebp
0x1800197b7  mov     [rsp+58h+var_18], r14
0x1800197bc  mov     [rsp+58h+var_8], rsi
0x1800197c1  mov     [rsp+58h+arg_10], 1
0x1800197c9  cmp     ebx, 14h
0x1800197cc  jnb     short loc_180019825
0x1800197ce  mov     rcx, cs:hHandle; hHandle
0x1800197d5  mov     edx, 0BB8h; dwMilliseconds
0x1800197da  call    cs:__imp_WaitForSingleObject
0x1800197e1  nop     dword ptr [rax+rax+00h]
0x1800197e6  test    eax, eax
0x1800197e8  jz      short loc_180019814
0x1800197ea  lea     rcx, [rsp+58h+arg_10]
0x1800197ef  call    TeredoNewManagedNetworkDetection
0x1800197f4  mov     ecx, 100000h
0x1800197f9  test    eax, eax
0x1800197fb  jz      loc_1800199DC
0x180019801  mov     r8d, ebx
0x180019804  lea     rdx, aCouldNotDetere; "Could not deteremine managed network. L"...
0x18001980b  call    EventWriteError0
0x180019810  inc     ebx
0x180019812  jmp     short loc_1800197C9
0x180019814  lea     rdx, aStopnetworkdet_0; "StopNetworkDetection signalled"
0x18001981b  mov     ecx, 100000h
0x180019820  call    EventWrite0
0x180019825  mov     esi, [rsp+58h+arg_10]
0x180019829  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x180019830  jnz     loc_1800199F4
0x180019836  mov     rdi, cs:g_TeredoLock
0x18001983d  lea     r14, aTeredonetworkc; "TeredoNetworkChangeNotificationWorker"
0x180019844  mov     r8, rdi
0x180019847  mov     dword ptr [rsp+58h+var_30], 87Ch
0x18001984f  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180019856  mov     [rsp+58h+var_38], r14
0x18001985b  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x180019862  mov     ecx, 800000h
0x180019867  call    EventWrite0
0x18001986c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180019871  mov     rcx, rdi; hHandle
0x180019874  call    cs:__imp_WaitForSingleObject
0x18001987b  nop     dword ptr [rax+rax+00h]
0x180019880  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180019887  mov     r8, rdi
0x18001988a  mov     ebx, eax
0x18001988c  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180019893  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x18001989a  mov     [rsp+58h+var_28], ebx
0x18001989e  test    ebx, ebx
0x1800198a0  mov     dword ptr [rsp+58h+var_30], 87Ch
0x1800198a8  mov     ecx, 800000h
0x1800198ad  mov     [rsp+58h+var_38], r14
0x1800198b2  cmovnz  rdx, rax
0x1800198b6  call    EventWrite0
0x1800198bb  test    ebx, ebx
0x1800198bd  jnz     loc_180019963
0x1800198c3  cmp     cs:dword_1800CA09C, 3
0x1800198ca  mov     cs:dword_1800CA0A4, ebp
0x1800198d0  jz      short loc_180019921
0x1800198d2  mov     rbx, cs:g_ProtocolStateTeredo
0x1800198d9  test    rbx, rbx
0x1800198dc  jz      short loc_180019921
0x1800198de  mov     eax, esi
0x1800198e0  lea     rsi, g_ProtocolStateTeredo
0x1800198e7  cmp     rbx, rsi
0x1800198ea  jz      short loc_180019921
0x1800198ec  test    eax, eax
0x1800198ee  mov     edi, ebp
0x1800198f0  setnz   dil
0x1800198f4  cmp     [rbx+0AD4h], edi
0x1800198fa  jnz     loc_180019A0F
0x180019900  mov     r8d, edi
0x180019903  lea     rdx, aTeredoCompartm; "Teredo compartment network change: Mana"...
0x18001990a  mov     ecx, 100000h
0x18001990f  call    EventWrite0
0x180019914  call    CheckDefaultGateways
0x180019919  mov     rbx, [rbx]
0x18001991c  cmp     rbx, rsi
0x18001991f  jnz     short loc_1800198F4
0x180019921  mov     rbx, cs:g_TeredoLock
0x180019928  mov     rcx, rbx; hMutex
0x18001992b  call    cs:__imp_ReleaseMutex
0x180019932  nop     dword ptr [rax+rax+00h]
0x180019937  mov     [rsp+58h+var_28], eax
0x18001993b  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180019942  mov     dword ptr [rsp+58h+var_30], 88Ch
0x18001994a  mov     r8, rbx
0x18001994d  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180019954  mov     [rsp+58h+var_38], r14
0x180019959  mov     ecx, 800000h
0x18001995e  call    EventWrite0
0x180019963  mov     r8d, cs:g_Reference
0x18001996a  lea     rax, aOnecoreuapNetN_19; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180019971  shr     r8d, 1
0x180019974  lea     rdx, aDereferenceser; "DereferenceService: --%u (%hs) @ %ls:%u"
0x18001997b  and     r8d, 3FFFFFFFh
0x180019982  mov     dword ptr [rsp+58h+var_30], 890h
0x18001998a  mov     r9, r14
0x18001998d  mov     cs:dword_1800CA0A4, ebp
0x180019993  mov     ecx, 40000h
0x180019998  mov     [rsp+58h+var_38], rax
0x18001999d  call    EventWrite0
0x1800199a2  mov     eax, 0FFFFFFFEh
0x1800199a7  lock xadd cs:g_Reference, eax
0x1800199af  mov     r14, [rsp+58h+var_18]
0x1800199b4  mov     rdi, [rsp+58h+var_10]
0x1800199b9  mov     rsi, [rsp+58h+var_8]
0x1800199be  mov     rbp, [rsp+58h+arg_8]
0x1800199c3  mov     rbx, [rsp+58h+arg_0]
0x1800199c8  cmp     eax, 3
0x1800199cb  jnz     short loc_1800199D6
0x1800199cd  add     rsp, 58h
0x1800199d1  jmp     CleanupHelperService
0x1800199d6  add     rsp, 58h
0x1800199da  retn
0x1800199dc  mov     esi, [rsp+58h+arg_10]
0x1800199e0  lea     rdx, aManagedNetwork; "Managed network detection is complete. "...
0x1800199e7  mov     r8d, esi
0x1800199ea  call    EventWrite0
0x1800199ef  jmp     loc_180019829
0x1800199f4  mov     r8d, esi
0x1800199f7  lea     rdx, EVENT_IPHLPSVC_ETW_NLM_DOMAIN_DETECTION
0x1800199fe  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180019a05  call    McTemplateU0q_EventWriteTransfer
0x180019a0a  jmp     loc_180019836
0x180019a0f  mov     [rbx+0AD4h], edi
0x180019a15  mov     rcx, rbx
0x180019a18  mov     edx, cs:dword_1800CA09C
0x180019a1e  call    TeredoCompartmentConfigurationChangeNotification
0x180019a23  jmp     loc_180019900
```
