# V2SetDhcpAdapterIPAddress(_V2_DHCP_INTERFACE_INFO *)

- ea: `0x1800240d4`
- end: `0x18002447d`
- name: `?V2SetDhcpAdapterIPAddress@@YAKPEAU_V2_DHCP_INTERFACE_INFO@@@Z`
- size: `937`
- prototype: `unsigned int __fastcall(struct _V2_DHCP_INTERFACE_INFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180025c54`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800202e0`
- `0x1800240d4`
- `0x180043eac`
- `0x18004fd9c`
- `0x180051f30`
- `0x180052bf4`
- `0x180077008`
- `0x1800777ec`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1800241c6`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1800241c6`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180024168`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180024168`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x180024314`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x180024314`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18002426a`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18002426a`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18002420a`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18002420a`

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
0x1800240d4  push    rbp
0x1800240d6  push    rbx
0x1800240d7  push    rsi
0x1800240d8  push    rdi
0x1800240d9  push    r12
0x1800240db  push    r13
0x1800240dd  push    r14
0x1800240df  push    r15
0x1800240e1  lea     rbp, [rsp-1Fh]
0x1800240e6  sub     rsp, 0B8h
0x1800240ed  mov     rax, cs:__security_cookie
0x1800240f4  xor     rax, rsp
0x1800240f7  mov     [rbp+57h+var_50], rax
0x1800240fb  mov     rsi, rcx
0x1800240fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180024105  lea     r13, WPP_GLOBAL_Control
0x18002410c  mov     r12d, 200h
0x180024112  cmp     rcx, r13
0x180024115  jz      short loc_180024138
0x180024117  test    [rcx+1Ch], r12d
0x18002411b  jz      short loc_180024138
0x18002411d  cmp     byte ptr [rcx+19h], 6
0x180024121  jb      short loc_180024138
0x180024123  mov     rcx, [rcx+10h]
0x180024127  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x18002412e  mov     edx, 10h
0x180024133  call    WPP_SF_
0x180024138  xor     edx, edx; Val
0x18002413a  mov     [rbp+57h+InterfaceIndex], 0FFFFFFFFh
0x180024141  lea     rcx, [rbp+57h+Row]; void *
0x180024145  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x18002414d  lea     r8d, [rdx+50h]; Size
0x180024151  call    memset_0
0x180024156  lea     r15, [rsi+18h]
0x18002415a  mov     [rbp+57h+var_B8], 0
0x180024161  mov     rcx, r15; InterfaceGuid
0x180024164  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180024168  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18002416f  nop     dword ptr [rax+rax+00h]
0x180024174  mov     ebx, eax
0x180024176  test    eax, eax
0x180024178  jz      short loc_1800241BE
0x18002417a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024181  cmp     rcx, r13
0x180024184  jz      loc_18002445A
0x18002418a  test    [rcx+1Ch], r12d
0x18002418e  jz      loc_180024431
0x180024194  mov     edi, 2
0x180024199  cmp     [rcx+19h], dil
0x18002419d  jb      loc_180024431
0x1800241a3  lea     edx, [rdi+0Fh]
0x1800241a6  mov     rcx, [rcx+10h]
0x1800241aa  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x1800241b1  mov     r9d, eax
0x1800241b4  call    WPP_SF_d
0x1800241b9  jmp     loc_18002442A
0x1800241be  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x1800241c2  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x1800241c6  call    cs:__imp_ConvertInterfaceLuidToIndex
0x1800241cd  nop     dword ptr [rax+rax+00h]
0x1800241d2  mov     ebx, eax
0x1800241d4  test    eax, eax
0x1800241d6  jz      short loc_180024206
0x1800241d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241df  cmp     rcx, r13
0x1800241e2  jz      loc_18002445A
0x1800241e8  test    [rcx+1Ch], r12d
0x1800241ec  jz      loc_180024431
0x1800241f2  mov     edi, 2
0x1800241f7  cmp     [rcx+19h], dil
0x1800241fb  jb      loc_180024431
0x180024201  lea     edx, [rdi+10h]
0x180024204  jmp     short loc_1800241A6
0x180024206  lea     rcx, [rbp+57h+Row]; Row
0x18002420a  call    cs:__imp_InitializeUnicastIpAddressEntry
0x180024211  nop     dword ptr [rax+rax+00h]
0x180024216  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x18002421a  mov     edi, 2
0x18002421f  mov     r9d, [rsi+0Ch]
0x180024223  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x180024227  mov     eax, [rbp+57h+InterfaceIndex]
0x18002422a  mov     [rbp+57h+Row.InterfaceIndex], eax
0x18002422d  mov     al, [rsi+28h]
0x180024230  mov     [rbp+57h+Row.OnLinkPrefixLength], al
0x180024233  mov     word ptr [rbp+57h+Row.Address], di
0x180024237  mov     dword ptr [rbp+57h+Row.Address+4], r9d
0x18002423b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024242  cmp     rcx, r13
0x180024245  jz      short loc_180024266
0x180024247  test    [rcx+1Ch], r12d
0x18002424b  jz      short loc_180024266
0x18002424d  cmp     byte ptr [rcx+19h], 4
0x180024251  jb      short loc_180024266
0x180024253  mov     rcx, [rcx+10h]
0x180024257  lea     edx, [rdi+11h]
0x18002425a  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180024261  call    WPP_SF_d
0x180024266  lea     rcx, [rbp+57h+Row]; Row
0x18002426a  call    cs:__imp_DeleteUnicastIpAddressEntry
0x180024271  nop     dword ptr [rax+rax+00h]
0x180024276  test    eax, eax
0x180024278  jz      short loc_1800242AA
0x18002427a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024281  cmp     rcx, r13
0x180024284  jz      short loc_1800242AA
0x180024286  test    [rcx+1Ch], r12d
0x18002428a  jz      short loc_1800242AA
0x18002428c  cmp     byte ptr [rcx+19h], 3
0x180024290  jb      short loc_1800242AA
0x180024292  mov     rcx, [rcx+10h]
0x180024296  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x18002429d  mov     edx, 14h
0x1800242a2  mov     r9d, eax
0x1800242a5  call    WPP_SF_d
0x1800242aa  mov     rcx, qword ptr [rbp+57h+InterfaceLuid]; union _NET_LUID_LH
0x1800242ae  lea     r8, [rbp+57h+var_B8]; unsigned int *
0x1800242b2  xor     edx, edx; unsigned int
0x1800242b4  call    ?V2SetDuplicateAddressDetectionTransmits@@YAKT_NET_LUID_LH@@KPEAK@Z; V2SetDuplicateAddressDetectionTransmits(_NET_LUID_LH,ulong,ulong *)
0x1800242b9  test    eax, eax
0x1800242bb  jz      short loc_1800242F1
0x1800242bd  xor     r14d, r14d
0x1800242c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242c7  cmp     rcx, r13
0x1800242ca  jz      short loc_1800242F7
0x1800242cc  test    [rcx+1Ch], r12d
0x1800242d0  jz      short loc_1800242F7
0x1800242d2  cmp     [rcx+19h], dil
0x1800242d6  jb      short loc_1800242F7
0x1800242d8  mov     rcx, [rcx+10h]
0x1800242dc  lea     edx, [r14+15h]
0x1800242e0  mov     r9d, eax
0x1800242e3  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x1800242ea  call    WPP_SF_d
0x1800242ef  jmp     short loc_1800242F7
0x1800242f1  mov     r14d, 1
0x1800242f7  lea     rcx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x1800242fb  call    ?TryAcquirePrivateIPAddress@SharedAccessUtils@@SAKAEAU_MIB_UNICASTIPADDRESS_ROW@@@Z; SharedAccessUtils::TryAcquirePrivateIPAddress(_MIB_UNICASTIPADDRESS_ROW &)
0x180024300  mov     ebx, eax
0x180024302  test    eax, eax
0x180024304  jnz     loc_1800243DA
0x18002430a  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x18002430d  lea     rcx, [rbp+57h+Row]; Row
0x180024311  mov     [rsi+0Ch], eax
0x180024314  call    cs:__imp_CreateUnicastIpAddressEntry
0x18002431b  nop     dword ptr [rax+rax+00h]
0x180024320  mov     ebx, eax
0x180024322  test    eax, eax
0x180024324  jz      short loc_180024354
0x180024326  mov     rcx, cs:WPP_GLOBAL_Control
0x18002432d  cmp     rcx, r13
0x180024330  jz      loc_180024416
0x180024336  test    [rcx+1Ch], r12d
0x18002433a  jz      loc_180024416
0x180024340  cmp     [rcx+19h], dil
0x180024344  jb      loc_180024416
0x18002434a  mov     edx, 16h
0x18002434f  jmp     loc_1800243F7
0x180024354  mov     rcx, cs:WPP_GLOBAL_Control
0x18002435b  cmp     rcx, r13
0x18002435e  jz      short loc_180024385
0x180024360  test    [rcx+1Ch], r12d
0x180024364  jz      short loc_180024385
0x180024366  cmp     byte ptr [rcx+19h], 5
0x18002436a  jb      short loc_180024385
0x18002436c  mov     r9d, [rsi+0Ch]
0x180024370  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180024377  mov     rcx, [rcx+10h]
0x18002437b  mov     edx, 17h
0x180024380  call    WPP_SF_d
0x180024385  lea     r8, [rbp+57h+var_C0]; bool *
0x180024389  mov     [rbp+57h+var_C0], 1
0x18002438d  lea     rdx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180024391  mov     rcx, r15; struct _GUID *
0x180024394  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x180024399  test    eax, eax
0x18002439b  jz      short loc_18002440F
0x18002439d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243a4  cmp     rcx, r13
0x1800243a7  jz      short loc_180024416
0x1800243a9  test    [rcx+1Ch], r12d
0x1800243ad  jz      short loc_180024416
0x1800243af  cmp     [rcx+19h], dil
0x1800243b3  jb      short loc_180024416
0x1800243b5  mov     rcx, [rcx+10h]
0x1800243b9  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x1800243c0  mov     [rsp+0F0h+var_C8], eax
0x1800243c4  mov     edx, 18h
0x1800243c9  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x1800243cc  mov     r9, r15
0x1800243cf  mov     [rsp+0F0h+var_D0], eax
0x1800243d3  call    WPP_SF__guid_DD
0x1800243d8  jmp     short loc_18002440F
0x1800243da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243e1  cmp     rcx, r13
0x1800243e4  jz      short loc_180024416
0x1800243e6  test    [rcx+1Ch], r12d
0x1800243ea  jz      short loc_180024416
0x1800243ec  cmp     [rcx+19h], dil
0x1800243f0  jb      short loc_180024416
0x1800243f2  mov     edx, 19h
0x1800243f7  mov     r9d, [rsi+0Ch]
0x1800243fb  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180024402  mov     rcx, [rcx+10h]
0x180024406  mov     [rsp+0F0h+var_D0], eax
0x18002440a  call    WPP_SF_Dd
0x18002440f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024416  test    r14d, r14d
0x180024419  jz      short loc_180024431
0x18002441b  mov     edx, [rbp+57h+var_B8]; unsigned int
0x18002441e  xor     r8d, r8d; unsigned int *
0x180024421  mov     rcx, qword ptr [rbp+57h+InterfaceLuid]; union _NET_LUID_LH
0x180024425  call    ?V2SetDuplicateAddressDetectionTransmits@@YAKT_NET_LUID_LH@@KPEAK@Z; V2SetDuplicateAddressDetectionTransmits(_NET_LUID_LH,ulong,ulong *)
0x18002442a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024431  cmp     rcx, r13
0x180024434  jz      short loc_18002445A
0x180024436  test    [rcx+1Ch], r12d
0x18002443a  jz      short loc_18002445A
0x18002443c  cmp     byte ptr [rcx+19h], 6
0x180024440  jb      short loc_18002445A
0x180024442  mov     rcx, [rcx+10h]
0x180024446  lea     r8, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x18002444d  mov     edx, 1Ah
0x180024452  mov     r9d, ebx
0x180024455  call    WPP_SF_d
0x18002445a  mov     eax, ebx
0x18002445c  mov     rcx, [rbp+57h+var_50]
0x180024460  xor     rcx, rsp; StackCookie
0x180024463  call    __security_check_cookie
0x180024468  add     rsp, 0B8h
0x18002446f  pop     r15
0x180024471  pop     r14
0x180024473  pop     r13
0x180024475  pop     r12
0x180024477  pop     rdi
0x180024478  pop     rsi
0x180024479  pop     rbx
0x18002447a  pop     rbp
0x18002447b  retn
```
