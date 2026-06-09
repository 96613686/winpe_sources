# ReadDUIDOverride

- ea: `0x18002a8ec`
- end: `0x18002aa2e`
- name: `ReadDUIDOverride`
- size: `322`
- prototype: `__int64 __fastcall(LPBYTE *, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180016658`

## callees

- `0x180007564`
- `0x18000c740`
- `0x18002a8ec`
- `0x1800338c0`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a943`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a9cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a943`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a9cb`

## pseudocode

```c
__int64 __fastcall ReadDUIDOverride(LPBYTE *a1, DWORD *a2)
{
  unsigned int v4; // ebx
  LPBYTE v5; // rdi
  LPBYTE lpData[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  lpData[0] = 0;
  cbData = 0;
  Type = 3;
  v4 = RegQueryValueExW(Dhcpv6GlobalTcpipParametersKey, L"Dhcpv6DUIDOverride", 0, &Type, 0, &cbData);
  if ( !v4 )
  {
    if ( Type != 3 )
    {
LABEL_3:
      v4 = 13;
      goto LABEL_11;
    }
    if ( !cbData )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_(1025, cbData + 12, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      goto LABEL_3;
    }
    lpData[0] = (LPBYTE)DhcpAlloc(cbData);
    v5 = lpData[0];
    if ( lpData[0] )
    {
      v4 = RegQueryValueExW(Dhcpv6GlobalTcpipParametersKey, L"Dhcpv6DUIDOverride", 0, &Type, lpData[0], &cbData);
      if ( !v4 )
      {
        *a2 = cbData;
        *a1 = v5;
        lpData[0] = 0;
      }
    }
    else
    {
      v4 = 8;
    }
  }
LABEL_11:
  DhcpFree(lpData);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 13, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18002a8ec  mov     r11, rsp
0x18002a8ef  mov     [r11+8], rbx
0x18002a8f3  mov     [r11+10h], rsi
0x18002a8f7  push    rbp
0x18002a8f8  push    rdi
0x18002a8f9  push    r14
0x18002a8fb  mov     rbp, rsp
0x18002a8fe  sub     rsp, 40h
0x18002a902  lea     rax, [rbp+cbData]
0x18002a906  mov     [rbp+var_10], 0
0x18002a90e  mov     rsi, rdx
0x18002a911  mov     [r11-30h], rax
0x18002a915  mov     r14, rcx
0x18002a918  mov     qword ptr [r11-38h], 0
0x18002a920  mov     rcx, cs:Dhcpv6GlobalTcpipParametersKey; hKey
0x18002a927  lea     r9, [rbp+Type]; lpType
0x18002a92b  xor     r8d, r8d; lpReserved
0x18002a92e  mov     [rbp+cbData], 0
0x18002a935  lea     rdx, aDhcpv6duidover; "Dhcpv6DUIDOverride"
0x18002a93c  mov     [rbp+Type], 3
0x18002a943  call    cs:__imp_RegQueryValueExW
0x18002a94a  nop     dword ptr [rax+rax+00h]
0x18002a94f  mov     ebx, eax
0x18002a951  test    eax, eax
0x18002a953  jnz     loc_18002A9ED
0x18002a959  cmp     [rbp+Type], 3
0x18002a95d  jz      short loc_18002A969
0x18002a95f  mov     ebx, 0Dh
0x18002a964  jmp     loc_18002A9ED
0x18002a969  mov     eax, [rbp+cbData]
0x18002a96c  test    eax, eax
0x18002a96e  jnz     short loc_18002A98F
0x18002a970  test    byte ptr cs:xmmword_1800423E0, 2
0x18002a977  jz      short loc_18002A95F
0x18002a979  lea     edx, [rax+0Ch]
0x18002a97c  mov     ecx, 401h
0x18002a981  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18002a988  call    WPP_SF_
0x18002a98d  jmp     short loc_18002A95F
0x18002a98f  mov     rcx, rax
0x18002a992  call    DhcpAlloc
0x18002a997  mov     [rbp+var_10], rax
0x18002a99b  mov     rdi, rax
0x18002a99e  test    rax, rax
0x18002a9a1  jnz     short loc_18002A9A8
0x18002a9a3  lea     ebx, [rax+8]
0x18002a9a6  jmp     short loc_18002A9ED
0x18002a9a8  mov     rcx, cs:Dhcpv6GlobalTcpipParametersKey; hKey
0x18002a9af  lea     rax, [rbp+cbData]
0x18002a9b3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002a9b8  lea     r9, [rbp+Type]; lpType
0x18002a9bc  xor     r8d, r8d; lpReserved
0x18002a9bf  mov     [rsp+40h+lpData], rdi; lpData
0x18002a9c4  lea     rdx, aDhcpv6duidover; "Dhcpv6DUIDOverride"
0x18002a9cb  call    cs:__imp_RegQueryValueExW
0x18002a9d2  nop     dword ptr [rax+rax+00h]
0x18002a9d7  mov     ebx, eax
0x18002a9d9  test    eax, eax
0x18002a9db  jnz     short loc_18002A9ED
0x18002a9dd  mov     eax, [rbp+cbData]
0x18002a9e0  mov     [rsi], eax
0x18002a9e2  mov     [r14], rdi
0x18002a9e5  mov     [rbp+var_10], 0
0x18002a9ed  lea     rcx, [rbp+var_10]
0x18002a9f1  call    DhcpFree
0x18002a9f6  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002a9fd  jz      short loc_18002AA18
0x18002a9ff  mov     edx, 0Dh
0x18002aa04  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18002aa0b  mov     ecx, 404h
0x18002aa10  mov     r9d, ebx
0x18002aa13  call    WPP_SF_D
0x18002aa18  mov     rsi, [rsp+40h+arg_8]
0x18002aa1d  mov     eax, ebx
0x18002aa1f  mov     rbx, [rsp+40h+arg_0]
0x18002aa24  add     rsp, 40h
0x18002aa28  pop     r14
0x18002aa2a  pop     rdi
0x18002aa2b  pop     rbp
0x18002aa2c  retn
```
