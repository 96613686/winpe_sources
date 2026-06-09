# GetAddrCommonA(W3_CONTEXT *,sockaddr *,char const * *,ulong *)

- ea: `0x18002bae4`
- end: `0x18002bbd1`
- name: `?GetAddrCommonA@@YAJPEAVW3_CONTEXT@@PEAUsockaddr@@PEAPEBDPEAK@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, struct sockaddr *, const char **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d050`
- `0x18002d5e0`

## callees

- `0x18002bae4`
- `0x180037722`
- `0x180038010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringExA` at `0x18002bba6`
- `ntdll!RtlIpv6AddressToStringExA` at `0x18002bba6`
- `WS2_32!__imp_inet_ntoa` at `0x18002bb41`
- `WS2_32!__imp_inet_ntoa` at `0x18002bb41`
- `WS2_32!__imp_WSAGetLastError` at `0x18002bb55`
- `WS2_32!__imp_WSAGetLastError` at `0x18002bb55`

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
0x18002bae4  push    rbx
0x18002bae6  push    rsi
0x18002bae7  push    rdi
0x18002bae8  push    r14
0x18002baea  sub     rsp, 38h
0x18002baee  cmp     word ptr [rdx], 2
0x18002baf2  mov     rsi, r9
0x18002baf5  mov     r14, r8
0x18002baf8  mov     rbx, rdx
0x18002bafb  jnz     short loc_18002BB04
0x18002bafd  mov     edx, 10h
0x18002bb02  jmp     short loc_18002BB13
0x18002bb04  cmp     word ptr [rdx], 17h
0x18002bb08  jnz     loc_18002BBC1
0x18002bb0e  mov     edx, 3Ch ; '<'
0x18002bb13  mov     rax, [rcx]
0x18002bb16  mov     [rsp+58h+arg_8], edx
0x18002bb1a  mov     rax, [rax+90h]
0x18002bb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb26  mov     rdi, rax
0x18002bb29  test    rax, rax
0x18002bb2c  jnz     short loc_18002BB38
0x18002bb2e  mov     eax, 80070008h
0x18002bb33  jmp     loc_18002BBC6
0x18002bb38  cmp     word ptr [rbx], 2
0x18002bb3c  jnz     short loc_18002BB8F
0x18002bb3e  mov     ecx, [rbx+4]; in
0x18002bb41  call    cs:__imp_inet_ntoa
0x18002bb48  nop     dword ptr [rax+rax+00h]
0x18002bb4d  mov     rdx, rax; Src
0x18002bb50  test    rax, rax
0x18002bb53  jnz     short loc_18002BB6F
0x18002bb55  call    cs:__imp_WSAGetLastError
0x18002bb5c  nop     dword ptr [rax+rax+00h]
0x18002bb61  test    eax, eax
0x18002bb63  jle     short loc_18002BBC6
0x18002bb65  movzx   eax, ax
0x18002bb68  or      eax, 80070000h
0x18002bb6d  jmp     short loc_18002BBC6
0x18002bb6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bb73  inc     rax
0x18002bb76  cmp     byte ptr [rdx+rax], 0
0x18002bb7a  jnz     short loc_18002BB73
0x18002bb7c  inc     eax
0x18002bb7e  mov     rcx, rdi; void *
0x18002bb81  mov     r8d, eax; Size
0x18002bb84  mov     [rsp+58h+arg_8], eax
0x18002bb88  call    memcpy_0
0x18002bb8d  jmp     short loc_18002BBB2
0x18002bb8f  mov     edx, [rbx+18h]; ScopeId
0x18002bb92  lea     rax, [rsp+58h+arg_8]
0x18002bb97  xor     r8d, r8d; Port
0x18002bb9a  mov     [rsp+58h+AddressStringLength], rax; AddressStringLength
0x18002bb9f  lea     rcx, [rbx+8]; Address
0x18002bba3  mov     r9, rdi; AddressString
0x18002bba6  call    cs:__imp_RtlIpv6AddressToStringExA
0x18002bbad  nop     dword ptr [rax+rax+00h]
0x18002bbb2  mov     eax, [rsp+58h+arg_8]
0x18002bbb6  dec     eax
0x18002bbb8  mov     [r14], rdi
0x18002bbbb  mov     [rsi], eax
0x18002bbbd  xor     eax, eax
0x18002bbbf  jmp     short loc_18002BBC6
0x18002bbc1  mov     eax, 8007000Dh
0x18002bbc6  add     rsp, 38h
0x18002bbca  pop     r14
0x18002bbcc  pop     rdi
0x18002bbcd  pop     rsi
0x18002bbce  pop     rbx
0x18002bbcf  retn
```
