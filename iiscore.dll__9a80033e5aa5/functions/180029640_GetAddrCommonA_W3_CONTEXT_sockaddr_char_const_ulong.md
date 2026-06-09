# GetAddrCommonA(W3_CONTEXT *,sockaddr *,char const * *,ulong *)

- ea: `0x180029640`
- end: `0x180029717`
- name: `?GetAddrCommonA@@YAJPEAVW3_CONTEXT@@PEAUsockaddr@@PEAPEBDPEAK@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, struct sockaddr *, const char **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002aa60`
- `0x18002af90`

## callees

- `0x180029640`
- `0x180034382`
- `0x180035010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExA` at `0x1800296f3`
- `ntdll!RtlIpv6AddressToStringExA` at `0x1800296f3`
- `WS2_32!__imp_inet_ntoa` at `0x18002969a`
- `WS2_32!__imp_inet_ntoa` at `0x18002969a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800296a8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800296a8`

## pseudocode

```c
signed int __fastcall GetAddrCommonA(struct W3_CONTEXT *a1, struct sockaddr *a2, CHAR **a3, unsigned int *a4)
{
  ULONG v7; // edx
  __int64 v8; // rax
  CHAR *v9; // rdi
  signed int result; // eax
  char *v11; // rdx
  __int64 v12; // rax
  ULONG v13; // eax
  ULONG AddressStringLength; // [rsp+68h] [rbp+10h] BYREF

  if ( a2->sa_family == 2 )
  {
    v7 = 16;
  }
  else
  {
    if ( a2->sa_family != 23 )
      return -2147024883;
    v7 = 60;
  }
  v8 = *(_QWORD *)a1;
  AddressStringLength = v7;
  v9 = (CHAR *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v8 + 144))(a1);
  if ( !v9 )
    return -2147024888;
  if ( a2->sa_family != 2 )
  {
    RtlIpv6AddressToStringExA(
      (const struct in6_addr *)&a2->sa_data[6],
      *(_DWORD *)&a2[1].sa_data[6],
      0,
      v9,
      &AddressStringLength);
LABEL_15:
    v13 = AddressStringLength - 1;
    *a3 = v9;
    *a4 = v13;
    return 0;
  }
  v11 = inet_ntoa(*(struct in_addr *)&a2->sa_data[2]);
  if ( v11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    AddressStringLength = v12 + 1;
    memcpy_0(v9, v11, (unsigned int)(v12 + 1));
    goto LABEL_15;
  }
  result = WSAGetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180029640  push    rbx
0x180029642  push    rsi
0x180029643  push    rdi
0x180029644  push    r14
0x180029646  sub     rsp, 38h
0x18002964a  cmp     word ptr [rdx], 2
0x18002964e  mov     rsi, r9
0x180029651  mov     r14, r8
0x180029654  mov     rbx, rdx
0x180029657  jnz     short loc_180029660
0x180029659  mov     edx, 10h
0x18002965e  jmp     short loc_18002966F
0x180029660  cmp     word ptr [rdx], 17h
0x180029664  jnz     loc_180029708
0x18002966a  mov     edx, 3Ch ; '<'
0x18002966f  mov     rax, [rcx]
0x180029672  mov     [rsp+58h+arg_8], edx
0x180029676  mov     rax, [rax+90h]
0x18002967d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029682  mov     rdi, rax
0x180029685  test    rax, rax
0x180029688  jnz     short loc_180029691
0x18002968a  mov     eax, 80070008h
0x18002968f  jmp     short loc_18002970D
0x180029691  cmp     word ptr [rbx], 2
0x180029695  jnz     short loc_1800296DC
0x180029697  mov     ecx, [rbx+4]; in
0x18002969a  call    cs:__imp_inet_ntoa
0x1800296a0  mov     rdx, rax; Src
0x1800296a3  test    rax, rax
0x1800296a6  jnz     short loc_1800296BC
0x1800296a8  call    cs:__imp_WSAGetLastError
0x1800296ae  test    eax, eax
0x1800296b0  jle     short loc_18002970D
0x1800296b2  movzx   eax, ax
0x1800296b5  or      eax, 80070000h
0x1800296ba  jmp     short loc_18002970D
0x1800296bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800296c0  inc     rax
0x1800296c3  cmp     byte ptr [rdx+rax], 0
0x1800296c7  jnz     short loc_1800296C0
0x1800296c9  inc     eax
0x1800296cb  mov     rcx, rdi; void *
0x1800296ce  mov     r8d, eax; Size
0x1800296d1  mov     [rsp+58h+arg_8], eax
0x1800296d5  call    memcpy_0
0x1800296da  jmp     short loc_1800296F9
0x1800296dc  mov     edx, [rbx+18h]; ScopeId
0x1800296df  lea     rax, [rsp+58h+arg_8]
0x1800296e4  xor     r8d, r8d; Port
0x1800296e7  mov     [rsp+58h+AddressStringLength], rax; AddressStringLength
0x1800296ec  lea     rcx, [rbx+8]; Address
0x1800296f0  mov     r9, rdi; AddressString
0x1800296f3  call    cs:__imp_RtlIpv6AddressToStringExA
0x1800296f9  mov     eax, [rsp+58h+arg_8]
0x1800296fd  dec     eax
0x1800296ff  mov     [r14], rdi
0x180029702  mov     [rsi], eax
0x180029704  xor     eax, eax
0x180029706  jmp     short loc_18002970D
0x180029708  mov     eax, 8007000Dh
0x18002970d  add     rsp, 38h
0x180029711  pop     r14
0x180029713  pop     rdi
0x180029714  pop     rsi
0x180029715  pop     rbx
0x180029716  retn
```
