# DhcpRegReadEnabledDhcp

- ea: `0x18000761c`
- end: `0x1800077a6`
- name: `DhcpRegReadEnabledDhcp`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR, _DWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007248`
- `0x180008240`
- `0x18001bcac`

## callees

- `0x18000761c`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007743`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007743`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007752`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000769a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000769a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800076c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800076f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800076f8`

## pseudocode

```c
__int64 __fastcall DhcpRegReadEnabledDhcp(LPCWSTR lpSubKey, LPCWSTR a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  char v7; // al
  BYTE Data[8]; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF

  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  phkResult = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 20, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
  if ( !a3 )
    goto LABEL_11;
  *a3 = 0;
  if ( !a2 )
    goto LABEL_11;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  if ( v6 )
    goto LABEL_12;
  v6 = RegOpenKeyExW(hKey, a2, 0, 1u, &phkResult);
  if ( v6 )
    goto LABEL_12;
  cbData = 4;
  v6 = RegQueryValueExW(phkResult, L"EnableDhcp", 0, &Type, Data, &cbData);
  if ( v6 )
    goto LABEL_12;
  if ( Type != 4 )
  {
LABEL_11:
    v6 = 87;
    goto LABEL_12;
  }
  v7 = Data[0];
  *a3 = *(_DWORD *)Data;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_SD(1028, 21, (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids, (_DWORD)a2, v7);
LABEL_12:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 22, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000761c  mov     [rsp-18h+arg_0], rbx
0x180007621  push    rbp
0x180007622  push    rsi
0x180007623  push    rdi
0x180007624  mov     rbp, rsp
0x180007627  sub     rsp, 50h
0x18000762b  mov     rdi, r8
0x18000762e  mov     [rbp+cbData], 0
0x180007635  mov     rsi, rdx
0x180007638  mov     [rbp+Type], 0
0x18000763f  mov     rbx, rcx
0x180007642  mov     dword ptr [rbp+Data], 0
0x180007649  mov     [rbp+hKey], 0
0x180007651  mov     [rbp+var_18], 0
0x180007659  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007660  jnz     loc_180007770
0x180007666  test    rdi, rdi
0x180007669  jz      loc_180007735
0x18000766f  mov     dword ptr [rdi], 0
0x180007675  test    rsi, rsi
0x180007678  jz      loc_180007735
0x18000767e  lea     rax, [rbp+hKey]
0x180007682  mov     r9d, 1; samDesired
0x180007688  xor     r8d, r8d; ulOptions
0x18000768b  mov     [rsp+50h+phkResult], rax; phkResult
0x180007690  mov     rdx, rbx; lpSubKey
0x180007693  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000769a  call    cs:__imp_RegOpenKeyExW
0x1800076a0  mov     ebx, eax
0x1800076a2  test    eax, eax
0x1800076a4  jnz     loc_18000773A
0x1800076aa  mov     rcx, [rbp+hKey]; hKey
0x1800076ae  lea     rax, [rbp+var_18]
0x1800076b2  lea     r9d, [rbx+1]; samDesired
0x1800076b6  mov     [rsp+50h+phkResult], rax; phkResult
0x1800076bb  xor     r8d, r8d; ulOptions
0x1800076be  mov     rdx, rsi; lpSubKey
0x1800076c1  call    cs:__imp_RegOpenKeyExW
0x1800076c7  mov     ebx, eax
0x1800076c9  test    eax, eax
0x1800076cb  jnz     short loc_18000773A
0x1800076cd  mov     rcx, [rbp+var_18]; hKey
0x1800076d1  lea     rax, [rbp+cbData]
0x1800076d5  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800076da  lea     r9, [rbp+Type]; lpType
0x1800076de  lea     rax, [rbp+Data]
0x1800076e2  mov     [rbp+cbData], 4
0x1800076e9  xor     r8d, r8d; lpReserved
0x1800076ec  mov     [rsp+50h+phkResult], rax; lpData
0x1800076f1  lea     rdx, aEnabledhcp; "EnableDhcp"
0x1800076f8  call    cs:__imp_RegQueryValueExW
0x1800076fe  mov     ebx, eax
0x180007700  test    eax, eax
0x180007702  jnz     short loc_18000773A
0x180007704  cmp     [rbp+Type], 4
0x180007708  jnz     short loc_180007735
0x18000770a  mov     eax, dword ptr [rbp+Data]
0x18000770d  mov     [rdi], eax
0x18000770f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007716  jz      short loc_18000773A
0x180007718  lea     edx, [rbx+15h]
0x18000771b  mov     dword ptr [rsp+50h+phkResult], eax
0x18000771f  mov     ecx, 404h
0x180007724  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000772b  mov     r9, rsi
0x18000772e  call    WPP_SF_SD
0x180007733  jmp     short loc_18000773A
0x180007735  mov     ebx, 57h ; 'W'
0x18000773a  mov     rcx, [rbp+var_18]; hKey
0x18000773e  test    rcx, rcx
0x180007741  jz      short loc_180007749
0x180007743  call    cs:__imp_RegCloseKey
0x180007749  mov     rcx, [rbp+hKey]; hKey
0x18000774d  test    rcx, rcx
0x180007750  jz      short loc_180007758
0x180007752  call    cs:__imp_RegCloseKey
0x180007758  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000775f  jnz     short loc_18000778B
0x180007761  mov     eax, ebx
0x180007763  mov     rbx, [rsp+50h+arg_0]
0x180007768  add     rsp, 50h
0x18000776c  pop     rdi
0x18000776d  pop     rsi
0x18000776e  pop     rbp
0x18000776f  retn
0x180007770  mov     edx, 14h
0x180007775  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000777c  mov     ecx, 404h
0x180007781  call    WPP_SF_
0x180007786  jmp     loc_180007666
0x18000778b  mov     edx, 16h
0x180007790  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180007797  mov     ecx, 404h
0x18000779c  mov     r9d, ebx
0x18000779f  call    WPP_SF_D
0x1800077a4  jmp     short loc_180007761
```
