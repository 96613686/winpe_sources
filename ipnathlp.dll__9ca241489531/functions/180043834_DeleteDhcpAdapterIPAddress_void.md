# DeleteDhcpAdapterIPAddress(void)

- ea: `0x180043834`
- end: `0x180043a75`
- name: `?DeleteDhcpAdapterIPAddress@@YAXXZ`
- size: `577`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800487d8`

## callees

- `0x18000c750`
- `0x180043834`
- `0x18004c068`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180069cdc`
- `0x180071d38`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180043910`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180043910`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800438c0`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800438c0`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180043978`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180043978`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18004394a`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18004394a`

## pseudocode

```c
void DeleteDhcpAdapterIPAddress(void)
{
  unsigned int v0; // eax
  PVOID *v1; // rcx
  __int64 v2; // rdx
  unsigned int v3; // eax
  PVOID *v4; // rcx
  unsigned int v5; // eax
  bool v6; // [rsp+30h] [rbp-39h] BYREF
  ULONG InterfaceIndex; // [rsp+34h] [rbp-35h] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-31h] BYREF
  struct _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+40h] [rbp-29h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids,
      &DhcpAdapterGuid);
  }
  InterfaceIndex = -1;
  InterfaceLuid.Value = 0;
  memset_0(&Row, 0, sizeof(Row));
  v0 = ConvertInterfaceGuidToLuid(&DhcpAdapterGuid, &InterfaceLuid);
  if ( v0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v2 = 33;
    goto LABEL_10;
  }
  v0 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
  if ( v0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v2 = 34;
LABEL_10:
    WPP_SF_d(v1[2], v2, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, v0);
LABEL_31:
    v1 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  InitializeUnicastIpAddressEntry(&Row);
  Row.InterfaceLuid = InterfaceLuid;
  Row.InterfaceIndex = InterfaceIndex;
  Row.Address.Ipv4.sin_addr.S_un.S_addr = DhcpAdapterIPAddress;
  Row.Address.Ipv4.sin_family = 2;
  Row.OnLinkPrefixLength = 24;
  v3 = DeleteUnicastIpAddressEntry(&Row);
  if ( !v3 )
    goto LABEL_21;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_26;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, v3);
LABEL_21:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_d(v4[2], 36, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, DhcpAdapterIPAddress);
LABEL_26:
  v6 = 0;
  v5 = SharedAccessUtils::TryPublishWnfStateData(&DhcpAdapterGuid, &Row, &v6);
  if ( !v5 )
    goto LABEL_31;
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF__guid_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids,
      &DhcpAdapterGuid,
      Row.Address.Ipv4.sin_addr.S_un.S_addr,
      v5);
    goto LABEL_31;
  }
LABEL_32:
  if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x200) != 0 && *((_BYTE *)v1 + 25) >= 6u )
    WPP_SF_d(v1[2], 38, &WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids, InterfaceIndex);
}

```

## disassembly

