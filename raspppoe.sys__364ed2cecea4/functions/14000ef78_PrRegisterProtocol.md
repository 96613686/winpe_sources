# PrRegisterProtocol

- ea: `0x14000ef78`
- end: `0x14000f1a5`
- name: `PrRegisterProtocol`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140019078`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140007040`
- `0x14000ea24`
- `0x14000ef78`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000f0e3`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000f0e3`
- `NDIS!NdisRegisterProtocolDriver` at `0x14000f08e`
- `NDIS!NdisRegisterProtocolDriver` at `0x14000f08e`
- `NDIS!NdisDeregisterProtocolDriver` at `0x14000f14c`
- `NDIS!NdisDeregisterProtocolDriver` at `0x14000f14c`

## pseudocode

```c
__int64 PrRegisterProtocol()
{
  unsigned int v0; // ebx
  PVOID v1; // rdi
  _NDIS_PROTOCOL_DRIVER_CHARACTERISTICS ProtocolCharacteristics; // [rsp+28h] [rbp-39h] BYREF
  PVOID NdisProtocolHandle; // [rsp+D0h] [rbp+6Fh] BYREF

  NdisProtocolHandle = 0;
  memset(&ProtocolCharacteristics, 0, sizeof(ProtocolCharacteristics));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  *(_DWORD *)(&ProtocolCharacteristics.Name.MaximumLength + 1) = 0;
  ProtocolCharacteristics.Header = (NDIS_OBJECT_HEADER)8389269;
  ProtocolCharacteristics.Name.Buffer = L"RasPppoe";
  *(_DWORD *)&ProtocolCharacteristics.MajorNdisVersion = 73222;
  ProtocolCharacteristics.BindAdapterHandlerEx = (BIND_HANDLER_EX)PrBindAdapterEx;
  ProtocolCharacteristics.UnbindAdapterHandlerEx = (UNBIND_HANDLER_EX)&PrUnbindAdapterEx;
  ProtocolCharacteristics.OpenAdapterCompleteHandlerEx = (OPEN_ADAPTER_COMPLETE_HANDLER_EX)PrOpenAdapterComplete;
  ProtocolCharacteristics.CloseAdapterCompleteHandlerEx = (CLOSE_ADAPTER_COMPLETE_HANDLER_EX)PrCloseAdapterComplete;
  ProtocolCharacteristics.NetPnPEventHandler = (NET_PNP_EVENT_HANDLER)PrPnPEvent;
  ProtocolCharacteristics.UninstallHandler = (UNINSTALL_PROTOCOL_HANDLER)PrUninstall;
  ProtocolCharacteristics.OidRequestCompleteHandler = (OID_REQUEST_COMPLETE_HANDLER)PrRequestComplete;
  ProtocolCharacteristics.StatusHandlerEx = (STATUS_HANDLER_EX)PrIndicateStatus;
  ProtocolCharacteristics.ReceiveNetBufferListsHandler = (RECEIVE_NET_BUFFER_LISTS_HANDLER)&PrReceiveNetBufferListChain;
  ProtocolCharacteristics.SendNetBufferListsCompleteHandler = (SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER)PrSendNetBufferListChainComplete;
  *(_DWORD *)&ProtocolCharacteristics.Name.Length = 1179664;
  v0 = NdisRegisterProtocolDriver(0, &ProtocolCharacteristics, &NdisProtocolHandle);
  if ( v0 )
  {
    if ( NdisProtocolHandle )
      NdisDeregisterProtocolDriver(NdisProtocolHandle);
    goto LABEL_16;
  }
  v1 = NdisProtocolHandle;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  gl_NdisProtocolDriverHandle = v1;
  KeInitializeSpinLock(&gl_lockProtocol);
  gl_ulNumBindings = 0;
  qword_14000A1E8 = (__int64)&gl_linkBindings;
  gl_linkBindings = (__int64)&gl_linkBindings;
  PrLoad();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
LABEL_16:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, v0);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x14000ef78  mov     rax, rsp
0x14000ef7b  mov     [rax+18h], rbx
0x14000ef7f  mov     [rax+20h], rdi
0x14000ef83  mov     [rax+10h], rdx
0x14000ef87  mov     [rax+8], rcx
0x14000ef8b  push    rbp
0x14000ef8c  push    r13
0x14000ef8e  push    r15
0x14000ef90  lea     rbp, [rax-5Fh]
0x14000ef94  sub     rsp, 0A0h
0x14000ef9b  xor     edx, edx; Val
0x14000ef9d  mov     [rbp+57h+NdisProtocolHandle], 0
0x14000efa5  mov     r8d, 80h; Size
0x14000efab  lea     rcx, [rbp+57h+ProtocolCharacteristics]; void *
0x14000efaf  call    memset
0x14000efb4  xor     ecx, ecx
0x14000efb6  mov     [rbp+57h+arg_0], rcx
0x14000efba  mov     rcx, cs:WPP_GLOBAL_Control
0x14000efc1  lea     r15, WPP_GLOBAL_Control
0x14000efc8  cmp     rcx, r15
0x14000efcb  jz      short loc_14000EFEF
0x14000efcd  mov     eax, [rcx+2Ch]
0x14000efd0  test    al, 4
0x14000efd2  jz      short loc_14000EFEF
0x14000efd4  cmp     byte ptr [rcx+29h], 2
0x14000efd8  jb      short loc_14000EFEF
0x14000efda  mov     rcx, [rcx+18h]
0x14000efde  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000efe5  mov     edx, 20h ; ' '
0x14000efea  call    WPP_SF_
0x14000efef  mov     rax, [rbp+57h+arg_0]
0x14000eff3  lea     r8, [rbp+57h+NdisProtocolHandle]; NdisProtocolHandle
0x14000eff7  mov     dword ptr [rbp+57h+ProtocolCharacteristics.Name+4], eax
0x14000effa  lea     rdx, [rbp+57h+ProtocolCharacteristics]; ProtocolCharacteristics
0x14000effe  lea     rax, aRaspppoe; "RasPppoe"
0x14000f005  mov     dword ptr [rbp+57h+ProtocolCharacteristics.Header.Type], 800295h
0x14000f00c  mov     [rbp+57h+ProtocolCharacteristics.Name.Buffer], rax
0x14000f010  xor     ecx, ecx; ProtocolDriverContext
0x14000f012  lea     rax, PrBindAdapterEx
0x14000f019  mov     dword ptr [rbp+57h+ProtocolCharacteristics.MajorNdisVersion], 11E06h
0x14000f020  mov     [rbp+57h+ProtocolCharacteristics.BindAdapterHandlerEx], rax
0x14000f024  lea     rax, PrUnbindAdapterEx
0x14000f02b  mov     [rbp+57h+ProtocolCharacteristics.UnbindAdapterHandlerEx], rax
0x14000f02f  lea     rax, PrOpenAdapterComplete
0x14000f036  mov     [rbp+57h+ProtocolCharacteristics.OpenAdapterCompleteHandlerEx], rax
0x14000f03a  lea     rax, PrCloseAdapterComplete
0x14000f041  mov     [rbp+57h+ProtocolCharacteristics.CloseAdapterCompleteHandlerEx], rax
0x14000f045  lea     rax, PrPnPEvent
0x14000f04c  mov     [rbp+57h+ProtocolCharacteristics.NetPnPEventHandler], rax
0x14000f050  lea     rax, PrUninstall
0x14000f057  mov     [rbp+57h+ProtocolCharacteristics.UninstallHandler], rax
0x14000f05b  lea     rax, PrRequestComplete
0x14000f062  mov     [rbp+57h+ProtocolCharacteristics.OidRequestCompleteHandler], rax
0x14000f066  lea     rax, PrIndicateStatus
0x14000f06d  mov     [rbp+57h+ProtocolCharacteristics.StatusHandlerEx], rax
0x14000f071  lea     rax, PrReceiveNetBufferListChain
0x14000f078  mov     [rbp+57h+ProtocolCharacteristics.ReceiveNetBufferListsHandler], rax
0x14000f07c  lea     rax, PrSendNetBufferListChainComplete
0x14000f083  mov     [rbp+57h+ProtocolCharacteristics.SendNetBufferListsCompleteHandler], rax
0x14000f087  mov     dword ptr [rbp+57h+ProtocolCharacteristics.Name.Length], 120010h
0x14000f08e  call    cs:__imp_NdisRegisterProtocolDriver
0x14000f095  nop     dword ptr [rax+rax+00h]
0x14000f09a  mov     ebx, eax
0x14000f09c  test    eax, eax
0x14000f09e  jnz     loc_14000F143
0x14000f0a4  mov     rdi, [rbp+57h+NdisProtocolHandle]
0x14000f0a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0af  cmp     rcx, r15
0x14000f0b2  jz      short loc_14000F0D5
0x14000f0b4  mov     edx, [rcx+2Ch]
0x14000f0b7  test    dl, 4
0x14000f0ba  jz      short loc_14000F0D5
0x14000f0bc  cmp     byte ptr [rcx+29h], 3
0x14000f0c0  jb      short loc_14000F0D5
0x14000f0c2  mov     rcx, [rcx+18h]
0x14000f0c6  lea     edx, [rax+0Ah]
0x14000f0c9  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000f0d0  call    WPP_SF_
0x14000f0d5  lea     rcx, gl_lockProtocol; SpinLock
0x14000f0dc  mov     cs:gl_NdisProtocolDriverHandle, rdi
0x14000f0e3  call    cs:__imp_KeInitializeSpinLock
0x14000f0ea  nop     dword ptr [rax+rax+00h]
0x14000f0ef  lea     rax, gl_linkBindings
0x14000f0f6  mov     cs:gl_ulNumBindings, 0
0x14000f100  mov     cs:qword_14000A1E8, rax
0x14000f107  mov     cs:gl_linkBindings, rax
0x14000f10e  call    PrLoad
0x14000f113  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f11a  cmp     rcx, r15
0x14000f11d  jz      short loc_14000F189
0x14000f11f  mov     eax, [rcx+2Ch]
0x14000f122  test    al, 4
0x14000f124  jz      short loc_14000F158
0x14000f126  cmp     byte ptr [rcx+29h], 3
0x14000f12a  jb      short loc_14000F158
0x14000f12c  mov     rcx, [rcx+18h]
0x14000f130  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000f137  mov     edx, 0Bh
0x14000f13c  call    WPP_SF_
0x14000f141  jmp     short loc_14000F158
0x14000f143  mov     rcx, [rbp+57h+NdisProtocolHandle]; NdisProtocolHandle
0x14000f147  test    rcx, rcx
0x14000f14a  jz      short loc_14000F158
0x14000f14c  call    cs:__imp_NdisDeregisterProtocolDriver
0x14000f153  nop     dword ptr [rax+rax+00h]
0x14000f158  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f15f  cmp     rcx, r15
0x14000f162  jz      short loc_14000F189
0x14000f164  mov     eax, [rcx+2Ch]
0x14000f167  test    al, 4
0x14000f169  jz      short loc_14000F189
0x14000f16b  cmp     byte ptr [rcx+29h], 2
0x14000f16f  jb      short loc_14000F189
0x14000f171  mov     rcx, [rcx+18h]
0x14000f175  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000f17c  mov     edx, 21h ; '!'
0x14000f181  mov     r9d, ebx
0x14000f184  call    WPP_SF_d
0x14000f189  lea     r11, [rsp+0B0h+var_10]
0x14000f191  mov     eax, ebx
0x14000f193  mov     rbx, [r11+30h]
0x14000f197  mov     rdi, [r11+38h]
0x14000f19b  mov     rsp, r11
0x14000f19e  pop     r15
0x14000f1a0  pop     r13
0x14000f1a2  pop     rbp
0x14000f1a3  retn
```
