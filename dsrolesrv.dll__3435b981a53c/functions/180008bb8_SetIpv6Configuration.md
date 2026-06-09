# SetIpv6Configuration

- ea: `0x180008bb8`
- end: `0x180008e9d`
- name: `SetIpv6Configuration`
- size: `741`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180003ff0`

## callees

- `0x18000700c`
- `0x180008bb8`
- `0x180008f24`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008d15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008d15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008e67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008c37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008c37`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008d9d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e37`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008dcc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008dcc`
- `ntdll!RtlIpv6StringToAddressW` at `0x180008c7f`
- `ntdll!RtlIpv6StringToAddressW` at `0x180008c7f`
- `DNSAPI!DnsNotifyResolver` at `0x180008e4a`
- `DNSAPI!DnsNotifyResolver` at `0x180008e4a`

## string_xrefs

- `0x180008d07`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall SetIpv6Configuration(__int64 a1)
{
  size_t v2; // rsi
  __int64 i; // rdx
  int v4; // eax
  wchar_t *v5; // rax
  wchar_t *v6; // rdi
  DWORD LastError; // ebx
  unsigned int j; // r15d
  const WCHAR *v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  DWORD AllInterfaceInfo; // eax
  HLOCAL v13; // r15
  int v14; // r12d
  HLOCAL k; // r14
  const wchar_t *v16; // r8
  HKEY hKey; // [rsp+30h] [rbp-79h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-71h] BYREF
  PCWSTR Terminator; // [rsp+40h] [rbp-69h] BYREF
  in6_addr Addr; // [rsp+48h] [rbp-61h] BYREF
  WCHAR WideCharStr[40]; // [rsp+60h] [rbp-49h] BYREF

  hKey = 0;
  Terminator = 0;
  v2 = 0;
  Addr = 0;
  hMem = 0;
  for ( i = 0; i != 4; ++i )
  {
    v4 = *(_DWORD *)(a1 + 4 * i + 160);
    if ( v4 && *(_QWORD *)(a1 + 8 * i + 128) )
      v2 += (unsigned int)(v4 + 1);
  }
  if ( !v2 )
    v2 = 1;
  v5 = (wchar_t *)LocalAlloc(0x40u, 2 * v2);
  v6 = v5;
  if ( !v5 )
  {
    LastError = 14;
    goto LABEL_40;
  }
  *v5 = 0;
  for ( j = 0; j < 4; ++j )
  {
    if ( *(_DWORD *)(a1 + 4LL * j + 160) )
    {
      v9 = *(const WCHAR **)(a1 + 8LL * j + 128);
      if ( v9 )
      {
        v10 = RtlIpv6StringToAddressW(v9, &Terminator, &Addr);
        LastError = v10;
        if ( v10 )
        {
          DsRolepLogPrintRoutine(
            1,
            "vDC Cloning: Error validating IPv6 DNS resolver address '%ws': 0x%x.\n",
            *(_QWORD *)(a1 + 8LL * j + 128),
            v10);
          goto LABEL_40;
        }
        if ( *v6 && StringCchCatW(v6, v2, L",") < 0
          || StringCchCatW(v6, v2, *(STRSAFE_LPCWSTR *)(a1 + 8LL * j + 128)) < 0 )
        {
          LastError = 87;
          goto LABEL_40;
        }
      }
    }
  }
  v6[v2 - 1] = 0;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces",
                0,
                0x2001Fu,
                &hKey);
  if ( !LastError )
  {
    AllInterfaceInfo = GetAllInterfaceInfo(v11, &hMem);
    v13 = hMem;
    LastError = AllInterfaceInfo;
    if ( !AllInterfaceInfo )
    {
      if ( !hMem )
        goto LABEL_40;
      v14 = 0;
      for ( k = hMem; k; k = (HLOCAL)*((_QWORD *)k + 1) )
      {
        if ( (*((_DWORD *)k + 23) & 0x100) != 0 && *((_DWORD *)k + 25) != 131 && *((_DWORD *)k + 25) != 24 )
        {
          if ( !MultiByteToWideChar(0, 8u, *((LPCCH *)k + 2), -1, WideCharStr, 39) )
          {
            LastError = GetLastError();
            goto LABEL_38;
          }
          LastError = RegSetKeyValueW(hKey, WideCharStr, L"NameServer", 1u, v6, 2 * v2);
          if ( LastError )
            goto LABEL_38;
          v14 = 1;
          DsRolepLogPrintRoutine(4, "vDC Cloning: Set IPv6 DNS server search order:\n");
          DsRolepLogPrintRoutine(4, "\tAdapter name: %ws\n", *((_QWORD *)k + 9));
          DsRolepLogPrintRoutine(4, "\tAdapter guid: %ws\n", WideCharStr);
          v16 = L"Obtain DNS server address automatically";
          if ( v2 > 1 )
            v16 = v6;
          DsRolepLogPrintRoutine(LastError + 4, "\tIPv6 DNS Resolvers: %ws\n", v16);
        }
      }
      if ( v14 )
        DnsNotifyResolver(0, 0);
    }
LABEL_38:
    if ( v13 )
      LocalFree(v13);
  }
