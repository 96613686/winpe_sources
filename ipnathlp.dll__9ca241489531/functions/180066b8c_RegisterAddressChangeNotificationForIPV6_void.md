# RegisterAddressChangeNotificationForIPV6(void)

- ea: `0x180066b8c`
- end: `0x180066d9b`
- name: `?RegisterAddressChangeNotificationForIPV6@@YAKXZ`
- size: `527`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18006fa64`

## callees

- `0x180007de8`
- `0x18000c110`
- `0x18000c750`
- `0x180066b8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066bf8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180066bf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c0a`
- `NSI!NsiRequestChangeNotification` at `0x180066cf1`
- `NSI!NsiRequestChangeNotification` at `0x180066cf1`
- `ntdll!RtlRegisterWait` at `0x180066c67`
- `ntdll!RtlRegisterWait` at `0x180066c67`
- `ntdll!RtlDeregisterWait` at `0x180066d07`
- `ntdll!RtlDeregisterWait` at `0x180066d07`
- `ntdll!RtlNtStatusToDosError` at `0x180066c8d`
- `ntdll!RtlNtStatusToDosError` at `0x180066c8d`
- `ntdll!NtClose` at `0x180066c7a`
- `ntdll!NtClose` at `0x180066d1f`
- `ntdll!NtClose` at `0x180066c7a`
- `ntdll!NtClose` at `0x180066d1f`

## pseudocode

```c
__int64 RegisterAddressChangeNotificationForIPV6(void)
{
  HANDLE EventW; // rax
  ULONG LastError; // eax
  ULONG v2; // ebx
  PVOID *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  int v6; // ebx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2e9dbe9a69f234af9504dc881051edd4_Traceguids);
  }
  v8 = 0;
  gPublicAdapterIPV6BindingInfo = NhQueryBindingInformationForIPv6(gICSPublicAdapterIndex);
  EventW = CreateEventW(0, 0, 0, 0);
  hIPV6AddressChangeEvent = EventW;
  if ( EventW )
  {
    v6 = RtlRegisterWait(&hIPV6AddressChangeWaitHandle, EventW, IPV6AddressChangeCallbackRoutine, 0, 0xFFFFFFFF, 0);
    if ( v6 >= 0 )
    {
      qword_1800A8710 = (__int64)hIPV6AddressChangeEvent;
      v2 = NsiRequestChangeNotification(0, &NPI_MS_IPV6_MODULEID, 10, &NsiAddrChnageNotifyOverLapped, &v8);
      if ( v2 == 997 )
      {
LABEL_22:
        v3 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_23;
      }
      RtlDeregisterWait(hIPV6AddressChangeWaitHandle);
      hIPV6AddressChangeWaitHandle = 0;
      NtClose(hIPV6AddressChangeEvent);
      hIPV6AddressChangeEvent = 0;
      v3 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v2;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_23;
      v4 = 13;
      v5 = v2;
LABEL_21:
      WPP_SF_d(v3[2], v4, WPP_2e9dbe9a69f234af9504dc881051edd4_Traceguids, v5);
      goto LABEL_22;
    }
    NtClose(hIPV6AddressChangeEvent);
    hIPV6AddressChangeEvent = 0;
    LastError = RtlNtStatusToDosError(v6);
    v2 = LastError;
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v2;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_23;
    v4 = 12;
LABEL_10:
    v5 = LastError;
    goto LABEL_21;
  }
  LastError = GetLastError();
  v2 = LastError;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = 11;
    goto LABEL_10;
  }
