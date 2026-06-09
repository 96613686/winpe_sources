# Dhcpv6GenServerDuid(void)

- ea: `0x18006f330`
- end: `0x18006f88d`
- name: `?Dhcpv6GenServerDuid@@YAKXZ`
- size: `1373`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18006f210`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18006f330`
- `0x18006fc78`
- `0x18006fc90`
- `0x180095b28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f481`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f4ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f6af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f756`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f807`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f481`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f4ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f6af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f756`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f807`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006f495`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006f501`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006f76f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006f495`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006f501`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006f76f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f6c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f81b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f6c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f81b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f411`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f7a9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f411`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006f7a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f3bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f3bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f66d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006f66d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f5c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f845`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f5c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f845`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f619`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f619`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18006f464`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18006f4c3`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18006f464`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18006f4c3`
- `WS2_32!__imp_htonl` at `0x18006f58a`
- `WS2_32!__imp_htonl` at `0x18006f58a`
- `WS2_32!__imp_htons` at `0x18006f54d`
- `WS2_32!__imp_htons` at `0x18006f560`
- `WS2_32!__imp_htons` at `0x18006f54d`
- `WS2_32!__imp_htons` at `0x18006f560`

## string_xrefs

- `0x18006f398`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x18006f5e6`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 Dhcpv6GenServerDuid(void)
{
  unsigned int v0; // eax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  ULONG v3; // ebx
  HANDLE ProcessHeap; // rax
  IP_ADAPTER_ADDRESSES_LH *v5; // rdi
  _DWORD *v6; // r14
  ULONG AdaptersAddresses; // ebx
  unsigned int PhysicalAddressLength; // eax
  unsigned int v9; // ebx
  HANDLE v10; // rax
  _DWORD *v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  time_t v15; // rdx
  double v16; // xmm0_8
  unsigned int v17; // eax
  HANDLE v18; // rax
  PVOID *v19; // rcx
  DWORD v20; // ebx
  HANDLE v21; // rax
  unsigned int v22; // eax
  HANDLE v23; // rax
  time_t Time; // [rsp+50h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+38h] BYREF
  ULONG SizePointer; // [rsp+A8h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+B0h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids);
  }
  SizePointer = 0;
  hKey = 0;
  dwDisposition = 0;
  cbData = 0;
  Time = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters", 0, 1u, &hKey);
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = 33;
LABEL_15:
      WPP_SF_d(v1[2], v2, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids, v0);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v0 = RegQueryValueExW(hKey, L"Dhcpv6InformServerDuid", 0, 0, 0, &cbData);
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = 34;
      goto LABEL_15;
    }
LABEL_16:
    if ( GetAdaptersAddresses(0, 0, 0, 0, &SizePointer) == 111 )
    {
      v3 = SizePointer;
      ProcessHeap = GetProcessHeap();
      v5 = (IP_ADAPTER_ADDRESSES_LH *)HeapAlloc(ProcessHeap, 8u, v3);
      if ( v5 )
      {
        v6 = 0;
        AdaptersAddresses = GetAdaptersAddresses(0, 0, 0, v5, &SizePointer);
        if ( !AdaptersAddresses )
        {
          PhysicalAddressLength = v5->PhysicalAddressLength;
          v9 = PhysicalAddressLength + 9;
          if ( PhysicalAddressLength + 9 >= PhysicalAddressLength )
          {
            v10 = GetProcessHeap();
            v11 = HeapAlloc(v10, 8u, v9);
            v6 = v11;
            if ( v11 )
            {
              *((_WORD *)v11 + 1) = htons(1u);
              *(_WORD *)v6 = htons(1u);
              Time = time(&Time);
              v16 = difftime(Time, v15);
              v6[1] = htonl((int)v16);
              memcpy_0(v6 + 2, v5->PhysicalAddress, v5->PhysicalAddressLength);
              qword_1800AEC58 = v6;
              *(&DhcpV6GlobalInfo + 2) = v5->PhysicalAddressLength + 8;
              if ( hKey )
              {
                RegCloseKey(hKey);
                hKey = 0;
              }
              v17 = RegCreateKeyExW(
                      HKEY_LOCAL_MACHINE,
                      L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
                      0,
                      0,
                      0,
                      0xF003Fu,
                      0,
                      &hKey,
                      &dwDisposition);
              AdaptersAddresses = v17;
              if ( v17 )
              {
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_40;
                }
                v13 = 39;
              }
              else
              {
                v17 = RegSetValueExW(hKey, L"Dhcpv6InformServerDuid", 0, 3u, (const BYTE *)v6, *(&DhcpV6GlobalInfo + 2));
                AdaptersAddresses = v17;
                if ( !v17 )
                  goto LABEL_40;
                v12 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_40;
                }
                v13 = 40;
              }
              v14 = v17;
            }
            else
            {
              AdaptersAddresses = 8;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_40;
              }
              v13 = 38;
              v14 = 8;
            }
            WPP_SF_d(v12[2], v13, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids, v14);
          }
          else
          {
            AdaptersAddresses = 240;
          }
        }
