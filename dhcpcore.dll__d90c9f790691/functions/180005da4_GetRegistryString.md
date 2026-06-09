# GetRegistryString

- ea: `0x180005da4`
- end: `0x180005f22`
- name: `GetRegistryString`
- size: `382`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, _QWORD *, DWORD *)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800026fc`
- `0x180003ea0`
- `0x1800042b8`
- `0x180004ae0`
- `0x18000a194`
- `0x18000f51c`
- `0x180011454`
- `0x1800139e4`
- `0x18001a5d0`
- `0x180036008`
- `0x18003b520`

## callees

- `0x1800057f0`
- `0x180005da4`
- `0x180006440`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005eb2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005e12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005eb2`

## pseudocode

```c
__int64 __fastcall GetRegistryString(HKEY hKey, LPCWSTR lpValueName, _QWORD *a3, DWORD *a4)
{
  unsigned int v8; // ebx
  LPBYTE v10; // rsi
  unsigned int v11; // eax
  __int64 v12; // rcx
  LPBYTE lpData[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+18h] BYREF
  DWORD Type; // [rsp+88h] [rbp+20h] BYREF

  Type = 0;
  cbData = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  if ( !v8 && cbData )
  {
    lpData[0] = (LPBYTE)DhcpAlloc(cbData + 2LL);
    v10 = lpData[0];
    if ( lpData[0] )
    {
      v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData[0], &cbData);
      v8 = v11;
      if ( v11 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_D(1025, 11, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v11);
        DhcpPunycodeFree(lpData);
      }
      else
      {
        v12 = cbData & 0xFFFFFFFE;
        *a3 = lpData[0];
        *(_WORD *)&v10[v12] = 0;
        if ( a4 )
          *a4 = cbData;
      }
    }
    else
    {
      v8 = 8;
    }
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 12, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180005da4  mov     rax, rsp
0x180005da7  mov     [rax+8], rbx
0x180005dab  push    rbp
0x180005dac  push    rsi
0x180005dad  push    rdi
0x180005dae  push    r14
0x180005db0  push    r15
0x180005db2  sub     rsp, 40h
0x180005db6  mov     rdi, r9
0x180005db9  mov     dword ptr [rax+20h], 0
0x180005dc0  mov     r14, r8
0x180005dc3  mov     dword ptr [rax+18h], 0
0x180005dca  mov     rbp, rdx
0x180005dcd  mov     r15, rcx
0x180005dd0  test    byte ptr cs:xmmword_1800616A0, 10h
0x180005dd7  jnz     short loc_180005E53
0x180005dd9  mov     qword ptr [r14], 0
0x180005de0  test    rdi, rdi
0x180005de3  jz      short loc_180005DEB
0x180005de5  mov     dword ptr [rdi], 0
0x180005deb  lea     rax, [rsp+68h+cbData]
0x180005df3  xor     r8d, r8d; lpReserved
0x180005df6  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180005dfb  lea     r9, [rsp+68h+Type]; lpType
0x180005e03  mov     rdx, rbp; lpValueName
0x180005e06  mov     [rsp+68h+lpData], 0; lpData
0x180005e0f  mov     rcx, r15; hKey
0x180005e12  call    cs:__imp_RegQueryValueExW
0x180005e18  mov     ebx, eax
0x180005e1a  test    eax, eax
0x180005e1c  jz      short loc_180005E6E
0x180005e1e  test    byte ptr cs:xmmword_1800616A0, 10h
0x180005e25  jz      short loc_180005E40
0x180005e27  mov     edx, 0Ch
0x180005e2c  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180005e33  mov     ecx, 404h
0x180005e38  mov     r9d, ebx
0x180005e3b  call    WPP_SF_D
0x180005e40  mov     eax, ebx
0x180005e42  mov     rbx, [rsp+68h+arg_0]
0x180005e47  add     rsp, 40h
0x180005e4b  pop     r15
0x180005e4d  pop     r14
0x180005e4f  pop     rdi
0x180005e50  pop     rsi
0x180005e51  pop     rbp
0x180005e52  retn
0x180005e53  mov     edx, 0Ah
0x180005e58  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180005e5f  mov     ecx, 404h
0x180005e64  call    WPP_SF_
0x180005e69  jmp     loc_180005DD9
0x180005e6e  mov     eax, [rsp+68h+cbData]
0x180005e75  test    eax, eax
0x180005e77  jz      short loc_180005E1E
0x180005e79  lea     rcx, [rax+2]
0x180005e7d  call    DhcpAlloc
0x180005e82  mov     [rsp+68h+var_38], rax
0x180005e87  mov     rsi, rax
0x180005e8a  test    rax, rax
0x180005e8d  jz      short loc_180005EE7
0x180005e8f  lea     rax, [rsp+68h+cbData]
0x180005e97  xor     r8d, r8d; lpReserved
0x180005e9a  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180005e9f  lea     r9, [rsp+68h+Type]; lpType
0x180005ea7  mov     rdx, rbp; lpValueName
0x180005eaa  mov     [rsp+68h+lpData], rsi; lpData
0x180005eaf  mov     rcx, r15; hKey
0x180005eb2  call    cs:__imp_RegQueryValueExW
0x180005eb8  mov     ebx, eax
0x180005eba  test    eax, eax
0x180005ebc  jnz     short loc_180005EF1
0x180005ebe  mov     ecx, [rsp+68h+cbData]
0x180005ec5  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180005ec9  mov     [r14], rsi
0x180005ecc  mov     [rcx+rsi], ax
0x180005ed0  test    rdi, rdi
0x180005ed3  jz      loc_180005E1E
0x180005ed9  mov     eax, [rsp+68h+cbData]
0x180005ee0  mov     [rdi], eax
0x180005ee2  jmp     loc_180005E1E
0x180005ee7  mov     ebx, 8
0x180005eec  jmp     loc_180005E1E
0x180005ef1  test    byte ptr cs:xmmword_1800616A0, 2
0x180005ef8  jz      short loc_180005F13
0x180005efa  mov     edx, 0Bh
0x180005eff  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180005f06  mov     ecx, 401h
0x180005f0b  mov     r9d, eax
0x180005f0e  call    WPP_SF_D
0x180005f13  lea     rcx, [rsp+68h+var_38]
0x180005f18  call    DhcpPunycodeFree
0x180005f1d  jmp     loc_180005E1E
```
