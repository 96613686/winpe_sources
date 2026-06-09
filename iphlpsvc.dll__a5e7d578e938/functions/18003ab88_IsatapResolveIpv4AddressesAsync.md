# IsatapResolveIpv4AddressesAsync

- ea: `0x18003ab88`
- end: `0x18003ad45`
- name: `IsatapResolveIpv4AddressesAsync`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005a8a8`

## callees

- `0x180009010`
- `0x18000d7c0`
- `0x1800159d4`
- `0x180024250`
- `0x18003ab88`
- `0x180040a14`
- `0x18004c188`
- `0x18005af44`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003ac22`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003accd`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003ac22`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003accd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003ac00`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003ac00`
- `WS2_32!GetAddrInfoExW` at `0x18003acb7`
- `WS2_32!GetAddrInfoExW` at `0x18003acb7`

## string_xrefs

- `0x18003ac38`: `SetCurrentThreadCompartmentId(%d) returned error %d`
- `0x18003acf2`: `IsatapResolveIpv4AddressesAsync.GetAddrInfoExW(%ls) returned error %d in compartment %d`

## pseudocode

```c
__int64 __fastcall IsatapResolveIpv4AddressesAsync(__int64 a1, const WCHAR *a2)
{
  __int64 v2; // rsi
  NET_IF_COMPARTMENT_ID v6; // ecx
  unsigned int v7; // eax
  unsigned int AddrInfo; // edi
  ADDRINFOEXW *hints; // [rsp+20h] [rbp-A8h]
  ADDRINFOEXW v10; // [rsp+50h] [rbp-78h] BYREF

  v2 = *(_QWORD *)(a1 + 2640);
  memset_0(&v10, 0, sizeof(v10));
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Entered: IsatapResolveIpv4AddressesAsync");
  if ( !(unsigned __int8)RoReferenceEx(a1 + 12) )
    return 0;
  IsatapStopUpdateRouterAddressAsync(a1);
  ResetEvent(*(HANDLE *)(a1 + 4784));
  ++*(_QWORD *)(a1 + 4840);
  *(_BYTE *)(a1 + 4776) = 1;
  v6 = *(_DWORD *)(v2 + 16);
  if ( v6 == 1 || (v7 = SetCurrentThreadCompartmentId(v6), (AddrInfo = v7) == 0) )
  {
    memset_0(&v10, 0, sizeof(v10));
    v10.ai_family = 2;
    AddrInfo = GetAddrInfoExW(
                 a2,
                 0,
                 0,
                 0,
                 &v10,
                 (PADDRINFOEXW *)(a1 + 4792),
                 0,
                 (LPOVERLAPPED)(a1 + 4800),
                 IsatapUpdateRouterAddressAsyncCallback,
                 (LPHANDLE)(a1 + 4832));
    if ( *(_DWORD *)(v2 + 16) != 1 )
      SetCurrentThreadCompartmentId(0);
    if ( AddrInfo == 997 )
    {
      AddrInfo = 0;
    }
    else
    {
      IsatapUpdateRouterAddressAsyncCallbackUnderGlobalIsatapLock(AddrInfo, a1);
      if ( AddrInfo )
      {
        LODWORD(hints) = *(_DWORD *)(v2 + 16);
        EventWrite0(
          0x2000000,
          L"IsatapResolveIpv4AddressesAsync.GetAddrInfoExW(%ls) returned error %d in compartment %d",
          a2,
          AddrInfo,
          hints);
      }
    }
    EventWrite0(0x2000000, L"IsatapResolveIpv4AddressesAsync returned error %d", AddrInfo);
    EventWriteLeaveEx(0x20000, L"Leaving: IsatapResolveIpv4AddressesAsync");
  }
  else
  {
    EventWrite0(0x2000000, L"SetCurrentThreadCompartmentId(%d) returned error %d", *(unsigned int *)(v2 + 16), v7);
  }
  return AddrInfo;
}

```

## disassembly

