# Dhcpv6GenServerDuid(void)

- ea: `0x180069fcc`
- end: `0x18006a4a4`
- name: `?Dhcpv6GenServerDuid@@YAKXZ`
- size: `1240`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180069eac`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180069fcc`
- `0x18006a88c`
- `0x18006a8a0`
- `0x18008e908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a10b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a2f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a392`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a431`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a10b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a2f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a392`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a431`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a119`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a173`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a3a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a119`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a173`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a3a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a305`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a43f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a305`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a43f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006a0a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006a3d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006a0a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006a3d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a058`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a058`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006a2bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006a2bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a220`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a463`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a220`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a463`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a26d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a26d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18006a0f4`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18006a141`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18006a0f4`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18006a141`
- `WS2_32!__imp_htonl` at `0x18006a1ea`
- `WS2_32!__imp_htonl` at `0x18006a1ea`
- `WS2_32!__imp_htons` at `0x18006a1b9`
- `WS2_32!__imp_htons` at `0x18006a1c6`
- `WS2_32!__imp_htons` at `0x18006a1b9`
- `WS2_32!__imp_htons` at `0x18006a1c6`

## string_xrefs

- `0x18006a034`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x18006a23a`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
              qword_1800A7B98 = v6;
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
  qword_1800A7B98 = v6;
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
  qword_1800A7B98 = 0;
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
0x180069fcc  push    rbp
0x180069fce  push    rbx
0x180069fcf  push    rsi
0x180069fd0  push    rdi
0x180069fd1  push    r13
0x180069fd3  push    r14
0x180069fd5  mov     rbp, rsp
0x180069fd8  sub     rsp, 68h
0x180069fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180069fe3  lea     r13, WPP_GLOBAL_Control
0x180069fea  lea     rdi, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids
0x180069ff1  cmp     rcx, r13
0x180069ff4  jz      short loc_18006A013
0x180069ff6  test    byte ptr [rcx+1Ch], 4
0x180069ffa  jz      short loc_18006A013
0x180069ffc  cmp     byte ptr [rcx+19h], 6
0x18006a000  jb      short loc_18006A013
0x18006a002  mov     rcx, [rcx+10h]
0x18006a006  mov     edx, 20h ; ' '
0x18006a00b  mov     r8, rdi
0x18006a00e  call    WPP_SF_
0x18006a013  lea     rax, [rbp+hKey]
0x18006a017  mov     [rbp+SizePointer], 0
0x18006a01e  mov     r9d, 1; samDesired
0x18006a024  mov     [rsp+68h+phkResult], rax; phkResult
0x18006a029  xor     r8d, r8d; ulOptions
0x18006a02c  mov     [rbp+hKey], 0
0x18006a034  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18006a03b  mov     [rbp+dwDisposition], 0
0x18006a042  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006a049  mov     [rbp+cbData], 0
0x18006a050  mov     [rbp+Time], 0
0x18006a058  call    cs:__imp_RegOpenKeyExW
0x18006a05e  mov     r14b, 2
0x18006a061  test    eax, eax
0x18006a063  jz      short loc_18006A084
0x18006a065  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a06c  cmp     rcx, r13
0x18006a06f  jz      short loc_18006A0E1
0x18006a071  test    byte ptr [rcx+1Ch], 4
0x18006a075  jz      short loc_18006A0E1
0x18006a077  cmp     [rcx+19h], r14b
0x18006a07b  jb      short loc_18006A0E1
0x18006a07d  mov     edx, 21h ; '!'
0x18006a082  jmp     short loc_18006A0D2
0x18006a084  mov     rcx, [rbp+hKey]; hKey
0x18006a088  lea     rax, [rbp+cbData]
0x18006a08c  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18006a091  lea     rdx, aDhcpv6informse; "Dhcpv6InformServerDuid"
0x18006a098  xor     r9d, r9d; lpType
0x18006a09b  mov     [rsp+68h+phkResult], 0; lpData
0x18006a0a4  xor     r8d, r8d; lpReserved
0x18006a0a7  call    cs:__imp_RegQueryValueExW
0x18006a0ad  test    eax, eax
0x18006a0af  jz      loc_18006A38F
0x18006a0b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a0bc  cmp     rcx, r13
0x18006a0bf  jz      short loc_18006A0E1
0x18006a0c1  test    byte ptr [rcx+1Ch], 4
0x18006a0c5  jz      short loc_18006A0E1
0x18006a0c7  cmp     [rcx+19h], r14b
0x18006a0cb  jb      short loc_18006A0E1
0x18006a0cd  mov     edx, 22h ; '"'
0x18006a0d2  mov     rcx, [rcx+10h]
0x18006a0d6  mov     r9d, eax
0x18006a0d9  mov     r8, rdi
0x18006a0dc  call    WPP_SF_d
0x18006a0e1  lea     rax, [rbp+SizePointer]
0x18006a0e5  xor     r9d, r9d; AdapterAddresses
0x18006a0e8  xor     r8d, r8d; Reserved
0x18006a0eb  mov     [rsp+68h+phkResult], rax; SizePointer
0x18006a0f0  xor     edx, edx; Flags
0x18006a0f2  xor     ecx, ecx; Family
0x18006a0f4  call    cs:__imp_GetAdaptersAddresses
0x18006a0fa  mov     esi, 8
0x18006a0ff  cmp     eax, 6Fh ; 'o'
0x18006a102  jnz     loc_18006A327
0x18006a108  mov     ebx, [rbp+SizePointer]
0x18006a10b  call    cs:__imp_GetProcessHeap
0x18006a111  mov     r8d, ebx; dwBytes
0x18006a114  mov     edx, esi; dwFlags
0x18006a116  mov     rcx, rax; hHeap
0x18006a119  call    cs:__imp_HeapAlloc
0x18006a11f  mov     rdi, rax
0x18006a122  test    rax, rax
0x18006a125  jz      loc_18006A31E
0x18006a12b  lea     rax, [rbp+SizePointer]
0x18006a12f  mov     r9, rdi; AdapterAddresses
0x18006a132  xor     r8d, r8d; Reserved
0x18006a135  mov     [rsp+68h+phkResult], rax; SizePointer
0x18006a13a  xor     edx, edx; Flags
0x18006a13c  xor     ecx, ecx; Family
0x18006a13e  xor     r14d, r14d
0x18006a141  call    cs:__imp_GetAdaptersAddresses
0x18006a147  mov     ebx, eax
0x18006a149  test    eax, eax
0x18006a14b  jnz     loc_18006A2F7
0x18006a151  mov     eax, [rdi+58h]
0x18006a154  lea     ebx, [rax+9]
0x18006a157  cmp     ebx, eax
0x18006a159  jnb     short loc_18006A165
0x18006a15b  mov     ebx, 0F0h
0x18006a160  jmp     loc_18006A2F7
0x18006a165  call    cs:__imp_GetProcessHeap
0x18006a16b  mov     r8d, ebx; dwBytes
0x18006a16e  mov     edx, esi; dwFlags
0x18006a170  mov     rcx, rax; hHeap
0x18006a173  call    cs:__imp_HeapAlloc
0x18006a179  mov     r14, rax
0x18006a17c  test    rax, rax
0x18006a17f  jnz     short loc_18006A1B2
0x18006a181  mov     ebx, esi
0x18006a183  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a18a  cmp     rcx, r13
0x18006a18d  jz      loc_18006A2F7
0x18006a193  test    byte ptr [rcx+1Ch], 4
0x18006a197  jz      loc_18006A2F7
0x18006a19d  cmp     byte ptr [rcx+19h], 2
0x18006a1a1  jb      loc_18006A2F7
0x18006a1a7  lea     edx, [rax+26h]
0x18006a1aa  mov     r9d, esi
0x18006a1ad  jmp     loc_18006A2E7
0x18006a1b2  mov     ebx, 1
0x18006a1b7  mov     ecx, ebx; hostshort
0x18006a1b9  call    cs:__imp_htons
0x18006a1bf  mov     ecx, ebx; hostshort
0x18006a1c1  mov     [r14+2], ax
0x18006a1c6  call    cs:__imp_htons
0x18006a1cc  lea     rcx, [rbp+Time]; Time
0x18006a1d0  mov     [r14], ax
0x18006a1d4  call    time
0x18006a1d9  mov     rcx, rax; Time1
0x18006a1dc  mov     [rbp+Time], rax
0x18006a1e0  call    difftime
0x18006a1e5  cvttsd2si rcx, xmm0; hostlong
0x18006a1ea  call    cs:__imp_htonl
0x18006a1f0  mov     [r14+4], eax
0x18006a1f4  lea     rdx, [rdi+50h]; Src
0x18006a1f8  mov     r8d, [rdi+58h]; Size
0x18006a1fc  lea     rcx, [r14+8]; void *
0x18006a200  call    memcpy_0
0x18006a205  mov     rcx, [rbp+hKey]; hKey
0x18006a209  mov     cs:qword_1800A7B98, r14
0x18006a210  mov     eax, [rdi+58h]
0x18006a213  add     eax, esi
0x18006a215  mov     dword ptr cs:?DhcpV6GlobalInfo@@3U_IP_AUTO_DHCPv6_GLOBAL_INFO@@A+8, eax; _IP_AUTO_DHCPv6_GLOBAL_INFO DhcpV6GlobalInfo
0x18006a21b  test    rcx, rcx
0x18006a21e  jz      short loc_18006A22E
0x18006a220  call    cs:__imp_RegCloseKey
0x18006a226  mov     [rbp+hKey], 0
0x18006a22e  lea     rax, [rbp+dwDisposition]
0x18006a232  xor     r9d, r9d; lpClass
0x18006a235  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18006a23a  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18006a241  lea     rax, [rbp+hKey]
0x18006a245  xor     r8d, r8d; Reserved
0x18006a248  mov     [rsp+68h+var_30], rax; phkResult
0x18006a24d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006a254  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006a25d  mov     dword ptr [rsp+68h+lpcbData], 0F003Fh; samDesired
0x18006a265  mov     dword ptr [rsp+68h+phkResult], 0; dwOptions
0x18006a26d  call    cs:__imp_RegCreateKeyExW
0x18006a273  mov     ebx, eax
0x18006a275  test    eax, eax
0x18006a277  jz      short loc_18006A298
0x18006a279  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a280  cmp     rcx, r13
0x18006a283  jz      short loc_18006A2F7
0x18006a285  test    byte ptr [rcx+1Ch], 4
0x18006a289  jz      short loc_18006A2F7
0x18006a28b  cmp     byte ptr [rcx+19h], 2
0x18006a28f  jb      short loc_18006A2F7
0x18006a291  mov     edx, 27h ; '''
0x18006a296  jmp     short loc_18006A2E4
0x18006a298  mov     eax, dword ptr cs:?DhcpV6GlobalInfo@@3U_IP_AUTO_DHCPv6_GLOBAL_INFO@@A+8; _IP_AUTO_DHCPv6_GLOBAL_INFO DhcpV6GlobalInfo
0x18006a29e  lea     rdx, aDhcpv6informse; "Dhcpv6InformServerDuid"
0x18006a2a5  mov     rcx, [rbp+hKey]; hKey
0x18006a2a9  mov     r9d, 3; dwType
0x18006a2af  mov     dword ptr [rsp+68h+lpcbData], eax; cbData
0x18006a2b3  xor     r8d, r8d; Reserved
0x18006a2b6  mov     [rsp+68h+phkResult], r14; lpData
0x18006a2bb  call    cs:__imp_RegSetValueExW
0x18006a2c1  mov     ebx, eax
0x18006a2c3  test    eax, eax
0x18006a2c5  jz      short loc_18006A2F7
0x18006a2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a2ce  cmp     rcx, r13
0x18006a2d1  jz      short loc_18006A2F7
0x18006a2d3  test    byte ptr [rcx+1Ch], 4
0x18006a2d7  jz      short loc_18006A2F7
0x18006a2d9  cmp     byte ptr [rcx+19h], 2
0x18006a2dd  jb      short loc_18006A2F7
0x18006a2df  mov     edx, 28h ; '('
0x18006a2e4  mov     r9d, eax
0x18006a2e7  mov     rcx, [rcx+10h]
0x18006a2eb  lea     r8, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids
0x18006a2f2  call    WPP_SF_d
0x18006a2f7  call    cs:__imp_GetProcessHeap
0x18006a2fd  mov     r8, rdi; lpMem
0x18006a300  xor     edx, edx; dwFlags
0x18006a302  mov     rcx, rax; hHeap
0x18006a305  call    cs:__imp_HeapFree
0x18006a30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a312  lea     rdi, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids
0x18006a319  jmp     loc_18006A428
0x18006a31e  lea     rdi, WPP_b37e5fa9822e34ec781cdb9656fd67ca_Traceguids
0x18006a325  jmp     short loc_18006A350
0x18006a327  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a32e  cmp     rcx, r13
0x18006a331  jz      short loc_18006A357
0x18006a333  test    byte ptr [rcx+1Ch], 4
0x18006a337  jz      short loc_18006A357
0x18006a339  cmp     [rcx+19h], r14b
0x18006a33d  jb      short loc_18006A357
0x18006a33f  mov     rcx, [rcx+10h]
0x18006a343  mov     edx, 24h ; '$'
0x18006a348  mov     r8, rdi
0x18006a34b  call    WPP_SF_
0x18006a350  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a357  mov     ebx, esi
0x18006a359  cmp     rcx, r13
0x18006a35c  jz      loc_18006A44C
0x18006a362  test    byte ptr [rcx+1Ch], 4
0x18006a366  jz      loc_18006A44C
0x18006a36c  cmp     [rcx+19h], r14b
0x18006a370  jb      loc_18006A44C
0x18006a376  mov     rcx, [rcx+10h]
0x18006a37a  mov     edx, 25h ; '%'
0x18006a37f  mov     r9d, esi
0x18006a382  mov     r8, rdi
0x18006a385  call    WPP_SF_d
0x18006a38a  jmp     loc_18006A445
0x18006a38f  mov     ebx, [rbp+cbData]
0x18006a392  call    cs:__imp_GetProcessHeap
0x18006a398  mov     esi, 8
0x18006a39d  mov     r8d, ebx; dwBytes
0x18006a3a0  mov     edx, esi; dwFlags
0x18006a3a2  mov     rcx, rax; hHeap
0x18006a3a5  call    cs:__imp_HeapAlloc
0x18006a3ab  mov     r14, rax
0x18006a3ae  test    rax, rax
0x18006a3b1  jnz     short loc_18006A3BA
0x18006a3b3  mov     ebx, esi
0x18006a3b5  jmp     loc_18006A445
0x18006a3ba  mov     rcx, [rbp+hKey]; hKey
0x18006a3be  lea     rax, [rbp+cbData]
0x18006a3c2  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18006a3c7  lea     rdx, aDhcpv6informse; "Dhcpv6InformServerDuid"
0x18006a3ce  xor     r9d, r9d; lpType
0x18006a3d1  mov     [rsp+68h+phkResult], r14; lpData
0x18006a3d6  xor     r8d, r8d; lpReserved
0x18006a3d9  call    cs:__imp_RegQueryValueExW
0x18006a3df  mov     ebx, eax
0x18006a3e1  test    eax, eax
0x18006a3e3  jz      short loc_18006A411
0x18006a3e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a3ec  cmp     rcx, r13
0x18006a3ef  jz      short loc_18006A418
0x18006a3f1  test    byte ptr [rcx+1Ch], 4
0x18006a3f5  jz      short loc_18006A418
0x18006a3f7  cmp     byte ptr [rcx+19h], 3
0x18006a3fb  jb      short loc_18006A418
0x18006a3fd  mov     rcx, [rcx+10h]
0x18006a401  mov     edx, 23h ; '#'
0x18006a406  mov     r9d, eax
0x18006a409  mov     r8, rdi
0x18006a40c  call    WPP_SF_d
0x18006a411  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a418  mov     eax, [rbp+cbData]
0x18006a41b  mov     dword ptr cs:?DhcpV6GlobalInfo@@3U_IP_AUTO_DHCPv6_GLOBAL_INFO@@A+8, eax; _IP_AUTO_DHCPv6_GLOBAL_INFO DhcpV6GlobalInfo
0x18006a421  mov     cs:qword_1800A7B98, r14
0x18006a428  test    ebx, ebx
0x18006a42a  jz      short loc_18006A457
0x18006a42c  test    r14, r14
0x18006a42f  jz      short loc_18006A44C
0x18006a431  call    cs:__imp_GetProcessHeap
0x18006a437  mov     r8, r14; lpMem
0x18006a43a  xor     edx, edx; dwFlags
0x18006a43c  mov     rcx, rax; hHeap
0x18006a43f  call    cs:__imp_HeapFree
0x18006a445  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a44c  mov     cs:qword_1800A7B98, 0
0x18006a457  mov     rax, [rbp+hKey]
0x18006a45b  test    rax, rax
0x18006a45e  jz      short loc_18006A470
0x18006a460  mov     rcx, rax; hKey
0x18006a463  call    cs:__imp_RegCloseKey
0x18006a469  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a470  cmp     rcx, r13
0x18006a473  jz      short loc_18006A495
0x18006a475  test    byte ptr [rcx+1Ch], 4
0x18006a479  jz      short loc_18006A495
0x18006a47b  cmp     byte ptr [rcx+19h], 6
0x18006a47f  jb      short loc_18006A495
0x18006a481  mov     rcx, [rcx+10h]
0x18006a485  mov     edx, 29h ; ')'
0x18006a48a  mov     r9d, ebx
0x18006a48d  mov     r8, rdi
0x18006a490  call    WPP_SF_d
0x18006a495  mov     eax, ebx
  ... truncated ...
```
