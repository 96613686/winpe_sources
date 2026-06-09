# OpenDhcpv6Socket

- ea: `0x180006ed8`
- end: `0x18000733d`
- name: `OpenDhcpv6Socket`
- size: `1125`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180008f80`
- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`
- `0x1800216a4`
- `0x1800218e0`
- `0x180021b58`
- `0x1800225c8`
- `0x180022b80`

## callees

- `0x180001d8c`
- `0x180004b30`
- `0x180006ed8`
- `0x180007564`
- `0x1800075b0`
- `0x1800075f8`
- `0x18000e55c`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180028a64`
- `0x180031008`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033900`
- `0x180033970`
- `0x180033a9c`
- `0x180033de4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006ffa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007123`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007123`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006fdd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180006fdd`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180006f98`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000721a`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180006f98`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000721a`

## pseudocode

```c
__int64 __fastcall OpenDhcpv6Socket(__int64 a1, int a2, int a3)
{
  IP_ADAPTER_ADDRESSES_LH *v4; // rbp
  __int64 v5; // rcx
  ULONG AdaptersAddresses; // edi
  IP_ADAPTER_ADDRESSES_LH *v7; // r13
  PIP_ADAPTER_UNICAST_ADDRESS_LH i; // rax
  LPSOCKADDR lpSockaddr; // rdx
  __int64 v11; // rdx
  unsigned int v12; // eax
  ULONG SizePointer; // [rsp+30h] [rbp-D8h] BYREF
  int v14; // [rsp+34h] [rbp-D4h]
  int v15; // [rsp+38h] [rbp-D0h]
  __int64 v16; // [rsp+40h] [rbp-C8h] BYREF
  WCHAR WideCharStr[56]; // [rsp+50h] [rbp-B8h] BYREF

  v14 = a2;
  v15 = a3;
  v16 = 0;
  SizePointer = 0;
  memset_0(WideCharStr, 0, 0x64u);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 23, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, 50);
    return 50;
  }
  if ( a1 && (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_J(1028, 24, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 24));
  if ( *(_QWORD *)(a1 + 64) != -1 )
    return 0;
  if ( Dhcpv6GlobalPdcCount <= 0 && (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_d(1025, 25, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, (unsigned int)Dhcpv6GlobalPdcCount);
  SizePointer = 15000;
  v4 = (IP_ADAPTER_ADDRESSES_LH *)DhcpAlloc(15000);
  if ( !v4 )
    return 8;
  AdaptersAddresses = GetAdaptersAddresses(0x17u, 0xEu, 0, v4, &SizePointer);
  if ( AdaptersAddresses == 111 )
  {
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
    v4 = (IP_ADAPTER_ADDRESSES_LH *)DhcpAlloc(SizePointer);
    if ( v4 )
    {
      AdaptersAddresses = GetAdaptersAddresses(0x17u, 0xEu, 0, v4, &SizePointer);
      goto LABEL_7;
    }
    return 8;
  }
LABEL_7:
  v7 = v4;
  if ( AdaptersAddresses )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_DS(
        1025,
        26,
        (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids,
        AdaptersAddresses,
        *(_QWORD *)(a1 + 56));
LABEL_18:
    *(_QWORD *)(a1 + 64) = -1;
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_SD(
        1025,
        31,
        (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids,
        *(_QWORD *)(a1 + 56),
        AdaptersAddresses);
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
      McTemplateU0qq_EtwEventWriteTransfer(v5, ErrorOpeningSocket, *(unsigned int *)(a1 + 48), AdaptersAddresses);
    TraceLogErrorv6(a1, AdaptersAddresses, 124);
  }
  else
  {
    while ( 1 )
    {
      if ( !v4 )
      {
        AdaptersAddresses = 1627;
        goto LABEL_18;
      }
      if ( !MultiByteToWideChar(0, 0, v4->AdapterName, -1, WideCharStr, 50) )
      {
        AdaptersAddresses = GetLastError();
        if ( !AdaptersAddresses )
          goto LABEL_31;
        goto LABEL_18;
      }
      if ( !(unsigned int)_o__wcsicmp(WideCharStr, *(_QWORD *)(a1 + 56)) )
        break;
      v4 = v4->Next;
    }
    if ( v14 && *(_DWORD *)(a1 + 560) )
    {
      if ( !(unsigned int)GetScopedIpv6Address(1, v4, &v16) )
      {
        if ( (xmmword_1800423E0 & 0x10) == 0 )
          goto LABEL_31;
        v11 = 27;
        goto LABEL_47;
      }
LABEL_28:
      AdaptersAddresses = InitializeDhcpv6Socket(a1 + 64);
      if ( AdaptersAddresses )
        goto LABEL_18;
      if ( Dhcpv6GlobalUseWakeUpPattern && v15 )
      {
        v12 = PlumbWakeUpPatternOnDhcpv6Socket(a1 + 64);
        if ( v12 )
        {
          *(_DWORD *)(a1 + 9052) = 0;
          if ( (xmmword_1800423E0 & 2) != 0 )
            WPP_SF_D(1025, 30, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v12);
        }
        else
        {
          *(_DWORD *)(a1 + 9052) = 1;
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_(1028, 29, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
          AdaptersAddresses = 0;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 9052) = 0;
      }
    }
    else
    {
      for ( i = v4->FirstUnicastAddress; i; i = i->Next )
      {
        lpSockaddr = i->Address.lpSockaddr;
        if ( lpSockaddr->sa_data[6] == -2 && lpSockaddr->sa_data[7] == (CHAR)0x80 )
          goto LABEL_28;
      }
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        v11 = 28;
LABEL_47:
        WPP_SF_S(1028, v11, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 56));
      }
    }
  }
LABEL_31:
  HeapFree(NtCurrentPeb()->ProcessHeap, 0, v7);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x180006ed8  push    rbx
0x180006eda  push    rbp
0x180006edb  push    rsi
0x180006edc  push    rdi
0x180006edd  push    r12
0x180006edf  push    r13
0x180006ee1  sub     rsp, 0D8h
0x180006ee8  mov     rax, cs:__security_cookie
0x180006eef  xor     rax, rsp
0x180006ef2  mov     [rsp+108h+var_48], rax
0x180006efa  mov     [rsp+108h+var_D4], edx
0x180006efe  mov     rbx, rcx
0x180006f01  xor     edx, edx; Val
0x180006f03  mov     [rsp+108h+var_D0], r8d
0x180006f08  lea     rcx, [rsp+108h+WideCharStr]; void *
0x180006f0d  mov     [rsp+108h+var_C8], 0
0x180006f16  mov     [rsp+108h+var_D8], 0
0x180006f1e  lea     r8d, [rdx+64h]; Size
0x180006f22  call    memset_0
0x180006f27  call    DhcpIsFSEGuestSystem
0x180006f2c  test    eax, eax
0x180006f2e  jnz     loc_1800071B2
0x180006f34  lea     rsi, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180006f3b  test    rbx, rbx
0x180006f3e  jnz     loc_180007078
0x180006f44  lea     r12, [rbx+40h]
0x180006f48  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180006f4d  jnz     loc_1800071FC
0x180006f53  mov     r9d, cs:Dhcpv6GlobalPdcCount
0x180006f5a  test    r9d, r9d
0x180006f5d  jle     loc_180007152
0x180006f63  mov     ecx, 3A98h
0x180006f68  mov     [rsp+108h+var_D8], ecx
0x180006f6c  call    DhcpAlloc
0x180006f71  mov     rbp, rax
0x180006f74  test    rax, rax
0x180006f77  jz      loc_1800070D3
0x180006f7d  xor     r8d, r8d; Reserved
0x180006f80  lea     rax, [rsp+108h+var_D8]
0x180006f85  mov     r9, rbp; AdapterAddresses
0x180006f88  mov     [rsp+108h+SizePointer], rax; SizePointer
0x180006f8d  lea     r13d, [r8+0Eh]
0x180006f91  mov     edx, r13d; Flags
0x180006f94  lea     ecx, [r8+17h]; Family
0x180006f98  call    cs:__imp_GetAdaptersAddresses
0x180006f9f  nop     dword ptr [rax+rax+00h]
0x180006fa4  mov     edi, eax
0x180006fa6  cmp     eax, 6Fh ; 'o'
0x180006fa9  jz      loc_1800070A0
0x180006faf  mov     r13, rbp
0x180006fb2  test    edi, edi
0x180006fb4  jnz     loc_18000722D
0x180006fba  test    rbp, rbp
0x180006fbd  jz      short loc_18000703C
0x180006fbf  mov     r8, [rbp+10h]; lpMultiByteStr
0x180006fc3  lea     rax, [rsp+108h+WideCharStr]
0x180006fc8  mov     [rsp+108h+cchWideChar], 32h ; '2'; cchWideChar
0x180006fd0  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180006fd4  xor     edx, edx; dwFlags
0x180006fd6  mov     [rsp+108h+SizePointer], rax; lpWideCharStr
0x180006fdb  xor     ecx, ecx; CodePage
0x180006fdd  call    cs:__imp_MultiByteToWideChar
0x180006fe4  nop     dword ptr [rax+rax+00h]
0x180006fe9  test    eax, eax
0x180006feb  jz      loc_1800071C5
0x180006ff1  mov     rdx, [rbx+38h]
0x180006ff5  lea     rcx, [rsp+108h+WideCharStr]
0x180006ffa  call    cs:__imp__o__wcsicmp
0x180007001  nop     dword ptr [rax+rax+00h]
0x180007006  test    eax, eax
0x180007008  jz      short loc_180007010
0x18000700a  mov     rbp, [rbp+8]
0x18000700e  jmp     short loc_180006FBA
0x180007010  cmp     [rsp+108h+var_D4], 0
0x180007015  jnz     loc_180007176
0x18000701b  mov     rax, [rbp+18h]
0x18000701f  test    rax, rax
0x180007022  jz      loc_1800072F4
0x180007028  mov     rdx, [rax+10h]
0x18000702c  cmp     byte ptr [rdx+8], 0FEh
0x180007030  jz      loc_1800070DA
0x180007036  mov     rax, [rax+8]
0x18000703a  jmp     short loc_18000701F
0x18000703c  mov     edi, 65Bh
0x180007041  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180007049  test    byte ptr cs:xmmword_1800423E0, 2
0x180007050  jnz     loc_180007306
0x180007056  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x18000705d  jnz     loc_180007325
0x180007063  mov     r8d, 7Ch ; '|'
0x180007069  mov     edx, edi
0x18000706b  mov     rcx, rbx
0x18000706e  call    TraceLogErrorv6
0x180007073  jmp     loc_18000710C
0x180007078  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000707f  jz      loc_180006F44
0x180007085  mov     r9, [rbx+18h]
0x180007089  mov     edx, 18h
0x18000708e  mov     ecx, 404h
0x180007093  mov     r8, rsi
0x180007096  call    WPP_SF_J
0x18000709b  jmp     loc_180006F44
0x1800070a0  mov     rcx, gs:60h
0x1800070a9  mov     r8, rbp; lpMem
0x1800070ac  xor     edx, edx; dwFlags
0x1800070ae  mov     rcx, [rcx+30h]; hHeap
0x1800070b2  call    cs:__imp_HeapFree
0x1800070b9  nop     dword ptr [rax+rax+00h]
0x1800070be  mov     ecx, [rsp+108h+var_D8]
0x1800070c2  call    DhcpAlloc
0x1800070c7  mov     rbp, rax
0x1800070ca  test    rax, rax
0x1800070cd  jnz     loc_180007203
0x1800070d3  mov     eax, 8
0x1800070d8  jmp     short loc_180007131
0x1800070da  cmp     byte ptr [rdx+9], 80h
0x1800070de  jnz     loc_180007036
0x1800070e4  mov     rcx, r12
0x1800070e7  call    InitializeDhcpv6Socket
0x1800070ec  mov     edi, eax
0x1800070ee  test    eax, eax
0x1800070f0  jnz     loc_180007041
0x1800070f6  cmp     cs:Dhcpv6GlobalUseWakeUpPattern, eax
0x1800070fc  jnz     loc_180007282
0x180007102  mov     dword ptr [rbx+235Ch], 0
0x18000710c  test    r13, r13
0x18000710f  jz      short loc_18000712F
0x180007111  mov     rcx, gs:60h
0x18000711a  mov     r8, r13; lpMem
0x18000711d  xor     edx, edx; dwFlags
0x18000711f  mov     rcx, [rcx+30h]; hHeap
0x180007123  call    cs:__imp_HeapFree
0x18000712a  nop     dword ptr [rax+rax+00h]
0x18000712f  mov     eax, edi
0x180007131  mov     rcx, [rsp+108h+var_48]
0x180007139  xor     rcx, rsp; StackCookie
0x18000713c  call    __security_check_cookie
0x180007141  add     rsp, 0D8h
0x180007148  pop     r13
0x18000714a  pop     r12
0x18000714c  pop     rdi
0x18000714d  pop     rsi
0x18000714e  pop     rbp
0x18000714f  pop     rbx
0x180007150  retn
0x180007152  test    byte ptr cs:xmmword_1800423E0, 2
0x180007159  jz      loc_180006F63
0x18000715f  mov     edx, 19h
0x180007164  mov     ecx, 401h
0x180007169  mov     r8, rsi
0x18000716c  call    WPP_SF_d
0x180007171  jmp     loc_180006F63
0x180007176  cmp     dword ptr [rbx+230h], 0
0x18000717d  jz      loc_18000701B
0x180007183  lea     r8, [rsp+108h+var_C8]
0x180007188  mov     rdx, rbp
0x18000718b  mov     ecx, 1
0x180007190  call    GetScopedIpv6Address
0x180007195  test    eax, eax
0x180007197  jnz     loc_180007278
0x18000719d  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800071a4  jz      loc_18000710C
0x1800071aa  lea     edx, [rax+1Bh]
0x1800071ad  jmp     loc_180007262
0x1800071b2  test    byte ptr cs:xmmword_1800423E0, 2
0x1800071b9  jnz     short loc_1800071E0
0x1800071bb  mov     eax, 32h ; '2'
0x1800071c0  jmp     loc_180007131
0x1800071c5  call    cs:__imp_GetLastError
0x1800071cc  nop     dword ptr [rax+rax+00h]
0x1800071d1  mov     edi, eax
0x1800071d3  test    eax, eax
0x1800071d5  jz      loc_18000710C
0x1800071db  jmp     loc_180007041
0x1800071e0  mov     edx, 17h
0x1800071e5  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800071ec  mov     ecx, 401h
0x1800071f1  lea     r9d, [rdx+1Bh]
0x1800071f5  call    WPP_SF_D
0x1800071fa  jmp     short loc_1800071BB
0x1800071fc  xor     eax, eax
0x1800071fe  jmp     loc_180007131
0x180007203  xor     r8d, r8d; Reserved
0x180007206  lea     rax, [rsp+108h+var_D8]
0x18000720b  mov     r9, rbp; AdapterAddresses
0x18000720e  mov     [rsp+108h+SizePointer], rax; SizePointer
0x180007213  mov     edx, r13d; Flags
0x180007216  lea     ecx, [r8+17h]; Family
0x18000721a  call    cs:__imp_GetAdaptersAddresses
0x180007221  nop     dword ptr [rax+rax+00h]
0x180007226  mov     edi, eax
0x180007228  jmp     loc_180006FAF
0x18000722d  test    byte ptr cs:xmmword_1800423E0, 2
0x180007234  jz      loc_180007041
0x18000723a  mov     rax, [rbx+38h]
0x18000723e  mov     edx, 1Ah
0x180007243  mov     ecx, 401h
0x180007248  mov     [rsp+108h+SizePointer], rax
0x18000724d  mov     r9d, edi
0x180007250  mov     r8, rsi
0x180007253  call    WPP_SF_DS
0x180007258  jmp     loc_180007041
0x18000725d  mov     edx, 1Ch
0x180007262  mov     r9, [rbx+38h]
0x180007266  mov     ecx, 404h
0x18000726b  mov     r8, rsi
0x18000726e  call    WPP_SF_S
0x180007273  jmp     loc_18000710C
0x180007278  mov     rdx, [rsp+108h+var_C8]
0x18000727d  jmp     loc_1800070E4
0x180007282  cmp     [rsp+108h+var_D0], 0
0x180007287  jz      loc_180007102
0x18000728d  mov     rcx, r12
0x180007290  call    PlumbWakeUpPatternOnDhcpv6Socket
0x180007295  test    eax, eax
0x180007297  jnz     short loc_1800072C3
0x180007299  mov     dword ptr [rbx+235Ch], 1
0x1800072a3  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800072aa  jz      short loc_1800072BC
0x1800072ac  lea     edx, [rax+1Dh]
0x1800072af  mov     ecx, 404h
0x1800072b4  mov     r8, rsi
0x1800072b7  call    WPP_SF_
0x1800072bc  xor     edi, edi
0x1800072be  jmp     loc_18000710C
0x1800072c3  mov     dword ptr [rbx+235Ch], 0
0x1800072cd  test    byte ptr cs:xmmword_1800423E0, 2
0x1800072d4  jz      loc_18000710C
0x1800072da  mov     edx, 1Eh
0x1800072df  mov     ecx, 401h
0x1800072e4  mov     r9d, eax
0x1800072e7  mov     r8, rsi
0x1800072ea  call    WPP_SF_D
0x1800072ef  jmp     loc_18000710C
0x1800072f4  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800072fb  jz      loc_18000710C
0x180007301  jmp     loc_18000725D
0x180007306  mov     r9, [rbx+38h]
0x18000730a  mov     edx, 1Fh
0x18000730f  mov     ecx, 401h
0x180007314  mov     dword ptr [rsp+108h+SizePointer], edi
0x180007318  mov     r8, rsi
0x18000731b  call    WPP_SF_SD
0x180007320  jmp     loc_180007056
0x180007325  mov     r8d, [rbx+30h]
0x180007329  lea     rdx, ErrorOpeningSocket
0x180007330  mov     r9d, edi
0x180007333  call    McTemplateU0qq_EtwEventWriteTransfer
0x180007338  jmp     loc_180007063
```
