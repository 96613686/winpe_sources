# V2DeleteDhcpAdapterIPAddress(_V2_DHCP_INTERFACE_INFO *)

- ea: `0x18008e1e4`
- end: `0x18008e449`
- name: `?V2DeleteDhcpAdapterIPAddress@@YAXPEAU_V2_DHCP_INTERFACE_INFO@@@Z`
- size: `613`
- prototype: `void __fastcall(struct _V2_DHCP_INTERFACE_INFO *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002dd0c`
- `0x18008e63c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18004fd9c`
- `0x180051f30`
- `0x180052bf4`
- `0x1800777ec`
- `0x18008e1e4`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18008e2d0`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18008e2d0`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18008e279`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18008e279`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18008e342`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18008e342`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18008e311`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18008e311`

## pseudocode

```c
void __fastcall V2DeleteDhcpAdapterIPAddress(struct _V2_DHCP_INTERFACE_INFO *a1)
{
  unsigned int v2; // eax
  PVOID *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  PVOID *v6; // rcx
  unsigned int v7; // eax
  bool v8; // [rsp+30h] [rbp-39h] BYREF
  ULONG InterfaceIndex; // [rsp+34h] [rbp-35h] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-31h] BYREF
  struct _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+40h] [rbp-29h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids);
  }
  InterfaceIndex = -1;
  InterfaceLuid.Value = 0;
  memset_0(&Row, 0, sizeof(Row));
  v2 = ConvertInterfaceGuidToLuid((const GUID *)((char *)a1 + 24), &InterfaceLuid);
  if ( v2 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v4 = 28;
    goto LABEL_10;
  }
  v2 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
  if ( v2 )
  {
    v3 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v4 = 29;
LABEL_10:
    WPP_SF_d(v3[2], v4, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, v2);
LABEL_31:
    v3 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  InitializeUnicastIpAddressEntry(&Row);
  Row.InterfaceLuid = InterfaceLuid;
  Row.InterfaceIndex = InterfaceIndex;
  Row.Address.Ipv4.sin_addr.S_un.S_addr = *((_DWORD *)a1 + 3);
  Row.Address.Ipv4.sin_family = 2;
  Row.OnLinkPrefixLength = 24;
  v5 = DeleteUnicastIpAddressEntry(&Row);
  if ( !v5 )
    goto LABEL_21;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_26;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, v5);
LABEL_21:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x200) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_d(v6[2], 31, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids, Row.Address.Ipv4.sin_addr.S_un.S_addr);
LABEL_26:
  v8 = 0;
  v7 = SharedAccessUtils::TryPublishWnfStateData((const struct _GUID *)((char *)a1 + 24), &Row, &v8);
  if ( !v7 )
    goto LABEL_31;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF__guid_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids,
      (char *)a1 + 24,
      Row.Address.Ipv4.sin_addr.S_un.S_addr,
      v7);
    goto LABEL_31;
  }
LABEL_32:
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x200) != 0 && *((_BYTE *)v3 + 25) >= 6u )
    WPP_SF_(v3[2], 33, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids);
}

```

## disassembly

