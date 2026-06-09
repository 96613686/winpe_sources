# TeredoStartClient

- ea: `0x180014180`
- end: `0x180014767`
- name: `TeredoStartClient`
- size: `1511`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `8`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180005510`
- `0x1800087c0`
- `0x18000c210`
- `0x1800135b0`
- `0x1800138bc`
- `0x180013f74`
- `0x180014120`
- `0x180043310`

## callees

- `0x180008af4`
- `0x18000d7c0`
- `0x180012dcc`
- `0x180014180`
- `0x180014770`
- `0x18001480c`
- `0x180015170`
- `0x180015a00`
- `0x180015a7c`
- `0x1800163e4`
- `0x180016ac0`
- `0x1800190f0`
- `0x180039adc`
- `0x180040fe0`
- `0x18004d2b8`
- `0x180050274`

## import_xrefs

- `IPHLPAPI!InternalSetTeredoPort` at `0x180014672`
- `IPHLPAPI!InternalSetTeredoPort` at `0x180014672`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800145c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800145c6`
- `WS2_32!__imp_ntohs` at `0x1800146bd`
- `WS2_32!__imp_ntohs` at `0x1800146bd`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x1800146a2`
- `ext-ms-win-networking-iphlpsvc-l1-1-0!IphlpsvcExtConfigureTeredoClientPort` at `0x1800146a2`
- `NSI!NsiGetAllParameters` at `0x18001442c`
- `NSI!NsiGetAllParameters` at `0x18001442c`

## string_xrefs

- `0x180014190`: `Teredo starting client:  0x%p (CompartmentId %u)`
- `0x1800145e9`: `%s has been created: timer memory pointer = %p`
- `0x18001446e`: `onecoreuap\net\netio\iphlpsvc\service\client.c`
- `0x1800141f8`: `Configuration is not complete. State = %d`
- `0x180014279`: `In low power mode. Skipping start attempt in state %d.`

## pseudocode

```c
__int64 __fastcall TeredoStartClient(unsigned int *pv)
{
  __int64 v1; // rsi
  __int64 result; // rax
  unsigned int v4; // r8d
  bool v5; // zf
  const wchar_t *v6; // r8
  unsigned int v7; // ebp
  unsigned int AllParameters; // r14d
  unsigned int v9; // edx
  __int64 v10; // rax
  unsigned int started; // eax
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rdi
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned int v16; // ecx
  __int64 v17; // rax
  u_short v18; // ax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // [rsp+20h] [rbp-68h]
  __int64 v22; // [rsp+20h] [rbp-68h]
  __int64 v23; // [rsp+90h] [rbp+8h] BYREF

  v1 = *((_QWORD *)pv + 988);
  v23 = 0;
  result = EventWrite0(0x100000, L"Teredo starting client:  0x%p (CompartmentId %u)", pv, *(unsigned int *)(v1 + 16));
  if ( *(_DWORD *)(v1 + 16) == 1 && dword_1800CB7E8 )
    return EventWrite0(0x100000, L"Server is not offline yet. State = %d");
  if ( !*(_DWORD *)(v1 + 24) )
  {
    if ( !pv[2169] )
      return EventWrite0(0x100000, L"Configuration is not complete. State = %d", pv[2146]);
    if ( !*(_DWORD *)(v1 + 2784) )
    {
      result = EventWriteError0(0x100000, L"BFE not running. Skipping start.");
      *(_DWORD *)(v1 + 2868) = 18;
      return result;
    }
    if ( !*(_DWORD *)(v1 + 19480) )
    {
      result = EventWriteError0(0x100000, L"Default block filter not found. Skipping start.");
      *(_DWORD *)(v1 + 2868) = 19;
      return result;
    }
    if ( *((_BYTE *)pv + 14394) && !*((_BYTE *)pv + 8697) )
    {
      result = EventWriteError0(0x100000, L"In low power mode. Skipping start attempt in state %d.", pv[2146]);
      *(_DWORD *)(v1 + 2868) = 21;
      return result;
    }
    v4 = pv[2146];
    if ( v4 )
    {
      if ( v4 != 1 )
        return EventWrite0(0x100000, L"Client state is %d. Does not need starting.");
      result = TeredoClientChangeStateAndLog(pv, 2);
      if ( !*((_BYTE *)pv + 8698) )
        return TeredoClientUpdateStateInNsi(pv);
      return result;
    }
    if ( pv[3594] )
    {
      EventWrite0(0x100000, L"TeredoStartClient: resetting NumConsecutiveFailures (was %u)", pv[3592]);
      pv[3592] = 0;
    }
    *(_DWORD *)(v1 + 2872) = *(_DWORD *)(v1 + 2868);
    v5 = *(_DWORD *)(v1 + 2768) == 0;
    *(_DWORD *)(v1 + 2868) = 0;
    *(_DWORD *)(v1 + 2876) = 0;
    *(_DWORD *)(v1 + 2864) = !v5 + 1;
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STATE_CHANGE,
        pv[2146],
        8);
    v6 = L"Relay";
    if ( *(_DWORD *)(*((_QWORD *)pv + 988) + 2864LL) != 1 )
      v6 = L"Client";
    EventWrite0(0x100000, L"Current status: %ws Mode, Firewall enabled %d, Listening Apps %u", v6, pv[2172], pv[2171]);
    v7 = 1;
    pv[2146] = 8;
    pv[2170] = 0;
    pv[2745] = 0;
    pv[2746] = 6;
    AllParameters = NsiGetAllParameters(1, &NPI_MS_FL6T_MODULEID, 0, 0, 0, 0, 0, &v23, 8, 0, 0);
    if ( !AllParameters )
    {
      pv[2171] = v23;
      EventWrite0(0x100000, L"ListeningApplications is %u");
    }
    TeredoStartIo(pv + 1286);
    LODWORD(v21) = 2500;
    EventWrite0(
      0x100000,
      L"TeredoReferenceClient: ++%d @ %ls:%u",
      *pv,
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
      v21);
    v9 = *pv;
    v10 = 5LL * (_InterlockedExchangeAdd((volatile signed __int32 *)pv + 2, 1u) & 0x3F);
    pv[2 * v10 + 4] = v9;
    pv[2 * v10 + 8] = 2500;
    *(_QWORD *)&pv[2 * v10 + 6] = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c";
    pv[2 * v10 + 12] = 0;
    *(_QWORD *)&pv[2 * v10 + 10] = 0;
    _InterlockedIncrement((volatile signed __int32 *)pv);
    TeredoInitializeAddressComponents(pv + 1286);
    if ( !pv[1940] )
      goto LABEL_43;
    TeredoTraceAddress(L"Previous address initialized to", v1 + 4932);
    *(_QWORD *)((char *)pv + 7862) = *(_QWORD *)(v1 + 4940);
    started = TeredoStartDevice(pv + 2098);
    AllParameters = started;
    if ( started )
    {
      EventWriteError0(0x100000, L"Failed to start Teredo client. Could not start tunnel (%u)", started);
      *(_DWORD *)(v1 + 2868) = 5;
      *(_DWORD *)(v1 + 2876) = AllParameters;
LABEL_43:
      if ( *(_DWORD *)(v1 + 2868) )
      {
        v7 = *(_DWORD *)(v1 + 2868);
      }
      else
      {
        *(_DWORD *)(v1 + 2868) = 1;
        *(_DWORD *)(v1 + 2876) = AllParameters;
      }
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(
          MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
          EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_START_FAILED,
          v7);
      EventWrite0(0x100000, L"Failed to wake-up Teredo client. Hence, stopping.");
      return TeredoStopClient(pv, v19, v20);
    }
    v12 = MALLOC(0x20u);
    *((_QWORD *)pv + 1369) = v12;
    if ( !v12 )
      goto LABEL_42;
    v5 = pv[2168] == 8;
    *((_BYTE *)pv + 14392) = 0;
    if ( v5 )
    {
      v13 = TeredoSetMediaStateToConnected(*((_QWORD *)pv + 1052));
      AllParameters = v13;
      if ( v13 )
      {
        EventWriteError0(
          0x100000,
          L"Failed to start Teredo client. Could not set interface to Media Connected (%u)",
          v13);
        *(_DWORD *)(v1 + 2868) = 5;
        *(_DWORD *)(v1 + 2876) = AllParameters;
        *(_DWORD *)(v1 + 19396) = 2;
        goto LABEL_43;
      }
      *((_BYTE *)pv + 14392) = 1;
    }
    v14 = *((_QWORD *)pv + 1369);
    ThreadpoolTimer = CreateThreadpoolTimer(TeredoClientTimerCallback, pv, &CallbackEnvironment);
    *(_QWORD *)(v14 + 16) = ThreadpoolTimer;
    if ( !ThreadpoolTimer
      || (EventWrite0(
            0x8000000,
            L"%s has been created: timer memory pointer = %p",
            L"Teredo Client Timer",
            ThreadpoolTimer),
          !(unsigned int)TpclSetTimer(L"Teredo Client Timer", *(_QWORD *)(v14 + 16), 0, 0x7FFFFFFF)) )
    {
LABEL_42:
      *(_DWORD *)(v1 + 2876) = 8;
      *(_DWORD *)(v1 + 2868) = 1;
      goto LABEL_43;
    }
    LODWORD(v22) = 2584;
    EventWrite0(
      0x100000,
      L"TeredoReferenceClient: ++%d @ %ls:%u",
      *pv,
      L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
      v22);
    v16 = *pv;
    v17 = 5LL * (_InterlockedExchangeAdd((volatile signed __int32 *)pv + 2, 1u) & 0x3F);
    pv[2 * v17 + 4] = v16;
    pv[2 * v17 + 8] = 2584;
    *(_QWORD *)&pv[2 * v17 + 6] = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c";
    pv[2 * v17 + 12] = 0;
    *(_QWORD *)&pv[2 * v17 + 10] = 0;
    _InterlockedIncrement((volatile signed __int32 *)pv);
    TeredoClientUpdateStateInNsi(pv);
    if ( (unsigned int)InternalSetTeredoPort(0) )
      EventWriteError0(0x100000, L"Unable to initialize Teredo port state in NSI.");
    result = IsIphlpsvcExtConfigureTeredoClientPortPresent();
    if ( (_BYTE)result )
    {
      result = IphlpsvcExtConfigureTeredoClientPort(0);
      if ( (_DWORD)result )
      {
        v18 = ntohs(*((_WORD *)pv + 3903));
        return EventWriteError0(0x100000, L"Unable to set Teredo port value (%d) in Xbox Virtual NIC", v18);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014180  push    rbx
0x180014182  push    rsi
0x180014183  push    r15
0x180014185  sub     rsp, 70h
0x180014189  mov     rsi, [rcx+1EE0h]
0x180014190  lea     rdx, aTeredoStarting; "Teredo starting client:  0x%p (Compartm"...
0x180014197  mov     rbx, rcx
0x18001419a  mov     r8, rcx
0x18001419d  xor     r15d, r15d
0x1800141a0  mov     ecx, 100000h
0x1800141a5  mov     [rsp+88h+arg_0], r15
0x1800141ad  mov     r9d, [rsi+10h]
0x1800141b1  call    EventWrite0
0x1800141b6  cmp     dword ptr [rsi+10h], 1
0x1800141ba  jnz     short loc_1800141DE
0x1800141bc  mov     r8d, cs:dword_1800CB7E8
0x1800141c3  test    r8d, r8d
0x1800141c6  jz      short loc_1800141DE
0x1800141c8  lea     rdx, aServerIsNotOff; "Server is not offline yet. State = %d"
0x1800141cf  mov     ecx, 100000h
0x1800141d4  call    EventWrite0
0x1800141d9  jmp     loc_18001475D
0x1800141de  cmp     [rsi+18h], r15d
0x1800141e2  jnz     loc_18001475D
0x1800141e8  cmp     [rbx+21E4h], r15d
0x1800141ef  jnz     short loc_18001420E
0x1800141f1  mov     r8d, [rbx+2188h]
0x1800141f8  lea     rdx, aConfigurationI; "Configuration is not complete. State = "...
0x1800141ff  mov     ecx, 100000h
0x180014204  call    EventWrite0
0x180014209  jmp     loc_18001475D
0x18001420e  cmp     [rsi+0AE0h], r15d
0x180014215  jnz     short loc_180014237
0x180014217  lea     rdx, aBfeNotRunningS; "BFE not running. Skipping start."
0x18001421e  mov     ecx, 100000h
0x180014223  call    EventWriteError0
0x180014228  mov     dword ptr [rsi+0B34h], 12h
0x180014232  jmp     loc_18001475D
0x180014237  cmp     [rsi+4C18h], r15d
0x18001423e  jnz     short loc_180014260
0x180014240  lea     rdx, aDefaultBlockFi; "Default block filter not found. Skippin"...
0x180014247  mov     ecx, 100000h
0x18001424c  call    EventWriteError0
0x180014251  mov     dword ptr [rsi+0B34h], 13h
0x18001425b  jmp     loc_18001475D
0x180014260  cmp     [rbx+383Ah], r15b
0x180014267  jz      short loc_180014299
0x180014269  cmp     [rbx+21F9h], r15b
0x180014270  jnz     short loc_180014299
0x180014272  mov     r8d, [rbx+2188h]
0x180014279  lea     rdx, aInLowPowerMode_0; "In low power mode. Skipping start attem"...
0x180014280  mov     ecx, 100000h
0x180014285  call    EventWriteError0
0x18001428a  mov     dword ptr [rsi+0B34h], 15h
0x180014294  jmp     loc_18001475D
0x180014299  mov     r8d, [rbx+2188h]
0x1800142a0  test    r8d, r8d
0x1800142a3  jz      short loc_1800142ED
0x1800142a5  cmp     r8d, 1
0x1800142a9  jz      short loc_1800142C6
0x1800142ab  lea     rdx, aClientStateIsD_0; "Client state is %d. Does not need start"...
0x1800142b2  mov     ecx, 100000h
0x1800142b7  call    EventWrite0
0x1800142bc  add     rsp, 70h
0x1800142c0  pop     r15
0x1800142c2  pop     rsi
0x1800142c3  pop     rbx
0x1800142c4  retn
0x1800142c6  mov     edx, 2
0x1800142cb  mov     rcx, rbx
0x1800142ce  call    TeredoClientChangeStateAndLog
0x1800142d3  cmp     [rbx+21FAh], r15b
0x1800142da  jnz     loc_18001475D
0x1800142e0  mov     rcx, rbx
0x1800142e3  call    TeredoClientUpdateStateInNsi
0x1800142e8  jmp     loc_18001475D
0x1800142ed  mov     [rsp+88h+arg_8], rbp
0x1800142f5  mov     [rsp+88h+arg_10], rdi
0x1800142fd  mov     [rsp+88h+var_20], r12
0x180014302  mov     [rsp+88h+var_28], r14
0x180014307  cmp     [rbx+3828h], r15d
0x18001430e  jz      short loc_18001432F
0x180014310  mov     r8d, [rbx+3820h]
0x180014317  lea     rdx, aTeredostartcli; "TeredoStartClient: resetting NumConsecu"...
0x18001431e  mov     ecx, 100000h
0x180014323  call    EventWrite0
0x180014328  mov     [rbx+3820h], r15d
0x18001432f  mov     eax, [rsi+0B34h]
0x180014335  mov     [rsi+0B38h], eax
0x18001433b  mov     eax, r15d
0x18001433e  cmp     [rsi+0AD0h], eax
0x180014344  mov     [rsi+0B34h], r15d
0x18001434b  setnz   al
0x18001434e  mov     [rsi+0B3Ch], r15d
0x180014355  inc     eax
0x180014357  mov     [rsi+0B30h], eax
0x18001435d  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x180014364  jz      short loc_180014386
0x180014366  mov     r8d, [rbx+2188h]
0x18001436d  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_STATE_CHANGE
0x180014374  mov     r9d, 8
0x18001437a  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180014381  call    McTemplateU0qq_EventWriteTransfer
0x180014386  mov     rax, [rbx+1EE0h]
0x18001438d  lea     rcx, aClient; "Client"
0x180014394  mov     r9d, [rbx+21F0h]
0x18001439b  lea     r8, aRelay; "Relay"
0x1800143a2  lea     rdx, aCurrentStatusW; "Current status: %ws Mode, Firewall enab"...
0x1800143a9  cmp     dword ptr [rax+0B30h], 1
0x1800143b0  mov     eax, [rbx+21ECh]
0x1800143b6  cmovnz  r8, rcx
0x1800143ba  mov     dword ptr [rsp+88h+var_68], eax
0x1800143be  mov     ecx, 100000h
0x1800143c3  call    EventWrite0
0x1800143c8  mov     [rsp+88h+var_38], r15d
0x1800143cd  lea     rax, [rsp+88h+arg_0]
0x1800143d5  mov     [rsp+88h+var_40], r15
0x1800143da  lea     rdx, NPI_MS_FL6T_MODULEID
0x1800143e1  mov     [rsp+88h+var_48], 8
0x1800143e9  mov     ebp, 1
0x1800143ee  mov     [rsp+88h+var_50], rax
0x1800143f3  xor     r9d, r9d
0x1800143f6  mov     [rsp+88h+var_58], r15d
0x1800143fb  xor     r8d, r8d
0x1800143fe  mov     [rsp+88h+var_60], r15
0x180014403  mov     ecx, ebp
0x180014405  mov     dword ptr [rsp+88h+var_68], r15d
0x18001440a  mov     dword ptr [rbx+2188h], 8
0x180014414  mov     [rbx+21E8h], r15d
0x18001441b  mov     [rbx+2AE4h], r15d
0x180014422  mov     dword ptr [rbx+2AE8h], 6
0x18001442c  call    cs:__imp_NsiGetAllParameters
0x180014433  nop     dword ptr [rax+rax+00h]
0x180014438  mov     r14d, eax
0x18001443b  test    eax, eax
0x18001443d  jnz     short loc_18001445F
0x18001443f  mov     r8d, dword ptr [rsp+88h+arg_0]
0x180014447  lea     rdx, aListeningappli; "ListeningApplications is %u"
0x18001444e  mov     ecx, 100000h
0x180014453  mov     [rbx+21ECh], r8d
0x18001445a  call    EventWrite0
0x18001445f  lea     rcx, [rbx+1418h]
0x180014466  call    TeredoStartIo
0x18001446b  mov     r8d, [rbx]
0x18001446e  lea     r12, aOnecoreuapNetN_27; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180014475  mov     r9, r12
0x180014478  mov     dword ptr [rsp+88h+var_68], 9C4h
0x180014480  lea     rdx, aTeredoreferenc_0; "TeredoReferenceClient: ++%d @ %ls:%u"
0x180014487  mov     ecx, 100000h
0x18001448c  call    EventWrite0
0x180014491  mov     edx, [rbx]
0x180014493  mov     eax, ebp
0x180014495  lock xadd [rbx+8], eax
0x18001449a  and     eax, 3Fh
0x18001449d  lea     rax, [rax+rax*4]
0x1800144a1  mov     [rbx+rax*8+10h], edx
0x1800144a5  mov     dword ptr [rbx+rax*8+20h], 9C4h
0x1800144ad  mov     [rbx+rax*8+18h], r12
0x1800144b2  mov     [rbx+rax*8+30h], r15d
0x1800144b7  mov     [rbx+rax*8+28h], r15
0x1800144bc  lock inc dword ptr [rbx]
0x1800144bf  lea     rcx, [rbx+1418h]
0x1800144c6  call    TeredoInitializeAddressComponents
0x1800144cb  cmp     [rbx+1E50h], r15d
0x1800144d2  jz      loc_1800146F0
0x1800144d8  lea     rdx, [rsi+1344h]
0x1800144df  lea     rcx, aPreviousAddres; "Previous address initialized to"
0x1800144e6  call    TeredoTraceAddress
0x1800144eb  mov     rax, [rsi+134Ch]
0x1800144f2  lea     rcx, [rbx+20C8h]
0x1800144f9  mov     [rbx+1EB6h], rax
0x180014500  call    TeredoStartDevice
0x180014505  mov     r14d, eax
0x180014508  test    eax, eax
0x18001450a  jz      short loc_180014536
0x18001450c  mov     r8d, eax
0x18001450f  lea     rdx, aFailedToStartT_2; "Failed to start Teredo client. Could no"...
0x180014516  mov     ecx, 100000h
0x18001451b  call    EventWriteError0
0x180014520  mov     dword ptr [rsi+0B34h], 5
0x18001452a  mov     [rsi+0B3Ch], r14d
0x180014531  jmp     loc_1800146F0
0x180014536  mov     ecx, 20h ; ' '; dwBytes
0x18001453b  call    MALLOC
0x180014540  mov     [rbx+2AC8h], rax
0x180014547  test    rax, rax
0x18001454a  jz      loc_1800146E0
0x180014550  cmp     dword ptr [rbx+21E0h], 8
0x180014557  mov     [rbx+3838h], r15b
0x18001455e  jnz     short loc_1800145AE
0x180014560  mov     rcx, [rbx+20E0h]
0x180014567  call    TeredoSetMediaStateToConnected
0x18001456c  mov     r14d, eax
0x18001456f  test    eax, eax
0x180014571  jz      short loc_1800145A7
0x180014573  mov     r8d, eax
0x180014576  lea     rdx, aFailedToStartT_1; "Failed to start Teredo client. Could no"...
0x18001457d  mov     ecx, 100000h
0x180014582  call    EventWriteError0
0x180014587  mov     dword ptr [rsi+0B34h], 5
0x180014591  mov     [rsi+0B3Ch], r14d
0x180014598  mov     dword ptr [rsi+4BC4h], 2
0x1800145a2  jmp     loc_1800146F0
0x1800145a7  mov     [rbx+3838h], bpl
0x1800145ae  mov     rdi, [rbx+2AC8h]
0x1800145b5  lea     r8, CallbackEnvironment; pcbe
0x1800145bc  mov     rdx, rbx; pv
0x1800145bf  lea     rcx, TeredoClientTimerCallback; pfnti
0x1800145c6  call    cs:__imp_CreateThreadpoolTimer
0x1800145cd  nop     dword ptr [rax+rax+00h]
0x1800145d2  mov     [rdi+10h], rax
0x1800145d6  test    rax, rax
0x1800145d9  jz      loc_1800146E0
0x1800145df  mov     r9, rax
0x1800145e2  lea     r8, aTeredoClientTi_1; "Teredo Client Timer"
0x1800145e9  lea     rdx, aSHasBeenCreate; "%s has been created: timer memory point"...
0x1800145f0  mov     ecx, 8000000h
0x1800145f5  call    EventWrite0
0x1800145fa  mov     rdx, [rdi+10h]
0x1800145fe  lea     rcx, aTeredoClientTi_1; "Teredo Client Timer"
0x180014605  mov     r9d, 7FFFFFFFh
0x18001460b  xor     r8d, r8d
0x18001460e  call    TpclSetTimer
0x180014613  test    eax, eax
0x180014615  jz      loc_1800146E0
0x18001461b  mov     r8d, [rbx]
0x18001461e  lea     rdx, aTeredoreferenc_0; "TeredoReferenceClient: ++%d @ %ls:%u"
0x180014625  mov     r9, r12
0x180014628  mov     dword ptr [rsp+88h+var_68], 0A18h
0x180014630  mov     ecx, 100000h
0x180014635  call    EventWrite0
0x18001463a  mov     ecx, [rbx]
0x18001463c  lock xadd [rbx+8], ebp
0x180014641  mov     eax, ebp
0x180014643  and     eax, 3Fh
0x180014646  lea     rax, [rax+rax*4]
0x18001464a  mov     [rbx+rax*8+10h], ecx
0x18001464e  mov     dword ptr [rbx+rax*8+20h], 0A18h
0x180014656  mov     [rbx+rax*8+18h], r12
0x18001465b  mov     [rbx+rax*8+30h], r15d
0x180014660  mov     [rbx+rax*8+28h], r15
0x180014665  lock inc dword ptr [rbx]
0x180014668  mov     rcx, rbx
0x18001466b  call    TeredoClientUpdateStateInNsi
0x180014670  xor     ecx, ecx
0x180014672  call    cs:__imp_InternalSetTeredoPort
0x180014679  nop     dword ptr [rax+rax+00h]
0x18001467e  test    eax, eax
0x180014680  jz      short loc_180014693
0x180014682  lea     rdx, aUnableToInitia; "Unable to initialize Teredo port state "...
0x180014689  mov     ecx, 100000h
0x18001468e  call    EventWriteError0
0x180014693  call    IsIphlpsvcExtConfigureTeredoClientPortPresent
0x180014698  test    al, al
0x18001469a  jz      loc_180014743
0x1800146a0  xor     ecx, ecx
0x1800146a2  call    cs:__imp_IphlpsvcExtConfigureTeredoClientPort
0x1800146a9  nop     dword ptr [rax+rax+00h]
0x1800146ae  test    eax, eax
0x1800146b0  jz      loc_180014743
0x1800146b6  movzx   ecx, word ptr [rbx+1E7Eh]; netshort
0x1800146bd  call    cs:__imp_ntohs
0x1800146c4  nop     dword ptr [rax+rax+00h]
0x1800146c9  movzx   r8d, ax
0x1800146cd  lea     rdx, aUnableToSetTer; "Unable to set Teredo port value (%d) in"...
0x1800146d4  mov     ecx, 100000h
0x1800146d9  call    EventWriteError0
0x1800146de  jmp     short loc_180014743
0x1800146e0  mov     dword ptr [rsi+0B3Ch], 8
0x1800146ea  mov     [rsi+0B34h], ebp
0x1800146f0  mov     eax, [rsi+0B34h]
0x1800146f6  test    eax, eax
0x1800146f8  jnz     short loc_180014709
0x1800146fa  mov     [rsi+0B34h], ebp
0x180014700  mov     [rsi+0B3Ch], r14d
0x180014707  jmp     short loc_18001470B
0x180014709  mov     ebp, eax
0x18001470b  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 1
0x180014712  jz      short loc_18001472A
0x180014714  mov     r8d, ebp
0x180014717  lea     rdx, EVENT_IPHLPSVC_ETW_TEREDO_CLIENT_START_FAILED
0x18001471e  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x180014725  call    McTemplateU0q_EventWriteTransfer
0x18001472a  lea     rdx, aFailedToWakeUp_1; "Failed to wake-up Teredo client. Hence,"...
0x180014731  mov     ecx, 100000h
0x180014736  call    EventWrite0
0x18001473b  mov     rcx, rbx
0x18001473e  call    TeredoStopClient
0x180014743  mov     r12, [rsp+88h+var_20]
0x180014748  mov     rdi, [rsp+88h+arg_10]
0x180014750  mov     rbp, [rsp+88h+arg_8]
0x180014758  mov     r14, [rsp+88h+var_28]
0x18001475d  add     rsp, 70h
0x180014761  pop     r15
0x180014763  pop     rsi
0x180014764  pop     rbx
0x180014765  retn
```
