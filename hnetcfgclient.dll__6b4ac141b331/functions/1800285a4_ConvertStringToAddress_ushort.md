# ConvertStringToAddress(ushort *)

- ea: `0x1800285a4`
- end: `0x18002866d`
- name: `?ConvertStringToAddress@@YAKPEAG@Z`
- size: `201`
- prototype: `__int64 __fastcall(LPWSTR AddressString)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002a31c`

## callees

- `0x1800285a4`
- `0x18002d1d2`
- `0x18002d200`

## import_xrefs

- `WS2_32!WSAStringToAddressW` at `0x18002862b`
- `WS2_32!WSAStringToAddressW` at `0x18002862b`
- `WS2_32!__imp_WSAStartup` at `0x180028600`
- `WS2_32!__imp_WSAStartup` at `0x180028600`
- `WS2_32!__imp_WSACleanup` at `0x180028644`
- `WS2_32!__imp_WSACleanup` at `0x180028644`

## pseudocode

```c
__int64 __fastcall ConvertStringToAddress(LPWSTR AddressString)
{
  unsigned int v3; // ebx
  int AddressLength[4]; // [rsp+30h] [rbp-248h] BYREF
  struct sockaddr Address; // [rsp+40h] [rbp-238h] BYREF
  struct WSAData WSAData; // [rsp+C0h] [rbp-1B8h] BYREF

  memset_0(&Address, 0, 0x80u);
  AddressLength[0] = 128;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WSAStartup(0x202u, &WSAData) )
    return 0xFFFFFFFFLL;
  v3 = -1;
  if ( WSAStringToAddressW(AddressString, 2, 0, &Address, AddressLength) != -1 )
  {
    v3 = *(_DWORD *)&Address.sa_data[2];
    if ( Address.sa_family == 23 )
      v3 = *(_DWORD *)&Address.sa_data[6];
  }
  WSACleanup();
  return v3;
}

```

## disassembly

```asm
0x1800285a4  mov     [rsp+arg_8], rbx
0x1800285a9  push    rdi
0x1800285aa  sub     rsp, 270h
0x1800285b1  mov     rax, cs:__security_cookie
0x1800285b8  xor     rax, rsp
0x1800285bb  mov     [rsp+278h+var_18], rax
0x1800285c3  mov     rdi, rcx
0x1800285c6  mov     ebx, 80h
0x1800285cb  mov     r8d, ebx; Size
0x1800285ce  lea     rcx, [rsp+278h+Address]; void *
0x1800285d3  xor     edx, edx; Val
0x1800285d5  call    memset_0
0x1800285da  xor     edx, edx; Val
0x1800285dc  mov     [rsp+278h+AddressLength], ebx
0x1800285e0  mov     r8d, 198h; Size
0x1800285e6  lea     rcx, [rsp+278h+WSAData]; void *
0x1800285ee  call    memset_0
0x1800285f3  mov     ecx, 202h; wVersionRequested
0x1800285f8  lea     rdx, [rsp+278h+WSAData]; lpWSAData
0x180028600  call    cs:__imp_WSAStartup
0x180028606  test    eax, eax
0x180028608  jz      short loc_18002860F
0x18002860a  or      eax, 0FFFFFFFFh
0x18002860d  jmp     short loc_18002864C
0x18002860f  xor     r8d, r8d; lpProtocolInfo
0x180028612  lea     rax, [rsp+278h+AddressLength]
0x180028617  lea     r9, [rsp+278h+Address]; lpAddress
0x18002861c  mov     [rsp+278h+lpAddressLength], rax; lpAddressLength
0x180028621  mov     rcx, rdi; AddressString
0x180028624  or      ebx, 0FFFFFFFFh
0x180028627  lea     edx, [r8+2]; AddressFamily
0x18002862b  call    cs:__imp_WSAStringToAddressW
0x180028631  cmp     eax, ebx
0x180028633  jz      short loc_180028644
0x180028635  cmp     [rsp+278h+Address.sa_family], 17h
0x18002863b  mov     ebx, dword ptr [rsp+278h+Address.sa_data+2]
0x18002863f  cmovz   ebx, dword ptr [rsp+278h+Address.sa_data+6]
0x180028644  call    cs:__imp_WSACleanup
0x18002864a  mov     eax, ebx
0x18002864c  mov     rcx, [rsp+278h+var_18]
0x180028654  xor     rcx, rsp; StackCookie
0x180028657  call    __security_check_cookie
0x18002865c  mov     rbx, [rsp+278h+arg_8]
0x180028664  add     rsp, 270h
0x18002866b  pop     rdi
0x18002866c  retn
```
