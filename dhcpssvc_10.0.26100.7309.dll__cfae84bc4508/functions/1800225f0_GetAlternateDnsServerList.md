# GetAlternateDnsServerList

- ea: `0x1800225f0`
- end: `0x180022967`
- name: `GetAlternateDnsServerList`
- size: `887`
- prototype: `LPVOID __fastcall(unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001f770`
- `0x18001fc7c`
- `0x180025bf4`

## callees

- `0x1800225f0`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!wcstombs` at `0x180022820`
- `msvcrt!wcstombs` at `0x180022820`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800226ce`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800226ce`
- `ADVAPI32!RegCloseKey` at `0x180022865`
- `ADVAPI32!RegCloseKey` at `0x1800228bd`
- `ADVAPI32!RegCloseKey` at `0x180022865`
- `ADVAPI32!RegCloseKey` at `0x1800228bd`
- `ADVAPI32!RegOpenKeyExW` at `0x18002267a`
- `ADVAPI32!RegOpenKeyExW` at `0x18002267a`
- `ADVAPI32!RegEnumValueW` at `0x180022801`
- `ADVAPI32!RegEnumValueW` at `0x180022801`
- `WS2_32!__imp_inet_addr` at `0x18002283b`
- `WS2_32!__imp_inet_addr` at `0x18002283b`
- `KERNEL32!HeapAlloc` at `0x18002271e`
- `KERNEL32!HeapAlloc` at `0x18002275e`
- `KERNEL32!HeapAlloc` at `0x180022792`
- `KERNEL32!HeapAlloc` at `0x18002271e`
- `KERNEL32!HeapAlloc` at `0x18002275e`
- `KERNEL32!HeapAlloc` at `0x180022792`
- `KERNEL32!HeapFree` at `0x18002287d`
- `KERNEL32!HeapFree` at `0x180022895`
- `KERNEL32!HeapFree` at `0x1800228e4`
- `KERNEL32!HeapFree` at `0x180022908`
- `KERNEL32!HeapFree` at `0x180022925`
- `KERNEL32!HeapFree` at `0x18002287d`
- `KERNEL32!HeapFree` at `0x180022895`
- `KERNEL32!HeapFree` at `0x1800228e4`
- `KERNEL32!HeapFree` at `0x180022908`
- `KERNEL32!HeapFree` at `0x180022925`

## string_xrefs

- `0x180022652`: `System\CurrentControlSet\Services\DhcpServer\Parameters\AlternateDnsServer`

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
0x1800225f0  mov     [rsp-8+arg_8], rbx
0x1800225f5  mov     [rsp-8+arg_10], rsi
0x1800225fa  push    rbp
0x1800225fb  push    rdi
0x1800225fc  push    r12
0x1800225fe  push    r14
0x180022600  push    r15
0x180022602  lea     rbp, [rsp-37h]
0x180022607  sub     rsp, 0A0h
0x18002260e  mov     rax, cs:__security_cookie
0x180022615  xor     rax, rsp
0x180022618  mov     [rbp+57h+var_28], rax
0x18002261c  mov     rax, cs:DhcpGlobalAlternateDnsServers
0x180022623  xor     r12d, r12d
0x180022626  mov     r15, rcx
0x180022629  test    rax, rax
0x18002262c  jnz     loc_180022935
0x180022632  xorps   xmm0, xmm0
0x180022635  mov     [rbp+57h+hKey], r12
0x180022639  lea     rax, [rbp+57h+hKey]
0x18002263d  mov     [rbp+57h+cValues], r12d
0x180022641  lea     r9d, [r12+1]; samDesired
0x180022646  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002264b  xor     r8d, r8d; ulOptions
0x18002264e  mov     [rbp+57h+cbMaxValueLen], r12d
0x180022652  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Dh"...
0x180022659  mov     [rbp+57h+Type], r12d
0x18002265d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022664  mov     [rbp+57h+cchValueName], r12d
0x180022668  movups  xmmword ptr [rbp+57h+Dest], xmm0
0x18002266c  mov     esi, r12d
0x18002266f  mov     [rbp+57h+cbData], r12d
0x180022673  mov     r14d, r12d
0x180022676  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x18002267a  call    cs:__imp_RegOpenKeyExW
0x180022681  nop     dword ptr [rax+rax+00h]
0x180022686  test    eax, eax
0x180022688  jnz     loc_1800228AD
0x18002268e  mov     rcx, [rbp+57h+hKey]; hKey
0x180022692  lea     rax, [rbp+57h+cbMaxValueLen]
0x180022696  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18002269b  xor     r9d, r9d; lpReserved
0x18002269e  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800226a3  xor     r8d, r8d; lpcchClass
0x1800226a6  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800226ab  xor     edx, edx; lpClass
0x1800226ad  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800226b1  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800226b6  lea     rax, [rbp+57h+cValues]
0x1800226ba  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x1800226bf  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800226c4  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800226c9  mov     [rsp+0C0h+phkResult], r12; lpcSubKeys
0x1800226ce  call    cs:__imp_RegQueryInfoKeyW
0x1800226d5  nop     dword ptr [rax+rax+00h]
0x1800226da  test    eax, eax
0x1800226dc  jnz     loc_1800228AD
0x1800226e2  cmp     [rbp+57h+cValues], r12d
0x1800226e6  jz      loc_1800228AD
0x1800226ec  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800226ef  lea     ecx, [rax+1]
0x1800226f2  cmp     ecx, eax
0x1800226f4  jb      loc_1800228AD
0x1800226fa  mov     eax, ecx
0x1800226fc  mov     ebx, 0FFFFFFFFh
0x180022701  add     rax, rax
0x180022704  cmp     rax, rbx
0x180022707  ja      loc_1800228AD
0x18002270d  mov     rcx, cs:gDhcpHeap; hHeap
0x180022714  lea     edi, [r12+8]
0x180022719  mov     edx, edi; dwFlags
0x18002271b  mov     r8d, eax; dwBytes
0x18002271e  call    cs:__imp_HeapAlloc
0x180022725  nop     dword ptr [rax+rax+00h]
0x18002272a  mov     r14, rax
0x18002272d  test    rax, rax
0x180022730  jz      loc_1800228AD
0x180022736  mov     eax, [rbp+57h+cbMaxValueLen]
0x180022739  lea     ecx, [rax+1]
0x18002273c  cmp     ecx, eax
0x18002273e  jb      loc_1800228AD
0x180022744  mov     eax, ecx
0x180022746  add     rax, rax
0x180022749  cmp     rax, rbx
0x18002274c  ja      loc_1800228AD
0x180022752  mov     rcx, cs:gDhcpHeap; hHeap
0x180022759  mov     edx, edi; dwFlags
0x18002275b  mov     r8d, eax; dwBytes
0x18002275e  call    cs:__imp_HeapAlloc
0x180022765  nop     dword ptr [rax+rax+00h]
0x18002276a  mov     rsi, rax
0x18002276d  test    rax, rax
0x180022770  jz      loc_1800228AD
0x180022776  mov     eax, [rbp+57h+cValues]
0x180022779  shl     rax, 2
0x18002277d  cmp     rax, rbx
0x180022780  ja      loc_1800228AD
0x180022786  mov     rcx, cs:gDhcpHeap; hHeap
0x18002278d  mov     edx, edi; dwFlags
0x18002278f  mov     r8d, eax; dwBytes
0x180022792  call    cs:__imp_HeapAlloc
0x180022799  nop     dword ptr [rax+rax+00h]
0x18002279e  mov     cs:DhcpGlobalAlternateDnsServers, rax
0x1800227a5  mov     rbx, rax
0x1800227a8  test    rax, rax
0x1800227ab  jz      loc_1800228B4
0x1800227b1  mov     edi, r12d
0x1800227b4  cmp     [rbp+57h+cValues], r12d
0x1800227b8  jbe     loc_180022858
0x1800227be  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800227c1  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800227c5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800227c9  mov     r8, r14; lpValueName
0x1800227cc  mov     edx, edi; dwIndex
0x1800227ce  lea     eax, ds:2[rax*2]
0x1800227d5  mov     [rbp+57h+cbData], eax
0x1800227d8  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800227db  lea     eax, ds:2[rax*2]
0x1800227e2  mov     [rbp+57h+cchValueName], eax
0x1800227e5  lea     rax, [rbp+57h+cbData]
0x1800227e9  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x1800227ee  lea     rax, [rbp+57h+Type]
0x1800227f2  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpData
0x1800227f7  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x1800227fc  mov     [rsp+0C0h+phkResult], r12; lpReserved
0x180022801  call    cs:__imp_RegEnumValueW
0x180022808  nop     dword ptr [rax+rax+00h]
0x18002280d  test    eax, eax
0x18002280f  jnz     loc_1800228AD
0x180022815  lea     r8d, [rax+10h]; MaxCount
0x180022819  mov     rdx, rsi; Source
0x18002281c  lea     rcx, [rbp+57h+Dest]; Dest
0x180022820  call    cs:__imp_wcstombs
0x180022827  nop     dword ptr [rax+rax+00h]
0x18002282c  cmp     rax, 0Fh
0x180022830  ja      short loc_1800228AD
0x180022832  lea     rcx, [rbp+57h+Dest]; cp
0x180022836  mov     [rbp+rax+57h+Dest], r12b
0x18002283b  call    cs:__imp_inet_addr
0x180022842  nop     dword ptr [rax+rax+00h]
0x180022847  mov     [rbx], eax
0x180022849  inc     edi
0x18002284b  add     rbx, 4
0x18002284f  cmp     edi, [rbp+57h+cValues]
0x180022852  jb      loc_1800227BE
0x180022858  mov     rcx, [rbp+57h+hKey]; hKey
0x18002285c  mov     [r15], edi
0x18002285f  mov     cs:DhcpGlobalAlternateDnsServerCount, edi
0x180022865  call    cs:__imp_RegCloseKey
0x18002286c  nop     dword ptr [rax+rax+00h]
0x180022871  mov     rcx, cs:gDhcpHeap; hHeap
0x180022878  mov     r8, rsi; lpMem
0x18002287b  xor     edx, edx; dwFlags
0x18002287d  call    cs:__imp_HeapFree
0x180022884  nop     dword ptr [rax+rax+00h]
0x180022889  mov     rcx, cs:gDhcpHeap; hHeap
0x180022890  mov     r8, r14; lpMem
0x180022893  xor     edx, edx; dwFlags
0x180022895  call    cs:__imp_HeapFree
0x18002289c  nop     dword ptr [rax+rax+00h]
0x1800228a1  mov     rax, cs:DhcpGlobalAlternateDnsServers
0x1800228a8  jmp     loc_18002293E
0x1800228ad  mov     rbx, cs:DhcpGlobalAlternateDnsServers
0x1800228b4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800228b8  test    rcx, rcx
0x1800228bb  jz      short loc_1800228D0
0x1800228bd  call    cs:__imp_RegCloseKey
0x1800228c4  nop     dword ptr [rax+rax+00h]
0x1800228c9  mov     rbx, cs:DhcpGlobalAlternateDnsServers
0x1800228d0  mov     [r15], r12d
0x1800228d3  test    rbx, rbx
0x1800228d6  jz      short loc_1800228F0
0x1800228d8  mov     rcx, cs:gDhcpHeap; hHeap
0x1800228df  mov     r8, rbx; lpMem
0x1800228e2  xor     edx, edx; dwFlags
0x1800228e4  call    cs:__imp_HeapFree
0x1800228eb  nop     dword ptr [rax+rax+00h]
0x1800228f0  mov     cs:DhcpGlobalAlternateDnsServers, r12
0x1800228f7  test    rsi, rsi
0x1800228fa  jz      short loc_180022914
0x1800228fc  mov     rcx, cs:gDhcpHeap; hHeap
0x180022903  mov     r8, rsi; lpMem
0x180022906  xor     edx, edx; dwFlags
0x180022908  call    cs:__imp_HeapFree
0x18002290f  nop     dword ptr [rax+rax+00h]
0x180022914  test    r14, r14
0x180022917  jz      short loc_180022931
0x180022919  mov     rcx, cs:gDhcpHeap; hHeap
0x180022920  mov     r8, r14; lpMem
0x180022923  xor     edx, edx; dwFlags
0x180022925  call    cs:__imp_HeapFree
0x18002292c  nop     dword ptr [rax+rax+00h]
0x180022931  xor     eax, eax
0x180022933  jmp     short loc_18002293E
0x180022935  mov     ecx, cs:DhcpGlobalAlternateDnsServerCount
0x18002293b  mov     [r15], ecx
0x18002293e  mov     rcx, [rbp+57h+var_28]
0x180022942  xor     rcx, rsp; StackCookie
0x180022945  call    __security_check_cookie
0x18002294a  lea     r11, [rsp+0C0h+var_20]
0x180022952  mov     rbx, [r11+38h]
0x180022956  mov     rsi, [r11+40h]
0x18002295a  mov     rsp, r11
0x18002295d  pop     r15
0x18002295f  pop     r14
0x180022961  pop     r12
0x180022963  pop     rdi
0x180022964  pop     rbp
0x180022965  retn
```