LABEL_40:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    LocalFree(v6);
  return LastError;
}

```

## disassembly

```asm
0x180008bb8  push    rbp
0x180008bba  push    rbx
0x180008bbb  push    rsi
0x180008bbc  push    rdi
0x180008bbd  push    r12
0x180008bbf  push    r13
0x180008bc1  push    r14
0x180008bc3  push    r15
0x180008bc5  lea     rbp, [rsp-1Fh]
0x180008bca  sub     rsp, 0C8h
0x180008bd1  mov     rax, cs:__security_cookie
0x180008bd8  xor     rax, rsp
0x180008bdb  mov     [rbp+57h+var_50], rax
0x180008bdf  xor     ebx, ebx
0x180008be1  xorps   xmm0, xmm0
0x180008be4  mov     r14, rcx
0x180008be7  mov     [rbp+57h+hKey], rbx
0x180008beb  mov     [rbp+57h+Terminator], rbx
0x180008bef  mov     esi, ebx
0x180008bf1  movups  xmmword ptr [rbp+57h+Addr.u], xmm0
0x180008bf5  lea     r8d, [rbx+1]
0x180008bf9  mov     [rbp+57h+hMem], rbx
0x180008bfd  mov     edx, ebx
0x180008bff  mov     eax, [r14+rdx*4+0A0h]
0x180008c07  test    eax, eax
0x180008c09  jz      short loc_180008C1B
0x180008c0b  cmp     [r14+rdx*8+80h], rbx
0x180008c13  jz      short loc_180008C1B
0x180008c15  lea     ecx, [rax+1]
0x180008c18  add     rsi, rcx
0x180008c1b  add     rdx, r8
0x180008c1e  cmp     rdx, 4
0x180008c22  jnz     short loc_180008BFF
0x180008c24  test    rsi, rsi
0x180008c27  mov     ecx, 40h ; '@'; uFlags
0x180008c2c  cmovz   rsi, r8
0x180008c30  lea     r13, [rsi+rsi]
0x180008c34  mov     rdx, r13; uBytes
0x180008c37  call    cs:__imp_LocalAlloc
0x180008c3d  mov     rdi, rax
0x180008c40  test    rax, rax
0x180008c43  jnz     short loc_180008C4D
0x180008c45  lea     ebx, [rax+0Eh]
0x180008c48  jmp     loc_180008E5E
0x180008c4d  mov     [rax], bx
0x180008c50  mov     r15d, ebx
0x180008c53  cmp     r15d, 4
0x180008c57  jnb     loc_180008CEF
0x180008c5d  mov     r12d, r15d
0x180008c60  cmp     [r14+r12*4+0A0h], ebx
0x180008c68  jz      short loc_180008CBF
0x180008c6a  mov     rcx, [r14+r12*8+80h]; S
0x180008c72  test    rcx, rcx
0x180008c75  jz      short loc_180008CBF
0x180008c77  lea     r8, [rbp+57h+Addr]; Addr
0x180008c7b  lea     rdx, [rbp+57h+Terminator]; Terminator
0x180008c7f  call    cs:__imp_RtlIpv6StringToAddressW
0x180008c85  mov     ebx, eax
0x180008c87  test    eax, eax
0x180008c89  jnz     short loc_180008CCE
0x180008c8b  xor     ebx, ebx
0x180008c8d  cmp     [rdi], bx
0x180008c90  jz      short loc_180008CA8
0x180008c92  lea     r8, asc_18003A4E8; ","
0x180008c99  mov     rdx, rsi; cchDest
0x180008c9c  mov     rcx, rdi; pszDest
0x180008c9f  call    StringCchCatW
0x180008ca4  test    eax, eax
0x180008ca6  js      short loc_180008CC4
0x180008ca8  mov     r8, [r14+r12*8+80h]; pszSrc
0x180008cb0  mov     rdx, rsi; cchDest
0x180008cb3  mov     rcx, rdi; pszDest
0x180008cb6  call    StringCchCatW
0x180008cbb  test    eax, eax
0x180008cbd  js      short loc_180008CC4
0x180008cbf  inc     r15d
0x180008cc2  jmp     short loc_180008C53
0x180008cc4  mov     ebx, 57h ; 'W'
0x180008cc9  jmp     loc_180008E5E
0x180008cce  mov     r8, [r14+r12*8+80h]
0x180008cd6  lea     rdx, aVdcCloningErro; "vDC Cloning: Error validating IPv6 DNS "...
0x180008cdd  mov     r9d, eax
0x180008ce0  mov     ecx, 1
0x180008ce5  call    DsRolepLogPrintRoutine
0x180008cea  jmp     loc_180008E5E
0x180008cef  lea     rax, [rbp+57h+hKey]
0x180008cf3  mov     [rdi+r13-2], bx
0x180008cf9  mov     r9d, 2001Fh; samDesired
0x180008cff  mov     [rsp+100h+phkResult], rax; phkResult
0x180008d04  xor     r8d, r8d; ulOptions
0x180008d07  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x180008d0e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008d15  call    cs:__imp_RegOpenKeyExW
0x180008d1b  xor     r13d, r13d
0x180008d1e  mov     ebx, eax
0x180008d20  test    eax, eax
0x180008d22  jnz     loc_180008E5E
0x180008d28  lea     rdx, [rbp+57h+hMem]
0x180008d2c  call    GetAllInterfaceInfo
0x180008d31  mov     r15, [rbp+57h+hMem]
0x180008d35  mov     ebx, eax
0x180008d37  test    eax, eax
0x180008d39  jnz     loc_180008E50
0x180008d3f  test    r15, r15
0x180008d42  jz      loc_180008E5E
0x180008d48  mov     r12d, r13d
0x180008d4b  mov     r14, r15
0x180008d4e  test    r14, r14
0x180008d51  jz      loc_180008E41
0x180008d57  test    dword ptr [r14+5Ch], 100h
0x180008d5f  jz      loc_180008E2E
0x180008d65  cmp     dword ptr [r14+64h], 83h
0x180008d6d  jz      loc_180008E2E
0x180008d73  cmp     dword ptr [r14+64h], 18h
0x180008d78  jz      loc_180008E2E
0x180008d7e  mov     r8, [r14+10h]; lpMultiByteStr
0x180008d82  lea     rax, [rbp+57h+WideCharStr]
0x180008d86  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180008d8a  mov     [rsp+100h+cchWideChar], 27h ; '''; cchWideChar
0x180008d92  xor     ecx, ecx; CodePage
0x180008d94  mov     [rsp+100h+phkResult], rax; lpWideCharStr
0x180008d99  lea     edx, [r9+9]; dwFlags
0x180008d9d  call    cs:__imp_MultiByteToWideChar
0x180008da3  test    eax, eax
0x180008da5  jz      loc_180008E37
0x180008dab  mov     rcx, [rbp+57h+hKey]; hKey
0x180008daf  lea     eax, [rsi+rsi]
0x180008db2  mov     [rsp+100h+cchWideChar], eax; cbData
0x180008db6  lea     r8, aNameserver; "NameServer"
0x180008dbd  mov     r9d, 1; dwType
0x180008dc3  mov     [rsp+100h+phkResult], rdi; lpData
0x180008dc8  lea     rdx, [rbp+57h+WideCharStr]; lpSubKey
0x180008dcc  call    cs:__imp_RegSetKeyValueW
0x180008dd2  mov     ebx, eax
0x180008dd4  test    eax, eax
0x180008dd6  jnz     short loc_180008E50
0x180008dd8  lea     rdx, aVdcCloningSetI_1; "vDC Cloning: Set IPv6 DNS server search"...
0x180008ddf  lea     ecx, [rax+4]
0x180008de2  lea     r12d, [rax+1]
0x180008de6  call    DsRolepLogPrintRoutine
0x180008deb  mov     r8, [r14+48h]
0x180008def  lea     rdx, aAdapterNameWs; "\tAdapter name: %ws\n"
0x180008df6  lea     ecx, [rbx+4]
0x180008df9  call    DsRolepLogPrintRoutine
0x180008dfe  lea     r8, [rbp+57h+WideCharStr]
0x180008e02  lea     rdx, aAdapterGuidWs; "\tAdapter guid: %ws\n"
0x180008e09  lea     ecx, [rbx+4]
0x180008e0c  call    DsRolepLogPrintRoutine
0x180008e11  cmp     rsi, r12
0x180008e14  lea     r8, aObtainDnsServe; "Obtain DNS server address automatically"
0x180008e1b  lea     rdx, aIpv6DnsResolve_0; "\tIPv6 DNS Resolvers: %ws\n"
0x180008e22  cmova   r8, rdi
0x180008e26  lea     ecx, [rbx+4]
0x180008e29  call    DsRolepLogPrintRoutine
0x180008e2e  mov     r14, [r14+8]
0x180008e32  jmp     loc_180008D4E
0x180008e37  call    cs:__imp_GetLastError
0x180008e3d  mov     ebx, eax
0x180008e3f  jmp     short loc_180008E50
0x180008e41  test    r12d, r12d
0x180008e44  jz      short loc_180008E50
0x180008e46  xor     edx, edx
0x180008e48  xor     ecx, ecx
0x180008e4a  call    cs:__imp_DnsNotifyResolver
0x180008e50  test    r15, r15
0x180008e53  jz      short loc_180008E5E
0x180008e55  mov     rcx, r15; hMem
0x180008e58  call    cs:__imp_LocalFree
0x180008e5e  mov     rcx, [rbp+57h+hKey]; hKey
0x180008e62  test    rcx, rcx
0x180008e65  jz      short loc_180008E6D
0x180008e67  call    cs:__imp_RegCloseKey
0x180008e6d  test    rdi, rdi
0x180008e70  jz      short loc_180008E7B
0x180008e72  mov     rcx, rdi; hMem
0x180008e75  call    cs:__imp_LocalFree
0x180008e7b  mov     eax, ebx
0x180008e7d  mov     rcx, [rbp+57h+var_50]
0x180008e81  xor     rcx, rsp; StackCookie
0x180008e84  call    __security_check_cookie
0x180008e89  add     rsp, 0C8h
0x180008e90  pop     r15
0x180008e92  pop     r14
0x180008e94  pop     r13
0x180008e96  pop     r12
0x180008e98  pop     rdi
0x180008e99  pop     rsi
0x180008e9a  pop     rbx
0x180008e9b  pop     rbp
0x180008e9c  retn
```
