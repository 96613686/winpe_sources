# NsiCliAddHostRouteHelper

- ea: `0x140006efc`
- end: `0x140007010`
- name: `NsiCliAddHostRouteHelper`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006ed0`
- `0x140007018`

## callees

- `0x140006efc`
- `0x1400076d0`
- `0x140007ac0`

## import_xrefs

- `NETIO!InternalCreateOrRefIpForwardEntry2` at `0x140006fe9`
- `NETIO!InternalCreateOrRefIpForwardEntry2` at `0x140006fe9`
- `NETIO!GetBestRoute2` at `0x140006f93`
- `NETIO!GetBestRoute2` at `0x140006f93`

## pseudocode

```c
NTSTATUS __fastcall NsiCliAddHostRouteHelper(ADDRESS_FAMILY a1, ULONG *a2, UINT8 a3, NET_IFINDEX *a4)
{
  NTSTATUS result; // eax
  SOCKADDR_INET DestinationAddress; // [rsp+40h] [rbp-89h] BYREF
  struct _MIB_IPFORWARD_ROW2 BestRoute; // [rsp+60h] [rbp-69h] BYREF
  SOCKADDR_INET BestSourceAddress; // [rsp+D0h] [rbp+7h] BYREF

  memset(&BestRoute, 0, sizeof(BestRoute));
  memset(&DestinationAddress, 0, sizeof(DestinationAddress));
  DestinationAddress.Ipv4.sin_family = a1;
  memset(&BestSourceAddress, 0, sizeof(BestSourceAddress));
  if ( a1 == 23 )
    *(_OWORD *)(&DestinationAddress.si_family + 4) = *(_OWORD *)a2;
  else
    DestinationAddress.Ipv4.sin_addr.S_un.S_addr = *a2;
  result = GetBestRoute2(0, 0, 0, &DestinationAddress, 0, &BestRoute, &BestSourceAddress);
  if ( result >= 0 )
  {
    if ( BestRoute.DestinationPrefix.Prefix.Ipv4.sin_family == 23 )
      *(_OWORD *)(&BestRoute.DestinationPrefix.Prefix.si_family + 4) = *(_OWORD *)a2;
    else
      BestRoute.DestinationPrefix.Prefix.Ipv4.sin_addr.S_un.S_addr = *a2;
    BestRoute.DestinationPrefix.PrefixLength = a3;
    BestRoute.ValidLifetime = -1;
    BestRoute.PreferredLifetime = -1;
    BestRoute.Metric = 1;
    BestRoute.Protocol = RouteProtocolNetMgmt;
    *(_WORD *)&BestRoute.Publish = 256;
    if ( a4 )
      *a4 = BestRoute.InterfaceIndex;
    return InternalCreateOrRefIpForwardEntry2(1, &BestRoute);
  }
  return result;
}

