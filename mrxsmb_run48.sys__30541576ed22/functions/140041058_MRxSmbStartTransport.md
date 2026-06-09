# MRxSmbStartTransport

- ea: `0x140041058`
- end: `0x140041573`
- name: `MRxSmbStartTransport`
- size: `1307`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140081d80`

## callees

- `0x14002be60`
- `0x14003838c`
- `0x140041058`
- `0x140059dc0`
- `0x14007e008`
- `0x140084d4c`

## import_xrefs

- `ntoskrnl!IoWMIOpenBlock` at `0x1400414c6`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400414c6`
- `ntoskrnl!IoWMISetNotificationCallback` at `0x1400414ea`
- `ntoskrnl!IoWMISetNotificationCallback` at `0x1400414ea`
- `ntoskrnl!ZwQueryLicenseValue` at `0x1400413c2`
- `ntoskrnl!ZwQueryLicenseValue` at `0x1400413c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140041231`
- `ntoskrnl!RtlInitUnicodeString` at `0x140041399`
- `ntoskrnl!RtlInitUnicodeString` at `0x140041231`
- `ntoskrnl!RtlInitUnicodeString` at `0x140041399`
- `ntoskrnl!ExAllocatePool2` at `0x14004109f`
- `ntoskrnl!ExAllocatePool2` at `0x14004109f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041192`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041192`
- `TDI!TdiRegisterPnPHandlers` at `0x14004127a`
- `TDI!TdiRegisterPnPHandlers` at `0x14004127a`
- `NETIO!GetBestInterfaceEx` at `0x1400410dd`
- `NETIO!GetBestInterfaceEx` at `0x14004114b`
- `NETIO!GetBestInterfaceEx` at `0x1400410dd`
- `NETIO!GetBestInterfaceEx` at `0x14004114b`
- `NETIO!NsiRegisterChangeNotification` at `0x1400412e9`
- `NETIO!NsiRegisterChangeNotification` at `0x140041351`
- `NETIO!NsiRegisterChangeNotification` at `0x140041404`
- `NETIO!NsiRegisterChangeNotification` at `0x14004146c`
- `NETIO!NsiRegisterChangeNotification` at `0x1400412e9`
- `NETIO!NsiRegisterChangeNotification` at `0x140041351`
- `NETIO!NsiRegisterChangeNotification` at `0x140041404`
- `NETIO!NsiRegisterChangeNotification` at `0x14004146c`

## pseudocode

```c
__int64 MRxSmbStartTransport()
{
  _DWORD *Pool2; // rbx
  int BestInterface; // eax
  int v2; // eax
  int v3; // edi
  int v4; // eax
  __int128 v5; // xmm0
  __int64 v6; // r9
  NTSTATUS v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // r9
  int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // r9
  unsigned int v15; // eax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  int v19; // [rsp+30h] [rbp-69h] BYREF
  int v20; // [rsp+34h] [rbp-65h] BYREF
  int v21; // [rsp+38h] [rbp-61h] BYREF
  int v22; // [rsp+3Ch] [rbp-5Dh] BYREF
  TDI_CLIENT_INTERFACE_INFO ClientInterfaceInfo; // [rsp+40h] [rbp-59h] BYREF
  UNICODE_STRING v24; // [rsp+78h] [rbp-21h] BYREF
  UNICODE_STRING DestinationString[2]; // [rsp+88h] [rbp-11h] BYREF

  v20 = 0;
  v22 = 0;
  v21 = 0;
  v24 = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, 128, 1834184788);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v19 = 0;
  memset(DestinationString, 0, 28);
  *(IN_ADDR *)(&DestinationString[0].MaximumLength + 1) = in4addr_loopback;
  DestinationString[0].Length = 2;
  BestInterface = GetBestInterfaceEx(DestinationString, &v19);
  if ( BestInterface < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        &WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids,
        (unsigned int)BestInterface);
    }
    DestinationString[0].Length = 23;
    *(IN6_ADDR *)&DestinationString[0].Buffer = in6addr_loopback;
    v2 = GetBestInterfaceEx(DestinationString, &v19);
    v3 = v2;
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          &WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids,
          (unsigned int)v2);
      }
      goto LABEL_12;
    }
  }
  v4 = v19;
  *(_WORD *)Pool2 = -5371;
  v5 = *(_OWORD *)MRxSmbLoopbackTransportName;
  Pool2[12] = v4;
  Pool2[14] = 1;
  *((_OWORD *)Pool2 + 2) = v5;
  Pool2[13] = dword_1400709B8;
  Pool2[16] = 65537;
  v3 = SmbCeAddTransport(MRxSmbDeviceObject, 0, Pool2);
  if ( v3 >= 0 )
  {
    SmbCeDiscardUnavailableServerList(&MRxSmbHostUnavailableServers);
    SmbCeDiscardInvalidAuthEntryList(&MRxSmbHostInvalidAuthEntries);
    if ( !MRxSmbTdiNotificationHandle )
    {
      DestinationString[0] = 0;
      memset(&ClientInterfaceInfo, 0, sizeof(ClientInterfaceInfo));
      RtlInitUnicodeString(DestinationString, L"LanmanWorkStation");
      *(_DWORD *)&ClientInterfaceInfo.MajorTdiVersion = 2;
      ClientInterfaceInfo.ClientName = DestinationString;
      ClientInterfaceInfo.40 = 0u;
      ClientInterfaceInfo.BindingHandler = (TDI_BINDING_HANDLER)&MRxSmbPnPBindingHandler;
      ClientInterfaceInfo.PnPPowerHandler = (TDI_PNP_POWER_HANDLER)MRxSmbPnPPowerHandler;
      v7 = TdiRegisterPnPHandlers(&ClientInterfaceInfo, 0x38u, &MRxSmbTdiNotificationHandle);
      if ( v7 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          &WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids,
          (unsigned int)v7);
      }
    }
    if ( !MRxSmbIPv4NsiHandle )
    {
      LOBYTE(v6) = 1;
      v8 = NsiRegisterChangeNotification(
             &NPI_MS_IPV4_MODULEID,
             10,
             MRxSmbIPv4AddressChangeHandler,
             v6,
             0,
             &MRxSmbIPv4NsiHandle);
      if ( v8 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          &WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids,
          (unsigned int)v8);
      }
    }
    if ( !MRxSmbIPv6NsiHandle )
    {
      LOBYTE(v6) = 1;
      v9 = NsiRegisterChangeNotification(
             &NPI_MS_IPV6_MODULEID,
             10,
             MRxSmbIPv6AddressChangeHandler,
             v6,
             0,
             &MRxSmbIPv6NsiHandle);
      if ( v9 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          &WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids,
          (unsigned int)v9);
      }
    }
    RtlInitUnicodeString(&v24, L"SMBClient-AllowRdmaUsage");
    if ( (int)ZwQueryLicenseValue(&v24, &v22, &v20, 4, &v21) >= 0 )
    {
      if ( v20 )
      {
        if ( !MRxSmbRdmaNotificationHandle )
        {
          LOBYTE(v10) = 1;
          v11 = NsiRegisterChangeNotification(
                  &NPI_MS_FLRDMA_MODULEID,
                  0,
                  MRxSmbRdmaNotificationHandler,
                  v10,
                  0,
                  &MRxSmbRdmaNotificationHandle);
          if ( v11 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              17,
              &WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids,
              (unsigned int)v11);
          }
        }
      }
    }
    if ( !MRxSmbRssNotificationHandle )
    {
      LOBYTE(v10) = 1;
      v12 = NsiRegisterChangeNotification(
              &NPI_MS_RSS_MODULEID,
              0,
              MRxSmbRssNotificationHandler,
              v10,
              0,
              &MRxSmbRssNotificationHandle);
      if ( v12 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          &WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids,
          (unsigned int)v12);
      }
    }
    if ( MRxSmbWmiDataBlock )
      return 0;
    v13 = IoWMIOpenBlock(&GUID_NDIS_STATUS_LINK_STATE, 4u, &MRxSmbWmiDataBlock);
    v14 = v13;
    if ( v13 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return 0;
      }
      v17 = 20;
    }
    else
    {
      v15 = IoWMISetNotificationCallback(MRxSmbWmiDataBlock, MRxSmbWmiLinkStateNotificationHandler, 0);
      if ( !v15 )
        return 0;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xDu)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return 0;
      }
      v17 = 19;
      v14 = v15;
    }
    WPP_SF_d(v16->AttachedDevice, v17, &WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids, v14);
    return 0;
  }
