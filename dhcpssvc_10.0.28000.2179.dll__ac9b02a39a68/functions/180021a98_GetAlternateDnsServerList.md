# GetAlternateDnsServerList

- ea: `0x180021a98`
- end: `0x180021e0f`
- name: `GetAlternateDnsServerList`
- size: `887`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001ed34`
- `0x18001f248`
- `0x180025144`

## callees

- `0x180021a98`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!wcstombs` at `0x180021cc8`
- `msvcrt!wcstombs` at `0x180021cc8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180021b76`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180021b76`
- `ADVAPI32!RegCloseKey` at `0x180021d0d`
- `ADVAPI32!RegCloseKey` at `0x180021d65`
- `ADVAPI32!RegCloseKey` at `0x180021d0d`
- `ADVAPI32!RegCloseKey` at `0x180021d65`
- `ADVAPI32!RegOpenKeyExW` at `0x180021b22`
- `ADVAPI32!RegOpenKeyExW` at `0x180021b22`
- `ADVAPI32!RegEnumValueW` at `0x180021ca9`
- `ADVAPI32!RegEnumValueW` at `0x180021ca9`
- `WS2_32!__imp_inet_addr` at `0x180021ce3`
- `WS2_32!__imp_inet_addr` at `0x180021ce3`
- `KERNEL32!HeapAlloc` at `0x180021bc6`
- `KERNEL32!HeapAlloc` at `0x180021c06`
- `KERNEL32!HeapAlloc` at `0x180021c3a`
- `KERNEL32!HeapAlloc` at `0x180021bc6`
- `KERNEL32!HeapAlloc` at `0x180021c06`
- `KERNEL32!HeapAlloc` at `0x180021c3a`
- `KERNEL32!HeapFree` at `0x180021d25`
- `KERNEL32!HeapFree` at `0x180021d3d`
- `KERNEL32!HeapFree` at `0x180021d8c`
- `KERNEL32!HeapFree` at `0x180021db0`
- `KERNEL32!HeapFree` at `0x180021dcd`
- `KERNEL32!HeapFree` at `0x180021d25`
- `KERNEL32!HeapFree` at `0x180021d3d`
- `KERNEL32!HeapFree` at `0x180021d8c`
- `KERNEL32!HeapFree` at `0x180021db0`
- `KERNEL32!HeapFree` at `0x180021dcd`

## string_xrefs

- `0x180021afa`: `System\CurrentControlSet\Services\DhcpServer\Parameters\AlternateDnsServer`

## pseudocode

```c
LPVOID __fastcall GetAlternateDnsServerList(unsigned int *a1)
{
  LPVOID result; // rax
  void *v3; // rsi
  void *v4; // r14
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rax
  unsigned int *v8; // rbx
  unsigned int v9; // edi
  size_t v10; // rax
  HKEY v11; // rcx
  DWORD cValues; // [rsp+60h] [rbp-9h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-5h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-1h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp+3h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+Fh] BYREF
  DWORD Type; // [rsp+80h] [rbp+17h] BYREF
  char Dest[16]; // [rsp+88h] [rbp+1Fh] BYREF

  result = DhcpGlobalAlternateDnsServers;
  if ( DhcpGlobalAlternateDnsServers )
  {
    *a1 = DhcpGlobalAlternateDnsServerCount;
    return result;
  }
  hKey = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  Type = 0;
  cchValueName = 0;
  *(_OWORD *)Dest = 0;
  v3 = 0;
  cbData = 0;
  v4 = 0;
  cbMaxValueNameLen = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\DhcpServer\\Parameters\\AlternateDnsServer",
         0,
         1u,
         &hKey) )
  {
    goto LABEL_18;
  }
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
    goto LABEL_18;
  if ( !cValues )
    goto LABEL_18;
  if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen )
    goto LABEL_18;
  v5 = 2LL * (cbMaxValueNameLen + 1);
  if ( v5 > 0xFFFFFFFF )
    goto LABEL_18;
  v4 = HeapAlloc(gDhcpHeap, 8u, (unsigned int)v5);
  if ( !v4 )
    goto LABEL_18;
  if ( cbMaxValueLen + 1 < cbMaxValueLen )
    goto LABEL_18;
  v6 = 2LL * (cbMaxValueLen + 1);
  if ( v6 > 0xFFFFFFFF )
    goto LABEL_18;
  v3 = HeapAlloc(gDhcpHeap, 8u, (unsigned int)v6);
  if ( !v3 )
    goto LABEL_18;
  v7 = 4LL * cValues;
  if ( v7 > 0xFFFFFFFF )
    goto LABEL_18;
  DhcpGlobalAlternateDnsServers = HeapAlloc(gDhcpHeap, 8u, (unsigned int)v7);
  v8 = (unsigned int *)DhcpGlobalAlternateDnsServers;
  if ( DhcpGlobalAlternateDnsServers )
  {
    v9 = 0;
    if ( !cValues )
    {
LABEL_17:
      v11 = hKey;
      *a1 = v9;
      DhcpGlobalAlternateDnsServerCount = v9;
      RegCloseKey(v11);
      HeapFree(gDhcpHeap, 0, v3);
      HeapFree(gDhcpHeap, 0, v4);
      return DhcpGlobalAlternateDnsServers;
    }
    while ( 1 )
    {
      cbData = 2 * cbMaxValueLen + 2;
      cchValueName = 2 * cbMaxValueNameLen + 2;
      if ( RegEnumValueW(hKey, v9, (LPWSTR)v4, &cchValueName, 0, &Type, (LPBYTE)v3, &cbData) )
        break;
      v10 = wcstombs(Dest, (const wchar_t *)v3, 0x10u);
      if ( v10 > 0xF )
        break;
      Dest[v10] = 0;
      *v8 = inet_addr(Dest);
      ++v9;
      ++v8;
      if ( v9 >= cValues )
        goto LABEL_17;
    }
LABEL_18:
    v8 = (unsigned int *)DhcpGlobalAlternateDnsServers;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v8 = (unsigned int *)DhcpGlobalAlternateDnsServers;
  }
  *a1 = 0;
  if ( v8 )
    HeapFree(gDhcpHeap, 0, v8);
  DhcpGlobalAlternateDnsServers = 0;
  if ( v3 )
    HeapFree(gDhcpHeap, 0, v3);
  if ( v4 )
    HeapFree(gDhcpHeap, 0, v4);
  return 0;
}

