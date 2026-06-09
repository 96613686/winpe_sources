# NcaConfigMgrSortDteList(NCA_POLICY_ *)

- ea: `0x180005df8`
- end: `0x180006185`
- name: `?NcaConfigMgrSortDteList@@YAJPEAUNCA_POLICY_@@@Z`
- size: `909`
- prototype: `__int64 __fastcall(struct NCA_POLICY_ *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180005180`
- `0x180005770`
- `0x180005c20`

## callees

- `0x180003770`
- `0x180004f34`
- `0x180005398`
- `0x180005df8`
- `0x180019d84`
- `0x18001ac28`
- `0x18001cc3e`
- `0x18001cc70`

## import_xrefs

- `WS2_32!InetPtonW` at `0x180005fb6`
- `WS2_32!InetPtonW` at `0x180005fb6`
- `IPHLPAPI!FreeMibTable` at `0x180006149`
- `IPHLPAPI!FreeMibTable` at `0x180006149`
- `IPHLPAPI!CreateSortedAddressPairs` at `0x18000601f`
- `IPHLPAPI!CreateSortedAddressPairs` at `0x18000601f`
- `ntdll!RtlIpv6AddressToStringW` at `0x180006083`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800060a3`
- `ntdll!RtlIpv6AddressToStringW` at `0x180006083`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800060a3`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrSortDteList(struct NCA_POLICY_ *a1)
{
  SOCKADDR_IN6_LH *v2; // rsi
  int Multisite; // eax
  unsigned int v4; // eax
  __int64 i; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  __int64 j; // r14
  ULONG v12; // r9d
  __int64 v13; // r15
  unsigned int v14; // eax
  __int64 k; // r14
  __int64 v16; // r12
  __int64 v17; // r15
  int v18; // eax
  int v19; // ecx
  ULONG SortedAddressPairCount; // [rsp+40h] [rbp-C0h] BYREF
  PSOCKADDR_IN6 DestinationAddressList; // [rsp+48h] [rbp-B8h] BYREF
  PSOCKADDR_IN6_PAIR SortedAddressPairList; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR S[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v25[264]; // [rsp+270h] [rbp+170h] BYREF

  SortedAddressPairCount = 0;
  memset_0(S, 0, 0x208u);
  memset_0(v25, 0, 0x208u);
  v2 = 0;
  SortedAddressPairList = 0;
  DestinationAddressList = 0;
  Multisite = NcaConfigMgrLoadMultisite(a1);
  if ( Multisite < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids,
        (unsigned int)Multisite);
    goto LABEL_46;
  }
  v4 = *((_DWORD *)a1 + 4);
  for ( i = 0; (unsigned int)i < v4; v4 = *((_DWORD *)a1 + 4) )
  {
    v6 = 3 * i;
    i = (unsigned int)(i + 1);
    *(_DWORD *)(*((_QWORD *)a1 + 3) + 8 * v6 + 16) = 0;
  }
  if ( !*((_DWORD *)a1 + 23) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_46;
    v8 = 41;
LABEL_11:
    v9 = 0;
LABEL_45:
    WPP_SF_d(v7[2], v8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids, v9);
    goto LABEL_46;
  }
  if ( !*((_QWORD *)a1 + 12) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_46;
    v8 = 42;
    goto LABEL_11;
  }
  if ( v4 >= 2 )
  {
    v10 = NcaAllocCheckSize(28, v4, &DestinationAddressList);
    if ( v10 >= 0 )
    {
      v2 = DestinationAddressList;
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        v12 = *((_DWORD *)a1 + 4);
        if ( (unsigned int)j >= v12 )
          break;
        v13 = (unsigned int)j;
        if ( InetPtonW(23, *(PCWSTR *)(*((_QWORD *)a1 + 3) + 24 * j + 8), &v2[v13].sin6_addr) != 1 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 44;
LABEL_44:
            v9 = 87;
            goto LABEL_45;
          }
          goto LABEL_46;
        }
        v2[v13].sin6_family = 23;
      }
      v14 = CreateSortedAddressPairs(0, 0, v2, v12, 0, &SortedAddressPairList, &SortedAddressPairCount);
      if ( v14 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 45;
          v9 = v14;
          goto LABEL_45;
        }
      }
      else if ( SortedAddressPairList && SortedAddressPairCount >= 2 )
      {
        RtlIpv6AddressToStringW(&SortedAddressPairList->DestinationAddress->sin6_addr, S);
        RtlIpv6AddressToStringW(&SortedAddressPairList[1].DestinationAddress->sin6_addr, v25);
        for ( k = 0; (unsigned int)k < *((_DWORD *)a1 + 4); *(_DWORD *)(*((_QWORD *)a1 + 3) + 8 * v16 + 16) = v19 )
        {
          v16 = 3 * k;
          v17 = *(_QWORD *)(*((_QWORD *)a1 + 3) + 24 * k + 8);
          if ( !(unsigned int)NcaWcsICmp(v17, S) || (v18 = NcaWcsICmp(v17, v25), v19 = 2, !v18) )
            v19 = 1;
          k = (unsigned int)(k + 1);
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 46;
          goto LABEL_44;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids,
          (unsigned int)v10);
      v2 = DestinationAddressList;
    }
  }