```asm
0x18003ab88  push    rbx
0x18003ab8a  push    rbp
0x18003ab8b  push    rsi
0x18003ab8c  push    rdi
0x18003ab8d  sub     rsp, 0A8h
0x18003ab94  mov     rsi, [rcx+0A50h]
0x18003ab9b  mov     rbp, rdx
0x18003ab9e  xor     edx, edx; Val
0x18003aba0  mov     rbx, rcx
0x18003aba3  lea     rcx, [rsp+0C8h+var_78]; void *
0x18003aba8  lea     r8d, [rdx+48h]; Size
0x18003abac  call    memset_0
0x18003abb1  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18003abb8  jz      short loc_18003ABDD
0x18003abba  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x18003abc1  jge     short loc_18003ABDD
0x18003abc3  lea     r8, aEnteredIsatapr; "Entered: IsatapResolveIpv4AddressesAsyn"...
0x18003abca  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18003abd1  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18003abd8  call    McTemplateU0z_EventWriteTransfer
0x18003abdd  lea     rcx, [rbx+0Ch]
0x18003abe1  call    RoReferenceEx
0x18003abe6  test    al, al
0x18003abe8  jnz     short loc_18003ABF1
0x18003abea  xor     eax, eax
0x18003abec  jmp     loc_18003AD38
0x18003abf1  mov     rcx, rbx
0x18003abf4  call    IsatapStopUpdateRouterAddressAsync
0x18003abf9  mov     rcx, [rbx+12B0h]; hEvent
0x18003ac00  call    cs:__imp_ResetEvent
0x18003ac07  nop     dword ptr [rax+rax+00h]
0x18003ac0c  inc     qword ptr [rbx+12E8h]
0x18003ac13  mov     byte ptr [rbx+12A8h], 1
0x18003ac1a  mov     ecx, [rsi+10h]; CompartmentId
0x18003ac1d  cmp     ecx, 1
0x18003ac20  jz      short loc_18003AC51
0x18003ac22  call    cs:__imp_SetCurrentThreadCompartmentId
0x18003ac29  nop     dword ptr [rax+rax+00h]
0x18003ac2e  mov     edi, eax
0x18003ac30  test    eax, eax
0x18003ac32  jz      short loc_18003AC51
0x18003ac34  mov     r8d, [rsi+10h]
0x18003ac38  lea     rdx, aSetcurrentthre; "SetCurrentThreadCompartmentId(%d) retur"...
0x18003ac3f  mov     r9d, eax
0x18003ac42  mov     ecx, 2000000h
0x18003ac47  call    EventWrite0
0x18003ac4c  jmp     loc_18003AD36
0x18003ac51  xor     edx, edx; Val
0x18003ac53  lea     rcx, [rsp+0C8h+var_78]; void *
0x18003ac58  lea     r8d, [rdx+48h]; Size
0x18003ac5c  call    memset_0
0x18003ac61  lea     rax, [rbx+12E0h]
0x18003ac68  mov     [rsp+0C8h+var_78.ai_family], 2
0x18003ac70  mov     [rsp+0C8h+lpHandle], rax; lpHandle
0x18003ac75  lea     rcx, [rbx+12C0h]
0x18003ac7c  lea     rax, IsatapUpdateRouterAddressAsyncCallback
0x18003ac83  xor     r9d, r9d; lpNspId
0x18003ac86  mov     [rsp+0C8h+lpCompletionRoutine], rax; lpCompletionRoutine
0x18003ac8b  lea     rdx, [rbx+12B8h]
0x18003ac92  mov     [rsp+0C8h+lpOverlapped], rcx; lpOverlapped
0x18003ac97  lea     rax, [rsp+0C8h+var_78]
0x18003ac9c  mov     [rsp+0C8h+timeout], 0; timeout
0x18003aca5  xor     r8d, r8d; dwNameSpace
0x18003aca8  mov     [rsp+0C8h+ppResult], rdx; ppResult
0x18003acad  mov     rcx, rbp; pName
0x18003acb0  xor     edx, edx; pServiceName
0x18003acb2  mov     [rsp+0C8h+hints], rax; hints
0x18003acb7  call    cs:__imp_GetAddrInfoExW
0x18003acbe  nop     dword ptr [rax+rax+00h]
0x18003acc3  cmp     dword ptr [rsi+10h], 1
0x18003acc7  mov     edi, eax
0x18003acc9  jz      short loc_18003ACD9
0x18003accb  xor     ecx, ecx; CompartmentId
0x18003accd  call    cs:__imp_SetCurrentThreadCompartmentId
0x18003acd4  nop     dword ptr [rax+rax+00h]
0x18003acd9  cmp     edi, 3E5h
0x18003acdf  jz      short loc_18003AD0F
0x18003ace1  mov     rdx, rbx
0x18003ace4  mov     ecx, edi
0x18003ace6  call    IsatapUpdateRouterAddressAsyncCallbackUnderGlobalIsatapLock
0x18003aceb  test    edi, edi
0x18003aced  jz      short loc_18003AD11
0x18003acef  mov     eax, [rsi+10h]
0x18003acf2  lea     rdx, aIsatapresolvei_0; "IsatapResolveIpv4AddressesAsync.GetAddr"...
0x18003acf9  mov     r9d, edi
0x18003acfc  mov     dword ptr [rsp+0C8h+hints], eax
0x18003ad00  mov     r8, rbp
0x18003ad03  mov     ecx, 2000000h
0x18003ad08  call    EventWrite0
0x18003ad0d  jmp     short loc_18003AD11
0x18003ad0f  xor     edi, edi
0x18003ad11  mov     r8d, edi
0x18003ad14  lea     rdx, aIsatapresolvei; "IsatapResolveIpv4AddressesAsync returne"...
0x18003ad1b  mov     ecx, 2000000h
0x18003ad20  call    EventWrite0
0x18003ad25  lea     rdx, aLeavingIsatapr; "Leaving: IsatapResolveIpv4AddressesAsyn"...
0x18003ad2c  mov     ecx, 20000h
0x18003ad31  call    EventWriteLeaveEx
0x18003ad36  mov     eax, edi
0x18003ad38  add     rsp, 0A8h
0x18003ad3f  pop     rdi
0x18003ad40  pop     rsi
0x18003ad41  pop     rbp
0x18003ad42  pop     rbx
0x18003ad43  retn
```
