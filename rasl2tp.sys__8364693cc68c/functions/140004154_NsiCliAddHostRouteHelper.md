# NsiCliAddHostRouteHelper

- ea: `0x140004154`
- end: `0x140004268`
- name: `NsiCliAddHostRouteHelper`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004128`
- `0x140004270`

## callees

- `0x140004154`
- `0x1400047f0`
- `0x140004c00`

## import_xrefs

- `NETIO!InternalCreateOrRefIpForwardEntry2` at `0x140004241`
- `NETIO!InternalCreateOrRefIpForwardEntry2` at `0x140004241`
- `NETIO!GetBestRoute2` at `0x1400041eb`
- `NETIO!GetBestRoute2` at `0x1400041eb`

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
0x140004154  push    rbp
0x140004156  push    rbx
0x140004157  push    rsi
0x140004158  push    rdi
0x140004159  push    r14
0x14000415b  lea     rbp, [rsp-37h]
0x140004160  sub     rsp, 100h
0x140004167  mov     rax, cs:__security_cookie
0x14000416e  xor     rax, rsp
0x140004171  mov     [rbp+57h+var_30], rax
0x140004175  mov     rdi, rdx
0x140004178  mov     r14b, r8b
0x14000417b  xor     edx, edx; Val
0x14000417d  movzx   ebx, cx
0x140004180  lea     rcx, [rbp+57h+var_C0]; void *
0x140004184  mov     rsi, r9
0x140004187  lea     r8d, [rdx+68h]; Size
0x14000418b  call    memset
0x140004190  xorps   xmm0, xmm0
0x140004193  xorps   xmm1, xmm1
0x140004196  movups  xmmword ptr [rsp+120h+DestinationAddress], xmm0
0x14000419b  xor     eax, eax
0x14000419d  mov     word ptr [rsp+120h+DestinationAddress], bx
0x1400041a2  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x1400041a6  movups  xmmword ptr [rbp+57h+DestinationAddress+0Ch], xmm0
0x1400041aa  movups  xmmword ptr [rbp+57h+var_50+0Ch], xmm1
0x1400041ae  cmp     bx, 17h
0x1400041b2  jnz     short loc_1400041BF
0x1400041b4  movups  xmm0, xmmword ptr [rdi]
0x1400041b7  movdqu  xmmword ptr [rsp+120h+DestinationAddress+8], xmm0
0x1400041bd  jmp     short loc_1400041C5
0x1400041bf  mov     eax, [rdi]
0x1400041c1  mov     dword ptr [rsp+120h+DestinationAddress+4], eax
0x1400041c5  lea     rax, [rbp+57h+var_50]
0x1400041c9  xor     r8d, r8d; SourceAddress
0x1400041cc  mov     [rsp+120h+BestSourceAddress], rax; BestSourceAddress
0x1400041d1  lea     r9, [rsp+120h+DestinationAddress]; DestinationAddress
0x1400041d6  lea     rax, [rbp+57h+var_C0]
0x1400041da  xor     edx, edx; InterfaceIndex
0x1400041dc  mov     [rsp+120h+BestRoute], rax; BestRoute
0x1400041e1  xor     ecx, ecx; InterfaceLuid
0x1400041e3  mov     [rsp+120h+AddressSortOptions], 0; AddressSortOptions
0x1400041eb  call    cs:__imp_GetBestRoute2
0x1400041f2  nop     dword ptr [rax+rax+00h]
0x1400041f7  test    eax, eax
0x1400041f9  js      short loc_14000424D
0x1400041fb  cmp     word ptr [rbp+57h+var_C0.DestinationPrefix.Prefix], 17h
0x140004200  jnz     short loc_14000420C
0x140004202  movups  xmm0, xmmword ptr [rdi]
0x140004205  movdqu  xmmword ptr [rbp+57h+var_C0.DestinationPrefix.Prefix+8], xmm0
0x14000420a  jmp     short loc_140004211
0x14000420c  mov     eax, [rdi]
0x14000420e  mov     dword ptr [rbp+57h+var_C0.DestinationPrefix.Prefix+4], eax
0x140004211  or      eax, 0FFFFFFFFh
0x140004214  mov     [rbp+57h+var_C0.DestinationPrefix.PrefixLength], r14b
0x140004218  mov     [rbp+57h+var_C0.ValidLifetime], eax
0x14000421b  mov     ecx, 1
0x140004220  mov     [rbp+57h+var_C0.PreferredLifetime], eax
0x140004223  mov     [rbp+57h+var_C0.Metric], ecx
0x140004226  mov     [rbp+57h+var_C0.Protocol], 3
0x14000422d  mov     word ptr [rbp+57h+var_C0.Publish], 100h
0x140004233  test    rsi, rsi
0x140004236  jz      short loc_14000423D
0x140004238  mov     eax, [rbp+57h+var_C0.InterfaceIndex]
0x14000423b  mov     [rsi], eax
0x14000423d  lea     rdx, [rbp+57h+var_C0]
0x140004241  call    cs:__imp_InternalCreateOrRefIpForwardEntry2
0x140004248  nop     dword ptr [rax+rax+00h]
0x14000424d  mov     rcx, [rbp+57h+var_30]
0x140004251  xor     rcx, rsp; StackCookie
0x140004254  call    __security_check_cookie
0x140004259  add     rsp, 100h
0x140004260  pop     r14
0x140004262  pop     rdi
0x140004263  pop     rsi
0x140004264  pop     rbx
0x140004265  pop     rbp
0x140004266  retn
```