```

## disassembly

```asm
0x140006efc  push    rbp
0x140006efe  push    rbx
0x140006eff  push    rsi
0x140006f00  push    rdi
0x140006f01  push    r14
0x140006f03  lea     rbp, [rsp-37h]
0x140006f08  sub     rsp, 100h
0x140006f0f  mov     rax, cs:__security_cookie
0x140006f16  xor     rax, rsp
0x140006f19  mov     [rbp+57h+var_30], rax
0x140006f1d  mov     rdi, rdx
0x140006f20  mov     r14b, r8b
0x140006f23  xor     edx, edx; Val
0x140006f25  movzx   ebx, cx
0x140006f28  lea     rcx, [rbp+57h+var_C0]; void *
0x140006f2c  mov     rsi, r9
0x140006f2f  lea     r8d, [rdx+68h]; Size
0x140006f33  call    memset
0x140006f38  xorps   xmm0, xmm0
0x140006f3b  xorps   xmm1, xmm1
0x140006f3e  movups  xmmword ptr [rsp+120h+DestinationAddress], xmm0
0x140006f43  xor     eax, eax
0x140006f45  mov     word ptr [rsp+120h+DestinationAddress], bx
0x140006f4a  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x140006f4e  movups  xmmword ptr [rbp+57h+DestinationAddress+0Ch], xmm0
0x140006f52  movups  xmmword ptr [rbp+57h+var_50+0Ch], xmm1
0x140006f56  cmp     bx, 17h
0x140006f5a  jnz     short loc_140006F67
0x140006f5c  movups  xmm0, xmmword ptr [rdi]
0x140006f5f  movdqu  xmmword ptr [rsp+120h+DestinationAddress+8], xmm0
0x140006f65  jmp     short loc_140006F6D
0x140006f67  mov     eax, [rdi]
0x140006f69  mov     dword ptr [rsp+120h+DestinationAddress+4], eax
0x140006f6d  lea     rax, [rbp+57h+var_50]
0x140006f71  xor     r8d, r8d; SourceAddress
0x140006f74  mov     [rsp+120h+BestSourceAddress], rax; BestSourceAddress
0x140006f79  lea     r9, [rsp+120h+DestinationAddress]; DestinationAddress
0x140006f7e  lea     rax, [rbp+57h+var_C0]
0x140006f82  xor     edx, edx; InterfaceIndex
0x140006f84  mov     [rsp+120h+BestRoute], rax; BestRoute
0x140006f89  xor     ecx, ecx; InterfaceLuid
0x140006f8b  mov     [rsp+120h+AddressSortOptions], 0; AddressSortOptions
0x140006f93  call    cs:__imp_GetBestRoute2
0x140006f9a  nop     dword ptr [rax+rax+00h]
0x140006f9f  test    eax, eax
0x140006fa1  js      short loc_140006FF5
0x140006fa3  cmp     word ptr [rbp+57h+var_C0.DestinationPrefix.Prefix], 17h
0x140006fa8  jnz     short loc_140006FB4
0x140006faa  movups  xmm0, xmmword ptr [rdi]
0x140006fad  movdqu  xmmword ptr [rbp+57h+var_C0.DestinationPrefix.Prefix+8], xmm0
0x140006fb2  jmp     short loc_140006FB9
0x140006fb4  mov     eax, [rdi]
0x140006fb6  mov     dword ptr [rbp+57h+var_C0.DestinationPrefix.Prefix+4], eax
0x140006fb9  or      eax, 0FFFFFFFFh
0x140006fbc  mov     [rbp+57h+var_C0.DestinationPrefix.PrefixLength], r14b
0x140006fc0  mov     [rbp+57h+var_C0.ValidLifetime], eax
0x140006fc3  mov     ecx, 1
0x140006fc8  mov     [rbp+57h+var_C0.PreferredLifetime], eax
0x140006fcb  mov     [rbp+57h+var_C0.Metric], ecx
0x140006fce  mov     [rbp+57h+var_C0.Protocol], 3
0x140006fd5  mov     word ptr [rbp+57h+var_C0.Publish], 100h
0x140006fdb  test    rsi, rsi
0x140006fde  jz      short loc_140006FE5
0x140006fe0  mov     eax, [rbp+57h+var_C0.InterfaceIndex]
0x140006fe3  mov     [rsi], eax
0x140006fe5  lea     rdx, [rbp+57h+var_C0]
0x140006fe9  call    cs:__imp_InternalCreateOrRefIpForwardEntry2
0x140006ff0  nop     dword ptr [rax+rax+00h]
0x140006ff5  mov     rcx, [rbp+57h+var_30]
0x140006ff9  xor     rcx, rsp; StackCookie
0x140006ffc  call    __security_check_cookie
0x140007001  add     rsp, 100h
0x140007008  pop     r14
0x14000700a  pop     rdi
0x14000700b  pop     rsi
0x14000700c  pop     rbx
0x14000700d  pop     rbp
0x14000700e  retn
```
