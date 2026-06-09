# V2SetDhcpAdapterIPAddress(_V2_DHCP_INTERFACE_INFO *)

- ea: `0x180021f28`
- end: `0x1800222b2`
- name: `?V2SetDhcpAdapterIPAddress@@YAKPEAU_V2_DHCP_INTERFACE_INFO@@@Z`
- size: `906`
- prototype: `unsigned int __fastcall(struct _V2_DHCP_INTERFACE_INFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800237ec`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18001ec08`
- `0x180021f28`
- `0x180040590`
- `0x18004c068`
- `0x18004e0c0`
- `0x18004ed64`
- `0x1800715b4`
- `0x180071d38`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180022014`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180022014`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180021fbc`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180021fbc`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x180022150`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x180022150`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x1800220ac`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x1800220ac`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180022052`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180022052`

## pseudocode

```c
__int64 __fastcall V2SetDhcpAdapterIPAddress(struct _V2_DHCP_INTERFACE_INFO *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  unsigned int v7; // eax
  unsigned int v8; // eax
  int v9; // r14d
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  bool v14; // [rsp+30h] [rbp-69h] BYREF
  ULONG InterfaceIndex; // [rsp+34h] [rbp-65h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-61h] BYREF
  NET_LUID InterfaceLuid; // [rsp+40h] [rbp-59h] BYREF
  _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+50h] [rbp-49h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids);
  }
  InterfaceIndex = -1;
  InterfaceLuid.Value = 0;
  memset_0(&Row, 0, sizeof(Row));
  v16 = 0;
  v2 = ConvertInterfaceGuidToLuid((const GUID *)((char *)a1 + 24), &InterfaceLuid);
  v3 = v2;
  if ( !v2 )
  {
    v2 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
    v3 = v2;
    if ( v2 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v3;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_55;
      v5 = 18;
      goto LABEL_10;
    }
    InitializeUnicastIpAddressEntry(&Row);
    v6 = *((unsigned int *)a1 + 3);
    Row.InterfaceLuid = InterfaceLuid;
    Row.InterfaceIndex = InterfaceIndex;
    Row.OnLinkPrefixLength = *((_BYTE *)a1 + 40);
    Row.Address.Ipv4.sin_family = 2;
    Row.Address.Ipv4.sin_addr.S_un.S_addr = v6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, v6);
    }
    v7 = DeleteUnicastIpAddressEntry(&Row);
    if ( v7
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, v7);
    }
    v8 = V2SetDuplicateAddressDetectionTransmits(InterfaceLuid, 0, &v16);
    if ( v8 )
    {
      v9 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, v8);
      }
    }
    else
    {
      v9 = 1;
    }
    v10 = SharedAccessUtils::TryAcquirePrivateIPAddress(&Row);
    v3 = v10;
    if ( v10 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 25;
        goto LABEL_50;
      }
    }
    else
    {
      *((_DWORD *)a1 + 3) = Row.Address.Ipv4.sin_addr.S_un.S_addr;
      v10 = CreateUnicastIpAddressEntry(&Row);
      v3 = v10;
      if ( v10 )
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 22;
LABEL_50:
          WPP_SF_Dd(v4[2], v11, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, *((unsigned int *)a1 + 3), v10);
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
            23,
            WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids,
            *((unsigned int *)a1 + 3));
        }
        v14 = 1;
        v12 = SharedAccessUtils::TryPublishWnfStateData((const struct _GUID *)((char *)a1 + 24), &Row, &v14);
        if ( !v12 )
          goto LABEL_51;
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF__guid_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids,
            (char *)a1 + 24,
            Row.Address.Ipv4.sin_addr.S_un.S_addr,
            v12);
LABEL_51:
          v4 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
    if ( v9 )
    {
      V2SetDuplicateAddressDetectionTransmits(InterfaceLuid, v16, 0);
      goto LABEL_54;
    }
    goto LABEL_55;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 17;
LABEL_10:
    WPP_SF_d(v4[2], v5, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, v2);
