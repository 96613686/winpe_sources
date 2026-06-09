# DhcpSetBindingInfo

- ea: `0x180022d84`
- end: `0x180022f4f`
- name: `DhcpSetBindingInfo`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004e020`

## callees

- `0x18000c2e4`
- `0x18001c56c`
- `0x18001d43c`
- `0x18001e26c`
- `0x180022d84`
- `0x18002435c`
- `0x1800cdac0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180022ee2`
- `ADVAPI32!RegCloseKey` at `0x180022f04`
- `ADVAPI32!RegCloseKey` at `0x180022ee2`
- `ADVAPI32!RegCloseKey` at `0x180022f04`
- `ADVAPI32!RegSetValueExW` at `0x180022ed0`
- `ADVAPI32!RegSetValueExW` at `0x180022ed0`
- `ADVAPI32!RegDeleteValueW` at `0x180022e8a`
- `ADVAPI32!RegDeleteValueW` at `0x180022e8a`

## pseudocode

```c
__int64 __fastcall DhcpSetBindingInfo(__int64 a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // edx
  __int64 v4; // rcx
  unsigned int v5; // r14d
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int128 v8; // xmm0
  int v9; // eax
  HKEY v10; // rcx
  HKEY hKey; // [rsp+38h] [rbp-69h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-61h] BYREF
  __int128 v14; // [rsp+48h] [rbp-59h] BYREF
  _WORD v15[64]; // [rsp+58h] [rbp-49h] BYREF

  v2 = 0;
  hKey = 0;
  v3 = 0;
  if ( !*(_DWORD *)a1 )
    goto LABEL_23;
  v4 = *(_QWORD *)(a1 + 8);
  do
  {
    if ( (*(_BYTE *)(v4 + 40LL * v3) & 1) != 0 && !*(_DWORD *)(v4 + 40LL * v3 + 4) )
      return 20051;
    ++v3;
  }
  while ( v3 < *(_DWORD *)a1 );
  v5 = 0;
  while ( 1 )
  {
    v14 = 0;
    v6 = *(_QWORD *)(a1 + 8);
    if ( (*(_BYTE *)(v6 + 40LL * v5) & 1) != 0 )
      goto LABEL_18;
    v7 = *(_DWORD *)(v6 + 40LL * v5 + 8);
    if ( *(_DWORD *)(v6 + 40LL * v5 + 24) != 16 )
      goto LABEL_22;
    v8 = *(_OWORD *)*(_QWORD *)(v6 + 40LL * v5 + 32);
    v15[0] = 0;
    v14 = v8;
    ConvertGuidToString(&v14, v15);
    v9 = DhcpOpenInterfaceByName(v15, &hKey);
    v10 = hKey;
    if ( v9 )
      goto LABEL_21;
    if ( !(unsigned int)IsAdapterStaticIP(hKey) || !(unsigned int)CheckKeyForBindability(hKey, v7) )
      break;
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL * v5 + 4) == 1 )
    {
      v2 = RegDeleteValueW(hKey, L"BindToDHCPServer");
      if ( v2 - 2 <= 1 )
        v2 = 0;
    }
    else
    {
      *(_DWORD *)Data = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 40LL * v5 + 4);
      v2 = RegSetValueExW(hKey, L"BindToDHCPServer", 0, 4u, Data, 4u);
    }
    RegCloseKey(hKey);
    if ( v2 )
      goto LABEL_23;
LABEL_18:
    if ( ++v5 >= *(_DWORD *)a1 )
      goto LABEL_23;
  }
  v10 = hKey;
LABEL_21:
  RegCloseKey(v10);
LABEL_22:
  v2 = 20050;
LABEL_23:
  WalkthroughEndpoints(0, RefreshBinding);
  return v2;
}

