# Start6to4InCompartment

- ea: `0x180051170`
- end: `0x180051443`
- name: `Start6to4InCompartment`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180051958`

## callees

- `0x180004ca0`
- `0x18000cea0`
- `0x18000d7c0`
- `0x1800190f0`
- `0x18001e6d0`
- `0x18001f6d8`
- `0x180022b40`
- `0x180024250`
- `0x18002dcc0`
- `0x18003fbd0`
- `0x180040fe0`
- `0x18004eb10`
- `0x18004f564`
- `0x18004f94c`
- `0x180051170`
- `0x180051860`
- `0x1800519b0`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18005129d`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18005129d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800512ee`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800512ee`

## string_xrefs

- `0x18005124f`: `Process6to4ConfigurationChange`
- `0x18005130e`: `Process6to4ConfigurationChange`
- `0x180051248`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180051307`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x1800512dd`: `Updating the link layer address has failed`
- `0x1800511ca`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180051277`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180051378`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180051425`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180051187`: `Entered Start6to4InCompartment, Compartment %d, 6to4 luid is %I64x`
- `0x1800511bd`: `Start6to4InCompartment`
- `0x18005126a`: `Start6to4InCompartment`
- `0x18005136b`: `Start6to4InCompartment`
- `0x180051417`: `Start6to4InCompartment`
- `0x180051437`: `Leaving: 6to4: Start6to4InCompartment`
- `0x180051327`: `Failed to start 6to4 in compartment`
- `0x180051384`: `Leaving: 6to4: Start6to4InCompartment ended in failure`

## pseudocode

```c
__int64 __fastcall Start6to4InCompartment(__int64 a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int started; // eax
  int i; // edi
  __int64 v7; // rcx
  const wchar_t *v8; // rdx
  _DWORD v9[4]; // [rsp+20h] [rbp-10h] BYREF
  char v10; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+28h] BYREF
  NET_LUID InterfaceLuid; // [rsp+60h] [rbp+30h] BYREF

  v1 = *(_QWORD *)(a1 + 2624);
  v2 = *(unsigned int *)(a1 + 16);
  v11 = 0;
  InterfaceLuid.Value = 0;
  v10 = 0;
  EventWrite0(0x1000000, L"Entered Start6to4InCompartment, Compartment %d, 6to4 luid is %I64x", v2, v1);
  if ( (unsigned int)GetAndTraceLock(
                       "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
                       "Start6to4InCompartment",
                       3336,
                       g_6to4Lock)
    && !dword_1800C9750 )
  {
    if ( !*(_DWORD *)(a1 + 2724) )
    {
      started = StartTunnelInterface(11, &SIXTOFOUR_INTERFACE_GUID);
      v11 = started;
      if ( started )
      {
        EventWrite0(0x1000000, L"Failed to start interface, retry again. Error: 0x%x", started);
        if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x20) != 0 )
          McTemplateU0q_EventWriteTransfer(
            MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
            EVENT_IPHLPSVC_ETW_6TO4_START_FAILED,
            v11);
        if ( !(unsigned int)ReferenceServiceEx(
                              "Process6to4ConfigurationChange",
                              L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
                              3363) )
          return ReleaseAndTraceLock(
                   "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
                   "Start6to4InCompartment",
                   3364,
                   g_6to4Lock);
        goto LABEL_14;
      }
      *(_DWORD *)(a1 + 2724) = 1;
      ConvertInterfaceGuidToLuid(&SIXTOFOUR_INTERFACE_GUID, &InterfaceLuid);
    }
    for ( i = 0; i < 10; ++i )
    {
      v9[0] = *(_DWORD *)(a1 + 16);
      v9[1] = 0;
      v9[2] = 2130706433;
      if ( (unsigned int)UpdateLinkAddress(&InterfaceLuid, v9, 12) )
      {
        *(NET_LUID *)(a1 + 2624) = InterfaceLuid;
        *(_QWORD *)(a1 + 2632) = 0;
        *(_DWORD *)(a1 + 2640) = 0;
        EventWrite0(0x1000000, L"Started with LUID %I64x", *(_QWORD *)(a1 + 2624));
        if ( (unsigned int)Configure6to4LinkLayerAddress(a1) )
          ForEachAddressInCompartment(a1, Configure6to4AddressInCompartment, 0, &v11);
        Update6to4Routes(a1);
        UpdateGlobalRoutingState(a1);
        UpdateGlobalResolutionState(a1, 0);
        *(_DWORD *)(a1 + 2720) = 2;
        ReleaseAndTraceLock(
          "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
          "Start6to4InCompartment",
          3442,
          g_6to4Lock);
        v8 = L"Leaving: 6to4: Start6to4InCompartment";
        return EventWriteLeaveEx(0x20000, v8);
      }
      EventWriteError0(0x1000000, L"Updating the link layer address has failed");
      Sleep(0x32u);
    }
    if ( !(unsigned int)ReferenceServiceEx(
                          "Process6to4ConfigurationChange",
                          L"onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
                          3406) )
      goto LABEL_15;
LABEL_14:
    Process6to4ConfigurationChange(0, 0);
  }
LABEL_15:
  EventWrite0(0x1000000, L"Failed to start 6to4 in compartment");
  if ( *(_DWORD *)(a1 + 2724) )
  {
    v11 = Disable6To4Interface(v7, &InterfaceLuid, 0, &v10);
    if ( v11 || !v10 )
      *(_QWORD *)(a1 + 2624) = 0;
  }
  ReleaseAndTraceLock(
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\6to4svc.c",
    "Start6to4InCompartment",
    3475,
    g_6to4Lock);
  v8 = L"Leaving: 6to4: Start6to4InCompartment ended in failure";
  return EventWriteLeaveEx(0x20000, v8);
}

```

