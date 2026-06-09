# DeleteDhcpAdapterIPAddress(void)

- ea: `0x1800471b8`
- end: `0x180047412`
- name: `?DeleteDhcpAdapterIPAddress@@YAXXZ`
- size: `602`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004c410`

## callees

- `0x18000d090`
- `0x1800471b8`
- `0x18004fd9c`
- `0x180051f30`
- `0x180052bf4`
- `0x18006f014`
- `0x1800777ec`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004729a`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18004729a`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180047244`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180047244`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18004730e`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18004730e`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x1800472da`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x1800472da`

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
0x1800471b8  push    rbp
0x1800471ba  push    rbx
0x1800471bb  push    rsi
0x1800471bc  push    rdi
0x1800471bd  push    r14
0x1800471bf  lea     rbp, [rsp-37h]
0x1800471c4  sub     rsp, 0A0h
0x1800471cb  mov     rax, cs:__security_cookie
0x1800471d2  xor     rax, rsp
0x1800471d5  mov     [rbp+57h+var_30], rax
0x1800471d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800471e0  lea     rsi, WPP_GLOBAL_Control
0x1800471e7  lea     r14, WPP_48491dda36bf3a44e2f0141b66444ac7_Traceguids
0x1800471ee  mov     edi, 200h
0x1800471f3  cmp     rcx, rsi
0x1800471f6  jz      short loc_18004721B
0x1800471f8  test    [rcx+1Ch], edi
0x1800471fb  jz      short loc_18004721B
0x1800471fd  cmp     byte ptr [rcx+19h], 6
0x180047201  jb      short loc_18004721B
0x180047203  mov     rcx, [rcx+10h]
0x180047207  lea     r9, ?DhcpAdapterGuid@@3U_GUID@@A; _GUID DhcpAdapterGuid
0x18004720e  mov     edx, 20h ; ' '
0x180047213  mov     r8, r14
0x180047216  call    WPP_SF__guid_
0x18004721b  xor     edx, edx; Val
0x18004721d  mov     [rbp+57h+InterfaceIndex], 0FFFFFFFFh
0x180047224  lea     rcx, [rbp+57h+Row]; void *
0x180047228  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x180047230  lea     r8d, [rdx+50h]; Size
0x180047234  call    memset_0
0x180047239  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18004723d  lea     rcx, ?DhcpAdapterGuid@@3U_GUID@@A; InterfaceGuid
0x180047244  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18004724b  nop     dword ptr [rax+rax+00h]
0x180047250  test    eax, eax
0x180047252  jz      short loc_180047292
0x180047254  mov     rcx, cs:WPP_GLOBAL_Control
0x18004725b  cmp     rcx, rsi
0x18004725e  jz      loc_1800473F7
0x180047264  test    [rcx+1Ch], edi
0x180047267  jz      loc_1800473D2
0x18004726d  mov     ebx, 2
0x180047272  cmp     [rcx+19h], bl
0x180047275  jb      loc_1800473D2
0x18004727b  lea     edx, [rbx+1Fh]
0x18004727e  mov     rcx, [rcx+10h]
0x180047282  mov     r9d, eax
0x180047285  mov     r8, r14
0x180047288  call    WPP_SF_d
0x18004728d  jmp     loc_1800473CB
0x180047292  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x180047296  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18004729a  call    cs:__imp_ConvertInterfaceLuidToIndex
0x1800472a1  nop     dword ptr [rax+rax+00h]
0x1800472a6  test    eax, eax
0x1800472a8  jz      short loc_1800472D6
0x1800472aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472b1  cmp     rcx, rsi
0x1800472b4  jz      loc_1800473F7
0x1800472ba  test    [rcx+1Ch], edi
0x1800472bd  jz      loc_1800473D2
0x1800472c3  mov     ebx, 2
0x1800472c8  cmp     [rcx+19h], bl
0x1800472cb  jb      loc_1800473D2
0x1800472d1  lea     edx, [rbx+20h]
0x1800472d4  jmp     short loc_18004727E
0x1800472d6  lea     rcx, [rbp+57h+Row]; Row
0x1800472da  call    cs:__imp_InitializeUnicastIpAddressEntry
0x1800472e1  nop     dword ptr [rax+rax+00h]
0x1800472e6  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x1800472ea  lea     rcx, [rbp+57h+Row]; Row
0x1800472ee  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x1800472f2  mov     ebx, 2
0x1800472f7  mov     eax, [rbp+57h+InterfaceIndex]
0x1800472fa  mov     [rbp+57h+Row.InterfaceIndex], eax
0x1800472fd  mov     eax, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x180047303  mov     dword ptr [rbp+57h+Row.Address+4], eax
0x180047306  mov     word ptr [rbp+57h+Row.Address], bx
0x18004730a  mov     [rbp+57h+Row.OnLinkPrefixLength], 18h
0x18004730e  call    cs:__imp_DeleteUnicastIpAddressEntry
0x180047315  nop     dword ptr [rax+rax+00h]
0x18004731a  test    eax, eax
0x18004731c  jz      short loc_180047347
0x18004731e  mov     rcx, cs:WPP_GLOBAL_Control
0x180047325  cmp     rcx, rsi
0x180047328  jz      short loc_180047376
0x18004732a  test    [rcx+1Ch], edi
0x18004732d  jz      short loc_18004734E
0x18004732f  cmp     byte ptr [rcx+19h], 3
0x180047333  jb      short loc_18004734E
0x180047335  mov     rcx, [rcx+10h]
0x180047339  lea     edx, [rbx+21h]
0x18004733c  mov     r9d, eax
0x18004733f  mov     r8, r14
0x180047342  call    WPP_SF_d
0x180047347  mov     rcx, cs:WPP_GLOBAL_Control
0x18004734e  cmp     rcx, rsi
0x180047351  jz      short loc_180047376
0x180047353  test    [rcx+1Ch], edi
0x180047356  jz      short loc_180047376
0x180047358  cmp     byte ptr [rcx+19h], 5
0x18004735c  jb      short loc_180047376
0x18004735e  mov     r9d, cs:?DhcpAdapterIPAddress@@3KA; ulong DhcpAdapterIPAddress
0x180047365  mov     edx, 24h ; '$'
0x18004736a  mov     rcx, [rcx+10h]
0x18004736e  mov     r8, r14
0x180047371  call    WPP_SF_d
0x180047376  lea     r8, [rbp+57h+var_90]; bool *
0x18004737a  mov     [rbp+57h+var_90], 0
0x18004737e  lea     rdx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180047382  lea     rcx, ?DhcpAdapterGuid@@3U_GUID@@A; struct _GUID *
0x180047389  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x18004738e  test    eax, eax
0x180047390  jz      short loc_1800473CB
0x180047392  mov     rcx, cs:WPP_GLOBAL_Control
0x180047399  cmp     rcx, rsi
0x18004739c  jz      short loc_1800473F7
0x18004739e  test    [rcx+1Ch], edi
0x1800473a1  jz      short loc_1800473D2
0x1800473a3  cmp     [rcx+19h], bl
0x1800473a6  jb      short loc_1800473D2
0x1800473a8  mov     rcx, [rcx+10h]
0x1800473ac  lea     r9, ?DhcpAdapterGuid@@3U_GUID@@A; _GUID DhcpAdapterGuid
0x1800473b3  mov     [rsp+0C0h+var_98], eax
0x1800473b7  mov     edx, 25h ; '%'
0x1800473bc  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x1800473bf  mov     r8, r14
0x1800473c2  mov     [rsp+0C0h+var_A0], eax
0x1800473c6  call    WPP_SF__guid_DD
0x1800473cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473d2  cmp     rcx, rsi
0x1800473d5  jz      short loc_1800473F7
0x1800473d7  test    [rcx+1Ch], edi
0x1800473da  jz      short loc_1800473F7
0x1800473dc  cmp     byte ptr [rcx+19h], 6
0x1800473e0  jb      short loc_1800473F7
0x1800473e2  mov     r9d, [rbp+57h+InterfaceIndex]
0x1800473e6  mov     edx, 26h ; '&'
0x1800473eb  mov     rcx, [rcx+10h]
0x1800473ef  mov     r8, r14
0x1800473f2  call    WPP_SF_d
0x1800473f7  mov     rcx, [rbp+57h+var_30]
0x1800473fb  xor     rcx, rsp; StackCookie
0x1800473fe  call    __security_check_cookie
0x180047403  add     rsp, 0A0h
0x18004740a  pop     r14
0x18004740c  pop     rdi
0x18004740d  pop     rsi
0x18004740e  pop     rbx
0x18004740f  pop     rbp
0x180047410  retn
```