```

## disassembly

```asm
0x180021a98  mov     [rsp-8+arg_8], rbx
0x180021a9d  mov     [rsp-8+arg_10], rsi
0x180021aa2  push    rbp
0x180021aa3  push    rdi
0x180021aa4  push    r12
0x180021aa6  push    r14
0x180021aa8  push    r15
0x180021aaa  lea     rbp, [rsp-37h]
0x180021aaf  sub     rsp, 0A0h
0x180021ab6  mov     rax, cs:__security_cookie
0x180021abd  xor     rax, rsp
0x180021ac0  mov     [rbp+57h+var_28], rax
0x180021ac4  mov     rax, cs:DhcpGlobalAlternateDnsServers
0x180021acb  xor     r12d, r12d
0x180021ace  mov     r15, rcx
0x180021ad1  test    rax, rax
0x180021ad4  jnz     loc_180021DDD
0x180021ada  xorps   xmm0, xmm0
0x180021add  mov     [rbp+57h+hKey], r12
0x180021ae1  lea     rax, [rbp+57h+hKey]
0x180021ae5  mov     [rbp+57h+cValues], r12d
0x180021ae9  lea     r9d, [r12+1]; samDesired
0x180021aee  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180021af3  xor     r8d, r8d; ulOptions
0x180021af6  mov     [rbp+57h+cbMaxValueLen], r12d
0x180021afa  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Dh"...
0x180021b01  mov     [rbp+57h+Type], r12d
0x180021b05  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021b0c  mov     [rbp+57h+cchValueName], r12d
0x180021b10  movups  xmmword ptr [rbp+57h+Dest], xmm0
0x180021b14  mov     esi, r12d
0x180021b17  mov     [rbp+57h+cbData], r12d
0x180021b1b  mov     r14d, r12d
0x180021b1e  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x180021b22  call    cs:__imp_RegOpenKeyExW
0x180021b29  nop     dword ptr [rax+rax+00h]
0x180021b2e  test    eax, eax
0x180021b30  jnz     loc_180021D55
0x180021b36  mov     rcx, [rbp+57h+hKey]; hKey
0x180021b3a  lea     rax, [rbp+57h+cbMaxValueLen]
0x180021b3e  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180021b43  xor     r9d, r9d; lpReserved
0x180021b46  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180021b4b  xor     r8d, r8d; lpcchClass
0x180021b4e  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180021b53  xor     edx, edx; lpClass
0x180021b55  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180021b59  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180021b5e  lea     rax, [rbp+57h+cValues]
0x180021b62  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x180021b67  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180021b6c  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180021b71  mov     [rsp+0C0h+phkResult], r12; lpcSubKeys
0x180021b76  call    cs:__imp_RegQueryInfoKeyW
0x180021b7d  nop     dword ptr [rax+rax+00h]
0x180021b82  test    eax, eax
0x180021b84  jnz     loc_180021D55
0x180021b8a  cmp     [rbp+57h+cValues], r12d
0x180021b8e  jz      loc_180021D55
0x180021b94  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180021b97  lea     ecx, [rax+1]
0x180021b9a  cmp     ecx, eax
0x180021b9c  jb      loc_180021D55
0x180021ba2  mov     eax, ecx
0x180021ba4  mov     ebx, 0FFFFFFFFh
0x180021ba9  add     rax, rax
0x180021bac  cmp     rax, rbx
0x180021baf  ja      loc_180021D55
0x180021bb5  mov     rcx, cs:gDhcpHeap; hHeap
0x180021bbc  lea     edi, [r12+8]
0x180021bc1  mov     edx, edi; dwFlags
0x180021bc3  mov     r8d, eax; dwBytes
0x180021bc6  call    cs:__imp_HeapAlloc
0x180021bcd  nop     dword ptr [rax+rax+00h]
0x180021bd2  mov     r14, rax
0x180021bd5  test    rax, rax
0x180021bd8  jz      loc_180021D55
0x180021bde  mov     eax, [rbp+57h+cbMaxValueLen]
0x180021be1  lea     ecx, [rax+1]
0x180021be4  cmp     ecx, eax
0x180021be6  jb      loc_180021D55
0x180021bec  mov     eax, ecx
0x180021bee  add     rax, rax
0x180021bf1  cmp     rax, rbx
0x180021bf4  ja      loc_180021D55
0x180021bfa  mov     rcx, cs:gDhcpHeap; hHeap
0x180021c01  mov     edx, edi; dwFlags
0x180021c03  mov     r8d, eax; dwBytes
0x180021c06  call    cs:__imp_HeapAlloc
0x180021c0d  nop     dword ptr [rax+rax+00h]
0x180021c12  mov     rsi, rax
0x180021c15  test    rax, rax
0x180021c18  jz      loc_180021D55
0x180021c1e  mov     eax, [rbp+57h+cValues]
0x180021c21  shl     rax, 2
0x180021c25  cmp     rax, rbx
0x180021c28  ja      loc_180021D55
0x180021c2e  mov     rcx, cs:gDhcpHeap; hHeap
0x180021c35  mov     edx, edi; dwFlags
0x180021c37  mov     r8d, eax; dwBytes
0x180021c3a  call    cs:__imp_HeapAlloc
0x180021c41  nop     dword ptr [rax+rax+00h]
0x180021c46  mov     cs:DhcpGlobalAlternateDnsServers, rax
0x180021c4d  mov     rbx, rax
0x180021c50  test    rax, rax
0x180021c53  jz      loc_180021D5C
0x180021c59  mov     edi, r12d
0x180021c5c  cmp     [rbp+57h+cValues], r12d
0x180021c60  jbe     loc_180021D00
0x180021c66  mov     eax, [rbp+57h+cbMaxValueLen]
0x180021c69  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180021c6d  mov     rcx, [rbp+57h+hKey]; hKey
0x180021c71  mov     r8, r14; lpValueName
0x180021c74  mov     edx, edi; dwIndex
0x180021c76  lea     eax, ds:2[rax*2]
0x180021c7d  mov     [rbp+57h+cbData], eax
0x180021c80  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180021c83  lea     eax, ds:2[rax*2]
0x180021c8a  mov     [rbp+57h+cchValueName], eax
0x180021c8d  lea     rax, [rbp+57h+cbData]
0x180021c91  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x180021c96  lea     rax, [rbp+57h+Type]
0x180021c9a  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpData
0x180021c9f  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x180021ca4  mov     [rsp+0C0h+phkResult], r12; lpReserved
0x180021ca9  call    cs:__imp_RegEnumValueW
0x180021cb0  nop     dword ptr [rax+rax+00h]
0x180021cb5  test    eax, eax
0x180021cb7  jnz     loc_180021D55
0x180021cbd  lea     r8d, [rax+10h]; MaxCount
0x180021cc1  mov     rdx, rsi; Source
0x180021cc4  lea     rcx, [rbp+57h+Dest]; Dest
0x180021cc8  call    cs:__imp_wcstombs
0x180021ccf  nop     dword ptr [rax+rax+00h]
0x180021cd4  cmp     rax, 0Fh
0x180021cd8  ja      short loc_180021D55
0x180021cda  lea     rcx, [rbp+57h+Dest]; cp
0x180021cde  mov     [rbp+rax+57h+Dest], r12b
0x180021ce3  call    cs:__imp_inet_addr
0x180021cea  nop     dword ptr [rax+rax+00h]
0x180021cef  mov     [rbx], eax
0x180021cf1  inc     edi
0x180021cf3  add     rbx, 4
0x180021cf7  cmp     edi, [rbp+57h+cValues]
0x180021cfa  jb      loc_180021C66
0x180021d00  mov     rcx, [rbp+57h+hKey]; hKey
0x180021d04  mov     [r15], edi
0x180021d07  mov     cs:DhcpGlobalAlternateDnsServerCount, edi
0x180021d0d  call    cs:__imp_RegCloseKey
0x180021d14  nop     dword ptr [rax+rax+00h]
0x180021d19  mov     rcx, cs:gDhcpHeap; hHeap
0x180021d20  mov     r8, rsi; lpMem
0x180021d23  xor     edx, edx; dwFlags
0x180021d25  call    cs:__imp_HeapFree
0x180021d2c  nop     dword ptr [rax+rax+00h]
0x180021d31  mov     rcx, cs:gDhcpHeap; hHeap
0x180021d38  mov     r8, r14; lpMem
0x180021d3b  xor     edx, edx; dwFlags
0x180021d3d  call    cs:__imp_HeapFree
0x180021d44  nop     dword ptr [rax+rax+00h]
0x180021d49  mov     rax, cs:DhcpGlobalAlternateDnsServers
0x180021d50  jmp     loc_180021DE6
0x180021d55  mov     rbx, cs:DhcpGlobalAlternateDnsServers
0x180021d5c  mov     rcx, [rbp+57h+hKey]; hKey
0x180021d60  test    rcx, rcx
0x180021d63  jz      short loc_180021D78
0x180021d65  call    cs:__imp_RegCloseKey
0x180021d6c  nop     dword ptr [rax+rax+00h]
0x180021d71  mov     rbx, cs:DhcpGlobalAlternateDnsServers
0x180021d78  mov     [r15], r12d
0x180021d7b  test    rbx, rbx
0x180021d7e  jz      short loc_180021D98
0x180021d80  mov     rcx, cs:gDhcpHeap; hHeap
0x180021d87  mov     r8, rbx; lpMem
0x180021d8a  xor     edx, edx; dwFlags
0x180021d8c  call    cs:__imp_HeapFree
0x180021d93  nop     dword ptr [rax+rax+00h]
0x180021d98  mov     cs:DhcpGlobalAlternateDnsServers, r12
0x180021d9f  test    rsi, rsi
0x180021da2  jz      short loc_180021DBC
0x180021da4  mov     rcx, cs:gDhcpHeap; hHeap
0x180021dab  mov     r8, rsi; lpMem
0x180021dae  xor     edx, edx; dwFlags
0x180021db0  call    cs:__imp_HeapFree
0x180021db7  nop     dword ptr [rax+rax+00h]
0x180021dbc  test    r14, r14
0x180021dbf  jz      short loc_180021DD9
0x180021dc1  mov     rcx, cs:gDhcpHeap; hHeap
0x180021dc8  mov     r8, r14; lpMem
0x180021dcb  xor     edx, edx; dwFlags
0x180021dcd  call    cs:__imp_HeapFree
0x180021dd4  nop     dword ptr [rax+rax+00h]
0x180021dd9  xor     eax, eax
0x180021ddb  jmp     short loc_180021DE6
0x180021ddd  mov     ecx, cs:DhcpGlobalAlternateDnsServerCount
0x180021de3  mov     [r15], ecx
0x180021de6  mov     rcx, [rbp+57h+var_28]
0x180021dea  xor     rcx, rsp; StackCookie
0x180021ded  call    __security_check_cookie
0x180021df2  lea     r11, [rsp+0C0h+var_20]
0x180021dfa  mov     rbx, [r11+38h]
0x180021dfe  mov     rsi, [r11+40h]
0x180021e02  mov     rsp, r11
0x180021e05  pop     r15
0x180021e07  pop     r14
0x180021e09  pop     r12
0x180021e0b  pop     rdi
0x180021e0c  pop     rbp
0x180021e0d  retn
```
