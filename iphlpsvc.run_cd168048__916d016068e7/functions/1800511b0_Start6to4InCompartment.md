# Start6to4InCompartment

- ea: `0x1800511b0`
- end: `0x180051483`
- name: `Start6to4InCompartment`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180051998`

## callees

- `0x180004c90`
- `0x18000ce90`
- `0x18000d7b0`
- `0x1800190e0`
- `0x18001e6c0`
- `0x18001f6c8`
- `0x180022b30`
- `0x180024240`
- `0x18002dcb0`
- `0x18003fc10`
- `0x180041020`
- `0x18004eb50`
- `0x18004f5a4`
- `0x18004f98c`
- `0x1800511b0`
- `0x1800518a0`
- `0x1800519f0`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800512dd`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800512dd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005132e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005132e`

## string_xrefs

- `0x18005128f`: `Process6to4ConfigurationChange`
- `0x18005134e`: `Process6to4ConfigurationChange`
- `0x180051288`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180051347`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x18005131d`: `Updating the link layer address has failed`
- `0x18005120a`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x1800512b7`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x1800513b8`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x180051465`: `onecoreuap\net\netio\iphlpsvc\service\6to4svc.c`
- `0x1800511c7`: `Entered Start6to4InCompartment, Compartment %d, 6to4 luid is %I64x`
- `0x1800511fd`: `Start6to4InCompartment`
- `0x1800512aa`: `Start6to4InCompartment`
- `0x1800513ab`: `Start6to4InCompartment`
- `0x180051457`: `Start6to4InCompartment`
- `0x180051477`: `Leaving: 6to4: Start6to4InCompartment`
- `0x180051367`: `Failed to start 6to4 in compartment`
- `0x1800513c4`: `Leaving: 6to4: Start6to4InCompartment ended in failure`

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
0x1800511b0  mov     [rsp-18h+arg_18], rbx
0x1800511b5  push    rbp
0x1800511b6  push    rdi
0x1800511b7  push    r14
0x1800511b9  mov     rbp, rsp
0x1800511bc  sub     rsp, 30h
0x1800511c0  mov     r9, [rcx+0A40h]
0x1800511c7  lea     rdx, aEnteredStart6t; "Entered Start6to4InCompartment, Compart"...
0x1800511ce  mov     r8d, [rcx+10h]
0x1800511d2  mov     rbx, rcx
0x1800511d5  mov     r14d, 1000000h
0x1800511db  mov     [rbp+arg_8], 0
0x1800511e2  mov     ecx, r14d
0x1800511e5  mov     qword ptr [rbp+InterfaceLuid], 0
0x1800511ed  mov     [rbp+arg_0], 0
0x1800511f1  call    EventWrite0
0x1800511f6  mov     r9, cs:g_6to4Lock
0x1800511fd  lea     rdx, aStart6to4incom; "Start6to4InCompartment"
0x180051204  mov     r8d, 0D08h
0x18005120a  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180051211  call    GetAndTraceLock
0x180051216  test    eax, eax
0x180051218  jz      loc_180051367
0x18005121e  cmp     cs:dword_1800C9750, 0
0x180051225  jnz     loc_180051367
0x18005122b  cmp     dword ptr [rbx+0AA4h], 0
0x180051232  jnz     loc_1800512E9
0x180051238  lea     rdx, SIXTOFOUR_INTERFACE_GUID
0x18005123f  mov     ecx, 0Bh
0x180051244  call    StartTunnelInterface
0x180051249  mov     [rbp+arg_8], eax
0x18005124c  test    eax, eax
0x18005124e  jz      short loc_1800512C8
0x180051250  mov     r8d, eax
0x180051253  lea     rdx, aFailedToStartI; "Failed to start interface, retry again."...
0x18005125a  mov     ecx, r14d
0x18005125d  call    EventWrite0
0x180051262  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 20h
0x180051269  jz      short loc_180051282
0x18005126b  mov     r8d, [rbp+arg_8]
0x18005126f  lea     rdx, EVENT_IPHLPSVC_ETW_6TO4_START_FAILED
0x180051276  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18005127d  call    McTemplateU0q_EventWriteTransfer
0x180051282  mov     r8d, 0D23h
0x180051288  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005128f  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x180051296  call    ReferenceServiceEx
0x18005129b  test    eax, eax
0x18005129d  jnz     loc_18005135E
0x1800512a3  mov     r9, cs:g_6to4Lock
0x1800512aa  lea     rdx, aStart6to4incom; "Start6to4InCompartment"
0x1800512b1  mov     r8d, 0D24h
0x1800512b7  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800512be  call    ReleaseAndTraceLock
0x1800512c3  jmp     loc_1800513D5
0x1800512c8  lea     rdx, [rbp+InterfaceLuid]; InterfaceLuid
0x1800512cc  mov     dword ptr [rbx+0AA4h], 1
0x1800512d6  lea     rcx, SIXTOFOUR_INTERFACE_GUID; InterfaceGuid
0x1800512dd  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1800512e4  nop     dword ptr [rax+rax+00h]
0x1800512e9  xor     edi, edi
0x1800512eb  mov     eax, [rbx+10h]
0x1800512ee  lea     rdx, [rbp+var_10]
0x1800512f2  mov     r8d, 0Ch
0x1800512f8  mov     [rbp+var_10], eax
0x1800512fb  lea     rcx, [rbp+InterfaceLuid]
0x1800512ff  mov     [rbp+var_C], 0
0x180051306  mov     [rbp+var_8], 7F000001h
0x18005130d  call    UpdateLinkAddress
0x180051312  mov     ecx, r14d
0x180051315  test    eax, eax
0x180051317  jnz     loc_1800513E4
0x18005131d  lea     rdx, aUpdatingTheLin; "Updating the link layer address has fai"...
0x180051324  call    EventWriteError0
0x180051329  mov     ecx, 32h ; '2'; dwMilliseconds
0x18005132e  call    cs:__imp_Sleep
0x180051335  nop     dword ptr [rax+rax+00h]
0x18005133a  inc     edi
0x18005133c  cmp     edi, 0Ah
0x18005133f  jl      short loc_1800512EB
0x180051341  mov     r8d, 0D4Eh
0x180051347  lea     rdx, aOnecoreuapNetN_23; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005134e  lea     rcx, aProcess6to4con; "Process6to4ConfigurationChange"
0x180051355  call    ReferenceServiceEx
0x18005135a  test    eax, eax
0x18005135c  jz      short loc_180051367
0x18005135e  xor     edx, edx; Context
0x180051360  xor     ecx, ecx; Instance
0x180051362  call    Process6to4ConfigurationChange
0x180051367  lea     rdx, aFailedToStart6; "Failed to start 6to4 in compartment"
0x18005136e  mov     ecx, r14d
0x180051371  call    EventWrite0
0x180051376  cmp     dword ptr [rbx+0AA4h], 0
0x18005137d  jz      short loc_1800513A4
0x18005137f  lea     r9, [rbp+arg_0]
0x180051383  xor     r8d, r8d
0x180051386  lea     rdx, [rbp+InterfaceLuid]
0x18005138a  call    Disable6To4Interface
0x18005138f  mov     [rbp+arg_8], eax
0x180051392  test    eax, eax
0x180051394  jnz     short loc_18005139B
0x180051396  cmp     [rbp+arg_0], al
0x180051399  jnz     short loc_1800513A4
0x18005139b  xor     eax, eax
0x18005139d  mov     [rbx+0A40h], rax
0x1800513a4  mov     r9, cs:g_6to4Lock
0x1800513ab  lea     rdx, aStart6to4incom; "Start6to4InCompartment"
0x1800513b2  mov     r8d, 0D93h
0x1800513b8  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800513bf  call    ReleaseAndTraceLock
0x1800513c4  lea     rdx, aLeaving6to4Sta_0; "Leaving: 6to4: Start6to4InCompartment e"...
0x1800513cb  mov     ecx, 20000h
0x1800513d0  call    EventWriteLeaveEx
0x1800513d5  mov     rbx, [rsp+30h+arg_18]
0x1800513da  add     rsp, 30h
0x1800513de  pop     r14
0x1800513e0  pop     rdi
0x1800513e1  pop     rbp
0x1800513e2  retn
0x1800513e4  mov     rax, qword ptr [rbp+InterfaceLuid]
0x1800513e8  lea     rdx, aStartedWithLui; "Started with LUID %I64x"
0x1800513ef  mov     [rbx+0A40h], rax
0x1800513f6  xor     eax, eax
0x1800513f8  mov     [rbx+0A48h], rax
0x1800513ff  mov     [rbx+0A50h], eax
0x180051405  mov     r8, [rbx+0A40h]
0x18005140c  call    EventWrite0
0x180051411  mov     rcx, rbx
0x180051414  call    Configure6to4LinkLayerAddress
0x180051419  test    eax, eax
0x18005141b  jz      short loc_180051433
0x18005141d  lea     r9, [rbp+arg_8]
0x180051421  xor     r8d, r8d
0x180051424  lea     rdx, Configure6to4AddressInCompartment
0x18005142b  mov     rcx, rbx
0x18005142e  call    ForEachAddressInCompartment
0x180051433  mov     rcx, rbx
0x180051436  call    Update6to4Routes
0x18005143b  mov     rcx, rbx
0x18005143e  call    UpdateGlobalRoutingState
0x180051443  xor     edx, edx
0x180051445  mov     rcx, rbx
0x180051448  call    UpdateGlobalResolutionState
0x18005144d  mov     dword ptr [rbx+0AA0h], 2
0x180051457  lea     rdx, aStart6to4incom; "Start6to4InCompartment"
0x18005145e  mov     r9, cs:g_6to4Lock
0x180051465  lea     rcx, aOnecoreuapNetN_37; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005146c  mov     r8d, 0D72h
0x180051472  call    ReleaseAndTraceLock
0x180051477  lea     rdx, aLeaving6to4Sta; "Leaving: 6to4: Start6to4InCompartment"
0x18005147e  jmp     loc_1800513CB
```