## disassembly

```asm
0x180051170  mov     [rsp-18h+arg_18], rbx
0x180051175  push    rbp
0x180051176  push    rdi
0x180051177  push    r14
0x180051179  mov     rbp, rsp
0x18005117c  sub     rsp, 30h
0x180051180  mov     r9, [rcx+0A40h]
0x180051187  lea     rdx, aEnteredStart6t; "Entered Start6to4InCompartment, Compart"...
0x18005118e  mov     r8d, [rcx+10h]
0x180051192  mov     rbx, rcx
0x180051195  mov     r14d, 1000000h
0x18005119b  mov     [rbp+arg_8], 0
0x1800511a2  mov     ecx, r14d
0x1800511a5  mov     qword ptr [rbp+InterfaceLuid], 0
0x1800511ad  mov     [rbp+arg_0], 0
0x1800511b1  call    EventWrite0
0x1800511b6  mov     r9, cs:g_6to4Lock
0x1800511bd  lea     rdx, aStart6to4incom; "Start6to4InCompartment"
0x1800511c4  mov     r8d, 0D08h
0x1800511ca  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800511d1  call    GetAndTraceLock
0x1800511d6  test    eax, eax
0x1800511d8  jz      loc_180051327
0x1800511de  cmp     cs:dword_1800C9750, 0
0x1800511e5  jnz     loc_180051327
0x1800511eb  cmp     dword ptr [rbx+0AA4h], 0
0x1800511f2  jnz     loc_1800512A9
0x1800511f8  lea     rdx, SIXTOFOUR_INTERFACE_GUID
0x1800511ff  mov     ecx, 0Bh
0x180051204  call    StartTunnelInterface
0x180051209  mov     [rbp+arg_8], eax
0x18005120c  test    eax, eax
0x18005120e  jz      short loc_180051288
0x180051210  mov     r8d, eax
0x180051213  lea     rdx, aFailedToStartI; "Failed to start interface, retry again."...
0x18005121a  mov     ecx, r14d
0x18005121d  call    EventWrite0
0x180051222  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 20h
0x180051229  jz      short loc_180051242
0x18005122b  mov     r8d, [rbp+arg_8]
0x18005122f  lea     rdx, EVENT_IPHLPSVC_ETW_6TO4_START_FAILED
0x180051236  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005123d  call    McTemplateU0q_EventWriteTransfer
0x180051242  mov     r8d, 0D23h
0x180051248  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005124f  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x180051256  call    ReferenceServiceEx
0x18005125b  test    eax, eax
0x18005125d  jnz     loc_18005131E
0x180051263  mov     r9, cs:g_6to4Lock
0x18005126a  lea     rdx, aStart6to4incom; "Start6to4InCompartment"
0x180051271  mov     r8d, 0D24h
0x180051277  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005127e  call    ReleaseAndTraceLock
0x180051283  jmp     loc_180051395
0x180051288  lea     rdx, [rbp+InterfaceLuid]; InterfaceLuid
0x18005128c  mov     dword ptr [rbx+0AA4h], 1
0x180051296  lea     rcx, SIXTOFOUR_INTERFACE_GUID; InterfaceGuid
0x18005129d  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1800512a4  nop     dword ptr [rax+rax+00h]
0x1800512a9  xor     edi, edi
0x1800512ab  mov     eax, [rbx+10h]
0x1800512ae  lea     rdx, [rbp+var_10]
0x1800512b2  mov     r8d, 0Ch
0x1800512b8  mov     [rbp+var_10], eax
0x1800512bb  lea     rcx, [rbp+InterfaceLuid]
0x1800512bf  mov     [rbp+var_C], 0
0x1800512c6  mov     [rbp+var_8], 7F000001h
0x1800512cd  call    UpdateLinkAddress
0x1800512d2  mov     ecx, r14d
0x1800512d5  test    eax, eax
0x1800512d7  jnz     loc_1800513A4
0x1800512dd  lea     rdx, aUpdatingTheLin; "Updating the link layer address has fai"...
0x1800512e4  call    EventWriteError0
0x1800512e9  mov     ecx, 32h ; '2'; dwMilliseconds
0x1800512ee  call    cs:__imp_Sleep
0x1800512f5  nop     dword ptr [rax+rax+00h]
0x1800512fa  inc     edi
0x1800512fc  cmp     edi, 0Ah
0x1800512ff  jl      short loc_1800512AB
0x180051301  mov     r8d, 0D4Eh
0x180051307  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005130e  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x180051315  call    ReferenceServiceEx
0x18005131a  test    eax, eax
0x18005131c  jz      short loc_180051327
0x18005131e  xor     edx, edx; Context
0x180051320  xor     ecx, ecx; Instance
0x180051322  call    Process6to4ConfigurationChange
0x180051327  lea     rdx, aFailedToStart6; "Failed to start 6to4 in compartment"
0x18005132e  mov     ecx, r14d
0x180051331  call    EventWrite0
0x180051336  cmp     dword ptr [rbx+0AA4h], 0
0x18005133d  jz      short loc_180051364
0x18005133f  lea     r9, [rbp+arg_0]
0x180051343  xor     r8d, r8d
0x180051346  lea     rdx, [rbp+InterfaceLuid]
0x18005134a  call    Disable6To4Interface
0x18005134f  mov     [rbp+arg_8], eax
0x180051352  test    eax, eax
0x180051354  jnz     short loc_18005135B
0x180051356  cmp     [rbp+arg_0], al
0x180051359  jnz     short loc_180051364
0x18005135b  xor     eax, eax
0x18005135d  mov     [rbx+0A40h], rax
0x180051364  mov     r9, cs:g_6to4Lock
0x18005136b  lea     rdx, aStart6to4incom; "Start6to4InCompartment"
0x180051372  mov     r8d, 0D93h
0x180051378  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005137f  call    ReleaseAndTraceLock
0x180051384  lea     rdx, aLeaving6to4Sta_0; "Leaving: 6to4: Start6to4InCompartment e"...
0x18005138b  mov     ecx, 20000h
0x180051390  call    EventWriteLeaveEx
0x180051395  mov     rbx, [rsp+30h+arg_18]
0x18005139a  add     rsp, 30h
0x18005139e  pop     r14
0x1800513a0  pop     rdi
0x1800513a1  pop     rbp
0x1800513a2  retn
0x1800513a4  mov     rax, qword ptr [rbp+InterfaceLuid]
0x1800513a8  lea     rdx, aStartedWithLui; "Started with LUID %I64x"
0x1800513af  mov     [rbx+0A40h], rax
0x1800513b6  xor     eax, eax
0x1800513b8  mov     [rbx+0A48h], rax
0x1800513bf  mov     [rbx+0A50h], eax
0x1800513c5  mov     r8, [rbx+0A40h]
0x1800513cc  call    EventWrite0
0x1800513d1  mov     rcx, rbx
0x1800513d4  call    Configure6to4LinkLayerAddress
0x1800513d9  test    eax, eax
0x1800513db  jz      short loc_1800513F3
0x1800513dd  lea     r9, [rbp+arg_8]
0x1800513e1  xor     r8d, r8d
0x1800513e4  lea     rdx, Configure6to4AddressInCompartment
0x1800513eb  mov     rcx, rbx
0x1800513ee  call    ForEachAddressInCompartment
0x1800513f3  mov     rcx, rbx
0x1800513f6  call    Update6to4Routes
0x1800513fb  mov     rcx, rbx
0x1800513fe  call    UpdateGlobalRoutingState
0x180051403  xor     edx, edx
0x180051405  mov     rcx, rbx
0x180051408  call    UpdateGlobalResolutionState
0x18005140d  mov     dword ptr [rbx+0AA0h], 2
0x180051417  lea     rdx, aStart6to4incom; "Start6to4InCompartment"
0x18005141e  mov     r9, cs:g_6to4Lock
0x180051425  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005142c  mov     r8d, 0D72h
0x180051432  call    ReleaseAndTraceLock
0x180051437  lea     rdx, aLeaving6to4Sta; "Leaving: 6to4: Start6to4InCompartment"
0x18005143e  jmp     loc_18005138B
```
