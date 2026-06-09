# SetIkev2TrafficSelectorsRegParams

- ea: `0x180030f9c`
- end: `0x180031172`
- name: `SetIkev2TrafficSelectorsRegParams`
- size: `470`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030c30`

## callees

- `0x180030f9c`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031017`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003104b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003107f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800310b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003114a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031017`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003104b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003107f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800310b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003114a`
- `ntdll!RtlIpv4AddressToStringW` at `0x1800310d9`
- `ntdll!RtlIpv4AddressToStringW` at `0x180031124`
- `ntdll!RtlIpv4AddressToStringW` at `0x1800310d9`
- `ntdll!RtlIpv4AddressToStringW` at `0x180031124`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800310d1`
- `ntdll!RtlIpv6AddressToStringW` at `0x18003111c`
- `ntdll!RtlIpv6AddressToStringW` at `0x1800310d1`
- `ntdll!RtlIpv6AddressToStringW` at `0x18003111c`

## string_xrefs

- `0x180030ff0`: `Protocol`

## pseudocode

```c
LSTATUS __fastcall SetIkev2TrafficSelectorsRegParams(HKEY hKey, __int64 a2)
{
  LSTATUS result; // eax
  const struct in6_addr *v5; // rcx
  const struct in6_addr *v6; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE lpData[12]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR S[136]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v10[136]; // [rsp+150h] [rbp+50h] BYREF

  memset_0(S, 0, 0x102u);
  memset_0(v10, 0, 0x102u);
  *(_DWORD *)Data = *(unsigned __int8 *)(a2 + 4);
  result = RegSetValueExW(hKey, L"Protocol", 0, 4u, Data, 4u);
  if ( !result )
  {
    *(_DWORD *)lpData = *(unsigned __int16 *)(a2 + 10);
    result = RegSetValueExW(hKey, L"TsPayloadId", 0, 4u, lpData, 4u);
    if ( !result )
    {
      *(_DWORD *)Data = *(unsigned __int16 *)(a2 + 6);
      result = RegSetValueExW(hKey, L"StartPort", 0, 4u, Data, 4u);
      if ( !result )
      {
        *(_DWORD *)Data = *(unsigned __int16 *)(a2 + 8);
        result = RegSetValueExW(hKey, L"EndPort", 0, 4u, Data, 4u);
        if ( !result )
        {
          v5 = (const struct in6_addr *)(a2 + 16);
          if ( *(_WORD *)(a2 + 12) == 23 )
            RtlIpv6AddressToStringW(v5, S);
          else
            RtlIpv4AddressToStringW((const struct in_addr *)v5, S);
          result = RegSetValueExW(hKey, L"StartIP", 0, 1u, (const BYTE *)S, 0x81u);
          if ( !result )
          {
            v6 = (const struct in6_addr *)(a2 + 36);
            if ( *(_WORD *)(a2 + 32) == 23 )
              RtlIpv6AddressToStringW(v6, v10);
            else
              RtlIpv4AddressToStringW((const struct in_addr *)v6, v10);
            return RegSetValueExW(hKey, L"EndIP", 0, 1u, (const BYTE *)v10, 0x81u);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030f9c  mov     [rsp-8+arg_10], rbx
0x180030fa1  push    rbp
0x180030fa2  push    rsi
0x180030fa3  push    rdi
0x180030fa4  lea     rbp, [rsp-170h]
0x180030fac  sub     rsp, 270h
0x180030fb3  mov     rax, cs:__security_cookie
0x180030fba  xor     rax, rsp
0x180030fbd  mov     [rbp+180h+var_20], rax
0x180030fc4  mov     rbx, rdx
0x180030fc7  mov     rdi, rcx
0x180030fca  mov     esi, 102h
0x180030fcf  lea     rcx, [rsp+280h+S]; void *
0x180030fd4  mov     r8d, esi; Size
0x180030fd7  xor     edx, edx; Val
0x180030fd9  call    memset_0
0x180030fde  mov     r8d, esi; Size
0x180030fe1  lea     rcx, [rbp+180h+var_130]; void *
0x180030fe5  xor     edx, edx; Val
0x180030fe7  call    memset_0
0x180030fec  movzx   eax, byte ptr [rbx+4]
0x180030ff0  lea     rdx, aProtocol; "Protocol"
0x180030ff7  mov     dword ptr [rsp+280h+Data], eax
0x180030ffb  mov     esi, 4
0x180031000  lea     rax, [rsp+280h+Data]
0x180031005  mov     [rsp+280h+cbData], esi; cbData
0x180031009  mov     r9d, esi; dwType
0x18003100c  mov     [rsp+280h+lpData], rax; lpData
0x180031011  xor     r8d, r8d; Reserved
0x180031014  mov     rcx, rdi; hKey
0x180031017  call    cs:__imp_RegSetValueExW
0x18003101d  test    eax, eax
0x18003101f  jnz     loc_180031150
0x180031025  movzx   eax, word ptr [rbx+0Ah]
0x180031029  lea     rdx, aTspayloadid; "TsPayloadId"
0x180031030  mov     dword ptr [rsp+280h+var_24C], eax
0x180031034  mov     r9d, esi; dwType
0x180031037  lea     rax, [rsp+280h+var_24C]
0x18003103c  mov     [rsp+280h+cbData], esi; cbData
0x180031040  xor     r8d, r8d; Reserved
0x180031043  mov     [rsp+280h+lpData], rax; lpData
0x180031048  mov     rcx, rdi; hKey
0x18003104b  call    cs:__imp_RegSetValueExW
0x180031051  test    eax, eax
0x180031053  jnz     loc_180031150
0x180031059  movzx   eax, word ptr [rbx+6]
0x18003105d  lea     rdx, aStartport; "StartPort"
0x180031064  mov     dword ptr [rsp+280h+Data], eax
0x180031068  mov     r9d, esi; dwType
0x18003106b  lea     rax, [rsp+280h+Data]
0x180031070  mov     [rsp+280h+cbData], esi; cbData
0x180031074  xor     r8d, r8d; Reserved
0x180031077  mov     [rsp+280h+lpData], rax; lpData
0x18003107c  mov     rcx, rdi; hKey
0x18003107f  call    cs:__imp_RegSetValueExW
0x180031085  test    eax, eax
0x180031087  jnz     loc_180031150
0x18003108d  movzx   eax, word ptr [rbx+8]
0x180031091  lea     rdx, aEndport; "EndPort"
0x180031098  mov     dword ptr [rsp+280h+Data], eax
0x18003109c  mov     r9d, esi; dwType
0x18003109f  lea     rax, [rsp+280h+Data]
0x1800310a4  mov     [rsp+280h+cbData], esi; cbData
0x1800310a8  xor     r8d, r8d; Reserved
0x1800310ab  mov     [rsp+280h+lpData], rax; lpData
0x1800310b0  mov     rcx, rdi; hKey
0x1800310b3  call    cs:__imp_RegSetValueExW
0x1800310b9  test    eax, eax
0x1800310bb  jnz     loc_180031150
0x1800310c1  cmp     word ptr [rbx+0Ch], 17h
0x1800310c6  lea     rcx, [rbx+10h]; Addr
0x1800310ca  lea     rdx, [rsp+280h+S]; S
0x1800310cf  jnz     short loc_1800310D9
0x1800310d1  call    cs:__imp_RtlIpv6AddressToStringW
0x1800310d7  jmp     short loc_1800310DF
0x1800310d9  call    cs:__imp_RtlIpv4AddressToStringW
0x1800310df  mov     esi, 81h
0x1800310e4  lea     rax, [rsp+280h+S]
0x1800310e9  mov     [rsp+280h+cbData], esi; cbData
0x1800310ed  lea     rdx, aStartip; "StartIP"
0x1800310f4  xor     r8d, r8d; Reserved
0x1800310f7  mov     [rsp+280h+lpData], rax; lpData
0x1800310fc  mov     rcx, rdi; hKey
0x1800310ff  lea     r9d, [rsi-80h]; dwType
0x180031103  call    cs:__imp_RegSetValueExW
0x180031109  test    eax, eax
0x18003110b  jnz     short loc_180031150
0x18003110d  cmp     word ptr [rbx+20h], 17h
0x180031112  lea     rcx, [rbx+24h]; Addr
0x180031116  lea     rdx, [rbp+180h+var_130]; S
0x18003111a  jnz     short loc_180031124
0x18003111c  call    cs:__imp_RtlIpv6AddressToStringW
0x180031122  jmp     short loc_18003112A
0x180031124  call    cs:__imp_RtlIpv4AddressToStringW
0x18003112a  lea     rax, [rbp+180h+var_130]
0x18003112e  mov     [rsp+280h+cbData], esi; cbData
0x180031132  mov     r9d, 1; dwType
0x180031138  mov     [rsp+280h+lpData], rax; lpData
0x18003113d  xor     r8d, r8d; Reserved
0x180031140  lea     rdx, aEndip; "EndIP"
0x180031147  mov     rcx, rdi; hKey
0x18003114a  call    cs:__imp_RegSetValueExW
0x180031150  mov     rcx, [rbp+180h+var_20]
0x180031157  xor     rcx, rsp; StackCookie
0x18003115a  call    __security_check_cookie
0x18003115f  mov     rbx, [rsp+280h+arg_10]
0x180031167  add     rsp, 270h
0x18003116e  pop     rdi
0x18003116f  pop     rsi
0x180031170  pop     rbp
0x180031171  retn
```
