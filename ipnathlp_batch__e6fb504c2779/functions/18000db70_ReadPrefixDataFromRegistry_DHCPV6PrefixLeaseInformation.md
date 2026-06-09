# ReadPrefixDataFromRegistry(_DHCPV6PrefixLeaseInformation *)

- ea: `0x18000db70`
- end: `0x18000e0a5`
- name: `?ReadPrefixDataFromRegistry@@YAKPEAU_DHCPV6PrefixLeaseInformation@@@Z`
- size: `1333`
- prototype: `__int64 __fastcall(struct _DHCPV6PrefixLeaseInformation *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000ca50`
- `0x18003ba60`
- `0x18006aab8`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000db70`
- `0x18003313c`
- `0x180051f30`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e080`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e080`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dda8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000de4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dda8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000de4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e094`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dd68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000de16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000de94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dece`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000df0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000df51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000df93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dfd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e04a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dd68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000de16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000de94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dece`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000df0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000df51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000df93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dfd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e04a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dc75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dc75`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dc55`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dc55`

## string_xrefs

- `0x18000dc22`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
0x18000db70  mov     r11, rsp
0x18000db73  push    rbp
0x18000db74  push    rbx
0x18000db75  lea     rbp, [r11-1C8h]
0x18000db7c  sub     rsp, 2B8h
0x18000db83  mov     rax, cs:__security_cookie
0x18000db8a  xor     rax, rsp
0x18000db8d  mov     [rbp+1C0h+var_30], rax
0x18000db94  mov     [r11+10h], rsi
0x18000db98  mov     rsi, rcx
0x18000db9b  mov     [r11+20h], r12
0x18000db9f  mov     [r11-18h], r13
0x18000dba3  mov     [r11-20h], r14
0x18000dba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbae  lea     r13, WPP_GLOBAL_Control
0x18000dbb5  cmp     rcx, r13
0x18000dbb8  jz      short loc_18000DBCA
0x18000dbba  test    byte ptr [rcx+1Ch], 80h
0x18000dbbe  jz      short loc_18000DBCA
0x18000dbc0  cmp     byte ptr [rcx+19h], 6
0x18000dbc4  jnb     loc_18000DFF0
0x18000dbca  xor     r12d, r12d
0x18000dbcd  mov     [rsp+2C0h+arg_10], rdi
0x18000dbd5  xor     edx, edx; Val
0x18000dbd7  mov     dword ptr [rsp+2C0h+Data], r12d
0x18000dbdc  mov     r8d, 208h; Size
0x18000dbe2  mov     dword ptr [rsp+2C0h+var_258], r12d
0x18000dbe7  lea     rcx, [rbp+1C0h+ValueName]; void *
0x18000dbeb  mov     dword ptr [rsp+2C0h+var_254], r12d
0x18000dbf0  mov     dword ptr [rsp+2C0h+var_250], r12d
0x18000dbf5  mov     [rsp+2C0h+var_248], r12d
0x18000dbfa  mov     dword ptr [rsp+2C0h+var_24C], r12d
0x18000dbff  mov     [rsp+2C0h+cbData], r12d
0x18000dc04  mov     [rsp+2C0h+dwDisposition], r12d
0x18000dc09  mov     [rsp+2C0h+hKey], r12
0x18000dc0e  call    memset_0
0x18000dc13  lea     rax, [rsp+2C0h+dwDisposition]
0x18000dc18  mov     dword ptr [rsp+2C0h+var_25C], r12d
0x18000dc1d  mov     [rsp+40h], rax; lpdwDisposition
0x18000dc22  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18000dc29  lea     rax, [rsp+2C0h+hKey]
0x18000dc2e  xor     r9d, r9d; lpClass
0x18000dc31  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18000dc36  xor     r8d, r8d; Reserved
0x18000dc39  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000dc3e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dc45  mov     [rsp+2C0h+samDesired], 0F003Fh; samDesired
0x18000dc4d  mov     r14d, r12d
0x18000dc50  mov     [rsp+2C0h+dwOptions], r12d; dwOptions
0x18000dc55  call    cs:__imp_RegCreateKeyExW
0x18000dc5c  nop     dword ptr [rax+rax+00h]
0x18000dc61  mov     ebx, eax
0x18000dc63  test    eax, eax
0x18000dc65  jz      loc_18000DD3A
0x18000dc6b  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000dc70  test    rcx, rcx
0x18000dc73  jz      short loc_18000DC81
0x18000dc75  call    cs:__imp_RegCloseKey
0x18000dc7c  nop     dword ptr [rax+rax+00h]
0x18000dc81  test    ebx, ebx
0x18000dc83  jnz     short loc_18000DCFB
0x18000dc85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc8c  mov     r14, [rsp+2C0h+var_18]
0x18000dc94  cmp     rcx, r13
0x18000dc97  mov     r13, [rsp+2B0h]
0x18000dc9f  mov     r12, [rsp+2C0h+arg_18]
0x18000dca7  mov     rdi, [rsp+2C0h+arg_10]
0x18000dcaf  mov     rsi, [rsp+2C0h+arg_8]
0x18000dcb7  jnz     short loc_18000DCD5
0x18000dcb9  mov     eax, ebx
0x18000dcbb  mov     rcx, [rbp+1C0h+var_30]
0x18000dcc2  xor     rcx, rsp; StackCookie
0x18000dcc5  call    __security_check_cookie
0x18000dcca  add     rsp, 2B8h
0x18000dcd1  pop     rbx
0x18000dcd2  pop     rbp
0x18000dcd3  retn
0x18000dcd5  test    byte ptr [rcx+1Ch], 80h
0x18000dcd9  jz      short loc_18000DCB9
0x18000dcdb  cmp     byte ptr [rcx+19h], 6
0x18000dcdf  jb      short loc_18000DCB9
0x18000dce1  mov     rcx, [rcx+10h]
0x18000dce5  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000dcec  mov     edx, 0Bh
0x18000dcf1  mov     r9d, ebx
0x18000dcf4  call    WPP_SF_d
0x18000dcf9  jmp     short loc_18000DCB9
0x18000dcfb  test    r14, r14
0x18000dcfe  jnz     loc_18000E073
0x18000dd04  mov     rdi, [rsi+40h]
0x18000dd08  test    rdi, rdi
0x18000dd0b  jz      loc_18000DC85
0x18000dd11  call    cs:__imp_GetProcessHeap
0x18000dd18  nop     dword ptr [rax+rax+00h]
0x18000dd1d  mov     r8, rdi; lpMem
0x18000dd20  xor     edx, edx; dwFlags
0x18000dd22  mov     rcx, rax; hHeap
0x18000dd25  call    cs:__imp_HeapFree
0x18000dd2c  nop     dword ptr [rax+rax+00h]
0x18000dd31  mov     [rsi+40h], r12
0x18000dd35  jmp     loc_18000DC85
0x18000dd3a  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000dd3f  lea     rax, [rsp+2C0h+cbData]
0x18000dd44  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000dd49  lea     rdx, ValueName; "NumberOfPrefixes"
0x18000dd50  lea     rax, [rsp+2C0h+Data]
0x18000dd55  mov     [rsp+2C0h+cbData], 4
0x18000dd5d  xor     r9d, r9d; lpType
0x18000dd60  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000dd65  xor     r8d, r8d; lpReserved
0x18000dd68  call    cs:__imp_RegQueryValueExW
0x18000dd6f  nop     dword ptr [rax+rax+00h]
0x18000dd74  mov     ebx, eax
0x18000dd76  test    eax, eax
0x18000dd78  jnz     loc_18000DC6B
0x18000dd7e  mov     eax, dword ptr [rsp+2C0h+Data]
0x18000dd82  test    eax, eax
0x18000dd84  jz      loc_18000E00A
0x18000dd8a  shl     eax, 5
0x18000dd8d  mov     ebx, eax
0x18000dd8f  call    cs:__imp_GetProcessHeap
0x18000dd96  nop     dword ptr [rax+rax+00h]
0x18000dd9b  mov     r8d, ebx; dwBytes
0x18000dd9e  mov     ebx, 8
0x18000dda3  mov     edx, ebx; dwFlags
0x18000dda5  mov     rcx, rax; hHeap
0x18000dda8  call    cs:__imp_HeapAlloc
0x18000ddaf  nop     dword ptr [rax+rax+00h]
0x18000ddb4  mov     r14, rax
0x18000ddb7  test    rax, rax
0x18000ddba  jz      loc_18000DC6B
0x18000ddc0  mov     [rsp+2C0h+var_20], r15
0x18000ddc8  mov     edi, r12d
0x18000ddcb  mov     r15, rax
0x18000ddce  mov     [rsp+2C0h+cbData], 20h ; ' '
0x18000ddd6  mov     eax, dword ptr [rsp+2C0h+Data]
0x18000ddda  test    eax, eax
0x18000dddc  jnz     loc_18000E014
0x18000dde2  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000dde7  lea     rdx, aIcsIpv6Dhcpv6s_0; "ICS_IPv6_Dhcpv6ServerIDLen"
0x18000ddee  mov     [rsi], eax
0x18000ddf0  xor     r9d, r9d; lpType
0x18000ddf3  lea     rax, [rsp+2C0h+cbData]
0x18000ddf8  mov     [rsi+8], r14
0x18000ddfc  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000de01  xor     r8d, r8d; lpReserved
0x18000de04  lea     rax, [rsp+2C0h+var_25C]
0x18000de09  mov     [rsp+2C0h+cbData], 4
0x18000de11  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000de16  call    cs:__imp_RegQueryValueExW
0x18000de1d  nop     dword ptr [rax+rax+00h]
0x18000de22  mov     eax, dword ptr [rsp+2C0h+var_25C]
0x18000de26  mov     r15, [rsp+2C0h+var_20]
0x18000de2e  test    eax, eax
0x18000de30  jz      loc_18000E069
0x18000de36  mov     [rsi+48h], eax
0x18000de39  mov     edi, eax
0x18000de3b  call    cs:__imp_GetProcessHeap
0x18000de42  nop     dword ptr [rax+rax+00h]
0x18000de47  mov     r8d, edi; dwBytes
0x18000de4a  mov     edx, ebx; dwFlags
0x18000de4c  mov     rcx, rax; hHeap
0x18000de4f  call    cs:__imp_HeapAlloc
0x18000de56  nop     dword ptr [rax+rax+00h]
0x18000de5b  mov     [rsi+40h], rax
0x18000de5f  mov     rcx, rax
0x18000de62  test    rax, rax
0x18000de65  jz      loc_18000DC6B
0x18000de6b  mov     eax, dword ptr [rsp+2C0h+var_25C]
0x18000de6f  lea     rdx, aIcsIpv6Dhcpv6s; "ICS_IPv6_Dhcpv6ServerID"
0x18000de76  mov     [rsp+2C0h+cbData], eax
0x18000de7a  xor     r9d, r9d; lpType
0x18000de7d  lea     rax, [rsp+2C0h+cbData]
0x18000de82  xor     r8d, r8d; lpReserved
0x18000de85  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000de8a  mov     qword ptr [rsp+2C0h+dwOptions], rcx; lpData
0x18000de8f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000de94  call    cs:__imp_RegQueryValueExW
0x18000de9b  nop     dword ptr [rax+rax+00h]
0x18000dea0  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000dea5  lea     rax, [rsp+2C0h+cbData]
0x18000deaa  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000deaf  lea     rdx, aIcsIpv6Iaid; "ICS_IPv6_iaid"
0x18000deb6  lea     rax, [rsp+2C0h+var_258]
0x18000debb  mov     [rsp+2C0h+cbData], 4
0x18000dec3  xor     r9d, r9d; lpType
0x18000dec6  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000decb  xor     r8d, r8d; lpReserved
0x18000dece  call    cs:__imp_RegQueryValueExW
0x18000ded5  nop     dword ptr [rax+rax+00h]
0x18000deda  mov     eax, dword ptr [rsp+2C0h+var_258]
0x18000dede  lea     rdx, aIcsIpv6T1; "ICS_IPv6_T1"
0x18000dee5  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000deea  xor     r9d, r9d; lpType
0x18000deed  mov     [rsi+10h], eax
0x18000def0  xor     r8d, r8d; lpReserved
0x18000def3  lea     rax, [rsp+2C0h+cbData]
0x18000def8  mov     [rsp+2C0h+cbData], 4
0x18000df00  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000df05  lea     rax, [rsp+2C0h+var_254]
0x18000df0a  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000df0f  call    cs:__imp_RegQueryValueExW
0x18000df16  nop     dword ptr [rax+rax+00h]
0x18000df1b  mov     eax, dword ptr [rsp+2C0h+var_254]
0x18000df1f  lea     rdx, aIcsIpv6T2; "ICS_IPv6_T2"
0x18000df26  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000df2b  xor     r9d, r9d; lpType
0x18000df2e  mov     [rsi+18h], rax
0x18000df32  xor     r8d, r8d; lpReserved
0x18000df35  lea     rax, [rsp+2C0h+cbData]
0x18000df3a  mov     [rsp+2C0h+cbData], 4
0x18000df42  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000df47  lea     rax, [rsp+2C0h+var_250]
0x18000df4c  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000df51  call    cs:__imp_RegQueryValueExW
0x18000df58  nop     dword ptr [rax+rax+00h]
0x18000df5d  mov     eax, dword ptr [rsp+2C0h+var_250]
0x18000df61  lea     rdx, aIcsIpv6Dhcpv6l; "ICS_IPv6_Dhcpv6LastRenewalTime"
0x18000df68  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000df6d  xor     r9d, r9d; lpType
0x18000df70  mov     [rsi+20h], rax
0x18000df74  xor     r8d, r8d; lpReserved
0x18000df77  lea     rax, [rsp+2C0h+cbData]
0x18000df7c  mov     [rsp+2C0h+cbData], 4
0x18000df84  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000df89  lea     rax, [rsp+2C0h+var_24C]
0x18000df8e  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000df93  call    cs:__imp_RegQueryValueExW
0x18000df9a  nop     dword ptr [rax+rax+00h]
0x18000df9f  mov     eax, dword ptr [rsp+2C0h+var_24C]
0x18000dfa3  lea     rdx, aIcsIpv6Dhcpv6m; "ICS_IPv6_Dhcpv6MaxLeaseExpirationTime"
0x18000dfaa  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000dfaf  xor     r9d, r9d; lpType
0x18000dfb2  mov     [rsi+30h], rax
0x18000dfb6  xor     r8d, r8d; lpReserved
0x18000dfb9  lea     rax, [rsp+2C0h+cbData]
0x18000dfbe  mov     [rsp+2C0h+cbData], 4
0x18000dfc6  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000dfcb  lea     rax, [rsp+2C0h+var_248]
0x18000dfd0  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x18000dfd5  call    cs:__imp_RegQueryValueExW
0x18000dfdc  nop     dword ptr [rax+rax+00h]
0x18000dfe1  mov     ebx, eax
0x18000dfe3  mov     eax, [rsp+2C0h+var_248]
0x18000dfe7  mov     [rsi+28h], rax
0x18000dfeb  jmp     loc_18000DC6B
0x18000dff0  mov     rcx, [rcx+10h]
0x18000dff4  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18000dffb  mov     edx, 0Ah
0x18000e000  call    WPP_SF_
0x18000e005  jmp     loc_18000DBCA
0x18000e00a  mov     ebx, 57h ; 'W'
0x18000e00f  jmp     loc_18000DC6B
0x18000e014  mov     r9d, edi
0x18000e017  lea     r8, aIcsIpv6PrefixD; "ICS_IPv6_Prefix_%d"
0x18000e01e  mov     edx, 104h; unsigned __int64
0x18000e023  lea     rcx, [rbp+1C0h+ValueName]; unsigned __int16 *
0x18000e027  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e02c  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18000e031  lea     rax, [rsp+2C0h+cbData]
0x18000e036  mov     qword ptr [rsp+2C0h+samDesired], rax; lpcbData
0x18000e03b  lea     rdx, [rbp+1C0h+ValueName]; lpValueName
0x18000e03f  xor     r9d, r9d; lpType
0x18000e042  mov     qword ptr [rsp+2C0h+dwOptions], r15; lpData
0x18000e047  xor     r8d, r8d; lpReserved
0x18000e04a  call    cs:__imp_RegQueryValueExW
0x18000e051  nop     dword ptr [rax+rax+00h]
0x18000e056  mov     eax, dword ptr [rsp+2C0h+Data]
0x18000e05a  add     r15, 20h ; ' '
0x18000e05e  inc     edi
0x18000e060  cmp     edi, eax
0x18000e062  jb      short loc_18000E014
0x18000e064  jmp     loc_18000DDE2
0x18000e069  mov     ebx, 57h ; 'W'
0x18000e06e  jmp     loc_18000DC6B
0x18000e073  cmp     [rsi+8], r14
0x18000e077  jnz     short loc_18000E080
0x18000e079  mov     [rsi+8], r12
0x18000e07d  mov     [rsi], r12d
0x18000e080  call    cs:__imp_GetProcessHeap
0x18000e087  nop     dword ptr [rax+rax+00h]
0x18000e08c  mov     r8, r14; lpMem
0x18000e08f  xor     edx, edx; dwFlags
0x18000e091  mov     rcx, rax; hHeap
0x18000e094  call    cs:__imp_HeapFree
0x18000e09b  nop     dword ptr [rax+rax+00h]
0x18000e0a0  jmp     loc_18000DD04
```
