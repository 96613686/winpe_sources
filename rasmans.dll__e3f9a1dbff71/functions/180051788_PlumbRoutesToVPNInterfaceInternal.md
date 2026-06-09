# PlumbRoutesToVPNInterfaceInternal

- ea: `0x180051788`
- end: `0x180051f39`
- name: `PlumbRoutesToVPNInterfaceInternal`
- size: `1969`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180051434`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x18000bfb0`
- `0x180032118`
- `0x180050a50`
- `0x180051788`
- `0x180053ab8`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051a88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051a88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051ecf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051ecf`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180051a1a`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180051a1a`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180051bd4`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180051d82`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180051bd4`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180051d82`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800518b2`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1800518b2`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180051ab1`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180051ab1`

## pseudocode

```c
__int64 __fastcall PlumbRoutesToVPNInterfaceInternal(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  struct _LIST_ENTRY *v6; // rbx
  unsigned int v7; // r15d
  IP_ADAPTER_ADDRESSES_LH *v8; // r14
  __int64 v9; // r13
  _DWORD *v10; // rsi
  __int64 v11; // r9
  struct _LIST_ENTRY *v12; // rcx
  NTSTATUS v13; // eax
  ULONG AdaptersAddresses; // ebx
  struct _LIST_ENTRY *v15; // r10
  IP_ADAPTER_ADDRESSES_LH *v16; // rbx
  __int64 v17; // rdx
  unsigned int v18; // edi
  __int64 v19; // r8
  __int64 v20; // rdx
  LPSOCKADDR lpSockaddr; // rcx
  bool v22; // zf
  LPSOCKADDR v23; // rcx
  unsigned int v24; // eax
  int v26; // [rsp+30h] [rbp-89h]
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-81h] BYREF
  SIZE_T uBytes; // [rsp+40h] [rbp-79h] BYREF
  __int64 v29; // [rsp+48h] [rbp-71h]
  __int64 v30; // [rsp+50h] [rbp-69h]
  MIB_IPFORWARD_ROW2 Row; // [rsp+60h] [rbp-59h] BYREF

  v30 = a2;
  v4 = a2;
  v29 = a1;
  v5 = a1;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 12, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  LODWORD(uBytes) = 15000;
  memset_0(&Row, 0, sizeof(Row));
  InterfaceLuid.Value = 0;
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v6[1].Blink) & 0x2000) != 0
    && BYTE1(v6[1].Blink) >= 5u )
  {
    WPP_SF_d(v6[1].Flink, 13, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, a3);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    v8 = 0;
    v26 = 0;
    ConvertInterfaceGuidToLuid((const GUID *)(v5 + 144), &InterfaceLuid);
    v6 = WPP_GLOBAL_Control;
    v9 = 0;
    while ( 1 )
    {
      v10 = (_DWORD *)(v4 + 36 * v9);
      v11 = (unsigned int)v10[1];
      if ( (_DWORD)v11 == 2 )
      {
        if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v6[1].Blink) & 0x2000) != 0
          && BYTE1(v6[1].Blink) >= 5u )
        {
          WPP_SF_d(v6[1].Flink, 16, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, (unsigned int)v10[3]);
        }
      }
      else
      {
        if ( (_DWORD)v11 != 23 )
        {
          if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v6[1].Blink) & 0x2000) != 0
            && BYTE1(v6[1].Blink) >= 4u )
          {
            WPP_SF_d(v6[1].Flink, 15, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v11);
LABEL_22:
            v6 = WPP_GLOBAL_Control;
            goto LABEL_122;
          }
          goto LABEL_122;
        }
        if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v6[1].Blink) & 0x2000) != 0
          && BYTE1(v6[1].Blink) >= 5u )
        {
          WPP_SF_s(v6[1].Flink, 17, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v10 + 3);
        }
      }
      if ( !*v10 )
        *v10 = 1;
      CreateRouteEntry(&Row);
      if ( v10[7] )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 18, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
          v12 = WPP_GLOBAL_Control;
        }
        if ( v10[8] )
        {
          Row.InterfaceIndex = v10[8];
          v13 = DeleteIpForwardEntry2(&Row);
          if ( v13
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qD)(
              WPP_GLOBAL_Control[1].Flink,
              19,
              WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids,
              (NET_LUID)InterfaceLuid.Value,
              v13);
          }
        }
        else if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
               && (HIDWORD(v12[1].Blink) & 0x2000) != 0
               && BYTE1(v12[1].Blink) >= 4u )
        {
          WPP_SF_(v12[1].Flink, 20, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
        }
        while ( 1 )
        {
          v8 = (IP_ADAPTER_ADDRESSES_LH *)LocalAlloc(0x40u, (unsigned int)uBytes);
          if ( !v8 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              return v7;
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 21, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 8);
              goto LABEL_14;
            }
            goto LABEL_130;
          }
          AdaptersAddresses = GetAdaptersAddresses(v10[1], 0x90u, 0, v8, (PULONG)&uBytes);
          if ( AdaptersAddresses != 111 )
            break;
          LocalFree(v8);
          v8 = 0;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 22, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 111, v26);
            v15 = WPP_GLOBAL_Control;
          }
          if ( (unsigned int)++v26 >= 3 )
            goto LABEL_57;
        }
        v15 = WPP_GLOBAL_Control;