LABEL_40:
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v5);
        v19 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_60;
      }
    }
    else
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids);
    }
    v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_47:
    AdaptersAddresses = 8;
    if ( v19 == &WPP_GLOBAL_Control || (*((_BYTE *)v19 + 28) & 4) == 0 || *((_BYTE *)v19 + 25) < 2u )
      goto LABEL_64;
    WPP_SF_d(v19[2], 37, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids, 8);
    goto LABEL_63;
  }
  v20 = cbData;
  v21 = GetProcessHeap();
  v6 = HeapAlloc(v21, 8u, v20);
  if ( !v6 )
  {
    AdaptersAddresses = 8;
LABEL_63:
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_64;
  }
  v22 = RegQueryValueExW(hKey, L"Dhcpv6InformServerDuid", 0, 0, (LPBYTE)v6, &cbData);
  AdaptersAddresses = v22;
  if ( v22 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_59;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids, v22);
  }
  v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_59:
  *(&DhcpV6GlobalInfo + 2) = cbData;
  qword_1800AEC58 = v6;
LABEL_60:
  if ( !AdaptersAddresses )
    goto LABEL_65;
  if ( v6 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v6);
    goto LABEL_63;
  }
LABEL_64:
  qword_1800AEC58 = 0;
LABEL_65:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 && *((_BYTE *)v19 + 25) >= 6u )
    WPP_SF_d(v19[2], 41, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids, AdaptersAddresses);
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x18006f330  push    rbp
0x18006f332  push    rbx
0x18006f333  push    rsi
0x18006f334  push    rdi
0x18006f335  push    r13
0x18006f337  push    r14
0x18006f339  mov     rbp, rsp
0x18006f33c  sub     rsp, 68h
0x18006f340  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f347  lea     r13, WPP_GLOBAL_Control
0x18006f34e  lea     rdi, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids
0x18006f355  cmp     rcx, r13
0x18006f358  jz      short loc_18006F377
0x18006f35a  test    byte ptr [rcx+1Ch], 4
0x18006f35e  jz      short loc_18006F377
0x18006f360  cmp     byte ptr [rcx+19h], 6
0x18006f364  jb      short loc_18006F377
0x18006f366  mov     rcx, [rcx+10h]
0x18006f36a  mov     edx, 20h ; ' '
0x18006f36f  mov     r8, rdi
0x18006f372  call    WPP_SF_
0x18006f377  lea     rax, [rbp+hKey]
0x18006f37b  mov     [rbp+SizePointer], 0
0x18006f382  mov     r9d, 1; samDesired
0x18006f388  mov     [rsp+68h+phkResult], rax; phkResult
0x18006f38d  xor     r8d, r8d; ulOptions
0x18006f390  mov     [rbp+hKey], 0
0x18006f398  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18006f39f  mov     [rbp+dwDisposition], 0
0x18006f3a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006f3ad  mov     [rbp+cbData], 0
0x18006f3b4  mov     [rbp+Time], 0
0x18006f3bc  call    cs:__imp_RegOpenKeyExW
0x18006f3c3  nop     dword ptr [rax+rax+00h]
0x18006f3c8  mov     r14b, 2
0x18006f3cb  test    eax, eax
0x18006f3cd  jz      short loc_18006F3EE
0x18006f3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f3d6  cmp     rcx, r13
0x18006f3d9  jz      short loc_18006F451
0x18006f3db  test    byte ptr [rcx+1Ch], 4
0x18006f3df  jz      short loc_18006F451
0x18006f3e1  cmp     [rcx+19h], r14b
0x18006f3e5  jb      short loc_18006F451
0x18006f3e7  mov     edx, 21h ; '!'
0x18006f3ec  jmp     short loc_18006F442
0x18006f3ee  mov     rcx, [rbp+hKey]; hKey
0x18006f3f2  lea     rax, [rbp+cbData]
0x18006f3f6  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18006f3fb  lea     rdx, aDhcpv6informse; "Dhcpv6InformServerDuid"
0x18006f402  xor     r9d, r9d; lpType
0x18006f405  mov     [rsp+68h+phkResult], 0; lpData
0x18006f40e  xor     r8d, r8d; lpReserved
0x18006f411  call    cs:__imp_RegQueryValueExW
0x18006f418  nop     dword ptr [rax+rax+00h]
0x18006f41d  test    eax, eax
0x18006f41f  jz      loc_18006F753
0x18006f425  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f42c  cmp     rcx, r13
0x18006f42f  jz      short loc_18006F451
0x18006f431  test    byte ptr [rcx+1Ch], 4
0x18006f435  jz      short loc_18006F451
0x18006f437  cmp     [rcx+19h], r14b
0x18006f43b  jb      short loc_18006F451
0x18006f43d  mov     edx, 22h ; '"'
0x18006f442  mov     rcx, [rcx+10h]
0x18006f446  mov     r9d, eax
0x18006f449  mov     r8, rdi
0x18006f44c  call    WPP_SF_d
0x18006f451  lea     rax, [rbp+SizePointer]
0x18006f455  xor     r9d, r9d; AdapterAddresses
0x18006f458  xor     r8d, r8d; Reserved
0x18006f45b  mov     [rsp+68h+phkResult], rax; SizePointer
0x18006f460  xor     edx, edx; Flags
0x18006f462  xor     ecx, ecx; Family
0x18006f464  call    cs:__imp_GetAdaptersAddresses
0x18006f46b  nop     dword ptr [rax+rax+00h]
0x18006f470  mov     esi, 8
0x18006f475  cmp     eax, 6Fh ; 'o'
0x18006f478  jnz     loc_18006F6EB
0x18006f47e  mov     ebx, [rbp+SizePointer]
0x18006f481  call    cs:__imp_GetProcessHeap
0x18006f488  nop     dword ptr [rax+rax+00h]
0x18006f48d  mov     r8d, ebx; dwBytes
0x18006f490  mov     edx, esi; dwFlags
0x18006f492  mov     rcx, rax; hHeap
0x18006f495  call    cs:__imp_HeapAlloc
0x18006f49c  nop     dword ptr [rax+rax+00h]
0x18006f4a1  mov     rdi, rax
0x18006f4a4  test    rax, rax
0x18006f4a7  jz      loc_18006F6E2
0x18006f4ad  lea     rax, [rbp+SizePointer]
0x18006f4b1  mov     r9, rdi; AdapterAddresses
0x18006f4b4  xor     r8d, r8d; Reserved
0x18006f4b7  mov     [rsp+68h+phkResult], rax; SizePointer
0x18006f4bc  xor     edx, edx; Flags
0x18006f4be  xor     ecx, ecx; Family
0x18006f4c0  xor     r14d, r14d
0x18006f4c3  call    cs:__imp_GetAdaptersAddresses
0x18006f4ca  nop     dword ptr [rax+rax+00h]
0x18006f4cf  mov     ebx, eax
0x18006f4d1  test    eax, eax
0x18006f4d3  jnz     loc_18006F6AF
0x18006f4d9  mov     eax, [rdi+58h]
0x18006f4dc  lea     ebx, [rax+9]
0x18006f4df  cmp     ebx, eax
0x18006f4e1  jnb     short loc_18006F4ED
0x18006f4e3  mov     ebx, 0F0h
0x18006f4e8  jmp     loc_18006F6AF
0x18006f4ed  call    cs:__imp_GetProcessHeap
0x18006f4f4  nop     dword ptr [rax+rax+00h]
0x18006f4f9  mov     r8d, ebx; dwBytes
0x18006f4fc  mov     edx, esi; dwFlags
0x18006f4fe  mov     rcx, rax; hHeap
0x18006f501  call    cs:__imp_HeapAlloc
0x18006f508  nop     dword ptr [rax+rax+00h]
0x18006f50d  mov     r14, rax
0x18006f510  test    rax, rax
0x18006f513  jnz     short loc_18006F546
0x18006f515  mov     ebx, esi
0x18006f517  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f51e  cmp     rcx, r13
0x18006f521  jz      loc_18006F6AF
0x18006f527  test    byte ptr [rcx+1Ch], 4
0x18006f52b  jz      loc_18006F6AF
0x18006f531  cmp     byte ptr [rcx+19h], 2
0x18006f535  jb      loc_18006F6AF
0x18006f53b  lea     edx, [rax+26h]
0x18006f53e  mov     r9d, esi
0x18006f541  jmp     loc_18006F69F
0x18006f546  mov     ebx, 1
0x18006f54b  mov     ecx, ebx; hostshort
0x18006f54d  call    cs:__imp_htons
0x18006f554  nop     dword ptr [rax+rax+00h]
0x18006f559  mov     ecx, ebx; hostshort
0x18006f55b  mov     [r14+2], ax
0x18006f560  call    cs:__imp_htons
0x18006f567  nop     dword ptr [rax+rax+00h]
0x18006f56c  lea     rcx, [rbp+Time]; Time
0x18006f570  mov     [r14], ax
0x18006f574  call    time
0x18006f579  mov     rcx, rax; Time1
0x18006f57c  mov     [rbp+Time], rax
0x18006f580  call    difftime
0x18006f585  cvttsd2si rcx, xmm0; hostlong
0x18006f58a  call    cs:__imp_htonl
0x18006f591  nop     dword ptr [rax+rax+00h]
0x18006f596  mov     [r14+4], eax
0x18006f59a  lea     rdx, [rdi+50h]; Src
0x18006f59e  mov     r8d, [rdi+58h]; Size
0x18006f5a2  lea     rcx, [r14+8]; void *
0x18006f5a6  call    memcpy_0
0x18006f5ab  mov     rcx, [rbp+hKey]; hKey
0x18006f5af  mov     cs:qword_1800AEC58, r14
0x18006f5b6  mov     eax, [rdi+58h]
0x18006f5b9  add     eax, esi
0x18006f5bb  mov     dword ptr cs:?DhcpV6GlobalInfo@@3U_IP_AUTO_DHCPv6_GLOBAL_INFO@@A+8, eax; _IP_AUTO_DHCPv6_GLOBAL_INFO DhcpV6GlobalInfo
0x18006f5c1  test    rcx, rcx
0x18006f5c4  jz      short loc_18006F5DA
0x18006f5c6  call    cs:__imp_RegCloseKey
0x18006f5cd  nop     dword ptr [rax+rax+00h]
0x18006f5d2  mov     [rbp+hKey], 0
0x18006f5da  lea     rax, [rbp+dwDisposition]
0x18006f5de  xor     r9d, r9d; lpClass
0x18006f5e1  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18006f5e6  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18006f5ed  lea     rax, [rbp+hKey]
0x18006f5f1  xor     r8d, r8d; Reserved
0x18006f5f4  mov     [rsp+68h+var_30], rax; phkResult
0x18006f5f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006f600  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006f609  mov     dword ptr [rsp+68h+lpcbData], 0F003Fh; samDesired
0x18006f611  mov     dword ptr [rsp+68h+phkResult], 0; dwOptions
0x18006f619  call    cs:__imp_RegCreateKeyExW
0x18006f620  nop     dword ptr [rax+rax+00h]
0x18006f625  mov     ebx, eax
0x18006f627  test    eax, eax
0x18006f629  jz      short loc_18006F64A
0x18006f62b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f632  cmp     rcx, r13
0x18006f635  jz      short loc_18006F6AF
0x18006f637  test    byte ptr [rcx+1Ch], 4
0x18006f63b  jz      short loc_18006F6AF
0x18006f63d  cmp     byte ptr [rcx+19h], 2
0x18006f641  jb      short loc_18006F6AF
0x18006f643  mov     edx, 27h ; '''
0x18006f648  jmp     short loc_18006F69C
0x18006f64a  mov     eax, dword ptr cs:?DhcpV6GlobalInfo@@3U_IP_AUTO_DHCPv6_GLOBAL_INFO@@A+8; _IP_AUTO_DHCPv6_GLOBAL_INFO DhcpV6GlobalInfo
0x18006f650  lea     rdx, aDhcpv6informse; "Dhcpv6InformServerDuid"
0x18006f657  mov     rcx, [rbp+hKey]; hKey
0x18006f65b  mov     r9d, 3; dwType
0x18006f661  mov     dword ptr [rsp+68h+lpcbData], eax; cbData
0x18006f665  xor     r8d, r8d; Reserved
0x18006f668  mov     [rsp+68h+phkResult], r14; lpData
0x18006f66d  call    cs:__imp_RegSetValueExW
0x18006f674  nop     dword ptr [rax+rax+00h]
0x18006f679  mov     ebx, eax
0x18006f67b  test    eax, eax
0x18006f67d  jz      short loc_18006F6AF
0x18006f67f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f686  cmp     rcx, r13
0x18006f689  jz      short loc_18006F6AF
0x18006f68b  test    byte ptr [rcx+1Ch], 4
0x18006f68f  jz      short loc_18006F6AF
0x18006f691  cmp     byte ptr [rcx+19h], 2
0x18006f695  jb      short loc_18006F6AF
0x18006f697  mov     edx, 28h ; '('
0x18006f69c  mov     r9d, eax
0x18006f69f  mov     rcx, [rcx+10h]
0x18006f6a3  lea     r8, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids
0x18006f6aa  call    WPP_SF_d
0x18006f6af  call    cs:__imp_GetProcessHeap
0x18006f6b6  nop     dword ptr [rax+rax+00h]
0x18006f6bb  mov     r8, rdi; lpMem
0x18006f6be  xor     edx, edx; dwFlags
0x18006f6c0  mov     rcx, rax; hHeap
0x18006f6c3  call    cs:__imp_HeapFree
0x18006f6ca  nop     dword ptr [rax+rax+00h]
0x18006f6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f6d6  lea     rdi, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids
0x18006f6dd  jmp     loc_18006F7FE
0x18006f6e2  lea     rdi, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids
0x18006f6e9  jmp     short loc_18006F714
0x18006f6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f6f2  cmp     rcx, r13
0x18006f6f5  jz      short loc_18006F71B
0x18006f6f7  test    byte ptr [rcx+1Ch], 4
0x18006f6fb  jz      short loc_18006F71B
0x18006f6fd  cmp     [rcx+19h], r14b
0x18006f701  jb      short loc_18006F71B
0x18006f703  mov     rcx, [rcx+10h]
0x18006f707  mov     edx, 24h ; '$'
0x18006f70c  mov     r8, rdi
0x18006f70f  call    WPP_SF_
0x18006f714  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f71b  mov     ebx, esi
0x18006f71d  cmp     rcx, r13
0x18006f720  jz      loc_18006F82E
0x18006f726  test    byte ptr [rcx+1Ch], 4
0x18006f72a  jz      loc_18006F82E
0x18006f730  cmp     [rcx+19h], r14b
0x18006f734  jb      loc_18006F82E
0x18006f73a  mov     rcx, [rcx+10h]
0x18006f73e  mov     edx, 25h ; '%'
0x18006f743  mov     r9d, esi
0x18006f746  mov     r8, rdi
0x18006f749  call    WPP_SF_d
0x18006f74e  jmp     loc_18006F827
0x18006f753  mov     ebx, [rbp+cbData]
0x18006f756  call    cs:__imp_GetProcessHeap
0x18006f75d  nop     dword ptr [rax+rax+00h]
0x18006f762  mov     esi, 8
0x18006f767  mov     r8d, ebx; dwBytes
0x18006f76a  mov     edx, esi; dwFlags
0x18006f76c  mov     rcx, rax; hHeap
0x18006f76f  call    cs:__imp_HeapAlloc
0x18006f776  nop     dword ptr [rax+rax+00h]
0x18006f77b  mov     r14, rax
0x18006f77e  test    rax, rax
0x18006f781  jnz     short loc_18006F78A
0x18006f783  mov     ebx, esi
0x18006f785  jmp     loc_18006F827
0x18006f78a  mov     rcx, [rbp+hKey]; hKey
0x18006f78e  lea     rax, [rbp+cbData]
0x18006f792  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18006f797  lea     rdx, aDhcpv6informse; "Dhcpv6InformServerDuid"
0x18006f79e  xor     r9d, r9d; lpType
0x18006f7a1  mov     [rsp+68h+phkResult], r14; lpData
0x18006f7a6  xor     r8d, r8d; lpReserved
0x18006f7a9  call    cs:__imp_RegQueryValueExW
0x18006f7b0  nop     dword ptr [rax+rax+00h]
0x18006f7b5  mov     ebx, eax
0x18006f7b7  test    eax, eax
0x18006f7b9  jz      short loc_18006F7E7
0x18006f7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f7c2  cmp     rcx, r13
0x18006f7c5  jz      short loc_18006F7EE
0x18006f7c7  test    byte ptr [rcx+1Ch], 4
0x18006f7cb  jz      short loc_18006F7EE
0x18006f7cd  cmp     byte ptr [rcx+19h], 3
0x18006f7d1  jb      short loc_18006F7EE
0x18006f7d3  mov     rcx, [rcx+10h]
0x18006f7d7  mov     edx, 23h ; '#'
0x18006f7dc  mov     r9d, eax
0x18006f7df  mov     r8, rdi
0x18006f7e2  call    WPP_SF_d
0x18006f7e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f7ee  mov     eax, [rbp+cbData]
0x18006f7f1  mov     dword ptr cs:?DhcpV6GlobalInfo@@3U_IP_AUTO_DHCPv6_GLOBAL_INFO@@A+8, eax; _IP_AUTO_DHCPv6_GLOBAL_INFO DhcpV6GlobalInfo
0x18006f7f7  mov     cs:qword_1800AEC58, r14
0x18006f7fe  test    ebx, ebx
0x18006f800  jz      short loc_18006F839
0x18006f802  test    r14, r14
0x18006f805  jz      short loc_18006F82E
0x18006f807  call    cs:__imp_GetProcessHeap
0x18006f80e  nop     dword ptr [rax+rax+00h]
0x18006f813  mov     r8, r14; lpMem
0x18006f816  xor     edx, edx; dwFlags
0x18006f818  mov     rcx, rax; hHeap
0x18006f81b  call    cs:__imp_HeapFree
  ... truncated ...
```
