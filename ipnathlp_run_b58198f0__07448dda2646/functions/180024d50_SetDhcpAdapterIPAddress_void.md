# SetDhcpAdapterIPAddress(void)

- ea: `0x180024d50`
- end: `0x1800250f1`
- name: `?SetDhcpAdapterIPAddress@@YAKXZ`
- size: `929`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800250f8`

## callees

- `0x18000d090`
- `0x1800202e0`
- `0x180024d50`
- `0x180035b60`
- `0x18004fd9c`
- `0x180051f30`
- `0x180052bf4`
- `0x18006f014`
- `0x180077008`
- `0x1800777ec`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180024e43`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180024e43`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180024de9`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180024de9`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x180024f86`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x180024f86`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180024ee4`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180024ee4`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180024e87`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180024e87`

## pseudocode

```c
__int64 SetDhcpAdapterIPAddress(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  PVOID *v2; // rcx
  __int64 v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // eax
  int v6; // esi
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // eax
  bool v11; // [rsp+30h] [rbp-59h] BYREF
  ULONG InterfaceIndex; // [rsp+34h] [rbp-55h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-51h] BYREF
  NET_LUID InterfaceLuid; // [rsp+40h] [rbp-49h] BYREF
  struct _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+50h] [rbp-39h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids,
      &DhcpAdapterGuid);
  }
  InterfaceIndex = -1;
  InterfaceLuid.Value = 0;
  memset_0(&Row, 0, sizeof(Row));
  v13 = 0;
  v0 = ConvertInterfaceGuidToLuid(&DhcpAdapterGuid, &InterfaceLuid);
  v1 = v0;
  if ( !v0 )
  {
    v0 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
    v1 = v0;
    if ( v0 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v1;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v3 = 23;
      goto LABEL_10;
    }
    InitializeUnicastIpAddressEntry(&Row);
    Row.InterfaceLuid = InterfaceLuid;
    Row.InterfaceIndex = InterfaceIndex;
    Row.Address.Ipv4.sin_family = 2;
    Row.OnLinkPrefixLength = 24;
    Row.Address.Ipv4.sin_addr.S_un.S_addr = DhcpAdapterIPAddress;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids,
        DhcpAdapterIPAddress);
    }
    v4 = DeleteUnicastIpAddressEntry(&Row);
    if ( v4
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, v4);
    }
    v5 = SetDuplicateAddressDetectionTransmits(InterfaceLuid, 0, &v13);
    if ( v5 )
    {
      v6 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, v5);
      }
    }
    else
    {
      v6 = 1;
    }
    v7 = SharedAccessUtils::TryAcquirePrivateIPAddress(&Row);
    v1 = v7;
    if ( v7 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 30;
        goto LABEL_50;
      }
    }
    else
    {
      DhcpAdapterIPAddress = Row.Address.Ipv4.sin_addr.S_un.S_addr;
      v7 = CreateUnicastIpAddressEntry(&Row);
      v1 = v7;
      if ( v7 )
      {
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 27;
LABEL_50:
          WPP_SF_Dd(v2[2], v8, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, DhcpAdapterIPAddress, v7);
          goto LABEL_51;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids,
            DhcpAdapterIPAddress);
        }
        v11 = 1;
        v9 = SharedAccessUtils::TryPublishWnfStateData(&DhcpAdapterGuid, &Row, &v11);
        if ( !v9 )
          goto LABEL_51;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF__guid_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids,
            &DhcpAdapterGuid,
            Row.Address.Ipv4.sin_addr.S_un.S_addr,
            v9);
LABEL_51:
          v2 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
    if ( v6 )
    {
      SetDuplicateAddressDetectionTransmits(InterfaceLuid, v13, 0);
      goto LABEL_54;
    }
    goto LABEL_55;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = 22;
LABEL_10:
    WPP_SF_d(v2[2], v3, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, v0);
LABEL_54:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_55:
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x200) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_Dd(v2[2], 31, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, v1, InterfaceIndex);
  return v1;
}