LABEL_57:
        if ( AdaptersAddresses
          && v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v15[1].Blink) & 0x2000) != 0
          && BYTE1(v15[1].Blink) >= 5u )
        {
          WPP_SF_d(v15[1].Flink, 23, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, AdaptersAddresses);
          v15 = WPP_GLOBAL_Control;
        }
        v16 = v8;
        if ( v8 )
        {
          while ( v16->IfIndex != Row.InterfaceIndex && v16->Ipv6IfIndex != Row.InterfaceIndex )
          {
            v16 = v16->Next;
            if ( !v16 )
              goto LABEL_66;
          }
          if ( v16->FirstPrefix->PrefixLength != v10[2] )
            goto LABEL_89;
          lpSockaddr = v16->FirstUnicastAddress->Address.lpSockaddr;
          if ( v10[1] == 2 )
          {
            v22 = Row.DestinationPrefix.Prefix.Ipv4.sin_addr.S_un.S_addr == *(_DWORD *)&lpSockaddr->sa_data[2];
            goto LABEL_82;
          }
          if ( *((_QWORD *)&Row.DestinationPrefix.Prefix.si_family + 1) != *(_QWORD *)&lpSockaddr->sa_data[6] )
            goto LABEL_89;
          v22 = *((_QWORD *)&Row.DestinationPrefix.Prefix.si_family + 2) == *(_QWORD *)&lpSockaddr[1].sa_family;
LABEL_82:
          if ( v22 )
          {
            if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v15[1].Blink) & 0x2000) != 0
              && BYTE1(v15[1].Blink) >= 5u )
            {
              v17 = 24;
LABEL_70:
              WPP_SF_(v15[1].Flink, v17, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
            }
          }
          else
          {
LABEL_89:
            if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v15[1].Blink) & 0x2000) != 0
              && BYTE1(v15[1].Blink) >= 5u )
            {
              WPP_SF_(v15[1].Flink, 25, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
            }
            v23 = v16->FirstGatewayAddress->Address.lpSockaddr;
            if ( v10[1] == 2 )
              Row.NextHop.Ipv4.sin_addr.S_un.S_addr = *(_DWORD *)&v23->sa_data[2];
            else
              *(struct sockaddr *)(&Row.NextHop.si_family + 4) = *(struct sockaddr *)&v23->sa_data[6];
          }
        }
        else
        {
LABEL_66:
          if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v15[1].Blink) & 0x2000) != 0
            && BYTE1(v15[1].Blink) >= 5u )
          {
            v17 = 26;
            goto LABEL_70;
          }
        }
        Row.InterfaceIndex = *(_DWORD *)(v5 + 852);
        v18 = CreateIpForwardEntry2(&Row);
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 28, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v18);
          }
          v10[8] = 0;
          v6 = WPP_GLOBAL_Control;
          goto LABEL_114;
        }
        v5 = v29;
        v10[8] = *(_DWORD *)(v29 + 852);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          v20 = 27;
          goto LABEL_76;
        }
        goto LABEL_122;
      }
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 29, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
      }
      Row.InterfaceLuid = InterfaceLuid;
      v24 = CreateIpForwardEntry2(&Row);
      v18 = v24;
      if ( !v10[7] || v24 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 31, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v24);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v18 )
        {
LABEL_114:
          if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v6[1].Blink) & 0x2000) != 0
            && BYTE1(v6[1].Blink) >= 2u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qD)(
              v6[1].Flink,
              32,
              WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids,
              (NET_LUID)InterfaceLuid.Value,
              v18);
            v6 = WPP_GLOBAL_Control;
          }
          v7 = v18;
          if ( v18 == 5 || v18 == 50 || v18 == 1168 )
          {
LABEL_128:
            if ( v8 )
            {
              LocalFree(v8);
              v6 = WPP_GLOBAL_Control;
            }
            goto LABEL_130;
          }
        }
        v5 = v29;
      }
      else
      {
        v5 = v29;
        v10[8] = *(_DWORD *)(v29 + 852);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          v20 = 30;
LABEL_76:
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_I)(
            v6[1].Flink,
            v20,
            v19,
            (NET_LUID)InterfaceLuid.Value);
          goto LABEL_22;
        }
      }