LABEL_23:
  if ( v3 != &WPP_GLOBAL_Control && *((char *)v3 + 28) < 0 && *((_BYTE *)v3 + 25) >= 6u )
    WPP_SF_d(v3[2], 14, WPP_2e9dbe9a69f234af9504dc881051edd4_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180066b8c  mov     [rsp+arg_8], rbx
0x180066b91  mov     [rsp+arg_10], rbp
0x180066b96  push    r14
0x180066b98  sub     rsp, 30h
0x180066b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066ba3  lea     rbp, WPP_GLOBAL_Control
0x180066baa  lea     r14, WPP_2e9dbe9a69f234af9504dc881051edd4_Traceguids
0x180066bb1  cmp     rcx, rbp
0x180066bb4  jz      short loc_180066BD3
0x180066bb6  test    byte ptr [rcx+1Ch], 80h
0x180066bba  jz      short loc_180066BD3
0x180066bbc  cmp     byte ptr [rcx+19h], 6
0x180066bc0  jb      short loc_180066BD3
0x180066bc2  mov     rcx, [rcx+10h]
0x180066bc6  mov     edx, 0Ah
0x180066bcb  mov     r8, r14
0x180066bce  call    WPP_SF_
0x180066bd3  mov     ecx, cs:?gICSPublicAdapterIndex@@3KA; unsigned int
0x180066bd9  mov     [rsp+38h+arg_0], 0
0x180066be2  call    ?NhQueryBindingInformationForIPv6@@YAPEAUIPV6_ADAPTER_BINDING_INFO@@K@Z; NhQueryBindingInformationForIPv6(ulong)
0x180066be7  xor     r9d, r9d; lpName
0x180066bea  mov     cs:?gPublicAdapterIPV6BindingInfo@@3PEAUIPV6_ADAPTER_BINDING_INFO@@EA, rax; IPV6_ADAPTER_BINDING_INFO * gPublicAdapterIPV6BindingInfo
0x180066bf1  xor     r8d, r8d; bInitialState
0x180066bf4  xor     edx, edx; bManualReset
0x180066bf6  xor     ecx, ecx; lpEventAttributes
0x180066bf8  call    cs:__imp_CreateEventW
0x180066bfe  mov     cs:?hIPV6AddressChangeEvent@@3PEAXEA, rax; void * hIPV6AddressChangeEvent
0x180066c05  test    rax, rax
0x180066c08  jnz     short loc_180066C43
0x180066c0a  call    cs:__imp_GetLastError
0x180066c10  mov     ebx, eax
0x180066c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180066c19  cmp     rcx, rbp
0x180066c1c  jz      loc_180066D88
0x180066c22  test    byte ptr [rcx+1Ch], 80h
0x180066c26  jz      loc_180066D63
0x180066c2c  cmp     byte ptr [rcx+19h], 2
0x180066c30  jb      loc_180066D63
0x180066c36  mov     edx, 0Bh
0x180066c3b  mov     r9d, eax
0x180066c3e  jmp     loc_180066D50
0x180066c43  mov     [rsp+38h+ulFlags], 0; ulFlags
0x180066c4b  lea     r8, ?IPV6AddressChangeCallbackRoutine@@YAXPEAXE@Z; Callback
0x180066c52  xor     r9d, r9d; pvContext
0x180066c55  mov     [rsp+38h+ulMilliseconds], 0FFFFFFFFh; ulMilliseconds
0x180066c5d  mov     rdx, rax; hObject
0x180066c60  lea     rcx, ?hIPV6AddressChangeWaitHandle@@3PEAXEA; phNewWaitObject
0x180066c67  call    cs:__imp_RtlRegisterWait
0x180066c6d  mov     ebx, eax
0x180066c6f  test    eax, eax
0x180066c71  jns     short loc_180066CC3
0x180066c73  mov     rcx, cs:?hIPV6AddressChangeEvent@@3PEAXEA; Handle
0x180066c7a  call    cs:__imp_NtClose
0x180066c80  mov     ecx, ebx; Status
0x180066c82  mov     cs:?hIPV6AddressChangeEvent@@3PEAXEA, 0; void * hIPV6AddressChangeEvent
0x180066c8d  call    cs:__imp_RtlNtStatusToDosError
0x180066c93  mov     ebx, eax
0x180066c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180066c9c  cmp     rcx, rbp
0x180066c9f  jz      loc_180066D88
0x180066ca5  test    byte ptr [rcx+1Ch], 80h
0x180066ca9  jz      loc_180066D63
0x180066caf  cmp     byte ptr [rcx+19h], 2
0x180066cb3  jb      loc_180066D63
0x180066cb9  mov     edx, 0Ch
0x180066cbe  jmp     loc_180066C3B
0x180066cc3  mov     rax, cs:?hIPV6AddressChangeEvent@@3PEAXEA; void * hIPV6AddressChangeEvent
0x180066cca  lea     r9, ?NsiAddrChnageNotifyOverLapped@@3U_OVERLAPPED@@A; _OVERLAPPED NsiAddrChnageNotifyOverLapped
0x180066cd1  mov     cs:qword_1800A8710, rax
0x180066cd8  lea     rdx, NPI_MS_IPV6_MODULEID
0x180066cdf  lea     rax, [rsp+38h+arg_0]
0x180066ce4  mov     r8d, 0Ah
0x180066cea  xor     ecx, ecx
0x180066cec  mov     qword ptr [rsp+38h+ulMilliseconds], rax
0x180066cf1  call    cs:__imp_NsiRequestChangeNotification
0x180066cf7  mov     ebx, eax
0x180066cf9  cmp     eax, 3E5h
0x180066cfe  jz      short loc_180066D5C
0x180066d00  mov     rcx, cs:?hIPV6AddressChangeWaitHandle@@3PEAXEA; hWaitHandle
0x180066d07  call    cs:__imp_RtlDeregisterWait
0x180066d0d  mov     rcx, cs:?hIPV6AddressChangeEvent@@3PEAXEA; Handle
0x180066d14  mov     cs:?hIPV6AddressChangeWaitHandle@@3PEAXEA, 0; void * hIPV6AddressChangeWaitHandle
0x180066d1f  call    cs:__imp_NtClose
0x180066d25  mov     cs:?hIPV6AddressChangeEvent@@3PEAXEA, 0; void * hIPV6AddressChangeEvent
0x180066d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d37  cmp     rcx, rbp
0x180066d3a  jz      short loc_180066D88
0x180066d3c  test    byte ptr [rcx+1Ch], 80h
0x180066d40  jz      short loc_180066D63
0x180066d42  cmp     byte ptr [rcx+19h], 2
0x180066d46  jb      short loc_180066D63
0x180066d48  mov     edx, 0Dh
0x180066d4d  mov     r9d, ebx
0x180066d50  mov     rcx, [rcx+10h]
0x180066d54  mov     r8, r14
0x180066d57  call    WPP_SF_d
0x180066d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d63  cmp     rcx, rbp
0x180066d66  jz      short loc_180066D88
0x180066d68  test    byte ptr [rcx+1Ch], 80h
0x180066d6c  jz      short loc_180066D88
0x180066d6e  cmp     byte ptr [rcx+19h], 6
0x180066d72  jb      short loc_180066D88
0x180066d74  mov     rcx, [rcx+10h]
0x180066d78  mov     edx, 0Eh
0x180066d7d  mov     r9d, ebx
0x180066d80  mov     r8, r14
0x180066d83  call    WPP_SF_d
0x180066d88  mov     rbp, [rsp+38h+arg_10]
0x180066d8d  mov     eax, ebx
0x180066d8f  mov     rbx, [rsp+38h+arg_8]
0x180066d94  add     rsp, 30h
0x180066d98  pop     r14
0x180066d9a  retn
```
