# V2DeleteDhcpAdapterIPAddress(_V2_DHCP_INTERFACE_INFO *)

- ea: `0x18008764c`
- end: `0x180087898`
- name: `?V2DeleteDhcpAdapterIPAddress@@YAXPEAU_V2_DHCP_INTERFACE_INFO@@@Z`
- size: `588`
- prototype: `void __fastcall(struct _V2_DHCP_INTERFACE_INFO *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800218f0`
- `0x180087a78`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18004c068`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180071d38`
- `0x18008764c`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180087732`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180087732`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800876e1`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800876e1`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180087798`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180087798`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18008776d`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18008776d`

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
0x18008764c  mov     [rsp-8+arg_8], rbx
0x180087651  mov     [rsp-8+arg_10], rsi
0x180087656  push    rbp
0x180087657  push    rdi
0x180087658  push    r12
0x18008765a  push    r14
0x18008765c  push    r15
0x18008765e  lea     rbp, [rsp-37h]
0x180087663  sub     rsp, 0A0h
0x18008766a  mov     rax, cs:__security_cookie
0x180087671  xor     rax, rsp
0x180087674  mov     [rbp+57h+var_30], rax
0x180087678  mov     rdi, rcx
0x18008767b  mov     rcx, cs:WPP_GLOBAL_Control
0x180087682  lea     r15, WPP_GLOBAL_Control
0x180087689  lea     r12, WPP_c6bccde9edde3e8494cb97405f2a0ee4_Traceguids
0x180087690  mov     r14d, 200h
0x180087696  cmp     rcx, r15
0x180087699  jz      short loc_1800876B8
0x18008769b  test    [rcx+1Ch], r14d
0x18008769f  jz      short loc_1800876B8
0x1800876a1  cmp     byte ptr [rcx+19h], 6
0x1800876a5  jb      short loc_1800876B8
0x1800876a7  mov     rcx, [rcx+10h]
0x1800876ab  mov     edx, 1Bh
0x1800876b0  mov     r8, r12
0x1800876b3  call    WPP_SF_
0x1800876b8  xor     edx, edx; Val
0x1800876ba  mov     [rbp+57h+InterfaceIndex], 0FFFFFFFFh
0x1800876c1  lea     rcx, [rbp+57h+Row]; void *
0x1800876c5  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x1800876cd  lea     r8d, [rdx+50h]; Size
0x1800876d1  call    memset_0
0x1800876d6  lea     rsi, [rdi+18h]
0x1800876da  mov     rcx, rsi; InterfaceGuid
0x1800876dd  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x1800876e1  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1800876e7  test    eax, eax
0x1800876e9  jz      short loc_18008772A
0x1800876eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800876f2  cmp     rcx, r15
0x1800876f5  jz      loc_180087870
0x1800876fb  test    [rcx+1Ch], r14d
0x1800876ff  jz      loc_18008784E
0x180087705  mov     ebx, 2
0x18008770a  cmp     [rcx+19h], bl
0x18008770d  jb      loc_18008784E
0x180087713  lea     edx, [rbx+1Ah]
0x180087716  mov     rcx, [rcx+10h]
0x18008771a  mov     r9d, eax
0x18008771d  mov     r8, r12
0x180087720  call    WPP_SF_d
0x180087725  jmp     loc_180087847
0x18008772a  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x18008772e  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x180087732  call    cs:__imp_ConvertInterfaceLuidToIndex
0x180087738  test    eax, eax
0x18008773a  jz      short loc_180087769
0x18008773c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087743  cmp     rcx, r15
0x180087746  jz      loc_180087870
0x18008774c  test    [rcx+1Ch], r14d
0x180087750  jz      loc_18008784E
0x180087756  mov     ebx, 2
0x18008775b  cmp     [rcx+19h], bl
0x18008775e  jb      loc_18008784E
0x180087764  lea     edx, [rbx+1Bh]
0x180087767  jmp     short loc_180087716
0x180087769  lea     rcx, [rbp+57h+Row]; Row
0x18008776d  call    cs:__imp_InitializeUnicastIpAddressEntry
0x180087773  mov     rax, qword ptr [rbp+57h+InterfaceLuid]
0x180087777  lea     rcx, [rbp+57h+Row]; Row
0x18008777b  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x18008777f  mov     ebx, 2
0x180087784  mov     eax, [rbp+57h+InterfaceIndex]
0x180087787  mov     [rbp+57h+Row.InterfaceIndex], eax
0x18008778a  mov     eax, [rdi+0Ch]
0x18008778d  mov     dword ptr [rbp+57h+Row.Address+4], eax
0x180087790  mov     word ptr [rbp+57h+Row.Address], bx
0x180087794  mov     [rbp+57h+Row.OnLinkPrefixLength], 18h
0x180087798  call    cs:__imp_DeleteUnicastIpAddressEntry
0x18008779e  test    eax, eax
0x1800877a0  jz      short loc_1800877CC
0x1800877a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800877a9  cmp     rcx, r15
0x1800877ac  jz      short loc_1800877F9
0x1800877ae  test    [rcx+1Ch], r14d
0x1800877b2  jz      short loc_1800877D3
0x1800877b4  cmp     byte ptr [rcx+19h], 3
0x1800877b8  jb      short loc_1800877D3
0x1800877ba  mov     rcx, [rcx+10h]
0x1800877be  lea     edx, [rbx+1Ch]
0x1800877c1  mov     r9d, eax
0x1800877c4  mov     r8, r12
0x1800877c7  call    WPP_SF_d
0x1800877cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800877d3  cmp     rcx, r15
0x1800877d6  jz      short loc_1800877F9
0x1800877d8  test    [rcx+1Ch], r14d
0x1800877dc  jz      short loc_1800877F9
0x1800877de  cmp     byte ptr [rcx+19h], 5
0x1800877e2  jb      short loc_1800877F9
0x1800877e4  mov     r9d, dword ptr [rbp+57h+Row.Address+4]
0x1800877e8  mov     edx, 1Fh
0x1800877ed  mov     rcx, [rcx+10h]
0x1800877f1  mov     r8, r12
0x1800877f4  call    WPP_SF_d
0x1800877f9  lea     r8, [rbp+57h+var_90]; bool *
0x1800877fd  mov     [rbp+57h+var_90], 0
0x180087801  lea     rdx, [rbp+57h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180087805  mov     rcx, rsi; struct _GUID *
0x180087808  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x18008780d  test    eax, eax
0x18008780f  jz      short loc_180087847
0x180087811  mov     rcx, cs:WPP_GLOBAL_Control
0x180087818  cmp     rcx, r15
0x18008781b  jz      short loc_180087870
0x18008781d  test    [rcx+1Ch], r14d
0x180087821  jz      short loc_18008784E
0x180087823  cmp     [rcx+19h], bl
0x180087826  jb      short loc_18008784E
0x180087828  mov     rcx, [rcx+10h]
0x18008782c  mov     edx, 20h ; ' '
0x180087831  mov     [rsp+0C0h+var_98], eax
0x180087835  mov     r9, rsi
0x180087838  mov     eax, dword ptr [rbp+57h+Row.Address+4]
0x18008783b  mov     r8, r12
0x18008783e  mov     [rsp+0C0h+var_A0], eax
0x180087842  call    WPP_SF__guid_DD
0x180087847  mov     rcx, cs:WPP_GLOBAL_Control
0x18008784e  cmp     rcx, r15
0x180087851  jz      short loc_180087870
0x180087853  test    [rcx+1Ch], r14d
0x180087857  jz      short loc_180087870
0x180087859  cmp     byte ptr [rcx+19h], 6
0x18008785d  jb      short loc_180087870
0x18008785f  mov     rcx, [rcx+10h]
0x180087863  mov     edx, 21h ; '!'
0x180087868  mov     r8, r12
0x18008786b  call    WPP_SF_
0x180087870  mov     rcx, [rbp+57h+var_30]
0x180087874  xor     rcx, rsp; StackCookie
0x180087877  call    __security_check_cookie
0x18008787c  lea     r11, [rsp+0C0h+var_20]
0x180087884  mov     rbx, [r11+38h]
0x180087888  mov     rsi, [r11+40h]
0x18008788c  mov     rsp, r11
0x18008788f  pop     r15
0x180087891  pop     r14
0x180087893  pop     r12
0x180087895  pop     rdi
0x180087896  pop     rbp
0x180087897  retn
```