LABEL_46:
  if ( SortedAddressPairList )
    FreeMibTable(SortedAddressPairList);
  if ( v2 )
    NcaFree(v2);
  return 0;
}

```

## disassembly

```asm
0x180005df8  push    rbp
0x180005dfa  push    rsi
0x180005dfb  push    rdi
0x180005dfc  push    r12
0x180005dfe  push    r14
0x180005e00  push    r15
0x180005e02  lea     rbp, [rsp-398h]
0x180005e0a  sub     rsp, 498h
0x180005e11  mov     rax, cs:__security_cookie
0x180005e18  xor     rax, rsp
0x180005e1b  mov     [rbp+3C0h+var_40], rax
0x180005e22  mov     rdi, rcx
0x180005e25  mov     [rsp+4C0h+var_480], 0
0x180005e2d  lea     rcx, [rsp+4C0h+S]; void *
0x180005e32  xor     edx, edx; Val
0x180005e34  mov     r8d, 208h; Size
0x180005e3a  call    memset_0
0x180005e3f  xor     edx, edx; Val
0x180005e41  lea     rcx, [rbp+3C0h+var_250]; void *
0x180005e48  mov     r8d, 208h; Size
0x180005e4e  call    memset_0
0x180005e53  xor     esi, esi
0x180005e55  mov     [rsp+4C0h+var_470], 0
0x180005e5e  mov     rcx, rdi; struct NCA_POLICY_ *
0x180005e61  mov     [rsp+4C0h+DestinationAddressList], rsi
0x180005e66  call    ?NcaConfigMgrLoadMultisite@@YAJPEAUNCA_POLICY_@@@Z; NcaConfigMgrLoadMultisite(NCA_POLICY_ *)
0x180005e6b  test    eax, eax
0x180005e6d  jns     short loc_180005EAB
0x180005e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e76  lea     rdx, WPP_GLOBAL_Control
0x180005e7d  cmp     rcx, rdx
0x180005e80  jz      loc_18000613F
0x180005e86  test    byte ptr [rcx+1Ch], 1
0x180005e8a  jz      loc_18000613F
0x180005e90  mov     rcx, [rcx+10h]
0x180005e94  lea     edx, [rsi+28h]
0x180005e97  mov     r9d, eax
0x180005e9a  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180005ea1  call    WPP_SF_d
0x180005ea6  jmp     loc_18000613F
0x180005eab  mov     eax, [rdi+10h]
0x180005eae  xor     edx, edx
0x180005eb0  test    eax, eax
0x180005eb2  jz      short loc_180005EC9
0x180005eb4  mov     rax, [rdi+18h]
0x180005eb8  lea     rcx, [rdx+rdx*2]
0x180005ebc  inc     edx
0x180005ebe  mov     [rax+rcx*8+10h], esi
0x180005ec2  mov     eax, [rdi+10h]
0x180005ec5  cmp     edx, eax
0x180005ec7  jb      short loc_180005EB4
0x180005ec9  cmp     [rdi+5Ch], esi
0x180005ecc  jnz     short loc_180005EFC
0x180005ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ed5  lea     rdx, WPP_GLOBAL_Control
0x180005edc  cmp     rcx, rdx
0x180005edf  jz      loc_18000613F
0x180005ee5  test    byte ptr [rcx+1Ch], 1
0x180005ee9  jz      loc_18000613F
0x180005eef  mov     edx, 29h ; ')'
0x180005ef4  xor     r9d, r9d
0x180005ef7  jmp     loc_18000612F
0x180005efc  cmp     [rdi+60h], rsi
0x180005f00  jnz     short loc_180005F2A
0x180005f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f09  lea     rdx, WPP_GLOBAL_Control
0x180005f10  cmp     rcx, rdx
0x180005f13  jz      loc_18000613F
0x180005f19  test    byte ptr [rcx+1Ch], 1
0x180005f1d  jz      loc_18000613F
0x180005f23  mov     edx, 2Ah ; '*'
0x180005f28  jmp     short loc_180005EF4
0x180005f2a  cmp     eax, 2
0x180005f2d  jb      loc_18000613F
0x180005f33  mov     edx, eax
0x180005f35  lea     r8, [rsp+4C0h+DestinationAddressList]
0x180005f3a  mov     ecx, 1Ch
0x180005f3f  call    NcaAllocCheckSize
0x180005f44  test    eax, eax
0x180005f46  jns     short loc_180005F83
0x180005f48  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f4f  lea     rdx, WPP_GLOBAL_Control
0x180005f56  cmp     rcx, rdx
0x180005f59  jz      short loc_180005F79
0x180005f5b  test    byte ptr [rcx+1Ch], 1
0x180005f5f  jz      short loc_180005F79
0x180005f61  mov     rcx, [rcx+10h]
0x180005f65  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180005f6c  mov     edx, 2Bh ; '+'
0x180005f71  mov     r9d, eax
0x180005f74  call    WPP_SF_d
0x180005f79  mov     rsi, [rsp+4C0h+DestinationAddressList]
0x180005f7e  jmp     loc_18000613F
0x180005f83  mov     rsi, [rsp+4C0h+DestinationAddressList]
0x180005f88  xor     r14d, r14d
0x180005f8b  lea     r12d, [r14+17h]
0x180005f8f  mov     r9d, [rdi+10h]; DestinationAddressCount
0x180005f93  cmp     r14d, r9d
0x180005f96  jnb     short loc_180005FFC
0x180005f98  mov     rdx, [rdi+18h]
0x180005f9c  lea     r8, [rsi+8]
0x180005fa0  mov     eax, r14d
0x180005fa3  mov     ecx, r12d; Family
0x180005fa6  imul    r15, rax, 1Ch
0x180005faa  lea     rax, [r14+r14*2]
0x180005fae  mov     rdx, [rdx+rax*8+8]; pszAddrString
0x180005fb3  add     r8, r15; pAddrBuf
0x180005fb6  call    cs:__imp_InetPtonW
0x180005fbd  nop     dword ptr [rax+rax+00h]
0x180005fc2  cmp     eax, 1
0x180005fc5  jnz     short loc_180005FD1
0x180005fc7  mov     [r15+rsi], r12w
0x180005fcc  inc     r14d
0x180005fcf  jmp     short loc_180005F8F
0x180005fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fd8  lea     rdx, WPP_GLOBAL_Control
0x180005fdf  cmp     rcx, rdx
0x180005fe2  jz      loc_18000613F
0x180005fe8  test    byte ptr [rcx+1Ch], 1
0x180005fec  jz      loc_18000613F
0x180005ff2  mov     edx, 2Ch ; ','
0x180005ff7  jmp     loc_180006129
0x180005ffc  lea     rax, [rsp+4C0h+var_480]
0x180006001  mov     r8, rsi; DestinationAddressList
0x180006004  mov     [rsp+4C0h+SortedAddressPairCount], rax; SortedAddressPairCount
0x180006009  xor     edx, edx; SourceAddressCount
0x18000600b  lea     rax, [rsp+4C0h+var_470]
0x180006010  xor     ecx, ecx; SourceAddressList
0x180006012  mov     [rsp+4C0h+SortedAddressPairList], rax; SortedAddressPairList
0x180006017  mov     [rsp+4C0h+AddressSortOptions], 0; AddressSortOptions
0x18000601f  call    cs:__imp_CreateSortedAddressPairs
0x180006026  nop     dword ptr [rax+rax+00h]
0x18000602b  test    eax, eax
0x18000602d  jz      short loc_18000605D
0x18000602f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006036  lea     rdx, WPP_GLOBAL_Control
0x18000603d  cmp     rcx, rdx
0x180006040  jz      loc_18000613F
0x180006046  test    byte ptr [rcx+1Ch], 1
0x18000604a  jz      loc_18000613F
0x180006050  mov     edx, 2Dh ; '-'
0x180006055  mov     r9d, eax
0x180006058  jmp     loc_18000612F
0x18000605d  mov     rcx, [rsp+4C0h+var_470]
0x180006062  test    rcx, rcx
0x180006065  jz      loc_18000610B
0x18000606b  cmp     [rsp+4C0h+var_480], 2
0x180006070  jb      loc_18000610B
0x180006076  mov     rcx, [rcx+8]
0x18000607a  lea     rdx, [rsp+4C0h+S]; S
0x18000607f  add     rcx, 8; Addr
0x180006083  call    cs:__imp_RtlIpv6AddressToStringW
0x18000608a  nop     dword ptr [rax+rax+00h]
0x18000608f  mov     rax, [rsp+4C0h+var_470]
0x180006094  lea     rdx, [rbp+3C0h+var_250]; S
0x18000609b  mov     rcx, [rax+18h]
0x18000609f  add     rcx, 8; Addr
0x1800060a3  call    cs:__imp_RtlIpv6AddressToStringW
0x1800060aa  nop     dword ptr [rax+rax+00h]
0x1800060af  xor     r14d, r14d
0x1800060b2  cmp     [rdi+10h], r14d
0x1800060b6  jbe     loc_18000613F
0x1800060bc  mov     rax, [rdi+18h]
0x1800060c0  lea     r12, [r14+r14*2]
0x1800060c4  lea     rdx, [rsp+4C0h+S]
0x1800060c9  mov     r15, [rax+r12*8+8]
0x1800060ce  mov     rcx, r15
0x1800060d1  call    NcaWcsICmp
0x1800060d6  test    eax, eax
0x1800060d8  jz      short loc_1800060F2
0x1800060da  lea     rdx, [rbp+3C0h+var_250]
0x1800060e1  mov     rcx, r15
0x1800060e4  call    NcaWcsICmp
0x1800060e9  mov     ecx, 2
0x1800060ee  test    eax, eax
0x1800060f0  jnz     short loc_1800060F7
0x1800060f2  mov     ecx, 1
0x1800060f7  mov     rax, [rdi+18h]
0x1800060fb  inc     r14d
0x1800060fe  mov     [rax+r12*8+10h], ecx
0x180006103  cmp     r14d, [rdi+10h]
0x180006107  jb      short loc_1800060BC
0x180006109  jmp     short loc_18000613F
0x18000610b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006112  lea     rdx, WPP_GLOBAL_Control
0x180006119  cmp     rcx, rdx
0x18000611c  jz      short loc_18000613F
0x18000611e  test    byte ptr [rcx+1Ch], 1
0x180006122  jz      short loc_18000613F
0x180006124  mov     edx, 2Eh ; '.'
0x180006129  mov     r9d, 57h ; 'W'
0x18000612f  mov     rcx, [rcx+10h]
0x180006133  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x18000613a  call    WPP_SF_d
0x18000613f  mov     rcx, [rsp+4C0h+var_470]; Memory
0x180006144  test    rcx, rcx
0x180006147  jz      short loc_180006155
0x180006149  call    cs:__imp_FreeMibTable
0x180006150  nop     dword ptr [rax+rax+00h]
0x180006155  test    rsi, rsi
0x180006158  jz      short loc_180006162
0x18000615a  mov     rcx, rsi; lpMem
0x18000615d  call    NcaFree
0x180006162  xor     eax, eax
0x180006164  mov     rcx, [rbp+3C0h+var_40]
0x18000616b  xor     rcx, rsp; StackCookie
0x18000616e  call    __security_check_cookie
0x180006173  add     rsp, 498h
0x18000617a  pop     r15
0x18000617c  pop     r14
0x18000617e  pop     r12
0x180006180  pop     rdi
0x180006181  pop     rsi
0x180006182  pop     rbp
0x180006183  retn
```
