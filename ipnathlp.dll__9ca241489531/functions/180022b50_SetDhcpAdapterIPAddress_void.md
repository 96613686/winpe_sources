# SetDhcpAdapterIPAddress(void)

- ea: `0x180022b50`
- end: `0x180022ed2`
- name: `?SetDhcpAdapterIPAddress@@YAKXZ`
- size: `898`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180022ed8`

## callees

- `0x18000c750`
- `0x18001ec08`
- `0x180022b50`
- `0x1800332ac`
- `0x18004c068`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180069cdc`
- `0x1800715b4`
- `0x180071d38`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180022c3d`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180022c3d`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180022be9`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180022be9`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x180022d6e`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x180022d6e`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180022cd2`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180022cd2`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180022c7b`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180022c7b`

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
0x180022b50  push    rbp
0x180022b52  push    rbx
0x180022b53  push    rsi
0x180022b54  push    rdi
0x180022b55  push    r12
0x180022b57  push    r14
0x180022b59  push    r15
0x180022b5b  lea     rbp, [rsp-27h]
0x180022b60  sub     rsp, 0B0h
0x180022b67  mov     rax, cs:__security_cookie
0x180022b6e  xor     rax, rsp
0x180022b71  mov     [rbp+57h+var_40], rax
0x180022b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b7c  lea     r15, WPP_GLOBAL_Control
0x180022b83  lea     r12, WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids
0x180022b8a  mov     r14d, 200h
0x180022b90  cmp     rcx, r15
0x180022b93  jz      short loc_180022BB9
0x180022b95  test    [rcx+1Ch], r14d
0x180022b99  jz      short loc_180022BB9
0x180022b9b  cmp     byte ptr [rcx+19h], 6
0x180022b9f  jb      short loc_180022BB9
0x180022ba1  mov     rcx, [rcx+10h]
0x180022ba5  lea     r9, ?DhcpAdapterGuid@@3U_GUID@@A; _GUID DhcpAdapterGuid
0x180022bac  mov     edx, 15h
0x180022bb1  mov     r8, r12
0x180022bb4  call    WPP_SF__guid_
0x180022bb9  xor     edx, edx; Val
0x180022bbb  mov     [rbp+57h+InterfaceIndex], 0FFFFFFFFh
0x180022bc2  lea     rcx, [rbp+57h+Row]; void *
0x180022bc6  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x180022bce  lea     r8d, [rdx+50h]; Size
0x180022bd2  call    memset_0
0x180022bd7  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180022bdb  mov     [rbp+57h+var_A8], 0
0x180022be2  lea     rcx, ?DhcpAdapterGuid@@3U_GUID@@A; InterfaceGuid
0x180022be9  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180022bef  mov     ebx, eax
0x180022bf1  test    eax, eax
0x180022bf3  jz      short loc_180022C35
0x180022bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bfc  cmp     rcx, r15
0x180022bff  jz      loc_180022EB2
0x180022c05  test    [rcx+1Ch], r14d
0x180022c09  jz      loc_180022E86
0x180022c0f  mov     edi, 2
0x180022c14  cmp     [rcx+19h], dil
0x180022c18  jb      loc_180022E86
0x180022c1e  lea     edx, [rdi+14h]
0x180022c21  mov     rcx, [rcx+10h]
0x180022c25  mov     r9d, eax
0x180022c28  mov     r8, r12
0x180022c2b  call    WPP_SF_d
0x180022c30  jmp     loc_180022E7F
0x180022c35  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x180022c39  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180022c3d  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180022c43  mov     ebx, eax
0x180022c45  test    eax, eax
0x180022c47  jz      short loc_180022C77
0x180022c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c50  cmp     rcx, r15
0x180022c53  jz      loc_180022EB2
0x180022c59  test    [rcx+1Ch], r14d
0x180022c5d  jz      loc_180022E86
0x180022c63  mov     edi, 2
0x180022c68  cmp     [rcx+19h], dil
0x180022c6c  jb      loc_180022E86
0x180022c72  lea     edx, [rdi+15h]
0x180022c75  jmp     short loc_180022C21
0x180022c77  lea     rcx, [rbp+57h+Row]; Row
0x180022c7b  call    cs:__imp_InitializeUnicastIpAddressEntry
0x180022c81  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x180022c85  mov     edi, 2
0x180022c8a  mov     r9d, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x180022c91  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x180022c95  mov     eax, [rbp+57h+InterfaceIndex]
0x180022c98  mov     [rbp+57h+Row.InterfaceIndex], eax
0x180022c9b  mov     word ptr [rbp+57h+Row.Address], di
0x180022c9f  mov     [rbp+57h+Row.OnLinkPrefixLength], 18h
0x180022ca3  mov     dword ptr [rbp+57h+Row.Address+4], r9d
0x180022ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cae  cmp     rcx, r15
0x180022cb1  jz      short loc_180022CCE
0x180022cb3  test    [rcx+1Ch], r14d
0x180022cb7  jz      short loc_180022CCE
0x180022cb9  cmp     byte ptr [rcx+19h], 4
0x180022cbd  jb      short loc_180022CCE
0x180022cbf  mov     rcx, [rcx+10h]
0x180022cc3  lea     edx, [rdi+16h]
0x180022cc6  mov     r8, r12
0x180022cc9  call    WPP_SF_d
0x180022cce  lea     rcx, [rbp+57h+Row]; Row
0x180022cd2  call    cs:__imp_DeleteUnicastIpAddressEntry
0x180022cd8  test    eax, eax
0x180022cda  jz      short loc_180022D08
0x180022cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ce3  cmp     rcx, r15
0x180022ce6  jz      short loc_180022D08
0x180022ce8  test    [rcx+1Ch], r14d
0x180022cec  jz      short loc_180022D08
0x180022cee  cmp     byte ptr [rcx+19h], 3
0x180022cf2  jb      short loc_180022D08
0x180022cf4  mov     rcx, [rcx+10h]
0x180022cf8  mov     edx, 19h
0x180022cfd  mov     r9d, eax
0x180022d00  mov     r8, r12
0x180022d03  call    WPP_SF_d
0x180022d08  mov     rcx, qword ptr [rbp+57h+InterfaceLuid]; union _NET_LUID_LH
0x180022d0c  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x180022d10  xor     edx, edx; unsigned int
0x180022d12  call    ?SetDuplicateAddressDetectionTransmits@@YAKT_NET_LUID_LH@@KPEAK@Z; SetDuplicateAddressDetectionTransmits(_NET_LUID_LH,ulong,ulong *)
0x180022d17  test    eax, eax
0x180022d19  jz      short loc_180022D49
0x180022d1b  xor     esi, esi
0x180022d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d24  cmp     rcx, r15
0x180022d27  jz      short loc_180022D4E
0x180022d29  test    [rcx+1Ch], r14d
0x180022d2d  jz      short loc_180022D4E
0x180022d2f  cmp     [rcx+19h], dil
0x180022d33  jb      short loc_180022D4E
0x180022d35  mov     rcx, [rcx+10h]
0x180022d39  lea     edx, [rsi+1Ah]
0x180022d3c  mov     r9d, eax
0x180022d3f  mov     r8, r12
0x180022d42  call    WPP_SF_d
0x180022d47  jmp     short loc_180022D4E
0x180022d49  mov     esi, 1
0x180022d4e  lea     rcx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180022d52  call    ?TryAcquirePrivateIPAddress@SharedAccessUtils@@SAKAEAU_MIB_UNICASTIPADDRESS_ROW@@@Z; SharedAccessUtils::TryAcquirePrivateIPAddress(_MIB_UNICASTIPADDRESS_ROW &)
0x180022d57  mov     ebx, eax
0x180022d59  test    eax, eax
0x180022d5b  jnz     loc_180022E31
0x180022d61  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x180022d64  lea     rcx, [rbp+57h+Row]; Row
0x180022d68  mov     cs:?DhcpAdapterIPAddress@@3KA, eax; ulong DhcpAdapterIPAddress
0x180022d6e  call    cs:__imp_CreateUnicastIpAddressEntry
0x180022d74  mov     ebx, eax
0x180022d76  test    eax, eax
0x180022d78  jz      short loc_180022DA8
0x180022d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d81  cmp     rcx, r15
0x180022d84  jz      loc_180022E6C
0x180022d8a  test    [rcx+1Ch], r14d
0x180022d8e  jz      loc_180022E6C
0x180022d94  cmp     [rcx+19h], dil
0x180022d98  jb      loc_180022E6C
0x180022d9e  mov     edx, 1Bh
0x180022da3  jmp     loc_180022E4E
0x180022da8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022daf  cmp     rcx, r15
0x180022db2  jz      short loc_180022DD8
0x180022db4  test    [rcx+1Ch], r14d
0x180022db8  jz      short loc_180022DD8
0x180022dba  cmp     byte ptr [rcx+19h], 5
0x180022dbe  jb      short loc_180022DD8
0x180022dc0  mov     r9d, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x180022dc7  mov     edx, 1Ch
0x180022dcc  mov     rcx, [rcx+10h]
0x180022dd0  mov     r8, r12
0x180022dd3  call    WPP_SF_d
0x180022dd8  lea     r8, [rbp+57h+var_B0]; bool *
0x180022ddc  mov     [rbp+57h+var_B0], 1
0x180022de0  lea     rdx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180022de4  lea     rcx, ?DhcpAdapterGuid@@3U_GUID@@A; struct _GUID *
0x180022deb  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x180022df0  test    eax, eax
0x180022df2  jz      short loc_180022E65
0x180022df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dfb  cmp     rcx, r15
0x180022dfe  jz      short loc_180022E6C
0x180022e00  test    [rcx+1Ch], r14d
0x180022e04  jz      short loc_180022E6C
0x180022e06  cmp     [rcx+19h], dil
0x180022e0a  jb      short loc_180022E6C
0x180022e0c  mov     rcx, [rcx+10h]
0x180022e10  lea     r9, ?DhcpAdapterGuid@@3U_GUID@@A; _GUID DhcpAdapterGuid
0x180022e17  mov     [rsp+0E0h+var_B8], eax
0x180022e1b  mov     edx, 1Dh
0x180022e20  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x180022e23  mov     r8, r12
0x180022e26  mov     [rsp+0E0h+var_C0], eax
0x180022e2a  call    WPP_SF__guid_DD
0x180022e2f  jmp     short loc_180022E65
0x180022e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e38  cmp     rcx, r15
0x180022e3b  jz      short loc_180022E6C
0x180022e3d  test    [rcx+1Ch], r14d
0x180022e41  jz      short loc_180022E6C
0x180022e43  cmp     [rcx+19h], dil
0x180022e47  jb      short loc_180022E6C
0x180022e49  mov     edx, 1Eh
0x180022e4e  mov     r9d, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x180022e55  mov     r8, r12
0x180022e58  mov     rcx, [rcx+10h]
0x180022e5c  mov     [rsp+0E0h+var_C0], eax
0x180022e60  call    WPP_SF_Dd
0x180022e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e6c  test    esi, esi
0x180022e6e  jz      short loc_180022E86
0x180022e70  mov     edx, [rbp+57h+var_A8]; unsigned int
0x180022e73  xor     r8d, r8d; unsigned int *
0x180022e76  mov     rcx, qword ptr [rbp+57h+InterfaceLuid]; union _NET_LUID_LH
0x180022e7a  call    ?SetDuplicateAddressDetectionTransmits@@YAKT_NET_LUID_LH@@KPEAK@Z; SetDuplicateAddressDetectionTransmits(_NET_LUID_LH,ulong,ulong *)
0x180022e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e86  cmp     rcx, r15
0x180022e89  jz      short loc_180022EB2
0x180022e8b  test    [rcx+1Ch], r14d
0x180022e8f  jz      short loc_180022EB2
0x180022e91  cmp     byte ptr [rcx+19h], 6
0x180022e95  jb      short loc_180022EB2
0x180022e97  mov     eax, [rbp+57h+InterfaceIndex]
0x180022e9a  mov     edx, 1Fh
0x180022e9f  mov     rcx, [rcx+10h]
0x180022ea3  mov     r9d, ebx
0x180022ea6  mov     r8, r12
0x180022ea9  mov     [rsp+0E0h+var_C0], eax
0x180022ead  call    WPP_SF_Dd
0x180022eb2  mov     eax, ebx
0x180022eb4  mov     rcx, [rbp+57h+var_40]
0x180022eb8  xor     rcx, rsp; StackCookie
0x180022ebb  call    __security_check_cookie
0x180022ec0  add     rsp, 0B0h
0x180022ec7  pop     r15
0x180022ec9  pop     r14
0x180022ecb  pop     r12
0x180022ecd  pop     rdi
0x180022ece  pop     rsi
0x180022ecf  pop     rbx
0x180022ed0  pop     rbp
0x180022ed1  retn
```
