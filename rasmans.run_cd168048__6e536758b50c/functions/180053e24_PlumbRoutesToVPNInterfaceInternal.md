# PlumbRoutesToVPNInterfaceInternal

- ea: `0x180053e24`
- end: `0x180054606`
- name: `PlumbRoutesToVPNInterfaceInternal`
- size: `2018`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180053ab8`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x18000c3c0`
- `0x18003372c`
- `0x180053080`
- `0x180053e24`
- `0x1800562c4`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054130`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054175`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054595`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054175`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054595`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x1800540bc`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x1800540bc`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x18005428e`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180054442`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x18005428e`
- `IPHLPAPI!CreateIpForwardEntry2` at `0x180054442`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180053f4e`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180053f4e`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005415f`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18005415f`

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
0x180053e24  mov     [rsp-8+arg_18], rbx
0x180053e29  push    rbp
0x180053e2a  push    rsi
0x180053e2b  push    rdi
0x180053e2c  push    r12
0x180053e2e  push    r13
0x180053e30  push    r14
0x180053e32  push    r15
0x180053e34  lea     rbp, [rsp-27h]
0x180053e39  sub     rsp, 0E0h
0x180053e40  mov     rax, cs:__security_cookie
0x180053e47  xor     rax, rsp
0x180053e4a  mov     [rbp+57h+var_40], rax
0x180053e4e  mov     r12d, r8d
0x180053e51  mov     [rbp+57h+var_C0], rdx
0x180053e55  mov     rsi, rdx
0x180053e58  mov     [rbp+57h+var_C8], rcx
0x180053e5c  mov     rdi, rcx
0x180053e5f  mov     rbx, cs:WPP_GLOBAL_Control
0x180053e66  lea     rax, WPP_GLOBAL_Control
0x180053e6d  cmp     rbx, rax
0x180053e70  jz      short loc_180053E9D
0x180053e72  test    dword ptr [rbx+1Ch], 2000h
0x180053e79  jz      short loc_180053E9D
0x180053e7b  cmp     byte ptr [rbx+19h], 6
0x180053e7f  jb      short loc_180053E9D
0x180053e81  mov     rcx, [rbx+10h]
0x180053e85  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053e8c  mov     edx, 0Ch
0x180053e91  call    WPP_SF_
0x180053e96  mov     rbx, cs:WPP_GLOBAL_Control
0x180053e9d  xor     r15d, r15d
0x180053ea0  mov     dword ptr [rbp+57h+uBytes], 3A98h
0x180053ea7  xor     edx, edx; Val
0x180053ea9  lea     rcx, [rbp+57h+Row]; void *
0x180053ead  lea     r8d, [r15+68h]; Size
0x180053eb1  call    memset_0
0x180053eb6  mov     qword ptr [rsp+110h+InterfaceLuid], r15
0x180053ebb  lea     r14, WPP_GLOBAL_Control
0x180053ec2  cmp     rbx, r14
0x180053ec5  jz      short loc_180053EF4
0x180053ec7  test    dword ptr [rbx+1Ch], 2000h
0x180053ece  jz      short loc_180053EF4
0x180053ed0  cmp     byte ptr [rbx+19h], 5
0x180053ed4  jb      short loc_180053EF4
0x180053ed6  mov     rcx, [rbx+10h]
0x180053eda  lea     edx, [r15+0Dh]
0x180053ede  mov     r9d, r12d
0x180053ee1  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053ee8  call    WPP_SF_d
0x180053eed  mov     rbx, cs:WPP_GLOBAL_Control
0x180053ef4  test    r12d, r12d
0x180053ef7  jnz     short loc_180053F3A
0x180053ef9  cmp     rbx, r14
0x180053efc  jz      loc_1800545DB
0x180053f02  test    dword ptr [rbx+1Ch], 2000h
0x180053f09  jz      loc_1800545AF
0x180053f0f  cmp     byte ptr [rbx+19h], 5
0x180053f13  jb      loc_1800545AF
0x180053f19  mov     rcx, [rbx+10h]
0x180053f1d  lea     edx, [r12+0Eh]
0x180053f22  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053f29  call    WPP_SF_
0x180053f2e  mov     rbx, cs:WPP_GLOBAL_Control
0x180053f35  jmp     loc_1800545AF
0x180053f3a  xor     r14d, r14d
0x180053f3d  lea     rcx, [rdi+90h]; InterfaceGuid
0x180053f44  lea     rdx, [rsp+110h+InterfaceLuid]; InterfaceLuid
0x180053f49  mov     [rsp+110h+var_E0], r14d
0x180053f4e  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180053f55  nop     dword ptr [rax+rax+00h]
0x180053f5a  mov     rbx, cs:WPP_GLOBAL_Control
0x180053f61  xor     r13d, r13d
0x180053f64  test    r12d, r12d
0x180053f67  jz      loc_1800545A8
0x180053f6d  lea     rcx, ds:0[r13*8]
0x180053f75  add     rcx, r13
0x180053f78  lea     rsi, [rsi+rcx*4]
0x180053f7c  mov     r9d, [rsi+4]
0x180053f80  cmp     r9d, 2
0x180053f84  jz      loc_18005400E
0x180053f8a  cmp     r9d, 17h
0x180053f8e  jz      short loc_180053FD8
0x180053f90  lea     rax, WPP_GLOBAL_Control
0x180053f97  cmp     rbx, rax
0x180053f9a  jz      loc_18005453C
0x180053fa0  test    dword ptr [rbx+1Ch], 2000h
0x180053fa7  jz      loc_18005453C
0x180053fad  cmp     byte ptr [rbx+19h], 4
0x180053fb1  jb      loc_18005453C
0x180053fb7  mov     rcx, [rbx+10h]
0x180053fbb  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053fc2  mov     edx, 0Fh
0x180053fc7  call    WPP_SF_d
0x180053fcc  mov     rbx, cs:WPP_GLOBAL_Control
0x180053fd3  jmp     loc_18005453C
0x180053fd8  lea     rax, WPP_GLOBAL_Control
0x180053fdf  cmp     rbx, rax
0x180053fe2  jz      short loc_180054042
0x180053fe4  test    dword ptr [rbx+1Ch], 2000h
0x180053feb  jz      short loc_180054042
0x180053fed  cmp     byte ptr [rbx+19h], 5
0x180053ff1  jb      short loc_180054042
0x180053ff3  mov     rcx, [rbx+10h]
0x180053ff7  lea     r9, [rsi+0Ch]
0x180053ffb  mov     edx, 11h
0x180054000  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180054007  call    WPP_SF_s
0x18005400c  jmp     short loc_180054042
0x18005400e  lea     rax, WPP_GLOBAL_Control
0x180054015  cmp     rbx, rax
0x180054018  jz      short loc_180054042
0x18005401a  test    dword ptr [rbx+1Ch], 2000h
0x180054021  jz      short loc_180054042
0x180054023  cmp     byte ptr [rbx+19h], 5
0x180054027  jb      short loc_180054042
0x180054029  mov     r9d, [rsi+0Ch]
0x18005402d  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180054034  mov     rcx, [rbx+10h]
0x180054038  mov     edx, 10h
0x18005403d  call    WPP_SF_d
0x180054042  xor     ebx, ebx
0x180054044  cmp     [rsi], ebx
0x180054046  jnz     short loc_18005404E
0x180054048  mov     dword ptr [rsi], 1
0x18005404e  mov     r9d, [rdi+354h]
0x180054055  lea     r8, [rsp+110h+InterfaceLuid]
0x18005405a  mov     rdx, rsi
0x18005405d  lea     rcx, [rbp+57h+Row]; void *
0x180054061  call    CreateRouteEntry
0x180054066  cmp     [rsi+1Ch], ebx
0x180054069  jz      loc_1800543FE
0x18005406f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054076  lea     r14, WPP_GLOBAL_Control
0x18005407d  mov     ebx, 2000h
0x180054082  cmp     rcx, r14
0x180054085  jz      short loc_1800540AE
0x180054087  test    [rcx+1Ch], ebx
0x18005408a  jz      short loc_1800540AE
0x18005408c  cmp     byte ptr [rcx+19h], 5
0x180054090  jb      short loc_1800540AE
0x180054092  mov     rcx, [rcx+10h]
0x180054096  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005409d  mov     edx, 12h
0x1800540a2  call    WPP_SF_
0x1800540a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800540ae  mov     eax, [rsi+20h]
0x1800540b1  test    eax, eax
0x1800540b3  jz      short loc_180054103
0x1800540b5  lea     rcx, [rbp+57h+Row]; Row
0x1800540b9  mov     [rbp+57h+Row.InterfaceIndex], eax
0x1800540bc  call    cs:__imp_DeleteIpForwardEntry2
0x1800540c3  nop     dword ptr [rax+rax+00h]
0x1800540c8  test    eax, eax
0x1800540ca  jz      short loc_180054128
0x1800540cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800540d3  cmp     rcx, r14
0x1800540d6  jz      short loc_180054128
0x1800540d8  test    [rcx+1Ch], ebx
0x1800540db  jz      short loc_180054128
0x1800540dd  cmp     byte ptr [rcx+19h], 2
0x1800540e1  jb      short loc_180054128
0x1800540e3  mov     r9, qword ptr [rsp+110h+InterfaceLuid]
0x1800540e8  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800540ef  mov     rcx, [rcx+10h]
0x1800540f3  mov     edx, 13h
0x1800540f8  mov     dword ptr [rsp+110h+SizePointer], eax
0x1800540fc  call    WPP_SF_qD
0x180054101  jmp     short loc_180054128
0x180054103  cmp     rcx, r14
0x180054106  jz      short loc_180054128
0x180054108  test    [rcx+1Ch], ebx
0x18005410b  jz      short loc_180054128
0x18005410d  cmp     byte ptr [rcx+19h], 4
0x180054111  jb      short loc_180054128
0x180054113  mov     rcx, [rcx+10h]
0x180054117  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005411e  mov     edx, 14h
0x180054123  call    WPP_SF_
0x180054128  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x18005412b  mov     ecx, 40h ; '@'; uFlags
0x180054130  call    cs:__imp_LocalAlloc
0x180054137  nop     dword ptr [rax+rax+00h]
0x18005413c  mov     r14, rax
0x18005413f  test    rax, rax
0x180054142  jz      loc_18005454D
0x180054148  mov     ecx, [rsi+4]; Family
0x18005414b  lea     rax, [rbp+57h+uBytes]
0x18005414f  mov     r9, r14; AdapterAddresses
0x180054152  mov     [rsp+110h+SizePointer], rax; SizePointer
0x180054157  xor     r8d, r8d; Reserved
0x18005415a  mov     edx, 90h; Flags
0x18005415f  call    cs:__imp_GetAdaptersAddresses
0x180054166  nop     dword ptr [rax+rax+00h]
0x18005416b  mov     ebx, eax
0x18005416d  cmp     eax, 6Fh ; 'o'
0x180054170  jnz     short loc_1800541E2
0x180054172  mov     rcx, r14; hMem
0x180054175  call    cs:__imp_LocalFree
0x18005417c  nop     dword ptr [rax+rax+00h]
0x180054181  xor     r14d, r14d
0x180054184  mov     r10, cs:WPP_GLOBAL_Control
0x18005418b  lea     rax, WPP_GLOBAL_Control
0x180054192  cmp     r10, rax
0x180054195  jz      short loc_1800541CD
0x180054197  test    dword ptr [r10+1Ch], 2000h
0x18005419f  jz      short loc_1800541CD
0x1800541a1  cmp     byte ptr [r10+19h], 5
0x1800541a6  jb      short loc_1800541CD
0x1800541a8  mov     eax, [rsp+110h+var_E0]
0x1800541ac  lea     edx, [rbx-59h]
0x1800541af  mov     rcx, [r10+10h]
0x1800541b3  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800541ba  mov     r9d, ebx
0x1800541bd  mov     dword ptr [rsp+110h+SizePointer], eax
0x1800541c1  call    WPP_SF_Dd
0x1800541c6  mov     r10, cs:WPP_GLOBAL_Control
0x1800541cd  mov     eax, [rsp+110h+var_E0]
0x1800541d1  inc     eax
0x1800541d3  mov     [rsp+110h+var_E0], eax
0x1800541d7  cmp     eax, 3
0x1800541da  jb      loc_180054128
0x1800541e0  jmp     short loc_1800541E9
0x1800541e2  mov     r10, cs:WPP_GLOBAL_Control
0x1800541e9  test    ebx, ebx
0x1800541eb  jz      short loc_180054229
0x1800541ed  lea     rdx, WPP_GLOBAL_Control
0x1800541f4  cmp     r10, rdx
0x1800541f7  jz      short loc_180054230
0x1800541f9  test    dword ptr [r10+1Ch], 2000h
0x180054201  jz      short loc_180054230
0x180054203  cmp     byte ptr [r10+19h], 5
0x180054208  jb      short loc_180054230
0x18005420a  mov     rcx, [r10+10h]
0x18005420e  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180054215  mov     edx, 17h
0x18005421a  mov     r9d, ebx
0x18005421d  call    WPP_SF_d
0x180054222  mov     r10, cs:WPP_GLOBAL_Control
0x180054229  lea     rdx, WPP_GLOBAL_Control
0x180054230  mov     rbx, r14
0x180054233  test    r14, r14
0x180054236  jz      short loc_180054256
0x180054238  mov     eax, [rbp+57h+Row.InterfaceIndex]
0x18005423b  cmp     [rbx+4], eax
0x18005423e  jz      loc_1800542F7
0x180054244  cmp     [rbx+6Ch], eax
0x180054247  jz      loc_1800542F7
0x18005424d  mov     rbx, [rbx+8]
0x180054251  test    rbx, rbx
0x180054254  jnz     short loc_18005423B
0x180054256  cmp     r10, rdx
0x180054259  jz      short loc_180054281
0x18005425b  test    dword ptr [r10+1Ch], 2000h
0x180054263  jz      short loc_180054281
0x180054265  cmp     byte ptr [r10+19h], 5
0x18005426a  jb      short loc_180054281
0x18005426c  mov     edx, 1Ah
0x180054271  mov     rcx, [r10+10h]
0x180054275  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005427c  call    WPP_SF_
0x180054281  mov     eax, [rdi+354h]
0x180054287  lea     rcx, [rbp+57h+Row]; Row
0x18005428b  mov     [rbp+57h+Row.InterfaceIndex], eax
0x18005428e  call    cs:__imp_CreateIpForwardEntry2
0x180054295  nop     dword ptr [rax+rax+00h]
0x18005429a  mov     edi, eax
0x18005429c  test    eax, eax
0x18005429e  jnz     loc_1800543B1
0x1800542a4  mov     rdi, [rbp+57h+var_C8]
0x1800542a8  mov     eax, [rdi+354h]
0x1800542ae  mov     [rsi+20h], eax
0x1800542b1  mov     rbx, cs:WPP_GLOBAL_Control
0x1800542b8  lea     rax, WPP_GLOBAL_Control
0x1800542bf  cmp     rbx, rax
0x1800542c2  jz      loc_18005453C
0x1800542c8  test    dword ptr [rbx+1Ch], 2000h
0x1800542cf  jz      loc_18005453C
0x1800542d5  cmp     byte ptr [rbx+19h], 4
0x1800542d9  jb      loc_18005453C
0x1800542df  mov     edx, 1Bh
0x1800542e4  mov     r9, qword ptr [rsp+110h+InterfaceLuid]
0x1800542e9  mov     rcx, [rbx+10h]
0x1800542ed  call    WPP_SF_I
0x1800542f2  jmp     loc_180053FCC
0x1800542f7  mov     rcx, [rbx+0B0h]
0x1800542fe  mov     eax, [rsi+8]
0x180054301  cmp     [rcx+20h], eax
0x180054304  jnz     short loc_18005435C
0x180054306  cmp     dword ptr [rsi+4], 2
0x18005430a  mov     rax, [rbx+18h]
0x18005430e  mov     rcx, [rax+10h]
0x180054312  jnz     short loc_18005431C
0x180054314  mov     eax, dword ptr [rbp+57h+Row.DestinationPrefix.Prefix+4]
0x180054317  cmp     eax, [rcx+4]
0x18005431a  jmp     short loc_18005432E
0x18005431c  mov     rax, qword ptr [rbp+57h+Row.DestinationPrefix.Prefix+8]
0x180054320  cmp     rax, [rcx+8]
0x180054324  jnz     short loc_18005435C
0x180054326  mov     rax, qword ptr [rbp+57h+Row.DestinationPrefix.Prefix+10h]
  ... truncated ...
```