LABEL_12:
  ExFreePoolWithTag(Pool2, 0x6D537054u);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140041058  push    rbp
0x14004105a  push    rbx
0x14004105b  push    rsi
0x14004105c  push    rdi
0x14004105d  push    r12
0x14004105f  push    r13
0x140041061  push    r14
0x140041063  push    r15
0x140041065  lea     rbp, [rsp-1Fh]
0x14004106a  sub     rsp, 0B8h
0x140041071  mov     rax, cs:__security_cookie
0x140041078  xor     rax, rsp
0x14004107b  mov     [rbp+57h+var_48], rax
0x14004107f  xor     esi, esi
0x140041081  xorps   xmm0, xmm0
0x140041084  mov     edx, 80h
0x140041089  mov     [rbp+57h+var_BC], esi
0x14004108c  mov     r8d, 6D537054h
0x140041092  mov     [rbp+57h+var_B4], esi
0x140041095  mov     [rbp+57h+var_B8], esi
0x140041098  lea     ecx, [rsi+40h]
0x14004109b  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x14004109f  call    cs:__imp_ExAllocatePool2
0x1400410a6  nop     dword ptr [rax+rax+00h]
0x1400410ab  mov     rbx, rax
0x1400410ae  test    rax, rax
0x1400410b1  jz      loc_14004154B
0x1400410b7  mov     ecx, dword ptr cs:in4addr_loopback.S_un
0x1400410bd  lea     eax, [rsi+2]
0x1400410c0  xorps   xmm0, xmm0
0x1400410c3  mov     [rbp+57h+var_C0], esi
0x1400410c6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400410ca  mov     dword ptr [rbp+57h+DestinationString+4], ecx
0x1400410cd  lea     rdx, [rbp+57h+var_C0]
0x1400410d1  lea     rcx, [rbp+57h+DestinationString]
0x1400410d5  mov     [rbp+57h+DestinationString.Length], ax
0x1400410d9  movups  xmmword ptr [rbp+57h+DestinationString.Buffer+4], xmm0
0x1400410dd  call    cs:__imp_GetBestInterfaceEx
0x1400410e4  nop     dword ptr [rax+rax+00h]
0x1400410e9  lea     r15, WPP_GLOBAL_Control
0x1400410f0  lea     r14d, [rsi+1]
0x1400410f4  lea     r13, WPP_f5db7b01804c3d2d4fcad5e89631cde4_Traceguids
0x1400410fb  test    eax, eax
0x1400410fd  jns     loc_1400411A3
0x140041103  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004110a  cmp     rcx, r15
0x14004110d  jz      short loc_14004112E
0x14004110f  bt      dword ptr [rcx+2Ch], 0Dh
0x140041114  jnb     short loc_14004112E
0x140041116  cmp     [rcx+29h], r14b
0x14004111a  jb      short loc_14004112E
0x14004111c  mov     rcx, [rcx+18h]
0x140041120  lea     edx, [rsi+0Ch]
0x140041123  mov     r9d, eax
0x140041126  mov     r8, r13
0x140041129  call    WPP_SF_d
0x14004112e  movups  xmm0, xmmword ptr cs:in6addr_loopback.u
0x140041135  mov     eax, 17h
0x14004113a  lea     rdx, [rbp+57h+var_C0]
0x14004113e  lea     rcx, [rbp+57h+DestinationString]
0x140041142  mov     [rbp+57h+DestinationString.Length], ax
0x140041146  movdqu  xmmword ptr [rbp+57h+DestinationString.Buffer], xmm0
0x14004114b  call    cs:__imp_GetBestInterfaceEx
0x140041152  nop     dword ptr [rax+rax+00h]
0x140041157  mov     edi, eax
0x140041159  test    eax, eax
0x14004115b  jns     short loc_1400411A3
0x14004115d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140041164  cmp     rcx, r15
0x140041167  jz      short loc_14004118A
0x140041169  bt      dword ptr [rcx+2Ch], 0Dh
0x14004116e  jnb     short loc_14004118A
0x140041170  cmp     [rcx+29h], r14b
0x140041174  jb      short loc_14004118A
0x140041176  mov     rcx, [rcx+18h]
0x14004117a  mov     edx, 0Dh
0x14004117f  mov     r9d, eax
0x140041182  mov     r8, r13
0x140041185  call    WPP_SF_d
0x14004118a  mov     edx, 6D537054h; Tag
0x14004118f  mov     rcx, rbx; P
0x140041192  call    cs:__imp_ExFreePoolWithTag
0x140041199  nop     dword ptr [rax+rax+00h]
0x14004119e  jmp     loc_140041550
0x1400411a3  mov     eax, [rbp+57h+var_C0]
0x1400411a6  mov     r8, rbx
0x1400411a9  mov     word ptr [rbx], 0EB05h
0x1400411ae  xor     edx, edx
0x1400411b0  movups  xmm0, xmmword ptr cs:MRxSmbLoopbackTransportName; ",."
0x1400411b7  mov     [rbx+30h], eax
0x1400411ba  mov     [rbx+38h], r14d
0x1400411be  movdqu  xmmword ptr [rbx+20h], xmm0
0x1400411c3  mov     eax, cs:dword_1400709B8
0x1400411c9  mov     [rbx+34h], eax
0x1400411cc  mov     dword ptr [rbx+40h], 10001h
0x1400411d3  mov     rcx, cs:MRxSmbDeviceObject
0x1400411da  call    SmbCeAddTransport
0x1400411df  mov     edi, eax
0x1400411e1  test    eax, eax
0x1400411e3  js      short loc_14004118A
0x1400411e5  lea     rcx, MRxSmbHostUnavailableServers
0x1400411ec  call    SmbCeDiscardUnavailableServerList
0x1400411f1  lea     rcx, MRxSmbHostInvalidAuthEntries
0x1400411f8  call    SmbCeDiscardInvalidAuthEntryList
0x1400411fd  cmp     cs:MRxSmbTdiNotificationHandle, rsi
0x140041204  jnz     loc_1400412B7
0x14004120a  xorps   xmm1, xmm1
0x14004120d  lea     rdx, aLanmanworkstat_0; "LanmanWorkStation"
0x140041214  xorps   xmm0, xmm0
0x140041217  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004121b  xor     eax, eax
0x14004121d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140041221  mov     qword ptr [rbp+57h+ClientInterfaceInfo.28h+8], rax
0x140041225  movups  xmmword ptr [rbp+57h+ClientInterfaceInfo], xmm1
0x140041229  movups  xmmword ptr [rbp+57h+ClientInterfaceInfo.PnPPowerHandler], xmm1
0x14004122d  movups  xmmword ptr [rbp+57h+ClientInterfaceInfo.18h+8], xmm1
0x140041231  call    cs:__imp_RtlInitUnicodeString
0x140041238  nop     dword ptr [rax+rax+00h]
0x14004123d  lea     rax, [rbp+57h+DestinationString]
0x140041241  mov     dword ptr [rbp+57h+ClientInterfaceInfo], 2
0x140041248  mov     [rbp+57h+ClientInterfaceInfo.ClientName], rax
0x14004124c  lea     r8, MRxSmbTdiNotificationHandle; BindingHandle
0x140041253  lea     rax, MRxSmbPnPBindingHandler
0x14004125a  mov     qword ptr [rbp+57h+ClientInterfaceInfo.28h], rsi
0x14004125e  mov     qword ptr [rbp+57h+ClientInterfaceInfo.18h], rax
0x140041262  lea     rcx, [rbp+57h+ClientInterfaceInfo]; ClientInterfaceInfo
0x140041266  lea     rax, MRxSmbPnPPowerHandler
0x14004126d  mov     qword ptr [rbp+57h+ClientInterfaceInfo.28h+8], rsi
0x140041271  mov     edx, 38h ; '8'; InterfaceInfoSize
0x140041276  mov     [rbp+57h+ClientInterfaceInfo.PnPPowerHandler], rax
0x14004127a  call    cs:__imp_TdiRegisterPnPHandlers
0x140041281  nop     dword ptr [rax+rax+00h]
0x140041286  test    eax, eax
0x140041288  jns     short loc_1400412B7
0x14004128a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140041291  cmp     rcx, r15
0x140041294  jz      short loc_1400412B7
0x140041296  bt      dword ptr [rcx+2Ch], 0Dh
0x14004129b  jnb     short loc_1400412B7
0x14004129d  cmp     [rcx+29h], r14b
0x1400412a1  jb      short loc_1400412B7
0x1400412a3  mov     rcx, [rcx+18h]
0x1400412a7  mov     edx, 0Eh
0x1400412ac  mov     r9d, eax
0x1400412af  mov     r8, r13
0x1400412b2  call    WPP_SF_d
0x1400412b7  cmp     cs:MRxSmbIPv4NsiHandle, rsi
0x1400412be  mov     ebx, 0Ah
0x1400412c3  jnz     short loc_140041324
0x1400412c5  lea     rax, MRxSmbIPv4NsiHandle
0x1400412cc  mov     r9b, r14b
0x1400412cf  mov     [rsp+0F0h+var_C8], rax
0x1400412d4  lea     r8, MRxSmbIPv4AddressChangeHandler
0x1400412db  mov     edx, ebx
0x1400412dd  mov     [rsp+0F0h+var_D0], rsi
0x1400412e2  lea     rcx, NPI_MS_IPV4_MODULEID
0x1400412e9  call    cs:__imp_NsiRegisterChangeNotification
0x1400412f0  nop     dword ptr [rax+rax+00h]
0x1400412f5  test    eax, eax
0x1400412f7  jns     short loc_140041324
0x1400412f9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140041300  cmp     rcx, r15
0x140041303  jz      short loc_140041324
0x140041305  bt      dword ptr [rcx+2Ch], 0Dh
0x14004130a  jnb     short loc_140041324
0x14004130c  cmp     [rcx+29h], r14b
0x140041310  jb      short loc_140041324
0x140041312  mov     rcx, [rcx+18h]
0x140041316  lea     edx, [rbx+5]
0x140041319  mov     r9d, eax
0x14004131c  mov     r8, r13
0x14004131f  call    WPP_SF_d
0x140041324  cmp     cs:MRxSmbIPv6NsiHandle, rsi
0x14004132b  jnz     short loc_14004138E
0x14004132d  lea     rax, MRxSmbIPv6NsiHandle
0x140041334  mov     r9b, r14b
0x140041337  mov     [rsp+0F0h+var_C8], rax
0x14004133c  lea     r8, MRxSmbIPv6AddressChangeHandler
0x140041343  mov     edx, ebx
0x140041345  mov     [rsp+0F0h+var_D0], rsi
0x14004134a  lea     rcx, NPI_MS_IPV6_MODULEID
0x140041351  call    cs:__imp_NsiRegisterChangeNotification
0x140041358  nop     dword ptr [rax+rax+00h]
0x14004135d  test    eax, eax
0x14004135f  jns     short loc_14004138E
0x140041361  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140041368  cmp     rcx, r15
0x14004136b  jz      short loc_14004138E
0x14004136d  bt      dword ptr [rcx+2Ch], 0Dh
0x140041372  jnb     short loc_14004138E
0x140041374  cmp     [rcx+29h], r14b
0x140041378  jb      short loc_14004138E
0x14004137a  mov     rcx, [rcx+18h]
0x14004137e  mov     edx, 10h
0x140041383  mov     r9d, eax
0x140041386  mov     r8, r13
0x140041389  call    WPP_SF_d
0x14004138e  lea     rdx, aSmbclientAllow_0; "SMBClient-AllowRdmaUsage"
0x140041395  lea     rcx, [rbp+57h+var_78]; DestinationString
0x140041399  call    cs:__imp_RtlInitUnicodeString
0x1400413a0  nop     dword ptr [rax+rax+00h]
0x1400413a5  lea     rax, [rbp+57h+var_B8]
0x1400413a9  mov     ebx, 4
0x1400413ae  mov     r9d, ebx
0x1400413b1  mov     [rsp+0F0h+var_D0], rax
0x1400413b6  lea     r8, [rbp+57h+var_BC]
0x1400413ba  lea     rdx, [rbp+57h+var_B4]
0x1400413be  lea     rcx, [rbp+57h+var_78]
0x1400413c2  call    cs:__imp_ZwQueryLicenseValue
0x1400413c9  nop     dword ptr [rax+rax+00h]
0x1400413ce  test    eax, eax
0x1400413d0  js      short loc_14004143F
0x1400413d2  cmp     [rbp+57h+var_BC], esi
0x1400413d5  jz      short loc_14004143F
0x1400413d7  cmp     cs:MRxSmbRdmaNotificationHandle, rsi
0x1400413de  jnz     short loc_14004143F
0x1400413e0  lea     rax, MRxSmbRdmaNotificationHandle
0x1400413e7  mov     r9b, r14b
0x1400413ea  mov     [rsp+0F0h+var_C8], rax
0x1400413ef  lea     r8, MRxSmbRdmaNotificationHandler
0x1400413f6  xor     edx, edx
0x1400413f8  mov     [rsp+0F0h+var_D0], rsi
0x1400413fd  lea     rcx, NPI_MS_FLRDMA_MODULEID
0x140041404  call    cs:__imp_NsiRegisterChangeNotification
0x14004140b  nop     dword ptr [rax+rax+00h]
0x140041410  test    eax, eax
0x140041412  jns     short loc_14004143F
0x140041414  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004141b  cmp     rcx, r15
0x14004141e  jz      short loc_14004143F
0x140041420  bt      dword ptr [rcx+2Ch], 0Dh
0x140041425  jnb     short loc_14004143F
0x140041427  cmp     [rcx+29h], r14b
0x14004142b  jb      short loc_14004143F
0x14004142d  mov     rcx, [rcx+18h]
0x140041431  lea     edx, [rbx+0Dh]
0x140041434  mov     r9d, eax
0x140041437  mov     r8, r13
0x14004143a  call    WPP_SF_d
0x14004143f  cmp     cs:MRxSmbRssNotificationHandle, rsi
0x140041446  jnz     short loc_1400414A9
0x140041448  lea     rax, MRxSmbRssNotificationHandle
0x14004144f  mov     r9b, r14b
0x140041452  mov     [rsp+0F0h+var_C8], rax
0x140041457  lea     r8, MRxSmbRssNotificationHandler
0x14004145e  xor     edx, edx
0x140041460  mov     [rsp+0F0h+var_D0], rsi
0x140041465  lea     rcx, NPI_MS_RSS_MODULEID
0x14004146c  call    cs:__imp_NsiRegisterChangeNotification
0x140041473  nop     dword ptr [rax+rax+00h]
0x140041478  test    eax, eax
0x14004147a  jns     short loc_1400414A9
0x14004147c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140041483  cmp     rcx, r15
0x140041486  jz      short loc_1400414A9
0x140041488  bt      dword ptr [rcx+2Ch], 0Dh
0x14004148d  jnb     short loc_1400414A9
0x14004148f  cmp     [rcx+29h], r14b
0x140041493  jb      short loc_1400414A9
0x140041495  mov     rcx, [rcx+18h]
0x140041499  mov     edx, 12h
0x14004149e  mov     r9d, eax
0x1400414a1  mov     r8, r13
0x1400414a4  call    WPP_SF_d
0x1400414a9  cmp     cs:MRxSmbWmiDataBlock, rsi
0x1400414b0  jnz     loc_140041547
0x1400414b6  lea     r8, MRxSmbWmiDataBlock; DataBlockObject
0x1400414bd  mov     edx, ebx; DesiredAccess
0x1400414bf  lea     rcx, GUID_NDIS_STATUS_LINK_STATE; Guid
0x1400414c6  call    cs:__imp_IoWMIOpenBlock
0x1400414cd  nop     dword ptr [rax+rax+00h]
0x1400414d2  mov     r9d, eax
0x1400414d5  test    eax, eax
0x1400414d7  jnz     short loc_14004151D
0x1400414d9  mov     rcx, cs:MRxSmbWmiDataBlock; Object
0x1400414e0  lea     rdx, MRxSmbWmiLinkStateNotificationHandler; Callback
0x1400414e7  xor     r8d, r8d; Context
0x1400414ea  call    cs:__imp_IoWMISetNotificationCallback
0x1400414f1  nop     dword ptr [rax+rax+00h]
0x1400414f6  test    eax, eax
0x1400414f8  jz      short loc_140041547
0x1400414fa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140041501  cmp     rcx, r15
0x140041504  jz      short loc_140041547
0x140041506  bt      dword ptr [rcx+2Ch], 0Dh
0x14004150b  jnb     short loc_140041547
0x14004150d  cmp     [rcx+29h], r14b
0x140041511  jb      short loc_140041547
0x140041513  mov     edx, 13h
0x140041518  mov     r9d, eax
0x14004151b  jmp     short loc_14004153B
0x14004151d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140041524  cmp     rcx, r15
0x140041527  jz      short loc_140041547
0x140041529  bt      dword ptr [rcx+2Ch], 0Dh
0x14004152e  jnb     short loc_140041547
0x140041530  cmp     [rcx+29h], r14b
0x140041534  jb      short loc_140041547
0x140041536  mov     edx, 14h
0x14004153b  mov     rcx, [rcx+18h]
  ... truncated ...
```
