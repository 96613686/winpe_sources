# IsatapResolveIpv4AddressesAsync

- ea: `0x18003ab78`
- end: `0x18003ad35`
- name: `IsatapResolveIpv4AddressesAsync`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005a888`

## callees

- `0x180009000`
- `0x18000d7b0`
- `0x1800159c4`
- `0x180024240`
- `0x18003ab78`
- `0x180040a54`
- `0x18004c1c8`
- `0x18005af24`

## import_xrefs

- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003ac12`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003acbd`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003ac12`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18003acbd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003abf0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003abf0`
- `WS2_32!GetAddrInfoExW` at `0x18003aca7`
- `WS2_32!GetAddrInfoExW` at `0x18003aca7`

## string_xrefs

- `0x18003ac28`: `SetCurrentThreadCompartmentId(%d) returned error %d`
- `0x18003ace2`: `IsatapResolveIpv4AddressesAsync.GetAddrInfoExW(%ls) returned error %d in compartment %d`

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
0x18003ab78  push    rbx
0x18003ab7a  push    rbp
0x18003ab7b  push    rsi
0x18003ab7c  push    rdi
0x18003ab7d  sub     rsp, 0A8h
0x18003ab84  mov     rsi, [rcx+0A50h]
0x18003ab8b  mov     rbp, rdx
0x18003ab8e  xor     edx, edx; Val
0x18003ab90  mov     rbx, rcx
0x18003ab93  lea     rcx, [rsp+0C8h+var_78]; void *
0x18003ab98  lea     r8d, [rdx+48h]; Size
0x18003ab9c  call    memset_0
0x18003aba1  cmp     cs:IpHlpSvcEtwEnabled, 0
0x18003aba8  jz      short loc_18003ABCD
0x18003abaa  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, 0
0x18003abb1  jge     short loc_18003ABCD
0x18003abb3  lea     r8, aEnteredIsatapr; "Entered: IsatapResolveIpv4AddressesAsyn"...
0x18003abba  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18003abc1  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18003abc8  call    McTemplateU0z_EventWriteTransfer
0x18003abcd  lea     rcx, [rbx+0Ch]
0x18003abd1  call    RoReferenceEx
0x18003abd6  test    al, al
0x18003abd8  jnz     short loc_18003ABE1
0x18003abda  xor     eax, eax
0x18003abdc  jmp     loc_18003AD28
0x18003abe1  mov     rcx, rbx
0x18003abe4  call    IsatapStopUpdateRouterAddressAsync
0x18003abe9  mov     rcx, [rbx+12B0h]; hEvent
0x18003abf0  call    cs:__imp_ResetEvent
0x18003abf7  nop     dword ptr [rax+rax+00h]
0x18003abfc  inc     qword ptr [rbx+12E8h]
0x18003ac03  mov     byte ptr [rbx+12A8h], 1
0x18003ac0a  mov     ecx, [rsi+10h]; CompartmentId
0x18003ac0d  cmp     ecx, 1
0x18003ac10  jz      short loc_18003AC41
0x18003ac12  call    cs:__imp_SetCurrentThreadCompartmentId
0x18003ac19  nop     dword ptr [rax+rax+00h]
0x18003ac1e  mov     edi, eax
0x18003ac20  test    eax, eax
0x18003ac22  jz      short loc_18003AC41
0x18003ac24  mov     r8d, [rsi+10h]
0x18003ac28  lea     rdx, aSetcurrentthre; "SetCurrentThreadCompartmentId(%d) retur"...
0x18003ac2f  mov     r9d, eax
0x18003ac32  mov     ecx, 2000000h
0x18003ac37  call    EventWrite0
0x18003ac3c  jmp     loc_18003AD26
0x18003ac41  xor     edx, edx; Val
0x18003ac43  lea     rcx, [rsp+0C8h+var_78]; void *
0x18003ac48  lea     r8d, [rdx+48h]; Size
0x18003ac4c  call    memset_0
0x18003ac51  lea     rax, [rbx+12E0h]
0x18003ac58  mov     [rsp+0C8h+var_78.ai_family], 2
0x18003ac60  mov     [rsp+0C8h+lpHandle], rax; lpHandle
0x18003ac65  lea     rcx, [rbx+12C0h]
0x18003ac6c  lea     rax, IsatapUpdateRouterAddressAsyncCallback
0x18003ac73  xor     r9d, r9d; lpNspId
0x18003ac76  mov     [rsp+0C8h+lpCompletionRoutine], rax; lpCompletionRoutine
0x18003ac7b  lea     rdx, [rbx+12B8h]
0x18003ac82  mov     [rsp+0C8h+lpOverlapped], rcx; lpOverlapped
0x18003ac87  lea     rax, [rsp+0C8h+var_78]
0x18003ac8c  mov     [rsp+0C8h+timeout], 0; timeout
0x18003ac95  xor     r8d, r8d; dwNameSpace
0x18003ac98  mov     [rsp+0C8h+ppResult], rdx; ppResult
0x18003ac9d  mov     rcx, rbp; pName
0x18003aca0  xor     edx, edx; pServiceName
0x18003aca2  mov     [rsp+0C8h+hints], rax; hints
0x18003aca7  call    cs:__imp_GetAddrInfoExW
0x18003acae  nop     dword ptr [rax+rax+00h]
0x18003acb3  cmp     dword ptr [rsi+10h], 1
0x18003acb7  mov     edi, eax
0x18003acb9  jz      short loc_18003ACC9
0x18003acbb  xor     ecx, ecx; CompartmentId
0x18003acbd  call    cs:__imp_SetCurrentThreadCompartmentId
0x18003acc4  nop     dword ptr [rax+rax+00h]
0x18003acc9  cmp     edi, 3E5h
0x18003accf  jz      short loc_18003ACFF
0x18003acd1  mov     rdx, rbx
0x18003acd4  mov     ecx, edi
0x18003acd6  call    IsatapUpdateRouterAddressAsyncCallbackUnderGlobalIsatapLock
0x18003acdb  test    edi, edi
0x18003acdd  jz      short loc_18003AD01
0x18003acdf  mov     eax, [rsi+10h]
0x18003ace2  lea     rdx, aIsatapresolvei_0; "IsatapResolveIpv4AddressesAsync.GetAddr"...
0x18003ace9  mov     r9d, edi
0x18003acec  mov     dword ptr [rsp+0C8h+hints], eax
0x18003acf0  mov     r8, rbp
0x18003acf3  mov     ecx, 2000000h
0x18003acf8  call    EventWrite0
0x18003acfd  jmp     short loc_18003AD01
0x18003acff  xor     edi, edi
0x18003ad01  mov     r8d, edi
0x18003ad04  lea     rdx, aIsatapresolvei; "IsatapResolveIpv4AddressesAsync returne"...
0x18003ad0b  mov     ecx, 2000000h
0x18003ad10  call    EventWrite0
0x18003ad15  lea     rdx, aLeavingIsatapr; "Leaving: IsatapResolveIpv4AddressesAsyn"...
0x18003ad1c  mov     ecx, 20000h
0x18003ad21  call    EventWriteLeaveEx
0x18003ad26  mov     eax, edi
0x18003ad28  add     rsp, 0A8h
0x18003ad2f  pop     rdi
0x18003ad30  pop     rsi
0x18003ad31  pop     rbp
0x18003ad32  pop     rbx
0x18003ad33  retn
```