```asm
0x18008e1e4  mov     [rsp-8+arg_8], rbx
0x18008e1e9  mov     [rsp-8+arg_10], rsi
0x18008e1ee  push    rbp
0x18008e1ef  push    rdi
0x18008e1f0  push    r12
0x18008e1f2  push    r14
0x18008e1f4  push    r15
0x18008e1f6  lea     rbp, [rsp-37h]
0x18008e1fb  sub     rsp, 0A0h
0x18008e202  mov     rax, cs:__security_cookie
0x18008e209  xor     rax, rsp
0x18008e20c  mov     [rbp+57h+var_30], rax
0x18008e210  mov     rdi, rcx
0x18008e213  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e21a  lea     r15, WPP_GLOBAL_Control
0x18008e221  lea     r12, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x18008e228  mov     r14d, 200h
0x18008e22e  cmp     rcx, r15
0x18008e231  jz      short loc_18008E250
0x18008e233  test    [rcx+1Ch], r14d
0x18008e237  jz      short loc_18008E250
0x18008e239  cmp     byte ptr [rcx+19h], 6
0x18008e23d  jb      short loc_18008E250
0x18008e23f  mov     rcx, [rcx+10h]
0x18008e243  mov     edx, 1Bh
0x18008e248  mov     r8, r12
0x18008e24b  call    WPP_SF_
0x18008e250  xor     edx, edx; Val
0x18008e252  mov     [rbp+57h+InterfaceIndex], 0FFFFFFFFh
0x18008e259  lea     rcx, [rbp+57h+Row]; void *
0x18008e25d  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x18008e265  lea     r8d, [rdx+50h]; Size
0x18008e269  call    memset_0
0x18008e26e  lea     rsi, [rdi+18h]
0x18008e272  mov     rcx, rsi; InterfaceGuid
0x18008e275  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18008e279  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18008e280  nop     dword ptr [rax+rax+00h]
0x18008e285  test    eax, eax
0x18008e287  jz      short loc_18008E2C8
0x18008e289  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e290  cmp     rcx, r15
0x18008e293  jz      loc_18008E420
0x18008e299  test    [rcx+1Ch], r14d
0x18008e29d  jz      loc_18008E3FE
0x18008e2a3  mov     ebx, 2
0x18008e2a8  cmp     [rcx+19h], bl
0x18008e2ab  jb      loc_18008E3FE
0x18008e2b1  lea     edx, [rbx+1Ah]
0x18008e2b4  mov     rcx, [rcx+10h]
0x18008e2b8  mov     r9d, eax
0x18008e2bb  mov     r8, r12
0x18008e2be  call    WPP_SF_d
0x18008e2c3  jmp     loc_18008E3F7
0x18008e2c8  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x18008e2cc  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18008e2d0  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18008e2d7  nop     dword ptr [rax+rax+00h]
0x18008e2dc  test    eax, eax
0x18008e2de  jz      short loc_18008E30D
0x18008e2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e2e7  cmp     rcx, r15
0x18008e2ea  jz      loc_18008E420
0x18008e2f0  test    [rcx+1Ch], r14d
0x18008e2f4  jz      loc_18008E3FE
0x18008e2fa  mov     ebx, 2
0x18008e2ff  cmp     [rcx+19h], bl
0x18008e302  jb      loc_18008E3FE
0x18008e308  lea     edx, [rbx+1Bh]
0x18008e30b  jmp     short loc_18008E2B4
0x18008e30d  lea     rcx, [rbp+57h+Row]; Row
0x18008e311  call    cs:__imp_InitializeUnicastIpAddressEntry
0x18008e318  nop     dword ptr [rax+rax+00h]
0x18008e31d  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x18008e321  lea     rcx, [rbp+57h+Row]; Row
0x18008e325  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x18008e329  mov     ebx, 2
0x18008e32e  mov     eax, [rbp+57h+InterfaceIndex]
0x18008e331  mov     [rbp+57h+Row.InterfaceIndex], eax
0x18008e334  mov     eax, [rdi+0Ch]
0x18008e337  mov     dword ptr [rbp+57h+Row.Address+4], eax
0x18008e33a  mov     word ptr [rbp+57h+Row.Address], bx
0x18008e33e  mov     [rbp+57h+Row.OnLinkPrefixLength], 18h
0x18008e342  call    cs:__imp_DeleteUnicastIpAddressEntry
0x18008e349  nop     dword ptr [rax+rax+00h]
0x18008e34e  test    eax, eax
0x18008e350  jz      short loc_18008E37C
0x18008e352  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e359  cmp     rcx, r15
0x18008e35c  jz      short loc_18008E3A9
0x18008e35e  test    [rcx+1Ch], r14d
0x18008e362  jz      short loc_18008E383
0x18008e364  cmp     byte ptr [rcx+19h], 3
0x18008e368  jb      short loc_18008E383
0x18008e36a  mov     rcx, [rcx+10h]
0x18008e36e  lea     edx, [rbx+1Ch]
0x18008e371  mov     r9d, eax
0x18008e374  mov     r8, r12
0x18008e377  call    WPP_SF_d
0x18008e37c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e383  cmp     rcx, r15
0x18008e386  jz      short loc_18008E3A9
0x18008e388  test    [rcx+1Ch], r14d
0x18008e38c  jz      short loc_18008E3A9
0x18008e38e  cmp     byte ptr [rcx+19h], 5
0x18008e392  jb      short loc_18008E3A9
0x18008e394  mov     r9d, dword ptr [rbp+57h+Row.Address+4]
0x18008e398  mov     edx, 1Fh
0x18008e39d  mov     rcx, [rcx+10h]
0x18008e3a1  mov     r8, r12
0x18008e3a4  call    WPP_SF_d
0x18008e3a9  lea     r8, [rbp+57h+var_90]; bool *
0x18008e3ad  mov     [rbp+57h+var_90], 0
0x18008e3b1  lea     rdx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x18008e3b5  mov     rcx, rsi; struct _GUID *
0x18008e3b8  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x18008e3bd  test    eax, eax
0x18008e3bf  jz      short loc_18008E3F7
0x18008e3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e3c8  cmp     rcx, r15
0x18008e3cb  jz      short loc_18008E420
0x18008e3cd  test    [rcx+1Ch], r14d
0x18008e3d1  jz      short loc_18008E3FE
0x18008e3d3  cmp     [rcx+19h], bl
0x18008e3d6  jb      short loc_18008E3FE
0x18008e3d8  mov     rcx, [rcx+10h]
0x18008e3dc  mov     edx, 20h ; ' '
0x18008e3e1  mov     [rsp+0C0h+var_98], eax
0x18008e3e5  mov     r9, rsi
0x18008e3e8  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x18008e3eb  mov     r8, r12
0x18008e3ee  mov     [rsp+0C0h+var_A0], eax
0x18008e3f2  call    WPP_SF__guid_DD
0x18008e3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e3fe  cmp     rcx, r15
0x18008e401  jz      short loc_18008E420
0x18008e403  test    [rcx+1Ch], r14d
0x18008e407  jz      short loc_18008E420
0x18008e409  cmp     byte ptr [rcx+19h], 6
0x18008e40d  jb      short loc_18008E420
0x18008e40f  mov     rcx, [rcx+10h]
0x18008e413  mov     edx, 21h ; '!'
0x18008e418  mov     r8, r12
0x18008e41b  call    WPP_SF_
0x18008e420  mov     rcx, [rbp+57h+var_30]
0x18008e424  xor     rcx, rsp; StackCookie
0x18008e427  call    __security_check_cookie
0x18008e42c  lea     r11, [rsp+0C0h+var_20]
0x18008e434  mov     rbx, [r11+38h]
0x18008e438  mov     rsi, [r11+40h]
0x18008e43c  mov     rsp, r11
0x18008e43f  pop     r15
0x18008e441  pop     r14
0x18008e443  pop     r12
0x18008e445  pop     rdi
0x18008e446  pop     rbp
0x18008e447  retn
```
