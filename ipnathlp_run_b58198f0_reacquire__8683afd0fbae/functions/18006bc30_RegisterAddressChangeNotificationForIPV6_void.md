# RegisterAddressChangeNotificationForIPV6(void)

- ea: `0x18006bc30`
- end: `0x18006be70`
- name: `?RegisterAddressChangeNotificationForIPV6@@YAKXZ`
- size: `576`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800753a8`

## callees

- `0x18000823c`
- `0x18000ca20`
- `0x18000d090`
- `0x18006bc30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006bc9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006bc9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bcb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bcb4`
- `NSI!NsiRequestChangeNotification` at `0x18006bdb3`
- `NSI!NsiRequestChangeNotification` at `0x18006bdb3`
- `ntdll!RtlRegisterWait` at `0x18006bd17`
- `ntdll!RtlRegisterWait` at `0x18006bd17`
- `ntdll!RtlDeregisterWait` at `0x18006bdcf`
- `ntdll!RtlDeregisterWait` at `0x18006bdcf`
- `ntdll!RtlNtStatusToDosError` at `0x18006bd49`
- `ntdll!RtlNtStatusToDosError` at `0x18006bd49`
- `ntdll!NtClose` at `0x18006bd30`
- `ntdll!NtClose` at `0x18006bded`
- `ntdll!NtClose` at `0x18006bd30`
- `ntdll!NtClose` at `0x18006bded`

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
      qword_1800AF7D0 = (__int64)hIPV6AddressChangeEvent;
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
0x18006bc30  mov     [rsp+arg_8], rbx
0x18006bc35  mov     [rsp+arg_10], rbp
0x18006bc3a  push    r14
0x18006bc3c  sub     rsp, 30h
0x18006bc40  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bc47  lea     rbp, WPP_GLOBAL_Control
0x18006bc4e  lea     r14, WPP_2e9dbe9a69f234af9504dc881051edd4_Traceguids
0x18006bc55  cmp     rcx, rbp
0x18006bc58  jz      short loc_18006BC77
0x18006bc5a  test    byte ptr [rcx+1Ch], 80h
0x18006bc5e  jz      short loc_18006BC77
0x18006bc60  cmp     byte ptr [rcx+19h], 6
0x18006bc64  jb      short loc_18006BC77
0x18006bc66  mov     rcx, [rcx+10h]
0x18006bc6a  mov     edx, 0Ah
0x18006bc6f  mov     r8, r14
0x18006bc72  call    WPP_SF_
0x18006bc77  mov     ecx, cs:?gICSPublicAdapterIndex@@3KA; unsigned int
0x18006bc7d  mov     [rsp+38h+arg_0], 0
0x18006bc86  call    ?NhQueryBindingInformationForIPv6@@YAPEAUIPV6_ADAPTER_BINDING_INFO@@K@Z; NhQueryBindingInformationForIPv6(ulong)
0x18006bc8b  xor     r9d, r9d; lpName
0x18006bc8e  mov     cs:?gPublicAdapterIPV6BindingInfo@@3PEAUIPV6_ADAPTER_BINDING_INFO@@EA, rax; IPV6_ADAPTER_BINDING_INFO * gPublicAdapterIPV6BindingInfo
0x18006bc95  xor     r8d, r8d; bInitialState
0x18006bc98  xor     edx, edx; bManualReset
0x18006bc9a  xor     ecx, ecx; lpEventAttributes
0x18006bc9c  call    cs:__imp_CreateEventW
0x18006bca3  nop     dword ptr [rax+rax+00h]
0x18006bca8  mov     cs:?hIPV6AddressChangeEvent@@3PEAXEA, rax; void * hIPV6AddressChangeEvent
0x18006bcaf  test    rax, rax
0x18006bcb2  jnz     short loc_18006BCF3
0x18006bcb4  call    cs:__imp_GetLastError
0x18006bcbb  nop     dword ptr [rax+rax+00h]
0x18006bcc0  mov     ebx, eax
0x18006bcc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bcc9  cmp     rcx, rbp
0x18006bccc  jz      loc_18006BE5C
0x18006bcd2  test    byte ptr [rcx+1Ch], 80h
0x18006bcd6  jz      loc_18006BE37
0x18006bcdc  cmp     byte ptr [rcx+19h], 2
0x18006bce0  jb      loc_18006BE37
0x18006bce6  mov     edx, 0Bh
0x18006bceb  mov     r9d, eax
0x18006bcee  jmp     loc_18006BE24
0x18006bcf3  mov     [rsp+38h+ulFlags], 0; ulFlags
0x18006bcfb  lea     r8, ?IPV6AddressChangeCallbackRoutine@@YAXPEAXE@Z; Callback
0x18006bd02  xor     r9d, r9d; pvContext
0x18006bd05  mov     [rsp+38h+ulMilliseconds], 0FFFFFFFFh; ulMilliseconds
0x18006bd0d  mov     rdx, rax; hObject
0x18006bd10  lea     rcx, ?hIPV6AddressChangeWaitHandle@@3PEAXEA; phNewWaitObject
0x18006bd17  call    cs:__imp_RtlRegisterWait
0x18006bd1e  nop     dword ptr [rax+rax+00h]
0x18006bd23  mov     ebx, eax
0x18006bd25  test    eax, eax
0x18006bd27  jns     short loc_18006BD85
0x18006bd29  mov     rcx, cs:?hIPV6AddressChangeEvent@@3PEAXEA; Handle
0x18006bd30  call    cs:__imp_NtClose
0x18006bd37  nop     dword ptr [rax+rax+00h]
0x18006bd3c  mov     ecx, ebx; Status
0x18006bd3e  mov     cs:?hIPV6AddressChangeEvent@@3PEAXEA, 0; void * hIPV6AddressChangeEvent
0x18006bd49  call    cs:__imp_RtlNtStatusToDosError
0x18006bd50  nop     dword ptr [rax+rax+00h]
0x18006bd55  mov     ebx, eax
0x18006bd57  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bd5e  cmp     rcx, rbp
0x18006bd61  jz      loc_18006BE5C
0x18006bd67  test    byte ptr [rcx+1Ch], 80h
0x18006bd6b  jz      loc_18006BE37
0x18006bd71  cmp     byte ptr [rcx+19h], 2
0x18006bd75  jb      loc_18006BE37
0x18006bd7b  mov     edx, 0Ch
0x18006bd80  jmp     loc_18006BCEB
0x18006bd85  mov     rax, cs:?hIPV6AddressChangeEvent@@3PEAXEA; void * hIPV6AddressChangeEvent
0x18006bd8c  lea     r9, ?NsiAddrChnageNotifyOverLapped@@3U_OVERLAPPED@@A; _OVERLAPPED NsiAddrChnageNotifyOverLapped
0x18006bd93  mov     cs:qword_1800AF7D0, rax
0x18006bd9a  lea     rdx, NPI_MS_IPV6_MODULEID
0x18006bda1  lea     rax, [rsp+38h+arg_0]
0x18006bda6  mov     r8d, 0Ah
0x18006bdac  xor     ecx, ecx
0x18006bdae  mov     qword ptr [rsp+38h+ulMilliseconds], rax
0x18006bdb3  call    cs:__imp_NsiRequestChangeNotification
0x18006bdba  nop     dword ptr [rax+rax+00h]
0x18006bdbf  mov     ebx, eax
0x18006bdc1  cmp     eax, 3E5h
0x18006bdc6  jz      short loc_18006BE30
0x18006bdc8  mov     rcx, cs:?hIPV6AddressChangeWaitHandle@@3PEAXEA; hWaitHandle
0x18006bdcf  call    cs:__imp_RtlDeregisterWait
0x18006bdd6  nop     dword ptr [rax+rax+00h]
0x18006bddb  mov     rcx, cs:?hIPV6AddressChangeEvent@@3PEAXEA; Handle
0x18006bde2  mov     cs:?hIPV6AddressChangeWaitHandle@@3PEAXEA, 0; void * hIPV6AddressChangeWaitHandle
0x18006bded  call    cs:__imp_NtClose
0x18006bdf4  nop     dword ptr [rax+rax+00h]
0x18006bdf9  mov     cs:?hIPV6AddressChangeEvent@@3PEAXEA, 0; void * hIPV6AddressChangeEvent
0x18006be04  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be0b  cmp     rcx, rbp
0x18006be0e  jz      short loc_18006BE5C
0x18006be10  test    byte ptr [rcx+1Ch], 80h
0x18006be14  jz      short loc_18006BE37
0x18006be16  cmp     byte ptr [rcx+19h], 2
0x18006be1a  jb      short loc_18006BE37
0x18006be1c  mov     edx, 0Dh
0x18006be21  mov     r9d, ebx
0x18006be24  mov     rcx, [rcx+10h]
0x18006be28  mov     r8, r14
0x18006be2b  call    WPP_SF_d
0x18006be30  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be37  cmp     rcx, rbp
0x18006be3a  jz      short loc_18006BE5C
0x18006be3c  test    byte ptr [rcx+1Ch], 80h
0x18006be40  jz      short loc_18006BE5C
0x18006be42  cmp     byte ptr [rcx+19h], 6
0x18006be46  jb      short loc_18006BE5C
0x18006be48  mov     rcx, [rcx+10h]
0x18006be4c  mov     edx, 0Eh
0x18006be51  mov     r9d, ebx
0x18006be54  mov     r8, r14
0x18006be57  call    WPP_SF_d
0x18006be5c  mov     rbp, [rsp+38h+arg_10]
0x18006be61  mov     eax, ebx
0x18006be63  mov     rbx, [rsp+38h+arg_8]
0x18006be68  add     rsp, 30h
0x18006be6c  pop     r14
0x18006be6e  retn
```