LABEL_54:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_55:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 26, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180021f28  push    rbp
0x180021f2a  push    rbx
0x180021f2b  push    rsi
0x180021f2c  push    rdi
0x180021f2d  push    r12
0x180021f2f  push    r13
0x180021f31  push    r14
0x180021f33  push    r15
0x180021f35  lea     rbp, [rsp-1Fh]
0x180021f3a  sub     rsp, 0B8h
0x180021f41  mov     rax, cs:__security_cookie
0x180021f48  xor     rax, rsp
0x180021f4b  mov     [rbp+57h+var_50], rax
0x180021f4f  mov     rsi, rcx
0x180021f52  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f59  lea     r13, WPP_GLOBAL_Control
0x180021f60  mov     r12d, 200h
0x180021f66  cmp     rcx, r13
0x180021f69  jz      short loc_180021F8C
0x180021f6b  test    [rcx+1Ch], r12d
0x180021f6f  jz      short loc_180021F8C
0x180021f71  cmp     byte ptr [rcx+19h], 6
0x180021f75  jb      short loc_180021F8C
0x180021f77  mov     rcx, [rcx+10h]
0x180021f7b  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180021f82  mov     edx, 10h
0x180021f87  call    WPP_SF_
0x180021f8c  xor     edx, edx; Val
0x180021f8e  mov     [rbp+57h+InterfaceIndex], 0FFFFFFFFh
0x180021f95  lea     rcx, [rbp+57h+Row]; void *
0x180021f99  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x180021fa1  lea     r8d, [rdx+50h]; Size
0x180021fa5  call    memset_0
0x180021faa  lea     r15, [rsi+18h]
0x180021fae  mov     [rbp+57h+var_B8], 0
0x180021fb5  mov     rcx, r15; InterfaceGuid
0x180021fb8  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180021fbc  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180021fc2  mov     ebx, eax
0x180021fc4  test    eax, eax
0x180021fc6  jz      short loc_18002200C
0x180021fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fcf  cmp     rcx, r13
0x180021fd2  jz      loc_180022290
0x180021fd8  test    [rcx+1Ch], r12d
0x180021fdc  jz      loc_180022267
0x180021fe2  mov     edi, 2
0x180021fe7  cmp     [rcx+19h], dil
0x180021feb  jb      loc_180022267
0x180021ff1  lea     edx, [rdi+0Fh]
0x180021ff4  mov     rcx, [rcx+10h]
0x180021ff8  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180021fff  mov     r9d, eax
0x180022002  call    WPP_SF_d
0x180022007  jmp     loc_180022260
0x18002200c  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x180022010  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180022014  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18002201a  mov     ebx, eax
0x18002201c  test    eax, eax
0x18002201e  jz      short loc_18002204E
0x180022020  mov     rcx, cs:WPP_GLOBAL_Control
0x180022027  cmp     rcx, r13
0x18002202a  jz      loc_180022290
0x180022030  test    [rcx+1Ch], r12d
0x180022034  jz      loc_180022267
0x18002203a  mov     edi, 2
0x18002203f  cmp     [rcx+19h], dil
0x180022043  jb      loc_180022267
0x180022049  lea     edx, [rdi+10h]
0x18002204c  jmp     short loc_180021FF4
0x18002204e  lea     rcx, [rbp+57h+Row]; Row
0x180022052  call    cs:__imp_InitializeUnicastIpAddressEntry
0x180022058  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x18002205c  mov     edi, 2
0x180022061  mov     r9d, [rsi+0Ch]
0x180022065  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x180022069  mov     eax, [rbp+57h+InterfaceIndex]
0x18002206c  mov     [rbp+57h+Row.InterfaceIndex], eax
0x18002206f  mov     al, [rsi+28h]
0x180022072  mov     [rbp+57h+Row.OnLinkPrefixLength], al
0x180022075  mov     word ptr [rbp+57h+Row.Address], di
0x180022079  mov     dword ptr [rbp+57h+Row.Address+4], r9d
0x18002207d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022084  cmp     rcx, r13
0x180022087  jz      short loc_1800220A8
0x180022089  test    [rcx+1Ch], r12d
0x18002208d  jz      short loc_1800220A8
0x18002208f  cmp     byte ptr [rcx+19h], 4
0x180022093  jb      short loc_1800220A8
0x180022095  mov     rcx, [rcx+10h]
0x180022099  lea     edx, [rdi+11h]
0x18002209c  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x1800220a3  call    WPP_SF_d
0x1800220a8  lea     rcx, [rbp+57h+Row]; Row
0x1800220ac  call    cs:__imp_DeleteUnicastIpAddressEntry
0x1800220b2  test    eax, eax
0x1800220b4  jz      short loc_1800220E6
0x1800220b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220bd  cmp     rcx, r13
0x1800220c0  jz      short loc_1800220E6
0x1800220c2  test    [rcx+1Ch], r12d
0x1800220c6  jz      short loc_1800220E6
0x1800220c8  cmp     byte ptr [rcx+19h], 3
0x1800220cc  jb      short loc_1800220E6
0x1800220ce  mov     rcx, [rcx+10h]
0x1800220d2  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x1800220d9  mov     edx, 14h
0x1800220de  mov     r9d, eax
0x1800220e1  call    WPP_SF_d
0x1800220e6  mov     rcx, qword ptr [rbp+57h+InterfaceLuid]; union _NET_LUID_LH
0x1800220ea  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x1800220ee  xor     edx, edx; unsigned int
0x1800220f0  call    ?V2SetDuplicateAddressDetectionTransmits@@YAKT_NET_LUID_LH@@KPEAK@Z; V2SetDuplicateAddressDetectionTransmits(_NET_LUID_LH,ulong,ulong *)
0x1800220f5  test    eax, eax
0x1800220f7  jz      short loc_18002212D
0x1800220f9  xor     r14d, r14d
0x1800220fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022103  cmp     rcx, r13
0x180022106  jz      short loc_180022133
0x180022108  test    [rcx+1Ch], r12d
0x18002210c  jz      short loc_180022133
0x18002210e  cmp     [rcx+19h], dil
0x180022112  jb      short loc_180022133
0x180022114  mov     rcx, [rcx+10h]
0x180022118  lea     edx, [r14+15h]
0x18002211c  mov     r9d, eax
0x18002211f  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180022126  call    WPP_SF_d
0x18002212b  jmp     short loc_180022133
0x18002212d  mov     r14d, 1
0x180022133  lea     rcx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180022137  call    ?TryAcquirePrivateIPAddress@SharedAccessUtils@@SAKAEAU_MIB_UNICASTIPADDRESS_ROW@@@Z; SharedAccessUtils::TryAcquirePrivateIPAddress(_MIB_UNICASTIPADDRESS_ROW &)
0x18002213c  mov     ebx, eax
0x18002213e  test    eax, eax
0x180022140  jnz     loc_180022210
0x180022146  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x180022149  lea     rcx, [rbp+57h+Row]; Row
0x18002214d  mov     [rsi+0Ch], eax
0x180022150  call    cs:__imp_CreateUnicastIpAddressEntry
0x180022156  mov     ebx, eax
0x180022158  test    eax, eax
0x18002215a  jz      short loc_18002218A
0x18002215c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022163  cmp     rcx, r13
0x180022166  jz      loc_18002224C
0x18002216c  test    [rcx+1Ch], r12d
0x180022170  jz      loc_18002224C
0x180022176  cmp     [rcx+19h], dil
0x18002217a  jb      loc_18002224C
0x180022180  mov     edx, 16h
0x180022185  jmp     loc_18002222D
0x18002218a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022191  cmp     rcx, r13
0x180022194  jz      short loc_1800221BB
0x180022196  test    [rcx+1Ch], r12d
0x18002219a  jz      short loc_1800221BB
0x18002219c  cmp     byte ptr [rcx+19h], 5
0x1800221a0  jb      short loc_1800221BB
0x1800221a2  mov     r9d, [rsi+0Ch]
0x1800221a6  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x1800221ad  mov     rcx, [rcx+10h]
0x1800221b1  mov     edx, 17h
0x1800221b6  call    WPP_SF_d
0x1800221bb  lea     r8, [rbp+57h+var_C0]; bool *
0x1800221bf  mov     [rbp+57h+var_C0], 1
0x1800221c3  lea     rdx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x1800221c7  mov     rcx, r15; struct _GUID *
0x1800221ca  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x1800221cf  test    eax, eax
0x1800221d1  jz      short loc_180022245
0x1800221d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221da  cmp     rcx, r13
0x1800221dd  jz      short loc_18002224C
0x1800221df  test    [rcx+1Ch], r12d
0x1800221e3  jz      short loc_18002224C
0x1800221e5  cmp     [rcx+19h], dil
0x1800221e9  jb      short loc_18002224C
0x1800221eb  mov     rcx, [rcx+10h]
0x1800221ef  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x1800221f6  mov     [rsp+0F0h+var_C8], eax
0x1800221fa  mov     edx, 18h
0x1800221ff  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x180022202  mov     r9, r15
0x180022205  mov     [rsp+0F0h+var_D0], eax
0x180022209  call    WPP_SF__guid_DD
0x18002220e  jmp     short loc_180022245
0x180022210  mov     rcx, cs:WPP_GLOBAL_Control
0x180022217  cmp     rcx, r13
0x18002221a  jz      short loc_18002224C
0x18002221c  test    [rcx+1Ch], r12d
0x180022220  jz      short loc_18002224C
0x180022222  cmp     [rcx+19h], dil
0x180022226  jb      short loc_18002224C
0x180022228  mov     edx, 19h
0x18002222d  mov     r9d, [rsi+0Ch]
0x180022231  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180022238  mov     rcx, [rcx+10h]
0x18002223c  mov     [rsp+0F0h+var_D0], eax
0x180022240  call    WPP_SF_Dd
0x180022245  mov     rcx, cs:WPP_GLOBAL_Control
0x18002224c  test    r14d, r14d
0x18002224f  jz      short loc_180022267
0x180022251  mov     edx, [rbp+57h+var_B8]; unsigned int
0x180022254  xor     r8d, r8d; unsigned int *
0x180022257  mov     rcx, qword ptr [rbp+57h+InterfaceLuid]; union _NET_LUID_LH
0x18002225b  call    ?V2SetDuplicateAddressDetectionTransmits@@YAKT_NET_LUID_LH@@KPEAK@Z; V2SetDuplicateAddressDetectionTransmits(_NET_LUID_LH,ulong,ulong *)
0x180022260  mov     rcx, cs:WPP_GLOBAL_Control
0x180022267  cmp     rcx, r13
0x18002226a  jz      short loc_180022290
0x18002226c  test    [rcx+1Ch], r12d
0x180022270  jz      short loc_180022290
0x180022272  cmp     byte ptr [rcx+19h], 6
0x180022276  jb      short loc_180022290
0x180022278  mov     rcx, [rcx+10h]
0x18002227c  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180022283  mov     edx, 1Ah
0x180022288  mov     r9d, ebx
0x18002228b  call    WPP_SF_d
0x180022290  mov     eax, ebx
0x180022292  mov     rcx, [rbp+57h+var_50]
0x180022296  xor     rcx, rsp; StackCookie
0x180022299  call    __security_check_cookie
0x18002229e  add     rsp, 0B8h
0x1800222a5  pop     r15
0x1800222a7  pop     r14
0x1800222a9  pop     r13
0x1800222ab  pop     r12
0x1800222ad  pop     rdi
0x1800222ae  pop     rsi
0x1800222af  pop     rbx
0x1800222b0  pop     rbp
0x1800222b1  retn
```
