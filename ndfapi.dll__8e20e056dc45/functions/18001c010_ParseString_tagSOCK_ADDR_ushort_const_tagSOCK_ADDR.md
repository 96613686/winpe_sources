# ParseString<tagSOCK_ADDR>(ushort const *,tagSOCK_ADDR &)

- ea: `0x18001c010`
- end: `0x18001c0e9`
- name: `??$ParseString@UtagSOCK_ADDR@@@@YAKPEBGAEAUtagSOCK_ADDR@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(LPWSTR AddressString, LPSOCKADDR lpAddress)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001c0f0`

## callees

- `0x18001c010`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `WS2_32!WSAStringToAddressW` at `0x18001c07f`
- `WS2_32!WSAStringToAddressW` at `0x18001c0aa`
- `WS2_32!WSAStringToAddressW` at `0x18001c07f`
- `WS2_32!WSAStringToAddressW` at `0x18001c0aa`
- `WS2_32!__imp_WSAStartup` at `0x18001c056`
- `WS2_32!__imp_WSAStartup` at `0x18001c056`
- `WS2_32!__imp_WSACleanup` at `0x18001c0bc`
- `WS2_32!__imp_WSACleanup` at `0x18001c0bc`

## pseudocode

```c
__int64 __fastcall ParseString<tagSOCK_ADDR>(LPWSTR AddressString, LPSOCKADDR lpAddress)
{
  unsigned int v4; // ebx
  int AddressLength[4]; // [rsp+30h] [rbp-1C8h] BYREF
  WSAData WSAData; // [rsp+40h] [rbp-1B8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WSAStartup(0x202u, &WSAData)
    || (AddressLength[0] = 128, (v4 = WSAStringToAddressW(AddressString, 2, 0, lpAddress, AddressLength)) != 0) )
  {
    AddressLength[0] = 128;
    v4 = WSAStringToAddressW(AddressString, 23, 0, lpAddress, AddressLength);
    if ( v4 )
      v4 = 87;
  }
  WSACleanup();
  return v4;
}

```

## disassembly

```asm
0x18001c010  mov     [rsp+arg_10], rbx
0x18001c015  mov     [rsp+arg_18], rsi
0x18001c01a  push    rdi
0x18001c01b  sub     rsp, 1F0h
0x18001c022  mov     rax, cs:__security_cookie
0x18001c029  xor     rax, rsp
0x18001c02c  mov     [rsp+1F8h+var_18], rax
0x18001c034  mov     rsi, rdx
0x18001c037  mov     rdi, rcx
0x18001c03a  xor     edx, edx; Val
0x18001c03c  lea     rcx, [rsp+1F8h+WSAData]; void *
0x18001c041  mov     r8d, 198h; Size
0x18001c047  call    memset_0
0x18001c04c  mov     ecx, 202h; wVersionRequested
0x18001c051  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x18001c056  call    cs:__imp_WSAStartup
0x18001c05c  test    eax, eax
0x18001c05e  jnz     short loc_18001C08B
0x18001c060  xor     r8d, r8d; lpProtocolInfo
0x18001c063  mov     [rsp+1F8h+AddressLength], 80h
0x18001c06b  lea     rax, [rsp+1F8h+AddressLength]
0x18001c070  mov     r9, rsi; lpAddress
0x18001c073  mov     rcx, rdi; AddressString
0x18001c076  mov     [rsp+1F8h+lpAddressLength], rax; lpAddressLength
0x18001c07b  lea     edx, [r8+2]; AddressFamily
0x18001c07f  call    cs:__imp_WSAStringToAddressW
0x18001c085  mov     ebx, eax
0x18001c087  test    eax, eax
0x18001c089  jz      short loc_18001C0BC
0x18001c08b  xor     r8d, r8d; lpProtocolInfo
0x18001c08e  mov     [rsp+1F8h+AddressLength], 80h
0x18001c096  lea     rax, [rsp+1F8h+AddressLength]
0x18001c09b  mov     r9, rsi; lpAddress
0x18001c09e  mov     rcx, rdi; AddressString
0x18001c0a1  mov     [rsp+1F8h+lpAddressLength], rax; lpAddressLength
0x18001c0a6  lea     edx, [r8+17h]; AddressFamily
0x18001c0aa  call    cs:__imp_WSAStringToAddressW
0x18001c0b0  mov     ebx, eax
0x18001c0b2  mov     eax, 57h ; 'W'
0x18001c0b7  test    ebx, ebx
0x18001c0b9  cmovnz  ebx, eax
0x18001c0bc  call    cs:__imp_WSACleanup
0x18001c0c2  mov     eax, ebx
0x18001c0c4  mov     rcx, [rsp+1F8h+var_18]
0x18001c0cc  xor     rcx, rsp; StackCookie
0x18001c0cf  call    __security_check_cookie
0x18001c0d4  lea     r11, [rsp+1F8h+var_8]
0x18001c0dc  mov     rbx, [r11+20h]
0x18001c0e0  mov     rsi, [r11+28h]
0x18001c0e4  mov     rsp, r11
0x18001c0e7  pop     rdi
0x18001c0e8  retn
```