```

## disassembly

```asm
0x180024d50  push    rbp
0x180024d52  push    rbx
0x180024d53  push    rsi
0x180024d54  push    rdi
0x180024d55  push    r12
0x180024d57  push    r14
0x180024d59  push    r15
0x180024d5b  lea     rbp, [rsp-27h]
0x180024d60  sub     rsp, 0B0h
0x180024d67  mov     rax, cs:__security_cookie
0x180024d6e  xor     rax, rsp
0x180024d71  mov     [rbp+57h+var_40], rax
0x180024d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d7c  lea     r15, WPP_GLOBAL_Control
0x180024d83  lea     r12, WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids
0x180024d8a  mov     r14d, 200h
0x180024d90  cmp     rcx, r15
0x180024d93  jz      short loc_180024DB9
0x180024d95  test    [rcx+1Ch], r14d
0x180024d99  jz      short loc_180024DB9
0x180024d9b  cmp     byte ptr [rcx+19h], 6
0x180024d9f  jb      short loc_180024DB9
0x180024da1  mov     rcx, [rcx+10h]
0x180024da5  lea     r9, ?DhcpAdapterGuid@@3U_GUID@@A; _GUID DhcpAdapterGuid
0x180024dac  mov     edx, 15h
0x180024db1  mov     r8, r12
0x180024db4  call    WPP_SF__guid_
0x180024db9  xor     edx, edx; Val
0x180024dbb  mov     [rbp+57h+InterfaceIndex], 0FFFFFFFFh
0x180024dc2  lea     rcx, [rbp+57h+Row]; void *
0x180024dc6  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x180024dce  lea     r8d, [rdx+50h]; Size
0x180024dd2  call    memset_0
0x180024dd7  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180024ddb  mov     [rbp+57h+var_A8], 0
0x180024de2  lea     rcx, ?DhcpAdapterGuid@@3U_GUID@@A; InterfaceGuid
0x180024de9  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180024df0  nop     dword ptr [rax+rax+00h]
0x180024df5  mov     ebx, eax
0x180024df7  test    eax, eax
0x180024df9  jz      short loc_180024E3B
0x180024dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e02  cmp     rcx, r15
0x180024e05  jz      loc_1800250D0
0x180024e0b  test    [rcx+1Ch], r14d
0x180024e0f  jz      loc_1800250A4
0x180024e15  mov     edi, 2
0x180024e1a  cmp     [rcx+19h], dil
0x180024e1e  jb      loc_1800250A4
0x180024e24  lea     edx, [rdi+14h]
0x180024e27  mov     rcx, [rcx+10h]
0x180024e2b  mov     r9d, eax
0x180024e2e  mov     r8, r12
0x180024e31  call    WPP_SF_d
0x180024e36  jmp     loc_18002509D
0x180024e3b  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x180024e3f  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180024e43  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180024e4a  nop     dword ptr [rax+rax+00h]
0x180024e4f  mov     ebx, eax
0x180024e51  test    eax, eax
0x180024e53  jz      short loc_180024E83
0x180024e55  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e5c  cmp     rcx, r15
0x180024e5f  jz      loc_1800250D0
0x180024e65  test    [rcx+1Ch], r14d
0x180024e69  jz      loc_1800250A4
0x180024e6f  mov     edi, 2
0x180024e74  cmp     [rcx+19h], dil
0x180024e78  jb      loc_1800250A4
0x180024e7e  lea     edx, [rdi+15h]
0x180024e81  jmp     short loc_180024E27
0x180024e83  lea     rcx, [rbp+57h+Row]; Row
0x180024e87  call    cs:__imp_InitializeUnicastIpAddressEntry
0x180024e8e  nop     dword ptr [rax+rax+00h]
0x180024e93  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x180024e97  mov     edi, 2
0x180024e9c  mov     r9d, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x180024ea3  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x180024ea7  mov     eax, [rbp+57h+InterfaceIndex]
0x180024eaa  mov     [rbp+57h+Row.InterfaceIndex], eax
0x180024ead  mov     word ptr [rbp+57h+Row.Address], di
0x180024eb1  mov     [rbp+57h+Row.OnLinkPrefixLength], 18h
0x180024eb5  mov     dword ptr [rbp+57h+Row.Address+4], r9d
0x180024eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ec0  cmp     rcx, r15
0x180024ec3  jz      short loc_180024EE0
0x180024ec5  test    [rcx+1Ch], r14d
0x180024ec9  jz      short loc_180024EE0
0x180024ecb  cmp     byte ptr [rcx+19h], 4
0x180024ecf  jb      short loc_180024EE0
0x180024ed1  mov     rcx, [rcx+10h]
0x180024ed5  lea     edx, [rdi+16h]
0x180024ed8  mov     r8, r12
0x180024edb  call    WPP_SF_d
0x180024ee0  lea     rcx, [rbp+57h+Row]; Row
0x180024ee4  call    cs:__imp_DeleteUnicastIpAddressEntry
0x180024eeb  nop     dword ptr [rax+rax+00h]
0x180024ef0  test    eax, eax
0x180024ef2  jz      short loc_180024F20
0x180024ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180024efb  cmp     rcx, r15
0x180024efe  jz      short loc_180024F20
0x180024f00  test    [rcx+1Ch], r14d
0x180024f04  jz      short loc_180024F20
0x180024f06  cmp     byte ptr [rcx+19h], 3
0x180024f0a  jb      short loc_180024F20
0x180024f0c  mov     rcx, [rcx+10h]
0x180024f10  mov     edx, 19h
0x180024f15  mov     r9d, eax
0x180024f18  mov     r8, r12
0x180024f1b  call    WPP_SF_d
0x180024f20  mov     rcx, qword ptr [rbp+57h+InterfaceLuid]; union _NET_LUID_LH
0x180024f24  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x180024f28  xor     edx, edx; unsigned int
0x180024f2a  call    ?SetDuplicateAddressDetectionTransmits@@YAKT_NET_LUID_LH@@KPEAK@Z; SetDuplicateAddressDetectionTransmits(_NET_LUID_LH,ulong,ulong *)
0x180024f2f  test    eax, eax
0x180024f31  jz      short loc_180024F61
0x180024f33  xor     esi, esi
0x180024f35  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f3c  cmp     rcx, r15
0x180024f3f  jz      short loc_180024F66
0x180024f41  test    [rcx+1Ch], r14d
0x180024f45  jz      short loc_180024F66
0x180024f47  cmp     [rcx+19h], dil
0x180024f4b  jb      short loc_180024F66
0x180024f4d  mov     rcx, [rcx+10h]
0x180024f51  lea     edx, [rsi+1Ah]
0x180024f54  mov     r9d, eax
0x180024f57  mov     r8, r12
0x180024f5a  call    WPP_SF_d
0x180024f5f  jmp     short loc_180024F66
0x180024f61  mov     esi, 1
0x180024f66  lea     rcx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180024f6a  call    ?TryAcquirePrivateIPAddress@SharedAccessUtils@@SAKAEAU_MIB_UNICASTIPADDRESS_ROW@@@Z; SharedAccessUtils::TryAcquirePrivateIPAddress(_MIB_UNICASTIPADDRESS_ROW &)
0x180024f6f  mov     ebx, eax
0x180024f71  test    eax, eax
0x180024f73  jnz     loc_18002504F
0x180024f79  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x180024f7c  lea     rcx, [rbp+57h+Row]; Row
0x180024f80  mov     cs:?DhcpAdapterIPAddress@@3KA, eax; ulong DhcpAdapterIPAddress
0x180024f86  call    cs:__imp_CreateUnicastIpAddressEntry
0x180024f8d  nop     dword ptr [rax+rax+00h]
0x180024f92  mov     ebx, eax
0x180024f94  test    eax, eax
0x180024f96  jz      short loc_180024FC6
0x180024f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f9f  cmp     rcx, r15
0x180024fa2  jz      loc_18002508A
0x180024fa8  test    [rcx+1Ch], r14d
0x180024fac  jz      loc_18002508A
0x180024fb2  cmp     [rcx+19h], dil
0x180024fb6  jb      loc_18002508A
0x180024fbc  mov     edx, 1Bh
0x180024fc1  jmp     loc_18002506C
0x180024fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fcd  cmp     rcx, r15
0x180024fd0  jz      short loc_180024FF6
0x180024fd2  test    [rcx+1Ch], r14d
0x180024fd6  jz      short loc_180024FF6
0x180024fd8  cmp     byte ptr [rcx+19h], 5
0x180024fdc  jb      short loc_180024FF6
0x180024fde  mov     r9d, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x180024fe5  mov     edx, 1Ch
0x180024fea  mov     rcx, [rcx+10h]
0x180024fee  mov     r8, r12
0x180024ff1  call    WPP_SF_d
0x180024ff6  lea     r8, [rbp+57h+var_B0]; bool *
0x180024ffa  mov     [rbp+57h+var_B0], 1
0x180024ffe  lea     rdx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180025002  lea     rcx, ?DhcpAdapterGuid@@3U_GUID@@A; struct _GUID *
0x180025009  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x18002500e  test    eax, eax
0x180025010  jz      short loc_180025083
0x180025012  mov     rcx, cs:WPP_GLOBAL_Control
0x180025019  cmp     rcx, r15
0x18002501c  jz      short loc_18002508A
0x18002501e  test    [rcx+1Ch], r14d
0x180025022  jz      short loc_18002508A
0x180025024  cmp     [rcx+19h], dil
0x180025028  jb      short loc_18002508A
0x18002502a  mov     rcx, [rcx+10h]
0x18002502e  lea     r9, ?DhcpAdapterGuid@@3U_GUID@@A; _GUID DhcpAdapterGuid
0x180025035  mov     [rsp+0E0h+var_B8], eax
0x180025039  mov     edx, 1Dh
0x18002503e  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x180025041  mov     r8, r12
0x180025044  mov     [rsp+0E0h+var_C0], eax
0x180025048  call    WPP_SF__guid_DD
0x18002504d  jmp     short loc_180025083
0x18002504f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025056  cmp     rcx, r15
0x180025059  jz      short loc_18002508A
0x18002505b  test    [rcx+1Ch], r14d
0x18002505f  jz      short loc_18002508A
0x180025061  cmp     [rcx+19h], dil
0x180025065  jb      short loc_18002508A
0x180025067  mov     edx, 1Eh
0x18002506c  mov     r9d, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x180025073  mov     r8, r12
0x180025076  mov     rcx, [rcx+10h]
0x18002507a  mov     [rsp+0E0h+var_C0], eax
0x18002507e  call    WPP_SF_Dd
0x180025083  mov     rcx, cs:WPP_GLOBAL_Control
0x18002508a  test    esi, esi
0x18002508c  jz      short loc_1800250A4
0x18002508e  mov     edx, [rbp+57h+var_A8]; unsigned int
0x180025091  xor     r8d, r8d; unsigned int *
0x180025094  mov     rcx, qword ptr [rbp+57h+InterfaceLuid]; union _NET_LUID_LH
0x180025098  call    ?SetDuplicateAddressDetectionTransmits@@YAKT_NET_LUID_LH@@KPEAK@Z; SetDuplicateAddressDetectionTransmits(_NET_LUID_LH,ulong,ulong *)
0x18002509d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250a4  cmp     rcx, r15
0x1800250a7  jz      short loc_1800250D0
0x1800250a9  test    [rcx+1Ch], r14d
0x1800250ad  jz      short loc_1800250D0
0x1800250af  cmp     byte ptr [rcx+19h], 6
0x1800250b3  jb      short loc_1800250D0
0x1800250b5  mov     eax, [rbp+57h+InterfaceIndex]
0x1800250b8  mov     edx, 1Fh
0x1800250bd  mov     rcx, [rcx+10h]
0x1800250c1  mov     r9d, ebx
0x1800250c4  mov     r8, r12
0x1800250c7  mov     [rsp+0E0h+var_C0], eax
0x1800250cb  call    WPP_SF_Dd
0x1800250d0  mov     eax, ebx
0x1800250d2  mov     rcx, [rbp+57h+var_40]
0x1800250d6  xor     rcx, rsp; StackCookie
0x1800250d9  call    __security_check_cookie
0x1800250de  add     rsp, 0B0h
0x1800250e5  pop     r15
0x1800250e7  pop     r14
0x1800250e9  pop     r12
0x1800250eb  pop     rdi
0x1800250ec  pop     rsi
0x1800250ed  pop     rbx
0x1800250ee  pop     rbp
0x1800250ef  retn
```