LABEL_122:
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= a3 )
        goto LABEL_128;
      v4 = v30;
    }
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(v6[1].Blink) & 0x2000) != 0 && BYTE1(v6[1].Blink) >= 5u )
    {
      WPP_SF_(v6[1].Flink, 14, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
LABEL_14:
      v6 = WPP_GLOBAL_Control;
    }
LABEL_130:
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v6[1].Blink) & 0x2000) != 0
      && BYTE1(v6[1].Blink) >= 6u )
    {
      WPP_SF_d(v6[1].Flink, 33, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v7);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180051788  mov     [rsp-8+arg_18], rbx
0x18005178d  push    rbp
0x18005178e  push    rsi
0x18005178f  push    rdi
0x180051790  push    r12
0x180051792  push    r13
0x180051794  push    r14
0x180051796  push    r15
0x180051798  lea     rbp, [rsp-27h]
0x18005179d  sub     rsp, 0E0h
0x1800517a4  mov     rax, cs:__security_cookie
0x1800517ab  xor     rax, rsp
0x1800517ae  mov     [rbp+57h+var_40], rax
0x1800517b2  mov     r12d, r8d
0x1800517b5  mov     [rbp+57h+var_C0], rdx
0x1800517b9  mov     rsi, rdx
0x1800517bc  mov     [rbp+57h+var_C8], rcx
0x1800517c0  mov     rdi, rcx
0x1800517c3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800517ca  lea     rax, WPP_GLOBAL_Control
0x1800517d1  cmp     rbx, rax
0x1800517d4  jz      short loc_180051801
0x1800517d6  test    dword ptr [rbx+1Ch], 2000h
0x1800517dd  jz      short loc_180051801
0x1800517df  cmp     byte ptr [rbx+19h], 6
0x1800517e3  jb      short loc_180051801
0x1800517e5  mov     rcx, [rbx+10h]
0x1800517e9  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800517f0  mov     edx, 0Ch
0x1800517f5  call    WPP_SF_
0x1800517fa  mov     rbx, cs:WPP_GLOBAL_Control
0x180051801  xor     r15d, r15d
0x180051804  mov     dword ptr [rbp+57h+uBytes], 3A98h
0x18005180b  xor     edx, edx; Val
0x18005180d  lea     rcx, [rbp+57h+Row]; void *
0x180051811  lea     r8d, [r15+68h]; Size
0x180051815  call    memset_0
0x18005181a  mov     qword ptr [rsp+110h+InterfaceLuid], r15
0x18005181f  lea     r14, WPP_GLOBAL_Control
0x180051826  cmp     rbx, r14
0x180051829  jz      short loc_180051858
0x18005182b  test    dword ptr [rbx+1Ch], 2000h
0x180051832  jz      short loc_180051858
0x180051834  cmp     byte ptr [rbx+19h], 5
0x180051838  jb      short loc_180051858
0x18005183a  mov     rcx, [rbx+10h]
0x18005183e  lea     edx, [r15+0Dh]
0x180051842  mov     r9d, r12d
0x180051845  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005184c  call    WPP_SF_d
0x180051851  mov     rbx, cs:WPP_GLOBAL_Control
0x180051858  test    r12d, r12d
0x18005185b  jnz     short loc_18005189E
0x18005185d  cmp     rbx, r14
0x180051860  jz      loc_180051F0F
0x180051866  test    dword ptr [rbx+1Ch], 2000h
0x18005186d  jz      loc_180051EE3
0x180051873  cmp     byte ptr [rbx+19h], 5
0x180051877  jb      loc_180051EE3
0x18005187d  mov     rcx, [rbx+10h]
0x180051881  lea     edx, [r12+0Eh]
0x180051886  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005188d  call    WPP_SF_
0x180051892  mov     rbx, cs:WPP_GLOBAL_Control
0x180051899  jmp     loc_180051EE3
0x18005189e  xor     r14d, r14d
0x1800518a1  lea     rcx, [rdi+90h]; InterfaceGuid
0x1800518a8  lea     rdx, [rsp+110h+InterfaceLuid]; InterfaceLuid
0x1800518ad  mov     [rsp+110h+var_E0], r14d
0x1800518b2  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1800518b8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800518bf  xor     r13d, r13d
0x1800518c2  test    r12d, r12d
0x1800518c5  jz      loc_180051EDC
0x1800518cb  lea     rcx, ds:0[r13*8]
0x1800518d3  add     rcx, r13
0x1800518d6  lea     rsi, [rsi+rcx*4]
0x1800518da  mov     r9d, [rsi+4]
0x1800518de  cmp     r9d, 2
0x1800518e2  jz      loc_18005196C
0x1800518e8  cmp     r9d, 17h
0x1800518ec  jz      short loc_180051936
0x1800518ee  lea     rax, WPP_GLOBAL_Control
0x1800518f5  cmp     rbx, rax
0x1800518f8  jz      loc_180051E76
0x1800518fe  test    dword ptr [rbx+1Ch], 2000h
0x180051905  jz      loc_180051E76
0x18005190b  cmp     byte ptr [rbx+19h], 4
0x18005190f  jb      loc_180051E76
0x180051915  mov     rcx, [rbx+10h]
0x180051919  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180051920  mov     edx, 0Fh
0x180051925  call    WPP_SF_d
0x18005192a  mov     rbx, cs:WPP_GLOBAL_Control
0x180051931  jmp     loc_180051E76
0x180051936  lea     rax, WPP_GLOBAL_Control
0x18005193d  cmp     rbx, rax
0x180051940  jz      short loc_1800519A0
0x180051942  test    dword ptr [rbx+1Ch], 2000h
0x180051949  jz      short loc_1800519A0
0x18005194b  cmp     byte ptr [rbx+19h], 5
0x18005194f  jb      short loc_1800519A0
0x180051951  mov     rcx, [rbx+10h]
0x180051955  lea     r9, [rsi+0Ch]
0x180051959  mov     edx, 11h
0x18005195e  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180051965  call    WPP_SF_s
0x18005196a  jmp     short loc_1800519A0
0x18005196c  lea     rax, WPP_GLOBAL_Control
0x180051973  cmp     rbx, rax
0x180051976  jz      short loc_1800519A0
0x180051978  test    dword ptr [rbx+1Ch], 2000h
0x18005197f  jz      short loc_1800519A0
0x180051981  cmp     byte ptr [rbx+19h], 5
0x180051985  jb      short loc_1800519A0
0x180051987  mov     r9d, [rsi+0Ch]
0x18005198b  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180051992  mov     rcx, [rbx+10h]
0x180051996  mov     edx, 10h
0x18005199b  call    WPP_SF_d
0x1800519a0  xor     ebx, ebx
0x1800519a2  cmp     [rsi], ebx
0x1800519a4  jnz     short loc_1800519AC
0x1800519a6  mov     dword ptr [rsi], 1
0x1800519ac  mov     r9d, [rdi+354h]
0x1800519b3  lea     r8, [rsp+110h+InterfaceLuid]
0x1800519b8  mov     rdx, rsi
0x1800519bb  lea     rcx, [rbp+57h+Row]; void *
0x1800519bf  call    CreateRouteEntry
0x1800519c4  cmp     [rsi+1Ch], ebx
0x1800519c7  jz      loc_180051D3E
0x1800519cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800519d4  lea     r14, WPP_GLOBAL_Control
0x1800519db  mov     ebx, 2000h
0x1800519e0  cmp     rcx, r14
0x1800519e3  jz      short loc_180051A0C
0x1800519e5  test    [rcx+1Ch], ebx
0x1800519e8  jz      short loc_180051A0C
0x1800519ea  cmp     byte ptr [rcx+19h], 5
0x1800519ee  jb      short loc_180051A0C
0x1800519f0  mov     rcx, [rcx+10h]
0x1800519f4  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800519fb  mov     edx, 12h
0x180051a00  call    WPP_SF_
0x180051a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180051a0c  mov     eax, [rsi+20h]
0x180051a0f  test    eax, eax
0x180051a11  jz      short loc_180051A5B
0x180051a13  lea     rcx, [rbp+57h+Row]; Row
0x180051a17  mov     [rbp+57h+Row.InterfaceIndex], eax
0x180051a1a  call    cs:__imp_DeleteIpForwardEntry2
0x180051a20  test    eax, eax
0x180051a22  jz      short loc_180051A80
0x180051a24  mov     rcx, cs:WPP_GLOBAL_Control
0x180051a2b  cmp     rcx, r14
0x180051a2e  jz      short loc_180051A80
0x180051a30  test    [rcx+1Ch], ebx
0x180051a33  jz      short loc_180051A80
0x180051a35  cmp     byte ptr [rcx+19h], 2
0x180051a39  jb      short loc_180051A80
0x180051a3b  mov     r9, qword ptr [rsp+110h+InterfaceLuid]
0x180051a40  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180051a47  mov     rcx, [rcx+10h]
0x180051a4b  mov     edx, 13h
0x180051a50  mov     dword ptr [rsp+110h+SizePointer], eax
0x180051a54  call    WPP_SF_qD
0x180051a59  jmp     short loc_180051A80
0x180051a5b  cmp     rcx, r14
0x180051a5e  jz      short loc_180051A80
0x180051a60  test    [rcx+1Ch], ebx
0x180051a63  jz      short loc_180051A80
0x180051a65  cmp     byte ptr [rcx+19h], 4
0x180051a69  jb      short loc_180051A80
0x180051a6b  mov     rcx, [rcx+10h]
0x180051a6f  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180051a76  mov     edx, 14h
0x180051a7b  call    WPP_SF_
0x180051a80  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x180051a83  mov     ecx, 40h ; '@'; uFlags
0x180051a88  call    cs:__imp_LocalAlloc
0x180051a8e  mov     r14, rax
0x180051a91  test    rax, rax
0x180051a94  jz      loc_180051E87
0x180051a9a  mov     ecx, [rsi+4]; Family
0x180051a9d  lea     rax, [rbp+57h+uBytes]
0x180051aa1  mov     r9, r14; AdapterAddresses
0x180051aa4  mov     [rsp+110h+SizePointer], rax; SizePointer
0x180051aa9  xor     r8d, r8d; Reserved
0x180051aac  mov     edx, 90h; Flags
0x180051ab1  call    cs:__imp_GetAdaptersAddresses
0x180051ab7  mov     ebx, eax
0x180051ab9  cmp     eax, 6Fh ; 'o'
0x180051abc  jnz     short loc_180051B28
0x180051abe  mov     rcx, r14; hMem
0x180051ac1  call    cs:__imp_LocalFree
0x180051ac7  xor     r14d, r14d
0x180051aca  mov     r10, cs:WPP_GLOBAL_Control
0x180051ad1  lea     rax, WPP_GLOBAL_Control
0x180051ad8  cmp     r10, rax
0x180051adb  jz      short loc_180051B13
0x180051add  test    dword ptr [r10+1Ch], 2000h
0x180051ae5  jz      short loc_180051B13
0x180051ae7  cmp     byte ptr [r10+19h], 5
0x180051aec  jb      short loc_180051B13
0x180051aee  mov     eax, [rsp+110h+var_E0]
0x180051af2  lea     edx, [rbx-59h]
0x180051af5  mov     rcx, [r10+10h]
0x180051af9  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180051b00  mov     r9d, ebx
0x180051b03  mov     dword ptr [rsp+110h+SizePointer], eax
0x180051b07  call    WPP_SF_Dd
0x180051b0c  mov     r10, cs:WPP_GLOBAL_Control
0x180051b13  mov     eax, [rsp+110h+var_E0]
0x180051b17  inc     eax
0x180051b19  mov     [rsp+110h+var_E0], eax
0x180051b1d  cmp     eax, 3
0x180051b20  jb      loc_180051A80
0x180051b26  jmp     short loc_180051B2F
0x180051b28  mov     r10, cs:WPP_GLOBAL_Control
0x180051b2f  test    ebx, ebx
0x180051b31  jz      short loc_180051B6F
0x180051b33  lea     rdx, WPP_GLOBAL_Control
0x180051b3a  cmp     r10, rdx
0x180051b3d  jz      short loc_180051B76
0x180051b3f  test    dword ptr [r10+1Ch], 2000h
0x180051b47  jz      short loc_180051B76
0x180051b49  cmp     byte ptr [r10+19h], 5
0x180051b4e  jb      short loc_180051B76
0x180051b50  mov     rcx, [r10+10h]
0x180051b54  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180051b5b  mov     edx, 17h
0x180051b60  mov     r9d, ebx
0x180051b63  call    WPP_SF_d
0x180051b68  mov     r10, cs:WPP_GLOBAL_Control
0x180051b6f  lea     rdx, WPP_GLOBAL_Control
0x180051b76  mov     rbx, r14
0x180051b79  test    r14, r14
0x180051b7c  jz      short loc_180051B9C
0x180051b7e  mov     eax, [rbp+57h+Row.InterfaceIndex]
0x180051b81  cmp     [rbx+4], eax
0x180051b84  jz      loc_180051C37
0x180051b8a  cmp     [rbx+6Ch], eax
0x180051b8d  jz      loc_180051C37
0x180051b93  mov     rbx, [rbx+8]
0x180051b97  test    rbx, rbx
0x180051b9a  jnz     short loc_180051B81
0x180051b9c  cmp     r10, rdx
0x180051b9f  jz      short loc_180051BC7
0x180051ba1  test    dword ptr [r10+1Ch], 2000h
0x180051ba9  jz      short loc_180051BC7
0x180051bab  cmp     byte ptr [r10+19h], 5
0x180051bb0  jb      short loc_180051BC7
0x180051bb2  mov     edx, 1Ah
0x180051bb7  mov     rcx, [r10+10h]
0x180051bbb  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180051bc2  call    WPP_SF_
0x180051bc7  mov     eax, [rdi+354h]
0x180051bcd  lea     rcx, [rbp+57h+Row]; Row
0x180051bd1  mov     [rbp+57h+Row.InterfaceIndex], eax
0x180051bd4  call    cs:__imp_CreateIpForwardEntry2
0x180051bda  mov     edi, eax
0x180051bdc  test    eax, eax
0x180051bde  jnz     loc_180051CF1
0x180051be4  mov     rdi, [rbp+57h+var_C8]
0x180051be8  mov     eax, [rdi+354h]
0x180051bee  mov     [rsi+20h], eax
0x180051bf1  mov     rbx, cs:WPP_GLOBAL_Control
0x180051bf8  lea     rax, WPP_GLOBAL_Control
0x180051bff  cmp     rbx, rax
0x180051c02  jz      loc_180051E76
0x180051c08  test    dword ptr [rbx+1Ch], 2000h
0x180051c0f  jz      loc_180051E76
0x180051c15  cmp     byte ptr [rbx+19h], 4
0x180051c19  jb      loc_180051E76
0x180051c1f  mov     edx, 1Bh
0x180051c24  mov     r9, qword ptr [rsp+110h+InterfaceLuid]
0x180051c29  mov     rcx, [rbx+10h]
0x180051c2d  call    WPP_SF_I
0x180051c32  jmp     loc_18005192A
0x180051c37  mov     rcx, [rbx+0B0h]
0x180051c3e  mov     eax, [rsi+8]
0x180051c41  cmp     [rcx+20h], eax
0x180051c44  jnz     short loc_180051C9C
0x180051c46  cmp     dword ptr [rsi+4], 2
0x180051c4a  mov     rax, [rbx+18h]
0x180051c4e  mov     rcx, [rax+10h]
0x180051c52  jnz     short loc_180051C5C
0x180051c54  mov     eax, dword ptr [rbp+57h+Row.DestinationPrefix.Prefix+4]
0x180051c57  cmp     eax, [rcx+4]
0x180051c5a  jmp     short loc_180051C6E
0x180051c5c  mov     rax, qword ptr [rbp+57h+Row.DestinationPrefix.Prefix+8]
0x180051c60  cmp     rax, [rcx+8]
0x180051c64  jnz     short loc_180051C9C
0x180051c66  mov     rax, qword ptr [rbp+57h+Row.DestinationPrefix.Prefix+10h]
0x180051c6a  cmp     rax, [rcx+10h]
0x180051c6e  jnz     short loc_180051C9C
0x180051c70  cmp     r10, rdx
0x180051c73  jz      loc_180051BC7
0x180051c79  test    dword ptr [r10+1Ch], 2000h
0x180051c81  jz      loc_180051BC7
  ... truncated ...
```
