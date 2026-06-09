# ReadPrefixDataFromRegistry(_DHCPV6PrefixLeaseInformation *)

- ea: `0x18000d1d0`
- end: `0x18000d692`
- name: `?ReadPrefixDataFromRegistry@@YAKPEAU_DHCPV6PrefixLeaseInformation@@@Z`
- size: `1218`
- prototype: `unsigned int __fastcall(struct _DHCPV6PrefixLeaseInformation *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000c140`
- `0x180038be4`
- `0x180065b08`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000d1d0`
- `0x18002e7a4`
- `0x18004e0c0`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d46a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d46a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d679`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d3e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d478`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d3e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d478`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d372`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d687`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d372`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d687`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d3af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d44b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d4b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d4eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d526`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d562`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d59e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d5da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d649`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d3af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d44b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d4b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d4eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d526`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d562`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d59e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d5da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d2cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d2cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d2b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000d2b5`

## string_xrefs

- `0x18000d282`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 __fastcall ReadPrefixDataFromRegistry(struct _DHCPV6PrefixLeaseInformation *a1)
{
  struct _DHCPV6Prefix *v2; // r14
  unsigned int Value; // ebx
  LPBYTE ServerId; // rdi
  HANDLE v6; // rax
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v9; // r8
  struct _DHCPV6Prefix *v10; // rax
  unsigned int v11; // edi
  BYTE *v12; // r15
  DWORD i; // eax
  HKEY v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edi
  HANDLE v17; // rax
  BYTE *v18; // rax
  HKEY v19; // rcx
  HKEY v20; // rcx
  HKEY v21; // rcx
  HKEY v22; // rcx
  HANDLE v23; // rax
  DWORD cbData[2]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+68h] [rbp-A0h] BYREF
  BYTE v27[4]; // [rsp+6Ch] [rbp-9Ch] BYREF
  BYTE v28[4]; // [rsp+70h] [rbp-98h] BYREF
  BYTE v29[4]; // [rsp+74h] [rbp-94h] BYREF
  BYTE v30[4]; // [rsp+78h] [rbp-90h] BYREF
  BYTE v31[4]; // [rsp+7Ch] [rbp-8Ch] BYREF
  unsigned int v32; // [rsp+80h] [rbp-88h] BYREF
  DWORD dwDisposition; // [rsp+84h] [rbp-84h] BYREF
  WCHAR ValueName[264]; // [rsp+88h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b002d07646b635308a4693336a4759d4_Traceguids);
  }
  *(_DWORD *)Data = 0;
  *(_DWORD *)v28 = 0;
  *(_DWORD *)v29 = 0;
  *(_DWORD *)v30 = 0;
  v32 = 0;
  *(_DWORD *)v31 = 0;
  cbData[0] = 0;
  dwDisposition = 0;
  hKey = 0;
  memset_0(ValueName, 0, 0x208u);
  *(_DWORD *)v27 = 0;
  v2 = 0;
  Value = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
            0,
            0,
            0,
            0xF003Fu,
            0,
            &hKey,
            &dwDisposition);
  if ( !Value )
  {
    cbData[0] = 4;
    Value = RegQueryValueExW(hKey, L"NumberOfPrefixes", 0, 0, Data, cbData);
    if ( !Value )
    {
      if ( *(_DWORD *)Data )
      {
        v7 = 32 * *(_DWORD *)Data;
        ProcessHeap = GetProcessHeap();
        v9 = v7;
        Value = 8;
        v10 = (struct _DHCPV6Prefix *)HeapAlloc(ProcessHeap, 8u, v9);
        v2 = v10;
        if ( v10 )
        {
          v11 = 0;
          v12 = (BYTE *)v10;
          cbData[0] = 32;
          for ( i = *(_DWORD *)Data; v11 < *(_DWORD *)Data; ++v11 )
          {
            StringCchPrintfW(ValueName, 0x104u, L"ICS_IPv6_Prefix_%d", v11);
            RegQueryValueExW(hKey, ValueName, 0, 0, v12, cbData);
            i = *(_DWORD *)Data;
            v12 += 32;
          }
          v14 = hKey;
          a1->nPrefixes = i;
          a1->prefixArray = v2;
          cbData[0] = 4;
          RegQueryValueExW(v14, L"ICS_IPv6_Dhcpv6ServerIDLen", 0, 0, v27, cbData);
          v15 = *(_DWORD *)v27;
          if ( *(_DWORD *)v27 )
          {
            a1->ServerIdLen = *(_DWORD *)v27;
            v16 = v15;
            v17 = GetProcessHeap();
            v18 = (BYTE *)HeapAlloc(v17, 8u, v16);
            a1->ServerId = v18;
            if ( v18 )
            {
              cbData[0] = *(_DWORD *)v27;
              RegQueryValueExW(hKey, L"ICS_IPv6_Dhcpv6ServerID", 0, 0, v18, cbData);
              cbData[0] = 4;
              RegQueryValueExW(hKey, L"ICS_IPv6_iaid", 0, 0, v28, cbData);
              v19 = hKey;
              a1->iaid = *(_DWORD *)v28;
              cbData[0] = 4;
              RegQueryValueExW(v19, L"ICS_IPv6_T1", 0, 0, v29, cbData);
              v20 = hKey;
              a1->T1 = *(unsigned int *)v29;
              cbData[0] = 4;
              RegQueryValueExW(v20, L"ICS_IPv6_T2", 0, 0, v30, cbData);
              v21 = hKey;
              a1->T2 = *(unsigned int *)v30;
              cbData[0] = 4;
              RegQueryValueExW(v21, L"ICS_IPv6_Dhcpv6LastRenewalTime", 0, 0, v31, cbData);
              v22 = hKey;
              a1->LastRenewalTime = *(unsigned int *)v31;
              cbData[0] = 4;
              Value = RegQueryValueExW(v22, L"ICS_IPv6_Dhcpv6MaxLeaseExpirationTime", 0, 0, (LPBYTE)&v32, cbData);
              a1->MaxLeaseExpirationTime = v32;
            }
          }
          else
          {
            Value = 87;
          }
        }
      }
      else
      {
        Value = 87;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( Value )
  {
    if ( v2 )
    {
      if ( a1->prefixArray == v2 )
      {
        a1->prefixArray = 0;
        a1->nPrefixes = 0;
      }
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v2);
    }
    ServerId = a1->ServerId;
    if ( ServerId )
    {
      v6 = GetProcessHeap();
      HeapFree(v6, 0, ServerId);
      a1->ServerId = 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b002d07646b635308a4693336a4759d4_Traceguids, Value);
  }
  return Value;
}

```

## disassembly

```asm
0x18000d1d0  mov     r11, rsp
0x18000d1d3  push    rbp
0x18000d1d4  push    rbx
0x18000d1d5  lea     rbp, [r11-1C8h]
0x18000d1dc  sub     rsp, 2B8h
0x18000d1e3  mov     rax, cs:__security_cookie
0x18000d1ea  xor     rax, rsp
0x18000d1ed  mov     [rbp+1C0h+var_30], rax
0x18000d1f4  mov     [r11+10h], rsi
0x18000d1f8  mov     rsi, rcx
0x18000d1fb  mov     [r11+20h], r12
0x18000d1ff  mov     [r11-18h], r13
0x18000d203  mov     [r11-20h], r14
0x18000d207  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d20e  lea     r13, WPP_GLOBAL_Control
0x18000d215  cmp     rcx, r13
0x18000d218  jz      short loc_18000D22A
0x18000d21a  test    byte ptr [rcx+1Ch], 80h
0x18000d21e  jz      short loc_18000D22A
0x18000d220  cmp     byte ptr [rcx+19h], 6
0x18000d224  jnb     loc_18000D5EF
0x18000d22a  xor     r12d, r12d
0x18000d22d  mov     [rsp+2C0h+arg_10], rdi
0x18000d235  xor     edx, edx; Val
0x18000d237  mov     dword ptr [rsp+2C0h+Data], r12d
0x18000d23c  mov     r8d, 208h; Size
0x18000d242  mov     dword ptr [rsp+2C0h+var_258], r12d
0x18000d247  lea     rcx, [rbp+1C0h+ValueName]; void *
0x18000d24b  mov     dword ptr [rsp+2C0h+var_254], r12d
0x18000d250  mov     dword ptr [rsp+2C0h+var_250], r12d
0x18000d255  mov     [rsp+2C0h+var_248], r12d
0x18000d25a  mov     dword ptr [rsp+2C0h+var_24C], r12d
0x18000d25f  mov     [rsp+2C0h+cbData], r12d
0x18000d264  mov     [rsp+2C0h+dwDisposition], r12d
0x18000d269  mov     [rsp+2C0h+hKey], r12
0x18000d26e  call    memset_0
0x18000d273  lea     rax, [rsp+2C0h+dwDisposition]
0x18000d278  mov     dword ptr [rsp+2C0h+var_25C], r12d
0x18000d27d  mov     [rsp+40h], rax; lpdwDisposition
0x18000d282  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18000d289  lea     rax, [rsp+2C0h+hKey]
0x18000d28e  xor     r9d, r9d; lpClass
0x18000d291  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18000d296  xor     r8d, r8d; Reserved
0x18000d299  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000d29e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d2a5  mov     [rsp+2C0h+samDesired], 0F003Fh; samDesired
0x18000d2ad  mov     r14d, r12d
0x18000d2b0  mov     [rsp+2C0h+dwOptions], r12d; dwOptions
0x18000d2b5  call    cs:__imp_RegCreateKeyExW
0x18000d2bb  mov     ebx, eax
0x18000d2bd  test    eax, eax
0x18000d2bf  jz      loc_18000D381
0x18000d2c5  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d2ca  test    rcx, rcx
0x18000d2cd  jz      short loc_18000D2D5
0x18000d2cf  call    cs:__imp_RegCloseKey
0x18000d2d5  test    ebx, ebx
0x18000d2d7  jnz     short loc_18000D34E
0x18000d2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2e0  mov     r14, [rsp+2C0h+var_18]
0x18000d2e8  cmp     rcx, r13
0x18000d2eb  mov     r13, [rsp+2B0h]
0x18000d2f3  mov     r12, [rsp+2C0h+arg_18]
0x18000d2fb  mov     rdi, [rsp+2C0h+arg_10]
0x18000d303  mov     rsi, [rsp+2C0h+arg_8]
0x18000d30b  jnz     short loc_18000D328
0x18000d30d  mov     eax, ebx
0x18000d30f  mov     rcx, [rbp+1C0h+var_30]
0x18000d316  xor     rcx, rsp; StackCookie
0x18000d319  call    __security_check_cookie
0x18000d31e  add     rsp, 2B8h
0x18000d325  pop     rbx
0x18000d326  pop     rbp
0x18000d327  retn
0x18000d328  test    byte ptr [rcx+1Ch], 80h
0x18000d32c  jz      short loc_18000D30D
0x18000d32e  cmp     byte ptr [rcx+19h], 6
0x18000d332  jb      short loc_18000D30D
0x18000d334  mov     rcx, [rcx+10h]
0x18000d338  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000d33f  mov     edx, 0Bh
0x18000d344  mov     r9d, ebx
0x18000d347  call    WPP_SF_d
0x18000d34c  jmp     short loc_18000D30D
0x18000d34e  test    r14, r14
0x18000d351  jnz     loc_18000D66C
0x18000d357  mov     rdi, [rsi+40h]
0x18000d35b  test    rdi, rdi
0x18000d35e  jz      loc_18000D2D9
0x18000d364  call    cs:__imp_GetProcessHeap
0x18000d36a  mov     r8, rdi; lpMem
0x18000d36d  xor     edx, edx; dwFlags
0x18000d36f  mov     rcx, rax; hHeap
0x18000d372  call    cs:__imp_HeapFree
0x18000d378  mov     [rsi+40h], r12
0x18000d37c  jmp     loc_18000D2D9
0x18000d381  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d386  lea     rax, [rsp+2C0h+cbData]
0x18000d38b  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d390  lea     rdx, ValueName; "NumberOfPrefixes"
0x18000d397  lea     rax, [rsp+2C0h+Data]
0x18000d39c  mov     [rsp+2C0h+cbData], 4
0x18000d3a4  xor     r9d, r9d; lpType
0x18000d3a7  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000d3ac  xor     r8d, r8d; lpReserved
0x18000d3af  call    cs:__imp_RegQueryValueExW
0x18000d3b5  mov     ebx, eax
0x18000d3b7  test    eax, eax
0x18000d3b9  jnz     loc_18000D2C5
0x18000d3bf  mov     eax, dword ptr [rsp+2C0h+Data]
0x18000d3c3  test    eax, eax
0x18000d3c5  jz      loc_18000D609
0x18000d3cb  shl     eax, 5
0x18000d3ce  mov     ebx, eax
0x18000d3d0  call    cs:__imp_GetProcessHeap
0x18000d3d6  mov     r8d, ebx; dwBytes
0x18000d3d9  mov     ebx, 8
0x18000d3de  mov     edx, ebx; dwFlags
0x18000d3e0  mov     rcx, rax; hHeap
0x18000d3e3  call    cs:__imp_HeapAlloc
0x18000d3e9  mov     r14, rax
0x18000d3ec  test    rax, rax
0x18000d3ef  jz      loc_18000D2C5
0x18000d3f5  mov     [rsp+2C0h+var_20], r15
0x18000d3fd  mov     edi, r12d
0x18000d400  mov     r15, rax
0x18000d403  mov     [rsp+2C0h+cbData], 20h ; ' '
0x18000d40b  mov     eax, dword ptr [rsp+2C0h+Data]
0x18000d40f  test    eax, eax
0x18000d411  jnz     loc_18000D613
0x18000d417  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d41c  lea     rdx, aIcsIpv6Dhcpv6s_0; "ICS_IPv6_Dhcpv6ServerIDLen"
0x18000d423  mov     [rsi], eax
0x18000d425  xor     r9d, r9d; lpType
0x18000d428  lea     rax, [rsp+2C0h+cbData]
0x18000d42d  mov     [rsi+8], r14
0x18000d431  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d436  xor     r8d, r8d; lpReserved
0x18000d439  lea     rax, [rsp+2C0h+var_25C]
0x18000d43e  mov     [rsp+2C0h+cbData], 4
0x18000d446  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000d44b  call    cs:__imp_RegQueryValueExW
0x18000d451  mov     eax, dword ptr [rsp+2C0h+var_25C]
0x18000d455  mov     r15, [rsp+2C0h+var_20]
0x18000d45d  test    eax, eax
0x18000d45f  jz      loc_18000D662
0x18000d465  mov     [rsi+48h], eax
0x18000d468  mov     edi, eax
0x18000d46a  call    cs:__imp_GetProcessHeap
0x18000d470  mov     r8d, edi; dwBytes
0x18000d473  mov     edx, ebx; dwFlags
0x18000d475  mov     rcx, rax; hHeap
0x18000d478  call    cs:__imp_HeapAlloc
0x18000d47e  mov     [rsi+40h], rax
0x18000d482  mov     rcx, rax
0x18000d485  test    rax, rax
0x18000d488  jz      loc_18000D2C5
0x18000d48e  mov     eax, dword ptr [rsp+2C0h+var_25C]
0x18000d492  lea     rdx, aIcsIpv6Dhcpv6s; "ICS_IPv6_Dhcpv6ServerID"
0x18000d499  mov     [rsp+2C0h+cbData], eax
0x18000d49d  xor     r9d, r9d; lpType
0x18000d4a0  lea     rax, [rsp+2C0h+cbData]
0x18000d4a5  xor     r8d, r8d; lpReserved
0x18000d4a8  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d4ad  mov     qword ptr [rsp+2C0h+dwOptions], rcx; lpData
0x18000d4b2  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d4b7  call    cs:__imp_RegQueryValueExW
0x18000d4bd  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d4c2  lea     rax, [rsp+2C0h+cbData]
0x18000d4c7  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d4cc  lea     rdx, aIcsIpv6Iaid; "ICS_IPv6_iaid"
0x18000d4d3  lea     rax, [rsp+2C0h+var_258]
0x18000d4d8  mov     [rsp+2C0h+cbData], 4
0x18000d4e0  xor     r9d, r9d; lpType
0x18000d4e3  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000d4e8  xor     r8d, r8d; lpReserved
0x18000d4eb  call    cs:__imp_RegQueryValueExW
0x18000d4f1  mov     eax, dword ptr [rsp+2C0h+var_258]
0x18000d4f5  lea     rdx, aIcsIpv6T1; "ICS_IPv6_T1"
0x18000d4fc  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d501  xor     r9d, r9d; lpType
0x18000d504  mov     [rsi+10h], eax
0x18000d507  xor     r8d, r8d; lpReserved
0x18000d50a  lea     rax, [rsp+2C0h+cbData]
0x18000d50f  mov     [rsp+2C0h+cbData], 4
0x18000d517  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d51c  lea     rax, [rsp+2C0h+var_254]
0x18000d521  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000d526  call    cs:__imp_RegQueryValueExW
0x18000d52c  mov     eax, dword ptr [rsp+2C0h+var_254]
0x18000d530  lea     rdx, aIcsIpv6T2; "ICS_IPv6_T2"
0x18000d537  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d53c  xor     r9d, r9d; lpType
0x18000d53f  mov     [rsi+18h], rax
0x18000d543  xor     r8d, r8d; lpReserved
0x18000d546  lea     rax, [rsp+2C0h+cbData]
0x18000d54b  mov     [rsp+2C0h+cbData], 4
0x18000d553  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d558  lea     rax, [rsp+2C0h+var_250]
0x18000d55d  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000d562  call    cs:__imp_RegQueryValueExW
0x18000d568  mov     eax, dword ptr [rsp+2C0h+var_250]
0x18000d56c  lea     rdx, aIcsIpv6Dhcpv6l; "ICS_IPv6_Dhcpv6LastRenewalTime"
0x18000d573  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d578  xor     r9d, r9d; lpType
0x18000d57b  mov     [rsi+20h], rax
0x18000d57f  xor     r8d, r8d; lpReserved
0x18000d582  lea     rax, [rsp+2C0h+cbData]
0x18000d587  mov     [rsp+2C0h+cbData], 4
0x18000d58f  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d594  lea     rax, [rsp+2C0h+var_24C]
0x18000d599  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000d59e  call    cs:__imp_RegQueryValueExW
0x18000d5a4  mov     eax, dword ptr [rsp+2C0h+var_24C]
0x18000d5a8  lea     rdx, aIcsIpv6Dhcpv6m; "ICS_IPv6_Dhcpv6MaxLeaseExpirationTime"
0x18000d5af  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d5b4  xor     r9d, r9d; lpType
0x18000d5b7  mov     [rsi+30h], rax
0x18000d5bb  xor     r8d, r8d; lpReserved
0x18000d5be  lea     rax, [rsp+2C0h+cbData]
0x18000d5c3  mov     [rsp+2C0h+cbData], 4
0x18000d5cb  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d5d0  lea     rax, [rsp+2C0h+var_248]
0x18000d5d5  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000d5da  call    cs:__imp_RegQueryValueExW
0x18000d5e0  mov     ebx, eax
0x18000d5e2  mov     eax, [rsp+2C0h+var_248]
0x18000d5e6  mov     [rsi+28h], rax
0x18000d5ea  jmp     loc_18000D2C5
0x18000d5ef  mov     rcx, [rcx+10h]
0x18000d5f3  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000d5fa  mov     edx, 0Ah
0x18000d5ff  call    WPP_SF_
0x18000d604  jmp     loc_18000D22A
0x18000d609  mov     ebx, 57h ; 'W'
0x18000d60e  jmp     loc_18000D2C5
0x18000d613  mov     r9d, edi
0x18000d616  lea     r8, aIcsIpv6PrefixD; "ICS_IPv6_Prefix_%d"
0x18000d61d  mov     edx, 104h; unsigned __int64
0x18000d622  lea     rcx, [rbp+1C0h+ValueName]; unsigned __int16 *
0x18000d626  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d62b  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000d630  lea     rax, [rsp+2C0h+cbData]
0x18000d635  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000d63a  lea     rdx, [rbp+1C0h+ValueName]; lpValueName
0x18000d63e  xor     r9d, r9d; lpType
0x18000d641  mov     qword ptr [rsp+2C0h+dwOptions], r15; lpData
0x18000d646  xor     r8d, r8d; lpReserved
0x18000d649  call    cs:__imp_RegQueryValueExW
0x18000d64f  mov     eax, dword ptr [rsp+2C0h+Data]
0x18000d653  add     r15, 20h ; ' '
0x18000d657  inc     edi
0x18000d659  cmp     edi, eax
0x18000d65b  jb      short loc_18000D613
0x18000d65d  jmp     loc_18000D417
0x18000d662  mov     ebx, 57h ; 'W'
0x18000d667  jmp     loc_18000D2C5
0x18000d66c  cmp     [rsi+8], r14
0x18000d670  jnz     short loc_18000D679
0x18000d672  mov     [rsi+8], r12
0x18000d676  mov     [rsi], r12d
0x18000d679  call    cs:__imp_GetProcessHeap
0x18000d67f  mov     r8, r14; lpMem
0x18000d682  xor     edx, edx; dwFlags
0x18000d684  mov     rcx, rax; hHeap
0x18000d687  call    cs:__imp_HeapFree
0x18000d68d  jmp     loc_18000D357
```
