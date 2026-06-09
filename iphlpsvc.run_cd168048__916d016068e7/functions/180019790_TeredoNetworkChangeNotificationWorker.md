# TeredoNetworkChangeNotificationWorker

- ea: `0x180019790`
- end: `0x180019a18`
- name: `TeredoNetworkChangeNotificationWorker`
- size: `648`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005500`
- `0x18000d7b0`
- `0x1800190e0`
- `0x180019790`
- `0x180019a20`
- `0x180019bd4`
- `0x18001a0a0`
- `0x180041020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001991b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001991b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800197ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019864`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800197ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019864`

## string_xrefs

- `0x180019964`: `DereferenceService: --%u (%hs) @ %ls:%u`
- `0x18001983f`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18001987c`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18001992b`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18001995a`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x1800198f3`: `Teredo compartment network change: Managed flag = %d\n`
- `0x1800199d0`: `Managed network detection is complete. Managed:(%d)`

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
0x180019790  sub     rsp, 58h
0x180019794  mov     [rsp+58h+arg_0], rbx
0x180019799  mov     [rsp+58h+arg_8], rbp
0x18001979e  xor     ebp, ebp
0x1800197a0  mov     [rsp+58h+var_10], rdi
0x1800197a5  mov     ebx, ebp
0x1800197a7  mov     [rsp+58h+var_18], r14
0x1800197ac  mov     [rsp+58h+var_8], rsi
0x1800197b1  mov     [rsp+58h+arg_10], 1
0x1800197b9  cmp     ebx, 14h
0x1800197bc  jnb     short loc_180019815
0x1800197be  mov     rcx, cs:hHandle; hHandle
0x1800197c5  mov     edx, 0BB8h; dwMilliseconds
0x1800197ca  call    cs:__imp_WaitForSingleObject
0x1800197d1  nop     dword ptr [rax+rax+00h]
0x1800197d6  test    eax, eax
0x1800197d8  jz      short loc_180019804
0x1800197da  lea     rcx, [rsp+58h+arg_10]
0x1800197df  call    TeredoNewManagedNetworkDetection
0x1800197e4  mov     ecx, 100000h
0x1800197e9  test    eax, eax
0x1800197eb  jz      loc_1800199CC
0x1800197f1  mov     r8d, ebx
0x1800197f4  lea     rdx, aCouldNotDetere; "Could not deteremine managed network. L"...
0x1800197fb  call    EventWriteError0
0x180019800  inc     ebx
0x180019802  jmp     short loc_1800197B9
0x180019804  lea     rdx, aStopnetworkdet_0; "StopNetworkDetection signalled"
0x18001980b  mov     ecx, 100000h
0x180019810  call    EventWrite0
0x180019815  mov     esi, [rsp+58h+arg_10]
0x180019819  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x180019820  jnz     loc_1800199E4
0x180019826  mov     rdi, cs:g_TeredoLock
0x18001982d  lea     r14, aTeredonetworkc; "TeredoNetworkChangeNotificationWorker"
0x180019834  mov     r8, rdi
0x180019837  mov     dword ptr [rsp+58h+var_30], 87Ch
0x18001983f  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180019846  mov     [rsp+58h+var_38], r14
0x18001984b  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x180019852  mov     ecx, 800000h
0x180019857  call    EventWrite0
0x18001985c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180019861  mov     rcx, rdi; hHandle
0x180019864  call    cs:__imp_WaitForSingleObject
0x18001986b  nop     dword ptr [rax+rax+00h]
0x180019870  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x180019877  mov     r8, rdi
0x18001987a  mov     ebx, eax
0x18001987c  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180019883  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x18001988a  mov     [rsp+58h+var_28], ebx
0x18001988e  test    ebx, ebx
0x180019890  mov     dword ptr [rsp+58h+var_30], 87Ch
0x180019898  mov     ecx, 800000h
0x18001989d  mov     [rsp+58h+var_38], r14
0x1800198a2  cmovnz  rdx, rax
0x1800198a6  call    EventWrite0
0x1800198ab  test    ebx, ebx
0x1800198ad  jnz     loc_180019953
0x1800198b3  cmp     cs:dword_1800CA09C, 3
0x1800198ba  mov     cs:dword_1800CA0A4, ebp
0x1800198c0  jz      short loc_180019911
0x1800198c2  mov     rbx, cs:g_ProtocolStateTeredo
0x1800198c9  test    rbx, rbx
0x1800198cc  jz      short loc_180019911
0x1800198ce  mov     eax, esi
0x1800198d0  lea     rsi, g_ProtocolStateTeredo
0x1800198d7  cmp     rbx, rsi
0x1800198da  jz      short loc_180019911
0x1800198dc  test    eax, eax
0x1800198de  mov     edi, ebp
0x1800198e0  setnz   dil
0x1800198e4  cmp     [rbx+0AD4h], edi
0x1800198ea  jnz     loc_1800199FF
0x1800198f0  mov     r8d, edi
0x1800198f3  lea     rdx, aTeredoCompartm; "Teredo compartment network change: Mana"...
0x1800198fa  mov     ecx, 100000h
0x1800198ff  call    EventWrite0
0x180019904  call    CheckDefaultGateways
0x180019909  mov     rbx, [rbx]
0x18001990c  cmp     rbx, rsi
0x18001990f  jnz     short loc_1800198E4
0x180019911  mov     rbx, cs:g_TeredoLock
0x180019918  mov     rcx, rbx; hMutex
0x18001991b  call    cs:__imp_ReleaseMutex
0x180019922  nop     dword ptr [rax+rax+00h]
0x180019927  mov     [rsp+58h+var_28], eax
0x18001992b  lea     r9, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180019932  mov     dword ptr [rsp+58h+var_30], 88Ch
0x18001993a  mov     r8, rbx
0x18001993d  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x180019944  mov     [rsp+58h+var_38], r14
0x180019949  mov     ecx, 800000h
0x18001994e  call    EventWrite0
0x180019953  mov     r8d, cs:g_Reference
0x18001995a  lea     rax, aOnecoreuapNetN_19; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180019961  shr     r8d, 1
0x180019964  lea     rdx, aDereferenceser; "DereferenceService: --%u (%hs) @ %ls:%u"
0x18001996b  and     r8d, 3FFFFFFFh
0x180019972  mov     dword ptr [rsp+58h+var_30], 890h
0x18001997a  mov     r9, r14
0x18001997d  mov     cs:dword_1800CA0A4, ebp
0x180019983  mov     ecx, 40000h
0x180019988  mov     [rsp+58h+var_38], rax
0x18001998d  call    EventWrite0
0x180019992  mov     eax, 0FFFFFFFEh
0x180019997  lock xadd cs:g_Reference, eax
0x18001999f  mov     r14, [rsp+58h+var_18]
0x1800199a4  mov     rdi, [rsp+58h+var_10]
0x1800199a9  mov     rsi, [rsp+58h+var_8]
0x1800199ae  mov     rbp, [rsp+58h+arg_8]
0x1800199b3  mov     rbx, [rsp+58h+arg_0]
0x1800199b8  cmp     eax, 3
0x1800199bb  jnz     short loc_1800199C6
0x1800199bd  add     rsp, 58h
0x1800199c1  jmp     CleanupHelperService
0x1800199c6  add     rsp, 58h
0x1800199ca  retn
0x1800199cc  mov     esi, [rsp+58h+arg_10]
0x1800199d0  lea     rdx, aManagedNetwork; "Managed network detection is complete. "...
0x1800199d7  mov     r8d, esi
0x1800199da  call    EventWrite0
0x1800199df  jmp     loc_180019819
0x1800199e4  mov     r8d, esi
0x1800199e7  lea     rdx, EVENT_IPHLPSVC_ETW_NLM_DOMAIN_DETECTION
0x1800199ee  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x1800199f5  call    McTemplateU0q_EventWriteTransfer
0x1800199fa  jmp     loc_180019826
0x1800199ff  mov     [rbx+0AD4h], edi
0x180019a05  mov     rcx, rbx
0x180019a08  mov     edx, cs:dword_1800CA09C
0x180019a0e  call    TeredoCompartmentConfigurationChangeNotification
0x180019a13  jmp     loc_1800198F0
```