```asm
0x180043834  push    rbp
0x180043836  push    rbx
0x180043837  push    rsi
0x180043838  push    rdi
0x180043839  push    r14
0x18004383b  lea     rbp, [rsp-37h]
0x180043840  sub     rsp, 0A0h
0x180043847  mov     rax, cs:__security_cookie
0x18004384e  xor     rax, rsp
0x180043851  mov     [rbp+57h+var_30], rax
0x180043855  mov     rcx, cs:WPP_GLOBAL_Control
0x18004385c  lea     rsi, WPP_GLOBAL_Control
0x180043863  lea     r14, WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids
0x18004386a  mov     edi, 200h
0x18004386f  cmp     rcx, rsi
0x180043872  jz      short loc_180043897
0x180043874  test    [rcx+1Ch], edi
0x180043877  jz      short loc_180043897
0x180043879  cmp     byte ptr [rcx+19h], 6
0x18004387d  jb      short loc_180043897
0x18004387f  mov     rcx, [rcx+10h]
0x180043883  lea     r9, ?DhcpAdapterGuid@@3U_GUID@@A; _GUID DhcpAdapterGuid
0x18004388a  mov     edx, 20h ; ' '
0x18004388f  mov     r8, r14
0x180043892  call    WPP_SF__guid_
0x180043897  xor     edx, edx; Val
0x180043899  mov     [rbp+57h+InterfaceIndex], 0FFFFFFFFh
0x1800438a0  lea     rcx, [rbp+57h+Row]; void *
0x1800438a4  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x1800438ac  lea     r8d, [rdx+50h]; Size
0x1800438b0  call    memset_0
0x1800438b5  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x1800438b9  lea     rcx, ?DhcpAdapterGuid@@3U_GUID@@A; InterfaceGuid
0x1800438c0  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1800438c6  test    eax, eax
0x1800438c8  jz      short loc_180043908
0x1800438ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438d1  cmp     rcx, rsi
0x1800438d4  jz      loc_180043A5B
0x1800438da  test    [rcx+1Ch], edi
0x1800438dd  jz      loc_180043A36
0x1800438e3  mov     ebx, 2
0x1800438e8  cmp     [rcx+19h], bl
0x1800438eb  jb      loc_180043A36
0x1800438f1  lea     edx, [rbx+1Fh]
0x1800438f4  mov     rcx, [rcx+10h]
0x1800438f8  mov     r9d, eax
0x1800438fb  mov     r8, r14
0x1800438fe  call    WPP_SF_d
0x180043903  jmp     loc_180043A2F
0x180043908  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x18004390c  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180043910  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180043916  test    eax, eax
0x180043918  jz      short loc_180043946
0x18004391a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043921  cmp     rcx, rsi
0x180043924  jz      loc_180043A5B
0x18004392a  test    [rcx+1Ch], edi
0x18004392d  jz      loc_180043A36
0x180043933  mov     ebx, 2
0x180043938  cmp     [rcx+19h], bl
0x18004393b  jb      loc_180043A36
0x180043941  lea     edx, [rbx+20h]
0x180043944  jmp     short loc_1800438F4
0x180043946  lea     rcx, [rbp+57h+Row]; Row
0x18004394a  call    cs:__imp_InitializeUnicastIpAddressEntry
0x180043950  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x180043954  lea     rcx, [rbp+57h+Row]; Row
0x180043958  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x18004395c  mov     ebx, 2
0x180043961  mov     eax, [rbp+57h+InterfaceIndex]
0x180043964  mov     [rbp+57h+Row.InterfaceIndex], eax
0x180043967  mov     eax, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x18004396d  mov     dword ptr [rbp+57h+Row.Address+4], eax
0x180043970  mov     word ptr [rbp+57h+Row.Address], bx
0x180043974  mov     [rbp+57h+Row.OnLinkPrefixLength], 18h
0x180043978  call    cs:__imp_DeleteUnicastIpAddressEntry
0x18004397e  test    eax, eax
0x180043980  jz      short loc_1800439AB
0x180043982  mov     rcx, cs:WPP_GLOBAL_Control
0x180043989  cmp     rcx, rsi
0x18004398c  jz      short loc_1800439DA
0x18004398e  test    [rcx+1Ch], edi
0x180043991  jz      short loc_1800439B2
0x180043993  cmp     byte ptr [rcx+19h], 3
0x180043997  jb      short loc_1800439B2
0x180043999  mov     rcx, [rcx+10h]
0x18004399d  lea     edx, [rbx+21h]
0x1800439a0  mov     r9d, eax
0x1800439a3  mov     r8, r14
0x1800439a6  call    WPP_SF_d
0x1800439ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439b2  cmp     rcx, rsi
0x1800439b5  jz      short loc_1800439DA
0x1800439b7  test    [rcx+1Ch], edi
0x1800439ba  jz      short loc_1800439DA
0x1800439bc  cmp     byte ptr [rcx+19h], 5
0x1800439c0  jb      short loc_1800439DA
0x1800439c2  mov     r9d, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x1800439c9  mov     edx, 24h ; '$'
0x1800439ce  mov     rcx, [rcx+10h]
0x1800439d2  mov     r8, r14
0x1800439d5  call    WPP_SF_d
0x1800439da  lea     r8, [rbp+57h+var_90]; bool *
0x1800439de  mov     [rbp+57h+var_90], 0
0x1800439e2  lea     rdx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x1800439e6  lea     rcx, ?DhcpAdapterGuid@@3U_GUID@@A; struct _GUID *
0x1800439ed  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x1800439f2  test    eax, eax
0x1800439f4  jz      short loc_180043A2F
0x1800439f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439fd  cmp     rcx, rsi
0x180043a00  jz      short loc_180043A5B
0x180043a02  test    [rcx+1Ch], edi
0x180043a05  jz      short loc_180043A36
0x180043a07  cmp     [rcx+19h], bl
0x180043a0a  jb      short loc_180043A36
0x180043a0c  mov     rcx, [rcx+10h]
0x180043a10  lea     r9, ?DhcpAdapterGuid@@3U_GUID@@A; _GUID DhcpAdapterGuid
0x180043a17  mov     [rsp+0C0h+var_98], eax
0x180043a1b  mov     edx, 25h ; '%'
0x180043a20  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x180043a23  mov     r8, r14
0x180043a26  mov     [rsp+0C0h+var_A0], eax
0x180043a2a  call    WPP_SF__guid_DD
0x180043a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a36  cmp     rcx, rsi
0x180043a39  jz      short loc_180043A5B
0x180043a3b  test    [rcx+1Ch], edi
0x180043a3e  jz      short loc_180043A5B
0x180043a40  cmp     byte ptr [rcx+19h], 6
0x180043a44  jb      short loc_180043A5B
0x180043a46  mov     r9d, [rbp+57h+InterfaceIndex]
0x180043a4a  mov     edx, 26h ; '&'
0x180043a4f  mov     rcx, [rcx+10h]
0x180043a53  mov     r8, r14
0x180043a56  call    WPP_SF_d
0x180043a5b  mov     rcx, [rbp+57h+var_30]
0x180043a5f  xor     rcx, rsp; StackCookie
0x180043a62  call    __security_check_cookie
0x180043a67  add     rsp, 0A0h
0x180043a6e  pop     r14
0x180043a70  pop     rdi
0x180043a71  pop     rsi
0x180043a72  pop     rbx
0x180043a73  pop     rbp
0x180043a74  retn
```