```

## disassembly

```asm
0x180022d84  mov     rax, rsp
0x180022d87  mov     [rax+10h], rbx
0x180022d8b  mov     [rax+18h], rsi
0x180022d8f  mov     [rax+20h], rdi
0x180022d93  push    rbp
0x180022d94  push    r14
0x180022d96  push    r15
0x180022d98  lea     rbp, [rax-5Fh]
0x180022d9c  sub     rsp, 0E0h
0x180022da3  mov     rax, cs:__security_cookie
0x180022daa  xor     rax, rsp
0x180022dad  mov     [rbp+57h+var_20], rax
0x180022db1  xor     r15d, r15d
0x180022db4  mov     rdi, rcx
0x180022db7  mov     ebx, r15d
0x180022dba  mov     [rbp+57h+hKey], r15
0x180022dbe  mov     edx, r15d
0x180022dc1  cmp     [rcx], r15d
0x180022dc4  jbe     loc_180022F15
0x180022dca  mov     rcx, [rcx+8]
0x180022dce  mov     eax, edx
0x180022dd0  lea     r8, [rax+rax*4]
0x180022dd4  test    byte ptr [rcx+r8*8], 1
0x180022dd9  jz      short loc_180022DE6
0x180022ddb  cmp     [rcx+r8*8+4], r15d
0x180022de0  jz      loc_180022EA5
0x180022de6  inc     edx
0x180022de8  cmp     edx, [rdi]
0x180022dea  jb      short loc_180022DCE
0x180022dec  mov     r14d, r15d
0x180022def  mov     eax, r14d
0x180022df2  xorps   xmm0, xmm0
0x180022df5  movups  [rbp+57h+var_B0], xmm0
0x180022df9  lea     rsi, [rax+rax*4]
0x180022dfd  mov     rax, [rdi+8]
0x180022e01  test    byte ptr [rax+rsi*8], 1
0x180022e05  jnz     loc_180022EF2
0x180022e0b  cmp     dword ptr [rax+rsi*8+18h], 10h
0x180022e10  mov     ebx, [rax+rsi*8+8]
0x180022e14  jnz     loc_180022F10
0x180022e1a  mov     rax, [rax+rsi*8+20h]
0x180022e1f  lea     rdx, [rbp+57h+var_A0]
0x180022e23  lea     rcx, [rbp+57h+var_B0]
0x180022e27  movups  xmm0, xmmword ptr [rax]
0x180022e2a  mov     [rbp+57h+var_A0], r15w
0x180022e2f  movdqu  [rbp+57h+var_B0], xmm0
0x180022e34  call    ConvertGuidToString
0x180022e39  lea     rdx, [rbp+57h+hKey]
0x180022e3d  lea     rcx, [rbp+57h+var_A0]
0x180022e41  call    DhcpOpenInterfaceByName
0x180022e46  mov     rcx, [rbp+57h+hKey]
0x180022e4a  test    eax, eax
0x180022e4c  jnz     loc_180022F04
0x180022e52  call    IsAdapterStaticIP
0x180022e57  test    eax, eax
0x180022e59  jz      loc_180022F00
0x180022e5f  mov     rcx, [rbp+57h+hKey]
0x180022e63  mov     edx, ebx
0x180022e65  call    CheckKeyForBindability
0x180022e6a  test    eax, eax
0x180022e6c  jz      loc_180022F00
0x180022e72  mov     rax, [rdi+8]
0x180022e76  mov     rcx, [rbp+57h+hKey]; hKey
0x180022e7a  mov     edx, [rax+rsi*8+4]
0x180022e7e  cmp     edx, 1
0x180022e81  jnz     short loc_180022EAC
0x180022e83  lea     rdx, aBindtodhcpserv; "BindToDHCPServer"
0x180022e8a  call    cs:__imp_RegDeleteValueW
0x180022e91  nop     dword ptr [rax+rax+00h]
0x180022e96  mov     ebx, eax
0x180022e98  add     eax, 0FFFFFFFEh
0x180022e9b  cmp     eax, 1
0x180022e9e  ja      short loc_180022EDE
0x180022ea0  mov     ebx, r15d
0x180022ea3  jmp     short loc_180022EDE
0x180022ea5  mov     eax, 4E53h
0x180022eaa  jmp     short loc_180022F25
0x180022eac  mov     dword ptr [rbp+57h+Data], edx
0x180022eaf  lea     rax, [rbp+57h+Data]
0x180022eb3  lea     rdx, aBindtodhcpserv; "BindToDHCPServer"
0x180022eba  mov     [rsp+0F0h+cbData], 4; cbData
0x180022ec2  mov     r9d, 4; dwType
0x180022ec8  mov     [rsp+0F0h+lpData], rax; lpData
0x180022ecd  xor     r8d, r8d; Reserved
0x180022ed0  call    cs:__imp_RegSetValueExW
0x180022ed7  nop     dword ptr [rax+rax+00h]
0x180022edc  mov     ebx, eax
0x180022ede  mov     rcx, [rbp+57h+hKey]; hKey
0x180022ee2  call    cs:__imp_RegCloseKey
0x180022ee9  nop     dword ptr [rax+rax+00h]
0x180022eee  test    ebx, ebx
0x180022ef0  jnz     short loc_180022F15
0x180022ef2  inc     r14d
0x180022ef5  cmp     r14d, [rdi]
0x180022ef8  jb      loc_180022DEF
0x180022efe  jmp     short loc_180022F15
0x180022f00  mov     rcx, [rbp+57h+hKey]; hKey
0x180022f04  call    cs:__imp_RegCloseKey
0x180022f0b  nop     dword ptr [rax+rax+00h]
0x180022f10  mov     ebx, 4E52h
0x180022f15  lea     rdx, RefreshBinding
0x180022f1c  xor     ecx, ecx
0x180022f1e  call    WalkthroughEndpoints
0x180022f23  mov     eax, ebx
0x180022f25  mov     rcx, [rbp+57h+var_20]
0x180022f29  xor     rcx, rsp; StackCookie
0x180022f2c  call    __security_check_cookie
0x180022f31  lea     r11, [rsp+0F0h+var_10]
0x180022f39  mov     rbx, [r11+28h]
0x180022f3d  mov     rsi, [r11+30h]
0x180022f41  mov     rdi, [r11+38h]
0x180022f45  mov     rsp, r11
0x180022f48  pop     r15
0x180022f4a  pop     r14
0x180022f4c  pop     rbp
0x180022f4d  retn
```
